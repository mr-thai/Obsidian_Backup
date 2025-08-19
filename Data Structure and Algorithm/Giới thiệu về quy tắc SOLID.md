### 1. **Single Responsibility Principle (SRP) - Nguyên tắc trách nhiệm duy nhất**

**Định nghĩa:**  
Mỗi class chỉ nên có **một nhiệm vụ duy nhất**, và chỉ có **một lý do duy nhất** để thay đổi.

**Ví dụ sai:**
```cpp
class ReportManager {
    void generateReport(string data);  // Tạo báo cáo
    void saveReportToFile(string path);  // Lưu báo cáo vào file
    void sendReportToEmail(string email);  // Gửi báo cáo qua email
};
```
Class này làm quá nhiều việc (tạo báo cáo, lưu file, gửi email), dẫn đến khó bảo trì.

**Ví dụ đúng:**  
Tách từng nhiệm vụ ra các class riêng:
```cpp
class ReportGenerator {
    void generateReport(string data);  // Tạo báo cáo
};

class FileSaver {
    void saveToFile(string path);  // Lưu file
};

class EmailSender {
    void sendEmail(string email);  // Gửi email
};
```
Khi đó, nếu bạn muốn thay đổi cách gửi email, bạn chỉ cần sửa `EmailSender` mà không ảnh hưởng đến `ReportGenerator` hay `FileSaver`.

---

### 2. **Open/Closed Principle (OCP) - Nguyên tắc đóng/mở**

**Định nghĩa:**  
Không nên chỉnh sửa lại code đã có sẵn (chạy tốt rồi) mà hãy viết sao cho class con có tính kế thừa từ class cha mà không ảnh hưởng gì đến class cha

**Ví dụ sai:**  
```cpp
class AccountManager {
    void calculateInterest(string accountType) {
        if (accountType == "Savings") {
            // Tính lãi suất cho tài khoản tiết kiệm
        } else if (accountType == "Current") {
            // Tính lãi suất cho tài khoản thanh toán
        }
    }
};
```
Khi thêm loại tài khoản mới (ví dụ: "Fixed Deposit"), bạn phải sửa code trong `AccountManager`.

**Ví dụ đúng:**  
Sử dụng abstraction (trừu tượng hóa) và kế thừa:
```cpp
class Account {
    virtual void calculateInterest() = 0;  // Abstract method
};

class SavingsAccount : public Account {
    void calculateInterest() override {
        // Tính lãi suất cho tài khoản tiết kiệm
    }
};

class CurrentAccount : public Account {
    void calculateInterest() override {
        // Tính lãi suất cho tài khoản thanh toán
    }
};
```
Khi thêm loại tài khoản mới, chỉ cần tạo class mới kế thừa từ `Account`, không phải sửa code cũ.

---

### 3. **Liskov Substitution Principle (LSP) - Nguyên tắc thay thế Liskov**

**Định nghĩa:**  
Lớp con phải có thể thay thế lớp cha mà không làm thay đổi cách hoạt động của chương trình.

**Ví dụ sai:**  
```cpp
class Bird {
    virtual void fly() = 0;  // Mọi loài chim đều bay?
};

class Penguin : public Bird {
    void fly() override {
        throw "Penguins không bay được!";
    }
};
```
Penguin vi phạm nguyên tắc LSP vì nó không phù hợp với hành vi của lớp cha `Bird`.

**Ví dụ đúng:**  
Tách riêng hành vi bay:
```cpp
class Bird {};

class FlyingBird : public Bird {
    virtual void fly() = 0;
};

class Sparrow : public FlyingBird {
    void fly() override {
        // Chim sẻ có thể bay
    }
};

class Penguin : public Bird {
    // Không cần phương thức bay
};
```

---

### 4. **Interface Segregation Principle (ISP) - Nguyên tắc phân tách giao diện**

**Định nghĩa:**  
Một class không nên thực thi những phương thức mà nó không dùng đếnđến.

**Ví dụ sai:**  
```cpp
class Machine {
    virtual void print() = 0;
    virtual void scan() = 0;
    virtual void fax() = 0;
};
```
Nếu một class chỉ là **máy in**, nó vẫn phải cài đặt các phương thức `scan` và `fax` dù không cần dùng.

**Ví dụ đúng:**  
Tách nhỏ các giao diện:
```cpp
class Printer {
    virtual void print() = 0;
};

class Scanner {
    virtual void scan() = 0;
};

class Fax {
    virtual void fax() = 0;
};
```
Bây giờ, một class chỉ cần thực thi giao diện mà nó cần.

---

### 5. **Dependency Inversion Principle (DIP) - Nguyên tắc đảo ngược phụ thuộc**

**Định nghĩa:**  
Module cấp cao không nên phụ thuộc vào module cấp thấp, cả hai nên phụ thuộc vào abstraction (trừu tượng hóa).

**Giải thích dễ hiểu:**  
Thay vì phụ thuộc vào những chi tiết cụ thể (như một loại cơ sở dữ liệu), code nên phụ thuộc vào abstraction (như interface) để dễ dàng thay đổi hoặc mở rộng.

**Ví dụ sai:**  
```cpp
class MySQLDatabase {
    void saveData(string data) {
        // Lưu dữ liệu vào MySQL
    }
};

class Application {
    MySQLDatabase db;  // Phụ thuộc vào MySQL
    void save(string data) {
        db.saveData(data);
    }
};
```
Nếu bạn muốn chuyển sang sử dụng MongoDB, bạn phải sửa rất nhiều code.

**Ví dụ đúng:**  
Sử dụng interface:
```cpp
class IDataBase {
    virtual void saveData(string data) = 0;
};

class MySQLDatabase : public IDataBase {
    void saveData(string data) override {
        // Lưu dữ liệu vào MySQL
    }
};

class MongoDB : public IDataBase {
    void saveData(string data) override {
        // Lưu dữ liệu vào MongoDB
    }
};

class Application {
    IDataBase* db;  // Phụ thuộc vào abstraction
    Application(IDataBase* database) : db(database) {}

    void save(string data) {
        db->saveData(data);
    }
};
```
Bạn có thể thay đổi cơ sở dữ liệu mà không cần sửa code `Application`.

