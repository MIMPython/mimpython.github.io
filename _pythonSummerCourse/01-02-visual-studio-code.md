---
title: "Bài 2. Visual Studio Code"
permalink: /pythonSummerCourse/week-01-visual-studio-code/
last_modified_at: 2022-06-30
redirect_from:
  - /theme-setup/
toc: false
---
## 1. Visual Studie Code là gì?

**Visual Studio Code** *(VS Code hay VSC)* Là một trình biên tập lập trình code miễn phí dành cho Windows, Linux và macOS, Visual Studio Code được phát triển bởi Microsoft. Nó được xem là một sự kết hợp hoàn hảo giữa IDE và Code Editor.

VS Code hỗ trợ chức năng debug, đi kèm với Git, có syntax highlighting, tự hoàn thành mã thông minh, snippets, và cải tiến mã nguồn. Nhờ tính năng tùy chỉnh, Visual Studio Code cũng cho phép người dùng thay đổi theme, phím tắt, và các tùy chọn khác.

Học viên tải Visual Studio Code tại [đây](https://code.visualstudio.com/).

## 2. VS Code với Python

### 2.1 Cài đặt tiện ích Python
Cài đặt [Python extension for VS Code](https://marketplace.visualstudio.com/items?itemName=ms-python.python) hoặc xem mục Extension trong VS Code appliation.

### 2.2 VS Code in a project (workspace) folder
Sử dung `cmd` hoặc `Power shell`, tạo mới 1 thư mục trống có tên là "Hello"
```console
mkdir Hello
cd Hello
code .
```

Khởi động VS Code trong một thư mục, thư mục đó sẽ trở thành "Workspace" của bạn
### 2.3 Tạo file code python
Chọn **New File** button trong `Hello` folder
<div>
	<img src="/assets/images/courses/01-02-visual-studio-code/native-toolbar-export.png"
	style="width:80%;
	max-width:700px;
	display: block;
	margin-left: auto;
	margin-right: auto;
	padding-top:20px;
	padding-bottom:20px;">
</div>

Tạo file tên `hello.py`, và nó sẽ tự động mở ở khu vực editor
<div>
	<img src="/assets/images/courses/01-02-visual-studio-code/hello-py-file-created.png"
	style="width:80%;
	max-width:700px;
	display: block;
	margin-left: auto;
	margin-right: auto;
	padding-top:20px;
	padding-bottom:20px;">
</div>

Viết đoạn mã sau vào `hello.py`

```py
msg = "Hello World"
print(msg)
```

<div>
	<img src="/assets/images/courses/01-02-visual-studio-code/intellisense01.png"
	style="width:80%;
	max-width:700px;
	display: block;
	margin-left: auto;
	margin-right: auto;
	padding-top:20px;
	padding-bottom:20px;">
</div>

### 2.4 Chạy Hello World
Cách đơn giản nhất để chạy `hello.py` với Python là nhấp vào nút `Run Python File in Terminal` play ở phía trên cùng bên phải.

<div>
	<img src="/assets/images/courses/01-02-visual-studio-code/run-python-file-in-terminal-button.png"
	style="width:80%;
	max-width:700px;
	display: block;
	margin-left: auto;
	margin-right: auto;
	padding-top:20px;
	padding-bottom:20px;">
</div>

Ngoài ra, bạn có thể chạy với `Terminal` bằng cách mở terminal trong **VS Code**  
<div>
	<img src="/assets/images/courses/01-02-visual-studio-code/vs-code-terminal.png"
	style="width:80%;
	max-width:400px;
	display: block;
	margin-left: auto;
	margin-right: auto;
	padding-top:20px;
	padding-bottom:20px;">
</div>

```console
python hello.py # Window
python3 hello.py # Linux / MacOs
```



## 3. VS Code với Jupyter Notebook
### 3.1 Tạo/Mở file **Jupyter Notebook**
Chạy **Jupyter: Create New Jupyter Notebook** trong Command Palette (`Ctrl + Shift + P`) hoặc tạo file `.ipynb` file trong workspace.

<div>
	<img src="/assets/images/courses/01-02-visual-studio-code/native-code-cells-01.png"
	style="width:80%;
	max-width:700px;
	display: block;
	margin-left: auto;
	margin-right: auto;
	padding-top:20px;
	padding-bottom:20px;">
</div>

Tiếp theo, chọn một **kernel** bằng cách sử dụng bộ chọn **kernel** ở trên cùng bên phải.

<div>
	<img src="/assets/images/courses/01-02-visual-studio-code/native-kernel-picker.png"
	style="width:80%;
	max-width:700px;
	display: block;
	margin-left: auto;
	margin-right: auto;
	padding-top:20px;
	padding-bottom:20px;">
</div>

Sau khi chọn **kernel**, chọn ngôn ngữ nằm ở dưới cùng bên phải của mỗi cell sẽ tự động cập nhật.

<div>
	<img src="/assets/images/courses/01-02-visual-studio-code/native-language-picker-01.png"
	style="width:80%;
	max-width:700px;
	display: block;
	margin-left: auto;
	margin-right: auto;
	padding-top:20px;
	padding-bottom:20px;">
</div>

### 3.2 Chạy cell
Bạn có thể chạy một ô mã bằng cách sử dụng biểu tượng Run ở bên trái ô và kết quả đầu ra sẽ xuất hiện ngay bên dưới ô mã.

Ngoài ra có thể sử dụng phím tắt `Ctrl + Enter` để chạy ô hiện tại, `Shift + Enter` chạy ô hiện tại và chuyển đến ô tiếp theo.

<div>
	<img src="/assets/images/courses/01-02-visual-studio-code/native-code-cells-03.png"
	style="width:80%;
	max-width:700px;
	display: block;
	margin-left: auto;
	margin-right: auto;
	padding-top:20px;
	padding-bottom:20px;">
</div>

Bạn cũng có thể chạy nhiều cell một lúc bằng **Run All**, **Run All Above**, or **Run All Below**

<div>
	<img src="/assets/images/courses/01-02-visual-studio-code/native-code-runs.png"
	style="width:80%;
	max-width:700px;
	display: block;
	margin-left: auto;
	margin-right: auto;
	padding-top:20px;
	padding-bottom:20px;">
</div>

### 3.3 Lưu Jupyter Notebook

Bạn có thể lưu file Jupyter Notebook bằng cách `Ctrl + S` hoặc `File > Save`

### 3.4 Export Jupyter Notebook

Bạn có thể xuất **Jupyter Notebook** dưới dạng tệp **Python** (`.py`), **PDF** hoặc **HTML**. 

Chọn `Export` trên thanh công cụ chính. Sau đó, bạn sẽ thấy một danh sách các tùy chọn định dạng tệp.

<div>
	<img src="/assets/images/courses/01-02-visual-studio-code/native-toolbar-export.png"
	style="width:80%;
	max-width:700px;
	display: block;
	margin-left: auto;
	margin-right: auto;
	padding-top:20px;
	padding-bottom:20px;">
</div>

## 4. Một số Extension hay
**GitLen**

Giúp việc thao tác với Git trực quan, dễ thực hiện

**TabNine** 

Gợi ý code, sử dụng AI tăng hiệu suất viết code

**GitHub Compilot** 

Tương tự như **TabNine**



> Dưới đây chỉ tóm tắt cơ bản nhất về **VS Code**, bạn có thể đọc và tham khảo thêm ở các tài liệu tham khảo ở dưới.

## Tài liệu tham khảo
- Hướng dẫn sử dụng [terminal](https://code.visualstudio.com/docs/editor/integrated-terminal) trong VS Code
- [Python](https://code.visualstudio.com/docs/python/python-tutorial) trong VS Code
- [Jupyter notebook](https://code.visualstudio.com/docs/datascience/jupyter-notebooks) trong VS Code
- [Một bài viết chi tiết](https://realpython.com/python-development-visual-studio-code/) trên trang web Real Python về VS Code.
