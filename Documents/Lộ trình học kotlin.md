## **Giai đoạn 1: Nắm nền tảng Kotlin**

**Mục tiêu:** Hiểu cú pháp cơ bản, kiểu dữ liệu, cách viết code đơn giản.  
**Thời gian:** 1–2 tuần.

### Kiến thức cần học

- Cài môi trường:
    
    - IntelliJ IDEA (đề xuất) hoặc VSCodium + Kotlin plugin.
        
    - JDK 17+.
        
- Cú pháp cơ bản:
    
    - Variables (`val`, `var`)
        
    - Kiểu dữ liệu (`Int`, `Double`, `String`, `Boolean`, `Any`, `Unit`, `Nothing`)
        
    - String templates
        
    - Toán tử
        
- Cấu trúc điều khiển:
    
    - `if-else`
        
    - `when`
        
    - `for`, `while`, `do-while`
        
- Functions:
    
    - Định nghĩa hàm
        
    - Tham số mặc định, named arguments
        
    - Hàm trả về giá trị hoặc `Unit`
        
- Collections cơ bản:
    
    - `List`, `Set`, `Map`
        
    - Vòng lặp qua collection
        

### Tài liệu

- [Kotlin Lang Official Docs - Basics](https://kotlinlang.org/docs/basic-syntax.html)
    
- Sách _Kotlin Programming: The Big Nerd Ranch Guide_ – Chương 1–4.
    

### Bài tập thực hành

- Viết chương trình tính toán BMI.
    
- Chuyển đổi nhiệt độ (C ↔ F).
    
- Đếm số nguyên tố từ 1 đến 100.
    
- Tạo danh sách tên anime yêu thích và in ra theo nhiều cách khác nhau.
    

---

## **Giai đoạn 2: Lập trình hướng đối tượng (OOP) trong Kotlin**

**Mục tiêu:** Hiểu class, object, kế thừa, interface, và đặc trưng Kotlin.  
**Thời gian:** 1–2 tuần.

### Kiến thức cần học

- Class, object, constructor
    
- Properties (getter/setter)
    
- `data class`
    
- `object` & singleton
    
- Kế thừa (`open`, `override`)
    
- Interface
    
- Enum & Sealed Class
    

### Tài liệu

- [Kotlin OOP - Official Docs](https://kotlinlang.org/docs/classes.html)
    
- Sách _Kotlin in Action_ – Chương 3–6.
    

### Bài tập

- Tạo class `Student` có tên, tuổi, điểm và hàm tính học lực.
    
- Tạo `data class` để lưu thông tin phim (tên, năm phát hành, thể loại).
    
- Tạo enum lưu các rank nhân vật trong Genshin Impact.
    
- Dùng sealed class để mô tả trạng thái tải dữ liệu (Loading, Success, Error).
    

---

## **Giai đoạn 3: Kotlin nâng cao & Functional Programming**

**Mục tiêu:** Sử dụng được các tính năng mạnh của Kotlin để viết code gọn, tối ưu.  
**Thời gian:** 2–3 tuần.

### Kiến thức cần học

- Extension functions & properties
    
- Higher-order functions, lambda expressions
    
- `let`, `apply`, `run`, `also`, `with`
    
- Null safety (`?`, `!!`, `?:`)
    
- Collection operations nâng cao (`map`, `filter`, `reduce`, `groupBy`)
    
- Generics
    

### Tài liệu

- [Kotlin Scope Functions](https://kotlinlang.org/docs/scope-functions.html)
    
- _Kotlin in Action_ – Chương 7–9.
    

### Bài tập

- Tạo extension function để đảo ngược một chuỗi.
    
- Viết hàm nhận một list số nguyên và trả về list chỉ chứa số chẵn.
    
- Xử lý danh sách nhân vật anime → nhóm theo thể loại.
    
- Tạo một mini DSL (Domain Specific Language) để build cấu hình game.
    

---

## **Giai đoạn 4: Kotlin + Dự án nhỏ**

**Mục tiêu:** Biết cách tổ chức project, áp dụng code Kotlin vào ứng dụng thực tế.  
**Thời gian:** 3–4 tuần.

### Lựa chọn hướng đi

- **Backend**: Kotlin + Spring Boot (API, web service)
    
- **Android**: Kotlin + Android Studio (ứng dụng di động)
    
- **Multiplatform**: Kotlin Multiplatform Mobile (KMM)
    

### Kiến thức cần học thêm (tùy hướng)

- **Android**: Activity, Fragment, ViewBinding, RecyclerView, Navigation Component, Coroutines.
    
- **Backend**: REST API, Spring Boot basics, JPA/Hibernate, Database.
    
- **KMM**: Chia sẻ code logic, tích hợp với UI Android/iOS.
    

### Bài tập/Dự án

- Android: App ghi chú đơn giản (thêm/sửa/xóa).
    
- Backend: API quản lý danh sách nhân vật Genshin (CRUD + database).
    
- KMM: App từ điển mini chạy cả Android và iOS.
    

---

## **Giai đoạn 5: Kotlin chuyên sâu & Thực chiến**

**Mục tiêu:** Thành thạo Kotlin, sẵn sàng đi làm.  
**Thời gian:** 2–3 tháng.

### Kiến thức cần học

- Coroutines sâu (launch, async, flow, channel)
    
- Dependency Injection (Koin/Dagger-Hilt)
    
- Unit Test & UI Test
    
- Best practices & Clean Architecture
    
- Performance optimization
    

### Dự án lớn

- Android: App quản lý công việc + đồng bộ cloud.
    
- Backend: Hệ thống API bán hàng với phân quyền.
    
- KMM: App chat real-time đơn giản.
    

---

📌 **Nguyên tắc học:**

- Code mỗi ngày, dù chỉ 30 phút.
    
- Luôn làm bài tập và dự án nhỏ song song với học lý thuyết.
    
- Khi không hiểu, đọc lại docs hoặc xem code mẫu trên GitHub.
    
- Đặt deadline cho từng giai đoạn.
