**Trần Mạnh Dũng**

# Một số NOTE lý thuyết:
1. Để có thể tạo pull request vào một repo bất kỳ nào đó, ta phải clone repo đó về local để có thể tải cả lịch sử commit của các developers khác thì mới có thể có commit mà so sánh để tạo pull request.
2. Trong git có các trạng thái cơ bản sau:
- unchecked: là các file chưa được checked để đem đi commit. ```git add .```
- commited: là các file đã được commit và chuẩn bị push lên remote. ```git commit -m "message"```
- staging: là các file đã được push lên remote repo. ```git push -u origin master```
3. Cách di chuyển giữa các branch trong repo:
- ```^```: di chuyển lên trên 1 bước.
- ```~<number>```: di chuyển lên trên ``number`` bước.

# Các lệnh git thông dụng:

1. ```git init```: khởi tạo repo dưới local
2. ```git add ./<file_name>```: đưa tất cả các file với option là `.` còn với 1 số file chỉ định với option `<file_name>` vào để commit.
3. ```git commit -m "message"```: thực hiện commit với nội dung commit là "message".
4. ```git branch```: hiển thi danh sách các nhánh có trong repo.
5. ```git checkout -b <branch_name>```: thực hiện 2 thao tác liên tiếp là: tạo 1 branch mới có tên là `<branch_name>` sau đó chuyển hoạt động sang nhánh `<branch_name>`
6. ```git checkout <branch_name>```: thực hiện chuyển sang hoạt động ở nhánh `<branch_name>` đã có sẵn.
7. ```git reset```: Ví dụ đang ở commit C2 và chúng ta muốn hủy coomit C2 đi và trở lại commit trước đó là C1 thì ta dùng ```git reset```. Sau khi thực hiện lệnh, mọi thứ sẽ trở lại giống như chưa hề thực hiện commit C2.
8. ```git revert```: Mong muốn cũng giống như git reset nhưng khi dùng ```git revert``` thì nó sẽ tạo ra một commit mới là C2' giống với commit C1 và nằm ngay sau commit C2.

##### So sánh <i>git revert</i> với <i>git reset</i>:
- Đều có mục đích quay trở lại commit trước đó khi không hài lòng với commit mới.
- Đối với `git revert`thì sẽ không xóa đi commit không mong muốn mà sẽ giữ nguyên rồi tạo commit mới giống commit trước đó để khi các thành viên trong project muốn check lại thì hoàn toàn có thể.
- Đối với `git reset` thì sẽ xóa commit không mong muốn đi. Nó phù hợp trong các trường hợp commit nhầm lẫn file hay nội dung commit không phù hợp với dự án,...
- Kết luận:
> Dù có chung một mục đích là quay trở về commit trước đó nhưng dùng ```git revert``` hay ```git reset``` sẽ tùy vào từng trường hợp thực tế.
- Ví dụ: 
  - ```git reset HEAD^```
  - ```get revert C2```
9. ```git log --oneline```: Hiển thị lịch sử commit của repo.

**Mở rộng**: ```git log --oneline --graph```: Hiển thị lịch sủ commit của repo dưới dạng biểu đồ rẽ nhánh.