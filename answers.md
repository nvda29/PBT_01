### PHẦN A
### CÂU A1
Câu A1 — HTTP & Browser

Nguồn tham chiếu:

File: 01_introduction_html_universe.md
Phần: "Cuộc Hành Trình 0.3 Giây Xuyên Đại Dương" và "1.3 Browser Rendering — Từ Code thành Hình ảnh"
1. Các bước khi truy cập https://shopee.vn:

Dựa trên tài liệu, trình tự các bước như sau:

Trình duyệt gửi request từ laptop qua router WiFi
Request đi qua nhà mạng Internet (VNPT)
Thực hiện DNS lookup để tìm địa chỉ IP của server
Request được gửi đến server (data center)
Server xử lý yêu cầu của người dùng
Server trả về response (HTML, CSS, JavaScript)
Trình duyệt parse HTML → tạo DOM
Tải thêm CSS và JavaScript
Render trang web và hiển thị giao diện cho người dùng

Trích dẫn từ tài liệu:

“Request của Minh xuất phát từ laptop → đi qua router WiFi…”
“Server xử lý…”
“Chrome nhận file HTML, CSS, JS → render ra giao diện”
2. Tab Network trong DevTools hiển thị:

Tab Network cho phép quan sát toàn bộ quá trình request/response giữa trình duyệt và server, bao gồm:

Danh sách các request (HTML, CSS, JS, hình ảnh…)
Status Code (200, 404, 500…)
Thời gian tải của từng request
Tổng thời gian load trang
Loại tài nguyên (document, stylesheet, script…)

Trích dẫn từ tài liệu:

“Network | Xem requests/responses | Website tải chậm — file nào nặng nhất?”
### CÂU A2
Câu A2 — Semantic HTML

Nguồn tham chiếu:

File: 04_semantic_html.md
Phần: Semantic HTML và SEO
Trang web bị SEO thấp vì:

Trang web sử dụng quá nhiều thẻ <div> thay vì các thẻ semantic HTML5, khiến cho:

Google không hiểu rõ cấu trúc nội dung
Screen reader khó đọc
Mất ý nghĩa ngữ nghĩa (semantic meaning)
Các lỗi semantic (ít nhất 4 lỗi):
Dùng <div class="header"> thay vì <header>
Menu không dùng <nav>
Sản phẩm không dùng <article>
Không có <main> để bao nội dung chính
Tiêu đề sản phẩm dùng <div> thay vì <h1> hoặc <h2>
Giá sản phẩm không có ý nghĩa semantic (nên dùng <p> hoặc <strong>)
Footer dùng <div> thay vì <footer>
Code sau khi sửa (semantic đúng):
<header>
    <h1>ShopTLU</h1>
    <nav>
        <a href="/">Trang chủ</a>
        <a href="/products">Sản phẩm</a>
    </nav>
</header>

<main>
    <section>
        <article>
            <h2>iPhone 16 Pro</h2>
            <p><strong>25.990.000đ</strong></p>
            <figure>
                <img src="iphone.jpg" alt="iPhone 16 Pro">
            </figure>
        </article>
    </section>
</main>

<footer>
    <p>© 2026 ShopTLU</p>
</footer>

### CÂU A3
Nguồn tham chiếu:
File: 03_block_inline.md
Phần: Block elements và Inline elements

Kết quả hiển thị (mô tả bằng text)

Hộp 1
Text A Text B
Hộp 2
Text C Text D
Hộp 3

Giải thích

Trong HTML, các phần tử được chia thành hai nhóm chính: block và inline.

<div> là block element:
Luôn chiếm toàn bộ chiều ngang của dòng
Luôn tự động xuống dòng sau mỗi phần tử
<span> và <strong> là inline elements:
Chỉ chiếm đúng phần nội dung bên trong
Không tạo xuống dòng mới, hiển thị trên cùng một dòng

### CÂU A4
Nguồn tham chiếu:
File: 05_tables_hyperlinks.md
Phần: Table structure (thead, tbody, tfoot) và best practices

1. Sự khác nhau giữa <thead>, <tbody>, <tfoot>

Trong HTML table, dữ liệu được chia thành 3 phần chính để tổ chức rõ ràng:

<thead> (table head):
Chứa phần tiêu đề của bảng
Thường gồm các cột header (<th>)
Giúp xác định ý nghĩa từng cột dữ liệu
<tbody> (table body):
Chứa toàn bộ dữ liệu chính của bảng
Là phần nội dung chính mà người dùng cần xem
<tfoot> (table foot):
Chứa phần tổng kết hoặc kết luận của bảng
Ví dụ: tổng tiền, tổng số lượng, ghi chú cuối bảng
2. Tại sao không nên dùng table để tạo layout trang web

Không nên dùng table để xây dựng bố cục trang web vì các lý do sau:

Không đúng mục đích sử dụng
Table được thiết kế để hiển thị dữ liệu dạng bảng, không phải để dựng layout giao diện.
Khó responsive trên thiết bị di động
Layout bằng table rất khó điều chỉnh khi hiển thị trên màn hình nhỏ như điện thoại.
Code khó bảo trì và mở rộng
Khi layout phức tạp, table làm code rối và khó chỉnh sửa so với CSS layout (Flexbox, Grid).
Không tối ưu SEO và semantic HTML
Search engine khó hiểu cấu trúc trang khi dùng table sai mục đích, ảnh hưởng đến SEO

### CÂU C1
Nguồn tham chiếu:
File: 04_semantic_html.md, 05_tables_hyperlinks.md
Phần: Semantic layout structure, tables, navigation structure
Cấu trúc HTML (chỉ skeleton + comment)
<!DOCTYPE html>
<html lang="vi">
<head>
    <!-- Metadata của trang -->
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Chi tiết sản phẩm</title>
</head>

