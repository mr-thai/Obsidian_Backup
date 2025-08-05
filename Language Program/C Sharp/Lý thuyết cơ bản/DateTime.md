### **1. Khởi tạo đối tượng `DateTime`**

Bạn có thể khởi tạo một đối tượng `DateTime` bằng cách sử dụng các phương thức khác nhau:

#### Khởi tạo `DateTime` bằng năm, tháng, ngày, giờ, phút, giây:
```csharp
DateTime date1 = new DateTime(2025, 1, 22, 14, 30, 0); // 22/01/2025 14:30:00
Console.WriteLine(date1);
```

#### Khởi tạo `DateTime` từ chuỗi:
```csharp
DateTime date2 = DateTime.Parse("2025-01-22 14:30:00");
Console.WriteLine(date2);
```

#### Khởi tạo `DateTime` từ ngày hiện tại:
```csharp
DateTime now = DateTime.Now; // Ngày và giờ hiện tại
Console.WriteLine(now);
```

#### Khởi tạo `DateTime` từ ngày UTC (Thời gian chuẩn quốc tế):
```csharp
DateTime utcNow = DateTime.UtcNow; // Ngày và giờ hiện tại UTC
Console.WriteLine(utcNow);
```

---

### **2. Các thuộc tính chính của `DateTime`**

| **Thuộc tính**           | **Mô tả**                                                                        |
|--------------------------|---------------------------------------------------------------------------------|
| `Now`                    | Trả về thời gian hiện tại theo giờ hệ thống.                                    |
| `UtcNow`                 | Trả về thời gian hiện tại theo giờ UTC.                                        |
| `Today`                  | Trả về ngày hiện tại nhưng giờ, phút, giây được đặt là 00:00:00.               |
| `Day`, `Month`, `Year`   | Trả về ngày, tháng, năm của đối tượng `DateTime`.                               |
| `Hour`, `Minute`, `Second` | Trả về giờ, phút, giây của đối tượng `DateTime`.                                |
| `DayOfWeek`              | Trả về ngày trong tuần (enum `DayOfWeek`).                                      |
| `DayOfYear`              | Trả về ngày trong năm (1 - 365 hoặc 366).                                       |
| `IsLeapYear`             | Kiểm tra xem năm có phải là năm nhuận không.                                    |

**Ví dụ:**
```csharp
DateTime now = DateTime.Now;
Console.WriteLine("Ngày hiện tại: " + now.ToString("dd/MM/yyyy"));
Console.WriteLine("Tháng hiện tại: " + now.Month);
Console.WriteLine("Ngày trong tuần: " + now.DayOfWeek);
```

---

### **3. Các phương thức của `DateTime`**

| **Phương thức**          | **Mô tả**                                                                        | **Ví dụ** |
|--------------------------|---------------------------------------------------------------------------------|----------|
| `AddDays(double value)`   | Thêm số ngày vào `DateTime` hiện tại.                                           | `now.AddDays(5)` (Thêm 5 ngày vào `now`) |
| `AddMonths(int months)`   | Thêm số tháng vào `DateTime` hiện tại.                                          | `now.AddMonths(1)` (Thêm 1 tháng vào `now`) |
| `AddYears(int years)`     | Thêm số năm vào `DateTime` hiện tại.                                            | `now.AddYears(1)` (Thêm 1 năm vào `now`) |
| `AddHours(double hours)`  | Thêm số giờ vào `DateTime` hiện tại.                                            | `now.AddHours(3)` (Thêm 3 giờ vào `now`) |
| `AddMinutes(double minutes)` | Thêm số phút vào `DateTime` hiện tại.                                         | `now.AddMinutes(30)` (Thêm 30 phút vào `now`) |
| `ToString(string format)` | Chuyển đổi `DateTime` thành chuỗi với định dạng cụ thể.                         | `now.ToString("yyyy-MM-dd")` |
| `Compare(DateTime t1, DateTime t2)` | So sánh hai đối tượng `DateTime`.                                         | `DateTime.Compare(date1, date2)` |
| `IsLeapYear(int year)`    | Kiểm tra xem năm có phải là năm nhuận không.                                    | `DateTime.IsLeapYear(2024)` |
| `Parse(string s)`         | Chuyển chuỗi thành `DateTime`.                                                   | `DateTime.Parse("2025-01-22")` |
| `TryParse(string s, out DateTime result)` | Cố gắng chuyển chuỗi thành `DateTime`, trả về kết quả dưới dạng Boolean. | `DateTime.TryParse("2025-01-22", out DateTime result)` |

**Ví dụ:**
```csharp
DateTime now = DateTime.Now;
Console.WriteLine("Ngày sau 10 ngày: " + now.AddDays(10));
Console.WriteLine("Ngày sau 3 tháng: " + now.AddMonths(3));
Console.WriteLine("Ngày sau 1 năm: " + now.AddYears(1));
Console.WriteLine("Ngày sau 2 giờ: " + now.AddHours(2));
```

---

### **4. Định dạng `DateTime`**

C# hỗ trợ rất nhiều định dạng chuỗi để hiển thị `DateTime`. Các định dạng phổ biến bao gồm:

| **Định dạng**  | **Mô tả**                                      | **Ví dụ** |
|----------------|------------------------------------------------|----------|
| `d`            | Ngày ngắn, không có giờ.                       | `23/01/2025` |
| `D`            | Ngày đầy đủ, bao gồm tên ngày trong tuần.      | `Friday, January 23, 2025` |
| `t`            | Giờ ngắn.                                      | `2:30 PM` |
| `T`            | Giờ đầy đủ.                                    | `2:30:15 PM` |
| `f`            | Ngày và giờ ngắn.                              | `Friday, January 23, 2025 2:30 PM` |
| `F`            | Ngày và giờ đầy đủ.                            | `Friday, January 23, 2025 2:30:15 PM` |
| `yyyy-MM-dd`   | Năm-tháng-ngày.                                | `2025-01-23` |
| `hh:mm:ss`     | Giờ:phút:giây.                                 | `14:30:15` |

**Ví dụ:**
```csharp
DateTime now = DateTime.Now;
Console.WriteLine("Ngày theo định dạng ngắn: " + now.ToString("d"));
Console.WriteLine("Ngày đầy đủ: " + now.ToString("D"));
Console.WriteLine("Giờ theo định dạng ngắn: " + now.ToString("t"));
Console.WriteLine("Giờ đầy đủ: " + now.ToString("T"));
Console.WriteLine("Ngày theo định dạng yyyy-MM-dd: " + now.ToString("yyyy-MM-dd"));
```

---

### **5. Một số lưu ý khi sử dụng `DateTime`**

- **So sánh `DateTime`:** Dùng các phương thức như `Compare`, `Equals`, hoặc toán tử so sánh (`<`, `>`, $==$) để so sánh các đối tượng `DateTime`.
  
- **Thời gian UTC và Local:** Cẩn thận khi làm việc với `DateTime.Now` (giờ hệ thống) và `DateTime.UtcNow` (giờ UTC). Nếu làm việc với các ứng dụng đa quốc gia, nên sử dụng giờ UTC để tránh các vấn đề về múi giờ.

- **Ngày kết thúc tháng:** Phương thức `AddDays` có thể dẫn đến thay đổi tháng hoặc năm nếu thêm ngày vượt qua cuối tháng.

---

### **Ví dụ thực tế:**
Tính toán sự khác biệt giữa hai thời điểm:
```csharp
DateTime start = new DateTime(2025, 1, 1);
DateTime end = DateTime.Now;
TimeSpan difference = end - start;
Console.WriteLine("Sự khác biệt là: " + difference.Days + " ngày");
```
