# Bài 70. Ôn tập tổng hợp Chương 5 — Quy hoạch động

---

# I. Mục tiêu bài học

## 1. Về kiến thức

Hệ thống lại các dạng DP đã học:

1. Tư duy DP.
2. Top-down và memoization.
3. DP đếm cách.
4. DP tối ưu trên dãy.
5. Kadane.
6. LIS.
7. DP trên lưới.
8. LCS.
9. Edit Distance.
10. Knapsack 0/1.
11. Balo vô hạn.
12. Truy vết nghiệm.

## 2. Về kỹ năng

- Nhận dạng dạng bài.
- Chọn trạng thái hợp lý.
- Viết công thức chuyển.
- Chọn kiểu DP phù hợp.
- Truy vết khi đề yêu cầu.

## 3. Về tư duy

- Không học DP như công thức rời rạc.
- Biết xây dựng từ câu hỏi:
  - Cần gì?
  - Trạng thái mô tả điều gì?
  - Từ đâu chuyển tới?
  - Kết quả nằm ở đâu?

---

# II. Bản đồ kiến thức Chương 5

| Dạng bài | Ý tưởng chính | Trạng thái thường gặp |
|---|---|---|
| Fibonacci / bậc thang | Đếm cách | `dp[i]` |
| Không chọn kề nhau | Chọn / bỏ | `dp[i]` |
| Maximum subarray | Tốt nhất kết thúc tại i | `dp[i]` |
| LIS | Dãy tăng kết thúc tại i | `dp[i]` |
| Lưới đếm đường | Tới ô (i,j) | `dp[i][j]` |
| Lưới min/max | Giá trị tốt nhất tới ô | `dp[i][j]` |
| LCS | Hai tiền tố xâu | `dp[i][j]` |
| Edit Distance | Biến đổi hai tiền tố | `dp[i][j]` |
| Knapsack 0/1 | i món, sức chứa w | `dp[i][w]` |
| Balo vô hạn | Sức chứa w | `dp[w]` |

---

# III. Quy trình giải một bài DP

## Bước 1. Đọc kỹ yêu cầu

- Đếm số cách?
- Tìm tối đa?
- Tìm tối thiểu?
- In phương án?

---

## Bước 2. Xác định trạng thái

Hãy viết thành câu đầy đủ:

> `dp[i]` là ...

hoặc:

> `dp[i][j]` là ...

---

## Bước 3. Tìm công thức chuyển

Trả lời:

- Để tới trạng thái này, bước trước đó có thể ở đâu?
- Nếu chọn / không chọn thì sao?
- Nếu ký tự bằng / khác nhau thì sao?

---

## Bước 4. Điều kiện đầu

Không có điều kiện đầu, bảng DP không thể chạy đúng.

---

## Bước 5. Thứ tự tính

Trạng thái nào cần tính trước?

---

## Bước 6. Đáp án nằm ở đâu?

- `dp[n]`
- `dp[m][n]`
- `max(dp)`
- `min(dp)`?

---

# IV. Bảng nhận dạng nhanh

| Từ khóa đề bài | Gợi ý dạng DP |
|---|---|
| “Số cách...” | DP đếm cách |
| “Không chọn hai kề nhau” | DP chọn / bỏ |
| “Đoạn con liên tiếp lớn nhất” | Kadane |
| “Dãy con tăng dài nhất” | LIS |
| “Đi trên bảng...” | DP lưới |
| “Hai xâu...” | LCS / Edit Distance |
| “Balo / sức chứa...” | Knapsack |
| “Đổi tiền...” | Coin Change |

---

# V. Bộ bài tập ôn tập

---

## Bài 1. Leo cầu thang

Mỗi bước 1 hoặc 2 bậc. Đếm số cách.

---

## Bài 2. Chọn quà

Không chọn hai món kề nhau. Tìm tổng lớn nhất.

---

## Bài 3. Đoạn con lớn nhất

Tìm tổng lớn nhất của đoạn con liên tiếp.

---

## Bài 4. LIS

Tìm độ dài dãy con tăng dài nhất.

---

## Bài 5. Đếm đường trên lưới

Có vật cản.

---

## Bài 6. Tổng lớn nhất trên lưới

---

## Bài 7. LCS

Tìm độ dài và một xâu con chung dài nhất.

---

## Bài 8. Edit Distance

---

