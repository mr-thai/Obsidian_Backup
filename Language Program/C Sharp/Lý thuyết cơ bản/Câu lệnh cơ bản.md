```cs
Console.Write();
```
- Xuất dữ liệu, giá trị có thể là chuỗi ký tự, sô
```cs
Console.WriteLine();
```
- Giống lệnh trên nhưng khi thực thi việc in ra dữ liệu hoặc giá trị thì xuống dòng
```cs
Console.Readline();
```
- Dùng để dùng chương trình sau khi chạy trong màn hình teminal tương tự `cin.get();` của c++ cho đến khi nhấn phím enter
```cs 
 Console.OutputEncoding = Encoding.UTF8;
```
- định dạng giá trị đầu ra là UTF 8
- Thường dùng để gõ tiếng việt
```cs
int soLuong = 0;
float diem = 9.8f;
Console.WriteLine("so luong {0}, diem {1}", soLuong, diem);
```
- **`{0}`**: Tham chiếu đến giá trị đầu tiên trong danh sách tham số (`soLuong`).
- **`{1}`**: Tham chiếu đến giá trị thứ hai trong danh sách tham số (`diem`).
- Khá giống với ngôn ngữ `C`
