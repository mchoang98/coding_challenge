# BÀI 20. ĐỘ PHỨC TẠP THUẬT TOÁN

## Làm sao biết một chương trình chạy nhanh hay chậm?

---

# I. Mục tiêu bài học

Sau bài này, học sinh cần đạt được:

## 1. Về kiến thức

* Hiểu **độ phức tạp thuật toán** là gì.
* Biết vì sao cùng một bài toán có cách chạy nhanh, có cách chạy chậm.
* Nắm được các mức độ phức tạp cơ bản:

  * `O(1)`
  * `O(log N)`
  * `O(N)`
  * `O(N log N)`
  * `O(N²)`
  * `O(N³)`
* Biết cách **ước lượng số phép tính** dựa vào giới hạn dữ liệu.

## 2. Về kỹ năng

* Nhìn đoạn code và đoán được độ phức tạp.
* Phân tích vòng lặp đơn, vòng lặp lồng nhau.
* Phân biệt:

  * Vòng lặp chạy `N` lần
  * Vòng lặp chạy `log N` lần
  * Hai vòng lặp lồng nhau chạy `N²` lần
* Biết dùng độ phức tạp để đánh giá:

  > “Cách làm này có chạy được với dữ liệu đề bài không?”

## 3. Về tư duy

* Không chỉ hỏi: **“Code này đúng không?”**
* Mà phải hỏi thêm:

  > **“Code này có đủ nhanh không?”**

Tài liệu chuyên Tin xem phân tích độ phức tạp là bước nền tảng để chọn được thuật toán hiệu quả, thay vì chỉ dừng lại ở lời giải đúng về mặt ý tưởng. 

---

# II. Đặt vấn đề: Vì sao cần học độ phức tạp?

---

## 1. Một bài toán, hai cách làm

### Bài toán

Cho số nguyên dương `N`.
Hãy tính:

[
S = 1 + 2 + 3 + \dots + N
]

---

## Cách 1. Cộng từng số

```python
n = int(input())

s = 0
for i in range(1, n + 1):
    s += i

print(s)
```

Nếu `N = 5`, chương trình thực hiện:

* `s += 1`
* `s += 2`
* `s += 3`
* `s += 4`
* `s += 5`

Tức là **5 lần cộng**.

Nếu `N = 1 000 000`, chương trình thực hiện **1 000 000 lần cộng**.

---

## Cách 2. Dùng công thức

[
S = \frac{N(N+1)}{2}
]

```python
n = int(input())

s = n * (n + 1) // 2

print(s)
```

Dù `N = 5` hay `N = 1 000 000 000`, chương trình vẫn chỉ làm vài phép tính.

---

## So sánh

| Cách           |     Số bước chính |
| -------------- | ----------------: |
| Dùng vòng lặp  |     Tăng theo `N` |
| Dùng công thức | Gần như không đổi |

### Kết luận

Hai chương trình đều đúng, nhưng:

* Một chương trình **chậm dần khi N lớn**
* Một chương trình **gần như nhanh như nhau với mọi N**

Đó là lý do ta cần học **độ phức tạp thuật toán**.

---

# III. Độ phức tạp thuật toán là gì?

---

## 1. Khái niệm đơn giản

**Độ phức tạp thuật toán** cho biết:

> Khi kích thước dữ liệu tăng lên, số bước xử lý của thuật toán tăng nhanh cỡ nào.

Ta thường dùng ký hiệu:

[
O(...)
]

đọc là **Big O**.

---

## 2. Ví dụ trực quan

Giả sử `N` là số phần tử cần xử lý.

| Độ phức tạp | Ý nghĩa trực quan                                 |
| ----------- | ------------------------------------------------- |
| `O(1)`      | Dữ liệu lớn hơn nhưng số bước gần như không đổi   |
| `O(log N)`  | Dữ liệu tăng rất mạnh nhưng số bước tăng rất chậm |
| `O(N)`      | Dữ liệu gấp đôi thì số bước xấp xỉ gấp đôi        |
| `O(N²)`     | Dữ liệu gấp đôi thì số bước xấp xỉ gấp 4          |
| `O(N³)`     | Dữ liệu gấp đôi thì số bước xấp xỉ gấp 8          |

