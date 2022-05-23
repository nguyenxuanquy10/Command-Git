
# Những câu lệnh cơ bản thường sử dụng

1.Thiết lập chứng thực cá nhân <br>
$ git config --global user.name "User Name"<br>
$ git config --global user.email "username@gmail.com"<br>
Lưu ý: –global được sử dụng để áp dụng cho tất cả các projects. Nếu bạn ko sử dụng –global thì settings sẽ chỉ dùng cho riêng project đó.<br>

2.Tạo một kho chứa Git<br>
$ git init<br>
Nếu như bạn muốn theo dõi một dự án cũ trong Git, bạn cần ở trong thư mục của dự án đó. Lệnh này sẽ tạo một thư mục mới có tên .git, thư mục này chứa tất cả các tập tin cần thiết cho kho chứa.<br>
<br>
3.Sao chép một kho chứa đã tồn tại<br>
$ git clone https://github.com/user/repository.git<br><br>
Câu lệnh trên sẽ tạo một thư mục mới có tên giống trên của Repo.<br>
<br>
4.Nhánh trong git<br>
Khi sử dụng Git, bạn có thể tạo ra nhiều nhánh (branch) khác nhau. Câu lệnh Git này dùng để kiểm tra branch hiện tại:<br>
$ git branch<br>
<br>
5.Để tạo mới một branch:<br>
$ git branch <name_branch><br>
or $ git checkout -b <name_branch>
<br>
6.Để chuyển và tạo mới:<br>
$ git branch -b <name_branch><br>
<br>
7.Chuyển nhánh<br>
Trước khi muốn thay đổi source code, điều đầu tiên mà bạn cần phải làm là checkout một nhánh. Để checkout một nhánh, bạn dùng câu lệnh Git sau:<br>
$ git checkout <name_branch><br>
<br>
8.Cập nhật thay đổi<br>
Sau khi bạn thay đổi source code: thêm mới, sửa, xoá files,… Bạn cần phải cập nhật lên Staging Area. Để cập nhật hết các files:<br>
$ git add .<br>
<br>
9.Sau lệnh add, bạn cần sử dụng câu lệnh Commit để đây thông tin thay đổi lên Local Respository:<br>
$ git commit -m "Message"<br>
<br>
10.Cập nhật lên server<br>
Sau câu lệnh Commit, thông tin mới chỉ được cập nhật lên Local Repository. Nếu muốn cập nhật lên server thì bạn phải sử dụng câu lệnh push:<br>
$ git push origin <name_branch><br>
<br>
11.Ngoài ra, nếu chưa tồn tại remote trên server thì bạn cần phải add mới một remote trước rồi mới push:<br>
$ git remote add origin <remote_url><br>
$ git push origin <name_branch><br>
<br>
12.Gộp nhánh<br>
Sau một thời gian cập nhật các file và push lên git trên branch mới, bây giờ mình cần ghép (merge) code lại vào nhánh gốc (master). Trước tiên, cần phải checkout ra khỏi branch hiện tại cần gộp để vào branch master, sau đó thì dùng lệnh merge để ghép branch mới vào master:<br>
$ git checkout master<br>
$ git merge <new_branch><br>
<br>
13.Xem lại lịch sử commit<br>
$ git log<br>
Lệnh git log sẽ cho bạn biết về người commit, ngày giờ, message của những lần commit đó.<br>
<br>
14.Xem thay đổi trước khi push<br>
$ git diff<br>
Lệnh này giúp bạn biết những gì đã được thay đổi giữa nhánh hiện tại và nhánh trước nó.<br>
<br>
15.Gộp commit<br>
$ git rebase -i HEAD~<br>
Sau dấu ~ là số commit bạn muốn gộp. Sau khi gõ lệnh này một cửa sổ trình soạn thảo hiện ra. Thay đổi ký tự pick của dòng các dòng sau dòng đầu thành s rồi lưu lại/kết thúc. Khi đó, trình soạn thảo để chỉnh sửa giải thích commit thiết lập cho commit sau khi đã tổng hợp sẽ được hiển thị, nên hãy chỉnh sửa lưu lại/kết thúc.<br>
<br>
16.Pull từ remote repository<br>
$ git pull origin master<br>
Lệnh trên sẽ gộp những thay đổi mới kéo về từ máy chủ từ xa với nhánh hiện tại trên máy local.<br>
