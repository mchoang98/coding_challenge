# Bài 8. Tổng dãy và công thức số học đơn giản

    ---

    # I. Mục tiêu bài học

    ## 1. Về kiến thức

    - Biết công thức tổng từ 1 đến N.
- Biết tổng số lẻ đầu tiên và tổng bình phương.
- Nhận ra lợi ích của công thức đóng.

    ## 2. Về kỹ năng

    - Viết được chương trình Python đúng cú pháp.
    - Áp dụng được nội dung bài học vào bài toán nhập môn.
    - Trình bày lời giải rõ ràng theo hướng giáo án.

    ## 3. Về tư duy

    - Biết xác định Input, Xử lý và Output.
    - Biết kiểm tra công thức trước khi code.

    ---

    # II. Lý thuyết

    ## 1. Tổng tự nhiên

$S = \frac{N(N+1)}{2}$.

## 2. Tổng số lẻ

$1 + 3 + ... + (2N-1) = N^2$.

## 3. Tổng bình phương

$1^2 + 2^2 + ... + N^2 = \frac{N(N+1)(2N+1)}{6}$.

    ---

    # III. Ví dụ minh họa

    ## 1. Tổng từ 1 đến N

```python
n = int(input())
print(n * (n + 1) // 2)
```

## 2. Tổng bình phương

```python
n = int(input())
print(n * (n + 1) * (2 * n + 1) // 6)
```

    ---

    # IV. Bài tập vận dụng

    ## Bài 1. Tính tổng từ 1 đến N.

## Bài 2. Tính tổng số lẻ đầu tiên.

## Bài 3. Tính tổng bình phương.

    ---

    # V. Bài tập về nhà

    ## Bài 1. Tính tổng lập phương.

## Bài 2. Tính tổng số chẵn đầu tiên.

## Bài 3. So sánh lời giải công thức với lời giải lặp.

    ---

    # VI. Lỗi học sinh thường gặp

    ## Bài 1. Nhầm công thức.

## Bài 2. Dùng `/` thay vì `//`.

## Bài 3. Sai thứ tự nhân chia.

    ---

    # VII. Đề thi thật và bài chuẩn nhập môn

    ## Đề 1. Tổng các số tự nhiên liên tiếp.

## Đề 2. Tổng bình phương.

## Đề 3. Tổng lập phương.

    ---

    # VIII. Ghi nhớ cuối bài

    - Đọc kỹ đề.
    - Xác định đúng dữ liệu đầu vào và đầu ra.
    - Viết công thức trước khi triển khai chương trình.

    ---

    # IX. Tóm tắt bài học

    Công thức đúng có thể rút thời gian xử lý từ rất dài xuống cực ngắn.
