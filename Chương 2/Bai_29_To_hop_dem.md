# Bài 29. Tổ hợp đếm cơ bản

---

# I. Mục tiêu bài học

Sau bài học này, học sinh cần đạt được các yêu cầu sau:

## 1. Về kiến thức

- Hiểu được tư duy **đếm số cách**.
- Nắm được:
  - Nguyên lý cộng.
  - Nguyên lý nhân.
  - Hoán vị.
  - Chỉnh hợp.
  - Tổ hợp.
- Biết phân biệt các tình huống:
  - Có xét thứ tự.
  - Không xét thứ tự.
  - Có lặp.
  - Không lặp.

## 2. Về kỹ năng

- Tính được số cách trong các bài toán cơ bản.
- Nhận diện đúng công thức phù hợp.
- Viết được chương trình tính:
  - Giai thừa.
  - Hoán vị.
  - Tổ hợp nhỏ.
- Vận dụng vào các bài toán:
  - Chọn học sinh.
  - Lập số.
  - Đếm xâu nhị phân.
  - Đếm cách sắp xếp.

## 3. Về tư duy

- Biết phân rã bài toán đếm thành các bước độc lập.
- Hiểu rằng việc đếm thường dựa trên:
  - Chia trường hợp.
  - Nhân số lựa chọn từng bước.
- Xây nền cho các chuyên đề khó hơn:
  - Quy hoạch động.
  - Sinh cấu hình.
  - Tổ hợp nâng cao.

---

# II. Lý thuyết

## 1. Nguyên lý cộng

Nếu một công việc có thể được thực hiện theo một trong nhiều trường hợp không trùng nhau, ta cộng số cách của từng trường hợp.

### Ví dụ

Một học sinh có thể chọn:

- $3$ loại bút bi.
- $2$ loại bút chì.

Nếu chỉ chọn đúng một loại bút, số cách là:

$3 + 2 = 5$

---

## 2. Nguyên lý nhân

Nếu một công việc gồm nhiều bước liên tiếp, ta nhân số cách chọn ở từng bước.

### Ví dụ

Có:

- $3$ chiếc áo.
- $2$ chiếc quần.

Số bộ trang phục là:

$3 \times 2 = 6$

---

## 3. Giai thừa

Giai thừa của $n$, ký hiệu là $n!$, được tính bằng:

$n! = 1 \times 2 \times 3 \times ... \times n$

Quy ước:

$0! = 1$

### Ví dụ

$5! = 1 \times 2 \times 3 \times 4 \times 5 = 120$

---

## 4. Hoán vị

Hoán vị của $n$ phần tử là cách sắp xếp $n$ phần tử đó theo thứ tự.

Số hoán vị của $n$ phần tử là:

$P_n = n!$

### Ví dụ

Có $3$ chữ cái `A`, `B`, `C`.

Các cách sắp xếp là:

- `ABC`
- `ACB`
- `BAC`
- `BCA`
- `CAB`
- `CBA`

Có tổng cộng:

$3! = 6$

---

## 5. Chỉnh hợp không lặp

Chỉnh hợp chập $k$ của $n$ phần tử là cách chọn $k$ phần tử từ $n$ phần tử và có xét thứ tự.

Công thức:

$A_n^k = \frac{n!}{(n-k)!}$

### Ví dụ

Có $5$ học sinh.  
Chọn một lớp trưởng và một lớp phó.

Ta cần chọn:

- Người thứ nhất làm lớp trưởng.
- Người thứ hai làm lớp phó.

Có xét thứ tự vai trò.

Số cách là:

$A_5^2 = 5 \times 4 = 20$

---

## 6. Tổ hợp

Tổ hợp chập $k$ của $n$ phần tử là cách chọn $k$ phần tử từ $n$ phần tử mà không xét thứ tự.

Công thức:

$C_n^k = \frac{n!}{k!(n-k)!}$

### Ví dụ

Có $5$ học sinh.  
Chọn $2$ bạn tham gia câu lạc bộ.

Không xét ai được chọn trước.

Số cách là:

$C_5^2 = 10$

---

## 7. Phân biệt chỉnh hợp và tổ hợp

| Tình huống | Có xét thứ tự? | Công thức |
|---|---|---|
| Chọn lớp trưởng và lớp phó | Có | Chỉnh hợp |
| Chọn 2 bạn đi thi | Không | Tổ hợp |

---

## 8. Đếm xâu nhị phân

Một xâu nhị phân độ dài $N$ gồm các ký tự `0` và `1`.

Mỗi vị trí có $2$ lựa chọn.

