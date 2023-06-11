---
title: "Bài 7. Thao tác với file dữ liệu"
permalink: /pythonSummerCourse/lesson-07-managing-files/
last_modified_at: 2022-09-04
redirect_from:
  - /theme-setup/
toc: false
---

_Tác giả: Hoàng Anh Quân_

Phần tóm tắt nội dung bài viết sử dụng cây thư mục được minh họa dưới đây
```
mainFolder/
    folderA/
        main.py
        data.txt
    folderB/
```

Trong toàn bộ bài viết, ta sử dụng thuật ngữ terminal để gọi chung cho terminal trên Linux và command prompt trên Windows.

## 1. Đường dẫn
Để tham chiếu đến một file/thư mục nào đó trong cây thư mục, ta cần truyền vào đường dẫn tới file/thư mục đó. Có hai loại đường dẫn: đường dẫn tuyệt đối và đường dẫn tương đối.

Trong mục này, ta sẽ minh hoạ kiến thức về đường dẫn thông qua việc thực thi chương trình trong file `main.py` bằng nhiều cách khác nhau.

Cách thực hiện đơn giản nhất là mở một terminal tại thư mục `folderA` rồi chạy câu lệnh
```sh
python main.py
```

### 1.1. Đường dẫn tương đối
Câu lệnh viết ở trên minh họa một cách thực thi chương trình sử dụng đường dẫn tương đối. Cụ thể, đường dẫn tương đối của một file dữ liệu là cách di chuyển từ vị trí hiện tại của terminal tới file đó.

Vị trí hiện tại của terminal thường được thể hiện trong terminal. Ví dụ như trong terminal dưới đây
```sh
quanhoang@laptop (04:20:00) ~/OptimaLab/mainFolder $
```
thì thư mục hiện tại của terminal này là `mainFolder.` Ngoài ra, khoảng trống sau dấu `$` là nơi để viết câu lệnh.

