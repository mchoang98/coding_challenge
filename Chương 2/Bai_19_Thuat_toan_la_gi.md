# BÀI 19. THUẬT TOÁN LÀ GÌ?

## Cách phân tích một bài toán lập trình

---

## I. Mục tiêu bài học

Sau bài này, học sinh cần:

### 1. Về kiến thức

* Hiểu được **thuật toán là gì**.
* Biết một bài toán lập trình luôn có:

  * **Dữ liệu vào – Input**
  * **Dữ liệu ra – Output**
  * **Cách xử lý – Thuật toán**
* Nắm được các đặc điểm cơ bản của một thuật toán tốt:

  * Rõ ràng
  * Chính xác
  * Hữu hạn
  * Có thể áp dụng cho nhiều bộ dữ liệu

### 2. Về kỹ năng

* Biết cách đọc đề và tách đề thành:

  1. Đề cho gì?
  2. Cần tìm gì?
  3. Làm tay với ví dụ nhỏ như thế nào?
  4. Các bước giải ra sao?
  5. Chuyển ý tưởng thành code thế nào?
* Biết viết thuật toán đơn giản bằng:

  * Lời văn
  * Các bước tuần tự
  * Code Python cơ bản

### 3. Về tư duy

* Không vội viết code ngay khi đọc đề.
* Hình thành thói quen:

  > **Hiểu đề → Phân tích → Nghĩ cách giải → Viết code → Kiểm tra lại**

---

# II. Kiến thức trọng tâm

---

## 1. Thuật toán là gì?

### 1.1. Khái niệm đơn giản

**Thuật toán** là một dãy các bước rõ ràng, thực hiện theo thứ tự, để giải một bài toán.

Có thể hiểu:

> Thuật toán giống như **công thức nấu ăn**.
> Muốn nấu được món ăn đúng, ta phải làm đúng các bước theo đúng thứ tự.

---

### 1.2. Ví dụ đời sống

#### Ví dụ: Thuật toán pha mì

**Input:**

* 1 gói mì
* Nước sôi
* Gia vị

**Các bước:**

1. Cho mì vào tô.
2. Cho gói gia vị vào.
3. Đổ nước sôi.
4. Đậy nắp 3 phút.
5. Mở nắp và ăn.

**Output:**

* Một tô mì đã ăn được.

---

### 1.3. Ví dụ trong lập trình

#### Bài toán

Nhập hai số `a`, `b`. Tính tổng của chúng.

**Input:**

* Hai số `a`, `b`

**Output:**

* Tổng `a + b`

**Thuật toán:**

1. Nhập `a`
2. Nhập `b`
3. Tính `s = a + b`
4. In `s`

**Code Python**

```python
a = int(input())
b = int(input())

s = a + b

print(s)
```

---

# III. Các thành phần của một bài toán lập trình

Một bài toán lập trình thường có 3 phần chính:

| Thành phần | Ý nghĩa                              |
| ---------- | ------------------------------------ |
| Input      | Dữ liệu đề bài cung cấp              |
| Output     | Kết quả cần in ra                    |
| Thuật toán | Cách xử lý để đi từ Input đến Output |

---

## Ví dụ minh họa

### Đề bài

Nhập số nguyên dương `N`. Tính bình phương của `N`.

### Phân tích

#### 1. Input

* Một số nguyên dương `N`

#### 2. Output

* Giá trị `N²`

#### 3. Cách xử lý

* Tính `N * N`

### Code

```python
n = int(input())
print(n * n)
```

---

# IV. Đặc điểm của một thuật toán tốt

---

## 1. Tính rõ ràng

Mỗi bước phải dễ hiểu, không mơ hồ.

### Ví dụ chưa rõ

> “Xử lý số N.”

Không rõ xử lý kiểu gì.

### Ví dụ rõ

> “Tính tổng các chữ số của N.”

---

## 2. Tính chính xác

Thuật toán phải cho ra kết quả đúng.

### Ví dụ

