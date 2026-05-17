# Bài 9. Chia nguyên, chia dư và ứng dụng

    ---

    # I. Mục tiêu bài học

    ## 1. Về kiến thức

    - Hiểu `//` và `%`.
- Biết tách chữ số.
- Biết đổi thời gian bằng thương và dư.

    ## 2. Về kỹ năng

    - Viết được chương trình Python đúng cú pháp.
    - Áp dụng được nội dung bài học vào bài toán nhập môn.
    - Trình bày lời giải rõ ràng theo hướng giáo án.

    ## 3. Về tư duy

    - Biết xác định Input, Xử lý và Output.
    - Biết kiểm tra công thức trước khi code.

    ---

    # II. Lý thuyết

    ## 1. Chia nguyên

`a // b` là thương nguyên.

## 2. Chia dư

`a % b` là phần dư.

## 3. Ứng dụng

Tách chữ số, đổi giây thành phút giây, đổi ngày thành tuần ngày.

    ---

    # III. Ví dụ minh họa

    ## 1. Tổng chữ số số hai chữ số

```python
n = int(input())
print(n // 10 + n % 10)
```

## 2. Đổi giây sang phút và giây

```python
t = int(input())
print(t // 60, t % 60)
```

    ---

    # IV. Bài tập vận dụng

    ## Bài 1. Tách hàng chục và hàng đơn vị.

## Bài 2. Tổng chữ số số hai chữ số.

## Bài 3. Đổi phút thành giờ và phút.

    ---

    # V. Bài tập về nhà

    ## Bài 1. Tách chữ số số ba chữ số.

## Bài 2. Đổi ngày thành tuần và ngày lẻ.

## Bài 3. Đổi giây sang giờ, phút, giây.

    ---

    # VI. Lỗi học sinh thường gặp

    ## Bài 1. Dùng `/` để tách chữ số.

## Bài 2. Nhầm `% 10` với `// 10`.

## Bài 3. Quên cập nhật phần còn lại khi đổi đơn vị.

    ---

    # VII. Đề thi thật và bài chuẩn nhập môn

    ## Đề 1. Tách chữ số.

## Đề 2. Đổi thời gian.

## Đề 3. Tổng chữ số.

    ---

    # VIII. Ghi nhớ cuối bài

    - Đọc kỹ đề.
    - Xác định đúng dữ liệu đầu vào và đầu ra.
    - Viết công thức trước khi triển khai chương trình.

    ---

    # IX. Tóm tắt bài học

    Chia nguyên và chia dư là nền tảng cho nhiều bài xử lý số.
