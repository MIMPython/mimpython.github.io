---
title: "Bài tập tuần 7"
permalink: /pythonSummerCourse/week-07-assignment/
last_modified_at: 2022-08-24
redirect_from:
  - /theme-setup/
toc: false
---


**Danh sách bài tập tuần 7 đang được cập nhật.**

Bài tập tuần 7 gồm .. bài tập, bao gồm
- .. bài tập cơ bản: ... (làm tối thiểu .. bài).
- .. bài tập nâng cao: ... .


**Bài tập.** Thiết kế class Fraction.

**Bài tập.** Thiết kế class Polynomial sao cho có thể thực hiện các phép toán cộng (+), trừ (−), nhân (∗) giữa hai instance của class này ví dụ như trong đoạn code dưới đây

```py
polynomialA = Polynomial(...)
polynomialB = Polynomial(...)

polynomialC = polynomialA + polynomialB
polynomialD = polynomialA - polynomialB
polynomialE = -polynomialA
polynomialF = polynomialA * polynomialB
```

**Bài tập.** Viết một chương trình sử dụng các thư viện hình học cơ bản (code từ những buổi trước). Cấu trúc thư mục cần đạt được là

```
foo/
  additionalFolder/
    geometricalShapes/
      thisFileContainsPoint.py
      thisFileContainsCircle.py
  bar.py
```

File `bar.py` cần có phần đầu chứa dòng sau
```py
from additionalFolder.geometricalShapes import Point, Line, Circle
```

Chú ý rằng cấu trúc trên là bắt buộc phải có. Học viên thực hiện hai việc sau:
- phải đổi tên thư mục nộp (`foo/`) và tên file nộp (`bar.py`) cho phù hợp
- có thể bổ sung các file khác (của bài tập này hoặc của những bài tập khác) vào trong thư mục `foo/`
