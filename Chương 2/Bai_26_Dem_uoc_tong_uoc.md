# Bài 26. Đếm ước và tính tổng ước từ phân tích thừa số nguyên tố

---

# I. Mục tiêu bài học

Sau bài học này, học sinh cần đạt được các yêu cầu sau:

## 1. Về kiến thức

- Hiểu mối liên hệ giữa:
  - Phân tích thừa số nguyên tố.
  - Số lượng ước.
  - Tổng các ước.
- Nắm được công thức tính số ước của $N$.
- Nắm được công thức tính tổng các ước của $N$.
- Hiểu vì sao các công thức này đúng ở mức trực quan.
- Biết phân biệt:
  - Tổng mọi ước.
  - Tổng các ước thực sự nhỏ hơn $N$.

## 2. Về kỹ năng

- Phân tích $N$ thành dạng:

$N = p_1^{a_1} \times p_2^{a_2} \times ... \times p_k^{a_k}$

- Tính được:
  - Số lượng ước của $N$.
  - Tổng các ước của $N$.
- Viết được chương trình áp dụng trực tiếp công thức.
- Kiểm tra được một số có phải số hoàn hảo hay không.

## 3. Về tư duy

- Biết thay thế cách duyệt toàn bộ ước bằng công thức dựa trên phân tích nguyên tố.
- Hiểu tư duy “một kết quả số học có thể rút ra từ cấu trúc thừa số của số đó”.
- Tăng khả năng nhận diện bài toán số học nâng cao trong đề thi.

---

# II. Lý thuyết

## 1. Nhắc lại phân tích thừa số nguyên tố

Giả sử:

$N = p_1^{a_1} \times p_2^{a_2} \times ... \times p_k^{a_k}$

Trong đó:

- $p_1, p_2, ..., p_k$ là các số nguyên tố khác nhau.
- $a_1, a_2, ..., a_k$ là các số mũ nguyên dương.

### Ví dụ

$72 = 2^3 \times 3^2$

---

## 2. Công thức tính số lượng ước

Nếu:

$N = p_1^{a_1} \times p_2^{a_2} \times ... \times p_k^{a_k}$

thì số lượng ước nguyên dương của $N$ là:

$d(N) = (a_1 + 1)(a_2 + 1)...(a_k + 1)$

---

## 3. Vì sao công thức số ước đúng?

Mỗi ước của $N$ được tạo ra bằng cách chọn số mũ cho từng thừa số nguyên tố.

Ví dụ:

$72 = 2^3 \times 3^2$

Một ước của $72$ có dạng:

$2^x \times 3^y$

Trong đó:

- $x$ có thể chọn từ $0$ đến $3$: có $4$ cách.
- $y$ có thể chọn từ $0$ đến $2$: có $3$ cách.

Vì vậy số ước là:

$4 \times 3 = 12$

---

## 4. Ví dụ tính số ước

### Ví dụ 1

$12 = 2^2 \times 3^1$

Số ước là:

$(2 + 1)(1 + 1) = 3 \times 2 = 6$

Các ước là:

$1, 2, 3, 4, 6, 12$

---

### Ví dụ 2

$360 = 2^3 \times 3^2 \times 5^1$

Số ước là:

$(3 + 1)(2 + 1)(1 + 1) = 4 \times 3 \times 2 = 24$

---

## 5. Công thức tính tổng các ước

Nếu:

$N = p_1^{a_1} \times p_2^{a_2} \times ... \times p_k^{a_k}$

thì tổng các ước của $N$ là:

$\sigma(N) = (1 + p_1 + p_1^2 + ... + p_1^{a_1}) \times ... \times (1 + p_k + p_k^2 + ... + p_k^{a_k})$

---

## 6. Ví dụ tính tổng các ước

### Ví dụ 1

$12 = 2^2 \times 3^1$

Tổng các ước là:

$(1 + 2 + 4)(1 + 3) = 7 \times 4 = 28$

Quả thật:

$1 + 2 + 3 + 4 + 6 + 12 = 28$

---

### Ví dụ 2

$18 = 2^1 \times 3^2$

Tổng các ước là:

$(1 + 2)(1 + 3 + 9) = 3 \times 13 = 39$

Các ước của $18$ là:

$1, 2, 3, 6, 9, 18$

Tổng là:

$39$

---

## 7. Tổng các ước thực sự nhỏ hơn N

Các ước thực sự của $N$ là các ước nhỏ hơn $N$.

Nếu tổng mọi ước là $\sigma(N)$, thì tổng các ước thực sự là:

$\sigma(N) - N$

---

## 8. Số hoàn hảo

Một số $N$ được gọi là **số hoàn hảo** nếu tổng các ước thực sự của nó bằng chính nó.

Điều kiện:

$\sigma(N) - N = N$

hay tương đương:

$\sigma(N) = 2N$

### Ví dụ

$6$ là số hoàn hảo vì các ước thực sự là:

