## **1. Tổng quan về CSS Animations**

CSS Animations hoạt động dựa trên hai thành phần chính:

1. **@keyframes**: Định nghĩa các trạng thái và thay đổi giữa các trạng thái trong hoạt hình.
2. **Thuộc tính animation**: Điều chỉnh cách hoạt hình hoạt động trên phần tử.

---

## **2. Cách tạo Animation trong CSS**

### **Cấu trúc cơ bản**

- **@keyframes**:

```css
@keyframes animation-name {
  0% { /* Trạng thái ban đầu */ }
  100% { /* Trạng thái cuối cùng */ }
}
```

- **Áp dụng vào phần tử**:

```css
.element {
  animation: animation-name duration timing-function delay iteration-count direction fill-mode;
}
```

---

### **3. Thuộc tính `animation` chi tiết**

|Thuộc tính|Mô tả|Giá trị mặc định|
|---|---|---|
|`animation-name`|Tên của animation được định nghĩa trong `@keyframes`.|none|
|`animation-duration`|Thời gian chạy 1 chu kỳ của animation.|0s|
|`animation-timing-function`|Cách animation tăng tốc hoặc giảm tốc trong quá trình chạy.|ease|
|`animation-delay`|Độ trễ trước khi animation bắt đầu.|0s|
|`animation-iteration-count`|Số lần lặp của animation.|1|
|`animation-direction`|Hướng của animation (chạy ngược, chạy lại từ đầu, v.v.).|normal|
|`animation-fill-mode`|Quy định trạng thái phần tử khi animation chưa bắt đầu hoặc đã kết thúc.|none|
|`animation-play-state`|Dừng hoặc chạy animation.|running|

---

### **4. Chi tiết từng thuộc tính**

#### **4.1. animation-name**

- Định nghĩa tên của animation trong `@keyframes`.

```css
@keyframes slideIn {
  0% { transform: translateX(-100%); }
  100% { transform: translateX(0); }
}

.element {
  animation-name: slideIn;
}
```

#### **4.2. animation-duration**

- Xác định thời gian chạy của animation (đơn vị: `s` hoặc `ms`).

```css
.element {
  animation-duration: 2s;
}
```

#### **4.3. animation-timing-function**

- Kiểm soát cách animation tăng tốc hoặc giảm tốc.  
    Các giá trị phổ biến:
    - **ease**: Bắt đầu và kết thúc chậm, ở giữa nhanh.
    - **linear**: Tốc độ không đổi.
    - **ease-in**: Bắt đầu chậm, sau đó nhanh dần.
    - **ease-out**: Bắt đầu nhanh, sau đó chậm dần.
    - **ease-in-out**: Bắt đầu và kết thúc chậm.
    - **steps(n, direction)**: Animation thực hiện qua từng bước cố định.

```css
.element {
  animation-timing-function: ease-in-out;
}
```

#### **4.4. animation-delay**

- Độ trễ trước khi animation bắt đầu.

```css
.element {
  animation-delay: 1s;
}
```

#### **4.5. animation-iteration-count**

- Số lần lặp của animation:
    - **1**: Chạy 1 lần.
    - **infinite**: Lặp vô hạn.
    - **n**: Lặp lại `n` lần.

```css
.element {
  animation-iteration-count: infinite;
}
```

#### **4.6. animation-direction**

- Quy định hướng chạy của animation:
    - **normal**: Chạy từ trạng thái đầu đến cuối (mặc định).
    - **reverse**: Chạy ngược từ cuối đến đầu.
    - **alternate**: Chạy từ đầu đến cuối, sau đó ngược lại.
    - **alternate-reverse**: Chạy từ cuối đến đầu, sau đó ngược lại.

```css
.element {
  animation-direction: alternate;
}
```

#### **4.7. animation-fill-mode**

- Quy định trạng thái phần tử khi animation chưa bắt đầu hoặc đã kết thúc:
    - **none**: Không giữ trạng thái.
    - **forwards**: Giữ trạng thái cuối cùng.
    - **backwards**: Giữ trạng thái ban đầu.
    - **both**: Giữ cả trạng thái ban đầu và cuối cùng.

```css
.element {
  animation-fill-mode: forwards;
}
```

#### **4.8. animation-play-state**

- Điều khiển animation chạy hoặc tạm dừng:
    - **running**: Animation chạy.
    - **paused**: Animation bị dừng.

```css
.element {
  animation-play-state: paused;
}
```

---

### **5. Tổ hợp nhiều thuộc tính trong `animation`**

Bạn có thể gộp các thuộc tính trên vào một dòng:

```css
.element {
  animation: slideIn 2s ease-in-out 1s infinite alternate forwards;
}
```

---

## **6. @keyframes: Chi tiết nâng cao**

Bạn có thể định nghĩa nhiều bước trong animation:

```css
@keyframes example {
  0% { transform: translateX(0); opacity: 0; }
  50% { transform: translateX(50px); opacity: 0.5; }
  100% { transform: translateX(100px); opacity: 1; }
}
```

---

## **7. Các ví dụ thực tế**

### **7.1. Fade-in (Hiệu ứng xuất hiện)**

```css
@keyframes fadeIn {
  0% { opacity: 0; }
  100% { opacity: 1; }
}

.element {
  animation: fadeIn 2s ease-in-out;
}
```

### **7.2. Bounce (Nảy lên xuống)**

```css
@keyframes bounce {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-30px); }
}

.element {
  animation: bounce 1s infinite;
}
```

### **7.3. Rotate (Quay vòng)**

```css
@keyframes rotate {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}

.element {
  animation: rotate 2s linear infinite;
}
```

---

## **8. Animation nâng cao với JavaScript**

Bạn có thể điều khiển animation bằng JavaScript với các sự kiện như:

- `animationstart`: Bắt đầu animation.
- `animationiteration`: Lặp lại animation.
- `animationend`: Kết thúc animation.

Ví dụ:

```javascript
const element = document.querySelector('.element');
element.addEventListener('animationend', () => {
  alert('Animation đã kết thúc!');
});
```

---

## **9. Các công cụ hỗ trợ tạo CSS Animations**

1. **[Animate.css](https://animate.style/)**: Bộ sưu tập animation CSS sẵn có.
2. **[Keyframes.app](https://keyframes.app/)**: Công cụ tạo animation trực quan.
3. **[Easing Functions Cheat Sheet](https://easings.net/)**: Thử nghiệm và chọn các hàm `timing-function`.
