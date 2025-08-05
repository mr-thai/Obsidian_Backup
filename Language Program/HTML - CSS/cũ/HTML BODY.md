- thẻ body dùng để chứa nội dung chính của trang web
- các phần từ trong body sẽ hiện thị trực tiếp trên màn hình trình duyệt
# các loại thẻ phần tự trong body
## 1. Thẻ h (header)
- dùng để định nghĩa tiêu đề
- thẻ h dùng để căn chỉnh kích thước và mức độ quan trọng của tiêu đề
- thẻ h gồm 6 cấp độ tường ứng với từ h1->h6
```html
<body>
    <h1>tiêu đề h1</h1>
    <h2>tiêu đề h2</h2>
    <h3>tiêu đề h3</h3>
    <h4>tiêu đề h4</h4>
    <h5>tiêu đề h5</h5>
    <h6>tiêu đề h6</h6>
  </body>
```
 
- nêu h lớn hơn 6 thì ko còn là đánh dấu header
- trong đó thẻ h1 là thẻ tiêu đề chính của web -> chỉ nên dùng 1 thẻ h1 trong 1 trang web vì sẽ gây nhầm lẫm trong việc tìm kiếm
- không nhảy thẻ h (ví dụ h1 đến h3 mà không qua thẻ h2)
## 2. Thẻ p (paragraph)
-dùng để chứa các đoạn văn bản
```html
<body>
    <p>văn bản</p>
</body>
```

## 3. Thẻ tự đóng (br, hr)
### Thẻ br (break)
-dùng để xuống dòng hoặc ngắt dòng
```html
<body>
    <p>
	văn bản<br>
	văn bản
    </p>
</body>
```

### Thẻ hr(horizontal rule)
-dùng để tạo một dòng kẻ chia trang
```html
<body>
    <p>
	văn bản<hr>
	văn bản
    </p>
</body>
```

## 4. Thẻ in b,i,u
### Thẻ b
- in đậm văn bản
```html
<body>
	<p>văn bản <b>in đậm </b></p>
</body>
```
### Thẻ i
- in nghiêng văn bản
```html
<body>
	<p>văn bản <i>in nghiêng </i></p>
</body>
```
### Thẻ u
- in gạch chân văn bản
```html
<body>
	<p>văn bản <u>in gạch chân</u></p>
</body>
```
### Kết hợp thẻ
```html
<body>
	<p>văn bản <b><u>in đậm và gạch chân </u></b></p>
</body>
```
### Thẻ mang ngữ nghĩa
- thẻ hiện những nội dung quan trọng mà máy tính có thể hiệu được
#### Thẻ strong
- in đạm văn bản
- thể hiện nội dung quan trọng khác với thẻ "b" chỉ in đậm chữ
```html
<body>
    <p>văn bản <strong>in đậm </strong></p>
</body>
```
#### Thẻ em (emphasis)
- in nghiêng văn bản
- thể hiện nội dung quan trọng khác với thẻ "i" chỉ in nghiêng chữ
```html
<body>
    <p>văn bản <em>in đậm </em></p>
</body>
```

## 5. Thẻ list ul, ol, và thẻ li
### Thẻ li (list item)
- là thẻ con nằm trong thẻ ul và ol
```html
<li>Item</li>
```
### Thẻ ul (unordered list)
- tạo một danh sách mà không có số thứ tự
```html
<body>
    <ul>
      <li>Item 1</li>
      <li>Item 2</li>
      <li>Item 3</li>
    </ul>
</body>
```
### Thẻ ol (ordered list)
- tạo một danh sách mà có số thứ tự
```html
<body>
    <ol>
      <li>Item 1</li>
      <li>Item 2</li>
      <li>Item 3</li>
    </ol>
</body>
```
#### Các thuộc tính đặc biệt
##### Thuộc tính reversed (đảo ngược thứ tự)
```html
<body>
    <ol reversed>
      <li>Item 1</li>
      <li>Item 2</li>
      <li>Item 3</li>
    </ol>
</body>
```
##### Thuộc tính type (định dạng)
- mặc định type="1" là số thứ tự 1,2,3,...
- các định dạng type khác
   1. type="A" ->A, B, C, ...
   2. type="a" ->a, b, c, ...
   3. type="I" ->I, II, III, ...
   4. type="i"->i, ii, iii, ...
