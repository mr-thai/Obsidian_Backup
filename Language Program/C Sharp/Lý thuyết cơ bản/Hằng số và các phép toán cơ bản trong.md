## Hằng số
- là những giá trị không đổi trong suốt quá trình chạy code
- Gán tên cho giá trị hằng : `<const> <type> <tên hằng> = <Giá trị>`
```cs
	const int doSoiNuoc = 100;
```
- Không thể thay đổi giá trị của hằng số

## Các phép toán cơ bản
### **1. Phép toán số học**

|**Phép toán**|**Ký hiệu**|**Ý nghĩa**|**Ví dụ**|**Kết quả**|
|---|---|---|---|---|
|Cộng|`+`|Cộng hai giá trị|`5 + 3`|`8`|
|Trừ|`-`|Trừ giá trị thứ hai từ giá trị thứ nhất|`5 - 3`|`2`|
|Nhân|`*`|Nhân hai giá trị|`5 * 3`|`15`|
|Chia|`/`|Chia giá trị thứ nhất cho giá trị thứ hai|`5 / 2`|`2` (số nguyên)|
|Chia dư|`%`|Lấy phần dư của phép chia|`5 % 2`|`1`|
|Cộng đơn vị|`++`|Tăng giá trị lên 1|`x++` hoặc `++x`|`x + 1`|
|Trừ đơn vị|`--`|Giảm giá trị đi 1|`x--` hoặc `--x`|`x - 1`|
- Với cộng đơn vị và trừ đơn vị thì có hai trường hợp là [[Prefix và Postfix]]
---

### **2. Phép toán so sánh**

