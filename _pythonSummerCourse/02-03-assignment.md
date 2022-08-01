---
title: "Bài tập tuần 2"
permalink: /pythonSummerCourse/week-02-assignment/
last_modified_at: 2022-08-01
redirect_from:
  - /theme-setup/
toc: false
---


Bài tập tuần 2 gồm 14 bài tập, bao gồm
- 7 bài tập cơ bản: 1, 2, 3, 4, 5, 6, 7 (làm tối thiểu 4 bài).
- 7 bài tập nâng cao: 8, 9, 10, 11, 12, 13, 14.

Cập nhật
- 25/07/2022. Bổ sung bài tập 11, bài tập 12.
- 27/07/2022. Bổ sung yêu cầu về số bài tập cần thực hiện tối thiểu.
- 31/07/2022. Đổi thứ tự bài tập 11 và bài tập 12, bổ sung bài tập 13 và bài tập 14.
- 31/07/2022. Làm rõ nội dung của bài tập 3 và bài tập 6.


## Danh sách bài tập

**Bài tập 1.** Hãy trả lời những câu hỏi, thực hiện những yêu cầu sau đây

(a) Những kí tự nào không được phép xuất hiện trong tên biến trong Python? \
(b) Cho ví dụ về tên biến hợp lệ và ví dụ về tên biến không hợp lệ. \
(c) Khi nói đến việc đặt tên biến, tác giả Robert C. Martin viết trong cuốn sách _Clean Code: A Handbook of Agile Software Craftsmanship_ viết

> It is easy to say that names should reveal intent. What we want to impress upon you is that we are serious about this. Choosing good names takes time but saves more than it takes. So take care with your names and change them when you find better ones. Everyone who reads your code (including you) will be happier if you do. \
> The name of a variable should answer all the big questions. It should tell you why it exists, what it does, and how it is used. If a name requires a com- ment, then the name does not reveal its intent.

Hãy cho ví dụ về cách đặt tên biến tốt kèm theo tình huống sử dụng những biến này.

(d) Cho danh sách những tên biến có cùng ý nghĩa thể hiện số sinh viên
- numberofcollegestudents
- NUMBEROFCOLLEGESTUDENTS
- numberOfCollegeStudents
- NumberOfCollegeStudents
- number_of_college_students

Hãy mô tả các phong cách đặt những tên biến trên. \
(e) Phân biệt các phong cách đặt tên biến Camel Case, Pascal Case và Snake Case. Cho ví dụ. \
(f) Bạn chọn phong cách đặt tên biến nào?

**Bài tập 2.** Viết một hàm tính bình phương của một số nguyên. \
**Ghi chú:** Đối với tất cả bài tập yêu cầu cài đặt chương trình (implementation), nội dung được trình bày trong một file `.py` cần có đủ những ví dụ minh họa. Khi đó, chỉ cần thực thi chương trình để kiểm chứng nội dung của chương trình. \
Dưới đây là một lời giải tham khảo cho bài tập này.
```py
def foo(x):
    return x**2

if __name__ == '__main__':
    print(foo(-2)) # 4
    print(foo(5)) # 25
    print(foo(0)) # 0
```

**Bài tập 3.** Viết một hàm nhận vào tên học viên (kiểu string), id học viên (kiểu nguyên), số thứ tự tuần học (kiểu nguyên), số thứ tự bài tập (kiểu nguyên) và trả về tên file `.py` tương ứng. Ví dụ

```py
studentName = 'NguyenVanA'
studentIndex = 7
weekIndex = 2
assignmentIndex = 1

someMethod(studentName, studentIndex, weekIndex, assignmentIndex) # week02_assignment01_student07_NguyenVanA.py
```

**Bài tập 4.** Cho đoạn văn sau \
*Python was designed to be easy to understand and fun to use (its name came from Monty Python so a lot of its beginner tutorials reference it). Fun is a great motivator, and since you’ll be able to build prototypes and tools quickly with Python, many find coding in Python a satisfying experience. Thus, Python has gained popularity for being a beginner-friendly language, and it has replaced Java as the most popular introductory language at Top U.S. Universities.*

(a) Kiểm tra xem các từ khóa `Python`, `contains`, `experience`, `difficult` có tồn tại trong đoạn văn trên hay không? \
(b) Đếm số lần xuất hiện của từ khóa `Python` trong đoạn văn. \
(c) Một từ (tiếng Anh) là một chuỗi liên tục các chữ cái thuộc bảng chữ cái (tiếng Anh), viết thường hoặc viết hoa. Tính số từ trong đoạn văn trên. \
(d) Viết lại đoạn văn trên, trong đó viết hoa tất cả các chữ cái trong câu đầu tiên của đoạn văn.

