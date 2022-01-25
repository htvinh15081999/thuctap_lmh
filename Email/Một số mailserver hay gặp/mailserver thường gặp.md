# Một số mailserver hay gặp
*Sẽ tìm hiểu vè Zimbra, Mdeamon, Kerio, Gmail, Office 365 Outlook, Microsoft exchange*
## Zimbra Mailserver
### Zimbra là gì
- Zimbra được biết đến là bộ phần mềm bao gồm máy chủ email và máy khách website, hay nói cách khác dễ hiểu hơn, Zimbra Collaboration Suite(Zimbra) là một trong những ứng dụng nguồn mở miễn phí nổi tiếng về tính năng, độ định và bảo mật cao. Zimbra không chỉ đơn giản là tên của một ứng dụng về email mà nó còn là một giải pháp, một hệ thống khá hoàn chỉnh để triển khai môi trường chia sẻ công tác phục vụ cho quản lý và công việc.
### Tính năng chính
- Thư điện tử: một hệ thống thư điện tử hoàn chỉnh gồm Mail server (SMTP, POP3, IMAP, antivirus, antispam, openLDAP, backup, …, có đầy đủ các tính năng như auto-reply, auto-forward, mail filter, …) và Mail client (Zimbra desktop và Zimbra Web Client).
- Lịch công tác (calendar): lịch cá nhân và lịch nhóm, tự động gửi mail mời họp,…
- Sổ địa chỉ (Contacts): sổ cá nhân và sổ chung của nhóm
- Danh mục công việc (Task): của cá nhân và nhóm.
- Tài liệu (Documents): tài liệu dưới dạng wiki của cá nhân hoặc soạn tập thể
- Cặp hồ sơ (Briefcase): lưu file dùng riêng hoặc chung.
- Chat: chat nội bộ trong mạng LAN hoặc trên Internet.
- Tất cả các mục trên đều có phần chạy trên máy chủ (nằm trong Zimbra Server), lưu trên máy chủ để có thể dùng chung được và truy cập được từ bất kỳ đâu có Internet. (nếu cài trên máy chủ có Internet). Các mục đó đều có khả năng share (kể cả các thư mục email: Inbox, Sent) cho người khác dùng chung.
### Tương thích người dùng
- Zimbra có hai phần mềm client: Zimbra desktop và Zimbra Web client là giao diện với người dùng. Zimbra desktop (tương tự như Outlook, KMail,…) cài được trên Windows, Mac, Linux. Ngoài ra có thể dùng các mail client khác như Outlook, Evolution, KMail, Thunderbird, … Hai loại mail client trên ứng với hai cách làm việc:
    + Làm việc online, dùng Zimbra web client. Mọi thông tin sẽ lưu trên máy chủ Zimbra. Zimbra Web Client có hai giao diện: dạng html thông thường, nhanh nhưng ít tính năng và dạng Ajax (tương tự Yahoo Mail). Zimbra Web Client là một trong những Web Client hoàn chỉnh nhất hiện nay (hỗ trợ hầu hết tính năng của Zimbra Server, kể cả chat).
    + Làm việc offline, dùng các mail client còn lại. Riêng Outlook, Apple Desktop và Evolution có thể đồng bộ email, calendar, contacts và task với máy chủ Zimbra, các mail client khác chỉ dùng đọc và gửi email.
- Zimbra cũng hỗ trợ làm việc với các điện thoại di động iPhone, Blackberry, …
### Kiến trúc
- Về kiến trúc bên trong, Zimbra vẫn sử dụng các bộ phần mềm chức năng (nguồn mở) phổ biến như OpenLDAP, Postfix, SpamAssassin, Amavisd, Tomcat, … cùng với một số phần mềm riêng tạo nên một hệ thống tích hợp chặt chẽ. Có thể không dùng OpenLDAP mà dùng Windows Active Directory, hoặc import user từ một máy chủ Exchange sang.

