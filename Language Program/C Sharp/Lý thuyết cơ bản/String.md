## **Phần 1: Khái niệm cơ bản về String trong C#**

### 1. **String là gì?**

- Trong C#, `string` là một kiểu dữ liệu tham chiếu (reference type) dùng để lưu trữ chuỗi ký tự Unicode.
- Chuỗi trong C# là **immutable** (bất biến), nghĩa là khi một chuỗi được tạo ra, nó không thể thay đổi. Mọi thao tác chỉnh sửa trên chuỗi sẽ tạo ra một đối tượng mới.

#### **Khai báo chuỗi**

```csharp
string str1 = "Hello, World!"; // Chuỗi ký tự
string str2 = string.Empty;   // Chuỗi rỗng
string str3 = null;           // Giá trị null (không chứa gì)
```

#### **So sánh chuỗi**

- So sánh hai chuỗi trong C# là phân biệt hoa thường:

```csharp
string str1 = "Hello";
string str2 = "hello";

Console.WriteLine(str1 == str2); // False
```

#### **Chuỗi rỗng (`Empty`) và `null`**

- Chuỗi rỗng (`""` hoặc `string.Empty`) khác với `null`:

```csharp
string emptyString = "";
string nullString = null;

Console.WriteLine(string.IsNullOrEmpty(emptyString)); // True
Console.WriteLine(string.IsNullOrEmpty(nullString));  // True
```

---

### 2. **Các cách tạo chuỗi**

#### **Sử dụng dấu ngoặc kép (`"`)**

```csharp
string greeting = "Hello, C#!";
```

#### **Sử dụng ký tự đặc biệt**

- Trong chuỗi có thể chứa các ký tự đặc biệt như `\n`, `\t`, hoặc sử dụng `@` để không cần escape:

```csharp
string withEscape = "Line1\nLine2";   // Sử dụng escape sequence
string verbatim = @"C:\Program Files\MyApp"; // Chuỗi không cần escape
```

#### **Sử dụng nối chuỗi**

- Nối hai chuỗi với dấu `+` hoặc `String.Concat`:

```csharp
string firstName = "John";
string lastName = "Doe";
string fullName = firstName + " " + lastName; // Kết quả: "John Doe"
```

---

## **Phần 2: Các hàm xử lý String trong C#**

C# cung cấp rất nhiều phương thức tiện ích để xử lý chuỗi từ lớp `System.String`.

---

### 1. **Hàm kiểm tra và thao tác cơ bản**

|**Hàm**|**Công dụng**|**Ví dụ**|
|---|---|---|
|`string.IsNullOrEmpty()`|Kiểm tra chuỗi rỗng hoặc `null`.|`string.IsNullOrEmpty(""); // True`|
|`string.IsNullOrWhiteSpace()`|Kiểm tra chuỗi rỗng, `null` hoặc toàn khoảng trắng.|`string.IsNullOrWhiteSpace(" "); // True`|
|`Equals()`|So sánh hai chuỗi.|`"Hello".Equals("hello", StringComparison.OrdinalIgnoreCase); // True`|
|`Length`|Trả về độ dài chuỗi.|`"Hello".Length; // 5`|

---

### 2. **Hàm chuyển đổi chuỗi**

|**Hàm**|**Công dụng**|**Ví dụ**|
|---|---|---|
|`ToUpper()`|Chuyển chuỗi thành chữ in hoa.|`"hello".ToUpper(); // "HELLO"`|
|`ToLower()`|Chuyển chuỗi thành chữ thường.|`"HELLO".ToLower(); // "hello"`|
|`Trim()`|Loại bỏ khoảng trắng ở đầu và cuối chuỗi.|`" hello ".Trim(); // "hello"`|
|`TrimStart()`|Loại bỏ khoảng trắng ở đầu chuỗi.|`" hello".TrimStart(); // "hello"`|
|`TrimEnd()`|Loại bỏ khoảng trắng ở cuối chuỗi.|`"hello ".TrimEnd(); // "hello"`|

