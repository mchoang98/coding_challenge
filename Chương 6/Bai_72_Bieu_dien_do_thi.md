# Bài 72. Biểu diễn đồ thị bằng danh sách kề và ma trận kề

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Biết hai cách biểu diễn đồ thị phổ biến:
  - Ma trận kề.
  - Danh sách kề.
- Hiểu ưu nhược điểm của từng cách.
- Biết cách nhập đồ thị từ dữ liệu cạnh.

## 2. Về kỹ năng

- Tạo danh sách kề trong Python.
- Tạo ma trận kề.
- Thêm cạnh đúng cho:
  - Đồ thị vô hướng.
  - Đồ thị có hướng.
  - Đồ thị có trọng số.

## 3. Về tư duy

- Chọn cấu trúc dữ liệu phù hợp với giới hạn đề.
- Không dùng ma trận kề khi `N` rất lớn và cạnh thưa.

---

# II. Vì sao cần biểu diễn đồ thị?

Máy tính không “nhìn thấy” hình vẽ đồ thị.  
Ta phải lưu đồ thị bằng cấu trúc dữ liệu.

---

# III. Ma trận kề

## 1. Ý tưởng

Với đồ thị có `N` đỉnh, tạo bảng `N × N`.

- `matrix[u][v] = 1` nếu có cạnh từ `u` đến `v`.
- `matrix[u][v] = 0` nếu không có cạnh.

---

## 2. Ví dụ

Đồ thị vô hướng có cạnh:

- 1-2
- 1-3
- 2-4

Ma trận kề:

|   | 1 | 2 | 3 | 4 |
|---|---|---|---|---|
| 1 | 0 | 1 | 1 | 0 |
| 2 | 1 | 0 | 0 | 1 |
| 3 | 1 | 0 | 0 | 0 |
| 4 | 0 | 1 | 0 | 0 |

---

## 3. Code Python

```python
n, m = map(int, input().split())

matrix = [[0] * (n + 1) for _ in range(n + 1)]

for _ in range(m):
    u, v = map(int, input().split())
    matrix[u][v] = 1
    matrix[v][u] = 1  # đồ thị vô hướng
```

---

## 4. Ưu điểm

- Kiểm tra có cạnh `u-v` hay không rất nhanh:
  $O(1)$

---

## 5. Nhược điểm

- Tốn bộ nhớ:
  $O(N^2)$
- Không phù hợp với đồ thị lớn nhưng ít cạnh.

---

# IV. Danh sách kề

## 1. Ý tưởng

Với mỗi đỉnh, lưu danh sách các đỉnh nối trực tiếp với nó.

---

## 2. Ví dụ

Cạnh:

- 1-2
- 1-3
- 2-4

Danh sách kề:

```text
1: 2, 3
2: 1, 4
3: 1
4: 2
```

---

## 3. Code Python

```python
n, m = map(int, input().split())

graph = [[] for _ in range(n + 1)]

for _ in range(m):
    u, v = map(int, input().split())
    graph[u].append(v)
    graph[v].append(u)  # vô hướng
```

---

## 4. Ưu điểm

- Tiết kiệm bộ nhớ:
  $O(N + M)$
- Rất phù hợp cho BFS, DFS.

---

## 5. Nhược điểm

- Kiểm tra trực tiếp `u-v` có cạnh hay không chậm hơn ma trận.

---

# V. Đồ thị có hướng

Nếu có cạnh:

$u \rightarrow v$

thì chỉ thêm:

```python
graph[u].append(v)
```

Không thêm ngược lại.

---

# VI. Đồ thị có trọng số

Nếu cạnh có dạng:

$u \leftrightarrow v, \text{ trọng số } w$

thì lưu cặp:

```python
graph[u].append((v, w))
graph[v].append((u, w))
```

Ví dụ:

```python
n, m = map(int, input().split())
graph = [[] for _ in range(n + 1)]

for _ in range(m):
    u, v, w = map(int, input().split())
    graph[u].append((v, w))
    graph[v].append((u, w))
```

---

# VII. So sánh hai cách biểu diễn

| Tiêu chí | Ma trận kề | Danh sách kề |
|---|---|---|
| Bộ nhớ | `O(N²)` | `O(N+M)` |
| Kiểm tra có cạnh | `O(1)` | `O(deg(u))` |
| Duyệt hàng xóm | `O(N)` | `O(deg(u))` |
| Dùng cho BFS/DFS | Được | Rất phù hợp |
| Dùng cho Floyd | Rất phù hợp | Không thuận tiện |

---

# VIII. Cách chọn biểu diễn

## 1. Dùng danh sách kề khi

- `N` lớn.
- `M` không quá dày.
- Làm BFS, DFS, Dijkstra.

---

## 2. Dùng ma trận kề khi

- `N` nhỏ.
- Cần Floyd-Warshall.
- Cần kiểm tra cạnh nhanh.

---

# IX. Bài tập vận dụng

---

## Bài 1. Tạo danh sách kề

Nhập `N, M` và các cạnh vô hướng.  
In ra danh sách kề từng đỉnh.

---

## Bài 2. Tạo ma trận kề

Nhập đồ thị vô hướng và in ma trận.

---

## Bài 3. Đồ thị có hướng

Nhập các cạnh `u → v`.  
Tạo danh sách kề.

---

## Bài 4. Đồ thị có trọng số

Nhập `u, v, w`.  
Tạo danh sách kề có trọng số.

---

## Bài 5. Tính bậc của từng đỉnh từ danh sách kề.

---

# X. Bài tập về nhà

---

## Bài 1. Chuyển danh sách cạnh sang ma trận kề.

---

## Bài 2. Chuyển ma trận kề sang danh sách kề.

---

## Bài 3. Với đồ thị có hướng, tính:
- Bậc vào.
- Bậc ra.

---

## Bài 4. Tìm xem cạnh `(u, v)` có tồn tại không.

---

## Bài 5. So sánh bộ nhớ giữa ma trận và danh sách kề khi:
- `N = 100000`
- `M = 200000`

---

# XI. Lỗi học sinh thường gặp

---

## 1. Với đồ thị vô hướng nhưng chỉ thêm một chiều

---

## 2. Với đồ thị có hướng lại thêm cả cạnh ngược

---

## 3. Nhầm thứ tự `(v, w)` thành `(w, v)`

---

## 4. Tạo ma trận quá lớn gây tràn bộ nhớ

---

## 5. Không chọn cách biểu diễn phù hợp với đề

---

# XII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Xây dựng mạng máy tính

---

## Đề 2. Danh sách hàng xóm

---

## Đề 3. Bản đồ thành phố có chi phí đường đi

---

## Đề 4. Quan hệ phụ thuộc có hướng

---

# XIII. Ghi nhớ cuối bài

- BFS/DFS thường dùng **danh sách kề**.
- Floyd thường dùng **ma trận**.
- Đồ thị vô hướng phải thêm cạnh hai chiều.

---

# XIV. Tóm tắt bài học

```python
graph = [[] for _ in range(n + 1)]

for _ in range(m):
    u, v = map(int, input().split())
    graph[u].append(v)
    graph[v].append(u)
```
