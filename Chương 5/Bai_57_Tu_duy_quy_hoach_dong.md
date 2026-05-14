# Bài 57. Tư duy quy hoạch động: trạng thái, công thức chuyển, điều kiện đầu

---

# I. Mục tiêu bài học

Sau bài học này, học sinh cần đạt được:

## 1. Về kiến thức

- Hiểu **quy hoạch động** là gì.
- Biết khi nào một bài toán có thể dùng DP.
- Nắm được bốn thành phần cốt lõi:
  1. Trạng thái.
  2. Công thức chuyển.
  3. Điều kiện ban đầu.
  4. Thứ tự tính.
- Phân biệt được:
  - Brute force.
  - Đệ quy thường.
  - Đệ quy có nhớ.
  - DP bảng.

## 2. Về kỹ năng

- Chuyển một bài toán đơn giản thành bảng `dp`.
- Viết được công thức chuyển ở dạng lời và dạng toán.
- Tự đặt câu hỏi đúng khi gặp bài DP.

## 3. Về tư duy

- Từ bài toán lớn, biết quy về các bài toán nhỏ hơn.
- Hiểu rằng DP hiệu quả vì **không tính lại kết quả cũ**.
- Có tư duy xây dựng lời giải từng lớp, thay vì chỉ lao vào code.

---

# II. Quy hoạch động là gì?

## 1. Ý tưởng trực giác

Quy hoạch động là kỹ thuật giải bài toán bằng cách:

1. Chia bài toán lớn thành các bài toán con.
2. Ghi nhớ kết quả của bài toán con.
3. Kết hợp chúng để xây dựng đáp án bài toán lớn.

---

## 2. Ví dụ đời thường

Giả sử cần đi từ tầng 1 lên tầng 10.

Mỗi lần có thể:

- Đi 1 tầng.
- Đi 2 tầng.

Muốn biết có bao nhiêu cách lên tầng 10, ta nhận thấy:

- Để lên tầng 10, bước cuối cùng:
  - Hoặc từ tầng 9 đi lên 1 tầng.
  - Hoặc từ tầng 8 đi lên 2 tầng.

Vậy:

\[
dp[10] = dp[9] + dp[8]
\]

---

## 3. Khi nào nghĩ đến DP?

Một bài toán thường phù hợp với DP khi có:

### 3.1. Bài toán con chồng lặp

Cùng một bài toán con bị tính đi tính lại nhiều lần.

Ví dụ:

\[
F(5) = F(4) + F(3)
\]

trong đó:

\[
F(4) = F(3) + F(2)
\]

Ta thấy `F(3)` bị tính nhiều lần.

---

### 3.2. Cấu trúc tối ưu

Đáp án tối ưu của bài toán lớn được tạo ra từ đáp án tối ưu của các bài toán nhỏ hơn.

Ví dụ:

- Tổng lớn nhất.
- Chi phí nhỏ nhất.
- Số cách.
- Độ dài lớn nhất.

---

# III. Bốn thành phần bắt buộc của một bài DP

---

## 1. Trạng thái

Trạng thái mô tả **ý nghĩa của một ô trong bảng DP**.

Ví dụ:

- `dp[i]`: số cách đi đến bậc `i`.
- `dp[i]`: tổng lớn nhất xét đến vị trí `i`.
- `dp[i][j]`: kết quả tốt nhất khi xét tới ô `(i, j)`.

---

## 2. Công thức chuyển

Công thức chuyển mô tả cách tính trạng thái hiện tại từ các trạng thái nhỏ hơn.

Ví dụ:

\[
dp[i] = dp[i-1] + dp[i-2]
\]

---

## 3. Điều kiện ban đầu

Là những trạng thái nhỏ nhất đã biết trước.

Ví dụ:

- `dp[0] = 1`
- `dp[1] = 1`

---

## 4. Thứ tự tính

Ta phải tính các trạng thái nhỏ trước, trạng thái lớn sau.

Ví dụ:

```python
for i in range(2, n + 1):
    dp[i] = dp[i - 1] + dp[i - 2]
```

---

# IV. Khung tư duy 5 câu hỏi khi gặp bài DP

Khi đọc đề, hãy lần lượt hỏi:

## Câu 1. Bài toán cần tối ưu hay đếm?

- Đếm số cách?
- Tìm giá trị lớn nhất?
- Tìm chi phí nhỏ nhất?
- Tìm độ dài lớn nhất?

---

## Câu 2. Trạng thái là gì?

Ví dụ:

- `dp[i]` ứng với việc đã xét bao nhiêu phần tử?
- `dp[i][j]` ứng với hai chỉ số nào?

---

## Câu 3. Từ trạng thái nào đi tới trạng thái hiện tại?

Ví dụ:

- `i - 1`
- `i - 2`
- Ô phía trên.
- Ô bên trái.

---

## Câu 4. Điều kiện đầu là gì?

Ví dụ:

- `dp[0] = 1`
- `dp[1] = a[1]`

---

## Câu 5. Duyệt bảng theo thứ tự nào?

- Tăng dần chỉ số.
- Theo hàng, rồi theo cột.
- Theo độ dài đoạn.

---

# V. Ví dụ minh họa

---

## Ví dụ 1. Fibonacci bằng quy hoạch động

### 1. Định nghĩa

\[
F_0 = 0,\quad F_1 = 1
\]

\[
F_n = F_{n-1} + F_{n-2}
\]

