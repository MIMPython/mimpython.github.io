---
title: "Bài 12. Github và markdown"
permalink: /pythonSummerCourse/lesson-12-github-markdown/
last_modified_at: 2023-02-09
redirect_from:
  - /theme-setup/
toc: false
---

<style>
  .image-site {
    img {
      width:80%;
      max-width:700px;
      display: block;
      margin-left: auto;
      margin-right: auto;
      padding-top:20px;
      padding-bottom:20px;
    }
  }
</style>

_Tác giả: Nguyễn Văn Quân_

## GitHub
### 1. GitHub là gì?
GitHub là một dịch vụ nổi tiếng cung cấp kho lưu trữ mã nguồn Git cho các dự án phần mềm. **Github có đầy đủ những tính năng của Git**, ngoài ra nó còn bổ sung những tính năng về social để các developer tương tác với nhau.

Vài thông tin về GIT:
* Là công cụ giúp quản lý source code tổ chức theo dạng dữ liệu phân tán.
* Giúp đồng bộ source code của team lên một server.
* Hỗ trợ các thao tác kiểm tra source code trong quá trình làm việc (diff, check modifications, show history, merge source, …)

### 2. GitHub cơ bản
#### Tạo GitHub Repository
Repository (gọi tắt là repo) là một không gian để lưu trữ dự án của bạn. Do tính chất phân tán của Git, nên có thể hiểu repo là nơi lưu trữ mã nguồn ở cả local và server.

Bạn có thể lưu trữ file code, text, hình ảnh hoặc bất kỳ loại tệp nào trong repo.

Để tạo một repo trên GitHub bạn làm như sau:

* Vào Github, đăng ký một tài khoản bằng cách click vào “Sign up for Github”.
* Sau khi đăng ký và kích hoạt thành công. Ấn dấu + trên thanh status bar chọn `New repository`.

<div class="image-site">
  <img src="/assets/images/courses/05-01-github-markdown/github-1.png">
</div>

Nhập tên Repositoty và nhấn nút “Create Repository”. Ngoài ra, bạn cũng có thể thêm mô tả cho repo.

<div class="image-site">
  <img src="/assets/images/courses/05-01-github-markdown/github-2.png">
</div>

Trong đó, bạn lưu ý 2 options sau:

* Theo mặc định thì repository để là public. Tức là ai cũng có thể xem được repo này của bạn. Nếu dự án của bạn chưa muốn công khai mà chỉ muốn quản lý nội bộ thì chọn Private.

