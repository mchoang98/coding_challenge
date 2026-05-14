# Bài 53. Quay lui: tư duy chọn hoặc không chọn

---

# I. Mục tiêu bài học

Sau bài học này, học sinh cần đạt được các yêu cầu sau:

## 1. Về kiến thức

- Hiểu khái niệm **quay lui**.
- Biết cách xây dựng lời giải bằng việc:
  - Chọn.
  - Không chọn.
- Hiểu quá trình:
  - Thử.
  - Đi tiếp.
  - Quay lại.
- Phân biệt quay lui với sinh cấu hình đơn giản.

## 2. Về kỹ năng

- Liệt kê các tập con.
- Liệt kê các tập con có tổng bằng $S$.
- Tìm nghiệm cho một số bài toán chọn phần tử.

## 3. Về tư duy

- Hiểu cách duyệt cây trạng thái.
- Biết cắt nhánh đơn giản khi không thể có lời giải.
- Chuẩn bị cho các bài quay lui tiêu biểu.

---

# II. Lý thuyết

## 1. Quay lui là gì?

Quay lui là kỹ thuật thử các lựa chọn, nếu một hướng không phù hợp thì quay lại trạng thái trước để thử hướng khác.

---

## 2. Mẫu chọn hoặc không chọn

Với mỗi phần tử:

1. Không chọn phần tử đó.
2. Chọn phần tử đó.

---

## 3. Cây quyết định

Với $N$ phần tử, mỗi phần tử có hai trạng thái:

- Chọn.
- Không chọn.

Số khả năng là:

$2^N$

---

## 4. Ví dụ tập con

Tập `{1, 2, 3}` có các tập con:

- Rỗng.
- `{1}`
- `{2}`
- `{3}`
- `{1,2}`
- `{1,3}`
- `{2,3}`
- `{1,2,3}`

---

# III. Ví dụ minh họa

---

## Ví dụ 1. Liệt kê mọi tập con

```python
n = int(input())
a = list(map(int, input().split()))

chosen = []

def backtrack(pos):
    if pos == n:
        print(chosen)
        return

    backtrack(pos + 1)

    chosen.append(a[pos])
    backtrack(pos + 1)
    chosen.pop()

backtrack(0)
```

---

## Ví dụ 2. Liệt kê tập con có tổng bằng S

```python
n, s = map(int, input().split())
a = list(map(int, input().split()))

chosen = []

def backtrack(pos, current_sum):
    if pos == n:
        if current_sum == s:
            print(chosen)
        return

    backtrack(pos + 1, current_sum)

    chosen.append(a[pos])
    backtrack(pos + 1, current_sum + a[pos])
    chosen.pop()

backtrack(0, 0)
```

---

## Ví dụ 3. Cắt nhánh khi dãy toàn số dương

Nếu tất cả phần tử dương và `current_sum > s`, ta có thể dừng nhánh.

```python
if current_sum > s:
    return
```

---

# IV. Bài tập vận dụng

---

## Bài 1. Liệt kê tập con

---

## Bài 2. Tập con có đúng K phần tử

---

## Bài 3. Tập con có tổng bằng S

---

## Bài 4. Đếm tập con có tổng bằng S

---

## Bài 5. Tập con có tổng lớn nhất không vượt quá S

---

# V. Bài tập về nhà

---

## Bài 1. Chọn học sinh

Liệt kê các nhóm có đúng $K$ học sinh.

---

## Bài 2. Chọn quà

Có các món quà với giá trị.  
Liệt kê các nhóm quà có tổng đúng $S$.

---

## Bài 3. Tập con toàn số chẵn

---

## Bài 4. Tập con có ít nhất một số nguyên tố

---

## Bài 5. Tập con có tích không vượt quá P

---

# VI. Lỗi học sinh thường gặp

---

## 1. Quên `pop()` sau khi thử chọn

---

## 2. In chosen trực tiếp nhưng không hiểu nó thay đổi tiếp

Nếu lưu kết quả, nên copy danh sách.

---

## 3. Cắt nhánh sai khi dãy có số âm

---

## 4. Không tách rõ hai nhánh chọn và không chọn

---

# VII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Tập con tổng S

Liệt kê hoặc đếm tập con có tổng đúng bằng $S$.

---

## Đề 2. Bài toán ba lô vét cạn

Chọn tập đồ có tổng trọng lượng không vượt quá giới hạn.

---

## Đề 3. Chọn đội hình

Liệt kê các nhóm thỏa ràng buộc.

---

## Đề 4. Phân hoạch đơn giản

Chia dãy thành hai nhóm có tổng gần nhau.

---

# VIII. Ghi nhớ cuối bài

- Quay lui là thử và quay lại.
- Nhánh chọn / không chọn là mẫu rất phổ biến.
- Luôn cần phục hồi trạng thái sau khi đi sâu.

---

# IX. Tóm tắt bài học

## Bài 53. Quay lui chọn hoặc không chọn

```python
backtrack(pos + 1)

chosen.append(a[pos])
backtrack(pos + 1)
chosen.pop()
```
