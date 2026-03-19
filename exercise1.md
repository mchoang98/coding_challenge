# Python Exercises – Input Processing & Logging (Refactored)

---

## General Rules

* Input is read from **stdin**.
* Output must be written to **stdout**.
* Follow exact output format (no extra spaces or lines).
* Index starts from **0** unless specified otherwise.
* Use deterministic logic (no randomness).

---

## Bài 1: Giám sát nhiệt độ

### Input

```
Dòng 1: time:INT,temp:INT
```

### Output

```
Nếu temp > 40 → in: [WARNING] High temperature
Dòng cuối: AVG: X
```

### Yêu cầu

* Parse input thành dictionary.
* Lưu lịch sử tối đa 5 giá trị temp gần nhất.
* Tính trung bình của các giá trị đã lưu.

### Sample

```
Input:
time:1,temp:35

Output:
AVG: 35.0
```

---

## Bài 2: Theo dõi trạng thái hệ thống

### Input

```
Dòng 1: N
Dòng tiếp theo N dòng: status:OPEN hoặc status:CLOSE
```

### Output

```
[time i] status=OPEN
Nếu OPEN xuất hiện > 5 lần trong 60 đơn vị time: [WARNING] Too many OPEN events
```

### Yêu cầu

* Dùng sliding window 60 đơn vị thời gian.
* Sử dụng chỉ số dòng làm time.

### Sample

```
Input:
6
OPEN
OPEN
OPEN
OPEN
OPEN
OPEN

Output:
[0] status=OPEN
...
[WARNING] Too many OPEN events
```

---

## Bài 3: Phân loại hành động

### Input

```
Dòng 1: value:INT
```

### Output

```
ACTION_LOW | ACTION_NORMAL | ACTION_HIGH
```

### Quy tắc

* value < 200 → LOW
* 200 ≤ value ≤ 500 → NORMAL
* value > 500 → HIGH

### Sample

```
Input:
value:300

Output:
ACTION_NORMAL
```

---

## Bài 4: Phân loại trạng thái

### Input

```
temp:INT,hum:INT,flag:INT
```

### Output

```
RAIN | HOT | NORMAL
```

### Quy tắc

* hum > 85 AND flag = 1 → RAIN
* else if temp > 35 → HOT
* else → NORMAL

### Sample

```
Input:
temp:30,hum:90,flag:1

Output:
RAIN
```

---

## Bài 5: Phát hiện giảm đột ngột

### Input

```
Dòng 1: N
Tiếp theo N dòng: value:INT
```

### Output

```
[WARNING] Sudden drop detected at index X
```

### Yêu cầu

* Nếu value[i-1] - value[i] > 10 → cảnh báo.

### Sample

```
Input:
3
100
80
70

Output:
[WARNING] Sudden drop detected at index 1
```

---

## Bài 6: Counter system

### Input

```
Dòng 1: N
Tiếp theo N dòng: IN hoặc OUT
```

### Output

```
Counter cuối cùng
Nếu > 50 → [WARNING] Counter too high
```

### Quy tắc

* IN → +1
* OUT → -1 (không nhỏ hơn 0)

### Sample

```
Input:
3
IN
IN
OUT

Output:
1
```

---

## Bài 7: Quản lý object

### Input

```
Dòng 1: N
Tiếp theo N dòng: id:INT,status:active/inactive
```

### Output

```
ACTIVE_COUNT: X
hoặc SYSTEM_IDLE
```

### Quy tắc

* Đếm số object active.
* Nếu không có object nào active → SYSTEM_IDLE

---

## Bài 8: Phát hiện bất thường

### Input

```
Dòng 1: N
Tiếp theo N dòng: value:INT
```

### Output

```
ANOMALY at index X
```

### Quy tắc

* Nếu |value[i] - value[i-1]| > 20 → bất thường

---

## Bài 9: Session processing

### Input

```
Dòng 1: id:INT,start:INT
Dòng 2: id:INT,end:INT
```

### Output

```
DURATION: X
hoặc ERROR: Invalid session
```

### Quy tắc

* duration = end - start
* start phải tồn tại trước end

---

## Bài 10: Command system

### Input

```
Dòng 1: N
Tiếp theo N dòng: cmd:STRING
```

### Output

```
STATE: START / STOP / PAUSE
hoặc ERROR: Invalid command
```

### Quy tắc

* Chỉ chấp nhận: START, STOP, PAUSE
* Cập nhật trạng thái hệ thống

---

## Ghi chú

* Tất cả bài có thể dùng để luyện:

  * parsing input
  * state management
  * logging system
  * sliding window
  * anomaly detection

---

End of file
