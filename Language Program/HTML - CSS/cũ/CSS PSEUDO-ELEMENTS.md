- PSEUDO-ELEMENTS là phần tự giải
- phần tự giải luôn có dấu `::`
### `::before`
- Dùng để thêm nội dung trước phần tử được chọn.
```html
p::before {
    content: "Start: ";
    color: green;
}

<p>This is a paragraph.</p>
```

### `::after`
- Dùng để thêm nội dung sau phần tử được chọn.
```html
p::after {
    content: " End.";
    color: red;
}

<p>This is a paragraph.</p>
```

### `::first-letter`
- Dùng để định kiểu chữ cái đầu tiên của phần tử, thường dùng với đoạn văn.
```html
p::first-letter {
    font-size: 200%;
    color: blue;
}

<p>This is a paragraph.</p>
```

### `::first-line`
- Dùng để định kiểu dòng đầu tiên của phần tử, thường dùng với đoạn văn.
```html
p::first-line {
    font-weight: bold;
    color: purple;
}

<p>This is a paragraph. It has multiple lines and styles only affect the first line.</p>
```

### `::selection`
- Dùng để định kiểu phần văn bản khi người dùng chọn (highlight).
```html
p::selection {
    background-color: yellow;
    color: black;
}

<p>Select this text to see the effect.</p>
```

### `::placeholder`
- Dùng để định kiểu cho nội dung placeholder của các phần tử input.
```html
input::placeholder {
    color: gray;
    font-style: italic;
}

<input type="text" placeholder="Enter your name" />
```

### `::marker`
- Dùng để định kiểu cho các dấu đầu dòng hoặc số trong danh sách.
```html
li::marker {
    color: red;
    font-size: 120%;
}

<ul>
    <li>First item</li>
    <li>Second item</li>
    <li>Third item</li>
</ul>
```

### `::backdrop`
- Dùng để định kiểu phần nền phía sau một phần tử có dialog khi mở ra.
```html
dialog::backdrop {
    background-color: rgba(0, 0, 0, 0.5);
}

<dialog open>This is a dialog</dialog>
```

### `::file-selector-button`
- Dùng để định kiểu cho nút chọn file của phần tử `<input type="file">`.
```html
input[type="file"]::file-selector-button {
    background-color: blue;
    color: white;
    border: none;
    padding: 5px 10px;
}

<input type="file" />
```

### `::part()`
- Dùng để định kiểu các phần tử được đặt tên bằng `part` trong Shadow DOM.
```html
custom-element::part(button) {
    background-color: red;
}

<!-- Ví dụ bên trong một phần tử custom-element -->
<custom-element>
    <button part="button">Click me</button>
</custom-element>
```

### `::slotted()`
- Dùng để định kiểu các phần tử được đưa vào Shadow DOM qua `<slot>`.
```html
custom-element::slotted(p) {
    color: blue;
}

<!-- Ví dụ bên trong phần tử custom-element -->
<custom-element>
    <p>Slotted content</p>
</custom-element>
```

### `::cue`
- Dùng để định kiểu cho phụ đề của video.
```html
::cue {
    color: yellow;
    background-color: black;
}

<video controls>
    <track src="subtitles.vtt" kind="subtitles" srclang="en" label="English">
</video>
```

Trên đây là danh sách các CSS pseudo-elements thông dụng, viết theo định dạng bạn yêu cầu!