PHẦN A — KIỂM TRA ĐỌC HIỂU
Câu A1 (5đ) — HTTP & Browser 
Nguồn tham chiếu Chương 1:01_introduction_html_universe.md
    -Phần Cuộc Hành Trình 0.3 Giây Xuyên Đại Dương
    - 4.3. Developer Tools (F12) — "Kính hiển vi" cho website

    (1). Khi bạn gõ https://shopee.vn vào trình duyệt và nhấn Enter, hãy liệt kê đúng thứ tự ít nhất 5 bước xảy ra (từ DNS lookup đến render).
        1.Request xuất phát từ laptop → đi qua router WiFi
        2.→ Qua nhà mạng VNPT → chạy xuyên cáp quang dưới đáy Thái Bình Dương
        3.→ Đến data center của Meta ở Menlo Park, California, cách 13.000 km
        4.→ Server xử lý: "Người dùng muốn xem Trang chủ Shopee"
        5.→ Response chạy ngược lại: cáp quang → VNPT → router → laptop
        6.→ Chrome nhận file HTML, CSS, JS → render ra giao diện → Người dùng thấy Trang chủ Shopee
    (2)Trong DevTools của Chrome, tab Network cho thấy thông tin gì? Hãy mở một trang web bất kỳ, chụp screenshot tab Network và đánh dấu (vẽ mũi tên/khoanh tròn) vào:
        Status Code của request đầu tiên
        Tổng thời gian load trang
        Một request trả về file CSS

        - tab Network cho thấy các requests và responses
        ![alt text](<Screenshot 2026-04-27 103432.png>)
Câu A2 (5đ) — Semantic HTML
Đọc chương 04, trả lời:Tại sao trang web dưới đây bị Google đánh giá SEO thấp? Liệt kê ít nhất 4 lỗi semantic và sửa lại.
Nguồn tham chiếu: Chương 4: 04_visible_part_html.md
    -Phần Semantic HTML5 — "Thẻ có ý nghĩa"

<div class="header">
    <div class="logo">ShopTLU</div>
    <div class="menu">
        <div><a href="/">Trang chủ</a></div>
        <div><a href="/products">Sản phẩm</a></div>
    </div>
</div>
<div class="main">
    <div class="product">
        <div class="title">iPhone 16 Pro</div>
        <div class="price">25.990.000đ</div>
        <div class="image"><img src="iphone.jpg"></div>
    </div>
</div>
<div class="footer">© 2026 ShopTLU</div>

-Trang web dưới đây được google đánh giá là seo thấp vì 
    . "Div Soup" — Google không hiểu gì
-Các lỗi semantic và sửa lại là:
    .Dùng <div class="header"> khiến cho Google không nhận biết rõ là phần đầu trang dẫn đến giảm khả năng hiểu layout->thay bằng <header>
    .Menu không dùng <nav>
    . Tiêu đề <div class="title">iPhone 16 Pro</div> không dùng thẻ heading(<h1>, <h2>)
    . Ảnh <img src="iphone.jpg"> không có thuộc tính alt 
    class="image"><img src="iphone.jpg">alt="iPhone 16 Pro chính hãng">

Câu A3 (5đ) — Block vs Inline
Nguồn tham chiếu: Chương 4: 04_visible_part_html.md
    - Block vs Inline — Hai loại element cơ bản

Không chạy code, hãy vẽ tay (hoặc mô tả bằng text art) kết quả hiển thị của đoạn HTML sau. Giải thích tại sao.
    <div>Hộp 1</div>
    <span>Text A</span>
    <span>Text B</span>
    <div>Hộp 2</div>
    <span>Text C</span>
    <strong>Text D</strong>
    <div>Hộp 3</div>
    
    ---------Hộp 1----------------------------------------------------------------------------------------------
    ----Text A-------
    ----Text B-------
    ---------Hộp 2----------------------------------------------------------------------------------------------
    ----Text C-------
    ----Text D-------
    ---------Hộp 3----------------------------------------------------------------------------------------------
    -các dòng có chưa <div> là Block,đặc điểm là thường chiếm cả dòng và có thể điều chỉnh height/weight
    - các dòng có chưa <span>, <strong> là Incline, đắc điểm là chỉ chứa nội dung và không thể điều chỉnh height/weight

