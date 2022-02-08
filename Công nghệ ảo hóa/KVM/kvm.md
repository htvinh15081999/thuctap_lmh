# KVM
## KVM là gì
- Thuật ngữ KVM là từ viết tắt của Kernel-based Virtual Machine (Máy ảo dựa trên hạt nhân). Sử dụng môi trường máy tính ảo không yêu cầu phần cứng bổ sung để thiết lập. Thay vào đó, nó sử dụng tài nguyên từ hệ thống máy tính hiện có (bao gồm cả phần cứng) đang lưu trữ nó. Sử dụng KVM với không gian người dùng cho phép người dùng thiết lập môi trường ảo cho nhiều mục đích sử dụng, bao gồm kiểm thử phần mềm và các không gian làm việc của người dùng khác.

## Yêu cầu của hệ thống KVM

- Việc sử dụng KVM trên một hệ thống máy vi tính cụ thể yêu cầu bộ xử lý phải có phần mở rộng được ảo hóa phần cứng. KVM hỗ trợ một số loại bộ xử lý: x86, S/390, PowerPC và IA-64. 
- Môi trường KVM sử dụng một BIOS cụ thể được gọi là SeaBIOS và có khả năng mô phỏng các thành phần phần cứng như card màn hình, card âm thanh, card mạng, RAM và CPU. Việc quản lý các môi trường này có thể được thực hiện thông qua việc sử dụng một số công cụ quản lý đồ họa, bao gồm Witsbits, ConVirt, OpenNode, SolusVM và Virtualbricks.

## Đặc điểm của KVM
- Công nghệ ảo hóa KVM có cách hoạt động giống như người quản lý, giúp chia sẻ các nguồn tài nguyên ổ đĩa, network, CPU một cách công bằng. Ngoài ra, công nghệ ảo hóa KVM nguồn mở còn được tích hợp trong Linux như sau: 
    + Với công nghệ ảo hóa KVM, bạn có thể chuyển Linux thành ảo hóa để máy chủ chạy trên nhiều môi trường ảo bị cô lập gọi là máy khách hoặc máy ảo VM. 
    + KVM là một phần của mã Linux và được hưởng lợi từ các tính năng, khi đó, KVM sẽ được hưởng lợi từ mọi tính năng, khả năng sửa lỗi và tiến bộ cập nhật mới của Linux mà không cần kỹ thuật bổ sung. 
    + Ảo hóa KVM không có tài nguyên dùng chung, bởi chúng đã được mặc định sẵn để chia sẻ. Do vậy mà RAM của mỗi KVM được định sẵn cho từng gói VPS, để có thể tận dụng triệt để 100% và không bị chia sẻ. Điều này sẽ giúp cho chúng hoạt động được ổn định hơn, ngoài ra sẽ không bị ảnh hưởng bởi các VPS khác chung hệ thống. Tương tự, với các tài nguyên ở ổ cứng cũng được định sẵn phân chia như RAM.
## Các hoạt động của KVM

- KVM giúp cung cấp một số thành phần cấp hệ điều hành, chẳng hạn như trình quản lý bộ nhớ, bộ lập lịch xử lý, ngăn xếp đầu vào / đầu ra (I/O), trình điều khiển thiết bị, trình quản lý bảo mật, ngăn xếp mạng … để có thể chạy ảo hóa. Mọi ảo hóa sẽ được triển khai như một quy trình Linux thông thường, được lên lịch sẵn bởi bộ lập lịch Linux tiêu chuẩn,với phần cứng ảo chuyên dụng như card mạng, bộ điều hợp đồ họa, CPU, bộ nhớ và đĩa.

## Tính năng công nghệ ảo hóa KVM

- Tính năng bảo mật 
    + Khi công nghệ KVM kết hợp với Linux sẽ giúp tăng khả năng bảo mật SELinux (xây dựng ranh giới bảo mật quanh máy ảo), sVirt (đẩy mạnh khả năng của SELinux, tăng khả năng bảo mật kiểm soát truy cập bắt buộc MAC dùng cho máy ảo khách, chống lỗi ghi nhãn thủ công, cách ly VM) 
- Lưu trữ 
    + KVM cho phép người dùng được sử dụng các bộ lưu trữ được Linux hỗ trợ như: bộ lưu trữ gắn mạng NAS, địa cục bộ,… Khi đó, bạn cũng có thể chia sẻ tệp để hình ảnh ảo hóa bởi nhiều máy chủ. 
