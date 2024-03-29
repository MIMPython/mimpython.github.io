---
title: "Khóa học lập trình MIMPython"
permalink: /pythonSummerCourse/
excerpt: "Giới thiệu về khóa học MIMPython"
last_modified_at: 2024-02-07
redirect_from:
  - /theme-setup/
toc: true
---

Khóa học lập trình MIMPython dành cho các bạn sinh viên [Khoa Toán - Cơ - Tin học](http://mim.hus.vnu.edu.vn/) có mong muốn tìm hiểu và học cách sử dụng ngôn ngữ lập trình Python.

## 1. Tiến trình khóa học
Khóa học được chia làm hai giai đoạn:

- Giai đoạn 1 kéo dài trong 14 tuần gồm 8 module với tổng thời lượng 80 tiếng được phân bố trong các chủ đề dưới đây:
  1. Làm quen với lập trình (5 tiếng)
  2. Nhập môn Python (25 tiếng)
  3. Các công cụ hỗ trợ (15 tiếng)
  4. Python nâng cao (25 tiếng)
  5. Các thư viện quan trọng trong Python (10 tiếng)

  Hàng tuần, học viên tự sắp xếp thời gian đọc tài liệu và xem video về những nội dung của tuần học, sau đó làm bài tập vận dụng những kiến thức này và bình luận code của học viên khác. Sau mỗi module, giảng viên và trợ giảng sẽ tổ chức một buổi trao đổi trực tiếp hoặc qua nền tảng Google Meet.

  Dưới đây là lịch trình nộp bài/bình luân code cho khóa học MIMPython năm 2023.

| Module | Thời hạn nộp bài | Thời hạn bình luận code | Buổi trao đổi |
|:---:|:---:|:---:|:---:|
| 1 | 22h 12/08/2023 | 16h 15/08/2023 | 20h30-22h 15/08/2023 (online) |
| 2 | 22h 26/08/2023 | 16h 29/08/2023 | 20h30-22h 29/08/2023 (online) |
| 3 | 22h 09/09/2023 | 16h 12/09/2023 | 15h-17h 13/09/2023 (offline) |
| 4 | 22h 23/09/2023 | 16h 26/09/2023 | 20h30-22h 26/09/2023 (online) |
| 5 | 22h 30/09/2023 | 16h 03/10/2023 | 20h30-22h 03/10/2023 (online) |
| 6 | 22h 14/10/2023 | 16h 17/10/2023 | 20h30-22h 17/10/2023 (online) |
| 7 | 22h 28/10/2023 | 16h 31/10/2023 | 20h30-22h 31/10/2023 (online) |
| 8 | 22h 11/11/2023 | 16h 14/11/2023 | 20h30-22h 14/11/2023 (online) |

- Giai đoạn 2 của khóa học kéo dài trong 4 tuần, trong đó học viên thực hiện một dự án theo chủ đề tự chọn. Đây là một thử thách đòi hỏi học viên phải áp dụng những kiến thức đã học đồng thời tìm hiểu và áp dụng thêm những kiến thức nâng cao khác.

Buổi báo cáo kết quả dự án của học viên khóa học MIMPython năm 2023 diễn ra vào 13h-15h ngày 31/1/2024.


## 2. Tài liệu tham khảo
Ba cuốn sách được liệt kê dưới đây là nguồn tham khảo chính xuyên suốt nội dung khóa học MIMPython.

- Eric Matthes, _Python Crash Course: A Hands-On, Project-Based Introduction to Programming_, 2nd edition, no starch press (2019).
- Julien Danjou, _Serious Python: Black-Belt Advice on Deployment, Scalability, Testing, and More_, no starch press (2018).
- Allen B. Downey, _Think Python: How to Think Like a Computer Scientist_, 2nd edition, O'Reilly Media (2015).

Từ giờ trở đi, ta gọi tên những cuốn sách này lần lượt là _PythonCrashCourse_, _SeriousPython_ và _ThinkPython_.

Ngoài ra khóa học còn tham khảo các tài liệu hướng dẫn sử dụng (documentation) của các thư viện phổ biến (ví dụ như [numpy](https://numpy.org/doc/), [pandas](https://pandas.pydata.org/docs/), [matplotlib](https://matplotlib.org/stable/index.html), [seaborn](https://seaborn.pydata.org/), ...) và các bài viết được đăng tải trên trang web [Real Python Tutorials](https://realpython.com/).


## 3. Quy định về nộp bài tập/bình luận code

### 3.1. Quy định chung
- Sinh viên tự học nội dung của module tương ứng và làm bài tập.
- Mỗi module bài học có một danh sách các bài tập, được chia thành bài tập cơ bản và bài tập nâng cao. Học viên được coi là hoàn thành đầy đủ bài tập khi làm đủ số bài tập cơ bản được yêu cầu. Ví dụ cho danh sách bài tập của một tuần:
  + Bài tập cơ bản: 1, 2, 3, 5, 7 (làm tối thiểu 3 bài)
  + Bài tập nâng cao: 4, 6
- Bài nộp của học viên trong từng module không được phép chứa (những) file có nội dung rỗng/vô nghĩa. Học viên vi phạm quy định này sẽ bị hủy toàn bộ bài nộp của module tương ứng.

### 3.2. Thư mục bài nộp
Tất cả bài làm của học viên phải được đặt trong một thư mục chính, với hướng dẫn cụ thể dưới đây.

**Thư mục chính** chứa tất cả bài làm (gồm các file `.py` và thư mục bổ sung) với tên được đặt theo mẫu `moduleXX_studentZZ_HoVaTen`.

**File bài tập** chứa code Python và có thêm:
- Tóm tắt đề bài
- Câu lệnh chạy chương trình
- (Tóm tắt) kết quả đầu ra
- Giải thích những bước thực hiện của chương trình

Mỗi bài tập phải được trình bày trong một file riêng biệt với tên được đặt theo mẫu `moduleXX_assignmentYY_studentZZ_HoVaTen.py` trong đó
- `XX` là số thứ tự module,
- `YY` là số thứ tự của bài tập,
- `ZZ` là số thứ tự (id) của học viên ở trong danh sách,
- `HoVaTen` là họ và tên của học viên viết liền không dấu.

Nếu giá trị số bé hơn 10 thì viết thêm số 0 ở trước, chẳng hạn như 01, 02, ... Ví dụ một tên file hợp lệ: `module03_assignment01_student02_PhungThuAn.py`.

**Thư mục bổ sung.** Trong trường hợp cần thiết, mỗi bài tập có thể có thêm danh sách những file đính kèm (dữ liệu đầu vào / kết quả đầu ra). Tất cả những file đính kèm này (nếu có) **phải đặt trong thư mục con có tên là `additionalFolder`**. Để thuận tiện cho việc quản lý bài nộp, tên các file đính kèm _nên_ có tiền tố theo mẫu `moduleXX_assignmentYY_studentZZ_HoVaTen_` với `XX, YY, ZZ` được quy ước như trên. Ví dụ một số file:
```txt
module01_assignment02_student03_NguyenVanA_data.txt
module01_assignment02_student03_NguyenVanA_image.png
```

Trong mỗi file bài tập, học viên cần liệt kê tên của tất cả những file bổ sung có liên quan đến bài tập đó.

Để minh họa nội dung của thư mục bài nộp, xét ví dụ với một tuần học có hai bài tập như sau:
- **Bài tập 1.** In ra dòng chữ `Hello World!` trên terminal.
- **Bài tập 2.** Viết chương trình tạo file `output.txt` với nội dung `Hello World!`.

Nếu học viên chỉ thực hiện bài tập 1 thì thư mục bài nộp sẽ chỉ chứa một file
```
module01_assignment01_student15_NguyenVanM.py
```

Nếu học viên thực hiện cả hai bài tập thì thư mục bài nộp sẽ gồm
```
module01_assignment01_student15_NguyenVanM.py
module01_assignment02_student15_NguyenVanM.py
additionalFolder/
  output.txt
```

### 3.3. Quy trình làm bài / nộp bài / bình luận code
- Khi bắt đầu một module, tạo pull request tới repository [MIMPython2023-Assignment](https://github.com/MIMPython/MIMPython2023-Assignment) với tiêu đề có format
  ```txt
  [submission] module01_student02_HoVaTen
  ```
- Trong quá trình học, commit bài làm vào pull request đã tạo. Đồng thời, nhận bình luận từ các học viên khác để cải thiện bài làm.
- Trước khi kết thúc hạn nộp bài, học viên nộp link pull request này (dưới dạng một file `.txt`) vào lớp học trên Google Classroom.

Ghi chú:
- Các pull request nộp bài sẽ được merge vào nhánh main bởi quản lý lớp học.
- Học viên cần theo dõi các pull request của học viên khác và đưa bình luận/góp ý/trao đổi _trong pull request_ tương ứng. Hạn chế bình luận trong từng commit riêng lẻ.
- Mỗi học viên chỉ tạo đúng một pull request cho mỗi module, không tự ý đóng pull request trừ trường hợp đặc biệt.


## 4. Một số chú ý khác
Trừ khi có những yêu cầu bắt buộc về việc đặt tên, _tất cả_ tên biến được sử dụng trong mô tả của đề bài đều chỉ mang tính chất minh họa.

Mỗi bài tập lập trình thường bao gồm một danh sách các câu hỏi, yêu cầu liên quan đến chủ đề bài tập. Việc trả lời từng câu hỏi, thực hiện từng yêu cầu một cách riêng biệt không phải cách duy nhất để hoàn thành bài tập. Tùy thuộc vào mỗi bài tập, học viên lựa chọn cách trình bày chương trình phù hợp, trong đó bao gồm (nhưng không giới hạn bởi) những phần sau đây:
- Phần 1: câu trả lời, bình luận (đặt trong phần docstring).
- Phần 2: định nghĩa phương thức (method), lớp (class) cần thiết cho chương trình.
- Phần 3: phần chương trình chính, kèm theo những comment giải thích phù hợp.

Chỉ nên sử dụng hàm `input()` và wildcard import `from someModule import *` trong trường hợp bất khả kháng, tức là khi đề bài bắt buộc sử dụng chúng hoặc không còn cách khả thi khác.

Ngoài ra, học viên cần soát lại chương trình để loại bỏ những dòng import không cần thiết xuất hiện trong file `.py` (có thể do IDE tự động bổ sung), ví dụ như
```py
from asyncio.windows_events import NULL
from dis import dis
from operator import indexOf
from turtle import distance
```


## 5. Lời cảm ơn
Xin gửi lời cảm ơn chân thành nhất tới thầy Hoàng Nam Dũng với ý tưởng khởi nguồn về khóa học này cũng như toàn bộ trang web MIMPython.

Dưới đây là danh sách các thành viên đã dành thời gian và công sức tổ chức khóa học trong năm đầu tiên (Hè 2022). Cảm ơn tất cả các bạn vì những đóng góp này.
- Đặng Quý Anh, Đinh Hoàng Nhật Minh, [Hoàng Anh Quân](https://quanhoang-pm.github.io/), Nguyễn Văn Quân, Trần Bá Tuấn, Trần Thanh Tùng thực hiện tổng hợp nội dung các bài học, đồng thời đưa nhận xét cho học viên về bài làm của họ hàng tuần.
- Hoàng Anh Quân và Lê Quốc Tuấn biên soạn bài tập hàng tuần.
- Trần Bá Tuấn và Trần Thanh Tùng quản lý danh sách học viên của khóa học.
- Nguyễn Văn Quân và Trần Thanh Tùng thiết kế [website MIMPython](https://mimpython.github.io/).
