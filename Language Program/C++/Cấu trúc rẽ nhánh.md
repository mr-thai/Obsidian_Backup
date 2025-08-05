## **1. Cấu trúc rẽ nhánh là gì?**

Cấu trúc rẽ nhánh (conditional statements) là một trong những cấu trúc điều khiển quan trọng trong lập trình C++. Nó cho phép chương trình quyết định thực hiện những đoạn mã khác nhau dựa trên điều kiện cụ thể.

---

## **2. Các loại cấu trúc rẽ nhánh trong C++**

Trong C++, có ba loại cấu trúc rẽ nhánh chính:

1. `if`, `if-else`
2. `if-else if-else`
3. `switch-case`

---

## **3. Cấu trúc `if`, `if-else`**

Dùng để kiểm tra một điều kiện. Nếu điều kiện đúng (`true`), đoạn mã trong `if` được thực thi, nếu sai (`false`), chương trình bỏ qua nó.

### **Cú pháp:**

```cpp
if (điều_kiện) {
    // Khối lệnh được thực thi nếu điều kiện đúng
} else {
    // Khối lệnh được thực thi nếu điều kiện sai
}
```

### **Ví dụ 1: Kiểm tra số chẵn/lẻ**

```cpp
#include <iostream>
using namespace std;

int main() {
    int num;
    cout << "Nhập số: ";
    cin >> num;

    if (num % 2 == 0) {
        cout << num << " là số chẵn.\n";
    } else {
        cout << num << " là số lẻ.\n";
    }

    return 0;
}
```

📌 **Giải thích:**

- Nếu `num % 2 == 0` (số chia hết cho 2), in ra "số chẵn".
- Nếu không, in ra "số lẻ".

---

## **4. Cấu trúc `if-else if-else`**

Dùng khi có nhiều điều kiện cần kiểm tra liên tiếp.

### **Cú pháp:**

```cpp
if (điều_kiện_1) {
    // Thực thi nếu điều_kiện_1 đúng
} else if (điều_kiện_2) {
    // Thực thi nếu điều_kiện_2 đúng
} else {
    // Thực thi nếu tất cả điều kiện trên sai
}
```

### **Ví dụ 2: Xếp loại học lực**

```cpp
#include <iostream>
using namespace std;

int main() {
    float diem;
    cout << "Nhập điểm: ";
    cin >> diem;

    if (diem >= 8.5) {
        cout << "Xếp loại: Giỏi\n";
    } else if (diem >= 6.5) {
        cout << "Xếp loại: Khá\n";
    } else if (diem >= 5.0) {
        cout << "Xếp loại: Trung bình\n";
    } else {
        cout << "Xếp loại: Yếu\n";
    }

    return 0;
}
```

📌 **Giải thích:**

- Nếu điểm lớn hơn hoặc bằng `8.5`, xếp loại "Giỏi".
- Nếu điểm từ `6.5` đến `<8.5`, xếp loại "Khá".
- Nếu điểm từ `5.0` đến `<6.5`, xếp loại "Trung bình".
- Nếu nhỏ hơn `5.0`, xếp loại "Yếu".

---

## **5. Cấu trúc `switch-case`**

Dùng khi có nhiều trường hợp (`case`) cố định cần xử lý. Nó thay thế `if-else if` trong một số trường hợp để code ngắn gọn hơn.

### **Cú pháp:**

```cpp
switch (biểu_thức) {
    case giá_trị_1:
        // Lệnh thực thi nếu biểu_thức == giá_trị_1
        break;
    case giá_trị_2:
        // Lệnh thực thi nếu biểu_thức == giá_trị_2
        break;
    ...
    default:
        // Lệnh thực thi nếu không khớp với case nào
}
```

### **Ví dụ 3: Chọn ngày trong tuần**

```cpp
#include <iostream>
using namespace std;

int main() {
    int day;
    cout << "Nhập số từ 1-7 để chọn ngày trong tuần: ";
    cin >> day;

    switch (day) {
        case 1:
            cout << "Chủ Nhật\n";
            break;
        case 2:
            cout << "Thứ Hai\n";
            break;
        case 3:
            cout << "Thứ Ba\n";
            break;
        case 4:
            cout << "Thứ Tư\n";
            break;
        case 5:
            cout << "Thứ Năm\n";
            break;
        case 6:
            cout << "Thứ Sáu\n";
            break;
        case 7:
            cout << "Thứ Bảy\n";
            break;
        default:
            cout << "Số không hợp lệ!\n";
    }

    return 0;
}
```

📌 **Giải thích:**

- Nếu nhập `1`, in ra "Chủ Nhật".
- Nếu nhập `2`, in ra "Thứ Hai", ...
- Nếu nhập số ngoài `1-7`, in ra "Số không hợp lệ!".
- `break;` giúp thoát khỏi `switch` ngay khi thực hiện một `case`, tránh thực thi tiếp các `case` sau.

---

## **6. So sánh `if-else` và `switch-case`**

|Tiêu chí|`if-else`|`switch-case`|
|---|---|---|
|Số điều kiện|Bất kỳ|Giá trị cụ thể (int, char)|
|Dễ đọc|Kém hơn nếu có nhiều điều kiện|Gọn gàng nếu có nhiều giá trị cụ thể|
|Tốc độ|Chậm hơn nếu có nhiều điều kiện|Nhanh hơn với nhiều `case`|
|Kiểu dữ liệu hỗ trợ|Bất kỳ (int, float, string, bool...)|Chỉ `int`, `char`, `enum`|

📌 **Khi nào dùng?**

- Dùng `if-else` nếu điều kiện là các biểu thức phức tạp.
- Dùng `switch-case` nếu chỉ kiểm tra giá trị cụ thể (số nguyên, ký tự).

---

## **7. Toán tử ba ngôi (`?:`) - Viết rẽ nhánh gọn hơn**

Toán tử ba ngôi (`?:`) là cách viết rút gọn của `if-else`.

### **Cú pháp:**

```cpp
biểu_thức ? giá_trị_nếu_true : giá_trị_nếu_false;
```

### **Ví dụ 4: Kiểm tra số chẵn/lẻ dùng toán tử ba ngôi**

```cpp
#include <iostream>
using namespace std;

int main() {
    int num;
    cout << "Nhập số: ";
    cin >> num;

    cout << (num % 2 == 0 ? "Số chẵn\n" : "Số lẻ\n");

    return 0;
}
```

📌 **Giải thích:**

- Nếu `num % 2 == 0`, in "Số chẵn".
- Nếu không, in "Số lẻ".

---

## **8. Tổng kết**

- `if-else` dùng khi có điều kiện phức tạp.
- `if-else if-else` dùng khi có nhiều điều kiện liên tiếp.
- `switch-case` dùng khi kiểm tra nhiều giá trị cụ thể.
- Toán tử `?:` giúp viết rẽ nhánh đơn giản.
