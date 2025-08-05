Toán tử bit (Bitwise Operators) là các toán tử trong C++ hoạt động trực tiếp trên từng bit của số nguyên. Chúng được sử dụng để thao tác, xử lý dữ liệu nhị phân một cách hiệu quả. Các toán tử bit thường gặp trong lập trình nhúng, tối ưu thuật toán và xử lý dữ liệu thấp cấp.

---

## 1. Các toán tử bit trong C++

| Toán tử | Tên       | Ý nghĩa                                                                                          |
| ------- | --------- | ------------------------------------------------------------------------------------------------ |
| `&`     | AND       | Giữ lại bit `1` nếu cả hai bit đều là `1`, ngược lại thành `0`                                   |
| \|      | \|        | OR                                                                                               |
| `^`     | XOR       | Giữ lại bit `1` nếu hai bit khác nhau, cùng giá trị thì thành `0`                                |
| `~`     | NOT       | Đảo bit (`0` thành `1`, `1` thành `0`)                                                           |
| `<<`    | Dịch trái | Dịch toàn bộ bit sang trái, thêm `0` vào bên phải                                                |
| `>>`    | Dịch phải | Dịch toàn bộ bit sang phải, bỏ bớt bit phải (có thể thêm `0` hoặc `1` bên trái tùy kiểu dữ liệu) |

---

## 2. Giải thích từng toán tử với ví dụ

### 2.1. Toán tử `&` (AND)

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 5, b = 3;
    cout << (a & b); // Output: 1
}
```

**Phân tích:**  
| Bit của `a = 5` (0101) |  
| Bit của `b = 3` (0011) |  
| Kết quả `(a & b)` (0001) = `1` |

➡ Giữ lại bit `1` khi cả hai đều `1`, còn lại là `0`.

---

### 2.2. Toán tử `|` (OR)

```cpp
int a = 5, b = 3;
cout << (a | b); // Output: 7
```

| Bit của `a = 5` (0101) |  
| Bit của `b = 3` (0011) |  
| Kết quả `(a | b)` (0111) = `7` |

➡ Bit nào có `1` thì giữ nguyên `1`.

---

### 2.3. Toán tử `^` (XOR)

```cpp
int a = 5, b = 3;
cout << (a ^ b); // Output: 6
```

| Bit của `a = 5` (0101) |  
| Bit của `b = 3` (0011) |  
| Kết quả `(a ^ b)` (0110) = `6` |

➡ Giữ lại `1` khi hai bit khác nhau.

---

### 2.4. Toán tử `~` (NOT)

```cpp
int a = 5;
cout << (~a); // Output: -6 (trên máy dùng số bù hai)
```

| Bit của `a = 5` (0101) |  
| Kết quả `~a` (1010) | (trong số bù hai, giá trị này là `-6`) |

➡ Đảo toàn bộ bit, chú ý cách biểu diễn số âm.

---

### 2.5. Toán tử `<<` (Dịch trái)

```cpp
int a = 5;
cout << (a << 1); // Output: 10
```

| Bit của `a = 5` (0101) |  
| Dịch trái `1` lần (1010) = `10` |

➡ Dịch toàn bộ bit sang trái, thêm `0` vào bên phải (tương đương nhân `2^n`).

---

### 2.6. Toán tử `>>` (Dịch phải)

```cpp
int a = 5;
cout << (a >> 1); // Output: 2
```

| Bit của `a = 5` (0101) |  
| Dịch phải `1` lần (0010) = `2` |

➡ Dịch toàn bộ bit sang phải, bỏ bớt bit phải (tương đương chia `2^n`).

---

## 3. Ứng dụng thực tế của toán tử bit

### **3.1. Kiểm tra số chẵn/lẻ nhanh**

Chỉ cần kiểm tra bit cuối cùng (`& 1`):

```cpp
int isOdd(int x) {
    return x & 1;
}
```

➡ Nếu bit cuối là `1` thì số lẻ, nếu `0` thì số chẵn.

---

### **3.2. Tìm số khác biệt trong mảng**

Dùng XOR để tìm số lẻ trong nhóm số chẵn:

```cpp
int findUnique(int arr[], int n) {
    int res = 0;
    for (int i = 0; i < n; i++) {
        res ^= arr[i];
    }
    return res;
}
```

➡ Vì `x ^ x = 0`, chỉ số xuất hiện lẻ lần sẽ còn lại.

---

### **3.3. Đảo bit để đổi dấu số**

```cpp
int negate(int x) {
    return ~x + 1;
}
```

➡ Công thức này dựa trên số bù hai.

---

### **3.4. Kiểm tra bit thứ `n` của số `x`**

```cpp
bool checkBit(int x, int n) {
    return (x & (1 << n)) != 0;
}
```

➡ Dịch `1` sang vị trí cần kiểm tra, rồi dùng `&`.

---

## 4. Kết luận

Toán tử bit giúp tối ưu hiệu năng khi làm việc với số nguyên và nhị phân. Hiểu rõ cách hoạt động sẽ giúp bạn viết code hiệu quả và tối ưu hơn trong nhiều bài toán lập trình! 🚀