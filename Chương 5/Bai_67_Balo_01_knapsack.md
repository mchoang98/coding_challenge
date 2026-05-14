# Bài 67. Balo 0/1 — Knapsack cơ bản

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu bài toán balo 0/1.
- Biết vì sao mỗi món đồ chỉ được chọn tối đa một lần.
- Xây dựng trạng thái DP hai chiều:
  - Xét `i` món đầu.
  - Với sức chứa `w`.

## 2. Về kỹ năng

- Cài đặt knapsack 0/1.
- Hiểu hai lựa chọn:
  - Không lấy món i.
  - Lấy món i.
- Tối ưu 1 chiều mức cơ bản.

## 3. Về tư duy

- Mỗi món đồ là một quyết định có/không.
- DP gom các khả năng tối ưu thay vì duyệt mọi tập con.

---

# II. Đề bài

Có `N` món đồ.  
Món thứ `i` có:

- Trọng lượng `weight[i]`.
- Giá trị `value[i]`.

Balo chịu được tối đa `W`.

Chọn một số món sao cho:

- Tổng trọng lượng không vượt quá `W`.
- Tổng giá trị là lớn nhất.

Mỗi món chỉ được chọn tối đa một lần.

---

# III. Trạng thái

`dp[i][w]` là giá trị lớn nhất khi:

- Chỉ xét `i` món đầu.
- Balo có sức chứa tối đa `w`.

---

# IV. Công thức chuyển

## 1. Không lấy món i

\[
dp[i][w] = dp[i-1][w]
\]

## 2. Lấy món i

Chỉ được lấy nếu:

\[
weight[i] \le w
\]

Khi đó:

\[
dp[i][w] = dp[i-1][w-weight[i]] + value[i]
\]

## 3. Tổng hợp

\[
dp[i][w] = \max(
dp[i-1][w],
dp[i-1][w-weight[i]] + value[i]
)
\]

---

# V. Code Python 2 chiều

```python
n, W = map(int, input().split())

weights = [0]
values = [0]

for _ in range(n):
    w, v = map(int, input().split())
    weights.append(w)
    values.append(v)

dp = [[0] * (W + 1) for _ in range(n + 1)]

for i in range(1, n + 1):
    for cap in range(W + 1):
        dp[i][cap] = dp[i - 1][cap]

        if weights[i] <= cap:
            dp[i][cap] = max(
                dp[i][cap],
                dp[i - 1][cap - weights[i]] + values[i]
            )

print(dp[n][W])
```

---

# VI. Tối ưu xuống 1 chiều

```python
n, W = map(int, input().split())

dp = [0] * (W + 1)

for _ in range(n):
    weight, value = map(int, input().split())

    for cap in range(W, weight - 1, -1):
        dp[cap] = max(dp[cap], dp[cap - weight] + value)

print(dp[W])
```

---

# VII. Vì sao phải duyệt cap giảm dần?

Nếu duyệt tăng dần, một món có thể bị dùng lại nhiều lần trong cùng lượt, biến thành balo vô hạn.

---

# VIII. Ví dụ minh họa

Balo `W = 7`

| Món | Trọng lượng | Giá trị |
|---|---:|---:|
| 1 | 3 | 4 |
| 2 | 4 | 5 |
| 3 | 2 | 3 |

Có thể chọn món 1 và 2:

- Tổng nặng = 7.
- Tổng giá trị = 9.

---

# IX. Bài tập vận dụng

---

## Bài 1. Knapsack 0/1 cơ bản

---

## Bài 2. Chọn quà

---

## Bài 3. Chọn sách theo khối lượng

---

## Bài 4. Tối ưu 1 chiều

---

## Bài 5. In bảng DP nhỏ để hiểu cách hoạt động

---

# X. Bài tập về nhà

---

## Bài 1. Truy vết danh sách món đã chọn

---

## Bài 2. Balo có đúng tổng trọng lượng W

---

## Bài 3. Đếm số cách đạt một trọng lượng

---

## Bài 4. Chọn đồ có giá trị ít nhất K với trọng lượng nhỏ nhất

---

## Bài 5. So sánh 0/1 knapsack và subset sum

---

# XI. Lỗi học sinh thường gặp

---

## 1. Dùng `dp[i][cap - weight[i]]` thay vì `dp[i-1][...]`

Sai với balo 0/1.

---

## 2. Tối ưu 1 chiều nhưng duyệt cap tăng dần

---

## 3. Không xét trường hợp không lấy món

---

## 4. Nhầm trọng lượng và giá trị

---

## 5. Khai báo bảng quá lớn

---

# XII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Balo 0/1

---

## Đề 2. Chọn đồ dùng tối ưu

---

## Đề 3. Chọn bài toán để đạt điểm tối đa trong thời gian giới hạn

---

## Đề 4. Chọn dự án theo chi phí

---

# XIII. Ghi nhớ cuối bài

- 0/1 knapsack: mỗi món dùng **tối đa một lần**.
- Bản 1 chiều phải duyệt sức chứa **giảm dần**.

---

# XIV. Tóm tắt bài học

```python
for weight, value in items:
    for cap in range(W, weight - 1, -1):
        dp[cap] = max(dp[cap], dp[cap - weight] + value)
```
