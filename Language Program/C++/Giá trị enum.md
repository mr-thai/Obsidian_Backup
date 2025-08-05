
Enum (Enumeration) trong C++ là một kiểu dữ liệu đặc biệt giúp định nghĩa một tập hợp các hằng số có tên, giúp mã nguồn dễ đọc và bảo trì hơn. Enum thường được sử dụng khi một biến có thể có một số giá trị xác định trước.

---

## **1. Định nghĩa Enum trong C++**

Enum có thể được khai báo bằng từ khóa `enum` hoặc `enum class`. Dưới đây là hai cách khai báo phổ biến:

### **1.1 Enum truyền thống (C-style Enum)**

```cpp
#include <iostream>

enum Color {
    RED,    // 0
    GREEN,  // 1
    BLUE    // 2
};

int main() {
    Color c = GREEN;
    std::cout << c << std::endl;  // Output: 1
    return 0;
}
```

📌 **Lưu ý:**

- Giá trị mặc định bắt đầu từ `0`, các giá trị tiếp theo tăng dần (`RED = 0`, `GREEN = 1`, `BLUE = 2`).
- Có thể gán giá trị tùy chỉnh:
    
    ```cpp
    enum Color {
        RED = 10,
        GREEN = 20,
        BLUE = 30
    };
    ```
    
- Không có kiểm tra phạm vi: có thể gán bất kỳ số nguyên nào cho biến kiểu `enum`, điều này có thể gây lỗi.

---

### **1.2 Enum Class (Scoped Enum)**

```cpp
#include <iostream>

enum class Color {
    RED,    // 0
    GREEN,  // 1
    BLUE    // 2
};

int main() {
    Color c = Color::GREEN;
    // std::cout << c; // Lỗi! Phải ép kiểu trước
    std::cout << static_cast<int>(c) << std::endl;  // Output: 1
    return 0;
}
```

📌 **Ưu điểm của `enum class`:** ✔ **Tự động giới hạn phạm vi**: Không thể dùng `Color::GREEN` trực tiếp như `GREEN`, tránh xung đột tên.  
✔ **Không thể gán giá trị ngoài phạm vi** (không thể gán số nguyên tùy ý như enum thường).  
✔ **Mạnh mẽ hơn, an toàn hơn, khuyến nghị sử dụng**.

---

## **2. So sánh Enum thường và Enum Class**

|**Đặc điểm**|**Enum thường**|**Enum Class**|
|---|---|---|
|Phạm vi tên|Toàn cục|Giới hạn (phải dùng `EnumName::Value`)|
|Ép kiểu tự động|Có|Không (phải `static_cast<int>`)|
|Tránh xung đột tên|Không|Có|
|Gán giá trị tự do|Có|Không|

---

## **3. Tùy chỉnh giá trị Enum**

Mặc định, giá trị của `enum` tăng dần từ `0`, nhưng có thể chỉnh sửa:

```cpp
enum Status {
    SUCCESS = 1,
    WARNING = 3,
    ERROR = 5
};

std::cout << SUCCESS; // Output: 1
```

- Có thể dùng toán tử `|` hoặc `&` để xử lý bit khi giá trị là lũy thừa của 2:
    
    ```cpp
    enum Permission {
        READ = 1,   // 001
        WRITE = 2,  // 010
        EXECUTE = 4 // 100
    };
    
    int permission = READ | WRITE; // 001 | 010 = 011 (3)
    ```
    

---

## **4. Kiểu dữ liệu nền của Enum**

Mặc định, enum dùng `int`, nhưng có thể chỉ định kiểu khác:

```cpp
enum class ErrorCode : char {
    OK = 'O',
    FAIL = 'F'
};

std::cout << static_cast<char>(ErrorCode::OK); // Output: O
```

✔ **Giúp tiết kiệm bộ nhớ** khi cần thiết.

---

## **5. Lặp qua các giá trị Enum**

C++ không hỗ trợ lặp qua `enum` trực tiếp, nhưng có thể dùng `std::array`:

```cpp
#include <iostream>
#include <array>

enum class Color { RED, GREEN, BLUE };

int main() {
    std::array<Color, 3> colors = {Color::RED, Color::GREEN, Color::BLUE};
    for (Color c : colors) {
        std::cout << static_cast<int>(c) << " ";
    }
    return 0;
}
// Output: 0 1 2
```

---

## **6. Chuyển Enum thành String**

C++ không hỗ trợ trực tiếp, nhưng có thể dùng `switch` hoặc `std::unordered_map`:

```cpp
#include <iostream>
#include <unordered_map>

enum class Color { RED, GREEN, BLUE };

std::string colorToString(Color color) {
    static std::unordered_map<Color, std::string> map = {
        {Color::RED, "Red"},
        {Color::GREEN, "Green"},
        {Color::BLUE, "Blue"}
    };
    return map[color];
}

int main() {
    std::cout << colorToString(Color::GREEN);  // Output: Green
}
```

✔ **Nhanh, dễ bảo trì**, nhưng cần C++11 trở lên.

---

## **7. Khi nào nên dùng Enum?**

✅ Khi cần tập hợp các giá trị cố định, dễ đọc hơn `#define`.  
✅ Khi giá trị không thay đổi trong suốt chương trình.  
✅ Khi cần kiểm tra điều kiện (`switch-case` với `enum` dễ đọc hơn so với `int`).  
✅ Khi muốn đại diện trạng thái (`enum class State { IDLE, RUNNING, STOPPED };`).

---

## **Kết luận**

🔹 Enum giúp mã nguồn dễ hiểu và tránh lỗi do sử dụng số nguyên trực tiếp.  
🔹 `enum class` an toàn hơn và được khuyến nghị dùng trong C++ hiện đại.  
🔹 Có thể tùy chỉnh kiểu dữ liệu và giá trị theo ý muốn.  
🔹 Cần các thủ thuật để chuyển đổi Enum sang string hoặc duyệt qua các giá trị.

🚀 **Lời khuyên:** Nếu đang làm việc với C++ hiện đại, **luôn ưu tiên dùng `enum class` thay vì `enum` truyền thống**.