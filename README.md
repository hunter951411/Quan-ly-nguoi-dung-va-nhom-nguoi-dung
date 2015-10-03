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

- Dòng đầu tiên của /etc/passwd mô tả thông tin cho user root( tất cả những tài khoản có User ID = 0 đều là root), Tieespp theo là các tải khoản khác của hệ thống, cuối cùng là các tài khoản của người dùng.


##2.2 Username

- Là chuỗi các kí tự xác định duy nhất cho một người dùng, dùng tên này để đăng nhập cũng như truy xuất tài khoản. Trong Linux phân biệt chữ hoa và chữ thường. Thông thường, Tên người dùng thường dùng chữ thường.

##2.3 Password
 
- Mỗi người dùng có một mật khẩu riêng để đăng nhập bằng username của mình. Mọi người đều có quyền đổi mật khẩu của chính mình. Người quản trị có thể đổi mật khẩu của nhữn người khác.

- Tập tin **/etc/shadow**: chứa chuỗi Password đã mã bóa của tất cả người dùng.

- Xem thông tin gói tin /etc/shadow:

<img src="http://i.imgur.com/feEF9zg.png">

- Nội dung gói tin /etc/shadow:

<img src="http://i.imgur.com/CEpAl73.png">

- Các dòng tương ứng với mỗi tài khoản, các cột cách nhau bởi dấu ":"
<ul>
<li>Cột 1: Tên của tài khoản.</li>
<li>Cột 2: Mật khẩu của tài khoản được mã hóa. Trong trường hợp tài khoản nào có mật khẩu là ! tức là tài khoản đang tạm thời bị khó, * là tài khoản bị disable.</li>
<li>Cột 3: Số ngày kể từ khi mật khẩu được thay đổi cuối cùng(Mặc định chưa thay mật khẩu 1-1-1970)</li>
<li>Cột 4: Số ngày tối thiểu để có thể thay được mật khẩu.</li>
<li>Cột 5: Số ngày mật khẩu hết hạn.</li>
<li>Cột 6: Số ngày cảnh báo ngời dùng phải thay đổi mật khẩu trước khi hết hạn.</li>
<li>Cột 7: Số ngày sau khi mật khẩu hết hạn, thì tài khoản bị disable.</li>
<li>Cột 8: Số ngày ể từ ngày 1-1-1970 tài khoản bị vô hiệu hóa.</li>
<li>Cột 9: Một lĩnh vực riêng dùng trong tương lai.</li>
</ul>

- Ký tự $ trước mật khẩu đã được mã hóa của người dùng cho biết mật khẩu này được tạo sử dụng một thuật toán mã hóa:
<ul>
<li>$1$ MD5</li>
<li>$5$ SHA 256</li>
<li>$6$ SHA 512</li>
</ul>

##2.4 User ID

- Để dễ dàng hơn trong việc quản lý người dùng, ngoài tên người dùng Linux còn sử dụng khái niệm định danh người dùng (User ID). Mỗi người có 1 con số định danh riêng. Theo quy ước, những người dùng có định danh là 0 là người dùng quản trị (root). Các User ID từ 1 - 99 sử dụng cho các tài khoản hệ thống, User ID của nguwofi dùng thường sử dụng giá trị bắt đầu từ 100.

##2.5 Group ID

- Định danh cho nhóm người dùng. Thông qau Group ID cso thể xác định người dùng đó thuộc nhóm nào, thông thường trên Linux, Group ID được đặt mặc định khi tạo ra một tài khoản và có giá trị >=500.

##2.6 Home Directory

- Khi người dùng login vào hệ thống được đặt làm việc tại thư mục cá nhân của mình. Thường khi mỗi người có một thư mục cá nhân riêng, người dùng có toàn quyền trên đó, nó dùng để chứa dữ liệu các nhân, các thông tin hệ thống cho hoạt động của người dùng như biến môi trường, script khởi động....... Home Directory của người dùng thường là /home, của root là /root. Tuy nhiên ta cũng có thể sửa lại bằng lệnh useradd hoặc user mode.


#3 Quản lý người dùng

##3.1 Tạo tài khoản.

- Để tạo tài khoản bạn có thể sử dụng lệnh user add, có pháp lệnh như sau:

**#useradd** [tùy_chọn] tên_tài_khoản

Demo: Tạo tài khoản user1:

<img src="http://i.imgur.com/b1pjlhp.png">

Kiểm tra tài khoản đã được tạo ra trong thư mục /etc/passwd

<img src="http://i.imgur.com/Vy0HtzT.png">

Option:

**-d**: Thiết lập thư mục home của người dùng. Mặc định khi ta tạo một người dùng thì sẽ được tạo thư mục **/home/ten_tai_khoan**

**-m**: Tạo thư mục home của người dùng nếu không có

**-M**: không tạo thư mục home của người dùng

**-u**: Mặc định lấy số ID tiếp theo để gán cho user(User ID)

***-G**: Thêm người dùng vào các group

**-c**: Mô tả(tên đầy đủ)

**-e**: Ngày hết hạn của tài khoản



Và còn nhiều tùy chọn khác.

- Dùng lệnh **passwd** để đặt password cho tài khoản

**#passwd** tên_tài_khoản

Demo: Đặt password cho tài khoản user1

<img src="http://i.imgur.com/v6Yiqpr.png">

Kiểm tra lại trong tập tin /etc/shadow

<img src="http://i.imgur.com/vdtaUF6.png">
