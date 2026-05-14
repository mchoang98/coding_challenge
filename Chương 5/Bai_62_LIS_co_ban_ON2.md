# Bài 62. Dãy con tăng dài nhất LIS cơ bản O(N²)

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu khái niệm **dãy con** và **dãy con tăng**.
- Nắm bài toán LIS:
  - Longest Increasing Subsequence.
- Biết công thức DP `O(N^2)`.

## 2. Về kỹ năng

- Tính độ dài LIS.
- Viết code theo trạng thái `dp[i]`.
- Truy vết được một dãy LIS đơn giản.

## 3. Về tư duy

- Với mỗi phần tử `i`, xét các phần tử trước đó có thể nối vào.
- Kết quả toàn bài không nhất thiết nằm ở cuối dãy.

---

# II. Khái niệm

## 1. Dãy con

Dãy con được tạo bằng cách xóa một số phần tử nhưng vẫn giữ nguyên thứ tự còn lại.

Ví dụ dãy:

`3 1 5 2 6`

Một dãy con là:

`1 2 6`

---

## 2. Dãy con tăng

Dãy con tăng nếu:

\[
b_1 < b_2 < ... < b_k
\]

---

# III. Đề bài LIS

Cho dãy `a[1..N]`.  
Tìm độ dài lớn nhất của một dãy con tăng.

---

# IV. Trạng thái DP

## 1. Ý nghĩa

`dp[i]` là độ dài LIS **kết thúc tại vị trí i**.

---

## 2. Khởi tạo

Mỗi phần tử đứng riêng lẻ cũng tạo thành dãy tăng độ dài 1.

\[
dp[i] = 1
\]

---

## 3. Công thức chuyển

Muốn nối phần tử `a[i]` sau `a[j]`, cần:

\[
a[j] < a[i],\quad j < i
\]

Khi đó:

\[
dp[i] = \max(dp[i], dp[j] + 1)
\]

---

## 4. Đáp án

\[
\max(dp[i])
\]

---

# V. Code Python cơ bản

```python
n = int(input())
a = list(map(int, input().split()))

dp = [1] * n

for i in range(n):
    for j in range(i):
        if a[j] < a[i]:
            dp[i] = max(dp[i], dp[j] + 1)

print(max(dp))
```

---

# VI. Ví dụ minh họa

Dãy:

`3 1 5 2 6 4 9`

Một LIS có thể là:

`1 2 4 9`

Độ dài:

`4`

---

# VII. Truy vết một dãy LIS

Ta dùng thêm mảng `parent`.

```python
n = int(input())
a = list(map(int, input().split()))

dp = [1] * n
parent = [-1] * n

for i in range(n):
    for j in range(i):
        if a[j] < a[i] and dp[j] + 1 > dp[i]:
            dp[i] = dp[j] + 1
            parent[i] = j

best_pos = max(range(n), key=lambda i: dp[i])

lis = []
while best_pos != -1:
    lis.append(a[best_pos])
    best_pos = parent[best_pos]

lis.reverse()

print(len(lis))
print(*lis)
```

---

# VIII. Biến thể

## 1. Dãy con không giảm

Thay:

```python
a[j] < a[i]
```

bằng:

```python
a[j] <= a[i]
```

---

## 2. Dãy con giảm dài nhất

Thay điều kiện thành:

```python
a[j] > a[i]
```

---

# IX. Bài tập vận dụng

---

## Bài 1. Độ dài LIS

---

## Bài 2. In ra một LIS

---

## Bài 3. Dãy con không giảm dài nhất

---

## Bài 4. Dãy con giảm dài nhất

---

## Bài 5. LIS của dãy chiều cao học sinh

---

# X. Bài tập về nhà

---

## Bài 1. Số phần tử cần xóa ít nhất để dãy tăng

---

## Bài 2. Chuỗi số đẹp

Tìm dãy con tăng dài nhất có tổng lớn nhất khi độ dài bằng nhau.

---

## Bài 3. Dãy con tăng có tổng lớn nhất

---

## Bài 4. So sánh `O(N^2)` với phiên bản `O(N log N)` về mặt ý tưởng

---

## Bài 5. Truy vết LIS trong trường hợp có nhiều nghiệm

---

# XI. Lỗi học sinh thường gặp

---

## 1. Nhầm “dãy con” với “đoạn con”

---

## 2. Lấy đáp án là `dp[n-1]`

Sai vì LIS có thể kết thúc trước vị trí cuối.

---

## 3. Quên gán mặc định `dp[i] = 1`

---

## 4. Điều kiện tăng viết sai

---

## 5. Truy vết parent không đồng bộ với cập nhật dp

---

# XII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Dãy con tăng

---

## Đề 2. Hàng rào độ cao

---

## Đề 3. Chọn thí sinh theo năng lực tăng dần

---

## Đề 4. Biến thể dãy không giảm

---

# XIII. Ghi nhớ cuối bài

- `dp[i]` = LIS kết thúc tại `i`.
- Duyệt mọi `j < i`.
- Nếu `a[j] < a[i]`, có thể nối.

---

# XIV. Tóm tắt bài học

```python
dp = [1] * n

for i in range(n):
    for j in range(i):
        if a[j] < a[i]:
            dp[i] = max(dp[i], dp[j] + 1)
```
