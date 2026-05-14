# Bài 76. BFS, DFS trên lưới ô vuông

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Nhìn lưới ô vuông như một đồ thị.
- Biết mỗi ô là một đỉnh.
- Biết các hướng di chuyển thường gặp:
  - 4 hướng.
  - 8 hướng.

## 2. Về kỹ năng

- Duyệt lưới bằng BFS/DFS.
- Đếm số vùng.
- Tìm đường đi trong mê cung.
- Kiểm tra biên an toàn.

## 3. Về tư duy

- Bài lưới thực chất là bài đồ thị.
- Điều quan trọng là:
  - Xác định ô hợp lệ.
  - Đánh dấu visited.
  - Duyệt hàng xóm.

---

# II. Mỗi ô là một đỉnh

Với lưới `m × n`:

- Ô `(i, j)` là một đỉnh.
- Hai ô kề nhau là có cạnh.

---

# III. Di chuyển 4 hướng

```python
directions = [
    (-1, 0),  # lên
    (1, 0),   # xuống
    (0, -1),  # trái
    (0, 1)    # phải
]
```

---

# IV. Kiểm tra ô hợp lệ

```python
def inside(x, y):
    return 0 <= x < m and 0 <= y < n
```

---

# V. DFS trên lưới — đếm số vùng

Giả sử:

- `'#'` là đất.
- `'.'` là nước.

Đếm số vùng đất tách biệt.

```python
import sys
sys.setrecursionlimit(10**6)

m, n = map(int, input().split())
grid = [list(input().strip()) for _ in range(m)]

visited = [[False] * n for _ in range(m)]
directions = [(-1, 0), (1, 0), (0, -1), (0, 1)]

def dfs(x, y):
    visited[x][y] = True

    for dx, dy in directions:
        nx = x + dx
        ny = y + dy

        if 0 <= nx < m and 0 <= ny < n:
            if grid[nx][ny] == '#' and not visited[nx][ny]:
                dfs(nx, ny)

regions = 0

for i in range(m):
    for j in range(n):
        if grid[i][j] == '#' and not visited[i][j]:
            regions += 1
            dfs(i, j)

print(regions)
```

---

# VI. BFS trên lưới

```python
from collections import deque

def bfs(sx, sy):
    queue = deque([(sx, sy)])
    visited[sx][sy] = True

    while queue:
        x, y = queue.popleft()

        for dx, dy in directions:
            nx = x + dx
            ny = y + dy

            if 0 <= nx < m and 0 <= ny < n:
                if grid[nx][ny] == '#' and not visited[nx][ny]:
                    visited[nx][ny] = True
                    queue.append((nx, ny))
```

---

# VII. Tìm đường đi ngắn trong mê cung

Nếu mỗi bước có chi phí như nhau, BFS cho đường đi ngắn nhất.

```python
from collections import deque

dist = [[-1] * n for _ in range(m)]
queue = deque()

dist[sx][sy] = 0
queue.append((sx, sy))

while queue:
    x, y = queue.popleft()

    for dx, dy in directions:
        nx = x + dx
        ny = y + dy

        if 0 <= nx < m and 0 <= ny < n:
            if grid[nx][ny] != '#' and dist[nx][ny] == -1:
                dist[nx][ny] = dist[x][y] + 1
                queue.append((nx, ny))
```

---

# VIII. Di chuyển 8 hướng

```python
directions8 = [
    (-1, -1), (-1, 0), (-1, 1),
    (0, -1),           (0, 1),
    (1, -1),  (1, 0),  (1, 1)
]
```

---

# IX. Bài tập vận dụng

---

## Bài 1. Đếm số đảo

---

## Bài 2. Đếm số vùng ký tự `1`

---

## Bài 3. Tìm đường ngắn nhất trong mê cung

---

## Bài 4. Đếm ô có thể đi tới từ vị trí xuất phát

---

## Bài 5. Đếm số vùng nếu đi 8 hướng

---

# X. Bài tập về nhà

---

## Bài 1. Tìm diện tích vùng lớn nhất

---

## Bài 2. Đếm số hồ nước

---

## Bài 3. Tìm đường đi từ S tới T và in khoảng cách

---

## Bài 4. Tìm số bước ít nhất để thoát khỏi mê cung

---

## Bài 5. Lưới có cửa khóa và chìa khóa — phân tích mở rộng

---

# XI. Lỗi học sinh thường gặp

---

## 1. Quên kiểm tra biên

---

## 2. Nhầm chỉ số hàng và cột

---

## 3. Quên đánh dấu visited

---

## 4. Dùng DFS để tìm đường đi ngắn nhất

---

## 5. Không đọc đề xem đi 4 hướng hay 8 hướng

---

# XII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Đếm đảo

---

## Đề 2. Mê cung

---

## Đề 3. Robot trong kho

---

## Đề 4. Vùng ảnh nhị phân

---

# XIII. Ghi nhớ cuối bài

Lưới = đồ thị ẩn.

Mẫu chuẩn:

1. Kiểm tra ô hợp lệ.
2. Kiểm tra chưa thăm.
3. Kiểm tra ô có được đi không.
4. Đưa vào BFS/DFS.

---

# XIV. Tóm tắt bài học

```python
for dx, dy in directions:
    nx = x + dx
    ny = y + dy

    if 0 <= nx < m and 0 <= ny < n:
        ...
```
