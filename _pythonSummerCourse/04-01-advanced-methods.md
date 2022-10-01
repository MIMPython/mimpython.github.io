---
title: "Bài 9. Thiết kế phương thức nâng cao"
permalink: /pythonSummerCourse/week-04-advanced-methods/
last_modified_at: 2022-07-29
redirect_from:
  - /theme-setup/
toc: false
---

_Tác giả: Trần Thanh Tùng_

## 1. Arguments

### 1.1. Positional arguments
Phải thống nhất về thứ tự và số lượng với các tham số được khai báo trong định nghĩa hàm.
```py
def describeChampion(name, health, mana, ultSkill):
    print(f'{name} is a champion in League of Legends with {health} HP and {mana} MP')
    print(f'Ultimate skill of {name} is {ultSkill}')

describeChampion('Yasuo', 650, 0, 'Last breath')
"""
Output:
  Yasuo is a champion in League of Legends with 650 HP and 0 MP
  Ultimate skill of Yasuo is Last breath
"""
describeChampion(650, 0, 'Yasuo', 'Last breath')
"""
Output:
  650 is a champion in League of Legends with Yasuo HP and 0 MP
  Ultimate skill of 650 is Last breath
"""
```

### 1.2. Keyword arguments
Phải thống nhất số lượng tham số được khai báo, nhưng chúng có thể được chỉ định theo thứ tự tùy ý.
```py
describeChampion(name='Yasuo', health=650, mana=0, ultSkill='Last breath')
"""
Output:
  Yasuo is a champion in League of Legends with 650 HP and 0 MP
  Ultimate skill of Yasuo is Last breath
"""

describeChampion(health=650, mana=0, ultSkill='Last breath', name='Yasuo')
"""
Output:
  Yasuo is a champion in League of Legends with 650 HP and 0 MP
  Ultimate skill of Yasuo is Last breath
"""
```

### 1.3. Default value
Gán giá trị mặc định cho các tham số và cho phép bỏ qua các tham số đó khi hàm được gọi.
```py
def describeChampion(name='Yasuo',
                       health=650,
                       mana=0,
                       ultSkill='Last breath'):
    print(f'{name} is a champion in League of Legends with {health} HP and {mana} MP')
    print(f'Ultimate skill of {name} is {ultSkill}')

describeChampion()
"""
Output:
  Yasuo is a champion in League of Legends with 650 HP and 0 MP
  Ultimate skill of Yasuo is Last breath
"""

describeChampion(name='Yone', ultSkill='Fate Sealed')
"""
Output:
  Yone is a champion in League of Legends with 650 HP and 0 MP
  Ultimate skill of Yone is Fate Sealed
"""
```

### 1.4. Argument Tuple Packing
Truyền tất cả tham số vào hàm dưới dạng 1 tuple
```py
def sumOfManyNumbers(*args):
    print(type(args))
    return sum(args)

print(sumOfManyNumbers(1, 2, 3))
"""
Output:
  <class 'tuple'>
  6
"""
numbersList = [1, 2, 3, 4, 5]
print(sumOfManyNumbers(*numbersList))
"""
Output:
  <class 'tuple'>
 15
"""
print(sumOfManyNumbers(1, *numbersList, 5))
"""
Output:
  <class 'tuple'>
  21
"""
```

### 1.5. Argument Dictionary Unpacking
Truyền tất cả tham số vào hàm dưới dạng 1 dictionary. Cách làm này thường được sử dụng ở các thư viện như matplotlib và numpy.
```py
describeYasuo = {'name': 'Yasuo',
                 'health': 100,
                 'mana': 0,
                 'ultSkill': 'Last breath'}
describeChampion(**describeYasuo)
"""
Output:
  Yasuo is a champion in League of Legends with 650 HP and 0 MP
  Ultimate skill of Yasuo is Last breath
"""

def printDictionary(**kwargs):
    for key, val in kwargs.items():
      print(f'{key}: {val}')

printDictionary(a=1, b=2, c=3)
"""
Output:
  a: 1
  b: 2
  c: 3
"""
numberDictionary = {'a': 1, 'b': 2, 'c': 3}
printDictionary(**numberDictionary)
"""
Output:
  a: 1
  b: 2
  c: 3
"""
def printDictionary(a, **kwargs):
    for key, val in kwargs.items():
      print(f'{key}: {val}')

printDictionary(1, b=2, c=3)
"""
Output:
  b: 2
  c: 3
"""
```

