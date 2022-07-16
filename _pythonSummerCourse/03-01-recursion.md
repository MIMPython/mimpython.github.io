---
title: "Bài 6. Vòng lặp"
permalink: /pythonSummerCourse/week-03-loops/
last_modified_at: 2022-06-30
redirect_from:
  - /theme-setup/
toc: false
---

## Nội dung kiến thức
- Các loại vòng lặp trong Python
- Dữ liệu lồng nhau (`list` của các `list`) và vòng lặp lồng nhau

### 1. Vòng lặp `for`
Vòng lặp `for` ở trong Python có tác dụng lặp các biến dữ liệu có trong 
`list` , `tuple`, `string`,... Sử dụng cú pháp như sau
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
    
> Output:
K63
K64
K65
K66
```
Ngoài ra, ta cũng có thể truy vào các thành phần của dữ liệu cần lặp thông qua 
chỉ số của các thành phần đấy với hàm `range`
```python
gradeList = ['K63', 'K64', 'K65', 'K66']
n = 4   # length of gradeList 
for index in range(n):
    print(gradeList[index])
    
> Output:
K63
K64
K65
K66
```
**Lưu ý:** 
- `range(start, end, step)` là một hàm trong `Python`, đầu vào nhận các 
**số nguyên** và trả về một chuỗi các giá trị **số nguyên** từ `start` tới `end-1`, và cách nhau `step`
đơn vị. Ở phần code trên, ta sử dụng `range(n)` là đang mặc định `start=0, step=1`.
  
- Chỉ số `index` trong `Python` bắt đầu từ `0`. 


### 2. Vòng lặp `while`
Cấu trúc của vòng lặp `while` trong `Python` sẽ như sau
```python
while   # condition is satistfied:
    # your code 
```
Ví dụ
```python
gradeList = ['K63', 'K64', 'K65', 'K66']
n = 4   # length of gradeList
index = 0   # started index
while index < n:
    print(gradeList[index])
    index = index + 1   # update index for stopped condition (or index += 1)

> Output:
K63
K64
K65
K66
```
Một lưu ý khi dùng vòng `while` là ta cần kiểm soát được điều kiện dừng, để tránh 
hiện tượng rơi vào `vòng lặp vô hạn`.


### 3. Vòng lặp với `break` và `continue`
`break` và `continue` là hai câu lệnh hỗ trợ trong các vòng lặp để 
- `break`: nếu gặp câu lệnh này, quá trình lặp lập tức bị dừng 
- `continue`: nếu gặp câu lệnh này, quá trình lặp sẽ bỏ qua vòng lặp hiện tại,
và chuyển tới vòng lặp tiếp theo, để tiếp tục thực hiện lặp
  
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
    
> Output:
K63
K65
```
Ở trên, khi gặp `index=1` (tức tại phần tử `K64`), ta dùng lệnh `continue` nên 
chương trình sẽ bỏ qua vòng lặp này, chuyển tới vòng lặp tiếp theo (nên không in ra phần tử `K64`). 
Khi gặp `index = 3`, chương trình hiểu sẽ phải dừng ngay quá trình lặp, nên phần tử `K66` cũng không được in ra. 


### 4. Dữ liệu lồng nhau (`list` của các `list`)
Kiểu dữ liệu `list` trong `Python` ngoài chứa được các thành phần có kiểu dữ liệu 
nguyên thủy như `string, int, float, boolean` thì còn có thể chứa được chính các kiểu dữ liệu 
nâng cao hơn như `list, dict, tuple, ...` Ví dụ
```python
mixedList = [['K63', 'K64'], True, 2, (3, 3), ['MAT', 'PHY']]
```
Ở ví dụ trên, ta có một danh sách hỗn hợp `mixedList` chứa các thành phần có 
các kiểu dữ liệu bao gồm: `list, boolean, int, tuple`. Chẳng hạn, ta muốn in ra 
các thành phần có kiểu dữ liệu `list`
```python
for element in mixedList:
    if type(element) is list:
        print(element)
        
> Output:
['K63', 'K64']
['MAT', 'PHY']
```
**Lưu ý:** `type(variable)` là một hàm trả về kiểu dữ liệu của biến `variable`.


### 5. Vòng lặp lồng nhau
Bên cạnh sử dụng các vòng lặp một cách đơn lẻ, ta có thể kết hợp sử dụng các vòng lặp 
lồng nhau. Chẳng hạn, ta có `list` sau
```python
numberList = [1, 2, 3] 
```
Để in ra các cặp chỉnh hợp gồm 2 phần tử của `numberList`, ta sẽ dùng các vòng lặp lồng nhau
```python
for firstE in numberList:
    for secondE in numberList:
        if firstE != secondE: 
            print(firstE, secondE)
        
> Output:
1 2
1 3
2 1
2 3
3 1
3 2
```


### 6. Thư viện `itertools`
Thư viện `itertools` là một công cụ cung cấp các chức năng khác nhau hoạt 
động trên các trình vòng lặp để tạo ra các trình vòng lặp phức tạp. Vì thế,
ta có thể sử dụng `itertools` để sinh ra các chỉnh hợp 2 phần tử như ở **5.** bằng cách 
```python
import itertools

numberList = [1, 2, 3] 
permutationList = itertools.permutations(numberList, 2)
for element in permutationList:
    print(element)
    
> Output:
(1, 2)
(1, 3)
(2, 1)
(2, 3)
(3, 1)
(3, 2)
```
Ngoài hàm tạo ra chỉnh hợp của một tập hơp, `itertools` còn cung cấp 
các hàm 
- `combinations(iterable, r)`: tạo ra tất cả các tổ hợp gồm `r` phần tử 
từ đối tượng `iterable`
  
- `product(iterable1, iterable2, ...)`: tạo ra tất cả các phần tử của tích `Cartesian` 
từ các đối tượng `iterable1, iterable2, ...`
  
- ...


> Nội dung trên chỉ là tóm tắt, học viên cần đọc các tài liệu liệt kê trong phần tài liệu tham khảo dưới đây.
## Tài liệu tham khảo
- PythonCrashCourse (trang 49-51, 53-56)
- SeriousPython (trang 162-163)
- ThinkPython (trang 75-85)
- Thư viện [itertools](https://docs.python.org/3/library/itertools.html)
