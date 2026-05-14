# Bài 43. Sắp xếp cơ bản: Bubble Sort, Selection Sort và Insertion Sort

---

# I. Mục tiêu bài học

Sau bài học này, học sinh cần đạt được các yêu cầu sau:

## 1. Về kiến thức

- Hiểu khái niệm **sắp xếp** trong lập trình.
- Biết vì sao sắp xếp là một kỹ thuật nền tảng.
- Nắm được ý tưởng của ba thuật toán:
  - Bubble Sort.
  - Selection Sort.
  - Insertion Sort.
- Biết độ phức tạp cơ bản của các thuật toán trên là $O(N^2)$.
- Hiểu khi nào nên dùng để học tư duy, khi nào nên dùng hàm sắp xếp có sẵn.

## 2. Về kỹ năng

- Cài đặt được ba thuật toán sắp xếp cơ bản bằng Python.
- Mô phỏng được quá trình đổi chỗ phần tử.
- So sánh được cách hoạt động của các thuật toán.
- Sắp xếp được dãy theo thứ tự:
  - Tăng dần.
  - Giảm dần.

## 3. Về tư duy

- Hiểu rằng nhiều thuật toán khác nhau có thể cùng giải một bài toán.
- Biết phân tích số vòng lặp và ước lượng độ phức tạp.
- Tạo nền cho:
  - Quick Sort.
  - Sắp xếp theo khóa.
  - Ứng dụng sắp xếp trong giải bài.

---

# II. Lý thuyết

## 1. Sắp xếp là gì?

Sắp xếp là quá trình đưa các phần tử về một trật tự nhất định.

Ví dụ:

Dãy ban đầu:

`5 2 8 1 4`

Sau khi sắp xếp tăng dần:

`1 2 4 5 8`

---

## 2. Vì sao cần sắp xếp?

Sắp xếp giúp:

- Tìm kiếm nhanh hơn.
- Dễ đếm tần suất.
- Dễ loại phần tử trùng.
- Dễ ghép cặp.
- Là bước chuẩn bị cho:
  - Binary Search.
  - Two Pointers.
  - Greedy.

---

## 3. Bubble Sort

### 3.1. Ý tưởng

Bubble Sort liên tục đổi chỗ hai phần tử kề nhau nếu chúng đang sai thứ tự.

Sau mỗi lượt:

- Phần tử lớn nhất còn lại sẽ “nổi” dần về cuối dãy.

---

### 3.2. Ví dụ

Dãy:

`5 2 4 1`

Lượt 1:

- So `5` và `2`, đổi chỗ → `2 5 4 1`
- So `5` và `4`, đổi chỗ → `2 4 5 1`
- So `5` và `1`, đổi chỗ → `2 4 1 5`

Sau lượt đầu, `5` đã về cuối.

---

### 3.3. Độ phức tạp

Có hai vòng lặp lồng nhau.

Độ phức tạp:

$O(N^2)$

---

## 4. Selection Sort

### 4.1. Ý tưởng

Ở mỗi vị trí `i`:

1. Tìm phần tử nhỏ nhất trong đoạn chưa sắp xếp.
2. Đưa phần tử đó về vị trí `i`.

---

### 4.2. Ví dụ

Dãy:

`5 2 4 1`

- Vị trí 0: nhỏ nhất là `1`, đổi với `5` → `1 2 4 5`
- Vị trí 1: nhỏ nhất của đoạn còn lại là `2`, giữ nguyên.
- Vị trí 2: nhỏ nhất còn lại là `4`, giữ nguyên.

---

### 4.3. Độ phức tạp

Độ phức tạp:

$O(N^2)$

---

## 5. Insertion Sort

### 5.1. Ý tưởng

Insertion Sort xây dựng dãy đã sắp xếp từ trái sang phải.

Mỗi bước:

1. Lấy phần tử hiện tại.
2. Chèn nó vào đúng vị trí trong phần bên trái đã sắp xếp.

---

### 5.2. Ví dụ

Dãy:

`5 2 4 1`

- Bắt đầu: `5`
- Chèn `2` vào trước `5` → `2 5`
- Chèn `4` vào giữa → `2 4 5`
- Chèn `1` vào đầu → `1 2 4 5`

---

### 5.3. Độ phức tạp

Trường hợp xấu nhất:

$O(N^2)$

Nếu dãy gần như đã sắp xếp, Insertion Sort thường hoạt động tốt hơn hai cách còn lại.

---

## 6. So sánh ba thuật toán

| Thuật toán | Ý tưởng chính | Độ phức tạp |
|---|---|---|
| Bubble Sort | Đổi cặp kề nhau | $O(N^2)$ |
| Selection Sort | Chọn nhỏ nhất từng lượt | $O(N^2)$ |
| Insertion Sort | Chèn vào vị trí đúng | $O(N^2)$ |

---

# III. Ví dụ minh họa

---

## Ví dụ 1. Bubble Sort tăng dần

### 1. Đề bài

Cho dãy $N$ số nguyên.  
Hãy sắp xếp dãy theo thứ tự tăng dần bằng Bubble Sort.

---

### 2. Code Python

```python
n = int(input())
a = list(map(int, input().split()))

for i in range(n - 1):
    for j in range(0, n - 1 - i):
        if a[j] > a[j + 1]:
            a[j], a[j + 1] = a[j + 1], a[j]

print(*a)
```

---

### 3. Input

```text
5
5 2 8 1 4
```

### 4. Output

```text
1 2 4 5 8
```

---

## Ví dụ 2. Selection Sort tăng dần

### 1. Code Python

