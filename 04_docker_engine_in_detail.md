- Docker sử dụng runc để chạy và tạo các công te nơ

- Để sử dụng runc, docker cần có 1 cái gì đó như cầu nối giữa daemon và runc. Lúc đó containerd xuất hiện

- Containerd như 1 người giám sát điều hành lifecycle của container: chạy, dừng, pause unpause và destroy 

Chúng ta dùng lệnh này để khởi tạo và chạy container
```
docker container run --name ctr1 -it alpine:latest sh
```
Thì nó sẽ như này

- Docker daemon nhận được command này từ docker cli nó sẽ gọi xuống conatinerd bằng RESTFUL-API

- Containerd không tạo container mới mà nó dùng runc để tạo, Nó biến đổi các docker image thành OCI bundle và bảo runc chạy nó

- runc giao tiếp với os kernel để cùng kéo về các thứ cần thiết để tạo thành container

- Mỗi lần tạo 1 container thì 1 runc được tạo ra và khi container được tạo thì runc biến mất, thay vào đó là `containerd-shim` sẽ take control

- `containerd-shim` sẽ keep container sống ngay cả khi container daemon bị tắt đi ( nói cách khác là độc lập hoàn toàn)

- Vậy `docker daemon` là gì? Đó là
    + Quản lý image
    + Khởi đọng build image
    + REST API
    + authen
    + bảo mật
    + ....