Theo nguyên lý nhân, số xâu là:

$2^N$

### Ví dụ

Với $N = 3$, có:

$2^3 = 8$

xâu nhị phân.

---

## 9. Đếm xâu nhị phân có đúng K số 1

Ta cần chọn $K$ vị trí trong $N$ vị trí để đặt số `1`.

Số cách là:

$C_N^K$

---

## 10. Đếm số có các chữ số khác nhau

Ví dụ lập số có $3$ chữ số khác nhau từ các chữ số:

$1, 2, 3, 4$

- Chữ số hàng trăm: $4$ cách.
- Chữ số hàng chục: $3$ cách.
- Chữ số hàng đơn vị: $2$ cách.

Tổng số cách:

$4 \times 3 \times 2 = 24$

---

# III. Ví dụ minh họa

---

## Ví dụ 1. Tính giai thừa

### 1. Đề bài

Cho số nguyên không âm $N$.  
Tính $N!$.

---

### 2. Code Python

```python
n = int(input())

factorial = 1

for i in range(1, n + 1):
    factorial *= i

print(factorial)
```

---

### 3. Input

```text
5
```

### 4. Output

```text
120
```

---

## Ví dụ 2. Tính số hoán vị

### 1. Đề bài

Có $N$ học sinh phân biệt.  
Hỏi có bao nhiêu cách xếp các học sinh đó thành một hàng?

---

### 2. Phân tích

Số cách là:

$N!$

---

### 3. Code Python

```python
n = int(input())

result = 1

for i in range(1, n + 1):
    result *= i

print(result)
```

---

## Ví dụ 3. Tính tổ hợp C(n, k)

### 1. Đề bài

Cho hai số nguyên $N$, $K$.  
Tính:

$C_N^K$

---

### 2. Code Python

```python
n = int(input())
k = int(input())

factorial_n = 1
factorial_k = 1
factorial_n_minus_k = 1

for i in range(1, n + 1):
    factorial_n *= i

for i in range(1, k + 1):
    factorial_k *= i

for i in range(1, n - k + 1):
    factorial_n_minus_k *= i

result = factorial_n // (factorial_k * factorial_n_minus_k)

print(result)
```

---

### 3. Input

```text
5
2
```

### 4. Output

```text
10
```

---

## Ví dụ 4. Đếm xâu nhị phân độ dài N

### 1. Đề bài

Cho số nguyên dương $N$.  
Đếm số lượng xâu nhị phân có độ dài $N$.

---

### 2. Phân tích

Mỗi vị trí có $2$ lựa chọn:

- `0`
- `1`

Số xâu là:

$2^N$

---

### 3. Code Python

```python
n = int(input())

print(2 ** n)
```

---

## Ví dụ 5. Đếm xâu nhị phân có đúng K số 1

### 1. Đề bài

Cho hai số nguyên dương $N$, $K$.  
Đếm số xâu nhị phân độ dài $N$ có đúng $K$ ký tự `1`.

---

### 2. Phân tích

Chỉ cần chọn $K$ vị trí trong $N$ vị trí để đặt số `1`.

Số cách là:

$C_N^K$

---

### 3. Code Python

```python
n = int(input())
k = int(input())

def factorial(x):
    result = 1

    for i in range(1, x + 1):
        result *= i

    return result

result = factorial(n) // (factorial(k) * factorial(n - k))

print(result)
```

---

# IV. Bài tập vận dụng

---

## Bài 1. Giai thừa

### Đề bài

Cho số nguyên không âm $N$.  
Tính $N!$.

---

## Bài 2. Hoán vị của N phần tử

### Đề bài

Cho số nguyên dương $N$.  
Tính số cách sắp xếp $N$ phần tử phân biệt thành một hàng.

---

## Bài 3. Chỉnh hợp

### Đề bài

Cho hai số nguyên dương $N$, $K$ với $K \le N$.  
Tính:

$A_N^K$

---

## Bài 4. Tổ hợp

### Đề bài

Cho hai số nguyên dương $N$, $K$ với $K \le N$.  
Tính:

$C_N^K$

---

## Bài 5. Chọn đội thi

### Đề bài

Một lớp có $N$ học sinh.  
Hãy tính số cách chọn $K$ học sinh tham gia đội thi.

---

## Bài 6. Chọn ban cán sự

### Đề bài

Một lớp có $N$ học sinh.  
Hãy tính số cách chọn:

- Một lớp trưởng.
- Một lớp phó.

---

## Bài 7. Xâu nhị phân

### Đề bài

