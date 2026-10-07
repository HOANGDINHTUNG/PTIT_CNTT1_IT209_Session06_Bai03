# Bài 3: Cấu hình tường lửa UFW và chuẩn đoán cổng mạng

## 1. Nhật ký lệnh cấu hình UFW

Đã thực hiện thiết lập các chính sách mặc định, mở cổng 22 (SSH) và 8080 (Web App):
\`\`\`bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow 22/tcp
sudo ufw allow 8080/tcp
sudo ufw enable
\`\`\`

## 2. Báo cáo kiểm tra trạng thái tường lửa

**Lệnh kiểm tra:** `sudo ufw status verbose`

**Kết quả đầu ra:**
\`\`\`text
Status: active
Logging: on (low)
Default: deny (incoming), allow (outgoing), disabled (routed)
New profiles: skip

To                         Action      From
--                         ------      ----
22/tcp                     ALLOW IN    Anywhere
8080/tcp                   ALLOW IN    Anywhere
22/tcp (v6)                ALLOW IN    Anywhere (v6)
8080/tcp (v6)              ALLOW IN    Anywhere (v6)
\`\`\`

**Lệnh chuẩn đoán cổng mạng:** `ss -tlnp`
*(Đã thực thi thành công để rà soát các tiến trình đang lắng nghe trên máy chủ).*