# Bài 41. Xử lý số lớn bằng xâu

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu vì sao cần biểu diễn số lớn bằng xâu.
- Biết các phép cơ bản:
  - So sánh.
  - Cộng.
  - Nhân số lớn với số nhỏ.
- Hiểu cách mô phỏng phép tính tay.

## 2. Về kỹ năng

- Chuẩn hóa số lớn.
- Cộng hai số lớn.
- Nhân số lớn với số nhỏ.
- Vận dụng để tính giai thừa hoặc Fibonacci lớn.

## 3. Về tư duy

- Biết thay đổi cách biểu diễn dữ liệu khi kiểu số thường không đủ.
- Hiểu giá trị của việc xử lý từng chữ số.

---

# II. Lý thuyết

## 1. Biểu diễn

Số lớn được lưu dưới dạng xâu:

```python
a = "12345678901234567890"
```

## 2. So sánh

- Số có nhiều chữ số hơn thì lớn hơn.
- Nếu cùng độ dài, so sánh từ trái sang phải.

## 3. Cộng hai số lớn

- Duyệt từ phải sang trái.
- Cộng hai chữ số và phần nhớ.
- Lấy phần đơn vị.
- Cập nhật nhớ.

## 4. Nhân số lớn với số nhỏ

Tương tự phép nhân tay từng chữ số.

## 5. Chuẩn hóa

- `"000123"` thành `"123"`.
- `"0000"` thành `"0"`.

---

# III. Ví dụ minh họa

## Ví dụ 1. So sánh số lớn

```python
a = input().strip().lstrip('0') or '0'
b = input().strip().lstrip('0') or '0'

if len(a) > len(b):
    print(">")
elif len(a) < len(b):
    print("<")
elif a > b:
    print(">")
elif a < b:
    print("<")
else:
    print("=")
```

---

## Ví dụ 2. Cộng hai số lớn

```python
a = input().strip()
b = input().strip()

i = len(a) - 1
j = len(b) - 1
carry = 0
result = []

while i >= 0 or j >= 0 or carry > 0:
    x = int(a[i]) if i >= 0 else 0
    y = int(b[j]) if j >= 0 else 0

    total = x + y + carry
    result.append(str(total % 10))
    carry = total // 10

    i -= 1
    j -= 1

result.reverse()
print("".join(result))
```

---

## Ví dụ 3. Nhân số lớn với số nhỏ

```python
a = input().strip()
b = int(input())

carry = 0
result = []

for i in range(len(a) - 1, -1, -1):
    total = int(a[i]) * b + carry
    result.append(str(total % 10))
    carry = total // 10

while carry > 0:
    result.append(str(carry % 10))
    carry //= 10

result.reverse()
print("".join(result).lstrip('0') or '0')
```

---

# IV. Bài tập vận dụng

## Bài 1. Chuẩn hóa số lớn

## Bài 2. So sánh hai số lớn

## Bài 3. Cộng hai số lớn

## Bài 4. Nhân số lớn với một chữ số

## Bài 5. Nhân số lớn với số nhỏ

## Bài 6. Tính giai thừa lớn

---

# V. Bài tập về nhà

## Bài 1. Trừ hai số lớn với $A \ge B$

## Bài 2. Cộng nhiều số lớn

## Bài 3. Tính Fibonacci lớn

## Bài 4. Tính $N!$ với $N \le 1000$

## Bài 5. Đếm chữ số của một số lớn

---

# VI. Lỗi học sinh thường gặp

- So sánh xâu trực tiếp khi độ dài khác nhau.
- Quên phần nhớ cuối cùng.
- Ghép kết quả sai chiều.
- Không chuẩn hóa số 0.
- Chuyển toàn bộ số lớn sang `int` thay vì xử lý xâu.

---

# VII. Đề thi thật và bài chuẩn chuyên

## Đề 1. Cộng số lớn

## Đề 2. Giai thừa lớn

## Đề 3. Fibonacci lớn

## Đề 4. So sánh hai số rất lớn

---

# VIII. Ghi nhớ cuối bài

- Số lớn cần được xử lý theo từng chữ số.
- Cộng và nhân số lớn mô phỏng phép tính tay.
- Đây là nền tảng quan trọng cho số học nâng cao.

---

# IX. Tóm tắt bài học

## Mẫu cộng số lớn

```python
while i >= 0 or j >= 0 or carry > 0:
    ...
```
