#### **1. Tổng Quan về Vòng lặp `while`**

Vòng lặp `while` trong C++ được sử dụng để thực thi một khối lệnh liên tục **miễn là điều kiện của nó đúng**. Nó hữu ích khi số lần lặp chưa xác định trước mà phụ thuộc vào một điều kiện.

#### **2. Cú pháp của `while`**

```cpp
while (điều_kiện) {
    // Khối lệnh được thực thi nếu điều kiện đúng (true)
}
```

- **Điều kiện** là một biểu thức logic (trả về `true` hoặc `false`).
- Nếu điều kiện **đúng**, khối lệnh bên trong được thực thi.
- Sau mỗi lần thực thi, điều kiện được kiểm tra lại.
- Nếu điều kiện **sai**, vòng lặp dừng lại.

#### **3. Ví dụ Minh Họa**

##### **Ví dụ 1: Đếm từ 1 đến 5**

```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 1; // Bắt đầu từ 1
    while (i <= 5) { // Lặp khi i ≤ 5
        cout << i << " ";
        i++; // Tăng i lên 1
    }
    return 0;
}
```

**Kết quả:**

```
1 2 3 4 5
```

- `i` khởi tạo là 1.
- Mỗi lần lặp, `i` tăng lên 1.
- Khi `i` đạt 6, điều kiện `i <= 5` sai, vòng lặp dừng.

---

#### **4. Các Vấn Đề Liên Quan**

##### **4.1. Vòng lặp vô hạn (`infinite loop`)**

Nếu không có điều kiện dừng hợp lệ, vòng lặp sẽ chạy mãi mãi.

```cpp
while (true) { 
    cout << "Vòng lặp vô hạn!\n"; 
}
```

❌ **Hệ quả:** CPU bị chiếm dụng 100%, chương trình không dừng.

🛠 **Cách khắc phục:** Đảm bảo có điều kiện dừng hoặc dùng `break`.

##### **4.2. Điều kiện sai ngay từ đầu**

Nếu điều kiện `false` ngay từ đầu, vòng lặp không chạy lần nào.

```cpp
int x = 10;
while (x < 5) { // Điều kiện sai ngay từ đầu
    cout << "Không bao giờ chạy!";
}
```

**Kết quả:** Không có dòng nào được in ra.

##### **4.3. Quên cập nhật biến điều kiện**

Nếu biến kiểm tra không thay đổi, vòng lặp sẽ vô hạn.

```cpp
int i = 1;
while (i <= 5) {
    cout << i << " "; // Không có i++ -> Vòng lặp vô hạn!
}
```

🛠 **Cách sửa:** Thêm `i++` để tránh vòng lặp vô tận.

---

#### **5. So sánh `while` với `do-while`**

|Đặc điểm|`while`|`do-while`|
|---|---|---|
|Kiểm tra điều kiện|Trước khi chạy|Sau khi chạy ít nhất 1 lần|
|Có thể không chạy lần nào?|✅ Có thể|❌ Luôn chạy ít nhất 1 lần|

##### **Ví dụ so sánh**

```cpp
// while
int x = 10;
while (x < 5) {
    cout << "Không chạy";
}

// do-while
do {
    cout << "Chạy ít nhất 1 lần";
} while (x < 5);
```

**Kết quả:** `do-while` in ra `"Chạy ít nhất 1 lần"`, còn `while` không in gì.

---

#### **6. Ứng dụng thực tế của `while`**

- **Nhập dữ liệu đến khi hợp lệ**

```cpp
int n;
cout << "Nhập số dương: ";
cin >> n;
while (n <= 0) {
    cout << "Sai! Nhập lại: ";
    cin >> n;
}
```

- **Đếm số chữ số của một số**

```cpp
int num = 12345, count = 0;
while (num > 0) {
    num /= 10;
    count++;
}
cout << "Số chữ số: " << count;
```

---

### **Tóm tắt**

✅ **Vòng lặp `while`** chạy khi điều kiện **đúng**, kiểm tra trước mỗi vòng.  
❌ **Lỗi thường gặp:** vòng lặp vô hạn, quên cập nhật biến, điều kiện sai từ đầu.  
💡 **Ứng dụng:** Nhập dữ liệu hợp lệ, xử lý số học, kiểm tra điều kiện dừng.