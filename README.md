# Docker exec và Docker logs

## Docker exec


## Docker exec là gì?
Docker exec là một lệnh cho phép bạn chạy một lệnh trong một container đang chạy. Đây là một cách hữu ích để khắc phục sự cố, thực hiện các tác vụ quản trị hoặc gỡ lỗi ứng dụng của bạn.

Để sử dụng docker exec, bạn cần biết tên của container mà bạn muốn chạy lệnh. Bạn có thể tìm thấy tên của container bằng cách sử dụng lệnh docker ps.

Khi bạn đã biết tên của container, bạn có thể sử dụng lệnh docker exec để chạy một lệnh trong container.

Ví dụ, để chạy lệnh ls trong container có tên my-container, bạn có thể sử dụng lệnh sau:

```
docker exec my-container ls
```

Bạn cũng có thể sử dụng docker exec để chạy một lệnh tương tác trong container. Để làm điều này, bạn cần thêm tùy chọn -it vào lệnh.

Ví dụ, để chạy lệnh bash tương tác trong container có tên my-container, bạn có thể sử dụng lệnh sau:

```
docker exec -it my-container bash
```

### Một số ví dụ khác về cách sử dụng docker exec:

- Khởi động lại một dịch vụ:

```
docker exec my-container supervisorctl restart my-service
```

- Gỡ lỗi một ứng dụng:

```
docker exec -it my-container gdb my-app
```

- Chạy một script:

```
docker exec -it my-container bash /path/to/script.sh
```

- Cài đặt một gói phần mềm:

```
docker exec my-container apt update && apt install my-package
```

### Một số mẹo khi sử dụng docker exec:

- Luôn luôn đảm bảo rằng bạn biết tên của container mà bạn muốn chạy lệnh trước khi sử dụng docker exec.
- Khi chạy các lệnh tương tác trong container, hãy nhớ thoát khỏi container khi bạn đã hoàn tất.
- Nếu bạn cần chạy một lệnh với các đặc quyền của người dùng khác, hãy sử dụng tùy chọn -u.
- Để biết thêm thông tin về docker exec, hãy tham khảo trang hướng dẫn chính thức của Docker.

### Docker exec cũng hỗ trợ một số tùy chọn khác, chẳng hạn như:

+ -e: Thiết lập một biến môi trường cho lệnh.
+ -w: Thiết lập thư mục làm việc cho lệnh.
+ -u: Chạy lệnh với tư cách là một người dùng khác.

## Docker logs

### Docker logs là gì?

Để sử dụng docker logs, bạn cần biết tên của container mà bạn muốn xem nhật ký. Bạn có thể tìm thấy tên của container bằng cách sử dụng lệnh docker ps.

Khi bạn đã biết tên của container, bạn có thể sử dụng lệnh docker logs để xem nhật ký của container.

- Để xem nhật ký của container có tên my-container, bạn có thể sử dụng lệnh sau:
- 
```
docker logs my-container
```

Bạn cũng có thể sử dụng docker logs để theo dõi nhật ký của container theo thời gian thực. Để làm điều này, bạn cần thêm tùy chọn -f vào lệnh.

- Để theo dõi nhật ký của container có tên my-container theo thời gian thực, bạn có thể sử dụng lệnh sau:
- 
```
docker logs -f my-container
```
Ngoài ra, bạn cũng có thể sử dụng docker logs để xem nhật ký của các container đã dừng. Để làm điều này, bạn cần thêm tùy chọn --since vào lệnh.

- Để xem nhật ký của container có tên my-container kể từ thời điểm 5 phút trước, bạn có thể sử dụng lệnh sau:

```
docker logs --since=5m my-container
```

### Một số tùy chọn khác:

+ -t: Theo dõi nhật ký của tất cả các container đang chạy.
+ -q: Chỉ hiển thị nhật ký của container gần đây nhất.
+ --tail: Chỉ hiển thị một số dòng nhật ký gần đây nhất.
+ --timestamps: Hiển thị thời gian của mỗi dòng nhật ký.
+ --details: Hiển thị thêm thông tin chi tiết về mỗi dòng nhật ký.

