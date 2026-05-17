# Bài 11. Tọa độ và khoảng cách hai điểm

    ---

    # I. Mục tiêu bài học

    ## 1. Về kiến thức

    - Biết biểu diễn điểm bằng tọa độ.
- Biết công thức khoảng cách hai điểm.
- Biết dùng `sqrt` trong thư viện `math`.

    ## 2. Về kỹ năng

    - Viết được chương trình Python đúng cú pháp.
    - Áp dụng được nội dung bài học vào bài toán nhập môn.
    - Trình bày lời giải rõ ràng theo hướng giáo án.

    ## 3. Về tư duy

    - Biết xác định Input, Xử lý và Output.
    - Biết kiểm tra công thức trước khi code.

    ---

    # II. Lý thuyết

    ## 1. Hai điểm

$A(x_1, y_1)$ và $B(x_2, y_2)$.

## 2. Khoảng cách

$AB = \sqrt{(x_2-x_1)^2 + (y_2-y_1)^2}$.

## 3. Thư viện math

Dùng `from math import sqrt`.

    ---

    # III. Ví dụ minh họa

    ## 1. Khoảng cách hai điểm

```python
from math import sqrt
x1 = float(input())
y1 = float(input())
x2 = float(input())
y2 = float(input())
d = sqrt((x2 - x1) ** 2 + (y2 - y1) ** 2)
print(f"{d:.2f}")
```

    ---

    # IV. Bài tập vận dụng

    ## Bài 1. Khoảng cách hai điểm.

## Bài 2. Khoảng cách từ điểm đến gốc tọa độ.

## Bài 3. Độ dài ba cạnh tam giác.

    ---

    # V. Bài tập về nhà

    ## Bài 1. Trung điểm đoạn thẳng.

## Bài 2. Chu vi tam giác từ tọa độ.

## Bài 3. Khoảng cách giữa hai điểm nguyên.

    ---

    # VI. Lỗi học sinh thường gặp

    ## Bài 1. Quên import `sqrt`.

## Bài 2. Sai dấu ngoặc.

## Bài 3. In sai số chữ số thập phân.

    ---

    # VII. Đề thi thật và bài chuẩn nhập môn

    ## Đề 1. Độ dài đoạn thẳng.

## Đề 2. Trung điểm.

## Đề 3. Chu vi tam giác.

    ---

    # VIII. Ghi nhớ cuối bài

    - Đọc kỹ đề.
    - Xác định đúng dữ liệu đầu vào và đầu ra.
    - Viết công thức trước khi triển khai chương trình.

    ---

    # IX. Tóm tắt bài học

    Bài tọa độ thường là bài công thức, không cần kỹ thuật phức tạp.
