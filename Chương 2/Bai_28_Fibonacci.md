# Bài 28. Dãy Fibonacci và dãy truy hồi cơ bản

---

# I. Mục tiêu bài học

Sau bài học này, học sinh cần đạt được các yêu cầu sau:

## 1. Về kiến thức

- Hiểu khái niệm **dãy Fibonacci**.
- Nắm được công thức truy hồi của dãy Fibonacci.
- Biết một số giá trị đầu tiên của dãy.
- Hiểu sự khác nhau giữa:
  - Đệ quy trực tiếp.
  - Dùng mảng.
  - Dùng hai biến.
- Biết rằng bài toán Fibonacci là bước chuẩn bị quan trọng cho quy hoạch động.

## 2. Về kỹ năng

- Viết được chương trình tính số Fibonacci thứ $N$.
- Liệt kê được các số Fibonacci không vượt quá $N$.
- Đếm được số lượng Fibonacci trong một đoạn.
- Kiểm tra được một số có thuộc dãy Fibonacci hay không bằng cách sinh dãy.
- Vận dụng Fibonacci vào một số bài toán đếm đơn giản.

## 3. Về tư duy

- Hiểu thế nào là một dãy được xác định từ các phần tử trước đó.
- Biết tối ưu từ đệ quy lặp lại sang vòng lặp.
- Hình thành tư duy lưu kết quả hoặc cập nhật kết quả theo trạng thái trước.

---

# II. Lý thuyết

## 1. Dãy Fibonacci là gì?

Dãy Fibonacci là dãy số được định nghĩa như sau:

- $F_1 = 1$
- $F_2 = 1$
- Với $n \ge 3$:

$F_n = F_{n-1} + F_{n-2}$

---

## 2. Các số Fibonacci đầu tiên

Dãy Fibonacci bắt đầu:

$1, 1, 2, 3, 5, 8, 13, 21, 34, 55, ...$

---

## 3. Cách tính trực tiếp theo định nghĩa

Ví dụ:

- $F_1 = 1$
- $F_2 = 1$
- $F_3 = F_2 + F_1 = 2$
- $F_4 = F_3 + F_2 = 3$
- $F_5 = F_4 + F_3 = 5$

---

## 4. Tính Fibonacci bằng đệ quy

### Code minh họa

```python
def fib(n):
    if n <= 2:
        return 1

    return fib(n - 1) + fib(n - 2)
```

### Nhận xét

Cách này đúng nhưng chậm vì nhiều giá trị bị tính lặp lại rất nhiều lần.

Ví dụ để tính `fib(6)`:

- `fib(5)` và `fib(4)` được gọi.
- Bên trong `fib(5)` lại gọi tiếp `fib(4)`.

Như vậy `fib(4)` bị tính nhiều lần.

---

## 5. Tính Fibonacci bằng mảng

Ta lưu lại các giá trị đã tính.

### Ý tưởng

- `f[1] = 1`
- `f[2] = 1`
- `f[i] = f[i - 1] + f[i - 2]`

### Code

```python
n = int(input())

f = [0] * (n + 1)

f[1] = 1

if n >= 2:
    f[2] = 1

for i in range(3, n + 1):
    f[i] = f[i - 1] + f[i - 2]

print(f[n])
```

---

## 6. Tính Fibonacci bằng hai biến

Ta chỉ cần giữ hai số gần nhất.

### Ý tưởng

Nếu đang có:

- `a = F[n - 2]`
- `b = F[n - 1]`

thì:

- `c = a + b = F[n]`

Sau đó cập nhật:

- `a = b`
- `b = c`

---

## 7. Code hai biến

```python
n = int(input())

if n <= 2:
    print(1)
else:
    a = 1
    b = 1

    for _ in range(3, n + 1):
        c = a + b
        a = b
        b = c

    print(b)
```

---

## 8. So sánh các cách tính

| Cách | Bộ nhớ | Tốc độ | Nhận xét |
|---|---|---|---|
| Đệ quy đơn giản | Ít | Chậm | Dễ hiểu nhưng không hiệu quả |
| Dùng mảng | $O(N)$ | $O(N)$ | Dễ mở rộng |
| Dùng hai biến | $O(1)$ | $O(N)$ | Tối ưu bộ nhớ |

---

## 9. Liệt kê Fibonacci không vượt quá N

Ta sinh lần lượt các số Fibonacci cho đến khi vượt quá $N$.

### Ví dụ

Nếu $N = 30$, các số Fibonacci không vượt quá $30$ là:

$1, 1, 2, 3, 5, 8, 13, 21$

---

## 10. Kiểm tra một số có thuộc dãy Fibonacci không

Một cách đơn giản:

1. Sinh dãy Fibonacci tăng dần.
2. Dừng khi số Fibonacci lớn hơn hoặc bằng $N$.
3. Nếu gặp đúng $N$, kết luận có.

---

# III. Ví dụ minh họa

---

## Ví dụ 1. Tính Fibonacci thứ N

### 1. Đề bài

Cho số nguyên dương $N$.  
Hãy tính số Fibonacci thứ $N$.

---

### 2. Code Python

```python
n = int(input())

if n <= 2:
    print(1)
else:
    a = 1
    b = 1

    for _ in range(3, n + 1):
        a, b = b, a + b

    print(b)
```

---

### 3. Input

```text
6
```

### 4. Output

```text
8
```

---

## Ví dụ 2. Liệt kê Fibonacci không vượt quá N

### 1. Đề bài

Cho số nguyên dương $N$.  
Liệt kê các số Fibonacci không vượt quá $N$.

---

### 2. Code Python

```python
n = int(input())

a = 1
b = 1

if n >= 1:
    print(a)

if n >= 1:
    print(b)

while True:
    c = a + b

    if c > n:
        break

    print(c)

    a = b
    b = c
```

---

### 3. Input

```text
20
```

### 4. Output

```text
1
1
2
3
5
8
13
```

---

## Ví dụ 3. Đếm số Fibonacci không vượt quá N

### 1. Đề bài

Cho số nguyên dương $N$.  
Đếm có bao nhiêu số Fibonacci không vượt quá $N$.

---

### 2. Code Python

```python
n = int(input())

a = 1
b = 1
count = 0

if a <= n:
    count += 1

if b <= n:
    count += 1

while True:
    c = a + b

    if c > n:
        break

    count += 1
    a = b
    b = c

print(count)
```

---

### 3. Input

```text
20
```

### 4. Output

```text
7
```

---

## Ví dụ 4. Kiểm tra một số có là Fibonacci không

### 1. Đề bài

Cho số nguyên dương $N$.  
Kiểm tra xem $N$ có thuộc dãy Fibonacci hay không.

Nếu có, in `YES`.  
Ngược lại, in `NO`.

---

### 2. Code Python

```python
n = int(input())

a = 1
b = 1
found = False

if n == 1:
    found = True

while b < n:
    a, b = b, a + b

if b == n:
    found = True

if found:
    print("YES")
else:
    print("NO")
```

---

## Ví dụ 5. Tổng các số Fibonacci không vượt quá N

### 1. Đề bài

Cho số nguyên dương $N$.  
Tính tổng các số Fibonacci không vượt quá $N$.

---

### 2. Code Python

```python
n = int(input())

a = 1
b = 1
total = 0

if a <= n:
    total += a

if b <= n:
    total += b

while True:
    c = a + b

    if c > n:
        break

    total += c
    a = b
    b = c

print(total)
```

---

# IV. Bài tập vận dụng

---

## Bài 1. Fibonacci thứ N

### Đề bài

Cho số nguyên dương $N$.  
Tính $F_N$.

---

## Bài 2. Liệt kê Fibonacci

### Đề bài

Cho số nguyên dương $N$.  
Liệt kê các số Fibonacci không vượt quá $N$.

---

## Bài 3. Đếm Fibonacci

### Đề bài

Cho số nguyên dương $N$.  
Đếm có bao nhiêu số Fibonacci không vượt quá $N$.

---

## Bài 4. Tổng Fibonacci

### Đề bài

Cho số nguyên dương $N$.  
Tính tổng các số Fibonacci không vượt quá $N$.

---

## Bài 5. Kiểm tra Fibonacci

### Đề bài

Cho số nguyên dương $N$.  
Kiểm tra xem $N$ có thuộc dãy Fibonacci hay không.

---

## Bài 6. Fibonacci chẵn

### Đề bài

Cho số nguyên dương $N$.  
Liệt kê các số Fibonacci chẵn không vượt quá $N$.

---

## Bài 7. Fibonacci nguyên tố

### Đề bài

Cho số nguyên dương $N$.  
Đếm bao nhiêu số Fibonacci không vượt quá $N$ đồng thời là số nguyên tố.

---

# V. Bài tập về nhà

---

## Bài 1. Fibonacci lớn nhất không vượt quá N

### Đề bài

Cho số nguyên dương $N$.  
Tìm số Fibonacci lớn nhất không vượt quá $N$.