```python
n = int(input())
a = list(map(int, input().split()))

for i in range(n - 1):
    min_pos = i

    for j in range(i + 1, n):
        if a[j] < a[min_pos]:
            min_pos = j

    a[i], a[min_pos] = a[min_pos], a[i]

print(*a)
```

---

## Ví dụ 3. Insertion Sort tăng dần

### 1. Code Python

```python
n = int(input())
a = list(map(int, input().split()))

for i in range(1, n):
    value = a[i]
    j = i - 1

    while j >= 0 and a[j] > value:
        a[j + 1] = a[j]
        j -= 1

    a[j + 1] = value

print(*a)
```

---

## Ví dụ 4. Sắp xếp giảm dần

### 1. Code Bubble Sort giảm dần

```python
n = int(input())
a = list(map(int, input().split()))

for i in range(n - 1):
    for j in range(0, n - 1 - i):
        if a[j] < a[j + 1]:
            a[j], a[j + 1] = a[j + 1], a[j]

print(*a)
```

---

# IV. Bài tập vận dụng

---

## Bài 1. Bubble Sort

Cho dãy số nguyên.  
Sắp xếp tăng dần bằng Bubble Sort.

---

## Bài 2. Selection Sort

Cho dãy số nguyên.  
Sắp xếp tăng dần bằng Selection Sort.

---

## Bài 3. Insertion Sort

Cho dãy số nguyên.  
Sắp xếp tăng dần bằng Insertion Sort.

---

## Bài 4. Sắp xếp giảm dần

Cho dãy số nguyên.  
Sắp xếp dãy theo thứ tự giảm dần bằng một trong ba thuật toán đã học.

---

## Bài 5. Đếm số lần đổi chỗ của Bubble Sort

Cho dãy số nguyên.  
Trong quá trình Bubble Sort tăng dần, đếm số lần đổi chỗ.

---

## Bài 6. Kiểm tra dãy đã sắp xếp chưa

Cho dãy số nguyên.  
Kiểm tra dãy có đang tăng không giảm hay không.

---

# V. Bài tập về nhà

---

## Bài 1. Sắp xếp số chẵn tăng dần

Cho dãy số nguyên.  
Đưa các số chẵn ra trước và sắp xếp chúng tăng dần.

---

## Bài 2. Sắp xếp theo trị tuyệt đối

Cho dãy số nguyên.  
Sắp xếp tăng dần theo giá trị tuyệt đối.

---

## Bài 3. Sắp xếp nửa đầu tăng, nửa sau giảm

Cho dãy có $N$ phần tử.  
Sắp xếp nửa đầu tăng dần và nửa sau giảm dần.

---

## Bài 4. Tìm phần tử lớn thứ K bằng sắp xếp

Cho dãy và số $K$.  
Sắp xếp rồi tìm phần tử lớn thứ $K$.

---

## Bài 5. Dãy gần tăng

Cho dãy số.  
Kiểm tra liệu có thể trở thành dãy tăng không giảm sau khi đổi chỗ đúng một cặp phần tử hay không.

---

# VI. Lỗi học sinh thường gặp

---

## 1. Sai giới hạn vòng lặp

Bubble Sort thường dùng:

```python
for j in range(0, n - 1 - i):
```

Nếu viết sai có thể truy cập vượt chỉ số.

---

## 2. Quên cập nhật vị trí nhỏ nhất trong Selection Sort

Cần cập nhật `min_pos`, không chỉ cập nhật giá trị.

---

## 3. Cập nhật sai trong Insertion Sort

Sau khi dịch chuyển, phải gán:

```python
a[j + 1] = value
```

---

## 4. Không hiểu tác dụng của từng lượt

Học sinh nên mô phỏng trên giấy với dãy nhỏ.

---

## 5. Dùng thuật toán $O(N^2)$ cho dữ liệu rất lớn

Trong thực tế, với $N$ lớn nên dùng hàm sắp xếp có sẵn hoặc thuật toán tốt hơn.

---

# VII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Giá trị nhỏ thứ K

Cho dãy số đôi một khác nhau và số $K$.  
Hãy tìm giá trị nhỏ thứ $K$ trong dãy.

Có thể bắt đầu bằng cách sắp xếp toàn bộ dãy.

---

## Đề 2. Thống kê sau sắp xếp

Cho dãy số nguyên.  
Sau khi sắp xếp, hãy đếm số lượng giá trị khác nhau.

---

## Đề 3. Học sinh xếp hạng

Cho danh sách học sinh gồm tên và điểm.  
Sắp xếp học sinh theo điểm giảm dần.

---

## Đề 4. Dãy nghịch thế

Cho dãy số.  
Đếm số cặp $(i, j)$ với $i < j$ và $a_i > a_j$ bằng cách duyệt trực tiếp.

---

# VIII. Ghi nhớ cuối bài

- Sắp xếp là kỹ thuật nền tảng.
- Ba thuật toán cơ bản:
  - Bubble Sort.
  - Selection Sort.
  - Insertion Sort.
- Cả ba đều có độ phức tạp xấu nhất là $O(N^2)$.
- Nên học để hiểu tư duy trước khi dùng công cụ mạnh hơn.

---

# IX. Tóm tắt bài học

## Bài 43. Sắp xếp cơ bản

Bubble Sort:

```python
for i in range(n - 1):
    for j in range(0, n - 1 - i):
        if a[j] > a[j + 1]:
            a[j], a[j + 1] = a[j + 1], a[j]
```

Selection Sort:

```python
for i in range(n - 1):
    min_pos = i
    for j in range(i + 1, n):
        if a[j] < a[min_pos]:
            min_pos = j
    a[i], a[min_pos] = a[min_pos], a[i]
```
