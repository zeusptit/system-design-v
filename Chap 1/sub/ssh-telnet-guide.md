# SSH và Telnet - Hướng dẫn sử dụng cơ bản

## Mục tiêu
- Hiểu sự khác nhau giữa SSH và Telnet.
- Thực hành kết nối đến một máy từ xa qua SSH và Telnet.
- Cấu hình và kiểm tra dịch vụ SSH/Telnet trên máy ảo nội bộ.

---

## 1. SSH là gì?

- **SSH (Secure Shell)** là giao thức mạng cho phép đăng nhập từ xa một cách bảo mật.
- SSH sử dụng mã hóa để bảo vệ dữ liệu truyền đi.
- Cổng mặc định: `22`

### Cài đặt SSH Server trên Ubuntu:
```bash
sudo apt update
sudo apt install openssh-server
```

### Kiểm tra trạng thái SSH:
```bash
sudo systemctl status ssh
```

### Kết nối tới máy khác qua SSH:
```bash
ssh username@ip_address
```

### Ví dụ:
```bash
ssh student@192.168.1.10
```

---

## 2. Telnet là gì?

- **Telnet** là giao thức mạng cho phép truy cập từ xa giống như SSH, nhưng KHÔNG mã hóa dữ liệu.
- Cổng mặc định: `23`
- Ít được sử dụng ngày nay do lý do bảo mật.

### Cài đặt Telnet server:
```bash
sudo apt install xinetd telnetd
```

### Kết nối đến Telnet server:
```bash
telnet ip_address
```

---

## 3. So sánh SSH và Telnet

| Thuộc tính        | SSH                         | Telnet                      |
|-------------------|------------------------------|-----------------------------|
| Bảo mật            | Có (mã hóa)                  | Không                        |
| Cổng mặc định       | 22                           | 23                          |
| Giao thức           | TCP                         | TCP                         |
| Sử dụng phổ biến hiện nay | ✅                      | ❌ (hiếm dùng)              |

---

## 4. Lab: SSH và Telnet nội bộ

### Yêu cầu:
- 2 máy ảo trong cùng mạng (hoặc sử dụng VirtualBox + Host-Only Network).
- Một máy làm server (cài openssh hoặc telnetd), một máy làm client.

### Bước 1: Cài đặt SSH/Telnet trên Server
```bash
sudo apt install openssh-server telnetd
```

### Bước 2: Kết nối từ Client

#### SSH:
```bash
ssh user@<server-ip>
```

#### Telnet:
```bash
telnet <server-ip>
```

### Bước 3: So sánh nội dung gói tin

- Dùng Wireshark để bắt gói và phân tích:
    - SSH: dữ liệu mã hóa
    - Telnet: dữ liệu dạng plain text

---

## 5. Ghi chú bảo mật

- KHÔNG sử dụng Telnet trên mạng Internet.
- SSH nên được cấu hình với khóa RSA thay vì password.

---

## Tài liệu tham khảo

- [OpenSSH Documentation](https://www.openssh.com/manual.html)
- [Telnet RFC 854](https://tools.ietf.org/html/rfc854)
