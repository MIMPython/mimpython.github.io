---
title: "Bài tập tuần 6"
permalink: /pythonSummerCourse/week-06-assignment/
last_modified_at: 2023-06-11
redirect_from:
  - /theme-setup/
toc: false
---


Bài tập tuần 6 gồm 12 bài tập, bao gồm
- 6 bài tập cơ bản: 1, 2, 3, 4, 5, 6 (làm tối thiểu 4 bài).
- 6 bài tập nâng cao: 7, 8, 9, 10, 11, 12.

Cập nhật
- 19/08/2022. Bổ sung bài tập 9, bài tập 10.
- 29/08/2022. Bổ sung bài tập 11, bài tập 12.


## Danh sách bài tập

**Bài tập 1.** *(numpy)* \
Mục tiêu của bài tập này là so sánh tốc độ thực hiện các phép toán tính tổng khi sử dụng thư viện `numpy` với khi sử dụng cách cài đặt thủ công. Dưới đây là danh sách _gợi ý_, không bắt buộc, những công việc cần thực hiện để giải quyết mục tiêu đề ra: \
a) Viết một hàm nhận vào hai số nguyên dương $m,n$ và trả về một bảng hai chiều (kiểu `list` hoặc `tuple`) gồm $m$ hàng và $n$ cột chứa các số tự nhiên ngẫu nhiên. \
b) Không sử dụng thư viện bổ sung, viết một hàm tính tổng các số thuộc cùng một cột của một bảng số cho trước.
```py
array = foo(3, 5)
array = [
  [2, 7, 3, 0, 0],
  [6, 4, 4, 3, 1],
  [0, 0, 9, 1, 2],
]
result = bar(array)
result = [8, 11, 16, 4, 3]
```

c) Sử dụng kiểu dữ liệu `numpy.ndarray`, thực hiện yêu cầu tương tự như hai ý (a) và (b). \
d) So sánh **tốc độ thực hiện của hai hàm tính tổng các số theo cột** đã cài đặt ở trên. Một số lưu ý:
- Nên kiểm nghiệm kết quả trên những bảng số với kích thước lớn, đồng thời chạy chương trình nhiều lần để cho ra kết quả mang ý nghĩa thống kê.
- Có thể sử dụng thư viện `time` để đo thời gian, cụ thể là dùng hàm `time.time()` hoặc `time.perf_counter()`.
- Cần so sánh tốc độ thực hiện chương trình trên những bộ dữ liệu đầu vào _tương tự_ nhau.
- Cần tách riêng thời gian tạo dữ liệu bảng số và thời gian tính tổng các số.
- Nên thể hiện kết quả so sánh thông qua hình vẽ.

e) Trả lời câu hỏi tương tự cho việc tính tổng các số thuộc cùng một hàng của bảng số.


**Bài tập 2.** *(numpy methods)* \
Một số hàm trong thư viện `numpy` được liệt kê dưới đây.
```
- mean, median
- max, min
- argmax, argmin
- linspace, arange
- repeat, random
- all, any
- ones, zeros
- savetxt, loadtxt
- apply_along_axis
- where
- isclose
- polyfit, polyval
- roots
```

Hãy tìm hiểu một số hàm trong thư viện `numpy` (không nhất thiết thuộc danh sách trên) và thực hiện những yêu cầu sau:
- Nêu ý nghĩa của hàm, cho ví dụ.
- Viết chương trình thực hiện đúng ý nghĩa đó mà hạn chế sử dụng thư viện `numpy`. Có thể sử dụng thư viện để khởi tạo mảng số nếu cần thiết.
- So sánh tốc độ thực thi giữa hai cách làm: phương pháp thủ công và phương pháp sử dụng `numpy`.


**Bài tập 3.** *(plotting method)* \
Thiết kế class về các đối tượng hình học (điểm, đoạn thẳng, hình tròn, ...) trong đó có những phương thức vẽ hình phù hợp. \
Gợi ý về cách sử dụng chương trình
```py
fig, ax = plt.subplots()
point.plot(ax, color='red')
circle.plot(ax, color='blue')
fig.savefig('image.svg')
fig.show()
```