## 2. Lambda calculus
Thường dùng với những hàm đơn giản
```py
# Example lambda
square = lambda x: x**2
print(square(2)) # 4

describeChampion = lambda name, ultSkill: f'Ultimate skill of {name} is {ultSkill}'
print(describeChampion('Yasuo', 'Last breath'))
"""
Output:
  Ultimate skill of Yasuo is Last breath
"""


# Arguments
describeChampion = lambda name, ultSkill='Last breath': f'Ultimate skill of {name} is {ultSkill}'
print(describeChampion('Yasuo'))
"""
Output:
  Ultimate skill of Yasuo is Last breath
"""
print(describeChampion(name='Yasuo'))
"""
Output:
  Ultimate skill of Yasuo is Last breath
"""
sumOfManyNumbers = lambda *args: sum(args)
print(sumOfManyNumbers(1, 2, 3)) # 6

sumOfManyNumbers = lambda **kwargs: sum(kwargs.values())
print(sumOfManyNumbers(a=1, b=2, c=3)) # 6
```

## 3. Sorting
```py
# sort()
# Ascending
numbersList = [3, 6, 1, -2, 7, 9, -6]
numbersList.sort()
print(numbersList) # [-6, -2, 1, 3, 6, 7, 9]
# Descending
numbersList = [3, 6, 1, -2, 7, 9, -6]
numbersList.sort(reverse= True)
print(numbersList) # [9, 7, 6, 3, 1, -2, -6]
# Sort by function
numbersList = [3, 6, 1, -2, 7, 9, -6]
numbersList.sort(key=lambda x: x**2)
print(numbersList) # [1, -2, 3, 6, -6, 7, 9]


# sorted()
# Ascending
numbersList = [3, 6, 1, -2, 7, 9, -6]
sortedNumbersList = sorted(numbersList)
print(numbersList) # [3, 6, 1, -2, 7, 9, -6]
print(sortedNumbersList) # [-6, -2, 1, 3, 6, 7, 9]
# Descending
numbersList = [3, 6, 1, -2, 7, 9, -6]
sortedNumbersList = sorted(numbersList, reverse=True)
print(numbersList) # [3, 6, 1, -2, 7, 9, -6]
print(sortedNumbersList) # [9, 7, 6, 3, 1, -2, -6]
# Sort by function
numbersList = [3, 6, 1, -2, 7, 9, -6]
sortedNumbersList = sorted(numbersList, key=lambda x: x**2)
print(numbersList) # [3, 6, 1, -2, 7, 9, -6]
print(sortedNumbersList) # [1, -2, 3, 6, -6, 7, 9]
```

> Nội dung trên chỉ là tóm tắt, học viên cần đọc các tài liệu liệt kê trong phần tài liệu tham khảo dưới đây.

## Tài liệu tham khảo
Tài liệu chính
- PythonCrashCourse (trang 130-136)
- ThinkPython (trang 232)
- [Bài viết về hàm `lambda`](https://realpython.com/python-lambda/) trên trang web Real Python
- [Bài viết về định nghĩa hàm/phương thức](https://realpython.com/defining-your-own-python-function/) trên trang web Real Python. Đặc biệt là hai mục **Argument Tuple Unpacking** và **Argument Dictionary Packing**

Tài liệu bổ sung
- Bài viết về nguyên lý [EAFP](https://blogs.msdn.microsoft.com/pythonengineering/2016/06/29/idiomatic-python-eafp-versus-lbyl/) (It’s Easier to Ask for Forgiveness than Permission)
- Đọc thêm: bài viết về [Single Responsibility Principle](https://dev.to/wemake-services/enforcing-single-responsibility-principle-in-python-2il8) trong Python
