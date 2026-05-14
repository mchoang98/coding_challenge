# Bài 25. Sàng Eratosthenes và ứng dụng

---

# I. Mục tiêu bài học

Sau bài học này, học sinh cần đạt được các yêu cầu sau:

## 1. Về kiến thức

- Hiểu hạn chế của việc kiểm tra số nguyên tố từng số một.
- Nắm được ý tưởng của **sàng Eratosthenes**.
- Biết vì sao thuật toán sàng có thể liệt kê nhanh các số nguyên tố không vượt quá $N$.
- Hiểu vai trò của mảng đánh dấu `prime`.
- Biết ý nghĩa của việc bắt đầu gạch từ $i \times i$.

## 2. Về kỹ năng

- Viết được chương trình sàng số nguyên tố.
- Liệt kê được các số nguyên tố không vượt quá $N$.
- Đếm được số lượng số nguyên tố từ $1$ đến $N$.
- Xây dựng mảng tiền tố để trả lời nhanh số lượng số nguyên tố trong đoạn $[L, R]$.
- Vận dụng sàng vào một số bài toán cơ bản.

## 3. Về tư duy

- Biết chọn đúng công cụ:
  - Kiểm tra một số nguyên tố: dùng $O(\sqrt{N})$.
  - Kiểm tra rất nhiều số: dùng sàng.
- Hiểu tư duy “đánh dấu trước, trả lời nhanh về sau”.
- Làm quen với kỹ thuật tiền xử lý dữ liệu.

---

# II. Lý thuyết

## 1. Vấn đề đặt ra

Ở bài trước, ta đã biết cách kiểm tra một số $N$ có phải số nguyên tố hay không bằng thuật toán $O(\sqrt{N})$.

Tuy nhiên, nếu cần:

- Liệt kê tất cả số nguyên tố đến $10^6$.
- Kiểm tra rất nhiều số có nguyên tố hay không.
- Trả lời nhiều truy vấn về số lượng số nguyên tố trong đoạn.

thì việc gọi `is_prime()` nhiều lần có thể tốn thời gian.

---

## 2. Ý tưởng của sàng Eratosthenes

Ta cần tìm tất cả các số nguyên tố từ $2$ đến $N$.

Ý tưởng:

1. Ban đầu giả sử mọi số từ $2$ đến $N$ đều là số nguyên tố.
2. Số $2$ là số nguyên tố.
3. Gạch bỏ mọi bội lớn hơn của $2$:
   - $4, 6, 8, 10, ...$
4. Số tiếp theo chưa bị gạch là $3$.
5. Gạch bỏ mọi bội lớn hơn của $3$:
   - $6, 9, 12, 15, ...$
6. Tiếp tục quá trình đó.
7. Những số không bị gạch chính là số nguyên tố.

---

## 3. Ví dụ sàng đến 30

Ban đầu xét các số:

$2, 3, 4, 5, 6, 7, 8, 9, ..., 30$

### Gạch theo bội của 2

Gạch:

$4, 6, 8, 10, 12, ..., 30$

### Gạch theo bội của 3

Gạch:

$6, 9, 12, 15, 18, ..., 30$

### Gạch theo bội của 5

Gạch:

$10, 15, 20, 25, 30$

Các số còn lại là:

$2, 3, 5, 7, 11, 13, 17, 19, 23, 29$

---

## 4. Vì sao chỉ cần sàng đến $\sqrt{N}$?

Nếu một số $x$ là hợp số, thì nó có ít nhất một ước không vượt quá $\sqrt{x}$.

Do đó, với mọi hợp số không vượt quá $N$, ta sẽ loại được chúng khi duyệt các ước từ $2$ đến $\sqrt{N}$.

Vì vậy, vòng lặp chính chỉ cần chạy khi:

$i \times i \le N$

---

## 5. Vì sao bắt đầu gạch từ i × i?

Khi xử lý số $i$, các bội nhỏ hơn $i \times i$ đã được gạch trước đó.

Ví dụ với $i = 5$:

- $5 \times 2 = 10$ đã bị gạch khi xử lý $2$.
- $5 \times 3 = 15$ đã bị gạch khi xử lý $3$.
- $5 \times 4 = 20$ đã bị gạch khi xử lý $2$.

Vì vậy, ta chỉ cần bắt đầu từ:

$i \times i$

