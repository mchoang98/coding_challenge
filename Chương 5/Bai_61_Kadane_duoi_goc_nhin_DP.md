# Bài 61. Đoạn con có tổng lớn nhất và tư duy Kadane dưới góc nhìn DP

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu bài toán **maximum subarray**.
- Biết công thức Kadane.
- Nhìn Kadane như một bài DP 1 chiều.

## 2. Về kỹ năng

- Tìm tổng lớn nhất của một đoạn con liên tiếp.
- Xử lý đúng trường hợp toàn số âm.
- Mở rộng để truy vết vị trí đoạn con.

## 3. Về tư duy

- Không cần xét mọi đoạn `O(N^2)`.
- Tối ưu về `O(N)` bằng việc lưu thông tin tốt nhất kết thúc tại vị trí hiện tại.

---

# II. Đề bài mẫu

Cho dãy số nguyên `a[1..N]`.  
Hãy tìm tổng lớn nhất của một đoạn con liên tiếp.

---

# III. Cách làm chậm

Duyệt mọi cặp `(L, R)` và tính tổng đoạn.

Độ phức tạp có thể là:

- `O(N^3)` nếu cộng lại từng đoạn.
- `O(N^2)` nếu dùng prefix sum.

Nhưng ta còn làm tốt hơn: `O(N)`.

---

# IV. Trạng thái DP

## 1. Ý nghĩa

`dp[i]` là tổng lớn nhất của một đoạn con **bắt buộc kết thúc tại vị trí i**.

---

## 2. Hai lựa chọn

Tại `a[i]`, có hai khả năng:

### Cách 1. Bắt đầu đoạn mới tại i

\[
a[i]
\]

### Cách 2. Nối vào đoạn tốt nhất kết thúc ở i-1

\[
dp[i-1] + a[i]
\]

---

## 3. Công thức

\[
dp[i] = \max(a[i], dp[i-1] + a[i])
\]

Đáp án toàn bài:

\[
\max(dp[i])
\]

---

# V. Code Python dùng mảng DP

```python
n = int(input())
a = list(map(int, input().split()))

dp = [0] * n
dp[0] = a[0]
answer = dp[0]

for i in range(1, n):
    dp[i] = max(a[i], dp[i - 1] + a[i])
    answer = max(answer, dp[i])

print(answer)
```

---

# VI. Code Python tối ưu bộ nhớ

```python
n = int(input())
a = list(map(int, input().split()))

best_ending_here = a[0]
answer = a[0]

for i in range(1, n):
    best_ending_here = max(a[i], best_ending_here + a[i])
    answer = max(answer, best_ending_here)

print(answer)
```

---

# VII. Ví dụ minh họa

Dãy:

`-2 1 -3 4 -1 2 1 -5 4`

Đoạn tốt nhất là:

`4 -1 2 1`

Tổng:

`6`

---

# VIII. Truy vết đoạn con

Ta có thể lưu:

- `start`: đầu đoạn hiện tại.
- `best_l`, `best_r`: đoạn tốt nhất toàn cục.

```python
n = int(input())
a = list(map(int, input().split()))

current_sum = a[0]
best_sum = a[0]

current_l = 0
best_l = 0
best_r = 0

for i in range(1, n):
    if a[i] > current_sum + a[i]:
        current_sum = a[i]
        current_l = i
    else:
        current_sum += a[i]

    if current_sum > best_sum:
        best_sum = current_sum
        best_l = current_l
        best_r = i

print(best_sum)
print(best_l + 1, best_r + 1)
```

---

# IX. Bài tập vận dụng

---

## Bài 1. Tổng đoạn con lớn nhất

---

## Bài 2. In ra tổng lớn nhất và vị trí đoạn

---

## Bài 3. Tổng đoạn con nhỏ nhất

Gợi ý: thay `max` bằng `min`.

---

## Bài 4. Tổng vòng tròn lớn nhất

---

## Bài 5. Đếm số đoạn đạt tổng lớn nhất trong trường hợp đơn giản

---

# X. Bài tập về nhà

---

## Bài 1. Độ dài ngắn nhất của đoạn đạt tổng lớn nhất

---

## Bài 2. Dãy chỉ gồm số dương và âm, phân tích sự khác biệt

---

## Bài 3. Tìm đoạn con có tổng lớn nhất nhưng phải có ít nhất K phần tử

---

## Bài 4. Maximum subarray modulo một số nhỏ — khảo sát nâng cao

---

## Bài 5. Viết lại thuật toán bằng dạng `dp[i]`.

---

# XI. Lỗi học sinh thường gặp

---

## 1. Khởi tạo `answer = 0`

Sai nếu dãy toàn số âm.

---

## 2. Nhầm đoạn con liên tiếp với dãy con không liên tiếp

---

## 3. Không hiểu ý nghĩa `dp[i]`

---

## 4. Chỉ lấy `max(dp[i-1], ...)`

Sai vì trạng thái phải **kết thúc tại i**.

---

# XII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Dãy con liên tiếp lớn nhất

---

## Đề 2. Lợi nhuận tối đa theo ngày

---

## Đề 3. Đoạn điểm số tốt nhất

---

## Đề 4. Phiên bản có truy vết

---

# XIII. Ghi nhớ cuối bài

Công thức cốt lõi:

\[
dp[i] = \max(a[i], dp[i-1] + a[i])
\]

Kadane là một dạng DP 1 chiều cực kỳ quan trọng.

---

# XIV. Tóm tắt bài học

```python
best = a[0]
cur = a[0]

for i in range(1, n):
    cur = max(a[i], cur + a[i])
    best = max(best, cur)
```
