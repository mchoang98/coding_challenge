# Bài 27. Hệ đếm và chuyển đổi cơ số

---

# I. Mục tiêu bài học

Sau bài học này, học sinh cần đạt được các yêu cầu sau:

## 1. Về kiến thức

- Hiểu khái niệm **hệ đếm**.
- Biết các hệ đếm thường gặp:
  - Hệ nhị phân cơ số $2$.
  - Hệ thập phân cơ số $10$.
  - Hệ thập lục phân cơ số $16$.
- Hiểu giá trị của mỗi chữ số phụ thuộc vào vị trí.
- Nắm được hai dạng chuyển đổi cơ bản:
  - Từ hệ cơ số $b$ sang hệ $10$.
  - Từ hệ $10$ sang hệ cơ số $b$.

## 2. Về kỹ năng

- Chuyển đổi thủ công các số nhỏ giữa các hệ đếm.
- Viết được chương trình:
  - Đổi từ hệ $10$ sang hệ $2$.
  - Đổi từ hệ $2$ sang hệ $10$.
  - Đổi từ hệ $10$ sang hệ $16$.
- Biết xử lý chữ số từ `A` đến `F` trong hệ $16$.
- Làm quen với việc biểu diễn số bằng xâu ký tự.

## 3. Về tư duy

- Hiểu rằng cùng một giá trị có thể có nhiều cách biểu diễn khác nhau.
- Biết tách một bài toán thành:
  - Lấy chữ số.
  - Xác định trọng số vị trí.
  - Ghép kết quả.
- Tăng khả năng xử lý xâu và số trong các bài thi chuyên Tin.

---

# II. Lý thuyết

## 1. Hệ đếm là gì?

Hệ đếm là cách dùng các ký hiệu để biểu diễn số.

Mỗi hệ đếm có một **cơ số**.

### Ví dụ

- Hệ thập phân có cơ số $10$.
- Hệ nhị phân có cơ số $2$.
- Hệ thập lục phân có cơ số $16$.

---

## 2. Hệ thập phân

Hệ thập phân dùng $10$ chữ số:

$0, 1, 2, 3, 4, 5, 6, 7, 8, 9$

### Ví dụ

Số $538$ được hiểu là:

$5 \times 10^2 + 3 \times 10^1 + 8 \times 10^0$

---

## 3. Hệ nhị phân

Hệ nhị phân dùng hai chữ số:

$0, 1$

### Ví dụ

Số $1011_2$ có giá trị thập phân là:

$1 \times 2^3 + 0 \times 2^2 + 1 \times 2^1 + 1 \times 2^0 = 11$

---

## 4. Hệ thập lục phân

Hệ thập lục phân dùng $16$ ký hiệu:

$0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F$

Trong đó:

- $A = 10$
- $B = 11$
- $C = 12$
- $D = 13$
- $E = 14$
- $F = 15$

---

## 5. Đổi từ hệ cơ số b sang hệ 10

Giả sử số có dạng:

$a_k a_{k-1} ... a_1 a_0$

ở hệ cơ số $b$.

Giá trị trong hệ $10$ là:

$a_k \times b^k + a_{k-1} \times b^{k-1} + ... + a_1 \times b + a_0$

---

## 6. Ví dụ đổi nhị phân sang thập phân

Đổi:

$1101_2$

Ta có:

$1 \times 2^3 + 1 \times 2^2 + 0 \times 2^1 + 1 \times 2^0$

$= 8 + 4 + 0 + 1 = 13$

Vậy:

$1101_2 = 13_{10}$

---

## 7. Cách tính nhanh bằng quét từ trái sang phải

Nếu đang có giá trị hiện tại là `value`, đọc thêm chữ số mới `digit`, ta cập nhật:

$value = value \times base + digit$

### Ví dụ với 1101₂

- Bắt đầu: `value = 0`
- Đọc `1`: `value = 0 * 2 + 1 = 1`
- Đọc `1`: `value = 1 * 2 + 1 = 3`
- Đọc `0`: `value = 3 * 2 + 0 = 6`
- Đọc `1`: `value = 6 * 2 + 1 = 13`

---

## 8. Đổi từ hệ 10 sang hệ cơ số b

### Ý tưởng

Muốn đổi số $N$ từ hệ $10$ sang hệ cơ số $b$:

1. Chia $N$ cho $b$.
2. Ghi lại phần dư.
3. Cập nhật $N$ bằng thương.
4. Lặp lại cho đến khi $N = 0$.
5. Đọc các phần dư theo thứ tự ngược lại.

---

## 9. Ví dụ đổi 13 sang nhị phân

Ta chia liên tiếp cho $2$:

- $13 : 2 = 6$, dư $1$
- $6 : 2 = 3$, dư $0$
- $3 : 2 = 1$, dư $1$
- $1 : 2 = 0$, dư $1$

