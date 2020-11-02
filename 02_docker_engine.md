- docker engine dùng để chạy và quản lý các container thường chỉ gọi là docker

- Gồm Docker client, docker daemon,containerd, runc

- Hãy tưởng tượng docker engine như máy ô tô, được cấu thành từ nhiều bộ phận và dùng để chạy image (ô tô)

![image](https://user-images.githubusercontent.com/45547213/93019431-34d50f80-f601-11ea-92a2-5968759ce339.png)

    + Docker client để tương tác với người dùng
    + Docker daemon để tiếp nhận code và gọi api xuống docker containerd bằng grpc
    + OCI tạo container



