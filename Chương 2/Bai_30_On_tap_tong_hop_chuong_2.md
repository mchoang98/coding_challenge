# Bài 30. Ôn tập tổng hợp Chương 2

---

# I. Mục tiêu bài học

Sau bài học này, học sinh cần đạt được các yêu cầu sau:

## 1. Về kiến thức

- Hệ thống lại toàn bộ kiến thức trong Chương 2:
  - Thuật toán và tư duy phân tích bài toán.
  - Độ phức tạp.
  - Tối ưu từ Brute Force.
  - UCLN, BCNN.
  - Số nguyên tố.
  - Phân tích thừa số nguyên tố.
  - Sàng Eratosthenes.
  - Đếm ước, tổng ước.
  - Hệ đếm.
  - Fibonacci.
  - Tổ hợp đếm cơ bản.

## 2. Về kỹ năng

- Nhận dạng nhanh từng nhóm bài toán.
- Chọn được thuật toán phù hợp.
- Viết code chính xác cho các dạng chuẩn.
- Phân tích được độ phức tạp của lời giải.
- Biết tổng hợp nhiều kiến thức trong cùng một đề.

## 3. Về tư duy

- Biết nhìn đề và đặt câu hỏi:
  - Đây là dạng số học nào?
  - Có thể dùng công thức không?
  - Có cần tiền xử lý không?
  - Có thể tối ưu hơn cách duyệt trực tiếp không?
- Chuẩn bị cho giai đoạn học thuật toán nâng cao hơn.

---

# II. Bản đồ kiến thức Chương 2

## 1. Thuật toán và độ phức tạp

### Kiến thức trọng tâm

- Input.
- Output.
- Thuật toán.
- Độ phức tạp:
  - $O(1)$
  - $O(\log N)$
  - $O(N)$
  - $O(N \log N)$
  - $O(N^2)$

### Dấu hiệu nhận biết

- Đề có giới hạn dữ liệu lớn.
- Cần chọn cách làm chạy kịp thời gian.

---

## 2. Tối ưu từ Brute Force

### Kiến thức trọng tâm

- Viết cách đúng trước.
- Giảm số vòng lặp.
- Tính trực tiếp biến còn lại.
- Dùng công thức thay cho duyệt.

### Dấu hiệu nhận biết

- Bài toán có nhiều biến.
- Có phương trình ràng buộc.
- Có thể tính một biến từ các biến khác.

---

## 3. UCLN và BCNN

### Kiến thức trọng tâm

- Thuật toán Euclid.
- Công thức:

$BCNN(a, b) = \frac{a \times b}{UCLN(a, b)}$

### Dấu hiệu nhận biết

- Bài toán về chia hết.
- Tìm chu kỳ trùng nhau.
- Đếm số chia hết cho cả hai số.

---

## 4. Số nguyên tố

### Kiến thức trọng tâm

- Kiểm tra nguyên tố $O(\sqrt{N})$.
- Xử lý riêng:
  - $N < 2$.
  - Số chẵn.

### Dấu hiệu nhận biết

- Đề yêu cầu:
  - Kiểm tra nguyên tố.
  - Đếm nguyên tố.
  - Tìm nguyên tố trong dãy.

---

## 5. Phân tích thừa số nguyên tố

### Kiến thức trọng tâm

- Chia liên tiếp.
- Dừng khi $i \times i > N$.
- Xử lý phần còn lại nếu $N > 1$.

### Dấu hiệu nhận biết

- Đề hỏi:
  - Thừa số nguyên tố.
  - Ước nguyên tố lớn nhất.
  - Số mũ trong phân tích.

---

## 6. Sàng Eratosthenes

### Kiến thức trọng tâm

- Đánh dấu nguyên tố đến $N$.
- Bắt đầu gạch từ $i \times i$.
- Dùng prefix sum cho truy vấn đoạn.

### Dấu hiệu nhận biết

- Nhiều truy vấn nguyên tố.
- Liệt kê hoặc đếm nguyên tố trong phạm vi lớn.

---

## 7. Đếm ước và tổng ước

### Kiến thức trọng tâm

Nếu:

$N = p_1^{a_1} \times ... \times p_k^{a_k}$

thì:

- Số ước:

$(a_1 + 1)...(a_k + 1)$

- Tổng ước:

$(1 + p_1 + ... + p_1^{a_1})...$

### Dấu hiệu nhận biết

- Bài hỏi số lượng ước.
- Bài hỏi tổng ước.
- Bài hỏi số hoàn hảo.

---

## 8. Hệ đếm

### Kiến thức trọng tâm

- Đổi cơ số.
- Từ hệ $b$ sang hệ $10$:

$value = value \times b + digit$

- Từ hệ $10$ sang hệ $b$:
  - Chia lấy dư.
  - Ghép ngược kết quả.

### Dấu hiệu nhận biết

- Đề có:
  - Nhị phân.
  - Hexa.
  - Chuyển đổi cơ số.

