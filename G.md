# G. Triển khai ứng dụng đến End-user
Trong Cloudflare: Tạo tunnel (đường hầm), chọn loại triển khai cho docker
<img width="1919" height="933" alt="image" src="https://github.com/user-attachments/assets/0f65cc22-26b6-4ab5-a77a-4626465a4c51" />

<img width="1915" height="871" alt="image" src="https://github.com/user-attachments/assets/63875cce-5c8e-4a7e-ae73-89f863e379b4" />

Convert lệnh docker run ... sang dạng docker compose

Khai báo kết quả convert vào trong file docker-compose.yml

<img width="1230" height="303" alt="image" src="https://github.com/user-attachments/assets/9b1f6823-edf8-424b-b5ea-a9f21b8fc2ef" />
Chạy lại docker compose

Public ứng dụng bằng cách thêm 1 router trỏ tới container đang chạy trong docker, dữ liệu sẽ đi qua tunnel, url dạng sub-domain
<img width="1919" height="904" alt="image" src="https://github.com/user-attachments/assets/b6ac3605-e55c-45ba-a189-420c71e503c4" />

Kiểm tra url sub-domain đã hoạt động public cho mọi end-user. 

<img width="1919" height="895" alt="image" src="https://github.com/user-attachments/assets/a5528876-1c0d-4bc9-8e22-eebb2407d61e" />
