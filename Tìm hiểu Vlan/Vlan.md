# 1. Tổng quan về Vlans
## 1.1 Giới thiệu
<img src="image/1.PNG">

- VLAN là viết tắt của Virtual Local Area Network hay còn gọi là mạng LAN ảo. Một VLAN được định nghĩa là một nhóm logic các thiết bị mạng và được thiết lập dựa trên các yếu tố như chức năng, bộ phận, ứng dụng… của công ty.

- Việc đặt các thiết bị vào các VLAN khác nhau có các đặc điểm sau:
    + Cung cấp phân đoạn các nhóm thiết bị khác nhau trên cùng một switch.
    + Cung cấp tổ chức dễ quản lý hơn
    + Broadcast, multicast và unicast được tách biệt trong VLAN riêng lẻ
    + Mỗi VLAN sẽ có dải địa chỉ IP riêng
    + Miền quảng bá nhỏ hơn

## 1.2 Lợi ích khi sử dụng Vlan: 
- Miền quảng bá nhỏ hơn: Chia mạng Lan ra nhỏ hơn, từ đó làm giảm kích thước miền quảng bá 
- Cái thiện về bảo mật: Chỉ có người dùng ở cùng Vlan mới có thể giao tiếp được với nhau
- Nâng cao hiệu quả IT: Vlans có thể nhóm các thiết bị với các yêu cầu tương ứng.
- Giảm chi phí: Một switch có thể hỗ trợ nhiều nhóm hoặc VLans khác nhau. 
- Hiệu năng tốt hơn: Với miền quảng bá nhỏ, sẽ giảm lưu lượng và tăng băng thông.
- Quản lí đơn giản hơn: Những nhóm tương tự nhau sẽ cần những ứng dụng giống nhau.

## 1.3 Phân loại Vlan

- Default Vlan: Vlan 1 là

    <img src="image/2.PNG">

    + Default Vlan
    + Dafault Native Vlan
    + Default Management Vlan
    + Không thế xóa hoặc đổi tên
- Data Vlan
    + Dành riêng cho lưu lượng truy cập của người dùng (email hoặc lướt web)
    + Vlan 1 là default data Vlan bởi vì tất cả các interface đều chỉ định tới với Vlan này
- Native Vlan
    + Chỉ sử dụng cho liên kết trunk
    + Tất cả frame đều được gán nhãn 802.1Q trừ các frame trên Native Vlan
- Management Vlan
    + Được sử dụng cho những traffic VTY telet/ssh và không dùng với traffic end user.
    + Thông thường, Vlan này là SVI cho switch layer 2.
- Voice Vlan   
    <img src="image/3.PNG">

    + Cần có 1 Vlan riêng vì Voice Traffic yêu cầu:
        - Băng thông đàm bảo
        - Ưu tiên QoS cao (Quaility of Service)
        - Khả năng tránh tắc nghẽn
        - Trễ ít hơn 150 ms từ nguồn đến đích
        - Toàn bộ mạng phải được thiết kế để hỗ trợ giọng nói


# 2. Vlan là một môi trường Multi Switched
- Định nghĩa một Vlan Trunks
    <img src="image/4.PNG">
    + Đường trunk là một liên kết điểm - điểm giữa hai thiết bị mạng.
    + Các chức năng của trunk cisco: 
        - Cho phép nhiều hơn một VLAN
        - Mở rộng VLAN trên toàn bộ mạng
        - Theo mặc định, hỗ trợ tất cả các VLAN
        - Hỗ trợ 802.1Q trunking

    <img src="image/5.PNG">

    + Nếu không cấu hình Vlan, tất cả các thiết bị kết nối với switch sẽ nhật được tất cả traffic unicast, multicast và broadcast.

    <img src="image/6.PNG">

    + Khi có Vlan, traffic unicast, multicast và broadcast được giới hạn trong một Vlan. Nếu không có thiết bị Layer 3 để kết nối các Vlan, các thiết bị trong Vlan khác nhau không thể giao tiếp.

- Định nghĩa Vlan với 1 tag
 
    <img src="image/7.PNG">
    + Header IEEE 802.1Q có độ dài 4 byte
    + Khi tag được tạo, FCS phải được tính toán lại.(frame check sequence)
    + Khi gửi tới điểm cuối, tag này phải được xóa và FCS được tính toán lại như lúc ban đầu.

    |Trường 802.1Q Vlan tag|Function|
    |----------------------|-------------------------------------------|
    |Type|2 bytes, với giá trị hex là 0x8100, được dùng như 1 Tag Protocal ID|
    |Ưu tiên người dùng|3 bit  |
    |CFI(Canonical Format Identifier)|1 bit, có thể hỗ trợ token ring frame trong Ethernet|
    |Vlan ID(VID)|12 bit, hỗ trợ lên đến 4096 Vlan|

- Native Vlan và tag 802.1Q: Đường trunk 802.1Q đơn giản:
    <img src="image/8.PNG">
    + Việc gắn thẻ thường được thực hiện trên tất cả các VLAN.
    + Việc sử dụng một VLAN gốc được thiết kế để sử dụng kế thừa, giống như hub ở trong hình.
    + Trừ khi được thay đổi, VLAN1 là Native Vlan.
    + Cả hai đầu của một liên kết trunk phải được cấu hình với cùng một VLAN gốc.
    + Mỗi trunk được cấu hình riêng biệt, vì vậy có thể có VLAN gốc khác nhau trên các trung kế riêng biệt.
# 3. Cấu hình Vlan


# 4. Vlans Trunk
# 5. Dynamic Trunking Protocol