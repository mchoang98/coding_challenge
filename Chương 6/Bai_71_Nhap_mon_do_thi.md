# Bài 71. Nhập môn đồ thị: đỉnh, cạnh, hướng, trọng số

---

# I. Mục tiêu bài học

## 1. Về kiến thức

Sau bài này, học sinh cần:

- Hiểu đồ thị là gì.
- Nắm được các khái niệm:
  - Đỉnh.
  - Cạnh.
  - Đường đi.
  - Bậc của đỉnh.
  - Đồ thị vô hướng.
  - Đồ thị có hướng.
  - Đồ thị có trọng số.
- Phân biệt được các loại bài toán cơ bản trên đồ thị.

## 2. Về kỹ năng

- Đọc mô tả đồ thị từ đề bài.
- Chuyển dữ kiện thực tế thành mô hình đỉnh - cạnh.
- Xác định đồ thị là:
  - Có hướng hay vô hướng.
  - Có trọng số hay không trọng số.

## 3. Về tư duy

- Nhìn bài toán mạng lưới, kết nối, đường đi, quan hệ phụ thuộc và nhận ra mô hình đồ thị.
- Biết đặt câu hỏi:
  > “Đối tượng nào là đỉnh? Quan hệ nào là cạnh?”

---

# II. Đồ thị là gì?

## 1. Định nghĩa trực quan

Đồ thị là một cấu trúc gồm:

- Một tập các **đỉnh**.
- Một tập các **cạnh** nối giữa các đỉnh.

Ví dụ:

- Thành phố là đỉnh.
- Đường nối hai thành phố là cạnh.

---

## 2. Ký hiệu toán học

Một đồ thị thường được ký hiệu:

\[
G = (V, E)
\]

Trong đó:

- \(V\): tập đỉnh.
- \(E\): tập cạnh.

---

# III. Các khái niệm cơ bản

---

## 1. Đỉnh

Đỉnh là một đối tượng trong đồ thị.

Ví dụ:

- Người dùng trong mạng xã hội.
- Thành phố trong bản đồ.
- Ô trong mê cung.
- Công việc trong bài toán phụ thuộc.

---

## 2. Cạnh

Cạnh biểu diễn mối liên hệ giữa hai đỉnh.

Ví dụ:

- Có đường đi giữa hai thành phố.
- Hai người là bạn.
- Từ công việc A phải hoàn thành trước công việc B.

---

## 3. Đồ thị vô hướng

Nếu cạnh nối `u` và `v` có thể đi cả hai chiều:

\[
u \leftrightarrow v
\]

thì đó là đồ thị vô hướng.

Ví dụ:

- Hai thành phố có đường đi hai chiều.
- Quan hệ bạn bè.

---

## 4. Đồ thị có hướng

Nếu cạnh đi từ `u` tới `v` nhưng chưa chắc đi ngược lại được:

\[
u \rightarrow v
\]

thì đó là đồ thị có hướng.

Ví dụ:

- Trang web A có link sang B.
- Công việc A phải xong trước B.

---

## 5. Đồ thị có trọng số

Nếu mỗi cạnh mang thêm một giá trị:

- Độ dài.
- Chi phí.
- Thời gian.
- Số km.

thì đó là đồ thị có trọng số.

Ví dụ:

\[
A \xrightarrow{5} B
\]

nghĩa là đi từ A tới B tốn chi phí 5.

---

# IV. Đường đi trong đồ thị

## 1. Đường đi

Đường đi là dãy đỉnh mà hai đỉnh liên tiếp có cạnh nối.

Ví dụ:

\[
1 \rightarrow 3 \rightarrow 5
\]

---

## 2. Chu trình

Chu trình là đường đi bắt đầu và kết thúc tại cùng một đỉnh.

Ví dụ:

\[
1 \rightarrow 2 \rightarrow 3 \rightarrow 1
\]

---

## 3. Đường đi đơn

Đường đi đơn là đường đi không lặp lại đỉnh.

---

# V. Bậc của đỉnh

## 1. Trong đồ thị vô hướng

Bậc của đỉnh = số cạnh nối với đỉnh đó.

Ví dụ:

- Đỉnh 2 nối với 1, 3, 5.
- Bậc của 2 là 3.

---

## 2. Trong đồ thị có hướng

Có hai loại:

- **Bậc vào**: số cạnh đi vào đỉnh.
- **Bậc ra**: số cạnh đi ra khỏi đỉnh.

---

# VI. Ví dụ mô hình hóa

---

## Ví dụ 1. Mạng bạn bè

Có 4 người:

- A kết bạn với B.
- A kết bạn với C.
- B kết bạn với D.

Mô hình:

- Đỉnh: A, B, C, D.
- Cạnh vô hướng:
  - A-B.
  - A-C.
  - B-D.

