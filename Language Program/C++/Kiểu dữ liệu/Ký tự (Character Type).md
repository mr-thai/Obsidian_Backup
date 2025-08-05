### **Kiểu dữ liệu Ký tự trong C++ (Character Type)**

#### **1. Tổng quan về kiểu ký tự**

Trong C++, kiểu dữ liệu ký tự (`char`) được sử dụng để lưu trữ một ký tự đơn lẻ như `'A'`, `'b'`, `'1'`, `'@'`,… Kiểu `char` thực chất là một số nguyên có kích thước **1 byte (8 bit)**, thường được biểu diễn dưới dạng **mã ASCII hoặc [[Unicode]]**.

#### **2. Các kiểu dữ liệu ký tự trong C++**

C++ hỗ trợ nhiều kiểu dữ liệu ký tự để phù hợp với các tiêu chuẩn mã hóa khác nhau:

|Kiểu dữ liệu|Kích thước|Mô tả|
|---|---|---|
|`char`|1 byte|Ký tự ASCII hoặc một phần của Unicode (UTF-8).|
|`signed char`|1 byte|Có thể lưu giá trị từ -128 đến 127 (dùng như số nguyên).|
|`unsigned char`|1 byte|Lưu giá trị từ 0 đến 255 (dùng như số nguyên).|
|`wchar_t`|2 hoặc 4 byte|Dùng để lưu ký tự rộng (wide character) trong Unicode.|
|`char16_t`|2 byte|Hỗ trợ Unicode UTF-16.|
|`char32_t`|4 byte|Hỗ trợ Unicode UTF-32.|

#### **3. Biểu diễn ký tự**

- Ký tự được đặt trong dấu nháy đơn: `'A'`, `'9'`, `'#'`.
- Sử dụng mã ASCII hoặc Unicode:
    
    ```cpp
    char c1 = 'A';     // Ký tự A
    char c2 = 65;      // Cũng là ký tự A (ASCII 65)
    wchar_t c3 = L'✓'; // Ký tự Unicode
    ```
    

#### **4. Hàm và toán tử xử lý ký tự**

C++ cung cấp một số hàm và toán tử giúp thao tác với kiểu ký tự.

##### **4.1 Toán tử làm việc với `char`**

| Toán tử            | Ý nghĩa            | Ví dụ                         |
| ------------------ | ------------------ | ----------------------------- |
| `+`                | Cộng giá trị ASCII | `'A' + 1` → `66` (ký tự 'B'). |
| `-`                | Trừ giá trị ASCII  | `'D' - 'A'` → `3`.            |
| ==, `!=`, `<`, `>` | So sánh ASCII      | `'A' < 'B'` → `true`.         |

##### **4.2 Các hàm trong thư viện `<cctype>`**

Thư viện `<cctype>` cung cấp các hàm xử lý ký tự chuẩn:

|Hàm|Mô tả|Ví dụ|
|---|---|---|
|`isalpha(c)`|Kiểm tra có phải chữ cái không|`isalpha('A')` → `true`|
|`isdigit(c)`|Kiểm tra có phải số không|`isdigit('5')` → `true`|
|`isspace(c)`|Kiểm tra có phải khoảng trắng không|`isspace(' ')` → `true`|
|`islower(c)`|Kiểm tra có phải chữ thường không|`islower('a')` → `true`|
|`isupper(c)`|Kiểm tra có phải chữ hoa không|`isupper('A')` → `true`|
|`tolower(c)`|Chuyển thành chữ thường|`tolower('A')` → `'a'`|
|`toupper(c)`|Chuyển thành chữ hoa|`toupper('a')` → `'A'`|

**Ví dụ:**

```cpp
#include <iostream>
#include <cctype>

int main() {
    char c = 'A';
    if (isalpha(c)) {
        std::cout << c << " là chữ cái.\n";
    }
    std::cout << "Chữ thường của " << c << " là " << (char)tolower(c) << "\n";
    return 0;
}
```

💡 **Ghi chú**: Các hàm này chỉ hoạt động với ký tự ASCII, không hỗ trợ Unicode mở rộng.

#### **5. Chuỗi ký tự và kiểu `char`**

Mặc dù `char` chỉ lưu trữ một ký tự, nhưng có thể dùng mảng `char` hoặc `std::string` để làm việc với nhiều ký tự:

- **Mảng `char`** (chuỗi C-style):
    
    ```cpp
    char str[] = "Hello"; // Kết thúc bằng ký tự '\0'
    ```
    
- **`std::string` (C++ STL)**:
    
    ```cpp
    #include <iostream>
    #include <string>
    
    int main() {
        std::string s = "Hello";
        s += " World!";
        std::cout << s << std::endl;
        return 0;
    }
    ```
    
    ✅ `std::string` dễ sử dụng hơn mảng `char` và hỗ trợ Unicode tốt hơn.

#### **6. Các vấn đề cần lưu ý**

1. **Dữ liệu kiểu `char` thực chất là số nguyên**, nên có thể xảy ra lỗi nếu không xử lý cẩn thận.
    
    ```cpp
    char c = 255;  // Nếu dùng signed char, giá trị này có thể bị âm
    ```
    
2. **Ký tự rỗng (`'\0'`)** quan trọng trong chuỗi C-style:
    
    ```cpp
    char str[5] = {'H', 'i', '\0'}; // Nếu thiếu '\0', có thể gây lỗi
    ```
    
3. **Unicode và đa nền tảng**: C++ không hỗ trợ Unicode hoàn toàn nếu chỉ dùng `char`, nên cần `wchar_t`, `char16_t`, hoặc `char32_t` khi làm việc với ký tự ngoài ASCII.

---

### **Tóm tắt**

- `char` là kiểu số nguyên 1 byte, lưu mã ASCII của ký tự.
- Có các biến thể như `unsigned char`, `wchar_t`, `char16_t`, `char32_t`.
- Toán tử có thể thực hiện phép toán trên `char` dựa vào giá trị ASCII.
- `<cctype>` cung cấp nhiều hàm xử lý ký tự hữu ích.
- Làm việc với nhiều ký tự cần dùng mảng `char[]` hoặc `std::string`.
- Cần chú ý đến vấn đề Unicode, kết thúc chuỗi (`'\0'`), và giá trị âm trong `char`.
