# Bài 74. Duyệt đồ thị bằng DFS

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu DFS:
  - Depth-First Search.
  - Duyệt theo chiều sâu.
- Biết hai cách cài đặt:
  - Đệ quy.
  - Stack tự quản lý.

## 2. Về kỹ năng

- Viết DFS cơ bản.
- Đếm đỉnh thăm được.
- Kiểm tra liên thông.

## 3. Về tư duy

- DFS đi sâu nhất có thể rồi quay lui.
- DFS đặc biệt phù hợp cho:
  - Thành phần liên thông.
  - Chu trình.
  - Đồ thị có hướng.
  - Duyệt cây.

---

# II. Ý tưởng DFS

Từ một đỉnh:

1. Thăm đỉnh đó.
2. Chọn một hàng xóm chưa thăm.
3. Đi tiếp thật sâu.
4. Khi không đi tiếp được thì quay lui.

---

# III. DFS đệ quy

```python
def dfs(u):
    visited[u] = True

    for v in graph[u]:
        if not visited[v]:
            dfs(v)
```

---

# IV. Code Python đầy đủ

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
order = []

def dfs(u):
    visited[u] = True
    order.append(u)

    for v in graph[u]:
        if not visited[v]:
            dfs(v)

start = int(input())
dfs(start)

print(*order)
```

---

# V. DFS dùng stack

```python
stack = [start]
visited = [False] * (n + 1)

while stack:
    u = stack.pop()

    if visited[u]:
        continue

    visited[u] = True
    print(u, end=" ")

    for v in graph[u]:
        if not visited[v]:
            stack.append(v)
```

---

# VI. So sánh BFS và DFS

| Tiêu chí | BFS | DFS |
|---|---|---|
| Cấu trúc | Queue | Stack / đệ quy |
| Kiểu duyệt | Theo lớp | Theo chiều sâu |
| Đường ngắn nhất không trọng số | Có | Không đảm bảo |
| Đếm thành phần liên thông | Có | Có |
| Phát hiện chu trình | Có thể | Rất hay dùng |

---

# VII. Ứng dụng DFS

## 1. Đếm thành phần liên thông

---

## 2. Kiểm tra có đường đi hay không

---

## 3. Phát hiện chu trình

---

## 4. Duyệt cây

---

## 5. Sắp xếp topo bằng DFS

---

# VIII. Bài tập vận dụng

---

## Bài 1. In thứ tự DFS từ đỉnh 1

---

## Bài 2. Đếm số đỉnh liên thông với đỉnh S

---

## Bài 3. Kiểm tra T có đi được từ S không

---

## Bài 4. Viết DFS không đệ quy

---

## Bài 5. Duyệt đồ thị có hướng

---

# IX. Bài tập về nhà

---

## Bài 1. Tính kích thước thành phần chứa đỉnh 1

---

## Bài 2. Tìm tất cả đỉnh trong cùng thành phần với S

---

## Bài 3. Viết DFS trên lưới

---

## Bài 4. Dùng DFS để đếm số vùng ký tự '#'

---

## Bài 5. So sánh kết quả duyệt BFS và DFS trên cùng một đồ thị.

---

# X. Lỗi học sinh thường gặp

---

## 1. Quên `sys.setrecursionlimit`

---

## 2. Gọi DFS lại trên đỉnh đã thăm

---

## 3. Trong đồ thị vô hướng bị quay lại cha liên tục

Giải bằng `visited`.

---

## 4. Nhầm thứ tự DFS phụ thuộc thứ tự danh sách kề

---

## 5. Dùng DFS để tìm đường ngắn nhất không trọng số

Sai trong nhiều trường hợp.

---

# XI. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Đếm số đảo

---

## Đề 2. Mạng liên thông

---

## Đề 3. Kiểm tra đường đi

---

## Đề 4. Duyệt cây

---

# XII. Ghi nhớ cuối bài

- DFS = đi sâu trước.
- DFS dùng đệ quy hoặc stack.
- DFS là một trong những công cụ quan trọng nhất của đồ thị.

---

# XIII. Tóm tắt bài học

```python
def dfs(u):
    visited[u] = True
    for v in graph[u]:
        if not visited[v]:
            dfs(v)
```
