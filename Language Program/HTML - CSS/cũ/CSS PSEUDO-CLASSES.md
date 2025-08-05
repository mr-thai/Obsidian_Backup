- PSEUDO-CLASSES có nghĩa là lớp giả
- các lớp giả luôn có ":" phía trước
### `: root`
- dùng để khai báo các thuộc tính và tham chiếu đến file html
```html
a::after{
	content: "("attr(href)")";
}

<a hred="http://youtube.com">youtube</a>
```


### `:hover`
- Dùng để thay đổi thuộc tính của phần tử khi người dùng đưa chuột vào.
```html
a:hover {
    color: red;
}

<a href="#">Hover me</a>
```

### `:focus`
- Dùng để thay đổi thuộc tính khi phần tử nhận focus (thường là input).
```html
input:focus {
    border: 2px solid blue;
}

<input type="text" />
```

### `:nth-child(n)`
- Dùng để chọn phần tử dựa vào thứ tự n trong danh sách (n tính từ 1).
```html
li:nth-child(2) {
    color: green;
}

<ul>
    <li>1</li>
    <li>2</li>
    <li>3</li>
</ul>
```

### `:first-child`
- Dùng để chọn phần tử đầu tiên của parent element.
```html
li:first-child {
    color: blue;
}

<ul>
    <li>1</li>
    <li>2</li>
    <li>3</li>
</ul>
```

### `:last-child`
- Dùng để chọn phần tử cuối cùng trong danh sách.
```html
li:last-child {
    color: red;
}

<ul>
    <li>1</li>
    <li>2</li>
    <li>3</li>
</ul>
```

### `:active`
- Dùng để thay đổi thuộc tính của phần tử khi người dùng nhấn chuột vào.
```html
button:active {
    background-color: red;
}

<button>Click me</button>
```

### `:checked`
- Dùng để chọn các phần tử checkbox hoặc radio khi chúng được chọn.
```html
input:checked {
    background-color: yellow;
}

<input type="checkbox" checked />
```

### `:disabled`
- Dùng để chọn phần tử bị vô hiệu hóa.
```html
input:disabled {
    background-color: lightgray;
}

<input type="text" disabled />
```

### `:not(selector)`
- Dùng để chọn tất cả các phần tử không khớp với selector chỉ định.
```html
p:not(.highlight) {
    color: gray;
}

<p class="highlight">Highlighted</p>
<p>Not highlighted</p>
```

### `:first-of-type`
- Dùng để chọn phần tử đầu tiên của loại phần tử (ví dụ: `p`, `div`, `li`).
```html
p:first-of-type {
    color: green;
}

<div>
    <p>First paragraph</p>
    <p>Second paragraph</p>
</div>
```

### `:last-of-type`
- Dùng để chọn phần tử cuối cùng của loại phần tử.
```html
p:last-of-type {
    color: red;
}

<div>
    <p>First paragraph</p>
    <p>Second paragraph</p>
</div>
```

### `:nth-of-type(n)`
- Dùng để chọn phần tử thứ n của loại phần tử trong danh sách.
```html
p:nth-of-type(2) {
    color: blue;
}

<div>
    <p>First paragraph</p>
    <p>Second paragraph</p>
</div>
```

### `:visited`
- Dùng để thay đổi màu của link sau khi nó đã được người dùng nhấn vào.
```html
a:visited {
    color: purple;
}

<a href="https://example.com">Visited link</a>
```

### `:link`
- Dùng để thay đổi thuộc tính của các link chưa được nhấn vào.
```html
a:link {
    color: blue;
}

<a href="https://example.com">Unvisited link</a>
```

### `:nth-last-child(n)`
- Dùng để chọn phần tử thứ n từ cuối lên trong danh sách.
```html
li:nth-last-child(2) {
    color: orange;
}

<ul>
    <li>1</li>
    <li>2</li>
    <li>3</li>
</ul>
```

### `:nth-last-of-type(n)`
- Dùng để chọn phần tử thứ n từ cuối lên của loại phần tử đó.
```html
p:nth-last-of-type(1) {
    color: purple;
}

<div>
    <p>First paragraph</p>
    <p>Second paragraph</p>
</div>
```

### `:only-child`
- Dùng để chọn phần tử nếu nó là con duy nhất của một parent element.
```html
p:only-child {
    color: purple;
}

<div>
    <p>Only child</p>
</div>
```

### `:empty`
- Dùng để chọn phần tử không có nội dung hoặc con.
```html
p:empty {
    border: 1px solid red;
}

<p></p>
```
