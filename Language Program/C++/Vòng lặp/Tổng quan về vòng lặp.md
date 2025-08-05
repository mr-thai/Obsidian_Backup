## 1. **Vòng lặp là gì?**

Vòng lặp trong C++ là một cấu trúc điều khiển cho phép thực thi một khối lệnh nhiều lần đến khi một điều kiện cụ thể không còn đúng. Điều này giúp tự động hóa các tác vụ lặp đi lặp lại mà không cần viết nhiều dòng lệnh.

## 2. **Các loại vòng lặp trong C++**

Trong C++, có ba loại vòng lặp chính:

- [[Vòng lặp for]]: Thường được sử dụng khi số lần lặp đã biết trước.
- [[Vòng lặp while]]: Dùng khi số lần lặp không xác định trước mà phụ thuộc vào điều kiện kiểm tra.
- [[Vòng lặp do-while]]: Giống `while`, nhưng luôn thực thi ít nhất một lần trước khi kiểm tra điều kiện.

## 3. **Cách hoạt động của vòng lặp**

Mỗi vòng lặp đều hoạt động dựa trên ba bước cơ bản:

1. **Khởi tạo**: Thiết lập giá trị ban đầu của biến điều khiển.
2. **Kiểm tra điều kiện**: Xác định xem có tiếp tục lặp không.
3. **Thực thi khối lệnh**: Nếu điều kiện đúng, thực thi khối lệnh bên trong vòng lặp.
4. **Cập nhật**: Thay đổi giá trị của biến điều khiển để tránh lặp vô hạn.

## 4. **Lợi ích của vòng lặp**

- Giúp giảm số dòng lệnh cần viết, tránh trùng lặp.
- Cải thiện hiệu suất lập trình, giúp code dễ bảo trì hơn.
- Cho phép xử lý dữ liệu theo cách hiệu quả hơn.
