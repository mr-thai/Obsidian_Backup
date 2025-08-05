### **1. `if-else`**

Cấu trúc này bao gồm:

- **if:** Kiểm tra một điều kiện. Nếu điều kiện đúng (`true`), khối lệnh trong `if` sẽ được thực thi.
- **else:** Được thực thi nếu điều kiện trong `if` không đúng (`false`).

#### **Cú pháp:**

```csharp
if (điều kiện)
{
    // Lệnh được thực thi nếu điều kiện là true
}
else
{
    // Lệnh được thực thi nếu điều kiện là false
}
```

#### **Ví dụ:**

```csharp
int score = 80;

if (score >= 50)
{
    Console.WriteLine("Đậu!");
}
else
{
    Console.WriteLine("Rớt!");
}
```

- Kết quả: Nếu `score` lớn hơn hoặc bằng 50, in "Đậu!", ngược lại in "Rớt!".

---

### **2. `else if`**

- Được sử dụng khi bạn muốn kiểm tra nhiều điều kiện khác nhau.
- Khi gặp một điều kiện đúng (`true`), các khối `else if` hoặc `else` sau đó sẽ không được kiểm tra nữa.

#### **Cú pháp:**

```csharp
if (điều kiện 1)
{
    // Lệnh được thực thi nếu điều kiện 1 là true
}
else if (điều kiện 2)
{
    // Lệnh được thực thi nếu điều kiện 1 là false và điều kiện 2 là true
}
else
{
    // Lệnh được thực thi nếu tất cả các điều kiện trên đều là false
}
```

#### **Ví dụ:**

```csharp
int score = 75;

if (score >= 85)
{
    Console.WriteLine("Xuất sắc!");
}
else if (score >= 65)
{
    Console.WriteLine("Khá!");
}
else
{
    Console.WriteLine("Trung bình!");
}
```

- Kết quả:
    - Nếu `score >= 85`, in "Xuất sắc!".
    - Nếu `score >= 65` nhưng nhỏ hơn 85, in "Khá!".
    - Nếu không thỏa mãn cả hai điều kiện trên, in "Trung bình!".

---

### **So sánh `if-else` và `else if`:**

|**Đặc điểm**|**if-else**|**else if**|
|---|---|---|
|**Số lượng điều kiện**|Xử lý một điều kiện chính và một trường hợp còn lại.|Xử lý nhiều điều kiện khác nhau.|
|**Độ phức tạp**|Đơn giản, ít phân nhánh.|Phức tạp hơn, nhiều nhánh kiểm tra.|
|**Thực thi**|Luôn kiểm tra 2 nhánh (nếu `if` sai, kiểm tra `else`).|Kiểm tra tuần tự, dừng lại khi gặp điều kiện đúng.|
|**Ứng dụng**|Thích hợp cho các quyết định 2 lựa chọn.|Phù hợp khi có nhiều trường hợp cần xử lý với điều kiện khác nhau.|

---

### **Ghi chú quan trọng:**

- **Thứ tự kiểm tra:** Trong cấu trúc `else if`, các điều kiện được kiểm tra từ trên xuống dưới. Nếu gặp điều kiện đúng, các điều kiện sau sẽ bị bỏ qua.
- **Lồng ghép `if`:** Bạn có thể lồng nhiều `if` vào nhau để kiểm tra các điều kiện phức tạp.
- **Toán tử logic:** Dùng các toán tử như `&&`, `||` trong điều kiện để kết hợp nhiều logic.

#### **Ví dụ phức tạp:**

```csharp
int age = 20;
bool isStudent = true;

if (age >= 18 && isStudent)
{
    Console.WriteLine("Bạn là sinh viên trưởng thành!");
}
else if (age < 18 && isStudent)
{
    Console.WriteLine("Bạn là sinh viên nhỏ tuổi!");
}
else
{
    Console.WriteLine("Bạn không phải là sinh viên!");
}
```
