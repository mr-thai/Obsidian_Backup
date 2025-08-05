# 1. **Đường dẫn tương đối (Relative URL)**

- Chỉ rõ vị trí của tài nguyên dựa trên vị trí của trang HTML hiện tại.
- Không cần chỉ rõ đầy đủ đường dẫn từ gốc trang web.
- Thường được sử dụng khi các file nằm trong cùng thư mục hoặc thư mục con.

**Ví dụ**: Giả sửcó một thư mục với cấu trúc sau:
```
/website
   /images
      picture.jpg
   index.html
```
Trong file `index.html`, bạn muốn chèn hình `picture.jpg`, sử dụng đường dẫn tương đối như sau:
```html
<img src="images/picture.jpg" alt="Picture">
```

Ở đây, đường dẫn `images/picture.jpg` tương đối với file `index.html` (nằm cùng cấp).

# 2. **Đường dẫn tuyệt đối (Absolute URL)**

- Chỉ rõ toàn bộ đường dẫn từ gốc (bao gồm cả tên miền hoặc vị trí chính xác).
- Thường được sử dụng khi tài nguyên nằm ở một vị trí khác hoàn toàn, ví dụ như trên một máy chủ khác.

**Ví dụ**: Chèn cùng hình ảnh, nhưng nó nằm trên một trang web khác:
```html
<img src="https://example.com/images/picture.jpg" alt="Picture">
```
Ở đây, bạn cung cấp toàn bộ URL bao gồm cả giao thức `https://` và tên miền `example.com`.

# Tóm lại:
- **Đường dẫn tương đối**: Phù hợp khi tài nguyên nằm trong cùng dự án web.
- **Đường dẫn tuyệt đối**: Phù hợp khi tài nguyên nằm trên máy chủ khác hoặc bạn muốn chỉ rõ toàn bộ đường dẫn.