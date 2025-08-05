```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body></body>
</html>
```

- **cấu trúc cơ bản của một file gồm :**
	+ DOCTYPE
	+ thẻ html
	+ thẻ head
	+ [[HTML BODY]]

```html
<!DOCTYPE html>
```
`< !DOCTYPE html>`là một khai báo doctype (document type declaration) trong html

```html
<html lang="en">
</html>
```
- `<html></html>` dung để định nghĩa phần thân của code html
-  `lang` để chỉ ngôn ngữ được dùng tròn code (HTML Language Codes)
- **1 file html có và chỉ có 1 cặp** `<html></html>`

```html
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
</head>
```
- thẻ `<head></head>` dùng để chứa những thông tin ko hiện thị trên giao diện chính
- `<head></head>` rất quan trọng trong việc tối ưu cồng cụ tìm kiếm
- `<title></title>` dùng để hiện thị tên trên tab trình duyệt

```html
<body></body>
```
-thẻ `<body></body>` dùng để chứa những thông tin hiện thị trên màn hình

**cách ghi chú html**
```html
<!-- đây là cách ghi chứ trong html --!>
```

**cách demo văn bản trong html**
```html
<body>
    <h1>Lorem</h1>
</body>
```
sau khi viết `lorem` và **enter** thì kết quả cho ra sẽ như thế này
> Lorem ipsum, dolor sit amet consectetur adipisicing elit. Assumenda quaerat ut aliquid vero, provident officiis possimus ex error doloribus minus, incidunt qui eum debitis excepturi laborum ullam nihil at inventore.


- có thể giới hạn số lượng từ xuất hiện bằng cách thêm số lượng từ muốn có sau lorem
```html
<body>
    <h1>Lorem9</h1>
</body>
```
kết quả sẽ cho ra
>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Provident!