Câu A4 (5đ) — Table
Đọc chương 05. Giải thích sự khác nhau giữa <thead>, <tbody>, <tfoot>. Tại sao KHÔNG NÊN dùng table để tạo layout trang web? (Ghi rõ ít nhất 3 lý do)
Nguồn tham chiếu: Chương 5-05_tables_hyperlinks.md
    - Phần Table — Bảng dữ liệu

    -Đặc điểm và sự khác nhau giữa <thead>, <tbody>, <tfoot> là:
        .Thẻ <thead> có vai trò header và dùng để chứa tiêu đề cột
        .Thẻ <tbody> có vai trò body và để chứa dữ liệu chính của table
        .Thẻ <tfoot> có vai trò footer để xử lý tổng kết các dữ liệu
    - Không nên dùng table để tạo layout trang web vì:
        .<table> sinh ra để xử lý dữ liệu dạng bảng không phải để xử lý layout
        .Layout bằng table quá phụ thuộc vào các hàng,các cột quá cứng nhắc và khó làm
        .Dùng CSS Grid/Flexbox thay vì dùng table để layout trang sẽ tối ưu hơn


Phần B THỰC HÀNH 
Câu B3:
    Lỗi 1: Dòng 1 — <!DOCTYPE> sai cú pháp — Sửa thành <!DOCTYPE html>
    Lỗi 2: Dòng 3 — Thiếu thuộc tính lang cho <html> — Sửa thành <html lang="vi">
    Lỗi 3: Dòng 5 — Thẻ <title> không đóng — Thêm </title>
    Lỗi 4: Dòng 6 — charset sai "utf8" — Sửa thành "UTF-8"
    Lỗi 5: Dòng 10 — Thẻ <h1> không đóng đúng — Sửa </h1>
    Lỗi 6: Dòng 14 — Thẻ <a> không đóng — Sửa thành </a>
    Lỗi 7: Dòng 14 — href không phải anchor hợp lệ — Sửa thành href="#home"
    Lỗi 8: Dòng 20 — <img> thiếu dấu ngoặc kép và alt — Sửa thành <img src="iphone.jpg" alt="...">
    Lỗi 9: Dòng 22 — Sai nesting thẻ <b> — Đặt <strong> đúng vị trí
    Lỗi 10: Dòng 28 — Table không có thead/tbody — Bổ sung cấu trúc semantic
    Lỗi 11: Dòng 37 — Dùng 2 thẻ <main> — Sửa cái thứ 2 thành <aside>
    Lỗi 12: Dòng 42 — <footer> thiếu thẻ đóng <p> — Thêm </p>
    Lỗi 13: Thiếu semantic cho hình ảnh — Thêm <figure> và <figcaption>
    Lỗi 14: Heading hierarchy sai (h1 → h3) — Sửa thành h1 → h2
    Lỗi 15: Không có alt cho ảnh — Bổ sung để tăng SEO và accessibility

Câu B4: Tiki.vn
    1.Chụp tab Element:
        - 3 thẻ semantic HTML5 mà tiki sử dụng là:
            . Thẻ <html> thẻ gốc của toàn bộ tài liệu 
            . Thẻ <head> chứa metadata (CSS, script,....)
            . Thẻ <body> chứa toàn bộ nội dung hiển thị của trang
        - 2 thẻ mà trang đó KHÔNG dùng đúng semantic (nếu có) là:
            . Sử dụng quá nhiều thẻ div thay cho các thẻ semantic
            . Không sử dụng thẻ <main> tất cả nội dung chính được bọc trong thẻ <div id="__next">
    2.Phân tích table
        - Trang tiki không sử dụng table thay vào đó là các HyperLinks
        Nguồn tham khảo: Chương 5-05_tables_hyperlinks.md
            -Phần HyperLink
    3.Phân tích form 


Phần C: Suy Luận

Câu C1:Bạn được giao thiết kế cấu trúc HTML cho trang chi tiết sản phẩm (giống trang sản phẩm Shopee/Tiki). Trang bao gồm:

Header + Navigation
Breadcrumb (Trang chủ > Điện thoại > iPhone 16)
Khu vực ảnh sản phẩm (5 ảnh)
Thông tin sản phẩm (tên, giá, đánh giá sao, mô tả)
Bảng thông số kỹ thuật
Khu vực đánh giá/bình luận
Sidebar: Sản phẩm tương tự
Footer
Yêu cầu: Viết chỉ phần cấu trúc HTML (không cần nội dung thật, chỉ cần đúng thẻ và nesting). Mỗi thẻ phải có comment giải thích tại sao bạn chọn thẻ đó.

<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8"> <!-- charset vì cần mã hóa tiếng Việt đúng -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0"> <!-- viewport vì cần responsive trên mobile -->
    <title>Chi tiết sản phẩm</title> <!-- title vì đây là tiêu đề tab trình duyệt -->
