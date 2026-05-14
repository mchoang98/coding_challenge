# Bài 45. Quick Sort và tư duy chia để trị

---

# I. Mục tiêu bài học

Sau bài học này, học sinh cần đạt được các yêu cầu sau:

## 1. Về kiến thức

- Hiểu khái niệm **chia để trị**.
- Nắm được ý tưởng của Quick Sort.
- Biết vai trò của phần tử chốt `pivot`.
- Hiểu quy trình:
  - Chia dãy.
  - Sắp xếp các đoạn con.
  - Kết hợp kết quả.
- Biết độ phức tạp trung bình của Quick Sort là $O(N \log N)$.

## 2. Về kỹ năng

- Mô phỏng được một lượt phân hoạch.
- Viết được Quick Sort đệ quy dạng dễ hiểu.
- Hiểu bản chất thuật toán đằng sau nhiều hàm sắp xếp nhanh.

## 3. Về tư duy

- Làm quen với kỹ thuật chia bài toán lớn thành bài toán nhỏ hơn.
- Chuẩn bị cho các bài đệ quy và chia để trị tiếp theo.
- Biết so sánh thuật toán $O(N^2)$ với $O(N \log N)$.

---

# II. Lý thuyết

## 1. Chia để trị là gì?

Chia để trị là chiến lược:

1. Chia bài toán lớn thành các bài toán nhỏ hơn.
2. Giải các bài toán nhỏ.
3. Kết hợp để thu được kết quả cuối.

---

## 2. Ý tưởng Quick Sort

Để sắp xếp dãy:

1. Chọn một phần tử làm `pivot`.
2. Chia dãy thành ba nhóm:
   - Nhỏ hơn `pivot`.
   - Bằng `pivot`.
   - Lớn hơn `pivot`.
3. Đệ quy sắp xếp nhóm nhỏ hơn và nhóm lớn hơn.
4. Ghép kết quả.

---

## 3. Ví dụ

Dãy:

`5 2 8 1 4`

Chọn `pivot = 5`.

- Nhỏ hơn `5`: `2 1 4`
- Bằng `5`: `5`
- Lớn hơn `5`: `8`

Sau khi sắp xếp đệ quy nhóm nhỏ:

`1 2 4`

Kết quả:

`1 2 4 5 8`

---

## 4. Độ phức tạp

### Trung bình

$O(N \log N)$

### Xấu nhất

$O(N^2)$

Trường hợp xấu có thể xảy ra nếu chia đoạn quá lệch.

---

## 5. Vì sao Quick Sort nhanh hơn Bubble Sort?

Bubble Sort có độ phức tạp $O(N^2)$.

Quick Sort trung bình $O(N \log N)$, nên phù hợp hơn nhiều khi $N$ lớn.

---

## 6. Phiên bản dễ hiểu bằng danh sách mới

Cách này dễ học, nhưng dùng thêm bộ nhớ.

---

# III. Ví dụ minh họa

---

## Ví dụ 1. Quick Sort dễ hiểu

### 1. Code Python

```python
def quick_sort(a):
    if len(a) <= 1:
        return a

    pivot = a[len(a) // 2]

    smaller = []
    equal = []
    greater = []

    for x in a:
        if x < pivot:
            smaller.append(x)
        elif x > pivot:
            greater.append(x)
        else:
            equal.append(x)

    return quick_sort(smaller) + equal + quick_sort(greater)


n = int(input())
a = list(map(int, input().split()))

result = quick_sort(a)

print(*result)
```

---

## Ví dụ 2. Minh họa lời gọi đệ quy

Dãy:

`4 1 7 3`

Chọn `pivot = 7`:

- Nhỏ hơn: `4 1 3`
- Bằng: `7`
- Lớn hơn: rỗng

Tiếp tục sắp xếp `4 1 3`.

---

## Ví dụ 3. Quick Sort giảm dần

