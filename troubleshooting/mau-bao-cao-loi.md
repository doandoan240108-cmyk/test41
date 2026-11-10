# Tự tra cứu và báo cáo lỗi

## 1. Tìm kiếm có mục tiêu

Không nhập nguyên câu hỏi văn nói. Tách thông báo lỗi/ngôn ngữ lập trình/phiên bản và tìm cụm từ đặc trưng.

| Toán tử | Ví dụ | Công dụng |
|---|---|---|
| Dấu ngoặc kép `" "` | `"ModuleNotFoundError: No module named"` | Tìm cụm chính xác |
| `site:` | `site:docs.python.org venv Windows` | Giới hạn website chính thức |
| Dấu trừ `-` | `React hydration error -Next.js` | Loại kết quả không liên quan |
| Kết hợp | `site:github.com/org/repo/issues "timeout" 2.4` | Tìm Issue trong repository và phiên bản cụ thể |

Ưu tiên tài liệu chính thức và kết quả khớp phiên bản. Bài StackOverflow trên 5 năm có thể vẫn hữu ích để hiểu khái niệm, nhưng cần kiểm tra câu trả lời với phiên bản hiện tại.

## 2. Đọc StackOverflow và GitHub Issues

- StackOverflow: xem phiên bản, ngày đăng, Accepted Answer, upvote và bình luận mới hơn. Chạy thử trong môi trường an toàn; không sao chép lệnh nguy hiểm hoặc lệnh đòi secrets.
- GitHub Issues: kiểm tra repository chính thức, nhãn, phiên bản và trạng thái `Open`/`Closed`. Issue đóng có thể đã được sửa hoặc không tái hiện; đọc comment cuối và liên kết release/PR.
- Ghi lại nguồn, phiên bản và workaround đã thử. Không tải binary/patch từ comment không đáng tin.

## 3. Prompt AI ba thành phần

Chỉ dùng AI được công ty phê duyệt với dữ liệu công việc. Thay thông tin nhạy cảm bằng placeholder trước khi gửi.

```text
Ngữ cảnh: Tôi đang dùng [công nghệ và phiên bản], trên [hệ điều hành/môi trường].
Lỗi nguyên văn: "[dán thông báo lỗi đã loại bỏ token, email, hostname nội bộ và dữ liệu khách hàng]"
Yêu cầu: Hãy giải thích nguyên nhân có khả năng, nêu các bước kiểm tra an toàn theo thứ tự,
và cho biết thông tin nào còn thiếu. Không giả định đã có quyền quản trị.
```

AI có thể sai hoặc đưa hướng dẫn lỗi thời. Đối chiếu với tài liệu chính thức, không dán secrets/mã nguồn nhạy cảm và không chạy lệnh phá hủy dữ liệu nếu chưa hiểu tác động.

## 4. Bug Reporting Framework

Gửi báo cáo theo bốn phần **Context – Expected – Actual – Log/Screenshot**:

```text
Tiêu đề: [dịch vụ/tính năng] – [triệu chứng ngắn] – [môi trường/phiên bản]

Context
- Thiết bị, hệ điều hành, ứng dụng/trình duyệt và phiên bản:
- Môi trường (local/staging/production), thời điểm và tần suất:
- Các bước ngay trước khi lỗi xảy ra:

Expected
- Kết quả mong đợi:

Actual
- Kết quả thực tế; có tái hiện được không:
- Các bước tái hiện tối thiểu:

Log/Screenshot
- Thông báo lỗi nguyên văn hoặc log liên quan:
- Ảnh chụp/Request ID (nếu được phép):
- Đã thử: [các bước và kết quả]
- Đã loại bỏ: token, cookie, mật khẩu, dữ liệu cá nhân/khách hàng
```

Không gửi mật khẩu, OTP, cookie/session, API key, dữ liệu cá nhân hay ảnh có thông tin nhạy cảm. Nếu lỗi liên quan sự cố bảo mật, báo theo kênh khẩn cấp Security thay vì đăng công khai trong kênh dự án.
