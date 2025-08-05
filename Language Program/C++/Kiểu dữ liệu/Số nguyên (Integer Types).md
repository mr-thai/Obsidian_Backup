### **1. Các kiểu số nguyên trong C++**

C++ cung cấp nhiều loại số nguyên với kích thước và phạm vi giá trị khác nhau.

|Kiểu dữ liệu|Kích thước (bit)|Phạm vi giá trị|
|---|---|---|
|`short`|16|-32,768 đến 32,767|
|`int`|32|-2,147,483,648 đến 2,147,483,647|
|`long`|32 hoặc 64|Tùy vào hệ thống|
|`long long`|64|-9,223,372,036,854,775,808 đến 9,223,372,036,854,775,807|
|`unsigned short`|16|0 đến 65,535|
|`unsigned int`|32|0 đến 4,294,967,295|
|`unsigned long`|32 hoặc 64|Tùy vào hệ thống|
|`unsigned long long`|64|0 đến 18,446,744,073,709,551,615|

📌 **Lưu ý:** Kích thước có thể thay đổi tùy vào hệ điều hành và trình biên dịch.

### **2. Các vấn đề liên quan đến số nguyên**

#### **2.1. Tràn số (Overflow) và Lỗi tràn số (Underflow)**

Nếu một biến số nguyên vượt quá giới hạn lưu trữ của nó, giá trị sẽ bị "tràn" và dẫn đến kết quả không mong muốn.

Ví dụ về tràn số:

```cpp
#include <iostream>
#include <limits>

int main() {
    int maxInt = std::numeric_limits<int>::max(); // Lấy giá trị lớn nhất của int
    std::cout << "Max int: " << maxInt << std::endl;
    std::cout << "Max int + 1: " << maxInt + 1 << std::endl; // Tràn số!
    return 0;
}
```

🔥 **Kết quả:** `maxInt + 1` có thể tạo ra một giá trị âm do tràn số.

#### **2.2. Ép kiểu số nguyên**

C++ cho phép ép kiểu số nguyên khi cần thiết:

```cpp
int a = 300;
short b = (short)a; // Ép kiểu từ int sang short
std::cout << b << std::endl;
```

⚠ **Lưu ý:** Nếu giá trị vượt quá phạm vi của kiểu dữ liệu đích, kết quả có thể không chính xác.

---

### **3. Các hàm liên quan đến số nguyên trong C++**

#### **3.1. `std::numeric_limits<>` (Xác định giới hạn của kiểu số)**

Dùng để kiểm tra giới hạn của kiểu dữ liệu số nguyên.

```cpp
#include <iostream>
#include <limits>

int main() {
    std::cout << "Min int: " << std::numeric_limits<int>::min() << std::endl;
    std::cout << "Max int: " << std::numeric_limits<int>::max() << std::endl;
    return 0;
}
```

#### **3.2. `abs()` - Giá trị tuyệt đối**

```cpp
#include <iostream>
#include <cmath>

int main() {
    int x = -10;
    std::cout << "abs(-10) = " << abs(x) << std::endl;
    return 0;
}
```

#### **3.3. `pow()` - Lũy thừa (Dùng với `double`, cần ép kiểu lại nếu dùng với số nguyên)**

```cpp
#include <iostream>
#include <cmath>

int main() {
    int base = 2, exponent = 5;
    int result = static_cast<int>(pow(base, exponent)); // Ép kiểu về int
    std::cout << "2^5 = " << result << std::endl;
    return 0;
}
```

#### **3.4. `rand()` - Sinh số ngẫu nhiên**

```cpp
#include <iostream>
#include <cstdlib> // Thư viện rand()
#include <ctime>   // Thư viện time()

int main() {
    srand(time(0)); // Khởi tạo seed cho rand()
    int randomNumber = rand() % 100; // Sinh số ngẫu nhiên từ 0 đến 99
    std::cout << "Random number: " << randomNumber << std::endl;
    return 0;
}
```

#### **3.5. `stoi()`, `stol()`, `stoll()` - Chuyển đổi chuỗi thành số nguyên**

```cpp
#include <iostream>
#include <string>

int main() {
    std::string numStr = "12345";
    int num = std::stoi(numStr);
    std::cout << "Converted number: " << num << std::endl;
    return 0;
}
```

---

### **4. Một số mẹo và best practices**

✅ **Dùng `unsigned` khi chắc chắn giá trị không âm** (Ví dụ: số lượng phần tử, chỉ mục mảng).  
✅ **Dùng `long long` cho số lớn thay vì `int`** để tránh tràn số.  
✅ **Dùng `std::numeric_limits<>` để kiểm tra phạm vi của kiểu số nguyên trước khi tính toán.**  
✅ **Tránh ép kiểu không cần thiết vì có thể mất dữ liệu.**

---

📌 **Kết luận:**

- Kiểu số nguyên trong C++ có nhiều loại với kích thước và phạm vi khác nhau.
- Cần chú ý đến tràn số (overflow) và các giới hạn của từng kiểu dữ liệu.
- Có nhiều hàm hỗ trợ thao tác với số nguyên như `abs()`, `pow()`, `rand()`, `stoi()`.
- Cần áp dụng các best practices để tránh lỗi liên quan đến số nguyên.

