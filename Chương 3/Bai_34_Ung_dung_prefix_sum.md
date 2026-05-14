# Bài 34. Ứng dụng Prefix Sum: tổng đoạn, đếm đoạn và truy vấn nhanh

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Củng cố công thức prefix sum.
- Biết áp dụng prefix vào:
  - Đếm điều kiện trong đoạn.
  - Tổng theo điều kiện.
  - Duyệt đoạn có độ dài cố định.
- Hiểu rằng nhiều bài toán đoạn có thể quy về hiệu hai prefix.

## 2. Về kỹ năng

- Tạo prefix cho số lượng số chẵn, số dương, số nguyên tố.
- Tính tổng lớn nhất của đoạn dài $K$.
- Kiểm tra tổng một đoạn có bằng một giá trị cho trước hay không.

## 3. Về tư duy

- Biết chọn đúng đại lượng để cộng dồn.
- Nhận ra prefix không chỉ dùng cho tổng toàn bộ giá trị.

---

# II. Lý thuyết

## 1. Prefix theo điều kiện

Nếu cần đếm số chẵn trong đoạn, ta xây mảng:

$b_i = 1$ nếu $a_i$ chẵn, ngược lại $b_i = 0$

Sau đó prefix hóa dãy $b$.

## 2. Prefix tổng theo điều kiện

Nếu cần tổng các số dương trong đoạn, ta xây:

$b_i = a_i$ nếu $a_i > 0$, ngược lại $b_i = 0$

## 3. Đoạn dài cố định K

Nếu đoạn kết thúc ở vị trí $R$, thì:

$L = R - K + 1$

Tổng đoạn:

$prefix[R] - prefix[L-1]$

## 4. Kiểm tra tổng đoạn bằng S

Ta chỉ cần tính tổng bằng prefix rồi so sánh với $S$.

## 5. Độ phức tạp

- Tiền xử lý: $O(N)$
- Mỗi truy vấn: $O(1)$
- Duyệt toàn bộ các đoạn dài $K$: $O(N)$

---

# III. Ví dụ minh họa

## Ví dụ 1. Tổng số dương trong đoạn

```python
n, q = map(int, input().split())
a = list(map(int, input().split()))

prefix_positive = [0] * (n + 1)

for i in range(1, n + 1):
    value = a[i - 1] if a[i - 1] > 0 else 0
    prefix_positive[i] = prefix_positive[i - 1] + value

for _ in range(q):
    l, r = map(int, input().split())
    print(prefix_positive[r] - prefix_positive[l - 1])
```

---

## Ví dụ 2. Tổng lớn nhất của đoạn dài K

```python
n, k = map(int, input().split())
a = list(map(int, input().split()))

prefix = [0] * (n + 1)

for i in range(1, n + 1):
    prefix[i] = prefix[i - 1] + a[i - 1]

best = None

for r in range(k, n + 1):
    l = r - k + 1
    current_sum = prefix[r] - prefix[l - 1]

    if best is None or current_sum > best:
        best = current_sum

print(best)
```

---

## Ví dụ 3. Kiểm tra đoạn có tổng bằng S

```python
n = int(input())
a = list(map(int, input().split()))
l, r, s = map(int, input().split())

prefix = [0] * (n + 1)

for i in range(1, n + 1):
    prefix[i] = prefix[i - 1] + a[i - 1]

segment_sum = prefix[r] - prefix[l - 1]

print("YES" if segment_sum == s else "NO")
```

---

# IV. Bài tập vận dụng

## Bài 1. Đếm số âm trong đoạn

Dùng prefix theo điều kiện.

## Bài 2. Tổng phần tử chia hết cho K trong đoạn

Tạo dãy phụ chỉ giữ các giá trị chia hết cho $K$.

## Bài 3. Tổng bình phương trong đoạn

Tạo prefix của $a_i^2$.

## Bài 4. Tổng nhỏ nhất của đoạn dài K

Duyệt mọi đoạn dài $K$ bằng prefix.

## Bài 5. Có đoạn dài K nào tổng bằng S?

Kiểm tra tất cả đoạn dài $K$.

---

# V. Bài tập về nhà

## Bài 1. Tìm đoạn dài K có nhiều số chẵn nhất

Dùng prefix đếm số chẵn.

## Bài 2. Tính chênh lệch số chẵn và số lẻ trong đoạn

Dùng hai mảng prefix hoặc một mảng quy đổi.

## Bài 3. Tổng chữ số trong đoạn xâu

Xâu chỉ gồm chữ số.  
Mỗi truy vấn hỏi tổng đoạn.

## Bài 4. Đếm ký tự A trong đoạn

Cho xâu `A/B`.  
Trả lời nhiều truy vấn.

---

# VI. Lỗi học sinh thường gặp

- Không xác định đúng đại lượng cần prefix.
- Dùng prefix tổng khi cần prefix đếm.
- Sai công thức đoạn độ dài cố định.
- Không xử lý trường hợp `best` ban đầu.
- Tưởng prefix tự giải mọi bài đoạn, trong khi một số bài cần kỹ thuật khác.

---

# VII. Đề thi thật và bài chuẩn chuyên

## Đề 1. Tổng lớn nhất đoạn K phần tử

Cho dãy và $K$.  
Tìm tổng lớn nhất của một đoạn liên tiếp độ dài $K$.

## Đề 2. Đếm số nguyên tố trong đoạn

Cho dãy số và nhiều truy vấn.  
Đếm số phần tử nguyên tố trong mỗi đoạn.

## Đề 3. Tổng chữ số theo đoạn

Cho xâu số dài.  
Trả lời tổng chữ số trong nhiều đoạn.

---

# VIII. Ghi nhớ cuối bài

- Prefix sum rất mạnh khi bài toán có nhiều truy vấn đoạn.
- Muốn đếm điều kiện, hãy biến điều kiện thành `0` hoặc `1`.
- Muốn tính tổng theo điều kiện, giữ giá trị cần cộng, còn lại gán `0`.

---

# IX. Tóm tắt bài học

## Mẫu tư duy

1. Xác định cần cộng dồn gì.
2. Tạo mảng phụ.
3. Tạo prefix.
4. Trả lời truy vấn bằng hiệu hai prefix.
