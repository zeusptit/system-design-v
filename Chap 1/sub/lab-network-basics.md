# 🧪 Lab Thực Hành Mạng Cơ Bản: Ping, Subnet, SSH, Telnet

## 🎯 Mục tiêu
- Làm quen với các thao tác cấu hình mạng cơ bản.
- Sử dụng các công cụ dòng lệnh mạng như `ping`, `tracert`, `telnet`, `ssh`.
- Phân biệt IP tĩnh và IP động (DHCP).
- Cấu hình subnet và thực hiện chia mạng.

---

## 🧰 Thiết bị cần
| Thiết bị     | Số lượng |
|--------------|----------|
| Router       | 1        |
| Switch       | 1        |
| PC           | 3        |
| Cáp mạng     | 3+       |

---

## 📊 Sơ đồ kết nối

```
PC0 ------\
           \
            Switch ---- Router ---- Internet (giả lập)
           /
PC1 ------/
PC2 ------/
```

---

## 📝 Bước 1: Cấu hình địa chỉ IP

### ✅ PC0 – Static IP
- IP: `192.168.1.10`
- Subnet: `255.255.255.0`
- Gateway: `192.168.1.1`

### ✅ PC1 – DHCP
- Đặt IP ở chế độ DHCP.
- Cấu hình DHCP server trên Router.

### ✅ Router
```bash
enable
conf t
interface fa0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit

ip dhcp excluded-address 192.168.1.1 192.168.1.9
ip dhcp pool LAN
 network 192.168.1.0 255.255.255.0
 default-router 192.168.1.1
 dns-server 8.8.8.8
```

---

## 🧪 Bước 2: Thực hành lệnh Ping & Tracert

### 🔧 Trên PC0:
```bash
ping 192.168.1.1         # Ping Gateway
ping 192.168.1.11        # Ping PC1
tracert 192.168.1.11     # Xem đường đi gói tin
```

---

## 🔐 Bước 3: SSH vào Router

### 🔒 Cấu hình SSH:
```bash
enable
conf t
hostname R1
ip domain-name demo.local
crypto key generate rsa
1024

username admin privilege 15 secret admin123

line vty 0 4
 login local
 transport input ssh
 exit

ip ssh version 2
```

### 🖥️ Trên PC0:
```bash
ssh -l admin 192.168.1.1
```

---

## 🧬 Bước 4: Thực hành Subnet

Chia subnet `192.168.10.0/24` thành 4 mạng con (`/26`):

- Subnet 1: `192.168.10.0/26`
- Subnet 2: `192.168.10.64/26`
- Subnet 3: `192.168.10.128/26`
- Subnet 4: `192.168.10.192/26`

📌 Gán địa chỉ IP thuộc các subnet trên cho các PC, kiểm tra kết nối bằng `ping`.

---

## 📞 Bước 5: Telnet vào Router

```bash
line vty 5 15
 password telnet123
 login
 transport input telnet
```

### 🖥️ Trên PC0:
```bash
telnet 192.168.1.1
```

---

## 🧠 Kiến thức áp dụng
- Giao thức ICMP (Ping)
- Bảng định tuyến cơ bản
- Cấu hình DHCP
- SSH / Telnet quản trị từ xa
- Subnetting và phân dải mạng

---

## 📎 Tài liệu liên quan
- [Tìm hiểu DHCP](./dhcp.md)
- [Cấu hình SSH và Telnet nâng cao](./ssh-telnet-guide.md)
