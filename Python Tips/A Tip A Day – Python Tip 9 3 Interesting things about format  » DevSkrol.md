---
created: 2024-03-12T19:32:27 (UTC -06:00)
tags: []
source: https://devskrol.com/2021/09/03/a-tip-a-day-python-tip-9-3-interesting-things-about-format/
author: Asha Ponraj
---

# A Tip A Day – Python Tip #9: 3 Interesting things about format  » DevSkrol

> ## Excerpt
> Python Tips: 3 Interesting things about format , using placeholder, Indexing, Naming arguments, Formatting numbers & strings

---
There may be situations, where we may need to dynamically place a value in a sub string of a string.

You may think it is easy that we can concatenate strings.

For example: “The patient name is ” + patient\_name + “ and age is ” + patient\_age

But Python provides a beautiful way where you can even format the patient\_name and patient\_age to align, pad spaces or any special characters, in case of float values, we can also format decimal places.

The string object’s format function will format the given values in specified formats and place them inside the place holders. {} curly brackets are used as place holders.

## 1\. How to use format:

<table><tbody><tr><td><p>1</p><p>2</p></td><td><div><p><code>output = "The patient's name is {}, {}.".format("firstname","lastname")</code></p><p><code>print(output)</code></p></div></td></tr></tbody></table>

The patient’s name is firstname, lastname.

## 2\. Indexed or Named placeholders:

<table><tbody><tr><td><p>1</p><p>2</p><p>3</p><p>4</p><p>5</p></td><td><div><p><code>#Named arguments</code></p><p><code>print("The patient name is {b} and age is {a}".format(a=5,b="test"))</code></p><p><code>#Indexed arguments</code></p><p><code>print("The patient name is {1} and age is {0}".format(5,"test"))</code></p></div></td></tr></tbody></table>

The patient name is test and age is 5  
The patient name is test and age is 5

## 3\. Alignment of string:

The placeholders also accept another argument to align the text or number.

**Syntax:** {index/name : formatting characters}

### For number formatting:

1.  A number to provide the width.
2.  % – Provides the value as percentage

<table><tbody><tr><td><p>1</p></td><td><div><p><code>print("The patient name is {1} and age is {0:%}".format(5.14,"test"))</code></p></div></td></tr></tbody></table>

The patient name is test and age is 514.000000%

### String Formatting:

1.  Any special character to fill the padding space
2.  < – to align left (or) > – to align right (or) ^ – center
3.  Any number for minimum width

<table><tbody><tr><td><p>1</p><p>2</p><p>3</p><p>4</p><p>5</p></td><td><div><p><code>print("The string value {:*^6} is output".format("a"))</code></p><p><code># * - padding, if not mentioned, empty space will be used</code></p><p><code># ^ - center</code></p><p><code># 6 - any number specifies the number of character space to use as minimum width</code></p></div></td></tr></tbody></table>

The string value \*\*a\*\*\* is output

### Float value formatting:

Adding a decimal point and the character “f” specifies the expected value is float.

Even thought the given value is a whole number “.00” will be added if “.2f” is specified.

![](A%20Tip%20A%20Day%20%E2%80%93%20Python%20Tip%209%203%20Interesting%20things%20about%20format%20%20%C2%BB%20DevSkrol/image.png)

<table><tbody><tr><td><p>1</p><p>2</p><p>3</p></td><td><div><p><code>print("The string value {:*^3.2f} is output".format(15.206))</code></p><p><code>print("The string value {:*^3.2f} is output".format(15206))</code></p><p><code>print("The string value {:*^15.2f} is output".format(15206))</code></p></div></td></tr></tbody></table>

The string value 15.21 is output  
The string value 15206.00 is output  
The string value \*\*\*15206.00\*\*\*\* is output

Specifying “f” but sending a string value will throw an error.

<table><tbody><tr><td><p>1</p></td><td><div><p><code>print("The string value {:*^15.2f} is output".format("15206"))</code></p></div></td></tr></tbody></table>

```
<span><strong>---------------------------------------------------------------------------</strong>
<strong>ValueError</strong>                                Traceback (most recent call last)
<strong>&lt;ipython-input-24-09127640ef53&gt;</strong> in &lt;module&gt;
<strong>----&gt; 1 </strong>print<strong>("The string value {:*^15.2f} is output".</strong>format<strong>("15206"))</strong>

<strong>ValueError</strong>: Unknown format code 'f' for object of type 'str'</span>
```

Thats it!

This post is a bit long for tips.

However I hope you enjoying learning formatting.

Lets explore more about Python in future tips.

### More interesting Python tips:

[A Tip A Day – Python Tip #6 – Pandas Merge](https://devskrol.com/index.php/2020/10/25/a-tip-a-day-python-tip-6-pandas-merge/)

[A Tip A Day – Python Tip #5 – Pandas Concat & Append](https://devskrol.com/index.php/2020/10/20/a-tip-a-day-python-tip-5-pandas-concat-append/)

[Best way to Impute NAN within Groups — Mean & Mode](https://devskrol.com/index.php/2020/08/09/best-way-to-impute-nan-within-groups-mean-mode/)

[https://devskrol.com/index.php/category/python-tips/](https://devskrol.com/index.php/category/python-tips/)
