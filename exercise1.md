

# Bài tập Python: Xử lý dữ liệu đầu vào và ghi log

---

## Bài 1: Hệ thống giám sát nhiệt độ

### Input
- Dòng 1: Một chuỗi dạng `time:1,temp:35`

### Output
- In ra log nếu cần.
- In ra giá trị nhiệt độ trung bình của 5 lần gần nhất (nếu chưa đủ 5 -> tính trung bình các giá trị đã có).

### Yêu cầu
- Parse input thành dictionary.
- Nếu `temp > 40` -> in ra: `[WARNING] High temperature`
- Tính nhiệt độ trung bình của 5 giá trị gần nhất.

---

## Bài 2: Theo dõi trạng thái hệ thống

### Input
- `N` dòng, mỗi dòng là một trạng thái:
```text
status:OPEN
status:CLOSE
```

### Output
- In log mỗi lần nhận trạng thái: `[time] status=OPEN`
- Nếu số lần `OPEN` trong 1 phút > 5, in ra: `[WARNING] Too many OPEN events`

### Yêu cầu
- Đếm số lần `OPEN` trong một khoảng thời gian.
- Xử lý log theo thứ tự thời gian.

---

## Bài 3: Quyết định hành động theo giá trị

### Input
- Dòng 1 có định dạng: `value:300`

### Output
- Trả về một trong các giá trị sau: `ACTION_LOW`, `ACTION_NORMAL`, hoặc `ACTION_HIGH`.

### Yêu cầu
- Nếu `value < 200` -> `ACTION_LOW`
- Nếu `200 <= value <= 500` -> `ACTION_NORMAL`
- Nếu `value > 500` -> `ACTION_HIGH`

---

## Bài 4: Phân loại trạng thái từ nhiều biến

### Input
- Một dòng chứa các thông số: `temp:28,hum:90,flag:1`

### Output
- Trả về một trong các trạng thái: `RAIN`, `HOT`, hoặc `NORMAL`.

### Yêu cầu
- Nếu `hum > 85` và `flag = 1` -> `RAIN`
- Nếu `temp > 35` -> `HOT`
- Các trường hợp còn lại -> `NORMAL`

---

## Bài 5: Theo dõi giá trị giảm dần

### Input
- `N` dòng chứa các giá trị:
```text
value:100
value:95
value:90
```

### Output
- In log nếu phát hiện bất thường: `[WARNING] Sudden drop detected at index X`

### Yêu cầu
- Tính delta (độ chênh lệch) giữa các lần liên tiếp.
- Nếu giá trị giảm `> 10` -> cảnh báo.

---

## Bài 6: Quản lý counter

### Input
- `N` dòng với các lệnh:
```text
IN
OUT
```

### Output
- In giá trị counter cuối cùng.
- Nếu counter > 50, in ra: `[WARNING] Counter too high`

### Yêu cầu
- `IN` -> tăng counter.
- `OUT` -> giảm counter.
- Không cho phép counter `< 0`.

---

## Bài 7: Quản lý nhiều object

### Input
- `N` dòng chứa id và trạng thái:
```text
id:1,status:active
id:2,status:inactive
```

### Output
- In số lượng object đang active: `ACTIVE_COUNT: X`
- Nếu tất cả đều inactive, in ra: `SYSTEM_IDLE`

### Yêu cầu
- Lưu và cập nhật trạng thái theo `id`.

---

## Bài 8: Phát hiện bất thường

### Input
- `N` dòng chứa các giá trị:
```text
value:10
value:12
value:50
```

### Output
- Nếu có bất thường, in ra: `ANOMALY at index X`

### Yêu cầu
- Nếu chênh lệch giữa 2 giá trị liên tiếp `> 20` -> ghi nhận là bất thường.

---

## Bài 9: Xử lý session

### Input
- 2 dòng chứa thông tin bắt đầu và kết thúc của một session:
```text
id:123,start:1000
id:123,end:2000
```

### Output
- Nếu hợp lệ: `DURATION: 1000`
- Nếu thiếu start hoặc end: `ERROR: Invalid session`

### Yêu cầu
- Tính thời gian bằng công thức: `end - start`

---

## Bài 10: Xử lý command stream

### Input
- `N` dòng chứa các lệnh:
```text
cmd:START
cmd:STOP
cmd:INVALID
```

### Output
- Nếu command hợp lệ: `STATE: START`
- Nếu command không hợp lệ: `ERROR: Invalid command`

### Yêu cầu
- Chỉ chấp nhận các lệnh: `START`, `STOP`, `PAUSE`.
- Lưu trữ và cập nhật trạng thái hệ thống hiện tại.

***
