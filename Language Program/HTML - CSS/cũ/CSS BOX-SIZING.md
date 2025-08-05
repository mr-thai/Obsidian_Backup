- thay đổi vị trí thông tin bên trong thẻ mà ko làm thay đổi kích thước thẻ
- cách thức hoạt động: lấy kích thước [[CSS BORDER]] làm gốc sau đó nó sẽ lấy kích thước của [[CSS PADDING]] và content-box làm sao cho kích thước tổng quan bằng với kích thước đã khai báo với [[CSS BORDER]]
```css
h1{
	box-sizing: border-box;
}
```
- các thuộc tính khắc:
	+ counter-box : đây là kích thước mặc định
	+ unset : hủy kích thước box-sizing