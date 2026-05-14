# Bài 73. Duyệt đồ thị bằng BFS

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu thuật toán BFS:
  - Breadth-First Search.
  - Duyệt theo từng lớp.
- Biết BFS dùng hàng đợi `queue`.
- Nắm được khi nào BFS phù hợp.

## 2. Về kỹ năng

- Viết BFS cơ bản bằng Python.
- Đánh dấu đỉnh đã thăm.
- Duyệt đồ thị từ một đỉnh xuất phát.

## 3. Về tư duy

- BFS lan rộng từ gần đến xa.
- Trong đồ thị không trọng số, BFS là nền tảng tìm đường đi ngắn nhất.

---

# II. Ý tưởng BFS

## 1. Trực giác

BFS giống như sóng nước lan ra:

- Thăm đỉnh xuất phát trước.
- Sau đó thăm các đỉnh cách 1 cạnh.
- Tiếp theo thăm các đỉnh cách 2 cạnh.
- Cứ tiếp tục như vậy.

---

# III. Cấu trúc dữ liệu dùng trong BFS

BFS dùng:

- **Queue** — hàng đợi FIFO.

Nguyên tắc:

- Vào trước.
- Ra trước.

---

# IV. Thuật toán BFS

## 1. Các bước

1. Đưa đỉnh bắt đầu vào queue.
2. Đánh dấu đã thăm.
3. Trong khi queue chưa rỗng:
   - Lấy một đỉnh ra.
   - Duyệt các hàng xóm chưa thăm.
   - Đánh dấu.
   - Đưa vào queue.

---

# V. Code Python cơ bản

```python
from collections import deque

n, m = map(int, input().split())
graph = [[] for _ in range(n + 1)]

for _ in range(m):
    u, v = map(int, input().split())
    graph[u].append(v)
    graph[v].append(u)

start = int(input())

visited = [False] * (n + 1)
queue = deque()

visited[start] = True
queue.append(start)

order = []

while queue:
    u = queue.popleft()
    order.append(u)

    for v in graph[u]:
        if not visited[v]:
            visited[v] = True
            queue.append(v)

print(*order)
```

---

# VI. Ví dụ minh họa

Đồ thị:

- 1-2
- 1-3
- 2-4
- 3-5

BFS từ 1 thường duyệt:

```text
1 2 3 4 5
```

---

# VII. Vì sao phải đánh dấu khi đưa vào queue?

Nếu chờ tới lúc lấy ra mới đánh dấu, một đỉnh có thể bị thêm vào queue nhiều lần.

Nên dùng:

```python
visited[v] = True
queue.append(v)
```

ngay khi phát hiện `v`.

---

# VIII. Ứng dụng của BFS

## 1. Kiểm tra có đường đi không

---

## 2. Đếm số đỉnh liên thông với start

---

## 3. Tính khoảng cách ngắn nhất trên đồ thị không trọng số

---

## 4. Tìm đường đi trong mê cung

---

# IX. Tính khoảng cách bằng BFS

```python
from collections import deque

dist = [-1] * (n + 1)
queue = deque()

dist[start] = 0
queue.append(start)

while queue:
    u = queue.popleft()

    for v in graph[u]:
        if dist[v] == -1:
            dist[v] = dist[u] + 1
            queue.append(v)
```

---

# X. Bài tập vận dụng

---

## Bài 1. In thứ tự BFS từ đỉnh 1

---

## Bài 2. Đếm số đỉnh đi tới được từ đỉnh S

---

## Bài 3. Kiểm tra T có đi được từ S hay không

---

## Bài 4. Tính khoảng cách ngắn nhất từ S tới mọi đỉnh

---

## Bài 5. Tìm khoảng cách từ S tới T

---

# XI. Bài tập về nhà

---

## Bài 1. BFS trên đồ thị có hướng

---

## Bài 2. Đếm số đỉnh cách S đúng K cạnh

---

## Bài 3. Kiểm tra một mạng máy tính có thông suốt từ máy 1 không

---

## Bài 4. Tìm đỉnh gần nhất trong tập đỉnh đặc biệt

---

## Bài 5. Ghi lại cha của từng đỉnh trong BFS

---

# XII. Lỗi học sinh thường gặp

---

## 1. Dùng list thường rồi `pop(0)`

`pop(0)` chậm. Nên dùng:

```python
deque
```

---

## 2. Đánh dấu visited quá muộn

---

## 3. Quên khởi tạo visited cho đỉnh xuất phát

---

## 4. Nhầm BFS với DFS

---

## 5. Không xét đồ thị không liên thông

---

# XIII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Truyền tin trong mạng

---

## Đề 2. Khoảng cách ngắn nhất trong mạng không trọng số

---

## Đề 3. Robot đi qua phòng

---

## Đề 4. Mạng bạn bè

---

# XIV. Ghi nhớ cuối bài

- BFS = duyệt theo lớp.
- BFS dùng `queue`.
- Với đồ thị không trọng số, BFS tìm đường ngắn nhất theo số cạnh.

---

# XV. Tóm tắt bài học

```python
queue = deque([start])
visited[start] = True

while queue:
    u = queue.popleft()
    for v in graph[u]:
        if not visited[v]:
            visited[v] = True
            queue.append(v)
```
