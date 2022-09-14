---
title: "Bài tập tuần 8"
permalink: /pythonSummerCourse/week-08-assignment/
last_modified_at: 2022-09-14
redirect_from:
  - /theme-setup/
toc: false
---


Bài tập tuần 8 gồm 7 bài tập, bao gồm
- 5 bài tập cơ bản: 1, 2, 3, 4, 5 (làm tối thiểu 3 bài).
- 2 bài tập nâng cao: 6, 7.


## Danh sách bài tập

**Bài tập 1.** *(documentation/docstrings)* \
Viết một file `.py` trong đó documentation/docstrings được trình bày theo một quy chuẩn tự chọn. Bổ sung type hint nếu có thể.


**Bài tập 2.** *(solving linear equations)* \
Viết một hàm thực hiện giải phương trình tuyến tính $Ax=b$ với $A,b$ lần lượt là ma trận, vector (với kích thước phù hợp) cho trước. So sánh (độ chính xác, thời gian thực thi của) hàm vừa viết với hàm dựng sẵn trong thư viện `numpy`.


**Bài tập 3.** *(DataFrame datetime tricks)* \
a) Tạo một `DataFrame` gồm một nghìn dòng và một cột `timestamp` với giá trị mỗi ô là một thời điểm ngẫu nhiên trong năm 2022. \
b) Bổ sung cột `date` vào `DataFrame` kể trên, trong đó chỉ lưu giá trị ngày tương ứng với giá trị của cột `timestamp`. Tìm cách tối ưu hóa thời gian thực thi công việc này. \
Dưới đây là ví dụ một `DataFrame` thỏa mãn yêu cầu đề bài.

```
## print(df)
              timestamp        date
0   2022-10-25 04:31:49  2022-10-25
1   2022-04-23 02:32:59  2022-04-23
2   2022-08-14 19:01:11  2022-08-14
..                  ...         ...
997 2022-01-24 23:08:03  2022-01-24
998 2022-01-06 15:18:19  2022-01-06
999 2022-11-15 00:45:31  2022-11-15

[1000 rows x 2 columns]

## print(df.dtypes)
timestamp    datetime64[ns]
date                 object
dtype: object
```


**Bài tập 4.** *(DataFrame groupby tricks)* \
a) Tạo ngẫu nhiên một `DataFrame` chứa dữ liệu về điểm trung bình của sinh viên. Dữ liệu cần có tối thiểu ba trường thông tin `name`, `class`, `score`. \
b) Thống kê điểm sinh viên theo từng lớp, trình bày thống kê trong một `DataFrame` với ít nhất ba cột `class`, `nStudents`, `meanScore`.

Dưới đây là một mẫu dữ liệu (được ghi bởi định dạng JSON).

```json
# (a)
{"name":"An","class":"K64","score":7.2}
{"name":"Binh","class":"K65","score":7.3}
{"name":"Chi","class":"K65","score":7.4}
{"name":"Dung","class":"K66","score":7.5}
{"name":"Giang","class":"K67","score":7.6}

# (b)
{"class":"K64","nStudents":1,"meanScore":7.2}
{"class":"K65","nStudents":2,"meanScore":7.35}
{"class":"K66","nStudents":1,"meanScore":7.5}
{"class":"K67","nStudents":1,"meanScore":7.6}
```


**Bài tập 5.** *(Filling missing digits)* \
Điền các số nguyên từ 1 đến 9 vào các chữ cái `A,B,C,D,E,F,G,H,I` dưới đây để thu được một phép tính đúng. Biết rằng các chữ cái khác nhau nhận giá trị khác nhau.

$$A \frac{B}{C} + D \frac{E}{F} = G \frac{H}{I}$$


**Bài tập 6.** *(Longest Collatz sequence)* \
Giải quyết [bài toán 14](https://projecteuler.net/problem=14) trên trang web Project Euler.


**Bài tập 7.** *(bad luck probability)* \
Trong một bộ bài tú lơ khơ tiêu chuẩn (gồm 52 lá bài), một tập hợp có từ ba lá bài trở lên được gọi là một phỏm nếu chúng thỏa mãn một trong hai điều kiện sau:
- ĐK1: chúng có cùng giá trị. Ví dụ bộ ba lá 2 cơ, 2 rô, 2 bích.
- ĐK2: chúng có cùng chất và có giá trị là các số nguyên liên tiếp, với quy ước J, Q, K lần lượt là 11, 12, 13. Ví dụ bộ bốn lá 9 cơ, 10 cơ, J cơ, Q cơ.

Hai lá bài (không kể thứ tự) được gọi là một cạ nếu chúng thuộc một phỏm nào đó. Ví dụ (3 cơ, 3 bích) là một cạ, (9 rô, J rô) là một cạ. Một tập hợp các lá bài được gọi là **ù khan** nếu hai lá bài bất kỳ đều không là một cạ.

Tính xác suất để: \
a) Một tập 9 lá bài rút ngẫu nhiên từ bộ bài là **ù khan**. \
b) Một tập 10 lá bài rút ngẫu nhiên từ bộ bài là **ù khan**. \
c) Bốn tập bài được đồng thời rút ngẫu nhiên từ bộ bài tiêu chuẩn, mỗi tập bài có lần lượt 10, 9, 9, 9 lá và chúng đều **ù khan** (không quan tâm đến trạng thái của 15 lá còn lại trong bộ bài).
