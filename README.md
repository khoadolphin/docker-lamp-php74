# Docker-lamp-php74

### Muốn custom image thì mở comment:

```
- build:
-   context: .
-   dockerfile: ./httpd/Dockerfile # đường dẫn đến file build image
```

- Lưu ý khoảng cách từ build phải thụt vào 2 space hoặc 1 tab để đúng cấu trúc

---



### 000-default.conf

- Các cấu hình ở file này đã được chỉnh sửa chuẩn để chạy trong www.
- Để chạy được apache cho laravel public:

```
DocumentRoot /var/www/html/public/ # thêm public 

 
```
