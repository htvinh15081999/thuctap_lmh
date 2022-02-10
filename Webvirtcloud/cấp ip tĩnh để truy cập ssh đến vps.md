# Các bước thực hiện

1. Đầu tiên chọn vps cần đổi ip ở intances

<img src="image/111.PNG">

2. Tắt nguồn máy 

<img src="image/112.PNG">

3. Vào setting

<img src="image/113.PNG">

4. Chọn network

<img src="image/114.PNG">

5. Ở phần nic, nếu chưa ở card vlan172 thì đổi thành vlan 172 sau đó apply,  không thì bỏ qua bước này

<img src="image/115.PNG">

6. Cấp nguồn lại

<img src="image/116.PNG">

7. Vào accces chọn console

<img src="image/117.PNG">

8. Ban đầu chưa có ip, card mạng là eth0

<img src="image/118.PNG">

9. Restart card mạng

- ifdown eth0

- ifup eth0

10. Đã có ip động, giờ cần đổi về ip tĩnh

<img src="image/119.PNG">

11. Mở file cấu hình mạng
- nano /etc/sysconfig/network-scripts/ifcfg-eth0

12. Cấu hình :

<img src="image/120.PNG">

- BOOTPROTO đổi từ DHCP sang Static

- ONBOOT đổi từ yes thành no

- Thêm 3 dòng IPADDR, NETMASK, GATEWAY (Cái này bảo a quản lí con gốc, không cho linh tinh được)


13. Lưu lại rồi restart mạng

- Systemctl restart network

14. Kiểm tra lại và ping thử

<img src="image/121.PNG">

- ok đã ăn IP tĩnh

15. Thử kết nối SSH

<img src="image/122.PNG">

- OK


