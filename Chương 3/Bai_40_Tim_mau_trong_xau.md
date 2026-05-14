# Bài 40. Tìm mẫu trong xâu bằng Brute Force

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Hiểu bài toán tìm mẫu trong xâu.
- Phân biệt xâu văn bản và xâu mẫu.
- Biết tìm:
  - Có xuất hiện hay không.
  - Vị trí đầu tiên.
  - Số lần xuất hiện.

## 2. Về kỹ năng

- Tự cài đặt tìm mẫu bằng hai vòng lặp.
- Đếm số lần xuất hiện có chồng lấn.
- Đếm số lần xuất hiện không chồng lấn.

## 3. Về tư duy

- Hiểu bản chất trước khi dùng hàm có sẵn.
- Chuẩn bị cho các thuật toán xâu nâng cao.

---

# II. Lý thuyết

## 1. Ý tưởng Brute Force

Giả sử:

- Xâu lớn có độ dài $N$.
- Mẫu có độ dài $M$.

Ta thử đặt mẫu tại mọi vị trí bắt đầu từ `0` đến `N-M`.

## 2. Độ phức tạp

Mỗi vị trí có thể so tối đa $M$ ký tự.

Độ phức tạp:

$O(NM)$

## 3. Chồng lấn và không chồng lấn

Ví dụ:

`S = "aaaa"`

`P = "aa"`

- Có chồng lấn: `3` lần.
- Không chồng lấn: `2` lần.

---

# III. Ví dụ minh họa

## Ví dụ 1. Kiểm tra mẫu có xuất hiện không

```python
s = input().strip()
p = input().strip()

n = len(s)
m = len(p)
found = False

for start in range(n - m + 1):
    match = True

    for j in range(m):
        if s[start + j] != p[j]:
            match = False
            break

    if match:
        found = True
        break

print("YES" if found else "NO")
```

---

## Ví dụ 2. Vị trí đầu tiên

```python
s = input().strip()
p = input().strip()

n = len(s)
m = len(p)
answer = -1

for start in range(n - m + 1):
    match = True

    for j in range(m):
        if s[start + j] != p[j]:
            match = False
            break

    if match:
        answer = start + 1
        break

print(answer)
```

---

## Ví dụ 3. Đếm mẫu có chồng lấn

```python
s = input().strip()
p = input().strip()

n = len(s)
m = len(p)
count = 0

for start in range(n - m + 1):
    if s[start:start + m] == p:
        count += 1

print(count)
```

---

# IV. Bài tập vận dụng

## Bài 1. Kiểm tra xâu con

## Bài 2. Tìm vị trí đầu tiên

## Bài 3. Đếm số lần xuất hiện có chồng lấn

## Bài 4. Đếm số lần xuất hiện không chồng lấn

## Bài 5. Liệt kê mọi vị trí xuất hiện

## Bài 6. Xóa mẫu khỏi xâu

---

# V. Bài tập về nhà

## Bài 1. Mẫu đảo

## Bài 2. Mẫu xuất hiện nhiều nhất trong danh sách mẫu

## Bài 3. Xâu con chung liên tiếp dài nhất bằng brute force

## Bài 4. Kiểm tra xâu là lặp của một mẫu nhỏ hơn

---

# VI. Lỗi học sinh thường gặp

- Thử vị trí quá xa, vượt khỏi xâu.
- Nhầm chỉ số từ `0` với vị trí từ `1`.
- Không phân biệt có chồng lấn hay không.
- Không dừng so sánh khi gặp ký tự khác.
- Lạm dụng `.find()` mà không hiểu thuật toán.

---

# VII. Đề thi thật và bài chuẩn chuyên

## Đề 1. Vị trí xâu con

## Đề 2. Đếm mẫu trong xâu

## Đề 3. Xâu con chung liên tiếp dài nhất

## Đề 4. Xóa mẫu trong xâu

---

# VIII. Ghi nhớ cuối bài

- Tìm mẫu Brute Force có độ phức tạp $O(NM)$.
- Đây là nền tảng trước khi học KMP hoặc hashing xâu.

---

# IX. Tóm tắt bài học

## Mẫu duyệt

```python
for start in range(n - m + 1):
    ...
```
