## Kiểu dữ liệu Boolean (`bool`) trong C++

### 1. Giới thiệu

Trong C++, kiểu dữ liệu **Boolean** (`bool`) chỉ có hai giá trị:

- `true` (đúng, tương ứng với giá trị 1)
- `false` (sai, tương ứng với giá trị 0)

Kiểu `bool` được sử dụng để lưu trữ các giá trị logic, thường xuất hiện trong các biểu thức điều kiện (`if`, `while`, `for`), các phép so sánh và toán tử logic.

---

### 2. Khai báo và gán giá trị

#### 2.1. Khai báo biến `bool`

```cpp
#include <iostream>

int main() {
    bool isReady = true;
    bool isFinished = false;
    std::cout << "isReady: " << isReady << "\n";
    std::cout << "isFinished: " << isFinished << "\n";
    return 0;
}
```

**Kết quả:**

```
isReady: 1  
isFinished: 0  
```

Mặc định, giá trị `true` sẽ được in ra là `1`, còn `false` là `0`.

---

#### 2.2. Gán giá trị từ số nguyên

- Bất kỳ số khác `0` khi gán vào `bool` sẽ trở thành `true`.
- Chỉ số `0` mới là `false`.

```cpp
bool a = 0;    // false
bool b = 1;    // true
bool c = -5;   // true
```

---

### 3. Các phép toán với `bool`

#### 3.1. Toán tử so sánh (trả về `bool`)

| Toán tử | Ý nghĩa           | Ví dụ (`a = 5, b = 10`) | Kết quả |
| ------- | ----------------- | ----------------------- | ------- |
| ==      | So sánh bằng      | `a == b`                | `false` |
| `!=`    | So sánh khác      | `a != b`                | `true`  |
| `<`     | Nhỏ hơn           | `a < b`                 | `true`  |
| `>`     | Lớn hơn           | `a > b`                 | `false` |
| `<=`    | Nhỏ hơn hoặc bằng | `a <= b`                | `true`  |
| `>=`    | Lớn hơn hoặc bằng | `a >= b`                | `false` |

---

#### 3.2. Toán tử logic (trả về `bool`)

|Toán tử|Ý nghĩa|Ví dụ (`x = true, y = false`)|Kết quả|
|---|---|---|---|
|`&&`|AND (và)|`x && y`|`false`|
|`||`|OR (hoặc)|
|`!`|NOT (phủ định)|`!x`|`false`|

**Ví dụ:**

```cpp
#include <iostream>

int main() {
    bool a = true, b = false;

    std::cout << "a && b: " << (a && b) << "\n";
    std::cout << "a || b: " << (a || b) << "\n";
    std::cout << "!a: " << !a << "\n";

    return 0;
}
```

**Kết quả:**

```
a && b: 0  
a || b: 1  
!a: 0  
```

---

### 4. Chuyển đổi giữa `bool` và kiểu số

- `bool` có thể được chuyển thành `int`, với `true` thành `1` và `false` thành `0`.
- `int` khi ép kiểu sang `bool` sẽ tuân theo quy tắc: `0 → false`, số khác `0 → true`.

```cpp
#include <iostream>

int main() {
    int x = true + 5;  // true là 1, nên x = 1 + 5 = 6
    bool y = 10;       // true vì 10 khác 0
    bool z = 0;        // false

    std::cout << "x: " << x << "\n";  // 6
    std::cout << "y: " << y << "\n";  // 1
    std::cout << "z: " << z << "\n";  // 0

    return 0;
}
```

---

### 5. Các vấn đề liên quan

#### 5.1. Kích thước của `bool`

Kích thước `bool` không bắt buộc phải là 1 byte, nhưng trên hầu hết trình biên dịch, nó có kích thước là **1 byte**.

```cpp
#include <iostream>

int main() {
    std::cout << "Size of bool: " << sizeof(bool) << " byte(s)\n";
    return 0;
}
```

**Kết quả (thường là 1 byte):**

```
Size of bool: 1 byte(s)
```

---

#### 5.2. Nhập xuất `bool`

- `std::cin` chấp nhận `0` hoặc `1`, nhưng với `std::boolalpha`, có thể nhập/xuất `true` và `false` dạng chữ.

```cpp
#include <iostream>

int main() {
    bool flag;

    std::cout << "Nhập true hoặc false: ";
    std::cin >> std::boolalpha >> flag;
    
    std::cout << "Bạn nhập: " << std::boolalpha << flag << "\n";

    return 0;
}
```

**Ví dụ nhập:**

```
true
```

**Kết quả:**

```
Bạn nhập: true
```

---

#### 5.3. Biến `bool` trong điều kiện `if`

```cpp
#include <iostream>

int main() {
    bool isValid = false;

    if (isValid) {
        std::cout << "Hợp lệ\n";
    } else {
        std::cout << "Không hợp lệ\n";
    }

    return 0;
}
```

**Kết quả:**

```
Không hợp lệ
```

---

#### 5.4. Tối ưu bộ nhớ với `std::vector<bool>`

Trong C++, `std::vector<bool>` được tối ưu đặc biệt, sử dụng **bitset** thay vì cấp phát từng byte như các kiểu khác.

```cpp
#include <iostream>
#include <vector>

int main() {
    std::vector<bool> flags = {true, false, true};
    for (bool f : flags) {
        std::cout << f << " ";
    }
    return 0;
}
```

**Kết quả:**

```
1 0 1
```

Tuy nhiên, do tối ưu bộ nhớ, `std::vector<bool>` không hoạt động như `std::vector<int>`, khiến việc truy cập và thay đổi phần tử phức tạp hơn.

---

### 6. Tổng kết

- `bool` chỉ có hai giá trị: `true` (1) và `false` (0).
- Dùng trong biểu thức điều kiện (`if`, `while`, `for`).
- Các toán tử so sánh và logic trả về giá trị `bool`.
- Tự động chuyển đổi giữa `bool` và `int`.
- `std::vector<bool>` có cơ chế tối ưu đặc biệt.

Kiểu `bool` giúp mã nguồn dễ đọc và hiệu suất tốt hơn khi làm việc với các giá trị logic.