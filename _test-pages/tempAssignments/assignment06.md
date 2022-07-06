#  User input and while loops

**1.** *(execute a Python script)*

Trong những bài tập trước chúng ta đã thực hành việc viết chương trình trong Jupyter notebook và thực thi đoạn chương trình đó bằng cách sử dụng tổ hợp phím **Ctrl+Enter.** 

Ngoài cách này, chương trình có thể được thực thi bằng cách thực thi lệnh

```cmd
python file.py
```
trên terminal trong hệ điều hành Linux/macOS (hoặc trên command prompt trong hệ điều hành Windows).

-  Viết một chương trình bằng ngôn ngữ lập trình Python, lưu chương trình trong một file Python (với định dạng .py) rồi thực thi chương trình qua terminal (hoặc command prompt)

- 
	```py
	for i in range(1, int(1e10) + 1):
		print(i)
	```

	<p style="text-align: center">Listing 1: Chương trình in các số từ 1 đến 10 tỷ</p>

	Đoạn chương trình trên cần nhiều hơn một phút để thực thi. Làm thế nào để dừng một chương trình đang chạy trên terminal/command prompt?

**Trình bày câu trả lời trong một file Jupyter notebook với tên được đặt theo mẫu**
<p style="text-align: center">Assignment06_FullName_ExecuteScript.ipynb</p>

**2.** *(infinite loop)*

Đoạn chương trình dưới chứa một vòng lặp vô hạn, do điều kiện trong while luôn đúng.

```py
foo = 1
while foo == 1:
	foo += 1
```
<p style="text-align: center">Listing 1: Chương trình in các số từ 1 đến 10 tỷ</p>

**3.** *(rock-paper-scissors game)*

$\qquad$ (a) Viết một chương trình để hai người có thể chơi trò chơi kéo - búa - bao (oẳn tù tì). Lưu chương trình trong một file Python với tên được đặt theo mẫu
<p style="text-align: center">Assignment06_FullName_RockPaperScissors.py</p>

$\qquad$ (b) Cách tiếp cận đơn giản là cho phép hai người chơi A, B lần lượt đưa ra lựa chọn và nhập nó vào chương trình thông qua bàn phím (giả sử A nhập trước). Cách chơi như vậy không công bằng vì ở mỗi lượt chơi B luôn biết được lựa chọn của A trước khi B đưa ra lựa chọn của mình. Có thể hiểu tính công bằng theo nghĩa nào khác? Làm thế nào để đảm bảo tính công bằng cho trò chơi?

*Fun fact: “Oẳn tù tì” có phát âm gần giống với “one two three”.*

**4.** *(sign up an account)*

Viết một chương trình cho phép người dùng tạo một tài khoản với tên đăng nhập (username) và mật khẩu (password) và yêu cầu người dùng xác nhận lại mật khẩu đã nhập. Lưu chương trình trong một file Python với tên được đặt theo mẫu
<p style="text-align: center">Assignment06_FullName_SignUpAccount.py</p>

# Additional Problems

**5.** *(largest prime factor)*

Giải quyết bài toán trong Project Euler problem 3. Trình bày câu trả lời trong một file Jupyter notebook với tên được đặt theo mẫu Assignment06_FullName_LargestPrimeFactor.ipynb

**6.** *(do-while conversion)*

Vòng lặp do-while trong ngôn ngữ lập trình C++ có dạn

```c
	do {
		2 // codes ;
		3
	 }
	while (testExpre ssion ) 
```
<p style="text-align: center">Listing 3: Cấu trúc của vòng lặp do-while trong C++</p>

