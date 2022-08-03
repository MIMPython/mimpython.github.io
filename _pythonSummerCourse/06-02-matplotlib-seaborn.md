---
title: "Bài 15. matplotlib and seaborn"
permalink: /pythonSummerCourse/week-06-matplotlib-seaborn/
last_modified_at: 2022-08-03
redirect_from:
  - /theme-setup/
toc: false
---


## 1. Thư viện matplotlib 
`matplotlib` là một thư viện được Python cung cấp cho việc trực quan hóa dữ liệu phục vụ cho việc suy luận thống kê.
Và module được phổ biến trong matplotlib là pyplot - chứa các hàm cơ bản để vẽ, thiết lập khung hình.

Dưới đây là một đoạn code minh họa khi sử dụng thư viện matplotlib:
```python 
# import library
import numpy as np
from matplotlib import pyplot as plt

# initialize function
f = lambda x: np.sin(2 * np.pi * x)
g = lambda x: np.cos(2 * np.pi * x)

# split lower bound and upper bound into 1000 range by 1001 points
lb, ub = -2, 2
x = np.linspace(lb, ub, 1001)
y1 = f(x)
y2 = g(x)

# plot
plt.figure(figsize=(15, 10))
plt.plot(x, y1, '--', color='blue', label='sin(x)')
plt.plot(x, y2, '-', color='red', label='cos(x)')
plt.xlabel('x', fontsize=14)
plt.ylabel('y', fontsize=14)
plt.title('Draw sin(x) and cos(x)', fontsize=18)
plt.legend(fontsize=14)
plt.grid()
plt.savefig('demo-matplotlib.png')
plt.show()
```
<div>
    <img src="/assets/images/courses/06-02-matplotlib-seaborn/demo-matplotlib.png"
    style="width:90%;
    max-width:800px;
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding-top:20px;
    padding-bottom:20px;">
</div>
trong đó,
- `plt.figure`: thiết lập kích thước khung hình (view)
- `plt.plot(x, y1, '--', color='blue', label='sin(x)')`: vẽ đồ thị của $y_1$ theo $x$ với nét đứt (`--`), màu xanh và với nhãn là `sin(x)`
- `plt.plot(x, y2, '--', color='red', label='cos(x)')`: vẽ đồ thị của $y_2$ theo $x$ với nét liền (`-`), màu đỏ và với nhãn là `cos(x)`
- `plt.xlabel('x', fontsize=14)`: đặt trên cho trục $x$ với cỡ chữ 14
- `plt.ylabel('y', fontsize=14)`: đặt trên cho trục $y$ với cỡ chữ 14
- `plt.title('Draw sin(x) and cos(x)', fontsize=18)`: đặt tên cho hình vẽ với cỡ chữ 18
- `plt.legend(fontsize=14)`: thiết lập nhãn cho các hàm đã vẽ qua label đã gán ỡ mỗi hàm `plt.plot`
- `plt.grid()`: thiết lập lưới cho miền vẽ 
- `plt.savefig('demo-matplotlib.png')`: để lưu lại hình đã vẽ dưới tên truyền vào
- `plt.show()`: để hiển thị hình vẽ 

Tuy nhiên, ta cũng có thể vẽ hai hàm số $sin(x)$ và $cos(x)$ ở 2 khung hình khác nhau bằng cách sử dụng `plt.subplot`
```python
# import library
import numpy as np
from matplotlib import pyplot as plt

# initialize function
f = lambda x: np.sin(2 * np.pi * x)
g = lambda x: np.cos(2 * np.pi * x)

# split lower bound and upper bound into 1000 range by 1001 points  
lb, ub = -2, 2
x = np.linspace(lb, ub, 1001)
y1 = f(x)
y2 = g(x)

plt.figure(figsize=(20, 10))
# Draw sin(x)
plt.subplot(1, 2, 1)
plt.plot(x, y1, '--', color='blue', label='sin(x)')
plt.xlabel('x', fontsize=14)
plt.ylabel('y', fontsize=14)
plt.title('Draw sin(x)', fontsize=18)
plt.grid()

# Draw cos(x)
plt.subplot(1, 2, 2)
plt.plot(x, y2, '-', color='red', label='cos(x)')
plt.xlabel('x', fontsize=14)
plt.ylabel('y', fontsize=14)
plt.title('Draw cos(x)', fontsize=18)
plt.grid()

# display
plt.show()
```
<div>
    <img src="/assets/images/courses/06-02-matplotlib-seaborn/demo-matplotlib-subplot.png"
    style="width:90%;
    max-width:800px;
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding-top:20px;
    padding-bottom:20px;">
