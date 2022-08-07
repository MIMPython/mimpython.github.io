---
title: "Bài 13. Bash script"
permalink: /pythonSummerCourse/week-05-bash-scripts/
last_modified_at: 2022-08-06
redirect_from:
  - /theme-setup/
toc: false
---
## 1. Lệnh cơ bản sử dụng trong Terminal/CMD
### 2.1 Linux
### Một sốlệnh cơ bản

* **sudo** (viết tắt của `superuser do`) - Cho phép bạn chạy các lệnh khác với quyền của admin. Nó hữu dụng khi mà bạn cần sửa các files ở trong các thư mục mà một user bình thường không có quyền truy cập.

* **pwd** (viết tắt của `print working directory`) - Lệnh này cho phép bạn biết được đường dẫn đến thư mục hiện tại mà bạn đang truy cập.

* **cd** chuyển hướng tập tin
  ```bash
  cd path/to/folder
  ```
  - `cd ..` (với 2 chấm) để chuyển lên 1 cấp thư mục trên
  - `cd` để tới thẳng thư mục home
  - `cd-` (với dấu gạch ngang) để chuyển tới thư mục bạn đã ở trước đó

* **ls** - Lệnh này sẽ hiển thị cho bạn thấy danh sách các files hay thư mục con trong thư mục hiện tại bạn đang truy cập.

  - `ls -l` sẽ hiển thị danh sách các files, thư mục kèm theo thông tin về dung lượng, thời gian được tạo, và quyền truy cập của các files, thư mục đó.
   - `ls -a` sẽ hiển thị danh sách bao gồm cả các files, thư mục bị ẩn trong thư mục hiện tại

* **cp** (`copy`) - Cho phép bạn copy một file.

  ```bash
  cp file foo
  ```
  - Ví dụ `cp file foo` sẽ tạo ra một bản copy của "file" với tên là "foo", nhưng "file" sẽ vẫn còn ở đó.
  - Nếu bạn muốn copy cả một thư mục, bạn phải sử dụng lệnh `cp -r directory foo`

* **mv** (`move`) - Lệnh này cho phép bạn di chuyển một file sang một thư mục khác hoặc đổi tên của một file nào đó.
  ```bash
  mv foo bar
  ```
  - Ví dụ, `mv foo bar` sẽ đổi tên của file "foo" thành "bar"
  - `mv foo ~/Pictures` sẽ di chuyển file "foo" đến thư mục Pictures, nhưng không đổi tên của nó. `mv foo ~/Pictures/bar` sẽ di chuyển file "foo" đến thư mục Pictures với tên "bar"

* **rm** (remove) - Cho phép bạn xóa một file. Sử dụng `rm -r` directory nếu bạn muốn xóa cả một thư mục

* **mkdir** (make directory) - Cho phép bạn tạo một thư mục mới.

* **history** - Hiển thị tất cả những lệnh bạn đã gõ trước đó.

* **man** - lệnh này hiển thị hướng dẫn sử dụng của những lệnh khác. Ví dụ, bạn muốn biết cách sử dụng lệnh `mkdir` như đã nói ở trên, bạn viết lệnh đó như sau: `man mkdir`.

### Một số phím tắt hữu dụng sử dụng trên terminal
* **Ctrl + A** or Home - Di chuyển con trỏ chuột về vị trí đầu dòng
* **Ctrl + E** or End - Di chuyển con trỏ chuột đến vị trí cuối dòng
* **Esc + B** - Di chuyển đến vị trí bắt đầu của từ hiện tại hoặc từ trước đó
* **Ctrl + K** - Xóa từ vị trí hiện tại của con trỏ đến cuối của dòng
* **Ctrl + U** - Xóa từ vị trí bắt đầu của dòng đến vị trí hiện tại của con trỏ
* **Ctrl + W** - Xóa từ đứng trước con trỏ
* **Alt + B** - Di chuyển lùi lại một từ
* **Alt + F** - Di chuyển tiến lên một từ
* **Alt + C** - Viết hoa kí tự ở vị trí con trỏ và chuyển con trỏ xuống cuối dòng

### 2.2 Window
### Một số lệnh cơ bản
* **cd** chuyển hướng tập tin (Tương tự như đối cới linux)
* **dir** duyệt ra các file và thư mục (không bao gồm file ẩn) tại vị trí thư mục hiện tại hoặc thư mục tiếp theo theo đường dẫn cho trước.
  > Để hiện thị tất cả file và thư mục bao gồm cả file, thư mục ẩn bạn có thể thêm /a vào sau dir.

* **mkdir** hoặc **md** tạo mới nhiều hoặc một thưc mục
  ```bash
  mkdir foo bar
  md foo bar
  ```

* **rmdir** hoặc **rd** Xóa một hoặc nhiều thư mục

  ```cmd
  rmdir foo bar
  rd foo bar
  ```

* **copy** sao chép một hoặc nhiều file
  ```cmd
  copy <file_1> <file_2> "path/to/save/folder"
  ```

* **move** di chuyển một hoặc nhiều file

  ```cmd
  move <file_1> <file_2> "path/to/save/folder"
  ```

* **del** xóa một hay nhiều file
  ```cmd
  del <file_1> <file_2>
  ```

## 2.  Cài đặt môi trường, truyền đối số vào file code Python

<!-- Nội dung kiến thức
- Những lệnh cơ bản được sử dụng trên terminal
- Cài đặt môi trường, truyền đối số vào file code Python
- Xử lý tham số câu lệnh trong Python (sử dụng `sys.argv` hoặc `argparse`) -->

Tài liệu tham khảo
- [Viết script trên Linux](https://www.freecodecamp.org/news/shell-scripting-crash-course-how-to-write-bash-scripts-in-linux/)
- [Những lệnh cơ bản trên Linux](https://www.geeksforgeeks.org/basic-shell-commands-in-linux/)
- [Thư viện argparse](https://docs.python.org/3/library/argparse.html) trong Python
- [Bài viết về thư viện `argparse`](https://realpython.com/command-line-interfaces-python-argparse/) trên trang web Real Python
- [Documentation](https://docs.python.org/3/library/argparse.html) của thư viện `argparse`
