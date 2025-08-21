---
tags:
  - language_program
  - basic
---
# 1. Cấu trúc chương trình
## 1.1 Hello World
## 1.2 Comment 1 dòng
## 1.3 Comment nhiều dòng
## 1.4 Cấu trúc file chương trình
## 1.5 Import thư viện / module
## 1.6 Quy tắc đặt tên (naming convention)
## 1.7 Coding style / formatting (lint, formatter)
## 1.8 Quản lý package/project (build tool, dependency)
---
# 2. Biến và hằng
## 2.1 Khai báo biến
## 2.2 Gán giá trị
## 2.3 Khai báo & gán cùng lúc
## 2.4 Hằng số (constant)
##  2.5 Phạm vi biến (scope: global, local, block, module)
##  2.6 Vùng nhớ & vòng đời biến (lifetime, stack/heap)
##  2.7 Static variable (nếu ngôn ngữ hỗ trợ)
---
# 3. Kiểu dữ liệu cơ bản
## 3.1 Số nguyên (int)
## 3.2 Số thực (float/double)
## 3.3 Ký tự (char)
## 3.4 Chuỗi (string)
## 3.5 Boolean
## 3.6 Null / None / nil
## 3.7 Ép kiểu dữ liệu
## 3.8 Kiểu dữ liệu phức tạp (struct, tuple, object)
## 3.9 Kiểu tham chiếu vs kiểu giá trị
## 3.10 Nullable / Optional type (có null-safety hay không)
---
# 4. Toán tử
## 4.1 Toán tử số học (+, -, *, /, %)
## 4.2 So sánh (== , !=, <, >, <=, >=)
## 4.3 Logic (AND, OR, NOT)
## 4.4 Gán rút gọn (+=, -=, *=, /=)
## 4.5 Tăng/giảm (++/--)
## 4.6 Toán tử bitwise (&, |, ^, ~, <<, >>)
## 4.7 Toán tử ba ngôi (ternary ? :) )
## 4.8 Toán tử đặc biệt (new, instanceof, typeof, in, is, as, pattern matching … tùy ngôn ngữ)
---
# 5. Nhập / Xuất dữ liệu
## 5.1 In ra màn hình
## 5.2 In có định dạng
## 5.3 Nhập từ bàn phím
 ## 5.4 Nhập từ file
## 5.5 Xuất ra file
## 5.6 Đọc ghi JSON / XML / YAML
## 5.7 Đọc ghi nhị phân (binary I/O)
## 5.8 Streaming (xử lý dữ liệu lớn theo luồng)
---
# 6. Cấu trúc điều khiển
## 6.1 If-elseif-else
## 6.4 Vòng while
## 6.5 Vòng do-while
## 6.6 For-each (duyệt mảng/danh sách)
## 6.7 Switch / Match
## 6.8 Vòng for (đếm)
## 6.9 break / continue
## 6.10 Label (goto / break label / continue label – tùy ngôn ngữ)
## 6.11 Pattern matching nâng cao (Rust, Scala, Python match-case)
---
# 7. Hàm (Function)
## 7.1 Khai báo hàm
## 7.3 Hàm có tham số
## 7.4 Hàm trả về giá trị
## 7.5 Tham số mặc định
## 7.6 Hàm ẩn danh / lambda
## 7.7 Đệ quy (recursion)
## 7.8 Overloading (đa hình hàm – nếu hỗ trợ)
## 7.9 Inline function
## 7.10 Higher-order function (hàm bậc cao: nhận hàm làm tham số, trả về hàm)
## 7.11 Closures (giữ trạng thái trong phạm vi)
## 7.12 Pure function & Side-effect
## 7.13 Scope (lexical vs dynamic scope)
---
# 8. Cấu trúc dữ liệu cơ bản
## 8.1 Mảng / Array
## 8.2 Duyệt mảng
## 8.3 Chuỗi: nối, cắt, tìm, độ dài
## 8.4 Map / Dictionary 
## 8.5 List / ArrayList
## 8.6 Set
## 8.7 Enum
## 8.8 Stack & Queue
## 8.9 Linked List
## 8.10 Tree / Graph (giới thiệu cơ bản)
## 8.11 Iterator / Generator
## 8.12 Immutable vs Mutable collections
---
# 9. Xử lý lỗi
## 9.1 try-catch
## 9.2 finally
## 9.3 throw / raise
## 9.4 Exception hierarchy (các loại lỗi con cụ thể)
## 9.5 Custom exception (tự định nghĩa lỗi)
## 9.6 Logging error
## 9.7 Error handling best practices (fail fast, fallback, retry …)
---
# 10. Lập trình hướng đối tượng (OOP)
## 10.1 Class & Object
## 10.2 Thuộc tính & phương thức
## 10.3 Constructor / Destructor
## 10.4 Kế thừa (Inheritance)
## 10.5 Đa hình (Polymorphism)
# 10.6 Trừu tượng (Abstract class, Interface)
## 10.7 Tính đóng gói (Encapsulation, getter/setter)
## 10.8 Overriding / Overloading
## 10.9 Static / Singleton pattern cơ bản
---
## 11. Lập trình hàm (Functional Programming - nếu ngôn ngữ hỗ trợ)
## 11.1 Immutability
## 11.2 Map / Filter / Reduce
## 11.3 Currying / Partial application
## 11.4 Monad / Functor (nâng cao, optional)
---
## 12. Quản lý bộ nhớ
## 12.1 Garbage Collector
## 12.2 Manual memory management (malloc/free, new/delete … tùy ngôn ngữ)
## 12.3 Smart pointer / Reference counting
## 12.4 Memory leak & cách tránh
---
## 13. Lập trình song song & bất đồng bộ
## 13.1 Thread / Process
## 13.2 Async / Await / Future / Promise
## 13.3 Coroutine (Python, Kotlin, C++20 …)
## 13.4 Synchronization (mutex, lock, semaphore)
## 13.5 Deadlock, race condition
## 13.6 Parallel processing (map-reduce, task pool)
---
## 14. Module & Package
## 14.1 Tổ chức code thành module
## 14.2 Import/export nâng cao
## 14.3 Dependency management (package manager)
## 14.4 Build system (make, gradle, maven, npm, cargo …)
---
## 15. Thư viện chuẩn (Standard Library)
## 15.1 Xử lý chuỗi
## 15.2 Xử lý file & thư mục
## 15.3 Xử lý ngày giờ
## 15.4 Network / HTTP
## 15.5 Math / Random / Statistics
---
## 16. Testing & Debugging
## 16.1 Unit Test
## 16.2 Mocking
## 16.3 Integration Test
## 16.4 Debugging tool (breakpoint, watch, trace)
## 16.5 Test-driven development (TDD)
---
## 17. Lập trình nâng cao
## 17.1 Generics / Template
## 17.2 Reflection / Introspection
## 17.3 Annotation / Attribute
## 17.4 Metaprogramming
## 17.5 DSL (domain specific language)
## 17.6 Operator overloading