---
title: "Bài 16. Class nâng cao"
permalink: /pythonSummerCourse/lesson-16-advanced-class/
last_modified_at: 2022-08-29
redirect_from:
  - /theme-setup/
toc: false
---

_Tác giả: Hoàng Anh Quân_

## 1. Kế thừa trong Python
Kế thừa là cách để đơn giản hóa cấu trúc chương trình, đồng thời tận dụng những phương thức, thuộc tính đã có sẵn.

```py
class Rectangle:
    nSides = 4

    @classmethod
    def hello(cls):
        print(f'This is a method defined in class Rectangle.')
        print(f'Hello from {cls.__name__}!')


class Square(Rectangle):
    pass


Rectangle.hello()
print(Rectangle.nSides)
Square.hello()
print(Square.nSides)
```

Trong ví dụ trên, class `Square` kế thừa từ class `Rectangle`. Việc kế thừa này muốn thể hiện rằng **một instance Square cũng là một instance Rectangle**, điều này đúng về mặt toán học.

Trong tài liệu tham khảo, có trường hợp class `Cube` (hình lập phương) kế thừa từ class `Square`. Điều này không đúng về mặt toán học, nhưng có thể được chấp nhận nếu người dùng có những lý do rất đặc biệt để làm vậy.

Kiến thức nâng cao
- Sử dụng `super()` để khởi tạo sử dụng hàm khởi tạo của class cha, xem thêm trong tài liệu tham khảo.
- method resolution order, diamond inheritance.
- Thuộc tính/phương thức ẩn khi thực hiện kế thừa.


## 2. property trong Python
- Ý nghĩa: kích hoạt một chuỗi hành động khi thuộc tính tương ứng được gọi trong chương trình.
- Ví dụ: thuộc tính `area` nên là một property của class Rectangle, được tính từ `length` và `width`.

Kiến thức nâng cao
- Ngoài việc cách sử dụng kể trên, property còn có hai tính năng liên quan là `setter` và `deleter`.
- `@property` đối với một instance của một class giống như `X` đối với một class. Tìm `X`.


## 3. Dunder methods - overloading operators
Từ dunder ghép bởi d(ouble) và under(scores). Dunder methods là những phương thức với hai dấu gạch dưới ở mỗi bên (methods with trailing double underscores). Sử dụng dunder methods giúp viết các phép toán một cách trực quan hơn. Danh sách các methods có trong tài liệu tham khảo.

Xét ví dụ khi cần cài đặt phương thức _cộng_ hai đối tượng của class `X`. Cách ngây thơ nhất là viết một hàm rời, nhận vào hai đối tượng và trả về một đối tượng tổng. Nâng cao hơn một chút, ta đặt hàm đó vào trong class `X` như trong mô tả dưới đây.

```py
class X:
    def addAnotherFraction(self, another):
        pass

objectC = objectA.addAnotherFraction(objectB)
```

Tuy nhiên, cách tốt nhất là cài đặt phương thức `__add__`. Ví dụ dưới đây thể hiện cách làm, đồng thời có thêm `__repr__` cho việc hiển thị đối tượng.

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
- Danh sách các [dunder methods](https://www.reddit.com/r/Python/comments/br9ok2/list_of_all_python_dunder_methods/) trong Python

Tài liệu bổ sung
- [Abstract base class](https://docs.python.org/3/library/abc.html) trong Python
- [Multiple inheritance](https://en.wikipedia.org/wiki/Multiple_inheritance)
- [Method resolution order](https://stackoverflow.com/questions/2010692/what-does-mro-do) in stackoverflow
- [Setter and deleter](https://www.programiz.com/python-programming/methods/built-in/property) in programiz
- https://realpython.com/python-super
- ThinkPython (trang 195-222)
