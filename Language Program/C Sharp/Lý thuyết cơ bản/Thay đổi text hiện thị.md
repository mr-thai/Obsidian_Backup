### **Thay đổi màu văn bản trong Console**

#### **Cú pháp cơ bản:**

```csharp
Console.ForegroundColor = ConsoleColor.Tên_màu;
// Nội dung hiển thị
Console.WriteLine("Văn bản màu sắc!");
// Đặt lại màu sắc về mặc định (thường là trắng hoặc màu ban đầu)
Console.ResetColor();
```

#### **Ví dụ đơn giản:**

```csharp
Console.ForegroundColor = ConsoleColor.Green; // Chọn màu xanh lá cây
Console.WriteLine("Đây là văn bản màu xanh lá cây.");

Console.ForegroundColor = ConsoleColor.Red; // Chọn màu đỏ
Console.WriteLine("Đây là văn bản màu đỏ.");

Console.ResetColor(); // Đặt lại màu về mặc định
Console.WriteLine("Màu văn bản trở lại mặc định.");
```

---

### **Bảng màu có sẵn trong `ConsoleColor`**

Dưới đây là danh sách các màu mà bạn có thể sử dụng trong thuộc tính `Console.ForegroundColor`:

| **Màu**          | **Tên trong `ConsoleColor`** |
| ---------------- | ---------------------------- |
| Đen              | `Black`                      |
| Xanh đậm         | `DarkBlue`                   |
| Xanh lá cây đậm  | `DarkGreen`                  |
| Xanh lam đậm     | `DarkCyan`                   |
| Đỏ đậm           | `DarkRed`                    |
| Tím đậm          | `DarkMagenta`                |
| Vàng nâu         | `DarkYellow`                 |
| Xám              | `Gray`                       |
| Xám đậm          | `DarkGray`                   |
| Xanh lam sáng    | `Blue`                       |
| Xanh lá cây sáng | `Green`                      |
| Xanh ngọc sáng   | `Cyan`                       |
| Đỏ sáng          | `Red`                        |
| Tím sáng         | `Magenta`                    |
| Vàng sáng        | `Yellow`                     |
| Trắng            | `White`                      |

---

### **Thay đổi cả màu nền (Background Color)**

Ngoài thay đổi màu chữ, bạn cũng có thể thay đổi màu nền bằng thuộc tính `Console.BackgroundColor`.

#### **Ví dụ:**

```csharp
// Đổi màu nền và màu chữ
Console.BackgroundColor = ConsoleColor.Blue; // Màu nền xanh lam
Console.ForegroundColor = ConsoleColor.White; // Màu chữ trắng
Console.WriteLine("Văn bản với màu nền xanh lam và chữ trắng");

// Đặt lại màu nền và chữ
Console.ResetColor();
Console.WriteLine("Trở về mặc định.");
```

---

### **Ứng dụng thực tế:**

#### Tạo giao diện với nhiều màu sắc:

```csharp
Console.ForegroundColor = ConsoleColor.Yellow;
Console.WriteLine("===== CHÀO MỪNG =====");
Console.ForegroundColor = ConsoleColor.Cyan;
Console.WriteLine("1. Bắt đầu");
Console.ForegroundColor = ConsoleColor.Green;
Console.WriteLine("2. Tùy chọn");
Console.ForegroundColor = ConsoleColor.Red;
Console.WriteLine("3. Thoát");
Console.ResetColor();
```

Kết quả sẽ hiển thị một menu với các tùy chọn được tô màu khác nhau, dễ dàng phân biệt.

---

### **Lưu ý khi sử dụng màu sắc:**

1. **Khả năng hiển thị:** Chọn màu dễ đọc trên nền console, tránh các màu quá tối hoặc không tương phản.
2. **Khôi phục màu mặc định:** Luôn gọi `Console.ResetColor()` sau khi thay đổi màu sắc để không ảnh hưởng đến các phần hiển thị khác.
3. **Giới hạn:** Các thay đổi chỉ áp dụng cho console, không ảnh hưởng đến giao diện đồ họa hoặc các cửa sổ khác.
