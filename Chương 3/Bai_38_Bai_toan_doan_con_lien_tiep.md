# Bài 38. Bài toán đoạn con liên tiếp

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu khái niệm **đoạn con liên tiếp**.
- Phân biệt đoạn con với dãy con.
- Biết số lượng đoạn con của dãy $N$ phần tử.
- Nhận diện các dạng:
  - Đếm đoạn.
  - Tổng đoạn.
  - Đoạn dài nhất.
  - Đoạn thỏa điều kiện.

## 2. Về kỹ năng

- Duyệt các đoạn con bằng hai vòng lặp.
- Tính tổng các đoạn bằng cách cộng dồn.
- Dùng prefix hoặc sliding window khi phù hợp.

## 3. Về tư duy

- Hiểu rằng bài toán đoạn con là nền tảng rất phổ biến trong thi thuật toán.
- Biết tối ưu dần từ cách duyệt thô.

---

# II. Lý thuyết

## 1. Số lượng đoạn con

Với dãy $N$ phần tử, số đoạn con liên tiếp là:

$\frac{N(N+1)}{2}$

## 2. Duyệt mọi đoạn

- Chọn đầu trái `L`.
- Chọn đầu phải `R`.

Có $O(N^2)$ đoạn.

## 3. Tính tổng từng đoạn

Nếu với mỗi đoạn lại duyệt từ `L` đến `R`, thời gian là $O(N^3)$.

Nếu cộng dồn khi mở rộng `R`, giảm còn $O(N^2)$.

## 4. Công cụ tối ưu

- Prefix sum: tính tổng đoạn nhanh.
- Sliding window: khi dãy không âm và điều kiện có tính đơn điệu.

---

# III. Ví dụ minh họa

## Ví dụ 1. Đếm số đoạn con

```python
n = int(input())

print(n * (n + 1) // 2)
```

---

## Ví dụ 2. In tổng từng đoạn bằng O(N²)

```python
n = int(input())
a = list(map(int, input().split()))

for left in range(n):
    current_sum = 0

    for right in range(left, n):
        current_sum += a[right]
        print(left + 1, right + 1, current_sum)
```

---

## Ví dụ 3. Đếm đoạn có tổng không vượt quá S với dãy không âm

```python
n, s = map(int, input().split())
a = list(map(int, input().split()))

left = 0
current_sum = 0
count = 0

for right in range(n):
    current_sum += a[right]

    while current_sum > s:
        current_sum -= a[left]
        left += 1

    count += right - left + 1

print(count)
```

---

# IV. Bài tập vận dụng

## Bài 1. Số lượng đoạn con

## Bài 2. Tổng mọi đoạn con

## Bài 3. Đếm đoạn có tổng bằng K bằng cách $O(N^2)$

## Bài 4. Đếm đoạn có tổng không vượt quá S với dãy không âm

## Bài 5. Đoạn dài nhất có tổng không vượt quá S

## Bài 6. Đoạn có tổng lớn nhất bằng cách $O(N^2)$

---

# V. Bài tập về nhà

## Bài 1. Đếm đoạn toàn số chẵn

## Bài 2. Đếm đoạn chứa ít nhất một phần tử lớn hơn hoặc bằng M

## Bài 3. Đoạn không chứa số âm dài nhất

## Bài 4. Đoạn có tổng bằng 0 dài nhất

## Bài 5. Đếm đoạn chứa đúng K số nguyên tố

---

# VI. Lỗi học sinh thường gặp

- Nhầm đoạn con với tập con.
- Nhầm công thức số đoạn với số cặp.
- Dùng sliding window cho dãy có số âm.
- Không cập nhật tổng dần khi duyệt đoạn.
- Không xác định rõ output là tổng, độ dài hay số lượng đoạn.

---

# VII. Đề thi thật và bài chuẩn chuyên

## Đề 1. Đếm đoạn có ít nhất một phần tử thỏa điều kiện

## Đề 2. Đoạn tổng bằng 0 dài nhất

## Đề 3. Đếm đoạn tổng không vượt quá S

## Đề 4. Tổng lớn nhất của đoạn con

---

# VIII. Ghi nhớ cuối bài

- Bài toán đoạn con là lõi của rất nhiều đề thi.
- Luôn nghĩ theo thứ tự:
  1. Duyệt thô.
  2. Cộng dồn.
  3. Prefix.
  4. Sliding window nếu áp dụng được.

---

# IX. Tóm tắt bài học

## Mẫu duyệt đoạn

```python
for left in range(n):
    current_sum = 0

    for right in range(left, n):
        current_sum += a[right]
```
