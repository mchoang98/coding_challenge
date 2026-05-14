# Bài 50. Đệ quy cơ bản

---

# I. Mục tiêu bài học

Sau bài học này, học sinh cần đạt được các yêu cầu sau:

## 1. Về kiến thức

- Hiểu khái niệm **đệ quy**.
- Biết hai thành phần bắt buộc:
  - Điều kiện dừng.
  - Lời gọi đệ quy.
- Hiểu cách một lời gọi hàm tự chia bài toán thành bài toán nhỏ hơn.
- Biết một số ví dụ đơn giản:
  - Giai thừa.
  - Tổng từ $1$ đến $N$.
  - Lũy thừa đơn giản.

## 2. Về kỹ năng

- Viết được hàm đệ quy cơ bản.
- Truy vết lời gọi đệ quy.
- So sánh đệ quy với vòng lặp.
- Nhận biết được khi nào đệ quy có thể bị lặp vô hạn.

## 3. Về tư duy

- Làm quen với cách định nghĩa lời giải dựa trên phiên bản nhỏ hơn của chính bài toán.
- Chuẩn bị cho:
  - Sinh cấu hình.
  - Quay lui.
  - DFS sau này.

---

# II. Lý thuyết

## 1. Đệ quy là gì?

Đệ quy là kỹ thuật trong đó một hàm gọi lại chính nó.

---

## 2. Hai thành phần bắt buộc

Một hàm đệ quy cần có:

1. **Điều kiện dừng**.
2. **Bước đệ quy** đưa bài toán về trường hợp nhỏ hơn.

---

## 3. Ví dụ giai thừa

Ta có:

$n! = n \times (n-1)!$

với:

$0! = 1$

---

## 4. Hàm đệ quy giai thừa

```python
def factorial(n):
    if n == 0:
        return 1

    return n * factorial(n - 1)
```

---

## 5. Truy vết factorial(4)

- `factorial(4) = 4 * factorial(3)`
- `factorial(3) = 3 * factorial(2)`
- `factorial(2) = 2 * factorial(1)`
- `factorial(1) = 1 * factorial(0)`
- `factorial(0) = 1`

Kết quả:

$4! = 24$

---

## 6. Tổng từ 1 đến N bằng đệ quy

Ta có:

$S(N) = N + S(N-1)$

với:

$S(1) = 1$

---

## 7. Khi nào nên cẩn thận?

Đệ quy có thể:

- Gọi quá sâu.
- Tốn bộ nhớ stack.
- Chậm nếu tính lặp nhiều kết quả giống nhau.

---

# III. Ví dụ minh họa

---

## Ví dụ 1. Giai thừa

```python
def factorial(n):
    if n == 0:
        return 1

    return n * factorial(n - 1)


n = int(input())
print(factorial(n))
```

---

## Ví dụ 2. Tổng từ 1 đến N

```python
def sum_to_n(n):
    if n == 1:
        return 1

    return n + sum_to_n(n - 1)


n = int(input())
print(sum_to_n(n))
```

---

## Ví dụ 3. Lũy thừa a^n

```python
def power(a, n):
    if n == 0:
        return 1

    return a * power(a, n - 1)


a, n = map(int, input().split())
print(power(a, n))
```

---

## Ví dụ 4. In ngược dãy từ N về 1

```python
def print_down(n):
    if n == 0:
        return

    print(n)
    print_down(n - 1)


n = int(input())
print_down(n)
```

---

# IV. Bài tập vận dụng

---

## Bài 1. Tính giai thừa

Viết hàm đệ quy tính $N!$.

---

## Bài 2. Tổng các số từ 1 đến N

Viết hàm đệ quy tính tổng.

---

## Bài 3. Tính a^n

Viết hàm đệ quy.

---

## Bài 4. In từ 1 đến N

Dùng đệ quy để in dãy số tăng dần.

---

## Bài 5. In từ N về 1

Dùng đệ quy để in dãy giảm dần.

---

## Bài 6. Đếm chữ số của N

Dùng đệ quy để đếm số chữ số của một số nguyên dương.

---

# V. Bài tập về nhà

---

## Bài 1. Tổng chữ số bằng đệ quy

---

## Bài 2. Đảo số bằng đệ quy ở mức nhập môn

---

## Bài 3. UCLN bằng đệ quy

Dùng công thức Euclid:

$gcd(a, b) = gcd(b, a \bmod b)$

---

## Bài 4. Fibonacci đệ quy

Viết hàm tính Fibonacci bằng đệ quy và nhận xét tốc độ.

---

## Bài 5. Kiểm tra xâu đối xứng bằng đệ quy

---

# VI. Lỗi học sinh thường gặp

---

## 1. Quên điều kiện dừng

Hàm sẽ gọi mãi và gây lỗi.

---

## 2. Bước đệ quy không làm bài toán nhỏ hơn

Ví dụ gọi lại cùng giá trị `n`.

---

## 3. Nhầm giá trị trả về

Cần hiểu lời gọi đệ quy cũng trả về một kết quả.

---

## 4. Dùng đệ quy cho bài có thể vòng lặp dễ hơn mà chưa hiểu lợi ích

Giai đoạn đầu nên học để hiểu cơ chế.

---

## 5. Không truy vết trên ví dụ nhỏ

---

# VII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Giai thừa

Tính $N!$ bằng đệ quy.

---

## Đề 2. Tổng chữ số

Tính tổng các chữ số của $N$ bằng đệ quy.

---

## Đề 3. UCLN đệ quy

Cài đặt thuật toán Euclid bằng đệ quy.

---

## Đề 4. Xâu đối xứng

Kiểm tra palindrome bằng đệ quy.

---

# VIII. Ghi nhớ cuối bài

- Đệ quy = hàm gọi lại chính nó.
- Luôn cần:
  - Điều kiện dừng.
  - Bước thu nhỏ bài toán.
- Đệ quy là nền móng cho:
  - Sinh cấu hình.
  - Quay lui.
  - Duyệt cây và đồ thị.

---

# IX. Tóm tắt bài học

## Bài 50. Đệ quy cơ bản

```python
def factorial(n):
    if n == 0:
        return 1

    return n * factorial(n - 1)
```