<style>
	.row {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.column {
		max-width: 45%;
		padding: 5px;
		padding-top: 20px;
		padding-bottom: 20px;
		display: flex;
	}

	.text-column {
		flex: 60%;
		padding-top: 20px;
		padding-bottom: 20px;
		padding-left:5px
	}

	.fliped-text {
		-moz-transform: scale(1, 1);
		-webkit-transform: scale(1, 1);
		-o-transform: scale(1, 1);
		-ms-transform: scale(1, 1);
		transform: scale(1, 1);
	}

	@media(min-width: 580px) {
		.row {
			flex-direction: row;
		}
	}
	.img-container {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 8px;
	}
</style>

<div class="row">
  <div class="column img-container">
    <img src=".\image\assign06-img1.png" style="width:100%; max-height:300px">
	<span>Hình 1: <a href="https://www.programiz.com/cpp-programming/do-while-loop">Programiz.com</a>
	</span>
  </div>
  <div class="text-column">
    <p style="width:100%" markdown="1">
	Hình 1 là sơ đồ thực thi của loại vòng lặp này. Chương trình thực thi khối lệnh trong phần do, sau đó kiểm tra điều kiện ở phần while. Nếu điều kiện xảy ra thì chương trình quay trở lại điểm xuất phát vòng lặp, nếu điều kiện không xảy ra thì chương trình thoát khỏi vòng lặp.

- So sánh vòng lặp do-while trong C++ với vòng lặp while trong
Python.
- Viết lại đoạn chương trình (3) ở bài tập 6 bằng ngôn ngữ lập trình
Python.

Trình bày câu trả lời trong một file Jupyter notebook với tên được đặt theo mẫu
<p style="text-align: center"> Assignment06_FullName_DoWhileConversion.ipynb</p>
	</p>
  </div>
</div>

**7.** *(unstoppable program)*

Trong bài tập 1, ta đã tìm hiểu những cách để dừng một chương trình đang được thực thi trên terminal/command prompt.

Một cách khả thi là dừng chương trình hiện tại bằng tổ hợp phím Ctrl + C. Một cách khác là đóng cửa sổ terminal/command prompt. Tuy nhiên việc đóng cửa sổ không được khuyến khích vì làm mất những thông tin hiện có của cửa sổ đó.

Hãy viết một chương trình sao cho một khi chương trình đó bắt đầu được thực thi, cách duy nhất để dừng nó là đóng cửa sổ hiện tại. Lưu chương trình trong một file Python với tên được đặt theo mẫu
<p style="text-align: center"> Assignment06_FullName_UnstoppableProgram.py</p>

<div style="transform: rotate(180deg)">Gợi ý: Sử dụng vòng lặp vô hạn và cấu trúc try/except.</div>

**8.** *(banking simulation)*

Nối tiếp bài tập 4, trong bài tập này ta sẽ xây dựng một chương trình mô phỏng hoạt động của một ngân hàng. Đầu tiên, cải tiến việc tạo tài khoản bằng cách thực hiện các yêu cầu sau:

1. Cung cấp cho người dùng những hướng dẫn phù hợp trong quá trình người dùng tương tácvới chương trình.
2. Nêu những tiêu chí thường được sử dụng để xác định một mật khẩu là hợp lệ. Sử dụng những tiêu chí đó để kiểm tra tính hợp lệ của mật khẩu.
3. Nhằm đảm bảo tính an toàn của tài khoản, yêu cầu người dùng nhập lại mật khẩu nếu nó không hợp lệ.
4. Ẩn đi mật khẩu trong quá trình người dùng nhập mật khẩu.

Ngoài việc tạo tài khoản với tên đăng nhập và mật khẩu, mô phỏng này cần:
1. Trong quá trình tạo tài khoản, cho phép người dùng cung cấp thêm các thông tin bổ sung. 
2. Lưu trữ thông tin của tất cả người dùng (ngay cả khi chương trình đã dừng).
3. Cho phép người dùng sửa đổi thông tin của chính họ.
4. Ghi nhận số tiền người dùng có trong tài khoản.
5. Cho phép chuyển tiền giữa các tài khoản.
6. Gửi/rút tiền tiết kiệm.
7. Tạo mật khẩu mới cho một tài khoản khi được yêu cầu.
8. Bảo đảm bí mật những thông tin của người dùng.
9. .  . .

Trình bày câu trả lời một cách thích hợp và đặt tên theo mẫu
<p style="text-align: center"> Assignment06_FullName_BankingSimulation</p>

**Chú ý:** trong thực tế việc mở tài khoản tại ngân hàng yêu cầu người dùng cung cấp các thông tin định danh khác (ví dụ như CMND). Tuy nhiên những yếu tố đó không được tính đến ở đây

**9.** *(4-to-9 points password)*
Hãy viết một chương trình mô phỏng việc tạo mật khẩu đường gấp khúc trên điện thoại thông minh

<div>
	<img src=".\image\assign06-img2.png"
	style="width:80%;
	max-width:500px;
	display: block;
	margin-left: auto;
	margin-right: auto;
	padding-top:20px">
</div>