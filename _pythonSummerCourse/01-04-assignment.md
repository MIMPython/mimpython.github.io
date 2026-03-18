---
title: "Bài tập lần 1"
permalink: /pythonSummerCourse/module-01-assignment/
last_modified_at: 2026-03-19
redirect_from:
  - /theme-setup/
toc: false
---

Bài tập lần 1 gồm 3 bài tập, bao gồm
- 3 bài tập cơ bản: 1, 2, 3 (làm tối thiểu 3 bài).


## Danh sách bài tập

**Bài tập 1.** Python \
(a) Ngôn ngữ lập trình Python được tạo ra bởi ai và vào thời gian nào? \
(b) Vì sao ngôn ngữ lập trình Python lại được đặt tên như vậy? \
(c) Tính tới thời điểm hiện tại, phiên bản Python mới nhất được phát hành là phiên bản nào?


**Bài tập 2.** VS Code \
(a) VS Code là một phần mềm mã nguồn mở, đúng hay sai? Vì sao? \
(b) Chỉ ra ít nhất hai text editor khác có chức năng tương tự VS Code. \
(c) Giải thích ý nghĩa của meme sau


<div>
    <img src="/assets/images/courses/homework/vscode_meme.png"
    style="width:70%;
    max-width:700px;
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding-top:20px;
    padding-bottom:20px;">
</div>

<center> Nguồn: internet </center>


**Bài tập 3.** pip \
(a) Công cụ `pip` được sử dụng vào mục đích gì? \
(b) Giải thích ý nghĩa của câu lệnh `pip freeze`. \
(c) Chỉ ra một công cụ khác có chức năng tương tự `pip`.


## Thảo luận
- Phím tắt bật/tắt thanh công cụ bên trái ở Visual Studio Code: `Ctrl+B`
- Phím tắt mở cây thư mục trong thanh công cụ: `Ctrl+Shift+E`
- Phím tắt phóng to/thu nhỏ cỡ chữ: `Ctrl + +` / `Ctrl + -`
- Khuyến khích sử dụng command prompt/terminal để chạy code
- Tên file không nên chứa các ký tự _đặc biệt_
- Mỗi dòng code chỉ nên chứa tối đa 79 ký tự (theo PEP8)
- Cách tạo đường kẻ dọc trong trang soạn thảo của Visual Studio Code
    + Vào cài đặt:
        * Cách 1. Mở hộp câu lệnh bằng phím tắt `Ctrl+Shift+P` và chọn `Preferences: Open User Settings (JSON)`
        * Cách 2. Chọn `File` → `Preferences` → `Settings`
    + Thêm đoạn mã dưới đây để tạo các đường kẻ dọc với màu sắc mặc định/tùy chọn:
    ```json
    "editor.rulers": [
        79,
        {"column": 99, "color": "#AB8A83"},
        119,
    ],
    ```
