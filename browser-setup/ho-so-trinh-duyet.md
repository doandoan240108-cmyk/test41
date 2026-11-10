# Hồ sơ trình duyệt chuyên nghiệp

## Hai Profile, hai vùng dữ liệu

Tạo hai Browser Profile độc lập trong Chrome, Edge hoặc trình duyệt được công ty phê duyệt:

| Profile | Mục đích | Tài khoản | Quy tắc |
|---|---|---|---|
| `Personal` | Duyệt web cá nhân | Tài khoản cá nhân | Không đăng nhập dịch vụ nội bộ; không lưu tài liệu công ty |
| `TechNova_Work` | Công việc | Email/GitHub/Drive công ty | Không dùng chung cookie, session hoặc đồng bộ với Profile cá nhân |

Đặt tên/màu dễ nhận biết, bật khóa thiết bị và không dùng cửa sổ Profile công việc trên máy dùng chung. Profile tách biệt giảm lẫn lộn cookie/session nhưng không thay thế khóa màn hình, mã hóa thiết bị hay chính sách bảo mật.

## Bookmark Manager

Tạo ba thư mục bookmark trong Profile `TechNova_Work`:

1. `01_Work_Dev` — GitHub tổ chức, CI/CD, tài liệu kỹ thuật được duyệt.
2. `02_Onboarding_Docs` — Drive, wiki nội bộ, chính sách, thông tin liên hệ IT.
3. `03_Tools` — công cụ nội bộ và dịch vụ được công ty phê duyệt.

Lưu URL chính thức, kiểm tra tên miền trước khi đăng nhập, xóa bookmark lỗi thời. Không bookmark liên kết chứa token truy cập hoặc thông tin bí mật.

## Extensions

Chỉ cài từ cửa hàng/chính sách được công ty duyệt; rà soát nhà phát hành và quyền trước khi cài. Tắt hoặc gỡ extension không cần thiết.

| Nhóm | Ví dụ chức năng | Cấu hình |
|---|---|---|
| Dev Suite | Công cụ kiểm tra web/dev được duyệt | Không cấp quyền đọc/sửa mọi trang nếu không cần |
| Productivity Suite | Ghi chú, quản lý tab hoặc đọc tài liệu | Chỉ bật cho website công việc cần thiết |
| Security Suite | Password Manager, kiểm tra an toàn do công ty duyệt | Không cài nhiều công cụ trùng chức năng |

Đặt **Site Access** ở `On click` (hoặc giới hạn theo danh sách website) khi extension hỗ trợ. Không cài extension lậu/crack; extension có quyền rộng có thể đọc dữ liệu trên trang.

## DevTools cơ bản (F12)

- `Inspect`: nhấp phải phần tử giao diện → Inspect, hoặc mở DevTools bằng F12. Thay đổi trực tiếp trong DevTools chỉ là tạm thời, không sửa mã nguồn ứng dụng.
- Console: đọc lỗi và cảnh báo; trước khi chia sẻ log, xóa token, cookie, email cá nhân và dữ liệu khách hàng.
- Network: xem trạng thái tải tài nguyên trong môi trường được phép; không sao chép request/header chứa thông tin xác thực.
- **Cookies** lưu trạng thái/phiên cho website; **Cache** lưu tài nguyên như ảnh, CSS, JS để tải nhanh. Xóa cookies có thể làm đăng xuất; xóa cache thường buộc tải lại tài nguyên.
- Khi kiểm tra giao diện sau cập nhật, thực hiện **Hard Reload** (Ctrl+Shift+R trên Windows/Linux; Cmd+Shift+R trên macOS) trước khi kết luận bản giao diện bị lỗi. Tùy trình duyệt, có thể mở DevTools rồi nhấn giữ nút Reload để chọn Empty Cache and Hard Reload.
- Chỉ dùng DevTools với hệ thống và dữ liệu mà bạn được phép truy cập.
