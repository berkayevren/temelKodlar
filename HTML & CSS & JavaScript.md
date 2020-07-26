# HTML & CSS & JavaScript

## 22.07.2020

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
## 23.07.2020

```javascript
let data = [
  {firstName:'Berkay', age:23},
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
---
```javascript
let people = [
  {firstName:'Berkay', lastName:'EVREN'},
  {firstName:'Ali', lastName:'ÖZDEMİR'},
  {firstName:'Ahmet', lastName:'TURGUT'}
];

let val = people.map(function(item){
  return item.firstName + ' ' + item.lastName;
});

console.log(val);   // val: string elemanları olan bir dizi olarak döner
```
> map() fonksiyonu kullanımı
---
```javascript
function sum(a=0,b=0){ ... } yerine Function Expressions:

var sum = function(a=0,b=0){    // Default 0 değerleri ES6 ile gelen bir özellik
  var c = a + b;
  return c;
}

console.log(sum(10,20));
```
> Function Expressions
---
```javascript
function sumAll(){
  var total = 0;
  
  for(let i = 0; i < arguments.length; i++){
    total += arguments[i];
  }
  
  return total;
}

console.log(sumAll(10,20,30,40,50));
```
> arguments özelliği
---
```javascript
var age = 20;

function(){
  var age = 30;
  console.log(age);   // age = 30
}
console.log(age);     // age = 20;

if(true){             
  var age = 40;       // Block scope oluşturmaz
  console.log(age);   // age = 40
}
console.log(age);     // age = 40

// ES6 ile gelen let ve const tipleri block scope oluşturur
if(true){
  var model   = 'Mercedes';
  let year    = 2016;
  const color = 'white';
  console.log(model, year, color);  // Aynen yazar
}
console.log(model); // var tanımı if içerisinde de global scope oluşturur. Yani dışarıda da geçerlidir. Aynen yazar.
console.log(year);  // let tanımı block scope oluşturur. Yani dışarıda geçerli değildir.
console.log(color); // const tanımı block scope oluşturur. Yani dışarıda geçerli değildir.
```
> Scops
---
```javascript
document.querySelector('#ornek');
document.getElementById('ornek');   // querySelector ile aynı seçimi yapar

let val = document.querySelector('#ornek');   // val yazılan yere bu ifade yazılmış olur

document.querySelector('li');                                               // İlk bulduğu li elemanını seçer
val = document.querySelectorAll('li');                                      // Bütün li elemanlarını seçer. NodeList döndürür.
val.forEach(function(item,index){item.textContent = `${index} - merhaba`}); // NodeList, forEach yapısına sahip olduğu için kullanabiliriz

val = document.querySelectorAll('li:nth-child(even)');            // Çift elemanlar seçildi
val.forEach(function(item){item.style.background = 'grey';});     // Bu şekilde renkli bir liste oluşturulabilir

document.querySelector('li:nth-child(3)');                        // CSS selector yapısı aynen kullanılabilir
document.querySelector('li:nth-child(3)').style.color = 'red';
document.querySelector('li:nth-child(3)').textContent = 'deneme'; // textContent = innerText

document.querySelector('#ornek').innerHtml = '<b>deneme</b>';
document.querySelector('#ornek').innerText = 'deneme';

document.querySelector('#ornek').className = 'ornekClass';    // Tüm class ları siler ve ornekClass ı yükler
document.querySelector('#ornek').classList.add('ornekClass'); // Var olan class ların sonuna ornekClass ı ekler

val = document.getElementsByClassName('ornekClass');          // Kaç adet ornekClass varsa o büyüklükte bir Collection döndürür.
val[2].style.fontSize = '25px';

/* getElement yapıları Collection döndürür. querySelector yapıları NodeList döndürür. */

for(let i = 0; i < val.length; i++){                          // Collection, forEach metodunu içermediği ve for metodu içerdiği için for kullandık
  val[i].style.color = 'red';
}

val = val[0].getElementsByTagName('div');   // ilk ornekClass sınıfının altındaki div elementlerini seçer 
```
> querySelector ve alternatifleri
---
## 25.07.2020

```javascript
let val;

let list = document.querySelector('.ornekClass');

val = list.childNodes;              // Bütün child Node ları alır
val = list.childNodes[0].nodeType;  // Node türünü döndürür
// element: return 1, attribute: return2, text: return 3, comment: retrun 4

val = list.children;  // HTMLCollection döndürür. Sadece html ifadeleri
val = list.children[0].textContent = 'deneme';
val = list.children[0].children;

val = list.firstChild;        // Node döndürür
val = list.firstElementChild; // HTML tag döndürür
val = list.children[0];       // Üstteki ile aynı

val = list.childElementCount;
val = list.parentElement.parentElement; // Üst elementin üst elementini döndürür.

val = list.children[0].nextSibling;             // children[0] dan sonraki Nodu u döndürür
val = list.children[0].nextElementSibling;      // children[0] dan sonraki HTML tag ı döndürür
val = list.children[1].previousElementSibling;  // children[1] den önceki HTML tag ı döndürür

for(let i = 0; i < list.children.length; i++){
  console.log(list.children[i]);
}

for(let i = 0; i < list.childNodes.length; i++){  // Bir önceki for döngüsü ile aynı işi yapar
  if(list.childNodes[i].nodeType === 1){
    console.log(list.childNodes[i]);
  }
}
```
> DOM elementlerini seçme
---
```javascript
const list = document.querySelector('.ornekClass');

