# Bài 4. Phép toán số học và thứ tự ưu tiên

---

# I. Mục tiêu bài học

## 1. Về kiến thức

* Nắm được các toán tử số học cơ bản trong Python:

  * `+`: Cộng
  * `-`: Trừ
  * `*`: Nhân
  * `/`: Chia thực
  * `//`: Chia nguyên
  * `%`: Chia lấy dư
  * `**`: Lũy thừa
* Hiểu thứ tự ưu tiên khi tính toán biểu thức.
* Biết dùng dấu ngoặc `()` để biểu thức rõ ràng và chính xác hơn.

## 2. Về kỹ năng

* Viết được chương trình Python đúng cú pháp.
* Sử dụng thành thạo các phép toán số học trong bài toán cơ bản.
* Chuyển được công thức toán học sang biểu thức Python.
* Trình bày lời giải rõ ràng theo hướng giáo án.

## 3. Về tư duy

* Biết xác định:

  * **Input**: Dữ liệu đầu vào
  * **Xử lý**: Công thức cần tính
  * **Output**: Kết quả cần in ra
* Biết kiểm tra công thức trước khi viết code.
* Biết thêm dấu ngoặc khi biểu thức có thể gây nhầm lẫn.

---

# II. Lý thuyết

## 1. Các phép toán số học cơ bản

Python hỗ trợ nhiều phép toán số học quen thuộc.

| Toán tử | Ý nghĩa     | Ví dụ    | Kết quả    |
| ------- | ----------- | -------- | ---------- |
| `+`     | Cộng        | `7 + 3`  | `10`       |
| `-`     | Trừ         | `7 - 3`  | `4`        |
| `*`     | Nhân        | `7 * 3`  | `21`       |
| `/`     | Chia thực   | `7 / 3`  | `2.333...` |
| `//`    | Chia nguyên | `7 // 3` | `2`        |
| `%`     | Chia lấy dư | `7 % 3`  | `1`        |
| `**`    | Lũy thừa    | `2 ** 3` | `8`        |

---

## 2. Phép chia `/`

Toán tử `/` dùng để chia và cho kết quả dạng số thực.

### Ví dụ

```python
print(10 / 2)
print(7 / 2)
```

Kết quả:

```text
5.0
3.5
```

---

## 3. Phép chia nguyên `//`

Toán tử `//` dùng để lấy phần nguyên của thương.

### Ví dụ

```python
print(7 // 2)
print(10 // 3)
```

Kết quả:

```text
3
3
```

---

## 4. Phép chia lấy dư `%`

Toán tử `%` dùng để lấy phần dư của phép chia.

### Ví dụ

```python
print(7 % 2)
print(10 % 3)
```

Kết quả:

```text
1
1
```

### Ứng dụng thường gặp

* Kiểm tra số chẵn, số lẻ.
* Tách chữ số cuối cùng của một số.
* Chia nhóm hoặc đổi đơn vị.

---

## 5. Phép lũy thừa `**`

Trong Python, lũy thừa dùng toán tử `**`.

### Ví dụ

```python
print(2 ** 3)
print(5 ** 2)
```

Kết quả:

```text
8
25
```

---

## 6. Thứ tự ưu tiên phép toán

Khi một biểu thức có nhiều phép toán, Python sẽ tính theo thứ tự ưu tiên sau:

1. Ngoặc `()`
2. Lũy thừa `**`
3. Nhân, chia, chia nguyên, chia dư: `*`, `/`, `//`, `%`
4. Cộng, trừ: `+`, `-`

---

### Ví dụ 1

```python
print(2 + 3 * 4)
```

Kết quả:

```text
14
```

Giải thích:

* Tính `3 * 4 = 12`
* Sau đó tính `2 + 12 = 14`

---

### Ví dụ 2

```python
print((2 + 3) * 4)
```

Kết quả:

```text
20
```

Giải thích:

* Tính trong ngoặc trước: `2 + 3 = 5`
* Sau đó tính `5 * 4 = 20`

---

## 7. Nên dùng ngoặc để công thức rõ ràng

Ngay cả khi Python có quy tắc ưu tiên, ta vẫn nên dùng dấu ngoặc để:

* Công thức dễ đọc hơn.
* Tránh hiểu sai.
* Giảm lỗi khi viết chương trình.

### Ví dụ

Công thức:

[
P = 2(a+b)
]

Nên viết:

```python
p = 2 * (a + b)
```

Không nên viết:

```python
p = 2 * a + b
```

Vì hai biểu thức này cho kết quả khác nhau.

---

# III. Ví dụ minh họa

## 1. Tính chu vi hình chữ nhật

### Bài toán

