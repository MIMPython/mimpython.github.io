---
title: "Bài 16. Class nâng cao"
permalink: /pythonSummerCourse/week-07-advanced-class/
last_modified_at: 2022-08-22
redirect_from:
  - /theme-setup/
toc: false
---


Nội dung tóm tắt của bài học đang được hoàn thiện.

## Phần 1. Kế thừa trong Python
- Cú pháp trong Python.
- Ví dụ: class Square kế thừa từ class Rectangle.
- Cách sử dụng `super()`.
- [nâng cao] method resolution order, diamond inheritance.

## Phần 2. property trong Python
- Ý nghĩa: kích hoạt một chuỗi hành động khi thuộc tính tương ứng được gọi trong chương trình.
- Ví dụ: thuộc tính `area` nên là một property của class Rectangle, được tính từ `length` và `width`.

## Phần 3. Dunder methods (a.k.a. methods with trailing double underscores)
- Ý nghĩa: giúp việc viết các phép toán một cách trực quan hơn.
- Ví dụ: class Fraction lưu tử số (numerator) và mẫu số (denominator). Thực hiện các `dunder methods` phù hợp, ví dụ như `__repr__`, `__add__`, `__lt__`, ...

## Phần 4. (kiến thức nâng cao) - abstract base class
Học viên tự tìm hiểu kiến thức trên Internet.

> Nội dung trên chỉ là tóm tắt, học viên cần đọc các tài liệu liệt kê trong phần tài liệu tham khảo dưới đây.

## Tài liệu tham khảo

Tài liệu chính
- https://realpython.com/inheritance-composition-python/
- https://realpython.com/lessons/object-inheritance-python/
- https://realpython.com/lessons/inheritance-python/
- [Bài viết về operator function overloading](https://realpython.com/operator-function-overloading/) trên trang web Real Python

Tài liệu bổ sung
- [Abstract base class](https://docs.python.org/3/library/abc.html) trong Python
- ThinkPython (trang 195-222)