---

## 6. Mảng đánh dấu prime

Ta dùng một mảng Boolean:

- `prime[x] = True`: tạm coi $x$ là số nguyên tố.
- `prime[x] = False`: $x$ không phải số nguyên tố.

Ban đầu:

- `prime[0] = False`
- `prime[1] = False`
- `prime[2..N] = True`

---

## 7. Thuật toán sàng cơ bản

### Các bước

1. Tạo mảng `prime` có $N+1$ phần tử, ban đầu đều là `True`.
2. Gán:
   - `prime[0] = False`
   - `prime[1] = False`
3. Duyệt `i` từ $2$ đến $\sqrt{N}$.
4. Nếu `prime[i]` là `True`, gạch các bội của `i` từ `i * i`.
5. Những chỉ số còn `True` là số nguyên tố.

---

## 8. Độ phức tạp

Sàng Eratosthenes có độ phức tạp xấp xỉ:

$O(N \log \log N)$

Đây là thuật toán rất hiệu quả khi cần xử lý nhiều số nguyên tố trong một phạm vi lớn.

---

## 9. Khi nào dùng is_prime, khi nào dùng sàng?

| Tình huống | Cách nên dùng |
|---|---|
| Kiểm tra một số $N$ rất lớn | `is_prime(N)` với $O(\sqrt{N})$ |
| Liệt kê nguyên tố đến $N$ | Sàng Eratosthenes |
| Kiểm tra nhiều số $\le N$ | Sàng trước |
| Trả lời nhiều truy vấn trong đoạn | Sàng + mảng tiền tố |

---

# III. Ví dụ minh họa

---

## Ví dụ 1. Liệt kê số nguyên tố không vượt quá N

### 1. Đề bài

Cho số nguyên dương $N$.  
Hãy liệt kê tất cả các số nguyên tố không vượt quá $N$.

---

### 2. Code Python

```python
n = int(input())

prime = [True] * (n + 1)

if n >= 0:
    prime[0] = False

if n >= 1:
    prime[1] = False

i = 2

while i * i <= n:
    if prime[i]:
        for j in range(i * i, n + 1, i):
            prime[j] = False
    i += 1

for x in range(2, n + 1):
    if prime[x]:
        print(x)
```

---

### 3. Input

```text
30
```

### 4. Output

```text
2
3
5
7
11
13
17
19
23
29
```

---

## Ví dụ 2. Đếm số nguyên tố không vượt quá N

### 1. Đề bài

Cho số nguyên dương $N$.  
Đếm xem có bao nhiêu số nguyên tố không vượt quá $N$.

---

### 2. Code Python

```python
n = int(input())

prime = [True] * (n + 1)

if n >= 0:
    prime[0] = False

if n >= 1:
    prime[1] = False

i = 2

while i * i <= n:
    if prime[i]:
        for j in range(i * i, n + 1, i):
            prime[j] = False
    i += 1

count = 0

for x in range(2, n + 1):
    if prime[x]:
        count += 1

print(count)
```

---

### 3. Input

```text
20
```

### 4. Output

```text
8
```

---

### 5. Giải thích

Các số nguyên tố không vượt quá $20$ là:

$2, 3, 5, 7, 11, 13, 17, 19$

Có tất cả $8$ số.

---

## Ví dụ 3. Kiểm tra nhanh nhiều số có nguyên tố hay không

### 1. Đề bài

Cho số nguyên dương $N$.  
Sau đó có $Q$ truy vấn, mỗi truy vấn là một số $x \le N$.

Hãy cho biết mỗi $x$ có phải số nguyên tố hay không.

---

### 2. Ý tưởng

- Sàng trước từ $1$ đến $N$.
- Với mỗi truy vấn:
  - Nếu `prime[x] == True`, in `YES`.
  - Ngược lại, in `NO`.

---

### 3. Code Python

```python
n = int(input())
q = int(input())

prime = [True] * (n + 1)

if n >= 0:
    prime[0] = False

if n >= 1:
    prime[1] = False

i = 2

while i * i <= n:
    if prime[i]:
        for j in range(i * i, n + 1, i):
            prime[j] = False
    i += 1

for _ in range(q):
    x = int(input())

    if prime[x]:
        print("YES")
    else:
        print("NO")
```

---

## Ví dụ 4. Đếm số nguyên tố trong đoạn [L, R]

