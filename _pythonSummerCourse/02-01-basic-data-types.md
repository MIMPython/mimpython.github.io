---
title: "Bài 4. Các kiểu dữ liệu cơ bản"
permalink: /pythonSummerCourse/week-02-basic-data-types/
last_modified_at: 2023-06-04
redirect_from:
  - /theme-setup/
toc: false
---

_Tác giả: Trần Thanh Tùng_

## 1. Các kiểu dữ liệu cơ bản
String, thao tác cơ bản với string

```python
fruit = 'banana'
letter = fruit[0]
print(letter) # 'b'

# Length of string
print(len(fruit)) # 6

# Slice
print(fruit[0:3]) # ban

# Search
print(fruit.find('a')) # 1
print('a' in fruit) # True
print('c' in fruit) # False
```

List, thao tác cơ bản với list
```python
colors = ['red', 'blue', 'green']
print(colors[1]) # blue

colors[2] = 'yellow'
print(colors) # ['red', 'blue', 'yellow']

# Length of list
print(len(colors)) # 3

# Add element
colors = ['red', 'blue', 'green']
colors.append('blue')
print(colors) # ['red', 'blue', 'green', 'blue']

# Remove element
colors = ['red', 'yellow', 'green', 'blue']
colors.pop(0)
print(colors) # ['yellow', 'green', 'blue']

colors = ['red', 'blue', 'yellow', 'green', 'blue']
colors.remove('blue')
print(colors) # ['red', 'yellow', 'green', 'blue']

# Sort element
colors = ['red', 'yellow', 'green', 'blue']
colors.sort()
print(colors) # ['blue', 'green', 'red', 'yellow']

# Reverse list
colors = ['red', 'yellow', 'green', 'blue']
colors.reverse()
print(colors) # ['blue', 'green', 'yellow', 'red']

# Check element in list
colors = ['red', 'yellow', 'green', 'blue']
print('red' in colors) # True
print('gray' in colors) # False
```

Tuple, thao tác cơ bản với tuple
```python
dimensions = (200, 50)
print(dimensions[0]) # 200

# You can't use
dimensions[0] = 100 # TypeError: 'tuple' object does not support item assignment

# Writing over a Tuple
dimensions = (200, 50)
print(dimensions) # (200, 50)
dimensions = (100, 100)
print(dimensions) # (100, 100)
```

Dictionary, thao tác với dictionary
```python
banana = {'name': 'banana', 'color': 'yellow', 'cost': 5000}
print(banana['cost']) # 5000

# Get key dictionary
print(banana.keys()) # dict_keys(['name', 'color', 'cost'])

# Get value of dictionary
print(banana.values()) # dict_values(['banana', 'yellow', 5000])
```

## 2. Vòng lặp for

```python
# Simple for loop
for i in range(3):
    print(i)
"""
Output:
0
1
2
"""

# Loop through a list
colors = ['red', 'yellow', 'green']
for color in colors:
    print(color)
"""
Output:
red
yellow
green
"""

# Loop through a tuple
path = (2, 5, 4, 1, 3)
for node in path:
    print(node)
"""
Output:
2
5
4
1
3
"""

# Loop thought dictionary
banana = {'name': 'banana', 'color': 'yellow', 'cost': 5000}
for key in banana.keys():
    print(banana[key])
"""
Output:
banana
yellow
5000
"""
```

> Nội dung trên chỉ là tóm tắt, học viên cần đọc các tài liệu liệt kê trong phần tài liệu tham khảo dưới đây.

## Tài liệu tham khảo

Tài liệu chính
- PythonCrashCourse (trang 34-48, 65-68, 91-112)
- ThinkPython (trang 85-95)

Tài liệu bổ sung
- ThinkPython (trang 107-150)
