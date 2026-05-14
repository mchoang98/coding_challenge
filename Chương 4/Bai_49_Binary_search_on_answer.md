# Bài 49. Binary Search trên đáp án

---

# I. Mục tiêu bài học

Sau bài học này, học sinh cần đạt được các yêu cầu sau:

## 1. Về kiến thức

- Hiểu khái niệm **binary search trên đáp án**.
- Biết điều kiện cốt lõi:
  - Hàm kiểm tra `check(x)` phải có tính đơn điệu.
- Biết các dạng thường gặp:
  - Tìm giá trị nhỏ nhất thỏa điều kiện.
  - Tìm giá trị lớn nhất thỏa điều kiện.

## 2. Về kỹ năng

- Xây dựng được hàm `check(mid)`.
- Cập nhật biên phù hợp với mục tiêu bài toán.
- Giải được một số bài:
  - Chia công việc.
  - Tìm tốc độ tối thiểu.
  - Tìm độ dài lớn nhất có thể cắt.

## 3. Về tư duy

- Không chỉ tìm trong mảng.
- Biết tìm kiếm trên **không gian đáp án**.
- Hình thành tư duy tối ưu hóa với điều kiện kiểm tra.

---

# II. Lý thuyết

## 1. Binary Search trên đáp án là gì?

Thay vì tìm một phần tử trong dãy, ta tìm một giá trị đáp án.

Ví dụ:

- Tốc độ nhỏ nhất để hoàn thành công việc.
- Độ dài lớn nhất của thanh cắt.
- Sức chứa nhỏ nhất để vận chuyển hàng.

---

## 2. Điều kiện đơn điệu

Giả sử ta cần tìm giá trị nhỏ nhất thỏa điều kiện.

Nếu:

- `check(x) = False` với các giá trị nhỏ.
- `check(x) = True` từ một ngưỡng trở đi.

thì ta có dạng:

`False False False True True True`

Binary search được áp dụng rất tốt.

---

## 3. Tìm nhỏ nhất thỏa điều kiện

Mẫu:

```python
left = low
right = high

while left < right:
    mid = (left + right) // 2

    if check(mid):
        right = mid
    else:
        left = mid + 1

print(left)
```

---

## 4. Tìm lớn nhất thỏa điều kiện

Mẫu:

```python
left = low
right = high

while left < right:
    mid = (left + right + 1) // 2

    if check(mid):
        left = mid
    else:
        right = mid - 1

print(left)
```

---

# III. Ví dụ minh họa

---

## Ví dụ 1. Tìm căn nguyên lớn nhất

### 1. Đề bài

Cho số nguyên $N$.  
Tìm số nguyên lớn nhất $x$ sao cho:

$x^2 \le N$

---

### 2. Code Python

```python
n = int(input())

left = 0
right = n

while left < right:
    mid = (left + right + 1) // 2

    if mid * mid <= n:
        left = mid
    else:
        right = mid - 1

print(left)
```

---

## Ví dụ 2. Cắt dây

### 1. Đề bài

Có $N$ sợi dây với các độ dài nguyên.  
Muốn cắt ra ít nhất $K$ đoạn bằng nhau.  
Hãy tìm độ dài lớn nhất của mỗi đoạn.

---

### 2. Ý tưởng

Với độ dài thử `x`, số đoạn cắt được là:

$\sum \left\lfloor \frac{a_i}{x} \right\rfloor$

Nếu cắt được ít nhất $K$ đoạn, `x` khả thi.

---

### 3. Code Python

```python
n, k = map(int, input().split())
a = list(map(int, input().split()))

def check(length):
    count = 0

    for rope in a:
        count += rope // length

    return count >= k

left = 1
right = max(a)

while left < right:
    mid = (left + right + 1) // 2

    if check(mid):
        left = mid
    else:
        right = mid - 1

print(left)
```

---

## Ví dụ 3. Vận chuyển hàng với sức chứa nhỏ nhất

### 1. Đề bài

Có $N$ kiện hàng theo thứ tự.  
Mỗi ngày vận chuyển liên tiếp một số kiện.  
Tìm sức chứa nhỏ nhất để vận chuyển hết trong không quá $D$ ngày.

---

### 2. Hàm kiểm tra

Với sức chứa `capacity`, ta đếm số ngày cần dùng.