Muốn tính diện tích hình chữ nhật cạnh `a`, `b`:

[
S = a \times b
]

Nếu viết nhầm:

[
S = a + b
]

thì chương trình sai.

---

## 3. Tính hữu hạn

Thuật toán phải dừng lại sau một số bước nhất định.

### Ví dụ sai

```python
while True:
    print("Hello")
```

Chương trình chạy mãi mãi, không dừng.

---

## 4. Tính tổng quát

Thuật toán phải dùng được cho nhiều dữ liệu khác nhau, không chỉ đúng với một ví dụ.

### Ví dụ không tốt

Muốn tính tổng từ 1 đến `N`, nhưng code:

```python
print(15)
```

Cách này chỉ đúng khi `N = 5`.

### Cách tốt

```python
n = int(input())
s = n * (n + 1) // 2
print(s)
```

Dùng được cho mọi `N`.

---

# V. Quy trình phân tích một bài toán lập trình

Khi nhận một đề, học sinh nên làm theo **5 bước**.

---

## Bước 1. Xác định đề cho gì

Đọc kỹ xem:

* Có bao nhiêu giá trị đầu vào?
* Kiểu dữ liệu là số hay xâu?
* Có điều kiện gì không?

### Ví dụ

> Cho số nguyên dương `N`.

Ta biết:

* Có 1 input
* Là số nguyên
* `N > 0`

---

## Bước 2. Xác định đề yêu cầu gì

Tìm câu quan trọng:

* “Hãy tính…”
* “Hãy đếm…”
* “Hãy kiểm tra…”
* “Hãy tìm…”

### Ví dụ

> Hãy tính tổng các số từ 1 đến N.

Kết quả cần tìm:
[
1 + 2 + 3 + ... + N
]

---

## Bước 3. Làm tay với ví dụ nhỏ

Đây là bước rất quan trọng.

### Ví dụ

Nếu `N = 5`:

[
1 + 2 + 3 + 4 + 5 = 15
]

Từ đó ta biết output phải là `15`.

---

## Bước 4. Tìm cách giải

Có thể nghĩ theo hai hướng:

### Cách 1. Làm theo đúng định nghĩa

Dùng vòng lặp cộng từng số.

```python
s = 0
for i in range(1, n + 1):
    s += i
```

### Cách 2. Tìm quy luật hoặc công thức

[
S = \frac{N(N+1)}{2}
]

```python
s = n * (n + 1) // 2
```

---

## Bước 5. Viết code và tự kiểm tra

Sau khi code, cần chạy thử với:

* Ví dụ đề bài
* Một vài test tự tạo
* Trường hợp nhỏ nhất

---

# VI. Ví dụ 1 – Tính tổng hai số

---

## 1. Đề bài

Nhập hai số nguyên `a`, `b`. In ra tổng của chúng.

---

## 2. Phân tích đề

### Input

* Số nguyên `a`
* Số nguyên `b`

### Output

* `a + b`

---

## 3. Làm tay

Nếu:

* `a = 4`
* `b = 7`

Thì:
[
4 + 7 = 11
]

---

## 4. Thuật toán bằng lời

1. Nhập `a`
2. Nhập `b`
3. Tính `s = a + b`
4. In `s`

---

## 5. Code Python

```python
a = int(input())
b = int(input())

s = a + b

print(s)
```

---

## 6. Test

### Input

```text
4
7
```

### Output

```text
11
```

---

# VII. Ví dụ 2 – Tính chu vi hình chữ nhật

---

## 1. Đề bài

Nhập chiều dài `a` và chiều rộng `b` của hình chữ nhật. Tính chu vi.

---

## 2. Phân tích

### Input

* `a`
* `b`

### Output

* Chu vi hình chữ nhật

### Công thức

[
P = 2(a + b)
]

---

## 3. Làm tay

Nếu:

* `a = 5`
* `b = 3`

Thì:
[
P = 2(5+3) = 16
]

---

## 4. Thuật toán

1. Nhập `a`
2. Nhập `b`
3. Tính `p = 2 * (a + b)`
4. In `p`