---

## 9. Fibonacci

### Kiến thức trọng tâm

- Công thức:

$F_n = F_{n-1} + F_{n-2}$

- Cách tính bằng:
  - Mảng.
  - Hai biến.

### Dấu hiệu nhận biết

- Dãy truy hồi.
- Số cách leo bậc.
- Đếm chuỗi tương tự Fibonacci.

---

## 10. Tổ hợp đếm

### Kiến thức trọng tâm

- Nguyên lý cộng.
- Nguyên lý nhân.
- Giai thừa.
- Hoán vị.
- Chỉnh hợp.
- Tổ hợp.

### Dấu hiệu nhận biết

- Bài toán hỏi “có bao nhiêu cách”.
- Cần chọn hoặc sắp xếp phần tử.

---

# III. Bảng chọn công cụ giải bài

| Dạng bài | Công cụ nên nghĩ đến |
|---|---|
| Kiểm tra số nguyên tố | $O(\sqrt{N})$ |
| Nhiều truy vấn nguyên tố | Sàng Eratosthenes |
| Số lượng ước | Phân tích thừa số |
| Tổng các ước | Phân tích thừa số |
| Tìm UCLN | Euclid |
| Tìm BCNN | Công thức từ UCLN |
| Chuyển nhị phân sang thập phân | Quét xâu từ trái sang phải |
| Chuyển thập phân sang nhị phân | Chia lấy dư |
| Tính Fibonacci | Hai biến |
| Chọn K phần tử | Tổ hợp |
| Sắp xếp N phần tử | Hoán vị |
| Đếm nhiều trường hợp | Nguyên lý cộng, nhân |

---

# IV. Ví dụ tổng hợp

---

## Ví dụ 1. Phân tích số học đầy đủ

### 1. Đề bài

Cho số nguyên dương $N$.  
Hãy:

1. Kiểm tra $N$ có phải số nguyên tố hay không.
2. Phân tích $N$ thành thừa số nguyên tố.
3. Tính số lượng ước của $N$.
4. Tính tổng các ước của $N$.

---

### 2. Gợi ý hướng giải

- Phần 1:
  - Dùng `is_prime(n)`.
- Phần 2:
  - Dùng chia liên tiếp.
- Phần 3 và 4:
  - Tận dụng các số mũ trong phân tích.

---

### 3. Code Python

```python
def is_prime(x):
    if x < 2:
        return False

    i = 2

    while i * i <= x:
        if x % i == 0:
            return False
        i += 1

    return True


n = int(input())
original_n = n

if is_prime(n):
    print("PRIME")
else:
    print("NOT PRIME")

i = 2
num_divisors = 1
sum_divisors = 1
factor_parts = []

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
        if count == 1:
            factor_parts.append(str(i))
        else:
            factor_parts.append(f"{i}^{count}")

        num_divisors *= count + 1
        sum_divisors *= power_sum

    i += 1

if n > 1:
    factor_parts.append(str(n))
    num_divisors *= 2
    sum_divisors *= 1 + n

print(" * ".join(factor_parts))
print(num_divisors)
print(sum_divisors)
```

---

## Ví dụ 2. Đếm nguyên tố trong đoạn nhiều truy vấn

### 1. Đề bài

Cho $N$ và $Q$ truy vấn.  
Mỗi truy vấn gồm $L$, $R$.

Hãy đếm số nguyên tố trong từng đoạn $[L, R]$.

---

### 2. Hướng giải

- Dùng sàng đến $N$.
- Tạo mảng tiền tố.
- Mỗi truy vấn trả lời trong $O(1)$.

---

### 3. Độ phức tạp

- Tiền xử lý: $O(N \log \log N)$
- Mỗi truy vấn: $O(1)$

---

## Ví dụ 3. Đổi cơ số và đếm bit 1

### 1. Đề bài

Cho số nguyên dương $N$.

Hãy:

1. Đổi $N$ sang nhị phân.
2. Đếm số chữ số `1` trong biểu diễn đó.

---

### 2. Code Python

```python
n = int(input())

if n == 0:
    binary = "0"
else:
    binary = ""

    while n > 0:
        binary = str(n % 2) + binary
        n //= 2

count_one = 0

for ch in binary:
    if ch == "1":
        count_one += 1

print(binary)
print(count_one)
```

---

# V. Bộ bài tập ôn tập

---

## Bài 1. Kiểm tra nguyên tố

Cho số nguyên dương $N$.  
Kiểm tra $N$ có phải số nguyên tố hay không.

---

## Bài 2. UCLN và BCNN

Cho hai số nguyên dương $A$, $B$.  
Tính:

1. $UCLN(A, B)$
2. $BCNN(A, B)$

---

## Bài 3. Phân tích thừa số nguyên tố

Cho $N > 1$.  
Phân tích $N$ thành các thừa số nguyên tố.

---

## Bài 4. Số lượng ước

Cho $N$.  
Tính số lượng ước nguyên dương của $N$.

