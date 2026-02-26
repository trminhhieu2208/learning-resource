# Tài Liệu Học HTML - Made By trminhhieu

## 📑 Mục lục (Table of Contents)

1. [Tổng quan (Overview)](#1-tổng-quan-overview)
2. [Cấu trúc tiêu chuẩn của một tài liệu HTML](#2-cấu-trúc-tiêu-chuẩn-của-một-tài-liệu-html)
3. [Kiến trúc hệ thống & Ngữ nghĩa (Architecture & Semantics)](#3-kiến-trúc-hệ-thống--ngữ-nghĩa-architecture--semantics)
4. [Tài liệu tham khảo API (API Reference)](#4-tài-liệu-tham-khảo-api-api-reference)
   - [4.1. Bố cục (Layout) & Sectioning](#41-bố-cục-layout--sectioning)
   - [4.2. Văn bản (Text & Inline Semantics)](#42-văn-bản-text--inline-semantics)
   - [4.3. Danh sách (Lists)](#43-danh-sách-lists)
   - [4.4. Đa phương tiện (Multimedia & Embeds)](#44-đa-phương-tiện-multimedia--embeds)
   - [4.5. Bảng (Tables)](#45-bảng-tables)
   - [4.6. Biểu mẫu (Forms)](#46-biểu-mẫu-forms)
5. [Các tiêu chuẩn nâng cao](#5-các-tiêu-chuẩn-nâng-cao)
   - [5.1. HTML Chuẩn SEO](#51-html-chuẩn-seo)
   - [5.2. Accessibility (A11y) - Khả năng truy cập](#52-accessibility-a11y---khả-năng-truy-cập)
   - [5.3. Comments - Chú thích mã nguồn](#53-comments---chú-thích-mã-nguồn)

---

## 1. Tổng quan (Overview)

**HTML (HyperText Markup Language - Ngôn ngữ Đánh dấu Siêu văn bản)** là thành phần xây dựng cơ bản nhất của không gian mạng (World Wide Web). Nhiệm vụ cốt lõi của HTML là **định nghĩa ý nghĩa và cấu trúc** của nội dung web.

- **Bản chất:** HTML là một **ngôn ngữ đánh dấu (markup)**, sử dụng các **thẻ (tags)** để chú thích văn bản, hình ảnh và hiển thị nội dung trên trình duyệt (ví dụ: `<p>`, `<img>`, `<video>`).
- **Lưu ý:** HTML **KHÔNG phải là ngôn ngữ lập trình** vì nó thiếu các cấu trúc điều khiển logic toán học (như vòng lặp, câu lệnh điều kiện).

### Vị trí trong Hệ sinh thái Front-End

Để xây dựng một trang web hoàn chỉnh, HTML hiếm khi đứng một mình mà thường được kết hợp với các công nghệ khác để tạo nên giao diện (CSS) và chức năng/hành vi (JavaScript).

**Sơ đồ 3 lớp của một Trang Web:**

```text
[ GIAO DIỆN WEB HOÀN CHỈNH ]
           │
           ▼
┌──────────────────────────────────────────┐
│ ⚡ LỚP 3: JAVASCRIPT (Ngôn ngữ lập trình)│
│    Vai trò: Cơ bắp / Chức năng           │ ──> Xử lý "HÀNH VI" (Pop-up, load data, logic động)
├──────────────────────────────────────────┤
│ 🎨 LỚP 2: CSS (Ngôn ngữ tạo kiểu)        │
│    Vai trò: Lớp da / Thẩm mỹ             │ ──> Quyết định "TRÌNH BÀY" (Màu sắc, khoảng cách, bố cục)
├──────────────────────────────────────────┤
│ 🧱 LỚP 1: HTML (Ngôn ngữ đánh dấu)       │
│    Vai trò: Bộ khung / Xương sống        │ ──> Định nghĩa "CẤU TRÚC & Ý NGHĨA" (Đâu là tiêu đề, đoạn văn)
└──────────────────────────────────────────┘
```

## [⬆ Quay lại Mục lục](#-mục-lục-table-of-contents)

## 2. Cấu trúc tiêu chuẩn của một tài liệu HTML

Để bắt đầu với HTML, bạn không cần cài đặt môi trường (Environment Setup) phức tạp — chỉ cần một trình soạn thảo văn bản (Text Editor) và một trình duyệt web. Dưới đây là "bộ khung xương" chuẩn mực bắt buộc phải có của mọi trang web hiện đại.

**Mã nguồn Copy-pasteable:**

```html
<!DOCTYPE html>
<html lang="vi">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Hello World - Trang Web Đầu Tiên</title>
  </head>
  <body>
    <h1>Chào mừng đến với thế giới HTML!</h1>
    <p>Đây là một đoạn văn bản cơ bản.</p>
  </body>
</html>
```

### Giải phẫu bộ khung HTML

Dù một trang web có phức tạp đến đâu, nó đều tuân theo cấu trúc phân cấp tĩnh và được xây dựng dựa trên các thành phần cốt lõi sau:

- `<!DOCTYPE html>` **(Khai báo kiểu tài liệu):** Đây không phải là một thẻ HTML, mà là một lệnh bắt buộc phải đặt ở dòng đầu tiên của file. Lệnh này khai báo rằng tài liệu sử dụng HTML5, giúp trình duyệt kích hoạt **chế độ tiêu chuẩn (no-quirks mode / standards mode)** để render giao diện, tránh các lỗi hiển thị do trình duyệt chạy ở chế độ tương thích với các trang web cũ.
- `<html>` **(Thẻ gốc - Root Element):** Là phần tử cấp cao nhất bao bọc toàn bộ mã HTML của trang.
  - _Thuộc tính_ `lang="vi"`: Cực kỳ quan trọng cho **Accessibility (Khả năng truy cập)**. Nó giúp các phần mềm đọc màn hình (Screen Readers) phát âm chuẩn ngôn ngữ, đồng thời hỗ trợ các công cụ dịch thuật và Search Engine xác định ngôn ngữ đích của trang.
- `<head>` **(Phần đầu trang):** Chứa các **siêu dữ liệu (metadata)** dành cho _máy móc_ (trình duyệt, công cụ tìm kiếm) đọc hiểu. Nội dung trong phần này không hiển thị trực tiếp lên không gian giao diện của người dùng.
  - `<meta>`: Thẻ đa năng cung cấp metadata. Dùng để cấu hình bảng mã (`charset="UTF-8"`), tương thích thiết bị (`name="viewport"`), hoặc thẻ mô tả cho SEO (`name="description"`).
  - `<title>`: Tiêu đề của trang web (hiển thị trên tab trình duyệt và kết quả Google).
  - `<link>`: Liên kết trang web với các tài nguyên bên ngoài. Phổ biến nhất là để nhúng file CSS (`<link rel="stylesheet" href="...">`) và icon trang web (`rel="icon"`).
  - `<style>`: Cặp thẻ dùng để viết trực tiếp các đoạn mã CSS vào bên trong file HTML.
  - `<script>`: Dùng để nhúng file JavaScript từ bên ngoài (`<script src="...">`) hoặc viết trực tiếp logic JavaScript bên trong.
  - `<noscript>`: Cung cấp nội dung dự phòng, nội dung này chỉ hiển thị khi trình duyệt của người dùng bị tắt hoặc không hỗ trợ JavaScript.
- `<body>` **(Phần thân trang):** Đại diện cho toàn bộ nội dung tài liệu **hiển thị cho người dùng** (như văn bản, hình ảnh, video, danh sách, biểu mẫu...). Trên một tài liệu HTML chỉ được phép tồn tại duy nhất một thẻ `<body>`.

[⬆ Quay lại Mục lục](#-mục-lục-table-of-contents)

---

## 3. Kiến trúc hệ thống & Ngữ nghĩa (Architecture & Semantics)

### 3.1. Cơ chế hoạt động: Từ Mã nguồn đến Giao diện

Trình duyệt không hiển thị trực tiếp các dòng code. Nó **phân tích cú pháp (parse)** HTML thành một cấu trúc cây trong bộ nhớ gọi là **DOM (Document Object Model)**.

```text
[ File .html ]
      │
      ▼ 1. Phân tích (Parse)
[ Cây DOM ] ◄═════════ 3. Thay đổi giao diện ═════════ [ JavaScript ]
      │                   (Không cần tải lại trang)
      ▼ 2. Hiển thị
[ Giao diện Web ]
```

Cây DOM chính là cầu nối. Nó chứa các "Nút" (Nodes) để JavaScript có thể tìm đến, can thiệp và cập nhật giao diện ngay trong thời gian thực.

### 3.2. HTML5 & Cuộc cách mạng Semantic (Ngữ nghĩa)

HTML5 cung cấp tính năng **xác thực biểu mẫu (Constraint Validation)** tự động mà không cần dùng đến JavaScript, đồng thời thay đổi hoàn toàn tư duy dựng khung trang web thông qua **Semantic HTML**.

Thay vì lạm dụng thẻ vô nghĩa, mỗi vùng nội dung giờ đây dùng một thẻ mang đúng ý nghĩa của nó:

```text
❌ Cấu trúc cũ (Div-soup)         ✅ Semantic HTML5
┌───────────────────────┐         ┌───────────────────────┐
│ <div id="header">     │         │ <header>              │
│ <div id="nav">        │   ──►   │ <nav>                 │
│ <div id="main">       │         │ <main>                │
│ <div id="footer">     │         │ <footer>              │
└───────────────────────┘         └───────────────────────┘
```

- **Quy tắc vàng:** Chỉ dùng thẻ vô nghĩa như `<div>` như là phương án cuối cùng khi không có thẻ ngữ nghĩa nào phù hợp (thường để bọc CSS).
- **Lợi ích:** Bot tìm kiếm (SEO) và các công cụ đọc màn hình (Accessibility) dựa vào các thẻ này để hiểu ngay đâu là phần điều hướng, đâu là nội dung cốt lõi của trang web.

[⬆ Quay lại Mục lục](#-mục-lục-table-of-contents)

---

### 4. Tài liệu tham khảo API (API Reference)

#### 4.1. Bố cục (Layout) & Sectioning

| Thẻ & thuộc tính                                                                                                                                                      | Chức năng                                                                                                           |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------ |
| [`<main>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/main)                                                                                            | Nội dung chính (chỉ nên có duy nhất 1 thẻ hiển thị trên mỗi trang).                                                 |
| [`<header>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/header) / [`<footer>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/footer)       | Phần đầu và phần chân của trang hoặc vùng nội dung.                                                                 |
| [`<article>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article)                                                                                      | Khối nội dung độc lập, có thể tái sử dụng được (như bài blog, bình luận).                                           |
| [`<section>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section)                                                                                      | Vùng nội dung theo chủ đề, nên đi kèm với thẻ tiêu đề.                                                              |
| [`<aside>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/aside)                                                                                          | Nội dung phụ, mang tính chất liên quan gián tiếp (như sidebar, chú thích).                                          |
| [`<nav>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/nav)                                                                                              | Thanh điều hướng.                                                                                                   |
| [`<search>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/search)                                                                                        | Khu vực thực hiện tìm kiếm/lọc.                                                                                     |
| [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)                                                                                              | Vùng chứa chung không mang ý nghĩa ngữ nghĩa (semantic). Chỉ nên dùng để bọc các phần tử cho mục đích tạo kiểu CSS. |
| [`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/id) / [`class`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/class) | Các thuộc tính toàn cục dùng làm định danh để áp dụng CSS.                                                          |
| [`hidden`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/hidden)                                                                                | Thuộc tính dùng để ẩn phần tử hoàn toàn khỏi hiển thị.                                                              |
| [`inert`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/inert)                                                                                  | Thuộc tính vô hiệu hóa mọi tương tác (click, focus).                                                                |

[⬆ Quay lại Mục lục](#-mục-lục-table-of-contents)

#### 4.2. Văn bản (Text & Inline Semantics)

| Thẻ & thuộc tính                                                                                                                                                                                                                                                                                              | Chức năng                                                                                           |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :-------------------------------------------------------------------------------------------------- |
| [`<h1>`-`<h6>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements)                                                                                                                                                                                                                   | Thẻ khối phân cấp tiêu đề.                                                                          |
| [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p)                                                                                                                                                                                                                                          | Thẻ khối tạo đoạn văn.                                                                              |
| [`<blockquote>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote)                                                                                                                                                                                                                        | Thẻ khối trích dẫn đoạn văn dài (sử dụng thuộc tính `cite` chứa URL nguồn).                         |
| [`<pre>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/pre)                                                                                                                                                                                                                                      | Thẻ khối giữ nguyên định dạng gốc của văn bản (thường dùng để bọc code).                            |
| [`<hr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/hr)                                                                                                                                                                                                                                        | Thẻ khối thêm đường phân cách ngang thể hiện sự chuyển đổi chủ đề.                                  |
| [`<strong>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/strong) / [`<em>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/em)                                                                                                                                                       | Văn bản quan trọng / Nhấn mạnh trọng âm.                                                            |
| [`<mark>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/mark)                                                                                                                                                                                                                                    | Highlight (làm nổi bật) văn bản.                                                                    |
| [`<s>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/s)                                                                                                                                                                                                                                          | Văn bản đã lỗi thời hoặc không còn chính xác.                                                       |
| [`<small>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/small)                                                                                                                                                                                                                                  | Dành cho các dòng in ấn nhỏ như điều khoản pháp lý, bản quyền.                                      |
| [`<q>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/q) / [`<cite>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/cite)                                                                                                                                                             | Đoạn trích dẫn ngắn / Tên một tác phẩm (như sách, phim).                                            |
| [`<dfn>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dfn) / [`<abbr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/abbr)                                                                                                                                                         | Định nghĩa một thuật ngữ / Từ viết tắt (nên kết hợp dùng thuộc tính `title` để giải thích ý nghĩa). |
| [`<code>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/code) / [`<kbd>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/kbd) / [`<samp>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/samp) / [`<var>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/var) | Định dạng cho: Mã máy / Nút bấm trên bàn phím / Đầu ra mẫu / Tên biến.                              |
| [`<data>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/data) / [`<time>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/time)                                                                                                                                                       | Gắn giá trị cho máy đọc (thuộc tính `value`) / Thời gian (thuộc tính `datetime`).                   |
| [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)                                                                                                                                                                                                                                          | Tạo siêu liên kết, đi kèm các thuộc tính quan trọng: `href`, `target="_blank"`, `download`, `rel`.  |
| [`<br>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/br) / [`<wbr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/wbr)                                                                                                                                                             | Dấu ngắt dòng (`<br>`) và thẻ quy định cơ hội ngắt dòng an toàn cho các từ quá dài (`<wbr>`).       |

[⬆ Quay lại Mục lục](#-mục-lục-table-of-contents)

#### 4.3. Danh sách (Lists)

| Thẻ & thuộc tính                                                                                                                                                                                                         | Chức năng                                                                                                                          |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------- |
| [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul)                                                                                                                                                   | Danh sách không thứ tự (đánh dấu bằng bullet).                                                                                     |
| [`<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol)                                                                                                                                                   | Danh sách có thứ tự. Bao gồm các thuộc tính định dạng: `start` (đếm bắt đầu từ n), `reversed` (đếm ngược), `type` (1, a, A, i, I). |
| [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li)                                                                                                                                                   | Phần tử con bên trong danh sách. Có thể dùng thuộc tính `value` giúp ép buộc thay đổi số thứ tự nếu nằm trong `<ol>`.              |
| [`<dl>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dl) , [`<dt>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dt) , [`<dd>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dd) | Danh sách mô tả cấu trúc theo dạng Cặp Key-Value.                                                                                  |
| [`<menu>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/menu)                                                                                                                                               | Về mặt ngữ nghĩa là danh sách các lệnh/công cụ.                                                                                    |

[⬆ Quay lại Mục lục](#-mục-lục-table-of-contents)

#### 4.4. Đa phương tiện (Multimedia & Embeds)

| Thẻ & thuộc tính                                                                                                                                                 | Chức năng                                                                                                                                                                                     |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img)                                                                                         | Embed (nhúng) một hình ảnh vào tài liệu. Luôn đi kèm thuộc tính `src` (đường dẫn) và `alt` (văn bản thay thế).                                                                                |
| [`<picture>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture), [`<source>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source) | Khung chứa `<picture>` cung cấp nhiều thẻ `<source>` để trình duyệt tự chọn phiên bản ảnh phù hợp nhất (dựa trên kích thước màn hình hoặc định dạng hỗ trợ), và một thẻ `<img>` làm dự phòng. |
| [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)                                                                                     | Nhúng nội dung âm thanh. Có thể kết hợp thẻ `<source>` để cung cấp các định dạng file khác nhau (mp3, ogg).                                                                                   |
| [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)                                                                                     | Nhúng trình phát video. Các thuộc tính hữu ích: `controls` (hiện nút bấm), `autoplay` (tự động chạy), `loop` (lặp lại), `muted` (tắt tiếng).                                                  |
| [`<track>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track)                                                                                     | Dùng bên trong `<audio>` hoặc `<video>` để thêm các file phụ đề (định dạng WebVTT).                                                                                                           |
| [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe)                                                                                   | Nhúng một trang web HTML khác, bản đồ (Google Maps), hoặc video (YouTube) vào trang hiện tại.                                                                                                 |

[⬆ Quay lại Mục lục](#-mục-lục-table-of-contents)

#### 4.5. Bảng (Tables)

| Thẻ & thuộc tính                                                                                                                                                      | Chức năng                                                                                                                                                       |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)                                                                                          | Khung bao bọc đại diện cho dữ liệu dạng bảng (tabular data),. Không được sử dụng bảng cho mục đích dàn trang (layout).                                          |
| [`<caption>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/caption)                                                                                      | Tiêu đề hoặc chú thích của bảng. Phải là phần tử con đầu tiên của `<table>`,.                                                                                   |
| [`<colgroup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/colgroup) / [`<col>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/col)         | Định nghĩa một nhóm các cột (`<colgroup>`) và từng cột cụ thể (`<col>`) bên trong bảng để dễ dàng áp dụng CSS chung.                                            |
| [`<thead>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/thead)                                                                                          | Gom nhóm phần đầu của bảng, thường chứa các thẻ tiêu đề cột,.                                                                                                   |
| [`<tbody>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody)                                                                                          | Gom nhóm phần thân chứa dữ liệu chính của bảng,.                                                                                                                |
| [`<tfoot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tfoot)                                                                                          | Gom nhóm phần chân bảng, thường dùng để chứa thông tin tóm tắt hoặc tổng kết (ví dụ: tính tổng một cột),.                                                       |
| [`<tr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr)                                                                                                | Định nghĩa một hàng ngang trong bảng.                                                                                                                           |
| [`<th>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/th)                                                                                                | Định nghĩa một ô tiêu đề của cột hoặc hàng. Thuộc tính `scope` (`row`, `col`, `rowgroup`, `colgroup`) giúp xác định rõ ô tiêu đề này áp dụng cho hàng/cột nào,. |
| [`<td>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td)                                                                                                | Định nghĩa một ô chứa dữ liệu bình thường trong bảng,.                                                                                                          |
| [`colspan`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td#colspan) / [`rowspan`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td#rowspan) | Thuộc tính dùng trên `<th>` và `<td>` để gộp các ô theo chiều ngang (`colspan`) hoặc chiều dọc (`rowspan`).                                                     |

[⬆ Quay lại Mục lục](#-mục-lục-table-of-contents)

#### 4.6. Biểu mẫu (Forms)

| Thẻ & thuộc tính                                                                                                                                                    | Chức năng                                                                                                                                                            |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)                                                                                          | Thẻ bao bọc toàn bộ biểu mẫu. Chứa các thuộc tính quản lý việc gửi dữ liệu: `action` (URL xử lý) và `method` (cách thức gửi: GET/POST),.                             |
| [`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label)                                                                                        | Chú thích cho các trường nhập liệu. Dùng thuộc tính `for` trỏ tới `id` của `<input>` để tạo liên kết. Khi bấm vào label, input tương ứng sẽ được focus,.             |
| [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)                                                                                        | Thẻ nhập liệu đa năng nhất. Thuộc tính `type` định nghĩa giao diện nhập: `text`, `password`, `email`, `radio`, `checkbox`, `file`, `date`, `color`, `number`, v.v.,. |
| [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)                                                                                  | Tạo khu vực nhập văn bản nhiều dòng. Sử dụng thuộc tính `rows` và `cols` để kiểm soát kích thước hiển thị.                                                           |
| [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) / [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option)     | `<select>` tạo một menu xổ xuống (dropdown), chứa các thẻ `<option>` đại diện cho từng lựa chọn.                                                                     |
| [`<optgroup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/optgroup)                                                                                  | Gom nhóm các `<option>` lại với nhau bên trong `<select>`, sử dụng thuộc tính `label` để đặt tên nhóm, (tham khảo cách dùng nhóm).                                   |
| [`<fieldset>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset) / [`<legend>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/legend) | `<fieldset>` đóng khung và gom nhóm các trường có liên quan. `<legend>` đặt tiêu đề hiển thị trên đường viền của `<fieldset>` đó.                                    |
| [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)                                                                                      | Nút bấm thao tác. Có 3 loại `type`: `submit` (gửi form mặc định), `reset` (xóa trắng form), và `button` (không có hành vi mặc định, thường dùng với JS),.            |
| [`<output>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/output)                                                                                      | Hiển thị kết quả tính toán của ứng dụng hoặc từ hành động của người dùng.                                                                                            |
| [`<progress>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/progress) / [`<meter>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meter)   | `<progress>` hiển thị tiến độ công việc (progress bar). `<meter>` hiển thị một giá trị trong một khoảng xác định (như dung lượng ổ cứng, đánh giá điểm).             |

##### Các thuộc tính kiểm tra tính hợp lệ (Form Validation Attributes) phổ biến trên thẻ `<input>`

| Thẻ & thuộc tính                                                                                                                                                                                                                    | Chức năng                                                                                           |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------- |
| [`required`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/required)                                                                                                                                                 | Bắt buộc người dùng phải nhập/chọn giá trị mới được gửi form.                                       |
| [`readonly`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/readonly)                                                                                                                                                 | Chỉ cho phép đọc, người dùng không thể chỉnh sửa giá trị.                                           |
| [`disabled`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/disabled)                                                                                                                                                 | Vô hiệu hóa thẻ, không thể tương tác và giá trị cũng không được gửi đi cùng form.                   |
| [`placeholder`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/placeholder)                                                                                                                                           | Đoạn chữ mờ gợi ý nội dung nhập liệu.                                                               |
| [`pattern`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/pattern)                                                                                                                                                   | Sử dụng biểu thức chính quy (Regular Expression) để ép buộc định dạng dữ liệu nhập vào.             |
| [`min`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/min) / [`max`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/max) / [`step`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/step) | Quy định giá trị nhỏ nhất, lớn nhất và bước nhảy (thường dùng cho input dạng `number` hoặc `date`). |

[⬆ Quay lại Mục lục](#-mục-lục-table-of-contents)

#### 4.7. Tương tác & Hình ảnh có chú thích (Interactive & Semantic Elements)

| Thẻ & thuộc tính                                                                                                                                                        | Chức năng                                                                                                                                                                                                                                                                         |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`<details>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details) / [`<summary>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/summary)     | Tạo một khối nội dung có thể thu gọn / mở rộng (accordion). `<summary>` đóng vai trò là tiêu đề luôn hiển thị. Bấm vào `<summary>` sẽ ẩn/hiện phần nội dung còn lại. Từ năm 2020, có thể dùng thuộc tính `name` để tạo các accordion độc quyền (mở cái này thì tự đóng cái kia),. |
| [`<dialog>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog)                                                                                          | Khởi tạo một hộp thoại (modal, popup window) chuyên dụng. Thường kết hợp với JavaScript (các hàm `show()`, `showModal()`, `close()`) để điều khiển,.                                                                                                                              |
| [`<figure>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figure) / [`<figcaption>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figcaption) | `<figure>` bao bọc một nội dung độc lập (như hình ảnh, sơ đồ, đoạn code). `<figcaption>` cung cấp phụ đề/chú thích cho nội dung bên trong `<figure>`,.                                                                                                                            |

[⬆ Quay lại Mục lục](#-mục-lục-table-of-contents)

#### 4.8. Thuộc tính toàn cục (Global Attributes)

| Thẻ & thuộc tính                                                                                                                                                       | Chức năng                                                                                                                                                      |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`class`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/class) và [`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/id) | Định danh phần tử. `class` dùng cho nhiều phần tử để áp dụng CSS chung, còn `id` phải là duy nhất trên toàn bộ trang (dùng cho JS hoặc làm liên kết neo).      |
| [`data-*`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/data-*) (Custom data attributes)                                                        | Cho phép nhà phát triển lưu trữ dữ liệu tùy chỉnh ngay trên thẻ HTML để JavaScript có thể đọc và thao tác (ví dụ: `data-user-id="123"`).                       |
| [`title`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/title)                                                                                   | Chứa thông tin cố vấn/mô tả. Khi người dùng di chuột (hover) qua phần tử, nó sẽ hiện ra một hộp tooltip nhỏ.                                                   |
| [`tabindex`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/tabindex)                                                                             | Quản lý việc người dùng dùng phím `Tab` trên bàn phím để điều hướng. Bằng 0 là theo thứ tự mặc định, -1 là không cho phép tab tới, số dương là thứ tự ưu tiên. |
| [`hidden`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/hidden)                                                                                 | Ẩn phần tử hoàn toàn khỏi giao diện hiển thị của trình duyệt.                                                                                                  |
| [`contenteditable`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/contenteditable)                                                               | Cho phép người dùng chỉnh sửa trực tiếp nội dung của thẻ HTML ngay trên trình duyệt (giống như đang gõ Word).                                                  |
| [`draggable`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/draggable)                                                                           | Cho phép người dùng dùng chuột kéo thả phần tử (kết hợp với Drag and Drop API).                                                                                |

[⬆ Quay lại Mục lục](#-mục-lục-table-of-contents)

---

## 5. Các tiêu chuẩn nâng cao

### 5.1. HTML Chuẩn SEO

**SEO (Search Engine Optimization)** là tập hợp các kỹ thuật tối ưu hóa nhằm giúp trang web đạt thứ hạng cao hơn trên các công cụ tìm kiếm như Google, Bing, Yahoo. Một mã nguồn HTML chuẩn SEO sẽ giúp các bot tìm kiếm "đọc hiểu" nội dung của bạn một cách chính xác nhất.

Các thành phần HTML chuẩn SEO bao gồm:

- **`<title>`:** Đây là thẻ quan trọng nhất. Cần phải chứa từ khóa chính, độ dài ngắn gọn (dưới 60 ký tự) và mang tính mô tả.
- **`<meta name="description">`:** Cung cấp đoạn tóm tắt nội dung trang (khoảng 150-160 ký tự) hiển thị ngay dưới tiêu đề trên trang kết quả tìm kiếm (SERP).
- **Heading Hierarchy (H1-H6):** Phải có duy nhất một thẻ `<h1>` chứa từ khóa trọng tâm nhất. Các thẻ từ `<h2>` đến `<h6>` dùng để phân cấp logic các ý phụ.
- **Thẻ `<a>` (Liên kết):** Thuộc tính `href` phải rõ ràng. Sử dụng anchor text mang ý nghĩa cụ thể thay vì các cụm từ vô nghĩa như "bấm vào đây".
- **Thuộc tính `alt` của thẻ `<img>`:** Cung cấp mô tả văn bản thay thế cho hình ảnh, giúp bot tìm kiếm hiểu ảnh nói về cái gì và hỗ trợ quá trình tìm kiếm hình ảnh.
- **Canonical Link:** Sử dụng `<link rel="canonical" href="...">` giúp tránh gặp lỗi trùng lặp nội dung (duplicate content) khi một trang có nhiều URL khác nhau.
- **Open Graph (Social SEO):** Sử dụng các thẻ `<meta property="og:...">` giúp kiểm soát tốt cách trang web của bạn hiển thị khi được chia sẻ trên các nền tảng mạng xã hội (như Facebook, LinkedIn).

[⬆ Quay lại Mục lục](#-mục-lục-table-of-contents)

### 5.2. Accessibility (A11y) - Khả năng truy cập

Accessibility (viết tắt là A11y) là việc thực hành thiết kế website sao cho **tất cả mọi người đều có thể sử dụng**, bao gồm cả những người khuyết tật (khiếm thị, khó khăn vận động,...) sử dụng các công cụ hỗ trợ như Trình đọc màn hình (Screen Readers).

Các tiêu chuẩn A11y cơ bản trong HTML bao gồm:

1. **Sử dụng Semantic HTML (Ngữ nghĩa):**
   Thay vì dùng toàn thẻ `<div>` vô nghĩa, hãy dùng đúng thẻ `<header>`, `<nav>`, `<main>`, `<footer>`. Máy đọc màn hình dựa vào đây để giúp người khiếm thị điều hướng nhanh giữa các khu vực của trang web.
2. **Luôn có thuộc tính `alt` cho hình ảnh:**
   Thẻ `<img>` bắt buộc phải có `alt="..."`. Nếu ảnh bị lỗi hoặc người dùng khiếm thị dùng phần mềm đọc, thuộc tính `alt` sẽ giải thích cho họ biết bức ảnh đó chứa nội dung gì. _(Lưu ý: Nếu ảnh chỉ để trang trí, hãy để `alt=""` để máy đọc bỏ qua)_.
3. **Liên kết nhãn (Label) rõ ràng cho Form:**
   Mọi thẻ `<input>` đều phải có một `<label>` đi kèm. Sử dụng thuộc tính `for` trên `<label>` khớp với thuộc tính `id` trên `<input>`. Việc này giúp máy đọc hiểu input đó yêu cầu nhập gì, đồng thời giúp người dùng click vào chữ cũng chọn được ô nhập liệu.
4. **Cấu trúc Heading (`<h1>` đến `<h6>`) mạch lạc:**
   Không dùng thẻ heading chỉ để chữ to ra (đó là việc của CSS). Heading phải thể hiện đúng cấu trúc dàn ý của trang. Chỉ nên có 1 thẻ `<h1>` trên mỗi trang.
5. **Thuộc tính ARIA (Accessible Rich Internet Applications):**
   Với các tương tác giao diện phức tạp (như Tabs, Modal, Dropdown), HTML thường không đủ ngữ nghĩa. Khi đó ta dùng các thuộc tính `aria-*` (như `aria-hidden`, `aria-label`, `aria-expanded`, `role="..."`) để truyền đạt trạng thái của giao diện cho công cụ hỗ trợ.

_Ví dụ thực tế:_

```html
<!-- Nút đóng chỉ có icon, cần nhãn mô tả cho người khiếm thị -->
<button aria-label="Đóng bảng tin">X</button>

<!-- Một thanh tiến trình tùy chỉnh cần role và các thuộc tính trạng thái -->
<div
  role="progressbar"
  aria-valuenow="70"
  aria-valuemin="0"
  aria-valuemax="100"
>
  70% hoàn thành
</div>
```

[⬆ Quay lại Mục lục](#-mục-lục-table-of-contents)

### 5.3. Comments - Chú thích mã nguồn

- **Cú pháp:** `<!-- Nội dung chú thích -->`.
- **Vai trò:** Trình duyệt sẽ bỏ qua phần này khi hiển thị, giúp lập trình viên ghi chú các luồng logic, đánh dấu các khu vực của trang hoặc dùng để tạm thời ẩn một đoạn mã nguồn.

**Thế nào là một Comment tốt?**

- **Giải thích "Tại sao" (Why), không giải thích "Cái gì" (What):** Nên tránh mô tả lại những gì đoạn thẻ HTML đã tự nói lên rõ ràng.
- **Đánh dấu các khu vực lớn:** Có ích trong việc điều hướng nhanh khi thao tác trong file mã nguồn dài.
- **Cảnh báo hoặc ghi chú bảo trì:** Giúp lưu ý cho đồng nghiệp (hoặc chính bản thân sau này) các lỗi tiềm ẩn hoặc lý giải tại sao một đoạn mã được viết theo một cách "kỳ lạ".

_Ví dụ tốt:_

```html
<!-- START: Header Navigation -->
<nav>...</nav>

<!-- Fix: Buộc phải dùng div ở đây để tương thích với thư viện Slider XYZ -->
<div class="slider-hack">...</div>
```

[⬆ Quay lại Mục lục](#-mục-lục-table-of-contents)
