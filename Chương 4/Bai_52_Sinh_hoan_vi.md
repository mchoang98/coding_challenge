# Bài 52. Sinh hoán vị

---

# I. Mục tiêu bài học

Sau bài học này, học sinh cần đạt được các yêu cầu sau:

## 1. Về kiến thức

- Hiểu khái niệm hoán vị.
- Biết số lượng hoán vị của $N$ phần tử là $N!$.
- Nắm được ý tưởng sinh hoán vị bằng đệ quy và mảng đánh dấu.

## 2. Về kỹ năng

- Viết chương trình sinh mọi hoán vị của `1..N`.
- Dùng mảng `used` để đánh dấu phần tử đã chọn.
- Sinh hoán vị của danh sách ký tự hoặc số.

## 3. Về tư duy

- Hiểu rằng mỗi vị trí chọn một phần tử chưa dùng.
- Biết vì sao cần “quay lại trạng thái cũ” sau khi gọi đệ quy.

---

# II. Lý thuyết

## 1. Hoán vị là gì?

Hoán vị của $N$ phần tử là một cách sắp xếp toàn bộ $N$ phần tử đó theo thứ tự.

Ví dụ với `1, 2, 3`:

- `1 2 3`
- `1 3 2`
- `2 1 3`
- `2 3 1`
- `3 1 2`
- `3 2 1`

Có:

$3! = 6$

hoán vị.

---

## 2. Ý tưởng sinh hoán vị

Ở vị trí `pos`:

1. Thử từng giá trị chưa dùng.
2. Đánh dấu giá trị đó đã dùng.
3. Gọi đệ quy cho vị trí tiếp theo.
4. Bỏ đánh dấu để thử lựa chọn khác.

---

## 3. Mảng đánh dấu used

Nếu `used[x] = True`, nghĩa là `x` đã xuất hiện trong hoán vị hiện tại.

---

# III. Ví dụ minh họa

---

## Ví dụ 1. Sinh hoán vị 1..N

```python
n = int(input())

perm = [0] * n
used = [False] * (n + 1)

def generate(pos):
    if pos == n:
        print(*perm)
        return

    for value in range(1, n + 1):
        if not used[value]:
            perm[pos] = value
            used[value] = True

            generate(pos + 1)

            used[value] = False

generate(0)
```

---

## Ví dụ 2. Sinh hoán vị của xâu ký tự

```python
s = input().strip()
n = len(s)

perm = [""] * n
used = [False] * n

def generate(pos):
    if pos == n:
        print("".join(perm))
        return

    for i in range(n):
        if not used[i]:
            perm[pos] = s[i]
            used[i] = True

            generate(pos + 1)

            used[i] = False

generate(0)
```

---

## Ví dụ 3. Đếm số hoán vị

```python
def factorial(n):
    result = 1

    for i in range(1, n + 1):
        result *= i

    return result

n = int(input())
print(factorial(n))
```

---

# IV. Bài tập vận dụng

---

## Bài 1. Sinh hoán vị 1..N

---

## Bài 2. Sinh hoán vị của xâu

---

## Bài 3. Hoán vị bắt đầu bằng 1

Liệt kê mọi hoán vị của `1..N` có phần tử đầu tiên là `1`.

---

## Bài 4. Hoán vị có tổng hai phần tử đầu chẵn

---

## Bài 5. Đếm số hoán vị thỏa điều kiện đơn giản

---

# V. Bài tập về nhà

---

## Bài 1. Hoán vị không có hai số chẵn đứng cạnh nhau

---

## Bài 2. Sinh hoán vị theo thứ tự từ điển bằng thư viện

---

## Bài 3. Hoán vị xâu có ký tự trùng

Đếm số hoán vị khác nhau.

---

## Bài 4. Bài toán xếp người

Có $N$ người ngồi vào $N$ ghế.  
Liệt kê hoặc đếm số cách.

---

## Bài 5. Hoán vị thỏa tổng cặp kề

---

# VI. Lỗi học sinh thường gặp

---

## 1. Quên bỏ đánh dấu used[value] = False

Nếu quên, các nhánh sau sẽ bị thiếu.

---

## 2. Không phân biệt tổ hợp và hoán vị

Hoán vị có xét thứ tự.

---

## 3. Dùng cùng một phần tử nhiều lần

Cần mảng `used`.

---

## 4. Xử lý sai khi xâu có ký tự trùng

Nếu các ký tự giống nhau, có thể sinh hoán vị trùng.

---

# VII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Liệt kê hoán vị

Cho $N$.  
In mọi hoán vị của `1..N`.

---

## Đề 2. Xếp vị trí

Đếm số cách xếp $N$ người vào $N$ vị trí.

---

## Đề 3. Hoán vị ký tự

Liệt kê mọi hoán vị khác nhau của một xâu.

---

## Đề 4. Hoán vị hợp lệ

Liệt kê hoán vị thỏa một số ràng buộc đề bài.

---

# VIII. Ghi nhớ cuối bài

- Hoán vị có số lượng $N!$.
- Mỗi vị trí chọn một phần tử chưa dùng.
- Sau lời gọi đệ quy phải trả trạng thái về như cũ.

---

# IX. Tóm tắt bài học

## Bài 52. Sinh hoán vị

```python
for value in range(1, n + 1):
    if not used[value]:
        perm[pos] = value
        used[value] = True
        generate(pos + 1)
        used[value] = False
```
