### Giới thiệu về DNS
- DNS - Domain Name System là một hệ thống dùng để ánh xạ tên miền thành địa chỉ IP và ngược lại.

### Mục đích của DNS
- Phân giải tên miền thành địa chỉ IP và ngược lại
- Phân giải tên domain.

### Cấu trúc của hệ thống tên miền
- Hiện nay hệ thống tên miền được phân thành nhiều cấp:
    + Gốc - Domain root : Mó là đỉnh của nhánh cây tên miền. Có thể biểu diễn đơn giản chỉ là dấu chấm "."
    + Tên miền cấp một (Top-level-domain): Gồm vài kí tự xác định một nước, khu vực hoặc tổ chức. VD: .com, .edu, 
    + Tên miền cấp hai (Second-level-domain): Nó rất đa dạng, có thể là tên một công ty, một tổ chức hay một cá nhân.
    + Tên miền cấp nhỏ hơn (Subdomain): Chia thêm ra của tên miền cấp hai trở xuống, thường được sử dụng như chi nhánh, phòng ban của một cơ quan hay chủ đề nào đó.

### Phân loại tên miền
- Com: Tên miền này được dùng cho các tổ chức thương mại.
- Edu: tên miền này được dùng cho các cơ quan giáo dục, trường học.
- Net: Tên miền này được dùng cho các tổ chức mạng lớn.
- Gov: Tên miền này được dùng cho các tổ chức chính phủ.
- Org: Tên miền này được dùng cho các tổ chức khác
- Int : dùng cho các tổ chức quốc tế.
- Info: Dùng cho việc phục vụ thông tin
- Arpa: Tên miền ngược
- Mil: Tên miền dùng cho các tổ chức quân sự, quốc phòng.
- Mã các quốc gia trên thế giới tham gia vào mạng internet, các quốc gia này được qui định bằng 2 chữ cái đầu theo tiêu chuẩn ISO-3166. Ví dụ: Việt Nam - .vn, Trung Quốc - .cn, Nhật Bản - .jp ....

### DNS Server
- Là một cơ sở dữ liệu chứa các thông tin về vị trí của các DNS domain và phân giải các truy vấn xuất phát từ các Client.
- DNS Server có thể cung cấp các thông tin do client yêu cầu, và chuyển đến một DNS server khác để nhờ phân giải hộ trong trường hợp nó không thể trả lời được các truy vấn về những tên miền không thuộc quyền quản lí và cùng luôn sãn sàng trả lời các máy chủ khác về tên miền mà nó quản lí. DNS server lưu thông tin của Zone, truy vấn và trả kết quả cho DNS Client.
- Máy chủ quản lí DNS cao cấp nhất là Root Server do tổ chức ICANN quả lí:
    + Là Server quản lí toàn bộ cấu trúc của hệ thống trên miền
    + Root Server không chứa dữ liệu thông tin về cấu trúc hệ thống DNS mà nó chỉ chuyển quyền quản lí xuống cho các Server cấp thấp hơn và do đó Root Server có khả năng định đường đến của một domain tại bất kì đâu trên mạng.
***Phân loại DNS Server
- Primary Server:
    + Được tạo ra khi ta add một Primary Zone mới thông qua New Zone Wizard.
    - Thông tin về tên miền do nó quản lí được lưu trữ tại đây và sau đó có thể được chuyển sang cho các Secondary Server. 
- Secondary Server:
- Caching-only Server
- Stub Server

### DNS Zone*
- Là tập hợp các ánh xạ từ host đến địa chỉ IP và từ IP đến host của một phần liên tục trong một nhánh của domain.
- Thông tin của DNS Zones là những record bao gồm tên Host và địa chỉ IP được lưu trong DNS Server, DNS Server  quản lí và trả lời những yêu cầu từ Client liên quan đến DNS Zones này.
- Hệ thống DNS cho phép phân chia tên miền để quản lí và nó chia hệ thống tên miền thành các Zone, trong ZOne quản lí tên miền được chia đó. Các Zone chứa thông tin về miền cấp thấp hơn, có khả năng chia thành các Zone cấp thấp hơn và phân quyền cho các DNS Server khác quản lí.
- Zone file: Lưu thông tin của Zone, có thể ở dạng text hoặc rtong Active Directory.
- Có 2 loại ZOne: 
    + Standard Primary Zone 
    + Active Directory Integrated Zones.