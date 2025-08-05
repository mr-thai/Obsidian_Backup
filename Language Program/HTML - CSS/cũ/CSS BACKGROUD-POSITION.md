- thuộc tính này giúp tùy chỉnh vị trí của [[CSS BACKGROUD-IMAGE]]
```css
h1{
	backgroud-position: top left;
}
```
### các loại thông số
- key word
	+ top left
	+ top right
	+ buttom left
	+ buttom right
-  kết hợp keyword và [[CSS UNITS]]
```css
h1{
	backgroud-position: top 30% left -40px;
}
```
- dùng [[CSS UNITS]]
	```css
	h1{
		backgroud-position: 30% -40px;
	}
	```
	+ với tọa độ gốc nằm ở góc trên với giá trị (0,0)
>nếu chỉ có một thông số đc định nghĩa như "left" thì thông số thứ 2 là center

