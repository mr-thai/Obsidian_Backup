PRIORITY(mức độ ưu tiên): khi dùng css nếu trong cùng một thẻ được gọi đến từ các thuộc tính khác nhau như id, class, style,... thì nó sẽ chuyển sang dạng mức độ ưu tiên để dùng với mức ưu tiên dựa trên các thang điểm điểm càng cao mức ưu tiên càng cao
# Internal, External
- nếu xét về độ ưu tiên hai loại này thì ai xuất hiện sau thì cái đó được dùng

# Các loại xếp bằng điểm
## Inline (1000)
## id (100)
## class (10)
## tag (1)
# Equal specificity
- là sự lặp lại của selector
>ví dụ
```css
	#*tên id*{ 
		color: red; 
	}
	#*tên id*{
		color: blue;
	}
```
- cái nào gọi sau thì sẽ được dùng
- cách khác phục
```css
h1#heading-id.heading-class{
	color: red;
}
```
- giải thích
	+ ở thê việc hết hợp tên thẻ, id, class có thể hiểu là cộng cá điểm lại với nhau với ví dụ trên là 
	>1 + 100 + 1000 = 1101 điểm 
# Universal selector and inheritel (10000)
- sự dụng để khai báo thuộc tính trên phảm vi rộng
```css
	* {
	color: red;
	}
```
- với ví dụ trên thì * được hiệu là khai báo tất cả các thẻ từ phảm vi link file css thành thuộc tính mà nó khai báo

```css
html{
color: blue;
}
```
- tương tự thì nó sẽ khai báo tất cả các thẻ nằm trong thẻ html thành định dạng yêu cầu
# (Important) Thẻ ưu tiên đặc biệt
- nếu trong các thể được khai báo thuộc tính giống nhau, độ ưu tiên ngẫu nhiên thì nếu muốn có một thuộc tính ưu tiên không muốn bị thay đổi thì thêm "!important" vào sau thuộc tính đó
```css
h1{
	color: red !important;
}
```
- loại thẻ có important có dộ ưu tiên cao nhất nên không thể bị thay thế bới các priority khác
- nhưng khi muốn thay đổi các thuộc tính ở các thể khác bắt buộc phải thêm important vào sau các thuộc tính có độ ưu tiên cao hơn thẻ đã khai báo trước đó
```css
h1{
	color: red !important;
}
```
```html
<h1 style="color: blue !important"> hello world </h1>
```
- với ví dụ trên thì important style trong thẻ h1 sẽ được ưu tiên cao hơn