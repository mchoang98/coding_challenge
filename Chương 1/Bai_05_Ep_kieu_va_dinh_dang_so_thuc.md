# Bài 5. Ép kiểu và định dạng số thực

---

# I. Mục tiêu bài học

## 1. Về kiến thức

* Biết sử dụng các hàm ép kiểu cơ bản:

  * `int()`
  * `float()`
  * `str()`
* Hiểu ép kiểu là chuyển dữ liệu từ kiểu này sang kiểu khác khi cần thiết.
* Biết in số thực với số chữ số sau dấu phẩy theo yêu cầu.
* Hiểu vì sao **định dạng output đúng** là một phần quan trọng của lời giải.

## 2. Về kỹ năng

* Viết được chương trình Python đúng cú pháp.
* Ép kiểu dữ liệu đúng trước khi thực hiện phép tính.
* Định dạng được số thực bằng:

  * `f"{x:.2f}"`
  * `"{:.3f}".format(x)`
* Áp dụng kiến thức vào các bài toán nhập môn.
* Trình bày lời giải rõ ràng theo hướng giáo án.

## 3. Về tư duy

* Biết xác định:

  * **Input**: Dữ liệu đầu vào
  * **Xử lý**: Công thức và kiểu dữ liệu cần dùng
  * **Output**: Kết quả và định dạng cần in
* Biết kiểm tra xem dữ liệu có cần ép kiểu hay không.
* Biết đọc kỹ yêu cầu về số chữ số thập phân trong đề bài.

---

# II. Lý thuyết

## 1. Ép kiểu là gì?

Ép kiểu là thao tác chuyển dữ liệu từ kiểu này sang kiểu khác.

Trong Python, ba hàm ép kiểu thường gặp là:

| Hàm       | Công dụng             | Ví dụ           |
| --------- | --------------------- | --------------- |
| `int()`   | Chuyển sang số nguyên | `int("12")`     |
| `float()` | Chuyển sang số thực   | `float("3.14")` |
| `str()`   | Chuyển sang chuỗi     | `str(2026)`     |

---

## 2. Ép kiểu bằng `int()`

Hàm `int()` dùng để chuyển dữ liệu sang số nguyên.

### Ví dụ 1

```python
x = int("15")
print(x)
print(type(x))
```

Kết quả:

```text
15
<class 'int'>
```

---

### Ví dụ 2

```python
a = int(input())
b = int(input())

print(a + b)
```

Nếu nhập:

```text
10
20
```

Kết quả:

```text
30
```

---

## 3. Ép kiểu bằng `float()`

Hàm `float()` dùng để chuyển dữ liệu sang số thực.

### Ví dụ

```python
x = float("8.5")
print(x)
print(type(x))
```

Kết quả:

```text
8.5
<class 'float'>
```

---

## 4. Ép kiểu bằng `str()`

Hàm `str()` dùng để chuyển dữ liệu sang chuỗi.

### Ví dụ

```python
age = 15
message = "Tôi năm nay " + str(age) + " tuổi"

print(message)
```

Kết quả:

```text
Tôi năm nay 15 tuổi
```

---

## 5. Vì sao cần ép kiểu khi nhập dữ liệu?

Dữ liệu được nhập bằng `input()` luôn có kiểu `str`.

### Ví dụ chưa ép kiểu

```python
a = input()
b = input()

print(a + b)
```

Nếu nhập:

```text
2
3
```

Kết quả:

```text
23
```

Vì `"2"` và `"3"` là chuỗi nên Python nối chúng lại.

---

### Ví dụ đã ép kiểu

```python
a = int(input())
b = int(input())

print(a + b)
```

Kết quả:

```text
5
```

---

## 6. Định dạng số thực

Nhiều bài toán yêu cầu in kết quả với đúng số chữ số sau dấu phẩy.

Ví dụ:

* In 2 chữ số thập phân
* In 3 chữ số thập phân

Trong Python, ta có thể dùng **f-string** hoặc `.format()`.

---

## 7. Định dạng bằng f-string

### Cú pháp

```python
print(f"{x:.2f}")
```

Ý nghĩa:

