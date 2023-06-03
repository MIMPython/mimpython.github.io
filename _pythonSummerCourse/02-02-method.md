---
title: "Bài 5. Phương thức"
permalink: /pythonSummerCourse/week-02-method/
last_modified_at: 2023-06-04
redirect_from:
  - /theme-setup/
toc: false
---

_Tác giả: Trần Bá Tuấn_

## 1. Hàm (function)
### 1.1. Hàm
- Ví dụ đơn giản về một hàm
```py
def greetUser():
    print("Hello!")
greetUser()
```
- Mỗi hàm trong Python có hai khía cạnh
  - Định nghĩa hàm (**function definition**): chứa các dòng lệnh xác định hành động của hàm đó.
  - Lời gọi hàm (**function invocation**): một hàm được dùng trong chương trình thông qua lời gọi hàm đó.
- Mỗi hàm được định nghĩa 1 lần nhưng có thể gọi nhiều lần.

### 1.2. Các thành phần trong hàm
```py
def total(a, b):
    result = a + b
    return result

print(total(2, 4))
```
- Ở ví dụ trên, từ khóa `def` đánh dấu bắt đầu định nghĩa hàm, tên hàm `total`, đối số `a`, `b`. Hàm `total` trả về tổng của hai đối số nhập vào bằng phép gán `result = a + b`.
- Từ khóa `return` được dùng để trả giá trị của hàm.
- Một hàm có thể không có đối số và không cần trả về giá trị gì.

### 1.3. Tham số mặc định
- Tham số của hàm có thể có giá trị mặc định, giá trị này có thể bỏ qua trong lời gọi hàm.
- Ví dụ

```py
def total(y, x=5):
    return x + y

s = 12
print(total(s))   # 17
print(total(s, 24))  # 36
```

### 1.4. Tham số có tiền tố `*` và `**`
- Trong Python, sử dụng tiền tố `*` để đánh dấu một tham số không cố định về số lượng tham số.
- Tiền tố `**` đánh dấu tham số mà mỗi đối số là 1 cặp khóa - giá trị (key - value).

Ví dụ với tiền tố `*`

```py
def total(*numbers):
    result = 0
    for i in numbers:
        result += i
    return result

print(total(17, 7, 5, 22, 20))  # 71
print(total(1, 7))  # 8
print(total(1, 2.4, 12, 20))  # 35.4
```
Ví dụ với tiền tố `**`
```py
def greetUser(**data):
    for name, age in data.items():
        print(f'Chào {name}! Bạn {age} tuổi, phải không?')

greetUser(**{"Peter": 5, "John": 3, "Emma": 4})
```
## 2. Từ khóa `pass`
- Trong mỗi vòng lặp, định nghĩa hàm (function), định nghĩa lớp (class) hoặc trong câu lệnh `if`, đoạn code tại đó không được phép để trống hoàn toàn.
- Câu lệnh `pass` được sử dụng có thể nói là "giữ chỗ cho code trong tương lai". Khi câu lệnh `pass` được thực thi thì không có điều gì xảy ra, đồng thời bạn tránh gặp lỗi khi code trống không được phép.

Ví dụ trong vòng lặp
```py
for i in [0, 1, 2, 3, 4]:
    pass
```
Ví dụ khi định nghĩa hàm
```py
def total():
    pass
```
Ví dụ khi định nghĩa lớp
```py
class Person:
    pass
```
Ví dụ trong câu lệnh `if`
```py
a = 100
b = 20
if a > b:
    pass
```
## 3. Booleans and conditionals

### 3.1. Booleans
- Booleans thể hiện cho một trong hai giá trị đúng hoặc sai (`True` hoặc `False`).
```py
print(6 > 5)  # True
print(6 == 5)  # False
print(6 < 5)  # False
```
- `True` và `False` là các giá trị đặc biệt kiểu `bool`, chúng không phải `string`.
```py
print(type(True))  # <class 'bool'>
print(type(False))  # <class 'bool'>
```
### 3.2. Conditionals
- Python hỗ trợ các điều kiện logic thông thường như: `==`, `!=`, `<`, `<=`, `>`, `>=`.
```py
>>> age = 22
>>> age < 25
True
>>> age <= 25
True
>>> age > 25
False
>>> age >= 25
False
```
Từ khóa `and` và `or`
```py
>>> ageOfA = 22
>>> ageOfB = 20
>>> ageOfA <= 21 and ageOfB <= 21
False
>>> ageOfA <= 21 or ageOfB <= 21
True
```
- Các điều kiện này có thể được sử dụng theo một số cách, phổ biến là trong câu lệnh `if` và vòng lặp.
```py
if x > 0:
    print('x là số dương')
```
```py
i = 1
while i < 4:
    print(i)
    i += 1
```
> Nội dung trên chỉ là tóm tắt, học viên cần đọc các tài liệu liệt kê trong phần tài liệu tham khảo dưới đây.

## Tài liệu tham khảo

Tài liệu chính
- PythonCrashCourse (trang 72-90, 130-155)
- [Bài viết về `pass`](https://realpython.com/python-pass/) trên trang web Real Python

Tài liệu bổ sung
- SeriousPython (trang 122-145)
- ThinkPython (trang 47-74)
- Danh sách [các hàm có sẵn](https://docs.python.org/3/library/functions.html) (built-in) trong Python
- [Hướng dẫn viết bình luận](https://realpython.com/python-comments-guide/) (comment) trong Python
