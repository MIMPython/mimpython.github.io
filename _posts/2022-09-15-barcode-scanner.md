---
title: "Scan barcode bằng Python"
last_modified_at: 2022-09-15
author: Dinh-Hoang-Nhat-Minh
author_profile: true
categories:
  - writing
tags:
  - image processing
---

Chào các bạn, hôm nay mình sẽ hướng dẫn mọi người tạo máy quét Barcode (trong đó được biết đến nhiều nhất có lẽ là QR code) bằng Python.

## 1. Các thư viện hỗ trợ
Trước hết, chúng ta cần cài đặt 3 thư viện hỗ trợ đó là: numpy, pyzbar, OpenCV.
Chúng ta cài đặt 3 thư viện này bằng cách chạy 3 câu lệnh sau ở terminal:

```
pip install numpy
```

```
pip install opencv-python
```

```
pip install pyzbar
```

Sau khi cài đặt xong thư viện, ta tạo một chương trình với tên `barcodeScanner.py` và import các thư viện này.
```
import numpy as np
import cv2
from pyzbar import pyzbar
```

## 2. Khai báo một số instants để sử dụng
Các instants này bao gồm: mã màu đỏ (màu khung barcode, màu nội dung hiển thị), độ dày khung, phông chữ hiển thị, tỉ lệ cỡ chữ, độ dày của chữ hiển thị, tên cửa sổ camera.
```py
RED = (0, 0, 255)
THICKNESS = 2
FONT = cv2.FONT_HERSHEY_DUPLEX
FONT_SCALE = 1
TEXT_THICKNESS = 1
windowName = 'Barcode scanner'
```

## 3. Tạo hàm đọc barcode

```py
def readBarcode(frame):
    # 1
    barcodes = pyzbar.decode(frame)

    for barcode in barcodes:
        # 2
        points = barcode.polygon
        x, y, w, h = barcode.rect
        pts = np.array(points, np.int32)
        pts = pts.reshape((-1, 1, 2))
        cv2.polylines(img=frame, pts=[pts], isClosed=True, 
                      color=RED, thickness=THICKNESS)
        # 3
        barcodeData = barcode.data.decode('utf-8')
        barcodeType = barcode.type
        # 4
        cv2.putText(img=frame, text=barcodeData, org=(x, y),   fontFace=FONT, 
                    fontScale=FONT_SCALE, color=RED, thickness=TEXT_THICKNESS)
        # 5
        with open(f"lastRecognizedBarcode.txt", mode ='w') as file:
            file.write(f"Last recognized barcode information \n"
                       f"Data: {barcodeData} \n" 
                       f"Type: {barcodeType}")
    return frame
```

Hàm `readBarcode` dùng để đọc barcode, hàm này nhận vào một khung hình, trả về khung hình có đóng khung và hiển thị nội dung của barcode (nếu có).

### Thứ tự thực hiện các bước trong hàm `readBarcode`: 

  - `1:` tìm các barcode có trong khung hình .

  Sau đó với mỗi barcode tìm được:
  - `2:` đóng khung các barcode đó trên khung hình.
  - `3:` đọc dữ liệu chứa trong barcode.
  - `4:` thêm chữ hiển thị dữ liệu đã đọc lên phía trên của barcode trong khung hình.
  - `5:` tạo một file kết quả có tên `lastRecognizedBarcode.txt` để lưu dữ liệu đã đọc được.

## 4. Tạo hàm main
```py
def main():
    # 1
    camera = cv2.VideoCapture(0)
    ret, frame = camera.read()

    # 2
    while ret:
        ret, frame = camera.read()
        frame = readBarcode(frame)
        cv2.imshow(windowName, frame)
        keyCode = cv2.waitKey(1)
        if keyCode & 0xFF == ord('q'):
            break
        if cv2.getWindowProperty(windowName, cv2.WND_PROP_VISIBLE) < 1:
            break
    # 3
    camera.release()
    cv2.destroyAllWindows()
```
Thứ tự thực hiện các bước trong hàm `main`:

  - `1:` mở camera, đọc dữ liệu từ camera với `ret` là một biến boolean thể hiện việc camera có đang được mở hay không, `frame` là khung hình được lưu.
  
  - `2:` vòng lặp `while` có ý nghĩa là nếu camera vẫn đang được mở, nút `q` hoặc nút tắt cửa sổ camera chưa được ấn thì ta vẫn tiếp tục việc đọc các khung hình và tìm barcode.

  - `3:` thực hiện việc tắt camera và đóng cửa sổ sau khi vòng lặp `while` kết thúc.

## 5. Gọi hàm main
Cuối cùng ta thực hiện bước gọi hàm `main` để chạy chương trình.
```py
if __name__ == '__main__':
    main()
```
Dưới đây là thành quả của chúng ta sau khi chạy file `barcodeScanner.py`.
<div>
    <img src="/assets/images/post/2022-09-15-barcode-scanner/barcodeScanner.png"
    style="width:40%;
    max-width:900px;
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding-top:20px;
    padding-bottom:20px;">
</div>

## 6. Lời kết
Vậy là mình đã hướng dẫn xong việc tạo một máy quét bằng Python. Mong rằng qua bài viết có thể tạo thêm hứng thú cho các bạn trong việc lập trình bằng Python.

Đây cũng có thể là một hướng để các bạn phát triển và lập trình một số chương trình khác về xử lí ảnh, tạo mã code,t...

## 7. Tài liệu tham khảo 

  - [Medium](https://towardsdatascience.com/build-your-own-barcode-and-qrcode-scanner-using-python-8b46971e719e)

  - [Geeksforgeeks](https://www.geeksforgeeks.org/python-opencv-capture-video-from-camera/)

