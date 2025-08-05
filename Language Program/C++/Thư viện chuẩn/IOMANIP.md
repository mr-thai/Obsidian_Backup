Thư viện `<iomanip>` trong C++ cung cấp các công cụ để định dạng đầu ra trên luồng **`std::cout`** hoặc các luồng đầu ra khác. Nó chủ yếu hoạt động thông qua các **manipulator (bộ điều chỉnh)** giúp điều chỉnh định dạng số, căn chỉnh, độ rộng hiển thị, và các ký tự đệm.

---

## **1. Các Manipulator Quan Trọng trong `<iomanip>`**

### **1.1. Điều chỉnh độ rộng hiển thị**

#### 🔹 `setw(n)`

- Đặt độ rộng tối thiểu của giá trị in ra.
- Nếu giá trị ngắn hơn `n`, nó sẽ được căn lề phải theo mặc định.

🔹 **Ví dụ:**

```cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    cout << setw(10) << 42 << endl;
    cout << setw(10) << "Hello" << endl;
    return 0;
}
```

🔹 **Output:**

```
        42
     Hello
```

> Lưu ý: `setw(n)` chỉ áp dụng cho giá trị ngay sau nó, không ảnh hưởng đến toàn bộ chương trình.

---

### **1.2. Căn chỉnh (Align)**

#### 🔹 `left` / `right` / `internal`

- `left`: Căn trái.
- `right`: Căn phải (mặc định).
- `internal`: Căn giữa, dấu `+/-` ở bên trái, số ở bên phải.

🔹 **Ví dụ:**

```cpp
cout << left  << setw(10) << 42 << "Left-aligned\n";
cout << right << setw(10) << 42 << "Right-aligned\n";
cout << internal << setw(10) << -42 << "Internal-aligned\n";
```

🔹 **Output:**

```
42        Left-aligned
        42Right-aligned
-        42Internal-aligned
```

> `internal` thường hữu ích khi hiển thị số âm hoặc số có dấu.

---

### **1.3. Ký tự đệm (`setfill`)**

- Dùng để thay thế khoảng trống bằng một ký tự khác khi sử dụng `setw`.

🔹 **Ví dụ:**

```cpp
cout << setfill('*') << setw(10) << 42 << endl;
```

🔹 **Output:**

```
********42
```

---

## **2. Định dạng số (Số nguyên & Số thực)**

### **2.1. Hệ cơ số (`dec`, `hex`, `oct`)**

- `dec`: Hệ thập phân (mặc định).
- `hex`: Hệ thập lục phân.
- `oct`: Hệ bát phân.

🔹 **Ví dụ:**

```cpp
int num = 255;
cout << "Decimal: " << dec << num << endl;
cout << "Hex: " << hex << num << endl;
cout << "Octal: " << oct << num << endl;
```

🔹 **Output:**

```
Decimal: 255
Hex: ff
Octal: 377
```

> **Lưu ý:** `hex` và `oct` giữ nguyên hiệu lực cho đến khi đổi về `dec`.

---

### **2.2. Hiển thị số dạng khoa học (`scientific`) và dấu chấm động (`fixed`)**

- `scientific`: Hiển thị số dạng khoa học (1.23e+04).
- `fixed`: Hiển thị số dạng dấu chấm động thông thường.

🔹 **Ví dụ:**

```cpp
double pi = 3.1415926535;
cout << scientific << pi << endl;
cout << fixed << pi << endl;
```

🔹 **Output:**

```
3.141593e+00
3.141593
```

> **Mặc định, C++ in ra 6 chữ số thập phân.**

---

### **2.3. Điều chỉnh số chữ số thập phân (`setprecision`)**

- `setprecision(n)`: Hiển thị `n` chữ số tổng thể (mặc định) hoặc `n` chữ số thập phân khi kết hợp với `fixed`.

🔹 **Ví dụ:**

```cpp
cout << setprecision(3) << 123.456789 << endl; // In ra 3 chữ số có nghĩa
cout << fixed << setprecision(3) << 123.456789 << endl; // 3 số sau dấu chấm
```

🔹 **Output:**

```
123
123.457
```

> **Lưu ý:** Khi không dùng `fixed`, `setprecision(n)` đếm cả phần nguyên và phần thập phân.

---

### **2.4. Hiển thị dấu `+` (`showpos`)**

- `showpos`: Hiển thị dấu `+` trước số dương.
- `noshowpos`: Tắt hiển thị dấu `+`.

🔹 **Ví dụ:**

```cpp
cout << showpos << 42 << " " << -42 << endl;
cout << noshowpos << 42 << " " << -42 << endl;
```

🔹 **Output:**

```
+42 -42
42 -42
```

---

### **2.5. Hiển thị số 0x và 0 trước số hệ 16 và 8 (`showbase`)**

- `showbase`: Hiển thị tiền tố `0x` (hex) và `0` (oct).
- `noshowbase`: Không hiển thị.

🔹 **Ví dụ:**

```cpp
cout << showbase << hex << 255 << endl;
cout << showbase << oct << 255 << endl;
```

🔹 **Output:**

```
0xff
0377
```

---

### **2.6. Hiển thị chữ số hex in hoa (`uppercase`)**

- `uppercase`: In chữ số hex (`A-F`) in hoa.
- `nouppercase`: In chữ số hex thường (`a-f`).

🔹 **Ví dụ:**

```cpp
cout << uppercase << hex << 255 << endl;
cout << nouppercase << hex << 255 << endl;
```

🔹 **Output:**

```
FF
ff
```

---

### **2.7. Hiển thị số `0` sau dấu chấm (`showpoint`)**

- `showpoint`: Luôn hiển thị phần thập phân (ngay cả khi là `.000`).
- `noshowpoint`: Không hiển thị nếu không cần.

🔹 **Ví dụ:**

```cpp
cout << showpoint << fixed << 10.0 << endl;
cout << noshowpoint << fixed << 10.0 << endl;
```

🔹 **Output:**

```
10.000000
10
```

---

## **3. Tổng hợp Ví dụ**

```cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    int num = 255;
    double pi = 3.1415926535;

    cout << "Width & Fill:\n";
    cout << setfill('*') << setw(10) << 42 << endl;

    cout << "\nAlignment:\n";
    cout << left << setw(10) << 42 << "Left\n";
    cout << right << setw(10) << 42 << "Right\n";

    cout << "\nNumber Formats:\n";
    cout << "Decimal: " << dec << num << endl;
    cout << "Hex (uppercase, showbase): " << showbase << uppercase << hex << num << endl;

    cout << "\nFloating Point:\n";
    cout << "Scientific: " << scientific << pi << endl;
    cout << "Fixed (3 decimal places): " << fixed << setprecision(3) << pi << endl;

    return 0;
}
```

🔹 **Output (rút gọn):**

```
Width & Fill:
********42

Alignment:
42        Left
        42Right

Number Formats:
Decimal: 255
Hex (uppercase, showbase): 0XFF

Floating Point:
Scientific: 3.141593e+00
Fixed (3 decimal places): 3.142
```

---

## **Kết luận**

- `<iomanip>` giúp định dạng đầu ra dễ đọc hơn.
- Hữu ích khi làm việc với số thực, căn chỉnh văn bản, và hiển thị số theo hệ khác.
- Kết hợp nhiều manipulator sẽ tối ưu hóa hiển thị.
