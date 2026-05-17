# Bài 12. Chu vi và diện tích tam giác bằng công thức Hê-rông

    ---

    # I. Mục tiêu bài học

    ## 1. Về kiến thức

    - Biết tính chu vi tam giác.
- Biết tính nửa chu vi.
- Biết áp dụng công thức Hê-rông.

    ## 2. Về kỹ năng

    - Viết được chương trình Python đúng cú pháp.
    - Áp dụng được nội dung bài học vào bài toán nhập môn.
    - Trình bày lời giải rõ ràng theo hướng giáo án.

    ## 3. Về tư duy

    - Biết xác định Input, Xử lý và Output.
    - Biết kiểm tra công thức trước khi code.

    ---

    # II. Lý thuyết

    ## 1. Chu vi

$P = a + b + c$.

## 2. Nửa chu vi

$p = \frac{a+b+c}{2}$.

## 3. Diện tích Hê-rông

$S = \sqrt{p(p-a)(p-b)(p-c)}$.

    ---

    # III. Ví dụ minh họa

    ## 1. Chu vi và diện tích

```python
from math import sqrt
a = float(input())
b = float(input())
c = float(input())
p = (a + b + c) / 2
area = sqrt(p * (p - a) * (p - b) * (p - c))
print(f"{a + b + c:.2f}")
print(f"{area:.3f}")
```

    ---

    # IV. Bài tập vận dụng

    ## Bài 1. Tính chu vi tam giác.

## Bài 2. Tính diện tích theo Hê-rông.

## Bài 3. In diện tích với 3 chữ số sau dấu phẩy.

    ---

    # V. Bài tập về nhà

    ## Bài 1. Diện tích tam giác vuông.

## Bài 2. Chu vi tam giác từ tọa độ.

## Bài 3. Tự tạo một bài hình học khác.

    ---

    # VI. Lỗi học sinh thường gặp

    ## Bài 1. Tính sai nửa chu vi.

## Bài 2. Thiếu ngoặc trong công thức.

## Bài 3. Nhầm diện tích với chu vi.

    ---

    # VII. Đề thi thật và bài chuẩn nhập môn

    ## Đề 1. Chu vi, diện tích tam giác.

## Đề 2. Tam giác từ tọa độ.

## Đề 3. Công thức Hê-rông.

    ---

    # VIII. Ghi nhớ cuối bài

    - Đọc kỹ đề.
    - Xác định đúng dữ liệu đầu vào và đầu ra.
    - Viết công thức trước khi triển khai chương trình.

    ---

    # IX. Tóm tắt bài học

    Công thức Hê-rông là bài luyện rất tốt cho cấu trúc tuần tự và số thực.
