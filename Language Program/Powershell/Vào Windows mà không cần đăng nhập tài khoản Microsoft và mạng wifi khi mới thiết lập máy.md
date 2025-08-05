### **Hướng dẫn sử dụng `OOBE\BYPASSNRO` để bỏ qua tài khoản Microsoft**

#### **1. Bắt đầu cài đặt Windows**

- Trong quá trình thiết lập (OOBE - Out of Box Experience), Windows sẽ yêu cầu bạn:
    - Kết nối với mạng.
    - Đăng nhập bằng tài khoản Microsoft.

#### **2. Mở CMD từ màn hình thiết lập**

- Khi ở bước yêu cầu kết nối mạng:
    - Nhấn tổ hợp phím **Shift + F10** để mở cửa sổ Command Prompt (CMD).

#### **3. Nhập lệnh `OOBE\BYPASSNRO`**

- Trong cửa sổ CMD, nhập lệnh sau và nhấn Enter:
    
    ```cmd
    OOBE\BYPASSNRO
    ```
    

#### **4. Tự động khởi động lại**

- Sau khi chạy lệnh, máy tính sẽ **tự động khởi động lại**.

#### **5. Tiếp tục thiết lập**

- Khi máy khởi động lại:
    - Bạn sẽ thấy xuất hiện tùy chọn **"I don’t have internet"** hoặc **"Skip for now"** ở bước yêu cầu kết nối mạng.
    - Chọn tùy chọn này để bỏ qua kết nối mạng.

#### **6. Tạo tài khoản cục bộ**

- Sau khi bỏ qua bước đăng nhập Microsoft:
    - Windows sẽ yêu cầu bạn tạo một tài khoản cục bộ (Local Account).
    - Nhập tên tài khoản và mật khẩu (nếu cần) để hoàn tất thiết lập.
