### 📌 Toán tử gán (Assignment Operators) trong C++

Toán tử gán (` = `) và các biến thể của nó là một phần quan trọng của C++ giúp gán giá trị cho biến. Cùng tìm hiểu chi tiết từng loại toán tử gán và cách chúng hoạt động!

---

## 🏆 1. Toán tử gán cơ bản (` = `)

🔹 **Công dụng**: Gán giá trị bên phải vào biến bên trái.  
🔹 **Cú pháp**:

```cpp
a = b;  // Gán giá trị của b vào a
```

🔹 **Ví dụ**:

```cpp
int x = 10;  // Gán 10 cho biến x
int y = x;   // Gán giá trị của x (10) cho y
```

🔹 **Lưu ý**:

- Nếu `b` có kiểu dữ liệu khác `a`, C++ sẽ tự động ép kiểu (có thể gây mất dữ liệu).
- Khi gán con trỏ (`int* p = &a;`), ta gán địa chỉ của `a` cho `p`.

---

## 🏆 2. Toán tử gán mở rộng (Compound Assignment Operators)

C++ hỗ trợ các toán tử gán kết hợp với toán tử số học và toán tử bit.

### 2.1 ✅ **Toán tử gán số học**

|Toán tử|Tương đương với|Chức năng|
|---|---|---|
|`a += b`|`a = a + b`|Cộng rồi gán|
|`a -= b`|`a = a - b`|Trừ rồi gán|
|`a *= b`|`a = a * b`|Nhân rồi gán|
|`a /= b`|`a = a / b`|Chia rồi gán|
|`a %= b`|`a = a % b`|Lấy dư rồi gán|

🔹 **Ví dụ**:

```cpp
int a = 10;
a += 5;  // a = a + 5 -> a = 15
a -= 3;  // a = a - 3 -> a = 12
a *= 2;  // a = a * 2 -> a = 24
a /= 4;  // a = a / 4 -> a = 6
a %= 5;  // a = a % 5 -> a = 1
```

### 2.2 ✅ **Toán tử gán bitwise (Bitwise Assignment)**

|Toán tử|Tương đương với|Chức năng|
|---|---|---|
|`a &= b`|`a = a & b`|AND bit|
|`a|= b`|`a = a|
|`a ^= b`|`a = a ^ b`|XOR bit|
|`a <<= n`|`a = a << n`|Dịch trái `n` bit|
|`a >>= n`|`a = a >> n`|Dịch phải `n` bit|

🔹 **Ví dụ**:

```cpp
int a = 5;  // 0101 (nhị phân)
a &= 3;     // 0101 & 0011 = 0001 -> a = 1
a |= 6;     // 0001 | 0110 = 0111 -> a = 7
a ^= 2;     // 0111 ^ 0010 = 0101 -> a = 5
a <<= 1;    // 0101 << 1 = 1010 -> a = 10
a >>= 2;    // 1010 >> 2 = 0010 -> a = 2
```

---

## 🏆 3. Toán tử gán đối với con trỏ

🔹 **Gán địa chỉ của biến**

```cpp
int a = 10;
int* p = &a; // Gán địa chỉ của a cho con trỏ p
```

🔹 **Gán con trỏ khác**

```cpp
int x = 5, y = 10;
int* ptr1 = &x;
int* ptr2 = ptr1; // ptr2 trỏ đến cùng địa chỉ với ptr1 (x)
```

🔹 **Gán `nullptr` để tránh lỗi con trỏ rác**

```cpp
int* p = nullptr; // Con trỏ không trỏ vào đâu cả
```

---

## 🏆 4. Toán tử gán đối với chuỗi (std::string)

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string s1 = "Hello";
    string s2 = s1;  // Gán chuỗi
    s1 += " World";  // Nối chuỗi rồi gán

    cout << s1 << endl; // "Hello World"
    cout << s2 << endl; // "Hello"
}
```

---

## 🏆 5. Toán tử gán trong lập trình hướng đối tượng (OOP)

Nếu lớp có con trỏ cấp phát động (`new`), cần viết **toán tử gán tùy chỉnh (`operator=`)** để tránh rò rỉ bộ nhớ.

🔹 **Ví dụ**:

```cpp
class MyClass {
private:
    int* data;
public:
    MyClass(int val) { data = new int(val); }
    ~MyClass() { delete data; }

    // Toán tử gán tùy chỉnh (deep copy)
    MyClass& operator=(const MyClass& other) {
        if (this == &other) return *this; // Tránh tự gán

        delete data;  // Giải phóng bộ nhớ cũ
        data = new int(*other.data);  // Cấp phát mới và sao chép

        return *this;
    }
};
```

🔹 **Lưu ý**: Nếu không định nghĩa `operator=`, khi gán hai đối tượng, cả hai sẽ trỏ cùng một vùng nhớ (shallow copy), dễ gây lỗi.

---

## 🏆 6. Toán tử gán di chuyển (`operator=` move)

Khi sử dụng **C++11 trở lên**, ta có thể tối ưu bằng **move assignment operator (`operator=` &&)**.

🔹 **Ví dụ**:

```cpp
class MyClass {
private:
    int* data;
public:
    MyClass(int val) { data = new int(val); }
    ~MyClass() { delete data; }

    // Move assignment (C++11)
    MyClass& operator=(MyClass&& other) noexcept {
        if (this == &other) return *this;

        delete data;
        data = other.data;
        other.data = nullptr; // Vô hiệu hóa đối tượng nguồn

        return *this;
    }
};
```

🔹 **Ưu điểm**:  
✔ Giúp tăng tốc độ khi gán đối tượng lớn.  
✔ Tránh cấp phát bộ nhớ mới không cần thiết.

---

## 🔥 Tổng kết

|Loại toán tử gán|Công dụng|
|---|---|
|`=`|Gán giá trị cơ bản|
|`+=`, `-=`, `*=`, `/=`, `%=`|Toán tử gán số học|
|`&=`, `|=`,` ^=`,` <<=`,` >>=`|
|`operator=`|Toán tử gán tùy chỉnh trong class|
|`operator=` (move)|Toán tử gán di chuyển (C++11)|

💡 **Mẹo nhớ nhanh**:

- Toán tử ` = ` dùng để gán giá trị.
- Các toán tử `+=, -=, *=...` giúp tối ưu code.
- Nếu sử dụng con trỏ hoặc bộ nhớ động, cần viết `operator=` tùy chỉnh.
- Dùng move assignment (`operator= &&`) để tối ưu hiệu suất.
