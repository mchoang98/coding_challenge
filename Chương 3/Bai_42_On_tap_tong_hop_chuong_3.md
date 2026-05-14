# Bài 42. Ôn tập tổng hợp Chương 3

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hệ thống lại toàn bộ Chương 3:
  - Tần suất.
  - Đếm phân phối.
  - Prefix sum 1D.
  - Ứng dụng prefix.
  - Prefix sum 2D.
  - Two pointers.
  - Sliding window.
  - Đoạn con liên tiếp.
  - Xâu nâng cao.
  - Tìm mẫu.
  - Số lớn.

## 2. Về kỹ năng

- Nhận dạng đúng dạng bài.
- Chọn kỹ thuật phù hợp.
- Kết hợp nhiều kỹ thuật trong một đề tổng hợp.

## 3. Về tư duy

- Biết đọc constraints để chọn thuật toán.
- Biết thay brute force bằng kỹ thuật hiệu quả hơn.

---

# II. Lý thuyết

## 1. Bảng chọn kỹ thuật

| Dạng bài | Kỹ thuật |
|---|---|
| Đếm xuất hiện | Tần suất |
| Sắp xếp miền nhỏ | Counting sort |
| Tổng đoạn nhiều truy vấn | Prefix sum |
| Tổng vùng ma trận | Prefix 2D |
| Cặp trong dãy đã sắp xếp | Two pointers |
| Cửa sổ liên tiếp | Sliding window |
| Mẫu trong xâu | Brute force matching |
| Số vượt giới hạn kiểu dữ liệu | Xâu số |

## 2. Tư duy chọn thuật toán

1. Xác định input/output.
2. Đọc giới hạn.
3. Viết cách đúng đơn giản.
4. Tìm kỹ thuật tối ưu hơn.
5. Kiểm tra bằng test nhỏ.

## 3. Liên hệ giữa các kỹ thuật

- Prefix sum và sliding window đều xử lý đoạn.
- Tần suất xuất hiện trong cả mảng và xâu.
- Two pointers và sliding window thường đi cùng nhau.

---

# III. Ví dụ minh họa

## Ví dụ 1. Bài đoạn tổng không vượt quá S

- Nếu dãy không âm: dùng sliding window.
- Nếu có số âm: cần kỹ thuật khác.

## Ví dụ 2. Bài đếm ký tự trong đoạn

- Dùng prefix theo ký tự hoặc prefix điều kiện.

## Ví dụ 3. Bài tổng vùng ma trận

- Dùng prefix 2D.

## Ví dụ 4. Bài số lớn

- Không dùng kiểu số thường.
- Dùng xâu số.

---

# IV. Bài tập vận dụng

## Bài 1. Tần suất phần tử

## Bài 2. Số nhỏ nhất không xuất hiện

## Bài 3. Truy vấn tổng đoạn

## Bài 4. Đếm phần tử chẵn trong đoạn

## Bài 5. Tổng vùng ma trận

## Bài 6. Đếm cặp tổng không vượt quá S

## Bài 7. Đoạn dài nhất có tổng không vượt quá S

## Bài 8. Nén xâu

## Bài 9. Đếm mẫu trong xâu

## Bài 10. Cộng hai số lớn

---

# V. Bài tập về nhà

## Bài 1. Đề tổng hợp mảng

Kết hợp tần suất, prefix và sliding window.

## Bài 2. Đề tổng hợp xâu

Kết hợp đếm ký tự, nén xâu, tìm mẫu.

## Bài 3. Đề tổng hợp ma trận

Kết hợp prefix 2D và truy vấn vùng.

## Bài 4. Đề số lớn

Kết hợp cộng số lớn và Fibonacci lớn.

---

# VI. Lỗi học sinh thường gặp

- Chọn sai kỹ thuật.
- Không đọc giới hạn dữ liệu.
- Sai chỉ số.
- Không xử lý biên.
- Chỉ biết code mẫu nhưng không nhận ra bài biến thể.

---

# VII. Đề thi thật và bài chuẩn chuyên

## Đề 1. Dãy và truy vấn

Cho dãy số cùng nhiều truy vấn đoạn.  
Kết hợp prefix và tần suất.

## Đề 2. Cửa sổ tối ưu

Cho dãy không âm.  
Tìm đoạn dài nhất thỏa giới hạn tổng.

## Đề 3. Bảng vùng sáng

Cho ma trận và nhiều truy vấn tổng vùng.

## Đề 4. Thông điệp nén

Cho xâu.  
Nén, giải nén hoặc thống kê nhóm ký tự.

## Đề 5. Tổng số lớn

Cho hai số rất lớn.  
Tính tổng chính xác.

---

# VIII. Ghi nhớ cuối bài

- Chương 3 là cầu nối từ lập trình cơ bản sang tư duy tối ưu mảng và xâu.
- Các kỹ thuật cần thuộc:
  - Tần suất.
  - Prefix.
  - Two pointers.
  - Sliding window.
- Đây là nhóm kiến thức xuất hiện rất nhiều trong đề thi chuyên và HSG.

---

# IX. Tóm tắt bài học

## Checklist tự đánh giá

- [ ] Biết dùng dictionary đếm tần suất.
- [ ] Biết counting sort.
- [ ] Biết prefix 1D và 2D.
- [ ] Biết two pointers.
- [ ] Biết sliding window.
- [ ] Biết xử lý đoạn con.
- [ ] Biết nén xâu.
- [ ] Biết tìm mẫu brute force.
- [ ] Biết cộng số lớn bằng xâu.
