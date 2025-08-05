### 1. **Khái niệm**

Vòng lặp `for` trong C++ là một cấu trúc lặp được sử dụng khi biết trước số lần lặp. Nó có cú pháp cố định và giúp viết mã ngắn gọn, dễ đọc hơn so với `while` hoặc `do-while` khi làm việc với số vòng lặp xác định.

### 2. **Cấu trúc tổng quát**

```cpp
for (khởi_tạo; điều_kiện; cập_nhật) {
    // Khối lệnh được thực thi mỗi lần lặp
}
```

- **Khởi tạo**: Chạy một lần trước khi vòng lặp bắt đầu. Thường dùng để khai báo và gán giá trị ban đầu cho biến lặp.
- **Điều kiện**: Kiểm tra trước mỗi lần lặp. Nếu điều kiện đúng (`true`), khối lệnh trong vòng lặp được thực thi; nếu sai (`false`), vòng lặp kết thúc.
- **Cập nhật**: Thực hiện sau mỗi lần lặp, thường dùng để thay đổi giá trị biến lặp.

### 3. **Ví dụ cơ bản**

In các số từ 1 đến 5:

```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 1; i <= 5; i++) {
        cout << i << " ";
    }
    return 0;
}
```

**Kết quả:**

```
1 2 3 4 5
```

**Diễn giải:**

1. `i` khởi tạo bằng 1.
2. Kiểm tra `i <= 5` (đúng) → thực thi `cout`.
3. `i++` tăng lên 2, kiểm tra lại điều kiện, tiếp tục vòng lặp.
4. Khi `i` trở thành 6, `i <= 5` sai → vòng lặp kết thúc.

---

### 4. **Biến thể của vòng lặp `for`**

#### a) **Bỏ qua phần khởi tạo**

Nếu biến đã được khai báo trước đó:

```cpp
int i = 1;
for (; i <= 5; i++) {
    cout << i << " ";
}
```

#### b) **Bỏ qua phần cập nhật**

Nếu cập nhật bên trong thân vòng lặp:

```cpp
for (int i = 1; i <= 5;) {
    cout << i << " ";
    i++; // Cập nhật ở trong vòng lặp
}
```

#### c) **Vòng lặp vô hạn**

Không có điều kiện dừng → vòng lặp chạy mãi mãi:

```cpp
for (;;) {
    cout << "Vòng lặp vô hạn! ";
}
```

(Có thể dừng bằng `break` hoặc `return`.)

#### d) **Dùng nhiều biểu thức trong `for`**

Có thể khai báo và cập nhật nhiều biến:

```cpp
for (int i = 0, j = 10; i < j; i++, j--) {
    cout << "i: " << i << ", j: " << j << endl;
}
```

**Kết quả:**

```
i: 0, j: 10
i: 1, j: 9
...
i: 4, j: 6
```

---

### 5. **Điều khiển vòng lặp**

#### a) **Dùng `break` để thoát vòng lặp**

Dừng vòng lặp ngay lập tức:

```cpp
for (int i = 1; i <= 10; i++) {
    if (i == 5) break; // Dừng vòng lặp khi i = 5
    cout << i << " ";
}
```

**Kết quả:**

```
1 2 3 4
```

#### b) **Dùng `continue` để bỏ qua lần lặp hiện tại**

Bỏ qua khi `i` là số chẵn:

```cpp
for (int i = 1; i <= 5; i++) {
    if (i % 2 == 0) continue;
    cout << i << " ";
}
```

**Kết quả:**

```
1 3 5
```

#### c) **Dùng `goto` để nhảy ra khỏi vòng lặp**

Ít dùng, nhưng có thể thực hiện như sau:

```cpp
for (int i = 1; i <= 10; i++) {
    if (i == 5) goto end_loop;
    cout << i << " ";
}
end_loop:
cout << "Kết thúc vòng lặp";
```

---

### 6. **Ứng dụng thực tế**

#### a) **Tính tổng từ 1 đến N**

```cpp
int sum = 0;
for (int i = 1; i <= 100; i++) {
    sum += i;
}
cout << "Tổng từ 1 đến 100: " << sum;
```

#### b) **Duyệt mảng bằng vòng lặp `for`**

```cpp
int arr[] = {10, 20, 30, 40, 50};
int n = sizeof(arr) / sizeof(arr[0]);

for (int i = 0; i < n; i++) {
    cout << arr[i] << " ";
}
```

**Kết quả:**

```
10 20 30 40 50
```

#### c) **Vòng lặp `for-each` (C++11 trở lên)**

Duyệt mảng dễ dàng hơn:

```cpp
for (int x : arr) {
    cout << x << " ";
}
```

---

### 7. **Lưu ý quan trọng**

- **Chỉ dùng `for` khi biết trước số lần lặp.** Nếu số lần lặp không xác định, nên dùng `while`.
- **Cẩn thận vòng lặp vô hạn**, đặc biệt khi điều kiện cập nhật không chính xác.
- **Tối ưu hiệu suất**, tránh các phép toán nặng trong điều kiện vòng lặp. Ví dụ, thay vì:
    
    ```cpp
    for (int i = 0; i < arr.size(); i++) // Không tối ưu
    ```
    
    Nên dùng:
    
    ```cpp
    int n = arr.size();
    for (int i = 0; i < n; i++) // Tốt hơn
    ```
    
    để tránh gọi `.size()` nhiều lần.

---

### 8. **So sánh `for` với `while` và `do-while`**

|Đặc điểm|`for`|`while`|`do-while`|
|---|---|---|---|
|Khi nào dùng|Khi biết trước số lần lặp|Khi chưa biết số lần lặp|Khi cần chạy ít nhất 1 lần|
|Kiểm tra điều kiện|Trước mỗi lần lặp|Trước mỗi lần lặp|Sau mỗi lần lặp|
|Tính rõ ràng|Cao|Trung bình|Thấp|

---

### 9. **Tổng kết**

- `for` là vòng lặp tối ưu khi biết trước số lần lặp.
- Cú pháp gồm 3 phần: **khởi tạo, điều kiện, cập nhật**.
- Có thể dùng `break`, `continue` để kiểm soát vòng lặp.
- `for-each` giúp duyệt mảng dễ dàng hơn.
- Tránh vòng lặp vô hạn hoặc cập nhật sai điều kiện.

