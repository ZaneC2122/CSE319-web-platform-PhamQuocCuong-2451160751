Câu A1 (5đ) — 3 Cách nhúng CSS
Đọc chương 08. Liệt kê 3 cách nhúng CSS vào HTML (inline, internal, external). Mỗi cách:

Viết 1 ví dụ code
Ưu điểm và nhược điểm
Khi nào nên dùng
Câu hỏi thêm: Nếu cùng 1 element có cả 3 cách CSS đồng thời áp dụng, cách nào "thắng"? Giải thích tại sao

Nguồn tham chiếu: Chương 8 INTRODUCTION TO CSS phần 3 cách thêm CSS
    1. Inline CSS (trong thẻ)
        Ví dụ:
            <h1 style="color: red; font-size: 30px;">
                Xin chào
            </h1>
        Ưu Điểm:
            Nhanh, đơn giản
            Phù hợp test nhanh giao diện
            CSS chỉ ảnh hưởng đúng element đó
        Nhược điểm:
            Code khó đọc nếu dùng nhiều
            Không tái sử dụng được
            Khó bảo trì
            Làm HTML bị lẫn logic giao diện
        Khi nào nên dùng:
            Test nhanh
            Chỉnh 1 vài style nhỏ
            Email HTML (thường dùng inline)

    2. Internal CSS (trong <style>) 
        Ví dụ:
            <style>
            h1 {
                color: blue;
                font-size: 32px;
            }
            </style>
        Ưu điểm:
            Dễ quản lý hơn inline
            Không cần tạo file CSS riêng
            Phù hợp trang đơn giản
        Nhược điểm:
            Không tái sử dụng giữa nhiều trang
            File HTML sẽ dài nếu CSS nhiều
            Tải lại CSS mỗi lần mở trang
        Khi nào nên dùng:
            Website nhỏ
            Trang đơn
            Demo hoặc bài tập học tập

    3. External CSS (file riêng)
        Ví dụ:
            File HTML:
            <head>
                <link rel="stylesheet" href="styles.css">
            </head>
            File CSS:
                h1 {
                    color: green;
                    font-size: 35px;
                }
        Ưu điểm
            Chuyên nghiệp nhất
            Dễ bảo trì
            Tái sử dụng cho nhiều trang
            HTML sạch và dễ đọc
            Trình duyệt cache CSS giúp tải nhanh hơn
        Nhược điểm
            Cần thêm file riêng
            Nếu link sai CSS sẽ không hoạt động
        Khi nào nên dùng
            Website thật
            Dự án lớn
            Website nhiều trang
            
    Câu hỏi thêm:
        Nếu cùng 1 element có cả 3 cách CSS đồng thời áp dụng, cách dùng inline sẽ "thắng" vì:
            Inline là làm trực tiếp trong thuộc tính <style> của thẻ HTML và có thứ tự ưu tiên cao nhất lần lượt là: Inline CSS > Internal CSS > External CSS

Câu A2 (8đ) — CSS Selectors — Dự đoán kết quả
Cho HTML sau:

<div id="app">
    <header class="top-bar dark">
        <h1>ShopTLU</h1>
        <nav>
            <a href="/" class="active">Home</a>
            <a href="/products">Products</a>
            <a href="/about">About</a>
        </nav>
    </header>
    <main>
        <article class="product">
            <h2>iPhone 16</h2>
            <p class="price">25.990.000đ</p>
            <p>Mô tả sản phẩm...</p>
        </article>
        <article class="product featured">
            <h2>MacBook Pro</h2>
            <p class="price">45.990.000đ</p>
            <p>Mô tả sản phẩm...</p>
        </article>
    </main>
</div>
Không chạy code, cho biết mỗi selector sau chọn được element nào? (Ghi cụ thể text content)

1. h1                           → Chọn: ???
2. .price                       → Chọn: ???
3. #app header                  → Chọn: ???
4. nav a:first-child             → Chọn: ???
5. .product.featured h2         → Chọn: ???
6. article > p                  → Chọn: ???
7. a[href="/"]                  → Chọn: ???
8. .top-bar.dark h1              → Chọn: ???
Sau khi trả lời, tạo file selectors_test.html để kiểm chứng đáp án. Chụp screenshot.

Nguồn tham chiếu: Chương 9 CSS SELECTORS phần 5 Loại Selector — Từ rộng đến hẹp

    1.h1 -> Chọn: tất cả thẻ <h1>
        <h1>ShopTLU</h1>
        ->Text content: "ShopTLU"
    
    2. .price -> Chọn: tất cả các element có class price
        <p class="price">25.990.000đ</p>
        <p class="price">45.990.000đ</p>
        ->Text content: "25.990.000đ" và "45.990.000đ"
    
    3. #app header -> Chọn thẻ <header> nằm bên trong element có id app
        <header class="top-bar dark">
            <h1>ShopTLU</h1>
            <nav>
                <a href="/" class="active">Home</a>
                <a href="/products">Products</a>
                <a href="/about">About</a>
            </nav>
        </header>
        ->Text content:"ShopTLU", "Home", "Products" và "About"
    
    4. nav a:first-child -> Chọn: thẻ <a> đầu tiên bên trong <nav>
        <nav>
            <a href="/" class="active">Home</a>
        -> Text content: "Home"
    
    5. .product.featured h2 -> Chọn: Element có đồng thời class product và featured sau đó chọn thẻ h2 bên trong
        <article class="product featured">
            <h2>MacBook Pro</h2>
        -> Text content: "Macbook Pro"
    
    6. article > p ->Chọn: tất cả thẻ <p> là con trực tiếp của <article>
        <article class="product">
            <h2>iPhone 16</h2>
            <p class="price">25.990.000đ</p>
            <p>Mô tả sản phẩm...</p>
        </article>
        -> Text content: "25.990.000đ" và "Mô tả sản phẩm..."
        <article class="product featured">
            <h2>MacBook Pro</h2>
            <p class="price">45.990.000đ</p>
            <p>Mô tả sản phẩm...</p>
        </article>
        -> Text content: "45.990.000đ" và "Mô tả sản phẩm..."

    7. a[href="/"] -> Chọn: thẻ <a> có thuộc tính href="/"
        <a href="/" class="active">Home</a>
        ->Text content: "Home"

    8. .top-bar.dark h1 -> Chọn: Element có đồng thời class "top-bar" và "dark" sau đố chọn tiêu đề h1 bên trong
        <header class="top-bar dark">
            <h1>ShopTLU</h1>
        -> Text content: "ShopTLU"
