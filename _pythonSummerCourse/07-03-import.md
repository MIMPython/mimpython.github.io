---
title: "Bài 18. Module trong Python"
permalink: /pythonSummerCourse/week-07-module-in-python/
last_modified_at: 2022-08-23
redirect_from:
  - /theme-setup/
toc: false
---


## TLDR
- **Không thể chạy trực tiếp một file sử dụng relative import.** Ví dụ, nếu câu lệnh thực thi là `python3 main.py` thì nội dung file `main.py` không được chứa relative import.
- Python tìm module trong các thư mục được liệt kê trong biến môi trường (environment variable) `PYTHONPATH`. Người dùng có thể thay đổi (chính xác hơn là bổ sung) những đường dẫn thư mục cần thiết vào `PYTHONPATH`.
- Phương pháp relative import thường được sử dụng trong file `__init__.py` để rút gọn việc import ở file code chính.


## 1. Đặt vấn đề
Xét cấu trúc thư mục như dưới đây
```
mainFolder/
  bar/
    utils.py
  main.py
```
Nội dung các file gồm có
```py
# utils.py
def foo():
    print('Hello MIMPython')

# main.py
from utils import foo
print(foo)
```

Mở một terminal tại thư mục `mainFolder/`, khi thực thi câu lệnh
```sh
python3 main.py
```
thì ta sẽ nhận được thông báo lỗi
```
ModuleNotFoundError: No module named 'utils'
```


## 2. Python tìm module ở đâu?
Khi thực thi một chương trình Python, chương trình sẽ tìm các module trong một danh sách các thư mục nhất định, danh sách này được lưu tại `sys.path` với kiểu dữ liệu `list`.

```py
import sys
print(sys.path)
```

Bổ sung hai dòng dưới vào file `main.py`
```py
import sys
sys.path.append('/path/to/mainFolder/bar/') # to import "utils" successfully
```
thì ta có thể chạy file `main.py` mà không gặp lỗi `ModuleNotFoundError`.

Tuy nhiên, phương pháp kể trên không tốt vì nó thực hiện việc thay đổi đường dẫn trong code. Một cách khác là thay đổi biến môi trường (environment variable) `PYTHONPATH`. Giá trị của biến này được hiển thị trên terminal với câu lệnh
```sh
echo $PYTHONPATH # Linux
```
hoặc bằng đoạn code Python sau
```py
import os
print(os.environ['PYTHONPATH'])
```

Để bổ sung thêm đường dẫn vào `PYTHONPATH`, ta thực hiện câu lệnh dưới đây trên terminal
```sh
# instructions for Linux
PYTHONPATH=$PYTHONPATH:/path/to/mainFolder/bar/
export PYTHONPATH
```
Hướng dẫn bổ sung đường dẫn trên Windows có thể tìm thấy trên stackoverflow.


## 3. Absolute import trong Python
Ví dụ cho cấu trúc absolute import
```py
import random
from math import sqrt
```

Một số thư viện phổ biến có những quy ước riêng về alias import (sử dụng keyword `as`), ví dụ như
```py
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd
```

**Chú ý.** Cấu trúc wildcard import có cách viết là `from x import *`. **Không nên sử dụng phương pháp này,** trừ những trường hợp bất khả kháng, ví dụ như khi sử dụng thư viện `manim`.


## 4. Relative import trong Python
Relative import sử dụng cách viết với một hoặc nhiều dấu `.` ở phần đầu. Chi tiết xem trong phần ví dụ phía dưới.


## 5. Ví dụ minh họa
Dưới đây là một ví dụ minh họa về cách sử dụng import trong Python.

```
testImport/
  utils/
    __init__.py
    fileA.py
    fileB.py
  main.py
```

Nội dung các file gồm có
```py
# fileA.py
def methodA():
    print('In methodA of fileA')
    return None

# fileB.py
from .fileA import methodA
def methodB():
    print('In methodB of fileB')
    return None

# __init__.py
from .fileA import methodA

# main.py
from utils import methodA
from utils.fileB import methodB
methodA()
methodB()
```

Bằng cách sử dụng import (cụ thể là relative import) trong file `__init__.py`, ta đã có thể lấy được `methodA` ngay từ `utils`, thay vì phải vào `utils.fileB` để lấy `methodB`. Một cách tổng quát, việc tạo (và sử dụng relative import trong) file `__init__.py` làm đơn giản hóa phần import trong file code chính.

Đứng ở thư mục `testImport/` và thực thi câu lệnh `python3 main.py`, ta thu được kết quả (thành công) như sau
```
In methodA of fileA
In methodB of fileB
```


## 6. Một số chú ý khác
- Quy ước cách viết import được liệt kê chi tiết trong PEP8.
- Không nên đặt tên file trùng với tên những thư viện phổ biến.
- Có thể sử dụng thư viện [ipynb](https://ipynb.readthedocs.io/en/latest/) để import `class/function/variable` từ một file Jupyter notebook sang một file Jupyter notebook khác. Tuy nhiên, đây là phương pháp bất đắc dĩ. Trong hầu hết các trường hợp, người viết code nên chuyển _những thứ cần được import_ vào một module (file `.py`).
- Lỗi cyclic import có thể phát sinh trong quá trình thiết kế chương trình. Đọc thêm [bài viết này](https://quanhoang-pm.github.io/programming/circular-imports-in-Python/) để biết cách giải quyết chúng.


## Tài liệu tham khảo
- [Hướng dẫn về Python packages](https://realpython.com/python-modules-packages/) trên trang web Real Python
- [Hướng dẫn về Python import](https://realpython.com/python-import/) trên trang web Real Python