Tài liệu chuyên Tin trình bày độ phức tạp như một cách đánh giá thời gian chạy của thuật toán theo kích thước dữ liệu đầu vào. 

---

# IV. Các độ phức tạp cơ bản

---

# 1. Độ phức tạp `O(1)` – Hằng số

## 1.1. Ý nghĩa

Số phép tính **không phụ thuộc vào N**.

---

## 1.2. Ví dụ

### Tính diện tích hình chữ nhật

```python
a = int(input())
b = int(input())

s = a * b

print(s)
```

Dù `a`, `b` lớn hay nhỏ, số phép tính chính vẫn như nhau.

### Độ phức tạp

[
O(1)
]

---

## 1.3. Ví dụ khác

```python
n = int(input())
print(n * n)
```

Chỉ có một phép nhân.

[
O(1)
]

---

# 2. Độ phức tạp `O(N)` – Tuyến tính

---

## 2.1. Ý nghĩa

Số bước xử lý tăng **tỉ lệ thuận** với `N`.

---

## 2.2. Ví dụ: Tính tổng từ 1 đến N bằng vòng lặp

```python
n = int(input())

s = 0
for i in range(1, n + 1):
    s += i

print(s)
```

Vòng lặp chạy đúng `N` lần.

### Độ phức tạp

[
O(N)
]

---

## 2.3. Ví dụ: Tìm số lớn nhất trong dãy

```python
n = int(input())
a = list(map(int, input().split()))

rmax = a[0]

for i in range(1, n):
    if a[i] > rmax:
        rmax = a[i]

print(rmax)
```

Ta duyệt qua từng phần tử đúng một lần.

### Độ phức tạp

[
O(N)
]

---

# 3. Độ phức tạp `O(N²)` – Bậc hai

---

## 3.1. Ý nghĩa

Thường xuất hiện khi có **hai vòng lặp lồng nhau**.

---

## 3.2. Ví dụ đơn giản

```python
for i in range(n):
    for j in range(n):
        print(i, j)
```

* Vòng ngoài chạy `N` lần.
* Mỗi lần vòng ngoài chạy, vòng trong chạy `N` lần.

Tổng số lần:

[
N \times N = N^2
]

### Độ phức tạp

[
O(N^2)
]

---

## 3.3. Ví dụ: Đếm mọi cặp phần tử trong dãy

```python
n = int(input())
a = list(map(int, input().split()))

count = 0

for i in range(n):
    for j in range(i + 1, n):
        count += 1

print(count)
```

Số cặp là:

[
\frac{N(N-1)}{2}
]

Khi xét Big O, ta chỉ giữ bậc lớn nhất:

[
O(N^2)
]

---

# 4. Độ phức tạp `O(N³)` – Bậc ba

---

## 4.1. Ý nghĩa

Thường có **ba vòng lặp lồng nhau**.

---

## 4.2. Ví dụ

```python
for i in range(n):
    for j in range(n):
        for k in range(n):
            print(i, j, k)
```

Tổng số lần lặp:

[
N \times N \times N = N^3
]

### Độ phức tạp

[
O(N^3)
]

---

## 4.3. Khi nào `O(N³)` còn dùng được?

* `N = 50`: có thể dùng.
* `N = 500`: thường quá chậm.
* `N = 10^5`: chắc chắn không chạy được.

---

# 5. Độ phức tạp `O(log N)` – Logarit

---

## 5.1. Ý nghĩa

Mỗi bước xử lý làm kích thước bài toán **giảm đi một nửa**.

---

## 5.2. Ví dụ

