- là đơn vị được sự dụng trong css
# Absolute units ( Đơn vị tuyệt đối)
### đây là giá trị sẽ không thay đổi khi bị tác động bởi các tác động đặc biệt như kích thước màn hình,...
- px
- pt
- cm
- mm
- inch
- pc

# Relative units (Đơn vị tương đối)
- % (phụ thuộc vào đối tượng mà nó liên kết)
	- Thuộc tính `width`, `height` với đơn vị `%` sẽ phụ thuộc vào kích thước `width`, `height` của thẻ mà nó phụ thuộc, mặc định là thẻ cha trực tiếp. Ví dụ: Thẻ cha có width `100px`, thẻ con có `width: 50%` sẽ tương ứng với `50px`.
	-  thuộc tính `width` và `height`, khi đặt theo `%` sẽ tỉ lệ vào thẻ mà nó phụ thuộc, mặc định là thẻ cha trực tiếp của nó. Vì vậy, thẻ cha của nó phải có kích thước cho `width` hoặc `height` thì thẻ con đặt theo `%` mới có tác dụng.

		- Với chiều rộng thì các thẻ như `body`, `div` sẽ mặc định có `width: 100%`. Vì vậy, ở bài [#1](https://fullstack.edu.vn/learning/html-css?id=dd794d1c-cea2-4f50-a792-91765cc92a74) các bạn mà comment thuộc tính `width` của `.box1` lại, bạn sẽ thấy nó chiếm `100%` chiều rộng.
		- Với chiều cao, mặc định các thẻ có `height: auto`, chiều cao sẽ tự động thay đổi khi nội dung bên trong nó tăng lên. Nếu thẻ cha có `height: auto` và thẻ con của nó `height: 50%` thì sẽ không có tác dụng, khi ấy thẻ con vẫn có `height: auto`.
- rem (phụ thuộc vào thuộc tính font size trong thẻ html)
	- giá trị `1rem` này sẽ phụ thuộc vào giá trị `font-size` được đặt cho thẻ `html`, mặc định tại trình duyệt thì `font-size: 16px`, vì vậy mặc định `font-size: 1rem` sẽ bằng `16px`, `2rem` sẽ bằng `32px`.
	- Mặc định font-size của thẻ html là 16px - tương ứng với 100%. Khi ấy, `1rem` sẽ bằng `16px`. Vậy khi muốn đặt font-size tương ứng với `10px` thì ta sẽ đặt bằng bao nhiêu rem?
	- Đương nhiên, theo mặc định `10px` đổi sang rem sẽ là `10/16 = 0.625`, như vậy để CSS bằng đơn vị `rem` ra được kích cỡ tương ứng `10px` ta sẽ CSS là `font-size: 0.625rem`.
	-  Khá hại não khi phải quy đổi như vậy. Vì vậy, chúng ta có thể quy đổi tỉ lệ tại thẻ html với CSS `font-size: 62.5%`. Kết quả thu được, `1rem = 10px`, `1.6rem = 16px`, `2rem = 20px`, `2.4rem = 24px`.
- pt
- em (phụ thuộc vào thể gần nhất chứa nó tức là nó sẽ quét rừ trong ra ngoài đến khi tìm thấy giá trị được khai báo thì dừng và lấy giá trị đó làm giá trị của mình)
- vw (phụ thuộc vào chiều rộng kích thước trình duyệt)
- vh (phụ thuộc vào chiều cao kích thước trình duyệt)
- vmin
- vmax
- ex
- ch
