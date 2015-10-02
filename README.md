# Quan-ly-nguoi-dung-va-nhom-nguoi-dung
Quản lý người dùng và nhóm người dùng


##1. Supper user

- Trong hệ thống Linux, tài khoản root có quyền cao nhất được sử dụng bởi người quản trị (Administrator). Root có quyền cao nhất trong hệ thống, tuy nhiên khi hệ thống bị sự cố do một lỗi nào đó, chúng ta mới thấ được sự nguy hiểm khi làm việc với root, do vậy nên hạn chế sử dụng tài khoản root. Với những Server quan trọng và có nhiều dịch vụ khác nhau bạn có thể tạ ra các Super user thích hợp cho từng dịch vụ để tránh dùng root cho các công việc này. Ví dụ như Supper user cho công tác backup chỉ cần chức năng đọc (read-only) mà không cần chức năng ghi.

- Trng Linux chúng ta có thể tạo tài khoản có tên khác nhưng có quyền root bằng cách tạo UserID bằng 0. Cần phân biệt bạn đang login bằng root hay người dùng thông qua dấu nhắc lệnh Shell.

- Mặc định trong ubuntu tài khoản Root không có password và cũng không đăn nhập được trên môi trường Desktop. Để đăng nhập tài khoản root ta làm như sau:
- Đặt password cho root bằng cách chạy câu lệnh
      $ sudo passwd root
- Và nhập password của tài khoản hiện tại, sau đố hệ thống sẽ cho bạn nhập mật khẩu cho tài khoản root và nhập lại 1 lần nữa mà bạn mong muốn vậy là bạn đã thay đổi dduowcj password của tài khoản root và có thể đăng nhập bằng tài khoản root.

- Đăng nhập bằng root 

<img src="http://i.imgur.com/Ln8qfTp.png">

- Đăng nhập bằng người dùng thường

<img src="http://i.imgur.com/Ln8qfTp.png">

Bạn chú ý dấu $ cho thấy ban đang kết nối như người dử dụng thường (ubuntuserver). Dấu 3 cho thấy bạn đang thực hiện lệnh với root.

##2. Thông tin của user

Mọi người muốn đăng nhập và sử dụng hệ thống linux đều cần có một tài khaorn việc tạo và quản lý tài khoản là vấn đề quan trọng mà người quản trị phải thực hiện.

Mỗi tài khoản người dùng phải có một tên sử dụng (username) và mật khẩu (password) riêng. Tập tin /etc/passwd là tập tin chứa thông tin về tài khoản người dùng của hệ thống.

###2.1 Tập tin /etc/

- Tập tin /etc/passwd đóng vai trò sống còn đối với một hệ thống Linux. Mọi người đều có thể đọc tập tin này nhưng chỉ có root mới có quyền thay đổi. Tập tin /etc/passwd được lưu dưới dạng văn bản như hầu hết các tập tin khác của linux.

- Để xem thông tin gói tin bạn thực hiện lệnh sau:

<img src="http://i.imgur.com/9RwR2Kj.png">

- Nội dung của tập tin:

<img src="http://i.imgur.com/D9XuMGb.png">

- Mỗi tài khoản được lưu trong một dòng gồm 7 cột, mỗi cột được ngăn cách bởi dấu ":" 
<ul>
<li>Cột 1: Username: Tên của người dùng.</li>
<li>Cột 2: Password: Mã liên quan đến mật khẩu tài khoản là "x" đối với Linux. Linux lưu mã này trong một tập tin là /etc/shadow mà chỉ có root mới có quyền đọc.</li>
<li>Cột 3: User ID: Mã định danh tài khoản. Hệ thống sử dụng UID để phân biệt người này với người khác.</li>
<li>Cột 4: Group ID: Mã định danh nhóm. đây là primary group của user này.</li>
<li>Cột 5: Comment: Mô tả về tài khoản.</li>
<li>Cột 6: Home Directery: Thư mục home của từng user, thường sẽ nằm trong /home/tên_tài_khoản.</li>
<li>Cột 7: Shell: Tên chương trình thực thi ngay sau khi đăng nhập. Nếu không có shell sẽ không thể đăng nhập.Mặc định trên Linux dùng bash shell.</li>
</ul>
