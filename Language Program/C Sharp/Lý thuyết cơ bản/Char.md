### **Kiểu dữ liệu `char` trong C# (Đầy đủ và chi tiết)**

Kiểu dữ liệu `char` trong C# dùng để lưu trữ một **ký tự Unicode** (định dạng UTF-16). Nó là kiểu dữ liệu giá trị (value type) và chiếm 2 byte (16-bit) bộ nhớ. `char` có phạm vi giá trị từ `\u0000` (0) đến `\uFFFF` (65,535).

---

### **1. Khởi tạo `char`**

Bạn có thể khởi tạo một biến `char` theo các cách sau:

```csharp
char c1 = 'A';               // Một ký tự thông thường
char c2 = '\u0041';          // Sử dụng mã Unicode
char c3 = '\n';              // Ký tự thoát (newline)
char c4 = (char)65;          // Ép kiểu từ số nguyên sang ký tự
```

---

### **2. Ép kiểu và chuyển đổi `char`**

#### Ép kiểu sang `int` (mã Unicode của ký tự):

```csharp
char c = 'A';
int unicodeValue = (int)c; // Giá trị là 65
```

#### Ép kiểu từ `int` sang `char`:

```csharp
int unicodeValue = 65;
char c = (char)unicodeValue; // Giá trị là 'A'
```

#### Chuyển ký tự số (`char`) sang số nguyên:

```csharp
char digit = '5';
int number = digit - '0'; // Giá trị là 5
```

#### Sử dụng phương thức để lấy giá trị số thực từ ký tự số:

```csharp
char digit = '5';
double numericValue = Char.GetNumericValue(digit); // Giá trị là 5.0
```

---

### **3. So sánh hai ký tự**

#### So sánh trực tiếp:

```csharp
char c1 = 'A';
char c2 = 'B';

bool isEqual = c1 == c2;  // False
bool isNotEqual = c1 != c2; // True
bool isGreater = c1 > c2; // False
bool isLess = c1 < c2;    // True
```

#### So sánh không phân biệt hoa/thường:

```csharp
char c1 = 'A';
char c2 = 'a';

bool isEqualIgnoreCase = Char.ToLower(c1) == Char.ToLower(c2); // True
```

---

### **4. Các phương thức kiểm tra trong lớp `Char`**

| **Phương thức**            | **Mô tả**                                                             |
| -------------------------- | --------------------------------------------------------------------- |
| `Char.IsLetter(char)`      | Kiểm tra ký tự có phải là chữ không (`A-Z`, `a-z`).                   |
| `Char.IsDigit(char)`       | Kiểm tra ký tự có phải là số không (`0-9`).                           |
| `Char.IsWhiteSpace(char)`  | Kiểm tra ký tự có phải là khoảng trắng không (space, tab, newline).   |
| `Char.IsUpper(char)`       | Kiểm tra ký tự có phải là chữ in hoa không.                           |
| `Char.IsLower(char)`       | Kiểm tra ký tự có phải là chữ in thường không.                        |
| `Char.IsControl(char)`     | Kiểm tra ký tự có phải là ký tự điều khiển không (control character). |
| `Char.IsSymbol(char)`      | Kiểm tra ký tự có phải là ký tự ký hiệu không (ví dụ: `$`, `@`, `#`). |
| `Char.IsPunctuation(char)` | Kiểm tra ký tự có phải là ký tự dấu câu không (ví dụ: `,`, `.`, `;`). |

**Ví dụ:**

```csharp
char c = 'A';
Console.WriteLine(Char.IsLetter(c));      // True
Console.WriteLine(Char.IsDigit(c));       // False
Console.WriteLine(Char.IsUpper(c));       // True
Console.WriteLine(Char.IsLower(c));       // False
Console.WriteLine(Char.IsWhiteSpace(' '));// True
```

---

### **5. Chuyển đổi ký tự**

