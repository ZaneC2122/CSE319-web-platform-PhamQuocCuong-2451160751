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

Câu A3 (7đ) — Box Model — Tính toán kích thước
Đọc chương 11 (Box Model). Tính kích thước thực tế (chiều rộng thực tế render trên browser) cho mỗi trường hợp sau:

Nguồn tham chiếu Chương 11 THE BOX MODEL OF CSS phần Cách tính kích thước — NGUYÊN NHÂN CỦA MỌI BUG LAYOUT, BORDER-BOX — Giải Pháp "Một Dòng Cứu Ngàn Dòng", Margin Collapse — Hiện tượng "Margin bị nuốt" 
/* Trường hợp 1: content-box (mặc định) */
.box-1 {
    width: 400px;
    padding: 20px;
    border: 5px solid black;
    margin: 10px;
}
→ Chiều rộng hiển thị = ???
→ Không gian chiếm trên trang = ???

/* Trường hợp 2: border-box */
.box-2 {
    box-sizing: border-box;
    width: 400px;
    padding: 20px;
    border: 5px solid black;
    margin: 10px;
}
→ Chiều rộng hiển thị = ???
→ Kích thước content thực tế = ???
→ Không gian chiếm trên trang = ???

/* Trường hợp 3: Margin collapse */
.box-a { margin-bottom: 25px; }
.box-b { margin-top: 40px; }
→ Khoảng cách giữa box-a và box-b = ???
→ Giải thích tại sao KHÔNG PHẢI 65px
Nâng cao: Nếu .box-a có margin-bottom: -10px và .box-b có margin-top: 40px, khoảng cách = bao nhiêu?

    Trường hợp 1: content-box (mặc định)
    .box-1 {
        width: 400px;
        padding: 20px;
        border: 5px solid black;
        margin: 10px;
    }
    → Chiều rộng hiển thị 
        Content: 400px
        Padding trái + phải: 20 + 20 = 40px
        Border trái + phải: 5 + 5 = 10px
        Chiều rộng hiển thị = 400 + 40 + 10 = 450px
    → Không gian chiếm trên trang
        Chiều rộng hiển thị: 450px
        Margin trái + phải: 10 + 10 = 20px
        Không gian chiếm trên trang = 450 + 20 = 470px
    
    Trường hợp 2: border-box 
    .box-2 {
        box-sizing: border-box;
        width: 400px;
        padding: 20px;
        border: 5px solid black;
        margin: 10px;
    }
    → Chiều rộng hiển thị = 400px (do có thuộc tính  box-sizing: border-box; nên chiều rộng hiển thị = width )
    → Kích thước content thực tế
        Từ 400px trừ đi padding và border:
            Padding trái + phải: 40px
            Border trái + phải: 10px
            Kích thước content thực tế = 400 - 40 - 10 = 350px
    → Không gian chiếm trên trang
        Kích thước content thực tế = 350px
        Margin trái + phải: 20px
        Không gian chiếm trên trang = 400 + 20 = 420px
    
    Trường hợp 3: Margin collapse
    .box-a { margin-bottom: 25px; }
    .box-b { margin-top: 40px; }
    → Khoảng cách giữa box-a và box-b = 40px
    → KHÔNG PHẢI 65px vid khi hai box đứng dọc liên tiếp sẽ có hiện tượng margin đè lên nhau gọi là margin collapse ở chiều dọc nên thay vì lấy khoảng cách là tổng giữa chúng thì ta sẽ lấy khoảng cách = max(25px,40px) = 40px

    Nâng cao: Nếu .box-a có margin-bottom: -10px và .box-b có margin-top: 40px, khoảng cách sẽ là (-10) + 40 = 30px vì giá trị âm làm giảm khoảng cách giữa 2 box

Câu A4 (5đ) — Specificity (Độ ưu tiên)
Cho các CSS rules sau cùng target 1 element <p class="price" id="main-price">:

p { color: black; }                    /* Rule A */
.price { color: blue; }               /* Rule B */
#main-price { color: red; }           /* Rule C */
p.price { color: green; }             /* Rule D */
1.Tính specificity score (a, b, c) cho mỗi rule 
2.Element sẽ có màu gì? Giải thích 
3.Nếu thêm <p class="price" id="main-price" style="color: orange;">, element có màu gì? 
4.Nếu Rule A thêm !important, element có màu gì? Tại sao?

