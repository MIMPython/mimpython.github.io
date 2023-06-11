---
title: "Bài tập lần 4"
permalink: /pythonSummerCourse/module-04-assignment/
last_modified_at: 2023-06-11
redirect_from:
  - /theme-setup/
toc: false
---

Bài tập lần 4 gồm 8 bài tập, bao gồm
- 5 bài tập cơ bản: 1, 2, 3, 4, 5 (làm tối thiểu 3 bài).
- 3 bài tập nâng cao: 6, 7, 8.


## Danh sách bài tập

**Bài tập 1.** (sort a list) \
Một list được gọi là _ổn_ nếu nó chỉ chứa các số thực và có ít nhất một phần tử. Cho một list gồm các list con _ổn_. Viết một chương trình sắp xếp list này theo thứ tự tăng dẫn của tổng các số trong mỗi list con. Ví dụ:
```py
A = [[1,2], [3,0,4], [2], [4,5]] # input
B = [[2], [1,2], [3,0,4], [4,5]] # output
```
Yêu cầu bổ sung: đặt ra thêm tiêu chí để so sánh hai list _ổn_ bất kỳ và áp dụng tiêu chí này để sắp xếp list đầu vào.

**Bài tập 2.** (class Point) \
Xây dựng class `Point` để biểu diễn các điểm trong mặt phẳng tọa độ $Oxy$.

1. Thiết kế phần khởi tạo của class `Point` (chọn tên thuộc tính phù hợp) và khởi tạo một số instance của class này.

2. Viết hàm `distance()` thuộc class `Point` để tính khoảng cách Euclid (hay còn gọi là chuẩn L2) giữa hai instance của class `Point`.

3. Bổ sung tham số `metric` (nhận giá trị là một `str`) trong hàm `distance()` vừa viết để tính khoảng cách giữa hai điểm theo một trong hai metric: khoảng cách Euclid (chuẩn L2) hoặc khoảng cách Manhattan (chuẩn L1). Dưới đây là ví dụ cách sử dụng hàm
  ```py
  distL1 = pointA.distance(pointB, metric='L1')
  distL2 = pointA.distance(pointB, metric='L2')
  ```

4. Viết một method để tạo một điểm đối xứng với một điểm cho trước qua gốc tọa độ. Thực hiện yêu cầu này bằng một trong ba cách dưới đây:
- Cách 1. Viết một hàm tách biệt so với class `Point`, nhận vào một instance của class `Point` và trả về một instance mới.
- Cách 2. Viết một hàm thuộc class `Point` để có thể sử dụng hàm bằng cách viết (ví dụ như) `pointA.getSomething()`.
- Cách 3. Cũng thực hiện như cách 2, nhưng trong nội dung của hàm này **không có** chữ `Point`. Gợi ý: sử dụng thuộc tính `self.__class__`.

5. Bổ sung hàm `__repr__()` cho class `Point`.

Đoạn code dưới đây minh họa một phần lời giải của bài tập này.

```py
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y
        return None

if __name__ == '__main__':
    pointA = Point(4, 2)
    print(pointA)
```

**Bài tập 3.** (class Line) \
Xây dựng class `Line` để biểu diễn các đường thẳng trong mặt phẳng $Oxy$ dựa theo những câu hỏi/yêu cầu dưới đây.

(a) Vì sao phương trình đường thẳng có dạng $y = ax + b$ với $a, b$ là hai tham số bất kỳ không phải là phương trình tổng quát của một đường thẳng trong mặt phẳng $Oxy$? Đường thẳng nào không biểu diễn được qua phương trình này?

(b) Xét phương trình $ax + by + c = 0$ với $a, b, c$ là ba tham số bất kỳ. Tìm điều kiện của ba tham số $a, b, c$ để phương trình này là phương trình tổng quát của một đường thẳng trong mặt phẳng $Oxy$.

(c) Phần khởi tạo của class `Line` có thể được viết như sau
```py
class Line:
    def __init__(self, a, b, c):
        self.a = a
        self.b = b
        self.c = c
```
Nhận xét đoạn code trên.

(d) Viết một phương thức trong class `Line` để xác định (những) giao điểm của hai đường thẳng (nếu có), đồng thời tự quyết định kiểu dữ liệu trả về của phương thức này.

