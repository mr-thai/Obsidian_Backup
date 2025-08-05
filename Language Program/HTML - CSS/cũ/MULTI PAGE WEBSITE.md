- **multi-page website** là một trang web có nhiều trang con, trái ngược với **single-page application (SPA)**, nơi tất cả nội dung đều tải trong một trang duy nhất.

# Cách tổ chức và xây dựng một multi-page website

1. **Cấu trúc thư mục**
   - Thông thường, mỗi trang web sẽ có một file HTML riêng biệt. Các file như CSS, hình ảnh, và JavaScript có thể được chia sẻ giữa các trang.
   - Ví dụ

   ```
   /website
      /css
         style.css
      /images
         logo.png
      index.html
      about.html
      contact.html
   ```

2. **Liên kết giữa các trang**
   - Đường dẫn này có thể là [[HTML LINK]].
   - Ví dụ, liên kết từ trang chủ (`index.html`) đến trang giới thiệu (`about.html`) và trang liên hệ (`contact.html`) :
   **trang chủ (`index.html`)**
   ```html
   <!-- index.html -->
   <nav>
      <a href="index.html">Home</a>
      <a href="about.html">About</a>
      <a href="contact.html">Contact</a>
   </nav>

   <h1>Welcome to Our Website</h1>
   ```
   **(`about.html`)**

   ```html
   <!-- about.html -->
   <nav>
      <a href="index.html">Home</a>
      <a href="about.html">About</a>
      <a href="contact.html">Contact</a>
   </nav>

   <h1>About Us</h1>
   ```
   **(`contact.html`)**

   ```html
   <!-- contact.html -->
   <nav>
      <a href="index.html">Home</a>
      <a href="about.html">About</a>
      <a href="contact.html">Contact</a>
   </nav>

   <h1>Contact Us</h1>
   ```


# Lợi ích và hạn chế

## Lợi ích:
- **Quản lý nội dung rõ ràng**: Mỗi trang có nội dung độc lập, dễ quản lý hơn khi trang web có nhiều chủ đề khác nhau.
- **Tốt cho SEO**: Mỗi trang có thể tối ưu riêng lẻ, giúp cải thiện thứ hạng tìm kiếm.
- **Tải nhanh với từng trang**: Người dùng chỉ tải dữ liệu cần thiết cho trang mà họ truy cập.

## Hạn chế:
- **Nhiều lượt tải trang**: Mỗi lần người dùng chuyển trang, toàn bộ trang HTML mới sẽ được tải lại, có thể gây chậm hơn so với một SPA.
- **Quản lý phức tạp**: Nếu trang web có quá nhiều trang, việc quản lý và cập nhật có thể trở nên phức tạp.