- Hỗ trợ phần cứng 
    + Công nghệ KVM cũng có thể sử dụng được nhiều nền tảng phần cứng được Linux hỗ trợ. 
- Quản lý bộ nhớ 
    + KVM được sở hữu các chức năng quản lý bộ nhớ của Linux, chúng giúp hỗ trợ truy cập bộ nhớ không đồng nhất, hợp nhất kernel cùng tran. Khi đó, bộ nhớ ảo hóa KVM có khả năng hoán đổi có hiệu suất tốt, được chia sẻ hoặc sao lưu bởi một tệp đĩa. 
- Di chuyển công nghệ ảo hóa KVM trực tiếp 
    + KVM sẽ cho phép bạn di chuyển ảo hóa trực tiếp – nghĩa là di chuyển một chương trình ảo hóa đang chạy mà không gây ra sự gián đoạn giữa các máy chủ vật lý. Lúc này, KVM vẫn được bật, mọi kết nối mạng và ứng dụng vẫn hoạt động bình thường. Đồng thời trong quá trình di chuyển nó không quên thực hiện cả các thao tác lưu trữ. 
- Hiệu suất, khả năng mở rộng 
    + Do KVM sở hữu các ưu điểm của của Linux, đồng thời có khả năng mở rộng giúp phù hợp để đáp ứng nhu cầu khi máy khách và yêu cầu truy cập tăng lên nhiều lần. Ngoài ra, công nghệ KVM cho phép khối lượng công việc ứng dụng yêu cầu khắt khe nhất được ảo hóa và là cơ sở cho nhiều thiết lập ảo hóa doanh nghiệp, điển hình như: trung tâm dữ liệu, máy chủ ảo vps và công nghệ đám mây riêng. 
- Độ trễ thấp hơn 
    + Do Linux có các phần cho phép mở rộng thời gian thực tế để các ứng dụng dựa trên KVM chạy trong một chế độ trễ thấp hơn với mức độ ưu tiên tốt hơn. Đồng thời, chúng cũng tiến hành phân chia các quá trình yêu cầu một khoảng thời gian dài tính toán thành các khoảng nhỏ hơn, rồi sau đó lên lịch để xử lý tương ứng.
- Quản lý với KVM 
    + Thông qua KVM cho phép quản lý thủ công chương trình ảo hóa sau khi được kích hoạt từ máy trạm mà không cần thông qua công cụ quản lý. Chức năng này thường được các doanh nghiệp lớn sử dụng để quản trị nguồn tài nguyên, tăng khả năng phân tích dữ liệu, hợp lý các hoạt động.

## Ưu điểm của KVM 
- Khả năng linh hoạt: Mặc dù máy chủ gốc được cài đặt Linux, nhưng KVM hỗ trợ tạo máy chủ ảo có thể chạy cả Linux, Windows. Khi được sử dụng kết hợp với QEMU, KVM có thể chạy MacOSX. Ngoài ra, KVM cũng hỗ trợ cả x86 và x86-64 system. 
- Có tính độc quyền cao: Cấu hình từng gói VPS KVM sẽ chỉ được một người sở hữu và toàn quyền sử dụng tài nguyên đó (bao gồm CPU, RAM, DISK SPACE…) mà không hề bị chia sẻ hay ảnh hưởng bởi các VPS khác hoạt động trên cùng hệ thống. 
- Độ bảo mật chắc chắn: Nhờ tích hợp các đặc điểm bảo mật của Linux như SELinux với các cơ chế bảo mật nhiều lớp, KVM bảo vệ các máy ảo tối đa và cách ly hoàn toàn, tránh bị xâm hại. 
- Giúp tiết kiệm chi phí, độ mở rộng cao: do được phát triển trên nền tảng mã nguồn mở hoàn toàn miễn phí và được hỗ trợ từ cộng đồng và nhà sản xuất thiết bị, KVM ngày càng lớn mạnh và trở thành một lựa chọn hàng đầu cho doanh nghiệp có chi phí thấp nhưng hiệu quả sử dụng đem lại cao. 
## Nhược điểm của KVM 
- Cần yêu cầu cao về máy chủ: Do là công nghệ ảo hóa hoàn toàn phần cứng, KVM yêu cầu cấu hình server vật lý cao. 
- KVM chỉ có sẵn trong các hệ thống Linux 
- Cần nhiều thời gian để nghiên cứu và học tập để có thể đưa vào sử dụng 
- Do tập trung hóa phần cứng nên rủi ro tăng cao trong trường hợp hệ thống bị lỗi.

