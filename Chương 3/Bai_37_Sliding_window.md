# Bài 37. Sliding Window

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu kỹ thuật **Sliding Window**.
- Phân biệt:
  - Cửa sổ độ dài cố định.
  - Cửa sổ co giãn.
- Biết sliding window liên quan chặt chẽ tới two pointers.

## 2. Về kỹ năng

- Tính tổng lớn nhất của đoạn dài $K$.
- Đếm số giá trị khác nhau trong cửa sổ dài $K$.
- Tìm đoạn dài nhất có tổng không vượt quá $S$.
- Duy trì trạng thái cửa sổ khi trượt.

## 3. Về tư duy

- Thay vì tính lại từ đầu, chỉ cập nhật phần thêm vào và phần rời đi.
- Biết duy trì một cấu trúc trạng thái của đoạn hiện tại.

---

# II. Lý thuyết

## 1. Sliding Window là gì?

Sliding Window là kỹ thuật duy trì thông tin của một đoạn liên tiếp khi đoạn đó dịch dần sang phải.

## 2. Cửa sổ cố định

Ví dụ đoạn có đúng $K$ phần tử.

Khi cửa sổ dịch sang phải:

$new = old - phần\ tử\ rời\ đi + phần\ tử\ mới$

## 3. Cửa sổ co giãn

Độ dài cửa sổ thay đổi tùy điều kiện.

Ví dụ:

- Tổng không vượt quá $S$.
- Có nhiều nhất $K$ giá trị khác nhau.

## 4. Độ phức tạp

Nhiều bài giảm từ:

$O(NK)$

xuống:

$O(N)$

---

# III. Ví dụ minh họa

## Ví dụ 1. Tổng lớn nhất đoạn K

```python
n, k = map(int, input().split())
a = list(map(int, input().split()))

current_sum = sum(a[:k])
best = current_sum

for right in range(k, n):
    current_sum += a[right]
    current_sum -= a[right - k]
    best = max(best, current_sum)

print(best)
```

---

## Ví dụ 2. Số lượng giá trị khác nhau trong mỗi đoạn K

```python
n, k = map(int, input().split())
a = list(map(int, input().split()))

freq = {}

for i in range(k):
    freq[a[i]] = freq.get(a[i], 0) + 1

print(len(freq))

for right in range(k, n):
    remove_value = a[right - k]
    freq[remove_value] -= 1

    if freq[remove_value] == 0:
        del freq[remove_value]

    add_value = a[right]
    freq[add_value] = freq.get(add_value, 0) + 1

    print(len(freq))
```

---

## Ví dụ 3. Đoạn dài nhất có tổng không vượt quá S

```python
n, s = map(int, input().split())
a = list(map(int, input().split()))

left = 0
current_sum = 0
best = 0

for right in range(n):
    current_sum += a[right]

    while current_sum > s:
        current_sum -= a[left]
        left += 1

    best = max(best, right - left + 1)

print(best)
```

---

# IV. Bài tập vận dụng

## Bài 1. Tổng nhỏ nhất của đoạn dài K

## Bài 2. Trung bình lớn nhất của đoạn dài K

## Bài 3. Đếm số chẵn trong mỗi cửa sổ dài K

## Bài 4. Tìm số lượng giá trị khác nhau lớn nhất trong một đoạn dài K

## Bài 5. Đoạn dài nhất có tổng không vượt quá S

## Bài 6. Đoạn ngắn nhất có tổng ít nhất S

---

# V. Bài tập về nhà

## Bài 1. Đoạn dài K có nhiều số nguyên tố nhất

## Bài 2. Cửa sổ có đúng T giá trị khác nhau

## Bài 3. Xâu con dài K có nhiều nguyên âm nhất

## Bài 4. Đoạn dài nhất chứa không quá K giá trị khác nhau

## Bài 5. Đếm cửa sổ dài K có tổng chia hết cho M

---

# VI. Lỗi học sinh thường gặp

- Quên xử lý cửa sổ đầu tiên.
- Cập nhật sai phần tử rời khỏi cửa sổ.
- Không xóa khóa khi tần suất về `0`.
- Dùng cửa sổ co giãn với dãy có số âm mà không kiểm tra tính đúng.
- Nhầm bài cửa sổ cố định với bài hai con trỏ co giãn.

---

# VII. Đề thi thật và bài chuẩn chuyên

## Đề 1. Tổng lớn nhất đoạn K phần tử

## Đề 2. Số lượng giá trị khác nhau trong từng cửa sổ

## Đề 3. Đoạn dài nhất có tổng không vượt quá S

## Đề 4. Xâu con dài K có nhiều ký tự khác nhau nhất

---

# VIII. Ghi nhớ cuối bài

- Sliding window dùng cho đoạn liên tiếp.
- Cửa sổ cố định cập nhật bằng cách thêm một, bớt một.
- Cửa sổ co giãn thường đi cùng two pointers.

---

# IX. Tóm tắt bài học

## Mẫu cửa sổ cố định

```python
current = initial_window

for right in range(k, n):
    current += add_value
    current -= remove_value
```