$1, 2, 3$

và:

$1 + 2 + 3 = 6$

---

## 9. Hướng cài đặt

Trong quá trình phân tích thừa số nguyên tố, với mỗi thừa số $p$:

- Đếm số mũ `count`.
- Cập nhật số ước:

`num_divisors *= count + 1`

- Tính tổng lũy thừa:

$1 + p + p^2 + ... + p^{count}$

- Cập nhật tổng ước bằng phép nhân.

---

# III. Ví dụ minh họa

---

## Ví dụ 1. Tính số lượng ước của N

### 1. Đề bài

Cho số nguyên dương $N$.  
Hãy tính số lượng ước nguyên dương của $N$.

---

### 2. Code Python

```python
n = int(input())

i = 2
num_divisors = 1

while i * i <= n:
    count = 0

    while n % i == 0:
        count += 1
        n //= i

    if count > 0:
        num_divisors *= count + 1

    i += 1

if n > 1:
    num_divisors *= 2

print(num_divisors)
```

---

### 3. Input

```text
72
```

### 4. Output

```text
12
```

---

### 5. Giải thích

$72 = 2^3 \times 3^2$

Số ước là:

$(3 + 1)(2 + 1) = 12$

---

## Ví dụ 2. Tính tổng các ước của N

### 1. Đề bài

Cho số nguyên dương $N$.  
Hãy tính tổng tất cả các ước nguyên dương của $N$.

---

### 2. Code Python

```python
n = int(input())

i = 2
sum_divisors = 1

while i * i <= n:
    count = 0
    power_sum = 1
    current_power = 1

    while n % i == 0:
        count += 1
        n //= i

        current_power *= i
        power_sum += current_power

    if count > 0:
        sum_divisors *= power_sum

    i += 1

if n > 1:
    sum_divisors *= 1 + n

print(sum_divisors)
```

---

### 3. Input

```text
12
```

### 4. Output

```text
28
```

---

### 5. Giải thích

$12 = 2^2 \times 3$

Tổng ước là:

$(1 + 2 + 4)(1 + 3) = 28$

---

## Ví dụ 3. Kiểm tra số hoàn hảo

### 1. Đề bài

Cho số nguyên dương $N$.  
Kiểm tra xem $N$ có phải số hoàn hảo hay không.

Nếu đúng, in `YES`.  
Ngược lại, in `NO`.

---

### 2. Code Python

```python
n = int(input())
original_n = n

i = 2
sum_divisors = 1

while i * i <= n:
    count = 0
    power_sum = 1
    current_power = 1

    while n % i == 0:
        count += 1
        n //= i

        current_power *= i
        power_sum += current_power

    if count > 0:
        sum_divisors *= power_sum

    i += 1

if n > 1:
    sum_divisors *= 1 + n

proper_divisor_sum = sum_divisors - original_n

if proper_divisor_sum == original_n:
    print("YES")
else:
    print("NO")
```

---

### 3. Input

```text
6
```

### 4. Output

```text
YES
```

---

## Ví dụ 4. Tính đồng thời số ước và tổng ước

### 1. Đề bài

Cho số nguyên dương $N$.  
Hãy in ra:

1. Số lượng ước của $N$.
2. Tổng các ước của $N$.

---

### 2. Code Python

```python
n = int(input())

i = 2
num_divisors = 1
sum_divisors = 1

while i * i <= n:
    count = 0
    power_sum = 1
    current_power = 1

    while n % i == 0:
        count += 1
        n //= i

        current_power *= i
        power_sum += current_power

    if count > 0:
        num_divisors *= count + 1
        sum_divisors *= power_sum

    i += 1

if n > 1:
    num_divisors *= 2
    sum_divisors *= 1 + n

print(num_divisors)
print(sum_divisors)
```

---

### 3. Input

```text
18
```

### 4. Output

```text
6
39
```

---

# IV. Bài tập vận dụng

---

## Bài 1. Đếm số ước

### Đề bài

Cho số nguyên dương $N$.  
Tính số lượng ước nguyên dương của $N$.

---

## Bài 2. Tổng các ước

### Đề bài

Cho số nguyên dương $N$.  
Tính tổng tất cả các ước nguyên dương của $N$.

---

## Bài 3. Tổng các ước thực sự

### Đề bài

Cho số nguyên dương $N$.  
Tính tổng các ước nguyên dương nhỏ hơn $N$.

---

## Bài 4. Kiểm tra số hoàn hảo

### Đề bài

Cho số nguyên dương $N$.  
Kiểm tra xem $N$ có phải số hoàn hảo hay không.

---

## Bài 5. Kiểm tra số có đúng K ước

### Đề bài

Cho hai số nguyên dương $N$, $K$.  
Kiểm tra xem $N$ có đúng $K$ ước nguyên dương hay không.

---

## Bài 6. Số có đúng ba ước

### Đề bài