```python
def quick_sort_desc(a):
    if len(a) <= 1:
        return a

    pivot = a[len(a) // 2]

    greater = []
    equal = []
    smaller = []

    for x in a:
        if x > pivot:
            greater.append(x)
        elif x < pivot:
            smaller.append(x)
        else:
            equal.append(x)

    return quick_sort_desc(greater) + equal + quick_sort_desc(smaller)
```

---

# IV. Bài tập vận dụng

---

## Bài 1. Quick Sort tăng dần

Cài đặt Quick Sort để sắp xếp dãy số nguyên tăng dần.

---

## Bài 2. Quick Sort giảm dần

Cài đặt Quick Sort để sắp xếp dãy giảm dần.

---

## Bài 3. Mô phỏng một lượt chia

Cho dãy và pivot.  
Chia dãy thành ba nhóm:
- Nhỏ hơn.
- Bằng.
- Lớn hơn pivot.

---

## Bài 4. So sánh với Bubble Sort

Chạy thử hai thuật toán trên một dãy nhỏ và đếm số lần so sánh.

---

## Bài 5. Sắp xếp xâu theo thứ tự từ điển bằng Quick Sort

---

# V. Bài tập về nhà

---

## Bài 1. Quick Sort theo trị tuyệt đối

Sắp xếp dãy số nguyên theo trị tuyệt đối tăng dần.

---

## Bài 2. Quick Sort danh sách cặp số

Sắp xếp các cặp $(x, y)$ theo $x$, nếu bằng thì theo $y$.

---

## Bài 3. Quick Sort và phần tử thứ K

Tìm phần tử nhỏ thứ $K$ sau khi sắp xếp.

---

## Bài 4. Chọn pivot khác nhau

Thử chọn:
- Pivot đầu.
- Pivot giữa.
- Pivot cuối.

Quan sát cách chia dãy.

---

## Bài 5. Dãy đã sắp xếp sẵn

Thử Quick Sort với pivot đầu tiên trên dãy đã tăng dần và nhận xét.

---

# VI. Lỗi học sinh thường gặp

---

## 1. Quên điều kiện dừng

Phải có:

```python
if len(a) <= 1:
    return a
```

---

## 2. Bỏ sót các phần tử bằng pivot

Cần có danh sách `equal`.

---

## 3. Nhầm Quick Sort với hàm sort của Python

Quick Sort là thuật toán tự cài đặt để học tư duy.

---

## 4. Không hiểu vì sao dùng đệ quy

Các đoạn con nhỏ hơn cần được sắp xếp tiếp.

---

## 5. Cho rằng Quick Sort luôn $O(N \log N)$

Thực tế, trường hợp xấu nhất là $O(N^2)$.

---

# VII. Đề thi thật và bài chuẩn chuyên

---

## Đề 1. Giá trị nhỏ thứ K

Sử dụng tư tưởng chia đoạn để rút ngắn phạm vi cần xét.

---

## Đề 2. Sắp xếp nhanh dãy số

Cho dãy số lớn.  
Sắp xếp không giảm.

---

## Đề 3. Phân vùng dữ liệu

Cho dãy và một giá trị chốt.  
Đưa các số nhỏ hơn chốt ra trước, lớn hơn chốt ra sau.

---

## Đề 4. Bài toán chia để trị

Dùng cách chia bài toán lớn thành các bài toán con tương tự.

---

# VIII. Ghi nhớ cuối bài

- Quick Sort dựa trên:
  - Pivot.
  - Chia mảng.
  - Đệ quy.
- Trung bình nhanh hơn các thuật toán $O(N^2)$.
- Đây là ví dụ tiêu biểu của tư duy chia để trị.

---

# IX. Tóm tắt bài học

## Bài 45. Quick Sort

```python
def quick_sort(a):
    if len(a) <= 1:
        return a

    pivot = a[len(a) // 2]

    smaller = [x for x in a if x < pivot]
    equal = [x for x in a if x == pivot]
    greater = [x for x in a if x > pivot]

    return quick_sort(smaller) + equal + quick_sort(greater)
```
