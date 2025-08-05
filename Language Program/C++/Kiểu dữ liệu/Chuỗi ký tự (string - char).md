# **1. Xâu ký tự trong C++ là gì?**

Trong C++, **xâu ký tự (string)** là một dãy ký tự liên tiếp nhau, có thể bao gồm chữ cái, chữ số, ký tự đặc biệt và dấu cách.

Có **2 cách chính** để làm việc với xâu ký tự trong C++:

1. **Mảng ký tự kiểu C (C-style string)** – Dùng `char[]` hoặc `char*`, kết thúc bằng ký tự `'\0'`.
2. **Lớp `std::string`** – Thuộc thư viện `<string>`, dễ dùng, có nhiều phương thức hỗ trợ.

---

# **2. Mảng ký tự kiểu C (C-style String)**

## **2.1. Khai báo và khởi tạo**

Có 3 cách để khai báo mảng ký tự:

```cpp
char str1[] = "Hello";       // Mảng ký tự tự động thêm '\0' ở cuối
char str2[10] = "World";     // Kích thước lớn hơn chuỗi thực tế
char* str3 = (char*)"C++";   // Con trỏ trỏ đến chuỗi hằng
```

📌 **Lưu ý:**

- Mảng ký tự phải có **kích thước đủ lớn** để chứa cả `'\0'`.
- Không thể gán lại giá trị mới trực tiếp (`str1 = "New"` ❌).

---

## **2.2. Nhập và xuất chuỗi**

```cpp
char name[20];
std::cin >> name;   // Chỉ nhập đến khoảng trắng
std::cout << name;
```

✔ Nhập cả dòng dùng `std::cin.getline()`:

```cpp
std::cin.getline(name, 20);
```

---

## **2.3. Các hàm thao tác với chuỗi trong `<cstring>`**

|Hàm|Công dụng|
|---|---|
|`strlen(str)`|Lấy độ dài chuỗi (không tính `'\0'`)|
|`strcpy(dest, src)`|Sao chép `src` vào `dest`|
|`strncpy(dest, src, n)`|Sao chép `n` ký tự đầu của `src` vào `dest`|
|`strcat(dest, src)`|Nối `src` vào cuối `dest`|
|`strcmp(str1, str2)`|So sánh 2 chuỗi (`0` nếu bằng nhau)|
|`strchr(str, c)`|Tìm ký tự `c` trong `str`|
|`strstr(str1, str2)`|Tìm chuỗi `str2` trong `str1`|

📌 **Ví dụ:**

```cpp
#include <iostream>
#include <cstring>

int main() {
    char str1[20] = "Hello";
    char str2[] = "World";

    strcat(str1, str2);  // str1 = "HelloWorld"
    std::cout << "Chuỗi nối: " << str1 << '\n';

    std::cout << "Độ dài: " << strlen(str1) << '\n';
}
```

⛔ **Lưu ý:** Cần đảm bảo mảng đủ lớn để tránh lỗi tràn bộ nhớ.

---

# **3. Lớp `std::string` trong C++**

Lớp `std::string` thuộc thư viện `<string>` giúp thao tác chuỗi dễ dàng hơn.

---

## **3.1. Khai báo và khởi tạo**

```cpp
#include <iostream>
#include <string>

int main() {
    std::string s1 = "Hello";
    std::string s2("World");
    std::string s3(s1);      // Sao chép từ s1
    std::string s4(5, 'A');  // "AAAAA"

    std::cout << s1 << " " << s2 << " " << s4 << '\n';
}
```

---

## **3.2. Nhập và xuất chuỗi**

```cpp
std::string name;
std::cin >> name;  // Chỉ nhập đến khoảng trắng
std::cout << name;
```

✔ Nhập cả dòng dùng `std::getline()`:

```cpp
std::getline(std::cin, name);
```

---

## **3.3. Các phương thức phổ biến**

|Phương thức|Công dụng|
|---|---|
|`s.length()`|Lấy độ dài chuỗi|
|`s.empty()`|Kiểm tra chuỗi rỗng|
|`s.append("abc")`|Nối chuỗi|
|`s.insert(pos, str)`|Chèn chuỗi vào vị trí `pos`|
|`s.erase(pos, len)`|Xóa `len` ký tự từ `pos`|
|`s.find(str)`|Tìm vị trí của `str` trong chuỗi|
|`s.substr(pos, len)`|Lấy chuỗi con từ `pos` dài `len`|
|`s.replace(pos, len, str)`|Thay thế `len` ký tự từ `pos` bằng `str`|

📌 **Ví dụ:**

```cpp
#include <iostream>
#include <string>

int main() {
    std::string s = "Hello World";

    s.insert(5, ",");     // "Hello, World"
    s.erase(6, 1);        // "Hello World"
    s.replace(6, 5, "C++"); // "Hello C++"

    std::cout << s << '\n';
}
```

---

# **4. So sánh `C-style string` và `std::string`**

|Đặc điểm|C-style String|`std::string`|
|---|---|---|
|Lưu trữ|Mảng ký tự tĩnh|Động (quản lý bộ nhớ tự động)|
|Kết thúc bằng `'\0'`|Có|Không bắt buộc|
|Dễ thao tác|Khó hơn (`<cstring>`)|Dễ hơn (`<string>`)|
|Dễ gây lỗi tràn bộ nhớ|Có|Ít hơn|

📌 **Khuyến nghị**: Dùng `std::string` nếu không có yêu cầu đặc biệt.

---

# **5. Bài toán thường gặp với chuỗi**

## **5.1. Đảo ngược chuỗi**

```cpp
#include <iostream>
#include <algorithm>
#include <string>

int main() {
    std::string s = "hello";
    std::reverse(s.begin(), s.end());
    std::cout << s; // "olleh"
}
```

---

## **5.2. Đếm số từ trong chuỗi**

```cpp
#include <iostream>
#include <sstream>
#include <string>

int main() {
    std::string s = "This is a test";
    std::stringstream ss(s);
    std::string word;
    int count = 0;

    while (ss >> word) count++;

    std::cout << "Số từ: " << count;
}
```

---

## **5.3. Kiểm tra chuỗi đối xứng (Palindrome)**

```cpp
#include <iostream>
#include <string>

bool isPalindrome(const std::string& s) {
    int l = 0, r = s.length() - 1;
    while (l < r) {
        if (s[l] != s[r]) return false;
        l++, r--;
    }
    return true;
}

int main() {
    std::string s = "madam";
    std::cout << (isPalindrome(s) ? "Đối xứng" : "Không đối xứng");
}
```

---

# **6. Tổng kết**

- **Dùng C-style string (`char[]`)** khi cần hiệu suất cao, nhưng dễ lỗi.
- **Dùng `std::string`** khi muốn code an toàn, dễ đọc.
- **Các thao tác quan trọng**: nối chuỗi, tìm kiếm, xóa, chèn, thay thế.
- **Bài toán thực tế**: đảo chuỗi, đếm từ, kiểm tra đối xứng.
