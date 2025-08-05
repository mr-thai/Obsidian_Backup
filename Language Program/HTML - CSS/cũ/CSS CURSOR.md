Thuộc tính `cursor` trong CSS được sử dụng để chỉ định kiểu dáng của con trỏ chuột khi nó di chuyển qua các phần tử HTML. Đây là một cách tạo hiệu ứng trực quan, giúp cải thiện trải nghiệm người dùng. Dưới đây là chi tiết về các giá trị của thuộc tính này:

---
Tìm hiểu chi tiết tại : [CSS cursor Property](https://www.w3schools.com/cssref/tryit.php?filename=trycss_cursor)
### **Cú pháp**

```css
cursor: value;
```

### **Giá trị phổ biến**

1. **default**
    
    - Hình dáng con trỏ mặc định của trình duyệt (thường là mũi tên).
    - Ví dụ:
        
        ```css
        cursor: default;
        ```
        
2. **pointer**
    
    - Hình bàn tay (thường sử dụng cho các liên kết hoặc nút bấm).
    - Ví dụ:
        
        ```css
        cursor: pointer;
        ```
        
3. **text**
    
    - Hình con trỏ giống dấu nháy (thường xuất hiện khi di chuột qua vùng có thể nhập văn bản).
    - Ví dụ:
        
        ```css
        cursor: text;
        ```
        
4. **move**
    
    - Hình con trỏ với mũi tên bốn hướng (dùng để biểu thị rằng phần tử có thể được di chuyển).
    - Ví dụ:
        
        ```css
        cursor: move;
        ```
        
5. **not-allowed**
    
    - Hình tròn với một gạch chéo, thể hiện rằng hành động không được phép.
    - Ví dụ:
        
        ```css
        cursor: not-allowed;
        ```
        
6. **help**
    
    - Hình dấu chấm hỏi, biểu thị rằng có thêm thông tin hoặc trợ giúp.
    - Ví dụ:
        
        ```css
        cursor: help;
        ```
        
7. **wait**
    
    - Hình đồng hồ cát hoặc biểu tượng đang chờ, thể hiện rằng đang có tiến trình xử lý.
    - Ví dụ:
        
        ```css
        cursor: wait;
        ```
        
8. **crosshair**
    
    - Hình chữ thập (+), thường sử dụng trong các công cụ chỉnh sửa ảnh hoặc đồ họa.
    - Ví dụ:
        
        ```css
        cursor: crosshair;
        ```
        
9. **none**
    
    - Ẩn con trỏ hoàn toàn khi di chuyển qua phần tử.
    - Ví dụ:
        
        ```css
        cursor: none;
        ```
        
10. **grab / grabbing**
    
    - **grab**: Hình bàn tay mở, thường xuất hiện khi một phần tử có thể được kéo.
    - **grabbing**: Hình bàn tay nắm chặt, hiển thị khi phần tử đang được kéo.
    - Ví dụ:
        
        ```css
        cursor: grab;
        cursor: grabbing;
        ```
        

---

### **Giá trị cụ thể cho resizing**

1. **col-resize**
    
    - Mũi tên hai chiều trái-phải (dùng để thay đổi kích thước cột).
    - Ví dụ:
        
        ```css
        cursor: col-resize;
        ```
        
2. **row-resize**
    
    - Mũi tên hai chiều lên-xuống (dùng để thay đổi kích thước hàng).
    - Ví dụ:
        
        ```css
        cursor: row-resize;
        ```
        
3. **n-resize, s-resize, e-resize, w-resize**
    
    - Mũi tên đơn chỉ về các hướng Bắc, Nam, Đông, hoặc Tây.
    - Ví dụ:
        
        ```css
        cursor: n-resize;
        cursor: s-resize;
        cursor: e-resize;
        cursor: w-resize;
        ```
        
4. **ne-resize, nw-resize, se-resize, sw-resize**
    
    - Mũi tên chỉ về các góc chéo (Bắc-Đông, Bắc-Tây, Nam-Đông, Nam-Tây).
    - Ví dụ:
        
        ```css
        cursor: ne-resize;
        cursor: nw-resize;
        ```
        

---

### **Giá trị tùy chỉnh**

- Có thể sử dụng URL của một hình ảnh làm con trỏ.
- Cú pháp:
    
    ```css
    cursor: url('custom-cursor.png'), auto;
    ```
    
    - `auto`: Dự phòng, sẽ sử dụng kiểu mặc định nếu URL không hợp lệ.
    - Hình ảnh sử dụng cần nhỏ và có định dạng `.png`, `.cur` hoặc `.gif`.

---

### **Mẹo sử dụng**

- **Hãy nhất quán**: Chỉ sử dụng các kiểu con trỏ phù hợp với hành động mà người dùng mong đợi (ví dụ: `pointer` cho các liên kết).
- **Kiểm tra độ tương thích trình duyệt**: Không phải giá trị nào cũng được hỗ trợ trên mọi trình duyệt.
