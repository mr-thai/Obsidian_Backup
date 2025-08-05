## 1. **Quy tắc tổng quát**

- Đặt tên có ý nghĩa, dễ hiểu, dễ đọc.
- Dùng tiếng Anh để dễ tra cứu và thống nhất với cộng đồng.
- Nhất quán về quy tắc đặt tên trong toàn bộ dự án.

---

## 2. **Quy tắc đặt tên [[biến]], hằng số**

### **Biến thường**

✅ **camelCase** (chữ đầu viết thường, chữ sau viết hoa):

```cpp
int maxValue;
float userScore;
string firstName;
```

🔹 **Không dùng dấu gạch dưới ( _ ) trừ khi có quy ước riêng.**

### **Biến toàn cục (Global Variable)**

- Hạn chế dùng biến toàn cục.
- Nếu dùng, có thể thêm tiền tố `g_` để dễ phân biệt:

```cpp
int g_maxUsers;
double g_totalRevenue;
```

### **[[Hằng số (const, constexpr, macro)]]**

✅ **UPPER_CASE_SNAKE_CASE** (chữ in hoa, cách nhau bằng `_`):

```cpp
const int MAX_USERS = 100;
constexpr double PI = 3.14159;
#define SCREEN_WIDTH 1920
```

---

## 3. **Quy tắc đặt tên hàm**

✅ **camelCase**, động từ đứng trước danh từ:

```cpp
void calculateArea();
int getUserId();
bool isValidEmail();
```

🔹 **Hàm getter/setter**:

```cpp
int getAge();
void setAge(int newAge);
```

---

## 4. **Quy tắc đặt tên class, struct**

✅ **PascalCase** (chữ đầu viết hoa, không có dấu gạch dưới `_`):

```cpp
class UserManager;
struct Point3D;
```

🔹 **Tên class nên là danh từ:**  
✅ `UserManager`, `FileHandler`, `NetworkSocket`  
❌ `ManageUser`, `HandleFile`

🔹 **Tên struct nếu chỉ là tập dữ liệu có thể viết đơn giản:**

```cpp
struct Point {
    int x, y;
};
```

---

## 5. **Quy tắc đặt tên namespace**

✅ **camelCase hoặc PascalCase**:

```cpp
namespace mathUtils {
    int add(int a, int b);
}

namespace GraphicsEngine {
    class Renderer;
}
```

---

## 6. **Quy tắc đặt tên file**

✅ **snake_case** (chữ thường, gạch dưới `_` để phân tách từ):

```cpp
math_utils.cpp
user_manager.h
game_engine.cpp
```

🔹 **Header file nên có phần mở rộng `.h` hoặc `.hpp`**  
🔹 **Source file nên có phần mở rộng `.cpp`**

---

## 7. **Quy tắc đặt tên thư mục**

✅ **snake_case hoặc PascalCase**:

```plaintext
src/
    core/
    utils/
    graphics/
```

✅ **Cấu trúc thư mục gọn gàng:**

```plaintext
project_name/
    include/    # Chứa file header (.h, .hpp)
    src/        # Chứa file mã nguồn (.cpp)
    assets/     # Chứa hình ảnh, âm thanh, tài nguyên
    tests/      # Chứa unit tests
    build/      # Chứa file biên dịch tạm thời
```

---

## 8. **Quy tắc đặt tên enum**

✅ **PascalCase cho kiểu enum, UPPER_CASE_SNAKE_CASE cho giá trị enum:**

```cpp
enum Color {
    RED,
    GREEN,
    BLUE
};
```

🔹 **Nếu dùng `enum class`, có thể viết PascalCase:**

```cpp
enum class LogLevel {
    Debug,
    Info,
    Warning,
    Error
};
```

---

## 9. **Quy tắc đặt tên [[template]]**

✅ **Một chữ cái viết hoa (T, U, V)** hoặc có ý nghĩa như `KeyType`, `ValueType`:

```cpp
template <typename T>
class Vector;

template <typename KeyType, typename ValueType>
class Map;
```

---

## 10. **Quy tắc đặt tên kiểu [[typedef]] và [[alias]]**

✅ **PascalCase**

```cpp
typedef unsigned int UInt;
using StringList = std::vector<std::string>;
```

---

### ✅ **Tóm tắt quy tắc đặt tên**

| Đối tượng      | Quy tắc đặt tên                    | Ví dụ                         |
| -------------- | ---------------------------------- | ----------------------------- |
| Biến thường    | camelCase                          | `userScore`                   |
| Biến toàn cục  | g_ + camelCase                     | `g_maxUsers`                  |
| Hằng số        | UPPER_CASE_SNAKE_CASE              | `MAX_USERS`                   |
| Hàm            | camelCase                          | `calculateArea()`             |
| Class / Struct | PascalCase                         | `UserManager`                 |
| Namespace      | camelCase / PascalCase             | `mathUtils`, `GraphicsEngine` |
| File           | snake_case                         | `user_manager.cpp`            |
| Thư mục        | snake_case / PascalCase            | `src/graphics/`               |
| Enum           | PascalCase / UPPER_CASE_SNAKE_CASE | `enum Color { RED, GREEN }`   |
| Template       | Một chữ cái hoặc PascalCase        | `template <typename T>`       |

---

⚡ **Ghi nhớ:** **Quan trọng nhất là phải nhất quán trong toàn bộ codebase!**