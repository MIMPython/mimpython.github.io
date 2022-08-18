---
title: "Bài tập tuần 6"
permalink: /pythonSummerCourse/week-06-assignment/
last_modified_at: 2022-08-18
redirect_from:
  - /theme-setup/
toc: false
---


Bài tập tuần 6 gồm .. bài tập, bao gồm
- .. bài tập cơ bản: 1, 2, 3, 4 (làm tối thiểu .. bài).
- .. bài tập nâng cao: ... .


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


**Bài tập 3.** *(largest product in a grid)* \
Giải quyết [bài toán 11](https://projecteuler.net/problem=11) trên trang web Project Euler.


**Bài tập 4.** *(plotting method)* \
Thiết kế class về các đối tượng hình học (điểm, đoạn thẳng, hình tròn, ...) trong đó có những phương thức vẽ hình phù hợp. \
Gợi ý về cách sử dụng chương trình
```py
fig, ax = plt.subplots()
point.plot(ax, color = 'red')
circle.plot(ax, color = 'blue')
fig.savefig('image.svg')
fig.show()
```


**Bài tập 5.** ([Savoury Days](http://www.savourydays.com/)) Cắt, ghép ảnh dưới đây để tạo một ảnh với dòng chữ "Bánh Trung thu ăn kiêng".

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

<center> Ảnh: Savoury Days fanpage </center>


**Bài tập.** *(examination timetabling)* \
Sử dụng thư viện pandas và (những) thư viện vẽ hình phù hợp để phân tích dữ liệu đầu vào của bài toán xếp lịch thi của Trường Đại học Khoa học Tự nhiên. Dữ liệu có thể tải xuống tại [đây](/assets/dataset/examinationTimetablingDataset.zip).


**Bài tập.** *(Conway's game of life)* \
Viết một chương trình mô phỏng [Conway's game of life](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life).
