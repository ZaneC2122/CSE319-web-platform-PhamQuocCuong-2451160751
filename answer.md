Câu A1 (5đ) — Input Types 
Liệt kê 10 input types khác nhau trong HTML5, cho mỗi type: Giao diện hiển thị (mô tả bằng lời) Validation tự động (nếu có) Use case cụ thể trong trang E-Commerce Format trả lời:
1. type="email" → Ô nhập text, tự kiểm tra có @ → Dùng cho form đăng ký 
2. type="..." → ...
Nguồn tham chiếu: Chương 7-07_forms_interactive.md
    -Phần Các Input Types HTML5

    1.type="email" → Ô nhập văn bản, thường có bàn phím tối ưu trên mobile → Tự kiểm tra định dạng email, phải có ký tự @ → Dùng cho form đăng ký, đăng nhập, nhận hóa đơn.
    2.type="password" → Ô nhập văn bản bị che bằng dấu • hoặc * → Không kiểm tra mạnh về nội dung, chủ yếu che ký tự → Dùng cho mật khẩu tài khoản, đổi mật khẩu.
    3.type="number" → Ô nhập số, có nút tăng/giảm tùy trình duyệt → Chỉ nhận giá trị số, có thể kiểm tra min, max, step → Dùng cho số lượng sản phẩm, tuổi, số điện thoại nội bộ.
    4.type="tel" → Ô nhập văn bản tối ưu cho số điện thoại → Không tự kiểm tra chặt định dạng, chủ yếu hỗ trợ bàn phím số trên mobile → Dùng cho số điện thoại khách hàng, giao hàng.
    5.type="url" → Ô nhập văn bản cho địa chỉ web → Tự kiểm tra định dạng URL hợp lệ → Dùng cho ô nhập link website, link mạng xã hội trong hồ sơ shop.
    6.type="search" → Ô tìm kiếm, giao diện giống text nhưng tối ưu cho tìm nhanh → Không có validation đặc biệt → Dùng cho ô tìm kiếm sản phẩm, đơn hàng, mã giảm giá.
    7.type="date" → Bộ chọn ngày theo lịch → Tự kiểm tra đúng định dạng ngày → Dùng cho ngày đặt hàng, ngày sinh, ngày giao dự kiến.
    8.type="time" → Bộ chọn giờ/phút → Tự kiểm tra định dạng thời gian → Dùng cho chọn khung giờ giao hàng, giờ nhận hàng.
    9.type="file" → Nút chọn tệp từ máy tính hoặc điện thoại → Có thể giới hạn loại file bằng accept, số lượng file bằng multiple → Dùng để upload ảnh sản phẩm, ảnh hóa đơn, avatar.
    10.type="checkbox" → Ô tích chọn vuông nhỏ, có thể chọn/bỏ chọn → Validation thường là bắt buộc nếu đặt required → Dùng cho đồng ý điều khoản, chọn nhiều thuộc tính sản phẩm như màu sắc, dịch vụ kèm theo.

Câu A2 (5đ) — Validation Attributes Đọc chương 07. Không chạy code, hãy dự đoán điều gì xảy ra khi user bấm Submit cho mỗi trường hợp sau. Giải thích TẠI SAO. 
<!-- Trường hợp 1 --> <input type="text" required value=""> <!-- User để trống -->
<!-- Trường hợp 2 --> <input type="email" value="abc"> <!-- User gõ "abc" --> 
<!-- Trường hợp 3 --> <input type="number" min="1" max="10" value="15"> <!-- User gõ 15 --> 
<!-- Trường hợp 4 --> <input type="text" pattern="[0-9]{10}" value="abc123"> <!-- User gõ "abc123" --> 
<!-- Trường hợp 5 --> <input type="password" minlength="8" value="123"> <!-- User gõ "123" --> 
Sau khi trả lời, tạo file validation_test.html, đặt 5 trường hợp trên vào 1 form, bấm Submit và chụp screenshot kết quả validation thực tế. So sánh với dự đoán.
Nguồn tham chiếu: Chương 7-07_forms_interactive.md
    -Phần HTML5 Validation Attributes:

    1) <input type="text" required value="">
    Kết quả: Không submit
    Lý do: Thuộc tính required bắt buộc phải có giá trị. Trường rỗng → valueMissing = true.

    2) <input type="email" value="abc">
    Kết quả: Không submit
    Lý do: type="email" kiểm tra định dạng email. Chuỗi “abc” không có @ → typeMismatch = true.

    3) <input type="number" min="1" max="10" value="15">
    Kết quả: Không submit
    Lý do: Giá trị 15 vượt max=10 → rangeOverflow = true.

    4) <input type="text" pattern="[0-9]{10}" value="abc123">
    Kết quả: Không submit
    Lý do: Pattern yêu cầu đúng 10 chữ số liên tiếp. “abc123” không khớp → patternMismatch = true.

    5) <input type="password" minlength="8" value="123">
    Kết quả: Không submit
    Lý do: Độ dài 3 < minlength=8 → tooShort = true.

    - Trong 4 trường hợp đầu tiên chạy đúng như dự đoán ban đầu nhưng trường hợp 5 lại có thể submit như bình thường sai lệch với dự đoán đề ra 

