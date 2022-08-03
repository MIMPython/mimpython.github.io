---
title: "Bài tập tuần 3"
permalink: /pythonSummerCourse/week-03-assignment/
last_modified_at: 2022-08-04
redirect_from:
  - /theme-setup/
toc: false
---


Bài tập tuần 3 gồm 13 bài tập, bao gồm
- 7 bài tập cơ bản: 1, 2, 3, 4, 5, 6, 11 (làm tối thiểu 5 bài).
- 6 bài tập nâng cao: 7, 8, 9, 10, 12, 13.

Cập nhật
- 25/07/2022. Bổ sung bài tập 11, bài tập 12.
- 27/07/2022. Bổ sung yêu cầu về số bài tập cần thực hiện tối thiểu.
- 31/07/2022. Bổ sung bài tập 13.
- 01/08/2022. Bổ sung yêu cầu loại bỏ thư mục `.git` khi thực hiện bài tập 11.
- 04/08/2022. Bổ sung Gợi ý, hướng dẫn giải. Thêm ý hỏi cho bài tập 5.


## Danh sách bài tập

**Bài tập 1.** (infinite loop)

Đoạn chương trình dưới đây là một vòng lặp vô hạn, do điều kiện trong phần `while` luôn đúng.
```py
foo = 1
while foo >= 1:
    foo += 1
```
Viết một chương trình chứa một vòng lặp vô hạn với ít ký tự nhất có thể.

