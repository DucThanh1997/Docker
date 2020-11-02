- Image bao gồm filesystem của os và các thứ liên quan đến app

- cách xem các image có trong docker trên máy
`docker image ls`

- cách pull 1 docker từ trên mạng về 
`docker image pull ubuntu:latest`

- cách chạy 1 container: `docker container run -it ubuntu:latest /bin/bash`

    + Sau khi chạy xong bạn thấy các user và promp thay đổi vì bạn ở trong cái container đó rồi

    + `docker container run` bảo docker daemon là hãy chạy 1 container mới

    + `-it` bảo dameon là chúng ta sẽ tương tác và gắn cái shell chúng ta đang có vào cái shell của container

    + tiếp theo chúng ta bảo docker chúng ta muốn là ubuntu:latest image

    + cuối cùng chúng ta bảo docker là chúng ta muốn chạy bên trong cái container đó bằng cái `/bin/bash`

- `ps -elf` để xem các process đang chạy trong container

- `Ctrl + P + Q` để quay về cửa sổ terminal bình thường mà không terminate cái container đó


- Docker file là 1 cái doc để miêu tả làm thế nào để build docker image

