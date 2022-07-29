---
title: "Bài tập tuần 4"
permalink: /pythonSummerCourse/week-04-assignment/
last_modified_at: 2022-07-27
redirect_from:
  - /theme-setup/
toc: false
---


**Danh sách bài tập tuần 4 đang được cập nhật.**

Bài tập tuần 4 gồm .. bài tập, bao gồm
- .. bài tập cơ bản: ... (làm tối thiểu .. bài).
- .. bài tập nâng cao: ... .


## Danh sách bài tập

**Bài tập 1.** (sort a list) \
Một list được gọi là _ổn_ nếu nó chỉ chứa các số thực và có ít nhất một phần tử. Cho một list gồm các list con _ổn_. Viết một chương trình sắp xếp list này theo thứ tự tăng dẫn của tổng các số trong mỗi list con. Ví dụ:
```py
A = [[1,2], [3,0,4], [2], [4,5]] # input
B = [[2], [1,2], [3,0,4], [4,5]] # output
```
Yêu cầu bổ sung: đặt ra thêm tiêu chí để so sánh hai list _ổn_ bất kỳ và áp dụng tiêu chí này để sắp xếp list đầu vào.

**Bài tập 2.** (class Point) \
Ta xây dựng class `Point` để biểu diễn các điểm trong mặt phẳng tọa độ $Oxy$.

1. Thiết kế phần khởi tạo của class `Point` (chọn tên thuộc tính phù hợp) và khởi tạo một số instance của class này.

2. Viết method `distance()` thuộc class `Point` để tính khoảng cách Euclid (hay còn gọi là chuẩn L2) giữa hai instance của class `Point`.

3. Bổ sung tham số `metric` (nhận giá trị là một `str`) trong method `distance()` vừa viết để tính khoảng cách giữa hai điểm theo một trong hai metric: khoảng cách Euclid (chuẩn L2) hoặc khoảng cách Manhattan (chuẩn L1). Dưới đây là cách sử dụng hàm
  ```py
  distL1 = pointA.distance(pointB, metric = 'L1')
  distL2 = pointA.distance(pointB, metric = 'L2')
  ```

4. Viết một method để tạo một điểm đối xứng với một điểm cho trước qua gốc tọa độ. Thực hiện yêu cầu trên bằng ba cách khác nhau:
  - Cách 1. Viết một hàm tách biệt so với class `Point`, nhận vào một instance của class `Point` và trả về một instance mới.
  - Cách 2. Viết một hàm thuộc class `Point` để có thể sử dụng hàm bằng cách viết (ví dụ như) `pointA.getSomething()`.
  - Cách 3. Cũng thực hiện như cách 2, nhưng trong nội dung hàm **không có** chữ `Point`. Gợi ý: sử dụng một thuộc tính _ẩn_ của `self`.

5. Bổ sung `__repr__()` cho class `Point`.

Viết class `Point` và những hàm liên quan thỏa mãn yêu cầu trên, rồi trình bày các ví dụ minh họa cho đoạn code vừa viết **trong một khối `if __name__ == '__main__'`:** ví dụ như:

```py
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y
        return None

if __name__ == '__main__':
    pointA = Point(4, 2)
```
