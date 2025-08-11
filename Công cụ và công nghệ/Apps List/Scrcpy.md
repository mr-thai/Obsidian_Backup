---
tags:
  - window
  - android
  - terminal
  - linux
---

[scrcpy](https://github.com/Genymobile/scrcpy) là công cụ dòng lệnh phù hợp cho cả win, linux, mac để chiếu màn hình điện thoại lên máy tính bằng wifi hoặc dây chuyền
Dưới đây là chi tiết về **scrcpy v3.1**:

---

### **Các tính năng nổi bật của scrcpy v3.1**

1. **Chiếu màn hình Android lên máy tính:**
       - Hỗ trợ độ phân giải cao (Full HD, 4K tùy thuộc vào thiết bị Android).
    - Độ trễ thấp (~35-70ms), đảm bảo hình ảnh được chiếu mượt mà và gần như theo thời gian thực.
2. **Điều khiển thiết bị từ máy tính:**
       - Sử dụng chuột và bàn phím để điều khiển.
    - Hỗ trợ thao tác như nhấn, vuốt, gõ văn bản, và mở ứng dụng trực tiếp trên màn hình.
3. **Kết nối qua USB hoặc Wi-Fi:**
       - Kết nối ổn định qua cáp USB (khuyến nghị để đạt hiệu suất tốt nhất).
    - Có thể kết nối không dây qua Wi-Fi sau khi thiết lập ban đầu.
4. **Hỗ trợ tốc độ khung hình cao (High FPS):**
       - Phiên bản mới cải thiện khả năng hiển thị với tốc độ khung hình cao, hỗ trợ lên đến **120 FPS** trên các thiết bị và màn hình tương thích.
5. **Ghi lại màn hình:**
       - Cho phép ghi lại màn hình Android trực tiếp trên máy tính, xuất ra file video với định dạng `.mp4` hoặc `.mkv`.
6. **Hỗ trợ clipboard:**
       - Sao chép/dán văn bản giữa máy tính và thiết bị Android.
    - Nhấn `Ctrl+C` trên máy tính để sao chép văn bản từ Android và dán vào máy tính.
7. **Hỗ trợ đa thiết bị:**
       - Có thể kết nối và điều khiển nhiều thiết bị Android cùng lúc trên một máy tính.
8. **Hỗ trợ các tính năng mới trong Android:**
       - Cải thiện khả năng tương thích với Android 12 và 13.
    - Hỗ trợ điều khiển tính năng "Permissions Dialog" trên Android hiện đại.
9. **Chế độ toàn màn hình và zoom:**
       - Nhấn `Ctrl+F` để vào chế độ toàn màn hình.
    - Zoom màn hình bằng tổ hợp phím `Ctrl` + cuộn chuột.
10. **Tùy chỉnh tốc độ bit và độ phân giải:**
       - Hỗ trợ giảm độ phân giải hoặc bitrate để tối ưu hiệu suất trên máy tính cấu hình thấp.
### **Cách sử dụng scrcpy v3.1**

1. **Tải về và cài đặt:**
       - Tải bản mới nhất từ [trang chính thức](https://github.com/Genymobile/scrcpy).
    - Giải nén file đã tải về (không cần cài đặt).
2. **Kết nối thiết bị:**
       - Bật **USB Debugging** trong **Developer Options** trên thiết bị Android.
    - Kết nối thiết bị với máy tính qua USB hoặc thiết lập Wi-Fi.
3. **Chạy scrcpy:**
       - Mở Terminal/Command Prompt và chạy lệnh:
        
     ```bash
        scrcpy
      ```
        
    - Để kết nối qua Wi-Fi, dùng lệnh:
        
        ```bash
        scrcpy --tcpip=192.168.x.x
        ```
        
        _(Thay `192.168.x.x` bằng địa chỉ IP của thiết bị Android)._
4. **Các phím tắt chính:**
    
    - `Ctrl+F`: Toàn màn hình.
    - `Ctrl+C`: Sao chép văn bản.
    - `Ctrl+Shift+S`: Chụp màn hình.
    - `Ctrl+S`: Bật/tắt ghi màn hình.

---

🚀 **Lưu ý:** Bạn có thể kết hợp nhiều tùy chọn cùng lúc, ví dụ:  
```sh
scrcpy -m 1280 -b 8M --max-fps 60
```

### **Ưu điểm của scrcpy v3.1**

- Hiệu suất cao và mượt mà.
- Miễn phí và mã nguồn mở.
- Không yêu cầu root thiết bị Android.
- Hỗ trợ đa nền tảng.
- Khả năng tùy chỉnh cao.

### **Nhược điểm**

- Cần cài đặt ADB, có thể phức tạp với người mới.
- Hiệu suất Wi-Fi không bằng kết nối USB.
- Không hỗ trợ truyền âm thanh trực tiếp từ thiết bị Android (phiên bản hiện tại).