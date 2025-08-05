## **Toán tử quan hệ trong C++ (Relational Operators)**

Toán tử quan hệ trong C++ được sử dụng để so sánh hai giá trị. Kết quả của một phép so sánh luôn là **true (1) hoặc false (0)**. Những toán tử này thường được dùng trong **câu lệnh điều kiện (if, while, for, ...)**.

### **Danh sách toán tử quan hệ**

| Toán tử | Ý nghĩa           | Ví dụ    | Kết quả    |
| ------- | ----------------- | -------- | ---------- |
| ` ==    | So sánh bằng      | `5 == 5` | `true (1)` |
| `!=`    | So sánh khác      | `5 != 3` | `true (1)` |
| `>`     | Lớn hơn           | `5 > 3`  | `true (1)` |
| `<`     | Nhỏ hơn           | `2 < 5`  | `true (1)` |
| `>=`    | Lớn hơn hoặc bằng | `5 >= 5` | `true (1)` |
| `<=`    | Nhỏ hơn hoặc bằng | `3 <= 5` | `true (1)` |

---

## **Cách hoạt động của toán tử quan hệ**

### **1. So sánh bằng ( == ) và khác (`!=`)**

Hai toán tử này kiểm tra xem hai giá trị có **bằng nhau** hoặc **khác nhau** hay không.

🔹 **Ví dụ**

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 10, b = 20;
    
    cout << (a == b) << endl; // Kết quả: 0 (false)
    cout << (a != b) << endl; // Kết quả: 1 (true)
    
    return 0;
}
```

📌 **Lưu ý:** Khi so sánh số thực (`float`, `double`), tránh sử dụng ` == ` vì số thực có thể bị sai số.

---

### **2. So sánh lớn hơn (`>`) và nhỏ hơn (`<`)**

Hai toán tử này kiểm tra mối quan hệ lớn hơn và nhỏ hơn.

🔹 **Ví dụ**

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 15, b = 10;
    
    cout << (a > b) << endl;  // Kết quả: 1 (true)
    cout << (a < b) << endl;  // Kết quả: 0 (false)
    
    return 0;
}
```

---

### **3. So sánh lớn hơn hoặc bằng (`>=`) và nhỏ hơn hoặc bằng (`<=`)**

Hai toán tử này kiểm tra xem một giá trị có **lớn hơn hoặc bằng** hay **nhỏ hơn hoặc bằng** một giá trị khác.

🔹 **Ví dụ**

```cpp
#include <iostream>
using namespace std;

int main() {
    int x = 10, y = 10;

    cout << (x >= y) << endl;  // Kết quả: 1 (true)
    cout << (x <= y) << endl;  // Kết quả: 1 (true)

    return 0;
}
```

---

## **Ứng dụng của toán tử quan hệ**

Toán tử quan hệ được dùng chủ yếu trong:

- **Câu lệnh điều kiện (`if`, `else`)**
- **Vòng lặp (`while`, `for`)**
- **Cấu trúc điều khiển chương trình**

🔹 **Ví dụ 1: Dùng trong câu lệnh điều kiện**

```cpp
#include <iostream>
using namespace std;

int main() {
    int age;
    cout << "Nhap tuoi: ";
    cin >> age;

    if (age >= 18) {
        cout << "Ban da du tuoi de lai xe!" << endl;
    } else {
        cout << "Ban chua du tuoi de lai xe!" << endl;
    }

    return 0;
}
```

📌 **Giải thích:**

- Nếu `age >= 18`, in ra `"Ban da du tuoi de lai xe!"`
- Nếu `age < 18`, in ra `"Ban chua du tuoi de lai xe!"`

---

🔹 **Ví dụ 2: Dùng trong vòng lặp**

```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 1;
    
    while (i <= 5) {  // Kiểm tra điều kiện i <= 5
        cout << "So thu tu: " << i << endl;
        i++;
    }

    return 0;
}
```

📌 **Giải thích:**

- Chương trình chạy từ `i = 1` đến `i = 5`
- Khi `i > 5`, vòng lặp kết thúc.

---

## **Lưu ý khi sử dụng toán tử quan hệ**

1. **Không nhầm lẫn ` = ` và  == **
    
    - ` = ` là toán tử gán
    - == là toán tử so sánh
    - ❌ **Sai:** `if (x = 5) { ... }` (Gán `x = 5` thay vì so sánh)
    - ✅ **Đúng:** `if (x == 5) { ... }` (So sánh `x` có bằng `5` không)
2. **Khi so sánh số thực (`float`, `double`), không nên dùng ` == `**
    
    - Do sai số khi lưu trữ số thực, `0.1 + 0.2` có thể không chính xác bằng `0.3`
    - Giải pháp: So sánh với **một khoảng sai số nhỏ (epsilon)**
    
    🔹 **Ví dụ**
    
    ```cpp
    #include <iostream>
    #include <cmath>  // Thư viện toán học
    using namespace std;
    
    int main() {
        double a = 0.1 + 0.2;
        double b = 0.3;
    
        if (fabs(a - b) < 1e-9) {  // fabs: giá trị tuyệt đối, 1e-9 là khoảng sai số
            cout << "Bang nhau!" << endl;
        } else {
            cout << "Khong bang nhau!" << endl;
        }
    
        return 0;
    }
    ```
    

---

## **Tóm tắt**

| Toán tử | Ý nghĩa           |
| ------- | ----------------- |
|  ==     | So sánh bằng      |
| `!=`    | So sánh khác      |
| `>`     | Lớn hơn           |
| `<`     | Nhỏ hơn           |
| `>=`    | Lớn hơn hoặc bằng |
| `<=`    | Nhỏ hơn hoặc bằng |

✅ **Ứng dụng chính:**

- Dùng trong **câu lệnh điều kiện** (`if`, `else`)
- Dùng trong **vòng lặp** (`while`, `for`)
- Kiểm tra giá trị và điều kiện trong chương trình

---

📌 **Kết luận**

- Toán tử quan hệ giúp kiểm tra điều kiện và đưa ra quyết định trong chương trình.
- Luôn cẩn thận khi dùng ` == ` với số thực.
- Tránh nhầm ` = ` (gán) với ` == ` (so sánh).