Câu A3 (5đ) — Accessibility
Đọc phần Accessibility trong chương 07. Giải thích:

Tại sao <label for="email"> quan trọng cho người dùng screen reader?
Khi nào dùng <fieldset> + <legend>? Cho ví dụ cụ thể.
aria-label dùng khi nào? Tại sao KHÔNG nên dùng aria-label khi đã có <label>?
Nguồn tham chiếu: Chương 7-07_forms_interactive.md
    -Phần Accessibility — Form cho mọi người

    1) Vì sao <label for="email"> quan trọng với screen reader?
    Tạo “accessible name” cho input: Khi for trỏ đúng id, screen reader đọc “Nhãn + trạng thái” (ví dụ: “Email, edit text, required”). Không có <label>, người dùng chỉ nghe “edit text” → mất ngữ cảnh.
    Mở rộng vùng click/focus: Click vào label sẽ focus vào input → hỗ trợ người dùng vận động hạn chế.
    Liên kết có cấu trúc: Trình đọc màn hình và công cụ hỗ trợ dựa vào quan hệ label–control để điều hướng form nhanh hơn.
    
    2) Khi nào dùng <fieldset> + <legend>? Ví dụ
    Dùng khi nhóm nhiều control liên quan (radio/checkbox hoặc các trường cùng một chủ đề) để cung cấp ngữ cảnh cấp nhóm cho người dùng, đặc biệt là screen reader.
    <legend> là tiêu đề của nhóm, được đọc trước khi duyệt từng control trong nhóm.

    Ví dụ (chọn phương thức thanh toán):
    <fieldset>
    <legend>Phương thức thanh toán</legend>
    <label><input type="radio" name="pay" value="cod"> Thanh toán khi nhận hàng</label>
    <label><input type="radio" name="pay" value="card"> Thẻ tín dụng</label>
    <label><input type="radio" name="pay" value="ewallet"> Ví điện tử</label>
    </fieldset>
    → Screen reader sẽ đọc: “Phương thức thanh toán, group” rồi đến từng lựa chọn.

    3) aria-label dùng khi nào? Vì sao không nên dùng khi đã có <label>?
    Dùng khi không có (hoặc không thể có) nhãn hiển thị bằng <label>/text — ví dụ icon button hoặc input ẩn nhãn:
    <button aria-label="Tìm kiếm">🔍</button>
    Không nên dùng khi đã có <label> vì:
    Gây trùng lặp hoặc xung đột accessible name (screen reader có thể đọc hai lần hoặc ưu tiên aria-label ghi đè nội dung label).
    Tăng chi phí bảo trì/i18n: phải đồng bộ hai nguồn nội dung.
    Vi phạm nguyên tắc “native HTML first”: ưu tiên cơ chế ngữ nghĩa sẵn có (<label>, <legend>) trước ARIA.

Câu A4 (5đ) — Media 
1.Giải thích thuộc tính loading="lazy" trên thẻ <img>. Nó cải thiện gì? Khi nào KHÔNG nên dùng? 
2.Tại sao nên cung cấp nhiều <source> trong thẻ <video>? Liệt kê ít nhất 3 format video web phổ biến. 
3.Thuộc tính alt trên <img> dùng để làm gì? Viết alt tốt cho 3 trường hợp: 
    Ảnh sản phẩm iPhone 16 
    Ảnh trang trí (decorative) 
    Ảnh biểu đồ doanh thu Q1/2026