```html
<body>
    <ol type="A">
      <li>Item 1</li>
      <li>Item 2</li>
      <li>Item 3</li>
    </ol>
</body>
```
### Emmet-gõ tắt
 - tạo nhanh một list có thể áp dụng đối với ul và ol
#### TTạo một list với số lượng phần tự nhanh
```html
 <body>
    ul>li*3 <!-- với *3 là tạo 3 phần tự con) --!>
  </body>
```
- thêm nội dung nhanh kết hợp tạo list nhanh
```html
<body>
      ul>li*3{Item $} <!-- $ là đếm từ 0 -> số lượng tối đa của list --!>
</body>
```
kêt quả sẽ tạo thành
><li>Item 1</li>
   <li>Item 2</li>
   <li>Item 3</li>

## 6. Thẻ a (anchor)
-dùng để gán liên kết, email, phone
```html
<body>
    <a href=""> click ở đây </a>
</body>
```
- href (hypertext reference) dùng để thêm URL cần liên kết
### Các kiểu href
1. href=""   <=> tải lại trang
2. href="#" <=> lên đầu trang
3.  href="**một đường link** "  <=> di chuyển đến đường link đã cung cấp
```html
<body>
    <a href="https://www.hoyolab.com/"> hoyolab </a>
</body>
```
#### Các thuộc tính trong href
##### Liên quan đến link (target)
```html
<body>
    <a href="https://www.hoyolab.com/"> mở tại trang hiện tại </a>
    <a href="https://www.hoyolab.com/" target="_self">mở tại trang hiện tại</a>
    <a href="https://www.hoyolab.com/" target="_blank"> mở tại trang khác </a>
</body>
```
- nếu ko có target nào thì mặc định là target = _self 
##### Liên quan đến số điện thoại (tel)
- tell dùng để chuyển hướng đến một ứng dụng có thể dùng để gọi trên thiết bị
```html
<body>
    <a href="tel:0387697411">0387697411</a>
    <a href="tel:+84387697411">0387697411</a>
</body>
```
##### Liên quan đến email (mailto)
- mailto dùng để chuyển hướng đến một ứng dụng có thể dùng để gửi email trên thiết bị
```html
<body>
    <a href="mailto:mr.thai2k5@gmail.com">email của tôi</a>
  </body>
```
###### Một số tham số có thể truyền cho mailto
- cc: danh sách email nhận bản sao thư
- bcc: danh sách email ẩn sẽ nhận bản sao thư
- subject: nội dung mail
- ?: dấu phân cách phần mailto với tham số
- &: phân cách các tham số
- ,: liệt kê thêm mail
```html
<body>
    <a href="mailto:mr.thai2k5@gmail.comcc=email2@gmail.com,email3@gmail.com&subject=nội dung mail">
    email của tôi
    </a>
</body>
```

## 7. Thẻ img (image)
- img là thẻ tự đóng (self closing tag) để hiện thị hình ảnh trên web
```html
<body>
    <img
      src="https://static.wikia.nocookie.net/gensin-impact/images/0/01/Kamisato_Ayaka_Card.png" alt="hinh ảnh lỗi"/>
    <img src="D:\OneDrive\Hình ảnh\Ảnh chụp màn hình"/>
  </body>
```
### Thuộc tính img
- src (source image file): dùng để chỉ những đường dẫn đến hình ảnh có thể mà link hoặc đường dẫn thư mục
- alt (alternative-thay thế): 
	+ hiện thị text khi ảnh bị lỗi
	+ hỗ trợ trình đọc màn hình cho người khiếm thị
	+ công cụ tìm kiếm thu thập dữ liệu trên mạng
- width, height (chiều rộng và chiều cao):
 + dùng để chỉ định kích thước cho ảnh
```html
<body>
    <img
      src="https://static.wikia.nocookie.net/gensin-impact/images/0/01/Kamisato_Ayaka_Card.png" alt="hinh ảnh lỗi" width="50" height="100"/>
  </body>
```
**một số lưu ý**
- nếu ko xét kích thước -> kích thước gốc
- ưu tiên chỉnh 1 chiều -> tránh bị móp ảnh
- nếu set 1 chiều -> chiều còn lại sẽ tự căn tỉ lệ
- có thể căn chỉnh theo "px" hoặc "%"