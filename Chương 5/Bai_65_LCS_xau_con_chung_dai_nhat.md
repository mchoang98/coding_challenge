# Bài 65. Xâu con chung dài nhất LCS

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu khái niệm **dãy con chung**.
- Biết bài toán LCS:
  - Longest Common Subsequence.
- Nắm được trạng thái `dp[i][j]`.

## 2. Về kỹ năng

- Tính độ dài LCS của hai xâu.
- Viết công thức chuyển đúng.
- Truy vết được một LCS.

## 3. Về tư duy

- Khi so hai tiền tố của hai xâu, xét:
  - Ký tự cuối bằng nhau.
  - Ký tự cuối khác nhau.

---

# II. Khái niệm

## 1. Dãy con của xâu

Từ xâu `"abcde"`:

- `"ace"` là dãy con.
- `"aec"` không phải dãy con vì sai thứ tự.

---

## 2. LCS là gì?

LCS của hai xâu là dãy con chung có độ dài lớn nhất.

Ví dụ:

- `A = "abcde"`
- `B = "ace"`

LCS là `"ace"`.

---

# III. Trạng thái DP

`dp[i][j]` là độ dài LCS của:

- `A[:i]`
- `B[:j]`

Tức là `i` ký tự đầu của A và `j` ký tự đầu của B.

---

# IV. Công thức chuyển

## 1. Nếu ký tự cuối giống nhau

Nếu:

```python
A[i - 1] == B[j - 1]
```

thì:

\[
dp[i][j] = dp[i-1][j-1] + 1
\]

---

## 2. Nếu ký tự cuối khác nhau

Ta bỏ đi một ký tự ở A hoặc ở B:

\[
dp[i][j] = \max(dp[i-1][j], dp[i][j-1])
\]

---

# V. Code Python tính độ dài LCS

```python
a = input().strip()
b = input().strip()

m = len(a)
n = len(b)

dp = [[0] * (n + 1) for _ in range(m + 1)]

for i in range(1, m + 1):
    for j in range(1, n + 1):
        if a[i - 1] == b[j - 1]:
            dp[i][j] = dp[i - 1][j - 1] + 1
        else:
            dp[i][j] = max(dp[i - 1][j], dp[i][j - 1])

print(dp[m][n])
```

---

# VI. Truy vết một LCS

```python
a = input().strip()
b = input().strip()

m = len(a)
n = len(b)

dp = [[0] * (n + 1) for _ in range(m + 1)]

for i in range(1, m + 1):
    for j in range(1, n + 1):
        if a[i - 1] == b[j - 1]:
            dp[i][j] = dp[i - 1][j - 1] + 1
        else:
            dp[i][j] = max(dp[i - 1][j], dp[i][j - 1])

i = m
j = n
res = []

while i > 0 and j > 0:
    if a[i - 1] == b[j - 1]:
        res.append(a[i - 1])
        i -= 1
        j -= 1
    elif dp[i - 1][j] >= dp[i][j - 1]:
        i -= 1
    else:
        j -= 1

res.reverse()
print("".join(res))
```

---

# VII. Ví dụ minh họa

- `A = "abac"`
- `B = "cab"`

Một LCS là:

`"ab"`

Độ dài:

`2`

---

# VIII. Bài tập vận dụng

---

## Bài 1. Độ dài LCS của hai xâu

---

## Bài 2. In ra một LCS

---

## Bài 3. LCS của hai dãy số

---

## Bài 4. Xâu con palindrome dài nhất thông qua LCS với xâu đảo

---

## Bài 5. Số ký tự cần xóa ít nhất để hai xâu giống nhau

---

# IX. Bài tập về nhà

---

## Bài 1. LCS nhiều test

---

## Bài 2. Tìm dãy con chung dài nhất của hai dãy số nguyên

---

## Bài 3. Số thao tác xóa ít nhất để biến A và B thành cùng một xâu

---

## Bài 4. Kiểm tra một xâu có là dãy con của xâu khác không

---

## Bài 5. Tối ưu bộ nhớ cho LCS khi chỉ cần độ dài

---

# X. Lỗi học sinh thường gặp

---

## 1. Nhầm substring với subsequence

- Substring: liên tiếp.
- Subsequence: không cần liên tiếp.

---

## 2. Sai chỉ số `i-1`, `j-1`

---

## 3. Không thêm hàng 0, cột 0

---

## 4. Khi ký tự khác nhau lại cộng 1

---

## 5. Truy vết đi sai hướng

---

# XI. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Xâu con chung dài nhất

---

## Đề 2. Dãy con chung dài nhất

---

## Đề 3. Biến đổi xâu bằng xóa

---

## Đề 4. Palindrome qua LCS

---

# XII. Ghi nhớ cuối bài

Công thức quan trọng:

\[
dp[i][j] =
\begin{cases}
dp[i-1][j-1] + 1, & \text{nếu } A[i-1] = B[j-1] \\
\max(dp[i-1][j], dp[i][j-1]), & \text{ngược lại}
\end{cases}
\]

---

# XIII. Tóm tắt bài học

```python
if a[i - 1] == b[j - 1]:
    dp[i][j] = dp[i - 1][j - 1] + 1
else:
    dp[i][j] = max(dp[i - 1][j], dp[i][j - 1])
```
