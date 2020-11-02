## Định nghĩa
- container là 1 vùng biệt lập của os với 1 dung lượng sử dụng được giới hạn
- container có process riêng, có mạng riêng, có thể chạy service có routing với iptable
- Sử dụng namespace và control group để build container cả 2 đều là linux kernel prmitive

    + Namespace để tạo các vùng biệt lập (giống như kiểu 1 con máy chủ vật lý chia ra thành nhiều máy ảo)

    + control group để set các giới hạn về dung lượng và hiệu năng

- Mỗi 1 container có 1 mạng lưới network riêng, pid riêng, user riêng, mnt, uts, ...

- Control Group là thằng manage giới hạn sử dụng của CPU như CPU RAM và disk