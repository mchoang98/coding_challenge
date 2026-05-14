# Bài 24. Phân tích thừa số nguyên tố

---

# I. Mục tiêu bài học

Sau bài học này, học sinh cần đạt được các yêu cầu sau:

## 1. Về kiến thức

- Hiểu được khái niệm **thừa số nguyên tố**.
- Biết rằng mọi số nguyên dương lớn hơn $1$ đều có thể phân tích thành tích các số nguyên tố.
- Nắm được cách phân tích một số bằng phương pháp chia liên tiếp.
- Hiểu vì sao chỉ cần thử ước đến khi $i \times i \le N$.
- Biết cách biểu diễn kết quả dưới hai dạng:
  - Danh sách các thừa số nguyên tố.
  - Dạng lũy thừa, ví dụ $60 = 2^2 \times 3 \times 5$.

## 2. Về kỹ năng

- Viết được chương trình phân tích $N$ thành thừa số nguyên tố.
- Viết được chương trình tìm:
  - Các thừa số nguyên tố khác nhau.
  - Ước nguyên tố lớn nhất.
  - Số lượng thừa số nguyên tố.
- Biết sử dụng vòng lặp `while` để chia liên tiếp.
- Biết tối ưu từ duyệt đến $N$ xuống duyệt đến $\sqrt{N}$.

## 3. Về tư duy

- Hiểu rằng việc “chia được bao nhiêu lần thì chia hết bấy nhiêu lần” là ý tưởng cốt lõi.
- Biết tận dụng phần còn lại của $N$ sau mỗi lần chia để giảm khối lượng xử lý.
- Hình thành thói quen quan sát:
  - Nếu sau khi thử đến $\sqrt{N}$ mà $N > 1$, thì $N$ còn lại chính là một thừa số nguyên tố.

---

# II. Lý thuyết

## 1. Thừa số nguyên tố là gì?

Một số nguyên tố $p$ được gọi là **thừa số nguyên tố** của $N$ nếu $N$ chia hết cho $p$.

### Ví dụ

- $2$ là thừa số nguyên tố của $12$.
- $3$ là thừa số nguyên tố của $12$.
- $5$ không phải là thừa số nguyên tố của $12$.

---

## 2. Phân tích thừa số nguyên tố là gì?

Phân tích thừa số nguyên tố là viết một số nguyên dương $N > 1$ thành tích của các số nguyên tố.

### Ví dụ

Ta có:

$12 = 2 \times 2 \times 3$

Hoặc viết gọn:

$12 = 2^2 \times 3$

---

## 3. Một số ví dụ quen thuộc

### Ví dụ 1

$18 = 2 \times 3 \times 3 = 2 \times 3^2$

### Ví dụ 2

$60 = 2 \times 2 \times 3 \times 5 = 2^2 \times 3 \times 5$

### Ví dụ 3

$84 = 2 \times 2 \times 3 \times 7 = 2^2 \times 3 \times 7$

---

## 4. Ý tưởng phân tích bằng chia liên tiếp

Giả sử cần phân tích $N$.

Ta thực hiện:

1. Thử chia $N$ cho $2$.
2. Nếu chia hết:
   - Ghi nhận $2$ là một thừa số.
   - Cập nhật $N = N / 2$.
   - Tiếp tục chia tiếp cho $2$.
3. Khi không còn chia hết cho $2$, chuyển sang thử $3$.
4. Tiếp tục với $4, 5, 6, ...$ hoặc tốt hơn là thử các số tăng dần.
5. Quá trình dừng khi $i \times i > N$.
6. Nếu lúc đó $N > 1$, phần còn lại chính là một thừa số nguyên tố.

---

## 5. Vì sao cần chia lặp lại nhiều lần?

Xét $N = 72$.

Ta có:

$72 = 2 \times 36$

$36 = 2 \times 18$

$18 = 2 \times 9$

$9 = 3 \times 3$

Do đó:

$72 = 2 \times 2 \times 2 \times 3 \times 3 = 2^3 \times 3^2$

Nếu chỉ kiểm tra $2$ một lần, ta sẽ bỏ sót các lần xuất hiện còn lại của $2$.

---

## 6. Tại sao chỉ cần thử đến $\sqrt{N}$?

Nếu $N$ là hợp số, thì tồn tại hai số $a$, $b$ sao cho:

$N = a \times b$

