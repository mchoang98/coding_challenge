# Bài 5. Ép kiểu và định dạng số thực

    ---

    # I. Mục tiêu bài học

    ## 1. Về kiến thức

    - Biết dùng `int()`, `float()`, `str()`.
- Biết in số thực theo số chữ số sau dấu phẩy yêu cầu.
- Hiểu vì sao output đúng định dạng rất quan trọng.

    ## 2. Về kỹ năng

    - Viết được chương trình Python đúng cú pháp.
    - Áp dụng được nội dung bài học vào bài toán nhập môn.
    - Trình bày lời giải rõ ràng theo hướng giáo án.

    ## 3. Về tư duy

    - Biết xác định Input, Xử lý và Output.
    - Biết kiểm tra công thức trước khi code.

    ---

    # II. Lý thuyết

    ## 1. Ép kiểu

Ép kiểu là chuyển dữ liệu từ dạng này sang dạng khác khi phù hợp.

## 2. Định dạng số thực

Có thể dùng `f"{x:.2f}"` hoặc `"{:.3f}".format(x)`.

## 3. Ứng dụng

Các bài hình học thường yêu cầu in 2 hoặc 3 chữ số thập phân.

    ---

    # III. Ví dụ minh họa

    ## 1. Trung bình cộng

```python
a = int(input())
b = int(input())
avg = (a + b) / 2
print(f"{avg:.2f}")
```

## 2. Diện tích hình tròn

```python
r = float(input())
s = 3.14 * r * r
print(f"{s:.2f}")
```

    ---

    # IV. Bài tập vận dụng

    ## Bài 1. In một số thực với 3 chữ số thập phân.

## Bài 2. Tính trung bình ba số.

## Bài 3. Ghép tuổi vào câu thông báo.

    ---

    # V. Bài tập về nhà

    ## Bài 1. Đổi độ C sang độ F.

## Bài 2. Tính diện tích tam giác vuông.

## Bài 3. Tạo thông báo chứa số năm nhập vào.

    ---

    # VI. Lỗi học sinh thường gặp

    ## Bài 1. Không ép kiểu trước khi tính.

## Bài 2. In sai số chữ số sau dấu phẩy.

## Bài 3. Dùng `int()` cho chuỗi chứa số thực.

    ---

    # VII. Đề thi thật và bài chuẩn nhập môn

    ## Đề 1. Tính diện tích và in chuẩn định dạng.

## Đề 2. Trung bình cộng có làm tròn.

## Đề 3. In thông báo chứa dữ liệu đầu vào.

    ---

    # VIII. Ghi nhớ cuối bài

    - Đọc kỹ đề.
    - Xác định đúng dữ liệu đầu vào và đầu ra.
    - Viết công thức trước khi triển khai chương trình.

    ---

    # IX. Tóm tắt bài học

    Định dạng output đúng là một phần của lời giải đúng.
