---
title: "Bài 17. Ngoại lệ/cảnh báo"
permalink: /pythonSummerCourse/week-07-custom-error-warning/
last_modified_at: 2022-08-28
redirect_from:
  - /theme-setup/
toc: false
---

## Nội dung kiến thức

## 1. Ngoại lệ (exception)
- Python sử dụng một đối tượng đặc biệt gọi là `exception` để quản lý lỗi xảy ra trong quá trình thực hiện chương trình.
- Một lỗi đơn giản là khi bạn chia một số cho 0 và cần phải bắt ngoại lệ đó.
  ```py
  >>> print(2/0)
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  ZeroDivisionError: division by zero
  ```

### 1.1. Từ khóa `raise`
- Sử dụng `raise` để bắt một ngoại lệ nếu điều kiện xảy ra.
- Để bắt một ngoại lệ khi điều kiện chắc chắn xảy ra thì sử dụng `raise` có thể như ví dụ dưới đây.
  ```py
  x = -2

  if x < 0:
      raise Exception("Numbers below zero")
  ```
- Khi bạn thực thi code:
  ```py
  ...> python test.py
  Traceback (most recent call last):
    File "...\test.py", line 4, in <module>
      raise Exception("Numbers below zero")
  Exception: Numbers below zero
  ```


### 1.2. Từ khóa `assert`
- Sử dụng `assert` khi nhất định điều kiện đó phải đáp ứng.

  ```py
  def average(scores):
      assert len(scores) != 0
      return sum(scores)/len(scores)

  score = []
  print("Average of score:", average(score))
  ```
Output:
  ```
  ...
  AssertionError
  ```

### 1.3. `try` and `except`
- Khối `try` and `except` được sử dụng để bắt (catch) và xử lý (handle) ngoại lệ.
  ```py
  try:
      print(a)
  except NameError:
      print("Variable a is not defined")
  ```
- Từ khóa `else` định nghĩa cho một khối code để thực thi nếu không có lỗi nào.
  ```py
  else:
      print("Nothing went wrong!")
  ```
- Khối `finally` nếu được chỉ định thì sẽ thực thi bất kể khối `try` dù có gây ra lỗi hay không.
  ```py
  finally:
      print("Hello!")
  ```
- Ví dụ khác
  ```py
  fruitsPrice = {
      'Apple': 5,
      'Orange': 7,
      'Banana': 9
  }

  key = None
  while True:
      try:
          key = input('Enter a key:')
          fruit = fruits[key.lower()]
      except KeyError:
          print(f'{key} does not exist.')
      except KeyboardInterrupt:
          break
      else:
          print(fruit)
      finally:
          print('Press Ctrl-C to exit.')
  ```

## 2. Cảnh báo (warning)
- `warning` được đưa ra để cảnh báo về các tình huống không nhất thiết phải ngoại lệ.
- Cảnh báo khác với một lỗi trong chương trình. Chương trình dừng ngay nếu khi gặp lỗi nhưng một cảnh báo mà không quan trọng thì nó hiển thị thông báo và chương trình vẫn chạy.
  ```py
  import warnings

  # displaying warning
  warnings.warn('This is a warning message!')
  ```
  ```py
  test.py:4: UserWarning: This is a warning message!
  warnings.warn('This is a warning message!')
  ```

## 3. Gỡ lỗi (debugging)
### 3.1. Sử dụng `breakpoint()`
- Ví dụ với 1 file có tên là `divisionCaculator.py`
  ```py
  def division(a, b):
      breakpoint()
      result = a / b
      return result

  print(division(12, 0))
  ```
- Trong terminal
```py
....> python divisionCaculator.py
> ...\divisioncaculator.py(3)division()
-> result = a / b
(Pdb)
```

### 3.2. Sử dụng `pdb module`
- `PDB` là Python Debugger. Để sử dụng `pdb` thì cần phải `import pdb` và sử dụng phương thức `set_trace()`.
  ```py
  import pdb
  import os


  def getPath(file):
      """Return file's path or empty string if no path."""
      head, tail = os.path.split(file)
      return head


  filename = __file__
  pdb.set_trace()
  filenamePath = getPath(filename)
  print(f'Path: {filenamePath}')
  ```

- Một số lệnh trong `pdb` cần thiết
  - `c`: tiếp tục thực thi.
  - `q`: thoát khỏi gỡ lỗi/ thực thi.
  - `n`: sang dòng tiếp theo trong cùng một hàm.
  - `s`: sang dòng tiếp theo trong hàm này hoặc một hàm được gọi.

> Nội dung trên chỉ là tóm tắt, học viên cần đọc các tài liệu liệt kê trong phần tài liệu tham khảo dưới đây.

## Tài liệu tham khảo

Tài liệu chính
- PythonCrashCourse (trang 194-202)
- [Ngoại lệ trong Python](https://realpython.com/python-exceptions/)
- [Gỡ lỗi trong Python](https://realpython.com/python-debugging-pdb/)

Tài liệu bổ sung
- [Một trao đổi](https://stackoverflow.com/questions/12265451/ask-forgiveness-not-permission-explain) trên stackoverflow
