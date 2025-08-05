## **1. Simple Selectors (Bộ chọn đơn giản)**

### **1.1. Universal Selector (Bộ chọn toàn cục)**

- **Cú pháp:** `*`
- **Chức năng:** Chọn **tất cả các phần tử** trong tài liệu HTML.
- **Ví dụ:**
    
    ```css
    * {
      margin: 0;
      padding: 0;
    }
    ```
    
    > **Ứng dụng:** Loại bỏ khoảng trống mặc định trên toàn bộ trang web.
    

---

### **1.2. Type Selector (Bộ chọn theo loại phần tử)**

- **Cú pháp:** `element`
- **Chức năng:** Chọn **tất cả các phần tử** theo tên thẻ (tag name).
- **Ví dụ:**
    
    ```css
    p {
      color: blue;
    }
    ```
    
    > **Ứng dụng:** Tô màu xanh cho toàn bộ văn bản trong thẻ `<p>`.
    

---

### **1.3. Class Selector (Bộ chọn lớp)**

- **Cú pháp:** `.classname`
- **Chức năng:** Chọn tất cả các phần tử có chứa **class** đã chỉ định.
- **Ví dụ:**
    
    ```css
    .highlight {
      background-color: yellow;
    }
    ```
    
    > **Ứng dụng:** Làm nổi bật các phần tử có class `highlight`.
    

---

### **1.4. ID Selector (Bộ chọn ID)**

- **Cú pháp:** `#id`
- **Chức năng:** Chọn một phần tử **duy nhất** có chứa **id** đã chỉ định.
- **Ví dụ:**
    
    ```css
    #header {
      font-size: 24px;
    }
    ```
    
    > **Ứng dụng:** Định kiểu riêng cho phần tử có id `header`.
    

---

### **1.5. Grouping Selector (Bộ chọn nhóm)**

- **Cú pháp:** `element1, element2, ...`
- **Chức năng:** Áp dụng cùng một style cho **nhiều phần tử**.
- **Ví dụ:**
    
    ```css
    h1, h2, h3 {
      color: green;
    }
    ```
    
    > **Ứng dụng:** Làm tất cả tiêu đề từ `<h1>` đến `<h3>` có màu xanh.
    

---

## **2. Combinator Selectors (Bộ chọn tổ hợp)**

### **2.1. Descendant Selector (Bộ chọn con cháu)**

- **Cú pháp:** `ancestor descendant`
- **Chức năng:** Chọn tất cả các **phần tử con cháu** bên trong một phần tử tổ tiên.
- **Ví dụ:**
    
    ```css
    div p {
      color: red;
    }
    ```
    
    > **Ứng dụng:** Làm đỏ văn bản trong tất cả các `<p>` nằm trong `<div>`.
    

---

### **2.2. Child Selector (Bộ chọn con trực tiếp)**

- **Cú pháp:** `parent > child`
- **Chức năng:** Chọn **phần tử con trực tiếp** (không bao gồm cháu).
- **Ví dụ:**
    
    ```css
    ul > li {
      list-style: none;
    }
    ```
    
    > **Ứng dụng:** Xóa ký hiệu danh sách chỉ cho các `<li>` là con trực tiếp của `<ul>`.
    

---

### **2.3. Adjacent Sibling Selector (Bộ chọn anh em liền kề)**

- **Cú pháp:** `element1 + element2`
- **Chức năng:** Chọn **phần tử anh em ngay sau** phần tử khác.
- **Ví dụ:**
    
    ```css
    h1 + p {
      font-style: italic;
    }
    ```
    
    > **Ứng dụng:** Làm nghiêng đoạn văn ngay sau tiêu đề `<h1>`.
    

---

### **2.4. General Sibling Selector (Bộ chọn anh em tổng quát)**

- **Cú pháp:** `element1 ~ element2`
- **Chức năng:** Chọn **tất cả anh em sau** một phần tử khác.
- **Ví dụ:**
    
    ```css
    h1 ~ p {
      color: gray;
    }
    ```
    
    > **Ứng dụng:** Làm tất cả đoạn văn sau `<h1>` có màu xám.
    

---

## **3. Pseudo-class Selectors (Bộ chọn giả lớp)**

### **3.1. Trạng thái phần tử**

- **Cú pháp:** `:state`
    
- **Các ví dụ phổ biến:**
    
    - `:hover`: Áp dụng khi chuột di chuyển vào phần tử.
    - `:focus`: Áp dụng khi phần tử được chọn (thường là input).
    - `:active`: Áp dụng khi phần tử đang được nhấn.
- **Ví dụ:**
    
    ```css
    button:hover {
      background-color: lightblue;
    }
    ```
    

### **3.2. Vị trí con trong danh sách**

- **Cú pháp:** `:nth-child(n)`, `:first-child`, `:last-child`, v.v.
- **Ví dụ:**
    
    ```css
    li:nth-child(odd) {
      background-color: #f0f0f0;
    }
    ```
    

---

## **4. Pseudo-element Selectors (Bộ chọn giả phần tử)**

### **4.1. ::before và ::after**

- **Cú pháp:** `::before`, `::after`
- **Chức năng:** Thêm nội dung trước hoặc sau nội dung của phần tử.
- **Ví dụ:**
    
    ```css
    h1::before {
      content: "⭐ ";
    }
    ```
    

---

## **5. Attribute Selectors (Bộ chọn thuộc tính)**

### **5.1. Bộ chọn cơ bản**

- **Cú pháp:** `[attribute]`
- **Ví dụ:**
    
    ```css
    [type="text"] {
      border: 1px solid black;
    }
    ```
    
