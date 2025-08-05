## Toán tử logic (Logical Operators) trong C++

Toán tử logic là các toán tử được sử dụng để thực hiện các phép toán logic, thường dùng trong các biểu thức điều kiện (`if`, `while`, `for`, ...) để kiểm tra tính đúng sai (`true` hoặc `false`).

C++ cung cấp 3 toán tử logic chính:

- **AND (`&&`)** – Chỉ đúng khi cả hai vế đều đúng.
- **OR (`||`)** – Đúng nếu ít nhất một vế đúng.
- **NOT (`!`)** – Đảo ngược giá trị logic của một biểu thức.

---

### 1. **Toán tử AND (`&&`)**

Toán tử `&&` trả về `true` nếu **cả hai toán hạng** đều `true`. Nếu **bất kỳ toán hạng nào là `false`**, nó sẽ trả về `false`.

#### **Bảng chân lý (Truth Table) của `&&`:**

|A (vế trái)|B (vế phải)|A && B (Kết quả)|
|---|---|---|
|`false`|`false`|`false`|
|`false`|`true`|`false`|
|`true`|`false`|`false`|
|`true`|`true`|`true`|

#### **Ví dụ C++:**

```cpp
#include <iostream>

int main() {
    bool a = true, b = false;
    std::cout << (a && b) << std::endl;  // Kết quả: 0 (false)

    bool x = true, y = true;
    std::cout << (x && y) << std::endl;  // Kết quả: 1 (true)

    return 0;
}
```

⮞ **Giải thích:**

- `true && false` → `false`
- `true && true` → `true`

---

### 2. **Toán tử OR (`||`)**

Toán tử `||` trả về `true` nếu **ít nhất một toán hạng** là `true`. Nếu **cả hai đều `false`**, nó sẽ trả về `false`.

#### **Bảng chân lý (Truth Table) của `||`:**


| A (vế trái) | B (vế phải) | A `\|\|` B (Kết quả) |
| ----------- | ----------- | -------------------- |
| `false`     | `false`     | `false`              |
| `false`     | `true`      | `true`               |
| `true`      | `false`     | `true`               |
| `true`      | `true`      | `true`               |

#### **Ví dụ C++:**

```cpp
#include <iostream>

int main() {
    bool a = false, b = true;
    std::cout << (a || b) << std::endl;  // Kết quả: 1 (true)

    bool x = false, y = false;
    std::cout << (x || y) << std::endl;  // Kết quả: 0 (false)

    return 0;
}
```

⮞ **Giải thích:**

- `false || true` → `true`
- `false || false` → `false`

---

### 3. **Toán tử NOT (`!`)**

Toán tử `!` đảo ngược giá trị logic của một biểu thức.

- Nếu toán hạng là `true`, kết quả sẽ là `false`.
- Nếu toán hạng là `false`, kết quả sẽ là `true`.

#### **Bảng chân lý (Truth Table) của `!`:**

|A (Toán hạng)|!A (Kết quả)|
|---|---|
|`false`|`true`|
|`true`|`false`|

#### **Ví dụ C++:**

```cpp
#include <iostream>

int main() {
    bool a = true;
    std::cout << !a << std::endl;  // Kết quả: 0 (false)

    bool b = false;
    std::cout << !b << std::endl;  // Kết quả: 1 (true)

    return 0;
}
```

⮞ **Giải thích:**

- `!true` → `false`
- `!false` → `true`

---

## **Tính chất quan trọng**

### 1. **Tính chất rút gọn (Short-circuit evaluation)**

C++ sử dụng **tính chất rút gọn** trong đánh giá biểu thức logic:

- Với `&&`: Nếu vế trái là `false`, vế phải **sẽ không được kiểm tra** (vì kết quả chắc chắn là `false`).
- Với `||`: Nếu vế trái là `true`, vế phải **sẽ không được kiểm tra** (vì kết quả chắc chắn là `true`).

#### **Ví dụ:**

```cpp
#include <iostream>

bool check() {
    std::cout << "Đã kiểm tra!" << std::endl;
    return true;
}

int main() {
    bool a = false;
    
    // "check()" sẽ không được gọi vì "a && check()" bị rút gọn (a đã là false)
    if (a && check()) {
        std::cout << "Điều kiện đúng!" << std::endl;
    }

    return 0;
}
```

⮞ **Kết quả chỉ in ra: (không có "Đã kiểm tra!")**

⮞ **Giải thích:** `a && check()` → `false && check()` → Không cần kiểm tra `check()`, chương trình bỏ qua.

---

### 2. **Kết hợp các toán tử logic**

Có thể kết hợp `&&`, `||` và `!` để tạo điều kiện phức tạp hơn.

#### **Ví dụ:**

```cpp
#include <iostream>

int main() {
    int x = 10, y = 20;
    
    if ((x > 5 && y < 30) || !(x == 10)) {
        std::cout << "Điều kiện đúng!" << std::endl;
    }

    return 0;
}
```

⮞ **Giải thích:**

- `(x > 5 && y < 30)` → `(true && true)` → `true`
- `!(x == 10)` → `!true` → `false`
- `true || false` → `true` → In ra `"Điều kiện đúng!"`

---

## **Ứng dụng thực tế**

Toán tử logic được sử dụng rộng rãi trong lập trình, đặc biệt là trong:

1. **Điều kiện (`if`, `while`, `for`)**
    
    ```cpp
    if (x > 0 && y > 0) {
        std::cout << "Cả hai số đều dương!" << std::endl;
    }
    ```
    
2. **Kiểm tra hợp lệ của dữ liệu**
    
    ```cpp
    if (age >= 18 && age <= 65) {
        std::cout << "Bạn đủ điều kiện làm việc!" << std::endl;
    }
    ```
    
3. **Tạo logic phức tạp cho game & AI**
    
    ```cpp
    if (enemyDetected && (playerHealth > 0 || hasShield)) {
        attack();
    }
    ```
    

---

## **Kết luận**

- `&&`: Chỉ đúng khi **cả hai vế đều đúng**.
- `||`: Đúng nếu **ít nhất một vế đúng**.
- `!`: Đảo ngược giá trị logic.
- C++ tối ưu đánh giá điều kiện bằng **short-circuit** (tính chất rút gọn).
- Toán tử logic rất quan trọng trong lập trình, dùng trong kiểm tra điều kiện, xác thực dữ liệu, game, AI,...
