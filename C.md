# C. Cấu hình docker compose:
Tạo thư mục: ~/myapp

Chuyển vào trong thư mục ~/myapp

Tạo thư mục: ./myweb
<img width="1173" height="135" alt="image" src="https://github.com/user-attachments/assets/99ed8f43-bee8-4c35-a7fa-2418e62f9757" />

Tạo file ./myweb/index.html (với nội dung là thông tin cá nhân của em)
<img width="1693" height="527" alt="image" src="https://github.com/user-attachments/assets/d9abe7ce-4893-4b5a-af5a-51a19329d23d" />

Tạo file docker-compose.yml để nó sẽ có các dịch vụ sau:

- Khai báo sử dụng nodered/node-red, cổng 1880, dữ liệu nằm tại thư mục ./nodered
- Khai báo sử dụng nginx, cổng 80, cấu hình trong file ./nginx/nginx.conf
- Mount thư mục ./myweb thành thư mục /myweb trong nginx
- Mount file ./nginx/nginx.conf vào file /etc/nginx/nginx.conf trong nginx
<img width="1604" height="787" alt="image" src="https://github.com/user-attachments/assets/7647bff1-44be-4546-bdb1-15d46a6243cc" />

Edit file ./nginx/nginx.conf để:
- Cấu hình web server cổng 80
- server_name là sub-domain (sub-domain tuỳ ý của em)
- location / trỏ tới root là thư mục /myweb
- location /api dùng proxy_pass trỏ tới 1 (hoặc nhiều) node http_in của nodered
<img width="1380" height="716" alt="image" src="https://github.com/user-attachments/assets/74738a05-f4d9-4c11-93a1-cf14afa7b335" />

Edit file ./nodered/settings.js để nodered bắt buộc đăng nhập

Chạy docker-compose lần đầu để Node-RED tự sinh file cấu hình trong thư mục ./nodered, sau đó mới tiến hành sửa settings.js và restart lại container
<img width="1919" height="867" alt="image" src="https://github.com/user-attachments/assets/c4645236-58a3-4b95-b9f8-e2d5e280fa13" />