|**Phương thức**|**Mô tả**|
|---|---|
|`Char.ToUpper(char)`|Chuyển ký tự sang chữ in hoa.|
|`Char.ToLower(char)`|Chuyển ký tự sang chữ in thường.|
|`Char.GetNumericValue(char)`|Chuyển ký tự số sang giá trị số thực.|

**Ví dụ:**

```csharp
char c = 'a';

Console.WriteLine(Char.ToUpper(c));       // 'A'
Console.WriteLine(Char.ToLower('B'));     // 'b'
Console.WriteLine(Char.GetNumericValue('7')); // 7.0
```

---

### **6. Duyệt qua chuỗi sử dụng `char`**

Bạn có thể duyệt qua từng ký tự trong chuỗi bằng `foreach` hoặc chỉ mục:

#### Sử dụng `foreach`:

```csharp
string str = "Hello";
foreach (char c in str)
{
    Console.WriteLine(c);
}
```

#### Sử dụng chỉ mục:

```csharp
string str = "World";
for (int i = 0; i < str.Length; i++)
{
    Console.WriteLine(str[i]);
}
```

---

### **7. Làm việc với mã Unicode**

#### Hiển thị mã Unicode:

```csharp
char c = 'A';
int unicode = (int)c;
Console.WriteLine($"Mã Unicode của '{c}' là {unicode}"); // 65
```

#### Tạo ký tự từ mã Unicode:

```csharp
int unicodeValue = 65;
char c = (char)unicodeValue;
Console.WriteLine($"Ký tự từ mã Unicode {unicodeValue} là '{c}'"); // 'A'
```

#### Ký tự Unicode sử dụng `\u`:

```csharp
char unicodeChar = '\u0041'; // Mã Unicode của 'A'
Console.WriteLine(unicodeChar); // 'A'
```

---

### **8. Ký tự thoát (`escape characters`)**

|**Ký tự thoát**|**Ý nghĩa**|
|---|---|
|`\n`|Xuống dòng (newline)|
|`\t`|Tab ngang|
|`\\`|Dấu gạch chéo ngược (`\`)|
|`\'`|Dấu nháy đơn (`'`)|
|`\"`|Dấu nháy kép (`"`)|
|`\r`|Trở về đầu dòng (carriage return)|
|`\b`|Backspace|
|`\f`|Form feed|
|`\0`|Ký tự null|

**Ví dụ:**

```csharp
string str = "Hello\nWorld";
Console.WriteLine(str);
```

---

### **9. Tổng hợp: Ví dụ toàn diện**

```csharp
using System;

class Program
{
    static void Main()
    {
        // Khởi tạo
        char letter = 'A';
        char digit = '7';
        char whitespace = ' ';
        
        // Kiểm tra
        Console.WriteLine(Char.IsLetter(letter));      // True
        Console.WriteLine(Char.IsDigit(digit));        // True
        Console.WriteLine(Char.IsWhiteSpace(whitespace)); // True

        // Chuyển đổi
        Console.WriteLine(Char.ToLower(letter));       // 'a'
        Console.WriteLine(Char.ToUpper('b'));          // 'B'
        Console.WriteLine(Char.GetNumericValue(digit));// 7.0

        // So sánh
        char c1 = 'A';
        char c2 = 'a';
        Console.WriteLine(c1 == c2);                  // False
        Console.WriteLine(Char.ToLower(c1) == c2);    // True

        // Mã Unicode
        Console.WriteLine((int)letter);               // 65
        Console.WriteLine((char)65);                  // 'A'
        
        // Duyệt chuỗi
        string str = "Hello";
        foreach (char c in str)
        {
            Console.WriteLine(c);
        }
    }
}
```

---

### **10. Lưu ý**

- **Phân biệt `char` và `string`:** `char` là một ký tự duy nhất, trong khi `string` là một chuỗi ký tự.
- **Ký tự số không phải là số nguyên:** `'5'` không phải là số 5, cần chuyển đổi nếu muốn dùng như số nguyên.
- **Sử dụng đúng ký tự thoát trong chuỗi:** Ví dụ, `'\n'` cho newline hoặc `'\t'` cho tab ngang.
