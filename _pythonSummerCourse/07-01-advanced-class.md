---
title: "Bài 16. Class nâng cao"
permalink: /pythonSummerCourse/week-07-advanced-class/
last_modified_at: 2022-08-28
redirect_from:
  - /theme-setup/
toc: false
---


## 1. Kế thừa trong Python
- Cú pháp trong Python.
- Ví dụ: class Square kế thừa từ class Rectangle.
- Cách sử dụng `super()`.
- [Kiến thức nâng cao] method resolution order, diamond inheritance.


## 2. property trong Python
- Ý nghĩa: kích hoạt một chuỗi hành động khi thuộc tính tương ứng được gọi trong chương trình.
- Ví dụ: thuộc tính `area` nên là một property của class Rectangle, được tính từ `length` và `width`.
- [Kiến thức nâng cao] Ngoài việc cách sử dụng kể trên, property còn có hai tính năng liên quan là `setter` và `deleter`.


## 3. Dunder methods - overloading operators
- dunder = d(ouble) + under(scores).
- dunder methods: methods with trailing double underscores.
- Ý nghĩa: giúp viết các phép toán một cách trực quan hơn.
- Danh sách các methods có trong tài liệu tham khảo.
- Ví dụ về `__add__` và `__repr__`

  ```py
  class Wallet:
      def __init__(self, amount):
          self.amount = amount
          return None

      def __add__(self, another):
          return Wallet(self.amount + another.amount)

      def __repr__(self):
          return f'Wallet with ${self.amount}'

  foo = Wallet(12)
  bar = Wallet(7)
  ham = foo + bar
  print(ham) # 'Wallet with $19'
  ```



## 4. (kiến thức nâng cao) - abstract base class
Học viên tự tìm hiểu kiến thức trên Internet.

> Nội dung trên chỉ là tóm tắt, học viên cần đọc các tài liệu liệt kê trong phần tài liệu tham khảo dưới đây.

## Tài liệu tham khảo

