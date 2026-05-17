# Bài 3. Biến và kiểu dữ liệu cơ bản

---

# I. Mục tiêu bài học

## 1. Về kiến thức

* Hiểu **biến** là nơi dùng để lưu trữ dữ liệu trong chương trình.
* Biết ba kiểu dữ liệu cơ bản:

  * `int`: Số nguyên
  * `float`: Số thực
  * `str`: Chuỗi ký tự
* Hiểu phép gán giá trị cho biến bằng dấu `=`.

## 2. Về kỹ năng

* Viết được chương trình Python đúng cú pháp.
* Khai báo và sử dụng biến trong các bài toán đơn giản.
* Nhận biết và kiểm tra được kiểu dữ liệu của một giá trị.
* Trình bày lời giải rõ ràng theo hướng giáo án.

## 3. Về tư duy

* Biết xác định:

  * **Input**: Dữ liệu đầu vào
  * **Xử lý**: Các thao tác cần thực hiện
  * **Output**: Kết quả cần in ra
* Biết lựa chọn kiểu dữ liệu phù hợp cho từng bài toán.
* Biết kiểm tra công thức trước khi viết chương trình.

---

# II. Lý thuyết

## 1. Biến là gì?

Biến là một tên gọi dùng để lưu trữ dữ liệu trong chương trình.

Ta có thể hình dung biến giống như một chiếc hộp:

* Tên biến là **nhãn dán** bên ngoài hộp.
* Giá trị là **dữ liệu** được đặt trong hộp.

### Ví dụ

```python
age = 15
```

Trong đó:

* `age` là tên biến.
* `15` là giá trị được lưu.
* Dấu `=` dùng để gán giá trị cho biến.

---

## 2. Phép gán trong Python

Trong Python, dấu `=` không mang nghĩa “bằng nhau” như trong toán học, mà có nghĩa là:

> Gán giá trị bên phải cho biến bên trái.

### Ví dụ

```python
x = 10
```

Nghĩa là biến `x` đang lưu giá trị `10`.

---

## 3. Biến có thể thay đổi giá trị

Một biến có thể được gán lại giá trị mới trong quá trình chạy chương trình.

### Ví dụ

```python
x = 5
x = 9
print(x)
```

Kết quả:

```text
9
```

Giải thích:

* Ban đầu `x` lưu giá trị `5`.
* Sau đó `x` được gán lại thành `9`.
* Khi in ra, chương trình dùng giá trị mới nhất của `x`.

---

## 4. Các kiểu dữ liệu cơ bản

### 4.1. Kiểu số nguyên `int`

Dùng để lưu các số nguyên, không có phần thập phân.

### Ví dụ

```python
age = 15
quantity = 100
```

---

### 4.2. Kiểu số thực `float`

Dùng để lưu các số có phần thập phân.

### Ví dụ

```python
score = 8.5
price = 12.75
```

---

### 4.3. Kiểu chuỗi `str`

Dùng để lưu văn bản hoặc ký tự.

Chuỗi thường được đặt trong dấu nháy đơn `' '` hoặc dấu nháy kép `" "`.

### Ví dụ

```python
name = "An"
class_name = "10A1"
```

---

## 5. Kiểm tra kiểu dữ liệu bằng `type()`

Hàm `type()` giúp quan sát kiểu dữ liệu của một biến hoặc một giá trị.

### Ví dụ

```python
x = 10
print(type(x))
```

Kết quả:

```text
<class 'int'>
```

---

### Ví dụ thêm

```python
a = 7
b = 8.5
c = "Python"

print(type(a))
print(type(b))
print(type(c))
```

Kết quả:

```text
<class 'int'>
<class 'float'>
<class 'str'>
```

---

# III. Ví dụ minh họa

## 1. Lưu thông tin học sinh

### Bài toán

Lưu tên, tuổi và điểm của một học sinh, sau đó in ra màn hình.

### Code

```python
name = "An"
age = 15
score = 8.5

print(name, age, score)
```

### Kết quả

```text
An 15 8.5
```

### Phân tích

* `name` có kiểu `str`.
* `age` có kiểu `int`.
* `score` có kiểu `float`.

---

## 2. Biến thay đổi giá trị

### Bài toán

Gán giá trị ban đầu cho biến `x`, thay đổi giá trị của nó, sau đó in ra kết quả.

### Code

```python
x = 5
x = 9

print(x)
```

### Kết quả

```text
9
```

---

## 3. Kiểm tra kiểu dữ liệu

### Bài toán

