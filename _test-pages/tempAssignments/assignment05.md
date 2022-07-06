# Dictionaries

**1.** Với dữ liệu tạo được từ ý (b) của bài tập 1 trong Assigment04 (If statement), em hãy thêm tên sinh viên cho mỗi bộ điểm đã tạo. Sau đó

$\qquad$ (a) Tìm ra các sinh viên có điểm trung bình môn cao nhất. \
$\qquad$ (b) Tìm ra các sinh viên có điểm trung bình môn thấp nhất. \
$\qquad$ (c) Tìm ra các sinh viên có xếp loại B+. \
$\qquad$ (d) Sắp xếp danh sách các sinh viên theo thứ tự giảm dần của điểm trung bình môn.

**2.** *(Mật mã Caesar)*\
Trong mã hóa, mật mã *Caesar* thay thế mỗi kí tự trong bảng chữ cái bởi một kí tự khác cũng trong bảng chữ cái đó ở vị trí cách nó một đoạn cố định.

Trong hình dưới đây, kí hiệu vòng trong là mã hóa cho kí hiệu vòng ngoài. Chẳng hạn, kí tự **T** là mã hóa của kí tự **A**, kí tự **U** là mã hóa của kí tự **B**, . . . Khi đó, nếu muốn gửi đi thông điệp **PYTHON** thì sẽ gửi đi mật mã **IRMAHG**.

<style>
	.row {
			display: flex;
			flex-direction: column;
			align-items: center;
  			justify-content: center;
		}

	.column {
		max-width: 45%;
		padding: 5px;
		padding-top: 20px;
		padding-bottom: 20px;
		display: flex;
	}

	.text-column {
		flex: 60%;
		padding-top: 20px;
		padding-bottom: 20px;
	}

	.fliped-text {
		-moz-transform: scale(1, 1);
		-webkit-transform: scale(1, 1);
		-o-transform: scale(1, 1);
		-ms-transform: scale(1, 1);
		transform: scale(1, 1);
	}

	@media(min-width: 580px) {
		.row {
			flex-direction: row;
		}
	}
</style>

<div class="row">
  <div class="column">
    <img src=".\image\assign05-img1.png" style="width:100%; max-height:300px">
  </div>
  <div class="text-column">
    <p style="width:100%" markdown="1">

* **ROT-13** là một trong những mã Caesar phổ biến nhất (rotate by 13 places). Em hãy viết chương trình mã hóa và giải mã cho **ROT-13**.

* Viết chương trình mã hóa và giải mã cho **ROT-x**, trong đó x là độ dài của đoạn dịch chuyển của mật mã Caesar.
	</p>
  </div>
</div>

**3.** Cho hai điểm A và B trên lưới ô vuông kích thước 10 × 10. Em hãy viết chương trình

$\qquad$ (a) In ra chỉ dẫn đi của một đường đi ngắn nhất từ A tới B. \
$\qquad$ (b) Tìm số lượng đường đi ngắn nhất từ A tới B.

*(Một đường đi trên lưới là một đường đi qua đỉnh của các ô vuông con thông qua các cạnh của chúng. Tức là được phép đi lên trên, xuống dưới, qua trái, qua phải; không được đi chéo.)*

<div>
	<img src=".\image\assign05-img2.png"
	style="width:60%;
	max-width:500px;
	display: block;
	margin-left: auto;
	margin-right: auto;">
</div>

# Additional Problems

**4.** *(Don’t Repeat Yourself)*

Trong đoạn code được trình bày ở dưới đây, các tham số (và giá trị của chúng) được sử dụng ở các hàm đều giống nhau. Theo nguyên lý Don’t Repeat Yourself **(DRY Principle)**, ta nên cải thiện đoạn code này để tránh sự lặp lại của các tham số. Hãy cải thiện đoạn code này.

```py
getArea(length=length_, width=width_, height=height_)
getVolume(length=length_, width=width_, height=height_)
getSomething(length=length_,width=width_,height=height_)
getSomethingElse(length=length_, width=width_, height=height_)
```
<p style="text-align: center">Listing 1: Repeated parameters in functions</p>

Gợi ý: Tạo một dict gồm các tham số và giá trị của chúng. Sử dụng `double asterisk operator`