**Bài tập 4.** ([Savoury Days](http://www.savourydays.com/)) Cắt, ghép ảnh dưới đây để tạo một ảnh với dòng chữ "Bánh Trung thu ăn kiêng".

<div>
    <img src="/assets/images/courses/homework/SD_mooncake.png"
    style="width:50%;
    max-width:700px;
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding-top:20px;
    padding-bottom:20px;">
</div>

<center> Ảnh: Savoury Days </center>

**Bài tập 5.** *(iterating a directory)* \
Viết một hàm liệt kê tất cả những tệp tin và thư mục là con trực tiếp của một thư mục cho trước, đồng thời trả lời xem mỗi đối tượng là tệp tin hay là thư mục. Học viên tự quyết định kiểu dữ liệu trả về phù hợp.

Ví dụ với cây thư mục như sau
```
foo/
  bar/
    fileA.txt
    fileB.png
  ham/
  egg/
    fileC.pdf
  fileD.svg
  fileE.tif
```
chương trình sẽ có input/output dưới đây
```
Input: /path/to/folder/foo
Output:
- object bar, type folder
- object ham, type folder
- object egg, type folder
- object fileD.svg, type file
- object fileE.tif, type file
```

Gợi ý. Tra cứu trên stackoverflow.


**Bài tập 6.** *(examination timetabling analysis)* \
Sử dụng thư viện `pandas` và (những) thư viện vẽ hình phù hợp để phân tích dữ liệu đầu vào của bài toán xếp lịch thi cho Trường Đại học Khoa học Tự nhiên, ĐHQGHN trong học kỳ II năm học 2021-2022.

Bộ dữ liệu đầu vào gồm có
- File `exams.csv` chứa danh sách mã môn học (`subjectCode`) và các mã lớp học (`classCode`) tương ứng. Một mã môn học có thể gồm nhiều mã lớp học khác nhau. Có thể sử dụng `pandas` đọc file này bằng câu lệnh `pd.read_csv(pathToFile)`.
- File nén `examinationTimetablingDataset.zip` chứa các file `csv`, mỗi file có tên (không tính phần mở rộng - extension) là một mã lớp học, nội dung mỗi file là danh sách mã sinh viên đăng ký lớp học tương ứng.

Dưới đây là phần mô tả những `DataFrame` có liên quan tới bộ dữ liệu này.

- DataFrame thứ nhất
  + Cột 1: một mã sinh viên
  + Cột 2: một mã lớp học mà sinh viên đó đăng ký
  + Cột 3: một mã môn học tương ứng với mã lớp học kể trên

  Ví dụ, với một sinh viên đăng ký 5 môn học thì trong DataFrame này sẽ có đúng 5 dòng có cột 1 là mã sinh viên của người này.

- DataFrame thứ hai
  + Cột 1: một mã lớp học
  + Cột 2: một `list` tất cả mã sinh viên đăng ký lớp học đó
  + Cột 3: số sinh viên đăng ký lớp học đó

- DataFrame thứ ba
  + Cột 1: một mã môn học
  + Cột 2: một `list` tất cả mã sinh viên đăng ký môn học đó
  + Cột 3: số sinh viên đăng ký môn học đó

- DataFrame thứ tư
  + Cột 1: một mã sinh viên
  + Cột 2: một `list` tất cả lớp học mà sinh viên đó đăng ký
  + Cột 3: một `list` tất cả môn học mà sinh viên đó đăng ký

- DataFrame thứ năm
  + Cột 1: một mã môn học
  + Cột 2: một mã môn học (nên khác với giá trị ở cột 1)
  + Cột 3: một `list` tất cả sinh viên cùng đăng ký hai môn học kể trên
  + Cột 4: số sinh viên cùng đăng ký hai môn học kể trên

Thực hiện các yêu cầu dưới đây. \
a) Tạo các DataFrame được liệt kê ở trên, chọn tên biến và tên cột phù hợp. Ngoài ra, các dòng trong mỗi DataFrame cũng nên được sắp xếp theo một thứ tự hợp lý. \
b) Xuất những DataFrame này (với định dạng file phù hợp) vào thư mục bổ sung trong thư mục nộp bài. \
c) Thống kê các thông tin liên quan tới bộ dữ liệu trên (càng nhiều càng tốt). Dưới đây là _gợi ý_ cho một số khía cạnh của bộ dữ liệu.
- Số sinh viên, lớp học, môn học của học kỳ.
- Số môn trung bình một sinh viên đăng ký.
- Sinh viên đăng ký nhiều môn học nhất, ít môn học nhất.
- Môn học có nhiều (hoặc ít) sinh viên đăng ký nhất.
- Có sinh viên nào học hai lớp có chung mã môn hay không?
- Hai môn học có chung nhiều sinh viên nhất.

