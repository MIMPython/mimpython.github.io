---
title: "Bài 19. Documentation and docstring"
permalink: /pythonSummerCourse/week-08-documentation-docstring/
last_modified_at: 2022-09-03
redirect_from:
  - /theme-setup/
toc: false
---

## 1. Docstring là gì?
- Docstring được hiểu đơn giản là chú thích (giải thích) cho các đối tượng, nhằm cung cấp một cái nhìn tổng quát cho những ai muốn tìm hiểu về code cũng như cách hoạt động của các đối tượng. 
- Trong Python, kiểu docstring thường được đặt trong cặp của 3 dấu ngoặc kép ```"""```. 
- Docstring có thể được viết trong nhiều dòng hoặc không. Trong trường hợp tối thiếu, docstring nên có một dòng mô tả khái quát.

Sau đây, là một ví dụ đơn giản khi viết docstring cho phương thức cộng hai số:
```python 
def add(x, y):
    """
    This method is used to add two numbers.
    
    Arguments:
        x (int): first number
        y (int): second number
        
    Returns:
        result: the result of x + y
    """
    result = x + y
    return result
```

## 2. Các loại docstring 
Tùy theo loại đối tượng viết docstring thì ta có thể chia làm 3 loại chính như sau 
- docstrong cho `class`: được đặt ngay sau class hoặc phương thức của class và lùi vào 1 tab (4 space)
- docstring cho `package` và `module`: được đặt ở đầu file `__init__.py` của package, và nên liệt kê những module và sub-package được dùng trong package
- docstring cho `script`: được đặt ở đầu file `script`, nội dung chỉ nên vừa đủ để hiểu cách hoạt động của `script`