---

## 5. Code Python

```python
a = int(input())
b = int(input())

p = 2 * (a + b)

print(p)
```

---

# VIII. Ví dụ 3 – Tính tổng từ 1 đến N

---

## 1. Đề bài

Nhập số nguyên dương `N`. Tính:

[
S = 1 + 2 + 3 + ... + N
]

---

## 2. Phân tích

### Input

* Một số nguyên dương `N`

### Output

* Tổng `S`

---

## 3. Làm tay

Với `N = 5`:

[
S = 1 + 2 + 3 + 4 + 5 = 15
]

---

## 4. Cách 1 – Dùng vòng lặp

### Thuật toán

1. Gán `s = 0`
2. Duyệt `i` từ `1` đến `N`
3. Cộng `i` vào `s`
4. In `s`

### Code

```python
n = int(input())

s = 0
for i in range(1, n + 1):
    s += i

print(s)
```

---

## 5. Cách 2 – Dùng công thức

[
S = \frac{N(N+1)}{2}
]

### Code

```python
n = int(input())

s = n * (n + 1) // 2

print(s)
```

---

## 6. So sánh hai cách

| Cách      | Ưu điểm   | Nhược điểm             |
| --------- | --------- | ---------------------- |
| Vòng lặp  | Dễ hiểu   | Chậm hơn nếu N rất lớn |
| Công thức | Rất nhanh | Cần nhận ra quy luật   |

---

# IX. Ví dụ 4 – Tìm số lớn hơn trong hai số

---

## 1. Đề bài

Nhập hai số nguyên `a`, `b`. In ra số lớn hơn.

---

## 2. Phân tích

### Input

* `a`, `b`

### Output

* Giá trị lớn hơn giữa `a` và `b`

---

## 3. Làm tay

Nếu:

* `a = 8`
* `b = 5`

Kết quả là `8`.

---

## 4. Thuật toán

1. Nhập `a`
2. Nhập `b`
3. Nếu `a > b`, in `a`
4. Ngược lại, in `b`

---

## 5. Code Python

```python
a = int(input())
b = int(input())

if a > b:
    print(a)
else:
    print(b)
```

---

# X. Mẫu tư duy giải bài cho học sinh

Khi gặp bài mới, có thể ghi ra giấy theo mẫu sau:

---

## Mẫu phân tích

### 1. Đề cho:

* ...

### 2. Cần tìm:

* ...

### 3. Ví dụ nhỏ:

* ...

### 4. Ý tưởng:

* ...

### 5. Các bước xử lý:

1. ...
2. ...
3. ...

### 6. Code:

```python
# Viết code ở đây
```

---

# XI. Câu hỏi gợi mở trên lớp

Giáo viên có thể đặt lần lượt:

### Câu 1

Nếu đề bài yêu cầu:

> “Nhập hai số a, b, tính tích của chúng”

thì:

* Input là gì?
* Output là gì?

---

### Câu 2

Một thuật toán có thể đúng với `N = 5` nhưng sai với `N = 10` không?

**Đáp án:** Có. Vì thuật toán có thể chưa tổng quát.

---

### Câu 3

Vì sao ta không nên mở máy code ngay khi chưa phân tích đề?

**Gợi ý:** Vì dễ:

* Hiểu sai yêu cầu
* Viết sai hướng
* Mất thời gian sửa

---

### Câu 4

Bài “tổng từ 1 đến N” có mấy cách giải?

**Đáp án:** Ít nhất 2:

* Duyệt cộng dồn
* Dùng công thức

---

# XII. Bài tập vận dụng trên lớp

---

## Bài 1. Tính diện tích hình chữ nhật

### Đề bài

Nhập chiều dài `a` và chiều rộng `b`. Tính diện tích hình chữ nhật.

### Gợi ý

[
S = a \times b
]

---

## Bài 2. Tính trung bình cộng hai số

### Đề bài

Nhập hai số `a`, `b`. Tính trung bình cộng.