<body>

    <header>
        <!-- Header chứa logo và điều hướng chính -->
        <nav>
            <!-- nav vì đây là khu vực điều hướng chính -->
            <a href="/">Trang chủ</a>
            <a href="/phone">Điện thoại</a>
            <a href="/product">Sản phẩm</a>
        </nav>
    </header>

    <nav aria-label="breadcrumb">
        <!-- breadcrumb thể hiện đường dẫn có thứ tự -->
        <ol>
            <li><a href="/">Trang chủ</a></li>
            <li><a href="/phone">Điện thoại</a></li>
            <li>iPhone 16</li>
        </ol>
    </nav>

    <main>

        <section>
            <!-- Khu vực ảnh sản phẩm -->
            <figure>
                <!-- Ảnh 1 -->
                <img src="img1.jpg" alt="Ảnh sản phẩm 1">
                <img src="img2.jpg" alt="Ảnh sản phẩm 2">
                <img src="img3.jpg" alt="Ảnh sản phẩm 3">
                <img src="img4.jpg" alt="Ảnh sản phẩm 4">
                <img src="img5.jpg" alt="Ảnh sản phẩm 5">
                <!-- figure dùng để nhóm hình ảnh có ngữ nghĩa -->
            </figure>
        </section>

        <section>
            <!-- Thông tin sản phẩm -->
            <article>
                <!-- article vì đây là nội dung độc lập của sản phẩm -->

                <h1>Tên sản phẩm</h1> <!-- tiêu đề chính -->
                <p>Giá sản phẩm</p> <!-- thông tin giá -->
                <p>Đánh giá sao</p> <!-- rating -->
                <p>Mô tả sản phẩm</p> <!-- mô tả -->
            </article>
        </section>

        <section>
            <!-- Bảng thông số kỹ thuật -->
            <table>
                <!-- table dùng để hiển thị dữ liệu dạng bảng -->
                <thead>
                    <tr>
                        <th>Thông số</th>
                        <th>Chi tiết</th>
                    </tr>
                </thead>

                <tbody>
                    <tr>
                        <td>Màn hình</td>
                        <td>6.7 inch</td>
                    </tr>
                    <tr>
                        <td>Chip</td>
                        <td>A18</td>
                    </tr>
                </tbody>

                <tfoot>
                    <!-- có thể dùng cho ghi chú hoặc tổng kết -->
                    <tr>
                        <td colspan="2">Thông tin có thể thay đổi</td>
                    </tr>
                </tfoot>
            </table>
        </section>

        <section>
            <!-- Khu vực đánh giá / bình luận -->
            <article>
                <h2>Đánh giá người dùng</h2>
                <p>Bình luận 1</p>
                <p>Bình luận 2</p>
            </article>
        </section>

    </main>

    <aside>
        <!-- Sidebar sản phẩm tương tự -->
        <section>
            <h3>Sản phẩm tương tự</h3>
            <ul>
                <li>Sản phẩm A</li>
                <li>Sản phẩm B</li>
                <li>Sản phẩm C</li>
            </ul>
        </section>
    </aside>

    <footer>
        <!-- Footer chứa thông tin cuối trang -->
        <p>© 2026 ShopTLU</p>
    </footer>

</body>
</html>

### CÂU C2
Nguồn tham chiếu:
File: 04_semantic_html.md
Phần: Semantic HTML, SEO và Accessibility
Semantic HTML không phải là “thêm thẻ cho rườm rà”, mà là cách xây dựng cấu trúc trang web có ý nghĩa rõ ràng cho cả máy tìm kiếm lẫn công nghệ hỗ trợ người dùng. Việc chỉ dùng <div> cho toàn bộ giao diện sẽ khiến trang web mất đi ngữ nghĩa, dẫn đến giảm hiệu quả SEO và gây khó khăn cho accessibility.

Về mặt kỹ thuật thứ nhất, SEO (Search Engine Optimization), các công cụ tìm kiếm như Google dựa vào cấu trúc HTML để hiểu nội dung trang web. Khi sử dụng các thẻ semantic như <header>, <nav>, <main>, <article>, Google có thể phân biệt rõ đâu là nội dung chính, đâu là điều hướng, đâu là nội dung phụ. Nếu chỉ dùng <div> với class, Google phải “đoán” cấu trúc, làm giảm độ chính xác trong việc index nội dung.

Về mặt kỹ thuật thứ hai, accessibility, các công nghệ hỗ trợ như screen reader (dành cho người khiếm thị) sử dụng semantic HTML để đọc nội dung đúng ngữ cảnh. Ví dụ, khi gặp <nav>, screen reader sẽ hiểu đây là khu vực điều hướng; hoặc <button> sẽ được hiểu là một hành động có thể tương tác. Nếu chỉ dùng <div>, người dùng sẽ không có được ngữ cảnh này.

Ví dụ cụ thể: một trang thương mại điện tử dùng <article> cho mỗi sản phẩm giúp Google hiểu đây là các thực thể độc lập. Điều này giúp cải thiện hiển thị trên kết quả tìm kiếm, ví dụ hiển thị rich snippet (giá, đánh giá sao).

Tuy nhiên, <div> vẫn có vai trò hợp lý trong thực tế, đặc biệt khi không có thẻ semantic phù hợp hoặc khi chỉ dùng để chia layout và styling bằng CSS (ví dụ: wrapper container, grid layout). Khi đó, <div> kết hợp với class vẫn là lựa chọn đúng.

Tóm lại, semantic HTML không thay thế <div>, mà bổ sung ý nghĩa cho cấu trúc web, giúp tối ưu SEO, accessibility và khả năng bảo trì code lâu dài.