Nhập chiều dài `a` và chiều rộng `b`.
Tính chu vi hình chữ nhật:

[
P = 2(a+b)
]

### Phân tích

* **Input**: `a`, `b`
* **Xử lý**: `p = 2 * (a + b)`
* **Output**: Chu vi `p`

### Code

```python
a = int(input())
b = int(input())

p = 2 * (a + b)

print(p)
```

### Ví dụ

Input:

```text
5
3
```

Output:

```text
16
```

---

## 2. Chia nguyên và chia dư

### Bài toán

Nhập hai số nguyên `a`, `b`.
In ra:

* Thương nguyên của `a` chia `b`
* Số dư của `a` chia `b`

### Code

```python
a = int(input())
b = int(input())

print(a // b)
print(a % b)
```

### Ví dụ

Input:

```text
17
5
```

Output:

```text
3
2
```

Giải thích:

[
17 = 5 \times 3 + 2
]

---

## 3. Tính bình phương tổng

### Bài toán

Nhập hai số nguyên `a`, `b`.
Tính:

[
(a+b)^2
]

### Code

```python
a = int(input())
b = int(input())

result = (a + b) ** 2

print(result)
```

### Ví dụ

Input:

```text
2
3
```

Output:

```text
25
```

---

# IV. Bài tập vận dụng

## Bài 1. Tính tổng, hiệu, tích hai số

Nhập hai số nguyên `a`, `b`.
In lần lượt:

* Tổng của hai số
* Hiệu của hai số
* Tích của hai số

---

## Bài 2. Tính (a^2 + b^2)

Nhập hai số nguyên `a`, `b`.
Tính và in ra:

[
a^2 + b^2
]

---

## Bài 3. Tính ((a+b)^2)

Nhập hai số nguyên `a`, `b`.
Tính và in ra:

[
(a+b)^2
]

---

# V. Bài tập về nhà

## Bài 1. Tính biểu thức

Nhập hai số nguyên `a`, `b`.
Tính:

[
P = a^2 + 2ab + b^2
]

---

## Bài 2. Đổi phút sang giây

Nhập số phút `m`.
Tính số giây tương ứng.

### Gợi ý

[
\text{Số giây} = m \times 60
]

---

## Bài 3. Tính diện tích hình vuông

Nhập cạnh hình vuông `a`.
Tính diện tích:

[
S = a^2
]

---

# VI. Lỗi học sinh thường gặp

## 1. Dùng `^` thay vì `**`

Trong Python:

* `**` mới là phép lũy thừa.
* `^` không dùng để tính lũy thừa.

### Sai

```python
x = 2 ^ 3
print(x)
```

### Đúng

```python
x = 2 ** 3
print(x)
```

---

## 2. Nhầm `/` và `//`

### Ví dụ

```python
print(7 / 2)
print(7 // 2)
```

Kết quả:

```text
3.5
3
```

Cần phân biệt:

* `/`: Chia thực
* `//`: Chia nguyên

---

## 3. Thiếu ngoặc trong công thức

### Ví dụ sai

Cần tính:

[
2(a+b)
]

Nhưng viết:

```python
p = 2 * a + b
```

Công thức trên thực chất là:

[
2a + b
]

### Đúng

```python
p = 2 * (a + b)
```

---

# VII. Đề thi thật và bài chuẩn nhập môn

## Đề 1. Tính chu vi hình chữ nhật

Nhập chiều dài và chiều rộng.
In ra chu vi hình chữ nhật.

---

## Đề 2. Tính bình phương tổng

Nhập hai số nguyên `a`, `b`.
In ra giá trị:

[
(a+b)^2
]

---

## Đề 3. Tìm thương và dư của phép chia

Nhập hai số nguyên dương `a`, `b`.
In ra:

* Thương nguyên của `a` chia `b`
* Số dư của `a` chia `b`

---

# VIII. Ghi nhớ cuối bài

* Nắm chắc các toán tử:

  * `+`, `-`, `*`, `/`
  * `//`, `%`, `**`
* Phân biệt:

  * Chia thực `/`
  * Chia nguyên `//`
  * Chia lấy dư `%`
* Lũy thừa trong Python dùng `**`, không dùng `^`.
* Khi viết công thức có nhiều phép toán, nên thêm ngoặc để tránh sai.

---

# IX. Tóm tắt bài học

Muốn code công thức đúng, trước hết phải:

* Hiểu ý nghĩa từng phép toán.
* Nắm thứ tự ưu tiên.
* Viết biểu thức toán học rõ ràng.
* Dùng dấu ngoặc khi cần thiết.

Một biểu thức Python đúng sẽ giúp chương trình cho ra kết quả chính xác.
