### **1. Nhập chuỗi ký tự (string)**

Sử dụng `Console.ReadLine()` để nhập một chuỗi từ bàn phím.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.Write("Nhập tên của bạn: ");
        string name = Console.ReadLine();
        Console.WriteLine("Xin chào, " + name + "!");
    }
}
```

**Giải thích:**

- `Console.ReadLine()`: Đọc toàn bộ dòng ký tự mà người dùng nhập vào.
- Kết quả sẽ được lưu dưới dạng chuỗi (`string`).

---

### **2. Nhập số nguyên (int)**

Cần chuyển đổi chuỗi nhập vào thành số nguyên bằng `int.Parse()` hoặc `Convert.ToInt32()`.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.Write("Nhập một số nguyên: ");
        int number = int.Parse(Console.ReadLine());
        Console.WriteLine("Số bạn vừa nhập là: " + number);
    }
}
```

**Lưu ý:**

- Nếu người dùng nhập sai (ví dụ nhập ký tự không phải số), chương trình sẽ báo lỗi.
- Có thể dùng `int.TryParse()` để kiểm tra và xử lý nhập sai (xem phần 6).

---

### **3. Nhập số thực (float/double)**

Tương tự như số nguyên, dùng `float.Parse()` hoặc `double.Parse()` để chuyển đổi.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.Write("Nhập một số thực: ");
        double number = double.Parse(Console.ReadLine());
        Console.WriteLine("Số thực bạn vừa nhập là: " + number);
    }
}
```

---

### **4. Nhập giá trị logic (bool)**

Dùng `bool.Parse()` để chuyển đổi chuỗi nhập vào thành giá trị logic (`true` hoặc `false`).

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.Write("Bạn có thích lập trình không? (true/false): ");
        bool likesProgramming = bool.Parse(Console.ReadLine());
        Console.WriteLine("Bạn vừa trả lời: " + likesProgramming);
    }
}
```

---

### **5. Nhập nhiều giá trị trên một dòng**

Dùng `Console.ReadLine()` kết hợp với `string.Split()` để tách các giá trị nhập vào.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.Write("Nhập hai số, cách nhau bằng dấu cách: ");
        string[] inputs = Console.ReadLine().Split(' ');

        int a = int.Parse(inputs[0]);
        int b = int.Parse(inputs[1]);

        Console.WriteLine($"Tổng của {a} và {b} là: {a + b}");
    }
}
```

**Giải thích:**

- `Split(' ')`: Tách chuỗi thành mảng các phần tử dựa trên khoảng trắng.
- Sau đó, bạn chuyển đổi từng phần tử thành kiểu dữ liệu mong muốn.

---

### **6. Kiểm tra đầu vào hợp lệ với TryParse**

Dùng `int.TryParse()`, `double.TryParse()` hoặc các phương thức tương tự để kiểm tra nhập liệu.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.Write("Nhập một số nguyên: ");
        if (int.TryParse(Console.ReadLine(), out int number))
        {
            Console.WriteLine("Số bạn vừa nhập là: " + number);
        }
        else
        {
            Console.WriteLine("Bạn đã nhập sai, vui lòng nhập một số nguyên!");
        }
    }
}
```

**Giải thích:**

- `TryParse()` trả về `true` nếu chuyển đổi thành công, đồng thời lưu kết quả vào biến `number`.
- Nếu nhập sai, chương trình vẫn chạy và thông báo lỗi thay vì dừng.

---

### **7. Nhập dữ liệu với kiểu khác (char, decimal, ...)**

- **Kiểu ký tự (`char`)**: Dùng `char.Parse()` để chuyển đổi.
- **Kiểu thập phân (`decimal`)**: Dùng `decimal.Parse()`.

Ví dụ:

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.Write("Nhập một ký tự: ");
        char ch = char.Parse(Console.ReadLine());
        Console.WriteLine("Ký tự bạn vừa nhập: " + ch);

        Console.Write("Nhập một số thập phân: ");
        decimal dec = decimal.Parse(Console.ReadLine());
        Console.WriteLine("Số thập phân: " + dec);
    }
}
```

