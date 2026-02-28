# Tài Liệu Ghi Chú: HTML, CSS và JavaScript

## I. Giới Thiệu Tổng Quan

**HTML, CSS và JavaScript** là ba ngôn ngữ duy nhất mà trình duyệt web có thể hiểu được.

| Công Nghệ  | Viết Tắt                  | Định Nghĩa                      | Vai Trò             |
| ---------- | ------------------------- | ------------------------------- | ------------------- |
| HTML       | HyperText Markup Language | Ngôn ngữ đánh dấu siêu văn bản  | Cấu trúc            |
| CSS        | Cascading Style Sheets    | Các tập tin định kiểu theo tầng | Thẩm mỹ             |
| JavaScript | —                         | Ngôn ngữ lập trình              | Tính năng tương tác |

## II. HTML - Ngôn Ngữ Đánh Dấu Siêu Văn Bản

### 1. Giới thiệu và Làm quen với HTML

**HTML không phải là ngôn ngữ lập trình** vì nó không chứa logic lập trình (như if...else...).

### 1.1. Cú Pháp Cơ Bản

Cú pháp HTML gồm **thẻ mở** và **thẻ đóng**:

```html
<h1>Đây là cú pháp cơ bản của HTML</h1>
```

- `<h1>` — thẻ mở
- `</h1>` — thẻ đóng

### 1.2. Cấu Trúc Tiêu Chuẩn

Tài liệu HTML có phần mở rộng **.html** (ví dụ: index.html, product.html).

**Cấu trúc tiêu chuẩn**:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <!-- Các thẻ meta ở đây -->
  </head>
  <body>
    <!-- Nội dung trang web ở đây -->
  </body>
</html>
```

**Thành Phần**:

- **`<!DOCTYPE html>`** — Khai báo tiêu chuẩn HTML5
- **`<html lang="en">...</html>`** — Phần tử gốc (root) cao cấp nhất; `lang="en"` khai báo ngôn ngữ
- **`<head>...</head>`** — Chứa metadata, tiêu đề, mô tả SEO, liên kết CSS
- **`<body>...</body>`** — Chứa toàn bộ nội dung hiển thị

#### 1.2.1. Các thẻ Meta

Thẻ meta bổ sung thông tin cho trang web hỗ trợ công cụ tìm kiếm, SEO và hiển thị.

| Thẻ                                                                        | Mục Đích                                    |
| -------------------------------------------------------------------------- | ------------------------------------------- |
| `<meta charset="UTF-8" />`                                                 | Khai báo bảng mã ký tự (tránh lỗi hiển thị) |
| `<title>Tiêu đề</title>`                                                   | Khai báo tiêu đề trang web                  |
| `<meta name="viewport" content="width=device-width, initial-scale=1.0" />` | Hỗ trợ hiển thị trên nhiều thiết bị         |

### 1.3. HTML Boilerplate

**Boilerplate** là những đoạn code tiêu chuẩn để tái sử dụng thay vì viết lặp lại.

### 1.4. Thuộc Tính HTML

Thuộc tính có dạng `key="value"` và được **viết trong thẻ mở**:

```html
<tag attribute="value">Content</tag>
```

- Mỗi thẻ HTML có thuộc tính riêng (không hoạt động ở thẻ khác)
- **Thuộc tính toàn cục** (Global Attributes): `lang`, `hidden`, `title`, `class`, `id`,...

### 1.5. Quy Tắc Viết Mã HTML

- ✓ Viết cú pháp mở và đóng thẻ trước, sau đó viết nội dung
- ✓ Sử dụng thụt lề (một Tab) cho các thẻ con
- ✓ Tránh viết dư thừa khoảng trắng và dấu ngắt dòng
- ✓ Sử dụng dấu ngắt dòng hợp lý, đảm bảo code dễ đọc
- ✓ Đặt thẻ đúng vị trí (ví dụ: `<li>` là con trực tiếp của `<ul>`, `<ol>`)
- ✓ Luôn sử dụng `https` cho URL trong thuộc tính `href`

## 2. Các thẻ trong HTML
