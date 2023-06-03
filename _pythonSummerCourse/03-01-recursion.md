---
title: "Bài 6. Vòng lặp"
permalink: /pythonSummerCourse/week-03-loops/
last_modified_at: 2023-06-04
redirect_from:
  - /theme-setup/
toc: false
---

_Tác giả: Đặng Quý Anh_

## Nội dung kiến thức
- Các loại vòng lặp trong Python
- Dữ liệu lồng nhau (`list` của các `list`) và vòng lặp lồng nhau
- Hàm `enumerate` và `zip` trong Python

## 1. Vòng lặp `for`
Vòng lặp `for` ở trong Python có tác dụng duyệt qua các biến dữ liệu có trong `list, tuple, string, ...` Sử dụng cú pháp như sau
```python
for element in data:
    # Your code
```
trong đó, `element` là các thành phần trong dữ liệu `data`.
Cụ thể, với kiểu dữ liệu `list`
```python
gradeList = ['K63', 'K64', 'K65', 'K66']
for gradeName in gradeList:
    print(gradeName)

# > Output:
# K63
# K64
# K65
# K66
```
Ngoài ra, ta cũng có thể truy vào các thành phần của dữ liệu cần lặp thông qua chỉ số của các thành phần đấy với hàm `range`
```python
gradeList = ['K63', 'K64', 'K65', 'K66']
n = 4 # length of gradeList
for index in range(n):
    print(gradeList[index])

# > Output:
# K63
# K64
# K65
# K66
```
**Lưu ý:**
- `range(start, end, step)` là một hàm trong `Python`, đầu vào nhận các **số nguyên** và trả về một chuỗi các giá trị **số nguyên** từ `start` tới `end-1`, và cách nhau `step` đơn vị.
Ở phần code trên, ta sử dụng `range(n)` là đang mặc định `start=0, step=1`.
- Chỉ số `index` trong `Python` bắt đầu từ `0`.


## 2. Vòng lặp `while`
Cấu trúc của vòng lặp `while` trong `Python` sẽ như sau
```python
while condition:
    # statement
```
Ví dụ
```python
gradeList = ['K63', 'K64', 'K65', 'K66']
n = 4 # length of gradeList
index = 0 # started index
while index < n:
    print(gradeList[index])
    index = index + 1 # update index for stopped condition (or index += 1)

# > Output:
# K63
# K64
# K65
# K66
```
Một lưu ý khi dùng vòng `while` là ta cần kiểm soát được điều kiện dừng, để tránh  hiện tượng rơi vào `vòng lặp vô hạn`.


## 3. Vòng lặp với `break` và `continue`
`break` và `continue` là hai câu lệnh hỗ trợ trong các vòng lặp để
- `break`: nếu gặp câu lệnh này, quá trình lặp lập tức bị dừng
- `continue`: nếu gặp câu lệnh này, quá trình lặp sẽ bỏ qua vòng lặp hiện tại, và chuyển tới vòng lặp tiếp theo, để tiếp tục thực hiện lặp

Dưới đây là ví dụ minh họa
```python
gradeList = ['K63', 'K64', 'K65', 'K66']
n = 4   # length of gradeList
for index in range(n):
    if index == 1:  # don't print K64, go to next loop
        continue
    if index == 3:  # stop program if index is 3
        break
    print(gradeList[index])

# > Output:
# K63
# K65
```
Ở trên, khi gặp `index == 1` (tức tại phần tử `K64`), ta dùng lệnh `continue` nên chương trình sẽ bỏ qua vòng lặp này, chuyển tới vòng lặp tiếp theo (nên không in ra phần tử `K64`).
Khi gặp `index == 3`, chương trình hiểu sẽ phải dừng ngay quá trình lặp, nên phần tử `K66` cũng không được in ra.


## 4. Dữ liệu lồng nhau (`list` của các `list`)
Kiểu dữ liệu `list` trong `Python` ngoài chứa được các thành phần có kiểu dữ liệu nguyên thủy như `string, int, float, boolean` thì còn có thể chứa được chính các kiểu dữ liệu
nâng cao hơn như `list, dict, tuple, ...` Ví dụ
```python
mixedList = [['K63', 'K64'], True, 2, (3, 3), ['MAT', 'PHY']]
```
Ở ví dụ trên, ta có một danh sách hỗn hợp `mixedList` chứa các thành phần có các kiểu dữ liệu bao gồm: `list, boolean, int, tuple`.
Chẳng hạn, ta muốn in ra các thành phần có kiểu dữ liệu `list`
```python
for element in mixedList:
    if type(element) is list:
        print(element)

# > Output:
# ['K63', 'K64']
# ['MAT', 'PHY']
```
**Lưu ý:** `type(variable)` là một hàm trả về kiểu dữ liệu của biến `variable`.


