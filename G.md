# G. Triển khai ứng dụng đến End-user
Trong Cloudflare: Tạo tunnel (đường hầm), chọn loại triển khai cho docker

Convert lệnh docker run ... sang dạng docker compose

Khai báo kết quả convert vào trong file docker-compose.yml

Chạy lại docker compose

Public ứng dụng bằng cách thêm 1 router trỏ tới container đang chạy trong docker, dữ liệu sẽ đi qua tunnel, url dạng sub-domain

Kiểm tra url sub-domain đã hoạt động public cho mọi end-user