- Hiện tại, Zimbra Server có các bản cài trên RedHat, Fedora, CentOS, Debian, SUSE, Ubuntu và MacOS. Nếu chỉ cài trên một máy chủ độc lập thì cách cài đặt khá đơn giản và nhanh.

- Zimbra có thể cài theo nhiều cấu hình khác nhau từ một hệ thống nhỏ vài chục account trên một máy chủ duy nhất cho đến hệ thống rất lớn hàng nghìn account trên nhiều máy chủ có các chức năng khác nhau. Có khả năng mở rộng (scalability) bằng cách thêm máy chủ dễ dàng.

- Zimbra có một kho các Zimlet (một thứ tương tự các extensions của Firefox) mà các quản trị mạng có thể chọn cài để bổ xung tính năng. Mọi người có thể tự viết các Zimlet để kết nối hệ thống Zimbra với các hệ thống thông tin khác hoặc mở rộng tính năng. Đây có lẽ là một trong những điểm mạnh nhất và sẽ gây nghiện cho người dùng giống như các extensions của Firefox vậy.
- Quản trị hệ thống qua giao diện web khá đầy đủ và chi tiết với nhiều tiện ích. Ví dụ có thể tạo hàng trăm account trong vài phút.

## Mdaemon Mailserver
### Mdaemon là gì
- MDaemon ( phát âm là M-Day-mon ) là một trong những mail server được sử dụng rộng rãi nhất trên thế giới , được khách hàng trên 90 quốc gia tin dùng để đáp ứng nhu cầu của các doanh nghiệp vừa và nhỏ. 
- MDaemon là một mailserver đáng tin cậy và an toàn, không yêu cầu quản trị tốn kém hoặc áp đặt chi phí cao cho mỗi người dùng. Nó đơn giản hóa các yêu cầu về nhắn tin và cộng tác với thiết kế trực quan, thân thiện với người dùng, cung cấp các tính năng cấp doanh nghiệp có thể được quản lý với sự đào tạo và hỗ trợ tối thiểu.
### TÍnh năng 
- MDaemon hỗ trợ các giao thức IMAP, SMTP và POP3 và mang lại hiệu suất ổn định nhờ thiết kế thân thiện và giàu tính năng của nó. Phần mềm máy chủ thư của chúng tôi mang lại giá trị tổng chi phí sở hữu (TCO) thấp được thiết kế để đáp ứng nhu cầu của khách hàng doanh nghiệp vừa và nhỏ. 
- MDaemon có sẵn bằng nhiều ngôn ngữ và hỗ trợ danh sách gửi thư, lọc nội dung, nhiều miền đồng thời cung cấp khả năng quản trị linh hoạt và thiết kế tiêu chuẩn mở.
- Các tính năng chính:
    + Bảo mật email
    + Mã hóa email
    + Lưu trữ email
    + Quản lí thiết bị di động
    + Quản trị từ xa
    + Webmail
    + Instant Message
    + Exchange
### Yêu cầu hệ thống
#### Server
-  Microsoft Windows 11 | Server 2022 | 2019 | 10 | 2016 | 8 | 2012 | 7 | 2008 R2
- Bộ xử lý CPU 800 MHz trở lên (khuyến nghị CPU lõi kép 2,4 GHz trở lên)
- RAM 512 MB (khuyến nghị 1 GB RAM)
- Không gian đĩa cứng điển hình yêu cầu: 200MB dung lượng trống, - không gian bổ sung cho bất kỳ thư nào được lưu trữ
- Đã cài đặt giao thức mạng TCP / IP
- Khả năng giao tiếp Internet hoặc Intranet
#### Client
- Microsoft Windows 10 | 8 | 7
- Microsoft Outlook 2019 | 2016 | 2013
- Bộ xử lý CPU 1 GHz trở lên (khuyến nghị CPU 2,4 GHz trở lên)
- RAM 1 GB
- Đã cài đặt giao thức mạng TCP / IP
- Dung lượng đĩa: 20MB dung lượng trống để cài đặt Trình kết nối MDaemon cho ứng dụng khách Outlook.\
- Khả năng giao tiếp Internet hoặc Intranet
- Mọi trình duyệt web hiện đại


