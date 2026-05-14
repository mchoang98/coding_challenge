# Bài 66. Khoảng cách chỉnh sửa và DP hai chiều trên xâu

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu bài toán **Edit Distance**.
- Biết ba phép biến đổi:
  - Chèn.
  - Xóa.
  - Thay thế.
- Nắm được trạng thái `dp[i][j]`.

## 2. Về kỹ năng

- Tính số phép ít nhất để biến xâu A thành xâu B.
- Viết công thức chuyển chính xác.
- Nhận ra quan hệ với DP trên tiền tố.

## 3. Về tư duy

- So sánh hai tiền tố thay vì nhìn toàn bộ xâu cùng lúc.
- Khi ký tự cuối khác nhau, xét ba lựa chọn.

---

# II. Đề bài

Cho hai xâu `A`, `B`.  
Tìm số phép ít nhất để biến `A` thành `B`, cho phép:

1. Chèn một ký tự.
2. Xóa một ký tự.
3. Thay một ký tự.

---

# III. Trạng thái

`dp[i][j]` là số phép ít nhất để biến:

- `A[:i]`
- thành `B[:j]`.

---

# IV. Điều kiện đầu

- `dp[0][j] = j`: từ xâu rỗng tạo B bằng `j` lần chèn.
- `dp[i][0] = i`: từ A tạo xâu rỗng bằng `i` lần xóa.

---

# V. Công thức chuyển

## 1. Nếu ký tự cuối giống nhau

```python
A[i - 1] == B[j - 1]
```

thì:

\[
dp[i][j] = dp[i-1][j-1]
\]

---

## 2. Nếu ký tự cuối khác nhau

Có ba lựa chọn:

### Xóa

\[
dp[i-1][j] + 1
\]

### Chèn

\[
dp[i][j-1] + 1
\]

### Thay thế

\[
dp[i-1][j-1] + 1
\]

Vậy:

\[
dp[i][j] = 1 + \min(dp[i-1][j], dp[i][j-1], dp[i-1][j-1])
\]

---

# VI. Code Python

```python
a = input().strip()
b = input().strip()

m = len(a)
n = len(b)

dp = [[0] * (n + 1) for _ in range(m + 1)]

for i in range(m + 1):
    dp[i][0] = i

for j in range(n + 1):
    dp[0][j] = j

for i in range(1, m + 1):
    for j in range(1, n + 1):
        if a[i - 1] == b[j - 1]:
            dp[i][j] = dp[i - 1][j - 1]
        else:
            dp[i][j] = 1 + min(
                dp[i - 1][j],      # xóa
                dp[i][j - 1],      # chèn
                dp[i - 1][j - 1]   # thay
            )

print(dp[m][n])
```

---

# VII. Ví dụ minh họa

`A = "cat"`  
`B = "cut"`

Chỉ cần thay `a` bằng `u`.

Đáp án = `1`.

---

# VIII. Bài tập vận dụng

---

## Bài 1. Tính edit distance của hai xâu

---

## Bài 2. Chỉ cho phép xóa và chèn

---

## Bài 3. Chỉ cho phép thay ký tự

---

## Bài 4. So sánh tên gần giống nhau

---

## Bài 5. Tìm khoảng cách giữa hai dãy số ngắn

---

# IX. Bài tập về nhà

---

## Bài 1. In bảng DP của một ví dụ nhỏ

---

## Bài 2. Tối ưu bộ nhớ xuống `O(N)`

---

## Bài 3. Truy vết lại chuỗi thao tác

---

## Bài 4. Biến đổi xâu với chi phí riêng cho từng thao tác

---

## Bài 5. So sánh Edit Distance và LCS

---

# X. Lỗi học sinh thường gặp

---

## 1. Nhầm công thức của chèn và xóa

---

## 2. Không khởi tạo hàng đầu, cột đầu

---

## 3. Ký tự giống nhau nhưng vẫn cộng 1

---

## 4. Không hiểu `dp[i][j]` xử lý tiền tố nào

---

# XI. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Khoảng cách từ

---

## Đề 2. Sửa lỗi gõ

---

## Đề 3. So khớp tên gần đúng

---

## Đề 4. Chuỗi thao tác tối thiểu

---

# XII. Ghi nhớ cuối bài

Edit Distance là mẫu DP xâu rất quan trọng.

Công thức khác nhau ở hai tình huống:

- Ký tự cuối bằng nhau.
- Ký tự cuối khác nhau.

---

# XIII. Tóm tắt bài học

```python
if a[i - 1] == b[j - 1]:
    dp[i][j] = dp[i - 1][j - 1]
else:
    dp[i][j] = 1 + min(
        dp[i - 1][j],
        dp[i][j - 1],
        dp[i - 1][j - 1]
    )
```