Đọc các số dư từ dưới lên:

$1101_2$

---

## 10. Đổi 255 sang hệ 16

Ta chia liên tiếp cho $16$:

- $255 : 16 = 15$, dư $15 = F$
- $15 : 16 = 0$, dư $15 = F$

Vậy:

$255_{10} = FF_{16}$

---

## 11. Bảng chữ số hệ 16

| Giá trị | Ký hiệu |
|---:|:---|
| 10 | A |
| 11 | B |
| 12 | C |
| 13 | D |
| 14 | E |
| 15 | F |

---

# III. Ví dụ minh họa

---

## Ví dụ 1. Đổi số từ hệ 10 sang hệ 2

### 1. Đề bài

Cho số nguyên không âm $N$.  
Hãy in ra biểu diễn nhị phân của $N$.

---

### 2. Code Python

```python
n = int(input())

if n == 0:
    print("0")
else:
    result = ""

    while n > 0:
        digit = n % 2
        result = str(digit) + result
        n //= 2

    print(result)
```

---

### 3. Input

```text
13
```

### 4. Output

```text
1101
```

---

## Ví dụ 2. Đổi số nhị phân sang hệ 10

### 1. Đề bài

Cho một xâu nhị phân.  
Hãy tính giá trị của nó trong hệ thập phân.

---

### 2. Code Python

```python
s = input().strip()

value = 0

for ch in s:
    digit = int(ch)
    value = value * 2 + digit

print(value)
```

---

### 3. Input

```text
1101
```

### 4. Output

```text
13
```

---

## Ví dụ 3. Đổi số từ hệ 10 sang hệ 16

### 1. Đề bài

Cho số nguyên không âm $N$.  
Hãy in ra biểu diễn của $N$ trong hệ $16$.

---

### 2. Code Python

```python
n = int(input())

digits = "0123456789ABCDEF"

if n == 0:
    print("0")
else:
    result = ""

    while n > 0:
        remainder = n % 16
        result = digits[remainder] + result
        n //= 16

    print(result)
```

---

### 3. Input

```text
255
```

### 4. Output

```text
FF
```

---

## Ví dụ 4. Đổi hệ 16 sang hệ 10

### 1. Đề bài

Cho một xâu biểu diễn số trong hệ $16$.  
Hãy đổi sang hệ $10$.

---

### 2. Code Python

```python
s = input().strip()

digits = "0123456789ABCDEF"

value = 0

for ch in s:
    digit = digits.index(ch)
    value = value * 16 + digit

print(value)
```

---

### 3. Input

```text
1A
```

### 4. Output

```text
26
```

---

## Ví dụ 5. Đổi nhị phân sang hệ 16 theo nhóm 4 bit

### 1. Ý tưởng

Mỗi chữ số hệ $16$ tương ứng với $4$ chữ số nhị phân.

Ví dụ:

- `0000` tương ứng `0`
- `1010` tương ứng `A`
- `1111` tương ứng `F`

---

### 2. Ví dụ

Đổi:

`10101100`

Ta chia thành nhóm:

`1010 1100`

- `1010 = A`
- `1100 = C`

Vậy:

`10101100₂ = AC₁₆`

---

# IV. Bài tập vận dụng

---

## Bài 1. Đổi hệ 10 sang hệ 2

### Đề bài

Cho số nguyên không âm $N$.  
In ra biểu diễn nhị phân của $N$.

---

## Bài 2. Đổi hệ 2 sang hệ 10

### Đề bài

Cho một xâu chỉ gồm `0` và `1`.  
Tính giá trị của xâu đó trong hệ thập phân.

---

## Bài 3. Đổi hệ 10 sang hệ 8

### Đề bài

Cho số nguyên không âm $N$.  
In ra biểu diễn cơ số $8$ của $N$.

---

## Bài 4. Đổi hệ 10 sang hệ 16

### Đề bài

Cho số nguyên không âm $N$.  
In ra biểu diễn cơ số $16$ của $N$.

---

## Bài 5. Đổi hệ 16 sang hệ 10

### Đề bài

Cho một xâu số hệ $16$.  
Đổi xâu đó sang hệ $10$.

---

## Bài 6. Đếm số bit 1

### Đề bài

Cho số nguyên không âm $N$.  
Hãy đếm số chữ số `1` trong biểu diễn nhị phân của $N$.

---

## Bài 7. Kiểm tra số nhị phân đối xứng

### Đề bài

Cho một xâu nhị phân.  
Kiểm tra xem xâu đó có đối xứng hay không.

---

## Bài 8. Nhị phân sang hệ 16

### Đề bài

Cho một xâu nhị phân có độ dài không vượt quá $200$.  
Hãy đổi sang hệ $16$.

