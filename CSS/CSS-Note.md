# CSS Note - Made By trminhhieu (có dùng AI)

**Mục lục:**

1. CSS là gì? Vai trò, điểm mạnh và các quy tắc
2. Đơn vị và Màu sắc trong CSS
3. Bố cục giao diện (Modern Layout)
4. Hiệu ứng Animation & Làm đẹp Hình ảnh
5. Thiết kế Đáp ứng (Responsive Design)
6. Cơ chế hiển thị (Browser Rendering)
7. Tiêu chuẩn thiết kế (Design System)

---

## 1. CSS là gì? Vai trò, điểm mạnh và các quy tắc

### CSS là gì?

**CSS (Cascading Style Sheets)** là một ngôn ngữ stylesheet được sử dụng để mô tả cách trình bày và hiển thị của một tài liệu viết bằng HTML hoặc XML (bao gồm cả SVG, MathML). Nó xác định cách các phần tử hiển thị trên màn hình, trên giấy, hoặc qua các phương tiện truyền thông khác.

### Vai trò và Điểm mạnh

- **Tính cốt lõi:** CSS là một trong những ngôn ngữ cốt lõi của nền tảng web mở (open web) và được chuẩn hóa trên toàn bộ các trình duyệt.
- **Tách biệt nội dung và giao diện:** Giúp mã HTML gọn gàng, tách biệt phần dữ liệu (content) khỏi phần thiết kế (design).
- **Tính xếp tầng (Cascade):** Đây là sức mạnh của CSS, giúp giải quyết xung đột khi có nhiều quy tắc cùng tác động lên một phần tử thông qua mức độ ưu tiên (specificity) và sự kế thừa (inheritance).

### Các quy tắc và Cấu trúc

- **BEM (Block Element Modifier):** Là một phương pháp luận đặt tên class độc lập giúp code dễ đọc và dễ bảo trì.
- **CSS Nesting (CSS lồng nhau):** CSS hiện đại hỗ trợ tính năng nesting nguyên bản, cho phép lồng các khối CSS vào nhau giống như Sass để tạo ra mã nguồn theo cấu trúc module và dễ bảo trì. Lưu ý rằng CSS Nesting gốc không hỗ trợ nối chuỗi (concatenation) trực tiếp để tạo class BEM như các preprocessor.

---

## 2. Đơn vị và Màu sắc trong CSS

### 2.1. Đơn vị đo lường (Values and Units)

CSS cung cấp hệ thống đơn vị đo lường phong phú cho từng trường hợp sử dụng:

- **Đơn vị tuyệt đối (Absolute):** `px`, `cm`, `mm`.
- **Đơn vị tương đối (Relative):** Tương đối theo font chữ như `rem`, `em`, `ch`, hoặc tương đối theo khung nhìn màn hình (viewport) như `vw`, `vh`, `vmin`, `vmax`.
- **Đơn vị cho Layout:** `fr` (fraction) dùng riêng trong CSS Grid để chia tỷ lệ không gian trống.
- **Hàm tính toán (Math functions):** CSS cho phép tính toán trực tiếp thông qua các hàm như `calc()`, `min()`, `max()`, và `clamp()`.

### 2.2. Màu sắc (Colors)

Màu sắc trong CSS rất mạnh mẽ và hỗ trợ nhiều không gian màu để phục vụ thiết kế hiển thị:

- **Định dạng cơ bản:** Hexadecimal (VD: `#bada55`), RGB (`rgb()`).
- **Định dạng trực quan:** HSL (Hue, Saturation, Lightness) và HWB, giúp dễ dàng tạo bảng màu bằng cách xoay vòng màu (color wheel).
- **Màu dải rộng (Wide Gamut):** Hỗ trợ các chuẩn không gian màu lớn như `lab()`, `lch()`, `oklab()`, `oklch()`, và hàm `color()` cho hiển thị độ phân giải cao.
- **Relative Color Syntax (Cú pháp màu tương đối):** Tính năng mới cho phép tính toán màu sắc phái sinh (sáng hơn, tối hơn, trong suốt hơn) dựa trên một màu gốc có sẵn (`origin color`). Bạn cũng có thể dùng hàm `color-mix()` để pha trộn màu và `light-dark()` cho dark/light mode.

---

## 3. Bố cục giao diện (Modern Layout)

CSS hiện đại xoay quanh 2 hệ thống layout cốt lõi giúp chia cột và căn chỉnh phần tử một cách linh hoạt, chia sẻ chung một hệ thống căn chỉnh (CSS box alignment).

### 3.1. Flexbox (Flexible Box Layout)

- **Bản chất:** Là hệ thống bố cục **một chiều (one-dimensional)**, chuyên xử lý phần tử theo một hàng ngang (row) hoặc một cột dọc (column) nhưng không làm cả hai cùng lúc.
- **Ứng dụng:** Căn giữa phần tử, làm thanh điều hướng (navigation menu), hoặc form điều khiển.
- **Cơ chế:** Điều khiển không gian dựa trên 3 thuộc tính chính của _flex items_: `flex-grow` (tỷ lệ phình to), `flex-shrink` (tỷ lệ co lại) và `flex-basis` (kích thước gốc).

