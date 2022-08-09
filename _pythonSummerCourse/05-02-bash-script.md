---
title: "Bài 13. Bash script"
permalink: /pythonSummerCourse/week-05-bash-scripts/
last_modified_at: 2022-08-09
redirect_from:
  - /theme-setup/
toc: false
---
## 1. Lệnh cơ bản sử dụng trong Terminal/Command Prompt
### 1.1 Linux
### Một số lệnh cơ bản

* **sudo** (viết tắt của `superuser do`): Cho phép bạn chạy các lệnh khác với quyền của admin. Nó hữu dụng khi mà bạn cần sửa các files ở trong các thư mục mà một user bình thường không có quyền truy cập.

* **pwd** (viết tắt của `print working directory`): Cho phép bạn biết được đường dẫn đến thư mục hiện tại mà bạn đang truy cập.

* **cd**: Chuyển hướng tập tin
  ```bash
  cd path/to/folder
  ```
  - `cd ..` (với 2 chấm) để chuyển lên 1 cấp thư mục trên
  - `cd` để tới thẳng thư mục home
  - `cd -` (với dấu gạch ngang) để chuyển tới thư mục bạn đã ở trước đó

* **ls**: Lệnh này sẽ hiển thị cho bạn thấy danh sách các files hay thư mục con trong thư mục hiện tại bạn đang truy cập.

  - `ls -l` sẽ hiển thị danh sách các files, thư mục kèm theo thông tin về dung lượng, thời gian được tạo, và quyền truy cập của các files, thư mục đó.
   - `ls -a` sẽ hiển thị danh sách bao gồm cả các files, thư mục bị ẩn trong thư mục hiện tại

* **cp** (`copy`): Cho phép bạn copy một file.

  ```bash
  cp file.sh foo.sh
  ```
  - Ví dụ `cp file.sh foo.sh` sẽ tạo ra một bản copy của "file.sh" với tên là "foo.sh", nhưng "file.sh" sẽ vẫn còn ở đó.
  - Nếu bạn muốn copy cả một thư mục, bạn phải sử dụng lệnh `cp -r directory foo`

* **mv** (`move`): Lệnh này cho phép bạn di chuyển một file sang một thư mục khác hoặc đổi tên của một file nào đó.
  ```bash
  mv foo.sh bar.sh
  ```
  - Ví dụ, `mv foo.sh bar.sh` sẽ đổi tên của file "foo.sh" thành "bar.sh"
  - `mv foo.sh ~/Pictures` sẽ di chuyển file "foo.sh" đến thư mục Pictures, nhưng không đổi tên của nó. `mv foo.sh ~/Pictures/bar.sh` sẽ di chuyển file "foo.sh" đến thư mục Pictures với tên "bar.sh"

* **rm** (remove): Cho phép bạn xóa một file. Sử dụng `rm -r` directory nếu bạn muốn xóa cả một thư mục

* **mkdir** (make directory): Cho phép bạn tạo một thư mục mới.

* **history**: Hiển thị tất cả những lệnh bạn đã gõ trước đó.

* **man**: lệnh này hiển thị hướng dẫn sử dụng của những lệnh khác. Ví dụ, bạn muốn biết cách sử dụng lệnh `mkdir` như đã nói ở trên, bạn viết lệnh đó như sau: `man mkdir`.

### Một số phím tắt hữu dụng sử dụng trên terminal
* **Ctrl + Alt + T**: Mở Terminal
* **Ctrl + Shift + W**: Đóng Terminal hiện tại.
* **Ctrl + Shift + Q**: Đóng toàn bộ Terminal.
* **Ctrl + A** hoặc **Home**: Di chuyển con trỏ chuột về vị trí đầu dòng
* **Ctrl + E** hoặc **End**: Di chuyển con trỏ chuột đến vị trí cuối dòng
* **Esc + B**: Di chuyển đến vị trí bắt đầu của từ hiện tại hoặc từ trước đó
* **Ctrl + K**: Xóa từ vị trí hiện tại của con trỏ đến cuối của dòng
* **Ctrl + U**: Xóa từ vị trí bắt đầu của dòng đến vị trí hiện tại của con trỏ
* **Ctrl + W**: Xóa từ đứng trước con trỏ
* **Alt + B**: Di chuyển lùi lại một từ
* **Alt + F**: Di chuyển tiến lên một từ
* **Alt + C**: Viết hoa kí tự ở vị trí con trỏ và chuyển con trỏ xuống cuối dòng

