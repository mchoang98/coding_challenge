# Giáo trình ôn luyện thi Chuyên Tin – HSG Tin – Lập trình thi đấu

**Lộ trình từ cơ bản → nâng cao → giải đề thực chiến**

Tôi đề xuất chia toàn bộ quá trình thành **8 chặng**, đi đúng thứ tự để học sinh không bị “hổng nền”, nhưng vẫn tiến tới các dạng bài thi chuyên và thi đấu thuật toán.

Tài liệu bạn đã tải lên **“Nhập môn Lập trình cơ bản”** rất phù hợp để dùng làm **giai đoạn nền tảng**, vì nó bao trùm 5 mảng cốt lõi đầu tiên: cấu trúc tuần tự, rẽ nhánh, lặp, mảng, xâu, với 110 bài tập có hướng dẫn và test. 

---

# Tổng quan lộ trình

| Chặng | Mục tiêu                             | Trọng tâm                                               |
| ----- | ------------------------------------ | ------------------------------------------------------- |
| 1     | Làm chủ Python lập trình cơ bản      | Biến, if, loop, hàm, mảng, xâu                          |
| 2     | Tư duy giải bài và số học thuật toán | Ước, nguyên tố, gcd, chia hết, chữ số                   |
| 3     | Kỹ thuật xử lý mảng – xâu            | Prefix sum, two pointers, frequency, sort               |
| 4     | Tìm kiếm – sắp xếp – vét cạn tối ưu  | Binary search, greedy cơ bản, backtracking              |
| 5     | Quy hoạch động                       | DP 1 chiều, 2 chiều, dãy con                            |
| 6     | Đồ thị                               | BFS, DFS, shortest path, cây                            |
| 7     | Cấu trúc dữ liệu nâng cao            | Stack, queue, heap, set/map, DSU, segment tree nhập môn |
| 8     | Luyện đề chuyên Tin/HSG/thi đấu      | Phân tích đề, chiến thuật điểm, tối ưu code             |

Các chủ đề như **sàng nguyên tố, two pointers, quy hoạch động, đồ thị, cấu trúc dữ liệu** là những mảng thường xuất hiện trong các lộ trình HSG/chuyên Tin và tài nguyên luyện VOI. ([HSG Tin][1])

---

# CHẶNG 1. Nền tảng lập trình Python thật chắc

## Mục tiêu

Học sinh:

* Đọc được đề, hiểu input/output.
* Viết chương trình đúng cú pháp.
* Biết chuyển ý tưởng đơn giản thành code.
* Không bị lỗi ở những bài cơ bản trong đề thi.

## Nội dung

### 1.1. Nhập xuất và phép toán

* `int`, `float`, `str`
* `input()`, `print()`
* Toán tử `+ - * / // % **`
* Ép kiểu
* Làm tròn, định dạng số thực

### 1.2. Cấu trúc tuần tự

* Công thức toán
* Tính chu vi, diện tích
* Tổng dãy số
* Bài toán mô phỏng công thức

**Nguồn bài tập:** Phần 1 của tài liệu upload: 15 bài đầu. 

---

### 1.3. Rẽ nhánh

* `if`, `elif`, `else`
* Điều kiện đơn, điều kiện kép
* `and`, `or`, `not`
* Tìm max/min
* Kiểm tra tam giác
* Giải phương trình
* Các bài tọa độ đơn giản

**Nguồn bài tập:** Phần 2 của tài liệu: bài 16–33. 

---

### 1.4. Vòng lặp

* `for`
* `while`
* Biến đếm, biến tổng, biến tích
* Kỹ thuật cờ hiệu
* Dừng vòng lặp bằng `break`

**Bài mẫu cần thành thạo**

* Tổng dãy
* Giai thừa
* Liệt kê ước
* Đếm số chính phương
* Kiểm tra số nguyên tố
* Tìm số nguyên tố tiếp theo
* Tổng chữ số

**Nguồn bài tập:** Phần 3 của tài liệu: bài 34–54. 

---

### 1.5. Hàm

* Khi nào cần viết hàm
* Hàm kiểm tra số nguyên tố
* Hàm gcd
* Hàm đảo xâu
* Hàm kiểm tra palindrome

---

### 1.6. Mảng một chiều

* Khai báo list
* Duyệt mảng
* Tìm min/max
* Đếm phần tử
* Tổng, trung bình
* Tìm vị trí
* Dãy không giảm
* Tổng 3 phần tử liên tiếp lớn nhất

**Nguồn bài tập:** Phần 4, nhóm mảng 1 chiều. 

---

### 1.7. Mảng hai chiều

* Nhập ma trận
* Duyệt hàng/cột
* Tổng từng hàng/cột
* Max mỗi hàng, min mỗi cột
* Vị trí số nguyên tố/chính phương