Ít nhất một trong hai số $a$, $b$ không vượt quá $\sqrt{N}$.

Vì vậy:

- Nếu $N$ còn chia được, ta sẽ tìm thấy một ước nhỏ trong đoạn từ $2$ đến $\sqrt{N}$.
- Nếu không tìm thấy và $N > 1$, thì $N$ còn lại là số nguyên tố.

---

## 7. Mã giả cơ bản

1. Gán `i = 2`.
2. Trong khi `i * i <= n`:
   - Trong khi `n % i == 0`:
     - In ra `i`.
     - Cập nhật `n //= i`.
   - Tăng `i` thêm `1`.
3. Nếu `n > 1`, in ra `n`.

---

## 8. Độ phức tạp

Thuật toán thử chia đến $\sqrt{N}$ có độ phức tạp xấp xỉ:

$O(\sqrt{N})$

Trong thực tế, chương trình thường chạy nhanh hơn vì $N$ giảm dần sau mỗi lần chia.

---

# III. Ví dụ minh họa

---

## Ví dụ 1. Phân tích N thành các thừa số nguyên tố

### 1. Đề bài

Cho số nguyên dương $N > 1$.  
Hãy in ra các thừa số nguyên tố của $N$ theo thứ tự tăng dần.

---

### 2. Ví dụ

Với:

$N = 84$

Ta có:

$84 = 2 \times 2 \times 3 \times 7$

---

### 3. Code Python

```python
n = int(input())

i = 2

while i * i <= n:
    while n % i == 0:
        print(i)
        n //= i
    i += 1

if n > 1:
    print(n)
```

---

### 4. Input

```text
84
```

### 5. Output

```text
2
2
3
7
```

---

## Ví dụ 2. Giải thích từng bước với N = 84

Ban đầu:

- $N = 84$
- $i = 2$

### Bước 1

$84 \bmod 2 = 0$

- In `2`
- Cập nhật $N = 84 / 2 = 42$

### Bước 2

$42 \bmod 2 = 0$

- In `2`
- Cập nhật $N = 42 / 2 = 21$

### Bước 3

$21 \bmod 2 \ne 0$

- Tăng $i = 3$

### Bước 4

$21 \bmod 3 = 0$

- In `3`
- Cập nhật $N = 21 / 3 = 7$

### Bước 5

Khi này:

$3 \times 3 = 9 > 7$

Vòng lặp dừng.

Vì $N = 7 > 1$, in ra `7`.

---

## Ví dụ 3. In dạng lũy thừa

### 1. Đề bài

Cho số nguyên dương $N > 1$.  
Hãy phân tích $N$ thành thừa số nguyên tố dưới dạng:

$p_1^{a_1} \times p_2^{a_2} \times ...$

---

### 2. Ý tưởng

Với mỗi ước $i$:

- Đếm số lần $i$ chia hết $N$.
- Nếu đếm được ít nhất một lần, in ra $i$ và số mũ.

---

### 3. Code Python

```python
n = int(input())

i = 2
parts = []

while i * i <= n:
    count = 0

    while n % i == 0:
        count += 1
        n //= i

    if count > 0:
        if count == 1:
            parts.append(str(i))
        else:
            parts.append(f"{i}^{count}")

    i += 1

if n > 1:
    parts.append(str(n))

print(" * ".join(parts))
```

---

### 4. Input

```text
72
```

### 5. Output

```text
2^3 * 3^2
```

---

## Ví dụ 4. Tìm ước nguyên tố lớn nhất

### 1. Đề bài

Cho số nguyên dương $N > 1$.  
Hãy tìm ước nguyên tố lớn nhất của $N$.

---

### 2. Ý tưởng

Mỗi khi phát hiện một thừa số nguyên tố, ta cập nhật kết quả.

---

### 3. Code Python

```python
n = int(input())

i = 2
largest_prime_factor = -1

while i * i <= n:
    while n % i == 0:
        largest_prime_factor = i
        n //= i
    i += 1

if n > 1:
    largest_prime_factor = n

print(largest_prime_factor)
```

---

### 4. Input

```text
84
```

### 5. Output

```text
7
```

---

## Ví dụ 5. Đếm số lượng thừa số nguyên tố

### 1. Đề bài

Cho số nguyên dương $N > 1$.  
Đếm tổng số thừa số nguyên tố của $N$, tính cả số lần lặp lại.