### 1.2 Windows
### Một số lệnh cơ bản trong `Command Prompt` (`CMD`)
* **cd**: Chuyển hướng tập tin (Tương tự như đối với `linux`)
* **dir**: Duyệt ra các file và thư mục (không bao gồm file ẩn) tại vị trí thư mục hiện tại hoặc thư mục tiếp theo theo đường dẫn cho trước.
  > Để hiện thị tất cả file và thư mục bao gồm cả file, thư mục ẩn có thể sử dụng  `dir /a`.

* **mkdir** hoặc **md**: Tạo mới nhiều hoặc một thưc mục
  ```bash
  mkdir foo bar
  md foo bar
  ```

* **rmdir** hoặc **rd**: Xóa một hoặc nhiều thư mục

  ```cmd
  rmdir foo bar
  rd foo bar
  ```

* **copy**: Sao chép một hoặc nhiều file
  ```cmd
  copy <file_1> <file_2> "path/to/save/folder"
  ```

* **move**: Di chuyển một hoặc nhiều file

  ```cmd
  move <file_1> <file_2> "path/to/save/folder"
  ```

* **del**: Xóa một hay nhiều file
  ```cmd
  del <file_1> <file_2>
  ```
### Một số phím tắt hữu dụng trong command prompt
* **Windows + X sau đó nhấn phím C**: Mở Command Prompt ở chế độ bình thường (phím tắt mới trên Windows 10).

* **Nhấn Windows + X, sau đó nhấn phím A**: Mở Command Prompt dưới quyền Admin (phím tắt mới trên Windows 10).

*  **Alt + F4**: Đóng Command Prompt.

* **Alt + Enter**: Chuyển đổi từ chế độ full màn hình sang chế độ cửa sổ.

* **Home/End**: Di chuyển dấu nhắc đến đầu/cuối trong dòng hiện tại.

* **Ctrl + ←/→**: Di chuyển dấu nhắc đến đầu hoặc kết tiếp của từ trước đó trong dòng hiện tại.

* **Ctrl + ↑/↓**: Cuộn trang lên hoặc xuống mà không di chuyển dấu nhắc.

* **Ctrl + A**: Chọn tất cả text trên dòng hiện tại. Nhấn **Ctrl + A** lần nữa để chọn tất cả text trên bộ đệm CMD (CMD Buffer).

* **Ctrl+ C** (hoặc **Ctrl + Insert**): Sao chép văn bản mà bạn đang chọn.

* **Ctrl + V** (hoặc **Shift + Insert**): Dán văn bản từ clipboard.

* **F3**: Lặp lại lệnh trước đó.

* **↑/↓**: Di chuyển ngược trở lại và chuyển tiếp thông qua các lệnh trước đó bạn đã nhập vào phiên hiện tại.

  > Ngoài ra bạn có thể nhấn phím F5 thay vì sử dụng phím mũi tên lên xuống để di chuyển ngược trở lại trên lịch sử lệnh.

* **F7**: Hiển thị lịch sử các lệnh trước đó. Ngoài ra bạn có thể sử dụng phím mũi tên lên/xuống để lựa chọn bất kỳ một lệnh nào đó, sau đó nhấn Enter để thực hiện lệnh.

* **Alt + F7**: Xóa lịch sử lệnh.

* **F8**: Di chuyển quay trở lại lịch sử lệnh để ghép với các lệnh hiện tại.
## 2.  Đối số trong python
### 2.1 Đối số là gì?
Trong Python, bạn có thể định nghĩa một hàm có số lượng đối số thay đổi. Chúng ta đã hiểu về cách xác định một hàm và gọi nó.

```py
def hello(name, msg):
    print(f'Hello {name}, {msg}')

hello('MIM Python', 'How are you?')
```

Kết quả:
```
Hello MIM Python, How are you?
```

Ở ví dụ trên hàm `hello()` có 2 tham số.

Ví ta đã call hàm này và có truyền vào 2 tham số nên hàm đã chạy chính xác và không gặp lỗi.

Nếu như ta call hàm này mà truyền vào thiếu một tham số hoặc không truyền vào tham số nào. Thì nó sẽ sảy ra lỗi. Khi hàm được định nghĩa có bao nhiêu tham số thì khi call hàm ta cần truyền vào đủ các tham số đó.

```py
hello('MIM Python') # only one 1 argument
```

Kết quả:
```
TypeError: hello() missing 1 required positional argument: 'msg'
```

