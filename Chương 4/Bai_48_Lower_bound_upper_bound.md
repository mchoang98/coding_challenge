# Bài 48. Lower Bound và Upper Bound

---

# I. Mục tiêu bài học

Sau bài học này, học sinh cần đạt được các yêu cầu sau:

## 1. Về kiến thức

- Hiểu:
  - Lower Bound.
  - Upper Bound.
- Biết cách tìm:
  - Vị trí đầu tiên có giá trị không nhỏ hơn $X$.
  - Vị trí đầu tiên có giá trị lớn hơn $X$.
- Hiểu ứng dụng:
  - Đếm số lần xuất hiện của $X$.
  - Tìm đoạn các phần tử bằng $X$.
  - Đếm số phần tử trong một khoảng giá trị.

## 2. Về kỹ năng

- Tự cài đặt lower bound.
- Tự cài đặt upper bound.
- Dùng `bisect_left`, `bisect_right` trong Python.
- Áp dụng để giải các bài toán đếm nhanh.

## 3. Về tư duy

- Chuyển từ “tìm đúng $X$” sang “tìm ranh giới”.
- Hiểu binary search không chỉ để kiểm tra tồn tại.

---

# II. Lý thuyết

## 1. Lower Bound là gì?

Lower Bound của $X$ là vị trí đầu tiên có giá trị:

$\ge X$

---

## 2. Upper Bound là gì?

Upper Bound của $X$ là vị trí đầu tiên có giá trị:

$> X$

---

## 3. Ví dụ

Dãy:

`1 2 2 2 4 6`

Với $X = 2$:

- Lower Bound là vị trí đầu tiên chứa `2`.
- Upper Bound là vị trí đầu tiên chứa `4`.

Nếu đánh chỉ số từ `0`:

- Lower Bound = `1`
- Upper Bound = `4`

---

## 4. Đếm số lần xuất hiện của X

Số phần tử bằng $X$ là:

$upper\_bound(X) - lower\_bound(X)$

---

## 5. Đếm số phần tử nằm trong [L, R]

Nếu dãy đã sắp xếp:

Số lượng phần tử thuộc đoạn giá trị $[L, R]$ là:

$upper\_bound(R) - lower\_bound(L)$

---

# III. Ví dụ minh họa

---

## Ví dụ 1. Lower Bound tự cài đặt

```python
def lower_bound(a, x):
    left = 0
    right = len(a)

    while left < right:
        mid = (left + right) // 2

        if a[mid] < x:
            left = mid + 1
        else:
            right = mid

    return left
```

---

## Ví dụ 2. Upper Bound tự cài đặt

```python
def upper_bound(a, x):
    left = 0
    right = len(a)

    while left < right:
        mid = (left + right) // 2

        if a[mid] <= x:
            left = mid + 1
        else:
            right = mid

    return left
```

---

## Ví dụ 3. Đếm số lần xuất hiện của X

```python
def lower_bound(a, x):
    left = 0
    right = len(a)

    while left < right:
        mid = (left + right) // 2

        if a[mid] < x:
            left = mid + 1
        else:
            right = mid

    return left


def upper_bound(a, x):
    left = 0
    right = len(a)

    while left < right:
        mid = (left + right) // 2

        if a[mid] <= x:
            left = mid + 1
        else:
            right = mid

    return left


n, x = map(int, input().split())
a = list(map(int, input().split()))

print(upper_bound(a, x) - lower_bound(a, x))
```

---

## Ví dụ 4. Dùng thư viện bisect

```python
from bisect import bisect_left, bisect_right

n, x = map(int, input().split())
a = list(map(int, input().split()))

count = bisect_right(a, x) - bisect_left(a, x)

print(count)
```

---

## Ví dụ 5. Đếm phần tử trong đoạn [L, R]

```python
from bisect import bisect_left, bisect_right

n = int(input())
a = list(map(int, input().split()))

l, r = map(int, input().split())

answer = bisect_right(a, r) - bisect_left(a, l)

print(answer)
```

---

# IV. Bài tập vận dụng

---

## Bài 1. Vị trí lower bound

Cho dãy tăng dần và $X$.  
Tìm vị trí đầu tiên có giá trị $\ge X$.

---

## Bài 2. Vị trí upper bound

Cho dãy tăng dần và $X$.  
Tìm vị trí đầu tiên có giá trị $> X$.

---

## Bài 3. Đếm số phần tử bằng X

Cho dãy tăng dần.  
Đếm số lần xuất hiện của $X$.

---

## Bài 4. Đếm số phần tử thuộc [L, R]

Cho dãy tăng dần.  
Đếm số phần tử có giá trị thuộc $[L, R]$.

---

## Bài 5. Tìm vị trí chèn X

Cho dãy tăng dần.  
Tìm vị trí chèn $X$ vào để dãy vẫn tăng.

---

# V. Bài tập về nhà

---

## Bài 1. Số lượng học sinh đạt điểm từ A đến B

Danh sách điểm đã sắp xếp.  
Trả lời nhiều truy vấn.

---

## Bài 2. Cặp chênh lệch không vượt quá K

Cho dãy tăng dần.  
Với mỗi phần tử, dùng upper bound để đếm phần tử phù hợp.

---

## Bài 3. Khoảng gần X

Cho dãy tăng dần.  
Đếm số phần tử thuộc đoạn $[X-D, X+D]$.

---

## Bài 4. Xếp hạng điểm

Cho điểm học sinh đã sắp xếp.  
Tìm số học sinh có điểm lớn hơn một ngưỡng.

---

## Bài 5. Số lượng phần tử nhỏ hơn X

Dùng lower bound để trả lời.

---

# VI. Lỗi học sinh thường gặp

---

## 1. Nhầm điều kiện lower và upper

- Lower: `a[mid] < x`
- Upper: `a[mid] <= x`

---

## 2. Dùng biên right = len(a) - 1 cho mẫu nửa kín

Mẫu lower/upper bound thường dùng đoạn:

`[left, right)`

nên `right = len(a)`.

---

## 3. Không hiểu kết quả có thể bằng len(a)

Nếu mọi phần tử nhỏ hơn $X$, lower bound có thể trả về cuối mảng.

---

## 4. Nhầm số lần xuất hiện

Phải lấy:

$upper - lower$

---

## 5. Không sắp xếp dãy trước

---

# VII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Đếm số lần xuất hiện

Cho dãy đã sắp xếp và nhiều truy vấn $X$.  
Với mỗi $X$, đếm số lần xuất hiện.

---

## Đề 2. Đếm điểm trong khoảng

Cho bảng điểm đã sắp xếp.  
Trả lời số học sinh có điểm trong đoạn $[L, R]$.

---

## Đề 3. Xếp hạng

Với từng điểm số, xác định vị trí chèn của điểm đó vào bảng.

---

## Đề 4. Tìm dải giá trị

Cho dãy tăng.  
Tìm đoạn chỉ số chứa toàn bộ giá trị bằng $X$.

---

# VIII. Ghi nhớ cuối bài

- Lower Bound: vị trí đầu tiên $\ge X$.
- Upper Bound: vị trí đầu tiên $> X$.
- Số lần xuất hiện của $X$:

$upper - lower$

- Đây là kỹ thuật rất mạnh cho bài toán đếm trên dãy đã sắp xếp.

---

# IX. Tóm tắt bài học

## Bài 48. Lower Bound và Upper Bound

```python
from bisect import bisect_left, bisect_right

count_x = bisect_right(a, x) - bisect_left(a, x)
count_range = bisect_right(a, r) - bisect_left(a, l)
```
