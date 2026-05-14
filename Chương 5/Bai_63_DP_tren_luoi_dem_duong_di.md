# Bài 63. DP trên lưới: đếm số đường đi

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu DP hai chiều trên lưới.
- Biết cách đếm số đường đi từ ô đầu đến ô cuối.
- Nắm công thức:
  \[
  dp[i][j] = dp[i-1][j] + dp[i][j-1]
  \]

## 2. Về kỹ năng

- Cài đặt bài đi lưới phải/xuống.
- Xử lý ô bị chặn.
- Dùng modulo khi số cách lớn.

## 3. Về tư duy

- Mỗi ô gom thông tin từ các ô có thể đi tới nó.
- Thứ tự duyệt bảng quyết định việc cập nhật đúng.

---

# II. Đề bài mẫu

Có bảng `M × N`.

Từ ô `(1,1)`, chỉ được đi:

- Sang phải.
- Xuống dưới.

Hỏi có bao nhiêu cách đi tới ô `(M,N)`?

---

# III. Trạng thái DP

`dp[i][j]` là số cách đi tới ô `(i, j)`.

---

# IV. Công thức chuyển

Muốn tới ô `(i,j)`:

- Đi từ ô phía trên `(i-1,j)`.
- Đi từ ô bên trái `(i,j-1)`.

Vậy:

\[
dp[i][j] = dp[i-1][j] + dp[i][j-1]
\]

---

# V. Điều kiện đầu

- `dp[1][1] = 1`
- Các vị trí ngoài bảng coi như 0.

Trong Python thường dùng chỉ số từ `0`.

---

# VI. Code Python — không có vật cản

```python
m, n = map(int, input().split())

dp = [[0] * n for _ in range(m)]
dp[0][0] = 1

for i in range(m):
    for j in range(n):
        if i == 0 and j == 0:
            continue

        from_top = dp[i - 1][j] if i > 0 else 0
        from_left = dp[i][j - 1] if j > 0 else 0

        dp[i][j] = from_top + from_left

print(dp[m - 1][n - 1])
```

---

# VII. Code Python — có vật cản

Giả sử:

- `0` là ô trống.
- `1` là ô bị chặn.

```python
m, n = map(int, input().split())
grid = [list(map(int, input().split())) for _ in range(m)]

dp = [[0] * n for _ in range(m)]

if grid[0][0] == 0:
    dp[0][0] = 1

for i in range(m):
    for j in range(n):
        if grid[i][j] == 1:
            dp[i][j] = 0
            continue

        if i == 0 and j == 0:
            continue

        from_top = dp[i - 1][j] if i > 0 else 0
        from_left = dp[i][j - 1] if j > 0 else 0

        dp[i][j] = from_top + from_left

print(dp[m - 1][n - 1])
```

---

# VIII. Dùng modulo

Nếu đề yêu cầu lấy kết quả modulo `MOD`:

```python
MOD = 10**9 + 7
dp[i][j] = (from_top + from_left) % MOD
```

---

# IX. Bài tập vận dụng

---

## Bài 1. Đếm đường đi không vật cản

---

## Bài 2. Đếm đường đi có vật cản

---

## Bài 3. Đường đi trên bảng có ô khóa

---

## Bài 4. Số cách đi từ góc trái trên tới góc phải dưới modulo `10^9+7`

---

## Bài 5. Đếm đường đi khi chỉ được xuống và chéo xuống phải

---

# X. Bài tập về nhà

---

## Bài 1. Đếm số đường đi tới mọi ô

---

## Bài 2. Tìm ô có nhiều cách đi tới nhất

---

## Bài 3. Đếm đường đi qua một ô bắt buộc

---

## Bài 4. Đếm đường đi tránh một vùng cấm

---

## Bài 5. Tối ưu bộ nhớ về `O(N)`

---

# XI. Lỗi học sinh thường gặp

---

## 1. Không xử lý ô xuất phát bị chặn

---

## 2. Cộng từ ô bị chặn

---

## 3. Duyệt sai thứ tự

---

## 4. Quên modulo

---

## 5. Nhầm `m`, `n`, hàng và cột

---

# XII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Đường đi robot

---

## Đề 2. Khu rừng có bẫy

---

## Đề 3. Lưới ô vuông có chướng ngại

---

## Đề 4. Bảng đường đi modulo

---

# XIII. Ghi nhớ cuối bài

DP lưới đếm cách thường có dạng:

\[
dp[i][j] = dp[i-1][j] + dp[i][j-1]
\]

---

# XIV. Tóm tắt bài học

```python
for i in range(m):
    for j in range(n):
        if blocked:
            continue
        dp[i][j] = from_top + from_left
```
