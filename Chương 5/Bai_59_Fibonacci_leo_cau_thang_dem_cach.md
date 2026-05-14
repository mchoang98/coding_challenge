# Bài 59. Fibonacci, leo cầu thang và bài toán đếm cách 1 chiều

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu nhóm bài **đếm số cách** trong DP 1 chiều.
- Nắm mối liên hệ giữa:
  - Fibonacci.
  - Leo cầu thang.
  - Lát gạch.
- Biết khi nào công thức chuyển dùng phép cộng.

## 2. Về kỹ năng

- Cài đặt DP bảng cho bài đếm cách.
- Xác định đúng `dp[0]`.
- Biết mở rộng từ 2 bước sang nhiều bước.

## 3. Về tư duy

- Với bài “đếm số cách”, thường:
  - Mỗi cách đến trạng thái hiện tại đến từ nhiều trạng thái trước.
  - Tổng số cách bằng tổng số cách của các trạng thái trước đó.

---

# II. Dạng tổng quát của bài đếm cách

## 1. Mẫu suy luận

Nếu để đến vị trí `i`, ta có thể đến từ:

- `i - 1`
- `i - 2`

thì:

\[
dp[i] = dp[i-1] + dp[i-2]
\]

---

## 2. Vì sao là phép cộng?

Vì:

- Mỗi cách đi tới `i-1` tạo ra một cách mới đi tới `i`.
- Mỗi cách đi tới `i-2` cũng tạo ra một cách mới đi tới `i`.
- Hai nhóm cách này không trùng nhau.

---

# III. Ví dụ 1 — Leo cầu thang

## 1. Đề bài

Có `N` bậc thang.  
Mỗi lần có thể bước:

- 1 bậc.
- 2 bậc.

Hỏi có bao nhiêu cách lên đúng bậc `N`?

---

## 2. Trạng thái

`dp[i]` là số cách lên đúng bậc `i`.

---

## 3. Điều kiện đầu

- `dp[0] = 1`: có 1 cách để đứng ở vị trí ban đầu — không làm gì.
- `dp[1] = 1`: chỉ có cách bước 1 bậc.

---

## 4. Công thức chuyển

\[
dp[i] = dp[i-1] + dp[i-2]
\]

---

## 5. Code Python

```python
n = int(input())

dp = [0] * (n + 1)
dp[0] = 1

if n >= 1:
    dp[1] = 1

for i in range(2, n + 1):
    dp[i] = dp[i - 1] + dp[i - 2]

print(dp[n])
```

---

# IV. Ví dụ 2 — Leo cầu thang bước 1, 2, 3

## 1. Công thức

\[
dp[i] = dp[i-1] + dp[i-2] + dp[i-3]
\]

---

## 2. Code Python

```python
n = int(input())

dp = [0] * (n + 1)
dp[0] = 1

for i in range(1, n + 1):
    if i - 1 >= 0:
        dp[i] += dp[i - 1]
    if i - 2 >= 0:
        dp[i] += dp[i - 2]
    if i - 3 >= 0:
        dp[i] += dp[i - 3]

print(dp[n])
```

---

# V. Ví dụ 3 — Lát gạch bảng 2 × N

## 1. Đề bài

Dùng domino `2 × 1` để lát kín bảng `2 × N`.

---

## 2. Ý tưởng

Để lát hết cột cuối:

- Đặt 1 viên domino đứng, còn lại là bảng `2 × (N-1)`.
- Đặt 2 viên domino nằm ngang, còn lại là bảng `2 × (N-2)`.

---

## 3. Công thức

\[
dp[n] = dp[n-1] + dp[n-2]
\]

---

## 4. Code Python

```python
n = int(input())

dp = [0] * (n + 1)
dp[0] = 1

if n >= 1:
    dp[1] = 1

for i in range(2, n + 1):
    dp[i] = dp[i - 1] + dp[i - 2]

print(dp[n])
```

---

# VI. Tối ưu bộ nhớ

Nếu công thức chỉ phụ thuộc vào 2 trạng thái trước, không nhất thiết phải giữ cả mảng.

```python
n = int(input())

if n == 0:
    print(1)
elif n == 1:
    print(1)
else:
    prev2 = 1
    prev1 = 1

    for _ in range(2, n + 1):
        cur = prev1 + prev2
        prev2 = prev1
        prev1 = cur

    print(prev1)
```

---

# VII. Bài tập vận dụng

---

## Bài 1. Leo cầu thang 1 hoặc 2 bước

---

## Bài 2. Leo cầu thang 1, 2 hoặc 3 bước

---

## Bài 3. Đếm cách lát bảng 2 × N bằng domino

---

## Bài 4. Đếm cách tạo tổng N bằng các số 1 và 2

---

## Bài 5. Đếm số dãy nhị phân độ dài N không có hai số 1 liên tiếp

Gợi ý: chia theo ký tự cuối cùng.

---

# VIII. Bài tập về nhà

---

## Bài 1. Đếm cách đi tới N bằng bước 1, 3, 5

---

## Bài 2. Đếm cách lát bảng 1 × N bằng gạch 1 × 1 và 1 × 2

---

## Bài 3. Dãy nhị phân độ dài N không có ba số 1 liên tiếp

---

## Bài 4. Đếm cách chia N thành tổng có thứ tự của 1 và 2

---

## Bài 5. Tính số cách modulo \(10^9 + 7\)

---

# IX. Lỗi học sinh thường gặp

---

## 1. Gán sai `dp[0]`

Trong bài đếm cách, `dp[0] = 1` thường rất quan trọng.

---

## 2. Quên kiểm tra chỉ số âm

---

## 3. Nhầm “đếm cách có thứ tự” với “không xét thứ tự”

---

## 4. Dùng `dp[i] = max(...)` thay vì cộng

---

## 5. Không để ý yêu cầu modulo

---

# X. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Lát gạch

---

## Đề 2. Bậc thang

---

## Đề 3. Dãy nhị phân hợp lệ

---

## Đề 4. Số cách đi trên đường thẳng

---

# XI. Ghi nhớ cuối bài

- Bài đếm cách thường dùng phép cộng.
- `dp[i]` thường là số cách để đạt trạng thái `i`.
- `dp[0] = 1` là điểm xuất phát tự nhiên trong nhiều bài.

---

# XII. Tóm tắt bài học

```python
dp[0] = 1

for i in range(1, n + 1):
    if i - 1 >= 0:
        dp[i] += dp[i - 1]
    if i - 2 >= 0:
        dp[i] += dp[i - 2]
```
