## DNS là gì
- The Domain Name System (DNS) được hiểu gần như là quyền danh bạ điện thoại trên Internet.
- Con người truy cập thông tin trực tuyến thông qua tên miền. Còn trình duyệt web thì tương tác thông qua địa chỉ IP.
- DNS chuyển đổi tên miền sang địa chỉ IP để trình duyệt có thể tải được các tài nguyên trên Internet.
- Mỗi cái thiết bị được kết nối vơi Internet có một địa chỉ duy nhất mà các máy khác sử dụng để tìm, truy cập đến. Máy chủ DNS loại bỏ việc con người phải nhớ các địa chỉ phức tạp như IPv4 và IPv6.

    <img src="image/1.PNG">

## DNS hoạt động như thế nào.
- Quá trình phân giải DNS bao gồm việc chuyển đổi tên máy chủ thành địa chỉ IP. Một địa chỉ IP được cấp cho mỗi thiết bị trên Internet và địa chỉ đó là cần thiết để tìm thiết bị Internet thích hợp - giống như địa chỉ đường phố được sử dụng để tìm một ngôi nhà cụ thể. 
- Để hiểu quy trình đằng sau quá trình phân giải DNS, điều quan trọng là phải tìm hiểu về các thành phần phần cứng mà một truy vấn DNS cần phải trải qua . Đối với trình duyệt web, việc tra cứu DNS diễn ra ở phía sau và NGƯỜI DÙNG KHÔNG CẦN QUAN TÂM ĐẾN QUÁ TRÌNH ĐẤY.

## 4 máy chủ DNS liên quan đến việc tải 1 trang web

1. DNS recursor
- DNS Recursor (DNS đệ quy) - Recursor có thể được coi như một thủ thư, người được yêu cầu đi tìm một cuốn sách cụ thể ở đâu đó trong thư viện. DNS Recursor là một máy chủ được thiết kế để nhận các truy vấn từ các máy khách thông qua các ứng dụng như trình duyệt web. Thông thường, DNS Recursor sau đó chịu trách nhiệm thực hiện các yêu cầu bổ sung để đáp ứng truy vấn DNS của khách hàng.
2. Root Nameserver
- Root Nameserver (Máy chủ định danh gốc) - root server là bước đầu tiên trong việc phân giải các tên máy chủ có thể đọc được của con người thành địa chỉ IP. Nó có thể được coi như một chỉ mục trong thư viện trỏ đến các giá sách khác nhau.
3. TLD nameserver
- TLD nameserver (Máy chủ định danh TLD) - Top level domain server( TLD ) có thể được coi như một giá sách cụ thể trong thư viện. Máy chủ định danh này là bước tiếp theo trong quá trình tìm kiếm địa chỉ IP cụ thể và nó lưu trữ phần cuối cùng của tên máy chủ (Trong example.com, máy chủ TLD là “com”).

4. Authoritative nameserver
- Authoritative nameserver (Máy chủ định danh có thẩm quyền)  - The final nameserver, Máy chủ định danh cuối cùng này có thể được coi như một cuốn từ điển trên giá sách, trong đó một tên cụ thể có thể được dịch theo định nghĩa của nó. Máy chủ định danh có thẩm quyền là điểm dừng cuối cùng trong truy vấn máy chủ định danh. Nếu máy chủ định danh có thẩm quyền có quyền truy cập vào bản ghi được yêu cầu, nó sẽ trả lại địa chỉ IP cho  DNS Recursor (thủ thư) , sau đó DNS Recursor sẽ trả lại thông tin cho người yêu cầu.

## Các bước để truy vấn DNS
1. Người dùng nhập thông tin, ví dụ như nhanhoa.com vào trình duyệt web. Một truy vấn sẽ được tạo ra và được nhận bởi trình phân giải đệ qui - DNS Recursive Resolver 
2. Trình phân giải này sẽ truy vấn tớt một root nameserver.
3. Root server sẽ phả hổi resolver một cái địa chỉ của TLD server, tùy theo thông tin mà ta nhập vào sẽ chuyển đến TLD khác nhau, trong ví dụ này sẽ là .com TLD.
4. Resolver sẽ tạo một request đến .com TLD.
5. TLD server sẽ phản hổi với một cái địa chỉ của domain's nameserver.
6. Resolver sẽ gửi 1 cái truy vấn đến domain's nameserver.
7. Một cái địa chỉ IP sẽ được trả lại cho resolver từ nameserver.
8. Resolver sẽ phản hổi lại cho trình duyệt web cái địa chỉ ip của cái domain.
## Trình phân giải DNS - Resolver là gì
- Resolver là điểm đầu tiên trong việc tra cứu DNS, nó chịu trách nhiệm xử lí ứng dụng khách đã đưa ra yêu cầu ban đầu. Resolver sẽ bắt đầu 1 chuỗi các truy vấn để cuổi cùng có cái IP của cái tên miền ban đầu.
- Phân biệt giữa DNS Recursor và DNS Recursive Resolver .

    <img src="image/2.PNG">

