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
---
```javascript
let val;

val = str.replace('str1','str2');   // str içerisinde ilk bulduğu str1 yerine str2'yi yazar
val = str.replace(/str1/g,'str2');  // str içerisinde bulduğu tüm str1 ler yerine str2'yi yazar
val = str.split(',');               // Array çıktısı verir
val = str.concat(' ',str1);         // str + ' ' + str1
val = str.toLowerCase();
val = str.toUpperCase();
val = str.includes('str1');         // true / false
val = str.indexOf('str1');
val = str.substring(3,5);           // 3 ve 4 karakterleri
val = str.trim();                   // Baştaki ve sondaki boşlukları siler
val = str.startWith('str1');        // str1 ile başlıyor mu? (true / false)
```
> Temel string fonksiyonları
---
```javascript
let val;

val = arr.push(itm);          // Sona ekler
val = arr.unshift(itm);       // Başa ekler
val = arr.pop();              // Sondakini siler
val = arr.shift();            // Baştakini siler
val = arr.indexOf('str');     // str itemi kaçıncı eleman
val = arr.reverse();    
val = arr.sort();             // alfabetik sıralar (Sayısal sıralama aşağıda)
val = arr.concat(arr2);       // arr sonuna arr2 ekler
val = arr.splice(2,1);        // 2.itemden itibaren 1 item siler (2.yi siler)
val = arr.splice(2,0,'str');  // 2.itemin olduğu yere araya str yi ekler
val = arr.splice(2,1,'str');  // 2.itemi silerek 2.iteme str yi ekler

function compare(a,b) {
  if(a>b) return 1;
  if(a==b) return 0;
  if(a<b) return -1;
}
arr.sort(compare);            // Sayısal olarak sıralar
```
> Temel array fonksiyonları
---
```javascript
let data = [
  {firstName:'Berkay', age:23}
  {firstName:'Ali', age:15}
];

console.log(data[0].firstName);
```
> Obje kullanımı
---
```javascript
for(var i = 0; i < 10; i++) {
  if(i == 3) {
    console.log('Harika' + i);
    continue;
  }
  console.log(i);
}
```
> Continue sonrası yapılmaz sonraki döngüden devam eder.
---
```javascript
let cars = ['BMW','Audi','Mitsubishi'];

for(let i in cars) {
  console.log(`index: ${i} value: ${cars[i]}`); // Ters tırnak ${değişken} kullanımı
}

cars.forEach(function(item){
    console.log(item)
 });
```
> for-in ve forEach kullanımı
