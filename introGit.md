- Git là hệ thống kiểm soát phiên bản phân tán mã nguồn mở 


***Repository:***
- Repo: nơi chứa tất cả các mã nguồn cho một dự án
- Có 2 cấu trúc dữ liệu chính là Object và Index được lưu trữ ẩn trong .git
- 2 lại repo: 
	+ Local repo: được cài trên máy, động bộ hóa với remote bằng các lệnh
	+ Remote repo: cài trên server chuyên dụng, điền hình hiện nay là Github.

***Branch:***
- Là những phân nhánh ghi lại luồng thay đổi của lịch sử

- Có thể thực hiện nhiều branch cùng lúc trên một repo

- Khi tạo một repo, một branch mặc định là master được tạo ra.
- Có 3 loại branch : 
	+ Local Branch: Branch có thể quản lí trong local repo
	+ Remote Branch: Branch ở trong remote repo.
	+ Remote tracking branch: Branch để local repo theo dõi remote branch
----------------------------------------------------------
***Một số thuật ngữ:***

- Working tree: Nơi người dùng edit, tạo file mới

- Index: Nơi bảo trì trạng thái sau khi edit trên working tree.

- Check out: triển khai branch ở repo lên working tree. Không chỉ branch mà tag, Specific commit cũng có thể check out.

- Commit: Cập nhật thông tin lên Local Repo.

- Tag: Tên được gắn vào để có thể dễ dàng tham chiếu commit

- Revision: Giá trị hash(hash value) được tạo ra mỗi lần commit, trên Git sử dụng hash value và thực hiện quản lí theo thế hệ.

- Head: Từ chỉ định commit mới nhất của branch đang check out hiện tại.

----------------------------------------------------------

***Flow cơ bản khi sử dụng git:***
- Clone project từ server về Local Repo
- Check-out 1 nhánh từ Local Repository về Working Tree
- Làm việc tại Working Tree
- Add : xác nhận sự thay đổi của các files (đưa đến vùng Staging Area)
- Commit: cập nhật sự thay đổi lên Local Repo

----------------------------------------------------------

***Những câu lệnh cơ bản trong Git***
- Thiết lập chứng thực cá nhân

    + $ git config --global user.name "User Name"
    + $ git config --global user.email "username@gmail.com"

    + global được sử dụng để áp dụng cho tất cả các projects. Nếu ko sử dụng –global thì settings sẽ chỉ dùng cho riêng project đó.

- Tạo một repo chưa git

    + $ git init
	+ Lệnh này sẽ tạo một thư mục mới có tên .git, thư mục này chứa tất cả các tập tin cần thiết cho kho chứa.

- Sao chép một repo đã tồn tại

    + $ git clone https://github.com/user/repository.git
    + Câu lệnh trên sẽ tạo một thư mục mới có tên giống trên của Repo.

- Kiểm tra branch hiện tại:

    + $ git branch

- Tạo mới một branch:

    + $ git branch <name_branch>

- Chuyển và tạo mới branch:

    + $ git branch -b <name_branch>

- Chuyển nhánh

    + Trước khi muốn thay đổi source code, điều đầu tiên cần phải làm là checkout một nhánh. Để checkout một nhánh, sử dụng câu lệnh:

    + $ git checkout <name_branch>

- Cập nhật thay đổi:

    + Sau khi thay đổi source code: thêm mới, sửa, xoá files,… Bạn cần phải cập nhật lên Staging Area. Để cập nhật hết các files dùng lệnh:

    + $ git add .

    + Sau lệnh add, cần sử dụng câu lệnh Commit để đẩy thông tin thay đổi lên Local Repo:

    + $ git commit -m "Message"

- Cập nhật lên server
    + Sau câu lệnh Commit, thông tin mới chỉ được cập nhật lên Local Repo. Nếu muốn cập nhật lên server thì phải sử dụng câu lệnh push:

    + $ git push origin <name_branch>

    + Ngoài ra, nếu chưa tồn tại remote trên server thì cần phải add mới một remote trước rồi mới push:

    + $ git remote add origin <remote_url>

    + $ git push origin <name_branch>

- Gộp nhánh:

    + Để gộp (merge) code lại vào nhánh gốc (master). Trước tiên, cần phải checkout ra khỏi branch hiện tại cần gộp để vào branch master, sau đó thì dùng lệnh merge để ghép branch mới vào master:

    + $ git checkout master

    + $ git merge <new_branch>

- Xem lại lịch sử commit:

    + $ git log
    + Lệnh git log sẽ hiện thông tin về người commit, ngày giờ, message của những lần commit đó.

- Xem thay đổi trước khi push:

    + $ git diff: 

    + Lệnh này giúp biết những gì đã được thay đổi giữa nhánh hiện tại và nhánh trước nó.

- Gộp commit:

    + $ git rebase -i HEAD~

    + Sau dấu ~ là số commit muốn gộp. 


- Pull từ remote repo:
    + $ git pull origin master

    + Lệnh trên sẽ gộp những thay đổi mới kéo về từ máy chủ từ xa với nhánh hiện tại trên máy local.