* Bạn có thêm một README file để giới thiệu repo kèm với một file .gitignore. Github đã có sẵn template [.gitignore](https://github.com/github/gitignore) cho bạn, cứ chọn một template phù hợp với mã nguồn dự án là được.

Khi tạo xong, repo sẽ như sau:

<div class="image-site">
  <img src="/assets/images/courses/05-01-github-markdown/github-3.png">
</div>

Khi đã có repository, bạn có thể clone, pull, push… source code của mình lên đó.

> Các lệnh thực hiện để làm việc với GitHub tương tự như với Git xem tại [đây](https://mimpython.github.io/pythonSummerCourse/lesson-08-git/)


## Markdown
### 1. Tiêu đề
Để tạo tiêu đề - heading h1, h2, h3 cho đến h6, thêm số lượng ký tự `#` tương ứng vào đầu dòng. Số lượng `#` bạn sử dụng tương ứng với cấp độ tiêu đề, một ký tự `#`tương đương với h1, 2 ký tự `#` tương đương với h2, ...

Ví dụ: để tạo tiêu đề cấp ba, sử dụng ba ký hiệu #

`### MIM Python`
### 2. Đoạn văn
Để tạo các đoạn văn, sử dụng một dòng trống để tách các dòng văn bản. Bạn không nên thụt lề các đoạn bằng dấu cách hoặc tab.

### 3. In đậm chữ
Để in đậm văn bản, thêm hai dấu hoa thị hoặc dấu gạch dưới trước và sau một từ hoặc cụm từ. Để in đậm chữ cái nằm giữa một từ để nhấn mạnh, thêm hai dấu sao trước và sau các chữ cái (không sử dụng space).

| Cú pháp        | Kết quả |
|:---------------|:--------|
| `**MIM Python**` | **MIM Python**|
| `__MIM Python__` | __MIM Python__|

### 4. In nghiêng
Để in nghiêng văn bản, thêm một dấu hoa thị hoặc gạch dưới trước và sau một từ hoặc cụm từ. Để in nghiêng chữ cái nằm giữa một từ để nhấn mạnh, thêm một dấu sao trước và sau các chữ cái (không sử dụng space).

| Cú pháp        | Kết quả |
|:---------------|:--------|
| `*MIM Python*` | *MIM Python*|
| `_MIM Python_` | _MIM Python_|

### 5. In đậm và in nghiêng
Để nhấn mạnh văn bản bằng chữ in đậm và in nghiêng cùng một lúc, thêm ba dấu hoa thị hoặc ba dấu gạch dưới trước và sau một từ hoặc cụm từ.

| Cú pháp        | Kết quả |
|:---------------|:--------|
| `***MIM Python***` | ***MIM Python***|
| `___MIM Python___` | ___MIM Python___|
| `__*MIM Python*__` | __*MIM Python*__|
| `**_MIM Python_**` | _**MIM Python**_|

### 6. Trích dẫn
Để tạo một blockquote, hãy thêm dấu `>` vào trước đoạn văn.

Blockquote có thể được lồng trong một Blockquote khác. Thêm dấu `>>` ở phía trước đoạn bạn muốn lồng.

Blockquote có thể chứa các yếu tố định dạng Markdown khác. Tuy nhiên, không phải tất cả các yếu tố đều có thể sử dụng được, vậy nên bạn cần thử nghiệm để xem định dạng nào sẽ hoạt động.

### 7. Danh sách
#### 7.1  Danh sách có thứ tự

| Cú pháp        | Kết quả |
|:---------------|:--------|
| 1. Mục một <br /> 2. Mục hai <br /> 3. Mục ba   | 1. Mục một <br /> 2. Mục hai  <br /> 3. Mục ba |
| 1. Mục một <br /> 1. Mục hai  <br /> 1. Mục ba   | 1. Mục một  <br /> 2. Mục hai  <br /> 3. Mục ba |
| 1. Mục một <br /> 2. Mục hai <br /> 1. Mục phụ <br /> 2. Mục phụ <br /> 3. Mục ba| 1. Mục một <br /> 2. Mục hai <br /> &nbsp;&nbsp;&nbsp;&nbsp; 1. Mục phụ <br /> &nbsp;&nbsp;&nbsp;&nbsp; 2. Mục phụ <br /> 3. Mục ba |

#### 7.2 Danh sách không có thứ tự
Để định đạng danh sách có các gạch đầu dòng trong Markdown, bạn dùng kí tự dấu gạch ngang `-`, dấu hoa thị `*` hoặc dấu cộng `+` và một dấu cách trước nội dung muốn tạo, dùng thêm 2 dấu cách ở đằng trước nếu muốn lùi vào một level.

| Cú pháp        | Kết quả |
|:---------------|:--------|
| * Mục một <br /> * Mục hai <br /> * Mục ba   | <li> Mục một </li> <li> Mục hai </li><li> Mục ba </li> |
| - Mục một <br /> - Mục hai  <br /> - Mục ba   |  <li> Mục một </li> <li> Mục hai </li><li> Mục ba </li> |
| - Mục một <br /> - Mục hai <br /> &nbsp;&nbsp;- Mục phụ <br /> &nbsp;&nbsp;- Mục phụ <br /> - Mục ba| <ul><li>Mục một</li><li>Mục hai<ul><li>Mục phụ</li><li>Mục phụ</li></ul></li><li>Mục ba</li></ul> |

### 8. Code
Để biểu thị một từ hoặc cụm từ dưới dạng code, hãy đặt nó trong dấu **`**.

Với khối code thì ta đặt chúng trong **```**
### 9. Liên kết
Một liên kết được tạo tự động với cặp móc nhọn `<,>` đơn giản bao quanh liên kết:
`<https://mimpython.github.io/>`

Hoặc cầu kỳ hơn bằng cách đặt văn bản liên kết trong ngoặc (ví dụ: [MIM Python]) và kèm theo URL trong ngoặc đơn (ví dụ: (https://mimpython.github.io/)).

`Trang tôi đang theo học là [MIM Python](https://mimpython.github.io/).`

Kết quả là:

Trang tôi đang theo học là [MIM Python](https://mimpython.github.io/)

Ngoài ra các bạn có thể định dạng chữ như **In đậm**, *In nghiêng* cho liên kết.

### 10. Hình ảnh
Để thêm hình ảnh trong markdown, bạn thêm ký tự `!` vào đầu tiên, sau đó ghi alt text trong ngoặc vuông `[]` và URL ảnh trong ngoặc đơn `()`.

**Chèn liên kết vào hình ảnh**

Để thêm một liên kết vào hình ảnh trong Markdown, bạn đặt toàn bộ khai báo hình ảnh như bước trên trong ngoặc vuông [] và thêm liên kết mình cần vào ngoặc đơn () đặt ngay tiếp sau.
## Tài liệu tham khảo
Tài liệu chính
- [Bài viết về git/github](https://realpython.com/python-git-github-intro/) trên trang web Real Python
- [Cú pháp cơ bản](https://www.markdownguide.org/basic-syntax/) của markdown