**Bài tập 5.** Cho list `A` với các giá trị dưới đây
```py
A = [70, 43, 7, 46, 34, 77, 80, 35, 49, 3, 1, 5, 53, 3, 53]
```
Hãy thực hiện những yêu cầu sau

(a) Thay giá trị tại vị trí thứ 3 của list A bởi bình phương của chính giá trị đó. \
(b) Xóa phần tử thứ 3 của list A bằng ít nhất hai cách khác nhau (gợi ý: sử dụng hàm pop hoặc hàm delete). \
(c) Thêm vào phía cuối list A một phần tử có giá trị bằng với bình phương của phần tử cuối cùng của list A. \
(d) Tính số phần tử trong list. \
(e) Tính tổng các phần tử trong list. \
(f) Tính tổng của các phần tử có chỉ số (index) 1, 2, 3, 5 trong list. \
(g) Tạo ra một list mới có thứ tự các phần tử đảo ngược với một list đã cho (bằng ít nhất hai cách khác nhau). \
(h) Tách list ban đầu thành hai list, một chỉ chứa các số chẵn, một chỉ chứa các số lẻ. \
(i) Tạo một list B gồm các phần tử của list A được sắp xếp theo thứ tự giảm dần từ trái qua phải. \
(j) So sánh độ dài của hai list A và list B để thấy rằng sau khi sắp xếp, số phần tử của một list không thay đổi. \
(k) Ghép hai list A và list B lại với nhau thành list C.

**Bài tập 6.** Viết một hàm tìm tất cả các nghiệm thực (phân biệt) của phương trình

$$a x^2 + b x + c = 0.$$

Input: ba số $a, b, c$ **không đồng thời bằng 0** \
Output: một tuple chứa tất cả các nghiệm thực (phân biệt), xếp theo thứ tự tăng dần, của phương trình $a x^2 + b x + c = 0.$ \
Ví dụ
```py
foo(1, 1, -2) # (-2, 1)
foo(1, 2, 1) # (-1, )
foo(1, 0, 1) # ()
```
Chú ý.
- Có thể tạo nhiều hàm con để thực hiện các công việc khác nhau bổ trợ cho hàm chính.
- Hàm chính chỉ trả về tuple được yêu cầu, không in thêm bất cứ thông tin gì trong quá trình tính toán.

**Câu hỏi nâng cao.** Với yêu cầu trả về một tuple chứa tất cả các nghiệm thực, tại sao cần điều kiện ba số $a, b, c$ không đồng thời bằng 0? Nếu bỏ điều kiện này đi thì cần thiết kế hàm này như thế nào?


**Bài tập 7.**  *(Mật mã Caesar)* \
Trong mã hóa, mật mã *Caesar* thay thế mỗi kí tự trong bảng chữ cái bởi một kí tự khác cũng trong bảng chữ cái đó ở vị trí cách nó một đoạn cố định.

Hình dưới đây thể hiện mã Caesar **ROT-19**, khi vòng chữ cái trong được xoay 19 nấc theo chiều dương để tạo ra bảng mã hóa cho vòng chữ cái ngoài. Chẳng hạn, kí tự **T** là mã hóa của kí tự **A**, kí tự **U** là mã hóa của kí tự **B**, ... Khi đó, nếu thông điệp ban đầu là **PYTHON** thì thông điệp được mã hóa tương ứng là **IRMAHG**.

<div>
    <img src="/assets/images/courses/homework/caesar.png"
    style="width:70%;
    max-width:700px;
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding-top:20px;
    padding-bottom:20px;">
</div>

**ROT-13** là một trong những mã Caesar phổ biến nhất. Hãy viết chương trình mã hóa (chuyển từ thông điệp gốc sang thông điệp mã hóa) và chương trình giải mã (chuyển từ thông điệp mã hóa sang thông điệp gốc) cho **ROT-13**.

**Bài tập 8.** Viết chương trình in ra các hình sau

```txt
*                  ******               ******
**                 *****                *   *
***                ****                 *  *
****               ***                  * *
*****              **                   **
******             *                    *
(1) Half Pyramid   (2) Inverted         (3) Hollow Inverted
                   Half Pyramid         Half Pyramid

     *              * * * * * *               *
    * *              * * * * *               * *
   * * *              * * * *               *   *
  * * * *              * * *               *     *
 * * * * *              * *               *       *
* * * * * *              *               * * * * * *
(4) Full Pyramid   (5) Inverted         (6) Hollow Full
                   Full Pyramid         Pyramid
```

