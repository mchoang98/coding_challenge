# Bài 83. Phát hiện chu trình trong đồ thị

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu chu trình trong:
  - Đồ thị vô hướng.
  - Đồ thị có hướng.
- Biết hai kỹ thuật cơ bản:
  - DFS với cha cho đồ thị vô hướng.
  - DFS màu trạng thái cho đồ thị có hướng.
- Biết có thể phát hiện chu trình có hướng bằng topo.

## 2. Về kỹ năng

- Viết kiểm tra chu trình vô hướng.
- Viết kiểm tra chu trình có hướng.
- Phân biệt hai bài toán.

## 3. Về tư duy

- Không áp dụng một công thức cho mọi loại đồ thị.
- Với đồ thị có hướng, quay lại đỉnh đang trong stack mới là chu trình.

---

# II. Chu trình trong đồ thị vô hướng

Ví dụ:

- 1-2
- 2-3
- 3-1

Tạo thành chu trình.

---

# III. DFS phát hiện chu trình vô hướng

Khi DFS từ `u` sang `v`:

- Nếu `v` chưa thăm: đi tiếp.
- Nếu `v` đã thăm và `v != parent[u]`: có chu trình.

---

# IV. Code Python — vô hướng

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

def dfs(u, parent):
    visited[u] = True

    for v in graph[u]:
        if not visited[v]:
            if dfs(v, u):
                return True
        elif v != parent:
            return True

    return False

has_cycle = False

for u in range(1, n + 1):
    if not visited[u]:
        if dfs(u, -1):
            has_cycle = True
            break

print("YES" if has_cycle else "NO")
```

---

# V. Chu trình trong đồ thị có hướng

Trong đồ thị có hướng, dùng ba trạng thái:

- `0`: chưa thăm.
- `1`: đang thăm.
- `2`: đã xử lý xong.

Nếu đi tới đỉnh có trạng thái `1`, có chu trình.

---

# VI. Code Python — có hướng

```python
import sys
sys.setrecursionlimit(10**6)

n, m = map(int, input().split())
graph = [[] for _ in range(n + 1)]

for _ in range(m):
    u, v = map(int, input().split())
    graph[u].append(v)

state = [0] * (n + 1)

def dfs(u):
    state[u] = 1

    for v in graph[u]:
        if state[v] == 0:
            if dfs(v):
                return True
        elif state[v] == 1:
            return True

    state[u] = 2
    return False

has_cycle = False

for u in range(1, n + 1):
    if state[u] == 0:
        if dfs(u):
            has_cycle = True
            break

print("YES" if has_cycle else "NO")
```

---

# VII. Phát hiện chu trình có hướng bằng topo

Nếu Kahn không lấy ra đủ `N` đỉnh:

- Có chu trình.

---

# VIII. Bài tập vận dụng

---

## Bài 1. Kiểm tra chu trình trong đồ thị vô hướng

---

## Bài 2. Kiểm tra chu trình trong đồ thị có hướng

---

## Bài 3. Dùng topo để kiểm tra có chu trình không

---

## Bài 4. Mạng phụ thuộc công việc có vòng lặp không

---

## Bài 5. Đồ thị liên thông có `M = N-1` có chắc là cây không?

Gợi ý: cần không chu trình.

---

# IX. Bài tập về nhà

---

## Bài 1. In ra một chu trình nếu tồn tại — phân tích hướng làm.

---

## Bài 2. Kiểm tra đầu vào có tạo thành cây không.

---

## Bài 3. Phát hiện chu trình trong quan hệ học trước.

---

## Bài 4. So sánh DFS chu trình và topo.

---

## Bài 5. Nếu đồ thị vô hướng có N đỉnh và M cạnh, khi nào chắc chắn có chu trình?

---

# X. Lỗi học sinh thường gặp

---

## 1. Dùng quy tắc `visited[v]` cho đồ thị có hướng

Sai vì cần phân biệt đỉnh đã xong và đỉnh đang nằm trong stack đệ quy.

---

## 2. Với đồ thị vô hướng quên loại cha

---

## 3. Không duyệt mọi thành phần

---

## 4. Nhầm chu trình với việc có cạnh ngược trong danh sách kề vô hướng

---

# XI. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Kiểm tra vòng phụ thuộc

---

## Đề 2. Kiểm tra cây

---

## Đề 3. Mạng dữ liệu có vòng lặp

---

## Đề 4. Chu trình trong đồ thị có hướng

---

# XII. Ghi nhớ cuối bài

- Vô hướng: `visited[v]` và `v != parent`.
- Có hướng: dùng trạng thái 0-1-2.

---

# XIII. Tóm tắt bài học

```python
elif v != parent:
    return True
```

và:

```python
elif state[v] == 1:
    return True
```