```python
n = int(input())

count = 0
while n > 0:
    n //= 2
    count += 1

print(count)
```

### Phân tích

Ví dụ `N = 16`:

|    Bước |  N |
| ------: | -: |
| Ban đầu | 16 |
|       1 |  8 |
|       2 |  4 |
|       3 |  2 |
|       4 |  1 |
|       5 |  0 |

Chỉ cần khoảng `log₂N` bước.

### Độ phức tạp

[
O(\log N)
]

---

## 5.3. Ví dụ đời sống

Tìm một từ trong từ điển:

* Không đọc từ trang đầu đến trang cuối.
* Mở giữa quyển sách.
* Nếu từ cần tìm đứng sau, bỏ nửa đầu.
* Nếu đứng trước, bỏ nửa sau.

Đó chính là tư duy `log N`.

---

# 6. Độ phức tạp `O(N log N)`

---

## 6.1. Ý nghĩa

Đây là mức rất phổ biến trong các thuật toán tốt:

* Sắp xếp nhanh
* Merge sort
* Một số bài duyệt + tìm kiếm

---

## 6.2. Ví dụ gần gũi

Python:

```python
a.sort()
```

Việc sắp xếp thông thường thường được đánh giá khoảng:

[
O(N \log N)
]

---

## 6.3. So với `O(N²)`

Nếu `N = 100000`:

* `N² = 10^{10}` bước → rất chậm.
* `N log N` chỉ khoảng vài triệu bước → chạy được.

---

# V. Cách đánh giá độ phức tạp của đoạn code

---

# 1. Quy tắc 1: Lệnh đơn là `O(1)`

Ví dụ:

```python
a = 5
b = 7
c = a + b
print(c)
```

Mỗi dòng là thao tác đơn giản.

### Độ phức tạp

[
O(1)
]

---

# 2. Quy tắc 2: Các đoạn nối tiếp lấy cái lớn nhất

---

## Ví dụ

```python
for i in range(n):
    print(i)

for j in range(n):
    print(j)
```

* Vòng 1: `O(N)`
* Vòng 2: `O(N)`

Tổng:
[
O(N) + O(N) = O(2N)
]

Bỏ hằng số:
[
O(N)
]

---

# 3. Quy tắc 3: Vòng lặp lồng nhau thì nhân vào

---

## Ví dụ

```python
for i in range(n):
    for j in range(n):
        print(i, j)
```

[
O(N) \times O(N) = O(N^2)
]

---

# 4. Quy tắc 4: Vòng lặp chia đôi thường là `O(log N)`

---

## Ví dụ

```python
while n > 1:
    n //= 2
```

### Độ phức tạp

[
O(\log N)
]

---

# VI. Phân tích chi tiết các ví dụ thường gặp

---

# Ví dụ 1. Một vòng lặp đơn

```python
for i in range(1, n + 1):
    print(i)
```

### Phân tích

* `i` chạy từ `1` đến `n`
* Có `n` lần lặp

### Độ phức tạp

[
O(N)
]

---

# Ví dụ 2. Vòng lặp chạy 2N lần

```python
for i in range(1, 2 * n + 1):
    print(i)
```

### Phân tích

Có `2N` lần lặp.

Trong Big O:
[
O(2N) = O(N)
]

### Kết luận

Không viết `O(2N)`, mà viết:
[
O(N)
]

---

# Ví dụ 3. Hai vòng lặp nối tiếp

```python
for i in range(n):
    print(i)

for j in range(n):
    print(j)
```

### Phân tích

* Vòng đầu: `N`
* Vòng sau: `N`

Tổng:
[
N + N = 2N
]

### Độ phức tạp

[
O(N)
]

---

# Ví dụ 4. Hai vòng lặp lồng nhau

```python
for i in range(n):
    for j in range(n):
        print(i, j)
```

### Phân tích

* Mỗi `i` có `N` giá trị `j`
* Có `N × N` lượt