Cho số nguyên dương $N$.  
Đếm số xâu nhị phân độ dài $N$.

---

## Bài 8. Xâu nhị phân có K số 1

### Đề bài

Cho $N$, $K$.  
Đếm số xâu nhị phân độ dài $N$ có đúng $K$ số `1`.

---

# V. Bài tập về nhà

---

## Bài 1. Lập số có 3 chữ số khác nhau

### Đề bài

Từ các chữ số $1, 2, 3, 4, 5$, lập được bao nhiêu số có $3$ chữ số đôi một khác nhau?

---

## Bài 2. Lập số chẵn

### Đề bài

Từ các chữ số $0, 1, 2, 3, 4, 5$, lập được bao nhiêu số chẵn có $3$ chữ số khác nhau?

---

## Bài 3. Chọn nhóm học sinh

### Đề bài

Một lớp có $N$ học sinh.  
Có bao nhiêu cách chọn một nhóm $K$ học sinh?

---

## Bài 4. Chọn trưởng nhóm và thành viên

### Đề bài

Một lớp có $N$ học sinh.  
Hỏi có bao nhiêu cách chọn:

- Một trưởng nhóm.
- $K-1$ thành viên còn lại.

---

## Bài 5. Đếm xâu ký tự

### Đề bài

Có một bảng chữ cái gồm $M$ ký tự.  
Hỏi có bao nhiêu xâu độ dài $N$?

---

## Bài 6. Đếm dãy nhị phân không có hai số 1 liền nhau

### Đề bài

Cho số nguyên dương $N$.  
Đếm số dãy nhị phân độ dài $N$ mà không có hai số `1` đứng cạnh nhau.

---

# VI. Lỗi học sinh thường gặp

---

## 1. Không phân biệt có xét thứ tự hay không

Ví dụ:

- Chọn lớp trưởng, lớp phó: có xét thứ tự.
- Chọn hai bạn đi thi: không xét thứ tự.

---

## 2. Nhầm hoán vị với tổ hợp

Hoán vị dùng khi sắp xếp toàn bộ phần tử.

Tổ hợp dùng khi chọn một nhóm mà không xét thứ tự.

---

## 3. Quên điều kiện k ≤ n

Các công thức tổ hợp, chỉnh hợp thường yêu cầu:

$0 \le K \le N$

---

## 4. Không nhớ 0! = 1

Quy ước:

$0! = 1$

rất quan trọng khi tính:

$C_N^0$ hoặc $C_N^N$

---

## 5. Lạm dụng công thức mà không hiểu bài toán

Trước khi chọn công thức, cần trả lời:

- Có xét thứ tự không?
- Có lặp không?
- Chọn bao nhiêu phần tử?

---

# VII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Đếm dãy nhị phân

### Bài toán

Cho số nguyên dương $N$.  
Đếm số lượng dãy nhị phân độ dài $N$ mà không có hai chữ số `1` nào đứng cạnh nhau.

---

## Đề 2. Hoán vị xâu

### Bài toán

Cho một xâu ký tự.  
Đếm số hoán vị khác nhau của xâu đó.

---

## Đề 3. Đặt quân xe

### Bài toán

Đếm số cách đặt $N$ quân xe lên bàn cờ $N \times N$ sao cho không có quân nào ăn được nhau.

---

## Đề 4. Chọn đội tuyển

### Bài toán

Một trường có $N$ học sinh xuất sắc.  
Hãy tính số cách chọn $K$ học sinh tham gia đội tuyển.

---

# VIII. Ghi nhớ cuối bài

- Nguyên lý cộng dùng khi chia thành các trường hợp rời nhau.
- Nguyên lý nhân dùng khi một công việc gồm nhiều bước liên tiếp.
- Giai thừa:

$n! = 1 \times 2 \times ... \times n$

- Hoán vị:

$P_n = n!$

- Chỉnh hợp:

$A_n^k = \frac{n!}{(n-k)!}$

- Tổ hợp:

$C_n^k = \frac{n!}{k!(n-k)!}$

---

# IX. Tóm tắt bài học

## Bài 29. Tổ hợp đếm cơ bản

- Cần xác định rõ:
  - Có xét thứ tự hay không?
  - Có lặp hay không?
- Công thức quan trọng:
  - Giai thừa.
  - Hoán vị.
  - Chỉnh hợp.
  - Tổ hợp.
- Ứng dụng:
  - Chọn nhóm.
  - Chọn chức vụ.
  - Đếm xâu nhị phân.
  - Bài toán đặt quân cờ.
