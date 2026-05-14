# Bài 77. Tìm đường đi và truy vết đường đi trong đồ thị

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu khái niệm lưu cha `parent`.
- Biết dùng BFS để:
  - Tìm đường đi ngắn nhất trong đồ thị không trọng số.
  - Truy vết một đường đi cụ thể.
- Hiểu vì sao cần đảo ngược đường đi sau khi truy vết.

## 2. Về kỹ năng

- Lưu `parent[v] = u`.
- Truy vết từ đích về nguồn.
- In ra đường đi đúng thứ tự.

## 3. Về tư duy

- Khi thăm một đỉnh mới, hãy ghi nhớ:
  > Ta đi tới đây từ đâu?

---

# II. Đề bài mẫu

Cho đồ thị không trọng số, hai đỉnh `S` và `T`.

Hãy:

1. Kiểm tra có đường đi từ `S` đến `T` không.
2. Nếu có, in ra một đường đi ngắn nhất.

---

# III. Ý tưởng

Dùng BFS từ `S`.

Khi phát hiện đỉnh `v` từ đỉnh `u`:

```python
parent[v] = u
```

---

# IV. Code Python đầy đủ

```python
from collections import deque

n, m = map(int, input().split())
graph = [[] for _ in range(n + 1)]

for _ in range(m):
    u, v = map(int, input().split())
    graph[u].append(v)
    graph[v].append(u)

s, t = map(int, input().split())

dist = [-1] * (n + 1)
parent = [-1] * (n + 1)

queue = deque([s])
dist[s] = 0

while queue:
    u = queue.popleft()

    for v in graph[u]:
        if dist[v] == -1:
            dist[v] = dist[u] + 1
            parent[v] = u
            queue.append(v)

if dist[t] == -1:
    print("NO PATH")
else:
    path = []
    cur = t

    while cur != -1:
        path.append(cur)
        cur = parent[cur]

    path.reverse()

    print(dist[t])
    print(*path)
```

---

# V. Ví dụ minh họa

Nếu đường đi từ 1 đến 6 được lưu:

- `parent[6] = 4`
- `parent[4] = 2`
- `parent[2] = 1`

Truy ngược:

```text
6 -> 4 -> 2 -> 1
```

Đảo lại:

```text
1 -> 2 -> 4 -> 6
```

---

# VI. Truy vết trên lưới

Thay vì lưu cha là đỉnh số, ta lưu tọa độ:

```python
parent[nx][ny] = (x, y)
```

---

# VII. Bài tập vận dụng

---

## Bài 1. In đường đi từ S đến T trong đồ thị

---

## Bài 2. In đường đi ngắn nhất bằng BFS

---

## Bài 3. Nếu không có đường đi, in `-1`

---

## Bài 4. Truy vết đường đi trong mê cung

---

## Bài 5. In số đỉnh trên đường đi

---

# VIII. Bài tập về nhà

---

## Bài 1. In một đường đi DFS bất kỳ từ S tới T

---

## Bài 2. In đường đi ngắn nhất trong mạng không trọng số

---

## Bài 3. Tìm nhiều đích gần nhất

---

## Bài 4. Truy vết đường đi ngắn nhất trên lưới

---

## Bài 5. Tìm đường đi có ít bước nhất và in chuỗi hướng `UDLR`

---

# IX. Lỗi học sinh thường gặp

---

## 1. Ghi `parent` quá muộn

---

## 2. Không gán cha của đỉnh xuất phát

Thường:

```python
parent[s] = -1
```

---

## 3. Quên đảo đường đi

---

## 4. Truy vết trong khi đích không tới được

---

## 5. Dùng DFS nhưng lại tưởng đường đi tìm được là ngắn nhất

---

# X. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Đường đi trong mạng máy tính

---

## Đề 2. Robot tìm lối ra

---

## Đề 3. Đường ngắn nhất giữa hai đỉnh

---

## Đề 4. In hành trình qua các phòng

---

# XI. Ghi nhớ cuối bài

Muốn in đường đi:

1. Dùng BFS/DFS.
2. Lưu `parent`.
3. Truy ngược từ đích.
4. Đảo kết quả.

---

# XII. Tóm tắt bài học

```python
parent[v] = u
```

và:

```python
while cur != -1:
    path.append(cur)
    cur = parent[cur]

path.reverse()
```