</div>
Các hàm vẽ cơ bản vẫn hoàn toàn như phần trước, nhưng thêm `plt.subplot(m, n, position)` - nghĩa là khung hình sẽ được chia làm $m$ hàng, $n$ cột (tức là có $m \times n$ hình vẽ con), và `postition` là vị trí hình vẽ hiện tại.
Bên cạnh `plt.subplot`, chúng ta cũng có thể dùng hàm gần tương tự nhưng đa dụng trong nhiều trường hợp hơn là [`plt.subplots`](https://matplotlib.org/stable/gallery/subplots_axes_and_figures/subplots_demo.html).

Ngoài ra, pyplot còn cung cấp các hàm vẽ sau:
- `plt.scatter`: vẽ biểu đồ phân tán 
- `plt.bar`: vẽ biểu đồ cột 
- `plt.boxplot`: vẽ biểu đồ ria mèo 
- `plt.pie`:  vẽ biểu đồ tròn 
- ...


## 2. Thư viện seaborn 
seaborn là mở rộng, kế thừa từ matplotlib, được Python cung cấp để thực hiện trực quan hóa dữ liệu, nhưng thường được dùng với kiểu dữ liệu từ `dataframe`.
seaborn cũng đa dạng các hàm để vẽ hơn và có thể được chia thành một số nhóm chính như sau 
- Nhóm các hàm vẽ quan hệ 
  - `scatterplot`: vẽ biểu đồ phân tán 
  - `lineplot`: vẽ biểu đồ đường
  
- Nhóm các hàm vẽ phân bố
  - `displot`: vẽ phân bố của biến 
  - `histplot`: vẽ biểu đồ `historygrams` của biến 
  - `kdeplot`:  vẽ đường xấp xỉ phân bố của biến 
  
- Nhóm các hàm dành cho biến rời rạc 
  - `boxplot`: vẽ biểu đồ ria mèo 
  - `barplot`: vẽ biểu đồ cột 
  - `countplot`: vẽ biều đồ theo số lượng biến 
  - `swarmplot`: vẽ biểu đồ phân tán phân loại với các điểm không trùng nhau
  
- Ngoài ra, còn có các nhóm: nhóm các hàm vẽ biến hồi quy, nhóm vẽ ma trận, nhóm để vẽ cho nhiều hình, ...

Sau đây là một ví dụ khi dùng `seaborn` kết hợp `matplotlib` trên kiểu dữ liệu `dataframe`.
Dữ liệu dùng trong bài học được lấy từ thư viện `seaborn` (xem chi tiết [tại đây](https://github.com/mwaskom/seaborn-data/blob/master/iris.csv)).

```python 
import seaborn as sns 

# set fontsize 
sns.set(font_scale=1.5)

# load dataframe
iris = sns.load_dataset('iris')

plt.figure(figsize=(20, 20))
# use countplot
plt.subplot(2, 2, 1)
sns.countplot(x='species', data=iris)

# use kdeplot
plt.subplot(2, 2, 2)
sns.kdeplot(x='petal_length', data=iris)

# use boxplot
plt.subplot(2, 2, 3)
sns.boxplot(x='petal_length', data=iris)

# use scatterplot
plt.subplot(2, 2, 4)
sns.scatterplot(x='petal_length', y='petal_width', data=iris)

# display 
plt.show()
```
<div>
    <img src="/assets/images/courses/06-02-matplotlib-seaborn/demo-seaborn.png"
    style="width:90%;
    max-width:800px;
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding-top:20px;
    padding-bottom:20px;">
</div>

> Nội dung trên chỉ là tóm tắt, học viên cần đọc các tài liệu liệt kê trong phần tài liệu tham khảo dưới đây.

## Tài liệu tham khảo
Tài liệu chính 
- Trang chủ [matplotlib](https://matplotlib.org/stable/tutorials/index)
- Trang chủ [seaborn](https://seaborn.pydata.org/api.html)
  
Tài liệu bổ sung 
- [Hướng dẫn sử dụng matplotlib](https://realpython.com/python-matplotlib-guide/) trên trang web Real Python
- SeriousPython (trang 27-32)
