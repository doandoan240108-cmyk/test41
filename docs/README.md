# TechNova Onboarding Kit

Bộ hồ sơ hướng dẫn nhân viên mới thiết lập không gian làm việc số an toàn, cộng tác đúng cách và tự xử lý các lỗi thường gặp.

## Mục lục

- [Mục tiêu](#mục-tiêu)
- [Cấu trúc dự án](#cấu-trúc-dự-án)
- [Hướng dẫn sử dụng](#hướng-dẫn-sử-dụng)
- [Checklist onboarding](#checklist-onboarding)
- [Bảng thiết bị và tài khoản](#bảng-thiết-bị-và-tài-khoản)
- [Quy tắc an toàn](#quy-tắc-an-toàn)
- [Tài liệu chi tiết](#tài-liệu-chi-tiết)

## Mục tiêu

Thống nhất cách tổ chức dữ liệu Local/Cloud, chia sẻ tài liệu, cấu hình trình duyệt, bảo vệ tài khoản và báo lỗi để nhân viên mới có thể làm việc an toàn ngay từ ngày đầu.

## Cấu trúc dự án

```text
Lop_MonHoc_MiniProject_TechNova/
├── .env                         # Cấu hình local giả định; không đưa lên Git
├── .gitignore                   # Quy tắc loại trừ áp dụng cho toàn repository
├── docs/
│   ├── README.md
│   └── srs-onboarding-kit.docx
├── cloud-workspace/
│   └── phan-quyen-chia-se.md
├── browser-setup/
│   └── ho-so-trinh-duyet.md
├── security/
│   ├── .env.example
│   ├── .gitignore
│   └── checklist-bao-mat.md
└── troubleshooting/
    └── mau-bao-cao-loi.md
```

Tên thư mục và tệp mới nên dùng `kebab-case`, không dấu, không khoảng trắng. Tên repository `Lop_MonHoc_MiniProject_TechNova` là tên mẫu; thay `Lop` và `MonHoc` bằng thông tin lớp/môn trước khi nộp.

## Hướng dẫn sử dụng

1. Đọc checklist bảo mật và thiết lập tài khoản công việc trước khi lưu dữ liệu nội bộ.
2. Tạo hai Browser Profile riêng theo hướng dẫn tại `browser-setup/ho-so-trinh-duyet.md`.
3. Tổ chức dữ liệu trong thư mục dự án Cloud, bật đồng bộ và cấp quyền theo bảng tại `cloud-workspace/phan-quyen-chia-se.md`.
4. Sao chép `security/.env.example` thành `.env` ở thư mục gốc khi chạy ứng dụng; thay placeholder bằng cấu hình được cấp qua kênh bí mật.
5. Khi gặp lỗi, tra cứu trước và gửi báo cáo đủ Context, Expected, Actual, Log/Screenshot.

```text
# Khởi động nhanh
1. Mở Profile TechNova_Work và đăng nhập bằng tài khoản công ty.
2. Hoàn tất password manager và 2FA.
3. Đồng bộ thư mục dự án với Cloud.
4. Kiểm tra .gitignore trước khi tạo commit đầu tiên.
5. Dùng mẫu Bug Report nếu tự tra cứu chưa giải quyết được lỗi.
```

## Checklist onboarding

- [ ] Tạo Profile `Personal` và `TechNova_Work`; xác nhận không dùng chung phiên đăng nhập.
- [ ] Lưu tài khoản công việc vào Bitwarden bằng mật khẩu riêng, mạnh.
- [ ] Bật 2FA bằng ứng dụng Authenticator cho GitHub và email công ty; lưu mã dự phòng trong Vault.
- [ ] Cài Drive for Desktop và xác nhận thư mục công việc được đồng bộ đúng tài khoản.
- [ ] Tạo cây thư mục dự án theo kebab-case và kiểm tra quyền truy cập.
- [ ] Tạo các bookmark và rà soát quyền Site Access của extension.
- [ ] Xác nhận `.env` bị Git bỏ qua và chỉ chia sẻ `.env.example`.
- [ ] Đọc hướng dẫn tìm kiếm, kiểm tra bản cập nhật và gửi Bug Report.
- [ ] Hỏi Mentor/IT khi quyền truy cập, thiết bị hoặc hướng dẫn có điểm chưa rõ.

## Bảng thiết bị và tài khoản

| Hạng mục | Dùng cho | Yêu cầu tối thiểu | Lưu ý |
|---|---|---|---|
| Máy tính công ty | Công việc và dữ liệu nội bộ | Cập nhật hệ điều hành, khóa màn hình | Không cài phần mềm crack |
| Profile `TechNova_Work` | Tài khoản, cookie và phiên công việc | Chỉ đăng nhập tài khoản công ty | Không đồng bộ với Profile cá nhân |
| Google Drive công ty | Tài liệu dự án | Đồng bộ thư mục được phê duyệt | Quyền tối thiểu cần thiết |
| Bitwarden | Lưu thông tin xác thực | Vault được khóa bằng mật khẩu chính mạnh | Không chia sẻ mật khẩu chính |
| Authenticator | TOTP/2FA | Thiết bị được bảo vệ bằng PIN/biometric | Mã dự phòng lưu riêng trong Vault |
| GitHub công ty | Mã nguồn và Issue | 2FA bật, quyền theo nhóm | Không commit `.env` hoặc secret |

## Quy tắc an toàn

- Không chia sẻ liên kết công khai với quyền Editor; ưu tiên Restricted theo email.
- Không dùng lại mật khẩu, không gửi mật khẩu/mã OTP qua chat hoặc email.
- Không đưa API key, token, mật khẩu thật vào mã nguồn, Issue, ảnh chụp hoặc log.
- Không mở tệp đính kèm/liên kết không rõ nguồn; kiểm tra kỹ tên miền trước khi đăng nhập.
- Không cài extension/phần mềm không được phê duyệt; giới hạn quyền truy cập website.

## Tài liệu chi tiết

- [Phân quyền và cộng tác Cloud](../cloud-workspace/phan-quyen-chia-se.md)
- [Hồ sơ trình duyệt](../browser-setup/ho-so-trinh-duyet.md)
- [Checklist bảo mật](../security/checklist-bao-mat.md)
- [Mẫu báo cáo lỗi và tra cứu](../troubleshooting/mau-bao-cao-loi.md)
- [SRS Onboarding Kit](./srs-onboarding-kit.docx)

---

Tài liệu nội bộ hướng dẫn quy trình. Khi có khác biệt với chính sách chính thức của TechNova, hãy ưu tiên chính sách và hướng dẫn từ IT/Security.
