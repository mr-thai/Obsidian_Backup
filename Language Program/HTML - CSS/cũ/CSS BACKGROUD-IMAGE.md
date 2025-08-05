- Tương tự với [[CSS BACKGROUD-CLIP]] thì thay vị đổ màu thì backgroud-image là thay bằng ảnh
```css
h1{
	backgroud-image: url();
}
```
- nếu muốn thêm nhiều hơn 1 ảnh thì mỗn đường link cách nhau 1 dấu ","
```css
h1{
	backgroud-image: url(),url();
}
```
### các thuộc tính chỉnh sửa backgroud
- backgroud-size: 100px (thay đổi kích thước ảnh)
	+ nếu backgroud-size được thêm 2 giá trị thì có thể dẫn đến bị méo ảnh nên ưu tiên đặt một giá trị hoặc auto
- background-repeat: repeat; (lặp lại ảnh)
	+ repeat (đây là trạng thái mặc định của backgroud)
	+ no-repeat (không lặp lại ảnh)
	+ sepeat-x (lặp lại theo chiều ngang)
	+ sepeat-y (lặp lại theo chiều dọc)
### các thuộc tính đặc biệt của backgroud-image
#### linear-gradient
- dùng để tạo ra một dại màu chuyển một cách đều đặn
```css
h1{
	backgroud-image: linear-gradient(0,#333,#ccc);
}
```
- giải thích các thông số
	+ thống số đầu tiên là góc chuyển đổi tức là vị trí màu đầu 
		>nếu giá trị >0 thì phải thêm deg phía sau giá trị (180 deg)
		>nếu bỏ thông số đầu tiên thì mặc định là 180 độ
	+ 2 thông số còn lại là màu chuyển đổi với màu <90 độ là từ thông số 1 sàng thông số 2 
	+ có thể thay màu hex thành màu rgpa 
		```css
			h1{
			backgroud-image: linear-gradient(0,rgpa(255,255,0,0.4,rgpa(0,255,255,0.3));
			}
		```
		- các chỉ số trong rgpa:
			+ 3 thông số đầu là 3 chỉ số màu cơ bản
			+ thồng số cuối là độ trong suốt dao đông từ ( 0->1) số càng lớn càng đậm
	