---

## Ví dụ 2. Các môn học phụ thuộc

- Học Toán rời rạc trước Thuật toán.
- Học Cấu trúc dữ liệu trước Thuật toán.

Mô hình:

- Đồ thị có hướng.
- Cạnh:
  - Toán rời rạc → Thuật toán.
  - Cấu trúc dữ liệu → Thuật toán.

---

## Ví dụ 3. Bản đồ giao thông

- Thành phố A nối B với quãng đường 10.
- Thành phố B nối C với quãng đường 7.

Mô hình:

- Đồ thị có trọng số.
- Mỗi cạnh mang trọng số khoảng cách.

---

# VII. Các dạng bài toán phổ biến trên đồ thị

## 1. Có đường đi giữa hai đỉnh không?

Thường dùng:

- BFS.
- DFS.

---

## 2. Đếm số nhóm tách biệt

Thường là:

- Thành phần liên thông.
- Đếm số vùng.

---

## 3. Tìm đường đi ngắn nhất

- Không trọng số: BFS.
- Trọng số không âm: Dijkstra.
- Mọi cặp đỉnh: Floyd-Warshall.

---

## 4. Kiểm tra chu trình

- DFS.
- Topological Sort.

---

## 5. Xác định thứ tự thực hiện công việc

- Sắp xếp topo.

---

# VIII. Bài tập vận dụng

---

## Bài 1. Xác định loại đồ thị

Với mỗi tình huống sau, hãy cho biết đồ thị là vô hướng hay có hướng:

1. Quan hệ bạn bè.
2. Quan hệ theo dõi trên mạng xã hội.
3. Đường hai chiều giữa hai thành phố.
4. Đường một chiều.

---

## Bài 2. Đỉnh và cạnh

Một trường học có:

- 5 phòng học.
- Các hành lang nối giữa các phòng.

Hãy chỉ ra:

- Đỉnh là gì?
- Cạnh là gì?

---

## Bài 3. Trọng số

Khi nào đồ thị cần trọng số?

---

## Bài 4. Bậc của đỉnh

Cho đồ thị vô hướng có cạnh:

- 1-2
- 1-3
- 2-3
- 2-4

Hãy tìm bậc từng đỉnh.

---

## Bài 5. Bậc vào và bậc ra

Cho đồ thị có hướng:

- 1 → 2
- 1 → 3
- 3 → 2
- 2 → 4

Tìm bậc vào và bậc ra của từng đỉnh.

---

# IX. Bài tập về nhà

---

## Bài 1. Mô hình hóa mạng lưới xe buýt thành đồ thị.

---

## Bài 2. Mô hình hóa quan hệ “phải học trước” giữa các môn học.

---

## Bài 3. Hãy tự vẽ một đồ thị có 6 đỉnh và 7 cạnh.

---

## Bài 4. Phân biệt chu trình và đường đi đơn.

---

## Bài 5. Hãy nêu 5 ví dụ đời sống có thể mô hình bằng đồ thị.

---

# X. Lỗi học sinh thường gặp

---

## 1. Không xác định được đâu là đỉnh

Ví dụ trong bài mê cung, nhiều bạn không nhận ra mỗi ô là một đỉnh.

---

## 2. Nhầm vô hướng và có hướng

Đường đi một chiều mà lại thêm cạnh ngược là sai.

---

## 3. Nhầm trọng số cạnh với số hiệu đỉnh

---

## 4. Nhầm đường đi với chu trình

---

## 5. Không đọc kỹ yêu cầu đề bài để chọn đúng mô hình

---

# XI. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Mạng máy tính

Các máy tính nối với nhau bằng cáp.  
Kiểm tra hai máy có liên lạc được không.

---

## Đề 2. Đường giao thông

Tìm số tuyến đường giữa các khu vực.

---

## Đề 3. Môn học phụ thuộc

Tìm thứ tự học hợp lệ.

---

## Đề 4. Bản đồ có trọng số

Tìm đường đi tối ưu.

---

# XII. Ghi nhớ cuối bài

Đồ thị = **đỉnh + cạnh**.

Khi đọc đề hãy hỏi:

1. Đối tượng nào là đỉnh?
2. Quan hệ nào là cạnh?
3. Cạnh có hướng không?
4. Cạnh có trọng số không?

---

# XIII. Tóm tắt bài học

| Khái niệm | Ý nghĩa |
|---|---|
| Đỉnh | Đối tượng |
| Cạnh | Quan hệ |
| Vô hướng | Đi hai chiều |
| Có hướng | Đi một chiều |
| Trọng số | Chi phí / độ dài / thời gian |
| Chu trình | Đi rồi quay lại điểm cũ |
