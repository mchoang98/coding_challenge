# Bài 33. Prefix Sum một chiều

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu khái niệm **tổng tiền tố**.
- Biết xây dựng mảng `prefix`.
- Nắm công thức tính tổng đoạn $[L, R]$.
- Hiểu vì sao prefix sum giúp trả lời truy vấn nhanh.

## 2. Về kỹ năng

- Tính tổng đoạn trong $O(1)$.
- Xử lý nhiều truy vấn tổng đoạn.
- Tạo prefix cho các đại lượng khác như số chẵn, số dương.

## 3. Về tư duy

- Biết tiền xử lý để giảm thời gian truy vấn.
- Chuyển từ duyệt lại đoạn nhiều lần sang dùng dữ liệu tích lũy.

---

# II. Lý thuyết

## 1. Định nghĩa

Cho dãy:

$a_1, a_2, ..., a_N$

Ta định nghĩa:

$prefix[i] = a_1 + a_2 + ... + a_i$

và:

$prefix[0] = 0$

## 2. Công thức xây dựng

$prefix[i] = prefix[i-1] + a_i$

## 3. Tổng đoạn [L, R]

$sum(L, R) = prefix[R] - prefix[L-1]$

## 4. Ví dụ

Dãy:

`3 1 4 1 5`

Prefix:

`0 3 4 8 9 14`

Tổng đoạn từ vị trí `2` đến `4` là:

$prefix[4] - prefix[1] = 9 - 3 = 6$

## 5. Độ phức tạp

- Xây prefix: $O(N)$
- Mỗi truy vấn: $O(1)$

---

# III. Ví dụ minh họa

## Ví dụ 1. Xây dựng prefix sum

```python
n = int(input())
a = list(map(int, input().split()))

prefix = [0] * (n + 1)

for i in range(1, n + 1):
    prefix[i] = prefix[i - 1] + a[i - 1]

print(*prefix[1:])
```

---

## Ví dụ 2. Nhiều truy vấn tổng đoạn

```python
n, q = map(int, input().split())
a = list(map(int, input().split()))

prefix = [0] * (n + 1)

for i in range(1, n + 1):
    prefix[i] = prefix[i - 1] + a[i - 1]

for _ in range(q):
    l, r = map(int, input().split())
    print(prefix[r] - prefix[l - 1])
```

---

## Ví dụ 3. Đếm số chẵn trong đoạn

```python
n, q = map(int, input().split())
a = list(map(int, input().split()))

prefix_even = [0] * (n + 1)

for i in range(1, n + 1):
    value = 1 if a[i - 1] % 2 == 0 else 0
    prefix_even[i] = prefix_even[i - 1] + value

for _ in range(q):
    l, r = map(int, input().split())
    print(prefix_even[r] - prefix_even[l - 1])
```

---

# IV. Bài tập vận dụng

## Bài 1. Tổng đoạn cơ bản

Cho một truy vấn $[L, R]$.  
Tính tổng đoạn.

## Bài 2. Nhiều truy vấn tổng đoạn

Trả lời $Q$ truy vấn bằng prefix sum.

## Bài 3. Đếm số dương trong đoạn

Tạo prefix theo điều kiện.

## Bài 4. Tổng số lẻ trong đoạn

Tạo prefix chỉ cộng các phần tử lẻ.

## Bài 5. Đếm phần tử chia hết cho K trong đoạn

Mỗi truy vấn trả lời trong $O(1)$.

---

# V. Bài tập về nhà

## Bài 1. Tổng bình phương trong đoạn

Cho dãy số.  
Với mỗi truy vấn, tính tổng bình phương phần tử.

## Bài 2. Tổng giá trị tuyệt đối trong đoạn

Cho dãy số nguyên.  
Tính tổng trị tuyệt đối.

## Bài 3. Đếm số nguyên tố trong đoạn

Dùng hàm kiểm tra nguyên tố rồi tạo prefix.

## Bài 4. Trung bình cộng đoạn

Tính tổng bằng prefix rồi chia cho độ dài đoạn.

---

# VI. Lỗi học sinh thường gặp

- Quên `prefix[0] = 0`.
- Nhầm chỉ số 0-based và 1-based.
- Dùng sai công thức $prefix[R] - prefix[L]$.
- Tạo prefix tổng giá trị khi bài cần đếm điều kiện.
- Duyệt lại đoạn trong từng truy vấn dù đã có prefix.

---

# VII. Đề thi thật và bài chuẩn chuyên

## Đề 1. Truy vấn tổng đoạn

Cho dãy số và nhiều truy vấn.  
Mỗi truy vấn hỏi tổng một đoạn.

## Đề 2. Đếm phần tử thỏa điều kiện

Cho dãy số.  
Đếm bao nhiêu phần tử chẵn trong từng đoạn.

## Đề 3. Xâu A/B

Cho xâu chỉ gồm `A` và `B`.  
Đếm số `A` trong mỗi đoạn truy vấn.

---

# VIII. Ghi nhớ cuối bài

- Prefix sum biến truy vấn đoạn từ chậm thành nhanh.
- Công thức phải nhớ:

$sum(L, R) = prefix[R] - prefix[L-1]$

- Có thể prefix hóa không chỉ tổng mà còn cả số lượng phần tử thỏa điều kiện.

---

# IX. Tóm tắt bài học

## Mẫu code chuẩn

```python
prefix = [0] * (n + 1)

for i in range(1, n + 1):
    prefix[i] = prefix[i - 1] + a[i - 1]
```

Truy vấn:

```python
ans = prefix[r] - prefix[l - 1]
```