---

### 2. Ví dụ

$72 = 2 \times 2 \times 2 \times 3 \times 3$

Số lượng thừa số nguyên tố là:

$5$

---

### 3. Code Python

```python
n = int(input())

i = 2
count = 0

while i * i <= n:
    while n % i == 0:
        count += 1
        n //= i
    i += 1

if n > 1:
    count += 1

print(count)
```

---

# IV. Bài tập vận dụng

---

## Bài 1. Phân tích thừa số nguyên tố

### Đề bài

Cho số nguyên dương $N > 1$.  
In ra từng thừa số nguyên tố của $N$ theo thứ tự tăng dần.

---

## Bài 2. Phân tích dạng lũy thừa

### Đề bài

Cho số nguyên dương $N > 1$.  
In ra dạng phân tích thừa số nguyên tố của $N$ dưới dạng lũy thừa.

### Ví dụ

Nếu:

$N = 360$

thì:

$360 = 2^3 \times 3^2 \times 5$

---

## Bài 3. Số lượng thừa số nguyên tố

### Đề bài

Cho số nguyên dương $N > 1$.  
Đếm tổng số thừa số nguyên tố của $N$, tính cả phần lặp.

---

## Bài 4. Số lượng thừa số nguyên tố khác nhau

### Đề bài

Cho số nguyên dương $N > 1$.  
Đếm có bao nhiêu thừa số nguyên tố khác nhau trong phân tích của $N$.

---

## Bài 5. Ước nguyên tố lớn nhất

### Đề bài

Cho số nguyên dương $N > 1$.  
Tìm ước nguyên tố lớn nhất của $N$.

---

## Bài 6. Ước nguyên tố nhỏ nhất

### Đề bài

Cho số nguyên dương $N > 1$.  
Tìm ước nguyên tố nhỏ nhất của $N$.

---

## Bài 7. Kiểm tra số có đúng hai thừa số nguyên tố khác nhau

### Đề bài

Cho số nguyên dương $N > 1$.  
Kiểm tra xem $N$ có đúng hai thừa số nguyên tố khác nhau hay không.

Nếu đúng, in `YES`.  
Ngược lại, in `NO`.

---

## Bài 8. Tích các thừa số nguyên tố khác nhau

### Đề bài

Cho số nguyên dương $N > 1$.  
Tính tích của các thừa số nguyên tố khác nhau của $N$.

---

# V. Bài tập về nhà

---

## Bài 1. Phân tích số lớn vừa

### Đề bài

Cho số nguyên dương $N$ với $2 \le N \le 10^9$.  
Hãy phân tích $N$ thành các thừa số nguyên tố.

---

## Bài 2. Thừa số nguyên tố xuất hiện nhiều nhất

### Đề bài

Cho số nguyên dương $N > 1$.  
Tìm thừa số nguyên tố có số lần xuất hiện lớn nhất trong phân tích của $N$.

Nếu có nhiều kết quả, in ra số nhỏ nhất.

---

## Bài 3. Tổng các thừa số nguyên tố

### Đề bài

Cho số nguyên dương $N > 1$.  
Tính tổng các thừa số nguyên tố của $N$, tính cả số lần lặp.

### Ví dụ

$12 = 2 \times 2 \times 3$

Tổng là:

$2 + 2 + 3 = 7$

---

## Bài 4. Tổng các thừa số nguyên tố khác nhau

### Đề bài

Cho số nguyên dương $N > 1$.  
Tính tổng các thừa số nguyên tố khác nhau của $N$.

---

## Bài 5. Kiểm tra số dạng p × q

### Đề bài

Một số được gọi là **semiprime** nếu nó là tích của đúng hai số nguyên tố, có thể trùng nhau.

Ví dụ:

- $4 = 2 \times 2$
- $6 = 2 \times 3$
- $9 = 3 \times 3$

Cho số nguyên dương $N$.  
Kiểm tra xem $N$ có phải semiprime hay không.

---

## Bài 6. Đếm số semiprime không vượt quá N

### Đề bài

Cho số nguyên dương $N$.  
Đếm bao nhiêu số semiprime không vượt quá $N$.

---

# VI. Lỗi học sinh thường gặp

---

## 1. Chỉ chia một lần cho mỗi ước

Ví dụ với $N = 72$:

