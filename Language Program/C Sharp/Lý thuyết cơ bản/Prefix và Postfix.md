### **1. Prefix (`++x` hoặc `--x`)**

- Toán tử được áp dụng **trước** khi sử dụng giá trị của biến.
- Giá trị của biến sẽ được **tăng/giảm trước**, sau đó giá trị mới được trả về.

#### **Ví dụ:**

```csharp
int x = 5;
int y = ++x; // x tăng lên 6, y nhận giá trị mới của x (6)

Console.WriteLine(x); // Output: 6
Console.WriteLine(y); // Output: 6
```

#### **Quy trình hoạt động:**

1. Tăng (hoặc giảm) giá trị của `x`.
2. Trả về giá trị mới của `x`.

---

### **2. Postfix (`x++` hoặc `x--`)**

- Toán tử được áp dụng **sau** khi sử dụng giá trị của biến.
- Giá trị của biến **ban đầu** được trả về, sau đó mới thực hiện tăng/giảm giá trị.

#### **Ví dụ:**

```csharp
int x = 5;
int y = x++; // y nhận giá trị hiện tại của x (5), sau đó x tăng lên 6

Console.WriteLine(x); // Output: 6
Console.WriteLine(y); // Output: 5
```

#### **Quy trình hoạt động:**

1. Trả về giá trị ban đầu của `x`.
2. Tăng (hoặc giảm) giá trị của `x`.

---

### **So sánh giữa Prefix và Postfix**

| **Đặc điểm**           | **Prefix (`++x`, `--x`)**           | **Postfix (`x++`, `x--`)**                    |
| ---------------------- | ----------------------------------- | --------------------------------------------- |
| **Thứ tự thực thi**    | Tăng/giảm giá trị trước khi sử dụng | Sử dụng giá trị ban đầu, sau đó tăng/giảm     |
| **Thứ tự ưu tiên**     | Thực hiện ngay lập tức              | Thực hiện sau khi giá trị được dùng           |
| **Ảnh hưởng đến biến** | Biến được cập nhật ngay lập tức     | Biến được cập nhật sau khi sử dụng giá trị cũ |

---

### **Ví dụ tổng hợp:**

```csharp
int a = 5, b = 5;

// Prefix
Console.WriteLine(++a); // Output: 6 (a tăng trước khi in)

// Postfix
Console.WriteLine(b++); // Output: 5 (b in giá trị ban đầu, sau đó tăng lên 6)

// Kiểm tra giá trị sau khi thay đổi
Console.WriteLine(a);   // Output: 6
Console.WriteLine(b);   // Output: 6
```

---

### **Khi nào nên dùng Prefix hoặc Postfix?**

- **Prefix** thường được dùng khi bạn muốn cập nhật giá trị trước khi sử dụng nó.
- **Postfix** thường được dùng khi bạn muốn sử dụng giá trị cũ và cập nhật nó sau.
