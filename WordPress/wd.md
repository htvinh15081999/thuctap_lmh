## WordPress là gì?
- WordPress là phần mềm mã nguồn mở Open Soucre miễn phí được viết bằng PHP và hệ quả trị cơ sở dữ liệu MySQL. 
- Đây là phần mềm quản lí nội dung CMS - Content Management System mà có thể sử dụng để tạo ra các trang web.

<img src="image/1.PNG">

## Cách cài WordPress.
### Trước hết phải cài LAMP.
#### 1. Cài apache như mọi lần.
#### 2. Cài MySQL- MariaDB
- MySQL được thay thế bằng MariaDB trong CentOS 7. Phải bổ sung kho yêu cầu: 

    + rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY*
    + yum -y install epel-release

- Cài đặt gói máy chủ MariaDB
    + yum -y install mariadb-server mariadb
- Khởi động MariaDB:
    + systemctl enable mariadb.service
    + systemctl start mariadb.service
- Chạy mysql_secure_installation để bảo vệ:
    + mysql_secure_installation

#### Cài đặt PHP
- Thêm Remi repo
    + rpm -Uvh http://rpms.remirepo.net/enterprise/remi-release-7.rpm
- Cài yum-untils để lấy tiện ích yum-config-manager:

    + yum -y install yum-utils
- Cập nhật:
    + yum update
- Cài đặt PHP 7.0
    + yum-config-manager --enable remi-php70
    + yum -y install php php-opcache

- Khởi động lại Apache:
#### Cài đặt hỗ trợ MySQL trong PHP
- yum search php
- yum -y install php-mysql
- yum -y install php-gd php-ldap php-odbc php-pear php-xml php-xmlrpc php-mbstring php-soap curl curl-devel
- Lệnh trên cài đặt những module phổ biến
- KHởi động lại apache.

### Cài đặt wordpress
1. Vào nơi lưu trữ vhost:
- cd /var/www/html/lmhlmh9x.xyz/
2. Tải về WP mới nhất
- wget https://wordpress.org/latest.tar.gz

3. Giải nén
- tar xzvf latest.tar.gz
4. Thiết lập quyền tránh vấn đề phat sinh sau này
- sudo chown -R apache:apache /var/www/html/lmhlmh9x.xyz/
5. Chuyển tập tin trong thư mục ra ngoài:

- mv wordpress/* /var/www/html/lmhlmh9x.xyz/
### Tạo cơ sở dữ liệu
1. Tạo cơ sở dữ liệu MySQL / MariaDB
1. Đăng nhập vào MariaDB:

    + mysql -u root -p
2. Tạo cơ sở dữ liệu và người dùng mới có quyền sử dụng nó:

    + CREATE DATABASE demo;
GRANT ALL PRIVILEGES on dmeo.* to 'lmh9x'@'localhost' identified by 'password';
- PHẢI CÓ @'localhost'

    + FLUSH PRIVILEGES;

3. Thoát khỏi MariaDB

### Cấu hình WP kết nối với DB
1. Đổi tên chỉnh sửa tệp cấu hình Wordpress.
- cd /var/www/html/lmhlmh9x.xyz/
- mv wp-config-sample.php wp-config.php
2. Chỉnh sửa cấu hình
- nano wp-config.php
- thay đổi giá trị DB_NAME, DB_USER, DB_PASSWORD
3. Restart apache phát cho chắc
### Tận hưởng thành quả.
## Cách vào trang quản trị WP
- Thêm /wp-admin vào sau tên miền là ok.