d) Tạo các hình vẽ phù hợp để minh họa cho những thống kê bên trên. Xuất những hình vẽ này vào thư mục bổ sung trong thư mục nộp bài. \
e) (câu hỏi thêm) Tìm kiếm thêm những dữ liệu liên quan để trả lời những câu hỏi không hiển nhiên liên quan đến bộ dữ liệu này. Ví dụ như
> Trong những khoa thuộc Trường Đại học Khoa học Tự nhiên, khoa nào có nhiều sinh viên nhất?

f) (câu hỏi thêm) Đọc thêm khái niệm về [khoảng cách](https://en.wikipedia.org/wiki/Distance_(graph_theory)) và [đường kính](https://mathworld.wolfram.com/GraphDiameter.html) của một đồ thị. Sau đó xây dựng những đồ thị có liên quan tới bộ dữ liệu này và đưa ra những thông tin liên quan đến đồ thị vừa xây dựng.

**Credit:** Dữ liệu trong bài tập này được thu thập bởi nhóm sinh viên Trường Đại học Khoa học Tự nhiên, ĐHQGHN nghiên cứu bài toán xếp lịch thi của Trường. Nội dung bài tập được chuẩn bị bởi Trần Thanh Tùng và Hoàng Anh Quân.


**Bài tập 7.** *(largest product in a grid)* \
Giải quyết [bài toán 11](https://projecteuler.net/problem=11) trên trang web Project Euler.


**Bài tập 8.** *(Conway's game of life)* \
Viết một chương trình mô phỏng [Conway's game of life](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life).


**Bài tập 9.** *(clock)* \
a) Viết chương trình vẽ hình ảnh một chiếc đồng hồ số và một chiếc đồng hồ kim thể hiện một thời điểm bất kỳ trong ngày, ví dụ 04h20m19s. \
b) Dựng một đoạn video mô phỏng sự hoạt động của một chiếc đồng hồ số và/hoặc một chiếc đồng hồ kim. Gợi ý: sử dụng thư viện `manim`.


**Bài tập 10.** *(Gauss elimination)* \
Viết một chương trình tính định thức của một ma trận (lưu dưới dạng một `numpy array`) bằng phương pháp khử Gauss. So sánh tốc độ của chương trình so với phương thức tính định thức có sẵn trong thư viện `numpy`.


**Bài tập 11.** *(green screen effect)* \
Nền xanh lá cây (green screen) thường được sử dụng trong quá trình ghi hình nhằm phục vụ việc thay đổi nền trong quá trình hậu kỳ. Hãy viết một chương trình thay đổi nền ảnh với
- Dữ liệu đầu vào: một ảnh chứa đối tượng trên nền xanh và một ảnh nền thật.
- Dữ liệu đầu ra: một ảnh chứa đối tượng trên nền thật.


**Bài tập 12.** *(Polyomino)* \
a) Viết một hàm thực hiện phép xoay một `numpy array` một góc 90 độ theo chiều kim đồng hồ.

```py
inputArr = np.array([
    [0, 1, 0],
    [0, 1, 1],
])
outputArr = array([
    [0, 0],
    [1, 1],
    [1, 0],
])
```

b) Xây dựng class `Polyomino` để kiểm chứng những nhận xét có trong [bài viết về Polyomino](https://en.wikipedia.org/wiki/Polyomino) trên Wikipedia.