Có thể truy xuất vị trí hiện tại của terminal thông qua câu lệnh (chạy trên hệ điều hành Linux) `echo $PWD`. [Một câu trả lời trên stack overflow](https://stackoverflow.com/questions/921741/windows-equivalent-to-unix-pwd) có thông tin về câu lệnh tương ứng cho hệ điều hành Windows.

Trong một đường dẫn tương đối, ta sử dụng dấu `..` để đi chuyển lên thư mục cha và sử dụng trực tiếp tên thư mục con để truy cập thư mục con đó. Ba ví dụ dưới đây thể hiện cách thực thi file `main.py` qua đường dẫn tương đối từ ba vị trí terminal khác nhau.

- Nếu terminal đang ở thư mục `folderA`, câu lệnh cần thực hiện là
```sh
python main.py
```

- Nếu terminal đang ở thư mục `mainFolder`, câu lệnh cần thực hiện (đối với từng hệ điều hành) là
```sh
python folderA/main.py # Linux
python folderA\main.py # Windows
```

- Nếu terminal đang ở thư mục `folderB`, câu lệnh cần thực hiện (đối với từng hệ điều hành) là
```sh
python ../folderA/main.py # Linux
python ..\folderA\main.py # Windows
```

### 1.2. Đường dẫn tuyệt đối
Đường dẫn tuyệt đối xuất phát từ gốc của cây thư mục và di chuyển tới file cần tham chiếu.

```sh
python /path/to/mainFolder/folderA/main.py # Linux
python D:\path\to\mainFolder\folderA\main.py # Windows
```

Đường dẫn tuyệt đối có ưu điểm là bất biến với vị trí của terminal. Tức là, để tham chiếu tới một file bất kỳ, người dùng có thể sử dụng cùng một đường dẫn tuyệt đối, bất kể vị trí hiện tại của terminal.

Đổi lại ưu điểm này, đường dẫn tuyệt đối thường **dài** và **chứa thông tin cá nhân của người sử dụng**. Sẽ không hay lắm nếu có đường dẫn mang nội dung dưới đây
```sh
python /home/trash/mimpython/main.py
```

### 1.3. Lời khuyên về đặt tên
Để thuận lợi trong quá trình lập trình, tên của các file, thư mục nên tuân thủ quy tắc ba không:
- Không chứa dấu tiếng Việt (sắc, huyền, hỏi, ngã, nặng)
- Không chứa dấu cách
- Không chứa kí tự đặc biệt (ví dụ như `?, :, +, -, *, (, ), [, ]`)


## 2. Đọc file
Giả sử file `data.txt` có nội dung dưới đây
```
MIM
Python
2022
```

Để đọc nội dung của file trên, file `main.py` nên được thiết kế như sau
```py
path = 'data.txt'
with open(path, 'r') as f:
    allLines = f.read().splitlines() # ['MIM', 'Python', '2022']
```
Phần nội dung xuất hiện sau dấu comment `#` thể hiện output khi thực hiện hàm `print()` cho biến tương ứng.

Một vài bình luận về việc đọc file

1. Để thực hiện chương trình trong `main.py`, người dùng cần chuyển đường dẫn tới thư mục `folderA.`

2. Biến `path` là đường dẫn tới file dữ liệu `data.txt`, hiện là một đường dẫn tương đối. Mốc khi xét đường dẫn tương đối luôn là **vị trị hiện tại của terminal**, chứ không phải là vị trí của file `main.py`.

3. Biến `path` có thể được thay bởi một đường dẫn tuyệt đối tới file `data.txt`.

4. Một số cách khác để tạo biến `allLines` chứa thông tin của tất cả các dòng trong file dữ liệu
```py
# cách thứ nhất
with open(path, 'r') as f:
    allLines = f.readlines() # ['MIM\n', 'Python\n', '2022\n']
# cách thứ hai
with open(path, 'r') as f:
    allLines = list(f) # ['MIM\n', 'Python\n', '2022\n']
```
Với hai cách này, người dùng nên sử dụng hàm `rstrip()` để loại bỏ ký tự `\n` ở cuối mỗi phần tử.

5. Hàm `split()` liên quan chặt chẽ tới việc xử lý file dữ liệu.
```py
splitedList = 'this_is_nothing'.split('_') # ['this', 'is', 'nothing']
```

6. Có một cách khác để đọc file mà không sử dụng cấu trúc `with ... as ...`
```py
f = open('data.txt', 'r')
allLines = f.read().splitlines()
f.close()
```
Tuy nhiên, người mới bắt đầu lập trình **không được khuyến khích** sử dụng cách này.

## 3. Tạo file
Sau khi xóa file `data.txt`, cấu trúc thư mục hiện tại là
```
mainFolder/
  folderA/ (vị trí hiện tại)
    main.py
  folderB/
    image.png
```

Khi thực thi file `main.py` với nội dung
```py
# the first edit: create a new file data.txt and write 2 lines into it
with open('data.txt', 'w') as f: # line 1
    f.write('mim\npython')       # line 2

# the second edit: append content to the existing file, not overwrite it
with open('data.txt', 'a') as f: # line 3
    f.write('2022')              # line 4
```
ta thu được file `data.txt` trong thư mục `folderA` với nội dung
```
mim
python2022
```

Một số câu hỏi liên quan

1. Giả sử file `data.txt` đã tồn tại từ trước. Hỏi trong đoạn code bên trên, nội dung hiện có sẽ bị mất khi chương trình thực thi tới dòng 1 (câu lệnh `with`) hay khi tới dòng 2 (câu lệnh `f.write`)?

2. Chuyện gì sẽ xảy ra nếu ta chạy dòng 3 và dòng 4, bỏ qua dòng 1 và dòng 2? Tức là sử dụng tham số `a` trong cấu trúc `with open` khi file chưa tồn tại.

Một vài bình luận về việc tạo file

1. Khi sử dụng câu lệnh `open(fileName, 'w')`, nội dung có từ trước trong file `fileName` **sẽ bị mất**.

2. Một tình huống sử dụng tính năng viết bổ sung vào một file có sẵn (`with open(fileName, 'a')`) là khi cập nhật log trong quá trình hoạt động của một chương trình.

3. Khi viết nội dung vào một file, ta thường dùng hàm `join()` để viết nhiều dòng dữ liệu trong cùng một câu lệnh.
```py
with open('data.txt', 'w') as f:
    dataList = ['fire', 'water', 'wood', 'metal', 'earth']
    f.write('\n'.join(dataList))
```

## 4. Tạo thư mục
Khi thực thi file `main.py` chứa nội dung dưới đây

```py
path = 'subFolder/newData.txt'
with open(path, 'w') as f:
    f.write('MIM')
```

ta nhận được thông báo lỗi
```
FileNotFoundError: [Errno 2] No such file or directory: 'subFolder/newData.txt'
```

Sở dĩ có lỗi này là do thư mục (dự kiến sẽ) chứa file ta định tạo, thư mục `subFolder`, chưa tồn tại. Ta phải tạo thư mục này trước khi tạo file trong đó. Có ít nhất ba cách thực hiện công việc này

1. Lệnh `mkdir` trên Linux. Có thể tham khảo câu lệnh `tldr mkdir` để nắm được hướng dẫn sử dụng của lệnh này.

2. Thư viện `os` trong Python
```py
import os
folderName = 'example_directory/subFolder/subSubFolder'
os.makedirs(folderName, exist_ok = True)
```

3. Thư viện `pathlib` trong Python
```py
from pathlib import Path
folderName = 'example_directory/subFolder/subSubFolder'
folder = Path(folderName)
folder.mkdir(exist_ok = True)
```
Thông thường, ta tạo một `Path` instance là file cần tạo rồi sử dụng `filePath.parent` để biết cha của file đang xét.
```py
filePath = Path('subFolder/newData.txt')
parentFolder = filePath.parent
parentFolder.mkdir(exist_ok = True)
```

> Nội dung trên chỉ là tóm tắt, học viên cần đọc các tài liệu liệt kê trong phần tài liệu tham khảo dưới đây.

## Tài liệu tham khảo
Tài liệu chính
- PythonCrashCourse (trang 183-193)

Tài liệu bổ sung
- [Bài viết về xử lý file](https://realpython.com/working-with-files-in-python/) trên trang web Real Python
- [Bài viết về thư viện pathlib](https://realpython.com/python-pathlib/) trên trang web Real Python
