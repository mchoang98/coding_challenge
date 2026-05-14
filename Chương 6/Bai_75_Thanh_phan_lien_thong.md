# Bài 75. Thành phần liên thông và đếm số vùng

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu thành phần liên thông.
- Biết cách đếm số thành phần liên thông bằng BFS hoặc DFS.
- Biết xác định đồ thị có liên thông hay không.

## 2. Về kỹ năng

- Lặp qua mọi đỉnh.
- Khi gặp đỉnh chưa thăm thì mở một lượt BFS/DFS mới.
- Đếm số nhóm tách biệt.

## 3. Về tư duy

- Một lần BFS/DFS từ một đỉnh sẽ thăm hết **một thành phần liên thông**.
- Số lần bắt đầu BFS/DFS mới chính là số thành phần.

---

# II. Thành phần liên thông là gì?

Trong đồ thị vô hướng:

Một thành phần liên thông là một nhóm đỉnh sao cho:

- Hai đỉnh bất kỳ trong nhóm đều có đường đi tới nhau.
- Không có đường nối tới đỉnh bên ngoài nhóm.

---

# III. Ví dụ

Đồ thị có các cạnh:

- 1-2
- 2-3
- 4-5

Ta có:

- Thành phần 1: `{1,2,3}`
- Thành phần 2: `{4,5}`

Số thành phần liên thông = 2.

---

# IV. Thuật toán

## 1. Ý tưởng

- Duyệt `u` từ 1 đến `n`.
- Nếu `u` chưa thăm:
  - Tăng số thành phần.
  - DFS/BFS từ `u`.

---

# V. Code Python dùng DFS

```python
import sys
sys.setrecursionlimit(10**6)

n, m = map(int, input().split())
graph = [[] for _ in range(n + 1)]

for _ in range(m):
    u, v = map(int, input().split())
    graph[u].append(v)
    graph[v].append(u)

visited = [False] * (n + 1)

def dfs(u):
    visited[u] = True
    for v in graph[u]:
        if not visited[v]:
            dfs(v)

components = 0

for u in range(1, n + 1):
    if not visited[u]:
        components += 1
        dfs(u)

print(components)
```

---

# VI. Code Python dùng BFS

```python
from collections import deque

visited = [False] * (n + 1)

def bfs(start):
    queue = deque([start])
    visited[start] = True

    while queue:
        u = queue.popleft()

        for v in graph[u]:
            if not visited[v]:
                visited[v] = True
                queue.append(v)

components = 0

for u in range(1, n + 1):
    if not visited[u]:
        components += 1
        bfs(u)

print(components)
```

---

# VII. Kiểm tra đồ thị liên thông

Đồ thị liên thông khi:

\[
\text{số thành phần liên thông} = 1
\]

---

# VIII. Đếm kích thước từng thành phần

```python
def dfs_size(u):
    visited[u] = True
    size = 1

    for v in graph[u]:
        if not visited[v]:
            size += dfs_size(v)

    return size
```

---

# IX. Bài tập vận dụng

---

## Bài 1. Đếm số thành phần liên thông

---

## Bài 2. Kiểm tra đồ thị có liên thông không

---

## Bài 3. In kích thước từng thành phần

---

## Bài 4. Tìm thành phần lớn nhất

---

## Bài 5. Số cạnh tối thiểu cần thêm để đồ thị liên thông

Gợi ý:

\[
components - 1
\]

---

# X. Bài tập về nhà

---

## Bài 1. Tìm thành phần chứa đỉnh 1

---

## Bài 2. Đếm số cặp đỉnh không thể đi tới nhau

---

## Bài 3. Kiểm tra mạng máy tính có chia nhóm không

---

## Bài 4. Đếm số nhóm học sinh có quen biết gián tiếp

---

## Bài 5. Ghi lại danh sách đỉnh của từng thành phần

---

# XI. Lỗi học sinh thường gặp

---

## 1. Chỉ DFS từ đỉnh 1 rồi nghĩ đã xong

Nếu đồ thị không liên thông, chưa thăm hết.

---

## 2. Tăng biến đếm ở sai vị trí

Chỉ tăng khi bắt đầu một DFS/BFS mới.

---

## 3. Quên reset hoặc dùng sai visited

---

## 4. Dùng cho đồ thị có hướng mà không điều chỉnh khái niệm

---

# XII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Mạng lưới giao thông tách rời

---

## Đề 2. Nhóm bạn bè

---

## Đề 3. Kết nối các đảo

---

## Đề 4. Số đường cần xây thêm

---

# XIII. Ghi nhớ cuối bài

Một lượt DFS/BFS = một thành phần liên thông.

---

# XIV. Tóm tắt bài học

```python
components = 0

for u in range(1, n + 1):
    if not visited[u]:
        components += 1
        dfs(u)
```
