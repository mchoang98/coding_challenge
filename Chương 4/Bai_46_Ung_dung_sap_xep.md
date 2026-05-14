# Bài 46. Ứng dụng sắp xếp trong đếm, ghép cặp và thống kê

---

# I. Mục tiêu bài học

Sau bài học này, học sinh cần đạt được các yêu cầu sau:

## 1. Về kiến thức

- Hiểu rằng sắp xếp không chỉ để “xếp lại dãy”.
- Biết các ứng dụng quan trọng:
  - Đếm giá trị khác nhau.
  - Tìm tần suất lớn nhất.
  - Ghép cặp tối ưu.
  - Tìm trung vị.
  - Trộn hoặc so sánh các dãy đã có thứ tự.

## 2. Về kỹ năng

- Đếm số giá trị khác nhau sau khi sắp xếp.
- Tìm tần suất xuất hiện lớn nhất bằng duyệt dãy đã sắp.
- Ghép cặp theo quy tắc sau khi sắp xếp.
- Dùng sắp xếp để giải các bài toán đơn giản hiệu quả hơn.

## 3. Về tư duy

- Biết nghĩ đến sắp xếp khi:
  - Cần gom các phần tử bằng nhau.
  - Cần xét các cặp gần nhau.
  - Cần khai thác thứ tự.
- Chuẩn bị cho:
  - Two pointers.
  - Greedy.
  - Binary search.

---

# II. Lý thuyết

## 1. Đếm giá trị khác nhau sau khi sắp xếp

Sau khi sắp xếp, các phần tử bằng nhau đứng cạnh nhau.

Ta chỉ cần:

- Đếm phần tử đầu tiên.
- Mỗi khi `a[i] != a[i-1]`, tăng kết quả.

---

## 2. Tìm tần suất lớn nhất

Sau khi sắp xếp, mỗi nhóm giá trị bằng nhau là một đoạn liên tiếp.

Ta duyệt dãy và đếm độ dài từng nhóm.

---

## 3. Tìm trung vị

Sau khi sắp xếp:

- Nếu $N$ lẻ, trung vị là phần tử giữa.
- Nếu $N$ chẵn, tùy đề bài có thể dùng hai phần tử giữa.

---

## 4. Ghép cặp tối ưu cơ bản

Trong nhiều bài toán, sau khi sắp xếp, việc ghép:

- Nhỏ với lớn.
- Nhỏ với nhỏ.
- Lớn với lớn.

có thể cho lời giải tối ưu.

---

## 5. Vì sao sắp xếp giúp bài toán dễ hơn?

Trước khi sắp xếp:

- Các giá trị nằm rải rác.

Sau khi sắp xếp:

- Giá trị giống nhau gom lại.
- Quan hệ lớn nhỏ rõ ràng.
- Dễ dùng hai con trỏ.

---

# III. Ví dụ minh họa

---

## Ví dụ 1. Đếm số giá trị khác nhau

### 1. Code Python

```python
n = int(input())
a = list(map(int, input().split()))

a.sort()

count = 1

for i in range(1, n):
    if a[i] != a[i - 1]:
        count += 1

print(count)
```

---

## Ví dụ 2. Tần suất lớn nhất

```python
n = int(input())
a = list(map(int, input().split()))

a.sort()

best = 1
current = 1

for i in range(1, n):
    if a[i] == a[i - 1]:
        current += 1
    else:
        current = 1

    if current > best:
        best = current

print(best)
```

---

## Ví dụ 3. Tìm trung vị

```python
n = int(input())
a = list(map(int, input().split()))

a.sort()

median = a[n // 2]

print(median)
```

---

## Ví dụ 4. Ghép hai dãy để tổng chênh lệch nhỏ

### 1. Đề bài

Cho hai dãy cùng $N$ phần tử.  
Ghép mỗi phần tử dãy thứ nhất với một phần tử dãy thứ hai sao cho tổng các độ lệch tuyệt đối nhỏ.

---

### 2. Ý tưởng

Sắp xếp cả hai dãy tăng dần, sau đó ghép cùng vị trí.

