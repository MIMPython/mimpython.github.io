### Assignment 10 - numpy

Bài tập 1. Cho một bảng hai chiều gồm các số (với cách xây dựng/lưu trữ dữ liệu tùy chọn). Hãy tính tổng các số theo các cột của bảng này. Bạn hãy thực hiện những yêu cầu sau:
a) Giải quyết vấn đề mà không sử dụng numpy (tự chọn kiểu dữ liệu phù hợp cho bảng số).
b) So sánh thời gian thực thi của hai cách tiếp cận với dữ liệu đầu vào là các bảng số đủ lớn.
c) Tìm hiểu cách sử dụng hàm numpy.sum()

Bài tập 2. Cho một danh sách gồm các đối tượng (objects) trong numpy.
- mean, median
- max, min
- argmax, argmin
- linspace, arange
- repeat
- random
- all, any
- apply\_along\_axis
- ones, zeros
- where
- isclose
- polyfit, polyval
- roots

Hãy tìm hiểu một số đối tượng trong danh sách trên bằng cách thực hiện các yêu cầu sau đây (đối với mỗi đối tượng được chọn):
- Nêu mục đích sử dụng của đối tượng, cho ví dụ.
- Viết hàm/chương trình thực hiện mục đích đó mà không sử dụng numpy.
- So sánh thời gian thực thi giữa hai phiên bản, một phiên bản sử dụng numpy và một phiên bản không sử dụng numpy.

Bài tập 3. Largest product in a grid. https://projecteuler.net/problem=11
Viết một chương trình giải quyết bài toán trong Project Euler problem 11.

Bài tập 4. class Vector
Hãy xây dựng class Vector để biểu diễn lớp các vector trong không gian $\mathbb{R}^3$. Class này cần hỗ trợ các phép toán cơ bản của vector, ví dụ như cộng/trừ hai vector, nhân vector với một vô hướng (scalar), tích vô hướng giữa hai vector, tích có hướng giữa hai vector, ...

Bài tập 5. Gauss Elimination. Viết một chương trình tính định thức của một ma trận bằng phương pháp khử Gauss.
Thư viện numpy có một phương thức được dùng để tính định thức của một ma trận. Hãy sử dụng method này và so sánh với chương trình đã viết.

Bài tập 6. spot the difference.
Viết một chương trình tìm điểm khác nhau trong những bức ảnh trong link sau https://www.rd.com/funny-stuff/spot-the-difference/ bằng cách thực hiện những yêu cầu sau:

- Viết một chương trình chia đôi một bức ảnh cho trước (do cặp ảnh cần so sánh được ghép liền nhau trong một bức ảnh).
- Tìm hiểu cách lưu trữ một bức ảnh bằng một numpy array
- Đưa ra định nghĩa của một điểm khác nhau giữa hai bức ảnh.
- Giải quyết vấn đề trong hai trường hợp:
	+ Số điểm khác nhau được cho trước.
	+ Số điểm khác nhau không được cho trước.

Có thể gửi kèm ảnh (là dữ liệu đầu vào của chương trình) nếu cần thiết.

Bài tập 7. green screen effect
Nền xanh lá cây (green screen) thường được sử dụng trong quá trình ghi hình nhằm phục vụ việc thay đổi nền trong quá trình hậu xử lý. Hãy viết một chương trình thực hiện việc thay đổi nền với

Dữ liệu đầu vào: gồm một ảnh đối tượng trên nền xanh lá cây và một ảnh nền.
Dữ liệu đầu ra: ảnh đối tượng trên nền thật.
Có thể gửi kèm ảnh (là dữ liệu đầu vào của chương trình) nếu cần thiết.

Bài tập 8. Langton's ant
Viết một chương trình mô phỏng \textbf{Langton's ant}. Trình bày câu trả lời trong một file \textit{Jupyter notebook} với tên được đặt theo mẫu
Một số vấn đề có liên quan:
- Lựa chọn kiểu dữ liệu phù hợp để lưu trữ thông tin về quá trình di chuyển. Chú ý rằng về lý thuyết mặt phẳng di chuyển của con kiến là vô hạn.
- Xác định trạng thái của các ô trong lưới ô vuông tại một thời điểm bất kỳ, tìm cách cải thiện tốc độ của thuật toán.

Gợi ý: Tại một thời điểm bất kỳ, những ô con kiến đã đi qua là hữu hạn. Có thể sử dụng bảng hữu hạn hoặc một dictionary với key là tọa độ của một ô vuông.

Bài tập 9. Conway's game of life
Viết một chương trình mô phỏng Conway's game of life