### 1. Đề bài

Cho nhiều truy vấn.  
Mỗi truy vấn gồm hai số $L$, $R$.

Hãy đếm xem trong đoạn $[L, R]$ có bao nhiêu số nguyên tố.

---

### 2. Ý tưởng

Ta xây dựng mảng tiền tố:

`prefix[i] = số lượng số nguyên tố từ 1 đến i`

Khi đó, kết quả truy vấn $[L, R]$ là:

$prefix[R] - prefix[L - 1]$

---

### 3. Code Python

```python
n = int(input())
q = int(input())

prime = [True] * (n + 1)

prime[0] = False
prime[1] = False

i = 2

while i * i <= n:
    if prime[i]:
        for j in range(i * i, n + 1, i):
            prime[j] = False
    i += 1

prefix = [0] * (n + 1)

for i in range(1, n + 1):
    prefix[i] = prefix[i - 1]

    if prime[i]:
        prefix[i] += 1

for _ in range(q):
    l = int(input())
    r = int(input())

    result = prefix[r] - prefix[l - 1]
    print(result)
```

---

### 4. Ví dụ

#### Input

```text
30
2
1
10
11
30
```

#### Output

```text
4
6
```

---

### 5. Giải thích

- Trong đoạn $[1, 10]$ có: $2, 3, 5, 7$.
- Trong đoạn $[11, 30]$ có: $11, 13, 17, 19, 23, 29$.

---

# IV. Bài tập vận dụng

---

## Bài 1. Liệt kê số nguyên tố

### Đề bài

Cho số nguyên dương $N$.  
Liệt kê tất cả các số nguyên tố không vượt quá $N$.

---

## Bài 2. Đếm số nguyên tố

### Đề bài

Cho số nguyên dương $N$.  
Đếm số lượng số nguyên tố không vượt quá $N$.

---

## Bài 3. Tổng các số nguyên tố

### Đề bài

Cho số nguyên dương $N$.  
Tính tổng tất cả các số nguyên tố không vượt quá $N$.

---

## Bài 4. Số nguyên tố thứ K

### Đề bài

Cho số nguyên dương $K$.  
Tìm số nguyên tố thứ $K$.

---

## Bài 5. Nhiều truy vấn nguyên tố

### Đề bài

Cho $N$ và $Q$.  
Sau đó có $Q$ truy vấn, mỗi truy vấn là số $x \le N$.

Hãy in `YES` nếu $x$ là số nguyên tố, ngược lại in `NO`.

---

## Bài 6. Đếm nguyên tố trong đoạn

### Đề bài

Cho nhiều truy vấn $[L, R]$.  
Đếm số lượng số nguyên tố trong mỗi đoạn.

---

## Bài 7. Tổng nguyên tố trong đoạn

### Đề bài

Cho nhiều truy vấn $[L, R]$.  
Tính tổng các số nguyên tố trong mỗi đoạn.

---

## Bài 8. Cặp Goldbach

### Đề bài

Cho số chẵn $N > 2$.  
Đếm số cặp số nguyên tố $(p, q)$ sao cho:

$p + q = N$

và:

$p \le q$

---

# V. Bài tập về nhà

---

## Bài 1. Số nguyên tố gần nhất

### Đề bài

Cho số nguyên dương $N$.  
Tìm:

- Số nguyên tố lớn nhất không vượt quá $N$.
- Số nguyên tố nhỏ nhất không nhỏ hơn $N$.

---

## Bài 2. Đếm cặp số nguyên tố có tổng bằng N

### Đề bài

Cho số nguyên dương $N$.  
Đếm số cặp số nguyên tố $(p, q)$ sao cho:

$p + q = N$

---

## Bài 3. Liệt kê số nguyên tố trong nhiều đoạn

### Đề bài

Cho $Q$ truy vấn.  
Mỗi truy vấn là đoạn $[L, R]$ với $R \le 10^6$.

Hãy liệt kê các số nguyên tố trong mỗi đoạn.

---

## Bài 4. Đếm số có đúng hai ước nguyên tố khác nhau

### Đề bài

Cho số nguyên dương $N$.  
Đếm bao nhiêu số trong đoạn từ $1$ đến $N$ có đúng hai ước nguyên tố khác nhau.

---

## Bài 5. Tìm số có nhiều ước nguyên tố nhất

