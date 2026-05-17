# Bài 13. Bài tập vận dụng cấu trúc tuần tự

    ---

    # I. Mục tiêu bài học

    ## 1. Về kiến thức

    - Củng cố nhập xuất, phép toán, công thức, đổi đơn vị, xử lý chữ số.
- Biết tự chọn công thức phù hợp.
- Biết kiểm tra lời giải bằng dữ liệu nhỏ.

    ## 2. Về kỹ năng

    - Viết được chương trình Python đúng cú pháp.
    - Áp dụng được nội dung bài học vào bài toán nhập môn.
    - Trình bày lời giải rõ ràng theo hướng giáo án.

    ## 3. Về tư duy

    - Biết xác định Input, Xử lý và Output.
    - Biết kiểm tra công thức trước khi code.

    ---

    # II. Lý thuyết

    ## 1. Nhóm dạng bài

Công thức số học, hình học, đổi đơn vị, chia nguyên và chia dư.

## 2. Quy trình

Phân tích đề → viết công thức → code → test.

## 3. Mục tiêu

Tăng độ tự lập trước khi bước sang rẽ nhánh.

    ---

    # III. Ví dụ minh họa

    ## 1. Tổng chữ số số ba chữ số

```python
n = int(input())
a = n // 100
b = (n // 10) % 10
c = n % 10
print(a + b + c)
```

## 2. Tính tiền sau giảm giá

```python
price = float(input())
quantity = int(input())
discount = float(input())
cost = price * quantity * (100 - discount) / 100
print(f"{cost:.2f}")
```

    ---

    # IV. Bài tập vận dụng

    ## Bài 1. Tổng chữ số số ba chữ số.

## Bài 2. Đổi thời gian.

## Bài 3. Khoảng cách tới gốc tọa độ.

## Bài 4. Chu vi tam giác.

## Bài 5. Tổng bình phương.

    ---

    # V. Bài tập về nhà

    ## Bài 1. Tính số viên gạch lát nền.

## Bài 2. Tính trung bình có trọng số.

## Bài 3. Đổi ngày giờ phút thành tổng phút.

    ---

    # VI. Lỗi học sinh thường gặp

    ## Bài 1. Không nhận dạng dạng bài.

## Bài 2. Dùng sai công thức.

## Bài 3. Không test với ví dụ nhỏ.

    ---

    # VII. Đề thi thật và bài chuẩn nhập môn

    ## Đề 1. Lát gạch.

## Đề 2. Khoảng cách hai điểm.

## Đề 3. Tổng dãy.

    ---

    # VIII. Ghi nhớ cuối bài

    - Đọc kỹ đề.
    - Xác định đúng dữ liệu đầu vào và đầu ra.
    - Viết công thức trước khi triển khai chương trình.

    ---

    # IX. Tóm tắt bài học

    Bài vận dụng giúp gom toàn bộ kỹ năng của chương thành năng lực giải đề.