---

## Bài 5. Tổng các ước

Cho $N$.  
Tính tổng tất cả các ước nguyên dương của $N$.

---

## Bài 6. Đếm số nguyên tố trong đoạn

Cho hai số $A$, $B$.  
Đếm số nguyên tố thuộc đoạn $[A, B]$.

---

## Bài 7. Chuyển đổi nhị phân

Cho số nguyên dương $N$.  
In ra biểu diễn nhị phân của $N$.

---

## Bài 8. Fibonacci thứ N

Cho $N$.  
Tính số Fibonacci thứ $N$.

---

## Bài 9. Chọn đội tuyển

Một lớp có $N$ học sinh.  
Có bao nhiêu cách chọn $K$ học sinh?

---

## Bài 10. Dãy nhị phân

Đếm số xâu nhị phân độ dài $N$ có đúng $K$ số `1`.

---

# VI. Đề luyện tổng hợp chương 2

---

## Câu 1. Số học cơ bản

Cho số nguyên dương $N$.  
Hãy:

1. Kiểm tra $N$ có phải số nguyên tố hay không.
2. Tìm ước nguyên tố lớn nhất của $N$.

---

## Câu 2. Chia hết và UCLN

Cho hai số nguyên dương $A$, $B$.  
Hãy tính:

1. $UCLN(A, B)$
2. $BCNN(A, B)$
3. Số lượng số từ $1$ đến $N$ chia hết cho cả $A$ và $B$.

---

## Câu 3. Hệ đếm

Cho xâu nhị phân $S$.  
Hãy đổi $S$ sang hệ $16$.

---

## Câu 4. Fibonacci

Cho hai số $A$, $B$.  
Đếm có bao nhiêu số Fibonacci thuộc đoạn $[A, B]$.

---

## Câu 5. Tổ hợp đếm

Cho $N$, $K$.  
Đếm số xâu nhị phân độ dài $N$ có đúng $K$ số `1`.

---

# VII. Checklist tự đánh giá

Học sinh tự kiểm tra:

## 1. Tôi đã làm được chưa?

- [ ] Tôi hiểu thuật toán là gì.
- [ ] Tôi phân tích được độ phức tạp cơ bản.
- [ ] Tôi biết tối ưu Brute Force đơn giản.
- [ ] Tôi viết được UCLN bằng Euclid.
- [ ] Tôi kiểm tra được số nguyên tố.
- [ ] Tôi phân tích được thừa số nguyên tố.
- [ ] Tôi dùng được sàng Eratosthenes.
- [ ] Tôi tính được số ước và tổng ước.
- [ ] Tôi đổi được hệ cơ số.
- [ ] Tôi tính được Fibonacci.
- [ ] Tôi phân biệt chỉnh hợp và tổ hợp.

---

# VIII. Lỗi học sinh thường gặp trong toàn chương

---

## 1. Không quan tâm giới hạn dữ liệu

Dẫn đến chọn thuật toán quá chậm.

---

## 2. Không xử lý trường hợp đặc biệt

Ví dụ:

- $N = 0$
- $N = 1$
- $N = 2$

---

## 3. Nhầm giữa các công thức số học

Ví dụ:

- Nhầm số ước với tổng ước.
- Nhầm UCLN với BCNN.
- Nhầm chỉnh hợp với tổ hợp.

---

## 4. Dùng đúng công cụ nhưng cài đặt sai

Ví dụ:

- Sàng quên gán `prime[1] = False`.
- Fibonacci cập nhật biến sai thứ tự.
- Đổi cơ số ghép số dư sai chiều.

---

## 5. Không kiểm tra lại bằng ví dụ nhỏ

Đây là lỗi làm mất nhiều điểm trong bài thi.

---

# IX. Ghi nhớ cuối chương

- Mỗi dạng bài nên có một công cụ đặc trưng.
- Cần nhận diện đúng bài trước khi viết code.
- Không chỉ cần chương trình đúng, mà còn cần chương trình đủ nhanh.
- Chương 2 là nền tảng số học và tư duy thuật toán quan trọng cho:
  - Mảng.
  - Prefix sum.
  - Two pointers.
  - Quy hoạch động.
  - Đồ thị.

---

# X. Tóm tắt chương 2

## Chương 2. Tư duy thuật toán và số học

Chương này giúp học sinh:

- Biết đọc đề và phân tích bài.
- Biết đánh giá độ phức tạp.
- Biết tối ưu từ cách làm đơn giản.
- Nắm các kỹ thuật số học nền tảng:
  - UCLN, BCNN.
  - Số nguyên tố.
  - Phân tích thừa số nguyên tố.
  - Sàng Eratosthenes.
  - Số lượng ước, tổng ước.
- Hiểu thêm về:
  - Hệ đếm.
  - Fibonacci.
  - Tổ hợp đếm.

Đây là bước chuyển quan trọng từ **lập trình cơ bản** sang **tư duy giải thuật**.