**Bài tập 2.** (large sum) \
Giải quyết [bài toán 13](https://projecteuler.net/problem=13) trên trang web Project Euler.

**Bài tập 3.** (names scores) \
Giải quyết [bài toán 22](https://projecteuler.net/problem=22) trên trang web Project Euler.

**Bài tập 4.** (Fibonacci numbers) \
Dãy số Fibonacci $\left\\{ F_n \right\\}_{n=0}^{\infty}$ được định nghĩa bằng công thức truy hồi:

$$F_0 = 0, F_1 = 1$$

$$F_{n+2} = F_{n+1} + F_{n} \quad \forall n \ge 0$$

Viết một chương trình tính số Fibonacci $F_n$ với một số tự nhiên $n$ cho trước. Hãy giải quyết bài tập này bằng nhiều cách khác nhau, trong đó có cách sử dụng thư viện `numpy, sympy`.

**Bài tập 5.** (rock-paper-scissors game) \
(a) Viết một chương trình sao cho khi chạy chương trình này, nó sẽ chỉ dừng lại khi người dùng nhập vào đúng một chữ số trong khoảng từ 0 đến 9. \
(b) Viết một chương trình để hai người có thể chơi trò chơi kéo - búa - bao với nhau. \
(c) Cách tiếp cận đơn giản là cho phép hai người chơi A, B lần lượt đưa ra lựa chọn và nhập nó vào chương trình thông qua bàn phím (giả sử A nhập trước). Cách chơi như vậy không công bằng vì ở mỗi lượt chơi B luôn biết được lựa chọn của A trước khi B đưa ra lựa chọn. Thiết kế chương trình để đảm bảo tính công bằng cho trò chơi. \
(d) Có thể hiểu tính công bằng theo nghĩa nào khác?

**Bài tập 6.** (probability of coprime integers) \
Cho $N$ là một số nguyên dương đủ lớn ($N \approx 10^6$). Lấy ngẫu nhiên hai số nguyên dương từ tập hợp các số nguyên dương không vượt quá $N$. Xác suất để hai số này nguyên tố cùng nhau là bao nhiêu? Giá trị này có mối liên quan gì tới số $\pi$? \
Hãy trả lời những câu hỏi trên bằng cách thực hiện các yêu cầu sau: \
(a) Viết một hàm tính ước chung lớn nhất của hai số tự nhiên sử dụng [thuật toán Euclid](https://en.wikipedia.org/wiki/Euclidean_algorithm). \
(b) Đặt giá trị xác suất cần tìm là $P$. Tính giá trị của $P$ bằng một trong hai cách:
- Lấy ngẫu nhiên hai số trong tập hợp đã cho rồi kiểm tra tính nguyên tố cùng nhau của chúng.
- Đếm số cặp số nguyên tố cùng nhau trong tất cả cặp số có thể chọn được từ tập số đã cho.

(c) Tìm mối liên hệ giữa giá trị của $P$ và $\pi$. *Gợi ý:* $P \approx\frac{a}{\pi^b}$ với $a, b$ là hai số dương.

**Bài tập 7.** (largest prime factor) \
Giải quyết [bài toán 3](https://projecteuler.net/problem=3) trên trang web Project Euler.

**Bài tập 8.** (banking simulation) \
Trong bài tập này, ta sẽ xây dựng một chương trình mô phỏng hoạt động của một ngân hàng.

Đầu tiên, viết một chương trình cho phép người dùng tạo một tài khoản với tên đăng nhập (username) và mật khẩu (password) và yêu cầu người dùng xác nhận lại mật khẩu đã nhập. Chương trình cần đáp ứng những yêu cầu sau:
- Sử dụng những tiêu chí phổ biến của một mật khẩu tốt đó để kiểm tra mật khẩu người dùng cung cấp.
- Cung cấp cho người dùng những hướng dẫn phù hợp trong quá trình người dùng tương tác với chương trình.
- Ẩn đi mật khẩu trong quá trình người dùng nhập mật khẩu.

Ngoài việc tạo tài khoản với tên đăng nhập và mật khẩu, mô phỏng này có thể có thêm những tính năng sau
- Trong quá trình tạo tài khoản, cho phép người dùng cung cấp thêm thông tin cá nhân.
- Lưu trữ thông tin của tất cả người dùng (ngay cả khi chương trình đã dừng).
- Cho phép người dùng sửa đổi thông tin của bản thân.
- Cho phép gửi/rút tiền, chuyển tiền giữa các tài khoản.
- Ghi nhận số tiền người dùng có trong tài khoản.
- Bảo đảm bí mật những thông tin của người dùng.

**Bài tập 9.** Giải thích meme dưới đây
<div>
    <img src="/assets/images/courses/homework/do-while-meme.jpg"
    style="width:70%;
    max-width:700px;
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding-top:20px;
    padding-bottom:20px;">
</div>

**Bài tập 10.** (do-while conversion)

Trong [một bài viết](https://www.programiz.com/cpp-programming/do-while-loop) trên trang web Programiz, ta biết rằng cấu trúc vòng lặp `do-while` trong ngôn ngữ lập trình C++ có dạng

```cpp
do {
  // body of loop;
}
while (condition);
```

<div>
    <img src="/assets/images/courses/homework/cpp-do-while-loop-flowchart.webp"
    style="width:50%;
    max-width:700px;
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding-top:20px;
    padding-bottom:20px;">
</div>

Chương trình thực thi khối lệnh trong phần `do`, sau đó kiểm tra điều kiện ở phần `while`. Nếu điều kiện xảy ra thì chương trình quay trở lại điểm xuất phát vòng lặp, nếu điều kiện không xảy ra thì chương trình thoát khỏi vòng lặp.

(a) So sánh vòng lặp `do-while` trong C++ với vòng lặp `while` trong Python. \
(b) Có thể biến đổi tương đương đoạn code sử dụng `do-while` trong C++ sang đoạn code sử dụng `while` trong Python hay không?

**Bài tập 11.** (git) \
Thực hiện những yêu cầu dưới đây \
a) Tạo một repository (sử dụng lệnh `git init`). \
b) Thực hiện ít nhất 3 commit trong repository này. \
c) Đăng repository này lên trang Github cá nhân, đặt chế độ công khai. \
d) Đặt link của repository trong phần trình bày của bài tập này. Ví dụ
  ```py
  """
  https://github.com/MIMPython/mimpython.github.io
  """
  ```

Chú ý. Một thư mục có tên `.git` sẽ được tạo ra khi thực hiện câu lệnh `git init`. Học viên **không** đặt thư mục này vào phần bài nộp.

**Bài tập 12.** \
Cho trước một số nguyên dương $n$, viết chuỗi số nguyên từ 1 đến $n$ theo chiều dương. Ví dụ với $n=14$
```
 7  6  5
 8  1  4
 9  2  3 14
10 11 12 13
```

**Bài tập 13.** \
Khi viết hai số nguyên $2^n$ và $5^n$ liền nhau ta được một số có bao nhiêu chữ số? Ví dụ với $n=3$, ta được một số có 4 chữ số (số đó là 8125).


## Gợi ý, hướng dẫn giải

1. Cách viết `sum = sum(values)` không tốt vì đã ghi đè hàm dựng sẵn (built-in) `sum()` bởi một giá trị số.
2. Trong Python, một mảng bất kỳ đều được đánh số mặc định từ 0. Nó có thể giống hoặc khác với (những) quy ước đánh chỉ số ở bên ngoài Python.
3. Sử dụng hàm `ord()` và `chr()` để chuyển đổi trong bảng mã `ASCII`.
4. Người dùng có thể nhấn tổ hợp phím `Ctrl+K` rồi `Z` để bật/tắt chế độ Zen mode trong Visual Studio Code.
5. Sử dụng thư viện `getpass` trong Python để ẩn đi input người dùng nhập vào.
6. Bài tập về dãy Fibonacci có thể thực hiện bởi ít nhất 3 cách khác nhau. Cần tránh lặp lại việc tính những giá trị giống nhau trong dãy Fibonacci.
7. Sử dụng `np.random.randint` để sinh ngẫu nhiên các số nguyên trong một khoảng nhất định.
