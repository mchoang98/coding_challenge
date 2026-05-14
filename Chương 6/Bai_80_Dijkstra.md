# Bài 80. Thuật toán Dijkstra — đường đi ngắn nhất có trọng số không âm

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu bài toán đường đi ngắn nhất có trọng số.
- Biết điều kiện áp dụng Dijkstra:
  - Trọng số cạnh không âm.
- Hiểu vai trò của priority queue / heap.

## 2. Về kỹ năng

- Cài đặt Dijkstra bằng `heapq`.
- Tính khoảng cách ngắn nhất từ nguồn tới mọi đỉnh.
- Tìm khoảng cách đến một đích cụ thể.

## 3. Về tư duy

- Luôn mở rộng đỉnh có khoảng cách tạm thời nhỏ nhất.
- Nếu trạng thái trong heap đã cũ, bỏ qua.

---

# II. Khi nào BFS không đủ?

Nếu cạnh có trọng số:

- Cạnh A-B giá 100.
- Cạnh A-C giá 1.
- Cạnh C-B giá 1.

BFS có thể chọn ít cạnh hơn nhưng chi phí lớn hơn.  
Khi đó cần Dijkstra.

---

# III. Điều kiện của Dijkstra

Dijkstra dùng đúng khi:

\[
w \ge 0
\]

với mọi cạnh.

Nếu có cạnh âm, Dijkstra không đảm bảo đúng.

---

# IV. Ý tưởng

- `dist[u]` = khoảng cách tốt nhất hiện biết từ nguồn đến `u`.
- Bắt đầu:
  - `dist[s] = 0`.
  - Các đỉnh khác = vô cực.
- Mỗi lần lấy đỉnh có `dist` nhỏ nhất ra khỏi heap.
- Relax các cạnh đi ra từ nó.

---

# V. Relax cạnh

Với cạnh:

\[
u \rightarrow v \text{ có trọng số } w
\]

Nếu:

\[
dist[v] > dist[u] + w
\]

thì cập nhật:

\[
dist[v] = dist[u] + w
\]

---

# VI. Code Python

```python
import heapq

n, m = map(int, input().split())
graph = [[] for _ in range(n + 1)]

for _ in range(m):
    u, v, w = map(int, input().split())
    graph[u].append((v, w))
    graph[v].append((u, w))  # nếu vô hướng

s = int(input())

INF = 10**18
dist = [INF] * (n + 1)
dist[s] = 0

pq = [(0, s)]

while pq:
    current_dist, u = heapq.heappop(pq)

    if current_dist != dist[u]:
        continue

    for v, w in graph[u]:
        if dist[v] > dist[u] + w:
            dist[v] = dist[u] + w
            heapq.heappush(pq, (dist[v], v))

for i in range(1, n + 1):
    if dist[i] == INF:
        print(-1, end=" ")
    else:
        print(dist[i], end=" ")
```

---

# VII. Truy vết đường đi trong Dijkstra

Khi cập nhật:

```python
parent[v] = u
```

Sau đó truy ngược giống BFS.

---

# VIII. Độ phức tạp

Với heap:

\[
O((N + M)\log N)
\]

---

# IX. Bài tập vận dụng

---

## Bài 1. Khoảng cách ngắn nhất từ S đến mọi đỉnh

---

## Bài 2. Khoảng cách từ S tới T

---

## Bài 3. In đường đi ngắn nhất

---

## Bài 4. Đồ thị có hướng trọng số không âm

---

## Bài 5. Đỉnh không thể tới thì in `-1`

---

# X. Bài tập về nhà

---

## Bài 1. Bản đồ thành phố có chi phí di chuyển

---

## Bài 2. Tìm đường rẻ nhất

---

## Bài 3. Truy vết hành trình ngắn nhất

---

## Bài 4. So sánh BFS và Dijkstra trên đồ thị trọng số 1

---

## Bài 5. Nêu ví dụ Dijkstra sai khi có cạnh âm

---

# XI. Lỗi học sinh thường gặp

---

## 1. Dùng Dijkstra với cạnh âm

---

## 2. Không bỏ trạng thái cũ trong heap

---

## 3. Nhầm `u, v, w`

---

## 4. Với đồ thị có hướng lại thêm cạnh ngược

---

## 5. Dùng `visited` không cẩn thận khiến bỏ lỡ cập nhật

---

# XII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Đường ngắn nhất giữa các thành phố

---

## Đề 2. Hệ thống đường có chi phí

---

## Đề 3. Giao hàng rẻ nhất

---

## Đề 4. Robot đi trên mạng trọng số

---

# XIII. Ghi nhớ cuối bài

- Không trọng số → BFS.
- Trọng số không âm → Dijkstra.
- Mỗi lần lấy đỉnh có khoảng cách nhỏ nhất ra xét.

---

# XIV. Tóm tắt bài học

```python
if dist[v] > dist[u] + w:
    dist[v] = dist[u] + w
    heapq.heappush(pq, (dist[v], v))
```