### Đề bài

Cho số nguyên dương $N$.  
Trong đoạn từ $1$ đến $N$, tìm số có nhiều thừa số nguyên tố khác nhau nhất.

Nếu có nhiều số, in ra số nhỏ nhất.

---

# VI. Lỗi học sinh thường gặp

---

## 1. Không gán false cho 0 và 1

Cần nhớ:

- $0$ không phải số nguyên tố.
- $1$ không phải số nguyên tố.

Do đó phải có:

```python
prime[0] = False
prime[1] = False
```

---

## 2. Bắt đầu gạch từ i thay vì i × i

Ví dụ viết:

```python
for j in range(i, n + 1, i):
    prime[j] = False
```

sẽ gạch nhầm chính số nguyên tố $i$.

Cách đúng:

```python
for j in range(i * i, n + 1, i):
    prime[j] = False
```

---

## 3. Quên kiểm tra prime[i] trước khi gạch

Nếu không có:

```python
if prime[i]:
```

thì chương trình vẫn đúng nhưng làm nhiều phép gạch thừa.

---

## 4. Sai kích thước mảng

Nếu cần xử lý đến $N$, cần tạo mảng có kích thước:

$N + 1$

---

## 5. Dùng sàng khi N quá lớn so với bộ nhớ

Sàng phù hợp khi giới hạn $N$ vừa phải, ví dụ $10^6$, $10^7$ tùy môi trường.

Nếu $N$ cực lớn và chỉ cần kiểm tra một số, nên dùng `is_prime()`.

---

# VII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Liệt kê số nguyên tố

### Bài toán

Cho số nguyên dương $N$ với $2 \le N \le 10^6$.  
Hãy liệt kê tất cả các số nguyên tố không vượt quá $N$.

---

## Đề 2. Truy vấn số nguyên tố

### Bài toán

Cho số nguyên dương $N$ và $Q$ truy vấn.  
Mỗi truy vấn là một số $x$ với $1 \le x \le N$.

Hãy cho biết $x$ có phải là số nguyên tố hay không.

---

## Đề 3. Đếm số nguyên tố trong đoạn

### Bài toán

Cho $Q$ truy vấn.  
Mỗi truy vấn gồm hai số $L$, $R$ với $1 \le L \le R \le 10^6$.

Hãy in ra số lượng số nguyên tố trong mỗi đoạn $[L, R]$.

---

## Đề 4. Tổng các số nguyên tố trong đoạn

### Bài toán

Cho $Q$ truy vấn.  
Mỗi truy vấn gồm hai số $L$, $R$ với $1 \le L \le R \le 10^6$.

Hãy tính tổng các số nguyên tố trong mỗi đoạn $[L, R]$.

---

# VIII. Ghi nhớ cuối bài

- Sàng Eratosthenes dùng để tìm nhanh tất cả số nguyên tố không vượt quá $N$.
- Ban đầu coi mọi số từ $2$ đến $N$ là nguyên tố.
- Dùng từng số nguyên tố nhỏ để gạch bỏ các bội của nó.
- Chỉ cần xử lý khi $i \times i \le N$.
- Khi gạch bội của $i$, nên bắt đầu từ $i \times i$.
- Sàng rất hiệu quả cho:
  - Liệt kê nguyên tố.
  - Đếm nguyên tố.
  - Kiểm tra nhiều truy vấn.
  - Kết hợp mảng tiền tố để trả lời đoạn.

---

# IX. Tóm tắt bài học

## Bài 25. Sàng Eratosthenes và ứng dụng

- Mục tiêu:
  - Tìm tất cả số nguyên tố từ $1$ đến $N$.
- Mảng đánh dấu:
  - `prime[x] = True` nếu $x$ đang được coi là nguyên tố.
- Thuật toán cơ bản:

```python
prime = [True] * (n + 1)
prime[0] = False
prime[1] = False

i = 2

while i * i <= n:
    if prime[i]:
        for j in range(i * i, n + 1, i):
            prime[j] = False
    i += 1
```

- Độ phức tạp: $O(N \log \log N)$
- Ứng dụng:
  - Liệt kê nguyên tố.
  - Đếm nguyên tố.
  - Trả lời truy vấn nguyên tố.
  - Đếm số nguyên tố trong đoạn bằng prefix sum.
