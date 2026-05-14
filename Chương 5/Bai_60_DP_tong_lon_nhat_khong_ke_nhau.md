# Bài 60. DP 1 chiều tối ưu: tổng lớn nhất không chọn hai phần tử kề nhau

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu bài toán chọn phần tử có ràng buộc “không kề nhau”.
- Biết xây dựng trạng thái `dp[i]`.
- Biết công thức:
  \[
  dp[i] = \max(dp[i-1], dp[i-2] + a[i])
  \]

## 2. Về kỹ năng

- Giải bài toán chọn quà / chọn nhà / chọn phần tử không kề nhau.
- Phân tích rõ hai quyết định:
  - Không chọn phần tử hiện tại.
  - Chọn phần tử hiện tại.

## 3. Về tư duy

- Với bài chọn hoặc bỏ, hãy chia thành các trường hợp rõ ràng.
- DP giúp tránh liệt kê mọi tập con.

---

# II. Đề bài mẫu

Cho dãy `a[1..N]`.  
Hãy chọn một số phần tử sao cho:

- Không có hai phần tử được chọn nằm kề nhau.
- Tổng các phần tử được chọn là lớn nhất.

---

# III. Phân tích ý tưởng

## 1. Trạng thái

`dp[i]` là tổng lớn nhất có thể đạt được khi chỉ xét các phần tử từ `1` đến `i`.

---

## 2. Hai lựa chọn tại vị trí i

### Trường hợp 1. Không chọn `a[i]`

Kết quả giữ nguyên như khi xét tới `i-1`:

\[
dp[i-1]
\]

### Trường hợp 2. Chọn `a[i]`

Khi đó không được chọn `a[i-1]`, nên cộng với kết quả tốt nhất tới `i-2`:

\[
dp[i-2] + a[i]
\]

---

## 3. Công thức chuyển

\[
dp[i] = \max(dp[i-1], dp[i-2] + a[i])
\]

---

## 4. Điều kiện đầu

- `dp[0] = 0`
- `dp[1] = max(0, a[1])` nếu được phép không chọn gì.
- Nếu đề bắt buộc chọn ít nhất một phần tử, cần xử lý riêng.

---

# IV. Ví dụ minh họa

## Ví dụ 1

Dãy:

`5 1 2 10 6`

Kết quả tốt nhất:

- Chọn `5`
- Chọn `10`

Tổng = `15`

---

# V. Code Python

```python
n = int(input())
a = [0] + list(map(int, input().split()))

dp = [0] * (n + 1)

if n >= 1:
    dp[1] = max(0, a[1])

for i in range(2, n + 1):
    dp[i] = max(dp[i - 1], dp[i - 2] + a[i])

print(dp[n])
```

---

# VI. Phiên bản tối ưu bộ nhớ

Chỉ cần lưu hai trạng thái trước.

```python
n = int(input())
a = list(map(int, input().split()))

if n == 0:
    print(0)
elif n == 1:
    print(max(0, a[0]))
else:
    prev2 = 0
    prev1 = max(0, a[0])

    for i in range(1, n):
        cur = max(prev1, prev2 + a[i])
        prev2 = prev1
        prev1 = cur

    print(prev1)
```

---

# VII. Biến thể thường gặp

## 1. Nhà trộm

Mỗi nhà có tiền.  
Không được trộm hai nhà liền nhau.

---

## 2. Chọn quà

Không chọn hai món quà đặt cạnh nhau.

---

## 3. Chọn điểm kiểm tra

Không được chọn hai ngày liên tiếp.

---

# VIII. Bài tập vận dụng

---

## Bài 1. Tổng lớn nhất không chọn kề nhau

---

## Bài 2. Nhà trộm

---

## Bài 3. Chọn tối đa điểm thưởng trong chuỗi ngày

---

## Bài 4. Có số âm

Cho dãy có cả âm và dương.  
Nếu được phép không chọn gì, hãy tìm tổng tốt nhất.

---

## Bài 5. Bắt buộc chọn ít nhất một phần tử

---

# IX. Bài tập về nhà

---

## Bài 1. Không chọn hai phần tử cách nhau dưới 2 vị trí

---

## Bài 2. Chọn tối đa tổng với điều kiện không có ba phần tử liên tiếp cùng được chọn

---

## Bài 3. Dãy vòng tròn: phần tử đầu và cuối cũng kề nhau

---

## Bài 4. Truy vết danh sách phần tử đã chọn

---

## Bài 5. Tối ưu bộ nhớ cho bài toán

---

# X. Lỗi học sinh thường gặp

---

## 1. Dùng `dp[i-1] + a[i]`

Sai vì có thể đã chọn `a[i-1]`.

---

## 2. Quên xét trường hợp không chọn phần tử hiện tại

---

## 3. Không phân biệt được “tối đa tổng” và “đếm số cách”

---

## 4. Xử lý sai khi có số âm

---

## 5. Không xác định bài có cho phép chọn rỗng hay không

---

# XI. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Chọn nhà

---

## Đề 2. Chọn phần thưởng

---

## Đề 3. Chọn số không kề nhau

---

## Đề 4. Dãy vòng tròn

---

# XII. Ghi nhớ cuối bài

Mẫu cực quan trọng:

\[
dp[i] = \max(dp[i-1], dp[i-2] + a[i])
\]

Ý nghĩa:

- Không lấy `i`.
- Hoặc lấy `i` và bỏ `i-1`.

---

# XIII. Tóm tắt bài học

```python
dp[0] = 0
dp[1] = max(0, a[1])

for i in range(2, n + 1):
    dp[i] = max(dp[i - 1], dp[i - 2] + a[i])
```
