# Giới thiệu về Iptables
- Iptables là một hệ thống tường lửa (Firewall) tiêu chuẩn được cấu hình, tích hợp mặc định trong hầu hết các bản phân phối của hệ điều hành Linux (CentOS, Ubuntu…). Iptables hoạt động dựa trên việc phân loại và thực thi các package ra/vào theo các quy tắc được thiết lập từ trước.

# Cài Đặt Iptables trên Centos 7
- Cài đặt gói :
    + yum install iptables

- Xem phiên bản và trạng thái của IPtables:
    + rpm -q iptables
    + service iptables status

<img src="image/1.PNG">


- Chưa chạy do Centos 7 sử dụng FirewallD làm tưởng lửa mặc định, nên ta cần làm:

    + systemctl mask firewalld
    + systemctl enable iptables
    + systemctl enable ip6tables
    + systemctl stop firewalld
    + systemctl start iptables
    + systemctl start ip6tables

    <img src="image/2.PNG">

- Đã chạy.

# Một số nguyên tắc áp dụng trong Iptables

- Đầu tiên cần xác định các service muốn đóng/mở và các port tương ứng. Ví dụ:
    + Để truy cập VPS bằng SSH, cần mở port SSH - 22
    + Truy cập Website, cần mở port HTTP - 80 và HTTPS - 443
    + Để gửi mail, cần mở port SMTP - 22 và SMTPS - 465/587
    + Để người dùng nhạn được mail, cần mở port POP3 -110, POP3S - 995, IMAP - 143 và IMAPS - 993.

- Sau khi đã xác định được các port cần mờ, cần thiết lập các qui tắt tường lửa tương ứng để cho phép.

- Xem các rules hiện tại:
    + iptables -L

<img src="image/3.PNG">

- Clear đi rules cũ dùng :
    + iptables -F

<img src="image/4.PNG">

- Thông tin về các cột :
    + Cột 1 target: Hành động sẽ được áp dụng cho mỗi qui tắc, gồm:
        - Accept : gói dữ liệu được chuyển tiếp để xử lí tại ứng dụng cuối hoặc hệ điều hành
        - Drop: gói dữ liệu bị chặn, loại bỏ
        - Reject: gói dữ liệu bị chặn, loại bỏ đồng thời gửi một thông báo lỗi tới người gửi
    + Cột 2: PROT (protocol – giao thức) quy định các giao thức sẽ được áp dụng để thực thi quy tắc, bao gồm all, TCP hay UDP. Các ứng dụng SSH, FTP, sFTP… đều sử dụng giao thức TCP.

    + Cột 4, 5: SOURCE và DESTINATION địa chỉ của lượt truy cập được phép áp dụng quy tắc

# Các sử dụng iptables để mở port cho VPS
- Để mở port trong iptables, cần chèn chuỗi ACCEPT PORT. Cấu trúc lệnh để mở port xxx như sau:
    + iptables -A INPUT -p tcp -m tcp --dport xxx -j ACCEPT
    + iptables -I INPUT -p tcp -m tcp --dport xxx -j ACCEPT

- A tức Append – chèn vào chuỗi INPUT (chèn xuống cuối)
- I tức Insert - chèn vào chuỗi INPUT (chèn vào dòng chỉ định rulenum)
- Để tránh xung đột với rule gốc, các bạn nên chèn rule vào đầu, sử dụng -I

## Mở port SSH
- Để truy cập VPS qua SSH, bạn cần mở port SSH 22:
    + iptables -I INPUT -p tcp -m tcp --dport 22 -j ACCEPT

<img src="image/5.PNG">

- Có thể cho phép kết nối VPS qua SSH duy nhất từ 1 ip bằng lệnh:

    + iptables -I INPUT -p tcp -s 117.4.255.125 -m tcp --dport 22 -j ACCEPT

    <img src="image/7.PNG">

## Mở port Webserver

- iptables -I INPUT -p tcp -m tcp --dport 80 -j ACCEPT
- iptables -I INPUT -p tcp -m tcp --dport 443 -j ACCEPT
 <img src="image/8.PNG">

## Mở port Mail
- SMTP
    + iptables -I INPUT -p tcp -m tcp --dport 25 -j ACCEPT
    + iptables -I INPUT -p tcp -m tcp --dport 465 -j ACCEPT
- POP3
    + iptables -A INPUT -p tcp -m tcp --dport 110 -j ACCEPT
    + iptables -A INPUT -p tcp -m tcp --dport 995 -j ACCEPT
- IMAP
    + iptables -A INPUT -p tcp -m tcp --dport 143 -j ACCEPT
    + iptables -A INPUT -p tcp -m tcp --dport 993 -j ACCEPT

<img src="image/9.PNG">

## Chặn 1 IP truy cập

- iptables -A INPUT -s IP_ADDRESS -j DROP

- Chặn 1 IP truy cập 1 port cụ thể:

    + iptables -A INPUT -p tcp -s IP_ADDRESS –dport PORT -j DROP

## Bước cuối :

- Sau khi đã thiết lập đầy đủ, bao gồm mở các port cần thiết hay hạn chế các kết nối, cần block toàn bộ các kết nối còn lại và cho phép toàn bộ các kết nối ra ngoài từ VPS.
    + iptables -P OUTPUT ACCEPT
    + iptables -P INPUT DROP

- Load lại:
    + Service reload iptables

## Các remove 1 rule

- Đầu tiên cần tìm dòng của rule đấy:

    + iptables -L INPUT --line-numbers

    <img src="image/10.PNG">

- Xóa theo dòng:

    + sudo iptables -D INPUT 5

    <img src="image/11.PNG">