# Bài 79. Đường đi ngắn nhất trên đồ thị không trọng số bằng BFS

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu vì sao BFS tìm đường đi ngắn nhất trong đồ thị không trọng số.
- Biết khái niệm khoảng cách theo số cạnh.
- Phân biệt khi nào dùng BFS, khi nào không.

## 2. Về kỹ năng

- Tính `dist[v]` từ đỉnh `S`.
- Tìm khoảng cách từ `S` đến `T`.
- Truy vết đường đi ngắn nhất.

## 3. Về tư duy

- BFS duyệt theo lớp nên lần đầu tới một đỉnh là số bước ít nhất.

---

# II. Đường đi ngắn nhất không trọng số

Trong đồ thị không trọng số:

- Mỗi cạnh có chi phí như nhau.
- Tối ưu theo số cạnh đi qua.

---

# III. Vì sao BFS đúng?

BFS duyệt:

- Lớp 0: đỉnh nguồn.
- Lớp 1: cách 1 cạnh.
- Lớp 2: cách 2 cạnh.

Do đó khi đỉnh `v` được phát hiện lần đầu, đó là đường đi ngắn nhất.

---

# IV. Code khoảng cách tới mọi đỉnh

```python
from collections import deque

n, m = map(int, input().split())
graph = [[] for _ in range(n + 1)]

for _ in range(m):
    u, v = map(int, input().split())
    graph[u].append(v)
    graph[v].append(u)

s = int(input())

dist = [-1] * (n + 1)
queue = deque([s])
dist[s] = 0

while queue:
    u = queue.popleft()

    for v in graph[u]:
        if dist[v] == -1:
            dist[v] = dist[u] + 1
            queue.append(v)

print(*dist[1:])
```

---

# V. Từ S tới T

```python
s, t = map(int, input().split())
```

Sau BFS:

```python
print(dist[t])
```

Nếu `dist[t] = -1`, không có đường đi.

---

# VI. Có truy vết đường đi

Dùng thêm `parent`.

```python
parent = [-1] * (n + 1)
```

Khi mở rộng:

```python
parent[v] = u
```

---

# VII. Bài tập vận dụng

---

## Bài 1. Khoảng cách từ đỉnh 1 tới mọi đỉnh

---

## Bài 2. Khoảng cách giữa S và T

---

## Bài 3. In đường đi ngắn nhất

---

## Bài 4. Số đỉnh có khoảng cách đúng K

---

## Bài 5. Đỉnh xa nhất từ S

---

# VIII. Bài tập về nhà

---

## Bài 1. Tìm đường đi ngắn nhất trong mê cung

---

## Bài 2. Tìm số bước ít nhất trong trò chơi di chuyển trạng thái

---

## Bài 3. Biến số A thành B bằng các phép biến đổi, mỗi phép tính 1 bước

---

## Bài 4. Nhiều nguồn BFS

---

## Bài 5. Tìm khoảng cách gần nhất tới một trạm cứu hộ

---

# IX. Lỗi học sinh thường gặp

---

## 1. Dùng DFS để tìm đường ngắn

---

## 2. Có trọng số mà vẫn dùng BFS thường

---

## 3. Không khởi tạo `dist` bằng `-1`

---

## 4. Không hiểu lần đầu thăm là tối ưu

---

# X. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Truyền tin ít bước nhất

---

## Đề 2. Đường đi trong mê cung

---

## Đề 3. Mạng chuyển tiếp

---

## Đề 4. Robot đi tối thiểu ô

---

# XI. Ghi nhớ cuối bài

BFS dùng cho:

- Đồ thị không trọng số.
- Mọi cạnh cùng chi phí 1.

---

# XII. Tóm tắt bài học

```python
dist[s] = 0

while queue:
    u = queue.popleft()
    for v in graph[u]:
        if dist[v] == -1:
            dist[v] = dist[u] + 1
            queue.append(v)
```
