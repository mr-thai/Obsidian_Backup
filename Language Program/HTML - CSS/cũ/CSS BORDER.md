- tương tự [[CSS PADDING]] thì border làm dạy kích thước thẻ
- nhưng khác với [[CSS PADDING]] thì border thường dùng để tạo viền và không có sự liên kết thông thường nào với nội dung chính như [[CSS PADDING]]
```css
h1{
	border-top-width: 10px;
	border-right-width: 10px;
	border-left-width: 10px;
	border-bottom-width: 10px;
	border-style: solid;
	border-color: #333;
}
```
 - trong đó :
	 + border-style: là kiểu border (có thể kà nét đứt, nét liền,...) với kích thước mặc định là 2px 
	 + border-color: là kiểu tạo màu cho border với màu mặc định là trong suốt
### cách viết đặc biệt
```css
h1{
	border: 10px 10px 10px 10px;
}
```
- cách viết này tường tự với cách viết đặc việt của [[CSS PADDING]] về kích thước

```css
h1{
	border: 10px solid #333;
}
```
- các viết này có nghĩa là 4 cạnh là 10px với định dạng border là solid màu sắc là #333

```css
h1{
	border-top: 10px solid #333;
}
```
- các viết này có nghĩa là cạnh trên là 10px với định dạng border là solid màu sắc là #333
- tường tự với 4 cạnh còn lại