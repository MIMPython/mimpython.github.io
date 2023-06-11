---
title: "Bài tập tuần 5"
permalink: /pythonSummerCourse/week-05-assignment/
last_modified_at: 2022-08-20
redirect_from:
  - /theme-setup/
toc: false
---


Bài tập tuần 5 gồm 9 bài tập, bao gồm
- 6 bài tập cơ bản: 1, 2, 3, 4, 5, 6 (làm tối thiểu 5 bài).
- 3 bài tập nâng cao: 7, 8, 9.

Cập nhật
- 10/08/2022. Bổ sung bài tập 7, bài tập 8, bài tập 9.
- 10/08/2022. Bổ sung một số lưu ý về việc nộp bài, xem chi tiết trong mục 3.2 và mục 4 trong phần [giới thiệu khóa học](/pythonSummerCourse/).
- 19/08/2022. Bổ sung mô tả cho bài tập 2.
- 20/08/2022. Bổ sung câu hỏi cho bài tập 4.


## Danh sách bài tập

**Bài tập 1.** *(Github)* \
Tạo một repository public trên Github và thực hiện những công việc có thể làm đối với một repository. Sau đó ghi link repository và danh sách công việc (khuyến khích sử dụng tiếng Anh) đã thực hiện vào phần bài làm của bài tập này. Dưới đây là ví dụ cho một file bài nộp.

```py
"""
Repository: https://github.com/MIMPython/MIMPython2022-Assignment

Danh sách công việc đã thực hiện
- viết commit
- tạo nhánh, tạo tag trên repo
- tạo issue, đóng issue
- tạo pull request
- chọn license cho repo
- viết README, đính kèm ảnh động (gif)
- có một người khác đóng góp commit vào repo
"""
```

**Bài tập 2.** *(markdown)* \
Viết một file markdown (đuôi `.md`) và đặt nó vào trong thư mục bổ sung `additionalFolder/`, sau đó ghi tên file markdown này vào phần bài làm của bài tập này. Tên file cần thể hiện rõ thông tin cá nhân của học viên.

**Bài tập 3.** *(scripting)* \
Mở một terminal và thực hiện những yêu cầu dưới đây. Ghi lại **tất cả** những câu lệnh đã thực thi (kể từ thời điểm mở terminal) vào phần bài làm của bài tập này, đồng thời đặt thư mục `X` vào trong thư mục bổ sung `additionalFolder/` trong phần bài nộp.

Danh sách yêu cầu
- Chuyển đường dẫn tới một thư mục rỗng `X` đã được tạo thủ công từ trước.
- Tạo một thư mục mới với tên `foo` trong đó.
- Chuyển đường dẫn vào thư mục `foo`.
- Tạo một file với tên `data.txt` trong thư mục `foo` và ghi `Hello World!` vào trong file này.
- Tạo một bản sao của file `data.txt` với tên `newData.txt` (cùng trong thư mục `foo`).
- Tạo một bản sao của file `data.txt` với tên `newData_2.txt` (cùng trong thư mục `foo`).
- Chuyển đường dẫn lên thư mục `X`.
- Tạo một thư mục mới với tên `bar` trong đó.
- Chuyển file `newData.txt` từ thư mục `foo` sang thư mục `bar`.
- Xóa file `newData_2.txt` trong thư mục `foo`.

Chú ý
- Bài làm cần ghi rõ hệ điều hành đã sử dụng.
- Sử dụng lệnh `code data.txt` để tạo mới file `data.txt` đồng thời ghi nội dung file bằng vscode.


**Bài tập 4.** *(về bờ không khó)* \
Giả sử giá của một cổ phiếu trong một ngày là cố định và phải nằm trong khung từ $93\%$ đến $107\%$ so với giá của ngày giao dịch liền trước. Ngày giao dịch là các ngày từ thứ hai đến thứ sáu trong tuần. Biết rằng vào ngày 08/08/2022, giá của cổ phiếu _F_ là 7.24 (đơn vị nghìn đồng). \
a) Chỉ ra giá tối đa mà cổ phiếu này có thể đạt được trong mỗi ngày trong khoảng từ 09/08/2022 đến 12/08/2022. \
b) Hỏi thời điểm sớm nhất mà giá của cổ phiếu này chạm mốc 58.69 nghìn đồng là khi nào?

Giải _Quyết_ bài tập này trong hai trường hợp sau đây: \
Trường hợp 1: Giá cổ phiếu nhận giá trị là một số thực. \
Trường hợp 2: Giá cổ phiếu (đơn vị nghìn đồng) là một số có hai chữ số sau dấu chấm thập phân, ví dụ $32.40$.


**Bài tập 5.** *(infinite loop)* \
a) Viết một chương trình chạy vô hạn sử dụng vòng lặp `while`. \
b) Viết một chương trình chạy vô hạn sử dụng vòng lặp `for` và không dùng vòng lặp `while`. \
c) Viết một chương trình chạy vô hạn sử dụng vòng lặp `for` mà đối tượng được duyệt (sau từ khóa `in`) không phải là một `list`, `tuple`, `set`, hay `dictionary`.


**Bài tập 6.** *(command line arguments)* \
Thực hiện lại bài tập 3 của tuần 2 với việc thực thi chương trình kèm với đối số truyền qua dòng lệnh. Chú ý tên file nộp phải ghi đúng quy tắc (là bài tập 6 tuần 5).


**Bài tập 7.** *(palindrome number)* \
Số xuôi ngược là một số tự nhiên không thay đổi khi được viết theo chiều ngược lại. Có tồn tại vô hạn số xuôi ngược đồng thời là một số chính phương hay không?


**Bài tập 8.** *(vietkey)* \
Viết một chương trình chuyển đổi giữa chuỗi ký tự tiếng Việt và chuỗi ký tự tiếng Anh tương ứng. Ví dụ

```
## vnm to eng
input: toán
output: toans

## eng to vnm
input: vawn
output: văn
```

**Nhận xét.** Có lẽ chương trình chuyển từ tiếng Việt sang tiếng Anh dễ thực hiện hơn, nhưng đồng thời nó có ít ý nghĩa thực tế hơn.


**Bài tập 9.** *(three hands of a clock)* \
Cho một đồng hồ kim với kim giờ, kim phút, kim giây có độ dài bằng nhau và bằng 1, được gắn với nhau tại tâm của đồng hồ và gọi $A$, $B$, $C$ lần lượt là ba đầu mút còn lại của ba kim đồng hồ đó. Đặt $M = AB + BC + CA$, ta đã biết một số giá trị của M tại một số thời điểm, ví dụ như: \
(i) $M = 0 + 0 + 0 = 0$ lúc 00h00'00" \
(ii) $M = 2 + 2 + 0 = 4$ lúc 06h00’00”

Hỏi trong thời gian hoạt động của đồng hồ từ 00h00’10” đến 11h59’50” cùng ngày, giá trị lớn nhất và giá trị bé nhất mà $M$ có thể đạt được là bao nhiêu? Những giá trị đó đạt được vào (những) thời điểm nào?

*Gợi ý:* $0 \leq M \leq 3\sqrt{3}$