## Kerio Mailserver
### Kerio Mailserver là gì
- Kerio MailServer đại diện cho một thế hệ các mail server mới được thiết kế cho các mạng công ty. 
- Để đối phó với các mối đe dọa bảo mật đang gia tăng, Kerio MailServer cung cấp hàng loạt các tính năng để bảo vệ email khỏi sự ngăn chặn và lây nhiễm do virus máy tính hoặc gởi email rác.
- Kerio MailServer là một email server an toàn hiện đại cho phép các công ty cộng tác với nhau qua email, các địa chỉ liên lạc, các lịch biểu và công việc chia sẻ.
### Lợi ích, tiêu biểu 
- Bảo mật mail: Kerio MailServer là một mail server đa domain bảo mật và cực nhanh, hoạt động với tất cả các mail clients POP3 và IMAP trên Windows, Linux và Mac.
- Chống virus: Chương trình chống virus nội trú độc đáo là một phần của cả hai phiên bản mail server: Kerio MailServer được tích hợp với McAfee Antivirus và Kerio MailServer hỗ trợ các phần mềm chống virus ngoại trú (Avast, AVG, eTrust, NOD32, Sophos, Symantec).
- Chức năng chống thư rác: Theo chuẩn, Kerio MailServer được tích hợp với phần mềm SpamEliminator cung cấp các chức năng phát hiện và cô lập các thư rác toàn diện. Một loạt các công cụ chống thư rác tiên tiến và mạnh mẽ như Caller ID, bảo vệ khỏi sự tấn công các thư mục và giới hạn băng thông giúp các công ty giảm đáng kể những nguy cơ bảo mật và pháp lý được liên kết với các thư rác.
- Kerio WebMail & Kerio WebMail Mini: Hai email clients có cơ sở web khác nhau, một có hình thức giống Microsoft Outlook và trình kia được tối ưu để xem email trên các thiết bị DPA cung cấp cho người dùng cả sử thoải mái và tốc độ trong khi làm việc với các trình duyệt web hiện đại nhất kể cả Safari và Firefox.
- Nhóm phần mềm: Nhằm thay thế cho Microsoft Exchange, Kerio MailServer cung cấp cách truy cập đến các lịch biểu, các địa chỉ liên lạc và các công việc đã được hia sẻ từ Microsoft Outlook, Microsoft Entourage, và Kerio WebMail, trong khi đó làm giảm chi phí của chủ sở hữu (TCO – Total Cost of Ownership) và mang lại kinh nghiệm sử dụng tốt hơn cho các doanh nghiệp vừa và nhỏ (SMEs – Small to Medium-sized Enterprises).
- Dễ quản trị: Các quản trị viên có thể download, cài đặt và cấu hình mail server chỉ trong vài phút. Các hướng dẫn trực quan đơn giản trợ giúp hầu hết các công việc quản trị thông dụng nhất. Bảng điều khiển quản trị cho phép truy cập từ xa an toàn và cung cấp các bookmarks cho nhiều server.
- Công cụ chuyển dời từ Microsoft Exchange: Để giúp các công ty chuyển dời từ Microsoft Exchange 5.5/2000/2003 sang Kerio MailServer, Kerio cung cấp công cụ Kerio Exchange Migration Tool. Nó chuyển dời các người sử dụng, cấu trúc thư mục, email, tất cả các attachment, lịch, sổ liên lạc và công việc.
- Dịch vụ thư mục: Quản lý các account người sử dụng trong Kerio MailServer có thể sử dụng cơ sở dữ liệu lưu trú hoặc các dịch vụ thư mục ngoại trú. Kerio MailServer tích hợp với Active Directory trên Windows và Apple Open Directory trên Mac OS X Server.
- Khả năng mở rộng: Kerio MailServer có thể mở rộng server gởi tin hỗ trợ 20 người sử dụng tại bất kỳ nơi nào, trong mạng nội bộ nhỏ, cho đến hàng ngàn người sử dụng hoạt động chỉ với một server. Một server dễ dàng hỗ trợ cùng lúc 500 người sử dụng IMAP với các bộ lọc chống thư rác và chống virus mà không ảnh hưởng đến hiệu quả hoạt động của nó.

