# B. Cài đặt Ubuntu + Docker

Cài đặt hệ điều hành Ubuntu 24.04.4 LTS

Sử dụng một trong các công cụ để giả lập: HyperV (có sẵn của windows), VirutualBox (Miễn phí), VM_Ware (bản quyền)
Download file iso để cài đặt.
<img width="1231" height="620" alt="image" src="https://github.com/user-attachments/assets/3ce154cf-1e8a-46e9-9e44-0c92b3fddca4" />

<img width="1220" height="625" alt="image" src="https://github.com/user-attachments/assets/b00f0124-4d45-4216-ae70-ea3d61d4578f" />

Cấu hình mạng trong Ubuntu (và công cụ giả lập) để cho phép truy cập SSH vào Ubuntu từ cmd của windows

Cấu hình mạng Virtualbox:
<img width="1073" height="994" alt="image" src="https://github.com/user-attachments/assets/b2501aac-eeab-4260-af1e-a8da4d9e3848" />

<img width="1068" height="997" alt="image" src="https://github.com/user-attachments/assets/9ffb8bfc-e4df-4099-b8b6-9707123ffbf7" />

Cấu hình mạng Ubuntu
<img width="1163" height="760" alt="image" src="https://github.com/user-attachments/assets/6fb6ae24-e296-461a-b993-a8952c0758f6" />

<img width="1160" height="775" alt="image" src="https://github.com/user-attachments/assets/0b7c3b77-b8b1-46f3-9c99-4915c6b41584" />

Các lệnh cần tìm hiểu:

- Liệt kê các file trong thư mục: ls
- Tạo thư mục: mkdir nameFolder
- Chuyển thư mục làm việc: cd path
- Copy file: cp file_nguồn path/file_đích
- Thay đổi quyền thao tác file: sudo chmod xxx filename
- Edit file: sudo nano tenfile
- CTRL+o : lưu nội dung sau khi edit
- CTRL+x : thoát edit file
- Xem ip của máy ubuntu: ip -4 addr
- Cài đặt docker cho Ubuntu

Kiểm tra phiên bản docker vừa cài đặt, kiểm tra phiên bản của docker compose

Cấu hình để docker chạy mà không cần tiền tố sudo

Tìm hiểu tập lệnh của docker và docker compose

Đảm bảo tường lửa trên Ubuntu đã cho phép các cổng 80, 1880, 9630 (Lệnh: sudo ufw allow ...)
