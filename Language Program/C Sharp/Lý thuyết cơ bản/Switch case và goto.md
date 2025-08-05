### **1. `switch-case`**

- **`switch-case`** được sử dụng để kiểm tra giá trị của một biểu thức và thực thi các khối lệnh tương ứng với giá trị đó.
- Nó thường được sử dụng thay cho các chuỗi `if-else if` khi có nhiều trường hợp cần xử lý.

#### **Cú pháp:**

```csharp
switch (biểu_thức)
{
    case giá_trị_1:
        // Lệnh thực thi nếu biểu_thức == giá_trị_1
        break;
    case giá_trị_2:
        // Lệnh thực thi nếu biểu_thức == giá_trị_2
        break;
    // Thêm các case khác
    default:
        // Lệnh thực thi nếu không có case nào khớp
        break;
}
```

#### **Ví dụ:**

```csharp
int day = 3;

switch (day)
{
    case 1:
        Console.WriteLine("Thứ hai");
        break;
    case 2:
        Console.WriteLine("Thứ ba");
        break;
    case 3:
        Console.WriteLine("Thứ tư");
        break;
    default:
        Console.WriteLine("Không xác định");
        break;
}
```

- Nếu `day == 3`, kết quả là **"Thứ tư"**.

---

#### **Lưu ý khi sử dụng `switch-case`:**

1. **`break` quan trọng:**
    
    - Dùng để kết thúc một khối `case`. Nếu thiếu, chương trình sẽ tiếp tục thực hiện các `case` sau đó (hiện tượng **fall-through**).
    - Ví dụ:
        
        ```csharp
        switch (3)
        {
            case 1:
                Console.WriteLine("One");
            case 3:
                Console.WriteLine("Three"); // Sẽ chạy
            default:
                Console.WriteLine("Default");
        }
        ```
        
        **Kết quả:**
        
        ```
        Three
        Default
        ```
        
2. **`default`:**
    
    - Không bắt buộc, nhưng nên sử dụng để xử lý trường hợp không có `case` nào khớp.
3. **Biểu thức trong `switch`:**
    
    - Phải là giá trị kiểu số nguyên (`int`, `byte`, `short`, `long`), `char`, `string`, hoặc `enum`. Các kiểu như `float`, `double` không được hỗ trợ.
4. **Nhiều `case` chung một khối lệnh:**
    
    - Có thể gom nhiều `case` lại với nhau:
        
        ```csharp
        switch (day)
        {
            case 1:
            case 2:
            case 3:
                Console.WriteLine("Đầu tuần");
                break;
            case 6:
            case 7:
                Console.WriteLine("Cuối tuần");
                break;
            default:
                Console.WriteLine("Ngày giữa tuần");
                break;
        }
        ```
        

---

### **2. `goto` trong C#**

- **`goto`** là một lệnh điều khiển luồng để nhảy trực tiếp đến một nhãn (label) được chỉ định.
- Trong C#, **`goto`** được sử dụng trong các trường hợp:
    1. **Nhảy đến một nhãn bất kỳ trong chương trình.**
    2. **Thoát khỏi một `switch-case` mà không cần sử dụng `break`.**

#### **Cú pháp:**

1. **Nhảy đến nhãn:**
    
    ```csharp
    goto tên_nhãn;
    ```
    
    Tên nhãn được khai báo như sau:
    
    ```csharp
    tên_nhãn:
    ```
    
2. **Trong `switch-case`:**
    
    ```csharp
    case giá_trị:
        goto tên_nhãn;
    ```
    

#### **Ví dụ:**

##### **a. Nhảy đến nhãn:**

```csharp
int count = 0;

start: // Nhãn (label)
Console.WriteLine($"Count: {count}");
count++;
if (count < 5)
{
    goto start; // Nhảy về nhãn start
}
Console.WriteLine("Kết thúc!");
```

- Kết quả:
    
    ```
    Count: 0
    Count: 1
    Count: 2
    Count: 3
    Count: 4
    Kết thúc!
    ```
    

##### **b. Trong `switch-case`:**

```csharp
int number = 2;

switch (number)
{
    case 1:
        Console.WriteLine("One");
        break;
    case 2:
        Console.WriteLine("Two");
        goto case 1; // Nhảy đến case 1
    default:
        Console.WriteLine("Default");
        break;
}
```

- Kết quả:
    
    ```
    Two
    One
    ```
    

---

### **Lưu ý khi sử dụng `goto`:**

1. **Sử dụng thận trọng:**
    - `goto` có thể làm mã nguồn khó đọc và bảo trì. Nên hạn chế dùng, trừ khi thực sự cần thiết.
2. **Không được nhảy ra ngoài phạm vi:**
    - `goto` không thể nhảy ra ngoài hàm hiện tại.

---

### **Khi nào nên dùng `switch-case` và `goto`?**

- **`switch-case`:** Dùng khi cần kiểm tra nhiều giá trị của một biến với các hành động cụ thể.
- **`goto`:** Chỉ dùng trong các trường hợp cần nhảy điều kiện phức tạp mà không thể giải quyết dễ dàng bằng cấu trúc lặp hoặc điều kiện thông thường.
