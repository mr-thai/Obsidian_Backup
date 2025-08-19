# mô tả 
- một công cụ đơn giản chạy trong nền cli 
- viết bằng c++ để tối ưu tài nguyên
## 1. mô tả chi tiết
- trước khi bắt đầu kiểm tra xem % máy có nằ trong 95%-100% ko ? nếu không thì ra thông báo và tạm ngưng rồi quay lại trang chủ
- nếu đã qua kiểm tra pin thì tiến hành kiểm tra xem có file chứa thông tin thời gian đã quá `time_battery.txt` ko ? nếu không thì tạo file
- sau khi kết thúc kiểm tra tiến hành mở một đường link youtube dài ít nhất 10 tiếng chất lượng tuỳ chọn
- cuối dùng sau khi kết thúc các lệnh trên tiến ành tính giờ 
## 2. mô tả app cli
```
2 h 24 p 12s
```
- chạy trong 3 vòng for với 
	- vòng 1 chạy từ 0 - 24 tương ứng với h
	- vòng 2 chay từ 0 - 59 tương ứng với p
	- vòng trong cùng từ 0 - 59 tương ứng với s
> trong quá trình này sẽ mất 1s trước khi sang trạng thái tiếp theo
- trong quá trình chạy quá trình xoá và ghi lại nội dùng vào file hiện trong cli diễn ra liên tục 
