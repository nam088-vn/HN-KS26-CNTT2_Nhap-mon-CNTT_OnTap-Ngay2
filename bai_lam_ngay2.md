# BÀI LÀM – ÔN TẬP NGÀY 2

- **Họ tên:** Nguyễn Thành Nam
- **Lớp:** CNTT2
- **Link repository:**
- **Hệ điều hành (Windows/macOS):** macOS

## Bài 1. Lọc log thủ công

### Lệnh đã chạy

```shell
% cat logs/access.log | grep "ERROR" > logs/error_report.txt
% head -n 2 logs/error_report.txt

```

### 2 dòng lỗi đầu tiên trong error_report.txt

```text
2025-10-18 08:17:59 [ERROR] Khong tim thay trang /lich-thi (404)
2025-10-18 08:25:55 [ERROR] Het thoi gian cho (timeout)
```

## Bài 2. Đếm bằng pipeline

### Lệnh

```shell
 cat logs/access.log | grep "WARNING" | wc -l
 cat logs/payment.log | grep "ERROR" | wc -l
```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
WARNING trong access.log:  4
ERROR trong payment.log: 3
```

## Bài 3. Chạy script auto_warning (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
zsh auto_warning.sh
cat logs/warning_report.txt
```

### Nội dung file logs/warning_report.txt

```text
2025-10-18 09:19:13 [WARNING] Cong thanh toan phan hoi cham
2025-10-18 09:28:16 [WARNING] Nhieu lan nhap sai ma OTP
2025-10-18 09:43:01 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:46:22 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:49:43 [WARNING] So du vi gan bang hoc phi
```

## Bài 4. Báo cáo tổng hợp

### Các lệnh đã chạy

```shell
echo "=== TONG HOP ACCESS LOG ===" > logs/tong_hop_ngay2.txt
cat logs/access.log | grep "ERROR" >> logs/tong_hop_ngay2.txt
cat logs/payment.log | grep "WARNING" | wc -l >> logs/tong_hop_ngay2.txt
```

### Nội dung file logs/tong_hop_ngay2.txt

```text
=== TONG HOP ACCESS LOG ===
2025-10-18 08:17:59 [ERROR] Khong tim thay trang /lich-thi (404)
2025-10-18 08:25:55 [ERROR] Het thoi gian cho (timeout)
2025-10-18 08:33:51 [ERROR] Ket noi may chu du lieu that bai
2025-10-18 08:37:19 [ERROR] Ket noi may chu du lieu that bai
2025-10-18 08:49:43 [ERROR] Het thoi gian cho (timeout)
2025-10-18 08:53:11 [ERROR] Het thoi gian cho (timeout)
       5
```

## Bài 5. Câu hỏi ngắn

- **a)** Khác biệt giữa > và >>:
> : Nếu file chưa có thì tạo mới. Nếu file đã có dữ liệu, nó sẽ xóa sạch dữ liệu cũ rồi mới ghi dữ liệu mới vào.
>> : Nó giữ nguyên nội dung cũ của file và viết tiếp dữ liệu mới vào cuối dòng. 
- **b)** Nếu bài 4 dùng '>' thay vì '>>' ở lệnh thứ hai: Dòng tiêu đề "=== TONG HOP ACCESS LOG ===" tạo ở bước 1 sẽ bị xóa hoàn toàn. File cuối cùng sẽ chỉ chứa các dòng 'ERROR'
- **c)** Đường dẫn tương đối lấy thư mục hiện tại làm gốc. Khi nén project gửi cho giảng viên hoặc đưa lên GitHub để người khác clone về máy họ, cấu trúc thư mục bên trong project vẫn giữ nguyên và code chạy bình thường. Còn nếu dùng đường dẫn tuyệt đối, code sang máy khác sẽ bị báo lỗi file không tồn tại 

## Tự chấm (điền sau khi có đáp án)

- **Điểm tự chấm:** ..../100
- **Lỗi mình đã mắc và cách sửa:**