**Nguồn bài tập:** Phần 4, nhóm mảng 2 chiều. 

---

### 1.8. Xâu ký tự

* `len`, `find`, `count`
* Đảo xâu
* Xâu đối xứng
* Chuẩn hóa xâu
* Đếm từ
* Tách số trong xâu
* Nén/giải nén xâu
* Xâu con chung dài nhất nhập môn

**Nguồn bài tập:** Phần 5 tài liệu upload. 

---

## Chuẩn đầu ra chặng 1

Học sinh giải ổn:

* Bài lập trình cơ bản mức dễ–trung bình.
* Các bài mảng, xâu, vòng lặp không tối ưu phức tạp.
* Có thể làm trọn **phần 110 bài nhập môn** trong tài liệu.

---

# CHẶNG 2. Số học thuật toán và tư duy tối ưu

Đây là nhóm cực quan trọng trong thi chuyên Tin, đặc biệt với học sinh mới.

## 2.1. Ước – bội – chia hết

* Ước số
* Bội số
* Số lượng ước
* Tổng ước
* Ước chung lớn nhất `gcd`
* Bội chung nhỏ nhất `lcm`

## 2.2. Số nguyên tố

* Kiểm tra nguyên tố `O(sqrt(n))`
* Phân tích thừa số nguyên tố
* Sàng Eratosthenes
* Đếm số nguyên tố trong đoạn
* Prime prefix

## 2.3. Chữ số và biến đổi số

* Tổng chữ số
* Tách chữ số
* Đảo số
* Số đối xứng
* Chữ số lớn nhất/nhỏ nhất
* Xóa chữ số, ghép chữ số

## 2.4. Toán tổ hợp nhập môn

* Giai thừa
* Chỉnh hợp, tổ hợp mức cơ bản
* Đếm cách đơn giản
* Modulo cơ bản

## 2.5. Kỹ năng phân tích độ phức tạp

* `O(1)`, `O(n)`, `O(n log n)`, `O(n²)`
* Khi nào vòng lặp lồng nhau bị chậm
* Ước lượng với `n = 10^5`, `10^6`

---

## Dạng bài trọng tâm chặng 2

1. Đếm số chia hết cho k trong đoạn `[L, R]`
2. Đếm ước của N
3. Tìm ước nguyên tố lớn nhất
4. Số nguyên tố gần nhất
5. Đếm cặp số có gcd = 1 mức đơn giản
6. Tính tổng dãy bằng công thức thay vì vòng lặp
7. Bài toán chữ số có điều kiện

---

# CHẶNG 3. Kỹ thuật xử lý mảng và xâu

Chặng này giúp học sinh chuyển từ “duyệt thường” sang “duyệt thông minh”.

## 3.1. Mảng đếm – tần suất

* Đếm số lần xuất hiện
* Tìm phần tử xuất hiện nhiều nhất
* Kiểm tra trùng
* Counting sort nhập môn

## 3.2. Prefix Sum

* Tổng đoạn `[L, R]`
* Đếm đoạn thỏa mãn điều kiện
* Prefix 1D
* Prefix 2D nhập môn

## 3.3. Two Pointers

* Dãy tăng
* Đoạn con có tổng ≤ K
* Đếm cặp
* Loại bỏ trùng

## 3.4. Sliding Window

* Tổng lớn nhất của đoạn dài K
* Đếm số đoạn hợp lệ
* Số phần tử phân biệt trong cửa sổ

## 3.5. Xâu nâng cao mức cơ bản

* Tần suất ký tự
* Chuẩn hóa
* So sánh hai xâu
* Tìm mẫu bằng brute force
* Prefix xâu mức nhập môn

---

## Dạng bài trọng tâm chặng 3

1. Tổng đoạn lớn nhất độ dài K
2. Đếm số đoạn có tổng không vượt quá S
3. Tìm đoạn con ngắn nhất thỏa điều kiện
4. Đếm tần suất chữ cái
5. Kiểm tra hai xâu có cùng bộ ký tự
6. Đếm số lần mẫu xuất hiện trong xâu

---

# CHẶNG 4. Tìm kiếm, sắp xếp, đệ quy, sinh, quay lui, tham lam

## 4.1. Sắp xếp

* Bubble sort để hiểu
* Selection sort, insertion sort
* Python `sort()`
* Sắp xếp theo khóa
* Sắp xếp cặp dữ liệu

## 4.2. Tìm kiếm nhị phân

* Binary search trên mảng
* Tìm vị trí đầu/cuối
* Lower bound / upper bound
* Binary search trên đáp án

## 4.3. Đệ quy

* Hàm gọi lại chính nó
* Giai thừa, Fibonacci
* Sinh dãy nhị phân
* Sinh hoán vị

## 4.4. Quay lui

* Liệt kê cấu hình
* Chọn/bỏ chọn
* Tổ hợp
* Hoán vị
* Bài toán xếp hậu mức nhập môn