## Gmail
### Gmail là gì
- Gmail là dịch vụ email miễn phí của Google. Người dùng có thể đăng ký, tạo tài khoản Gmail tại địa chỉ mail.google.com. Hiện nay, Gmail là địa chỉ email được nhiều người sử dụng nhất vì tính tiện dụng của nó và cũng vì ngày càng có nhiều người biết đến Gmail.

- Khi Gmail được ra mắt lần đầu, tốc độ phát triển của Gmail bị giới hạn bởi chính sách hạn chế mời bạn bè tạo tài khoản. Điều này giúp Gmail duy trì được danh tiếng của mình như là một dịch vụ email cao cấp. Tuy nhiên, sau đó, Gmail đã thay đổi chiến lược và vào ngày 14/2/2007, Gmail đã hủy bỏ chính sách giới hạn số người mở tài khoản. Kể từ đó đến nay, Gmail đã trở thành dịch vụ gửi email lớn nhất thế giới, vượt qua cả Yahoo Mail và Hotmail đình đám một thời.

### Tính năng chính của Gmail.
- Tính năng lọc thư rác
    + Hầu hết các dịch vụ email đều cung cấp chức năng lọc và loại bỏ thư rác tuy nhiên chức năng này của Gmail là hiệu quả hơn hết. Gmail có thể loại bỏ hầu hết những thư quảng cáo, thư có chứa virus và những thư rác khác. Mặc dù công cụ này của Gmail không phải là hoàn hảo 100% nhưng nếu so với Yahoo Mail thì Gmail đang làm tốt hơn hẳn.

- Tính năng kết nối với những ứng dụng khác
    + Một tiện ích khác của Gmail chính là nó có thể tự động kết nối hoặc giúp bạn đăng ký nhanh chóng ở các ứng dụng, dịch vụ khác. Ví dụ như thông qua Gmail, bạn có thể nhanh chóng tạo được các tài khoản cũng của Google như Google Hangouts, Google Analytics, Google+.... 
    + Bên cạnh đó, khi bạn truy cập vào các website thì phần lớn cũng tích hợp việc tạo tài khoản thông qua Gmail. Hay như khi truy cập vào các ứng dụng hay game trên điện thoại, bạn cũng có thể tạo tài khoản nhanh chóng bằng Gmail.

- Dung lượng lớn

    + Gmail trở nên nổi tiếng là nhờ vào dung lượng lưu trữ của mình. Một tài khoản miễn phí có thể có dung lượng lên đến 15GB. Và điều đặc biệt hơn hết là khi Gmail của bạn đã đầy bộ nhớ thì thay vì phải xóa các email cũ, bạn có thể lựa chọn chức năng archive chúng. Điều này giúp bạn dọn bớt bộ nhớ mà vẫn có thể lưu trữ những email đó. .

- Chức năng tìm kiếm hiệu quả

    + So với Yahoo Mail hay Hotmail thì Gmail có bộ tìm kiếm email nhanh chóng và chính xác hơn. Điều này cũng dễ hiểu khi Google vốn là bộ máy tìm kiếm lớn nhất thế giới hiện nay nên việc tìm kiếm email trong tài khoản cũng không phải là điều khó khăn. Chức năng tìm kiếm của Gmail luôn cho ra những kết quả có tính chính xác cao nhờ vào việc nó có thể loại bỏ những email nằm trong hòm thư rác.

