# Bài 82. Sắp xếp topo và đồ thị có hướng không chu trình

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu sắp xếp topo là gì.
- Biết nó chỉ áp dụng cho DAG:
  - Directed Acyclic Graph.
  - Đồ thị có hướng không chu trình.
- Hiểu ý nghĩa trong bài toán phụ thuộc công việc.

## 2. Về kỹ năng

- Tính bậc vào.
- Cài đặt Kahn’s Algorithm bằng queue.
- Kiểm tra đồ thị có chu trình thông qua topo.

## 3. Về tư duy

- Công việc không có điều kiện tiên quyết được làm trước.
- Sau khi làm xong một việc, giảm yêu cầu phụ thuộc của các việc sau.

---

# II. Ví dụ thực tế

Có các công việc:

- A phải xong trước C.
- B phải xong trước C.
- C phải xong trước D.

Một thứ tự hợp lệ:

```text
A B C D
```

hoặc:

```text
B A C D
```

---

# III. Đồ thị topo

- Mỗi công việc là một đỉnh.
- Cạnh `u → v` nghĩa là `u` phải làm trước `v`.

---

# IV. Bậc vào

`indegree[v]` = số cạnh đi vào `v`.

Một đỉnh có `indegree = 0`:

- Không phụ thuộc vào công việc nào khác.
- Có thể xử lý ngay.

---

# V. Thuật toán Kahn

## Các bước

1. Tính `indegree`.
2. Đưa mọi đỉnh có `indegree = 0` vào queue.
3. Lấy từng đỉnh ra:
   - Đưa vào thứ tự topo.
   - Với mỗi cạnh `u → v`:
     - Giảm `indegree[v]`.
     - Nếu `indegree[v] = 0`, đưa vào queue.
4. Nếu số đỉnh lấy ra < `N`, đồ thị có chu trình.

---

# VI. Code Python

```python
from collections import deque

n, m = map(int, input().split())
graph = [[] for _ in range(n + 1)]
indegree = [0] * (n + 1)

for _ in range(m):
    u, v = map(int, input().split())
    graph[u].append(v)
    indegree[v] += 1

queue = deque()

for u in range(1, n + 1):
    if indegree[u] == 0:
        queue.append(u)

topo = []

while queue:
    u = queue.popleft()
    topo.append(u)

    for v in graph[u]:
        indegree[v] -= 1
        if indegree[v] == 0:
            queue.append(v)

if len(topo) < n:
    print("CYCLE")
else:
    print(*topo)
```

---

# VII. Ví dụ minh họa

Cạnh:

- 1 → 3
- 2 → 3
- 3 → 4

Bậc vào:

- 1: 0
- 2: 0
- 3: 2
- 4: 1

Topo có thể là:

```text
1 2 3 4
```

---

# VIII. Ứng dụng

## 1. Lập lịch công việc

---

## 2. Thứ tự học môn học

---

## 3. Build system

---

## 4. Phát hiện phụ thuộc vòng

---

# IX. Bài tập vận dụng

---

## Bài 1. In một thứ tự topo

---

## Bài 2. Kiểm tra có tồn tại thứ tự hợp lệ không

---

## Bài 3. Lập lịch môn học

---

## Bài 4. Phụ thuộc công việc

---

## Bài 5. Topo với nhiều đỉnh indegree 0

---

# X. Bài tập về nhà

---

## Bài 1. Nếu có nhiều thứ tự, in thứ tự từ điển nhỏ nhất

Gợi ý: dùng heap.

---

## Bài 2. Đếm số đỉnh có thể bắt đầu ngay.

---

## Bài 3. Tìm lớp học theo từng học kỳ.

---

## Bài 4. Kiểm tra chu trình bằng topo.

---

## Bài 5. So sánh topo bằng DFS và topo bằng Kahn.

---

# XI. Lỗi học sinh thường gặp

---

## 1. Áp dụng topo cho đồ thị vô hướng

---

## 2. Không tính bậc vào đúng

---

## 3. Không kiểm tra số đỉnh xuất hiện trong kết quả

---

## 4. Nhầm cạnh `u → v`

---

# XII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Thứ tự môn học

---

## Đề 2. Quy trình sản xuất

---

## Đề 3. Build package

---

## Đề 4. Xếp thứ tự công việc

---

# XIII. Ghi nhớ cuối bài

Topo chỉ dùng được cho:

\[
\text{DAG}
\]

Nếu topo không lấy đủ `N` đỉnh, đồ thị có chu trình.

---

# XIV. Tóm tắt bài học

```python
if indegree[u] == 0:
    queue.append(u)
```

và:

```python
indegree[v] -= 1
```
