Comment (chú thích) trong C++ là phần nội dung giúp lập trình viên ghi chú, giải thích mã nguồn mà **trình biên dịch sẽ bỏ qua**. Comment không ảnh hưởng đến chương trình khi chạy.

---

## **1. Các loại Comment trong C++**

C++ hỗ trợ **hai loại comment chính**:

1. **Comment một dòng (`//`)**
2. **Comment nhiều dòng (`/* */`)**

---

## **2. Comment một dòng (`//`)**

- Dùng khi chỉ cần ghi chú trên **một dòng duy nhất**.
- Nội dung sau `//` sẽ bị trình biên dịch bỏ qua.

**Ví dụ:**

```cpp
#include <iostream>

int main() {
    std::cout << "Hello, World!"; // In ra màn hình dòng chữ "Hello, World!"
    return 0;
}
```

- Trình biên dịch chỉ thực thi dòng `std::cout << "Hello, World!";`
- Dòng `// In ra màn hình dòng chữ "Hello, World!"` sẽ bị bỏ qua.

---

## **3. Comment nhiều dòng (`/* */`)**

- Dùng khi cần ghi chú **nhiều dòng liên tiếp**.
- Nội dung nằm giữa `/*` và `*/` sẽ bị bỏ qua.

**Ví dụ:**

```cpp
#include <iostream>

int main() {
    /* Đây là một comment nhiều dòng
       giúp giải thích code bên dưới */
    std::cout << "Xin chào!"; 
    return 0;
}
```

### **Lưu ý:**

- Comment nhiều dòng **không thể lồng nhau**.  
    Ví dụ **SAI:**

```cpp
/* Đây là comment ngoài
   /* Đây là comment bên trong */ 
   */
```

- Nếu cần **lồng nhau**, nên dùng `//` hoặc đặt `/* */` cẩn thận.

Ví dụ **ĐÚNG:**

```cpp
/* Đây là comment ngoài  
   // Đây là comment bên trong  
*/
```

---

## **4. Ứng dụng của Comment**

### **4.1. Giúp hiểu rõ mã nguồn**

Comment giúp giải thích đoạn code làm gì, đặc biệt hữu ích khi làm việc nhóm hoặc đọc lại code sau thời gian dài.

Ví dụ:

```cpp
// Hàm tính tổng hai số nguyên a và b
int tong(int a, int b) {
    return a + b;
}
```

### **4.2. [[Debugging]] (Tạm vô hiệu hóa code)**

Khi kiểm tra lỗi, ta có thể **comment một đoạn code** để loại bỏ tạm thời mà không xóa.

Ví dụ:

```cpp
#include <iostream>

int main() {
    std::cout << "Dòng 1\n";
    // std::cout << "Dòng 2\n"; // Tạm tắt dòng này
    std::cout << "Dòng 3\n";
    return 0;
}
```

Kết quả chỉ in:

```
Dòng 1
Dòng 3
```

---

## **5. Comment tốt vs Comment xấu**

- **Comment tốt**: Giúp hiểu code mà không dư thừa.
- **Comment xấu**: Viết quá nhiều hoặc không cần thiết.

### **Ví dụ comment tốt:**

```cpp
// Tính tổng dãy số từ 1 đến n
int sum(int n) {
    return (n * (n + 1)) / 2; // Công thức tính tổng cấp số cộng
}
```

### **Ví dụ comment xấu:**

```cpp
int sum(int n) {
    return (n * (n + 1)) / 2; // Trả về tổng của dãy số từ 1 đến n
}
```

→ **Comment này thừa**, vì ai cũng hiểu ngay công thức trên.

---

## **6. Best Practices (Quy tắc viết Comment tốt)**

1. **Viết rõ ràng, đúng ý:** Không viết dài dòng hoặc dư thừa.
2. **Chỉ viết khi cần thiết:** Tránh viết những comment không mang lại giá trị.
3. **Dùng comment để làm rõ phần khó hiểu, thuật toán phức tạp.**
4. **Viết tiếng Anh khi làm việc nhóm quốc tế.**
5. **Không lạm dụng comment để giấu code kém chất lượng** – Hãy viết code dễ hiểu thay vì dựa vào comment để giải thích.

---

## **7. Tổng kết**

|Loại comment|Ký hiệu|Dùng khi nào?|
|---|---|---|
|**Comment một dòng**|`//`|Khi cần ghi chú ngắn trên một dòng|
|**Comment nhiều dòng**|`/* */`|Khi cần ghi chú dài, nhiều dòng|

➡ **Comment giúp code dễ hiểu, nhưng phải dùng hợp lý!**