Tạo ba biến thuộc ba kiểu dữ liệu cơ bản và in ra kiểu của từng biến.

### Code

```python
name = "Lan"
age = 16
height = 1.62

print(type(name))
print(type(age))
print(type(height))
```

### Kết quả

```text
<class 'str'>
<class 'int'>
<class 'float'>
```

---

# IV. Bài tập vận dụng

## Bài 1. Khai báo thông tin cá nhân

Khai báo ba biến:

* Tên
* Tuổi
* Điểm trung bình

Sau đó in cả ba giá trị ra màn hình.

---

## Bài 2. Nhập một số nguyên và in kiểu dữ liệu

Nhập một số nguyên từ bàn phím, sau đó in ra kiểu dữ liệu của biến vừa nhập.

### Gợi ý

Dùng:

```python
n = int(input())
print(type(n))
```

---

## Bài 3. Nhập một số thực và in kiểu dữ liệu

Nhập một số thực từ bàn phím, sau đó in ra kiểu dữ liệu của biến vừa nhập.

### Gợi ý

Dùng:

```python
x = float(input())
print(type(x))
```

---

# V. Bài tập về nhà

## Bài 1. Lưu thông tin sản phẩm

Khai báo các biến lưu:

* Tên sản phẩm
* Giá sản phẩm
* Số lượng còn lại

Sau đó in toàn bộ thông tin ra màn hình.

---

## Bài 2. Nhập năm sinh và tính tuổi gần đúng

Nhập năm sinh của một người, sau đó tính tuổi gần đúng theo công thức:

[
\text{Tuổi} = 2026 - \text{Năm sinh}
]

---

## Bài 3. So sánh `input()` và `int(input())`

Viết hai đoạn chương trình:

### Đoạn 1

```python
x = input()
print(type(x))
```

### Đoạn 2

```python
x = int(input())
print(type(x))
```

Quan sát sự khác biệt về kiểu dữ liệu.

---

# VI. Lỗi học sinh thường gặp

## 1. Dùng biến trước khi gán giá trị

### Sai

```python
print(x)
x = 10
```

Chương trình sẽ báo lỗi vì `x` chưa được tạo trước khi sử dụng.

### Đúng

```python
x = 10
print(x)
```

---

## 2. Đặt tên biến khó hiểu

### Chưa tốt

```python
a = "An"
b = 15
c = 8.5
```

### Tốt hơn

```python
name = "An"
age = 15
score = 8.5
```

Tên biến rõ nghĩa giúp chương trình dễ đọc và dễ sửa hơn.

---

## 3. Nhầm chuỗi số với số thật sự

### Ví dụ

```python
x = "10"
y = "20"
print(x + y)
```

Kết quả:

```text
1020
```

Vì `"10"` và `"20"` là chuỗi.

Muốn cộng như số, cần dùng kiểu `int`:

```python
x = 10
y = 20
print(x + y)
```

Kết quả:

```text
30
```

---

# VII. Đề thi thật và bài chuẩn nhập môn

## Đề 1. Tính diện tích hình chữ nhật

Khai báo hai biến:

* Chiều dài
* Chiều rộng

Tính và in diện tích hình chữ nhật:

[
S = \text{chiều dài} \times \text{chiều rộng}
]

---

## Đề 2. Tính điểm trung bình

Khai báo ba biến lưu điểm của ba môn học.
Tính điểm trung bình cộng và in kết quả.

[
\text{Điểm trung bình} = \frac{a+b+c}{3}
]

---

## Đề 3. Ghép tên và lớp thành thông báo

Khai báo:

* Tên học sinh
* Tên lớp

In ra thông báo theo mẫu:

```text
Bạn An học lớp 10A1
```

---

# VIII. Ghi nhớ cuối bài

* Biến là nơi lưu dữ liệu trong chương trình.
* Dấu `=` dùng để gán giá trị cho biến.
* Ba kiểu dữ liệu cơ bản:

  * `int`
  * `float`
  * `str`
* Dùng `type()` để kiểm tra kiểu dữ liệu.
* Nên đặt tên biến rõ ràng, dễ hiểu.
* Cần chọn đúng kiểu dữ liệu trước khi xử lý bài toán.

---

# IX. Tóm tắt bài học

Biến và kiểu dữ liệu là nền tảng quan trọng trong Python.

Một chương trình rõ ràng thường bắt đầu từ việc:

* Chọn tên biến phù hợp.
* Chọn kiểu dữ liệu đúng.
* Gán giá trị chính xác.
* Sử dụng biến để xử lý và in kết quả.