---

### 2. Trạng thái

`dp[i]` là số Fibonacci thứ `i`.

---

### 3. Công thức chuyển

\[
dp[i] = dp[i-1] + dp[i-2]
\]

---

### 4. Điều kiện đầu

```python
dp[0] = 0
dp[1] = 1
```

---

### 5. Code Python

```python
n = int(input())

if n == 0:
    print(0)
else:
    dp = [0] * (n + 1)
    dp[0] = 0
    dp[1] = 1

    for i in range(2, n + 1):
        dp[i] = dp[i - 1] + dp[i - 2]

    print(dp[n])
```

---

## Ví dụ 2. Tổng lớn nhất khi đi tới vị trí i

### 1. Đề bài đơn giản

Có dãy `a[1..n]`.  
Tại mỗi bước, có thể nhảy 1 hoặc 2 vị trí.  
Khi đặt chân vào vị trí nào thì nhận giá trị tại vị trí đó.

Hãy tìm tổng lớn nhất khi tới vị trí `n`.

---

### 2. Trạng thái

`dp[i]` là tổng lớn nhất để tới vị trí `i`.

---

### 3. Công thức chuyển

Để tới `i`, ta có thể tới từ:

- `i - 1`
- `i - 2`

Vậy:

\[
dp[i] = \max(dp[i-1], dp[i-2]) + a[i]
\]

---

### 4. Điều kiện đầu

- `dp[1] = a[1]`
- `dp[2] = a[1] + a[2]` nếu bắt buộc đi qua 1; hoặc tùy đề.

---

# VI. Cách nhận dạng bài DP trong đề thi

Một số từ khóa đáng chú ý:

- “Số cách...”
- “Ít nhất...”
- “Nhiều nhất...”
- “Tối đa...”
- “Tối thiểu...”
- “Dãy con...”
- “Đường đi...”
- “Chọn một số phần tử...”
- “Không chọn hai phần tử kề nhau...”

---

# VII. Bài tập vận dụng

---

## Bài 1. Nhận dạng trạng thái

Với bài toán leo cầu thang, hãy trả lời:

1. `dp[i]` là gì?
2. Công thức chuyển là gì?
3. Điều kiện đầu là gì?

---

## Bài 2. Fibonacci

Tính số Fibonacci thứ `N` bằng DP.

---

## Bài 3. Số cách đi đến ô thứ N

Mỗi bước đi được 1 hoặc 2 ô.  
Đếm số cách tới ô `N`.

---

## Bài 4. Đếm cách lát gạch

Bảng có kích thước `2 × N`, lát bằng domino `2 × 1`.  
Đếm số cách lát.

---

## Bài 5. Phân tích bài toán

Cho dãy số, chọn một số phần tử không kề nhau để tổng là lớn nhất.  
Hãy đề xuất ý nghĩa của `dp[i]`.

---

# VIII. Bài tập về nhà

---

## Bài 1. Số cách đi bậc thang với bước 1, 2, 3

---

## Bài 2. Số cách tạo tổng N từ các số 1 và 2

---

## Bài 3. Đường đi tổng lớn nhất trên một hàng

---

## Bài 4. Tối thiểu số bước để đi tới N nếu được cộng 1 hoặc nhân 2

---

## Bài 5. Hãy tự lấy một bài toán đã từng giải bằng brute force và thử nghĩ xem có thể dùng DP không.

---

# IX. Lỗi học sinh thường gặp

---

## 1. Chưa xác định rõ trạng thái đã vội code

Không biết `dp[i]` nghĩa là gì thì rất dễ viết sai.

---

## 2. Công thức chuyển thiếu trường hợp

Ví dụ được nhảy 1 hoặc 2 bước nhưng chỉ xét `i-1`.

---

## 3. Thiếu điều kiện đầu

Không đặt `dp[0]`, `dp[1]` rõ ràng sẽ dẫn đến sai toàn bộ.

---

## 4. Duyệt sai thứ tự

Muốn dùng `dp[i-1]` thì phải tính `dp[i-1]` trước.

---

## 5. Nhầm giữa số cách và giá trị tối ưu

- Đếm cách: thường cộng.
- Tối ưu: thường lấy `max` hoặc `min`.

---

# X. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Leo cầu thang

Đếm số cách đi lên bậc `N`.

---

## Đề 2. Lát gạch

Đếm số cách lát bảng `2 × N`.

---

## Đề 3. Chọn quà không kề nhau

Tối đa tổng giá trị quà.

---

## Đề 4. Đường đi điểm số

Tối đa hóa tổng điểm trên các bước nhảy.

---

# XI. Ghi nhớ cuối bài

- DP không phải là học thuộc công thức.
- DP là quá trình xác định:
  - Trạng thái.
  - Chuyển trạng thái.
  - Điều kiện đầu.
  - Thứ tự tính.
- Câu hỏi quan trọng nhất:
  > “Ô `dp[...]` này có ý nghĩa gì?”

---

# XII. Tóm tắt bài học

## Bài 57. Tư duy quy hoạch động

Khung chuẩn:

```python
# 1. Định nghĩa dp
# 2. Gán điều kiện đầu
# 3. Duyệt trạng thái
# 4. Trả lời kết quả
```

Ví dụ:

```python
dp[0] = 0
dp[1] = 1

for i in range(2, n + 1):
    dp[i] = dp[i - 1] + dp[i - 2]
```