Nếu chỉ chia một lần cho $2$, ta sẽ không nhận ra:

$72 = 2^3 \times 3^2$

Cần dùng vòng lặp:

```python
while n % i == 0:
    ...
```

---

## 2. Quên xử lý phần còn lại nếu N > 1

Ví dụ với $N = 14$:

- Sau khi chia cho $2$, còn lại $7$.
- Khi vòng lặp dừng, cần in thêm $7$.

---

## 3. Dùng `n / i` thay vì `n // i`

Trong Python:

```python
n //= i
```

là đúng vì ta cần phép chia nguyên.

Không nên dùng:

```python
n /= i
```

vì kết quả trở thành số thực.

---

## 4. Duyệt quá xa đến N

Cách này đúng nhưng chậm:

```python
for i in range(2, n + 1):
    ...
```

Nên tối ưu bằng điều kiện:

```python
while i * i <= n:
    ...
```

---

## 5. Không cập nhật N trong quá trình chia

Nếu quên dòng:

```python
n //= i
```

vòng lặp `while n % i == 0` sẽ chạy mãi không dừng.

---

# VII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Phân tích thừa số nguyên tố

### Bài toán

Cho số nguyên dương $N$ với $2 \le N \le 10^9$.  
Hãy phân tích $N$ thành thừa số nguyên tố và in ra theo thứ tự tăng dần.

### Input

- Một dòng chứa số nguyên dương $N$.

### Output

- Mỗi thừa số nguyên tố in trên một dòng.

### Ví dụ

#### Input

```text
84
```

#### Output

```text
2
2
3
7
```

---

## Đề 2. Ước nguyên tố lớn nhất

### Bài toán

Cho số nguyên dương $N > 1$.  
Hãy tìm ước nguyên tố lớn nhất của $N$.

### Ví dụ

#### Input

```text
630
```

#### Output

```text
7
```

---

## Đề 3. Đếm thừa số nguyên tố khác nhau

### Bài toán

Cho số nguyên dương $N > 1$.  
Hãy đếm số lượng thừa số nguyên tố khác nhau trong phân tích của $N$.

### Ví dụ

#### Input

```text
360
```

#### Output

```text
3
```

### Giải thích

$360 = 2^3 \times 3^2 \times 5$

Có ba thừa số nguyên tố khác nhau là:

$2, 3, 5$

---

## Đề 4. Tích các thừa số nguyên tố khác nhau

### Bài toán

Cho số nguyên dương $N > 1$.  
Tính tích của các thừa số nguyên tố khác nhau của $N$.

### Ví dụ

#### Input

```text
72
```

#### Output

```text
6
```

### Giải thích

$72 = 2^3 \times 3^2$

Tích các thừa số nguyên tố khác nhau là:

$2 \times 3 = 6$

---

# VIII. Ghi nhớ cuối bài

- Mọi số nguyên dương lớn hơn $1$ đều phân tích được thành tích các số nguyên tố.
- Muốn tìm thừa số nguyên tố, ta chia liên tiếp cho các ước từ nhỏ đến lớn.
- Khi một ước chia hết, phải chia nhiều lần cho đến khi không còn chia được nữa.
- Chỉ cần thử đến khi $i \times i \le N$.
- Nếu vòng lặp kết thúc mà $N > 1$, thì $N$ còn lại là một số nguyên tố.
- Các bài toán thường gặp:
  - Phân tích số.
  - Tìm ước nguyên tố lớn nhất.
  - Đếm số lượng thừa số nguyên tố.
  - Tính tổng hoặc tích các thừa số nguyên tố.

---

# IX. Tóm tắt bài học

## Bài 24. Phân tích thừa số nguyên tố

- Khái niệm:
  - Thừa số nguyên tố.
  - Phân tích thành thừa số nguyên tố.
- Ví dụ:
  - $60 = 2^2 \times 3 \times 5$
  - $72 = 2^3 \times 3^2$
- Thuật toán cơ bản:

```python
n = int(input())

i = 2

while i * i <= n:
    while n % i == 0:
        print(i)
        n //= i
    i += 1

if n > 1:
    print(n)
```

- Độ phức tạp xấp xỉ: $O(\sqrt{N})$
- Ý tưởng quan trọng:
  - Chia liên tiếp.
  - Giảm dần $N$.
  - Xử lý phần còn lại nếu $N > 1$.
