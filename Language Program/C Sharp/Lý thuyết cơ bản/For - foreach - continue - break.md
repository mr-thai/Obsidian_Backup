## **1. Vòng lặp `for`**

### **Cách hoạt động:**

- Sử dụng khi biết trước số lần lặp.
- Bao gồm 3 phần:
    1. **Khởi tạo:** Biến đếm bắt đầu.
    2. **Điều kiện:** Kiểm tra xem có tiếp tục lặp không.
    3. **Cập nhật:** Tăng/giảm giá trị biến đếm.

### **Cú pháp:**

```csharp
for (khởi_tạo; điều_kiện; cập_nhật)
{
    // Lệnh cần thực thi
}
```

### **Ví dụ:**

In các số từ 1 đến 5:

```csharp
for (int i = 1; i <= 5; i++)
{
    Console.WriteLine(i);
}
```

---

## **2. Vòng lặp `foreach`**

### **Cách hoạt động:**

- Sử dụng để duyệt qua tất cả phần tử trong một tập hợp (mảng, danh sách, v.v.).
- Đơn giản hơn `for` khi không cần quản lý chỉ số.

### **Cú pháp:**

```csharp
foreach (var phần_tử in tập_hợp)
{
    // Lệnh cần thực thi
}
```

### **Ví dụ:**

In từng phần tử trong mảng:

```csharp
string[] names = { "Alice", "Bob", "Charlie" };

foreach (string name in names)
{
    Console.WriteLine(name);
}
```

---

## **3. Lệnh `continue`**

### **Cách hoạt động:**

- Bỏ qua phần còn lại của vòng lặp hiện tại và chuyển sang lần lặp tiếp theo.

### **Cú pháp:**

```csharp
if (điều_kiện)
    continue;
```

### **Ví dụ:**

In các số từ 1 đến 10, bỏ qua số chẵn:

```csharp
for (int i = 1; i <= 10; i++)
{
    if (i % 2 == 0) 
        continue; // Bỏ qua số chẵn
    Console.WriteLine(i);
}
```

- **Kết quả:**
    
    ```
    1
    3
    5
    7
    9
    ```
    

---

## **4. Lệnh `break`**

### **Cách hoạt động:**

- Dừng vòng lặp ngay lập tức, thoát ra ngoài.

### **Cú pháp:**

```csharp
if (điều_kiện)
    break;
```

### **Ví dụ:**

Dừng vòng lặp khi gặp số lớn hơn 5:

```csharp
for (int i = 1; i <= 10; i++)
{
    if (i > 5) 
        break; // Dừng vòng lặp
    Console.WriteLine(i);
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

## **So sánh `for` và `foreach`**

| Đặc điểm           | `for`                                  | `foreach`                                         |
| ------------------ | -------------------------------------- | ------------------------------------------------- |
| **Cách sử dụng**   | Lặp với chỉ số hoặc điều kiện cụ thể.  | Lặp qua tất cả phần tử trong tập hợp.             |
| **Quản lý chỉ số** | Có thể sử dụng chỉ số (`i`, `j`, v.v.) | Không có chỉ số.                                  |
| **Đơn giản**       | Ít đơn giản hơn.                       | Đơn giản hơn, tránh lỗi khi thao tác với tập hợp. |
| **Hiệu suất**      | Nhanh hơn với mảng lớn.                | Có thể chậm hơn trong một số trường hợp.          |

---

## **Ứng dụng của `continue` và `break`**

1. **`continue`:**
    - Sử dụng khi cần bỏ qua phần còn lại của vòng lặp nhưng vẫn tiếp tục lặp.
2. **`break`:**
    - Sử dụng khi cần thoát khỏi vòng lặp ngay lập tức.

---

## **Ví dụ kết hợp tất cả**

In số từ 1 đến 10, bỏ qua số chẵn, và dừng nếu gặp số lớn hơn 7:

```csharp
for (int i = 1; i <= 10; i++)
{
    if (i % 2 == 0) 
        continue; // Bỏ qua số chẵn

    if (i > 7) 
        break; // Dừng vòng lặp

    Console.WriteLine(i);
}
```

- **Kết quả:**
    
    ```
    1
    3
    5
    7
    ```
    
