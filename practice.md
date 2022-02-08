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
&rlm;
`object-fit` کی ویلیو کو `cover` مقرر کرنا ایسے ہی ہے جیسے `background image` کے `background-size` کو `cover` سیٹ کرنا۔ ایسا ہم اس لیے کر رہے ہیں تاکہ تصویر اپنے ڈبے (grid item) کی لمبائی اور چوڑائی کے اندر ٹھیک سے اس کے aspect ratio کو برقرار رکھتے ہوئے آ جائے۔ 
> **یاد رکھیے:** `object-fit` پراپرٹی صرف اس وقت کام کرتی ہے جب ہم نے اس کی width اور height سیٹ کی ہوئی ہو۔

&rlm;
![image-2](https://cdn-media-1.freecodecamp.org/images/1*FBsVH1n06ufBr_WcB_xDDQ.png)

> **یاد رکھیے:** گرِڈ کے آئٹمز پہلے سے طے شدہ طور پر **grid auto placement** کے اصولوں کے مطابق ظاہر ہوتے ہیں۔

## گرِڈ کے آئٹمز کی ترتیب:
گرِڈ کے آئٹمز کو ترتیب دینے سے پہلے ہم کچھ بنیادی چیزوں کا مطالعہ کریں گے۔

**grid** والا `div` گرِڈ کنٹینر ہے، جس کے سرے براہِ راست children گرِڈ آئٹمز ہیں۔ جب ہم نے گرِڈ کے ٹریکس کو `grid-template-columns` اور `grid-template-rows` کے ساتھ متعین کیا تھا تو **grid** ںے ہمیں نمبروں والی لائنیں دی تھیں، جن **grid lines** کہا جاتا ہے تاکہ ہم ان کے ذریعے آئٹمز کی پوزیشن کو سیٹ کر سکیں۔ ہر لائن کے ساتھ ایک numerical index منسلک ہے۔ 

کالم 1 سے شروع ہوتے ہیں، عام طور پہ بائیں سے دائیں جانب، اور قطاریں (rows) بھی 1 سے شروع ہوتی ہیں مگر اوپر سے نیچے کی طرف۔ ایک کالم یا قطار بنانے کے لیے دو لائنیں درکار ہوتی ہیں، لہٰذا ہمارا 8 کالم اور آٹھ قطاروں والا گرِڈ 9 کالم والی لائنوں اور 9 قطار والی لائنوں پر مشتمل ہے۔

پہلی اور دوسری عمودی ( vertical ) لائنیں پہلے کالم کی ابتدا اور انتہا کو بیان کرتے ہیں، دوسری اور تیسری لائن دوسرے کالم کی ابتدا و انتہا کو بیان کرتی ہیں اور اسی طرح باقی تمام لائنیں۔ اسی طرح پہلی اور دوسری افقی (horizontal) لائنین پہلی قطار کا تعین کرتی ہیں اور اسی طرح باقی افقی لائنیں بھی۔ اوپر کی گئی باتوں کو جاننے سے آپ کو یہ بات سمجھنے میں مدد ہو گی کہ ہم تصویروں کی جگہ گرِڈ میں کیسے متعین کریں گے۔

اب ہم آئٹمز کی جگہ کو کنٹرول کرنے کے لیے گرڈ کی لائنوں کے نمبروں کا استعمال کریں گے، گرِڈ کی ہر آئٹم کے ساتھ براہِ راست CSS properties لگاتے ہوئے۔ہم یہ چیز متعین کر سکتے ہیں کہ گرڈ کا ایک آئٹم کس لائن سے شروع ہو گا اور کس لائن پر ختم ہو گ، اور یہ کتنے tracks پر پھیلے گا۔

### گرِڈ کا پہلا آئٹم
تو آئیے اب اپنے پہلے گرڈ آئٹم کے لیے کچھ CSS کے اصول لکھتے ہیں۔ پہلے ہم `grid-column-start` پراپرٹی کو استعمال کریں گے یہ بتانے کے لیے کہ پہلا گرڈ آئٹم کس لائن سے شروع اور گا، اور `grid-column-end` یہ بتانے کے لیے کہ پہلا گرڈ آئٹم کس گرڈ لائن پر ختم ہو گا۔

تو `grid-column-start` کی ویلیو ایک نمبر ہے جو کالم کے بائیں کنارے والی گرڈ لائن کے بارے میں بتاتا ہے جبکہ`grid-column-end` کی ویلیو کالم کی دائیں جانب والی گرڈ لائن کو ظاہر کرتی ہے۔

لہٰذا نیچے دی گئی مثال میں، `grid-column-start` کی ویلیو کو **1** اور `grid-column-end` کی ویلیو کو **3** مقرر کرنے کا مطلب یہ ہے کہ یہ گرڈ آئٹم پہلی گرڈ لائن کے بائیں کنارے سے شروع ہو کر تیسری گرڈ لائن تک پھیلے گا، جس سے یہ دو کالم گھیرے گا۔ ہم افقی (horizontal) گرڈ لائنوں پر گرڈ آئٹم کی شروع اور آخر کی جگہ کو بتانے کے لیے `grid-row-start` اور `grid-row-end` پراپرٹیز کا استعمال اسی طریقے سے کریں گے جس طریقے سے ہم نے کالموں کے لیے کیا تھا۔
```css
.gallery__item--1 {
    grid-column-start: 1;
    grid-column-end: 3;
    grid-row-start: 1;
    grid-row-end: 3;
}
```
&rlm;
![grid item 1](https://cdn-media-1.freecodecamp.org/images/1*ScnDXtFn-7wffVN62rqg5w.png)
#### اب ہم باقی آئموں کو بھی اِنہی اصولوں کے مطابق پوزیشن دیں گے۔

### گرڈ کا دوسرا آئٹم
```css
.gallery__item--2 {
    grid-column-start: 3;
    grid-column-end: 5;
    grid-row-start: 1;
    grid-row-end: 3;
}
```
&rlm;
![grid item 2](https://cdn-media-1.freecodecamp.org/images/1*U-OLT0CdIjjxvaV-4YpjLg.png)

### گرڈ کا تیسرا آئٹم
```css
.gallery__item--3 {
    grid-column-start: 5;
    grid-column-end: 9;
    grid-row-start: 1;
    grid-row-end: 6;
}
```
&rlm;
![grid item 3](https://cdn-media-1.freecodecamp.org/images/1*wEZB6kvCDGquI_PH1yH4gQ.png)

### گرڈ کا چوتھا آئٹم
```css
.gallery__item--4 {
    grid-column-start: 1;
    grid-column-end: 5;
    grid-row-start: 3;
    grid-row-end: 6;
}
```
&rlm;
![grid item 4](https://cdn-media-1.freecodecamp.org/images/1*AkEoMuGUJM5oB7q-2SLnxA.png)

### گرڈ کا پانچواں آئٹم
```css
.gallery__item--5 {
    grid-column-start: 1;
    grid-column-end: 5;
    grid-row-start: 6;
    grid-row-end: 9;
}
```
&rlm;
![grid item 5](https://cdn-media-1.freecodecamp.org/images/1*0SA_xLddgWzrV7y0hK8kEQ.png)

### گرڈ کا چھٹا آئٹم
```css
.gallery__item--6 {
    grid-column-start: 5;
    grid-column-end: 9;
    grid-row-start: 6;
    grid-row-end: 9;
}
```
&rlm;
![grid item 6](https://cdn-media-1.freecodecamp.org/images/1*rmUZZ0lsviNcnofEoAnRPw.png)

مکمل کوڈ آپ کو نیچے مل جائے گا۔
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">

        <link href="https://fonts.googleapis.com/css?family=Josefin+Sans:300,400,400i|Nunito:300,300i" rel="stylesheet">
        <link rel="stylesheet" href="css/style.css">
        <link rel="shortcut icon" type="image/png" href="img/favicon.png">

        <title>CSS Grids Gallery</title>
    </head>
    <body>
        <div class="container">
            <div class="gallery">
                <figure class="gallery__item gallery__item--1">
                    <img src="img/image-1.jpg" alt="Gallery image 1" class="gallery__img">
                </figure>
                <figure class="gallery__item gallery__item--2">
                    <img src="img/image-2.jpg" alt="Gallery image 2" class="gallery__img">
                </figure>
                <figure class="gallery__item gallery__item--3">
                    <img src="img/image-3.jpg" alt="Gallery image 3" class="gallery__img">
                </figure>
                <figure class="gallery__item gallery__item--4">
                    <img src="img/image-4.jpg" alt="Gallery image 4" class="gallery__img">
                </figure>
                <figure class="gallery__item gallery__item--5">
                    <img src="img/image-5.jpg" alt="Gallery image 5" class="gallery__img">
                </figure>
                <figure class="gallery__item gallery__item--6">
                    <img src="img/image-6.jpg" alt="Gallery image 6" class="gallery__img">
                </figure>
            </div>
        </div>
    </body>
</html>
```
اور سی ایس ایس:
```css
*,
*::after,
*::before {
  margin: 0;
  padding: 0;
  box-sizing: inherit; 
}

html {
  box-sizing: border-box;
  font-size: 62.5%; 
}

body {
  font-family: "Nunito", sans-serif;
  color: #333;
  font-weight: 300;
  line-height: 1.6; 
}

.container {
  width: 60%;
  margin: 2rem auto; 
}

.gallery {
  display: grid;
  grid-template-columns: repeat(8, 1fr);
  grid-template-rows: repeat(8, 5vw);
  grid-gap: 1.5rem; 
}

.gallery__img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block; 
}

.gallery__item--1 {
  grid-column-start: 1;
  grid-column-end: 3;
  grid-row-start: 1;
  grid-row-end: 3;

  /** Alternative Syntax **/
  /* grid-column: 1 / span 2;  */
  /* grid-row: 1 / span 2; */
}

.gallery__item--2 {
  grid-column-start: 3;
  grid-column-end: 5;
  grid-row-start: 1;
  grid-row-end: 3;

  /** Alternative Syntax **/
  /* grid-column: 3 / span 2;  */
  /* grid-row: 1 / span 2; */
}

.gallery__item--3 {
  grid-column-start: 5;
  grid-column-end: 9;
  grid-row-start: 1;
  grid-row-end: 6;

  /** Alternative Syntax **/
  /* grid-column: 5 / span 4;
  grid-row: 1 / span 5; */
}

.gallery__item--4 {
  grid-column-start: 1;
  grid-column-end: 5;
  grid-row-start: 3;
  grid-row-end: 6;

  /** Alternative Syntax **/
  /* grid-column: 1 / span 4;  */
  /* grid-row: 3 / span 3; */
}

.gallery__item--5 {
  grid-column-start: 1;
  grid-column-end: 5;
  grid-row-start: 6;
  grid-row-end: 9;

  /** Alternative Syntax **/
  /* grid-column: 1 / span 4; */
  /* grid-row: 6 / span 3; */
}

.gallery__item--6 {
  grid-column-start: 5;
  grid-column-end: 9;
  grid-row-start: 6;
  grid-row-end: 9;

  /* grid-column: 5 / span 4; */
  /* grid-row: 6 / span 3; */
}
```
آپ خود سے بھی سی ایس ایس ڈال کر اسے جیسا آپ دیکھنا چاہتے ہیں ویسا بنا سکتے ہیں۔ آپ اس سے زیادہ پیچیدہ گیلریاں بھی بہت آسانی سے بنا سکتے ہیں۔ 

آپ نیچے دی گئی لِنک سے سی ایس ایس گرِڈ کے بارے میں مزید جان سکتے ہیں۔

[A Complete Guide to Grid | CSS-Tricks](https://css-tricks.com/snippets/css/complete-guide-grid/)

مجھے امید ہے کہ آپ کو یہ پوسٹ معلومات افزا اور فائدہ مند لگی ہو گی۔ مجھے آپ کی رائے سن کر خوشی ہو گی۔

**پڑھنے کا شکریہ!**
