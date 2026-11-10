# Không gian cộng tác Cloud

## Hybrid Workflow: Local và Cloud

- Làm việc từ thư mục được cấu hình đồng bộ bằng Google Drive for Desktop; Local giúp thao tác thuận tiện, Cloud giúp sao lưu và cộng tác.
- Dùng tài khoản công ty trong ứng dụng Drive. Kiểm tra biểu tượng trạng thái đồng bộ trước khi tắt máy hoặc chuyển thiết bị.
- Không coi đồng bộ là bản sao lưu độc lập: xóa/sửa nhầm có thể đồng bộ lên Cloud. Với dữ liệu quan trọng, dùng lịch sử phiên bản/thùng rác theo chính sách công ty.
- Khi có xung đột đồng bộ, dừng sửa đồng thời, giữ nguyên các bản xung đột và nhờ chủ sở hữu/IT xử lý; không tự xóa bản chưa xác minh.
- Không lưu tài liệu nội bộ vào tài khoản Cloud cá nhân, USB không được duyệt hoặc thư mục tải xuống không quản lý.

## Cây thư mục dự án

Dùng kebab-case, tên ngắn, không dấu và nhất quán:

```text
<ten-du-an>/
├── 01-planning/
│   ├── briefs/
│   └── meeting-notes/
├── 02-design/
│   ├── research/
│   └── assets/
├── 03-development/
│   ├── source/
│   └── technical-notes/
├── 04-testing/
│   ├── test-cases/
│   └── bug-reports/
└── 05-delivery/
    ├── release-notes/
    └── handover/
```

Mỗi thư mục có chủ sở hữu rõ ràng. Không lưu secrets, mật khẩu hoặc dữ liệu cá nhân không cần thiết trong tài liệu cộng tác.

## Ma trận phân quyền mẫu

| Đối tượng | Quyền Drive | Phạm vi | Quy tắc |
|---|---|---|---|
| Nhân viên mới (tài liệu cá nhân) | Editor | Thư mục cá nhân thuộc tài khoản công ty | Chỉ chủ sở hữu và người được ủy quyền truy cập |
| Đồng đội cùng dự án | Editor | Thư mục dự án chung | Chỉ thành viên cần chỉnh sửa |
| Thực tập sinh phòng ban khác | Commenter | Tài liệu cần góp ý | Không cấp quyền sửa nếu chỉ cần phản hồi |
| Khách/đối tác bên ngoài | Viewer | Tệp cụ thể, Restricted theo email | Xác nhận chủ sở hữu và thời hạn trước khi chia sẻ |
| Người chỉ cần đọc | Viewer | Tệp/thư mục tối thiểu | Không mở rộng quyền toàn tổ chức nếu không cần |

**Nguyên tắc bắt buộc:** dùng `Restricted` và cấp quyền theo địa chỉ email cụ thể. Không kết hợp `Anyone with the link` với Editor. Nếu cần chia sẻ ngoài công ty, xin phê duyệt chủ sở hữu/IT, chỉ chia sẻ tệp cần thiết và đặt thời hạn nếu nền tảng hỗ trợ.

### Các bước chia sẻ an toàn

1. Mở Share và kiểm tra người nhận, miền email, vai trò.
2. Chọn Viewer, Commenter hoặc Editor theo đúng công việc; mặc định là quyền thấp nhất đủ dùng.
3. Giữ General access ở `Restricted`; không gửi liên kết trước khi xác nhận quyền.
4. Gửi thông báo có ngữ cảnh và thời hạn; rà soát quyền khi dự án/kỳ thực tập kết thúc.

## Kênh giao tiếp và văn hóa cộng tác

| Kênh | Mục đích | Cách sử dụng |
|---|---|---|
| `#onboarding` | Hỏi đáp với Mentor/nhân viên mới | Nêu bối cảnh, đã thử gì, và câu hỏi cụ thể |
| `#dev-<ten-du-an>` | Thảo luận kỹ thuật theo dự án | Mở thread cho từng vấn đề; chia sẻ log đã loại bỏ secrets |
| `#thong-bao` | Thông báo chính thức, chỉ đọc | Không chat tự do; theo dõi topic/pinned post |

- Trả lời bằng Reply in Thread để giữ câu chuyện cùng chủ đề.
- Tag đúng người chịu trách nhiệm; tránh `@all`/`@channel` ngoài tình huống khẩn cấp được quy định.
- Tránh “No-Hello”: gửi lời chào cùng câu hỏi và thông tin cần thiết trong một tin nhắn.
- Không đăng thông tin bí mật, token, dữ liệu khách hàng hoặc ảnh màn hình có thông tin nhạy cảm.
