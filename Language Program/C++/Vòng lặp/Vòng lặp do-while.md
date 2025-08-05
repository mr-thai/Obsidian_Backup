## **1. Định nghĩa và cú pháp**

Vòng lặp `do-while` là một cấu trúc lặp trong C++ đảm bảo khối lệnh bên trong được thực thi **ít nhất một lần**, ngay cả khi điều kiện kiểm tra ban đầu là `false`.

##### **Cú pháp:**

```cpp
do {
    // Khối lệnh được thực thi ít nhất một lần
} while (điều_kiện);
```

- Khối lệnh trong `do` sẽ chạy trước.
- Sau đó, điều kiện trong `while` được kiểm tra:
    - Nếu `true`, vòng lặp tiếp tục chạy.
    - Nếu `false`, vòng lặp kết thúc.

---

## **2. So sánh với vòng lặp `while`**

| Đặc điểm              | `do-while`                                                     | `while`                                   |
| --------------------- | -------------------------------------------------------------- | ----------------------------------------- |
| Kiểm tra điều kiện    | Sau khi chạy khối lệnh                                         | Trước khi chạy khối lệnh                  |
| Ít nhất chạy một lần? | Có                                                             | Không                                     |
| Sử dụng khi nào?      | Khi cần chạy lệnh ít nhất một lần trước khi kiểm tra điều kiện | Khi cần kiểm tra điều kiện trước khi chạy |

##### **Ví dụ minh họa:**

**Dùng `do-while`**

```cpp
#include <iostream>
using namespace std;

int main() {
    int x = 5;
    do {
        cout << "Giá trị của x: " << x << endl;
        x--;
    } while (x > 0);
    return 0;
}
```

📌 **Giá trị `x = 5`, vòng lặp chạy 5 lần rồi dừng.**

**Dùng `while`**

```cpp
int x = 5;
while (x > 0) {
    cout << "Giá trị của x: " << x << endl;
    x--;
}
```

🔹 **Kết quả tương tự, nhưng nếu `x = 0` ban đầu, `while` sẽ không chạy lần nào.**

---

## **3. Ứng dụng thực tế của `do-while`**

##### **3.1. Nhập dữ liệu hợp lệ từ người dùng**

Ngăn nhập sai bằng cách yêu cầu nhập lại nếu dữ liệu không hợp lệ.

```cpp
#include <iostream>
using namespace std;

int main() {
    int number;
    do {
        cout << "Nhập số nguyên dương: ";
        cin >> number;
    } while (number <= 0);  // Yêu cầu nhập lại nếu số không dương
    cout << "Số hợp lệ: " << number << endl;
    return 0;
}
```

📌 **Luôn yêu cầu nhập lại nếu người dùng nhập số âm hoặc 0.**

##### **3.2. Menu lặp lại cho đến khi người dùng thoát**

```cpp
#include <iostream>
using namespace std;

int main() {
    int choice;
    do {
        cout << "MENU\n";
        cout << "1. Chơi game\n";
        cout << "2. Xem điểm\n";
        cout << "3. Thoát\n";
        cout << "Chọn: ";
        cin >> choice;

        switch (choice) {
            case 1: cout << "Bắt đầu chơi game...\n"; break;
            case 2: cout << "Điểm số của bạn là 100.\n"; break;
            case 3: cout << "Thoát chương trình.\n"; break;
            default: cout << "Lựa chọn không hợp lệ! Nhập lại.\n";
        }
    } while (choice != 3);
    return 0;
}
```

📌 **Menu sẽ hiển thị lại cho đến khi người dùng chọn `3`.**

---

## **4. Lỗi thường gặp với `do-while`**

1. **Quên cập nhật điều kiện dừng → Vòng lặp vô hạn**
    
    ```cpp
    int x = 5;
    do {
        cout << x << endl;
        // Quên giảm giá trị x -> vòng lặp không bao giờ kết thúc
    } while (x > 0);
    ```
    
    ✅ **Giải pháp:** Đảm bảo điều kiện thay đổi trong mỗi lần lặp.
    
2. **Dấu chấm phẩy (`;`) bị thiếu hoặc thừa**
    
    ```cpp
    do {
        cout << "Hello";
    } while (false)  // Thiếu dấu chấm phẩy, lỗi cú pháp
    ```
    
    ✅ **Sửa:** `while (false);`  
    📌 **`do-while` bắt buộc phải có dấu `;` sau `while()`.**
    

---

## **5. Khi nào nên dùng `do-while`?**

| Trường hợp                      | Nên dùng `do-while`? | Giải thích                                    |
| ------------------------------- | -------------------- | --------------------------------------------- |
| Nhập dữ liệu hợp lệ             | ✅ Có                 | Chạy ít nhất một lần trước khi kiểm tra.      |
| Hiển thị menu lặp lại           | ✅ Có                 | Hiển thị menu ít nhất một lần trước khi chọn. |
| Duyệt mảng, danh sách           | ❌ Không              | `for` hoặc `while` phù hợp hơn.               |
| Lặp với điều kiện đã biết trước | ❌ Không              | `for` tối ưu hơn.                             |

---

#### **Tóm tắt**

- `do-while` đảm bảo **chạy ít nhất một lần**.
- **Phù hợp với các trường hợp cần thực thi trước khi kiểm tra điều kiện**.
- Cần **cẩn thận tránh lỗi vòng lặp vô hạn**.
- Không phải lúc nào cũng là lựa chọn tối ưu – cân nhắc giữa `while` và `for`.

📌 **Ghi nhớ:** Nếu muốn **luôn chạy ít nhất một lần trước khi kiểm tra điều kiện**, hãy dùng `do-while`! 🚀