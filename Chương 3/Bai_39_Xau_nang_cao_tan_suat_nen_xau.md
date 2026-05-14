# Bài 39. Xâu nâng cao: tần suất, gom nhóm và nén xâu

---

# I. Mục tiêu bài học

## 1. Về kiến thức

- Củng cố kỹ năng duyệt xâu.
- Biết thống kê tần suất ký tự.
- Hiểu kỹ thuật gom các ký tự giống nhau liên tiếp.
- Biết ý tưởng nén xâu dạng Run-Length Encoding.

## 2. Về kỹ năng

- Đếm ký tự.
- Tìm ký tự xuất hiện nhiều nhất.
- Gom nhóm liên tiếp.
- Nén và giải nén xâu đơn giản.

## 3. Về tư duy

- Phân biệt tần suất toàn cục với nhóm liên tiếp.
- Biết quan sát mẫu lặp trong xâu.

---

# II. Lý thuyết

## 1. Tần suất ký tự

Tần suất là số lần ký tự xuất hiện trong toàn xâu.

## 2. Gom nhóm liên tiếp

Ví dụ:

`aaabbccccd`

gồm các nhóm:

- `aaa`
- `bb`
- `cccc`
- `d`

## 3. Nén xâu

Ta có thể mã hóa:

`aaabbccccd`

thành:

`a3b2c4d1`

## 4. Giải nén

Đọc ký tự rồi đọc số lượng lặp để khôi phục xâu gốc.

---

# III. Ví dụ minh họa

## Ví dụ 1. Gom nhóm liên tiếp

```python
s = input().strip()

i = 0
n = len(s)

while i < n:
    j = i

    while j < n and s[j] == s[i]:
        j += 1

    print(s[i], j - i)
    i = j
```

---

## Ví dụ 2. Nén xâu

```python
s = input().strip()

i = 0
n = len(s)
result = ""

while i < n:
    j = i

    while j < n and s[j] == s[i]:
        j += 1

    result += s[i] + str(j - i)
    i = j

print(result)
```

---

## Ví dụ 3. Đếm tần suất ký tự

```python
s = input().strip()

freq = {}

for ch in s:
    freq[ch] = freq.get(ch, 0) + 1

for ch, count in freq.items():
    print(ch, count)
```

---

# IV. Bài tập vận dụng

## Bài 1. Đếm chữ số trong xâu

## Bài 2. Ký tự xuất hiện nhiều nhất

## Bài 3. Đếm số nhóm liên tiếp

## Bài 4. Nhóm liên tiếp dài nhất

## Bài 5. Nén xâu

## Bài 6. Giải nén xâu đơn giản

---

# V. Bài tập về nhà

## Bài 1. Hai xâu có cùng tần suất ký tự?

## Bài 2. Ký tự không xuất hiện

## Bài 3. Nén xâu và so sánh độ dài

## Bài 4. Giải nén với số lượng có nhiều chữ số

## Bài 5. Tìm nhóm dài nhất và ký tự tương ứng

---

# VI. Lỗi học sinh thường gặp

- Nhầm tần suất với nhóm liên tiếp.
- Quên cập nhật `i = j`.
- Giải nén sai khi số lượng có nhiều chữ số.
- Dùng mảng 26 phần tử cho xâu chứa ký tự ngoài `a-z`.
- Nối xâu rất lớn không tối ưu.

---

# VII. Đề thi thật và bài chuẩn chuyên

## Đề 1. Nén xâu

## Đề 2. Giải nén xâu

## Đề 3. Thống kê ký tự

## Đề 4. Nhóm lặp dài nhất

---

# VIII. Ghi nhớ cuối bài

- Tần suất và nhóm liên tiếp là hai khái niệm khác nhau.
- Kỹ thuật hai chỉ số `i`, `j` rất hữu ích để gom nhóm.
- Nén xâu là bài mẫu quan trọng của xử lý xâu.

---

# IX. Tóm tắt bài học

## Mẫu gom nhóm

```python
i = 0

while i < n:
    j = i

    while j < n and s[j] == s[i]:
        j += 1

    i = j
```
