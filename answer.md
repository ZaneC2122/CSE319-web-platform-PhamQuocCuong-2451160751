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