### Gợi ý

[
TBC = \frac{a+b}{2}
]

---

## Bài 3. Tính tổng ba số

### Đề bài

Nhập `a`, `b`, `c`. In tổng ba số.

---

## Bài 4. Tìm số nhỏ hơn trong hai số

### Đề bài

Nhập `a`, `b`. In số nhỏ hơn.

---

## Bài 5. Tính tổng các số chẵn từ 1 đến N

### Đề bài

Nhập `N`. Tính:

[
2 + 4 + 6 + ...
]

không vượt quá `N`.

---

# XIII. Bài tập về nhà

---

## Bài 1. Chu vi hình vuông

Nhập cạnh `a`, tính chu vi hình vuông.

---

## Bài 2. Diện tích tam giác

Nhập đáy `a`, chiều cao `h`, tính diện tích:

[
S = \frac{a \times h}{2}
]

---

## Bài 3. Tổng bình phương

Nhập `N`, tính:

[
1^2 + 2^2 + ... + N^2
]

---

## Bài 4. Tìm số lớn nhất trong ba số

Nhập `a`, `b`, `c`. In ra số lớn nhất.

---

## Bài 5. Kiểm tra số chẵn lẻ

Nhập `N`. In:

* `"EVEN"` nếu N chẵn
* `"ODD"` nếu N lẻ

---

# XIV. Đề thi vận dụng

---

## Đề 1. Tổng các số tự nhiên

### Bài toán

Cho số nguyên dương `N`. Tính:

[
S = 1 + 2 + ... + N
]

### Input

Một số nguyên dương `N`.

### Output

In ra giá trị `S`.

### Ví dụ

| Input | Output |
| ----- | ------ |
| 5     | 15     |

---

## Đề 2. Lát gạch viền

### Bài toán

Một hình chữ nhật kích thước `a × b` được chia thành các ô vuông đơn vị.
Các viên gạch ở viền có màu xanh, phần bên trong màu vàng.
Hãy tính số viên xanh và số viên vàng.

### Ý tưởng

* Gạch vàng:
  [
  (a-2)(b-2)
  ]
* Gạch xanh:
  [
  ab - (a-2)(b-2)
  ]

Dạng bài này xuất hiện trong tài liệu nhập môn và rất phù hợp để rèn bước **đọc đề → mô hình hóa → viết công thức**.

---

# XV. Lỗi học sinh hay gặp

---

## 1. Không xác định rõ input/output

Ví dụ đề yêu cầu in tổng, nhưng lại in cả câu chữ thừa.

---

## 2. Nhầm công thức

Ví dụ chu vi hình chữ nhật:

* Sai: `a * b`
* Đúng: `2 * (a + b)`

---

## 3. Không làm tay ví dụ nhỏ

Dẫn đến:

* Không phát hiện code sai
* Không hiểu kết quả mong muốn

---

## 4. Code trước, hiểu sau

Đây là thói quen cần sửa sớm.

---

# XVI. Ghi nhớ cuối bài

Học sinh cần thuộc 4 câu:

> **1. Bài toán lập trình luôn có Input, Output và cách xử lý.**

> **2. Thuật toán là các bước rõ ràng để giải bài toán.**

> **3. Trước khi code phải phân tích đề.**

> **4. Một bài toán có thể có nhiều cách giải, cần dần học cách chọn cách tốt hơn.**

---

# XVII. Phiên bản tóm tắt để ghi vở

## Bài 19. Thuật toán là gì?

* Thuật toán là dãy hữu hạn các bước rõ ràng để giải bài toán.
* Một bài toán lập trình gồm:

  * Input
  * Output
  * Thuật toán
* Quy trình giải bài:

  1. Xác định đề cho gì
  2. Xác định cần tìm gì
  3. Làm tay ví dụ nhỏ
  4. Lập các bước giải
  5. Viết code và kiểm tra
* Thuật toán tốt cần:

  * Rõ ràng
  * Chính xác
  * Hữu hạn
  * Tổng quát
