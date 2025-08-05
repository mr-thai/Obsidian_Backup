### 1. **Mảng là gì?**

Mảng (array) là một cấu trúc dữ liệu lưu trữ một tập hợp các phần tử có cùng kiểu dữ liệu, được đặt liên tiếp nhau trong bộ nhớ. Mảng giúp truy cập các phần tử nhanh chóng bằng chỉ số (index).

Cấu trúc chung của mảng:

```cpp
kiểu_dữ_liệu tên_mảng[kích_thước];
```

Ví dụ:

```cpp
int arr[5]; // Mảng gồm 5 phần tử kiểu int
```

### 2. **Khởi tạo mảng**

Có nhiều cách để khởi tạo mảng:

#### a. **Khởi tạo không gán giá trị**

```cpp
int arr[5]; // Giá trị mặc định là rác (garbage value)
```

#### b. **Khởi tạo có gán giá trị**

```cpp
int arr[5] = {1, 2, 3, 4, 5}; // Gán giá trị cho từng phần tử
```

Nếu số lượng phần tử ít hơn kích thước:

```cpp
int arr[5] = {1, 2}; // Các phần tử còn lại sẽ là 0
```

Nếu không chỉ định kích thước:

```cpp
int arr[] = {1, 2, 3, 4, 5}; // Compiler tự xác định kích thước
```

#### c. **Duyệt mảng và nhập xuất dữ liệu**

- **Duyệt mảng bằng vòng lặp `for`**

```cpp
for (int i = 0; i < 5; i++) {
    cout << arr[i] << " ";
}
```

- **Duyệt bằng vòng lặp `range-based for` (C++11)**

```cpp
for (int x : arr) {
    cout << x << " ";
}
```

- **Nhập xuất từ bàn phím**

```cpp
for (int i = 0; i < 5; i++) {
    cin >> arr[i]; // Nhập giá trị từ bàn phím
}
```

### 3. **Các vấn đề liên quan đến mảng**

#### a. **Truy cập ngoài phạm vi mảng (Array Out of Bounds)**

```cpp
int arr[5] = {1, 2, 3, 4, 5};
cout << arr[10]; // Lỗi: Truy cập vùng nhớ ngoài mảng, kết quả không xác định
```

#### b. **Tính kích thước của mảng**

```cpp
int arr[5];
cout << "Size of array: " << sizeof(arr) / sizeof(arr[0]); // Output: 5
```

⚠️ **Chỉ hoạt động với mảng khai báo tĩnh, không áp dụng với con trỏ.**

#### c. **Mảng và con trỏ**

- Mảng thực chất là một tập hợp các địa chỉ liên tiếp. Khi dùng tên mảng, nó chính là địa chỉ phần tử đầu tiên:

```cpp
int arr[5] = {1, 2, 3, 4, 5};
cout << arr;  // Địa chỉ của phần tử đầu tiên
cout << &arr[0]; // Giống nhau
```

- Truy cập mảng bằng con trỏ:

```cpp
int *p = arr;
cout << *p;    // 1
cout << *(p+1); // 2
```

#### d. **Mảng động (Dynamic Array)**

- Dùng `new` để tạo mảng động:

```cpp
int *arr = new int[5]; // Tạo mảng động có 5 phần tử
```

- Giải phóng bộ nhớ khi không dùng nữa:

```cpp
delete[] arr;
```

### 4. **Các thao tác cơ bản trên mảng**

#### a. **Tìm phần tử lớn nhất, nhỏ nhất**

```cpp
int max_val = arr[0];
for (int i = 1; i < 5; i++) {
    if (arr[i] > max_val) max_val = arr[i];
}
cout << "Max: " << max_val;
```

#### b. **Tìm kiếm tuyến tính**

```cpp
int key = 3;
bool found = false;
for (int i = 0; i < 5; i++) {
    if (arr[i] == key) {
        found = true;
        break;
    }
}
cout << (found ? "Found" : "Not Found");
```

#### c. **Sắp xếp mảng (Bubble Sort)**

```cpp
for (int i = 0; i < 5; i++) {
    for (int j = 0; j < 4 - i; j++) {
        if (arr[j] > arr[j+1]) {
            swap(arr[j], arr[j+1]);
        }
    }
}
```

C++ cung cấp `sort()` trong thư viện `<algorithm>` để tối ưu hơn:

```cpp
#include <algorithm>
sort(arr, arr + 5);
```

### 5. **Mảng hai chiều**

- Khai báo mảng 2D:

```cpp
int arr[3][3]; // Mảng 3x3
```

- Duyệt mảng 2D:

```cpp
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 3; j++) {
        cout << arr[i][j] << " ";
    }
    cout << endl;
}
```

- Nhập mảng 2D:

```cpp
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 3; j++) {
        cin >> arr[i][j];
    }
}
```

### 6. **So sánh mảng tĩnh và mảng động**

|Đặc điểm|Mảng tĩnh|Mảng động|
|---|---|---|
|Kích thước|Cố định|Có thể thay đổi|
|Cấp phát|Biến toàn cục hoặc stack|Heap (dùng `new`)|
|Giải phóng|Tự động khi ra khỏi scope|Phải dùng `delete[]`|
|Tốc độ|Nhanh hơn (do cấp phát trên stack)|Chậm hơn (heap allocation)|

### 7. **Ưu nhược điểm của mảng**

#### ✅ **Ưu điểm**

- Truy cập phần tử nhanh (`O(1)`) nhờ index.
- Cấu trúc đơn giản, dễ sử dụng.
- Lưu trữ dữ liệu liên tiếp trong bộ nhớ.

#### ❌ **Nhược điểm**

- Kích thước cố định (với mảng tĩnh).
- Thêm/xóa phần tử chậm (`O(n)`) vì cần dời các phần tử khác.
- Lãng phí bộ nhớ nếu cấp phát thừa.

---

**💡 Kết luận:**

- Nếu cần kích thước cố định, dùng mảng tĩnh.
- Nếu cần thay đổi kích thước, dùng mảng động hoặc `vector` (`#include <vector>`).
- Hiểu rõ mảng giúp tối ưu thuật toán và sử dụng bộ nhớ hiệu quả.