### Toán tử phạm vi (`::`) trong C++

Toán tử phạm vi (`::`) là một trong những toán tử quan trọng trong C++, được sử dụng để truy cập thành viên của một phạm vi cụ thể, chẳng hạn như một **namespace**, **class**, **struct**, hoặc **enum**. Nó giúp phân biệt các thực thể có cùng tên nhưng thuộc các phạm vi khác nhau.

---

## 1. **Công dụng của toán tử phạm vi**

Toán tử `::` có thể được sử dụng trong các trường hợp sau:

1. **Truy cập thành viên của namespace** (biến, hàm, class trong namespace)
2. **Truy cập thành viên tĩnh của class hoặc struct**
3. **Truy cập hàm hoặc biến toàn cục khi bị che khuất bởi tên cục bộ**
4. **Định nghĩa hàm bên ngoài lớp**
5. **Truy cập thành viên của enum**
6. **Truy cập kiểu dữ liệu bên trong class hoặc struct**

---

## 2. **Chi tiết cách sử dụng**

### 2.1 **Truy cập thành viên của namespace**

C++ hỗ trợ **namespace** để tổ chức mã nguồn. Khi một thành phần nằm trong namespace, ta dùng `::` để truy cập nó.

Ví dụ:

```cpp
#include <iostream>

namespace MyNamespace {
    int value = 10;
    void show() {
        std::cout << "Hello from MyNamespace!" << std::endl;
    }
}

int main() {
    std::cout << MyNamespace::value << std::endl; // Truy cập biến trong namespace
    MyNamespace::show();  // Gọi hàm trong namespace
    return 0;
}
```

**Giải thích:**

- `MyNamespace::value` truy cập biến `value` trong namespace `MyNamespace`.
- `MyNamespace::show()` gọi hàm `show()` trong namespace `MyNamespace`.

> **Lưu ý:** Nếu sử dụng `using namespace MyNamespace;`, ta có thể truy cập trực tiếp mà không cần `::`, nhưng điều này có thể gây xung đột tên.

---

### 2.2 **Truy cập thành viên tĩnh của class/struct**

Toán tử phạm vi được dùng để truy cập các thành viên **tĩnh** (static) của một class hoặc struct.

Ví dụ:

```cpp
#include <iostream>

class MyClass {
public:
    static int staticVar; // Biến tĩnh
    static void staticMethod() { // Hàm tĩnh
        std::cout << "Static method called!" << std::endl;
    }
};

// Định nghĩa biến tĩnh bên ngoài class
int MyClass::staticVar = 100;

int main() {
    std::cout << MyClass::staticVar << std::endl;  // Truy cập biến tĩnh
    MyClass::staticMethod();  // Gọi hàm tĩnh
    return 0;
}
```

**Giải thích:**

- `MyClass::staticVar` truy cập biến tĩnh của class.
- `MyClass::staticMethod()` gọi hàm tĩnh của class.

---

### 2.3 **Truy cập biến hoặc hàm toàn cục khi bị che khuất**

Nếu một biến hoặc hàm toàn cục bị che khuất bởi biến/hàm cục bộ trong một hàm, ta có thể dùng `::` để truy cập phiên bản toàn cục.

Ví dụ:

```cpp
#include <iostream>

int value = 42; // Biến toàn cục

int main() {
    int value = 10; // Biến cục bộ che khuất biến toàn cục
    std::cout << value << std::endl;   // In ra biến cục bộ (10)
    std::cout << ::value << std::endl; // Truy cập biến toàn cục (42)
    return 0;
}
```

**Giải thích:**

- `value` trong `main()` che khuất `value` toàn cục.
- `::value` đảm bảo truy cập biến toàn cục.

---

### 2.4 **Định nghĩa hàm bên ngoài lớp**

Trong C++, ta có thể khai báo một phương thức trong class và định nghĩa nó bên ngoài bằng cách dùng `::`.

Ví dụ:

```cpp
#include <iostream>

class MyClass {
public:
    void show(); // Khai báo phương thức
};

// Định nghĩa phương thức bên ngoài class
void MyClass::show() {
    std::cout << "Hello from MyClass!" << std::endl;
}

int main() {
    MyClass obj;
    obj.show(); // Gọi phương thức
    return 0;
}
```

**Giải thích:**

- `void MyClass::show()` dùng `::` để chỉ rõ `show()` thuộc `MyClass`.

---

### 2.5 **Truy cập thành viên của enum**

Toán tử `::` được dùng để truy cập các giá trị của enum.

Ví dụ:

```cpp
#include <iostream>

enum Color { RED, GREEN, BLUE };

int main() {
    Color myColor = Color::GREEN; // Truy cập giá trị enum
    std::cout << myColor << std::endl; // In ra 1 (vì GREEN = 1)
    return 0;
}
```

**Giải thích:**

- `Color::GREEN` giúp xác định `GREEN` thuộc `Color`.

---

### 2.6 **Truy cập kiểu dữ liệu bên trong class hoặc struct**

Trong C++, class hoặc struct có thể chứa kiểu dữ liệu bên trong, và ta cần `::` để truy cập chúng.

Ví dụ:

```cpp
#include <iostream>

class Outer {
public:
    class Inner { // Lớp bên trong
    public:
        static void show() {
            std::cout << "Inside Inner class!" << std::endl;
        }
    };
};

int main() {
    Outer::Inner::show(); // Truy cập phương thức của Inner
    return 0;
}
```

**Giải thích:**

- `Outer::Inner::show()` truy cập phương thức `show()` của class `Inner` bên trong `Outer`.

---

## 3. **Tổng kết**

| Trường hợp                   | Ví dụ                               |
| ---------------------------- | ----------------------------------- |
| Namespace                    | `std::cout`, `MyNamespace::func()`  |
| Biến/hàm toàn cục            | `::globalVar`, `::globalFunction()` |
| Thành viên tĩnh của class    | `ClassName::staticMember`           |
| Định nghĩa hàm ngoài class   | `ClassName::methodName()`           |
| [[Giá trị enum]]             | `EnumName::ENUM_VALUE`              |
| Kiểu dữ liệu bên trong class | `OuterClass::InnerClass`            |

Toán tử phạm vi (`::`) là một công cụ mạnh mẽ giúp kiểm soát và truy cập các thành phần trong chương trình một cách rõ ràng. Việc sử dụng đúng `::` giúp tránh xung đột tên, cải thiện tính tổ chức và đọc hiểu mã nguồn.