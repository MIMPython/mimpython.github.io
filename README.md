# Welcome to MIM Python

## Thêm Khóa học

Ví dụ muốn thêm khóa học `foobar`, thực hiện theo các bước sau:
- Tạo thư mục `_foobar` chứa các file `.md` là nội dung các bài học
- Các file bài học sẽ có format như sau:
    ```
    ---
    title: "Bài 1"
    permalink: /foobar/lesson-01/
    excerpt: "Mô tả về bài 1."
    last_modified_at: 2022-06-22
    toc: false
    ---
    
    Nội dung bài 1
    ```
    Trong đó `toc` là `table of content`
- Trong trường `feature_row` trong `_page/courses.md` thêm đoạn code sau:
    ```
    - image_path: /assets/images/foobar.png
        title: "Khóa học foobar"
        excerpt: "Description for foobar"
        url: "/foobar/" 
    ```
    Lưu ý: ảnh mô tả cho khóa học được dặt trong thư mục `assets/images`.
-  Tạo `navigation menu` cho khóa học bằng cách thêm `navigation` mới trong `_data/navigation.yml`,  VD như sau:
    ```
    foobar-navigation:
    - title: "Giới thiệu chung"
        url: /foobar/
    - title: Tuần 1
        url: /foobar/week-01/
        children:
        - title: "Bài 1"
            url: /foobar/lesson-01/
        - title: "Bài 2"
            url: /foobar/lesson-02/
        - title: "Bài tập tuần 1"
            url: /foobar/assignment-week-01/
    - title: Tuần 2
        url: /foobar/week-02/
        children:
        - title: "Bài 3"
            url: /foobar/lesson-03/
        - title: "Bài 4"
            url: /foobar/lesson-04/
        - title: "Bài tập tuần 2"
            url: /foobar/assignment-week-02/
    ```
- Thêm `scope` mới trong trường `default` trong file `_config.yml`. Vd như sau:
    ```
      - scope:
            path: ""
            type: foobar
        values:
            layout: single
            read_time: false
            author_profile: false
            share: false
            comments: false
            sidebar:
                nav: "foobar-navigation"
    ```

- Thêm đoạn code sau vào trường `collections` trong file `_config.yml`.
    ```
    foobar:
        output: true
        permalink: /:collection/:path/
    ```
Lưu ý: Thứ tự `next`, `previous` các trang chứa nội dung bài học là thứ tự các file chứ nội dung trong folder.
## Chạy trên local

Cài ruby tại [đây](https://www.ruby-lang.org/vi/documentation/installation/)

Cài đặt `jekyll bundler` bằng câu lệnh
```
gem install jekyll bundler
```

Cài đặt bundle cho trang web:

    ```
    bundle clean
    bundle install
    ```
Chạy web trên local"
    ```
    bundle exec jekyll serve
    ```

## Tham khảo

[Minimal mistake theme](https://github.com/mmistakes/minimal-mistakes)