</head>
<body>
    <header> <!-- header vì đây là phần đầu trang -->
        <nav aria-label="Điều hướng chính"> <!-- nav vì đây là khu vực điều hướng của trang -->
            <ul> <!-- ul vì menu điều hướng thường là danh sách các liên kết -->
                <li><a href="/">Trang chủ</a></li> <!-- li vì mỗi mục menu là một phần tử danh sách -->
                <li><a href="/dien-thoai">Điện thoại</a></li>
                <li><a href="/dien-thoai/iphone-16">iPhone 16</a></li>
            </ul>
        </nav>
    </header>

    <nav aria-label="breadcrumb"> <!-- nav vì breadcrumb là một dạng điều hướng phụ -->
        <ol> <!-- ol vì breadcrumb có thứ tự cấp bậc -->
            <li><a href="/">Trang chủ</a></li> <!-- li vì mỗi cấp là một phần tử của breadcrumb -->
            <li><a href="/dien-thoai">Điện thoại</a></li>
            <li aria-current="page">iPhone 16</li> <!-- aria-current vì đây là trang hiện tại -->
        </ol>
    </nav>

    <main> <!-- main vì đây là nội dung chính của trang -->
        <section aria-labelledby="product-images"> <!-- section vì đây là một khu nội dung riêng -->
            <h2 id="product-images">Ảnh sản phẩm</h2> <!-- h2 vì đây là tiêu đề của khu ảnh -->
            <figure> <!-- figure vì ảnh sản phẩm là một khối nội dung độc lập -->
                <img src="#" alt=""> <!-- img vì đây là ảnh sản phẩm -->
                <figcaption>Ảnh 1</figcaption> <!-- figcaption vì cần chú thích cho ảnh -->
            </figure>
            <figure>
                <img src="#" alt="">
                <figcaption>Ảnh 2</figcaption>
            </figure>
            <figure>
                <img src="#" alt="">
                <figcaption>Ảnh 3</figcaption>
            </figure>
            <figure>
                <img src="#" alt="">
                <figcaption>Ảnh 4</figcaption>
            </figure>
            <figure>
                <img src="#" alt="">
                <figcaption>Ảnh 5</figcaption>
            </figure>
        </section>

        <section aria-labelledby="product-info"> <!-- section vì đây là khối thông tin sản phẩm -->
            <h2 id="product-info">Thông tin sản phẩm</h2> <!-- h2 vì là tiêu đề khu vực -->
            <article> <!-- article vì thông tin sản phẩm là một nội dung độc lập -->
                <h3>...</h3> <!-- h3 vì là tiêu đề tên sản phẩm trong article -->
                <p>...</p> <!-- p vì mô tả và giá là văn bản nội dung -->
                <p aria-label="Đánh giá sao">...</p> <!-- p vì hiển thị rating dạng văn bản/biểu tượng -->
                <p>...</p>
            </article>
        </section>

        <section aria-labelledby="specs"> <!-- section vì đây là khu thông số kỹ thuật -->
            <h2 id="specs">Bảng thông số kỹ thuật</h2>
            <table> <!-- table vì dữ liệu dạng bảng -->
                <caption>Thông số kỹ thuật sản phẩm</caption> <!-- caption vì cần mô tả nội dung bảng -->
                <thead> <!-- thead vì đây là hàng tiêu đề của bảng -->
                    <tr> <!-- tr vì mỗi hàng bảng phải nằm trong một hàng -->
                        <th>...</th> <!-- th vì đây là ô tiêu đề cột -->
                        <th>...</th>
                    </tr>
                </thead>
                <tbody> <!-- tbody vì đây là phần dữ liệu chính của bảng -->
                    <tr>
                        <td>...</td> <!-- td vì đây là ô dữ liệu bình thường -->
                        <td>...</td>
                    </tr>
                </tbody>
                <tfoot> <!-- tfoot vì đây là phần tổng kết/chú thích cuối bảng -->
                    <tr>
                        <td colspan="2">...</td> <!-- colspan vì cần gộp nhiều cột -->
                    </tr>
                </tfoot>
            </table>
        </section>

        <section aria-labelledby="reviews"> <!-- section vì đây là khu đánh giá/bình luận -->
            <h2 id="reviews">Đánh giá / Bình luận</h2>
            <article> <!-- article vì mỗi bình luận là một nội dung độc lập -->
                <header> <!-- header vì bình luận có phần đầu: tên/ngày/điểm -->
                    <h3>...</h3>
                </header>
                <p>...</p>
            </article>
            <article>
                <header>
                    <h3>...</h3>
                </header>
                <p>...</p>
            </article>
        </section>
    </main>

    <aside aria-labelledby="similar-products"> <!-- aside vì đây là nội dung phụ, không phải trọng tâm -->
        <h2 id="similar-products">Sản phẩm tương tự</h2> <!-- h2 vì là tiêu đề của sidebar -->
        <article> <!-- article vì mỗi sản phẩm tương tự là một khối riêng -->
            <h3>...</h3>
            <p>...</p>
        </article>
        <article>
            <h3>...</h3>
            <p>...</p>
        </article>
    </aside>

    <footer> <!-- footer vì đây là phần chân trang -->
        <p>...</p> <!-- p vì thông tin bản quyền/liên hệ thường là văn bản -->
    </footer>
</body>
</html>
