## **1. Windows Package Manager (Winget)**

- **Cài đặt phần mềm**:
    
    ```powershell
    winget install <tên_package>
    ```
    
    Ví dụ: `winget install vscode`
- **Tìm kiếm phần mềm**:
    
    ```powershell
    winget search <tên_package>
    ```
    
    Ví dụ: `winget search firefox`
- **Cập nhật phần mềm**:
    
    ```powershell
    winget upgrade
    ```
    
- **Gỡ phần mềm**:
    
    ```powershell
    winget uninstall <tên_package>
    ```
    
- **Danh sách phần mềm đã cài**:
    
    ```powershell
    winget list
    ```
    

### **Ưu điểm**

- **Chính thức từ Microsoft**, ổn định và đáng tin cậy.
- Tích hợp sẵn, không cần cài thêm.
- Giao diện đơn giản, dễ tiếp cận.

### **Nhược điểm**

- Danh sách gói không đa dạng bằng các trình quản lý khác.
- Thiếu tính năng nâng cao (như script, quản lý môi trường).

---

## **2. Chocolatey**

### **Cách cài đặt**

1. Mở PowerShell với quyền **Administrator**.
2. Chạy lệnh:
    
    ```powershell
    Set-ExecutionPolicy Bypass -Scope Process -Force; 
    [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-ObjectSystem.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
    ```
    

### **Các lệnh cơ bản**

- **Cài đặt phần mềm**:
    
    ```powershell
    choco install <tên_package>
    ```
    
    Ví dụ: `choco install git`
- **Tìm kiếm phần mềm**:
    
    ```powershell
    choco search <tên_package>
    ```
    
- **Cập nhật phần mềm**:
    
    ```powershell
    choco upgrade <tên_package>
    ```
    
- **Gỡ phần mềm**:
    
    ```powershell
    choco uninstall <tên_package>
    ```
    

### **Ưu điểm**

- **Thư viện phong phú** với hàng nghìn gói (bao gồm cả phần mềm hệ thống và server).
- Hỗ trợ tốt cho môi trường doanh nghiệp.
- Có thể sử dụng script để tự động hóa.

### **Nhược điểm**

- Quá trình cài đặt ban đầu phức tạp hơn so với Winget.
- Một số gói yêu cầu phiên bản **Pro**.

### **Ứng dụng nâng cao**

- Tạo script tự động cài đặt:
    
    ```powershell
    choco install vscode -y
    choco install nodejs -y
    choco install git -y
    ```
    

---

## **3. Scoop**

### **Cách cài đặt**

1. Mở PowerShell với quyền **Administrator**.
2. Chạy lệnh:
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
    irm get.scoop.sh | iex
    ```
    

### **Các lệnh cơ bản**

- **Cài đặt phần mềm**:
    
    ```powershell
    scoop install <tên_package>
    ```
    
    Ví dụ: `scoop install python`
- **Tìm kiếm phần mềm**:
    
    ```powershell
    scoop search <tên_package>
    ```
    
- **Cập nhật phần mềm**:
    
    ```powershell
    scoop update <tên_package>
    ```
    
- **Gỡ phần mềm**:
    
    ```powershell
    scoop uninstall <tên_package>
    ```
    

### **Ưu điểm**

- **Không yêu cầu quyền Admin** để cài đặt phần mềm.
- Tập trung vào các công cụ dành cho developer.
- Gọn nhẹ, không cồng kềnh.

### **Nhược điểm**

- Thư viện gói ít hơn Chocolatey.
- Chủ yếu phù hợp cho developer, không tối ưu cho người dùng thông thường.

### **Ứng dụng nâng cao**

- Cài đặt môi trường phát triển nhanh chóng:
    
    ```powershell
    scoop install git nodejs python
    ```
    
