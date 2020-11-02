- Đầu tiên bạn phải lôi source code và có source code
- Tạo dockerfile
    + Dockerfile có 2 mục đích gồm miêu tả ứng dụng và bảo docker đóng container cái app thành image như nào

```
FROM alpine
LABEL maintainer="nigelpoulton@hotmail.com"
RUN apk add --update nodejs nodejs-npm
COPY . /src
WORKDIR /src
RUN npm install
EXPOSE 8080
ENTRYPOINT ["node", "./app.js"]
```

- Mọi dockerfile bắt đầu bằng `FROM`, nó sẽ là base layer của cả app và mọi các layer còn lại của app sẽ nằm ở trên nó

- `LABEL` sẽ khai báo ai là maintainer của app

- `RUN` chỉ định sẽ dùng Alpine apl package manager để tải nodejs và nodejs-npm vào image

- `COPY` bảo là copy các file cần từ build context

- `WORKDir` khai báo nơi làm việc chính

- Sau đó bảo nó chạy npm install

- `EXPOSE 8080` chỉ là sẽ chạy trên port 8080

- `ENTRYPOINT` chỉ app sẽ chạy chính khi image được chạy

- Sau đó chúng ta dùng lệnh này để build
`docker image build -t web:latest`

- Chạy thôi
```
docker container run -d --name c1 \
-p 80:8080 \
web:latest
```
chạy cái app web trên port 80