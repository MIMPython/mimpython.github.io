---
title: "Khóa học lập trình MIMPython"
permalink: /pythonSummerCourse/
excerpt: "Giới thiệu về khóa học MIMPython năm 2022."
last_modified_at: 2022-10-02
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


## 3. Quy định về nộp bài tập/bình luận code

### 3.1. Quy định chung
- Từ thứ 2 đến Chủ nhật: tự học nội dung của tuần tương ứng và làm bài tập.
- Mỗi tuần học có một danh sách các bài tập, được chia thành bài tập cơ bản và bài tập nâng cao. Học viên được coi là hoàn thành đầy đủ bài tập khi làm đủ số bài tập cơ bản được yêu cầu. Ví dụ cho danh sách bài tập của một tuần:
  + Bài tập cơ bản: 1, 2, 3, 5, 7 (làm tối thiểu 3 bài)
  + Bài tập nâng cao: 4, 6
- Bài nộp của học viên trong từng tuần không được phép chứa (những) file có nội dung rỗng/vô nghĩa. Học viên vi phạm quy định này sẽ bị hủy toàn bộ bài nộp của tuần tương ứng.

### 3.2. Cách chuẩn bị bài nộp
Tất cả bài làm của học viên phải được đặt trong một thư mục rồi nén thành một file zip theo hướng dẫn cụ thể dưới đây.

**Tên file bài tập.** Mỗi bài tập phải được trình bày trong một file riêng biệt với tên được đặt theo mẫu `weekXX_assignmentYY_studentZZ_HoVaTen.py` trong đó, `XX` là số thứ tự tuần, `YY` là số thứ tự của bài tập, `ZZ` là số thứ tự (id) của học viên ở trong danh sách (id từ 1 đến 9 thì viết thêm số 0, chẳng hạn như 01, 02, ...) và Họ và tên của học viên viết liền không dấu, ví dụ `week03_assignment02_student01_PhungThiThuAn.py`. **Lưu ý:** File bài tập chỉ cho phép file py.

**Thư mục bổ sung.** Trong trường hợp cần thiết, mỗi bài tập có thể có thêm danh sách những file đính kèm (file input hoặc file output). Tất cả những file đính kèm này (nếu có) **phải đặt trong thư mục con `additionalFolder`**. Để thuận tiện cho việc quản lý bài nộp, tên file _nên_ có tiền tố theo mẫu `weekXX_assignmentYY_studentZZ_HoVaTen_` với `XX, YY, ZZ` được quy ước như trên. Ví dụ một số file: `week01_assignment02_student03_NguyenVanA_data.txt`, `week01_assignment02_student03_NguyenVanA_image.png`.

Trong mỗi file bài tập, học viên cần liệt kê tên của tất cả những file bổ sung có liên quan đến bài tập đó.

Để minh họa nội dung của thư mục bài nộp, xét ví dụ với một tuần học có hai bài tập như sau:
- **Bài tập 1.** In ra dòng chữ `Hello World!` trên terminal.
- **Bài tập 2.** Viết chương trình tạo file `output.txt` với nội dung `Hello World!`.

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

**Thư mục chính.** Tất cả bài làm đặt trong thư mục bài nộp, với tên được đặt theo mẫu `weekXX_studentZZ_HoVaTen`. Sau đó, thư mục này được nén lại thành một file zip với tên được đặt theo mẫu `weekXX_studentZZ_HoVaTen.zip`, ví dụ `week03_student01_PhungThiThuAn.zip`.


### 3.3. Quy định nộp bài tập, bình luận
- Mỗi học viên **chỉ nộp duy nhất một file zip** cho mỗi tuần học. Deadline nộp bài tập 23h59, Chủ nhật hàng tuần.
- Mỗi học viên thực hiện bình luận bài tập theo phân công. Deadline bình luận bài tập 14h, Thứ 4 hàng tuần.
Ví dụ: một tuần học diễn ra từ 13/06 (T2) đến 19/06 (CN) thì deadline nộp bài tập là 23h59 19/06 (CN) và deadline bình luận bài tập là 14h 22/06 (T4).

## 4. Một số chú ý khác
Trừ khi có những yêu cầu bắt buộc về việc đặt tên, **tất cả** tên biến được sử dụng trong mô tả bài tập đều chỉ mang tính chất minh họa.

Mỗi bài tập lập trình thường bao gồm một danh sách các câu hỏi, yêu cầu liên quan đến chủ đề bài tập. Việc trả lời từng câu hỏi, thực hiện từng yêu cầu một cách riêng biệt không phải cách duy nhất để hoàn thành bài tập. Tùy thuộc vào mỗi bài tập, học viên lựa chọn cách trình bày chương trình phù hợp, trong đó bao gồm (nhưng không giới hạn bởi) những phần sau đây:
- Phần 1: câu trả lời, bình luận (đặt trong phần docstring).
- Phần 2: định nghĩa phương thức (method), lớp (class) cần thiết cho chương trình.
- Phần 3: phần chương trình chính, kèm theo những comment giải thích phù hợp.

Chỉ nên sử dụng hàm `input()` và cấu trúc `from someModule import *` trong trường hợp bất khả kháng, tức là khi đề bài bắt buộc sử dụng chúng hoặc không còn cách khả thi khác.

Ngoài ra, học viên cần soát lại chương trình để loại bỏ những dòng import không cần thiết xuất hiện trong file `.py`, ví dụ như
```py
from asyncio.windows_events import NULL
from dis import dis
from operator import indexOf
from turtle import distance
```


## 5. Lời cảm ơn
Lời cảm ơn chân thành nhất chắc chắn phải dành tới thầy D. với ý tưởng khởi nguồn về khóa học này cũng như toàn bộ trang web MIMPython.

Dưới đây là danh sách các thành viên đã dành thời gian và công sức cho khóa học. Cảm ơn các bạn vì sự đóng góp này.
- Đặng Quý Anh, Đinh Hoàng Nhật Minh, [Hoàng Anh Quân](https://quanhoang-pm.github.io/), Nguyễn Văn Quân, Trần Bá Tuấn, Trần Thanh Tùng thực hiện tổng hợp nội dung các bài học, đồng thời đưa nhận xét cho học viên về bài làm của họ hàng tuần.
- Hoàng Anh Quân và Lê Quốc Tuấn biên soạn bài tập hàng tuần.
- Trần Bá Tuấn và Trần Thanh Tùng quản lý danh sách học viên của khóa học.
- Nguyễn Văn Quân và Trần Thanh Tùng thiết kế website MIMPython.
