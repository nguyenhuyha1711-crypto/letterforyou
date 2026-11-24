HƯỚNG DẪN CÀI ĐẶT — MỘT LÁ THƯ DÀNH CHO HAI NGƯỜI

Gồm:
- index.html: giao diện phong thư, nội dung thư, form hồi âm.
- firebase-config.js: nơi điền cấu hình Firebase.
- firestore.rules: quy tắc Firestore.

A. CẤU HÌNH FIREBASE (BẮT BUỘC ĐỂ GỬI/ĐỌC HỒI ÂM)
1. Mở https://console.firebase.google.com/ và tạo/chọn một project.
2. Project settings (bánh răng) → General → Your apps → chọn Web app.
   Nếu chưa có Web app, bấm Add app (</>) để tạo.
3. Ở SDK setup and configuration, chọn Config.
4. Mở firebase-config.js và thay:
   DAN_API_KEY_VAO_DAY
   DAN_PROJECT_ID_VAO_DAY
   DAN_APP_ID_VAO_DAY
   bằng các giá trị tương ứng trong Firebase config.
   authDomain phải là giá trị authDomain Firebase đưa ra, không tự đoán.
5. Authentication → Sign-in method → bật Anonymous.
6. Authentication → Settings → Authorized domains:
   - localhost thường có sẵn.
   - Nếu dùng Live Server tại 127.0.0.1, thêm 127.0.0.1 nếu chưa có.
7. Firestore Database → Create database.
8. Vào Firestore → Rules, dán toàn bộ firestore.rules rồi bấm Publish.

B. CHẠY TRONG VS CODE
1. Đặt index.html, firebase-config.js cùng một thư mục.
2. Mở thư mục đó bằng VS Code.
3. Dùng Live Server để mở index.html (không mở bằng file://).
4. Nếu trang hiện “Đã kết nối hộp thư”, thử gửi hồi âm.
5. Deploy cả index.html và firebase-config.js lên cùng một hosting HTTPS để hai điện thoại dùng chung một link.

C. CHỈNH NỘI DUNG LÁ THƯ
Mở index.html và tìm:
   BẠN TỰ VIẾT NỘI DUNG LÁ THƯ Ở ĐÂY
Chỉnh phần chữ giữa hai chú thích đó. Không xóa phần script Firebase ở cuối trang.

D. QUAN TRỌNG VỀ RIÊNG TƯ
Website không yêu cầu mật khẩu. Phiên ẩn danh chỉ giúp Firebase nhận diện kết nối chứ KHÔNG xác minh đó là bạn hay bạn gái.
Với rules hiện tại, bất kỳ ai có thể truy cập project và website đều có thể đọc/gửi thư. Không chia sẻ công khai nếu thư cần riêng tư. Muốn chỉ hai người được đọc cần thêm cơ chế mã mời/kiểm tra phía máy chủ hoặc đăng nhập.
