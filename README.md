# DHCP Flooding Attack & Snort NIDS/IPS Defense Lab

Bài lab mô phỏng tấn công **DHCP Starvation / Flooding** và cấu hình giám sát, phát hiện tấn công bằng hệ thống phát hiện xâm nhập **Snort NIDS/IPS** trên nền tảng **Labtainers**.

---

## 🚀 Cài đặt & Khởi động nhanh (Quick Start)

Trên bất kỳ máy ảo **Labtainers** nào, chỉ cần mở terminal và chạy lệnh `imodule`:

### 1. Tải và cài đặt bài lab:
```bash
imodule https://raw.githubusercontent.com/ledinhtu72/dhcp-flooding-snort/main/dhcp-flooding-snort.tar
```

### 2. Khởi chạy bài lab:
```bash
labtainer dhcp-flooding-snort
```
> Hệ thống sẽ tự động tải các Docker images cần thiết từ Docker Hub (`zeus183/dhcp-flooding-snort`) và mở 3 terminal tương tác: `snort`, `attacker`, và `client`.

---

## 🎯 Kiểm tra kết quả & Đánh giá tự động

### Kiểm tra tiến độ hoàn thành (checkwork):
```bash
checkwork dhcp-flooding-snort
```

### Dừng bài lab:
```bash
stoplab
```

---

## 🏗️ Kiến trúc bài lab (Architecture)

Bài lab sử dụng mô hình mạng 2 subnet độc lập qua DHCP Relay:
- **INTERNAL_NET**: `192.168.0.0/24` (DHCP Server: `192.168.0.100`, Relay: `192.168.0.1`)
- **EXTERNAL_NET**: `10.10.0.0/24` (Relay: `10.10.0.1`, Snort: `10.10.0.5`, Attacker: `10.10.0.10`, Client: cấp phát động)
- **Docker Hub Images**: `zeus183/dhcp-flooding-snort`
