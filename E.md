# E. Triển khai (level test) ứng dụng

Chuyển vào trong thư mục ~/myapp

Gõ lệnh để docker compose chạy: sẽ run tất cả các service khai báo trong file docker-compose.yml

Lợi ích: Chỉ cần docker-compose up -d là toàn bộ hệ thống (Web + Node-RED + Tunnel) tự chạy,
```
version: '3.8'

services:
  nodered:
    image: nodered/node-red
    container_name: nodered
    ports:
      - "1880:1880"
    volumes:
      - ./nodered:/data
    restart: always

  nginx:
    image: nginx:latest
    container_name: nginx
    ports:
      - "80:80"
    volumes:
      - ./myweb:/myweb
      - ./nginx/nginx.conf:/etc/nginx/nginx.conf:ro
    depends_on:
      - nodered
    restart: always

  cloudflared:
    image: cloudflare/cloudflared
    container_name: cloudflared
    command: tunnel --no-autoupdate run --token ${CF_TOKEN}
    restart: always
    volumes:
      - ./cloudflared:/etc/cloudflared
    depends_on:
      - nginx
```
Kiểm tra các container đang chạy trong docker, nếu có cái nào bị restart cần tìm lỗi rồi edit lại docker-compose.yml

Kiểm tra kiểm thử các service đang chạy độc lập thông qua ip và port của nó: ví dụ mở trình duyệt ip_ubuntu:1880 để check nodered đã chạy chưa

Sử dụng nodered: kéo nodered http_in , http_response, function : để tạo api get đơn giản (dùng cho /api proxy_pass của nginx)
<img width="1919" height="855" alt="image" src="https://github.com/user-attachments/assets/f2299f4b-824c-4590-8588-1f963517bb80" />

Sửa file ./myweb/index.html : thêm code html+js để sử dụng được api đã khai báo proxy_pass (thực ra là sử dụng nodered http_in hoặc sử dụng service myapi)
<img width="1919" height="906" alt="image" src="https://github.com/user-attachments/assets/9d7b3e62-e0e3-4419-8847-0babbb9fdab0" />