## 5. Vòng lặp lồng nhau
Bên cạnh sử dụng các vòng lặp một cách đơn lẻ, ta có thể kết hợp sử dụng các vòng lặp lồng nhau. Chẳng hạn, ta có `list` sau
```python
numberList = [1, 2, 3]
```
Để in ra các cặp chỉnh hợp gồm 2 phần tử của `numberList`, ta sẽ dùng các vòng lặp lồng nhau
```python
for firstE in numberList:
    for secondE in numberList:
        if firstE != secondE:
            print(firstE, secondE)

# > Output:
# 1 2
# 1 3
# 2 1
# 2 3
# 3 1
# 3 2
```


## 6. Thư viện `itertools`
Thư viện `itertools` là một công cụ cung cấp các chức năng khác nhau hoạt động trên các trình vòng lặp để tạo ra các trình vòng lặp phức tạp.
Vì thế, ta có thể sử dụng `itertools` để sinh ra các chỉnh hợp 2 phần tử như ở mục **5.** bằng cách
```python
import itertools

numberList = [1, 2, 3]
permutationList = itertools.permutations(numberList, 2)
for element in permutationList:
    print(element)

# > Output:
# (1, 2)
# (1, 3)
# (2, 1)
# (2, 3)
# (3, 1)
# (3, 2)
```
Ngoài hàm tạo ra chỉnh hợp của một tập hơp, `itertools` còn cung cấp các hàm
- `combinations(iterable, r)`: tạo ra tất cả các tổ hợp gồm `r` phần tử từ đối tượng `iterable`
- `product(iterable1, iterable2, ...)`: tạo ra tất cả các phần tử của tích `Cartesian` từ các đối tượng `iterable1, iterable2, ...`
- ...


## 7. Hàm `enumerate` và `zip` trong `Python`
- Hàm `enumerate` trong `Python` thêm vào một bộ đếm trước đối tượng lặp với cú pháp
```
enumerate(iterable, start)
```
trong đó, `iterable` là một đối tượng có thể lặp như `list`, `start` là một số nguyên để bắt đầu bộ đếm, và mặc định là `start = 0`. Ví dụ

```python
for index, gradeName in enumerate(gradeList):
    print(index, gradeName)

# > Output:
# 0 K63
# 1 K64
# 2 K65
# 3 K66
```

- Hàm `zip` trong `Python`, cung cấp một phương thức để nhóm các phần tử có cùng vị trí của các đối tượng lặp, và trả về là một `iterator` dạng danh sách,
mỗi phần tử trong danh sách là một `tuple`. Cú pháp
```python
zip(iterable1, iterable2, ...)
```
trong đó `iterableX (X=1, 2, ...)` là các đối tượng có thể lặp như `string, list, tuple`. Và
    - Nếu không có tham số nào được truyền, `zip()` trả về một iterator rỗng.
    - Nếu tham số được truyền chỉ có duy nhất một iterable, `zip()` trả về tuple có 1 phần tử.
    - Nếu tham số được truyền có nhiều iterable và độ dài của các iterable không bằng nhau, zip sẽ tạo các tuple có độ dài bằng với số iterable nhỏ nhất.

Ví dụ về hàm `zip`:
```python
indexList = [0, 1, 2, 3]
gradeList = ['K63', 'K64', 'K65', 'K66']

for index, gradeName in zip(indexList, gradeList):
    print(index, gradeName)

# > Output:
# 0 K63
# 1 K64
# 2 K65
# 3 K66
```


> Nội dung trên chỉ là tóm tắt, học viên cần đọc các tài liệu liệt kê trong phần tài liệu tham khảo dưới đây.

## Tài liệu tham khảo
Tài liệu chính
- PythonCrashCourse (trang 49-51, 53-56)
- SeriousPython (trang 162-163)
- ThinkPython (trang 75-85)
- Bài viết về [`enumerate`](https://realpython.com/python-enumerate/) và [`zip`](https://realpython.com/python-zip-function/) trên trang web Real Python

Tài liệu bổ sung
- Thư viện [itertools](https://docs.python.org/3/library/itertools.html)