Nguồn tham chiếu 
    AI+Chương 4-04_visible_part_html.md
    -Phần Media — Ảnh, Video, Audio
    Chương6-06_graphics_multimedia.md
    -Phần Images — Responsive và tối ưu

    1) loading="lazy" trên <img> là gì?

    *)loading="lazy" yêu cầu trình duyệt hoãn tải ảnh cho đến khi ảnh sắp xuất hiện trong vùng nhìn thấy của người dùng.
        -Nó cải thiện:
            Tốc độ tải ban đầu của trang
            Giảm băng thông
            Giảm số request khởi tạo
            Cải thiện LCP/UX nếu ảnh nằm dưới màn hình

        -Không nên dùng cho:
            Ảnh quan trọng ngay đầu trang, nhất là ảnh hero / ảnh chính / ảnh LCP
            Ảnh cần hiển thị ngay lập tức cho trải nghiệm ban đầu
            Trường hợp ảnh phải tải sớm để tránh layout nhảy hoặc để trang nhìn đầy đủ ngay khi mở
    2) Vì sao nên cung cấp nhiều <source> trong <video>?
        Vì mỗi trình duyệt hỗ trợ codec/format khác nhau. Dùng nhiều <source> giúp:
            Tăng tương thích trình duyệt
            Tránh lỗi “không phát được video”
            Cho phép trình duyệt chọn định dạng phù hợp nhất
        3 format video web phổ biến:
            MP4 (.mp4, thường dùng H.264/AAC)
            WebM (.webm)
            Ogg (.ogv / .ogg)

    3) alt trên <img> dùng để làm gì?
        alt là văn bản thay thế cho ảnh, dùng khi:
            Ảnh không tải được
            Người dùng dùng screen reader
            Công cụ tìm kiếm hiểu nội dung ảnh
        alt tốt phải:
            Mô tả đúng mục đích của ảnh
            Ngắn gọn, tự nhiên
            Không nhồi từ khóa
        Viết alt tốt cho 3 trường hợp
            Ảnh sản phẩm iPhone 16
            <img src="iphone16.jpg" alt="iPhone 16 màu xanh titan">

            Ảnh trang trí (decorative)
            <img src="decor.png" alt="">

            Ảnh biểu đồ doanh thu Q1/2026
            <img src="revenue-q1-2026.png" alt="Biểu đồ doanh thu quý 1 năm 2026 tăng từ tháng 1 đến tháng 3">

Câu A5 (5đ) — So sánh <figure> vs <img>
<!-- Cách 1 -->
<img src="product.jpg" alt="iPhone">

<!-- Cách 2 -->
<figure>
    <img src="product.jpg" alt="iPhone 16 Pro Max 256GB Titan">
    <figcaption>iPhone 16 Pro Max — 25.990.000đ</figcaption>
</figure>
Khi nào dùng Cách 1, khi nào dùng Cách 2? Cho 2 ví dụ thực tế cho mỗi cách.
Nguồn tham chiếu AI+Chương 6-06_graphics_multimedia.md
    -Phần Images — Responsive và tối ưu

    Cách 1: <img> đơn lẻ
    Dùng khi ảnh chỉ đóng vai trò minh họa thuần và bản thân ảnh đã đủ ngữ cảnh từ phần xung quanh, hoặc khi không cần chú thích riêng.
    Ví dụ thực tế:
    Ảnh avatar người dùng trong danh sách bình luận.
    Ảnh icon minh họa trong banner trang chủ.

    Cách 2: <figure> + <figcaption>
    Dùng khi ảnh là một đối tượng nội dung độc lập và cần chú thích, mô tả, tên, giá, nguồn, hoặc giải thích đi kèm.
    Ví dụ thực tế:
    Ảnh sản phẩm trong trang bán hàng, kèm tên và giá.
    Ảnh biểu đồ, sơ đồ, hoặc ảnh minh họa trong bài viết học thuật kèm chú thích.
