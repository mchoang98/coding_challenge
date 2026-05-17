# Bài 2. Nhập xuất dữ liệu trong Python

---

# I. Mục tiêu bài học

## 1. Về kiến thức

* Biết dùng `input()` để nhập dữ liệu.
* Biết dùng `print()` để xuất kết quả.
* Hiểu rằng dữ liệu nhập bằng `input()` ban đầu là **chuỗi**.

## 2. Về kỹ năng

* Viết được chương trình Python đúng cú pháp.
* Áp dụng được nội dung bài học vào các bài toán nhập môn.
* Trình bày lời giải rõ ràng theo hướng giáo án.

## 3. Về tư duy

* Biết xác định:

  * **Input**: Dữ liệu đầu vào
  * **Xử lý**: Các phép tính hoặc thao tác cần thực hiện
  * **Output**: Kết quả cần in ra
* Biết kiểm tra công thức trước khi viết code.

---

# II. Lý thuyết

## 1. Nhập dữ liệu

Trong Python, hàm `input()` dùng để đọc một dòng dữ liệu từ bàn phím.

### Cú pháp

```python
bien = input()
```

### Ví dụ

```python
name = input()
```

Nếu người dùng nhập:

```text
Phu
```

thì biến `name` sẽ lưu giá trị:

```python
"Phu"
```

---

## 2. Xuất dữ liệu

Hàm `print()` dùng để in dữ liệu ra màn hình.

### Cú pháp

```python
print(gia_tri_can_in)
```

### Ví dụ

```python
print("Hello Python")
```

Kết quả:

```text
Hello Python
```

---

## 3. Dữ liệu nhập vào mặc định là chuỗi

Khi dùng `input()`, dữ liệu nhận được luôn có kiểu `str`, kể cả khi người dùng nhập số.

### Ví dụ

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

Kết quả sẽ là:

```text
23
```

Vì `"2"` và `"3"` là chuỗi, nên phép `+` sẽ nối chuỗi.

---

## 4. Nhập số nguyên và số thực

### Nhập số nguyên

Dùng `int(input())`.

```python
n = int(input())
```

### Nhập số thực

Dùng `float(input())`.

```python
x = float(input())
```

---

# III. Ví dụ minh họa

## 1. Nhập và in lại số nguyên

### Bài toán

Nhập một số nguyên `n`, sau đó in lại số đó.

### Code

```python
n = int(input())
print(n)
```

### Ví dụ

Input:

```text
15
```

Output:

```text
15
```

---

## 2. Tính tổng hai số nguyên

### Bài toán

Nhập hai số nguyên `a`, `b`. In ra tổng của chúng.

### Phân tích

* **Input**: `a`, `b`
* **Xử lý**: Tính `a + b`
* **Output**: Tổng hai số

### Code

```python
a = int(input())
b = int(input())

print(a + b)
```

### Ví dụ

Input:

```text
4
7
```

Output:

```text
11
```

---

## 3. Nhập tên và in lời chào

### Bài toán

Nhập tên một người và in ra lời chào.

### Code

```python
name = input()
print("Xin chào", name)
```

### Ví dụ

Input:

```text
Phu
```

Output:

```text
Xin chào Phu
```

---

# IV. Bài tập vận dụng

## Bài 1. Nhập tên và in lại tên

Nhập tên của một học sinh, sau đó in lại đúng tên vừa nhập.

---

## Bài 2. Tính hiệu hai số thực

Nhập hai số thực `a`, `b`. In ra giá trị:

[
a - b
]

---

## Bài 3. In thông báo tuổi

Nhập tuổi của một người, sau đó in ra câu:

```text
Ban nam nay X tuoi
```

Trong đó `X` là tuổi vừa nhập.

---

# V. Bài tập về nhà

## Bài 1. Tính tích hai số nguyên

Nhập hai số nguyên `a`, `b`. In ra tích:

[
a \times b
]

---

## Bài 2. In thông tin học sinh

Nhập lần lượt:

* Tên học sinh
* Lớp
* Điểm số

Sau đó in lại đầy đủ các thông tin trên.

---

## Bài 3. Tính trung bình cộng hai số

Nhập hai số thực `a`, `b`. In ra trung bình cộng của chúng:

[
\frac{a+b}{2}
]

---

# VI. Lỗi học sinh thường gặp

## 1. Quên ép kiểu khi nhập số

### Sai

```python
a = input()
b = input()
print(a + b)
```

Nếu nhập `2` và `3`, kết quả nhận được là:

```text
23
```

### Đúng

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

## 2. In sai số dòng so với yêu cầu

Một số bài yêu cầu mỗi kết quả nằm trên một dòng riêng.
Học sinh cần đọc kỹ đề để dùng `print()` phù hợp.

---

## 3. Nhầm `input()` với `print()`

* `input()` dùng để **nhập dữ liệu**.
* `print()` dùng để **xuất dữ liệu**.

---

# VII. Đề thi thật và bài chuẩn nhập môn

## Đề 1. Tổng số tuổi của hai bạn

Nhập tuổi của hai bạn. In ra tổng số tuổi.

---

## Đề 2. Tính tiền mua sản phẩm

Nhập:

* Đơn giá một sản phẩm
* Số lượng sản phẩm

In ra tổng số tiền cần trả.

---

## Đề 3. Tổng ba số nguyên

Nhập ba số nguyên trên ba dòng. In ra tổng của chúng.

---

# VIII. Ghi nhớ cuối bài

* Đọc kỹ đề bài trước khi lập trình.
* Xác định đúng:

  * Dữ liệu đầu vào
  * Cách xử lý
  * Kết quả đầu ra
* Dùng `input()` để nhập dữ liệu.
* Dùng `print()` để in kết quả.
* Khi nhập số, cần ép kiểu bằng `int()` hoặc `float()`.

---

# IX. Tóm tắt bài học

Mẫu nhập xuất cơ bản:

```python
n = int(input())
print(n)
```

Mẫu nhập hai số và tính toán:

```python
a = int(input())
b = int(input())

print(a + b)
```
