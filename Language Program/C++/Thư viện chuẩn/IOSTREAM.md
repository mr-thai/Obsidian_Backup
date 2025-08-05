### **Tổng Quan về Thư Viện `iostream` trong C++**

Thư viện **`iostream`** trong C++ cung cấp các công cụ để **nhập** (input) và **xuất** (output) dữ liệu. Đây là một thư viện rất quan trọng, hỗ trợ giao tiếp với người dùng thông qua bàn phím (nhập dữ liệu) và màn hình (xuất dữ liệu).

---

### **Các Thành Phần Chính Của Thư Viện `iostream`:**

#### **1. Các Đối Tượng Luồng (Stream Objects):**

- **`std::cin`**: Đối tượng dùng để nhập dữ liệu từ **bàn phím**.
    
    - Ví dụ:
        
        ```cpp
        int x;
        std::cin >> x;  // Nhập dữ liệu từ bàn phím và gán vào biến x
        ```
        
- **`std::cout`**: Đối tượng dùng để **xuất dữ liệu ra màn hình**.
    
    - Ví dụ:
        
        ```cpp
        std::cout << "Hello, World!" << std::endl;  // Xuất chuỗi "Hello, World!" ra màn hình
        ```
        
- **`std::cerr`**: Đối tượng dùng để xuất **thông báo lỗi**. Dữ liệu xuất qua `std::cerr` không qua bộ đệm, điều này có nghĩa là thông báo lỗi sẽ được in ngay lập tức.
    
    - Ví dụ:
        
        ```cpp
        std::cerr << "Error: Invalid input!" << std::endl;
        ```
        
- **`std::clog`**: Đối tượng dùng để xuất **thông báo lỗi không khẩn cấp**. Dữ liệu xuất qua `std::clog` sẽ được ghi vào bộ đệm và xuất ra sau.
    
    - Ví dụ:
        
        ```cpp
        std::clog << "Log: Program started." << std::endl;
        ```
        

---

#### **2. Các Toán Tử Nhập/Xuất (I/O Operators):**

- **Toán tử `<<` (Put to)**: Dùng để **xuất dữ liệu**. Thường được dùng với `std::cout` để hiển thị thông tin.
    
    - Ví dụ:
        
        ```cpp
        std::cout << "Enter a number: " << std::endl;
        ```
        
- **Toán tử `>>` (Get from)**: Dùng để **nhập dữ liệu** từ bàn phím. Thường được dùng với `std::cin`.
    
    - Ví dụ:
        
        ```cpp
        int x;
        std::cin >> x;  // Nhập dữ liệu vào biến x
        ```
        

---

#### **3. Manipulators (Điều Khiển Định Dạng Dữ Liệu)**

Thư viện `iostream` cung cấp một số manipulators giúp điều chỉnh cách dữ liệu được xuất ra màn hình.

- **`std::setw(int)`**: Thiết lập **độ rộng của trường** (số ký tự mà dữ liệu sẽ chiếm dụng khi xuất).
    
    - Ví dụ:
        
        ```cpp
        std::cout << std::setw(10) << 42 << std::endl;  // In ra 42 với độ rộng 10
        ```
        
- **`std::setprecision(int)`**: Thiết lập **số chữ số thập phân** cần hiển thị đối với số thực.
    
    - Ví dụ:
        
        ```cpp
        double pi = 3.14159;
        std::cout << std::setprecision(3) << pi << std::endl;  // In ra 3.14
        ```
        
- **`std::fixed`**: Hiển thị số thực theo **định dạng cố định** (fixed-point).
    
    - Ví dụ:
        
        ```cpp
        double pi = 3.14159265359;
        std::cout << std::fixed << std::setprecision(2) << pi << std::endl;  // In ra 3.14
        ```
        
- **`std::scientific`**: Hiển thị số thực theo **định dạng khoa học**.
    
    - Ví dụ:
        
        ```cpp
        double pi = 3.14159265359;
        std::cout << std::scientific << pi << std::endl;  // In ra 3.141593e+00
        ```
        
- **`std::endl`**: Xuất một dòng mới (newline) và **xả bộ đệm**.
    
    - Ví dụ:
        
        ```cpp
        std::cout << "Hello" << std::endl;  // In ra "Hello" và xuống dòng mới
        ```
        

---

#### **4. Nhập và Xuất với Chuỗi (String I/O)**

- **`std::getline()`**: Được dùng để nhập một **dòng văn bản đầy đủ** từ bàn phím, bao gồm cả dấu cách.
    
    - Ví dụ:
        
        ```cpp
        std::string line;
        std::getline(std::cin, line);  // Nhập một dòng văn bản vào biến line
        ```
        
- **`std::string` và `std::stringstream`**: Mặc dù không thuộc `iostream` trực tiếp, nhưng bạn có thể sử dụng `std::stringstream` (thư viện `<sstream>`) để thao tác với chuỗi như một luồng.
    
    - Ví dụ:
        
        ```cpp
        std::stringstream ss;
        ss << "100" << " " << 3.14;
        int x;
        double y;
        ss >> x >> y;
        std::cout << x << " " << y << std::endl;  // In ra 100 3.14
        ```
        

---

#### **5. Xử Lý Lỗi Nhập/Xuất**

Các hàm kiểm tra trạng thái của luồng dữ liệu:

- **`fail()`**: Kiểm tra xem luồng có gặp lỗi không.
    
    - Ví dụ:
        
        ```cpp
        if (std::cin.fail()) {
            std::cout << "Lỗi khi nhập!" << std::endl;
        }
        ```
        
- **`eof()`**: Kiểm tra xem đã đọc hết dữ liệu chưa (đến cuối tệp).
    
    - Ví dụ:
        
        ```cpp
        if (std::cin.eof()) {
            std::cout << "Đã đến cuối dòng" << std::endl;
        }
        ```
        
- **`good()`**: Kiểm tra xem luồng có hoạt động bình thường không (không có lỗi, không đến EOF).
    
    - Ví dụ:
        
        ```cpp
        if (std::cin.good()) {
            std::cout << "Nhập thành công!" << std::endl;
        }
        ```
        
- **`clear()`**: Đặt lại trạng thái của luồng sau khi gặp lỗi.
    
    - Ví dụ:
        
        ```cpp
        std::cin.clear();  // Đặt lại trạng thái lỗi của luồng
        ```
        

---

### **Tóm Tắt Các Thành Phần Chính Của `iostream`:**

- **Đối tượng luồng**: `std::cin`, `std::cout`, `std::cerr`, `std::clog`.
- **Toán tử nhập/xuất**: `<<` (xuất) và `>>` (nhập).
- **Manipulators**: `std::setw()`, `std::setprecision()`, `std::fixed`, `std::scientific`, `std::endl`.
- **Nhập/xuất chuỗi**: `std::getline()`.
- **Kiểm tra lỗi nhập/xuất**: `fail()`, `eof()`, `good()`, `clear()`.