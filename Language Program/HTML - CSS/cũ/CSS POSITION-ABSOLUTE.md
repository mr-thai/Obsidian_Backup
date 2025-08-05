- ABSOLUTE là vị trí tương đối
- vị trí của absolute phụ thuộc vào thẻ cha gần nhất có thuộc tính position không tính posittion dùng để khai báo chính nó
- mức độ ưu tiên vị trí
	+ top > bottom
	+ left > right
```css
.box{
	width:100%;
	height: 120px;
	backgound-color: #fff;
	position: relative;
}

.box-child{
	width:50px;
	height: 50px;
	background-color:#fff;
	position: absolute;
	top: 0;
	right: 0;
}

```
### tạo lớp phủ 
```css
.box{
	width:100%;
	height: 120px;
	backgound-color: #fff;
	position: relative;
}

.box-child{
	background-color:rgba(255,255,255,0.3);
	position: absolute;
	top: 0;
	right: 0;
	bottom: 0;
	left:0 ;
}

```