# HTML & CSS & JavaScript

```css
box-sizing: border-box;
```
> padding + border boyuta dahil
---
```css
html {
  font-size: 10px;
}
div {
  height: 45rem;
}
```
> height = 45*10 = 450px 
---
```css
background-image: xyz.png;
background-size: cover;
background-position: center;
```
> Düzgün boyutlanmış bir arkaplan resmi
---
```css
.div1 {
  float: left;
}
.div2.clearfix::after {
  content: "";
  display: block;
  clear: both;
}
```
> ```float: left``` den sonra oluşan kaymaları düzelten clearfix kullanımı.
---
```javascript
var val = x.toFixed(4)
```
> 10.**0000**
---
```javascript
let val = x.toPrecision(4)
```
> **10.00**
---
```javascript
x === y
```
> Hem değer hem tip kontrolü
---
```javascript
let val;

val = Math.round(x);    // Yuvarla -> En yakına
val = Math.ceil(x);     // Yuvarla -> Yukarıya
val = Math.floor(x);    // Yuvarla -> Aşağıya
val = Math.min(array);  // Array'in en küçük değeri
```
> Temel math fonksiyonları
---
```javascript
let val, minX, maxX;

val = minX + Math.random() * (maxX - minX);
```
> minX ve maxX aralığında rastgele sayı üretme
