# Bài 69. Truy vết nghiệm trong quy hoạch động

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu rằng DP không chỉ tính giá trị tối ưu mà còn có thể tìm lại phương án.
- Biết hai cách truy vết phổ biến:
  1. Lưu mảng cha / quyết định.
  2. Đi ngược từ bảng DP.

## 2. Về kỹ năng

- Truy vết đường đi trên lưới.
- Truy vết dãy LIS.
- Truy vết danh sách món đồ trong knapsack.

## 3. Về tư duy

- Khi cập nhật `dp`, hãy nghĩ:
  > “Ta đến trạng thái này từ đâu?”
- Muốn in nghiệm, phải lưu hoặc tái tạo đường đi.

---

# II. Vì sao cần truy vết?

Nhiều đề không chỉ hỏi:

- Giá trị lớn nhất là bao nhiêu?

mà còn hỏi:

- Chọn những phần tử nào?
- Đi theo đường nào?
- In một lời giải cụ thể.

---

# III. Cách 1 — Lưu mảng cha

Ví dụ LIS:

- `parent[i]` lưu vị trí đứng trước `i` trong dãy LIS.

---

# IV. Cách 2 — Đi ngược từ bảng DP

Ví dụ LCS:

- Nếu ký tự bằng nhau, đi chéo.
- Nếu khác nhau, đi lên hoặc sang trái theo ô có giá trị lớn hơn.

---

# V. Ví dụ 1 — Truy vết đường đi tổng lớn nhất trên lưới

```python
m, n = map(int, input().split())
a = [list(map(int, input().split())) for _ in range(m)]

dp = [[0] * n for _ in range(m)]
parent = [[None] * n for _ in range(m)]

dp[0][0] = a[0][0]

for j in range(1, n):
    dp[0][j] = dp[0][j - 1] + a[0][j]
    parent[0][j] = (0, j - 1)

for i in range(1, m):
    dp[i][0] = dp[i - 1][0] + a[i][0]
    parent[i][0] = (i - 1, 0)

for i in range(1, m):
    for j in range(1, n):
        if dp[i - 1][j] >= dp[i][j - 1]:
            dp[i][j] = dp[i - 1][j] + a[i][j]
            parent[i][j] = (i - 1, j)
        else:
            dp[i][j] = dp[i][j - 1] + a[i][j]
            parent[i][j] = (i, j - 1)

path = []
i, j = m - 1, n - 1

while True:
    path.append((i + 1, j + 1))
    if (i, j) == (0, 0):
        break
    i, j = parent[i][j]

path.reverse()

print(dp[m - 1][n - 1])
print(*path)
```

---

# VI. Ví dụ 2 — Truy vết knapsack 0/1

Sau khi có bảng `dp[i][w]`, đi ngược:

- Nếu `dp[i][w] == dp[i-1][w]`:
  - Không lấy món `i`.
- Ngược lại:
  - Có lấy món `i`.
  - Giảm `w` đi `weight[i]`.

```python
chosen = []
cap = W

for i in range(n, 0, -1):
    if dp[i][cap] != dp[i - 1][cap]:
        chosen.append(i)
        cap -= weights[i]

chosen.reverse()
print(*chosen)
```

---

# VII. Ví dụ 3 — Truy vết LIS

Đã học ở bài LIS, dùng mảng `parent`.

---

# VIII. Bài tập vận dụng

---

## Bài 1. Truy vết đường đi tổng lớn nhất trên lưới

---

## Bài 2. Truy vết một LIS

---

## Bài 3. Truy vết món đồ được chọn trong balo 0/1

---

## Bài 4. Truy vết LCS

---

## Bài 5. In chuỗi thao tác trong Edit Distance

---

# IX. Bài tập về nhà

---

## Bài 1. Đường đi chi phí nhỏ nhất và in đường đi

---

## Bài 2. Chọn phần tử không kề nhau và in phần tử được chọn

---

## Bài 3. Truy vết số đồng xu tối thiểu

---

## Bài 4. Nếu có nhiều nghiệm, in nghiệm có thứ tự từ điển nhỏ hơn

---

## Bài 5. So sánh lưu parent và đi ngược từ bảng dp

---

# X. Lỗi học sinh thường gặp

---

## 1. Tính đúng giá trị nhưng không lưu đường đi

---

## 2. Parent bị ghi sai khi có giá trị bằng nhau

---

## 3. Truy vết không đảo kết quả

---

## 4. Truy vết làm thay đổi biến đang còn cần dùng

---

## 5. Không hiểu lựa chọn tại mỗi trạng thái

---

# XI. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. In đường đi tốt nhất

---

## Đề 2. In dãy con tăng dài nhất

---

## Đề 3. In danh sách vật phẩm trong balo

---

## Đề 4. In xâu con chung dài nhất

---

# XII. Ghi nhớ cuối bài

Tính giá trị tối ưu và truy vết nghiệm là hai phần khác nhau.

Muốn truy vết tốt, hãy luôn tự hỏi:

> Trạng thái hiện tại được cập nhật từ đâu?

---

# XIII. Tóm tắt bài học

```python
if choose_this_transition:
    parent[state] = previous_state
```

Sau đó đi ngược từ trạng thái đích về trạng thái đầu.