---

### 3. **Hàm tách và nối chuỗi**

| **Hàm**   | **Công dụng**                                         | **Ví dụ**                                               |
| --------- | ----------------------------------------------------- | ------------------------------------------------------- |
| `Split()` | Tách chuỗi thành mảng dựa trên ký tự phân cách.       | `"a,b,c".Split(','); // {"a", "b", "c"}`                |
| `Join()`  | Nối các phần tử mảng thành chuỗi với ký tự phân cách. | `string.Join("-", new[] { "a", "b", "c" }); // "a-b-c"` |

---

### 4. **Hàm thay thế và tìm kiếm chuỗi**

|**Hàm**|**Công dụng**|**Ví dụ**|
|---|---|---|
|`Replace()`|Thay thế chuỗi con bằng chuỗi mới.|`"hello".Replace("l", "x"); // "hexxo"`|
|`Contains()`|Kiểm tra chuỗi con có tồn tại không.|`"hello".Contains("ll"); // True`|
|`IndexOf()`|Trả về vị trí đầu tiên của chuỗi con.|`"hello".IndexOf("l"); // 2`|
|`LastIndexOf()`|Trả về vị trí cuối cùng của chuỗi con.|`"hello".LastIndexOf("l"); // 3`|

---

### 5. **Hàm cắt chuỗi**

|**Hàm**|**Công dụng**|**Ví dụ**|
|---|---|---|
|`Substring()`|Lấy chuỗi con từ vị trí xác định.|`"hello".Substring(1, 3); // "ell"`|

---

### 6. **Hàm kiểm tra bắt đầu/kết thúc**

|**Hàm**|**Công dụng**|**Ví dụ**|
|---|---|---|
|`StartsWith()`|Kiểm tra chuỗi có bắt đầu bằng chuỗi con không.|`"hello".StartsWith("he"); // True`|
|`EndsWith()`|Kiểm tra chuỗi có kết thúc bằng chuỗi con không.|`"hello".EndsWith("lo"); // True`|

---

### 7. **Hàm định dạng chuỗi**

#### **String.Format**

- Chèn giá trị vào chuỗi theo mẫu:

```csharp
string name = "John";
int age = 30;
string formatted = string.Format("Name: {0}, Age: {1}", name, age);
// Kết quả: "Name: John, Age: 30"
```

#### **$ (Interpolated String)**

- Dễ dùng hơn `String.Format`:

```csharp
string name = "John";
int age = 30;
string formatted = $"Name: {name}, Age: {age}";
// Kết quả: "Name: John, Age: 30"
```

##  **Phần 3: StringBuilder trong C#**
## **1. String và StringBuilder: Nên chọn khi nào?**

### **String (Immutable)**

- **Bất biến:** Mỗi khi thay đổi nội dung chuỗi, C# sẽ tạo ra một đối tượng chuỗi mới trong bộ nhớ, khiến hiệu năng giảm khi thao tác nhiều.
- **Thích hợp cho:** Các chuỗi ngắn hoặc ít thay đổi.

#### **Ví dụ:**

```csharp
string str = "Hello";
str += " World!"; // Tạo một đối tượng chuỗi mới
Console.WriteLine(str); // Kết quả: "Hello World!"
```

---

### **StringBuilder (Mutable)**

- **Có thể thay đổi:** Không tạo đối tượng mới khi thay đổi, mà chỉnh sửa trực tiếp nội dung.
- **Thích hợp cho:** Các chuỗi lớn, thao tác nhiều như thêm, xóa, chèn.

#### **Ví dụ:**

```csharp
using System.Text;

StringBuilder sb = new StringBuilder("Hello");
sb.Append(" World!"); // Thêm chuỗi
sb.Insert(6, "Beautiful "); // Chèn chuỗi tại vị trí 6
Console.WriteLine(sb.ToString()); // Kết quả: "Hello Beautiful World!"
```

---

## **2. Các phương pháp tìm kiếm chuỗi nâng cao**

