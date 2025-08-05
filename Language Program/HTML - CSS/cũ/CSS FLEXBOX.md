![[Pasted image 20241022011725.png]]
- flex container : thẻ chứa
- flex item: thẻ thành phần
# Các thuộc tính cơ bản
- **display**: thuộc tính quyết định chế độ hiển thị.
	- `flex`: chế độ hiển thị flex.
	- `inline-flex`: cũng là chế độ hiển thị flex nhưng nằm trên một dòng.
- **flex-direction**: thuộc tính quyết định phương hướng của trục chính (main axis).
	- `row` (mặc định): từ trái sang phải.
		![[Pasted image 20241022110426.png]]
	- `row-reverse`: từ phải sang trái.
	    ![[Pasted image 20241022110441.png]]
	- `column`: từ trên xuống dưới.
		![[Pasted image 20241022110546.png]]
	- `column-reverse`: từ dưới lên trên.
	    ![[Pasted image 20241022110613.png]]
- **flex-wrap**: thuộc tính quyết định xem các phần tử flex có xuống dòng không khi các phần tử trên một dòng bị co lại do thay đổi kích thước khung hình.
	- `nowrap` (mặc định): tắt chức năng tự động xuống dòng.
	    ![[Pasted image 20241022110635.png]]
	- `wrap`: bật chức năng tự động xuống dòng.
	    ![[Pasted image 20241022110657.png]]
	- `wrap-reverse`: chức năng tự động xuống dòng theo hướng ngược lại (các phần tử nhảy lên trên).
	    ![[Pasted image 20241022110720.png]]
- **flex-basis**: thuộc tính xác định kích thước ban đầu của trục chính.
	- (length): giá trị độ dài như `px`, `%`, `em`, v.v.
- **justify-content**: căn chỉnh các phần tử flex theo trục chính.
	- `flex-start` (mặc định): kéo các phần tử về phía đầu trục chính.
		![[Pasted image 20241022111019.png]]
	- `flex-end`: kéo các phần tử về phía cuối trục chính.
		![[Pasted image 20241022111036.png]]
	- `center`: kéo các phần tử vào giữa trục chính.
		![[Pasted image 20241022111109.png]]
	- `space-between`: tạo khoảng trống đều giữa các phần tử, với các phần tử ngoài cùng sát với đầu và cuối trục.
		![[Pasted image 20241022111057.png]]
	- `space-around`: tạo các khoảng trống đều giữa các phần tử, kể cả khoảng trống trước phần tử đầu và sau phần tử cuối.
		![[Pasted image 20241022111136.png]]
	- `space-evenly`: khoảng cách giữa các phần tử và giữa phần tử đầu/cuối với cạnh container đều nhau.
- **justify-self**: tương tự với `justify-content` nhưng chỉ áp dụng cho từng phần tử riêng lẻ trong flex container. Nếu đã khai báo `justify-content`, thì không cần thiết khai báo `justify-self` nữa.
	- `flex-start`: kéo phần tử về phía đầu trục.
	- `flex-end`: kéo phần tử về phía cuối trục.
	- `center`: kéo phần tử vào giữa trục.
- **align-content**: tương tự `justify-content`, nhưng căn chỉnh các phần tử flex theo trục phụ (cross axis).
	- `flex-start`: kéo các phần tử về đầu trục phụ.
		![[Pasted image 20241022111216.png]]
	- `flex-end`: kéo các phần tử về cuối trục phụ.
		![[Pasted image 20241022111232.png]]
	- `center`: kéo các phần tử vào giữa trục phụ.
	    ![[Pasted image 20241022111245.png]]
	- `space-between`: tạo khoảng trống đều giữa các phần tử theo trục phụ.
		![[Pasted image 20241022111305.png]]
	- `space-around`: tạo các khoảng trống đều giữa các phần tử theo trục phụ, kể cả khoảng trống trước và sau các phần tử đầu/cuối.
	    ![[Pasted image 20241022111319.png]]
	- `stretch` (mặc định): kéo dãn các phần tử để lấp đầy trục phụ.
	    ![[Pasted image 20241022111335.png]]
- **align-items**: căn chỉnh các phần tử theo trục phụ trong flex container.
	- `flex-start`: kéo các phần tử về đầu trục phụ.
		![[Pasted image 20241022110805.png]]
	- `flex-end`: kéo các phần tử về cuối trục phụ.
		![[Pasted image 20241022110824.png]]
	- `center`: kéo các phần tử vào giữa trục phụ.
	    ![[Pasted image 20241022110835.png]]
	- `baseline`: căn chỉnh theo đường cơ sở của nội dung.
		![[Pasted image 20241022110900.png]] *ảnh có nhích lên một tí*
	- `stretch` (mặc định): kéo dãn các phần tử để lấp đầy trục phụ.
		![[Pasted image 20241022110943.png]]
- **align-self**: tương tự `align-items`, nhưng chỉ áp dụng cho từng phần tử riêng lẻ.
	- `flex-start`: kéo phần tử về đầu trục phụ.
	  ![[Pasted image 20241022111431.png]]
	- `flex-end`: kéo phần tử về cuối trục phụ.
	  ![[Pasted image 20241022111442.png]]
	- `center`: kéo phần tử vào giữa trục phụ.
	  ![[Pasted image 20241022111453.png]]
	- `baseline`: căn chỉnh theo đường cơ sở của nội dung.
	  ![[Pasted image 20241022111506.png]]
	- `stretch`: kéo dãn phần tử để lấp đầy trục phụ.
	  ![[Pasted image 20241022111532.png]]
- **flex-grow**: dùng để tăng kích thước của phần tử trong trục chính.
	- (number): tỷ lệ nở rộng so với các phần tử khác, giá trị mặc định là `0`.
	  **không có grow**
	  ![[Pasted image 20241022111842.png]]
	  **tất cả các phần tự đều có grow=1**
	  ![[Pasted image 20241022111926.png]]
	  **tất cả các phần tự đều có grow khác nhau**
	  ![[Pasted image 20241022111900.png]]
- **flex-shrink**: ngược với `flex-grow`, dùng để giảm kích thước của phần tử trong trục chính.
	- (number): tỷ lệ co lại so với các phần tử khác, giá trị mặc định là `1`.
	  **các phần tự đều có shrink như nhau**
	  ![[Pasted image 20241022112516.png]]
	 **các phần tự có shrink khác nhau**
	 ![[Pasted image 20241022112610.png]]	 
- **flex**: cú pháp rút gọn của `flex-grow` + `flex-shrink` + `flex-basis`.
	- Ví dụ: nếu `flex: 2`, phần tử có giá trị này sẽ lớn hơn 2 lần so với các phần tử khác khi kích thước thay đổi.
- **flex-flow**: cú pháp rút gọn của `flex-direction` + `flex-wrap`.
	- Ví dụ: `flex-flow: row wrap;` sẽ đặt hướng chính là hàng và cho phép xuống dòng.
- **order**: quyết định thứ tự của các phần tử flex.
	- (number): giá trị số xác định thứ tự hiển thị, mặc định là `0`.
	  **các items ban đầu**
	  ![[Pasted image 20241022113058.png]]
	  **các item sau khi sắp xếp**
	  ![[Pasted image 20241022113129.png]]