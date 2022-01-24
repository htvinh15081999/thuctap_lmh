# Các bước cài đặt Cpanel trên Centos 7
## Đầu tiên SSH vào VPS
## Cài và bật tắt 1 số dịch vụ cần thiết
### 1. Perl - Curl
- yum install perl
- yum install curl
### 2. Tắt SeLinux
- sed -i 's/SELINUX=/#SELINUX=/g' /etc/selinux/config
- SELINUX=disabled >> /etc/selinux/config
### 3. Tắt Network Manager
- systemctl stop NetworkManager.service
- systemctl disable NetworkManager.service
### 4. Update

- yum update -y
## Cài đặt cPanel
- cd /home && curl -o latest -L https://securedownloads.cpanel.net/latest && sh latest

- Ngồi đợi

<img src="image/1.PNG">

## Sau khi xong, truy cập địa chỉ :2087 để vào trang đăng nhập

- Đăng nhập vào cPanel bằng tài khoản root của VPS.
    
<img src="image/2.PNG">

- Sau đó login tài khoản đã đăng khí trên web của cPanel để dùng thử 15 ngày.

<img src="image/3.PNG">

- Một số thông tin nữa:

<img src="image/4.PNG">


## Xong
- Giao diện của cPanel:

<img src="image/5.PNG">