Dưới đây là một lời giải thực hiện _đúng_ yêu cầu đặt ra.
```py
print('*')
print('**')
print('***')
print('****')
print('*****')
print('******')
```

**Bài tập 9.** (Tic-tac-toe) \
Hai người chơi trò chơi Tic-tac-toe trên bàn cờ kích thước $3\times 3$. Hãy trình bày đầy đủ luật chơi và viết một chương trình đưa ra kết quả của một ván chơi dựa trên các nước đi được thực hiện. Học viên tự thiết kế input/output của chương trình.

**Bài tập 10.** (Equilateral polygon) \
Trên mặt phẳng $Oxy$, cho trước hai điểm phân biệt $A, B$. Viết một chương trình xác định vị trí (những) điểm $C$ (nếu có) sao cho tam giác $ABC$ là một tam giác đều. Tạo một bức ảnh với tam giác $ABC$ vừa tìm được.

**Bài tập 11.** (university scoring) \
Viết một hàm nhận vào ba điểm thành phần (điểm thường xuyên, điểm giữa kỳ, điểm cuối kỳ) của sinh viên và trả về điểm chữ tương ứng.

**Bài tập 12.** (variables) \
Ba biến sau đây có bằng nhau hay không?
```py
foo = ('a'),
bar = 'a',
ham = ('a', )
```

Hai biến sau đây có bằng nhau hay không?
```py
foo = 'Đà Nẵng'
bar = 'Đà Nẵng'
```

Bài học rút ra ở đây là gì?

**Bài tập 13.** (province name converter) \
Viết một hàm chuyển tên một tỉnh/thành phố của Việt Nam thành một tên viết liền không dấu. Ví dụ
```py
foo('Hà Nội') # HaNoi
```

**Bài tập 14.** (book numbering) \
Viết một hàm tính số chữ số đã sử dụng để đánh số trang của một cuốn sách với số trang cho trước. Ví dụ
```py
ham(10) # 11 # it takes 11 digits (1, 2, 3, ..., 8, 9, 1, 0) to number the first 10 pages
```
Viết một hàm thực hiện công việc ngược lại: tính số trang của một cuốn sách khi biết số chữ số đã được sử dụng để đánh số.


## Gợi ý, hướng dẫn gỉai

1. Nên học cách viết code theo quy ước trong PEP8.
```py
# not recommended
if(isinstance(x,int)==True):
    print('x is int')

# recommended
if isinstance(x, int):
    print('x is int')
```

2. Sử dụng index -1 để lấy phần tử cuối cùng của một list/tuple.

3. Một cấu trúc điều kiện rẽ nhánh nên kết thúc bằng `else`, mặc dù cú pháp Python cho phép điều ngược lại

4. Sử dụng hàm dựng sẵn (built-in) `ord` và `char` để làm việc với chữ cái.

5. Nên sử dụng `f-string` để in trong Python.
```py
value = 5
print(f'{value:03d}') # 005
```

6. Không nên sử dụng hàm `input()` trừ trường hợp thực sự cần thiết. Khi kiểm thử chương trình, sẽ tiện hơn nếu đặt sẵn giá trị của các biến cần thiết
```py
# cách sử dụng hàm input(), mỗi lần chạy chương trình phải nhập lại tất cả các biến
foo = input()
bar = input()
ham = int(input())
egg = int(input())
testMethod(foo, bar, ham, egg)

# đặt sẵn giá trị cần thiết, cách này tiện hơn mỗi khi chỉ thay một vài giá trị của biến
foo = 'MIM'
bar = 'Python'
ham = 300
egg = 42
testMethod(foo, bar, ham, egg)
```

7. Cần hiểu rõ cách các hàm built-in hoạt động, ví dụ
```py
'zzz'.count('z') == 3 # True
'zzz'.count('zz') == 1 # không đúng "theo trực giác"
```

8. Khi thiết kế chương trình, nên tìm hiểu các edge case (tạm dịch, trường hợp đặc biệt) có thể xảy ra. Ví dụ với hàm `upper()` hay `lower()`, liệu có thể sử dụng nó cho ký tự đặc biệt (`@, !, &, ...`), số (1, 2, 3, ...) hay chữ cái tiếng Việt (`đ, ê, â, ...`) hay không?

9. Cần import thư viện theo chuẩn mực được công nhận
```py
# not recommended
import math as whatever
import math as m
# recommended
import math
```
