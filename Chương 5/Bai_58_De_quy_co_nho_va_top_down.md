# Bài 58. Đệ quy có nhớ và quy hoạch động từ trên xuống

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu nhược điểm của đệ quy thuần.
- Biết khái niệm **memoization** — ghi nhớ kết quả.
- Hiểu DP từ trên xuống:
  - Gọi bài toán lớn.
  - Đệ quy xuống bài toán nhỏ.
  - Lưu lại kết quả đã tính.

## 2. Về kỹ năng

- Viết được đệ quy có nhớ cho Fibonacci.
- Chuyển từ đệ quy thuần sang memoization.
- Phân biệt:
  - Top-down.
  - Bottom-up.

## 3. Về tư duy

- Nhận ra việc lặp lại bài toán con.
- Biết chọn dạng cài đặt phù hợp:
  - Top-down khi công thức tự nhiên theo đệ quy.
  - Bottom-up khi muốn tối ưu kiểm soát vòng lặp.

---

# II. Vấn đề của đệ quy thuần

## 1. Ví dụ Fibonacci

Công thức:

\[
F(n) = F(n-1) + F(n-2)
\]

Code đệ quy thuần:

```python
def fib(n):
    if n <= 1:
        return n
    return fib(n - 1) + fib(n - 2)
```

---

## 2. Vì sao chậm?

Khi tính `fib(6)`:

- `fib(5)` cần `fib(4)` và `fib(3)`.
- `fib(4)` lại cần `fib(3)` và `fib(2)`.

`fib(3)` bị tính nhiều lần.

---

## 3. Độ phức tạp

Đệ quy thuần Fibonacci gần với:

\[
O(2^N)
\]

Rất chậm khi `N` lớn.

---

# III. Ý tưởng memoization

## 1. Ghi nhớ kết quả

Khi tính xong `fib(x)`, lưu lại vào mảng `memo[x]`.

Nếu lần sau cần `fib(x)`:

- Không tính lại.
- Trả ngay kết quả đã lưu.

---

## 2. Mẫu chung

```python
memo = [-1] * (n + 1)

def solve(x):
    if memo[x] != -1:
        return memo[x]

    # Tính kết quả thật sự ở đây
    memo[x] = ...
    return memo[x]
```

---

# IV. Ví dụ minh họa

---

## Ví dụ 1. Fibonacci top-down

```python
n = int(input())
memo = [-1] * (n + 1)

def fib(x):
    if x <= 1:
        return x

    if memo[x] != -1:
        return memo[x]

    memo[x] = fib(x - 1) + fib(x - 2)
    return memo[x]

print(fib(n))
```

---

## Ví dụ 2. Leo cầu thang top-down

### 1. Đề bài

Có `N` bậc thang.  
Mỗi lần đi 1 hoặc 2 bậc.  
Đếm số cách lên bậc `N`.

---

### 2. Trạng thái

`ways(i)` là số cách đi tới bậc `i`.

---

### 3. Công thức

\[
ways(i) = ways(i-1) + ways(i-2)
\]

---

### 4. Code Python

```python
n = int(input())
memo = [-1] * (n + 1)

def ways(i):
    if i == 0:
        return 1
    if i < 0:
        return 0

    if memo[i] != -1:
        return memo[i]

    memo[i] = ways(i - 1) + ways(i - 2)
    return memo[i]

print(ways(n))
```

---

## Ví dụ 3. Tổng nhỏ nhất để đến vị trí cuối

### 1. Đề bài

Có dãy chi phí `cost[0..n-1]`.  
Mỗi lần bước 1 hoặc 2 ô.  
Khi đứng vào ô nào, trả chi phí ô đó.  
Tìm chi phí nhỏ nhất để tới ô cuối.

---

### 2. Trạng thái

`solve(i)` là chi phí nhỏ nhất để tới ô `i`.

---

### 3. Công thức

\[
solve(i) = cost[i] + \min(solve(i-1), solve(i-2))
\]

---

# V. Top-down và Bottom-up

| Tiêu chí | Top-down | Bottom-up |
|---|---|---|
| Cách viết | Đệ quy + nhớ | Vòng lặp |
| Dễ suy luận | Rất tự nhiên | Cần xác định thứ tự tính |
| Rủi ro | Tràn ngăn xếp nếu sâu | Ít hơn |
| Tối ưu kiểm soát | Trung bình | Tốt |

---

# VI. Khi nào dùng Top-down?

Nên dùng khi:

- Công thức chuyển dễ viết bằng đệ quy.
- Không phải mọi trạng thái đều cần tính.
- Muốn làm nhanh phiên bản đầu tiên để kiểm chứng ý tưởng.

---

# VII. Bài tập vận dụng

---

## Bài 1. Fibonacci top-down

---

## Bài 2. Leo cầu thang với bước 1, 2

---

## Bài 3. Leo cầu thang với bước 1, 2, 3

---

## Bài 4. Chi phí nhỏ nhất đi tới vị trí N

---

## Bài 5. Đếm số cách tạo tổng N từ các số 1, 3, 4

---

# VIII. Bài tập về nhà

---

## Bài 1. Số cách đi tới N bằng bước 2 hoặc 5

---

## Bài 2. Tính số Catalan cơ bản bằng đệ quy có nhớ

---

## Bài 3. Tìm tổng lớn nhất khi nhảy 1 hoặc 2 bước

---

## Bài 4. Tối thiểu số phép để biến N về 1:
- Trừ 1.
- Nếu chia hết cho 2 thì chia 2.
- Nếu chia hết cho 3 thì chia 3.

---

## Bài 5. So sánh thời gian chạy của Fibonacci thường và Fibonacci có nhớ.

---

# IX. Lỗi học sinh thường gặp

---

## 1. Quên lưu kết quả vào memo

---

## 2. Đặt memo trước khi xử lý điều kiện dừng

---

## 3. Dùng `0` làm giá trị chưa tính trong khi đáp án có thể bằng 0

Nên dùng:

```python
None
```

hoặc:

```python
-1
```

nếu chắc chắn đáp án không âm.

---

## 4. Đệ quy quá sâu

Python giới hạn độ sâu đệ quy, nên với `N` rất lớn phải cân nhắc bottom-up.

---

## 5. Memo sai kích thước

---

# X. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Đếm cách lên cầu thang

---

## Đề 2. Tối thiểu số bước về 1

---

## Đề 3. Đếm cách sinh chuỗi hợp lệ

---

## Đề 4. Tối ưu đường đi tuyến tính

---

# XI. Ghi nhớ cuối bài

- Top-down = đệ quy + ghi nhớ.
- Mỗi trạng thái chỉ nên được tính **một lần**.
- Nếu thấy bài toán con bị gọi lặp lại, hãy nghĩ đến memoization.

---

# XII. Tóm tắt bài học

```python
memo = [-1] * (n + 1)

def solve(x):
    if x <= 1:
        return x

    if memo[x] != -1:
        return memo[x]

    memo[x] = solve(x - 1) + solve(x - 2)
    return memo[x]
```
