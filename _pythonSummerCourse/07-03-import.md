---
title: "Bài 18. Module trong Python"
permalink: /pythonSummerCourse/week-07-module-in-python/
last_modified_at: 2022-07-25
redirect_from:
  - /theme-setup/
toc: false
---

Nội dung kiến thức
- Cách viết một module trong Python
- Cách import một module (absolute import hoặc relative import)

Có thể sử dụng thư viện [ipynb](https://ipynb.readthedocs.io/en/latest/) để import `class/function/variable` từ một file Jupyter notebook sang một file Jupyter notebook khác. Tuy nhiên, đây là phương pháp bất đắc dĩ. Trong hầu hết các trường hợp, người viết code nên chuyển _những thứ cần được import_ vào một module (file `.py`).

Chú ý quan trọng nhất về cách import trong Python:

**Không thể chạy trực tiếp một file sử dụng relative import.**

Tức là nếu người dùng muốn thực thi câu lệnh
```sh
python main.py
```
thành công thì file `main.py` không được phép sử dụng relative import.

Mặt khác, giả sử file `main.py` này có nội dung
```py
from fileA import methodX
from fileB import methodY
```
thì trong `fileA.py` và `fileB.py` có thể sử dụng relative import.


## Tài liệu tham khảo
- [Hướng dẫn về Python packages](https://realpython.com/python-modules-packages/) trên trang web Real Python
