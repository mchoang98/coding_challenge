# Bài 47. Tìm kiếm nhị phân trên mảng đã sắp xếp

---

# I. Mục tiêu bài học

Sau bài học này, học sinh cần đạt được các yêu cầu sau:

## 1. Về kiến thức

- Hiểu bài toán tìm kiếm trong dãy đã sắp xếp.
- Nắm được ý tưởng của **Binary Search**.
- Biết vai trò của:
  - `left`
  - `right`
  - `mid`
- Hiểu tại sao mỗi bước loại bỏ được một nửa phạm vi tìm kiếm.
- Biết độ phức tạp là $O(\log N)$.

## 2. Về kỹ năng

- Viết được binary search kiểm tra một giá trị có xuất hiện không.
- Tìm vị trí của một phần tử trong dãy đã sắp xếp.
- So sánh binary search với tìm kiếm tuyến tính.

## 3. Về tư duy

- Biết tận dụng tính đã sắp xếp của dữ liệu.
- Hiểu kỹ thuật thu hẹp không gian tìm kiếm.
- Chuẩn bị cho:
  - Lower bound.
  - Upper bound.
  - Binary search on answer.

---

# II. Lý thuyết

## 1. Tìm kiếm tuyến tính

Nếu chưa có tính chất đặc biệt, ta duyệt từng phần tử.

Độ phức tạp:

$O(N)$

---

## 2. Binary Search là gì?

Binary Search là kỹ thuật tìm kiếm trên dãy đã sắp xếp.

Mỗi bước:

1. Xét phần tử ở giữa.
2. Nếu bằng giá trị cần tìm, kết thúc.
3. Nếu nhỏ hơn giá trị cần tìm, bỏ nửa trái.
4. Nếu lớn hơn giá trị cần tìm, bỏ nửa phải.

---

## 3. Điều kiện áp dụng

Dãy phải được sắp xếp theo đúng thứ tự mà ta khai thác.

Thông thường là tăng dần.

---

## 4. Ví dụ

Dãy:

`1 3 5 7 9 11`

Tìm `7`.

- Giữa là `5`, nhỏ hơn `7` → bỏ nửa trái.
- Xét đoạn `7 9 11`.
- Giữa là `9`, lớn hơn `7` → bỏ nửa phải.
- Còn `7` → tìm thấy.

---

## 5. Độ phức tạp

Mỗi bước chia đôi phạm vi.

Độ phức tạp:

$O(\log N)$

---

# III. Ví dụ minh họa

---

## Ví dụ 1. Kiểm tra X có trong dãy không

### 1. Code Python

```python
n, x = map(int, input().split())
a = list(map(int, input().split()))

left = 0
right = n - 1
found = False

while left <= right:
    mid = (left + right) // 2

    if a[mid] == x:
        found = True
        break
    elif a[mid] < x:
        left = mid + 1
    else:
        right = mid - 1

if found:
    print("YES")
else:
    print("NO")
```

---

## Ví dụ 2. Tìm vị trí đầu tiên tìm thấy

### 1. Ghi chú

Nếu dãy không có phần tử trùng, vị trí tìm thấy là duy nhất.

---

### 2. Code Python

```python
n, x = map(int, input().split())
a = list(map(int, input().split()))

left = 0
right = n - 1
answer = -1

while left <= right:
    mid = (left + right) // 2

    if a[mid] == x:
        answer = mid + 1
        break
    elif a[mid] < x:
        left = mid + 1
    else:
        right = mid - 1

print(answer)
```

---

## Ví dụ 3. Dùng hàm tự viết

```python
def binary_search(a, x):
    left = 0
    right = len(a) - 1

    while left <= right:
        mid = (left + right) // 2

        if a[mid] == x:
            return True
        elif a[mid] < x:
            left = mid + 1
        else:
            right = mid - 1

    return False
```

---

# IV. Bài tập vận dụng

---

## Bài 1. Kiểm tra tồn tại

Cho dãy tăng dần và số $X$.  
Kiểm tra $X$ có xuất hiện không.

---

## Bài 2. Tìm vị trí

Cho dãy tăng dần không trùng.  
Tìm vị trí của $X$.

---

## Bài 3. Nhiều truy vấn tìm kiếm

Cho dãy tăng dần và $Q$ truy vấn.  
Mỗi truy vấn hỏi một giá trị có xuất hiện hay không.

---

## Bài 4. Tìm số nhỏ nhất lớn hơn X

Cho dãy tăng dần.  
Tìm phần tử nhỏ nhất lớn hơn $X$.

---

## Bài 5. Tìm số lớn nhất nhỏ hơn X

Cho dãy tăng dần.  
Tìm phần tử lớn nhất nhỏ hơn $X$.

---

# V. Bài tập về nhà

---

## Bài 1. Tìm trong dãy giảm dần

Điều chỉnh binary search cho dãy giảm dần.

---

## Bài 2. Đếm số phần tử bằng X bằng cách kết hợp lower bound và upper bound

---

## Bài 3. Kiểm tra căn bậc hai nguyên

Dùng binary search để kiểm tra $N$ có phải số chính phương không.

---

## Bài 4. Tìm căn nguyên gần đúng

Tìm số nguyên lớn nhất $x$ sao cho $x^2 \le N$.

---

## Bài 5. Tìm điểm chèn

Cho dãy tăng dần và $X$.  
Tìm vị trí nên chèn $X$ để dãy vẫn tăng.

---

# VI. Lỗi học sinh thường gặp

---

## 1. Dùng binary search trên dãy chưa sắp xếp

Đây là lỗi nghiêm trọng.

---

## 2. Sai điều kiện vòng lặp

Thông thường dùng:

```python
while left <= right:
```

---

## 3. Không cập nhật biên đúng

- Nếu `a[mid] < x`, dùng `left = mid + 1`.
- Nếu `a[mid] > x`, dùng `right = mid - 1`.

---

## 4. Bỏ qua trường hợp không tìm thấy

Cần có kết quả mặc định như `-1` hoặc `NO`.

---

## 5. Nhầm chỉ số mảng với vị trí bài toán

Mảng Python bắt đầu từ `0`, nhiều đề đánh số từ `1`.

---

# VII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Tìm kiếm

Cho dãy đã sắp tăng dần và số $X$.  
In chỉ số của $X$ hoặc `0` nếu không tồn tại.

---

## Đề 2. Nhiều truy vấn thành viên

Cho danh sách số đã sắp xếp.  
Trả lời nhanh liệu từng truy vấn có thuộc danh sách không.

---

## Đề 3. Số chính phương

Dùng tìm kiếm nhị phân để xác định số chính phương.

---

## Đề 4. Vị trí chèn

Tìm vị trí đầu tiên có thể chèn $X$.

---

# VIII. Ghi nhớ cuối bài

- Binary Search chỉ dùng tốt khi dãy có thứ tự.
- Mỗi bước loại bỏ một nửa phạm vi.
- Độ phức tạp là $O(\log N)$.
- Đây là một trong những kỹ thuật quan trọng nhất trong giải thuật.

---

# IX. Tóm tắt bài học

## Bài 47. Binary Search cơ bản

```python
left = 0
right = n - 1

while left <= right:
    mid = (left + right) // 2

    if a[mid] == x:
        ...
    elif a[mid] < x:
        left = mid + 1
    else:
        right = mid - 1
```