### 2.2 Các loại đối số trong Python
### Đối số mặc định
Các đối số của hàm sẽ có giá trị mặc định trong Python.

Ta có thể cung cấp giá trị mặc định cho một đối số bằng cách sử dụng toán tử gán (=).

```py
def hello(name, msg='How are you?'):
    print(f'Hello {name}, {msg}')

hello('MIM Python')
hello('MIM Python', 'Good morning!')
```

Kết quả

```
Hello MIM Python, How are you?
Hello MIM Python, Good morning!
```

Ở ví dụ trên thì tham số `name` sẽ không có giá trị mặc định và khi call function thì cần bắt buộc phải truyền tham số `name` vào function.

Ngược lại với tham số `msg` đã luôn được gán giá trí mặc định là "How are you?". Vì vậy nếu như khi call function chúng ta có thể truyền tham số `msg`. Nếu ta truyền tham số vào thì `msg` sẽ có value là giá trí chúng ta truyền vào. Nếu chúng ta không truyền tham số thì giá trị của `msg` mặc định sẽ luôn là "How are you?".

### Đối số từ khóa trong Python

Khi chúng ta gọi một hàm với một số giá trị, các giá trị này được gán cho các đối số theo vị trí của chúng.

Ví dụ khi chúng ta gọi hàm `hello()` với cách gọi các tham số greet("MIM Python", "How are you?") . thì giá trị "MIM Python" sẽ tương ứng với với đối số `name` và "How are you?" sẽ là của đối số `msg`.

Python cho phép các hàm được gọi bằng cách sử dụng các đối số từ khóa. Khi chúng ta gọi các hàm theo cách này, thứ tự (vị trí) của các đối số có thể bị thay đổi. Các lệnh gọi sau đến hàm `hello()` ở dưới đây đều hợp lệ và tạo ra cùng một kết quả.

```py
# 2 keyword arguments
hello(name='MIM Python', msg='How are you?')

# 2 keyword arguments (out of order)
hello(msg='How are you?', name='MIM Python')

# 1 positional, 1 keyword argument
hello('MIM Python', msg='How are you?')
```

Như chúng ta thấy, chúng ta có thể thay đổi các đối số vị trí với các đối số từ khóa trong khi gọi hàm. Nhưng chúng ta phải lưu ý rằng các đối số từ khóa phải tuân theo các đối số vị trí.

Có một đối số vị trí sau các đối số từ khóa sẽ dẫn đến lỗi.

```py
hello(name='MIM Python', 'How are you?')
```

Kết quả sẽ lỗi:
```
SyntaxError: non-keyword arg after keyword arg
```

### Đối số tùy chọn trong Python
#### Sử dụng `*args`
Có những trường hợp chúng ta có thể sẽ chưa biết trước được số lướng đối số sẽ truyền vào một hàm là bao nhiều. Với trường hợp này Python sẽ cho chúng ta 1 giải pháp đó là gọi hàm với số lượng đối số tùy chọn.

Trong khi định nghĩa hàm, chúng ta sẽ sử dụng dấu hoa thị (*) trước tên tham số để biểu thị loại đối số này. Ví dụ dể tính tổng các số mà chúng ta không biết số lương truyền vào

``` py
def sum_cal(*args):
    result = 0
    for x in args:
        result += x
    return result

sum_cal(1, 2, 3, 4, 5, 6)
sum_cal(1, 2, 3, 4, 5, 6, 7, 8)
```

Kết quả:

```
21
36
```

Cú pháp này tiện lợi hơn rất nhiều do chúng ta hoàn toàn không cần xây dựng một list để truyền vào hàm. Tất cả các tham số truyền vào sẽ là phần tử của `*args` và chúng ta có thể duyệt qua nó như một **tuple** bình thường.

Ngoài ra, chúng ta hoàn toàn có thể kết hợp `*args` với các tham số khác của hàm với ý nghĩa "những tham số còn lại". Trong trường hợp này, `*args` sẽ phải đặt ở cuối cùng nếu không sẽ gặp lỗi.

```py
def foo(a, b, *arg):
    print('normal arguments', a, b)
    for x in args:
        print('another argument through *args', x)

foo(1, 2, 3, 4)
```

Kết quả:

```
normal arguments 1 2
another argument through *args 3
another argument through *args 4
```

#### Sử dụng (**kwargs)