- Chức năng truy cập offline

    + Một ưu điểm khác không thể không nhắc đến chính là chức năng truy cập offline của Gmail. Có thể nhiều bạn đã biết Gmail là gì nhưng ít ai biết đến chức năng này. Bạn có thể truy cập vào Gmail ngay cả khi không thể kết nối Internet. Bạn chỉ cần cài đặt tiện ích mở rộng Google offline trên Chrome là có thể vào Gmail bất kỳ lúc nào dù đang có Internet hay không. Tuy nhiên, những email mới nhất chắc chắn bạn sẽ không thể nhận được trừ khi bạn kết nối Internet lại sau đó.

## Outlook
### Outlook là gì
- Outlook là một ứng dụng mail hỗ trợ người dùng email quản lý thời gian, dung lượng của email. Ứng dụng này giúp người dùng có thể sắp xếp, quản lý và tìm kiếm thông tin dễ dàng, nhanh chóng. - Được phát triển bởi Microsoft từ những năm 2013 cho các máy sử dụng hệ điều hành Windows, Microsoft Outlook đã và đang trở thành một trợ lý email đắc lực cho người dùng. 

- Ngoài ra Outlook còn hỗ trợ người dùng trong việc quản lý liên lạc, tài liệu, công việc,…với các chức năng như phân loại thư, gửi thư theo nhóm,...

- Outlook có thể được xem là một phần mềm quản lý cá nhân tối ưu nhất cho người dùng. Tuy vậy, vẫn còn khá nhiều người vẫn chưa thành thạo và biết cách sử dụng Outlook hiệu quả để có thể áp dụng nó vào cuộc sống một cách dễ dàng. 
### Tính năng chính của outlook
- Tốc độ truy cập nhanh, không gian lưu trữ rộng mở
    + Đa số người dùng thường sử dụng tính năng email trên Outlook vì phần mềm này có tốc độ truy cập nhanh, không giới hạn không gian lưu trữ, email được sắp xếp theo dung lượng, thời gian nhận, thời gian gửi… dễ dàng tra cứu.

- Hỗ trợ việc gửi mail đính kèm tập tin có dung lượng lớn kết hợp với OneDrive, Skype Drive và khôi phục email đã xóa (trong phạm vi và thời gian cho phép) ngay cả khi bạn đã hoàn tất thao tác xóa email trong thùng rác.

- Cho phép sử dụng HTML và CSS
Cụ thể, người dùng có thể thỏa sức sáng tạo để làm cho bức thư của mình thêm sinh động hơn khi có thể soạn thảo theo chế độ HTML.

- Khôi phục email đã xoá
Outlook hỗ trợ khôi phục email đã xoá (trong phạm vi và thời gian ứng dụng cho phép) ngay cả khi bạn đã hoàn tất thao tác email trong thùng rác.

### ưu điểm outlook

- Tính bảo mật và khả năng chống spam cao
- Ưu điểm tiếp theo của Outlook đó là tính bảo mật cao, đây là một tính năng vô cùng quan trọng trong thế giới công nghệ phát triển phức tạp như hiện tại. Tính năng này sẽ giúp các công ty, doanh nghiệp an tâm làm việc trên không gian mạng. 
- Ngoài ra, Outlook còn có khả năng chống spam với thao tác chặn email theo địa chỉ hoặc tên miền cụ thể. Khởi tạo địa chỉ email chỉ dùng một lần (dùng cho các hoạt động gửi mail một lần hoặc Email Marketing) giúp bạn loại bỏ spam email hoàn toàn. 
ưu điểm

- Đa dạng kết nối
    + Tích hợp với các trang mạng xã hội đang chiếm ưu thế hiện nay như Facebook, Twitter hay LinkedIn… Giúp người dùng email có thể dễ dàng vừa check mail vừa lướt các kênh mạng xã hội này. Tích hợp Skype để trò chuyện thông qua Skype.

- Ngoài ra, Outlook còn cho phép sử dụng HTML và CSS. Cụ thể, người dùng có thể thỏa sức sáng tạo để làm cho bức thư của mình thêm sinh động hơn khi có thể soạn thảo theo chế độ HTML. Phân nhóm thư đến, lọc thư riêng của cá nhân / doanh nghiệp.


