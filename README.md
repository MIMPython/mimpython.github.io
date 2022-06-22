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
    last_modified_at: YYYY-MM-Đ
    toc: false
    ---
    
    Nội dung khóa học
    ```
    Trong đó `toc` là `table of content`
-  Tạo `navigation menu` cho khóa học bằng cách thêm `navigation` mới trong `_data/navigation.yml`,  VD như sau:
    ```
    foobar:
    - title: Tuần 1
        children:
        - title: "Bài 1"
          url: /foobar/lesson-01/
        - title: "Bài 2"
          url: /foobar/lesson-02/

    - title: Tuần 2
        children:
        - title: "Bài 3"
          url: /course1/lesson-03
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
                nav: "foobar"
    ```

- Thêm đoạn code sau vào trường `collections` trong file `_config.yml`.
    ```
    foobar:
        output: true
        permalink: /:collection/:path/
    ```

