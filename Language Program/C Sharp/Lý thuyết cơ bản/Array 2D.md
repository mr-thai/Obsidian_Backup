## 1. Giới Thiệu Về Mảng Hai Chiều

### 1.1. Định Nghĩa

Mảng hai chiều (two-dimensional array) là một tập hợp dữ liệu có cùng kiểu, được lưu trữ theo dạng bảng gồm nhiều hàng và nhiều cột. Nó thường được sử dụng trong các bài toán liên quan đến ma trận, bảng dữ liệu hoặc các cấu trúc phức tạp hơn.

### 1.2. Cách Khai Báo Mảng Hai Chiều

```csharp
int[,] array = new int[3, 4]; // Mảng có 3 hàng, 4 cột
```

Hoặc khai báo và khởi tạo giá trị:

```csharp
int[,] array = {
    {1, 2, 3, 4},
    {5, 6, 7, 8},
    {9, 10, 11, 12}
};
```

### 1.3. Truy Cập Phần Tử

Truy cập và thay đổi phần tử trong mảng:

```csharp
int value = array[1, 2]; // Lấy phần tử tại hàng 1, cột 2
array[0, 0] = 99; // Gán giá trị mới
```

### 1.4. Duyệt Mảng Hai Chiều

Duyệt bằng vòng lặp `for`:

```csharp
for (int i = 0; i < array.GetLength(0); i++) {
    for (int j = 0; j < array.GetLength(1); j++) {
        Console.Write(array[i, j] + " ");
    }
    Console.WriteLine();
}
```

Duyệt bằng vòng lặp `foreach`:

```csharp
foreach (int value in array) {
    Console.Write(value + " ");
}
```

## 2. Các Hàm Hỗ Trợ Cho Mảng Hai Chiều

### **2.1. Lấy Kích Thước Mảng**

|Hàm|Tác Dụng|Giới Thiệu Rõ Hơn|Cách Hoạt Động|Ví Dụ|
|---|---|---|---|---|
|`GetLength(dimension)`|Lấy số hàng hoặc số cột của mảng|`dimension = 0` là số hàng, `dimension = 1` là số cột|Trả về số phần tử theo chiều `dimension`|`int rows = array.GetLength(0); int cols = array.GetLength(1);`|

### Lưu ý:

- `array.Length` chỉ trả về tổng số phần tử, không phân biệt hàng/cột.

### **2.2. Tạo Mảng Mới & Sao Chép Mảng**

|Hàm|Tác Dụng|Giới Thiệu Rõ Hơn|Cách Hoạt Động|Ví Dụ|
|---|---|---|---|---|
|`Array.Copy(src, dest, length)`|Sao chép mảng|Chỉ hoạt động đúng với mảng một chiều|Không áp dụng trực tiếp cho mảng hai chiều|`Array.Copy(array1D, array2D, length);`|
|`Clone()`|Tạo bản sao của mảng|Chỉ sao chép tham chiếu, không sao chép dữ liệu thực|`array.Clone()` trả về object, cần ép kiểu|`int[,] newArray = (int[,])array.Clone();`|

### Lưu ý:

- Nếu muốn sao chép từng phần tử của mảng hai chiều, cần dùng vòng lặp thay vì `Array.Copy()`.

### **2.3. Chuyển Đổi Mảng Hai Chiều Thành Mảng Một Chiều**

|Hàm|Tác Dụng|Giới Thiệu Rõ Hơn|Cách Hoạt Động|Ví Dụ|
|---|---|---|---|---|
|`Cast<int>().ToArray()`|Chuyển đổi thành mảng một chiều|Dùng với `LINQ`|Trả về một mảng một chiều chứa tất cả phần tử|`int[] flatArray = array.Cast<int>().ToArray();`|

### Lưu ý:

- Cần thêm `using System.Linq;` khi dùng `Cast<int>().ToArray()`.

### **2.4. Duyệt Mảng Hai Chiều Với `foreach`**

|Hàm|Tác Dụng|Giới Thiệu Rõ Hơn|Cách Hoạt Động|Ví Dụ|
|---|---|---|---|---|
|`foreach`|Duyệt từng phần tử|Không thể truy cập trực tiếp chỉ mục|Duyệt tuần tự từng phần tử|`foreach (int item in array) { Console.Write(item + " "); }`|

### Lưu ý:

- Không dùng được `foreach` nếu cần biết chỉ mục hàng/cột của phần tử.

## 3. Một Số Lưu Ý Khi Sử Dụng Mảng Hai Chiều

- **Không thể thay đổi kích thước mảng hai chiều** sau khi khai báo.
- **Sử dụng `Jagged Array` (mảng mảng) khi cần kích thước linh hoạt**.
- **Cẩn thận khi sao chép mảng**, `Clone()` chỉ sao chép tham chiếu.

## 4. Ví Dụ Cụ Thể

### 4.1. Nhập & Xuất Mảng Hai Chiều

```csharp
int[,] matrix = new int[2, 3];
for (int i = 0; i < 2; i++) {
    for (int j = 0; j < 3; j++) {
        Console.Write($"Nhập phần tử [{i},{j}]: ");
        matrix[i, j] = int.Parse(Console.ReadLine());
    }
}
```

### 4.2. Tính Tổng Các Phần Tử Trong Mảng

```csharp
int sum = 0;
for (int i = 0; i < matrix.GetLength(0); i++) {
    for (int j = 0; j < matrix.GetLength(1); j++) {
        sum += matrix[i, j];
    }
}
Console.WriteLine($"Tổng các phần tử: {sum}");
```

### 4.3. Tìm Giá Trị Lớn Nhất Trong Mảng

```csharp
int max = matrix[0, 0];
for (int i = 0; i < matrix.GetLength(0); i++) {
    for (int j = 0; j < matrix.GetLength(1); j++) {
        if (matrix[i, j] > max) {
            max = matrix[i, j];
        }
    }
}
Console.WriteLine($"Giá trị lớn nhất: {max}");
```

## 5. Kết Luận

Mảng hai chiều là một phần quan trọng của C#, giúp lưu trữ dữ liệu dạng bảng. Việc hiểu cách khai báo, duyệt mảng và sử dụng các hàm hỗ trợ giúp lập trình hiệu quả hơn. Ngoài ra, việc kết hợp với các thư viện như `LINQ` giúp việc xử lý dữ liệu trở nên dễ dàng hơn.