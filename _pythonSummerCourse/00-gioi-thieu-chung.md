---
title: "Khóa học lập trình MIMPython"
permalink: /pythonSummerCourse/
excerpt: "Giới thiệu về khóa học MIMPython năm 2022."
last_modified_at: 2022-08-01
redirect_from:
  - /theme-setup/
toc: true
---

Khóa học lập trình MIMPython dành cho các bạn sinh viên Khoa Toán - Cơ - Tin học có mong muốn tìm hiểu và học cách sử dụng ngôn ngữ lập trình Python.

## 1. Tiến trình khóa học
Khóa học được chia làm hai giai đoạn:

- Giai đoạn 1 kéo dài trong 8 tuần với tổng thời lượng 80 tiếng được phân bố trong các chủ đề dưới đây:
  1. Làm quen với lập trình (5 tiếng)
  2. Nhập môn Python (25 tiếng)
  3. Các công cụ hỗ trợ (15 tiếng)
  4. Python nâng cao (25 tiếng)
  5. Các thư viện quan trọng trong Python (10 tiếng)

  Hàng tuần, học viên tự sắp xếp thời gian đọc tài liệu và xem video về những nội dung của tuần học, sau đó làm bài tập vận dụng những kiến thức này. Mỗi tuần, giảng viên và trợ giảng sẽ tổ chức một buổi trao đổi và chữa bài tập qua nền tảng Google Meet.

- Giai đoạn 2 của khóa học kéo dài trong 4 tuần, trong đó học viên thực hiện một dự án theo chủ đề tự chọn. Đó là một thử thách đòi hỏi học viên phải áp dụng những kiến thức đã được học đồng thời tìm tòi, áp dụng thêm những kiến thức nâng cao khác.

## 2. Tài liệu tham khảo
Ba cuốn sách được liệt kê dưới đây là nguồn tham khảo chính xuyên suốt nội dung khóa học MIMPython.

- Eric Matthes, _Python Crash Course: A Hands-On, Project-Based Introduction to Programming_, 2nd edition, no starch press (2019).
- Julien Danjou, _Serious Python: Black-Belt Advice on Deployment, Scalability, Testing, and More_, no starch press (2018).
- Allen B. Downey, _Think Python: How to Think Like a Computer Scientist_, 2nd edition, O'Reilly Media (2015).

Từ giờ trở đi, ta gọi tên những cuốn sách này lần lượt là _PythonCrashCourse_, _SeriousPython_ và _ThinkPython_.

Ngoài ra khóa học còn tham khảo các tài liệu hướng dẫn sử dụng (documentation) của các thư viện phổ biến (ví dụ như [numpy](https://numpy.org/doc/), [pandas](https://pandas.pydata.org/docs/), [matplotlib](https://matplotlib.org/stable/index.html), [seaborn](https://seaborn.pydata.org/), ...) và các bài viết được đăng tải trên trang web [Real Python Tutorials](https://realpython.com/).

## 3. Lưu ý khi thực hiện bài tập

Trừ khi có những yêu cầu bắt buộc về việc đặt tên, **tất cả** tên biến được sử dụng trong mô tả bài tập đều chỉ mang tính chất minh họa.

Mỗi bài tập lập trình thường bao gồm một danh sách các câu hỏi, yêu cầu liên quan đến chủ đề bài tập. Việc trả lời từng câu hỏi, thực hiện từng yêu cầu một cách riêng biệt không phải cách duy nhất để hoàn thành bài tập. Tùy thuộc vào mỗi bài tập, học viên lựa chọn cách trình bày chương trình phù hợp, trong đó bao gồm (nhưng không giới hạn bởi) những phần sau đây:
- Phần 1: câu trả lời, bình luận (đặt trong phần docstring).
- Phần 2: định nghĩa phương thức (method), lớp (class) cần thiết cho chương trình.
- Phần 3: phần chương trình chính, kèm theo những comment giải thích phù hợp.

Trong trường hợp cần thiết, mỗi bài tập có thể có thêm danh sách những file đính kèm (file input hoặc file output). Tất cả những file đính kèm này (nếu có) **phải đặt trong thư mục con `additionalFolder` của thư mục bài nộp**. Sau đó, thư mục bài nộp được nén lại thành một file zip.

Xét ví dụ với một tuần học có hai bài tập như sau: \
**Bài tập 1.** In ra dòng chữ `Hello World!` trên terminal. \
**Bài tập 2.** Viết chương trình tạo file `output.txt` với nội dung `Hello World!`.

Nếu học viên chỉ thực hiện bài tập 1 thì thư mục bài nộp sẽ chỉ chứa một file
```
week01_assignment01_student15_NguyenVanM.py
```

Nếu học viên thực hiện cả hai bài tập thì thư mục bài nộp sẽ gồm
```
week01_assignment01_student15_NguyenVanM.py
week01_assignment02_student15_NguyenVanM.py
additionalFolder/
  output.txt
```
Trong đó, lời giải cho bài tập 2 nên là
```py
with open('additionalFolder/output.txt', 'w') as f:
    f.write('Hello World!')
```