---

### 3. Code Python

```python
n = int(input())
a = list(map(int, input().split()))
b = list(map(int, input().split()))

a.sort()
b.sort()

total = 0

for i in range(n):
    total += abs(a[i] - b[i])

print(total)
```

---

# IV. Bài tập vận dụng

---

## Bài 1. Đếm giá trị khác nhau

Cho dãy số nguyên.  
Sắp xếp rồi đếm số giá trị khác nhau.

---

## Bài 2. Tần suất lớn nhất

Cho dãy số nguyên.  
Tìm số lần xuất hiện lớn nhất của một giá trị.

---

## Bài 3. Giá trị xuất hiện nhiều nhất

Sau khi sắp xếp, tìm giá trị có tần suất lớn nhất.

Nếu hòa, chọn giá trị nhỏ nhất.

---

## Bài 4. Trung vị của dãy

Cho dãy có số phần tử lẻ.  
Tìm trung vị.

---

## Bài 5. Ghép cặp nhỏ nhất

Cho hai dãy cùng độ dài.  
Ghép để tổng chênh lệch tuyệt đối nhỏ nhất.

---

## Bài 6. Khoảng cách nhỏ nhất giữa hai phần tử

Cho dãy số.  
Tìm hiệu nhỏ nhất giữa hai phần tử khác nhau.

---

# V. Bài tập về nhà

---

## Bài 1. Khoảng cách lớn nhất giữa hai giá trị liên tiếp sau sắp xếp

---

## Bài 2. Số đứng thứ K

Cho dãy số.  
Tìm số đứng thứ $K$ nếu dãy được sắp tăng.

---

## Bài 3. Tổng khoảng cách đến một điểm tối ưu

Cho dãy số.  
Tìm giá trị $X$ sao cho tổng $|a_i - X|$ nhỏ nhất.

---

## Bài 4. Đoạn phủ trục số

Cho các đoạn trên trục số.  
Sắp xếp để tính tổng độ dài phần được phủ.

---

## Bài 5. Ghép đội hình

Cho danh sách chiều cao của hai đội.  
Ghép cặp để tổng chênh lệch nhỏ nhất.

---

# VI. Lỗi học sinh thường gặp

---

## 1. Đếm giá trị khác nhau nhưng quên sắp xếp trước

Nếu dùng cách duyệt láng giềng, bắt buộc phải sắp xếp.

---

## 2. Không xử lý n = 0 hoặc n = 1 khi cần

Một số đề có thể có dãy rất nhỏ.

---

## 3. Nhầm trung vị với trung bình cộng

Hai khái niệm khác nhau.

---

## 4. Ghép sai quy tắc khi sắp xếp

Cần hiểu lý do chọn ghép tương ứng, không làm theo máy móc.

---

## 5. Không tận dụng việc các phần tử giống nhau đã đứng cạnh nhau

---

# VII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Thống kê dãy

Đếm số giá trị khác nhau và tần suất lớn nhất.

---

## Đề 2. Giá trị gần nhau nhất

Cho dãy số.  
Tìm hai phần tử có hiệu tuyệt đối nhỏ nhất.

---

## Đề 3. Ghép đội

Ghép hai dãy sau sắp xếp để tối ưu tổng chênh lệch.

---

## Đề 4. Trung vị tối ưu

Tìm điểm trên trục số làm nhỏ tổng khoảng cách Manhattan một chiều.

---

# VIII. Ghi nhớ cuối bài

- Sắp xếp giúp “gom nhóm” dữ liệu.
- Nhiều bài thống kê trở nên đơn giản sau khi sắp xếp.
- Đây là cầu nối quan trọng tới:
  - Binary search.
  - Two pointers.
  - Greedy.

---

# IX. Tóm tắt bài học

## Bài 46. Ứng dụng sắp xếp

Các dạng phổ biến:

- Đếm nhóm.
- Tần suất lớn nhất.
- Trung vị.
- Ghép cặp tối ưu.
- Khoảng cách nhỏ nhất.
