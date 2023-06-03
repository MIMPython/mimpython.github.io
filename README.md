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

## Thêm dự án

Ví dụ muốn tạo thêm dự án `sample-project` thực hiện các bước sau:

- Trong thư mục `_projects` thêm file `.md` chứa nội dung dự án

- Các file chứ nội dung dự án sẽ có format như sau:
    ```
    ---
    title: "Dự án mẫu"
    permalink: /projects/sample-project/
    excerpt: "Mô tả về dự án mẫu."
    last_modified_at: 2022-06-22
    toc: false
    ---

    Nội dung dự án
    ```

- Trong trường `feature_row trong _page/projects.md` thêm đoạn code sau:
    ```
    - image_path: /assets/images/sample-project.png
        title: "Dự án mẫu"
        excerpt: "Mô tả cho dự án mẫu"
        url: "/projects/sample-project/"
    ```

## Thêm video vào page

Ví dụ muốn thêm video có đường link https://www.youtube.com/watch?v=BFUteVm_2wY
để mô tả nội dung trong page, thêm dòng lệnh sau vào file chứ nội dung page, tại vị trí muốn hiển thị video

    {% include video id="BFUteVm_2wY" provider="youtube" %}

## Thêm bài viết

Trong thư mục `_post` tạo file có tên theo format `YYYY-MM-DD-post-name.md`.

Nội dung file bài viết sẽ có formamt như sau:

    ---
    title: "Post name"
    last_modified_at: YYYY-MM-DD
    categories:
    - writing
    tags:
    - python
    author: author-1
    author_profile: true
    ---

    Nội dung post

Lưu ý: `author-1` là 1 trường dữ liệu về 1 tác giả đã có trong `_data/authors.yml`

## Cài đặt trang web chạy trên local

Để chạy trang web trên local, yêu cầu phải có những thứ sau:
- Ruby phiên bản 2.5.0 hoặc cao hơn
- RubyGems
- GCC và Make

Hướng dẫn cài đặt chi tiết cho từng hệ điều hành có tại [đây](https://jekyllrb.com/docs/installation/)

Cập nhật Ruby:

    sudo apt-get install ruby-full build-essential

Clone repository:

    git clone https://github.com/MIMPython/mimpython.github.io


Điều hướng đến thư mục chứa trang web:

    cd mimpython.github.io

Cài đặt bundle cho trang web:

    bundle clean
    bundle install

Sau khi cài đặt bundle cho trang web, mỗi lần chạy trang web trên local chỉ cần chạy câu lệnh sau:

    bundle exec jekyll serve --port 1234

với đối số `--port 1234` thể hiện local port. Khi đó link tới trang web local là http://127.0.0.1:1234

## Thêm tác giả cho bài viết

Thêm dữ liệu về tác giả trong `_data/author.yml`, cấu trúc như sau:

    author-1:
        name             : "author-1-name"
        avatar           : "/assets/images/avatar/author-1-avatar"
        bio              :
        location         :
        email            :
        links:
            - label: "Email"
            icon: "fas fa-fw fa-envelope-square"
            url: "mailto:your.name@email.com"
            - label: "Website"
            icon: "fas fa-fw fa-link"
            url: "https://your-website.com"
            - label: "Twitter"
            icon: "fab fa-fw fa-twitter-square"
            url: "https://twitter.com/"
            - label: "Facebook"
            icon: "fab fa-fw fa-facebook-square"
            url: "https://facebook.com/"
            - label: "GitHub"
            icon: "fab fa-fw fa-github"
            url: "https://github.com/"
            - label: "Instagram"
            icon: "fab fa-fw fa-instagram"
            url: "https://instagram.com/"

Trong bài viết muốn thêm tác giả, thêm 2 dòng sau vào phần YAML Front Matter

    author: author-1
    author_profile: true

Lưu ý: trong các trường `scope` trong file `_config.yml` phải bỏ các trường `author_profile`.


## Thêm ảnh

Thông thường, có thể thêm ảnh trong một file markdown bằng cú pháp
```md
![](assets/images/statics/logo.png)
```
Ta sẽ thu được ảnh dưới đây
![](assets/images/statics/logo.png)

Mặt khác, ta có thể sử dụng HTML để điều chỉnh các thuộc tính của ảnh như trong đoạn code dưới đây (đề xuất bởi [Quân Persie](https://github.com/quanpersie2001))

```md
<div>
    <img src="assets/images/statics/logo.png"
    style="width:70%;
    max-width:700px;
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding-top:20px;
    padding-bottom:20px;">
</div>
```
Ảnh thu được là

<div>
    <img src="assets/images/statics/logo.png"
    style="width:70%;
    max-width:700px;
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding-top:20px;
    padding-bottom:20px;">
</div>


## Tham khảo

[Minimal mistake theme](https://github.com/mmistakes/minimal-mistakes)