Nguồn tham chiếu: Chương 9: CSS Selectors phần Specificity — "Ai thắng khi xung đột?"

    1. Tính Specificity Score
        Rule A:p
        ID: 0
        Class: 0
        Element: 1
        -> Score:(0,0,1)
        Rule B: .price
        ID: 0
        Class: 1
        Element: 0
        -> Score:(0,1,0)
        Rule C: #main-price
        ID: 1
        Class: 0
        Element: 0
        -> Score:(0,1,0)
        Rule D: p.price
        p → 1 element
        .price → 1 class
        Score
        (0, 1, 1)
    2. Element sẽ có màu đỏ vì Rule C(1,0,0): #main-price { color: red; } có score cao nhất mà trong sắp xếp Specificity khi nhiều rule nhắm cùng element → rule nào có specificity cao hơn thắng
    3. Nếu thêm inline style
        <p class="price" id="main-price" style="color: orange;">

        Inline style có độ ưu tiên cực cao(1,0,0,0)
        Inline > ID > Class > Element
        Khi đó màu sẽ không còn là màu đỏ(red) mà là màu cam (orange)
    4. Nếu Rule A thêm !important
        Rule A thành:
        p {color: black !important;}
        Kết quả: màu đen (black)
        Vì !important là đánh dấu quan trọng nên ưu tiên cao hơn specificity thông thường(♾️ Vô cực ).Nên dù #main-price mạnh hơn về specificity nhưng black !important vẫn thắng.

Phần B-thực hành:
Bài B1 (20đ) — Style trang Profile
    5 loại selector khác nhau trong file CSS
        1. Element Selector: Chọn theo tên thẻ HTML
            Ví dụ trong file: <body> , <table> , <footer>
        2. Class Selector: Chọn theo class bằng dấu .\
            Ví dụ trong file: nav a.active
        3. ID Selector: Chọn theo id bằng dấu #
            Ví dụ trong file: #main-header
        4. Descendant Selector: Chọn phần tử con nằm bên trong phần tử cha.
            Ví dụ trong file: nav a
        5. Pseudo-class Selector: Dùng dấu :
            Ví dụ: nav a:hover
Bài B2 (20đ) — Box Model Lab

    PHẦN 1 — content-box vs border-box

    Hộp 1 (content-box)
    CSS:
    - width: 300px
    - padding: 20px
    - border: 5px

    Tính toán:
    Chiều rộng thực tế:300 + 20 + 20 + 5 + 5 = 350px

    Kết quả DevTools:350px

    Hộp 2 (border-box)
    CSS:
    - width: 300px
    - padding: 20px
    - border: 5px
    - box-sizing: border-box

    Chiều rộng thực tế:300px
    Content thực tế: 300 - 40 - 10 = 250px

    Kết quả DevTools: 300px
    Giải thích 
    content-box:
    - width chỉ tính phần content
    - padding và border được cộng thêm bên ngoài
    border-box:
    - width bao gồm cả content + padding + border
    - kích thước ngoài giữ nguyên

    PHẦN 2 — Layout 3 cột

    Trường hợp KHÔNG dùng border-box
    Sidebar:250 + 15 + 15 + 2 + 2 = 284px
    Content:500 + 20 + 20 + 2 + 2 = 544px
    Ads:250 + 15 + 15 + 2 + 2 = 284px

    Tổng:284 + 544 + 284 = 1112px
    → Lớn hơn container 1000px
    → Layout bị tràn

    Trường hợp DÙNG border-box
    Sidebar:250px
    Content:500px
    Ads:250px

    Tổng:250 + 500 + 250 = 1000px
    → Layout vừa đúng container
    → Không bị overflow

Bài B3 (15đ) — Specificity Battle
    10 CSS Rules + Specificity Score
        Rule 1	p	(0,0,1)
        Rule 2	.text	(0,1,0)
        Rule 3	.highlight	(0,1,0)
        Rule 4	p.text	(0,1,1)
        Rule 5	p.highlight	(0,1,1)
        Rule 6	.text.highlight	(0,2,0)
        Rule 7	p.text.highlight	(0,2,1)
        Rule 8	#demo	(1,0,0)
        Rule 9	#demo.highlight	(1,1,0)
        Rule 10	p#demo.highlight	(1,1,1)
    
    Element cuối cùng hiển thị màu vàng Gold vì rule mạnh nhất là:
        p#demo.highlight {
            color: gold;
        }
    Selector này gồm:
        1 ID (#demo)
        1 class (.highlight)
        1 element (p)
    -> Specificity Score(1,1,1) là specificcity cao nhất trong các rule được liệt kê trong file specificity.css nên nó thágw toàn bộ các rulke còn lại
    
    Nếu thay đổi thứ tự rule trong CSS thì 
        Kết quả không đổi nếu specificity khác nhau
        Kết quả có thể thay đổi nếu specificity bằng nhau, khi đó rule xuất hiện sau sẽ thắng vì  CSS ưu tiên theo:  !important > Inline style > Specificity > Thứ tự xuất hiện trong file
