# Bài 56. Ôn tập tổng hợp Chương 4

---

# I. Mục tiêu bài học

Sau bài học này, học sinh cần đạt được các yêu cầu sau:

## 1. Về kiến thức

- Hệ thống lại toàn bộ nội dung Chương 4:
  - Sắp xếp cơ bản.
  - `sort()` và `key`.
  - Quick Sort.
  - Ứng dụng sắp xếp.
  - Binary Search.
  - Lower Bound, Upper Bound.
  - Binary Search trên đáp án.
  - Đệ quy.
  - Sinh dãy nhị phân.
  - Sinh tổ hợp.
  - Sinh hoán vị.
  - Quay lui.
  - Tham lam nhập môn.

## 2. Về kỹ năng

- Nhận diện đúng dạng bài.
- Chọn công cụ phù hợp.
- Viết code theo mẫu chuẩn.
- Kết hợp kỹ thuật khi cần.

## 3. Về tư duy

- Biết nhìn bài toán dưới các góc:
  - Có cần sắp xếp không?
  - Có tính đơn điệu để binary search không?
  - Có phải bài liệt kê cấu hình không?
  - Có chiến lược tham lam nào hợp lý không?

---

# II. Bản đồ kiến thức Chương 4

## 1. Sắp xếp

Dùng khi:

- Cần thứ tự.
- Cần gom giá trị giống nhau.
- Cần ghép cặp hoặc dùng two pointers.

---

## 2. Binary Search

Dùng khi:

- Dãy đã sắp xếp.
- Hoặc không gian đáp án có tính đơn điệu.

---

## 3. Đệ quy và quay lui

Dùng khi:

- Cần liệt kê các cấu hình.
- Bài toán có nhiều lựa chọn theo từng bước.

---

## 4. Tham lam

Dùng khi:

- Có thể chứng minh lựa chọn tốt nhất hiện tại dẫn đến tối ưu toàn cục.

---

# III. Bảng chọn kỹ thuật

| Dạng bài | Kỹ thuật |
|---|---|
| Sắp xếp dữ liệu | `sort()` / thuật toán sắp xếp |
| Tìm X trong dãy tăng | Binary Search |
| Đếm số bằng X | Lower/Upper Bound |
| Tìm min/max thỏa điều kiện | Binary Search on Answer |
| Liệt kê dãy 0/1 | Sinh nhị phân |
| Chọn K từ N | Tổ hợp |
| Sắp xếp thứ tự toàn bộ | Hoán vị |
| Chọn hoặc bỏ | Quay lui |
| Chọn nhiều lịch không giao nhau | Tham lam |

---

# IV. Ví dụ tổng hợp

---

## Ví dụ 1. Đếm số lần xuất hiện bằng sort + binary search

- Sắp xếp dãy.
- Dùng lower bound và upper bound.

---

## Ví dụ 2. Chọn nhiều hoạt động nhất

- Sắp xếp theo thời điểm kết thúc.
- Duyệt tham lam.

---

## Ví dụ 3. Liệt kê nhóm có tổng bằng S

- Dùng quay lui chọn hoặc không chọn.

---

## Ví dụ 4. Cắt dây dài nhất

- Dùng binary search trên đáp án.

---

# V. Bộ bài tập ôn tập

---

## Bài 1. Sắp xếp và thống kê

Cho dãy số.  
Sắp xếp, đếm giá trị khác nhau, tìm tần suất lớn nhất.

---

## Bài 2. Tìm kiếm nhanh

Cho dãy tăng dần và nhiều truy vấn.  
Kiểm tra mỗi truy vấn có tồn tại không.

---

## Bài 3. Đếm bằng lower bound

Đếm số phần tử thuộc đoạn giá trị $[L, R]$.

---

## Bài 4. Cắt gỗ

Dùng binary search trên đáp án.

---

## Bài 5. Sinh tổ hợp

Liệt kê mọi cách chọn $K$ học sinh từ $N$ học sinh.

---

## Bài 6. Sinh hoán vị

Liệt kê mọi thứ tự biểu diễn của $N$ tiết mục.

---

## Bài 7. Tập con tổng S

Dùng quay lui.

---

## Bài 8. Chọn công việc

Dùng tham lam.

---

# VI. Đề luyện tổng hợp Chương 4

---

## Câu 1. Thống kê xếp hạng

Cho dãy $N$ số.  
Hãy:

1. Sắp xếp tăng dần.
2. Tìm số nhỏ thứ $K$.
3. Đếm số lần xuất hiện của nó.

---

## Câu 2. Cắt thanh

Cho các thanh gỗ và số đoạn cần tạo.  
Tìm độ dài lớn nhất.

---

## Câu 3. Nhóm học sinh

Liệt kê mọi nhóm có đúng $K$ học sinh.

---

## Câu 4. Lịch làm việc

Chọn số công việc không giao nhau lớn nhất.

---

## Câu 5. Tập con tổng S

Đếm số tập con có tổng bằng $S$.

---

# VII. Checklist tự đánh giá

- [ ] Tôi dùng được `sort()` và `key`.
- [ ] Tôi hiểu Quick Sort.
- [ ] Tôi viết được Binary Search.
- [ ] Tôi hiểu Lower/Upper Bound.
- [ ] Tôi giải được binary search trên đáp án cơ bản.
- [ ] Tôi viết được hàm đệ quy đơn giản.
- [ ] Tôi sinh được dãy nhị phân.
- [ ] Tôi sinh được tổ hợp.
- [ ] Tôi sinh được hoán vị.
- [ ] Tôi hiểu quay lui chọn hoặc không chọn.
- [ ] Tôi nhận biết được bài tham lam nhập môn.

---

# VIII. Lỗi thường gặp trong toàn chương

---

## 1. Dùng sai thuật toán do chưa nhận dạng dạng bài

---

## 2. Dùng binary search trên dữ liệu chưa có tính đơn điệu

---

## 3. Quên phục hồi trạng thái khi quay lui

---

## 4. Nhầm tổ hợp và hoán vị

---

## 5. Áp dụng tham lam khi chưa kiểm tra tính đúng

---

# IX. Ghi nhớ cuối chương

- Chương 4 là bước chuyển quan trọng từ kỹ thuật xử lý dữ liệu sang các chiến lược giải thuật có tính hệ thống hơn.
- Đây là nền tảng cần thiết trước khi học:
  - Quy hoạch động.
  - Đồ thị.
  - Cấu trúc dữ liệu nâng cao.

---

# X. Tóm tắt Chương 4

## Chương 4. Sắp xếp, tìm kiếm, đệ quy, quay lui và tham lam

Các công cụ trọng tâm:

1. Sắp xếp.
2. Binary Search.
3. Binary Search trên đáp án.
4. Đệ quy.
5. Sinh cấu hình.
6. Quay lui.
7. Tham lam.

Học sinh nắm vững chương này sẽ có lợi thế lớn khi bước sang các bài toán thuật toán trung cấp.
