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

<http://prntscr.com/8mtjaf>

- Đăng nhập bằng người dùng thường

<http://prntscr.com/8mtjaf>
