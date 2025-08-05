| **Nhóm hàm**          | **Hàm**            | **Công dụng**                                             | **Cách dùng**                                                               | **Chú ý**                                                                            |
| --------------------- | ------------------ | --------------------------------------------------------- | --------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| **Số học cơ bản**     | `Math.Abs(x)`      | Tính giá trị tuyệt đối của `x`.                           | `csharp<br>int absValue = Math.Abs(-5);<br>// absValue = 5<br>`             | Dùng cho cả số nguyên và số thực.                                                    |
|                       | `Math.Max(x, y)`   | Trả về giá trị lớn nhất giữa `x` và `y`.                  | `csharp<br>double maxVal = Math.Max(3.5, 7.2);<br>// maxVal = 7.2<br>`      | Không giới hạn kiểu dữ liệu, miễn là cùng kiểu (int, double, float).                 |
|                       | `Math.Min(x, y)`   | Trả về giá trị nhỏ nhất giữa `x` và `y`.                  | `csharp<br>int minVal = Math.Min(10, 5);<br>// minVal = 5<br>`              | Tương tự như `Math.Max`.                                                             |
| **Làm tròn số**       | `Math.Round(x)`    | Làm tròn số `x` đến số nguyên gần nhất.                   | `csharp<br>double roundedVal = Math.Round(3.5);<br>// roundedVal = 4<br>`   | Làm tròn theo **MidpointRounding.ToEven** (mặc định).                                |
|                       | `Math.Floor(x)`    | Làm tròn xuống (trả về số nguyên nhỏ nhất ≤ `x`).         | `csharp<br>double floorVal = Math.Floor(3.7);<br>// floorVal = 3<br>`       | Luôn làm tròn xuống, không phụ thuộc vào phần thập phân.                             |
|                       | `Math.Ceiling(x)`  | Làm tròn lên (trả về số nguyên lớn nhất ≥ `x`).           | `csharp<br>double ceilVal = Math.Ceiling(3.2);<br>// ceilVal = 4<br>`       | Luôn làm tròn lên.                                                                   |
| **Hàm mũ và logarit** | `Math.Pow(x, y)`   | Tính `x` lũy thừa `y`.                                    | `csharp<br>double power = Math.Pow(2, 3);<br>// power = 8<br>`              | Kết quả luôn là kiểu `double`.                                                       |
|                       | `Math.Sqrt(x)`     | Tính căn bậc hai của `x`.                                 | `csharp<br>double sqrtVal = Math.Sqrt(16);<br>// sqrtVal = 4<br>`           | `x` phải không âm. Nếu `x < 0`, sẽ xảy ra lỗi.                                       |
|                       | `Math.Log(x)`      | Tính logarit tự nhiên cơ số `e` của `x`.                  | `csharp<br>double logVal = Math.Log(2.718);<br>// logVal ≈ 1<br>`           | `x` phải lớn hơn 0. Nếu không, sẽ xảy ra lỗi.                                        |
|                       | `Math.Exp(x)`      | Tính e^x.                                                 | `csharp<br>double expVal = Math.Exp(1);<br>// expVal ≈ 2.718<br>`           | Kết quả có thể rất lớn, dẫn đến tràn số.                                             |
| **Lượng giác**        | `Math.Sin(x)`      | Tính sin của góc `x` (đơn vị **radian**).                 | `csharp<br>double sinVal = Math.Sin(Math.PI / 2);<br>// sinVal = 1<br>`     | Góc đầu vào phải ở đơn vị radian. Sử dụng `Math.PI` để dễ dàng chuyển đổi.           |
|                       | `Math.Cos(x)`      | Tính cos của góc `x` (đơn vị **radian**).                 | `csharp<br>double cosVal = Math.Cos(0);<br>// cosVal = 1<br>`               | Tương tự như `Math.Sin`.                                                             |
|                       | `Math.Tan(x)`      | Tính tan của góc `x` (đơn vị **radian**).                 | `csharp<br>double tanVal = Math.Tan(Math.PI / 4);<br>// tanVal ≈ 1<br>`     | Với một số góc đặc biệt (như `π/2`), hàm này có thể trả về giá trị rất lớn.          |
| **Số ngẫu nhiên**     | `Math.Random()`    | Sinh số ngẫu nhiên từ 0.0 đến 1.0 (không bao gồm 1.0).    | Sử dụng class `Random` thay vì `Math`.                                      | Thực tế nên dùng `Random` để linh hoạt hơn (`Random.Next()`, `Random.NextDouble()`). |
| **Các hàm khác**      | `Math.Sign(x)`     | Trả về dấu của `x`: `-1` (âm), `0` (bằng 0), `1` (dương). | `csharp<br>int sign = Math.Sign(-5);<br>// sign = -1<br>`                   | Rất hữu ích để kiểm tra hướng hoặc dấu giá trị.                                      |
|                       | `Math.Truncate(x)` | Lấy phần nguyên của số `x`, loại bỏ phần thập phân.       | `csharp<br>double truncated = Math.Truncate(3.7);<br>// truncated = 3<br>`  | Khác với `Math.Floor`, nó chỉ bỏ phần thập phân mà không làm tròn.                   |
|                       | `Math.PI`          | Hằng số π (≈ 3.14159).                                    | `csharp<br>Console.WriteLine(Math.PI);<br>// Kết quả: 3.14159265358979<br>` | Thường dùng trong các phép toán lượng giác.                                          |
|                       | `Math.E`           | Hằng số e (≈ 2.71828).                                    | `csharp<br>Console.WriteLine(Math.E);<br>// Kết quả: 2.71828182845905<br>`  | Dùng trong tính toán lũy thừa và logarit.                                            |

---

### **Chú ý khi sử dụng thư viện `Math`:**

1. **Hiệu suất và kiểu dữ liệu:**
    
    - Các hàm `Math` luôn trả về kiểu `double`, ngay cả khi đầu vào là kiểu nguyên (`int`).
    - Chuyển đổi kiểu dữ liệu khi cần để tránh lỗi hoặc mất chính xác.
2. **Hạn chế giá trị đầu vào:**
    
    - Một số hàm như `Math.Sqrt` hoặc `Math.Log` yêu cầu đầu vào hợp lệ (`x ≥ 0` với căn bậc hai, `x > 0` với logarit).
    - Cần kiểm tra giá trị đầu vào trước khi sử dụng để tránh ngoại lệ.
3. **Đơn vị góc:**
    
    - Các hàm lượng giác như `Sin`, `Cos`, và `Tan` sử dụng góc tính bằng **radian**. Chuyển đổi từ độ sang radian bằng công thức:
        
        ```csharp
        double radians = degrees * (Math.PI / 180);
        ```
        
4. **Số thập phân lớn:**
    
    - Kết quả của một số hàm (như `Math.Pow`, `Math.Exp`) có thể dẫn đến tràn số khi giá trị đầu vào quá lớn.

