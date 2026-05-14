# Bài 81. Thuật toán Floyd-Warshall — khoảng cách mọi cặp đỉnh

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu bài toán đường đi ngắn nhất giữa mọi cặp đỉnh.
- Biết thuật toán Floyd-Warshall.
- Nắm ý nghĩa của ba vòng lặp:
  - Đỉnh trung gian `k`.
  - Đỉnh đầu `i`.
  - Đỉnh cuối `j`.

## 2. Về kỹ năng

- Tạo ma trận khoảng cách.
- Cập nhật khoảng cách mọi cặp.
- Xử lý đỉnh không nối trực tiếp.

## 3. Về tư duy

- Từng bước cho phép dùng thêm đỉnh trung gian.
- `dist[i][j]` có thể tốt hơn nếu đi qua `k`.

---

# II. Khi nào dùng Floyd?

Dùng Floyd-Warshall khi:

- `N` không quá lớn.
- Cần khoảng cách giữa mọi cặp đỉnh.
- Có thể chấp nhận:
  \[
  O(N^3)
  \]

---

# III. Trạng thái

`dist[i][j]` là khoảng cách ngắn nhất hiện biết từ `i` đến `j`.

---

# IV. Khởi tạo

- `dist[i][i] = 0`
- Nếu có cạnh `u → v` trọng số `w`:
  - `dist[u][v] = min(dist[u][v], w)`
- Nếu không có cạnh:
  - `INF`

---

# V. Công thức cập nhật

Khi cho phép đi qua đỉnh `k`:

\[
dist[i][j] = \min(dist[i][j], dist[i][k] + dist[k][j])
\]

---

# VI. Code Python

```python
n, m = map(int, input().split())
INF = 10**18

dist = [[INF] * (n + 1) for _ in range(n + 1)]

for i in range(1, n + 1):
    dist[i][i] = 0

for _ in range(m):
    u, v, w = map(int, input().split())
    dist[u][v] = min(dist[u][v], w)
    # dist[v][u] = min(dist[v][u], w)  # nếu vô hướng

for k in range(1, n + 1):
    for i in range(1, n + 1):
        for j in range(1, n + 1):
            if dist[i][k] + dist[k][j] < dist[i][j]:
                dist[i][j] = dist[i][k] + dist[k][j]

for i in range(1, n + 1):
    row = []
    for j in range(1, n + 1):
        row.append(-1 if dist[i][j] == INF else dist[i][j])
    print(*row)
```

---

# VII. Ví dụ ý tưởng

Nếu đi trực tiếp từ 1 tới 3 tốn 10, nhưng:

- 1 → 2 tốn 3.
- 2 → 3 tốn 4.

thì:

\[
dist[1][3] = 7
\]

tốt hơn 10.

---

# VIII. Phát hiện chu trình âm

Sau Floyd:

Nếu tồn tại `i` sao cho:

\[
dist[i][i] < 0
\]

thì có chu trình âm.

---

# IX. Bài tập vận dụng

---

## Bài 1. Tính ma trận khoảng cách

---

## Bài 2. Trả lời nhiều truy vấn khoảng cách `u, v`

---

## Bài 3. Tìm cặp đỉnh xa nhau nhất nhưng vẫn có đường đi

---

## Bài 4. Kiểm tra có chu trình âm không

---

## Bài 5. Tính transitive closure ở dạng reachability

---

# X. Bài tập về nhà

---

## Bài 1. Tối ưu nhập nhiều cạnh trùng nhau

---

## Bài 2. Tìm đường đi nhỏ nhất giữa mọi cặp trong đồ thị vô hướng

---

## Bài 3. So sánh Floyd với chạy Dijkstra từ mọi đỉnh

---

## Bài 4. Đếm số cặp đỉnh đi được tới nhau

---

## Bài 5. Cập nhật ma trận kề thành ma trận khoảng cách

---

# XI. Lỗi học sinh thường gặp

---

## 1. Không gán `dist[i][i] = 0`

---

## 2. Không lấy `min` nếu có nhiều cạnh trùng

---

## 3. Dùng Floyd cho `N` quá lớn

---

## 4. Nhầm thứ tự vòng lặp

`k` phải ở ngoài cùng.

---

## 5. Cộng `INF + INF` mà không hiểu ý nghĩa

Trong Python không tràn số nhưng cần hiểu bản chất.

---

# XII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Bảng khoảng cách mọi thành phố

---

## Đề 2. Hệ thống giao thông nhỏ

---

## Đề 3. Truy vấn quãng đường nhiều lần

---

## Đề 4. Chu trình âm

---

# XIII. Ghi nhớ cuối bài

Floyd = mọi cặp đỉnh.

Công thức:

\[
dist[i][j] = \min(dist[i][j], dist[i][k] + dist[k][j])
\]

---

# XIV. Tóm tắt bài học

```python
for k in range(1, n + 1):
    for i in range(1, n + 1):
        for j in range(1, n + 1):
            dist[i][j] = min(dist[i][j], dist[i][k] + dist[k][j])
```
