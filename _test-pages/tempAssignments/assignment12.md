# Matplotlib và biểu diễn dữ liệu

**1.** Cho các file dữ liệu *.vrptw và *.sol tương ứng chứa thông tin của các khách hàng và lịch trình di chuyển của đội xe phục vụ (giao hàng) các khách hàng đó.

Quan tâm tới các thông tin cơ bản

$\qquad$ (•) CAPACITY: tổng lượng hàng mỗi xe có.

$\qquad$ (•) SERVICE_TIME: thời gian xe dừng lại phục vụ tại mỗi khách hàng.

$\qquad$ (•) NODE_COORD_SECTION: thông tin về tọa độ của mỗi khách hàng.

$\qquad$ (•) DEMAND_SECTION: Nhu cầu hàng cần cung cấp tại mỗi khách hàng.

$\qquad$ (•) TIME_WINDOW_SECTION: Khung thời gian có thể phục vụ của mỗi khách hàng.

```txt
# vehicle 01
1 6 4 8 9 11 12 10 7 5 3 2 76 1
180 14 59.6181 # (total demand, number of customers, length of this route)

```
<center> Listing 1: Lịch trình di chuyển của 1 xe </center>

*Xe xuất phát từ điểm 1 (là kho), với tổng lượng hàng trên xe (CAPACITY), lần lượt giao hàng cho các khách hàng có số thứ tự là 6, 4, . . . , 76 và về lại 1.*

$\qquad$ (a) Hãy biểu diễn các khách hàng trên mặt phẳng.

$\qquad$ (b) Biểu diễn hành trình của mỗi xe trong đội xe trên mặt phẳng.

$\qquad$ (c) Với mỗi xe, kiểm tra lại các thông tin về tổng lượng hàng mỗi xe đã giao, số lượng khách hàng xe đã phục vụ, và tổng quãng đường xe đã đi.

$\qquad$ (d) Với mỗi khách hàng xe đã phục vụ, biểu diễn các thông tin

$\qquad$ $\qquad$ (•) Tọa độ của khách hàng.

$\qquad$ $\qquad$ (•) Số thứ tự của khách hàng trên hành trình của xe.

$\qquad$ $\qquad$ (•) Lượng hàng xe cần phục vụ.

$\qquad$ $\qquad$ (•) Thời gian xe dừng lại phục vụ.

$\qquad$ $\qquad$ (•) Thời điểm xe đến nơi, thời điểm xe bắt đầu phục vụ, thời điểm xe rời đi sau khi đã phục vụ *(Lấy gốc thời gian xe xuất phát từ kho là 0, độ dài quãng đường xe đã đi, tính theo khoảng cách Euclid là thời gian xe cần để đi hết quãng đường đó. Chú ý, nếu xe đến chỗ khách hàng sớm hơn thời điểm có thể phục vụ khách hàng, xe sẽ phải đợi tới thời điểm mở cửa để bắt đầu phục vụ)*.

$\qquad$ $\qquad$ (•) Số thứ tự của xe đã phục vụ.

$\qquad$ $\qquad$ Riêng với kho, thể hiện thông tin về thời điểm mỗi xe trở lại sau khi đã hoàn thành phục vụ các khách hàng.

$\qquad$ (e) Thêm tùy chỉnh để chỉ hiển thị lịch trình của 1 xe, của xe thứ $k$, hoặc của một số xe.

Gợi ý: Dùng Hover Labels.

**2.** Trong file allocate_land_use.txt chứa ma trận với các giá trị trong ma trận là 0, 1 và 2. Ma trận này lưu trữ thông tin phân lô của một khu đất cỡ 20 × 20 (chia nhỏ thành các ô, thửa); các giá trị 0, 1 và 2 tương ứng lô đất thuộc quyền sở hữu của ông D, ông Q và ông T. Hãy tìm một cách minh họa trực quan cho việc phân lô trên.


**3.** Sử dụng dữ liệu Canada.xlsx về lượng người nhập cư vào Canada từ 1980 - 2013, hãy thực hiện các yêu cầu sau

$\qquad$ (a) Loại bỏ đi các cột ’AREA’,’REG’,’DEV’,’Type’,’Coverage’.

$\qquad$ (b) Đổi lại tên các cột cho có ý nghĩa,

$\qquad$ $\qquad$ ’OdName’:’Country’, ’AreaName’:’Continent’, ’RegName’:’Region’.

$\qquad$ (c) Vẽ biểu đồ đường minh họa lượng người nhập cư từ Haiti vào Canada qua các năm.

$\qquad$ (d) Vẽ biểu đồ đường so sánh lượng người nhập cư đến từ China và India.

$\qquad$ (e) Sử dụng
```txt
fig = plt.figure() # create figure

ax0 = fig.add_subplot(1, 2, 1) # add subplot 1 (1 row, 2 columns, first plot)
ax1 = fig.add_subplot(1, 2, 2) # add subplot 2 (1 row, 2 columns, second plot).
```
<center>Listing 2: Sử dụng subplot.</center>

$\qquad$ vẽ hai biểu đồ ở ý (c) và (d) trên cùng một hình.

$\qquad$ (f) Vẽ biểu đồ đường (line), diện tích (area) minh họa lượng người nhập cư của 5 quốc gia đứng đầu về nhập cư vào Canada trong giai đoạn trên.

$\qquad$ (g) Vẽ biểu đồ cột (bar), minh họa cho lượng người nhập cư từ Iceland.

$\qquad$ (h) Vẽ biểu đồ tròn (pie), minh họa cho lượng người nhập cư theo mỗi khu vực.

$\qquad$ (i) Sử dụng các tùy chỉnh sau để biểu đồ tròn ở ý (h) được minh họa theo cách khác. Giải thích ý nghĩa của mỗi tùy chỉnh.

```txt
#change color list
colors_list = ['gold', 'yellowgreen', 'lightcoral', 'lightskyblue',
				'lightgreen', 'pink']
# some options
labels = None,
pctdistance = 1.12,
colors = colors_list,
explode = explode_list
```

<center>Listing 3: Một số tùy chỉnh cho biểu đồ tròn.</center>


# Additional Problems
**4.** *Coin tossing simulation*

Hãy viết chương trình mô phỏng việc tung (nhiều lần) một đồng xu *công bằng*. Vẽ hình thể hiện số mặt sấp và số mặt ngửa trong quá trình tung đồng xu. Đưa ra kết luận về mối quan hệ giữa số mặt sấp và số mặt ngửa khi tung đồng xu này.

Một số câu hỏi thêm.

$\qquad$ (a) Lưu những hình ảnh với một định dạng phù hợp. Hai định dạng phổ biến nhất là *png* và *pdf*, giải thích sự khác nhau giữa hai định dạng này và đưa ra lựa chọn.

$\qquad$ (b) Làm thế nào để đảm bảo tính tái lập (reproducibility) cho kết quả? Cụ thể hơn, cần làm gì để khi thực thi chương trình vẫn thu được kết quả giống với những lần thực thi trước đó.

$\qquad$ (c) How to make a fair coin from a biased coin?

**5.** *(Mandelbrot Set)*

According to [Wikipedia](https://en.wikipedia.org/wiki/Mandelbrot_set), the Mandelbrot set is the set of complex numbers $c$ for which the function $f_{c}(z) = z^2 + c$ does not diverge when iterated from $z = 0$. Illustrate the Mandelbrot set by Python programming language.
