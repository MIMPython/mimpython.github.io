---
title: "Bài 1. Python"
permalink: /pythonSummerCourse/week-01-python/
last_modified_at: 2022-06-30
redirect_from:
  - /theme-setup/
toc: false
---

## Giới thiệu python
- Tải xuống python tại [đây](https://www.python.org/downloads/) và cài đặt.
- Viết chương trình python đầu tiên. Taoj file có nội dung dưới đây và đặt tên là `helloWorld.py`.
    ```py
    print('Hello World!')
    ```
- Chạy chương trình python đầu tiên. Mở terminal và chạy dòng lệnh sau:
    ```sh
    python helloWorld.py
    ```
- Làm quen với biến trong python. Thay vì in ra trực tiếp, hãy gán chuỗi `Hello World` bằng 1 biến và in ra biến đó.
    ```py
    helloWorldString = 'Hello World!'
    print(helloWorldString)
    ```
- Làm quen với số và các phép tính cơ bản trong python.
    ```py
    print(2 + 3) #5
    print(3 - 2) #1
    print(2 * 3) #6
    print(3 / 2) #1.5
    print(3 ** 2) # 9
    ```
## Các lưu ý
- Tên biến nên thể hiện ý nghĩa của biến.
  ```py
  # correct
  numberOfOranges = 2
  numberOfApple = 3
  sumOfOrangesAndApples = numberOfOranges + numberOfApples
  # wrong
  a = 2
  b = 3
  c = a + b
  ```
- Tên biến nên được viết bằng tiếng Anh.
  ```py
  # correct
  numberOfOranges = 2
  numberOfApples = 3
  sumOfOrangesAndApples = numberOfOranges + numberOfApples
  # wrong
  soQuaCam = 2
  soQuaTao = 3
  tongSoCamVaTao = soQuaCam + soQuaTao
  ```
- Thống nhất 1 kiểu cho tên biến.
  ```py
  # camel style
  numberOfOranges = 2
  # snake style
  number_of_oranges = 2
  ```
- Thử chạy chương trình python có nội dung sau:
  ```py
  import this
  ```
## Tài liệu tham khảo
- PythonCrashCourse (trang 3-32, 68-70)
- SeriousPython (trang 14-20)
- ThinkPython (trang 11-19)
- [PEP8](https://peps.python.org/pep-0008/) - a coding style in Python
- [Lời khuyên](https://realpython.com/python-beginner-tips/) dành cho người mới bắt đầu
