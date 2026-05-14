# Bài 68. Balo vô hạn và đổi tiền bằng DP

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu sự khác nhau giữa:
  - Balo 0/1.
  - Balo vô hạn.
- Biết áp dụng DP cho:
  - Đổi tiền ít đồng nhất.
  - Đếm số cách đổi tiền.
- Hiểu vì sao thứ tự vòng lặp ảnh hưởng đến kết quả.

## 2. Về kỹ năng

- Cài đặt unbounded knapsack.
- Tính số đồng ít nhất để tạo tổng `S`.
- Đếm số cách đổi tiền không xét thứ tự.

## 3. Về tư duy

- Một vật có thể dùng lại nhiều lần => trạng thái cập nhật khác so với 0/1.

---

# II. Balo vô hạn là gì?

Có `N` loại đồ.  
Mỗi loại có thể chọn nhiều lần.

Ví dụ:

- Có đồng xu 1, 3, 4.
- Có thể dùng bao nhiêu đồng mỗi loại tùy ý.

---

# III. Đổi tiền ít đồng nhất

## 1. Đề bài

Cho các mệnh giá xu và tổng `S`.  
Tìm số đồng ít nhất để tạo ra đúng `S`.

---

## 2. Trạng thái

`dp[x]` là số đồng ít nhất để tạo tổng `x`.

---

## 3. Điều kiện đầu

- `dp[0] = 0`
- Các giá trị khác ban đầu là vô cực.

---

## 4. Công thức

Với mỗi tổng `x`, thử dùng đồng `coin`:

\[
dp[x] = \min(dp[x], dp[x-coin] + 1)
\]

---

## 5. Code Python

```python
n, S = map(int, input().split())
coins = list(map(int, input().split()))

INF = 10**18
dp = [INF] * (S + 1)
dp[0] = 0

for x in range(1, S + 1):
    for coin in coins:
        if x >= coin:
            dp[x] = min(dp[x], dp[x - coin] + 1)

if dp[S] == INF:
    print(-1)
else:
    print(dp[S])
```

---

# IV. Đếm số cách đổi tiền không xét thứ tự

## 1. Trạng thái

`dp[x]` là số cách tạo tổng `x`.

---

## 2. Điều kiện đầu

`dp[0] = 1`

---

## 3. Vòng lặp quan trọng

```python
for coin in coins:
    for x in range(coin, S + 1):
        dp[x] += dp[x - coin]
```

Duyệt **coin trước**, **tổng sau** để tránh đếm trùng thứ tự.

---

## 4. Code Python

```python
n, S = map(int, input().split())
coins = list(map(int, input().split()))

dp = [0] * (S + 1)
dp[0] = 1

for coin in coins:
    for x in range(coin, S + 1):
        dp[x] += dp[x - coin]

print(dp[S])
```

---

# V. Balo vô hạn tối đa giá trị

Nếu mỗi vật có:

- Trọng lượng `weight`
- Giá trị `value`

và được dùng vô hạn lần:

```python
for weight, value in items:
    for cap in range(weight, W + 1):
        dp[cap] = max(dp[cap], dp[cap - weight] + value)
```

Điểm khác với balo 0/1 là `cap` duyệt **tăng dần**.

---

# VI. Bài tập vận dụng

---

## Bài 1. Ít đồng nhất để đổi tiền

---

## Bài 2. Đếm số cách đổi tiền

---

## Bài 3. Balo vô hạn tối đa giá trị

---

## Bài 4. Tạo tổng S từ các số cho trước

---

## Bài 5. So sánh duyệt xu trước và tổng trước

---

# VII. Bài tập về nhà

---

## Bài 1. Đổi tiền có modulo

---

## Bài 2. Tạo tổng lớn nhất không vượt quá S

---

## Bài 3. Đếm số cách tạo tổng S có xét thứ tự

---

## Bài 4. Tối thiểu số vật để đạt trọng lượng chính xác

---

## Bài 5. Phân biệt ba bài:
- Đếm cách.
- Ít đồng nhất.
- Giá trị lớn nhất.

---

# VIII. Lỗi học sinh thường gặp

---

## 1. Dùng cùng công thức cho mọi bài đổi tiền

---

## 2. Sai thứ tự vòng lặp

---

## 3. Không xử lý trường hợp không thể tạo tổng

---

## 4. Nhầm vô hạn với 0/1

---

## 5. Quên khởi tạo `dp[0]`

---

# IX. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Đổi tiền

---

## Đề 2. Cắt thanh gỗ / mua vật tư nhiều lần

---

## Đề 3. Chọn món vô hạn

---

## Đề 4. Số cách phân tích tổng

---

# X. Ghi nhớ cuối bài

- 0/1 knapsack: cap duyệt giảm dần.
- Balo vô hạn: cap duyệt tăng dần.
- Đổi tiền:
  - Ít đồng nhất: `min`.
  - Đếm cách: `+`.

---

# XI. Tóm tắt bài học

```python
# Balo vô hạn
for weight, value in items:
    for cap in range(weight, W + 1):
        dp[cap] = max(dp[cap], dp[cap - weight] + value)
```
