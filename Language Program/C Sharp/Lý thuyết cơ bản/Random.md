### **1. Cách sử dụng `Random`**

```csharp
using System;

class Program
{
    static void Main(string[] args)
    {
        Random random = new Random(); // Tạo một đối tượng Random

        // Số nguyên ngẫu nhiên
        int randomInt = random.Next(); // Sinh số nguyên dương từ 0 đến int.MaxValue
        Console.WriteLine("Số nguyên ngẫu nhiên: " + randomInt);

        // Số nguyên ngẫu nhiên trong khoảng [min, max)
        int randomInRange = random.Next(1, 10); // Sinh số nguyên từ 1 đến 9
        Console.WriteLine("Số nguyên trong khoảng [1, 10): " + randomInRange);

        // Số thực dấu phẩy động ngẫu nhiên trong khoảng [0.0, 1.0)
        double randomDouble = random.NextDouble();
        Console.WriteLine("Số thực dấu phẩy động [0.0, 1.0): " + randomDouble);

        // Số thực ngẫu nhiên trong khoảng [min, max)
        double randomRealInRange = randomDouble * (10 - 5) + 5; // Sinh số từ 5.0 đến 10.0
        Console.WriteLine("Số thực trong khoảng [5.0, 10.0): " + randomRealInRange);
    }
}
```

---

### **2. Các phương thức chính của lớp `Random`**

| **Phương thức**                    | **Công dụng**                                                                   | **Ví dụ**                                                               |
| ---------------------------------- | ------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `Next()`                           | Sinh số nguyên từ `0` đến `int.MaxValue`.                                       | `csharp<br>int val = random.Next();<br>`                                |
| `Next(int maxValue)`               | Sinh số nguyên từ `0` đến `maxValue - 1`.                                       | `csharp<br>int val = random.Next(10); // [0, 9]<br>`                    |
| `Next(int minValue, int maxValue)` | Sinh số nguyên từ `minValue` đến `maxValue - 1`.                                | `csharp<br>int val = random.Next(5, 15); // [5, 14]<br>`                |
| `NextDouble()`                     | Sinh số thực dấu phẩy động từ `0.0` đến `1.0` (bao gồm 0.0, không bao gồm 1.0). | `csharp<br>double val = random.NextDouble();<br>`                       |
| `NextBytes(byte[] buffer)`         | Sinh các giá trị byte ngẫu nhiên và lưu vào mảng `buffer`.                      | `csharp<br>byte[] bytes = new byte[4];<br>random.NextBytes(bytes);<br>` |

---

int randomInt = random.Next(10, 20); // Từ 10 đến 19
```

#### Số thực:

```csharp
double randomDouble = random.NextDouble() * (max - min) + min; // Trong khoảng [min, max)
```

---

### **4. Lưu ý khi sử dụng `Random`**

1. **Khởi tạo đối tượng `Random`:**
    
    - Không nên khởi tạo nhiều đối tượng `Random` liên tiếp trong thời gian ngắn, vì chúng dựa trên `System.Environment.TickCount` để tạo seed. Điều này có thể dẫn đến kết quả giống nhau.
    - Khởi tạo một lần và tái sử dụng:
        
        ```csharp
        static Random random = new Random();
        ```
        
2. **Seed tùy chỉnh:**
    
    - Nếu cần tái tạo chuỗi số ngẫu nhiên giống nhau, có thể cung cấp seed khi khởi tạo:
        
        ```csharp
        Random random = new Random(42); // Seed cố định
        ```
        
3. **Không sử dụng trong bảo mật:**
    
    - `Random` không phù hợp để sinh số ngẫu nhiên trong ứng dụng bảo mật. Thay vào đó, dùng lớp `RNGCryptoServiceProvider` trong `System.Security.Cryptography`.

---

### **5. Ví dụ ứng dụng thực tế**

#### Sinh mảng số nguyên ngẫu nhiên:

```csharp
int[] randomNumbers = new int[10];
for (int i = 0; i < randomNumbers.Length; i++)
{
    randomNumbers[i] = random.Next(1, 101); // [1, 100]
}
Console.WriteLine(string.Join(", ", randomNumbers));
```

#### Tung xúc xắc:

```csharp
int diceRoll = random.Next(1, 7); // [1, 6]
Console.WriteLine("Bạn đã tung được: " + diceRoll);
```
