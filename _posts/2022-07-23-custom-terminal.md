---
title: "Tạo một terminal đẹp trên Windows"
last_modified_at: 2022-07-23
author: Tran-Thanh-Tung
author_profile: true
categories:
  - writing
tags:
  - terminal
  - design
---


<div>
    <img src="/assets/images/post/2022-07-15-custom-terminal/terminalCustom1.png"
    style="width:100%;
    max-width:900px;
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding-top:20px;
    padding-bottom:20px;">
</div>

Chào các bạn, hôm nay mình sẽ hướng dẫn mọi người tạo một terminal đẹp trên Windows để việc viết code trở nên thú vị hơn.

### 1. Cài đặt Windows Terminal

Để có một terminal đẹp, trước hết ta phải có một terminal xịn. Và theo mình đó là Windows Terminal, được Microsoft ra mắt năm 2019, WT (Windows Terminal) sở hữu nhiều tính năng ưu việt và đặc biệt đây là một dự án mã nguồn mở.

Chi tiết cài đặt WT các bạn có thể tham khảo tại [đây.](https://docs.microsoft.com/en-us/windows/terminal/install)

### 2. Tùy biến Windows Terminal

#### 2.1 Thay đổi background terminal

Việc thay đổi background trên WT thực sự rất đơn giản. Sau khi đã tải xuống và cài đặt WT, bạn chỉ cần làm theo các bước sau để tùy chỉnh background WT.

- Khởi động Windows Terminal, vào phần Setting.

<div>
    <img src="/assets/images/post/2022-07-15-custom-terminal/setting.png"
    style="width:100%;
    max-width:900px;
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding-top:20px;
    padding-bottom:20px;">
</div>

- Trong phần Setting, chọn phần Windows PowerShell ở thanh điều hướng bên trái, sau đó chọn Appearance

<div>
    <img src="/assets/images/post/2022-07-15-custom-terminal/PSAppearance.png"
    style="width:100%;
    max-width:900px;
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding-top:20px;
    padding-bottom:20px;">
</div>

- Cuối cùng là thay đổi hình nền trong phần Background image

<div>
    <img src="/assets/images/post/2022-07-15-custom-terminal/PSBackgroundImage.png"
    style="width:100%;
    max-width:900px;
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding-top:20px;
    padding-bottom:20px;">
</div>

#### 2.2 Thay đổi chủ đề WT sử dụng oh-my-posh

Để thay đổi chủ đề của WT, ta sử dụng oh-my-posh, một gói tùy biến cho terminal.

Cài đặt oh-my-posh bằng câu lệnh sau (sử dụng PowerShell trên WT)
  ```ps
  winget install oh-my-posh
  ```

Sau khi cài đặt, import oh-my-posh bằng câu lệnh sau:

  ```ps
  Import-Module oh-my-posh
  ```

Lúc này terminal của bạn đã chuyển sang theme mặc định của oh-my-posh. Bạn có thể chuyển sang một theme khác bằng câu lệnh sau:

  ```ps
  oh-my-posh --init --shell pwsh --config "~/AppData/Local/Programs/oh-my-posh/themes/your-theme.omp.json" | Invoke-Expression
  ```

Lưu ý: thay your-theme bằng tên một theme khác. Danh sách theme các bạn có thể xem tại [đây](https://ohmyposh.dev/docs/themes). Mình khá thích `1_shell` và `amro` 😃, bởi vì 2 theme này khá hợp với theme mình đang sử dụng trên Visual Studio Code.

Dưới đây là terminal mình đang sử dụng.
<div>
    <img src="/assets/images/post/2022-07-15-custom-terminal/terminalCustom2.png"
    style="width:100%;
    max-width:900px;
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding-top:20px;
    padding-bottom:20px;">
</div>

Như vậy là bạn đã có thể thay đổi theme của terminal. Tuy nhiên sẽ thật là bất tiện nếu mỗi lần bạn bật terminal lại phải chạy lại 2 lệnh trên để thay đổi theme. Thay vì thế bạn hãy làm theo các bước sau để thay đổi theme bất cứ khi nào bật PowerShell trên WT.

Chạy dòng lệnh sau
  ```ps
  notepad $PROFILE
  ```
Sau khi chạy lệnh trên, một file có tên `Microsoft.PowerShell_profile.ps1` được mở ra trên cửa sổ `notepad`. Lúc này, bạn chỉ cần lưu 2 dòng lệnh trên vào file này và lưu lại là xong.

Ngoài ra, bạn còn có thể tự tạo theme cho riêng mình bằng cách tạo 1 file `your-theme.omp.json` trong thư mục `~/AppData/Local/Programs/oh-my-posh/themes/`.

#### 2.3 Cài đặt font phù hợp

Nếu sau khi thay đổi theme của terminal, bạn lại gặp lỗi hiển thị với những ký tự đặc biệt thì hãy cài đặt font chữ phù hợp để hỗ trợ các hiển thị ký tự đó.

Mình đề xuất font chữ `MesloLGS Nerd`. Bạn có thể tải tại [đây](https://www.nerdfonts.com/).

- Thên font chữ trên Windows trong phần `Setting -> Personalization -> Font`
- Thêm font chữ trên PowerShell.
<div>
    <img src="/assets/images/post/2022-07-15-custom-terminal/settingFontWT.png"
    style="width:100%;
    max-width:900px;
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding-top:20px;
    padding-bottom:20px;">
</div>

### 3 Kết luận

Như vậy mình đã hướng dẫn các bạn thay mới terminal, nếu bạn dùng VS Code, bạn cũng có thể sử dụng terminal này bằng cách chọn PowerShell là terminal mặc định trên VS Code.

Dưới đây là hỉnh ảnh VS Code của mình, với theme VS Code `dracula` và theme oh-my-posh `1_shell`.
<div>
    <img src="/assets/images/post/2022-07-15-custom-terminal/VSCodeTerminal.png"
    style="width:100%;
    max-width:900px;
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding-top:20px;
    padding-bottom:20px;">
</div>

Đây là bài viết đầu tiên của mình trên MIMPython, mong rằng nó sẽ gây hứng thú cho các bạn 😃.