### **Regex (Regular Expressions)**

- Regex được sử dụng để tìm kiếm hoặc xử lý chuỗi phức tạp.
- Nằm trong namespace `System.Text.RegularExpressions`.

#### **Ví dụ: Tìm email hợp lệ**

```csharp
using System.Text.RegularExpressions;

string input = "Email me at example@mail.com.";
string pattern = @"[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}";

Match match = Regex.Match(input, pattern);
if (match.Success) {
    Console.WriteLine($"Email hợp lệ: {match.Value}");
}
```

**Kết quả:**

```
Email hợp lệ: example@mail.com
```

---

## **3. Thao tác với mảng và danh sách chuỗi**

### **Nối chuỗi từ mảng (`Join`)**

```csharp
string[] words = { "C#", "is", "awesome" };
string sentence = string.Join(" ", words);
Console.WriteLine(sentence); // Kết quả: "C# is awesome"
```

### **Tách chuỗi thành mảng (`Split`)**

```csharp
string sentence = "C# is awesome";
string[] words = sentence.Split(' ');

foreach (var word in words) {
    Console.WriteLine(word);
}
// Kết quả:
// C#
// is
// awesome
```

---

## **4. Xử lý chuỗi với định dạng và văn hóa**

### **Định dạng số và ngày tháng**

C# hỗ trợ định dạng số và ngày tháng dựa trên văn hóa (`CultureInfo`).

#### **Định dạng số**

```csharp
double price = 12345.678;
Console.WriteLine(price.ToString("C")); // Kết quả: $12,345.68 (Culture mặc định)
```

#### **Định dạng ngày tháng**

```csharp
using System.Globalization;

DateTime today = DateTime.Now;
Console.WriteLine(today.ToString("dd/MM/yyyy")); // Kết quả: 22/01/2025
Console.WriteLine(today.ToString("MMMM dd, yyyy", CultureInfo.InvariantCulture)); // Kết quả: January 22, 2025
```

---

## **5. Tối ưu hóa xử lý chuỗi**

### **So sánh chuỗi không phân biệt hoa thường**

```csharp
string str1 = "Hello";
string str2 = "hello";

bool isEqual = str1.Equals(str2, StringComparison.OrdinalIgnoreCase);
Console.WriteLine(isEqual); // Kết quả: True
```

---

## **6. Các hàm bổ sung mạnh mẽ trong C#**

### **Remove**

Xóa một phần chuỗi từ vị trí chỉ định.

```csharp
string str = "Hello, World!";
string result = str.Remove(5); // Xóa từ vị trí 5 trở đi
Console.WriteLine(result); // Kết quả: "Hello"
```

---

### **PadLeft/PadRight**

Thêm ký tự vào đầu hoặc cuối chuỗi cho đủ độ dài.

```csharp
string str = "123";
Console.WriteLine(str.PadLeft(5, '0')); // Kết quả: "00123"
Console.WriteLine(str.PadRight(5, '*')); // Kết quả: "123**"
```

---

### **StartsWith/EndsWith với biểu thức logic**

```csharp
string url = "https://example.com";

if (url.StartsWith("https://")) {
    Console.WriteLine("Đây là một URL bảo mật.");
}

if (url.EndsWith(".com")) {
    Console.WriteLine("Đây là một domain .com.");
}
```

---

## **7. Tình huống thực tế**

### **Xây dựng hàm đảo ngược chuỗi**

```csharp
string ReverseString(string input) {
    char[] charArray = input.ToCharArray();
    Array.Reverse(charArray);
    return new string(charArray);
}

Console.WriteLine(ReverseString("Hello")); // Kết quả: "olleH"
```

### **Tạo chuỗi JSON từ dữ liệu**

```csharp
using System.Text.Json;

var data = new {
    Name = "John",
    Age = 30
};

string json = JsonSerializer.Serialize(data);
Console.WriteLine(json); // Kết quả: {"Name":"John","Age":30}
```