## 4.5. Tham lam

* Chọn hoạt động
* Đổi tiền với hệ phù hợp
* Chọn đoạn
* Sắp xếp rồi tối ưu

---

## Dạng bài trọng tâm chặng 4

1. Tìm giá trị nhỏ nhất thỏa điều kiện bằng binary search
2. Sinh tất cả dãy nhị phân độ dài n
3. Sinh hoán vị 1..n
4. Chọn nhiều công việc nhất không chồng nhau
5. Chia nhóm / ghép cặp tối ưu đơn giản

---

# CHẶNG 5. Quy hoạch động – chuyên đề bắt buộc

Đây là phần phân loại học sinh khá với học sinh giỏi thực sự.

## 5.1. Tư duy DP

* Trạng thái là gì?
* Công thức chuyển
* Điều kiện ban đầu
* Thứ tự tính
* Truy vết kết quả

## 5.2. DP 1 chiều

* Fibonacci
* Leo cầu thang
* Tổng cách chia
* Dãy con tăng dài nhất bản cơ bản
* Đổi tiền
* Tổng lớn nhất không lấy kề nhau

## 5.3. DP 2 chiều

* Lưới đường đi
* Đếm đường đi
* Tổng lớn nhất trên ma trận
* LCS: xâu con chung dài nhất
* Edit distance mức giới thiệu

## 5.4. Knapsack

* Balo 0/1
* Balo vô hạn
* Chọn đồ đạt giá trị lớn nhất

## 5.5. DP dãy con

* LIS
* Maximum subarray / Kadane
* Đoạn tăng dài nhất

---

## Dạng bài trọng tâm chặng 5

1. Số cách leo n bậc
2. Đếm đường đi trên bảng
3. LCS
4. Balo 0/1
5. Chọn nhiều vật nhất/giá trị lớn nhất
6. Dãy con tăng dài nhất

Quy hoạch động là một mảng cốt lõi trong các lộ trình ôn luyện VOI/HSG chuyên sâu. ([GitHub][2])

---

# CHẶNG 6. Đồ thị

## 6.1. Kiến thức nền

* Đỉnh, cạnh
* Đồ thị vô hướng/có hướng
* Danh sách kề
* Ma trận kề

## 6.2. DFS và BFS

* Duyệt đồ thị
* Đếm thành phần liên thông
* Tìm đường đi
* Mê cung

## 6.3. Cây

* Cây là gì
* Duyệt cây
* Cha – con
* Độ sâu
* Số lá

## 6.4. Đường đi ngắn nhất

* BFS trên đồ thị không trọng số
* Dijkstra nhập môn
* Floyd mức biết khái niệm

## 6.5. Topological Sort

* Sắp xếp công việc có phụ thuộc
* DAG

---

## Dạng bài trọng tâm chặng 6

1. Đếm số vùng trong ma trận
2. Tìm đường đi ngắn nhất trong mê cung
3. Đếm thành phần liên thông
4. BFS trên lưới
5. Dijkstra cơ bản
6. Kiểm tra chu trình mức nhập môn

---

# CHẶNG 7. Cấu trúc dữ liệu phục vụ thi đấu

## 7.1. Stack

* Kiểm tra ngoặc
* Xóa ký tự
* Next greater element nhập môn

## 7.2. Queue / Deque

* BFS
* Sliding window tối ưu
* Mô phỏng hàng đợi

## 7.3. Set / Map / Dictionary

* Đếm nhanh
* Tìm kiếm nhanh
* Loại trùng
* Tần suất

## 7.4. Heap / Priority Queue

* Lấy min/max liên tục
* K phần tử lớn nhất
* Dijkstra

## 7.5. DSU – Disjoint Set Union

* Gộp nhóm
* Kiểm tra kết nối
* Kruskal nhập môn

## 7.6. Segment Tree / Fenwick Tree nhập môn

* Truy vấn tổng đoạn
* Cập nhật phần tử
* Dành cho giai đoạn khá–giỏi

---

# CHẶNG 8. Luyện đề thi chuyên, HSG, lập trình thi đấu

## 8.1. Kỹ năng đọc đề

* Xác định input/output
* Xác định giới hạn N
* Suy luận độ phức tạp cần đạt
* Tìm dữ kiện “ẩn” trong đề

## 8.2. Chiến lược làm bài

* Làm bài dễ trước
* Chia subtasks
* Lấy điểm từng phần
* Khi bí: viết brute force trước
* Tối ưu dần

## 8.3. Kỹ năng test

* Test nhỏ
* Test biên
* Test ngẫu nhiên
* So sánh brute force và lời giải tối ưu

## 8.4. Kỹ năng thi đấu

* Quản lý thời gian
* Không sa lầy một bài
* Ghi chú ý tưởng
* Kiểm tra định dạng output