### Độ phức tạp

[
O(N^2)
]

---

# Ví dụ 5. Vòng trong phụ thuộc vòng ngoài

```python
for i in range(1, n + 1):
    for j in range(1, i + 1):
        print(i, j)
```

### Phân tích

Số lần chạy của vòng trong:

* Khi `i = 1`: chạy 1 lần
* Khi `i = 2`: chạy 2 lần
* ...
* Khi `i = n`: chạy n lần

Tổng số lần:

[
1 + 2 + 3 + \dots + N = \frac{N(N+1)}{2}
]

Bậc lớn nhất là `N²`.

### Độ phức tạp

[
O(N^2)
]

Đây cũng là ví dụ được phân tích trực tiếp trong tài liệu chuyên Tin. 

---

# Ví dụ 6. Vòng lặp giảm một nửa

```python
while n > 0:
    n //= 2
```

### Phân tích

Nếu:

* `N = 8`: `8 → 4 → 2 → 1 → 0`
* `N = 16`: `16 → 8 → 4 → 2 → 1 → 0`

Mỗi bước giảm một nửa.

### Độ phức tạp

[
O(\log N)
]

Tài liệu chuyên Tin cũng đưa ra đúng mẫu bài này để học sinh nhận diện độ phức tạp logarit. 

---

# VII. Bảng ước lượng thuật toán theo giới hạn dữ liệu

Khi đọc đề, nhìn vào `N` có thể đoán được nên dùng thuật toán cỡ nào.

| Giới hạn N | Độ phức tạp thường chấp nhận          |
| ---------: | ------------------------------------- |
|   `N ≤ 20` | Có thể dùng `O(2^N)` trong một số bài |
|  `N ≤ 100` | `O(N³)` thường ổn                     |
| `N ≤ 1000` | `O(N²)` có thể ổn                     |
| `N ≤ 10^5` | Nên là `O(N log N)` hoặc `O(N)`       |
| `N ≤ 10^6` | Thường cần `O(N)`                     |
| `N ≥ 10^9` | Thường cần `O(log N)` hoặc `O(√N)`    |

---

# VIII. Ví dụ rất quan trọng: Đếm số chính phương ≤ N

---

## 1. Đề bài

Cho số nguyên dương `N`.
Hãy đếm có bao nhiêu số chính phương nhỏ hơn hoặc bằng `N`.

---

## 2. Cách 1 – Duyệt từng số

```python
from math import sqrt

n = int(input())
count = 0

for i in range(1, n + 1):
    if sqrt(i) == int(sqrt(i)):
        count += 1

print(count)
```

### Phân tích

* Duyệt từ `1` đến `N`
* Mỗi số kiểm tra một lần

### Độ phức tạp

[
O(N)
]

---

## 3. Cách 2 – Dùng nhận xét toán học

Các số chính phương không vượt quá `N` là:

[
1^2, 2^2, 3^2, \dots, \lfloor \sqrt{N} \rfloor^2
]

Vậy số lượng chính là:

[
\lfloor \sqrt{N} \rfloor
]

### Code

```python
from math import isqrt

n = int(input())
print(isqrt(n))
```

### Độ phức tạp

[
O(1)
]

---

## 4. So sánh

| Cách             | Độ phức tạp |
| ---------------- | ----------- |
| Duyệt từ 1 đến N | `O(N)`      |
| Dùng căn bậc hai | `O(1)`      |

Đây là một ví dụ rất hay trong tài liệu nhập môn: cùng một bài toán, cách dùng nhận xét toán học giảm từ `O(N)` xuống `O(1)`. 

---

# IX. Ví dụ nâng cao: Kiểm tra số nguyên tố

---

## 1. Đề bài

Kiểm tra xem số nguyên dương `N` có phải số nguyên tố không.

---

## 2. Cách 1 – Thử chia đến N - 1

