# Ôn KHTN 6–9 (GitHub Pages + Supabase)

Trang web tĩnh, không cần build. Tiến độ luyện tập lớp 6 lưu trong trình duyệt, và lưu lên Supabase khi học sinh đăng nhập.

## Cấu trúc
- `index.html`: toàn bộ trang (dữ liệu bài nằm trong thẻ script)
- `config.js`: URL và anon key của Supabase
- `supabase.sql`: tạo bảng `progress` và bật Row Level Security

## 1. Supabase
1. Tạo project tại supabase.com.
2. Vào SQL Editor, dán nội dung `supabase.sql`, bấm Run.
3. Vào Project Settings > API, chép **Project URL** và **anon public key** vào `config.js`.
4. Vào Authentication > Providers > Email. Nếu muốn con đăng ký xong dùng ngay, tắt "Confirm email". Nếu để bật, con phải bấm link trong email.
5. Sau khi có địa chỉ GitHub Pages (bước 2), vào Authentication > URL Configuration, đặt **Site URL** là địa chỉ đó.

## 2. GitHub Pages
1. Tạo repository mới (Public), tải cả 4 file lên nhánh `main`.
2. Settings > Pages > Source: Deploy from a branch, chọn `main` và thư mục `/ (root)`.
3. Sau 1–2 phút, trang chạy tại `https://<tên-github>.github.io/<tên-repo>/`.

## Bảo mật
- Anon key được phép công khai, vì mỗi học sinh chỉ đọc và ghi được dòng của chính mình nhờ Row Level Security.
- Không đưa `service_role` key vào repository.
- Dữ liệu lưu chỉ gồm email, mật khẩu (Supabase mã hóa) và tiến độ làm bài. Nếu con dưới 16 tuổi, phụ huynh nên tự tạo và giữ tài khoản.

## Ghi chú
- Khóa tiến độ hiện dạng `chương-câu` và chỉ dành cho lớp 6. Khi thêm lớp 7, cần thêm tiền tố lớp vào khóa.
