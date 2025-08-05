#### **1. Tổng Quan về Kiểu Số Thực**

Trong C++, kiểu số thực được sử dụng để biểu diễn các số có phần thập phân. Chúng phù hợp cho các phép toán khoa học, tính toán chính xác cao, nhưng có thể gặp lỗi do cách biểu diễn nhị phân.

##### **Các loại kiểu số thực trong C++:**

|Kiểu dữ liệu|Kích thước (thường gặp)|Độ chính xác (số thập phân)|Phạm vi giá trị|
|---|---|---|---|
|`float`|4 byte|~6-7 chữ số|±3.4 × 10⁻³⁸ → ±3.4 × 10³⁸|
|`double`|8 byte|~15-16 chữ số|±1.7 × 10⁻³⁰⁸ → ±1.7 × 10³⁰⁸|
|`long double`|8 - 16 byte|~19-34 chữ số|Phụ thuộc vào hệ thống|

> **Lưu ý:** `double` là kiểu mặc định khi làm việc với số thực.

##### **Ví dụ khai báo biến số thực:**

```cpp
float f = 3.14159f;      // Hậu tố 'f' để chỉ rõ là float
double d = 2.718281828;  // Không cần hậu tố, mặc định là double
long double ld = 1.6180339887L; // Hậu tố 'L' cho long double
```

---

#### **2. Các Vấn Đề Khi Sử Dụng Kiểu Số Thực**

##### **2.1. Sai số và lỗi làm tròn**

Máy tính lưu số thực dưới dạng nhị phân (IEEE 754), dẫn đến sai số nhỏ khi tính toán.  
Ví dụ:

```cpp
#include <iostream>
int main() {
    double a = 0.1 + 0.2;
    if (a == 0.3) 
        std::cout << "Bằng 0.3\n";
    else 
        std::cout << "Không bằng 0.3: " << a << "\n";
    return 0;
}
```

🔹 **Kết quả:** Không bằng 0.3 do lỗi làm tròn (`a = 0.30000000000000004`).

**Giải pháp:** So sánh bằng cách dùng sai số epsilon.

```cpp
#include <cmath> 
const double EPSILON = 1e-9;
if (fabs(a - 0.3) < EPSILON) { /* Được coi là bằng nhau */ }
```

##### **2.2. Tràn số (Overflow) và mất số (Underflow)**

- **Tràn số:** Khi giá trị quá lớn, biến lưu trữ bị vượt quá giới hạn.
- **Mất số:** Khi giá trị quá nhỏ, máy tính làm tròn về 0.

Ví dụ:

```cpp
double big = 1e308 * 10;  // Tràn số -> Trả về "inf" (vô cùng)
double small = 1e-324 / 10;  // Mất số -> Trả về 0
```

---

#### **3. Các Hàm Xử Lý Số Thực Trong C++**

##### **3.1. Thư viện `<cmath>` (Mathematics Library)**

C++ cung cấp thư viện `<cmath>` để xử lý các phép toán số thực.

|Hàm|Chức năng|Ví dụ|
|---|---|---|
|`sqrt(x)`|Căn bậc hai|`sqrt(16) -> 4`|
|`pow(x, y)`|Lũy thừa|`pow(2, 3) -> 8`|
|`fabs(x)`|Giá trị tuyệt đối|`fabs(-3.14) -> 3.14`|
|`floor(x)`|Làm tròn xuống|`floor(2.9) -> 2`|
|`ceil(x)`|Làm tròn lên|`ceil(2.1) -> 3`|
|`round(x)`|Làm tròn chuẩn|`round(2.5) -> 3`|
|`fmod(x, y)`|Phần dư|`fmod(5.5, 2) -> 1.5`|
|`log(x), log10(x)`|Logarit|`log(2.718) -> 1`|
|`sin(x), cos(x), tan(x)`|Lượng giác|`sin(3.14)`|

##### **Ví dụ:**

```cpp
#include <iostream>
#include <cmath>
int main() {
    double x = 3.7;
    std::cout << "floor(x) = " << floor(x) << "\n";
    std::cout << "ceil(x) = " << ceil(x) << "\n";
    std::cout << "round(x) = " << round(x) << "\n";
    std::cout << "sqrt(x) = " << sqrt(x) << "\n";
    return 0;
}
```

---

#### **4. Định Dạng Xuất Số Thực**

C++ cung cấp các cách định dạng số thực khi xuất ra màn hình.

##### **4.1. Sử dụng `std::fixed` và `std::setprecision`**

```cpp
#include <iostream>
#include <iomanip>
int main() {
    double pi = 3.141592653589;
    std::cout << std::fixed << std::setprecision(4) << pi << "\n"; // 3.1416
    return 0;
}
```

##### **4.2. Hiển thị ở dạng khoa học (`std::scientific`)**

```cpp
std::cout << std::scientific << pi;  // 3.1416e+00
```

---

#### **5. Kiểm Tra Đặc Biệt Trên Số Thực**

##### **5.1. Kiểm tra vô cùng (`isinf`) và NaN (`isnan`)**

```cpp
#include <iostream>
#include <cmath>
int main() {
    double a = 1.0 / 0.0;  // Vô cùng
    double b = 0.0 / 0.0;  // NaN
    std::cout << "a là vô cùng? " << std::isinf(a) << "\n";
    std::cout << "b là NaN? " << std::isnan(b) << "\n";
    return 0;
}
```

##### **5.2. Kiểm tra số gần 0 (`fpclassify`)**

```cpp
if (std::fpclassify(x) == FP_SUBNORMAL) {
    std::cout << "Số x rất nhỏ gần 0\n";
}
```

---

### **Tóm Tắt**

|Chủ đề|Nội dung chính|
|---|---|
|**Các kiểu dữ liệu**|`float`, `double`, `long double`|
|**Vấn đề phổ biến**|Sai số, tràn số, mất số|
|**Các hàm quan trọng**|`sqrt()`, `pow()`, `fabs()`, `round()`, `sin()`|
|**Định dạng số thực**|`std::fixed`, `std::scientific`, `std::setprecision()`|
|**Kiểm tra số đặc biệt**|`isinf()`, `isnan()`, `fpclassify()`|

---

### **Kết Luận**

- **Dùng `double` thay vì `float` để tránh mất độ chính xác.**
- **Dùng sai số (`EPSILON`) để so sánh số thực.**
- **Kiểm tra NaN và vô cùng khi xử lý số thực.**
- **Dùng `std::setprecision()` để điều chỉnh số chữ số hiển thị.**

👉 Nếu cần hiệu suất cao hơn hoặc chính xác tuyệt đối, hãy sử dụng thư viện **Arbitrary Precision** như `mpfr` hoặc `Boost.Multiprecision`.