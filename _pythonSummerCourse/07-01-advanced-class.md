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