---

### 3. Code Python

```python
n, d = map(int, input().split())
weights = list(map(int, input().split()))

def check(capacity):
    days = 1
    current = 0

    for w in weights:
        if current + w <= capacity:
            current += w
        else:
            days += 1
            current = w

    return days <= d

left = max(weights)
right = sum(weights)

while left < right:
    mid = (left + right) // 2

    if check(mid):
        right = mid
    else:
        left = mid + 1

print(left)
```

---

# IV. Bài tập vận dụng

---

## Bài 1. Căn bậc hai nguyên

Cho $N$.  
Tìm số nguyên lớn nhất $x$ sao cho $x^2 \le N$.

---

## Bài 2. Kiểm tra số chính phương bằng binary search

---

## Bài 3. Cắt thanh gỗ

Cho các thanh gỗ và số đoạn cần cắt.  
Tìm độ dài đoạn lớn nhất.

---

## Bài 4. Chia bài cho học sinh

Cho số trang của các quyển sách theo thứ tự.  
Chia cho $K$ học sinh sao cho số trang nhiều nhất một học sinh đọc là nhỏ nhất.

---

## Bài 5. Tốc độ tối thiểu

Một máy xử lý công việc.  
Tìm tốc độ nhỏ nhất để hoàn thành trước thời hạn.

---

# V. Bài tập về nhà

---

## Bài 1. Chia hàng hóa

Tìm sức chứa xe nhỏ nhất để vận chuyển hết hàng trong $D$ chuyến.

---

## Bài 2. Khoảng cách lớn nhất

Đặt $K$ trạm trên các vị trí cho trước sao cho khoảng cách nhỏ nhất giữa hai trạm là lớn nhất.

---

## Bài 3. Thời gian nấu tối thiểu

Có nhiều bếp với tốc độ khác nhau.  
Tìm thời gian nhỏ nhất để nấu đủ $M$ món.

---

## Bài 4. Độ cao cắt cây

Chọn chiều cao cắt sao cho thu được ít nhất $M$ đơn vị gỗ.

---

## Bài 5. Cân bằng tải

Chia các công việc liên tiếp cho $K$ máy để tải lớn nhất là nhỏ nhất.

---

# VI. Lỗi học sinh thường gặp

---

## 1. Check không có tính đơn điệu

Nếu điều kiện không đơn điệu, binary search trên đáp án có thể sai.

---

## 2. Chọn sai biên ban đầu

Cần xác định rõ đáp án nằm trong khoảng nào.

---

## 3. Cập nhật biên sai với bài min hoặc max

- Tìm min thỏa: `right = mid`
- Tìm max thỏa: `left = mid`

---

## 4. Dùng mid sai gây vòng lặp vô hạn

Bài tìm lớn nhất thỏa nên dùng:

```python
mid = (left + right + 1) // 2
```

---

## 5. Hàm check cài đặt sai

Binary search chỉ đúng nếu `check()` đúng.

---

# VII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Cắt dây

Tìm độ dài lớn nhất có thể cắt ra ít nhất $K$ đoạn.

---

## Đề 2. Cắt gỗ

Tìm độ cao lưỡi cưa lớn nhất để thu được đủ lượng gỗ.

---

## Đề 3. Chia sách

Tìm lượng trang lớn nhất tối thiểu khi chia sách cho học sinh.

---

## Đề 4. Đặt trạm

Tối đa hóa khoảng cách nhỏ nhất.

---

# VIII. Ghi nhớ cuối bài

- Binary Search trên đáp án dùng khi kết quả có tính đơn điệu.
- Bắt buộc viết hàm `check(x)`.
- Có hai mẫu chính:
  - Tìm nhỏ nhất thỏa.
  - Tìm lớn nhất thỏa.
- Đây là kỹ thuật rất mạnh trong lập trình thi đấu.

---

# IX. Tóm tắt bài học

## Bài 49. Binary Search on Answer

Tìm nhỏ nhất thỏa:

```python
while left < right:
    mid = (left + right) // 2

    if check(mid):
        right = mid
    else:
        left = mid + 1
```

Tìm lớn nhất thỏa:

```python
while left < right:
    mid = (left + right + 1) // 2

    if check(mid):
        left = mid
    else:
        right = mid - 1
```