---

## Bài 2. Fibonacci nhỏ nhất không nhỏ hơn N

### Đề bài

Cho số nguyên dương $N$.  
Tìm số Fibonacci nhỏ nhất không nhỏ hơn $N$.

---

## Bài 3. Khoảng cách đến Fibonacci gần nhất

### Đề bài

Cho số nguyên dương $N$.  
Tìm khoảng cách nhỏ nhất từ $N$ đến một số Fibonacci.

---

## Bài 4. Số Fibonacci trong đoạn [A, B]

### Đề bài

Cho hai số nguyên dương $A$, $B$.  
Đếm bao nhiêu số Fibonacci thuộc đoạn $[A, B]$.

---

## Bài 5. Dãy truy hồi mới

### Đề bài

Cho dãy:

- $A_1 = 2$
- $A_2 = 3$
- $A_n = A_{n-1} + A_{n-2}$ với $n \ge 3$

Hãy tính $A_N$.

---

## Bài 6. Số cách leo cầu thang

### Đề bài

Một học sinh có thể bước lên:

- $1$ bậc.
- $2$ bậc.

Hỏi có bao nhiêu cách để đi đến bậc thứ $N$?

### Gợi ý

Bài toán có quan hệ truy hồi giống Fibonacci.

---

# VI. Lỗi học sinh thường gặp

---

## 1. Nhầm chỉ số bắt đầu của dãy

Cần thống nhất trong bài:

- $F_1 = 1$
- $F_2 = 1$

---

## 2. Quên xử lý N = 1 hoặc N = 2

Nếu chương trình dùng vòng lặp từ $3$, cần xử lý hai trường hợp đầu riêng.

---

## 3. Cập nhật biến sai thứ tự

Nếu viết:

```python
a = b
b = a + b
```

thì giá trị `a` đã bị đổi trước khi tính `b`.

Nên dùng:

```python
a, b = b, a + b
```

---

## 4. Dùng đệ quy chậm cho N lớn

Đệ quy đơn giản có thể rất chậm.

Nên dùng:

- Mảng.
- Hai biến.
- Quy hoạch động ở các bài sau.

---

## 5. In trùng hoặc thiếu hai số 1 đầu tiên

Khi liệt kê dãy Fibonacci, cần xác định rõ đề có tính cả hai số $1$ hay không.

---

# VII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Fibonacci nguyên tố

### Bài toán

Cho số nguyên dương $P$.  
Hãy xác định có bao nhiêu số không vượt quá $P$ vừa là số Fibonacci, vừa là số nguyên tố.

---

## Đề 2. Đếm Fibonacci trong đoạn

### Bài toán

Cho hai số nguyên dương $A$, $B$.  
Đếm số lượng số Fibonacci thuộc đoạn $[A, B]$.

---

## Đề 3. Tách số thành tổng Fibonacci

### Bài toán

Cho số nguyên dương $N$.  
Hãy biểu diễn $N$ dưới dạng tổng các số Fibonacci đôi một khác nhau.

---

## Đề 4. Leo cầu thang

### Bài toán

Có một cầu thang gồm $N$ bậc.  
Mỗi bước có thể đi lên $1$ hoặc $2$ bậc.

Hãy đếm số cách để đi đến bậc thứ $N$.

---

# VIII. Ghi nhớ cuối bài

- Dãy Fibonacci thỏa:
  - $F_1 = 1$
  - $F_2 = 1$
  - $F_n = F_{n-1} + F_{n-2}$
- Không nên dùng đệ quy đơn giản cho $N$ lớn.
- Dùng vòng lặp hoặc mảng sẽ hiệu quả hơn.
- Dùng hai biến giúp tiết kiệm bộ nhớ.
- Fibonacci là ví dụ quan trọng để chuẩn bị học:
  - Dãy truy hồi.
  - Quy hoạch động.

---

# IX. Tóm tắt bài học

## Bài 28. Dãy Fibonacci

- Các số đầu tiên:

$1, 1, 2, 3, 5, 8, 13, ...$

- Công thức:

$F_n = F_{n-1} + F_{n-2}$

- Cách tính hiệu quả:

```python
a = 1
b = 1

for _ in range(3, n + 1):
    a, b = b, a + b
```

- Các dạng bài thường gặp:
  - Tính $F_N$.
  - Liệt kê Fibonacci.
  - Đếm Fibonacci trong đoạn.
  - Fibonacci nguyên tố.
  - Bài toán leo cầu thang.