* `x`: Giá trị cần in
* `.2f`: In số thực với **2 chữ số sau dấu phẩy**

---

### Ví dụ

```python
x = 3.1415926
print(f"{x:.2f}")
```

Kết quả:

```text
3.14
```

---

### Một số dạng thường dùng

| Cách viết    | Ý nghĩa                  |
| ------------ | ------------------------ |
| `f"{x:.1f}"` | In 1 chữ số sau dấu phẩy |
| `f"{x:.2f}"` | In 2 chữ số sau dấu phẩy |
| `f"{x:.3f}"` | In 3 chữ số sau dấu phẩy |

---

## 8. Định dạng bằng `.format()`

Ngoài f-string, ta có thể dùng:

```python
print("{:.3f}".format(x))
```

### Ví dụ

```python
x = 2.7182818
print("{:.3f}".format(x))
```

Kết quả:

```text
2.718
```

---

## 9. Sự khác nhau giữa giá trị và cách hiển thị

Khi dùng định dạng số thực, ta chỉ thay đổi **cách in ra màn hình**, không nhất thiết thay đổi giá trị thật đang lưu trong biến.

### Ví dụ

```python
x = 3.1415926

print(x)
print(f"{x:.2f}")
```

Kết quả:

```text
3.1415926
3.14
```

---

## 10. Ứng dụng trong bài toán

Các bài toán sau thường cần định dạng số thực:

* Diện tích hình tròn
* Trung bình cộng
* Chuyển đổi nhiệt độ
* Tính vận tốc, quãng đường, thời gian
* Các bài hình học yêu cầu in 2 hoặc 3 chữ số thập phân

---

# III. Ví dụ minh họa

## 1. Tính trung bình cộng hai số

### Bài toán

Nhập hai số nguyên `a`, `b`.
Tính trung bình cộng của chúng và in ra với 2 chữ số sau dấu phẩy.

### Công thức

$avg = \dfrac{a+b}{2}$

### Phân tích

* **Input**: `a`, `b`
* **Xử lý**: Tính $avg = \dfrac{a+b}{2}$
* **Output**: Giá trị trung bình với 2 chữ số thập phân

### Code

```python
a = int(input())
b = int(input())

avg = (a + b) / 2

print(f"{avg:.2f}")
```

### Ví dụ

Input:

```text
5
8
```

Output:

```text
6.50
```

---

## 2. Tính diện tích hình tròn

### Bài toán

Nhập bán kính hình tròn `r`.
Tính diện tích và in ra với 2 chữ số sau dấu phẩy.

### Công thức

$S = 3.14 \times r^2$

### Phân tích

* **Input**: `r`
* **Xử lý**: Tính $S = 3.14 \times r \times r$
* **Output**: Diện tích với 2 chữ số thập phân

### Code

```python
r = float(input())

s = 3.14 * r * r

print(f"{s:.2f}")
```

### Ví dụ

Input:

```text
2
```

Output:

```text
12.56
```

---

## 3. Ghép số vào câu thông báo

### Bài toán

Nhập tuổi của một người và in ra câu thông báo.

### Code

```python
age = int(input())

print("Bạn năm nay " + str(age) + " tuổi")
```

### Ví dụ

Input:

```text
16
```

Output:

```text
Bạn năm nay 16 tuổi
```

---

## 4. In số thực với 3 chữ số sau dấu phẩy

### Bài toán

Nhập một số thực `x`, in lại nó với 3 chữ số sau dấu phẩy.

### Code

```python
x = float(input())

print(f"{x:.3f}")
```

### Ví dụ

Input:

```text
7.2
```

Output:

```text
7.200
```

---

# IV. Bài tập vận dụng

## Bài 1. In số thực với 3 chữ số thập phân

Nhập một số thực `x`.
In ra giá trị của `x` với đúng 3 chữ số sau dấu phẩy.

---

## Bài 2. Tính trung bình cộng ba số

Nhập ba số thực `a`, `b`, `c`.
Tính trung bình cộng và in ra với 2 chữ số sau dấu phẩy.

### Công thức

$avg = \dfrac{a+b+c}{3}$

---