| **Phép toán**     | **Ký hiệu** | **Ý nghĩa**                                 | **Ví dụ** | **Kết quả** |
| ----------------- | ----------- | ------------------------------------------- | --------- | ----------- |
| Bằng nhau         | `==         | Kiểm tra hai giá trị có bằng nhau           | `5 == 3`  | `false`     |
| Không bằng        | `!=`        | Kiểm tra hai giá trị không bằng nhau        | `5 != 3`  | `true`      |
| Lớn hơn           | `>`         | Kiểm tra giá trị thứ nhất lớn hơn           | `5 > 3`   | `true`      |
| Nhỏ hơn           | `<`         | Kiểm tra giá trị thứ nhất nhỏ hơn           | `5 < 3`   | `false`     |
| Lớn hơn hoặc bằng | `>=`        | Kiểm tra giá trị thứ nhất lớn hơn hoặc bằng | `5 >= 5`  | `true`      |
| Nhỏ hơn hoặc bằng | `<=`        | Kiểm tra giá trị thứ nhất nhỏ hơn hoặc bằng | `3 <= 5`  | `true`      |

---

### **3. Phép toán logic**

| **Phép toán**   | **Ký hiệu** | **Ý nghĩa**                             | **Ví dụ**            | **Kết quả**                                    |
| --------------- | ----------- | --------------------------------------- | -------------------- | ---------------------------------------------- |
| Và (Logic AND)  | `&&`        | Trả về `true` nếu cả hai điều kiện đúng | `(5 > 3) && (4 > 2)` | `true`                                         |
| Hoặc (Logic OR) | \|\|        |                                         | \|\|                 | Trả về `true` nếu một trong hai điều kiện đúng |
| Phủ định (NOT)  | `!`         | Đảo ngược giá trị logic                 | `!(5 > 3)`           | `false`                                        |

---

### **4. Phép gán**

|**Phép toán**|**Ký hiệu**|**Ý nghĩa**|**Ví dụ**|**Kết quả**|
|---|---|---|---|---|
|Gán|`=`|Gán giá trị cho biến|`x = 5`|`x = 5`|
|Gán cộng|`+=`|Cộng giá trị và gán|`x += 3`|`x = x + 3`|
|Gán trừ|`-=`|Trừ giá trị và gán|`x -= 2`|`x = x - 2`|
|Gán nhân|`*=`|Nhân giá trị và gán|`x *= 2`|`x = x * 2`|
|Gán chia|`/=`|Chia giá trị và gán|`x /= 2`|`x = x / 2`|
|Gán chia dư|`%=`|Lấy phần dư và gán|`x %= 2`|`x = x % 2`|

---

### **5. Phép toán khác**

|**Phép toán**|**Ký hiệu**|**Ý nghĩa**|**Ví dụ**|**Kết quả**|
|---|---|---|---|---|
|Toán tử điều kiện|`? :`|Trả về giá trị dựa trên điều kiện (toán tử 3 ngôi)|`(5 > 3) ? 1 : 0`|`1`|
|Kiểm tra kiểu|`is`|Kiểm tra xem một đối tượng có phải là kiểu dữ liệu cụ thể hay không|`x is int`|`true/false`|
|Toán tử null-coalescing|`??`|Trả về giá trị đầu tiên không null trong danh sách|`x ?? y`|`x` (nếu x khác null)|
## Ưu tiên toán tử
**thứ tự ưu tiên các toán tử** trong C#, từ cao nhất đến thấp nhất. Mỗi toán tử trong một nhóm có cùng độ ưu tiên và được thực hiện từ **trái sang phải** hoặc **phải sang trái**, tùy thuộc vào tính chất kết hợp (associativity).
### **Bảng ưu tiên toán tử trong C#**

| **Mức ưu tiên**    | **Toán tử**                                | **Ý nghĩa**                                                        | **Kết hợp**                           |     |
| ------------------ | ------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------- | --- |
| **1 (Cao nhất)**   | `++`, `--`                                 | **Tăng, giảm đơn vị (Prefix/Postfix)**                             | **Trái sang phải**                    |     |
|                    | `+`, `-`                                   | **Unary plus/minus (dấu dương, dấu âm)**                           | **Phải sang trái**                    |     |
|                    | `!`, `~`                                   | **NOT logic, bitwise complement**                                  | **Phải sang trái**                    |     |
|                    | `(type)`                                   | **Ep kiểu (Type casting)**                                         | **Phải sang trái**                    |     |
|                    | `sizeof`, `typeof`, `checked`, `unchecked` | **Toán tử kích thước, kiểu, kiểm tra/không kiểm tra tràn số**      | **Phải sang trái**                    |     |
|                    | `new`, `delegate`                          | **Khởi tạo đối tượng, khai báo delegate**                          | **Phải sang trái**                    |     |
|                    | `->`, `.`                                  | **Truy cập thành phần hoặc đối tượng con**                         | **Trái sang phải**                    |     |
| **2**              | `*`, `/`, `%`                              | **Nhân, chia, chia dư**                                            | **Trái sang phải**                    |     |
| **3**              | `+`, `-`                                   | **Cộng, trừ**                                                      | **Trái sang phải**                    |     |
|                    | `<<`, `>>`                                 | **Dịch trái, dịch phải (Bitwise)**                                 | **Trái sang phải**                    |     |
| **4**              | `<`, `<=`, `>`, `>=`                       | **So sánh lớn hơn, nhỏ hơn, lớn hơn hoặc bằng, nhỏ hơn hoặc bằng** | **Trái sang phải**                    |     |
|                    | `is`, `as`                                 | **Kiểm tra kiểu (is), chuyển đổi kiểu có thể null (as)**           | **Trái sang phải**                    |     |
| **5**              | $==$, $!=$                                 | **So sánh bằng, không bằng**                                       | **Trái sang phải**                    |     |
| **6**              | `&`                                        | **Phép AND bit**                                                   | **Trái sang phải**                    |     |
| **7**              | `^`                                        | **Phép XOR bit**                                                   | **Trái sang phải**                    |     |
| **8**              | \|                                         | **OR bit**                                                         | **Phép OR bit**                       |     |
| **9**              | `&&`                                       | **Phép AND logic**                                                 | **Trái sang phải**                    |     |
| **10**             | \|\|                                       | **OR logic**                                                       | **Phép OR logic**                     |     |
| **11**             | `?:`                                       | **Toán tử 3 ngôi (Conditional Operator)**                          | **Phải sang trái**                    |     |
| **12**             | `=`, `+=`, `-=`, `*=`, `/=`, `%=`, `&=`, ` | =`,` ^=`,` <<=`,` >>=`                                             | **Toán tử gán (bao gồm gán kết hợp)** |     |
| **13 (Thấp nhất)** | `,`                                        | **Toán tử phân tách biểu thức (comma operator)**                   | **Trái sang phải**                    |     |

---

### **Ghi chú quan trọng:**

1. **Tính kết hợp trái/phải:**
    
    - Toán tử **trái sang phải**: Các biểu thức được thực hiện từ trái qua phải.
    - Toán tử **phải sang trái**: Các biểu thức được thực hiện từ phải qua trái.
2. **Nhóm ưu tiên cao nhất:**  
    Các toán tử như `++`, `--`, `!` có ưu tiên cao nhất và được thực thi trước hầu hết các toán tử khác.
    
3. **Toán tử 3 ngôi (`?:`)** và các toán tử gán ($`=`, `+=`, `-=`...$) có **ưu tiên thấp**, nghĩa là chúng được thực hiện sau các phép toán khác.
    
4. **Toán tử logic (`&&`, `||`)** có ưu tiên thấp hơn các phép toán so sánh ($`==`, `!=`, `<`, `>`$) nhưng cao hơn toán tử gán.
    

---

### **Ví dụ minh họa:**

```csharp
int x = 5, y = 10, z = 0;

// Toán tử ưu tiên: Nhân (*) trước Cộng (+)
z = x + y * 2; // z = 5 + (10 * 2) = 25

// Toán tử 3 ngôi (?:) có ưu tiên thấp hơn so với nhân (*)
z = (x > y) ? x * 2 : y * 3; // z = 10 * 3 = 30

// Toán tử gán (=) thực hiện sau tất cả các toán tử khác
z = x + y; // z = (5 + 10) = 15
```