list.remove();                              // ornekClass sınıfındaki tag ın altındaki elemanları siler
list.children[0].remove();                  // ornekClass sınıfındaki tag ın altındaki ilk elemanı siler
list.removeChild(list.children[0]);         // Aynı işlemi yapar
list.children[0].removeAttribute('class');  // class Attribute unu siler


const h2 = document.createElement('h2');
h2.setAttribute('class', 'ornekClass');
h2.className = 'ornekClass ikinciClass ucuncuClass';  // Üsttekinin alternatifi
h2.setAttribute('data-id', '3');
h2.appendChild(document.createTextNode('deneme'));    // İçerisinde deneme yazan h2 taglı bir element oluşturuldu

const parent = document.querySelector('.ornekClassParent');  // ornekClass sınıfının üstündeki ornekClassParent sınıfı
parent.replaceChild(h2, list);  // oluşturulan yeni element, eski ornekClass sınıflı element yerine yazıldı


val = list.className;                 // classları string olarak verir
val = list.classList;                 // classları liste olarak verir
val = list.classList[0];              // classlarından ilkini seçer
val = list.classList.add('new');      // new class ını ekler
val = list.classList.remove('new');   // new class ını siler
val = list.getAttribute('href');      // href Attribute unun içini string olarak döndürür
val = list.setAttribute('href', 'http://google.com/');
val = list.hasAttribute('data-val');  // true / false
```
> DOM elementleri silme ve düzenleme
---
```javascript
const btn = document.querySelector('#btn1');

btn.addEventListener('click',fonksiyon1);
btn.addEventListener('click',fonksiyon2);
function fonksiyon1() {...};
function fonksiyon2() {...};

btn.addEventListener('click',function(e){
  let val;
  
  val = e;  
  console.log(val); // event objesinin bütün bilgileri görüntülenir
  
  val = e.target; // hangi elemente (butona) tıklandığını gösterir
  val = e.target.id;
  val = e.target.classList;
  val = e.type    // event tipini verir (click)
  
  e.preventDefault(); // Örneğin href etkisini yok eder
  
});
```
> Event Listener kullanımı
---
```javascript
const btn = document.querySelector('#btn1');

btn.addEventListener('dblclick',eventHandler);
btn.addEventListener('mousedown',eventHandler);   // Tıklayınca
btn.addEventListener('mouseup',eventHandler);     // Tıklama kalkınca
btn.addEventListener('mouseenter',eventHandler);  // Üst üste nesnelerde diğer nesneye geçilse bile ana gövdenin içerisinden çıkılmadıkça tekrar enter oluşmaz
btn.addEventListener('mouseleave',eventHandler);  // Üst üste nesnelerde ana gövdeden çıkılmadıkça leave oluşmaz
btn.addEventListener('mouseover',eventHandler);   // Üst üste nesnelerde diğer nesneye geçildiğinde tekrar over oluşur
btn.addEventListener('mouseout',eventHandler);    // Üst üste nesnelerde diğer nesneye geçildiğinde out olayı oluşur
// mouseover ve mouseout nesnelerin alt elemanlarında da geçerli olur. mouseenter ve mouseleave alt elemanlarda geçerli değildir.

const h1 = document.querySelector('h1');  // Koordinat yazılacak etiket

ul.addEventListener('mousemove',eventHandler);

function eventHandler(event){
  h1.textContent = `MouseX: ${event.offsetX}    // ul nesnesi için üst sol nokta offset olarak belirlenerek
                    MouseY: ${event.offsetY}`;  // ul içerisinde mouse gezerken mouse koordinatları h1 taglı alana yazdırılıyor
}
```
> Mouse Events
---
## 26.07.2020

```javascript
const input = document.querySelector('#inputArea');

input.addEventListener('keydown',eventHandler);
input.addEventListener('keyup',eventHandler);
input.addEventListener('keypress',eventHandler);
input.addEventListener('focus',eventHandler);     // Input alanına tıklandığında
input.addEventListener('blur',eventHandler);      // Input alanından çıkıldığında
input.addEventListener('cut',eventHandler);       // Input alanında kesme işlemi yapıldıysa
input.addEventListener('paste',eventHandler);     // Input alanına yapıştırma işlemi yapıldıysa
input.addEventListener('select',eventHandler);    // Input alanında yazı seçildiyse

const selectMenu = document.querySelector('#select');
input.addEventListener('change',eventHandler);    // Select menüde seçili seçenek değiştiyse

function eventHandler(e){
  console.log('Event type: ' + e.type);     // Event tipi (focus)
  console.log('Key code ' + e.keyCode);     // Basılan tuşun ASCII karşılığı
  console.log('value ' + e.target.value);   // target ın yani input un içerisinde yazılı değer
  e.target.style.backgroundColor = 'blue';  // örneğin focus olayı gerçekleşince arka plan mavi olsun
}

const form = document.querySelector('form');
form.addEventListener('submit', eventHandler);

function eventHandler(e){   // Bu şekilde formun submit butonuna tıklandığında bir linke gitmemesi
  e.preventDefault();       // ve eventHandler fonksiyonunun içerisini yapması sağlanır
}
```
> Keyboard Events