## Bài 3. Ghép tuổi vào câu thông báo

Nhập tuổi của một học sinh.
In ra câu:

```text
Hoc sinh nam nay X tuoi
```

Trong đó `X` là tuổi vừa nhập.

---

# V. Bài tập về nhà

## Bài 1. Đổi độ C sang độ F

Nhập nhiệt độ theo độ C.
Tính nhiệt độ tương ứng theo độ F.

### Công thức

$F = C \times \dfrac{9}{5} + 32$

In kết quả với 2 chữ số sau dấu phẩy.

---

## Bài 2. Tính diện tích tam giác vuông

Nhập độ dài hai cạnh góc vuông `a`, `b`.
Tính diện tích tam giác vuông.

### Công thức

$S = \dfrac{a \times b}{2}$

In kết quả với 2 chữ số sau dấu phẩy.

---

## Bài 3. Tạo thông báo chứa số năm nhập vào

Nhập một năm bất kỳ.
In ra thông báo:

```text
Nam vua nhap la X
```

Trong đó `X` là năm vừa nhập.

---

# VI. Lỗi học sinh thường gặp

## 1. Không ép kiểu trước khi tính toán

### Sai

```python
a = input()
b = input()

print(a + b)
```

Nếu nhập `4` và `5`, kết quả là:

```text
45
```

### Đúng

```python
a = int(input())
b = int(input())

print(a + b)
```

Kết quả:

```text
9
```

---

## 2. In sai số chữ số sau dấu phẩy

### Yêu cầu

In kết quả với 2 chữ số sau dấu phẩy.

### Chưa đúng

```python
x = 3.5
print(x)
```

Kết quả:

```text
3.5
```

### Đúng

```python
x = 3.5
print(f"{x:.2f}")
```

Kết quả:

```text
3.50
```

---

## 3. Dùng `int()` cho chuỗi chứa số thực

### Sai

```python
x = int("3.14")
```

Chương trình sẽ báo lỗi vì `"3.14"` không phải chuỗi biểu diễn số nguyên.

### Đúng

```python
x = float("3.14")
```

---

## 4. Nhầm giữa làm tròn hiển thị và thay đổi giá trị thật

### Ví dụ

```python
x = 3.4567
print(f"{x:.2f}")
print(x)
```

Kết quả:

```text
3.46
3.4567
```

Giá trị khi in được hiển thị là `3.46`, nhưng biến `x` vẫn giữ giá trị ban đầu.

---

# VII. Đề thi thật và bài chuẩn nhập môn

## Đề 1. Tính diện tích và in chuẩn định dạng

Nhập cạnh hình vuông `a`.
Tính diện tích:

$S = a^2$

In kết quả với 2 chữ số sau dấu phẩy.

---

## Đề 2. Trung bình cộng có làm tròn

Nhập ba điểm số.
Tính điểm trung bình:

$avg = \dfrac{a+b+c}{3}$

In ra với 1 chữ số sau dấu phẩy.

---

## Đề 3. In thông báo chứa dữ liệu đầu vào

Nhập tên học sinh và năm sinh.
In ra thông báo theo mẫu:

```text
Ban An sinh nam 2010
```

---

# VIII. Ghi nhớ cuối bài

* `input()` luôn trả về dữ liệu kiểu `str`.
* Muốn tính toán với số, cần ép kiểu bằng:

  * `int()`
  * `float()`
* Muốn ghép số vào chuỗi, có thể dùng:

  * `str()`
  * f-string
* Số thực thường cần in đúng định dạng theo yêu cầu đề bài.
* Dùng:

  * `f"{x:.2f}"` để in 2 chữ số thập phân
  * `f"{x:.3f}"` để in 3 chữ số thập phân
* Định dạng output đúng là một phần của bài làm đúng.

---

# IX. Tóm tắt bài học

Ép kiểu giúp chương trình xử lý dữ liệu đúng cách.
Định dạng số thực giúp kết quả in ra đúng yêu cầu đề bài.

Một chương trình tốt cần:

* Nhập đúng kiểu dữ liệu.
* Tính toán bằng công thức chính xác.
* In kết quả đúng định dạng.