## Microsoft Exchange
- Microsoft Exchange Server là hệ thống máy chủ ảo giúp các doanh nghiệp quản lý email, lịch, danh bạ và hỗ trợ người dùng thông qua máy tính để bàn, điện thoại di động và trình duyệt web.

- Để đơn giản hóa định nghĩa thì, để có thể sử dụng được email trên Outlook hay Exchange Online, Microsoft Exchange Server phải hoạt động. Microsoft Exchange Server như “cơ quan đầu não” và Outlook hay Exchange Online là nguồn trung gian phân phối dữ liệu đến bạn.

- Exchange Server chủ yếu sử dụng một giao thức độc quyền được gọi là MAPI để nói chuyện với các ứng dụng email, nhưng sau đó đã thêm hỗ trợ cho POP3 , IMAP và EAS. Giao thức SMTP tiêu chuẩn được sử dụng để giao tiếp với các máy chủ thư Internet khác.

- Exchange Server được cấp phép cả phần mềm tại chỗ và phần mềm dưới dạng dịch vụ (SaaS).

### Cách thức hoạt động
- Exchange Server được doanh nghiệp sử dụng chủ yếu cho việc quản lý gửi, nhận và lưu trữ email. Ngoài ra, Exchange Server còn cung cấp một số tính năng cộng tác khác như tạo lịch và tích hợp chặt chẽ với các ứng dụng Microsoft Office khác.

- Một máy chủ Exchange có 4 thành phần chính hoạt động song song để quá trình hoạt động trơn tru, bao gồm:

    + Information Store: là kho lưu trữ thông tin, nơi định vị và tổ chức các email
    + System Attendant: Hệ thống phục vụ có chức năng tạo và quản lý địa chỉ email.
    + SMTP: Là giao thức truyền mail đơn giản. Đây là thành phần quan trọng cho phép truyền thông điệp liên máy chủ. Thông thường, các thư phải được chuyển tiếp từ máy chủ này sang máy chủ khác, đặc biệt trong các trường hợp vị trí của máy khách người nhận ở xa hoặc đang sử dụng một nhà cung cấp email khác không phải Microsoft.
    + Active Directory: có nhiệm vụ cập nhật thông tin hộp thư mới cho System Attendant. Nó cũng tự quản lý tài khoản người dùng và danh sách phân phối.
- Khi đã thiết lập một máy chủ Exchange, bạn cần tạo tài khoản email cho từng người dùng để gửi hoặc nhận mail thông qua máy chủ. Mỗi tài khoản email phải được định cấu hình riêng với phân quyền riêng và mức độ kiểm soát của người dùng hoặc của tổ chức với email của người dùng.

- Khi đã thiết lập người dùng, Quản trị viên phải thiết lập các tùy chọn lọc. Exchange Server cung cấp các tùy chọn chặn và lọc thư rác mạnh mẽ để bảo vệ người dùng khỏi thư rác, virus và các email không mong muốn khác. Các tin nhắn đến có thể bị chặn bằng tài khoản IP nhằm chặn một đối tượng cụ thể.

- Exchange Server cũng có thể chặn tin nhắn đến của người nhận, phù hợp với các email được chỉ định chỉ được gửi mà không được nhận theo chính sách của tổ chức.

- Khi email được Exchange Server duyệt và thông qua, chúng mới được gửi đến người nhận phù hợp.

### Một số tính năng
- Cung cấp hỗ trợ lên đến 256Gb bộ nhớ và 48 lõi CPU
- Cho phép cài đặt trên Window Server Core
- Cho phép các truy cập bên ngoài vào trung tâm quản trị Exchange (EAC) và Exchange Management Shell.
- Sử dụng phân bổ bộ nhớ đệm đồng bộ nhớ để tối ưu việc sử dụng bộ nhớ cho cơ sở dữ liệu hoạt động
- Ngăn chặn người tham dự chuyển tiếp lời mời họp
- Cung cấp cho người dùng các tùy chọn vắng mặt bổ sung