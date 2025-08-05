## 1. Giới thiệu về mảng một chiều

### 1.1. Định nghĩa

Mảng một chiều là một tập hợp các phần tử có cùng kiểu dữ liệu, được lưu trữ liên tiếp trong bộ nhớ. Mảng giúp quản lý nhiều giá trị một cách có hệ thống, thay vì khai báo nhiều biến riêng lẻ.

### 1.2. Đặc điểm của mảng một chiều trong C#

- **Mảng có chỉ mục (index)**: Chỉ mục bắt đầu từ 0, phần tử đầu tiên có chỉ số 0, phần tử cuối cùng có chỉ số `Length - 1`.
- **Mảng có kích thước cố định**: Khi khai báo mảng với số phần tử cụ thể, kích thước này không thể thay đổi.
- **Mảng có thể chứa giá trị mặc định**: Nếu không khởi tạo giá trị, các phần tử sẽ được gán giá trị mặc định của kiểu dữ liệu đó (ví dụ: `0` cho `int`, `false` cho `bool`, `null` cho `string`).
- **Mảng thuộc kiểu tham chiếu (Reference Type)**: Khi truyền một mảng vào phương thức, nó truyền tham chiếu đến mảng chứ không phải bản sao của mảng.
- **Mảng có thể chứa các kiểu dữ liệu bất kỳ**: Không chỉ số nguyên hay chuỗi, mảng có thể chứa cả kiểu dữ liệu phức tạp như đối tượng class.

## 2. Khai báo và khởi tạo mảng

### 2.1. Khai báo mảng với kích thước cố định

```csharp
int[] numbers = new int[5]; // Mảng có 5 phần tử, giá trị mặc định là 0
```

### 2.2. Khai báo mảng và khởi tạo giá trị ngay từ đầu

```csharp
int[] numbers2 = {1, 2, 3, 4, 5}; // Mảng có 5 phần tử đã được gán giá trị
```

### 2.3. Khai báo mảng không cố định kích thước (Sử dụng `new`)

```csharp
int[] numbers3 = new int[] {10, 20, 30, 40};
```

### 2.4. Khai báo mảng chứa kiểu dữ liệu khác

```csharp
string[] names = {"Alice", "Bob", "Charlie"};
```

## 3. Truy cập và thao tác trên mảng

### 3.1. Truy cập phần tử trong mảng

#### Truy cập phần tử bằng chỉ số

```csharp
int firstElement = numbers2[0]; // Lấy giá trị phần tử đầu tiên (1)
numbers2[1] = 10; // Thay đổi giá trị phần tử thứ hai thành 10
```

#### Lặp qua mảng bằng vòng lặp `for`

```csharp
for (int i = 0; i < numbers2.Length; i++)
{
    Console.WriteLine(numbers2[i]);
}
```

#### Lặp qua mảng bằng vòng lặp `foreach`

```csharp
foreach (int num in numbers2)
{
    Console.WriteLine(num);
}
```

## 4. Các phương thức hỗ trợ xử lý mảng một chiều trong C#

### 4.1. Các hàm xử lý chung

|Hàm|Cú pháp|Tác dụng|Ghi chú|Ví dụ|
|---|---|---|---|---|
|`Length`|`mang.Length`|Trả về số lượng phần tử trong mảng|Không thể thay đổi giá trị|`int size = numbers2.Length;`|
|`Array.IndexOf`|`Array.IndexOf(mang, giaTri)`|Tìm vị trí của phần tử trong mảng|Trả về -1 nếu không tìm thấy|`int index = Array.IndexOf(numbers2, 3);`|
|`Array.Exists`|`Array.Exists(mang, predicate)`|Kiểm tra xem phần tử có trong mảng không|Sử dụng biểu thức lambda|`bool exists = Array.Exists(numbers2, x => x == 3);`|
|`Array.Fill`|`Array.Fill(mang, giaTri)`|Gán một giá trị cho tất cả phần tử trong mảng|Có thể dùng để reset mảng|`Array.Fill(numbers2, 0);`|
|`Array.Clear`|`Array.Clear(mang, startIndex, count)`|Xóa một số phần tử trong mảng|Gán giá trị mặc định|`Array.Clear(numbers2, 1, 2);`|

### 4.2. Các hàm sắp xếp và đảo ngược

|Hàm|Cú pháp|Tác dụng|Ghi chú|Ví dụ|
|---|---|---|---|---|
|`Array.Sort`|`Array.Sort(mang)`|Sắp xếp mảng tăng dần|Thay đổi trực tiếp trên mảng|`Array.Sort(numbers2);`|
|`Array.Reverse`|`Array.Reverse(mang)`|Đảo ngược thứ tự phần tử trong mảng|Cần gọi sau khi sắp xếp để có thứ tự giảm dần|`Array.Reverse(numbers2);`|

### 4.3. Các hàm tìm kiếm nâng cao

|Hàm|Cú pháp|Tác dụng|Ghi chú|Ví dụ|
|---|---|---|---|---|
|`Array.FindIndex`|`Array.FindIndex(mang, predicate)`|Tìm vị trí phần tử đầu tiên thỏa điều kiện|Trả về -1 nếu không tìm thấy|`int index = Array.FindIndex(numbers2, x => x > 2);`|
|`Array.TrueForAll`|`Array.TrueForAll(mang, predicate)`|Kiểm tra xem tất cả phần tử có thỏa điều kiện không|Trả về `true` hoặc `false`|`bool allPositive = Array.TrueForAll(numbers2, x => x > 0);`|

## 5. Các vấn đề cần lưu ý chung

- Mảng có kích thước cố định sau khi khởi tạo.
- Khi truy cập phần tử ngoài phạm vi, sẽ phát sinh lỗi `IndexOutOfRangeException`.
- `Array.Fill` giúp nhanh chóng gán giá trị đồng nhất cho mảng.
- `Array.Resize` có thể thay đổi kích thước mảng nhưng phải dùng từ khóa `ref`.
- `Array.Clear` giúp reset một phần của mảng mà không cần tạo lại.
- `Array.Find` hữu ích khi cần lấy giá trị cụ thể mà không duyệt thủ công.
- `Array.Sort` và `Array.Reverse` có thể kết hợp để sắp xếp mảng theo nhiều kiểu.

## 6. Ví dụ minh họa mở rộng

### 6.1. Reset giá trị của mảng

```csharp
int[] numbers = {1, 2, 3, 4, 5};
Array.Fill(numbers, 0);
```

### 6.2. Xóa một phần tử trong mảng

```csharp
int[] numbers = {1, 2, 3, 4, 5};
Array.Clear(numbers, 1, 2);
```

### 6.3. Tìm kiếm phần tử đầu tiên thỏa điều kiện

```csharp
int[] numbers = {1, 3, 7, 9, 12};
int result = Array.Find(numbers, x => x > 5);
Console.WriteLine(result); // Kết quả: 7
```