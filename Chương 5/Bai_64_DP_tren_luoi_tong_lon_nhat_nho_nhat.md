# Bài 64. DP trên lưới: tổng lớn nhất / nhỏ nhất trên đường đi

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Biết DP tối ưu trên lưới.
- Phân biệt:
  - Đếm số cách.
  - Tìm giá trị lớn nhất.
  - Tìm chi phí nhỏ nhất.
- Nắm công thức:
  \[
  dp[i][j] = a[i][j] + \max(dp[i-1][j], dp[i][j-1])
  \]
  hoặc dùng `min`.

## 2. Về kỹ năng

- Tính tổng lớn nhất khi đi phải/xuống.
- Tính chi phí nhỏ nhất.
- Xử lý biên hàng đầu và cột đầu.

## 3. Về tư duy

- Giá trị tại ô hiện tại phụ thuộc vào lựa chọn tốt nhất trước đó.
- Với tối ưu:
  - Dùng `max` cho lớn nhất.
  - Dùng `min` cho nhỏ nhất.

---

# II. Đề bài mẫu

Cho bảng `M × N`, mỗi ô có giá trị.  
Từ `(1,1)` tới `(M,N)`, chỉ đi:

- Sang phải.
- Xuống dưới.

Hãy tìm tổng lớn nhất các giá trị trên đường đi.

---

# III. Trạng thái

`dp[i][j]` là tổng lớn nhất khi đi đến ô `(i,j)`.

---

# IV. Công thức chuyển

\[
dp[i][j] = a[i][j] + \max(dp[i-1][j], dp[i][j-1])
\]

---

# V. Điều kiện đầu

- `dp[0][0] = a[0][0]`
- Hàng đầu chỉ đi từ trái sang.
- Cột đầu chỉ đi từ trên xuống.

---

# VI. Code Python — tổng lớn nhất

```python
m, n = map(int, input().split())
a = [list(map(int, input().split())) for _ in range(m)]

dp = [[0] * n for _ in range(m)]
dp[0][0] = a[0][0]

for j in range(1, n):
    dp[0][j] = dp[0][j - 1] + a[0][j]

for i in range(1, m):
    dp[i][0] = dp[i - 1][0] + a[i][0]

for i in range(1, m):
    for j in range(1, n):
        dp[i][j] = a[i][j] + max(dp[i - 1][j], dp[i][j - 1])

print(dp[m - 1][n - 1])
```

---

# VII. Code Python — tổng nhỏ nhất

```python
m, n = map(int, input().split())
a = [list(map(int, input().split())) for _ in range(m)]

dp = [[0] * n for _ in range(m)]
dp[0][0] = a[0][0]

for j in range(1, n):
    dp[0][j] = dp[0][j - 1] + a[0][j]

for i in range(1, m):
    dp[i][0] = dp[i - 1][0] + a[i][0]

for i in range(1, m):
    for j in range(1, n):
        dp[i][j] = a[i][j] + min(dp[i - 1][j], dp[i][j - 1])

print(dp[m - 1][n - 1])
```

---

# VIII. Nếu có ô cấm

Với bài tìm min/max, ô cấm cần được đánh dấu bằng giá trị vô cực thích hợp.

Ví dụ tìm nhỏ nhất:

```python
INF = 10**18
```

Ô cấm có thể gán `INF`.

---

# IX. Bài tập vận dụng

---

## Bài 1. Tổng lớn nhất trên lưới

---

## Bài 2. Chi phí nhỏ nhất trên lưới

---

## Bài 3. Đường đi qua các ô có điểm âm

---

## Bài 4. Lưới có vật cản

---

## Bài 5. Truy vết một đường đi tốt nhất

---

# X. Bài tập về nhà

---

## Bài 1. Tìm tổng lớn nhất và số đường đi đạt tổng đó

---

## Bài 2. Lưới có bước chéo

---

## Bài 3. Tối ưu bộ nhớ `O(N)`

---

## Bài 4. Tìm đường đi từ hàng đầu đến hàng cuối với phép dịch cột ±1

---

## Bài 5. Tam giác số

---

# XI. Lỗi học sinh thường gặp

---

## 1. Dùng công thức cộng thay vì max/min

---

## 2. Khởi tạo hàng đầu và cột đầu sai

---

## 3. Không xét giá trị âm

---

## 4. Xử lý ô cấm không nhất quán

---

## 5. Nhầm tổng lớn nhất với đường đi có nhiều ô nhất

---

# XII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Tam giác số

---

## Đề 2. Thu thập vàng trên lưới

---

## Đề 3. Đường đi chi phí nhỏ nhất

---

## Đề 4. Hành trình trong mê cung có điểm số

---

# XIII. Ghi nhớ cuối bài

- Đếm cách: cộng.
- Tối ưu: max hoặc min.
- Cùng là DP lưới nhưng mục tiêu khác thì công thức khác.

---

# XIV. Tóm tắt bài học

```python
dp[i][j] = a[i][j] + max(dp[i - 1][j], dp[i][j - 1])
```
