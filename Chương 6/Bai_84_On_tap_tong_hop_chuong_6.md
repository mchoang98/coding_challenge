# Bài 84. Ôn tập tổng hợp Chương 6 — Đồ thị

---

# I. Mục tiêu bài học

## 1. Về kiến thức

Ôn tập toàn bộ các mảng đã học:

1. Khái niệm đồ thị.
2. Biểu diễn đồ thị.
3. BFS.
4. DFS.
5. Thành phần liên thông.
6. Đồ thị trên lưới.
7. Truy vết đường đi.
8. Cây cơ bản.
9. BFS đường đi ngắn nhất.
10. Dijkstra.
11. Floyd-Warshall.
12. Topological Sort.
13. Chu trình.

## 2. Về kỹ năng

- Nhận dạng bài toán.
- Chọn thuật toán phù hợp.
- Phân tích độ phức tạp cơ bản.
- Viết lời giải chuẩn nộp thi.

## 3. Về tư duy

- Đồ thị là mô hình rất rộng.
- Không quan trọng đề bài nói “graph” hay không; quan trọng là nhận ra quan hệ đỉnh - cạnh.

---

# II. Bản đồ kiến thức Chương 6

| Dạng bài | Thuật toán gợi ý |
|---|---|
| Đi được hay không | BFS / DFS |
| Đếm nhóm liên thông | BFS / DFS |
| Đếm vùng trên lưới | BFS / DFS |
| Đường ngắn nhất không trọng số | BFS |
| Đường ngắn có trọng số không âm | Dijkstra |
| Mọi cặp đường ngắn | Floyd-Warshall |
| Thứ tự phụ thuộc | Topological Sort |
| Kiểm tra chu trình | DFS / Topo |
| Duyệt cây | DFS |

---

# III. Quy trình giải bài đồ thị

## Bước 1. Xác định đỉnh

Ví dụ:

- Ô vuông.
- Thành phố.
- Công việc.
- Người.
- Trạng thái.

---

## Bước 2. Xác định cạnh

- Hai ô đi được.
- Có đường nối.
- Có phụ thuộc.
- Có phép biến đổi.

---

## Bước 3. Xác định loại đồ thị

- Vô hướng hay có hướng?
- Có trọng số hay không?
- Có phải cây không?

---

## Bước 4. Chọn cấu trúc lưu

- Danh sách kề.
- Ma trận kề.

---

## Bước 5. Chọn thuật toán

---

# IV. Bảng chọn thuật toán nhanh

| Dấu hiệu đề bài | Thuật toán |
|---|---|
| “Có đi được không?” | BFS / DFS |
| “Bao nhiêu nhóm?” | DFS / BFS |
| “Ít bước nhất?” | BFS |
| “Chi phí nhỏ nhất, trọng số không âm?” | Dijkstra |
| “N nhỏ, nhiều truy vấn khoảng cách?” | Floyd |
| “Công việc trước sau?” | Topo |
| “Có vòng phụ thuộc không?” | Topo / DFS chu trình |
| “N-1 cạnh, liên thông?” | Cây |

---

# V. Bộ bài tập ôn tập

---

## Bài 1. Danh sách kề

Nhập đồ thị vô hướng và in danh sách kề.

---

## Bài 2. BFS từ đỉnh 1

---

## Bài 3. DFS từ đỉnh 1

---

## Bài 4. Đếm thành phần liên thông

---

## Bài 5. Đếm đảo trong ma trận

---

## Bài 6. Tìm đường ngắn nhất trong mê cung

---

## Bài 7. Truy vết đường đi ngắn nhất

---

## Bài 8. Tính độ sâu trong cây

---

## Bài 9. Dijkstra từ nguồn S

---

## Bài 10. Floyd-Warshall

---

## Bài 11. Sắp xếp topo

---

## Bài 12. Phát hiện chu trình

---

# VI. Đề luyện tổng hợp Chương 6

---

## Câu 1. Mạng máy tính

Có `N` máy và `M` dây kết nối.  
Hỏi có bao nhiêu nhóm máy liên lạc được với nhau.

---

## Câu 2. Mê cung

Tìm số bước ít nhất từ S tới T.

---

## Câu 3. Giao hàng

Tìm chi phí nhỏ nhất từ kho tới mọi điểm giao.

---

## Câu 4. Lập lịch công việc

Cho các quan hệ phải làm trước.  
In một thứ tự hợp lệ hoặc báo không thể.

---

## Câu 5. Kiểm tra cây

Cho `N` đỉnh và `M` cạnh.  
Kiểm tra đồ thị có phải là cây hay không.

---

# VII. Checklist tự đánh giá

- [ ] Tôi hiểu đồ thị là đỉnh và cạnh.
- [ ] Tôi phân biệt được vô hướng và có hướng.
- [ ] Tôi tạo được danh sách kề.
- [ ] Tôi viết được BFS.
- [ ] Tôi viết được DFS.
- [ ] Tôi đếm được thành phần liên thông.
- [ ] Tôi duyệt được lưới.
- [ ] Tôi truy vết được đường đi.
- [ ] Tôi hiểu cây.
- [ ] Tôi dùng BFS cho đường ngắn không trọng số.
- [ ] Tôi dùng Dijkstra cho trọng số không âm.
- [ ] Tôi biết Floyd dùng khi N nhỏ.
- [ ] Tôi biết Topological Sort.
- [ ] Tôi phát hiện được chu trình cơ bản.

---

# VIII. Lỗi thường gặp trong toàn chương

---

## 1. Chọn sai thuật toán đường đi ngắn

---

## 2. Dùng ma trận kề cho N rất lớn

---

## 3. Không duyệt mọi thành phần

---

## 4. Duyệt lưới không kiểm tra biên

---

## 5. Đồ thị có hướng nhưng xử lý như vô hướng

---

## 6. Dijkstra với cạnh âm

---

## 7. Topo nhưng quên kiểm tra chu trình

---

## 8. Truy vết mà không lưu parent

---

# IX. Tóm tắt công thức và mẫu code trọng tâm

---

## 1. BFS

```python
queue = deque([s])
visited[s] = True
```

---

## 2. DFS

```python
def dfs(u):
    visited[u] = True
```

---

## 3. Đếm thành phần

```python
for u in range(1, n + 1):
    if not visited[u]:
        components += 1
        dfs(u)
```

---

## 4. Dijkstra

```python
if dist[v] > dist[u] + w:
    dist[v] = dist[u] + w
```

---

## 5. Floyd

```python
dist[i][j] = min(dist[i][j], dist[i][k] + dist[k][j])
```

---

## 6. Topo

```python
if indegree[v] == 0:
    queue.append(v)
```

---

# X. Ghi nhớ cuối chương

Đồ thị là một trong những chuyên đề xuất hiện rất nhiều trong:

- Thi chuyên Tin.
- HSG Tin.
- Tin học trẻ.
- Lập trình thi đấu.

Học tốt đồ thị cần:

1. Hiểu bản chất mô hình hóa.
2. Thuộc các mẫu BFS/DFS.
3. Chọn đúng thuật toán cho đường đi ngắn.
4. Luyện nhiều bài lưới, cây, phụ thuộc công việc.

---

# XI. Tóm tắt Chương 6

Sau Chương 6, học sinh đã có nền để bước sang:

- Stack, Queue, Heap.
- DSU.
- Cây nâng cao.
- Segment Tree.
- Thuật toán thi đấu mức cao hơn.