## Bài 9. Balo 0/1

---

## Bài 10. Đổi tiền ít đồng nhất

---

## Bài 11. Đếm số cách đổi tiền

---

## Bài 12. Truy vết phương án của một bài DP

---

# VI. Đề luyện tổng hợp Chương 5

---

## Câu 1. Bậc thang nâng cao

Có `N` bậc. Mỗi bước 1, 2 hoặc 3 bậc.  
Tính số cách lên đúng bậc `N`, lấy modulo \(10^9 + 7\).

---

## Câu 2. Dãy quà

Cho dãy giá trị.  
Chọn các phần tử không kề nhau sao cho tổng lớn nhất.

---

## Câu 3. Robot trên lưới

Tìm số đường đi từ góc trái trên tới góc phải dưới, có chướng ngại.

---

## Câu 4. Xâu tương đồng

Tìm độ dài LCS của hai xâu.

---

## Câu 5. Balo học sinh

Chọn đồ vào balo để giá trị lớn nhất.

---

# VII. Checklist tự đánh giá

- [ ] Tôi giải thích được DP là gì.
- [ ] Tôi xác định được trạng thái.
- [ ] Tôi viết được công thức chuyển.
- [ ] Tôi biết khi nào dùng cộng, max, min.
- [ ] Tôi làm được DP 1 chiều cơ bản.
- [ ] Tôi hiểu LIS `O(N²)`.
- [ ] Tôi làm được DP lưới.
- [ ] Tôi làm được LCS.
- [ ] Tôi hiểu Edit Distance.
- [ ] Tôi làm được knapsack 0/1.
- [ ] Tôi phân biệt được balo 0/1 và vô hạn.
- [ ] Tôi biết truy vết nghiệm.

---

# VIII. Lỗi thường gặp trong toàn chương

---

## 1. Không viết rõ ý nghĩa trạng thái

---

## 2. Công thức chuyển thiếu trường hợp

---

## 3. Khởi tạo sai điều kiện đầu

---

## 4. Duyệt sai thứ tự

---

## 5. Đáp án lấy sai vị trí trong bảng

---

## 6. Dùng DP quá máy móc

---

## 7. Không phân biệt:
- Đếm cách.
- Tối ưu.
- Kiểm tra tồn tại.

---

## 8. Không chú ý độ phức tạp bộ nhớ

---

# IX. Tóm tắt công thức trọng tâm

---

## 1. Leo cầu thang

\[
dp[i] = dp[i-1] + dp[i-2]
\]

---

## 2. Không chọn kề nhau

\[
dp[i] = \max(dp[i-1], dp[i-2] + a[i])
\]

---

## 3. Kadane

\[
dp[i] = \max(a[i], dp[i-1] + a[i])
\]

---

## 4. LIS

\[
dp[i] = \max(dp[i], dp[j] + 1)
\]

nếu:

\[
j < i,\quad a[j] < a[i]
\]

---

## 5. DP lưới đếm cách

\[
dp[i][j] = dp[i-1][j] + dp[i][j-1]
\]

---

## 6. DP lưới tối ưu

\[
dp[i][j] = a[i][j] + \max(dp[i-1][j], dp[i][j-1])
\]

---

## 7. LCS

Nếu ký tự bằng nhau:

\[
dp[i][j] = dp[i-1][j-1] + 1
\]

Ngược lại:

\[
dp[i][j] = \max(dp[i-1][j], dp[i][j-1])
\]

---

## 8. Knapsack 0/1

\[
dp[i][w] = \max(dp[i-1][w], dp[i-1][w-weight_i] + value_i)
\]

---

# X. Ghi nhớ cuối chương

Quy hoạch động là một trong những chuyên đề quan trọng nhất khi luyện:

- Thi chuyên Tin.
- HSG Tin.
- Lập trình thi đấu.

Không nên học thuộc lời giải từng bài.  
Hãy học cách **tự dựng trạng thái và công thức chuyển**.

---

# XI. Tóm tắt Chương 5

Sau Chương 5, học sinh cần tự tin với:

- DP 1 chiều.
- DP 2 chiều.
- DP trên dãy.
- DP trên lưới.
- DP trên xâu.
- Balo.
- Truy vết.

Đây là bước đệm quan trọng trước khi học:
- Đồ thị.
- Cấu trúc dữ liệu.
- Bài toán tối ưu nâng cao.
