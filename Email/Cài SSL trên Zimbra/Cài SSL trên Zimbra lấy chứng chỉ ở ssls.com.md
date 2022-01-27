# Các bước thực hiện
## Lấy chứng chỉ
1. Vào trang web ssls.com để đăng kí một tài khoản

<img src="image/1.PNG">
<img src="image/2.PNG">
<img src="image/3.PNG">
<img src="image/4.PNG">
<img src="image/5.PNG">
<img src="image/6.PNG">
<img src="image/7.PNG">
<img src="image/8.PNG">
<img src="image/9.PNG">
<img src="image/10.PNG">
<img src="image/11.PNG">
<img src="image/12.PNG">
<img src="image/13.PNG">
<img src="image/14.PNG">
<img src="image/15.PNG">
<img src="image/16.PNG">

## Cài đặt

Trước tiên cd /opt/zimbra/ssl/zimbra/commercial/

1. Tạo file commercial.crt
<img src="image/23.PNG">

2. Tạo file commercial_ca.crt

<img src="image/24.PNG">


3. Tạo file commercial.key lấy nội dung từ file .pem

<img src="image/25.PNG">

4. Verify chứng chỉ

- Trước tiên cấp quyền:
    + chown zimbra:zimbra * -R

- su zimbra
- /opt/zimbra/bin/zmcertmgr verifycrt comm

<img src="image/26.PNG">

5. Deploy chứng chỉ

- /opt/zimbra/bin/zmcertmgr deploycrt comm commercial.crt ./commercial_ca.crt

<img src="image/22.PNG">

6. Khởi động lại zimbra

- zmcontrol restart 

5. Xem thông tin chứng chỉ đã cài đặt bằng lệnh
- /opt/zimbra/bin/zmcertmgr viewdeployedcrt
<img src="image/27.PNG">

6. Xem thành quả trực tiếp:

<img src="image/28.PNG">