Cách sử dụng `**kwargs` cũng tương tự như như `*args`, tuy nhiên, nó không dùng cho các tham số thông thường truyền vào lần lượt, mà nó được sử dụng cho các tham số đặt tên (thuật ngữ chính xác là **named arguments** hoặc **keyword arguments**).

```py
def foo(**kwargs):
    for key, value in kwargs.items():
        print(key, value)

foo(a=1, b=2)
```
Kết quả:

```
a 1
b 2
```

Lưu ý rằng, với cách sử dụng `**kwargs` thì kwargs trong hàm sẽ nhận giá trị là một **dict** với key là các tham số được truyền kèm giá trị tương ứng của chúng.

Ngoài ra, cũng tương tự như `*args`, `**kwargs` cũng hoàn toàn có thể kết hợp được với các tham số thông thường khác, và kết hợp với cả `*args` luôn. Nhưng thứ tự khi khai báo các tham số này rất quan trọng và không thể thay đổi được. Thứ tự đúng sẽ là:

1. Các tham số bình thường
2. *args
3. **kwargs


> Việc sử dụng tên `*args` và `**kwargs` là hoàn toàn không bắt buộc. Chỉ có cú pháp với dấu * là bắt buộc mà thôi. Nếu muốn chúng ta hoàn toàn có thể viết là *var và **vars cũng không gặp bất cứ vấn đề gì cả. Tuy nhiên, `*args` và `**kwargs` được sử dụng phổ biến như một quy tắc ngầm vậy, do đó, hầu như mọi người đều sử dụng cách viết đó.


## 3. Đối số dòng lệnh trong python

### 3.1 Sử dụng thư viện `sys.argv`
Module `sys` Python cung cấp quyền truy cập vào bất kỳ đối số dòng lệnh nào thông qua `sys.argv`

`Sys.argv` là danh sách các đối số dòng lệnh được chuyển tới chương trình Python. Argv đại diện cho tất cả các mục đi kèm qua đầu vào của [ input ] dòng lệnh, về cơ bản nó là một mảng giữ các đối số dòng lệnh của chương trình của chúng ta. Và nó đếm **bắt đầu bằng 0 chứ không phải 1**

```py
# file foo.py

import sys

def foo(*args):
    result = 0
    for x in args:
        result += x
    return result

print(foo(sys.args[1], sys.args[2], sys.args[3]))
```

```bash
python foo.py 1 2 3

6
```
### 3.2 Sử dụng thư viện `argparse`

Các `sys.argv` danh sách chứa dưới dạng mục đầu tiên tên của tệp đã được chạy.

Cách này tuy đơn giản nhưng bạn phải thực hiện rất nhiều công đoạn. Bạn cần xác thực các đối số, đảm bảo rằng kiểu của chúng là chính xác, bạn cần in phản hồi cho người dùng nếu họ không sử dụng chương trình một cách chính xác.

Python cung cấp một gói khác trong thư viện chuẩn để giúp bạn: `argparse`.

```py
import argparse
parser = argparse.ArgumentParser(description=‘This program do something’)
```

Biến parser sẽ lưu giữ các thông tin cần thiết để truyền các biến t đối dòng lệnh. Tham số `description` được sử dụng để cung cấp thông tin mô tả chương trình của bạn.

Ngoài `description` thì ArgumentParrser còn một số các tham số khác như sau:

* `prog` : Tên của chương trình (Mặc định sys.argv[0], đây thường chính là tên file mà bạn lưu code. )
* `usage`: Một chuỗi miêu tả cách sử dụng chương trình
* `formatter_class`: Một class để tùy chỉnh phần thông tin trợ giúp
* `add_help` : Thêm cờ -h/--help cho chương trình để thiện phần thông tin trợ giúp
* `argument_default`: Các tham số mặc định truyền vào

```py
parser.add_argument('integers', metavar='N', type=int, nargs='+',
                    help='an integer for the accumulator')

parser.add_argument('--sum', dest='accumulate', action='store_const',
                    const=sum, default=max,
                    help='sum the integers (default: find the max)')
```

Ở đây, trước hết `add_argument` định nghĩa cách mà các biến từ đối dòng lệnh sẽ được truyền vào Python. Mỗi lần gọi `add_argument` sẽ xử lý một tham số duy nhất.

Ở vị trí đầu tiên (ở trong ví dụ là integers hoặc --sum), đây có thể là tên hoặc một flag bạn sẽ truyền vào.

