# Bài 78. Cây: khái niệm, duyệt cây, cha - con - độ sâu

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu cây là một đồ thị đặc biệt.
- Biết các khái niệm:
  - Gốc.
  - Cha.
  - Con.
  - Lá.
  - Độ sâu.
  - Kích thước cây con.
- Biết cây có `N` đỉnh thì có `N-1` cạnh.

## 2. Về kỹ năng

- Duyệt cây bằng DFS.
- Tính:
  - Độ sâu.
  - Cha của mỗi đỉnh.
  - Kích thước cây con.

## 3. Về tư duy

- Cây không có chu trình.
- Chọn một đỉnh làm gốc để biến cây vô hướng thành cấu trúc cha - con.

---

# II. Cây là gì?

Một cây là đồ thị vô hướng:

- Liên thông.
- Không có chu trình.

---

# III. Tính chất quan trọng

Với cây có `N` đỉnh:

\[
M = N - 1
\]

trong đó `M` là số cạnh.

---

# IV. Gốc cây

Nếu chọn một đỉnh làm gốc, ta có:

- Cha.
- Con.
- Cấp độ / độ sâu.

Ví dụ thường chọn đỉnh 1 làm gốc.

---

# V. DFS trên cây

```python
def dfs(u, p):
    parent[u] = p

    for v in tree[u]:
        if v != p:
            depth[v] = depth[u] + 1
            dfs(v, u)
```

---

# VI. Code Python đầy đủ

```python
import sys
sys.setrecursionlimit(10**6)

n = int(input())
tree = [[] for _ in range(n + 1)]

for _ in range(n - 1):
    u, v = map(int, input().split())
    tree[u].append(v)
    tree[v].append(u)

parent = [0] * (n + 1)
depth = [0] * (n + 1)

def dfs(u, p):
    parent[u] = p

    for v in tree[u]:
        if v != p:
            depth[v] = depth[u] + 1
            dfs(v, u)

dfs(1, 0)

print("Parent:", *parent[1:])
print("Depth:", *depth[1:])
```

---

# VII. Tính số lá

Một đỉnh là lá nếu:

- Không có con nào.
- Với gốc 1, đỉnh khác gốc có bậc 1 thường là lá.

---

# VIII. Tính kích thước cây con

`subtree[u]` = số đỉnh trong cây con gốc `u`.

```python
subtree = [0] * (n + 1)

def dfs_size(u, p):
    subtree[u] = 1

    for v in tree[u]:
        if v != p:
            dfs_size(v, u)
            subtree[u] += subtree[v]
```

---

# IX. Bài tập vận dụng

---

## Bài 1. Tính cha của từng đỉnh

---

## Bài 2. Tính độ sâu từ gốc 1

---

## Bài 3. Đếm số lá của cây

---

## Bài 4. Tính kích thước cây con

---

## Bài 5. Tìm đỉnh có độ sâu lớn nhất

---

# X. Bài tập về nhà

---

## Bài 1. Tính tổng độ sâu các đỉnh

---

## Bài 2. Tìm số con trực tiếp của từng đỉnh

---

## Bài 3. Kiểm tra dữ liệu đầu vào có tạo thành cây không

---

## Bài 4. Tìm chiều cao của cây gốc 1

---

## Bài 5. In thứ tự DFS trên cây

---

# XI. Lỗi học sinh thường gặp

---

## 1. DFS cây mà quên truyền cha

---

## 2. Nghĩ cây bắt buộc phải vẽ từ trên xuống

---

## 3. Nhầm độ sâu với số cạnh trong toàn cây

---

## 4. Không phân biệt lá với đỉnh bậc 1 khi gốc đặc biệt

---

# XII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Độ sâu trong cây

---

## Đề 2. Kích thước nhánh

---

## Đề 3. Đếm lá

---

## Đề 4. Cây gia phả

---

# XIII. Ghi nhớ cuối bài

Cây = đồ thị liên thông không chu trình.

Mẫu DFS cây:

```python
def dfs(u, p):
    for v in tree[u]:
        if v != p:
            dfs(v, u)
```

---

# XIV. Tóm tắt bài học

| Khái niệm | Ý nghĩa |
|---|---|
| Gốc | Đỉnh được chọn làm trung tâm |
| Cha | Đỉnh đi trước |
| Con | Đỉnh đi sau |
| Lá | Không có con |
| Depth | Khoảng cách từ gốc |
| Subtree size | Số đỉnh trong cây con |
