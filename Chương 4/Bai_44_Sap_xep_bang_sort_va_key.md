# Bài 44. Sử dụng sort trong Python và sắp xếp theo khóa

---

# I. Mục tiêu bài học

Sau bài học này, học sinh cần đạt được các yêu cầu sau:

## 1. Về kiến thức

- Biết sử dụng:
  - `list.sort()`
  - `sorted()`
- Phân biệt:
  - Sắp xếp tại chỗ.
  - Tạo danh sách mới.
- Biết sắp xếp:
  - Tăng dần.
  - Giảm dần.
  - Theo khóa `key`.
- Hiểu ứng dụng của sắp xếp tuple và nhiều tiêu chí.

## 2. Về kỹ năng

- Sắp xếp danh sách số.
- Sắp xếp xâu.
- Sắp xếp tuple hoặc danh sách cặp.
- Sắp xếp theo:
  - Giá trị tuyệt đối.
  - Độ dài xâu.
  - Điểm giảm dần, tên tăng dần.

## 3. Về tư duy

- Không tự viết sort thủ công khi đề không yêu cầu.
- Biết chọn khóa sắp xếp phù hợp với yêu cầu đề.
- Làm quen với việc biểu diễn dữ liệu nhiều thuộc tính.

---

# II. Lý thuyết

## 1. Hàm sort và sorted

### 1.1. `list.sort()`

Sắp xếp trực tiếp trên danh sách ban đầu.

```python
a.sort()
```

---

### 1.2. `sorted()`

Tạo ra danh sách mới đã sắp xếp.

```python
b = sorted(a)
```

---

## 2. Sắp xếp tăng dần

Mặc định Python sắp xếp tăng dần.

```python
a.sort()
```

---

## 3. Sắp xếp giảm dần

Dùng:

```python
a.sort(reverse=True)
```

---

## 4. Sắp xếp theo khóa

Cú pháp:

```python
a.sort(key=...)
```

Hàm `key` trả về giá trị dùng để so sánh.

---

## 5. Ví dụ sắp xếp theo trị tuyệt đối

Dãy:

`-7 2 -3 5`

Sắp xếp theo trị tuyệt đối:

`2 -3 5 -7`

Dùng:

```python
a.sort(key=abs)
```

---

## 6. Sắp xếp xâu theo độ dài

```python
words.sort(key=len)
```

---

## 7. Sắp xếp tuple

Nếu danh sách gồm các tuple:

```python
items = [(2, 5), (1, 9), (2, 3)]
items.sort()
```

Python so sánh:

1. Thành phần thứ nhất.
2. Nếu bằng nhau, xét thành phần thứ hai.

Kết quả:

`(1, 9), (2, 3), (2, 5)`

---

## 8. Sắp xếp theo nhiều tiêu chí

Ví dụ danh sách học sinh:

- Điểm giảm dần.
- Nếu bằng điểm thì tên tăng dần.

Ta dùng khóa:

```python
students.sort(key=lambda x: (-x[1], x[0]))
```

---

# III. Ví dụ minh họa

---

## Ví dụ 1. Sắp xếp tăng dần

### 1. Code Python

```python
n = int(input())
a = list(map(int, input().split()))

a.sort()

print(*a)
```

---

## Ví dụ 2. Sắp xếp giảm dần

```python
n = int(input())
a = list(map(int, input().split()))

a.sort(reverse=True)

print(*a)
```

---

## Ví dụ 3. Sắp xếp theo trị tuyệt đối

```python
n = int(input())
a = list(map(int, input().split()))

a.sort(key=abs)

print(*a)
```

---

## Ví dụ 4. Sắp xếp xâu theo độ dài

```python
n = int(input())
words = []

for _ in range(n):
    words.append(input().strip())

words.sort(key=len)

for word in words:
    print(word)
```

---

## Ví dụ 5. Sắp xếp cặp số

### 1. Đề bài

Cho $N$ cặp số $(x, y)$.  
Sắp xếp theo:

1. $x$ tăng dần.
2. Nếu $x$ bằng nhau, $y$ tăng dần.

---

### 2. Code Python

```python
n = int(input())
pairs = []

for _ in range(n):
    x, y = map(int, input().split())
    pairs.append((x, y))

pairs.sort()

for x, y in pairs:
    print(x, y)
```

---

## Ví dụ 6. Sắp xếp học sinh

### 1. Đề bài

Mỗi học sinh có:

- Tên.
- Điểm.

Sắp xếp theo:

1. Điểm giảm dần.
2. Nếu bằng điểm, tên tăng dần.

---

### 2. Code Python

```python
n = int(input())
students = []

for _ in range(n):
    name = input().strip()
    score = float(input())
    students.append((name, score))

students.sort(key=lambda x: (-x[1], x[0]))

for name, score in students:
    print(name, score)
```

---

# IV. Bài tập vận dụng

---

## Bài 1. Sắp xếp dãy tăng dần

Dùng `sort()` để sắp xếp dãy số.

---

## Bài 2. Sắp xếp dãy giảm dần

Dùng `reverse=True`.

---

## Bài 3. Sắp xếp theo trị tuyệt đối

Cho dãy số nguyên.  
Sắp xếp theo giá trị tuyệt đối tăng dần.

---

## Bài 4. Sắp xếp từ theo độ dài

Cho danh sách từ.  
Sắp xếp theo độ dài tăng dần.

---

## Bài 5. Sắp xếp cặp tọa độ

Cho các điểm $(x, y)$.  
Sắp xếp theo $x$ tăng dần, sau đó $y$ tăng dần.

---

## Bài 6. Sắp xếp theo tổng chữ số

Cho dãy số nguyên không âm.  
Sắp xếp theo tổng chữ số tăng dần.

---

# V. Bài tập về nhà

---

## Bài 1. Sắp xếp số chẵn trước, số lẻ sau

Trong mỗi nhóm, sắp xếp tăng dần.

---

## Bài 2. Sắp xếp học sinh

Danh sách học sinh gồm:

- Họ tên.
- Điểm.

Sắp xếp theo điểm giảm dần, nếu bằng điểm thì tên tăng dần.

---

## Bài 3. Sắp xếp phân số

Cho các phân số $\frac{a}{b}$.  
Sắp xếp theo giá trị tăng dần mà không dùng số thực.

---

## Bài 4. Sắp xếp chuỗi theo chữ cái cuối

Cho danh sách xâu.  
Sắp xếp theo ký tự cuối cùng.

---

## Bài 5. Sắp xếp theo khoảng cách đến 0

Cho dãy số nguyên.  
Sắp xếp theo trị tuyệt đối tăng dần, nếu bằng nhau thì số nhỏ hơn đứng trước.

---

# VI. Lỗi học sinh thường gặp

---

## 1. Nhầm `sort()` trả về danh sách mới

`a.sort()` thay đổi chính `a` và trả về `None`.

---

## 2. Dùng `sorted()` nhưng quên gán lại

```python
sorted(a)
```

không làm thay đổi `a`.

---

## 3. Key chưa đúng quy tắc đề bài

Cần kiểm tra kỹ thứ tự ưu tiên.

---

## 4. Sắp xếp điểm giảm dần nhưng tên cũng bị đảo chiều

Nếu dùng `reverse=True` cho cả tuple, mọi tiêu chí đều đảo.

Khi có nhiều tiêu chí, nên dùng `key`.

---

## 5. Dùng số thực để sắp xếp phân số

Có thể gây sai số.  
Nên so sánh chéo.

---

# VII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Danh sách học sinh

Sắp xếp học sinh theo tên hoặc điểm theo quy tắc đề bài.

---

## Đề 2. Ghép số lớn nhất

Cho các số nguyên dương.  
Sắp xếp theo quy tắc đặc biệt để ghép thành số lớn nhất.

---

## Đề 3. Khoảng cách điểm

Cho các điểm trên mặt phẳng.  
Sắp xếp theo khoảng cách tới gốc tọa độ.

---

## Đề 4. Dãy theo trị tuyệt đối

Sắp xếp dãy theo $|a_i|$, nếu bằng nhau sắp xếp theo giá trị tăng dần.

---

# VIII. Ghi nhớ cuối bài

- `sort()` thay đổi danh sách gốc.
- `sorted()` tạo danh sách mới.
- `reverse=True` dùng cho giảm dần đơn giản.
- `key` rất quan trọng cho sắp xếp theo yêu cầu đặc biệt.

---

# IX. Tóm tắt bài học

## Bài 44. sort và key

```python
a.sort()
a.sort(reverse=True)
a.sort(key=abs)
students.sort(key=lambda x: (-x[1], x[0]))
```

Đây là kỹ năng rất quan trọng khi giải bài thi thực tế.
