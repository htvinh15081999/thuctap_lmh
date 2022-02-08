# Open VZ
*https://en.wikipedia.org/wiki/OpenVZ*
## Giới thiệu

- OpenVZ là một công nghệ ảo hóa cấp hệ điều hành dành cho Linux. Nó cho phép một náy chủ vật lí chạy nhiều phiên bản hệ điều hành riêng biệt, được gọi là container, VPS, VEs(virtual environments). OpenVZ thì đơn giản hơn so với Solaris Container và LXC.

## So sánh OpenVZ với các công nghệ ảo hóa khác.

- Trong khi các công nghệ ảo hóa khác như VMWare, Xen hay KVM cung cấp khả năng ảo hóa đẩy đủ và có thể chạy nhiều hệ điều hành và các phiên bản nhân khác nhau, OpenVZ sử dụng một nhân Linux duy nhất và do đó chỉ có thể chạy Linux. 
- Tất cả các Container cùng chia sẻ một kiến trục và phiên bản Kernal. Điều này có thể gây bất lợi trong các tình huống mà khách hàng yêu cầu các phiên bản kernal khác với phiên bản của máy chủ. 
- Tuy nhiên, OpenVZ rất nhanh và hiệu quả.

## Kernal của OpenVZ

- Nhân của OpenVZ là một nhân Linux, được sủa đổi để thêm hỗ trợ cho các container OpenVZ. Kernal đã sửa đổi cung cấp ảo hóa, cô lập và quản lí tài nguyên. Kể từ vzctl 4.0, OpenVZ có thể hoạt động với các nhân Linux 3.x chưa được vá lỗi, với bộ tính năng bị lược giảm.

### Ảo hóa và cô lập
- Mỗi một container là một thực thể riêng biệt và hoạt động phần lớn như một máy chủ vật lí
- Mỗi cái đều có:
    + Các tập itn :Thư viện hệ thống, ứng dụng, ảo hóa /proc và /sys, khóa ảo...
    + Người dùng và nhóm: Mỗi container có root user riêng của nó, cũng như những user và gr khác.

    + Cây xử lí: Một container chỉ thấy được các qui trình của chính nó. PID được ảo hóa.
    + Mạng: Thiết bị mạng ảo, cho phép container có ip riêng, cũng như các rules tường lửa quà qui tắc định tuyến riêng.

    + Thiết bị: Nếu cần, bất kỳ container nào cũng có thể được cấp quyền truy cập vào các thiệt bị thực như network interface, phân vùng ổ đĩa...

### Quản lí tài nguyên
- Quản lí tài nguyên trong OpenVZ bao gồm 4 thành phần: Giới hạn đĩa 2 cấp, lịch CPU, Lịch I/O và bộ đếm người dùng

### Hạn chế của OpenVZ

- Theo mặc định, OpenVZ hạn chế quyền truy cập vùng chứa đối với các thiết bị vật lí thực, do đó làm cho vùng chứa không phụ thuộc vào phần cứng. Admin OpenVZ có thể cho phép truy cập container vào các thiết bị thực khác nhau, chặng hạn như ổ đĩa, cồng usb...
- /dev/loopN thường bị hạn chế trong triển khai.

- OpenVZ bị giới hạn chỉ cung cấp một số công nghệ VPN dựa trên PPP (PPTP, L2TP) và TUN/TAP. IPsec được hỗ trợ trong container kể từ kernal 2.6.32