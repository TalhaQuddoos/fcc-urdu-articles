# &rlm; CSS کے ساتھ کسی بھی چیز کو درمیان میں لائیں - div, text اور باقی چیزوں کو align کریں۔ 
&rlm; ![alt text](https://www.freecodecamp.org/news/content/images/size/w600/2021/06/5f9c9b00740569d1a4ca291b.jpg)

####  چیزوں کو درمیان میں لانا CSS کے سب سے مشکل پہلوؤں میں سے ایک ہے۔

ان طریقوں کو عام طور پر سمجھنا مشکل نہیں ہوتا، مگر درحقیقت ان چیزوں کو درمیان میں لانے کے بہت سارے طریقے ہیں۔
آپ کا درمیان میں لانے کا طریقہ آپ کے HTML element کے لحاظ سے مختلف ہو سکتا ہے، یا اس لحاظ سے کہ آپ اسے افقی (horizontally) یا عمودی (vertically) طور پر درمیان میں لانا چاہ رہے ہیں۔
اس سبق میں، ہم دیکھیں گے کہ کس طرح مختلف elements کو افقی، عمودی، اور ایک ساتھ دونوں طور پر درمیان میں لایا جا سکتا ہے۔

## افقی طور پر (horizontally) درمیان میں لانا
عام طور پر elements کو افقی طور پر درمیان میں لانا عمودی طور پر درمیان میں لانے سے زیادہ آسان ہوتا ہے۔نیچے چند مشہور elements کو افقی طور پر درمیان میں لانے کے مختلف طریقے ذکر کیے گئے ہیں۔
### &rlm; CSS کی `text-align` پراپرٹی کے ساتھ:
ٹیکسٹ یا لِنکس کو افقی طور پر سینٹر کرنے کے لیے صرف `text-align` پراپرٹی کو `center` ویلیو کے ساتھ استعمال کریں:

```HTML
<div class="container">
    <p>Hello, (centered) World!</p>
</div>
```
```CSS
.container {
  font-family: arial;
  font-size: 24px;
  margin: 25px;
  width: 350px;
  height: 200px;
  outline: dashed 1px black;
}

p {
  /* Center horizontally*/
  text-align: center;
}
```
![alt text](https://www.freecodecamp.org/news/content/images/2020/11/image-15.png)

### &rlm; CSS کی `margin` پراپرٹی کے ساتھ:
&rlm; `div` جیسی block-level elements کو افقی طور پر درمیان میں لانے کے لیے شارٹ ہینڈ پراپرٹی `margin` کو `᱐ auto` کی ویلیو کے ساتھ استعمال کریں۔

```HTML
<div class="container">
  <div class="child"></div>
</div>
```

```CSS
.container {
  font-family: arial;
  font-size: 24px;
  margin: 25px;
  width: 350px;
  height: 200px;
  outline: dashed 1px black;
}

.child {
  width: 50px;
  height: 50px;
  background-color: red;
  /* Center horizontally*/
  margin: 0 auto;
}
```

![alt text](https://www.freecodecamp.org/news/content/images/2020/11/box-centered-horizontally.jpg)

### فلیکس باکس (Flexbox) کے ساتھ ایک div کو افقی طور پر سینٹر کرنے کا طریقہ 

فلیکس باکس (Flexbox) پیج پر چیزوں کو درمیان میں لانے کا سب سے جدید طریقہ ہے اور responsive layouts کو ڈیزائن (design) کرنے کو پہلے سے کہیں زیادہ آسان بنا دیتا ہے۔ تاہم، یہ Internet Explorer جیسے کچھ پرانے browsers میں مکمل طور پر کام نہیں کرتا۔

فلیکس باکس (Flexbox) کے ساتھ کسی element کو افقی طور پر سینٹر کرنے کے لیے اس کے parent element پر `display: flex` اور `justify-content: center` لگا دیں:

```HTML
<div class="container">
  <div class="child"></div>
</div>
```

```CSS
.container {
  font-family: arial;
  font-size: 24px;
  margin: 25px;
  width: 350px;
  height: 200px;
  outline: dashed 1px black;
  /* Center child horizontally*/
  display: flex;
  justify-content: center;
}

.child {
  width: 50px;
  height: 50px;
  background-color: red;
}
```

![alt text](https://www.freecodecamp.org/news/content/images/2020/11/box-centered-horizontally-1.jpg)

## عمودی طور پر (vertically) درمیان میں لانا

فلیکس باکس (Flexbox) جیسے جدید طریقوں کے بغیر عمودی طور پر elements کو سینٹر کرنا ایک مشکل کام ہو سکتا ہے۔ یہاں ہم چیزوں کو vertically درمیان میں لانے کے لیے چند پرانے طریقوں کی طرف جائیں گے اور پھر آپ کو دکھائیں گے کہ اسے Flexbox کے ساتھ کیسے کرنا ہے۔

### &rlm; CSS کی Absolute Positioning اور منفی مارجن کے ذریعے

ایک عرصے تک چیزوں کو vertically درمیان میں لانے کا یہی مقبول طریقہ تھا۔ اس طریقہ کار کے لیے آپ کو اس element کی height کا علم ہونا چاہیے جسے آپ درمیان میں لانا چاہتے ہیں۔

سب سے پہلے، parent element کی `position` property کو `relative` پر سیٹ کریں۔

پھر child element کے لیے، `position` property کو `absolute` اور `top` کو `50%` پر سیٹ کریں:

```HTML
<div class="container">
  <div class="child"></div>
</div>
```

```CSS
.container {
  font-family: arial;
  font-size: 24px;
  margin: 25px;
  width: 350px;
  height: 200px;
  outline: dashed 1px black;
}

.child {
  width: 50px;
  height: 50px;
  background-color: red;
  /* Center horizontally*/
  margin: 0 auto;
}
```

![alt text](https://www.freecodecamp.org/news/content/images/2020/11/box-centered-vertically-1.jpg)

لیکن یہ صرف افقی طور پر child element کے اوپری کنارے (top edge) کو سینٹر کرتا ہے۔

صحیح معنوں میں child element کو سینٹر کرنے کے لیے، `margin-top` property کو `-(half the child element's height)` پر سیٹ کریں:

```CSS
.container {
  font-family: arial;
  font-size: 24px;
  margin: 25px;
  width: 350px;
  height: 200px;
  outline: dashed 1px black;
  /* Setup */
  position: relative;
}

.child {
  width: 50px;
  height: 50px;
  background-color: red;
  /* Center vertically */
  position: absolute;
  top: 50%;
  margin-top: -25px; /* Half this element's height */
}
```

![alt text](https://www.freecodecamp.org/news/content/images/2020/11/box-centered-vertically-final.jpg)

### &rlm; Transform اور Translate کے ذریعے 

اگر آپ اس element کی height کو نہیں جانتے جس کو آپ پیچ میں رکھنا چاہتے ہیں (یا اگر آپ جانتے بھی ہیں)، تو یہ طریقہ بہت عمدہ ہے۔

یہ طریقہ اوپر negative margins کے طریقہ کار سے بہت ملتا جلتا ہے۔ Parent element کی `position` property کو `relative` پر سیٹ کریں۔

اب child element کے لیے، position` property` کو `absolute` پر سیٹ کریں اور `top` کو `50%` پر سیٹ کریں۔ اب child element کو صحیح معنوں میں سینٹر کرنے کے لیے negative margin استعمال کرنے کے بجائے صرف `transform: translate(0, -50%)` کا استعمال کریں۔

```HTML
<div class="container">
  <div class="child"></div>
</div>
```

```CSS
.container {
  font-family: arial;
  font-size: 24px;
  margin: 25px;
  width: 350px;
  height: 200px;
  outline: dashed 1px black;
  /* Setup */
  position: relative;
}

.child {
  width: 50px;
  height: 50px;
  background-color: red;
  /* Center vertically */
  position: absolute;
  top: 50%;
  transform: translate(0, -50%);
}
```

![alt text](https://www.freecodecamp.org/news/content/images/2020/11/box-centered-vertically-final-1.jpg)

نوٹ کریں کہ `translate(0, -50%)` شارٹ ہینڈ (shorthand) ہے `translateX(0)` اور `translateY(-50%)` کے لیے۔ آپ `transform: translateY(-50%)` بھی لکھ سکتے ہیں child element کو عمودی طور پر سینٹر کرنے کے لیے۔

### فلیکس باکس (Flexbox) کے ذریعے

چیزوں کو افقی طور پر سینٹر کرنے کی طرح، Flexbox چیزوں کو عمودی طور پر سینٹر کرنا انتہائی آسان بناتا ہے۔

کسی element کو عمودی طور پر سینٹر کرنے کے لیے، اس کے parent element کے ساتھ `display: flex` اور `align-items: center` لگا دیں:

```HTML
<div class="container">
  <div class="child"></div>
</div>
```

```CSS
.container {
  font-family: arial;
  font-size: 24px;
  margin: 25px;
  width: 350px;
  height: 200px;
  outline: dashed 1px black;
  /* Center vertically */
  display: flex;
  align-items: center;
}

.child {
  width: 50px;
  height: 50px;
  background-color: red;
}
```

![alt text](https://www.freecodecamp.org/news/content/images/2020/11/box-centered-vertically-final-2.jpg)

## عمودی اور افقی طور پر سینٹر کرنا

### &rlm; Absolute Positioning اور منفی مارجن کے ذریعے

یہ کسی element کو عمودی طور پر سینٹر کرنے کے لیے اوپر دیے گئے طریقے سے بہت ملتا جلتا ہے۔ پچھلی بار کی طرح، آپ کو اس element کی width اور height کا علم ہونا چاہیے جسے آپ سینٹر کرنا چاہتے ہیں۔

&rlm; Parent element کی `position` property کو `relative` پر سیٹ کر دیں۔

پھر child کی `position` property کو `absolute`، اور`top` کو `50%`، اور `left` کو `50%` پر سیٹ کریں۔ یہ صرف child element کے top left corner کو عمودی اور افقی طور پر سینٹر کرتا ہے۔

چائلڈ ایلیمنٹ (child element) کو صحیح معنوں میں سینٹر کرنے کے لیے، child element کی نصف height کے برابر اوپر کی طرف سے منفی مارجن سیٹ کر دیں، اور اس کی width کے نصف کے برابر بائیں جانب سے منفی مارجن سیٹ کر دیں:

```HTML
<div class="container">
  <div class="child"></div>
</div>
```

```CSS
.container {
  font-family: arial;
  font-size: 24px;
  margin: 25px;
  width: 350px;
  height: 200px;
  outline: dashed 1px black;
  /* Setup */
  position: relative;
}

.child {
  width: 50px;
  height: 50px;
  background-color: red;
  /* Center vertically and horizontally */
  position: absolute;
  top: 50%;
  left: 50%;
  margin: -25px 0 0 -25px; /* Apply negative top and left margins to truly center the element */ 
}
```

![alt text](https://www.freecodecamp.org/news/content/images/2020/11/box-centered-vertically-and-horizontally.jpg)

### &rlm; Transform اور Translate کےذریعے

کسی element کو عمودی اور افقی طور پر سینٹر کرنے کے لیے اس طریقے کا استعمال کریں اگر آپ کو اس کی width اور height معلوم نہیں ہے اور آپ Flexbox استعمال نہیں کر سکتے ہیں۔

سب سے پہلے، parent element کی `position` property کو `relative` پر سیٹ کریں۔

اس کے بعد، child element کی `position` property کو `absolute`، اور `top` کو `50%`، اور `left` کو `50%` پر سیٹ کریں۔

آخر میں، `transform: translate(-50%, -50%)` کو صحیح معنوں میں child element کو سینٹر کرنے کے لیے استعمال کریں:

```HTML
<div class="container">
  <div class="child"></div>
</div>
```

```CSS
.container {
  font-family: arial;
  font-size: 24px;
  margin: 25px;
  width: 350px;
  height: 200px;
  outline: dashed 1px black;
  /* Setup */
  position: relative;
}

.child {
  width: 50px;
  height: 50px;
  background-color: red;
  /* Center vertically and horizontally */
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```

![alt text](https://www.freecodecamp.org/news/content/images/2020/11/box-centered-vertically-and-horizontally-1.jpg)

### فلیکس باکس (Flexbox) کے ذریعے

ایک element کو عمودی اور افقی طور پر سینٹر کرنے کا سب سے آسان طریقہ Flexbox ہے۔

یہ پچھلے دو Flexbox طریقوں کا صرف ایک مجموعہ ہے۔ Child element کو افقی اور عمودی طور پر سینٹر کرنے کے لیے parent element پر `justify-content: center` اور `align-items: center` لگا دیں:

```HTML
<div class="container">
  <div class="child"></div>
</div>
```

```CSS
.container {
  font-family: arial;
  font-size: 24px;
  margin: 25px;
  width: 350px;
  height: 200px;
  outline: dashed 1px black;
  /* Center vertically and horizontally */
  display: flex;
  justify-content: center;
  align-items: center;
}

.child {
  width: 50px;
  height: 50px;
  background-color: red;
}
```

![alt text](https://www.freecodecamp.org/news/content/images/2020/11/box-centered-vertically-and-horizontally-2.jpg)

یہی وہ سب کچھ ہے جس کے بارے میں آپ کو جاننا لازمی ہے تاکہ آپ بہترین طریقے سے چیزوں کو سینٹر کرسکیں۔ اب جائیں اور ہر چیز کو درمیان میں کر دیں۔
