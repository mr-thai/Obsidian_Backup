### **1. Hàm là gì?**

Hàm (function) trong C++ là một khối mã có thể được gọi thực thi nhiều lần thay vì viết lại cùng một đoạn mã nhiều lần. Hàm giúp mã nguồn gọn gàng hơn, dễ bảo trì, và tối ưu hiệu suất chương trình.

Ví dụ đơn giản về một hàm trong C++:

```cpp
#include <iostream>
using namespace std;

// Hàm cộng hai số nguyên
int add(int a, int b) {
    return a + b;
}

int main() {
    cout << add(3, 5); // Gọi hàm add và in kết quả: 8
    return 0;
}
```

---

### **2. Cấu trúc một hàm trong C++**

Một hàm trong C++ gồm 3 phần chính:

1. **Khai báo hàm (Function Declaration/Prototype)** – Khai báo trước để trình biên dịch biết kiểu trả về và tham số của hàm.
2. **Định nghĩa hàm (Function Definition)** – Phần viết nội dung thực thi của hàm.
3. **Gọi hàm (Function Call)** – Sử dụng hàm trong chương trình.

Ví dụ minh họa:

```cpp
#include <iostream>
using namespace std;

// Khai báo hàm
int multiply(int, int);

int main() {
    cout << multiply(4, 6); // Gọi hàm
    return 0;
}

// Định nghĩa hàm
int multiply(int x, int y) {
    return x * y;
}
```

---

### **3. Phân loại hàm trong C++**

#### **a) Hàm có giá trị trả về (Return Value Function)**

Hàm có kiểu trả về khác `void`, sử dụng `return` để trả về giá trị.

```cpp
double square(double x) {
    return x * x;
}
```

#### **b) Hàm không có giá trị trả về (void Function)**

Hàm kiểu `void` không trả về giá trị nào.

```cpp
void greet() {
    cout << "Hello, world!";
}
```

#### **c) Hàm có tham số và không có tham số**

- **Hàm có tham số:** Nhận giá trị từ bên ngoài.
- **Hàm không có tham số:** Không nhận giá trị bên ngoài.

Ví dụ:

```cpp
void sayHello() { // Không có tham số
    cout << "Hello!";
}

void printNumber(int num) { // Có tham số
    cout << "Number: " << num;
}
```

---

### **4. Truyền tham số vào hàm**

C++ hỗ trợ ba cách truyền tham số:

#### **a) Truyền tham trị (Pass by Value)**

- Hàm chỉ nhận một bản sao của tham số.
- Không ảnh hưởng đến giá trị gốc.

```cpp
void changeValue(int x) {
    x = 100;
}
```

#### **b) Truyền tham chiếu (Pass by Reference)**

- Dùng ký hiệu `&`, tham số là tham chiếu đến biến gốc.
- Thay đổi trong hàm cũng thay đổi biến gốc.

```cpp
void changeValue(int &x) {
    x = 100;
}
```

#### **c) Truyền con trỏ (Pass by Pointer)**

- Sử dụng con trỏ để truyền địa chỉ.

```cpp
void changeValue(int *x) {
    *x = 100;
}
```

---

### **5. Hàm nạp chồng (Function Overloading)**

Hàm có cùng tên nhưng khác số lượng hoặc kiểu tham số.

```cpp
int add(int a, int b) { return a + b; }
double add(double a, double b) { return a + b; }
```

Gọi hàm:

```cpp
cout << add(3, 5);   // Gọi add(int, int)
cout << add(2.5, 3.1); // Gọi add(double, double)
```

---

### **6. Hàm mặc định tham số (Default Arguments)**

C++ cho phép đặt giá trị mặc định cho tham số.

```cpp
void greet(string name = "Guest") {
    cout << "Hello, " << name;
}
```

Gọi hàm:

```cpp
greet();          // In: Hello, Guest
greet("Alice");   // In: Hello, Alice
```

---

### **7. Hàm đệ quy (Recursive Function)**

Hàm tự gọi chính nó để giải quyết bài toán.

Ví dụ: Tính giai thừa `n! = n * (n-1)!`

```cpp
int factorial(int n) {
    if (n == 0) return 1;
    return n * factorial(n - 1);
}
```

---

### **8. Hàm inline (Inline Function)**

Giúp tối ưu tốc độ bằng cách thay thế lời gọi hàm bằng mã nguồn hàm.

```cpp
inline int square(int x) { return x * x; }
```

---

### **9. Hàm trong namespace**

Namespace giúp tránh xung đột tên hàm.

```cpp
namespace Math {
    int add(int a, int b) { return a + b; }
}

int main() {
    cout << Math::add(3, 4); // Gọi hàm trong namespace
}
```

---

### **10. Hàm `main()` và `return 0`**

- `main()` là hàm bắt buộc trong C++.
- `return 0;` báo hiệu chương trình kết thúc bình thường.

```cpp
int main() {
    cout << "Hello, C++";
    return 0;
}
```

---

### **Tổng kết**

|Loại hàm|Đặc điểm|
|---|---|
|Hàm có trả về|Dùng `return` để trả về giá trị|
|Hàm không trả về|Kiểu `void`, không có `return`|
|Truyền tham trị|Chỉ truyền giá trị, không thay đổi biến gốc|
|Truyền tham chiếu|Dùng `&`, thay đổi biến gốc|
|Truyền con trỏ|Dùng `*`, thao tác trực tiếp trên bộ nhớ|
|Nạp chồng hàm|Cùng tên, khác tham số|
|Hàm mặc định tham số|Giá trị mặc định khi không truyền|
|Đệ quy|Hàm gọi chính nó|
|Inline|Tăng tốc chương trình|

---

### **Ứng dụng thực tế**

4. **Tính toán đơn giản:** Viết hàm cộng, trừ, nhân, chia.
5. **Xử lý chuỗi:** Viết hàm kiểm tra chuỗi đối xứng.
6. **Quản lý dữ liệu:** Viết hàm CRUD (Create, Read, Update, Delete).
7. **Giải thuật:** Viết hàm sắp xếp, tìm kiếm.
