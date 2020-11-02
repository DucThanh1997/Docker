## chap01
### 1.11 Running Hello World in Docker
Gõ docker thì nó sẽ ra 1 cái như document của các câu lệnh ấy

- `docker ps`: để show ra các container đang chạy còn nếu là `docker ps -a` thì sẽ list cả các docker đang ko chạy

- Muốn chạy 1 container thì dùng lệnh này:
`docker run busybox echo hello world`

Container được base trên image và image được chuyền vào container để chạy

- `docker rm` là để xóa các container
- `docker image` là list ra các image đã pull về
- `docker rmi` là để xóa các image


- `docker run -t -i ubuntu:14.04 /bin/bash` nếu bạn thêm `-t` và `-i` vào câu lệnh thì bạn sẽ ở trong container luôn




### 1.12 Running a Docker Container in Detached Mode
Nếu bạn muốn chạy docker ở background thì hãy sử dụng thêm option `-d`

`docker run -d -p 1234:1234 python:2.7 python -m SimpleHTTPServer 1234`


### 1.13 Creating, Starting, Stopping, and Removing Containers
- Tạo container: `docker create -P --expose=1234 python:2.7 python -m SimpleHTTPServer 1234`
- Chạy container: `docker start a842945e2414`
- Dừng hoặc kill container : `docker kill` or `docker stop`
- Xóa học khởi động lại container: `docker rm` or `docker restart`

### 1.14 Building a Docker Image with a Dockerle
Dockerfile là 1 file text dùng để mô tả các bước mà docker cần để chuẩn bị cho image bao gồm
- Tải các package
- Tạo directories
- Định nghĩa biến môi trường