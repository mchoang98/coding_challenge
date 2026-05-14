# Bài 32. Thống kê, phần tử xuất hiện nhiều nhất và đếm phân phối

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu ý tưởng của **đếm phân phối**.
- Biết khi nào có thể dùng counting sort.
- Biết ứng dụng bảng tần suất để tìm:
  - Giá trị xuất hiện nhiều nhất.
  - Phần tử thứ $K$ sau khi sắp xếp.
  - Số tự nhiên nhỏ nhất không xuất hiện.

## 2. Về kỹ năng

- Cài đặt counting sort.
- Truy xuất phần tử thứ $K$ dựa trên bảng đếm.
- Tìm missing number trong đoạn nhỏ.

## 3. Về tư duy

- Khi miền giá trị nhỏ, không nhất thiết phải dùng sort tổng quát.
- Bảng tần suất có thể thay thế nhiều phép xử lý trực tiếp.

---

# II. Lý thuyết

## 1. Đếm phân phối là gì?

Đếm phân phối là kỹ thuật:

1. Đếm số lần xuất hiện của từng giá trị.
2. Dựa vào bảng đếm để sắp xếp hoặc trả lời truy vấn.

## 2. Counting sort

Nếu các giá trị nằm trong đoạn $[0, K]$, ta tạo mảng `count` kích thước $K+1`.

Sau đó:

- Đếm tần suất.
- In lại các giá trị theo thứ tự tăng dần.

Độ phức tạp:

$O(N + K)$

## 3. Phần tử thứ K sau sắp xếp

Nếu biết tần suất từng giá trị, ta cộng dồn từ nhỏ đến lớn.

Giá trị đầu tiên làm tổng cộng dồn đạt ít nhất $K$ chính là phần tử thứ $K$.

## 4. Số tự nhiên nhỏ nhất không xuất hiện

Với dãy có $N$ phần tử, số tự nhiên nhỏ nhất không xuất hiện chắc chắn không vượt quá $N$.

Ta chỉ cần đánh dấu các số từ `0` đến `N`.

---

# III. Ví dụ minh họa

## Ví dụ 1. Counting sort

```python
n = int(input())
a = list(map(int, input().split()))

count = [0] * 1001

for x in a:
    count[x] += 1

result = []

for value in range(1001):
    result.extend([value] * count[value])

print(*result)
```

---

## Ví dụ 2. Tìm số tự nhiên nhỏ nhất không xuất hiện

```python
n = int(input())
a = list(map(int, input().split()))

present = [False] * (n + 1)

for x in a:
    if 0 <= x <= n:
        present[x] = True

for value in range(n + 1):
    if not present[value]:
        print(value)
        break
```

---

## Ví dụ 3. Tìm phần tử thứ K sau khi sắp xếp

```python
n, k = map(int, input().split())
a = list(map(int, input().split()))

count = [0] * 128

for x in a:
    count[x] += 1

total = 0

for value in range(128):
    total += count[value]

    if total >= k:
        print(value)
        break
```

---

# IV. Bài tập vận dụng

## Bài 1. Sắp xếp bằng đếm phân phối

Cho dãy số trong đoạn từ `0` đến `10000`.  
In dãy theo thứ tự tăng dần.

## Bài 2. Tìm phần tử thứ K

Cho dãy số trong đoạn nhỏ.  
Tìm giá trị thứ $K$ sau khi sắp xếp.

## Bài 3. Giá trị xuất hiện nhiều nhất

Dùng bảng tần suất để tìm mode của dãy.

## Bài 4. Số tự nhiên nhỏ nhất không xuất hiện

Cho dãy số tự nhiên.  
Tìm số nhỏ nhất không xuất hiện.

## Bài 5. Sắp xếp ký tự trong xâu

Cho xâu chữ thường.  
In các ký tự theo thứ tự bảng chữ cái.

---

# V. Bài tập về nhà

## Bài 1. Giá trị xuất hiện đúng K lần

Liệt kê các giá trị xuất hiện đúng $K$ lần.

## Bài 2. Tìm hai tần suất lớn nhất

Cho dãy số.  
Tìm hai giá trị có số lần xuất hiện lớn nhất.

## Bài 3. Phần tử thứ K trong dãy giảm

Dùng tần suất để tìm phần tử thứ $K$ nếu dãy được sắp giảm dần.

## Bài 4. Ký tự xuất hiện ít nhất

Cho xâu chữ thường.  
Tìm ký tự xuất hiện ít nhất nhưng phải xuất hiện ít nhất một lần.

---

# VI. Lỗi học sinh thường gặp

- Tạo mảng đếm lớn hơn khả năng bộ nhớ.
- Nhầm vị trí thứ $K$ với chỉ số bắt đầu từ `0`.
- Quên rằng missing number chỉ cần xét đến `N`.
- Dùng counting sort cho dữ liệu không phù hợp.
- Không xử lý quy tắc hòa khi nhiều giá trị cùng tần suất.

---

# VII. Đề thi thật và bài chuẩn chuyên

## Đề 1. Số tự nhiên nhỏ nhất không xuất hiện

Cho dãy $N$ số tự nhiên.  
Tìm số tự nhiên nhỏ nhất không xuất hiện.

## Đề 2. Giá trị thứ K

Cho dãy số nguyên có miền giá trị nhỏ.  
Tìm phần tử thứ $K$ sau khi sắp tăng.

## Đề 3. Tần suất lớn nhất

Cho dãy số.  
Tìm số lần lặp lớn nhất của một giá trị.

---

# VIII. Ghi nhớ cuối bài

- Counting sort mạnh khi miền giá trị nhỏ.
- Đếm phân phối giúp sắp xếp và truy vấn thứ hạng nhanh.
- Tư duy tần suất là nền tảng quan trọng của nhiều bài tối ưu.

---

# IX. Tóm tắt bài học

## Công thức tư duy

Nếu dữ liệu nằm trong đoạn nhỏ, hãy nghĩ:

1. Đếm trước.
2. Xử lý sau.

Đây là cách biến nhiều bài khó thành bài quét bảng đếm đơn giản.
