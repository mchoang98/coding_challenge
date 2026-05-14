# Bài 54. Bài toán liệt kê cấu hình điển hình

---

# I. Mục tiêu bài học

Sau bài học này, học sinh cần đạt được các yêu cầu sau:

## 1. Về kiến thức

- Hệ thống các dạng liệt kê cấu hình phổ biến:
  - Dãy nhị phân.
  - Tổ hợp.
  - Hoán vị.
  - Tập con.
- Biết chọn mô hình phù hợp với đề bài.

## 2. Về kỹ năng

- Phân loại bài toán liệt kê.
- Viết được lời giải quay lui phù hợp.
- Biết chuyển yêu cầu bằng lời sang dạng cấu hình.

## 3. Về tư duy

- Không học thuộc máy móc từng mẫu.
- Biết nhận dạng bài thuộc nhóm nào để dùng mẫu tương ứng.

---

# II. Lý thuyết

## 1. Bốn dạng cấu hình cơ bản

| Dạng | Đặc điểm |
|---|---|
| Dãy nhị phân | Mỗi vị trí chọn 0 hoặc 1 |
| Tổ hợp | Chọn K phần tử, không xét thứ tự |
| Hoán vị | Dùng toàn bộ phần tử, có xét thứ tự |
| Tập con | Mỗi phần tử chọn hoặc không |

---

## 2. Cách nhận dạng nhanh

### Dãy nhị phân

Đề có:

- Chuỗi 0/1.
- N công tắc bật/tắt.
- Chọn trạng thái cho từng vị trí.

---

### Tổ hợp

Đề có:

- Chọn $K$ phần tử từ $N$.
- Không quan tâm thứ tự.

---

### Hoán vị

Đề có:

- Sắp xếp thứ tự.
- Xếp người vào vị trí.
- Mỗi phần tử dùng đúng một lần.

---

### Tập con

Đề có:

- Mỗi phần tử chọn hoặc bỏ.
- Tìm nhóm phần tử thỏa tổng.

---

# III. Ví dụ minh họa

---

## Ví dụ 1. N công tắc

Mỗi công tắc có hai trạng thái:

- Tắt.
- Bật.

Bài toán tương ứng sinh dãy nhị phân.

---

## Ví dụ 2. Chọn đội 3 học sinh từ 10 học sinh

Không xét thứ tự.

Bài toán tương ứng sinh tổ hợp.

---

## Ví dụ 3. Xếp 5 học sinh thành hàng

Có xét thứ tự và dùng đủ tất cả.

Bài toán tương ứng sinh hoán vị.

---

## Ví dụ 4. Chọn một số món quà có tổng S

Mỗi món:

- Lấy.
- Không lấy.

Bài toán tương ứng sinh tập con.

---

# IV. Bài tập vận dụng

---

## Bài 1. Phân loại bài

Với mỗi mô tả, xác định thuộc loại:

- Dãy nhị phân.
- Tổ hợp.
- Hoán vị.
- Tập con.

---

## Bài 2. Liệt kê cách chọn K học sinh

---

## Bài 3. Liệt kê cách xếp N người

---

## Bài 4. Liệt kê trạng thái N bóng đèn

---

## Bài 5. Liệt kê nhóm phần tử có tổng S

---

# V. Bài tập về nhà

---

## Bài 1. Mật khẩu nhị phân

Sinh mọi mật khẩu độ dài $N$ chỉ gồm `0`, `1`.

---

## Bài 2. Chọn câu hỏi

Có $N$ câu hỏi, chọn $K$ câu.

---

## Bài 3. Xếp lịch biểu diễn

Sắp xếp $N$ tiết mục theo mọi thứ tự có thể.

---

## Bài 4. Chọn quà có tổng đúng tiền

---

## Bài 5. Hỗn hợp nhận dạng

Tự đặt 5 bài toán và phân loại dạng cấu hình.

---

# VI. Lỗi học sinh thường gặp

---

## 1. Dùng hoán vị cho bài tổ hợp

---

## 2. Không phân biệt có xét thứ tự hay không

---

## 3. Tạo cấu hình trùng lặp

---

## 4. Không ràng buộc phần tử đã dùng

---

# VII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Chọn nhóm

Bài toán tổ hợp.

---

## Đề 2. Xếp chỗ

Bài toán hoán vị.

---

## Đề 3. Bật tắt đèn

Bài toán dãy nhị phân.

---

## Đề 4. Chọn vật

Bài toán tập con.

---

# VIII. Ghi nhớ cuối bài

- Cần nhận dạng đúng loại cấu hình trước khi code.
- Mỗi dạng có một mẫu đệ quy đặc trưng.
- Việc phân loại đúng giúp giải bài nhanh hơn.

---

# IX. Tóm tắt bài học

## Bài 54. Liệt kê cấu hình điển hình

Bốn nhóm chính:

1. Dãy nhị phân.
2. Tổ hợp.
3. Hoán vị.
4. Tập con.
