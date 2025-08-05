### 1. **Kiểu dữ liệu cơ bản (Fundamental Data Types)**

Đây là các kiểu dữ liệu nguyên thủy được C++ cung cấp sẵn:

- [[Số nguyên (Integer Types)]]: `int`, `short`, `long`, `long long`, có thể là số dương (`unsigned`) hoặc có dấu (`signed`).
- [[Số thực (Floating-point Types)]]: `float`, `double`, `long double`.
- [[Ký tự (Character Type)]]: `char` (lưu trữ ký tự ASCII hoặc Unicode).
- [[Boolean (`bool`)]]: Chỉ có hai giá trị `true` hoặc `false`.

---

### 2. **Kiểu dữ liệu phức hợp (Complex Data Types)**

Bao gồm các kiểu dữ liệu cấu trúc và tự định nghĩa:

- [[Mảng (`array`)]]: Tập hợp các phần tử cùng kiểu dữ liệu, có kích thước cố định.
- [[Con trỏ (`pointer`)]]: Lưu trữ địa chỉ của biến khác.
- [[Chuỗi ký tự (string - char)]]: Đại diện cho chuỗi văn bản.
- **[[Struct (`struct`) và Union (`union`)]]**: Gom nhóm nhiều biến khác loại trong một cấu trúc.
- [[Kiểu liệt kê (`enum`)]]: Đại diện cho một tập hợp hằng số có tên.

---

### 3. **Kiểu dữ liệu mở rộng từ thư viện chuẩn**

- **`std::vector`, `std::list`, `std::map`, `std::set`**: Các cấu trúc dữ liệu động có trong thư viện STL.
- **`std::pair`, `std::tuple`**: Gom nhóm nhiều giá trị khác loại vào một đối tượng.
- **`std::variant`, `std::any`** (C++17+): Kiểu dữ liệu có thể chứa nhiều loại khác nhau.

---

### 4. **Kiểu dữ liệu tự định nghĩa**

- **Lớp (`class`) và đối tượng (`object`)**: Đại diện cho lập trình hướng đối tượng.
- **Kiểu typedef và alias (`typedef`, `using`)**: Định danh mới cho kiểu dữ liệu có sẵn.

---

### 5. **Kiểu dữ liệu trừu tượng**

- **Hàm (`function`)**: Một kiểu dữ liệu vì có thể truyền như tham số hoặc lưu vào con trỏ hàm.
- **Lambda expression (`auto lambda = []{}`)**: Biểu thức ẩn danh để tạo hàm nhanh chóng.

---

💡 **Tóm lại**: C++ hỗ trợ nhiều loại kiểu dữ liệu, từ cơ bản đến phức tạp, giúp lập trình viên có thể tối ưu bộ nhớ và hiệu năng khi làm việc với dữ liệu.