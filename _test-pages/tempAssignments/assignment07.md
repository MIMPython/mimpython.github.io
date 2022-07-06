# Assignment 07 - Functions
**1.** (equation solver)

Cho một phương trình có dạng
$$ a x^2 + b x + c = 0$$
với $x$ là ẩn và $a,b,c$ là các tham số. 
Viết một chương trình tìm tất cả các nghiệm của phương trình trên. Lưu chương trình trong một file Python với tên được đặt theo mẫu

```
    Assignment07_FullName_EquationSolver.py
```
**2.** (Fibonacci numbers) 

Dãy số Fibonacci $\left( F_n \right)_{n=0}^{\infty}$ được định nghĩa bằng công thức truy hồi:

$$ F_0 = 0, F_1 = 1 $$
$$ F_{n+2} = F_{n+1} + F_{n} \quad \forall n \ge 0 $$
	Viết một chương trình tính số Fibonacci $F_n$ với một số tự nhiên $n$ cho trước. Lưu chương trình trong một file Python với tên được đặt theo mẫu
```
Assignment07_FullName_FibonacciNumbers.py
```
*Gợi ý:* Có thể sử dụng các thư viện như numpy, sympy.


**3.** (probability of coprime integers)

Cho $N$ là một số nguyên dương đủ lớn ($N \approx 10^6$) . Lấy ngẫu nhiên hai số nguyên dương từ tập hợp
các số nguyên dương không vượt quá $N$. Xác suất $P$ để hai số này nguyên tố cùng nhau là bao nhiêu?
Xác suất P có mối liên quan gì tới số $\pi$

Hãy trả lời những câu hỏi trên bằng cách thực hiện các yêu cầu sau:

(a) Viết một chương trình tính ước chung lớn nhất của hai số tự nhiên sử dụng [thuật toán Euclid](https://en.wikipedia.org/wiki/Euclidean_algorithm)

(b) Tính giá trị của $P$ bằng một trong hai cách:
- Lấy ngẫu nhiên hai số tự nhiên rồi kiểm tra tính nguyên tố cùng nhau của hai số đó.
- Tính lượng cặp số nguyên tố cùng nhau trong tất cả cặp số có thể chọn được từ tập đã cho.

(c) Tìm mối liên hệ giữa giá trị của P và $\pi$.

Trình bày câu trả lời trong một file Jupyter notebook với tên được đặt theo mẫu
```
Assignment07_FullName_CoprimeNumbers.ipynb
```
*Gợi ý:* $P \approx \frac{a}{\pi ^b}$ với a, b là hai số dương.


**4.** (equilateral triangles)

(a) Trên mặt phẳng $Oxy$, cho trước hai điểm $A, B$. Viết một chương trình tìm vị trí điểm $C$ (nếu có)
sao cho tam giác $ABC$ là một tam giác đều.

(b) Viết một chương trình kiểm tra ba điểm cho trước trên mặt phẳng có tạo thành một tam giác
đều hay không.

(c) (bonus) Viết một chương trình vẽ ba điểm cho trước vào một hệ tọa độ và lưu bức ảnh đã vẽ với
định dạng eps.

Trình bày câu trả lời trong một file Jupyter notebook với tên được đặt theo mẫu
```
Assignment07_FullName_EquilateralTriangles.ipynb
```


# Additional Problems
**5.** (squares)

Giải quyết bài toán tương tự với bài tập (4) trong trường hợp hình vuông. Trình bày câu trả lời trong
một file Jupyter notebook với tên được đặt theo mẫu
```
Assignment07_FullName_Squares.ipynb
```


**6.** (simple calculator)

Viết một chương trình để thực hiện các biểu thức toán học mà người dùng nhập vào. Tính hiệu quả
của chương trình được đánh giá dựa trên khả năng thực hiện các dạng biểu thức toán học với độ
phức tạp tăng dần được liệt kê dưới đây:

(a) Cộng trừ hai số, ví dụ: `5+4, 15−6, 4−0,...` 

(b) Cộng trừ nhiều hơn hai số, ví dụ: `4−3+5, 4−1−3−4,...`

(c) Kết hợp phép nhân, chia, ví dụ: `5∗3−4`

(d) Kết hợp dấu ngoặc, ví dụ: `(4+3)∗5−4`

(e) Lũy thừa.

(f) Biểu thức toán học bất kỳ.

Lưu chương trình trong một file Python với tên được đặt theo mẫu
```
Assignment07_FullName_SimpleCalculator.py
```


**7.** (large sum)

Viết một chương trình giải quyết bài toán trong [Project Euler problem 13](https://projecteuler.net/problem=13). Lưu chương trình trong
một file Python với tên được đặt theo mẫu
```
Assignment07_FullName_LargeSum.py
```


**8.** (directory visualization)

Viết một chương trình in ra cây thư mục của máy tính. Có thể tham khảo cấu trúc cây thư mục trên
[trang web Real Python](https://realpython.com/python-pathlib/). Ngoài ra có thể tham khảo cấu trúc cây thư mục được trình bày bởi tree trên
hệ điều hành Ubuntu.
```
sudo apt install tree
tree -at /home/username/
```
Lưu chương trình trong một file Python với tên được đặt theo mẫu
```
Assignment07_FullName_DirectoryVisualization.py
```


# Related topics
- Lambda functions.
- pass keyword in Python.
- Positional arguments, keyword arguments.
- Function annotations in [PEP 3107](https://www.python.org/dev/peps/pep-3107/).
- Asterisk (∗) operator and double asterisk (∗∗) operator in method arguments.
- It’s Easier to Ask for Forgiveness than Permission [(EAFP principle)](https://blogs.msdn.microsoft.com/pythonengineering/2016/06/29/idiomatic-python-eafp-versus-lbyl/).
- Single Responsibility Principle (SRP) for functions and classes.