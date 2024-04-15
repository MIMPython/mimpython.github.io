---
title: "Random Fruits Game"
permalink: /projects/randomfruitsgame/
excerpt: "Game ứng dụng kiến thức Xử lý ảnh"
last_modified_at: 2024-03-06
---

Random Fruits Game là sản phẩm game đầu tiên của bạn [Nguyễn Quốc Hiệu](https://github.com/nqh-tq-32052503) sau khi học lập trình Python cơ bản được thực hiện vào cuối năm 2023.

Sau đây là lời giới thiệu về game của bạn Hiệu.

Đây là một tựa game ứng dụng kiến thức về Xử lý ảnh cùng với kỹ năng Lập trình Python. Mọi thao tác tiến hành trong trò chơi này, người chơi sẽ không cần sử dụng chuột và bàn phím mà chỉ tương tác với trò chơi thông qua webcam của máy tính. Để biết thêm hướng dẫn chi tiết cách tương tác với trò chơi, vui lòng theo dõi video đính kèm phía dưới. 

Game gồm 3 màn chơi, luật chơi của mỗi màn như sau:

- Màn 1: Người chơi di chuyển tay để điều khiển con trỏ chuột ảo trên màn hình "chạm" vào các loại quả rơi xuống và được tính điểm. Người chơi sẽ thắng và được chuyển đến màn tiếp theo khi "chạm" vào đúng loại và đủ số lượng quả được yêu cầu trên màn hình, đồng thời không vượt quá thời gian của màn chơi (thời gian đếm ngược ở góc của màn hình). Ngược lại, người chơi sẽ thua khi bị quá thời gian. 
- Màn 2: Mô tả màn chơi và điều kiện chiến thắng giống ở màn 1, tuy nhiên sẽ xuất hiện thêm các quả bom. Nếu người chơi chạm phải quả bom, thời gian đếm ngược sẽ bị trừ đi 1 giây. 
- Màn 3: Mô tả màn chơi và điều kiện chiến thắng giống màn 2, tuy nhiên mỗi giây trên màn hình sẽ xuất hiện thêm một dòng chữ. Dòng chữ đó là tên tiếng Anh của một loại quả nào đó. Nếu người chơi chạm phải quả đó hoặc quả có màu giống với màu của dòng chữ, thời gian đếm ngược sẽ bị trừ đi 1 giây. 

Các chức năng còn thiếu sót:

- Trong game chưa có hiển thị phần luật chơi 
- Nếu điều kiện ánh sáng của môi trường bên ngoài quá sáng hoặc quá tối, game sẽ bị lỗi do phần mềm không nhận diện ra được bàn tay của người chơi, dẫn tới có thể xuất hiện những lỗi không mong muốn trong quá trình chơi. Vui lòng đảm bảo điều kiện ánh sáng bình thường, không có nguồn sáng chói lóa ở phía sau người chơi. 

Mong rằng những sản phẩm tiếp theo của mình sẽ hoàn thiện hơn và mọi người sẽ có trải nghiệm vui vẻ với trò chơi.

{% include video id="FfLLefeRTss" provider="youtube" %}

[Source code](https://github.com/nqh-tq-32052503/RandomBallsGame)
