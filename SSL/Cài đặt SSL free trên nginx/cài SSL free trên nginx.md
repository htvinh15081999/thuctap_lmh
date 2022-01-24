## Cài đặt SSL Let's Encrypt với Certbot trên Nginx.
### 1. Cài đặt Cerbot Let's Ecrypt Client
- Đầu tiên cài đặt EPEL repository: 
    + yum -y install epel-release

    <img src="image/1.PNG">

- Tiếp đến cài đặt certbot-nginx bằng câu lệnh:
    + yum -y install certbot-nginx

    <img src="image/2.PNG">

### 2. Cài đặt SSL Let's Encrypt
- Chạy câu lệnh : certbot --nginx -d lmhlmh9x.xyz -d www.lmhlmh9x.xyz

    <img src="image/3.PNG">

    + Đầu là nhập domain theo của mình
    + Tiếp là mail
    + y để chấp nhận điều khoản
    + n để không nhận thông tin

- Khi thành công ta sẽ có thông tin về chứng chỉ và khóa được lưu tại đường dẫn nào.

    <img src="image/5.PNG"> 

### Kiểm tra kết quả
- Có thể kiểm tra trực tiếp trên trình duyệt:

    <img src="image/4.PNG">

- Hoặc kiểm tra trên SSL Checker:

    <img src="image/7.PNG">

    <img src="image/8.PNG">

### Cấu hình gia hạn tự động
- Chứng chỉ Let's Encrypt chỉ có hiệu lực trong 90 ngày.
- Mở cửa sổ thêm Cronjob:
    + nano crontab
- Thêm cấu hình 
    + 00 6 * * * /usr/bin/certbot renew --quiet
    + Cronjob này có nghĩa là cứ đúng 6:00 AM nó sẽ check chứng chỉ, nếu chứng chỉ hết hạn sẽ tự động gia hạn. Ngược lại, nếu còn hạn sẽ không thực hiện gia hạn.

    <img src="image/9.PNG">

# Cài trên apache
- Tương tự như trên nginx:
- Khác ở bước cài đặt cerbot apache ta dùng câu lệnh: 
    + yum -y install certbot python2-certbot-apache mod_ssl