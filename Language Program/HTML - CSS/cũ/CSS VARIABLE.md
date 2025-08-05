- varianbe là biến na ná giống trong c++ nó khai báo một giá trị trung tâm thay thế cho thuộc tính gốc bằng một cái tên khác mang tính toàn cụ hơn
### cách khai báo
```css
:root{
	--text-color: red;
}
```
- khai báo bằng cách thêm phần ":root" 
- bên trong root thì tạo tên biến cụ thể với hai dấu "--" phía trước
### cách sự dụng
```css
h1{
color: var(--text-color);
}
```
-dùng bằng cách thêm loại thuộc tính và thêm var(tên biến)

### đặt biến local
- là đặt biến bến trong một thẻ xác định
```css
h1{
	--my-color: green;
	color: var(--my-color);
}
```