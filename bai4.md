# Bài 4: Lưu trữ dữ liệu đơn giản với Docker Volume

## Các bước thực hiện

### 1. Tạo Docker Named Volume mới tên là `easy-volume`
```bash
docker volume create easy-volume
```

### 2. Kiểm tra danh sách volume trên hệ thống
```bash
docker volume ls
```

### 3. Dùng container Alpine thứ nhất để ghi dữ liệu vào volume
```bash
docker run --rm -v easy-volume:/data alpine sh -c "echo 'Luu tru du lieu Docker' > /data/test.txt"
```

### 4. Dùng container Alpine thứ hai để kiểm tra và đọc lại tệp trong volume
```bash
docker run --rm -v easy-volume:/data alpine cat /data/test.txt
```

## Kết quả mong đợi
Màn hình terminal in ra:
```
Luu tru du lieu Docker
```