Các đề HSG Tin năm 2025–2026 vẫn thường theo mô hình **3–4 bài, tăng dần độ khó, đánh vào xử lý số, dãy, tối ưu và tư duy thuật toán**, nên luyện đề tổng hợp là bắt buộc ở giai đoạn cuối. ([Thpt Kien Thuy][3])

---

# Lộ trình học khuyến nghị theo thời gian

## Giai đoạn A — 6 tuần đầu: Xây nền Python

* Tuần 1: Nhập xuất, công thức, cấu trúc tuần tự
* Tuần 2: Rẽ nhánh
* Tuần 3: Vòng lặp for/while
* Tuần 4: Hàm, số học cơ bản
* Tuần 5: Mảng 1 chiều, 2 chiều
* Tuần 6: Xâu ký tự

**Tài liệu chính:** hoàn thành toàn bộ 110 bài trong tài liệu upload. 

---

## Giai đoạn B — 8 tuần tiếp: Thuật toán nền tảng

* Tuần 7: Số học thuật toán
* Tuần 8: Sàng nguyên tố, ước, gcd
* Tuần 9: Sắp xếp và tìm kiếm
* Tuần 10: Prefix sum
* Tuần 11: Two pointers, sliding window
* Tuần 12: Đệ quy
* Tuần 13: Sinh, quay lui
* Tuần 14: Tham lam

---

## Giai đoạn C — 8 tuần tiếp: Thuật toán trung – nâng cao

* Tuần 15: DP nhập môn
* Tuần 16: DP dãy
* Tuần 17: DP bảng, LCS
* Tuần 18: Knapsack
* Tuần 19: Đồ thị cơ bản
* Tuần 20: BFS, DFS
* Tuần 21: Cây, topo
* Tuần 22: Dijkstra, heap

---

## Giai đoạn D — 6 tuần cuối: Luyện thi thực chiến

* Tuần 23: Đề chuyên Tin mức vừa
* Tuần 24: Đề HSG cấp trường/cấp tỉnh
* Tuần 25: Đề có subtasks
* Tuần 26: Đề hỗn hợp số học + mảng + DP
* Tuần 27: Đề đồ thị + cấu trúc dữ liệu
* Tuần 28: Thi thử full 180 phút

---

# Chuẩn đầu ra sau toàn bộ giáo trình

Sau lộ trình này, học sinh có thể:

### Mức 1 — Thi vào chuyên Tin

* Làm chắc bài 1, bài 2
* Có khả năng xử lý bài 3 nếu không quá nặng
* Biết tối ưu từ brute force sang thuật toán tốt hơn

### Mức 2 — HSG cấp tỉnh / thành phố

* Giải được các bài số học, dãy, xâu, prefix, greedy, DP cơ bản
* Làm được đồ thị cơ bản
* Biết phân tích constraints

### Mức 3 — Lập trình thi đấu

* Làm được bài Codeforces/VNOI mức cơ bản–khá
* Biết dùng các kỹ thuật tiêu chuẩn
* Bắt đầu tiếp cận DSU, segment tree, shortest path

---

# Thứ tự ưu tiên học quan trọng nhất

Nếu muốn đi nhanh mà vẫn chắc, tôi đề xuất thứ tự này:

1. **Python cơ bản**
2. **Mảng – xâu – vòng lặp**
3. **Số học**
4. **Sort + Binary Search**
5. **Prefix Sum**
6. **Two Pointers**
7. **Đệ quy + Quay lui**
8. **DP**
9. **Đồ thị**
10. **Cấu trúc dữ liệu nâng cao**
11. **Luyện đề**

---

# Kết luận

Giáo trình hợp lý nhất là:

* **Dùng tài liệu upload để xây nền tuyệt đối chắc**
* Sau đó nâng dần lên các **kỹ thuật thuật toán thường gặp trong thi chuyên/HSG**
* Cuối cùng tập trung **luyện đề, phân tích giới hạn, chiến thuật lấy điểm**

Đây là lộ trình tôi đánh giá phù hợp nhất cho mục tiêu:

> **Từ người mới Python → thi chuyên Tin → HSG Tin → bước đầu lập trình thi đấu.**

[1]: https://hsgtin.vn/hsg.html?utm_source=chatgpt.com "Lộ trình ôn thi HSG Tin học các cấp, thi vào 10 chuyên Tin, thi ..."
[2]: https://github.com/UPI05/VOI?utm_source=chatgpt.com "UPI05/VOI: Vietnamese Olympiad of Informatics training"
[3]: https://thptkienthuy.haiphong.edu.vn/de-thi/de-thi-chon-hsg-cap-truong-mon-tin-hoc-nam-hoc-2025-2026/ctmb/42598/467615?utm_source=chatgpt.com "Đề thi chọn HSG cấp trường môn Tin học năm học 2025"
