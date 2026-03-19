# Bài tập Python: Xử lý dữ liệu đầu vào và ghi log

## Bài 1: Hệ thống giám sát nhiệt độ
Input:
"time:1,temp:35"

Yêu cầu:
- Parse thành dictionary
- Nếu temp > 40 → log: "[WARNING] High temperature"
- Tính nhiệt độ trung bình của 5 giá trị gần nhất


## Bài 2: Theo dõi trạng thái hệ thống
Input:
"status:OPEN"
"status:CLOSE"

Yêu cầu:
- Đếm số lần OPEN
- Nếu OPEN > 5 lần trong 1 phút → log cảnh báo
- Ghi log dạng: "[time] status=OPEN"


## Bài 3: Quyết định hành động theo giá trị
Input:
"value:300"

Yêu cầu:
- Nếu value < 200 → log: ACTION_LOW
- Nếu 200–500 → ACTION_NORMAL
- Nếu > 500 → ACTION_HIGH


## Bài 4: Phân loại trạng thái từ nhiều biến
Input:
"temp:28,hum:90,flag:1"

Yêu cầu:
- Nếu hum > 85 và flag = 1 → log: "RAIN"
- Nếu temp > 35 → log: "HOT"
- Ngược lại → "NORMAL"


## Bài 5: Theo dõi giá trị giảm dần
Input:
"value:100"
"value:95"
"value:90"

Yêu cầu:
- Tính độ chênh lệch giữa các lần (delta)
- Nếu giảm quá nhanh (>10 mỗi lần) → log cảnh báo


## Bài 6: Quản lý counter
Input:
"IN"
"OUT"

Yêu cầu:
- Tăng/giảm counter
- Không cho counter < 0
- Nếu counter > 50 → log cảnh báo


## Bài 7: Quản lý trạng thái nhiều object
Input:
"id:1,status:active"
"id:2,status:inactive"

Yêu cầu:
- Lưu trạng thái theo id
- In số object đang active
- Nếu tất cả inactive → log: SYSTEM_IDLE


## Bài 8: Phát hiện bất thường (anomaly detection)
Input:
"value:10"
"value:12"
"value:50"

Yêu cầu:
- Nếu chênh lệch giữa 2 lần > 20 → log: ANOMALY
- In vị trí xảy ra bất thường


## Bài 9: Xử lý session
Input:
"id:123,start:1000"
"id:123,end:2000"

Yêu cầu:
- Tính thời gian (duration)
- Nếu thiếu start hoặc end → log lỗi


## Bài 10: Xử lý command stream
Input:
"cmd:START"
"cmd:STOP"
"cmd:INVALID"

Yêu cầu:
- Chỉ chấp nhận: START, STOP, PAUSE
- Command không hợp lệ → log lỗi
- Giữ trạng thái hiện tại của hệ thống
