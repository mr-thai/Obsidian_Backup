### var()
- sử dụng biến [[CSS VARIABLE]] 
### linear-gradient()
- tạo dại màu chuyển đổi [[CSS BACKGROUD-IMAGE]]
### rgpa()
- tạo màu bằng các thông số rgb [[CSS BACKGROUD-IMAGE]]
### rgb()
- tương tự rgpa những ko thể thay đổi số alpha (độ trong suốt)
```css
h1{
 backgroud: rgp(255,255,0);
}
```
### calc()
- dùng để tính toán 
```css
h1{
width: calc(30px + 20%);
}
```
### attr()
-  dùng để tạo thuộc tính thường được dùng trong [[CSS PSEUDO-CLASSES]]
```css
a::after{
	content: "("attr(href)")";
}

<a hred="http://youtube.com">youtube</a>
```