Cho số nguyên dương $N$.  
Kiểm tra xem $N$ có đúng ba ước nguyên dương hay không.

### Gợi ý

Một số có đúng ba ước khi nó là bình phương của một số nguyên tố.

---

## Bài 7. Tìm số ước nhiều nhất trong đoạn

### Đề bài

Cho hai số nguyên dương $A$, $B$.  
Tìm số trong đoạn $[A, B]$ có nhiều ước nhất.

Nếu có nhiều số, in ra số nhỏ nhất.

---

# V. Bài tập về nhà

---

## Bài 1. Đếm số có đúng 4 ước

### Đề bài

Cho số nguyên dương $N$.  
Đếm bao nhiêu số từ $1$ đến $N$ có đúng $4$ ước nguyên dương.

---

## Bài 2. Số phong phú

### Đề bài

Một số $N$ được gọi là **số phong phú** nếu tổng các ước thực sự của nó lớn hơn $N$.

Cho số nguyên dương $N$.  
Kiểm tra xem $N$ có phải số phong phú hay không.

---

## Bài 3. Số thiếu

### Đề bài

Một số $N$ được gọi là **số thiếu** nếu tổng các ước thực sự của nó nhỏ hơn $N$.

Cho số nguyên dương $N$.  
Kiểm tra xem $N$ có phải số thiếu hay không.

---

## Bài 4. Tổng ước lớn nhất

### Đề bài

Cho đoạn $[A, B]$.  
Tìm số có tổng các ước lớn nhất trong đoạn đó.

---

## Bài 5. Cặp số bạn bè

### Đề bài

Hai số $A$, $B$ được gọi là **số bạn bè** nếu:

- Tổng các ước thực sự của $A$ bằng $B$.
- Tổng các ước thực sự của $B$ bằng $A$.

Cho hai số $A$, $B$.  
Kiểm tra xem chúng có phải cặp số bạn bè hay không.

---

# VI. Lỗi học sinh thường gặp

---

## 1. Nhầm số ước với tổng ước

Ví dụ:

$12$ có:

- $6$ ước.
- Tổng các ước là $28$.

Hai kết quả này khác nhau hoàn toàn.

---

## 2. Quên cộng trường hợp số nguyên tố còn lại

Nếu sau khi phân tích mà `n > 1`, cần xử lý thêm một thừa số có số mũ $1$.

---

## 3. Tính tổng ước nhưng không giữ lại N gốc

Khi kiểm tra số hoàn hảo, cần lưu:

```python
original_n = n
```

vì `n` sẽ bị thay đổi trong quá trình phân tích.

---

## 4. Cộng thiếu lũy thừa của thừa số nguyên tố

Ví dụ với $2^3$, tổng phần này phải là:

$1 + 2 + 4 + 8$

Không được chỉ tính:

$1 + 2 + 8$

---

## 5. Dùng công thức nhưng không hiểu bản chất

Học sinh nên hiểu rằng:

- Số ước đến từ việc chọn số mũ.
- Tổng ước đến từ việc nhân các tổng lũy thừa.

---

# VII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Số lượng ước

### Bài toán

Cho số nguyên dương $N$ với $1 \le N \le 10^9$.  
Hãy tính số lượng ước nguyên dương của $N$.

---

## Đề 2. Tổng các ước

### Bài toán

Cho số nguyên dương $N$ với $1 \le N \le 10^9$.  
Hãy tính tổng các ước nguyên dương của $N$.

---

## Đề 3. Số hoàn hảo

### Bài toán

Cho số nguyên dương $N$.  
Kiểm tra xem $N$ có phải số hoàn hảo hay không.

---

## Đề 4. Số có nhiều ước nhất

### Bài toán

Cho đoạn $[A, B]$.  
Tìm số có nhiều ước nguyên dương nhất trong đoạn đó.

Nếu có nhiều số, in ra số nhỏ nhất.

---

# VIII. Ghi nhớ cuối bài

- Nếu:

$N = p_1^{a_1} \times p_2^{a_2} \times ... \times p_k^{a_k}$

thì số lượng ước là:

$(a_1 + 1)(a_2 + 1)...(a_k + 1)$

- Tổng các ước là:

$(1 + p_1 + ... + p_1^{a_1}) \times ... \times (1 + p_k + ... + p_k^{a_k})$

- Tổng các ước thực sự bằng:

$\sigma(N) - N$

- Số hoàn hảo thỏa:

$\sigma(N) = 2N$

---

# IX. Tóm tắt bài học

## Bài 26. Đếm ước và tính tổng ước

- Cần phân tích $N$ thành thừa số nguyên tố.
- Từ các số mũ, ta tính nhanh:
  - Số lượng ước.
  - Tổng các ước.
- Ví dụ:

$72 = 2^3 \times 3^2$

Số ước:

$(3 + 1)(2 + 1) = 12$

- Đây là chuyên đề rất quan trọng trong các bài toán số học lập trình.
