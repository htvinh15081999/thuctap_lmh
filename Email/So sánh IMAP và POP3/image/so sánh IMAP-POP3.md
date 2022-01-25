# So sánh IMAP và POP3
## Điểm giống
- Đều là giao thức trong Email.
- Tác dụng để nhận thư.
- Cho phép người dùng đọc các email cục bộ bằng một ứng dụng trung gian như Outlook, Thunderbird.
## Điểm khác

<img src="image/1.PNG">

### Cơ chế hoạt động
#### 1. IMAP - Là giao thức 2 chiều
- Kết nối đến server
- Lấy nội dung được yêu cầu từ người dùng và lưu đệm cục bộ, tổng kết email hay nội dung của những email được lựa chọn kĩ càng.
- Xử lí các biên tập từ người dùng.
#### POP3 - Là giao thức một chiều
- Kết nối đến server
- Nhận toàn bộ email
- Lưu cục bộ email mới
- Xóa mail trong server
### Port mặc định
#### IMAP
- 143 - không mã hóa
- 993 - mã hóa SSL/TLS - còn gọi là IMAPS

#### POP3S
- 110 - không mã hóa
- 995 - mã hóa SSL/TLS - còn được gọi là POP3S

### Đối tượng nên chọn giao thức
#### IMAP
- Truy cập truy cập email từ nhiều thiết bị khác nhau.
- Có một kết nối Internet thường xuyên và tin cậy.
- Muốn xem nhanh các email tới hoặc những email trên server.
- Không gian lưu trữ cục bộ hạn chế

#### POP
- Truy cập mail từ chỉ một thiết bị
- Cần truy cập thường xuyên dù có kết nối internet hay không.
- Không gian lưu trữ trên server hạn chế.