**Bình luận**
- Về mặt toán học, có tất cả ba trường hợp có thể xảy ra khi xét đến giao điểm của hai đường thẳng:
  + Trường hợp 1: hai đường thẳng không có giao điểm
  + Trường hợp 2: hai đường thẳng có duy nhất một giao điểm
  + Trường hợp 3: hai đường thẳng trùng nhau, có vô số giao điểm

- Với ba trường hợp có thể xảy ra kể trên, có hai cách thiết kế dữ liệu trả về của phương thức này:

  Cách cơ bản
  + Trường hợp 1: trả về một tuple rỗng
  + Trường hợp 2: trả về một tuple có một phần tử là một giao điểm với kiểu dữ liệu `Point`
  + Trường hợp 3: trả về một giá trị phù hợp nào đó

  Cách nâng cao (liên quan đến cấu trúc `try-except`)
  + Trường hợp 1: `raise ValueError('no roots')`
  + Trường hợp 2: trả về một giao điểm với kiểu dữ liệu `Point`
  + Trường hợp 3: `raise ValueError('infinite roots')`

(e) Viết một method trong class `Line` để xác định khoảng cách giữa một điểm và một đường thẳng.

(f) Biết rằng có duy nhất một đường thẳng đi qua hai điểm phân biệt cho trước. Viết một method trong class `Line` để khởi tạo một đường thẳng (là một instance của class `Line`) với tham số đầu vào là hai instance của class `Point`. *Gợi ý:* Sử dụng `@classmethod`


**Bài tập 4.** (triangle area) \
Một điểm nguyên trên mặt phẳng $Oxy$ là một điểm có tung độ và hoành độ đều là các số nguyên. Cho ba điểm nguyên $A, B, C$ trên mặt phẳng. Tính diện tích của tam giác (có thể suy biến) $ABC$.

**Bình luận**
- Có ít nhất ba cách để thực hiện bài tập này.
- Có thể cần import class `Point`, class `Line` để thực hiện bài tập này. Câu lệnh cần dùng thường có dạng
  ```py
  from yourFileWithClassPoint import Point
  from yourFileWithClassLine import Line
  ```
  Việc import này chính là lý do cần đặt phần code kiểm thử hai class trên (ở những bài tập trên) vào trong cấu trúc `if __name__ == '__main__'`.


**Bài tập 5.** (Morse code) \
Nên làm gì khi nhận được đoạn [mã Morse](https://en.wikipedia.org/wiki/Morse_code) dưới đây
```
.- .-.. .-.. .. .-- .- -. - - --- ... .- -.-- .. ... -.. --- - -.. --- - ... .--. .- -.-. . -.. --- - -.. .- ... .... -.. --- - -.. --- - ... .--. .- -.-. . -.. .- ... .... -.. .- ... .... -.. .- ... .... ... .--. .- -.-. . -.. --- - -.. --- - -.. --- - -.. .- ... .... ... .--. .- -.-. . -.. --- - ... .--. .- -.-. . -.. .- ... .... -.. --- - -.. .- ... .... -.. .- ... .... ... .--. .- -.-. . -.. .- ... .... -.. .- ... .... -.. .- ... .... ... .--. .- -.-. . -.. --- - -.. --- - -.. .- ... ....
```

**Bài tập 6.** (class Circle) \
Xây dựng class `Circle` để biểu diễn các đường tròn trong mặt phẳng $Oxy$. Khởi tạo với các thuộc tính thích hợp đồng thời cài đặt những thuộc tính, property thích hợp. Tham khảo cách thiết kế trong [the geometry module for SymPy package](https://docs.sympy.org/latest/modules/geometry/index.html).


**Bài tập 7.** (class Datetime) \
Xây dựng class `Datetime` cho phép thực hiện các tác vụ liên quan đến thời gian. Tham khảo `pandas.Timestamp` để nắm được những thuộc tính/phương thức cơ bản của class cần cài đặt.

**Bài tập 8.** (factorial number) \
Cho $n$ là một số tự nhiên, ta định nghĩa $n!$ là tích của $n$ số nguyên dương đầu tiên với quy ước $0! = 1$. Ví dụ $5!=120$. \
(a) Hỏi $n!$ có bao nhiêu chữ số 0 ở tận cùng bên phải? \
(b) Tạo một số mới bằng cách bỏ tất cả chữ số 0 ở tận cùng bên phải của $n!$. Hỏi chữ số tận cùng bên phải của số mới này bằng bao nhiêu?
