# Bài 55. Tham lam nhập môn

---

# I. Mục tiêu bài học

Sau bài học này, học sinh cần đạt được các yêu cầu sau:

## 1. Về kiến thức

- Hiểu khái niệm **tham lam**.
- Biết bản chất:
  - Chọn phương án tốt nhất tại thời điểm hiện tại.
- Nhận biết một số bài toán tham lam cơ bản:
  - Chọn nhiều hoạt động nhất.
  - Đổi tiền với hệ mệnh giá phù hợp.
  - Ghép cặp đơn giản.

## 2. Về kỹ năng

- Sắp xếp dữ liệu trước khi tham lam.
- Cài đặt bài chọn hoạt động.
- Phân tích vì sao một lựa chọn tham lam hợp lý trong ví dụ đơn giản.

## 3. Về tư duy

- Hiểu rằng không phải bài nào tham lam cũng đúng.
- Biết đặt câu hỏi:
  - Nếu chọn cục bộ tốt nhất, có ảnh hưởng đến tương lai không?
- Chuẩn bị cho các bài tham lam nâng cao.

---

# II. Lý thuyết

## 1. Thuật toán tham lam là gì?

Tham lam là cách giải trong đó ở mỗi bước ta chọn phương án có vẻ tốt nhất ngay lúc đó.

---

## 2. Khi nào tham lam có thể đúng?

Một bài toán tham lam thường đúng khi:

- Lựa chọn tốt nhất hiện tại không phá hỏng nghiệm tối ưu toàn cục.
- Sau khi chọn, bài toán còn lại có cấu trúc tương tự.

---

## 3. Ví dụ đổi tiền đơn giản

Nếu các mệnh giá là:

`100, 50, 20, 10`

và cần đổi `180`, ta lấy:

- `100`
- `50`
- `20`
- `10`

Đây là ví dụ tham lam.

Tuy nhiên, với một số hệ mệnh giá khác, chọn lớn nhất trước có thể không tối ưu.

---

## 4. Bài chọn hoạt động

Có nhiều hoạt động, mỗi hoạt động có:

- Thời điểm bắt đầu.
- Thời điểm kết thúc.

Mục tiêu:

- Chọn nhiều hoạt động nhất sao cho chúng không chồng lấn.

Chiến lược tham lam:

- Sắp xếp theo thời gian kết thúc tăng dần.
- Luôn chọn hoạt động kết thúc sớm nhất còn hợp lệ.

---

# III. Ví dụ minh họa

---

## Ví dụ 1. Đổi tiền bằng tham lam

```python
n = int(input())

denominations = [500, 200, 100, 50, 20, 10]

for value in denominations:
    count = n // value

    if count > 0:
        print(value, count)
        n %= value
```

---

## Ví dụ 2. Chọn nhiều hoạt động nhất

### 1. Code Python

```python
n = int(input())
activities = []

for _ in range(n):
    start, end = map(int, input().split())
    activities.append((end, start))

activities.sort()

count = 0
last_end = -10**18

for end, start in activities:
    if start >= last_end:
        count += 1
        last_end = end

print(count)
```

---

## Ví dụ 3. Ghép cặp để chênh lệch nhỏ

Nếu muốn ghép hai dãy sao cho tổng chênh lệch nhỏ, ta sắp xếp cả hai dãy tăng dần và ghép cùng vị trí.

---

# IV. Bài tập vận dụng

---

## Bài 1. Đổi tiền

Cho số tiền và hệ mệnh giá chuẩn.  
Đếm số tờ ít nhất bằng tham lam.

---

## Bài 2. Chọn hoạt động

Chọn nhiều khoảng thời gian không giao nhau nhất.

---

## Bài 3. Ghép cặp chiều cao

Ghép hai dãy để tổng chênh lệch nhỏ nhất.

---

## Bài 4. Chọn đoạn không chồng nhau

Cho các đoạn trên trục số.  
Chọn nhiều đoạn đôi một không giao nhau nhất.

---

## Bài 5. Phân phát bánh

Cho nhu cầu của trẻ và kích thước bánh.  
Tối đa số trẻ được phục vụ.

---

# V. Bài tập về nhà

---

## Bài 1. Chọn cuộc họp

Cho lịch họp.  
Chọn số cuộc họp tối đa có thể tham gia.

---

## Bài 2. Đổi tiền phản ví dụ

Tìm một hệ mệnh giá mà tham lam chọn tờ lớn nhất trước không tối ưu.

---

## Bài 3. Xếp lịch sử dụng phòng

---

## Bài 4. Tối đa số cặp phù hợp

Ghép yêu cầu và tài nguyên sao cho nhiều cặp nhất.

---

## Bài 5. Chọn trạm dừng

Tìm cách chọn ít điểm phủ nhất cho các đoạn.

---

# VI. Lỗi học sinh thường gặp

---

## 1. Nghĩ bài nào có vẻ tối ưu cũng dùng tham lam được

Không đúng.

---

## 2. Không sắp xếp trước khi chọn

Nhiều thuật toán tham lam phụ thuộc vào thứ tự sắp xếp.

---

## 3. Chọn theo điểm bắt đầu thay vì điểm kết thúc trong bài hoạt động

---

## 4. Không chứng minh hoặc kiểm tra tính hợp lý của chiến lược

---

# VII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Chọn nhiều công việc nhất

---

## Đề 2. Lịch biểu diễn

Chọn số tiết mục không chồng thời gian nhiều nhất.

---

## Đề 3. Ghép quà

Ghép tài nguyên với yêu cầu tối đa số đối tượng được phục vụ.

---

## Đề 4. Đổi tiền tối thiểu

Áp dụng khi hệ mệnh giá phù hợp.

---

# VIII. Ghi nhớ cuối bài

- Tham lam chọn điều có vẻ tốt nhất ngay hiện tại.
- Không phải bài nào tham lam cũng đúng.
- Cần nhận dạng cấu trúc bài toán.
- Bài chọn hoạt động là ví dụ kinh điển.

---

# IX. Tóm tắt bài học

## Bài 55. Tham lam nhập môn

Bài chọn hoạt động:

```python
activities.sort()

for end, start in activities:
    if start >= last_end:
        count += 1
        last_end = end
```
