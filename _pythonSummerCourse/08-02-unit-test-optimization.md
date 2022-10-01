---
title: "Bài 20. Kiểm thử và tối ưu hóa code"
permalink: /pythonSummerCourse/week-08-unit-testing-optimizaion/
last_modified_at: 2022-10-01
redirect_from:
  - /theme-setup/
toc: false
---

_Tác giả: Hoàng Anh Quân_

Một số lưu ý liên quan tới kiểm thử (testing) và tối ưu hóa code trong Python

- Thư viện pytest thực hiện việc kiểm thử code Python bằng cách thực thi các test case mà người dùng đặt ra.
- Nên sử dụng type hint (type annotation) để chỉ ra kiểu dữ liệu của các đối tượng trong Python.
- Thuộc tính `.dt` của `pandas.Series` rất hữu dụng, tham khảo tại [đây](https://pandas.pydata.org/docs/user_guide/basics.html).
- Tận dụng các phương thức có sẵn trong các thư viện, ví dụ như `groupby()` trong pandas.
- Sử dụng `yield` và `functools.lrucache` để tối ưu hóa bộ nhớ.

> Nội dung trên chỉ là tóm tắt, học viên cần đọc các tài liệu liệt kê trong phần tài liệu tham khảo dưới đây.

## Tài liệu tham khảo

Tài liệu chính
- SeriousPython (trang 92-121, 183-214)

Tài liệu bổ sung
- Thư viện [cProfile](https://docs.python.org/3/library/profile.html) trong Python
- [Bài viết về thư viện pytest](https://realpython.com/courses/test-driven-development-pytest/) trên trang web Real Python