* **metavar**: Tên của tham số khi được ghi trong các phần thông tin trợ giúp (ở trong ví dụ là các đoạn usage: prog.py [-h] [--sum] N [N ...] và positional  arguments: N an integer for the accumulator
* **type** : Kiểu dữ liệu mà tham số truyền vào sẽ được ép thành (ở trong ví dụ là kiểu int)
* **help**: Phần thông tin trợ giúp
* **dest**: Tên của thuộc tính mà sẽ được thêm vào biến được trả về bởi parse_args(). dest ở trong ví dụ là accumulate, và bạn có thể thấy thuộc tính này được gọi sau này.
* **const**: Một hằng giá trị , không được truyền vào từ đối dòng lệnh nhưng vẫn được lưu bên trong để 1 số hàm bên trong sử dụng, nhất là hàm action
* **default**: Giá trị mặc định trả về nếu không có biến nào được truyền vào từ đối dòng lệnh.

Trong hàm `add_argument`, có 2 tham số đặc biệt cần lưu ý là `nargs` và `action`

`action`: Mỗi tham số truyền vào đối dòng lệnh sẽ được lớp ArgumentParser đính với 1 action , tức là một hành động duy nhất.

* `store`: hành động này sẽ lưu giá trị truyền vào. Đây là hành động mặc định
* `store_const`: hành động này sẽ lưu trữ giá trị được định nghĩa bởi từ khóa const. Như ở ví dụ trên, const đang truyền vào hàm sum. Biến này thường được dùng với các tham số dạng flag.

```py
parser = argparse.ArgumentParser()
parser.add_argument('--foo', action='store_const', const=42)
parser.parse_args(['--foo'])
```

* `store_true` và `store_false` : đây là dạng đặc biệt của action `store_const`, chuyên dùng để lưu các biến True và False, và đồng thời tạo Các giá trị mặc định False và True.
* `count`: Đếm số lần một keyword argument xảy ra
* `extend`: Lưu 1 list, thêm các tham số truyền vào sau vào list đó.

`nargs`: Như đã nói ở trên thì mỗi tham số truyền vào đối dòng lệnh sẽ được lớp `ArgumentParser` đính với 1 `action` Tham số nargs có thể đính một số lượng các tham số khác nhau với 1 `action`.

* `*`: Tất cả các tham số truyền vào từ đối dòng lệnh được gom lại vào 1 list
* `+`: Giống như `*`. Nhưng sẽ trả ra 1 tin nhắn lỗi nếu không có tham số nào được truyền vào. Đây là giá trị được sử dụng ở ví dụ.
* `N`: Một số nguyên N các tham số truyền vaò từ đối dòng lệnh sẽ được gom vào một list.
* `?`: Sẽ chỉ có 1 tham số truyền vào từ đối dòng lệnh được xử lý. Nếu không có tham số nào thì giá trị từ tham số default sẽ được sử dụng.

```py
args = parser.parse_args()
```

Hàm `parse_args()` biến các tham số được gửi vào từ đối dòng lệnh thành các thuộc tính của 1 object và trả về object đó. Như vậy có thể thấy trong ví dụ ở bên trên, `args` sẽ là một object chứa các biến được truyền vào như `integer` và `accumulate`.

Ví dụ:

```py
import argparse


def foo(a):
    bar = a + 10
    print(bar)
    return

if __name__ == "__main__":
    try:

        parser = argparse.ArgumentParser(description='A test')
        parser.add_argument("--a", type=int, default=1, help="Test variable")


        args = parser.parse_args()
        a = args.a


        foo(a)
    except KeyboardInterrupt:
        print('User has exited the program')
```

```bash
python foo.py --a 2
12
```

## Tài liệu tham khảo
Tài liệu chính
- [Viết script trên Linux](https://www.freecodecamp.org/news/shell-scripting-crash-course-how-to-write-bash-scripts-in-linux/)
- [Những lệnh cơ bản trên Linux](https://www.geeksforgeeks.org/basic-shell-commands-in-linux/)
- [Thư viện argparse](https://docs.python.org/3/library/argparse.html) trong Python
- [Bài viết về thư viện `argparse`](https://realpython.com/command-line-interfaces-python-argparse/) trên trang web Real Python
- [Documentation](https://docs.python.org/3/library/argparse.html) của thư viện `argparse`

Tài liệu bổ sung
- [Python: *args và **kwargs](https://viblo.asia/p/python-args-va-kwargs-gDVK2pdnlLj)
- [Đối số trong Python](https://viblo.asia/p/doi-so-trong-python-YWOZrrD7ZQ0)