---

# V. Bài tập về nhà

---

## Bài 1. Đổi từ hệ 10 sang hệ b

### Đề bài

Cho hai số nguyên dương $N$, $b$ với $2 \le b \le 16$.  
Hãy biểu diễn $N$ trong hệ cơ số $b$.

---

## Bài 2. Đổi từ hệ a sang hệ 10

### Đề bài

Cho cơ số $a$ với $2 \le a \le 16$ và một xâu số hợp lệ trong hệ $a$.  
Hãy đổi sang hệ $10$.

---

## Bài 3. Đổi từ hệ a sang hệ b

### Đề bài

Cho hai cơ số $a$, $b$ với $2 \le a, b \le 16$, và một số ở hệ $a$.  
Hãy đổi số đó sang hệ $b$.

---

## Bài 4. Số nhị phân lớn hơn

### Đề bài

Cho hai xâu nhị phân có cùng độ dài.  
Hãy xác định xâu nào biểu diễn giá trị lớn hơn.

---

## Bài 5. Cộng hai số nhị phân

### Đề bài

Cho hai xâu nhị phân.  
Hãy tính tổng của chúng dưới dạng nhị phân.

---

## Bài 6. Đếm số khác nhau theo hệ 2

### Đề bài

Cho các số nguyên từ $0$ đến $N$.  
Đếm có bao nhiêu số có đúng $K$ bit `1` trong biểu diễn nhị phân.

---

# VI. Lỗi học sinh thường gặp

---

## 1. Đọc số dư theo sai thứ tự

Khi đổi từ hệ $10$ sang hệ khác, các số dư phải được đọc từ dưới lên.

Nếu ghép sai chiều, kết quả sẽ sai.

---

## 2. Không xử lý riêng trường hợp N = 0

Nếu $N = 0$, kết quả cần in là:

`0`

---

## 3. Nhầm giá trị A, B, C, D, E, F

Trong hệ $16$:

- `A = 10`
- `B = 11`
- `C = 12`
- `D = 13`
- `E = 14`
- `F = 15`

---

## 4. Tính giá trị theo vị trí từ trái sang nhưng dùng sai số mũ

Cách an toàn hơn là dùng công thức cập nhật:

$value = value \times base + digit$

---

## 5. Quên chuẩn hóa ký tự in hoa

Nếu đề cho chữ thường trong hệ $16$, có thể dùng:

```python
s = s.upper()
```

---

# VII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Nhị phân sang hệ 16

### Bài toán

Cho xâu chỉ gồm hai ký tự `0` và `1`, biểu diễn một số nguyên không âm trong hệ nhị phân.  
Độ dài xâu không vượt quá $200$.

Hãy đổi số đó sang hệ $16$.

---

## Đề 2. Đổi cơ số

### Bài toán

Cho một số được biểu diễn trong hệ cơ số $a$.  
Hãy đổi số đó sang hệ cơ số $b$.

Biết rằng:

- $2 \le a, b \le 16$.
- Độ dài xâu không quá $50$.

---

## Đề 3. Đếm bit 1

### Bài toán

Cho số nguyên không âm $N$.  
Hãy đếm số chữ số `1` trong biểu diễn nhị phân của $N$.

---

## Đề 4. Cộng số nhị phân

### Bài toán

Cho hai xâu nhị phân.  
Hãy tính tổng của chúng và in kết quả dưới dạng nhị phân.

---

# VIII. Ghi nhớ cuối bài

- Hệ đếm là cách biểu diễn số bằng các ký hiệu theo một cơ số nhất định.
- Hệ thường gặp:
  - Cơ số $2$.
  - Cơ số $10$.
  - Cơ số $16$.
- Đổi từ hệ $b$ sang hệ $10$:
  - Quét chữ số từ trái sang phải.
  - Cập nhật $value = value \times b + digit$.
- Đổi từ hệ $10$ sang hệ $b$:
  - Chia liên tiếp cho $b$.
  - Lấy các phần dư theo chiều ngược lại.
- Hệ $16$ dùng thêm các ký hiệu:
  - `A, B, C, D, E, F`.

---

# IX. Tóm tắt bài học

## Bài 27. Hệ đếm và chuyển đổi cơ số

- Một số có thể được biểu diễn trong nhiều hệ cơ số.
- Đổi từ nhị phân sang thập phân:

```python
value = 0

for ch in s:
    value = value * 2 + int(ch)
```

- Đổi từ thập phân sang nhị phân:

```python
result = ""

while n > 0:
    result = str(n % 2) + result
    n //= 2
```

- Các dạng bài thường gặp:
  - Đổi cơ số.
  - Đếm bit `1`.
  - Nhị phân sang hệ $16$.
  - Cộng số nhị phân.
