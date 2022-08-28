---
title: "Bài tập tuần 7"
permalink: /pythonSummerCourse/week-07-assignment/
last_modified_at: 2022-08-29
redirect_from:
  - /theme-setup/
toc: false
---


Bài tập tuần 7 gồm 6 bài tập, bao gồm
- 5 bài tập cơ bản: 1, 2, 3, 4, 5 (làm tối thiểu 3 bài).
- 1 bài tập nâng cao: 6.


## Danh sách bài tập

**Bài tập 1.** *(list average)* \
Viết một hàm nhận vào một `list` và trả về giá trị trung bình của danh sách đó. Đặt thêm cấu trúc `try-except` để thông báo khi nhận được một `list` rỗng. Bắt thêm các lỗi khác nếu có.


**Bài tập 2.** *(class inheritance)* \
1) Xây dựng class `Rectangle` và class `Square` (kế thừa từ `Rectangle`). Thiết kế các thuộc tính, phương thức có liên quan. \
1') Bổ sung thêm class `Rhombus` và thực hiện kế thừa một cách phù hợp. \
2) Thực hiện yêu cầu tương tự với class `Ellipse` và class `Circle`. Chú ý rằng việc tính chu vi hình ellipse là một bài toán thú vị.


**Bài tập 3.** *(geometrical classes)* \
Viết một chương trình giải quyết một bài tập hình học cơ bản. \
Yêu cầu đối với bài tập:
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
