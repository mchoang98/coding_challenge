# Bài 36. Kỹ thuật Two Pointers

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu kỹ thuật **Two Pointers**.
- Biết hai dạng phổ biến:
  - Hai con trỏ ở hai đầu.
  - Hai con trỏ cùng chiều.
- Nhận biết điều kiện để áp dụng:
  - Dãy đã sắp xếp.
  - Tổng đoạn có tính đơn điệu.

## 2. Về kỹ năng

- Tìm cặp có tổng bằng $S$.
- Đếm cặp có tổng không vượt quá $S$.
- Tìm đoạn dài nhất có tổng không vượt quá $S$ với dãy không âm.
- Tìm đoạn ngắn nhất có tổng ít nhất $S$.

## 3. Về tư duy

- Hiểu vì sao mỗi con trỏ chỉ di chuyển một chiều.
- Biết giảm độ phức tạp từ $O(N^2)$ xuống $O(N)$ trong các bài phù hợp.

---

# II. Lý thuyết

## 1. Hai con trỏ ở hai đầu

Áp dụng cho dãy đã sắp xếp.

Ví dụ tìm cặp tổng bằng $S$:

- Nếu tổng nhỏ hơn $S$, tăng con trỏ trái.
- Nếu tổng lớn hơn $S$, giảm con trỏ phải.
- Nếu bằng $S$, tìm thấy.

## 2. Hai con trỏ cùng chiều

Áp dụng cho bài toán đoạn liên tiếp.

Ví dụ:

- Đoạn dài nhất có tổng không vượt quá $S$.
- Đoạn ngắn nhất có tổng ít nhất $S$.

## 3. Vì sao nhanh?

Mỗi con trỏ chỉ tăng hoặc giảm tối đa $N$ lần.

Độ phức tạp thường là:

$O(N)$

---

# III. Ví dụ minh họa

## Ví dụ 1. Tìm cặp có tổng bằng S

```python
n, s = map(int, input().split())
a = list(map(int, input().split()))

left = 0
right = n - 1
found = False

while left < right:
    total = a[left] + a[right]

    if total == s:
        found = True
        break
    elif total < s:
        left += 1
    else:
        right -= 1

print("YES" if found else "NO")
```

---

## Ví dụ 2. Đếm cặp có tổng không vượt quá S

```python
n, s = map(int, input().split())
a = list(map(int, input().split()))

left = 0
right = n - 1
count = 0

while left < right:
    if a[left] + a[right] <= s:
        count += right - left
        left += 1
    else:
        right -= 1

print(count)
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

## Bài 1. Cặp tổng bằng S

Cho dãy đã sắp xếp.  
Kiểm tra có hai phần tử tổng bằng $S$ hay không.

## Bài 2. Đếm cặp tổng nhỏ hơn S

Đếm số cặp chỉ số có tổng nhỏ hơn $S$.

## Bài 3. Cặp có hiệu bằng K

Cho dãy tăng dần.  
Kiểm tra tồn tại cặp có hiệu đúng bằng $K$.

## Bài 4. Đoạn dài nhất tổng không vượt quá S

Dãy không âm.

## Bài 5. Đoạn ngắn nhất tổng ít nhất S

Dãy không âm.

---

# V. Bài tập về nhà

## Bài 1. Cặp gần S nhất

Tìm cặp có tổng gần $S$ nhất.

## Bài 2. Ba phần tử tổng bằng S

Dùng một vòng ngoài và two pointers bên trong.

## Bài 3. Gộp hai dãy đã sắp xếp

Dùng hai con trỏ để trộn hai mảng.

## Bài 4. Loại trùng trong dãy đã sắp xếp

In mỗi giá trị đúng một lần.

---

# VI. Lỗi học sinh thường gặp

- Dùng two pointers cho dãy chưa sắp xếp mà không xử lý trước.
- Tăng giảm con trỏ sai hướng.
- Quên điều kiện `left < right`.
- Không trừ phần tử rời cửa sổ khi tăng `left`.
- Dùng cửa sổ tổng cho dãy có số âm.

---

# VII. Đề thi thật và bài chuẩn chuyên

## Đề 1. Đếm cặp tổng không vượt quá S

Cho dãy đã sắp xếp.  
Đếm số cặp hợp lệ.

## Đề 2. Đoạn quà hợp lệ

Cho dãy không âm.  
Tìm đoạn dài nhất có tổng không vượt ngưỡng.

## Đề 3. Hiệu đúng K

Cho dãy tăng dần.  
Kiểm tra tồn tại cặp chênh lệch $K$.

---

# VIII. Ghi nhớ cuối bài

- Two pointers là kỹ thuật rất quan trọng để tránh hai vòng lặp.
- Điều kiện áp dụng phải được kiểm tra kỹ.
- Nếu mỗi con trỏ chỉ đi một chiều, tổng độ phức tạp thường là $O(N)$.

---

# IX. Tóm tắt bài học

## Mẫu cùng chiều

```python
left = 0

for right in range(n):
    ...

    while condition_broken:
        left += 1
```