```python
def is_prime(n):
    if n < 2:
        return False

    for k in range(2, n):
        if n % k == 0:
            return False

    return True
```

### Độ phức tạp

[
O(N)
]

---

## 3. Cách 2 – Chỉ thử đến căn bậc hai của N

```python
from math import isqrt

def is_prime(n):
    if n < 2:
        return False

    for k in range(2, isqrt(n) + 1):
        if n % k == 0:
            return False

    return True
```

### Độ phức tạp

[
O(\sqrt{N})
]

---

## 4. Vì sao chỉ cần đến √N?

Nếu `N = a × b` là hợp số, thì không thể cả `a` và `b` đều lớn hơn `√N`.

Ví dụ:
[
36 = 4 \times 9
]

Trong một cặp ước, luôn có ít nhất một ước không vượt quá `√N`.

---

## 5. Ý nghĩa

Tài liệu chuyên Tin dùng chính ví dụ kiểm tra nguyên tố để chứng minh rằng thuật toán tốt hơn có thể biến một bài tưởng như không chạy nổi thành chạy được rất nhanh. 

---

# X. Mẹo nhận diện nhanh độ phức tạp

---

## 1. Một vòng `for` chạy hết N phần tử

[
O(N)
]

```python
for i in range(n):
    ...
```

---

## 2. Hai vòng `for` lồng nhau cùng chạy theo N

[
O(N^2)
]

```python
for i in range(n):
    for j in range(n):
        ...
```

---

## 3. Ba vòng lặp lồng nhau

[
O(N^3)
]

---

## 4. Mỗi lần chia đôi

[
O(\log N)
]

```python
while n > 0:
    n //= 2
```

---

## 5. Hai đoạn code nối tiếp

Lấy độ phức tạp lớn hơn.

Ví dụ:

```python
for i in range(n):
    ...

for i in range(n):
    for j in range(n):
        ...
```

* Đoạn 1: `O(N)`
* Đoạn 2: `O(N²)`

Tổng:
[
O(N^2)
]

---

# XI. Câu hỏi gợi mở trên lớp

---

## Câu 1

Đoạn code sau chạy bao nhiêu lần?

```python
for i in range(10):
    print(i)
```

**Đáp án:** 10 lần, tức `O(1)` vì 10 là hằng số.

---

## Câu 2

Đoạn code sau là `O(N)` hay `O(N²)`?

```python
for i in range(n):
    print(i)

for j in range(n):
    print(j)
```

**Đáp án:** `O(N)`, vì hai vòng nối tiếp, không lồng nhau.

---

## Câu 3

Đoạn code sau là độ phức tạp gì?

```python
for i in range(n):
    for j in range(n):
        print(i, j)
```

**Đáp án:** `O(N²)`.

---

## Câu 4

Vì sao đoạn code này là `O(log N)`?

```python
while n > 1:
    n //= 2
```

**Gợi ý:** Mỗi lần `n` giảm đi một nửa.

---

## Câu 5

Nếu `N = 10^5`, ta có nên dùng `O(N²)` không?

**Đáp án:** Thường là không, vì có khoảng `10^10` phép xử lý.

---

# XII. Bài tập vận dụng trên lớp

---

# Bài 1. Xác định độ phức tạp

```python
s = 0
for i in range(n):
    s += i
```

**Đáp án:**
[
O(N)
]

---

# Bài 2. Xác định độ phức tạp

```python
for i in range(n):
    for j in range(n):
        print(i + j)
```

**Đáp án:**
[
O(N^2)
]

---

# Bài 3. Xác định độ phức tạp

```python
for i in range(n):
    for j in range(i):
        print(i, j)
```

**Đáp án:**
[
O(N^2)
]

---

# Bài 4. Xác định độ phức tạp

```python
while n > 0:
    n //= 10
```

**Đáp án:**
[
O(\log N)
]

Vì mỗi lần `N` bị giảm 10 lần.

---

# Bài 5. Xác định độ phức tạp