### 3.2. CSS Grid Layout

- **Bản chất:** Là hệ thống bố cục **hai chiều (two-dimensional)**, quản lý layout trên cả hàng và cột đồng thời.
- **Ứng dụng:** Cực kỳ mạnh mẽ để chia cấu trúc lớn của trang web (Header, Sidebar, Main, Footer).
- **Cơ chế:** Có thể đặt tên các vùng thông qua `grid-template-areas` hoặc vẽ các đường lưới (grid lines) để kiểm soát vị trí phần tử một cách chính xác. Kết hợp cùng đơn vị `fr` và hàm `minmax()` để tạo lưới linh hoạt.

---

## 4. Hiệu ứng Animation và Tối ưu Hình ảnh

### 4.1. Hiệu ứng chuyển động (Animations)

- **Transitions:** Chuyển đổi trạng thái từ A sang B một cách mượt mà (vd: đổi màu khi `:hover`) thông qua hàm gia tốc độ (easing functions).
- **Keyframe Animations:** Quy tắc `@keyframes` cho phép tự định nghĩa chuỗi chuyển động phức tạp với nhiều điểm dừng (waypoints) thông qua CSS Animations.

### 4.2. Tối ưu hiển thị Hình ảnh

- **CSS Gradients:** Tạo màu nền dạng chuyển sắc tự động bằng trình duyệt mà không cần tải ảnh thật.
- **Masking & Clipping:** Giúp che giấu hoặc cắt xén phần tử thành các hình thù tùy biến (tam giác, đa giác, hình tròn) thông qua module `mask` và `clip-path`.
- **Filters:** Chỉnh sửa độ tương phản, làm mờ, hay đổ bóng đồ họa của ảnh ngay trên trình duyệt thông qua CSS Filter Effects.

---

## 5. Thiết kế Đáp ứng (Responsive Design)

Trang web cần phải hiển thị tốt trên mọi màn hình từ di động đến máy tính.

- **Media Queries (`@media`):** Điều kiện kiểm tra thông số của màn hình (chiều rộng, cấu hình màu, v.v.) để áp dụng các khối CSS tương ứng. Đây là công cụ nền tảng để tạo responsive layout.
- **Container Queries (`@container`):** Tính năng nâng cao, cho phép phần tử con thay đổi kiểu dáng dựa vào **kích thước của phần tử chứa nó (container)** thay vì dựa vào toàn bộ màn hình trình duyệt (viewport).

---

## 6. Cơ chế hiển thị (Browser Rendering)

Trình duyệt phân tích HTML và CSS thông qua **Visual Formatting Model**.

- **Box Model (Mô hình hộp):** Mọi phần tử đều được vẽ thành một hình hộp chữ nhật bao gồm 4 lớp: `Content` (Nội dung), `Padding` (Vùng đệm), `Border` (Viền) và `Margin` (Lề).
- **Box Tree & Formatting Contexts:** Trình duyệt xây dựng _Box Tree_ dựa theo ngữ cảnh hiển thị. Ví dụ: Khối có `display: flex` sẽ tạo ra một _Flex formatting context_ cho các thành phần con.
- **Luồng xử lý (CSS value processing):** Thuộc tính trải qua nhiều bước tính toán: Từ giá trị khai báo ban đầu (Declared) -> Xếp tầng (Cascaded) -> Giá trị định sẵn (Specified) -> Toán học hóa (Computed value) -> Tính toán Bố cục (Used value / Reflow) -> Vẽ pixel ra màn hình (Actual value / Repaint).
- Trình duyệt tối ưu chuyển động bằng bước hòa trộn (Compositing and blending), rất hiệu quả khi kết hợp hiệu ứng CSS Transform.

---

## 7. Tiêu chuẩn thiết kế (Design System)

CSS cung cấp các công cụ module hóa để bạn chuẩn hóa khoảng cách, màu sắc và typography đồng nhất trên toàn dự án:

- **Color (Biến màu sắc):** Mọi mã màu nên được đưa vào **CSS Custom Properties** (hay còn gọi là Biến CSS, vd: `--primary-color: blue;`). Chúng có thể được tái sử dụng qua hàm `var()`, kế thừa theo cây DOM và kết hợp hàm `light-dark()` cho các theme tĩnh/động.
- **Spacing (Khoảng cách):** Thống nhất mô hình hộp và sử dụng thuộc tính `gap` (cùng `row-gap`, `column-gap`) để định hướng khoảng cách giữa các khối (flex/grid) thay vì lạm dụng margin cứng.
- **Typography (Hệ thống chữ):** Áp dụng linh hoạt Module CSS Fonts, đặc biệt là **Variable Fonts** – cho phép tinh chỉnh độ đậm, nghiêng, độ giãn chữ không giới hạn dựa trên chỉ một file font duy nhất, rất nhẹ và hiệu suất cao. Kích thước chữ nên kết hợp với đơn vị `rem` và độ cao dòng (`line-height`) đồng bộ.
