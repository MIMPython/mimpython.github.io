---
title: "Bài 14. numpy and pandas"
permalink: /pythonSummerCourse/week-06-numpy-and-pandas/
last_modified_at: 2022-06-30
redirect_from:
  - /theme-setup/
toc: false
---

## 1. Numpy - thư viện tính toán trong Python

### 1.1. Lợi ích khi sử dụng numpy

- Tốc độ nhanh
- Giảm vòng lặp
- Code rõ ràng hơn
- Tăng chất lượng Code

### 1.2. Cài đặt numpy

```sh
pip install numpy
```

### 1.3. Numpy cơ bản

Khởi tạo 1 numpy array
```py
import numpy as np


# Numpy array
arr = np.array([
            [1, 2, 3],
            [4, 5, 6],
            [6, 7, 9],
            ])
print(arr)
"""
Output:
  [[1 2 3]
   [4 5 6]
   [6 7 9]]
"""
```
Thao tác với numpy array
```py
# Get row
print(arr[0]) # [1 2 3]

# Get column
print(arr[:,0]) # [1 4 6]

# Get element
print(arr[0, 0]) # 1

# Get shape
print(arr.shape) # (3, 3)

# Get size
print(arr.size) # 9
```
Tính toán trên numpy array
```py
# Calculation
# By table
print(arr.sum()) # 43
# By dimension
print(arr.sum(axis=0)) # [11 14 18]
print(arr.sum(axis=1)) # [ 6 15 22]

# Some calculation: sum, max, min, argmin, argmax, mean, var, ...
```
Một số numpy array đặc biệt
```py
# Numpy array with all element equal 0
zerosArr = np.zeros((2, 3), dtype=int)
print(zerosArr)
"""
Output:
[[0 0 0]
 [0 0 0]]
"""

# Numpy array with all element equal 1
onesArr = np.ones((2,3), dtype=int)
print(onesArr)
"""
Output:
[[1 1 1]
 [1 1 1]]
"""
```
Vòng lặp trong numpy array
```py
# Loop through numpy array
arr = np.array([
            [1, 2, 3],
            [4, 5, 6],
            [6, 7, 9],
            ])

for i in range(arr.shape[0]):
    for j in range(arr.shape[1]):
      print(arr[i, j])
"""
Output:
  1
  2
  3
  4
  5
  6
  6
  7
  9
"""

```

## 2. Pandas - thư viện xử lý dữ liệu dạng bảng

### 2.1. Cài đặt pandas
```sh
pip install pandas
```
### 2.2. Pandas cơ bản

Khởi tạo DataFrame
```python
import pandas as pd


# DataFrame
loveDf = pd.DataFrame({
          'I': ['love','you','so','much'],
          'But': ['you','dont','love','me'],
          'So': ['I','am','broken','huhu']})
print(loveDf)
"""
Output:
      I   But      So
0  love   you       I
1   you  dont      am
2    so  love  broken
3  much    me    huhu
"""
```
Lấy dữ liệu cột
```py
# Get column
print(loveDf['I'])
"""
Output:
0    love
1     you
2      so
3    much
Name: I, dtype: object
"""
```
Nên đặt tên cột là một từ tiếng Anh không cách để lấy dữ liệu cột nhanh chóng bằng cách sau:
```py
print(loveDf.But)
"""
Output:
0     you
1    dont
2    love
3      me
Name: But, dtype: object
"""
```
Lấy dữ liệu hàng
```py
# Get row
print(loveDf.iloc[1])
"""
Output:
I       you
But    dont
So       am
Name: 1, dtype: object
"""
```
Thao tác cơ bản với DataFrame
```py
# Get shape
print(loveDf.shape) # (4, 3)

# Add new column
loveDf['And'] = ['I', 'will', 'forget', 'you']
print(loveDf)
"""
Output:
      I   But      So     And
0  love   you       I       I
1   you  dont      am    will
2    so  love  broken  forget
3  much    me    huhu     you
"""

# Change column order
loveDf = loveDf[['I', 'But', 'And', 'So']]
print(loveDf)
"""
Output:
      I   But     And      So
0  love   you       I       I
1   you  dont    will      am
2    so  love  forget  broken
3  much    me     you    huhu
"""

# Read dataframe from file
"""
Example, boysData.csv has the following content:
id, name, age
1, Bob, 10
2, Kenvin, 12
3, Otto, 9
"""
boysDf = pd.read_csv('boysData.csv')
print(boysDf)
"""
Output:
  id    name     age
0  1     Bob      10
1  2  Kenvin      12
2  3    Otto       9
"""

# Save dataframe
boysDf.to_csv('newBoysData.csv', index=False)

# Some kind of file pandas can read and save: .csv, .xlsx, .json, .xml, ...
```

> Nội dung trên chỉ là tóm tắt, học viên cần đọc các tài liệu liệt kê trong phần tài liệu tham khảo dưới đây.

## Tài liệu tham khảo

Tài liệu chính
- Trang chủ [numpy](https://numpy.org/doc/stable/reference/index.html)
- Trang chủ [pandas](https://pandas.pydata.org/docs/reference/index.html#api)

Tài liệu bổ sung
- [Hướng dẫn sử dụng numpy](https://realpython.com/numpy-tutorial/) trên trang web Real Python
- [Hướng dẫn sử dụng pandas](https://realpython.com/pandas-python-explore-dataset/) trên trang web Real Python