```python
for i in range(n):
    print(i)

for j in range(n):
    for k in range(n):
        print(j, k)
```

**Đáp án:**

* Đoạn 1: `O(N)`
* Đoạn 2: `O(N²)`

Tổng:
[
O(N^2)
]

---

# XIII. Bài tập vận dụng tư duy chọn thuật toán

---

## Bài 6. Tính tổng từ 1 đến N

Hãy viết:

1. Cách `O(N)`
2. Cách `O(1)`

---

## Bài 7. Đếm số chính phương ≤ N

Hãy viết:

1. Cách `O(N)`
2. Cách `O(1)`

---

## Bài 8. Kiểm tra số nguyên tố

Hãy viết:

1. Cách `O(N)`
2. Cách `O(√N)`

---

## Bài 9. Đếm số cặp `(i, j)` với `i < j`

Cho dãy có `N` phần tử.
Hãy ước lượng số cặp có thể tạo ra.

**Gợi ý:**
[
\frac{N(N-1)}{2}
]

---

## Bài 10. Đoán thuật toán phù hợp

Với từng giới hạn dưới đây, hãy đoán độ phức tạp phù hợp:

1. `N ≤ 100`
2. `N ≤ 10^5`
3. `N ≤ 10^9`

---

# XIV. Bài tập về nhà

---

## Bài 1. Phân tích độ phức tạp

```python
for i in range(1, n + 1):
    if i % 2 == 0:
        count += 1
```

---

## Bài 2. Phân tích độ phức tạp

```python
for i in range(1, n + 1):
    if i % 2 == 0:
        c1 += 1
    else:
        c2 += 1
```

---

## Bài 3. Phân tích độ phức tạp

```python
for i in range(1, n + 1):
    if i % 2 == 0:
        for j in range(1, n + 1):
            count += 1
```

---

## Bài 4. Phân tích độ phức tạp

```python
i = n
while i > 0:
    i -= 1
```

---

## Bài 5. Phân tích độ phức tạp

```python
i = n
while i > 0:
    i //= 2
```

---

## Bài 6. Phân tích độ phức tạp

```python
for i in range(1, n):
    for j in range(i + 1, n + 1):
        count += 1
```

---

## Bài 7. Phân tích độ phức tạp

```python
for i in range(1, n - 1):
    for j in range(i + 1, n):
        for k in range(j + 1, n + 1):
            count += 1
```

Nhóm bài tập này bám sát hệ thống bài luyện phân tích thuật toán trong tài liệu chuyên Tin. 

---

# XV. Đề thi vận dụng / Đề chuẩn chuyên

---

# Đề 1. Tồn tại đoạn con có tổng bằng K

## Bài toán

Cho dãy số nguyên dương gồm `N` phần tử và một số nguyên dương `K`.
Hãy xác định xem có tồn tại một đoạn con liên tiếp có tổng bằng `K` hay không.

---

## Yêu cầu phân tích

Hãy đề xuất:

### Cách 1

Thuật toán có độ phức tạp:
[
O(N^3)
]

### Cách 2

Thuật toán có độ phức tạp:
[
O(N^2)
]

### Cách 3

Thuật toán có độ phức tạp:
[
O(N)
]

Đây là bài tập trực tiếp trong chuyên đề phân tích thuật toán của tài liệu giáo khoa chuyên Tin, rất phù hợp để luyện tư duy “một bài – nhiều cấp độ tối ưu”. 

---

# Đề 2. Đếm số chính phương

## Bài toán

Cho số nguyên dương `N` (`1 ≤ N ≤ 10^12`).
Hãy đếm số lượng số chính phương không vượt quá `N`.

---

## Phân tích yêu cầu

* Nếu làm `O(N)`: không thể chạy.
* Cần nhận ra:
  [
  \text{số lượng} = \lfloor \sqrt{N} \rfloor
  ]

### Độ phức tạp cần đạt

