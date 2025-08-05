### **1. Vòng lặp `while`**

- **Cách hoạt động:**
    - Kiểm tra điều kiện **trước khi thực thi** khối lệnh.
    - Nếu điều kiện đúng (`true`), khối lệnh sẽ được thực thi.
    - Nếu điều kiện sai (`false`), vòng lặp kết thúc ngay lập tức.

#### **Cú pháp:**

```csharp
while (điều_kiện)
{
    // Lệnh cần thực thi nếu điều_kiện đúng
}
```

#### **Ví dụ:**

In các số từ 1 đến 5:

```csharp
int i = 1;

while (i <= 5)
{
    Console.WriteLine(i);
    i++;
}
```

- **Kết quả:**
    
    ```
    1
    2
    3
    4
    5
    ```
    

---

### **2. Vòng lặp `do-while`**

- **Cách hoạt động:**
    - **Thực thi khối lệnh ít nhất một lần**, sau đó kiểm tra điều kiện.
    - Nếu điều kiện đúng (`true`), vòng lặp tiếp tục.
    - Nếu điều kiện sai (`false`), vòng lặp kết thúc.

#### **Cú pháp:**

```csharp
do
{
    // Lệnh cần thực thi
}
while (điều_kiện);
```

#### **Ví dụ:**

In các số từ 1 đến 5:

```csharp
int i = 1;

do
{
    Console.WriteLine(i);
    i++;
}
while (i <= 5);
```

- **Kết quả:**
    
    ```
    1
    2
    3
    4
    5
    ```
    

#### **So sánh với `while`:**

- Nếu điều kiện ban đầu là `false`:
    
    ```csharp
    int i = 6;
    
    // while
    while (i <= 5)
    {
        Console.WriteLine(i);
    }
    // Không in gì cả
    
    // do-while
    do
    {
        Console.WriteLine(i);
    }
    while (i <= 5);
    // Kết quả: 6
    ```
    

---

### **3. Vòng lặp `while (true)`**

- **Cách hoạt động:**
    - `while(true)` là một vòng lặp vô hạn, chạy liên tục cho đến khi bị dừng bằng cách:
        - Gặp lệnh `break`.
        - Kết thúc chương trình.
    - Thường được sử dụng trong các chương trình yêu cầu vòng lặp vô tận (ví dụ: hệ thống xử lý sự kiện, server, game loop).

#### **Ví dụ:**

Yêu cầu người dùng nhập số cho đến khi nhập số âm:

```csharp
while (true)
{
    Console.Write("Nhập một số: ");
    int number = int.Parse(Console.ReadLine());

    if (number < 0)
    {
        Console.WriteLine("Kết thúc!");
        break; // Dừng vòng lặp
    }
    Console.WriteLine($"Bạn đã nhập: {number}");
}
```

- **Kết quả (giả sử nhập `5`, `10`, `-1`):**
    
    ```
    Nhập một số: 5
    Bạn đã nhập: 5
    Nhập một số: 10
    Bạn đã nhập: 10
    Nhập một số: -1
    Kết thúc!
    ```
    

---

### **So sánh giữa `while`, `do-while`, và `while(true)`**

|Đặc điểm|`while`|`do-while`|`while(true)`|
|---|---|---|---|
|**Kiểm tra điều kiện**|Trước khi thực thi khối lệnh|Sau khi thực thi ít nhất một lần|Không kiểm tra, luôn chạy|
|**Thực thi ít nhất 1 lần**|Không (nếu điều kiện ban đầu sai)|Có|Có, cho đến khi gặp `break`|
|**Ứng dụng**|Lặp khi điều kiện cụ thể còn đúng|Lặp khi cần ít nhất 1 lần chạy|Lặp vô hạn hoặc xử lý sự kiện|

---

### **Lưu ý khi sử dụng:**

1. **Tránh vòng lặp vô hạn không cần thiết:**
    - Kiểm tra điều kiện hợp lý hoặc sử dụng `break` để thoát.
2. **Xử lý đầu vào:** Khi nhập dữ liệu từ người dùng, luôn kiểm tra tính hợp lệ để tránh lỗi.
3. **`while (true)` cần `break`:**
    - Luôn đảm bảo có một cách thoát khỏi vòng lặp để tránh treo chương trình.
