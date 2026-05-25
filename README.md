# Cookies - PicoCTf write up
xin chào mọi người, hôm nay mình sẽ hướng dẫn các bạn giải challenge **Cookies** thuộc mảng Web exploitation trong **PicoCTf** nhé
![Screenshot 2026-05-24 205131](https://hackmd.io/_uploads/ryB7oCblMg.png)
Chúng ta sẽ mở URL của challenge trong trình duyệt và sử dụng công cụ Burp Suite để ghi lại các gói tin requets/responde 
![Screenshot 2026-05-24 205219](https://hackmd.io/_uploads/Hy9wsCZgzx.png)
Chúng ta sẽ thử nhập 1 giá trị bất kì vào ô trống ví dụ như "namthudo" để xem kết quả trả về.
![Screenshot 2026-05-25 213051](https://hackmd.io/_uploads/rJvfA0-xzl.png)
Trang web thông báo đây là giá trị cookie không tồn tại đồng thời chuyển hướng về lại trang chủ.
Trong gói tin Request được gửi đi ta có thể thấy giá trị của biến `name` trong trường `cookie` có value = -1.
Chúng ta sẽ tiếp tục thử nhập giá trị `snickerdoodle` như gợi ý trong phần nhập liệu của web. 
![cúi](https://hackmd.io/_uploads/H1i8gJflGx.png)
kết quả trả về là thông báo đây là 1 tên cookie hợp lệ của web đồng thời trong phần `value` của trường `cookie` ta có thể thấy giá trị hiện tại là 0. Khác với giá trị không hợp lệ bên trên là -1. Ta sẽ send request này vào tab intruder để thử thay các payload từ 1 đến 50. ![Screenshot 2026-05-24 205853](https://hackmd.io/_uploads/rkqt-yzxMe.png)
Trong phần kết quả, có thể thấy được sự thay đổi của độ dài reponde ở requets thứ 19 với payload là 18 so với các request còn lại. Ta có thể thấy được ngay giá trị của Flag nằm trong responde.
#### Challenge solve. Cảm ơn các bạn đã đọc. 





