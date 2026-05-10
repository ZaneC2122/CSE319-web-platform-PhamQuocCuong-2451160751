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