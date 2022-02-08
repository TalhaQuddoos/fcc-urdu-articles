# &rlm; CSS Grid کے ساتھ تصویروں کی گیلری بنائیں
&rlm;
![title](https://cdn-media-1.freecodecamp.org/images/1*2H0HPHmFNs2t78Zog8kd9w.png)

&rlm;
Unsplash, Pinterest اور ان جیسی کئی ویب سائٹس **positioning** اور **translating** جیسے طریقوں کو استعمال کرتے ہوئے امیج گیلری بناتی ہیں، جو کہ کافی پیچیدہ کام ہو سکتا ہے۔ یہی کام CSS Grid کو استعمال کرتے ہوئے آسانی سے کیا جا سکتا ہے۔
#### آئیے، شروع کرتے ہیں۔
## بنیادی Grid:
آئیے 8 &times; 8 سائز کی ایک گرِڈ بناتے ہیں۔ ہم دوسرے سائزوں کی گرِڈ بھی بنا سکتے ہیں لیکن ہمارے لیے یہاں  8 &times; 8 سائز کا 
گرڈ ہی بہترین ہے۔
* ایک **element** کو **grid container** بنانے کے لیے اس **element** کی **display** پراپرٹی کی ویلیو کو **grid** سیٹ کرنا پڑتا ہے۔
```css
.grid {
  display: grid;
}
```
اس مثال میں وہ `div` جس کی کلاس `grid` ہو گی، وہ ہمارا گرِڈ کنٹینر ہو گا۔
*  ہم کالموں کی چوڑائی اور تعداد کو سیٹ کرنے کیے لیے `grid-template-columns` پراپرٹی کا استعمال  کرتے ہیں جبکہ `grid-template-rows` پراپرٹی کا استعمال قطاروں (rows) کی تعداد اور چوڑائی بیان کرنے کے لیے کیا جاتا ہے۔
* `grid-gap` پراپرٹی قطاروں (rows) اور کالموں کے درمیان فاصلے کو سیٹ کرنے کے لیے استعمال کی جاتی ہے۔ یہ فاصلہ سی ایس ایس کے کسی بھی پیمانے(unit) میں متعین کی جا سکتا ہے، مثلا px, em, % وغیرہ۔ 
اس مثال میں میں نے اس کی مقدار`15px` رکھی ہے تاکہ ہمارا گرِڈ بہتر دکھے۔ 
### HTML:
```html
<div class="gallery"><div>
```

### CSS:
```css
.gallery {
    display: grid;
    grid-template-columns: repeat(8, 1fr);
    grid-template-rows: repeat(8, 5vw);
    grid-gap: 15px;
}
```
> **نوٹ:** ان قطاروں کی **height** ویوپورٹ کی چوڑائی (**view port width**) کے ساتھ منسلک ہے، تاکہ ہر سیل اپنا **aspect ratio** ٹھیک سے برقرار رکھ سکے۔ ہمارے پاس **آٹھ** قطاریں (rows) ہیں جن میں سے ہر ایک کی لمبائی **ویوپورٹ کی چوڑائی کا پانچ فیصد** (**5vw**) رکھی گئی ہے۔ میں نے ان heights کے ساتھ تجربہ کیا اور اس نتیجے پر پہنچا کہ * **ویوپورٹ کی چوڑائی کا پانچ فیصد** سائز ہی لمبائی کے لیے ٹھیک ہے۔ 


> **نوٹ:** گرِڈ کنٹینر کے سارے direct children خود بخود گرِڈ کے items بن جاتے ہیں۔

### گرِڈ آئٹمز
اب ہم گرِڈ کنٹینر کے اندر آئٹمز ڈالنے والے ہیں۔
```html
<div class="gallery">
  <figure class="gallery__item gallery__item--1">
    <img src="img/image-1.jpg" class="gallery__img" alt="Image 1">
  </figure>
  <figure class="gallery__item gallery__item--2">
    <img src="img/image-2.jpg" class="gallery__img" alt="Image 2">
  </figure>
  <figure class="gallery__item gallery__item--3">
    <img src="img/image-3.jpg" class="gallery__img" alt="Image 3">
  </figure>
  <figure class="gallery__item gallery__item--4">
    <img src="img/image-4.jpg" class="gallery__img" alt="Image 4">
  </figure>
  <figure class="gallery__item gallery__item--5">
    <img src="img/image-5.jpg" class="gallery__img" alt="Image 5">
  </figure>
  <figure class="gallery__item gallery__item--6">
    <img src="img/image-6.jpg" class="gallery__img" alt="Image 6">
  </figure>
</div>
```

### تصویروں کا سٹائل:
```css
.gallery__img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}
```
`object-fit` کی ویلیو کو `cover` مقرر کرنا ایسے ہی ہے جیسے `background image` کے `background-size` کو `cover` سیٹ کرنا۔ ایسا ہم اس لیے کر رہے ہیں تاکہ تصویر اپنے ڈبے (grid item) کی لمبائی اور چوڑائی کے اندر ٹھیک سے اس کے aspect ratio کو برقرار رکھتے ہوئے آ جائے۔ 
> **یاد رکھیے:** `object-fit` پراپرٹی صرف اس وقت کام کرتی ہے جب ہم نے اس کی width اور height سیٹ کی ہوئی ہو۔

