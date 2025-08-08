## **Lộ Trình Học PowerShell Script**

### **Giai đoạn 1 – Nền tảng PowerShell**

📌 Mục tiêu: Hiểu cú pháp, chạy được các lệnh cơ bản và điều hướng trong PowerShell.

1. **Cài đặt và môi trường**
    
    - Cài **PowerShell 7 (Core)** từ [GitHub](https://github.com/PowerShell/PowerShell)
        
    - Mở **Windows Terminal** hoặc **VSCode** để code script `.ps1`.
        
    - Biết cách **Set-ExecutionPolicy** để chạy script:
        
        ```powershell
        Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
        ```
        
2. **Làm quen với cmdlet và pipeline**
    
    - Cú pháp cơ bản: `Verb-Noun` (ví dụ: `Get-Process`, `Set-Date`).
        
    - Sử dụng **pipeline (`|`)** để nối lệnh:
        
        ```powershell
        Get-Process | Sort-Object CPU -Descending
        ```
        
    - Tìm trợ giúp:
        
        ```powershell
        Get-Help Get-Process -Full
        Get-Command
        ```
        
3. **Biến và kiểu dữ liệu**
    
    - Khai báo biến: `$name = "Thai"`
        
    - Các kiểu dữ liệu: string, int, bool, array, hashtable.
        
    - Nội suy chuỗi:
        
        ```powershell
        "Hello, $name"
        ```
        
4. **Thực hành nhỏ**
    
    - Viết script liệt kê file lớn nhất trong thư mục.
        
    - Lọc process tiêu tốn CPU cao và xuất ra file `.csv`.
        

---

### **Giai đoạn 2 – Lập trình cơ bản trong PowerShell**

📌 Mục tiêu: Có thể viết script hoàn chỉnh, có logic điều kiện và vòng lặp.

1. **Cấu trúc điều kiện**
    
    ```powershell
    if ($x -gt 10) { Write-Output "Lớn hơn 10" }
    elseif ($x -eq 10) { Write-Output "Bằng 10" }
    else { Write-Output "Nhỏ hơn 10" }
    ```
    
2. **Vòng lặp**
    
    - `for`, `foreach`, `while`, `do { } while()`
        
    - Duyệt mảng:
        
        ```powershell
        foreach ($file in Get-ChildItem) { Write-Output $file.Name }
        ```
        
3. **Hàm**
    
    - Định nghĩa:
        
        ```powershell
        function Get-Sum($a, $b) {
            return $a + $b
        }
        ```
        
    - Tham số bắt buộc và tùy chọn (`[Parameter()]`).
        
4. **Làm việc với file**
    
    - Đọc/ghi file text, CSV, JSON, XML.
        
    - Ví dụ đọc CSV:
        
        ```powershell
        Import-Csv users.csv | ForEach-Object { $_.Name }
        ```
        
5. **Thực hành nhỏ**
    
    - Script backup thư mục sang ổ khác.
        
    - Script đọc danh sách user từ CSV và tạo user trong hệ thống.
        

---

### **Giai đoạn 3 – Quản trị hệ thống với PowerShell**

📌 Mục tiêu: Tự động hóa quản lý Windows, dịch vụ, tiến trình, registry, network.

1. **Quản lý process & service**
    
    ```powershell
    Get-Process
    Start-Service Spooler
    Stop-Process -Name notepad
    ```
    
2. **Quản lý registry**
    
    ```powershell
    Get-ItemProperty "HKCU:\Software\Microsoft\Windows\CurrentVersion\Run"
    ```
    
3. **Quản lý hệ thống**
    
    - Thông tin phần cứng:
        
        ```powershell
        Get-ComputerInfo
        ```
        
    - Quản lý Windows Update, Scheduled Tasks.
        
4. **Quản lý network**
    
    - Kiểm tra kết nối:
        
        ```powershell
        Test-Connection google.com
        ```
        
5. **Thực hành nhỏ**
    
    - Script kiểm tra trạng thái dịch vụ và khởi động lại nếu dừng.
        
    - Script monitor CPU/RAM và gửi email cảnh báo.
        

---

### **Giai đoạn 4 – PowerShell nâng cao**

📌 Mục tiêu: Viết script lớn, module hóa, làm việc với API, remote automation.

1. **Module**
    
    - Tạo module `.psm1` để tái sử dụng code.
        
    - Import module:
        
        ```powershell
        Import-Module MyModule
        ```
        
2. **Error Handling**
    
    - Try/Catch/Finally:
        
        ```powershell
        try { ... } catch { Write-Error $_ }
        ```
        
3. **Tự động hóa từ xa**
    
    - Sử dụng `Invoke-Command` và **PowerShell Remoting** để quản lý nhiều máy.
        
4. **Làm việc với REST API**
    
    ```powershell
    Invoke-RestMethod -Uri "https://api.github.com/repos/microsoft/PowerShell" -Method Get
    ```
    
5. **Viết script dạng tool**
    
    - Thêm tham số nâng cao, validate input, xuất log, gửi thông báo.
        
6. **Thực hành lớn**
    
    - Viết script backup hệ thống định kỳ, lưu log, gửi mail báo cáo.
        
    - Viết tool quản lý user AD (nếu có môi trường domain).
        

---

### **Tài nguyên học**

- [Microsoft Learn – PowerShell](https://learn.microsoft.com/en-us/powershell/)
    
- Sách: **"Learn Windows PowerShell in a Month of Lunches"** (Don Jones)
    
- YouTube: **TechThoughts**, **Adam Driscoll**, **PowerShell.org**
