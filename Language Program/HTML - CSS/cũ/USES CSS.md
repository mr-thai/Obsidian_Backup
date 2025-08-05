## - **3 CÁCH DÙNG CSS :**
+  **internal**
	  - dùng một thẻ style trong thẻ html
	  - không dùng chèn vào thẻ khác 
	  >vi dụ
``` html
<style>
	h1{
		color:red;
		font-size: 20px;
	}
</style>
```
+ **external**
	- là tạo một file ngoài file html
	- bắt buộc phải link nguồn để sử dụng
	>cách link
	```html
<link rel="stylesheel" href="*đường dẫn*">
	```
	- cách dùng tương tự internal
	- chỉ cần di chuyển phần nằm trong style sang là được
	> vi dụ
	```
	h1{
		color:red;
		font-size: 20px;
	}
	```

	-==lưu ý == 
		+ bắt buộc phải link để dùng
		+ bắt buộc phải link để dùng

+ **inline**
	- đưa thuộc tính trực tiếp vào thẻ
	- dùng trực tiếp cho file html
	>ví dụ
	```html
	<h1 style="color:red;font-size: 20px;"> hello world </h1>
	```


Internal, External