## 3. Các hình thức viết docstring phổ biến 
Ta có thể viết docstring theo các quy chuẩn được đề xuất sau đây (*Lưu ý: Các quy chuẩn dưới đây đều được lấy ví dụ để viết qua hàm `add(x, y)` ở mục 1*)
- [Google Docstrings](https://github.com/google/styleguide/blob/gh-pages/pyguide.md#38-comments-and-docstrings): mẫu docstring được đề xuất bởi Google

```
"""This method is used to add two numbers.

Arguments:
    x (int): first number
    y (int): second number
    
Returns:
    result: the result of x + y
"""
```
trong đó, `Argments` chứa các tên, kiểu và mô tả của các đối số truyền vào, còn `Returns` bao gồm tên và mô tả của các kết quả trả về. 

Một repo phổ biến mà có sử dụng kiểu docstring này là [tensorflow](https://github.com/tensorflow/tensorflow).

- [reStructuredText](http://docutils.sourceforge.net/rst.html): mẫu docstring chính thức, quy chuẩn của Python

```
"""This method is used to add two numbers.

:param x: first number
:type x: int
:param y: second number
:type y: int 
:returns: the result of x + y
:rtype: int 
"""
```
trong đó, `:param` (mô tả chung về biến) và `:type` (kiểu của biến) đi theo từng cặp để mô tả cho đối số truyền vào.

- [NumPy/SciPy docstrings](https://numpydoc.readthedocs.io/en/latest/format.html): mẫu docstring này là sự kết hợp của Google Docstrings và reStructuredText

```
"""This method is used to add two numbers.

Parameters
----------
x: int 
    first number 
y: int 
    second number 


Returns
-------
result: int 
    the result of x + y
"""
```
khi các tham số truyền vào, cũng như trả về sẽ được mô tả qua 2 dòng, dòng đầu tiên gồm `tên biến: kiểu biến`, dòng thứ 2 thì thụt lùi vào hơn để mô tả cho biến đó.

Như cái tên, thư viện `numpy` và `scipy` là ví dụ tiểu biểu cho việc dùng docstring này. 

- [Epytext](http://epydoc.sourceforge.net/epytext.html): mẫu docstring chuyển thể từ [Epydoc](http://epydoc.sourceforge.net/), thường phù hợp với các Java Developer hơn 

```
"""This method is used to add two numbers.

@type x: int
@param x: first number
@type y: int 
@param y: second number
@rtype: int 
@returns: the result of x + y
"""
```
trong đó, với các tham số truyền vào có thể được mô tả 
```
@type tên biến: kiểu biến 
@param tên biến: mô tả về biến 
```
và các tham số trả về 
```
@rtype: kiểu biến trả về 
@returns: mô tả về biến trả về 
```

## 4. Viết documentation cho dự án Python
Mỗi dự án Python thì đều có cách dùng, mục đích, cách tiếp cận khác nhau. 
Vì thế, documentation là cần thiết để hướng dẫn chi tiết về điều đó. 
Về hình thức, có thể chia các dự án thành 3 nhóm chính 
- Private: dự án riêng tư, hướng tới mục đích sử dụng cá nhân, không chia sẻ với người cũng như tổ chức khác 
- Shared: dự án được chia sẻ, dự án có hợp tác với người hoặc tổ chức khác 
- Public and Open Source: không giới hạn đối tượng truy cập

Nhìn chung, với loại dự án nào thì bố cục chung của dự án và documentation cần có những thứ sau
  
```
project_root/
│
├── project/  # Project source code
├── docs/
├── README
├── HOW_TO_CONTRIBUTE
├── CODE_OF_CONDUCT
├── examples.py
```

### 4.1 Private Project 
Một số phần được đề xuát thêm vào dự án như 
- `README`: Tổng quan về dự án cũng như mục đích, các thư viện đòi hỏi cần cài đặt cho dự án.
- `examples.py`: một `script` đưa ra những ví dụ đơn giản để chạy dự án.

### 4.2 Shared Project 
Một số phần được đề xuát thêm vào dự án như 
- `README`: Tổng quan về dự án cũng như mục đích, các thư viện đòi hỏi cần cài đặt cho dự án.
- `examples.py`: một `script` đưa ra những ví dụ đơn giản để chạy dự án.
- `How to Contribute`: bao gồm các hướng dẫn để một người mới có thể bắt đầu tham gia và dự án.

### 4.3 Public and Open Source
Một số phần được đề xuát thêm vào dự án như 
- `README`: Tổng quan về dự án cũng như mục đích, các thư viện đòi hỏi cần cài đặt cho dự án. Đồng thời, mô tả sự thay đổi nếu có so với phiên bản trước.
- `How to Contribute`: Bao gồm cách những người đóng góp mới cho dự án có thể trợ giúp, phát triển các tính năng mới, khắc phục các sự cố đã biết, thêm tài liệu, thêm các thử nghiệm mới hoặc báo cáo sự cố.
- `Code of Conduct`: Xác định cách những người đóng góp khác đối xử với nhau khi phát triển hoặc sử dụng phần mềm của bạn. Điều này cũng cho biết điều gì sẽ xảy ra nếu mã này bị hỏng.
- `License`: Tệp văn bản mô tả giấy phép mà dự án của bạn đang sử dụng. 
- `docs`: Một thư mục chứa thêm tài liệu.

trong đó, thư mục `docs` nên có các phần chính sau 
- `Tutorials`: Cung cấp một loạt các bài học để giúp người dùng sử dụng dự án. 
- `How-To Guides`: Hướng dẫn người đọc qua các bước cần thiết để giải quyết một vấn đề chung. 
- `References`: Giải thích làm rõ và làm sáng tỏ một chủ đề cụ thể.
- `Explanations`: Mô tả cách vận hành (class, function, API, v.v.). 

> Nội dung trên chỉ là tóm tắt, học viên cần đọc các tài liệu liệt kê trong phần tài liệu tham khảo dưới đây.

## Tài liệu tham khảo
- [Bài viết về documentation/docstring](https://realpython.com/documenting-python-code/) trên trang web Real Python