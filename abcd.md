# UrMark

### An Urdu-specific Google Docs to Markdown Converter

## What is it?

This is a web app which converts Google Docs to Markdown, making necessary corrections and adjustments for Urdu language.

## How to Use?

1.  In <span dir="ltr">[Google Docs](https://docs.google.com)</span>, open the **File**menu, point the mouse over **Download** and click **Web Page (.html, zipped)**. A **.zip**  file will be downloaded into your computer.

![](https://res.cloudinary.com/talhaquddoos/image/upload/v1645554578/vgdmvfoqgbmbgmcoxftt.png)

2.  Now go to <span dir="ltr">[https://ur-mark.herokuapp.com/](https://ur-mark.herokuapp.com/)</span> and upload the downloaded file by dragging it over the upload area, and click **Convert**.
A markdown file will be downloaded into your computer.

![](https://res.cloudinary.com/talhaquddoos/image/upload/v1645554577/tv1wz6fhhwsdndvadfmt.png)

Here’s how the generated markdown looks:

![](https://res.cloudinary.com/talhaquddoos/image/upload/v1645554579/i946qfqxbqjhehmm4hmn.png)

If your links appear incorrect, you can change them manually :).

## Guidelines for Google Docs:

These are the guidelines you should follow while writing your article in Google Docs, so that the converter can handle them correctly.

### Headings:

To create a heading (`H1` for example), open the **Format**menu, point the mouse over **Paragraph styles** → **Heading 1** and click **Apply ‘Heading 1’** .

![](https://res.cloudinary.com/talhaquddoos/image/upload/v1645554578/q6zja84txlblokwz2wze.png)

### Inline Code:

To put inline code, format it as striked-through text, and the app will wrap it inside `\`` and `\``. I know it’s weird, but Google Docs doesn’t provide the ability to add code blocks by default.

![](https://res.cloudinary.com/talhaquddoos/image/upload/v1645554576/zu9lxg6pvqxeh7y29aum.png)

### Multi-line Code Block:

To add a code block, create a table with a single cell (one row and one column) and put your code inside it. You can also specify the language in  the first line (optional).

![](https://res.cloudinary.com/talhaquddoos/image/upload/v1645554578/pojusvo5m7kkiv1niemm.png)

* * *

![](https://res.cloudinary.com/talhaquddoos/image/upload/v1645554579/x8ctuvwjv3aheje74ohf.png)

### LTR (Left-to-Right) Text in Urdu Line:

When we write English text or code inside an RTL line, for example:

```
فنکشن کو کال کرنے کے لیے function() لکھا جاتا ہے۔

                    
```

The parentheses appear left to the `function` , while they should be on its right. To avoid this problem, format the text as underlined, like this:

![](https://res.cloudinary.com/talhaquddoos/image/upload/v1645554577/aldbma3wiagporlwjg1a.png)
