# Bài 31. Mảng đếm, tần suất và Dictionary

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu khái niệm **tần suất xuất hiện** của một giá trị.
- Biết dùng **mảng đếm** khi miền giá trị nhỏ.
- Biết dùng **dictionary** khi dữ liệu lớn, có số âm hoặc không liên tục.
- Phân biệt được bài toán cần lưu thứ tự với bài toán chỉ cần thống kê.

## 2. Về kỹ năng

- Đếm số lần xuất hiện của từng phần tử.
- Đếm số lượng giá trị khác nhau.
- Tìm phần tử xuất hiện nhiều nhất.
- Đếm tần suất ký tự trong xâu.

## 3. Về tư duy

- Khi đề hỏi “xuất hiện bao nhiêu lần”, cần nghĩ ngay đến bảng tần suất.
- Biết chọn cấu trúc dữ liệu phù hợp với giới hạn đề.

---

# II. Lý thuyết

## 1. Tần suất là gì?

Tần suất của một giá trị là số lần giá trị đó xuất hiện trong dãy hoặc xâu.

Ví dụ với dãy:

`2 5 2 7 5 2`

Ta có:

- `2` xuất hiện `3` lần.
- `5` xuất hiện `2` lần.
- `7` xuất hiện `1` lần.

## 2. Mảng đếm

Nếu các phần tử là số nguyên không âm và không vượt quá một giới hạn nhỏ, ta có thể dùng mảng đếm.

Ví dụ nếu $0 \le a_i \le 100$, ta tạo:

```python
count = [0] * 101
```

Khi gặp giá trị `x`, cập nhật:

```python
count[x] += 1
```

## 3. Dictionary

Nếu giá trị có thể:

- Rất lớn.
- Âm.
- Là xâu.
- Không liên tục.

ta nên dùng dictionary.

Mẫu đếm phổ biến:

```python
freq = {}

for x in a:
    freq[x] = freq.get(x, 0) + 1
```

## 4. Đếm số lượng giá trị khác nhau

Khi dùng dictionary:

```python
len(freq)
```

chính là số lượng giá trị khác nhau.

## 5. Tìm phần tử xuất hiện nhiều nhất

Ta duyệt bảng tần suất và chọn phần tử có số lần xuất hiện lớn nhất.

Nếu đề yêu cầu khi hòa chọn giá trị nhỏ nhất, ta xử lý thêm điều kiện phụ.

---

# III. Ví dụ minh họa

## Ví dụ 1. Đếm tần suất bằng mảng đếm

### Đề bài

Cho dãy số nguyên không âm, mỗi phần tử không vượt quá `100`.  
In ra các giá trị xuất hiện cùng số lần của chúng.

### Code Python

```python
n = int(input())
a = list(map(int, input().split()))

count = [0] * 101

for x in a:
    count[x] += 1

for value in range(101):
    if count[value] > 0:
        print(value, count[value])
```

---

## Ví dụ 2. Đếm số giá trị khác nhau bằng dictionary

### Code Python

```python
n = int(input())
a = list(map(int, input().split()))

freq = {}

for x in a:
    freq[x] = freq.get(x, 0) + 1

print(len(freq))
```

---

## Ví dụ 3. Tìm giá trị xuất hiện nhiều nhất

### Code Python

```python
n = int(input())
a = list(map(int, input().split()))

freq = {}

for x in a:
    freq[x] = freq.get(x, 0) + 1

best_value = None
best_count = -1

for value, count in freq.items():
    if count > best_count:
        best_value = value
        best_count = count
    elif count == best_count and value < best_value:
        best_value = value

print(best_value)
print(best_count)
```

---

## Ví dụ 4. Tần suất ký tự trong xâu

```python
s = input().strip()

count = [0] * 26

for ch in s:
    count[ord(ch) - ord('a')] += 1

for i in range(26):
    if count[i] > 0:
        print(chr(ord('a') + i), count[i])
```

---

# IV. Bài tập vận dụng

## Bài 1. Đếm số lần xuất hiện của X

Cho dãy $N$ số nguyên và số $X$.  
Hãy đếm số lần $X$ xuất hiện.

## Bài 2. Đếm số lượng giá trị khác nhau

Cho dãy $N$ số nguyên.  
Tính có bao nhiêu giá trị khác nhau.

## Bài 3. Phần tử xuất hiện đúng một lần

Liệt kê các giá trị xuất hiện đúng một lần.

## Bài 4. Tìm giá trị xuất hiện nhiều nhất

Nếu có nhiều đáp án, chọn giá trị nhỏ nhất.

## Bài 5. Đếm ký tự chữ số

Cho một xâu gồm chữ cái và chữ số.  
Đếm có bao nhiêu ký tự là chữ số.

---

# V. Bài tập về nhà

## Bài 1. Xóa trùng giữ nguyên thứ tự đầu tiên

Cho dãy số nguyên.  
In ra các giá trị khác nhau theo thứ tự xuất hiện đầu tiên.

## Bài 2. Từ xuất hiện nhiều nhất

Cho một dòng văn bản.  
Tìm từ xuất hiện nhiều lần nhất.

## Bài 3. So sánh hai xâu theo tần suất

Kiểm tra hai xâu chữ thường có cùng số lượng từng ký tự hay không.

## Bài 4. Ký tự không xuất hiện

Cho xâu chữ thường.  
Liệt kê các chữ cái từ `a` đến `z` không xuất hiện.

---

# VI. Lỗi học sinh thường gặp

- Dùng mảng đếm khi miền giá trị quá lớn.
- Quên xử lý số âm nếu dùng chỉ số mảng.
- Nhầm số lượng phần tử với số lượng giá trị khác nhau.
- Không đọc kỹ quy tắc khi có nhiều đáp án cùng tần suất.
- Quên dùng `get(x, 0)` khi tăng tần suất trong dictionary.

---

# VII. Đề thi thật và bài chuẩn chuyên

## Đề 1. Thống kê dãy số

Cho dãy $N$ số nguyên.  
Hãy:

1. Đếm số lượng giá trị khác nhau.
2. Tìm số lần lặp lớn nhất của một giá trị.

## Đề 2. Ký tự xuất hiện nhiều nhất

Cho xâu độ dài lớn.  
Tìm ký tự xuất hiện nhiều nhất và số lần xuất hiện.

## Đề 3. Giao của hai dãy

Cho hai dãy số nguyên.  
Đếm bao nhiêu giá trị xuất hiện trong cả hai dãy.

---

# VIII. Ghi nhớ cuối bài

- Tần suất giúp biến dữ liệu thô thành thông tin thống kê.
- Mảng đếm nhanh nhưng cần miền giá trị nhỏ.
- Dictionary linh hoạt hơn cho dữ liệu tổng quát.
- Đây là nền tảng cho counting sort, sliding window và nhiều bài xử lý xâu.

---

# IX. Tóm tắt bài học

## Mẫu code quan trọng

```python
freq = {}

for x in a:
    freq[x] = freq.get(x, 0) + 1
```

Khi cần đếm, hãy nghĩ đến **tần suất** trước tiên.
