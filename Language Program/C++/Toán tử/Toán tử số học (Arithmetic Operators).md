Toán tử số học là nhóm toán tử cơ bản giúp thực hiện các phép toán toán học trên dữ liệu số trong C++. Chúng có thể áp dụng cho kiểu **số nguyên (`int`, `long`...)** và **số thực (`float`, `double`)**.

---

## **1. Danh sách toán tử số học trong C++**

|Toán tử|Tên gọi|Chức năng|Ví dụ (`a = 10, b = 3`)|
|---|---|---|---|
|`+`|Cộng|Cộng hai số|`a + b` → `10 + 3 = 13`|
|`-`|Trừ|Trừ số thứ hai khỏi số thứ nhất|`a - b` → `10 - 3 = 7`|
|`*`|Nhân|Nhân hai số|`a * b` → `10 * 3 = 30`|
|`/`|Chia|Chia số thứ nhất cho số thứ hai|`a / b` → `10 / 3 = 3` _(phép chia nguyên)_|
|`%`|Chia lấy dư (modulo)|Lấy phần dư của phép chia số thứ nhất cho số thứ hai|`a % b` → `10 % 3 = 1`|

> **Lưu ý:**
> 
> - Khi cả hai toán hạng là số nguyên (`int`), phép chia `/` thực hiện **chia nguyên** (bỏ phần thập phân).
> - Để có kết quả số thực, ít nhất một toán hạng phải là số thực (`float`, `double`).

---

## **2. Ví dụ minh họa**

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 10, b = 3;
    float x = 10.0, y = 3.0;

    cout << "a + b = " << (a + b) << endl;
    cout << "a - b = " << (a - b) << endl;
    cout << "a * b = " << (a * b) << endl;
    cout << "a / b = " << (a / b) << endl;  // Chia nguyên
    cout << "x / y = " << (x / y) << endl;  // Chia thực
    cout << "a % b = " << (a % b) << endl;

    return 0;
}
```

### **Kết quả**

```
a + b = 13
a - b = 7
a * b = 30
a / b = 3      // Chia nguyên
x / y = 3.33333 // Chia thực
a % b = 1
```

---

## **3. Toán tử một ngôi (+, -)**

C++ hỗ trợ `+` và `-` ở dạng **toán tử một ngôi**:

- `+a`: Không thay đổi giá trị của `a` (hiếm khi sử dụng).
- `-a`: Đổi dấu của `a`.

### **Ví dụ**

```cpp
int a = 5, b = -8;
cout << "+a = " << +a << endl;  // 5
cout << "-b = " << -b << endl;  // 8
```

---

## **4. Lưu ý khi sử dụng toán tử số học**

### **4.1. Chia cho 0**

- Khi chia nguyên cho `0`, chương trình sẽ bị lỗi **runtime error**.
- Khi chia số thực cho `0`, kết quả có thể là **vô cùng (`inf`)** hoặc **NaN**.

🔴 **Ví dụ lỗi chia cho 0**

```cpp
int a = 10, b = 0;
cout << a / b; // LỖI: Chia cho 0 (runtime error)
```

✅ **Ví dụ xử lý an toàn**

```cpp
if (b != 0)
    cout << a / b;
else
    cout << "Không thể chia cho 0!";
```

---

### **4.2. Dùng `double` hoặc `float` để tránh chia nguyên**

```cpp
int a = 10, b = 3;
cout << a / b;       // Kết quả: 3 (chia nguyên)
cout << (double)a / b; // Kết quả: 3.33333
```

> **Cách ép kiểu tránh chia nguyên:**
> 
> - `(double)a / b`
> - `(float)a / b`
> - `static_cast<double>(a) / b`

---

## **5. Toán tử số học kết hợp (`+=, -=, *=, /=, %=`)**

|Toán tử|Tương đương với|Ví dụ (`a = 10, b = 3`)|
|---|---|---|
|`+=`|`a = a + b`|`a += b; // a = 13`|
|`-=`|`a = a - b`|`a -= b; // a = 7`|
|`*=`|`a = a * b`|`a *= b; // a = 30`|
|`/=`|`a = a / b`|`a /= b; // a = 3`|
|`%=`|`a = a % b`|`a %= b; // a = 1`|

### **Ví dụ**

```cpp
int a = 10;
a += 5; // Tương đương: a = a + 5;
cout << a; // 15
```

---

## **6. Toán tử tăng (`++`) và giảm (`--`)**

|Toán tử|Chức năng|Ghi chú|
|---|---|---|
|`++a`|Tăng `a` trước khi sử dụng|Tiền tố (prefix)|
|`a++`|Tăng `a` sau khi sử dụng|Hậu tố (postfix)|
|`--a`|Giảm `a` trước khi sử dụng|Tiền tố (prefix)|
|`a--`|Giảm `a` sau khi sử dụng|Hậu tố (postfix)|

### **Ví dụ**

```cpp
int x = 5;
cout << x++ << endl; // In ra 5, sau đó x = 6
cout << ++x << endl; // Tăng x lên 7, rồi in ra 7
```

**Cách nhớ dễ dàng:**

- **Tiền tố (`++a, --a`)** → tăng/giảm rồi mới dùng.
- **Hậu tố (`a++, a--`)** → dùng trước rồi mới tăng/giảm.

---

## **7. Tổng kết**

- **Toán tử số học**: `+`, `-`, `*`, `/`, `%`
- **Toán tử một ngôi**: `+a`, `-a`
- **Toán tử kết hợp**: `+=`, `-=`, `*=`, `/=`, `%=`
- **Toán tử tăng/giảm**: `++`, `--` (tiền tố/hậu tố)
- **Lưu ý quan trọng**:
    - Chia số nguyên `/` bị cắt phần thập phân.
    - Chia cho `0` gây lỗi runtime.
    - Ép kiểu (`(double)a / b`) để tránh chia nguyên.

