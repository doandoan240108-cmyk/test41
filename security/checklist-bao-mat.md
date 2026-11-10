# Checklist bảo mật cá nhân và dự án

## Digital Vault và mật khẩu

- Dùng Bitwarden hoặc password manager do công ty phê duyệt làm nơi lưu thông tin xác thực.
- Tạo một mật khẩu chính mạnh, duy nhất; không chia sẻ và không dùng làm mật khẩu cho website khác.
- Dùng Generator tạo mật khẩu riêng 16–32 ký tự cho từng tài khoản. Không lưu mật khẩu trong ghi chú văn bản, trình chat hoặc mã nguồn.
- Bật khóa Vault tự động, bảo vệ thiết bị bằng PIN/biometric và chỉ cài ứng dụng từ nguồn chính thức.
- Chỉ lưu/chia sẻ mục Vault theo quy trình được công ty cho phép.

## 2FA

- Bật 2FA cho GitHub và email công ty bằng ứng dụng Authenticator/TOTP hoặc khóa bảo mật theo chính sách.
- Không chọn SMS OTP làm phương thức chính nếu có lựa chọn TOTP/khóa bảo mật; SIM swap có thể làm SMS kém an toàn hơn.
- Lưu Backup/Recovery Codes trong mục bảo mật của Bitwarden, không lưu chung trong email hoặc thư mục chia sẻ.
- Không gửi mã OTP hoặc Recovery Code cho bất kỳ ai, kể cả người tự xưng là IT.
- Kiểm tra phương thức khôi phục tài khoản theo quy trình công ty; báo IT nếu mất thiết bị xác thực.

## Nhận diện lừa đảo và mã độc

- **Phishing:** email/tin nhắn thúc giục đăng nhập, thanh toán hoặc mở tệp. Kiểm tra người gửi và miền thật; tự mở trang qua bookmark/URL chính thức thay vì bấm liên kết đáng ngờ.
- **Typosquatting:** tên miền gần giống tên thật, có ký tự thêm/bớt hoặc thay thế. Đọc kỹ toàn bộ hostname trước khi nhập thông tin.
- **Mã độc/crack:** phần mềm bẻ khóa, keygen và installer không rõ nguồn có thể đánh cắp mật khẩu hoặc cài mã độc. Không tải/chạy; chỉ dùng phần mềm được cấp phép.
- Không bật macro/chạy script lạ theo hướng dẫn trong email hoặc trang web. Báo IT/Security và giữ nguyên bằng chứng nếu nghi ngờ sự cố.

## Quy tắc 5 KHÔNG

1. **Không** dùng lại mật khẩu giữa các tài khoản.
2. **Không** gửi mật khẩu, OTP, Recovery Code hoặc API key qua chat/email.
3. **Không** bấm liên kết hay mở tệp không xác minh được nguồn.
4. **Không** cài phần mềm crack, extension lạ hoặc công cụ chưa được duyệt.
5. **Không** đưa secrets/dữ liệu nội bộ vào repository công khai, prompt AI công cộng hoặc ảnh chụp màn hình.

## Bảo vệ secrets với `.env` và Git

- Khai báo `.env` bị ignore ở **root repository trước commit đầu tiên**; Git chỉ tự động áp dụng `.gitignore` ở vị trí phù hợp trong cây thư mục.
- Tạo `.env` local từ `security/.env.example`. Chỉ thay placeholder bằng secret được cấp qua kênh quản lý bí mật.
- Chỉ commit `.env.example` với tên biến và giá trị ví dụ không nhạy cảm; không bao giờ chép secret thật vào file mẫu.
- Không đưa `.env` vào Cloud/Drive chia sẻ. Trên máy chủ/CI, dùng secret manager hoặc kho secrets của nền tảng.
- Kiểm tra bằng `git status --short` và `git check-ignore -v .env` trước khi commit. Nếu secret đã commit, xóa file khỏi lịch sử là chưa đủ: thu hồi/rotate secret ngay và báo IT/Security.

Ví dụ kiểm tra tại thư mục gốc:

```text
git status --short
git check-ignore -v .env
```

`.gitignore` trong `security/` được giữ làm tài liệu/cấu hình cục bộ; quy tắc gốc ở `/.gitignore` mới bảo vệ `.env` ở root của repository.

## Khi nghi ngờ tài khoản hoặc thiết bị bị xâm nhập

Ngắt kết nối thiết bị nếu được hướng dẫn, không xóa log/bằng chứng, không tự gửi dữ liệu nhạy cảm qua chat. Báo ngay IT/Security qua kênh khẩn cấp chính thức, cung cấp thời điểm, thiết bị, hành động đã thực hiện và ảnh/log đã được làm sạch.
