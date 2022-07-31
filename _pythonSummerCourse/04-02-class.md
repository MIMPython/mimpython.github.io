---
title: "Bài 10. Lớp (class)"
permalink: /pythonSummerCourse/week-04-class/
last_modified_at: 2022-07-31
redirect_from:
  - /theme-setup/
toc: false
---
## 1. Class trong Python
```py
class Person:
    """
        Initialize a simple class.
    """
    def __init__(self, name, age):
        """Initialize name and age attributes."""
        self.name = name
        self.age = age

    def sit(self):
        """Indicate a person sitting."""
        print(f"{self.name} is now sitting.")
```
- Ở ví dụ trên, mỗi người được tạo ra từ lớp Person sẽ được lưu trữ tên (name), tuổi (age) và có hành động ngồi (sit()).

## 2. Các thuộc tính, phương thức của một class
### 2.1 Thuộc tính trong class
- Dựa vào ví dụ trên, các biến `name` và `age` được gọi là thuộc tính.
- Để truy cập các thuộc tính
  ```py
  myFriend = Person('John', 22)
  print(myFriend.name)  # John
  ```
- Một số thuộc tính mặc định (built-in) như `__doc__`, `__class__`, `__name__`, `__dict__`, `__module__`, ...
  - Ví dụ `__doc__` trong class và trong function cũng có.
    ```py
      print(sit.__doc__)  # Indicate a person sitting.
    print(Person.__doc__)  # Initialize a simple class.
    ```
  - Ví dụ `__class__`
    ```py
    print(myFriend.__class__)  # <class '__main__.Person'>
    ```
  - Ví dụ `__name__`
    ```py
    print(Person.__name__)  # Person
    ```

### 2.2. Phương thức trong class
- `sit()` là một phương thức trong class `Person`.
- Để gọi phương thức trong class
```py
myFriend.sit()  # John is now sitting.
```

## 3. `@classmethod`, `@staticmethod`, `@property` decorators
### 3.1. `@classmethod`
- Dùng `@classmethod` để đánh dấu cho một class method.
- Thay vì sử dụng tham số `self` thì class method dùng tham số `cls`.
  ```py
  from datetime import date


      # a class method to create a Person object by birth year.
      @classmethod
      def initializeBirthYear(cls, name, year):
          return cls(name, date.today().year - year)

  personA = Person('John', 22)
  personB = Person.initializeBirthYear('John', 2000)

  print(personA.age)  # 22
  print(personB.age)  # 22
  ```

### 3.2. `@staticmethod`
- Dùng `@staticmethod` để đánh đấu cho một static method.
- Không dùng tham số `self` và `cls`.
  ```py
      # a static method to check if a Person is retirement or not.
      @staticmethod
      def isRetired(age):
          return age > 65

  print(Person.isRetired(68))  # True
  ```

### 3.3 `@property`
- Trong Python property() được sử dụng như một decorators, có thể sử dụng `@property` để đánh dấu.
  ```py
    @property
    def height(self):
      """The height property."""
      print("Get height")
      return self._height

    @height.setter
    def height(self, height):
      print("Set height")
      self._height = height

    @height.deleter
    def height(self):
      print("Delete height")
      del self._height
  ```

> Nội dung trên chỉ là tóm tắt, học viên cần đọc các tài liệu liệt kê trong phần tài liệu tham khảo dưới đây.

# Tài liệu tham khảo
Tài liệu chính
- PythonCrashCourse (trang 157-182)
- [Bài viết về `@classmethod` và `@staticmethod`](https://realpython.com/instance-class-and-static-methods-demystified/) trên trang web Real Python
- [Bài viết về `@property`](https://realpython.com/python-property/) trên trang web Real Python

Tài liệu bổ sung
- ThinkPython (trang 177-187)
- [Câu trả lời trên stack overflow](https://stackoverflow.com/questions/207000/what-is-the-difference-between-class-and-instance-attributes) về sự khác biệt giữa thuộc tính của class và thuộc tính của đối tượng
- [Câu trả lời trên stack overflow](https://stackoverflow.com/questions/12179271/meaning-of-classmethod-and-staticmethod-for-beginner) về `@classmethod` và `@staticmethod`