[
O(1)
]

Bài này được nêu trong tài liệu nhập môn như một ví dụ điển hình cho việc tối ưu từ duyệt toàn bộ sang công thức trực tiếp. 

---

# Đề 3. Kiểm tra số nguyên tố lớn

## Bài toán

Cho `N ≤ 10^12`.
Hãy kiểm tra `N` có phải số nguyên tố hay không.

---

## Phân tích yêu cầu

* Không thể thử chia đến `N-1`.
* Cần thử chia đến:
  [
  \sqrt{N}
  ]

### Độ phức tạp

[
O(\sqrt{N})
]

---

# XVI. Lỗi học sinh thường gặp

---

## 1. Cứ thấy hai vòng lặp là kết luận `O(N²)`

Sai trong trường hợp hai vòng **nối tiếp**.

Ví dụ:

```python
for i in range(n):
    ...

for j in range(n):
    ...
```

Độ phức tạp vẫn là:
[
O(N)
]

---

## 2. Không bỏ hằng số

Sai:
[
O(2N)
]

Đúng:
[
O(N)
]

---

## 3. Không phân biệt `O(N + N²)` với `O(N²)`

Khi cộng các độ phức tạp, giữ phần lớn nhất:
[
O(N + N^2) = O(N^2)
]

---

## 4. Nghĩ code đúng là đủ

Trong thi thuật toán:

* Đúng nhưng quá chậm → vẫn không được điểm tối đa.
* Nhiều bài có subtasks, lời giải chậm chỉ lấy được điểm nhỏ.

---

## 5. Không nhìn giới hạn dữ liệu

Ví dụ:

* `N ≤ 10^5`
* Học sinh vẫn viết `O(N²)`

Đây là lỗi rất phổ biến.

---

# XVII. Ghi nhớ cuối bài

Học sinh cần nhớ 6 ý:

> **1. Độ phức tạp cho biết thuật toán chậm nhanh thế nào khi dữ liệu lớn lên.**

> **2. Một vòng lặp chạy N lần thường là O(N).**

> **3. Hai vòng lặp lồng nhau thường là O(N²).**

> **4. Mỗi lần dữ liệu giảm một nửa thường là O(log N).**

> **5. Khi nhiều đoạn code nối tiếp, lấy bậc lớn nhất.**

> **6. Đọc giới hạn dữ liệu trước khi chọn thuật toán.**

---

# XVIII. Phiên bản tóm tắt để ghi vở

## Bài 20. Độ phức tạp thuật toán

* Độ phức tạp dùng để đánh giá tốc độ thuật toán khi dữ liệu tăng.
* Ký hiệu thường dùng: `O(...)`.

### Các mức độ cơ bản

| Ký hiệu      | Ý nghĩa                  |
| ------------ | ------------------------ |
| `O(1)`       | Hằng số                  |
| `O(log N)`   | Chia nhỏ dần             |
| `O(N)`       | Duyệt một lần            |
| `O(N log N)` | Hiệu quả với dữ liệu lớn |
| `O(N²)`      | Hai vòng lặp lồng nhau   |
| `O(N³)`      | Ba vòng lặp lồng nhau    |

### Quy tắc

* Lệnh đơn: `O(1)`
* Vòng lặp chạy `N` lần: `O(N)`
* Hai vòng lặp lồng: `O(N²)`
* Ba vòng lặp lồng: `O(N³)`
* Mỗi lần chia đôi: `O(log N)`
* Các đoạn nối tiếp: lấy bậc lớn nhất

### Ý nghĩa khi làm bài

* `N ≤ 100`: có thể nghĩ tới `O(N³)`
* `N ≤ 1000`: có thể dùng `O(N²)`
* `N ≤ 10^5`: nên dùng `O(N log N)` hoặc `O(N)`
* `N` rất lớn: cần `O(log N)`, `O(√N)` hoặc `O(1)`
