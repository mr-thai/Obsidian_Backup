## Kiểu dữ liệu trong `C#`

| **Nhóm**           | **Kiểu dữ liệu** | **Kích thước (bytes)** | **Ý nghĩa**                                                                                              |
| ------------------ | ---------------- | ---------------------- | -------------------------------------------------------------------------------------------------------- |
| **Kiểu số nguyên** | **byte**         | 1                      | Số nguyên dương **không dấu**, giá trị từ **0** đến **255**                                              |
|                    | **sbyte**        | 1                      | Số nguyên **có dấu**, giá trị từ **-128** đến **127**                                                    |
|                    | **short**        | 2                      | Số nguyên **có dấu**, giá trị từ **-32,768** đến **32,767**                                              |
|                    | **ushort**       | 2                      | Số nguyên **không dấu**, giá trị từ **0** đến **65,535**                                                 |
|                    | **int**          | 4                      | Số nguyên **có dấu**, giá trị từ **-2,147,483,648** đến **2,147,483,647**                                |
|                    | **uint**         | 4                      | Số nguyên **không dấu**, giá trị từ **0** đến **4,294,967,295**                                          |
|                    | **long**         | 8                      | Số nguyên **có dấu**, giá trị từ **-9,223,372,036,854,775,808** đến **9,223,372,036,854,775,807**        |
|                    | **ulong**        | 8                      | Số nguyên **không dấu**, giá trị từ **0** đến **18,446,744,073,709,551,615**                             |
| **Kiểu ký tự**     | [[Char]]         | 2                      | Chứa một ký tự Unicode (ký tự ASCII mở rộng hoặc các ký tự đa dạng khác)                                 |
| **Kiểu logic**     | **bool**         | 1                      | Chứa 1 trong 2 giá trị logic: **true** hoặc **false**                                                    |
| **Kiểu số thực**   | **float**        | 4                      | Số thực dấu chấm động, giá trị từ **3.4E-38** đến **3.4E+38**, độ chính xác khoảng 7 chữ số              |
|                    | **double**       | 8                      | Số thực dấu chấm động, giá trị từ **1.7E-308** đến **1.7E+308**, độ chính xác khoảng 15–16 chữ số        |
|                    | **decimal**      | 16                     | Số thực dấu chấm động với độ chính xác cao (28–29 chữ số), phù hợp cho tính toán tài chính hoặc khoa học |
| **Kiểu đặc biệt**  | **object**       | 4 hoặc 8               | Đối tượng cơ bản nhất trong C#, có thể chứa bất kỳ kiểu dữ liệu nào                                      |
|                    | [[String]]       | Phụ thuộc nội dung     | Chuỗi ký tự Unicode, không giới hạn độ dài (miễn là đủ bộ nhớ)                                           |
|                    | **dynamic**      | Phụ thuộc nội dung     | Kiểu dữ liệu động, giá trị có thể thay đổi tại thời gian chạy                                            |
|                    | **var**          | Phụ thuộc nội dung     | Kiểu dữ liệu tự động được suy luận tại thời điểm biên dịch dựa trên giá trị khởi tạo                     |
## Biến trong `C#`
- Là tên gọi của một vùng nhớ, để lưu trữ dữ liệu
- Khai báo biến: `<Kiểu biến> + <tên biến> [Giá trị];`
```cs
int soLuong = 0;
float diemTrungBinh = 8.5f;
double diemToan = 9.5;
string name = "thái";
byte tuoi;
```
>- Ký tự **`f`** ở cuối giá trị **8.5f** cho biết đây là số thực kiểu `float`. Nếu không có `f`, trình biên dịch mặc định hiểu đây là kiểu **`double`** (có độ chính xác cao hơn, chiếm 8 bytes).
- Nếu biến có thêm giá trị thì được gọi là khởi tạo biến
- Nếu biến không thêm giá tri được gọi là khai báo biến
## Quy tắc khai báo biến trong `C#`
- Tên biến có phân biệt chữ hoa và chữ thường
- Không được bắt đầu bằng số
- Không được đặt trùng với các keyword có sẵn trong C#
- Quy tắc đặt tên (camel): Đặt tên sát với mục đích sử dụng biến, từ chữ thứ 2 thì viết hoa chữ cái đầu (Không bắt buộc)
- Không được dùng ký tự đặc biệt trong tên biến
## Ép kiểu dữ liệu
### 1. Ép kiểu từ dữ liệu bé hơn sang dữ liệu lớn hơn
- Hạn chế việc mất dữ liệu
```cs
byte x = 40;
int y = x;
```
### 2. Ép kiểu từ dữ liệu lớn sang dữ liệu bé hơn
- Có thể gây lỗi
```cs
int x = 400;
byte y = x;
```
### 3. Ép kiểu từ dữ liệu lớn sang dữ liệu bé hơn nhưng dùng tường minh
```cs
int x = 4000;
short y = (short)x;
```
- Không gây lỗi giống không gắp lỗi ép từ lớn sang bé
## Implicit type `C#`
- Kiểu ngầm hiểu C# tự nội suy `var`
- Chỉ nên dùng nội suy khi thực sự ta không biết được kiểu của biến không khuyến khích vì nội suy cũng gây tốn bộ nhớ
```cs 
var y = 123;
```
- Cách kiểm tra kiểu dữ liệu 
```cs 
Console.WriteLine("Kiểu dữ liệu của {0}", y.GetType().ToSting());
```
