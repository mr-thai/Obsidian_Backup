## 1. Kích Hoạt Tính Năng Cần Thiết

bật hai tính năng sau trong **Turn Windows features on or off** trên Windows:
- **Virtual Machine Platform**: Hỗ trợ nền tảng máy ảo cần thiết cho WSL 2.
- **Windows Subsystem for Linux**: Cho phép chạy các ứng dụng và dòng lệnh Linux ngay trên Windows.
## 2. Cài Đặt Bản Phân Phối Linux

Tải bản phối linux trên microsoft -> sau khi cài đặt kiểm tra trong start menu
## 3. Cấu Hình Ban Đầu

Thiết lập tài khoản mật khẩu ban đầu
## 4. Kiểm Tra Và Nâng Cấp Phiên Bản WSL

Để đảm bảo hiệu năng và tính tương thích cao nhất, bạn nên kiểm tra phiên bản WSL đang sử dụng và chuyển sang WSL 2 nếu chưa thực hiện.
   ```
    wsl -l -v
   ```
    
    Lệnh này hiển thị danh sách các bản phân phối cùng phiên bản WSL tương ứng.
    
Nếu muốn chuyển sang WSL 2, chạy:
```
    wsl --set-default-version 2
```
    
## 5. Cập nhật linux
    
```
    sudo apt update && sudo apt upgrade
```
    
- **Các lệnh hữu ích khác:**
    - `wsl -l --running`: Hiển thị các bản phân phối Linux đang chạy.
    - `wsl --shutdown`: Tắt hoàn toàn WSL khi cần.

