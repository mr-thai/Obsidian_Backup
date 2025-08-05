### **1. `typedef`, `using`, và `#define` trong C++**

Ba cách này giúp định nghĩa kiểu dữ liệu hoặc tạo bí danh (alias) cho kiểu dữ liệu trong C++. Tuy nhiên, chúng có sự khác biệt về cách hoạt động và phạm vi sử dụng.

---

## **1. `typedef` - Định danh kiểu dữ liệu**

### **Công dụng**

- Dùng để tạo tên thay thế cho một kiểu dữ liệu phức tạp.
- Giúp code ngắn gọn và dễ đọc hơn.

### **Cú pháp**

```cpp
typedef kiểu_dữ_liệu tên_mới;
```

### **Ví dụ**

```cpp
typedef unsigned int uint;
uint a = 10; // uint là bí danh của unsigned int
```

### **Ứng dụng nâng cao**

Khi làm việc với con trỏ, `typedef` giúp đơn giản hóa cú pháp:

```cpp
typedef int* IntPtr;
IntPtr p1, p2; // Cả p1 và p2 đều là con trỏ int
```

> **Lưu ý:** `typedef int* IntPtr;` khác với `int* p1, p2;`, vì `p2` trong câu lệnh thứ hai là `int`, không phải con trỏ.

---

## **2. `using` - Cách thay thế `typedef` trong C++11**

### **Công dụng**

- Cung cấp cách khai báo tương tự `typedef`, nhưng rõ ràng hơn.
- Hỗ trợ định nghĩa template alias.

### **Cú pháp**

```cpp
using tên_mới = kiểu_dữ_liệu;
```

### **Ví dụ**

```cpp
using uint = unsigned int;
uint a = 10; // uint là bí danh của unsigned int
```

### **So sánh `typedef` và `using`**

- Với kiểu dữ liệu đơn giản, `typedef` và `using` giống nhau.
- `using` **mạnh hơn** khi làm việc với **template**.

Ví dụ với template:

```cpp
template <typename T>
using Ptr = T*;

Ptr<int> p; // Tương đương int* p;
```

`typedef` không thể làm điều này.

---

## **3. `#define` - Macro thay thế ký tự**

### **Công dụng**

- Dùng để thay thế văn bản trong mã nguồn trước khi biên dịch.
- Không kiểm tra kiểu dữ liệu, dễ gây lỗi nếu sử dụng không cẩn thận.

### **Cú pháp**

```cpp
#define tên_mới giá_trị
```

### **Ví dụ**

```cpp
#define PI 3.14159
#define SQUARE(x) ((x) * (x))

double area = PI * SQUARE(5);
```

> **Lưu ý:** `#define` chỉ thay thế ký tự, không có kiểm tra kiểu dữ liệu.

---

## **4. So sánh `typedef`, `using`, và `#define`**

|Đặc điểm|`typedef`|`using`|`#define`|
|---|---|---|---|
|Kiểm tra kiểu|✅ Có|✅ Có|❌ Không|
|Hỗ trợ template|❌ Không|✅ Có|❌ Không|
|Phạm vi ảnh hưởng|Cục bộ|Cục bộ|Toàn bộ file (trước khi biên dịch)|
|Dễ gây lỗi|Ít|Ít|Nhiều|

### **Nên dùng cái nào?**

- Dùng **`using`** thay vì `typedef` trong C++11 trở lên.
- Chỉ dùng **`#define`** cho hằng số hoặc macro đơn giản, tránh dùng cho kiểu dữ liệu.

---

## **5. Khi nào nên sử dụng?**

|Trường hợp|Cách dùng|
|---|---|
|Định danh kiểu đơn giản|`using` hoặc `typedef`|
|Định danh kiểu dùng template|`using`|
|Định nghĩa hằng số|`constexpr` hoặc `#define`|
|Định nghĩa macro|`#define` (nếu cần thiết)|

Ví dụ thay `#define` bằng `constexpr`:

```cpp
constexpr double PI = 3.14159;
```

> `constexpr` an toàn hơn `#define` vì có kiểm tra kiểu dữ liệu.

---

## **Tóm tắt**

- **`typedef`**: Cũ hơn, giúp định nghĩa bí danh kiểu.
- **`using`**: Thay thế `typedef` trong C++11, mạnh hơn với template.
- **`#define`**: Thay thế văn bản trước khi biên dịch, không kiểm tra kiểu.

**=> Nên dùng `using` thay cho `typedef` và `constexpr` thay cho `#define` trong C++ hiện đại.**