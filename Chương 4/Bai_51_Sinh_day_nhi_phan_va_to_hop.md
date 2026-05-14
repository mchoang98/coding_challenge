# Bài 51. Sinh dãy nhị phân và sinh tổ hợp

---

# I. Mục tiêu bài học

Sau bài học này, học sinh cần đạt được các yêu cầu sau:

## 1. Về kiến thức

- Hiểu bài toán **sinh cấu hình**.
- Biết cách sinh:
  - Dãy nhị phân độ dài $N$.
  - Tổ hợp chập $K$ của $N$ phần tử.
- Hiểu vai trò của đệ quy trong liệt kê.

## 2. Về kỹ năng

- Viết được chương trình sinh mọi dãy nhị phân.
- Viết được chương trình sinh mọi tổ hợp.
- Biết dùng mảng phụ để lưu cấu hình đang xây dựng.

## 3. Về tư duy

- Biết xây dựng kết quả từng bước.
- Hiểu mỗi mức đệ quy tương ứng với một quyết định.
- Chuẩn bị cho quay lui.

---

# II. Lý thuyết

## 1. Sinh dãy nhị phân

Dãy nhị phân độ dài $N$ gồm các ký tự:

- `0`
- `1`

Mỗi vị trí có hai lựa chọn.

Số lượng dãy là:

$2^N$

---

## 2. Ý tưởng đệ quy

Ở vị trí thứ `pos`:

- Thử đặt `0`.
- Thử đặt `1`.
- Gọi tiếp cho vị trí `pos + 1`.

Khi đã điền đủ $N$ vị trí, in cấu hình.

---

## 3. Sinh tổ hợp

Tổ hợp chập $K$ của tập $\{1, 2, ..., N\}$ là chọn $K$ phần tử theo thứ tự tăng.

Ví dụ với $N = 4$, $K = 2$:

- `1 2`
- `1 3`
- `1 4`
- `2 3`
- `2 4`
- `3 4`

---

## 4. Ý tưởng sinh tổ hợp

Ta lưu mảng `chosen`.

Ở mỗi bước:

- Chọn phần tử tiếp theo lớn hơn phần tử trước.
- Gọi đệ quy sang vị trí kế tiếp.

---

# III. Ví dụ minh họa

---

## Ví dụ 1. Sinh mọi dãy nhị phân độ dài N

```python
n = int(input())
a = [0] * n

def generate(pos):
    if pos == n:
        print("".join(map(str, a)))
        return

    a[pos] = 0
    generate(pos + 1)

    a[pos] = 1
    generate(pos + 1)

generate(0)
```

---

## Ví dụ 2. Sinh tổ hợp chập K của N

```python
n, k = map(int, input().split())
chosen = [0] * k

def generate(pos, start):
    if pos == k:
        print(*chosen)
        return

    for value in range(start, n + 1):
        chosen[pos] = value
        generate(pos + 1, value + 1)

generate(0, 1)
```

---

## Ví dụ 3. Sinh dãy nhị phân có đúng K số 1

```python
n, k = map(int, input().split())
a = [0] * n

def generate(pos, count_one):
    if pos == n:
        if count_one == k:
            print("".join(map(str, a)))
        return

    a[pos] = 0
    generate(pos + 1, count_one)

    a[pos] = 1
    generate(pos + 1, count_one + 1)

generate(0, 0)
```

---

# IV. Bài tập vận dụng

---

## Bài 1. Sinh dãy nhị phân

Cho $N$.  
In tất cả dãy nhị phân độ dài $N$.

---

## Bài 2. Sinh dãy nhị phân có K số 1

---

## Bài 3. Sinh tổ hợp

Cho $N$, $K$.  
In mọi tổ hợp chập $K$.

---

## Bài 4. Sinh các tập con

Cho $N$.  
In mọi tập con của $\{1,2,...,N\}$.

---

## Bài 5. Sinh dãy tăng độ dài K

Cho $N$, $K$.  
In mọi dãy tăng gồm $K$ số lấy từ `1..N`.

---

# V. Bài tập về nhà

---

## Bài 1. Dãy nhị phân không có hai số 1 liền nhau

---

## Bài 2. Sinh tổ hợp có tổng bằng S

---

## Bài 3. Sinh tập con có đúng K phần tử

---

## Bài 4. Liệt kê các số có N chữ số chỉ gồm 0 và 1

---

## Bài 5. Tổ hợp học sinh

Liệt kê mọi cách chọn $K$ học sinh từ $N$ học sinh.

---

# VI. Lỗi học sinh thường gặp

---

## 1. Không xác định đúng điều kiện in kết quả

---

## 2. Quên `return` sau khi in cấu hình

---

## 3. Sinh tổ hợp nhưng cho phép trùng phần tử

---

## 4. Không tăng `start` trong sinh tổ hợp

---

## 5. Không hiểu mảng cấu hình được dùng chung qua các lời gọi

---

# VII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Dãy nhị phân

Liệt kê toàn bộ dãy nhị phân độ dài $N$.

---

## Đề 2. Tổ hợp

Liệt kê tất cả cách chọn $K$ phần tử từ $N$ phần tử.

---

## Đề 3. Dãy nhị phân hợp lệ

Liệt kê các dãy nhị phân không có hai số `1` đứng cạnh nhau.

---

## Đề 4. Tập con tổng S

Liệt kê các tập con có tổng đúng bằng $S$.

---

# VIII. Ghi nhớ cuối bài

- Sinh cấu hình bằng đệ quy là kỹ thuật quan trọng.
- Mỗi mức đệ quy tương ứng một quyết định.
- Dãy nhị phân: thử `0` hoặc `1`.
- Tổ hợp: chọn phần tử lớn hơn phần tử trước.

---

# IX. Tóm tắt bài học

## Bài 51. Sinh dãy nhị phân và tổ hợp

Dãy nhị phân:

```python
a[pos] = 0
generate(pos + 1)

a[pos] = 1
generate(pos + 1)
```

Tổ hợp:

```python
for value in range(start, n + 1):
    chosen[pos] = value
    generate(pos + 1, value + 1)
```
