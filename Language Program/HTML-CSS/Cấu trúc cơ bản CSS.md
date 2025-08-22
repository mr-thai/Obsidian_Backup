---
tags:
  - language_program
  - basic
---
## 1. Cách viết CSS

### 1.1 Inline CSS (trong thuộc tính `style`)

### 1.2 Internal CSS (`<style>`)

### 1.3 External CSS (`.css` file + `<link>`)

### 1.4 Selectors

- 1.4.1 Cơ bản: `tag`, `.class`, `#id`
    
- 1.4.2 Kết hợp: `div p`, `div > p`, `div + p`, `div ~ p`
    
- 1.4.3 Nhóm: `h1, h2, p {}`
    
- 1.4.4 Universal selector: `*`
    
- 1.4.5 Attribute selectors: `[type="text"]`, `[attr^=val]`, `[attr$=val]`, `[attr*=val]`
    

---

## 2. Thuộc tính cơ bản

### 2.1 Màu sắc

- 2.1.1 `color`
    
- 2.1.2 `background-color`
    
- 2.1.3 `background-image`
    
- 2.1.4 `linear-gradient`, `radial-gradient`
    

### 2.2 Font & chữ

- 2.2.1 `font-family`
    
- 2.2.2 `font-size`
    
- 2.2.3 `font-weight`
    
- 2.2.4 `line-height`
    
- 2.2.5 `letter-spacing`
    
- 2.2.6 `word-spacing` (bổ sung)
    
- 2.2.7 `text-align`
    
- 2.2.8 `text-decoration`
    
- 2.2.9 `text-transform` (uppercase/lowercase/capitalize) (bổ sung)
    
- 2.2.10 `white-space`, `overflow-wrap` (xử lý xuống dòng) (bổ sung)
    

### 2.3 Kích thước

- 2.3.1 `width`, `height`
    
- 2.3.2 `max-width`, `min-width`
    
- 2.3.3 `max-height`, `min-height`
    

### 2.4 Border & Outline

- 2.4.1 `border`
    
- 2.4.2 `border-radius`
    
- 2.4.3 `outline`
    

### 2.5 Box model

- 2.5.1 `margin`
    
- 2.5.2 `padding`
    
- 2.5.3 `box-sizing`
    

### 2.6 Hiển thị

- 2.6.1 `display` (block, inline, inline-block, none)
    
- 2.6.2 `visibility: hidden` vs `display: none` (bổ sung)
    
- 2.6.3 `opacity` (độ trong suốt) (bổ sung)
    

---

## 3. Bố cục (Layout)

### 3.1 Position

- 3.1.1 `static`
    
- 3.1.2 `relative`
    
- 3.1.3 `absolute`
    
- 3.1.4 `fixed`
    
- 3.1.5 `sticky`
    
- 3.1.6 `z-index`
    

### 3.2 Float & Clear

### 3.3 Flexbox

- 3.3.1 `display: flex`
    
- 3.3.2 `flex-direction`
    
- 3.3.3 `justify-content`
    
- 3.3.4 `align-items`
    
- 3.3.5 `align-content` (bổ sung)
    
- 3.3.6 `flex-wrap`
    
- 3.3.7 `flex-grow`, `flex-shrink`, `flex-basis` (bổ sung)
    
- 3.3.8 `order`
    
- 3.3.9 `gap`
    

### 3.4 Grid

- 3.4.1 `display: grid`
    
- 3.4.2 `grid-template-rows`, `grid-template-columns`
    
- 3.4.3 `grid-row`, `grid-column`
    
- 3.4.4 `grid-area`
    
- 3.4.5 `auto-fit`, `auto-fill`
    
- 3.4.6 `gap` (grid-gap)
    

### 3.5 Responsive

- 3.5.1 `@media` query
    
- 3.5.2 `meta viewport`
    
- 3.5.3 Responsive units: `%`, `em`, `rem`, `vh`, `vw`
    
- 3.5.4 Clamp: `clamp(min, preferred, max)` (bổ sung)
    

---

## 4. CSS nâng cao

### 4.1 Pseudo-class

- 4.1.1 `:hover`
    
- 4.1.2 `:active`
    
- 4.1.3 `:focus`
    
- 4.1.4 `:nth-child()`
    
- 4.1.5 `:first-child`, `:last-child`, `:not()`, `:checked` (bổ sung)
    

### 4.2 Pseudo-element

- 4.2.1 `::before`
    
- 4.2.2 `::after`
    
- 4.2.3 `::first-line`, `::first-letter` (bổ sung)
    

### 4.3 Transition

- 4.3.1 `transition-property`
    
- 4.3.2 `transition-duration`
    
- 4.3.3 `transition-timing-function`
    
- 4.3.4 `transition-delay` (bổ sung)
    

### 4.4 Animation

- 4.4.1 `@keyframes`
    
- 4.4.2 `animation-name`
    
- 4.4.3 `animation-duration`
    
- 4.4.4 `animation-iteration-count`
    
- 4.4.5 `animation-delay`, `animation-fill-mode` (bổ sung)
    

### 4.5 Transform

- 4.5.1 `scale`
    
- 4.5.2 `rotate`
    
- 4.5.3 `translate`
    
- 4.5.4 `skew`
    
- 4.5.5 `matrix` (bổ sung)
    

### 4.6 Shadow

- 4.6.1 `box-shadow`
    
- 4.6.2 `text-shadow`
    

### 4.7 CSS Variables

- 4.7.1 `--varName: value;`
    
- 4.7.2 `var(--varName)`
    

### 4.8 CSS Functions

- 4.8.1 `calc()`
    
- 4.8.2 `min()`
    
- 4.8.3 `max()`
    
- 4.8.4 `clamp()`
    

### 4.9 Fonts

- 4.9.1 Google Fonts
    
- 4.9.2 `@font-face`
    

### 4.10 Background nâng cao (bổ sung)

- 4.10.1 `background-size`
    
- 4.10.2 `background-position`
    
- 4.10.3 `background-attachment: fixed` (parallax)
    

### 4.11 Filter & Blend (bổ sung)

- 4.11.1 `filter: blur(), brightness(), contrast()`
    
- 4.11.2 `mix-blend-mode`
