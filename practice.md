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