Tài liệu chính
- https://realpython.com/inheritance-composition-python/
- https://realpython.com/lessons/object-inheritance-python/
- https://realpython.com/lessons/inheritance-python/
- [Bài viết về operator function overloading](https://realpython.com/operator-function-overloading/) trên trang web Real Python

Tài liệu bổ sung
- [Abstract base class](https://docs.python.org/3/library/abc.html) trong Python
- [Multiple inheritance](https://en.wikipedia.org/wiki/Multiple_inheritance)
- [Method resolution order](https://stackoverflow.com/questions/2010692/what-does-mro-do) in stackoverflow
- [Setter and deleter](https://www.programiz.com/python-programming/methods/built-in/property) in programiz
- ThinkPython (trang 195-222)






# --------------------------------------------------------------------------- #
# --------------------------------------------------------------------------- #
# --------------------------------------------------------------------------- #
# --------------------------------------------------------------------------- #


## Phần 1. Kế thừa.
class Rectangle: dài và rộng, rồi tính cả diện tích luôn, làm thêm cái repr. --> nói luôn là cái này không nên "thay đổi dài/rộng", vì nó sẽ sai với diện tích.

class Square: khởi
sẽ dùng super().__init__(side, side) để có dài và rộng
rồi cũng gán self.side = side.
KHÔNG CÓ RERP
thì khi in ra sẽ dùng repr của class trên.


class Rhombus: side, and angle, in ra là đang dùng thoi
vuông(thoi, hcn) --> khi đó hàm super sẽ gọi của thoi. Có lẽ cách thực hiện đúng sẽ là super(Square, self).__init__(length, length)
dẫn câu chuyện đến method resolution order, diamond inheritance.

https://realpython.com/python-super
class Cube(Square): --> không tốt
# --------------------------------------------------------------------------- #




## Phần 2. Property
--> để trigger hành động.
.area

Nhận xét: nhược điểm là phải tính lại mỗi lần gọi nó.
Cách 1. quy ước rằng không đc phép thay đổi, và code cứng area
Cách 2. "cho phép" thay đổi cạnh, property area tính từ cạnh
cách 3. code cái cạnh cũng là property, rồi khi thay nó thì cập nhật là cạnh và area, rồi property area chỉ gọi _area.
cách 4. tốt hơn nữa là khi đổi cạnh, nếu giá trị không đổi thì không tính lại area.

note: "không được thay đổi" chỉ mang tính quy ước. Guido nói rằng Python is for adults ???

https://mail.python.org/pipermail/tutor/2003-October/025932.html
> After all, we're all consenting adults here.




## Phần 3. - Dunder methods (a.k.a methods with trailing double underscores), e.g., (`__repr__`, `__add__`, `__lt__`, ...)
Lấy ví dụ về class Fraction, lưu numerator and denominator.

Ví dụ về việc cộng.
- Bình thường viết một hàm riêng.
- cách tốt hơn là viết .addAnotherFraction() trong class
- cách tuyệt nhất là __add__.


chú ý: nên code đủ tất cả __lt__, __eq__, __gt__, __le__, ...
repr
__add__
__sub__
__mul__
__exp__ thì phải.
Cho link tới danh sách đầy đủ.
https://www.reddit.com/r/Python/comments/br9ok2/list_of_all_python_dunder_methods/


dùng hàm sum() để nó có lỗi liên quan đến cái start = 0 không cộng được.
--> cho thành bài tập, gợi ý là phải khởi tạo một fraction(0, 1).




## Phần 4. (kiến thức nâng cao) - abstract base class
ý tưởng: tạo sẵn một khung, class kế thừa từ nó PHẢI CÓ các hàm/thuộc tính(?) nào đó nếu không sẽ lỗi.

# --------------------------------------------------------------------------- #
# --------------------------------------------------------------------------- #
# --------------------------------------------------------------------------- #
# --------------------------------------------------------------------------- #
# --------------------------------------------------------------------------- #


# Journey to the Rectangle class

Trong một buổi seminar của nhóm Python Programming, bạn A được giao nhiệm vụ xây dựng một class biểu diễn lớp các hình chữ nhật (không xét đến vị trí của chúng trong mặt phẳng). A đề xuất hai cách tổ chức class Rectangle được trình bày ở (5) và (7). Ta sẽ đánh giá hai cách tiếp cận này.

**Cách tiếp cận thứ nhất**
```
class Rectangle:
    def __init__(self, height, width):
        self.height = height
        self.width = width

    def calculate_area(self):
        return self.height * self.width
```

Khi nhắc đến một class biểu diễn lớp các hình chữ nhật, người dùng thường nghĩ rằng `length, width, area` là các thuộc tính (attribute) của một instance và sử dụng class `Rectangle` như trong đoạn code (6). Nói cách khác, việc sử dụng hàm `calculate_area` để có được thông tin về diện tích là *phản trực giác*.

```
rect = Rectangle(10, 5)
print(f'Height of the rectangle: {rect.height}') # 10
print(f'Width of the rectangle : {rect.width}') # 5
print(f'Area of the rectangle  : {rect.calculate_area()}') # counter-intuitive
print(f'Area of the rectangle  : {rect.area}') # attribute error
```
Listing 6: Cách người dùng sử dụng class Rectangle

Hãy thiết kế class Rectangle thỏa mãn hai yêu cầu:

(a) Diện tích hình chữ nhật được tính ngay tại thời điểm nó được nhắc đến (hàm `calculate_area` thỏa mãn yêu cầu này).

(b) Người dùng truy cập thông tin về diện tích thông qua thuộc tính area (hàm `calculate_area` không thỏa mãn yêu cầu này).

*Gợi ý:* Sử dụng @property

**Cách tiếp cận thứ hai**
```
class Rectangle:
    def __init__(self, height, width):
        self.height = height
        self.width = width
        self.area = height * width
```
Listing 7: Cách tiếp cận thứ hai

Cách tiếp cận ở (7) đã giải quyết được vấn đề về tính trực giác của chương trình khi tính (và lưu lại) diện tích hình chữ nhật ngay khi khởi tạo instance.

Tuy nhiên với cách thiết kế class Rectangle như vậy, sai sót sẽ xảy ra khi người dùng vô tình thay đổi các attribute cơ sở (trong trường hợp này là height, width). Đoạn code (8) thể hiện một ví dụ về lỗi này.

```
rect = Rectangle(10, 5)
rect.height = 20
print(f'Height of the rectangle: {rect.height}') # 10
print(f'Width of the rectangle : {rect.width}') # 5
print(f'Area of the rectangle  : {rect.area}') # 50 , it is supposed to be 100
```
Listing 8: Cách người dùng sử dụng class Rectangle

Hãy thiết kế class Rectangle thỏa mãn hai yêu cầu:

(a) Người dùng truy cập thông tin về diện tích thông qua thuộc tính area (cách tiếp cận trong (7) thỏa mãn yêu cầu này).

(b) Không cho phép (theo một nghĩa nào đó) người dùng thay đổi thuộc tính height, width sau khi đã khởi tạo instance của class Rectangle.

*Gợi ý:* Sử dụng @property

**Kết luận**
Hãy tổng kết lại những ưu điểm, nhược điểm của hai cách xây dựng class Rectangle đã nêu ở trên. Tìm nhược điểm chung (nếu có) của cả hai cách xây dựng này và đưa ra cách cải thiện phù hợp.
