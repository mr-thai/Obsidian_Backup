### **1. Tạo file bằng lệnh `fsutil` (Chỉ tạo file rỗng)**

#### **Cú pháp:**

```cmd
fsutil file createnew <tên_file> <kích_thước_tính_bằng_byte>
```

#### **Ví dụ:**

- Tạo một file rỗng 1 MB (1 MB = 1024 * 1024 byte):
    
    ```cmd
    fsutil file createnew testfile.txt 1048576
    ```
    
    File `testfile.txt` sẽ được tạo với dung lượng 1 MB.
    
- Tạo file 10 KB:
    
    ```cmd
    fsutil file createnew testfile.bin 10240
    ```
    

#### **Lưu ý:**

- File được tạo bằng lệnh này là file **rỗng** (chỉ chứa các byte `00`).
- Lệnh này yêu cầu quyền **Admin**. Nếu không chạy CMD dưới quyền Admin, bạn sẽ gặp lỗi.
- Dung lượng tính bằng **byte**:
    - 1 KB = 1024 byte
    - 1 MB = 1024 KB = 1048576 byte
    - 1 GB = 1024 MB = 1073741824 byte
- Định dạng file có thể chỉ mang tính "hình thức" nếu file rỗng hoặc không có nội dung thực tế.
