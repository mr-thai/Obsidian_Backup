Câu lệnh `:(){ :|:& };:` là một dạng **fork bomb** — một loại **mã độc đơn giản nhưng nguy hiểm** trong Unix/Linux, được viết rất ngắn gọn nhưng có thể gây **sập hệ thống chỉ trong vài giây** nếu được thực thi.

---

## 🧨 Giải thích chi tiết

```bash
:(){ :|:& };:
```

Từng phần được phân tích như sau:

### 1. `:()`

Đây là cách định nghĩa một **hàm có tên là `:`** trong Bash.

- `:` là tên hợp lệ cho một hàm.
    
- Dấu `()` cho thấy đây là một hàm không có tham số.
    

### 2. `{ :|:& }`

Đây là **thân của hàm**, nghĩa là khi gọi `:`, nó sẽ thực hiện:

- `:|:`  
    → Gọi chính nó hai lần, qua `pipe` (`|`).  
    → `:` gọi `:` (chính nó), rồi đẩy kết quả sang một bản khác cũng gọi `:` → **tạo 2 tiến trình con** mỗi lần gọi.
    
- `&`  
    → Thực hiện trong nền (**background**), để không chờ kết thúc rồi mới gọi tiếp → **tạo fork không giới hạn**.
    

### 3. `;`

Kết thúc phần định nghĩa hàm.

### 4. `:`

Gọi hàm `:` lần đầu tiên → bắt đầu quá trình **nhân bản vô hạn**.

---

## 💥 Tác hại

Khi bạn chạy lệnh này:

- Hệ thống bắt đầu **tạo vô hạn tiến trình**.
    
- Vì không có giới hạn, sẽ nhanh chóng **làm đầy bảng tiến trình**.
    
- Kết quả:
    
    - Hệ thống trở nên **chậm chạp hoặc treo hoàn toàn**.
        
    - Bạn **không thể mở terminal mới hoặc chạy lệnh gì khác**.
        
    - Chỉ còn cách **khởi động lại (hard reset)**.
        

---

## 🔐 Phòng tránh

- Không chạy bất kỳ dòng lệnh nào mà bạn **không hiểu rõ**.
    
- **Vô hiệu hoá quyền thực thi** với người dùng không tin cậy.
    
- Dùng các giới hạn hệ thống như:
    
    ```bash
    ulimit -u 100
    ```
    
    để giới hạn số tiến trình mỗi user (hữu ích khi test trên máy ảo).
    

---

## 📌 Kết luận

- `:(){ :|:& };:` là một **fork bomb** nguy hiểm, lợi dụng khả năng tự gọi để đánh sập hệ thống bằng cách tạo hàng loạt tiến trình.
    
- Tuy đơn giản, nó **có thể làm tê liệt server hoặc máy tính** nếu người dùng không biết.
    
- Hãy cực kỳ **cẩn trọng với shell code ngắn gọn lạ lùng**, nhất là từ các nguồn không rõ ràng.
    
