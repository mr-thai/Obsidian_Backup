Trong C++, hằng số là các giá trị không thể thay đổi sau khi được khai báo. Có ba cách chính để định nghĩa hằng số:

1. **`const`** – Hằng số thời gian chạy (runtime)
2. **`constexpr`** – Hằng số thời gian biên dịch (compile-time)
3. **Macro (`#define`)** – Tiền xử lý (preprocessor)

---

## 1. `const` – Hằng số thời gian chạy (Runtime Constant)

### 🔹 Cách sử dụng:

- Định nghĩa một biến nhưng không thể thay đổi giá trị của nó sau khi khởi tạo.
- Có thể sử dụng cho biến toàn cục, biến cục bộ, con trỏ, tham chiếu, và cả trong tham số hàm.
- Giá trị có thể được xác định tại **runtime** (chạy chương trình).

### 🔹 Cú pháp:

```cpp
const int x = 10;  // Hằng số nguyên
const double PI = 3.14159;  // Hằng số thực
```

### 🔹 `const` với con trỏ:

```cpp
const int* ptr1;     // Con trỏ tới hằng số (giá trị không đổi, nhưng con trỏ có thể trỏ nơi khác)
int* const ptr2;     // Con trỏ hằng số (con trỏ không đổi, nhưng giá trị có thể thay đổi)
const int* const ptr3;  // Con trỏ hằng số tới hằng số (cả con trỏ và giá trị đều không đổi)
```

### 🔹 `const` trong tham số hàm:

```cpp
void printValue(const int x) {
    // x không thể bị thay đổi trong hàm này
}
```

### 🔹 Nhược điểm:

- Không thể dùng `const` để khai báo hằng số mảng tĩnh có kích thước cố định (trong C++ trước C++11).
- `const` có thể thay đổi trong một số trường hợp bằng cách sử dụng `const_cast`.

---

## 2. `constexpr` – Hằng số thời gian biên dịch (Compile-time Constant)

### 🔹 Cách sử dụng:

- Được giới thiệu từ **C++11**.
- Đảm bảo rằng giá trị của biến **được biết tại thời gian biên dịch**.
- Tốt hơn `const` vì nó giúp tối ưu hóa chương trình.

### 🔹 Cú pháp:

```cpp
constexpr int x = 10;  // Giá trị của x phải được biết tại compile-time
constexpr double PI = 3.14159;
```

### 🔹 Sự khác biệt giữa `const` và `constexpr`:

|Đặc điểm|`const`|`constexpr`|
|---|---|---|
|Thời gian|Runtime|Compile-time|
|Có thể thay đổi bằng `const_cast`|Có|Không|
|Có thể dùng cho con trỏ|Có|Có|
|Hỗ trợ hàm hằng số|Không|Có|

### 🔹 `constexpr` với hàm:

- Hàm `constexpr` có thể tính toán **tại thời gian biên dịch** nếu tham số là hằng số.

```cpp
constexpr int square(int x) {
    return x * x;
}

constexpr int value = square(5);  // Được tính tại compile-time
```

---

## 3. Macro (`#define`) – Tiền xử lý

### 🔹 Cách sử dụng:

- Được xử lý **trước khi chương trình được biên dịch**.
- Không có kiểu dữ liệu (có thể gây lỗi khó phát hiện).

### 🔹 Cú pháp:

```cpp
#define PI 3.14159
#define SQUARE(x) ((x) * (x))
```

### 🔹 Nhược điểm:

- Không có kiểm tra kiểu (`PI` có thể dùng sai kiểu).
- Dễ gây lỗi khi sử dụng macro có đối số (`SQUARE(5+1)` → `((5+1) * (5+1))` → sai kết quả).

---

## 4. So sánh tổng quan

|Tính năng|`const`|`constexpr`|`#define`|
|---|---|---|---|
|Thời gian xử lý|Runtime|Compile-time|Trước khi biên dịch|
|Kiểm tra kiểu dữ liệu|Có|Có|Không|
|Dùng được với hàm|Không|Có|Có nhưng không an toàn|
|Hỗ trợ con trỏ|Có|Có|Không|
|Dễ bị lỗi|Ít|Ít nhất|Dễ bị lỗi|

---

## 5. Khi nào sử dụng?

- **Dùng `const`** khi bạn muốn một hằng số mà không cần tối ưu hóa biên dịch.
- **Dùng `constexpr`** khi bạn muốn hằng số có thể dùng trong biểu thức compile-time (tối ưu hơn `const`).
- **Dùng `#define`** nếu chỉ đơn giản là thay thế văn bản, nhưng **nên tránh dùng macro** trừ khi thực sự cần thiết.

---

### ✅ Kết luận:

- **Ưu tiên `constexpr`** nếu giá trị có thể xác định tại compile-time.
- **Dùng `const`** nếu cần một giá trị không đổi nhưng có thể được xác định tại runtime.
- **Tránh dùng `#define`** nếu có thể dùng `const` hoặc `constexpr`.

Bạn có cần ví dụ cụ thể hơn về một trong ba cách trên không? 🚀