# Ảo hóa

*Việc phân vùng ổ đĩa cũng được gọi là ảo hóa, vì từ 1 ổ đĩa cứng duy nhất chúng ta chia thành những ổ đĩa ảo*

## Giới thiệu về ảo hóa

- Trong máy tính, ảo hóa (virtualization) có nghĩa là tạo một phiên bản ảo của tài nguyên nào đó, chẳng hạn như server, storage device, network hoặc thậm chí operating system nơi framework chia tài nguyên thành một hoặc nhiều môi trường thực thi. 

- Các thiết bị, ứng dụng và người dùng có thể tương tác với tài nguyên ảo như thể nó là một tài nguyên logic thực sự duy nhất (single logical resource). Thuật ngữ ảo hóa đã trở thành một phần của các công nghệ máy tính, bao gồm:

    + Ảo hóa mạng (Network virtualization) là phương pháp kết hợp các tài nguyên sẵn có trong mạng bằng cách chia băng thông sẵn có thành các kênh, mỗi kênh độc lập với các kênh khác và mỗi kênh có thể được gán (hoặc gán lại) cho một máy chủ hoặc thiết bị cụ thể theo thời gian thực. Ý tưởng chính của Network virtualization là ảo hóa ngụy trang sự phức tạp thực sự của mạng bằng cách tách nó thành các phần có thể quản lý được, giống như ổ cứng được phân đoạn, giúp dễ dàng quản lý các tệp hơn.
    + Ảo hóa lưu trữ (Storage virtualization) là tổng hợp physical storage từ nhiều thiết bị lưu trữ mạng vào chỉ một thiết bị lưu trữ được quản lý từ bảng điều khiển trung tâm. Storage virtualization thường được sử dụng trong các mạng lưu trữ (SAN).
    + Ảo hóa máy chủ (Server virtualization) là ảo hóa tài nguyên máy chủ (bao gồm số và danh tính của máy chủ vật lý, bộ xử lý và hệ điều hành) từ server users. Mục đích là để người dùng tránh phải hiểu và quản lý các chi tiết phức tạp của tài nguyên máy chủ.
## Lợi ích của ảo hóa máy chủ (server virtualization)

1. Tiết kiệm năng lượng, thân thiện với môi trường (go green)
- Di chuyển các máy chủ vật lý thành các máy ảo và hợp nhất chúng vào số lượng ít các máy chủ vật lý hơn sẽ giúp bạn giảm chi phí điện và chi phí làm mát hàng tháng trong data center.

2. Máy chủ hoạt động nhanh hơn
- Ảo hóa máy chủ cho phép khả năng mở rộng hoặc thu hẹp quy mô trong quá trình triển khai hệ thống tại thời điểm có nhu cầu. Bạn có thể nhanh chóng sao chép một gold image, master template, hoặc virtual machine hiện có để có thể khởi chạy ngay một server trong vòng chỉ vài phút.

3. Tăng uptime
- Hầu hết các nền tảng ảo hóa máy chủ hiện cung cấp một số tính năng nâng cao mà máy chủ vật lý không có, giúp cải thiện tính liên tục của doanh nghiệp và tăng uptime. Mặc dù tên các tính năng của nhà cung cấp có thể khác nhau, nhưng chúng thường là các tính năng sau đây: live migration, storage migration, fault tolerance, high availability, và distributed resource scheduling. 

- Những công nghệ cung cấp khả năng phục hồi nhanh chóng từ các sự cố cúp điện không có kế hoạch. Khả năng di chuyển một máy ảo từ máy chủ này sang máy chủ khác nhanh chóng và dễ dàng có lẽ là một trong những lợi ích lớn nhất của ảo hóa, giúp ảo hóa được sử dụng rộng rãi. Khi công nghệ tiếp tục phát triển đến mức có thể thực hiện di chuyển đường dài (long-distance migration), chẳng hạn như có thể di chuyển máy ảo từ trung tâm dữ liệu này sang trung tâm dữ liệu khác bất kể độ trễ mạng.

4. Cải thiện disaster recovery
- Virtualization cung cấp cho tổ chức ba thành phần quan trọng trong việc xây dựng một giải pháp khắc phục thảm họa (disaster recovery solution).

    + Đầu tiên là khả năng trìu tượng hóa phần cứng. Bằng cách loại bỏ sự phụ thuộc vào một nhà cung cấp phần cứng hoặc mô hình máy chủ cụ thể, một disaster recovery site không còn cần phải giữ phần cứng giống nhau để phù hợp với môi trường làm việc và IT có thể tiết kiệm tiền bằng cách mua phần cứng rẻ hơn.
    + Thứ hai, bằng cách hợp nhất các máy chủ thành ít các máy vật lý hơn trong sản phẩm, một tổ chức có thể dễ dàng tạo ra một trang web nhân bản có giá cả phải chăng.
    + Thứ ba, hầu hết các nền tảng ảo hóa máy chủ doanh nghiệp đều có phần mềm có thể giúp tự động chịu lỗi khi xảy ra thảm họa. Các phần mềm tương tự cũng cung cấp một cách để kiểm tra disaster recovery failover. Bạn sẽ có thể thử nghiệm kế hoạch chuyển đổi dự phòng của mình sẽ hoạt động hiệu quả như thế nào trong thực tế, giúp bạn chuẩn bị tốt hơn cho những thảm họa bất ngờ trong tương lai.

# 2 loại Hypervisor.

## Loại 1 - Hypervisor Native
- Một hypervisor ở dạng native (hay còn gọi “bare-metal”) chạy trực tiếp trên phần cứng. Nó nằm giữa phần cứng và một hoặc nhiều hệ điều hành khách (guest operating system).


- Nó được khởi động trước cả hệ điều hành và tương tác trực tiếp với kernel. Điều này mang lại hiệu suất cao nhất có thể vì không có hệ điều hành chính nào cạnh tranh tài nguyên máy tính với nó. Tuy nhiên, nó cũng đồng nghĩa với việc hệ thống chỉ có thể được sử dụng để chạy các máy ảo vì hypervisor luôn phải chạy ngầm bên dưới.
## Loại 2 - Hypervisor Hosted
- Một hypervisor dạng hosted được cài đặt trên một máy tính chủ (host computer), mà trong đó có một hệ điều hành đã được cài đặt.


- Nó chạy như một ứng dụng cũng như các phần mềm khác trên máy tính.
- Hầu hết các hypervisor dạng hosted có thể quản lý và chạy nhiều máy ảo cùng một lúc. Lợi thế của một hypervisor dạng hosted là nó có thể được bật lên hoặc thoát ra khi cần thiết, giải phóng tài nguyên cho máy chủ. 
- Tuy nhiên, vì chạy bên trên một hệ điều hành, nó khó có thể đem lại hiệu suất tương tự như một hypervisor ở dạng native. Ví dụ về các hypervisor dạng hosted bao gồm VMware Workstation, Oracle VirtualBox và Parallels Desktop for Mac.
 