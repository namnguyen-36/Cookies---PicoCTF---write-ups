# Write up HTTP - IP restriction bypass - Root Me
xin chào các bạn hôm nya mình sẽ hướng dẫn các bạn giải challenge HTTP - IP restriction bypass thuộc mảng web server trong Root Me nhé.
<img width="1427" height="362" alt="Screenshot 2026-05-26 212351" src="https://github.com/user-attachments/assets/161a7e03-71a7-4fac-9078-070b9ad86890" />
**Link:** http://challenge01.root-me.org/web-serveur/ch68/
Mở URL của challenge ta nhận được một giao diện web sau.
<img width="527" height="242" alt="Screenshot 2026-05-26 214654" src="https://github.com/user-attachments/assets/7ea9fd27-508a-422c-8fda-bd18c23d4903" />

Theo như phần gợi ý của đề bài. Chỉ cần địa chỉ Ip của máy bạn nằm trong dải ip nội bộ (mạng Lan) là có thể đăng nhập vào web mà không cần đến `password` và `username`.
Vì vậy chúng ta sẽ chèn thêm trường HTTP - Ip vào request header với cú pháp `x-Fowarded-For: <clientIP>, <proxy1>, <proxy2>`
Ta sẽ dùng Burp Suite để thêm trường http -ip vào
Do địa chỉ IP mạng Lan có chuỗi từ 192.168.0.0 đến 192.168.255.255 nên sẽ thử một IP trong chuỗi này.
<img width="1493" height="327" alt="Screenshot 2026-05-26 215656" src="https://github.com/user-attachments/assets/a0c26a5e-4c00-4e17-9147-1868fdddf326" />
Kết quả khi gửi request này đi. Web server nhận đây là một địa chỉ Ip trong mạng Lan của công ty và cho phép chúng ta truy cập với `password` là chuỗi **Ip_$po0Fing**
Challenge solve. Cảm ơn các bạn đã đọc. 



