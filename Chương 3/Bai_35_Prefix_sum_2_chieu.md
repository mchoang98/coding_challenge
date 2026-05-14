# Bài 35. Prefix Sum hai chiều

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu tổng tiền tố trên ma trận.
- Nắm công thức xây dựng prefix 2D.
- Biết tính tổng hình chữ nhật con.
- Hiểu vì sao cần cộng lại vùng giao.

## 2. Về kỹ năng

- Xây dựng mảng prefix hai chiều.
- Trả lời nhiều truy vấn tổng vùng trong $O(1)$.
- Áp dụng cho bài đếm ô thỏa điều kiện trong ma trận.

## 3. Về tư duy

- Mở rộng tiền xử lý từ dãy một chiều sang bảng hai chiều.
- Biết dùng cộng trừ vùng để tránh đếm trùng.

---

# II. Lý thuyết

## 1. Định nghĩa

$prefix[i][j]$ là tổng các phần tử trong hình chữ nhật từ $(1,1)$ đến $(i,j)$.

## 2. Công thức xây dựng

$prefix[i][j] = a[i][j] + prefix[i-1][j] + prefix[i][j-1] - prefix[i-1][j-1]$

## 3. Tổng hình chữ nhật con

Với vùng có góc trên trái $(r_1,c_1)$ và góc dưới phải $(r_2,c_2)$:

$sum = prefix[r_2][c_2] - prefix[r_1-1][c_2] - prefix[r_2][c_1-1] + prefix[r_1-1][c_1-1]$

## 4. Độ phức tạp

- Xây dựng: $O(MN)$
- Mỗi truy vấn: $O(1)$

---

# III. Ví dụ minh họa

## Ví dụ 1. Tính tổng một vùng chữ nhật

```python
m, n = map(int, input().split())

a = []

for _ in range(m):
    a.append(list(map(int, input().split())))

r1, c1, r2, c2 = map(int, input().split())

prefix = [[0] * (n + 1) for _ in range(m + 1)]

for i in range(1, m + 1):
    for j in range(1, n + 1):
        prefix[i][j] = (
            a[i - 1][j - 1]
            + prefix[i - 1][j]
            + prefix[i][j - 1]
            - prefix[i - 1][j - 1]
        )

ans = (
    prefix[r2][c2]
    - prefix[r1 - 1][c2]
    - prefix[r2][c1 - 1]
    + prefix[r1 - 1][c1 - 1]
)

print(ans)
```

---

## Ví dụ 2. Đếm số chẵn trong vùng

Ta biến mỗi ô thành `1` nếu chẵn, ngược lại `0`, rồi tạo prefix 2D trên bảng mới.

```python
m, n = map(int, input().split())

a = [list(map(int, input().split())) for _ in range(m)]

prefix = [[0] * (n + 1) for _ in range(m + 1)]

for i in range(1, m + 1):
    for j in range(1, n + 1):
        value = 1 if a[i - 1][j - 1] % 2 == 0 else 0

        prefix[i][j] = (
            value
            + prefix[i - 1][j]
            + prefix[i][j - 1]
            - prefix[i - 1][j - 1]
        )
```

---

# IV. Bài tập vận dụng

## Bài 1. Tổng ma trận con

Cho một truy vấn vùng.  
Tính tổng các phần tử.

## Bài 2. Nhiều truy vấn vùng

Trả lời $Q$ truy vấn tổng hình chữ nhật.

## Bài 3. Đếm số chẵn trong vùng

Xây bảng `0/1` rồi prefix hóa.

## Bài 4. Tổng số dương trong vùng

Chỉ cộng các ô dương.

## Bài 5. Hình vuông K × K có tổng lớn nhất

Duyệt mọi hình vuông kích thước $K$ bằng prefix 2D.

---

# V. Bài tập về nhà

## Bài 1. Hình chữ nhật toàn số 0

Kiểm tra một vùng có tổng bằng `0` hay không.

## Bài 2. Tổng đường viền hình chữ nhật

Tính tổng biên của một vùng từ tổng các vùng phù hợp.

## Bài 3. Đếm ký tự A trong bảng ký tự

Biến `A` thành `1`, `B` thành `0`.

## Bài 4. Hình chữ nhật H × W có tổng lớn nhất

Tổng quát hóa bài hình vuông.

---

# VI. Lỗi học sinh thường gặp

- Sai dấu trong công thức truy vấn vùng.
- Không tạo hàng 0, cột 0.
- Nhầm chỉ số hàng và cột.
- Duyệt lại toàn vùng trong mỗi truy vấn.
- Không hiểu vì sao phải cộng lại vùng giao.

---

# VII. Đề thi thật và bài chuẩn chuyên

## Đề 1. Truy vấn tổng vùng

Cho ma trận và nhiều truy vấn hình chữ nhật.  
Tính tổng từng vùng.

## Đề 2. Hình vuông tối ưu

Cho ma trận và $K$.  
Tìm hình vuông $K \times K$ có tổng lớn nhất.

## Đề 3. Bảng ký tự

Đếm số ô `A` trong mỗi vùng truy vấn.

---

# VIII. Ghi nhớ cuối bài

- Prefix 2D là kỹ thuật chuẩn cho truy vấn ma trận.
- Công thức cần ghi nhớ thật chính xác.
- Tư duy cộng trừ vùng là chìa khóa của bài toán.

---

# IX. Tóm tắt bài học

## Công thức quan trọng

$sum = prefix[r_2][c_2] - prefix[r_1-1][c_2] - prefix[r_2][c_1-1] + prefix[r_1-1][c_1-1]$
