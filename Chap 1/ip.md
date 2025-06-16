# 📡 Địa chỉ IP (Internet Protocol)

Địa chỉ IP là mã định danh **duy nhất** để xác định một thiết bị trên Internet hoặc mạng cục bộ. IP là viết tắt của **Internet Protocol** – tập hợp các quy tắc quy định **định dạng và truyền dữ liệu** giữa các thiết bị trong mạng.

Về bản chất, địa chỉ IP:

- Cung cấp thông tin định vị để các thiết bị giao tiếp với nhau.
- Là yếu tố cốt lõi giúp Internet hoạt động.

---

## 🔢 Phiên bản địa chỉ IP

### 🌐 IPv4

- Giao thức IP đầu tiên, sử dụng địa chỉ **32-bit** dạng số thập phân chấm (dotted-decimal).
- Có thể tạo khoảng **4 tỷ địa chỉ IP**.
- Được sử dụng rộng rãi từ khi Internet ra đời.

📌 **Ví dụ**: `102.22.192.181`

---

### 🌍 IPv6

- Được giới thiệu vào **năm 1998** nhằm thay thế IPv4 do giới hạn số lượng địa chỉ.
- Sử dụng địa chỉ **128-bit** dưới dạng **thập lục phân (hexadecimal)**.
- Có thể tạo ra khoảng `340 sextillion` địa chỉ (tức ~340 × 10³⁶).

📌 **Ví dụ**: `2001:0db8:85a3:0000:0000:8a2e:0370:7334`

---

## 🧩 Các loại địa chỉ IP

### 🌐 Public IP (Địa chỉ công khai)

- Là địa chỉ chính gán cho toàn bộ mạng của bạn bởi nhà cung cấp dịch vụ Internet (ISP).
- Tất cả thiết bị trong cùng mạng thường chia sẻ cùng một public IP.

📌 **Ví dụ**: địa chỉ IP ngoài của router bạn dùng để truy cập Internet.

---

### 🏠 Private IP (Địa chỉ riêng tư)

- Là địa chỉ gán riêng cho mỗi thiết bị trong mạng nội bộ (LAN).
- Được router tạo ra cho từng thiết bị trong nhà bạn (PC, laptop, điện thoại...).

📌 **Ví dụ**: `192.168.0.101` (trong mạng gia đình)

---

### 📍 Static IP (Địa chỉ tĩnh)

- Là địa chỉ IP **không thay đổi**, được gán **thủ công**.
- Đắt hơn nhưng **đáng tin cậy**, thường dùng cho máy chủ hoặc hệ thống quan trọng.

📌 **Ví dụ**: Máy chủ hosting web, dịch vụ định vị, truy cập từ xa...

---

### 🔄 Dynamic IP (Địa chỉ động)

- Là địa chỉ **thay đổi theo thời gian**, được gán tự động bởi [**DHCP**](./sub/dhcp.md).
- Linh hoạt, tiết kiệm, dễ triển khai trên quy mô lớn.

📌 **Ví dụ**: IP của laptop, điện thoại trong gia đình thay đổi mỗi khi khởi động lại router.

---


## Thực hành

- Một số bài lab thực hành về mạng cần biết [**LAB-NETWORK-BASICS**](./sub/lab-network-basics.md)
