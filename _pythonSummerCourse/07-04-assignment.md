---
title: "Bài tập lần 7"
permalink: /pythonSummerCourse/module-07-assignment/
last_modified_at: 2025-09-08
redirect_from:
  - /theme-setup/
toc: false
---


Bài tập lần 7 gồm 7 bài tập, bao gồm
- 5 bài tập cơ bản: 1, 2, 3, 4, 5 (làm tối thiểu 3 bài).
- 2 bài tập nâng cao: 6, 7, 8.


## Danh sách bài tập

**Bài tập 1.** *(list average)* \
Viết một hàm nhận vào một `list` và trả về giá trị trung bình của danh sách đó. Đặt thêm cấu trúc `try-except` để thông báo khi nhận được một `list` rỗng. Bắt thêm các lỗi khác nếu có.


**Bài tập 2.** *(class inheritance)* \
(a) Xây dựng class `Rectangle` và class `Square` (kế thừa từ `Rectangle`). Thiết kế các thuộc tính, phương thức có liên quan. \
(b) Bổ sung thêm class `Rhombus` và thực hiện kế thừa một cách phù hợp. \
(c) Thực hiện yêu cầu tương tự với class `Ellipse` và class `Circle`. Chú ý rằng việc tính chu vi hình ellipse là một bài toán thú vị.


**Bài tập 3.** *(geometrical classes)* \
Viết một chương trình giải quyết một bài tập hình học cơ bản với các yêu cầu sau:
- Các thư viện hình học (class Point, class Line, class Circle, ...) cần được đặt bên trong thư mục `additionalFolder/`. (Nên) sử dụng relative import giữa các file Python.
- Trong file chính, import các thư viện hình học (sử dụng absolute import), đồng thời trình bày rõ cấu trúc thư mục trong phần docstrings.


**Bài tập 4.** *(class Fraction)* \
Thiết kế class `Fraction` với hai thuộc tính cơ bản gồm tử số và mẫu số (có thể thay đổi thuộc tính nếu cần thiết). Ngoài ra, xây dựng thêm những phương thức phù hợp để mô phỏng cách sử dụng một phân số trong những công việc thực tế. Dưới đây là một ví dụ minh họa

```py
foo = Fraction(2,3)
bar = Fraction.initializeFromFloat(0.42)
print(bar) # Frac(21,50)
print(foo >= bar) # True
```

Câu hỏi nâng cao. Sau khi đã cài đặt `__add__`, liệu có thể sử dụng cách viết
```py
totalValue = sum([fractionA, fractionB, fractionC])
```
được hay không?


**Bài tập 5.** *(class Polynomial)* \
Thiết kế class `Polynomial` sao cho có thể thực hiện các phép toán cộng (+), trừ (-), nhân (∗) giữa hai instance của class này, ví dụ như trong đoạn code dưới đây

```py
polynomialA = Polynomial([1, 2, 3])
polynomialB = Polynomial.initializeFromString('x^4 + 3x^2 - 5x + 1')

polynomialC = polynomialA + polynomialB
polynomialD = polynomialA - polynomialB
polynomialE = -polynomialA
polynomialF = polynomialA * polynomialB
```


**Bài tập 6.** *(Langton's ant)* \
Viết một chương trình mô phỏng [Langton's ant](https://en.wikipedia.org/wiki/Langton%27s_ant). Cần lựa chọn kiểu dữ liệu phù hợp để lưu trữ thông tin về quá trình di chuyển.


**Bài tập 7.** *(Lumosity's Pinball Recall)* \
Viết một chương trình giải quyết game [Pinball Recall](https://www.lumosity.com/en/brain-games/pinball-recall/) của Lumosity với dữ liệu đầu vào, đầu ra phù hợp.


**Bài tập 8.** *(Continuously compounded interest rate - lãi suất liên tục)* \
Thông thường, tài khoản tiết kiệm được tính lãi theo kỳ hạn, ví dụ gửi tiết kiệm 100 triệu VNĐ trong một năm với lãi suất 5%/năm thì sau một năm sẽ thu về 105 triệu VNĐ. Trong vấn đề dưới đây, ta sử dụng lãi suất liên tục $r$ (đơn vị 1/năm): bắt đầu với số tiền gửi $B$, sau thời gian $T$ năm, số tiền thu được là $B e^{r T}$. Dựa trên quan sát $e^x \approx 1 + x$ khi $x \approx 0$, ta thấy rằng hai khái niệm lãi suất này tương đối giống nhau. Ngoài ra, nhằm đơn giản hóa mô hình, ta giả sử một năm có 365 ngày.

Một nhà đầu tư mua vàng trong vòng một năm trở lại đây, với các thông tin về số lượng mua và giá vàng tại thời điểm mua như trong bảng dưới đây.

|    Ngày    | Số lượng | Đơn giá (kVND/chỉ) |
| :--------: | :------: | :----------------: |
| 01-10-2024 |     3    |        8,900       |
| 01-11-2024 |     1    |        8,590       |
| 01-12-2024 |     4    |        8,250       |
| 01-01-2025 |     1    |        8,660       |
| 01-02-2025 |     5    |        8,880       |
| 01-03-2025 |     9    |        9,650       |
| 01-04-2025 |     2    |       11,690       |
| 01-05-2025 |     6    |       11,300       |
| 01-06-2025 |     5    |       11,440       |
| 01-07-2025 |     3    |       11,620       |
| 01-08-2025 |     5    |       12,260       |
| 01-09-2025 |     8    |       12,780       |

(a) Nếu bỏ qua yếu tố lãi suất, người đó đã dành bao nhiêu tiền để mua số vàng trên? \
(b) Giả sử rằng tại mỗi thời điểm (01-10, 01-11, $\ldots$, 01-09) thay vì mua vàng, người đó gửi số tiền tương ứng vào ngân hàng với lãi suất liên tục 5%/năm. Hỏi tới ngày 08-09-2025, số tiền trong tài khoản là bao nhiêu? \
(c) Vào ngày 08-09-2025, giá vàng là 13,000,000 VNĐ/chỉ. Số vàng hiện tại có giá trị bao nhiêu? Đặt tình huống như ý (b), hãy xác định lãi suất liên tục $r$ sao cho tới ngày 08-09-2025, số tiền trong tài khoản đúng bằng giá trị này.
