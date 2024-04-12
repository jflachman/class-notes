---
created: 2024-03-12T19:32:43 (UTC -06:00)
tags: []
source: https://devskrol.com/2021/09/11/a-tip-a-day-python-tip-10-2-reasons-to-use-python-type-hints/
author: Asha Ponraj
---

# A Tip A Day – Python Tip #10: 2 reasons to use Python Type Hints » DevSkrol

> ## Excerpt
> Type hints for variables and functions, Type hints in functions for parameters and return types. Provide more information to developers.

---
Type hints are used to mention the expected data type of the variable.

Even before Python 3.6, developers provide preferred data type in comments. So that the same variable may not be used with different datatype in further enhancements.

After Python 3.6, Type hints were introduced.

## Why we need to use Type Hints?

## Reason #1: **Type hints can be used mention data type of a variable.**

**Syntax:**

<table><tbody><tr><td><p>1</p></td><td><div><p><code>&lt;variable_name&gt;: &lt;expected data type&gt;</code></p></div></td></tr></tbody></table>

**Example:**

We can also declare a variable using type hint alone without even defining the values.

**Example:**

<table><tbody><tr><td><p>1</p><p>2</p><p>3</p><p>4</p></td><td><div><p><code>total_amount: int</code></p><p><code>sales_1 = 100</code></p><p><code>sales_2 = 200</code></p><p><code>total_amount = sales_1 + sales_2</code></p></div></td></tr></tbody></table>

Type hints will never force the data type of the variable. Type hint is only for user reference.

So that, the usage of the same variable in later versions, which is going to be handled by different developers will get an idea about the expected value of the variable.

This will reduce runtime errors like, “Type Error” when string values are used with “\*” operator for multiplication.

It is just a hint and when an integer hinted variable is assigned with string value, no error will be raised at runtime to enforce the data type.

## Reason #2: Used in functions for Parameters and return types.

Type Hints are also very useful in functions.  
These helps the developers to know the expected data type of the parameters and available data type of the return value.  
For example, in the below example, the parameters must be a number.

<table><tbody><tr><td><p>1</p><p>2</p><p>3</p><p>4</p><p>5</p><p>6</p><p>7</p><p>8</p><p>9</p></td><td><div><p><code># Both the functions expect only numbers and not string values</code></p><p><code>def multiply(a, b):</code></p><p><code>&nbsp;&nbsp;&nbsp;&nbsp;</code><code>return a * b</code></p><p><code>def addition(a, b):</code></p><p><code>&nbsp;&nbsp;&nbsp;&nbsp;</code><code>return a + b</code></p><p><code>print(addition(5,6))</code></p><p><code>print(addition("5","6"))</code></p></div></td></tr></tbody></table>

11  
56

<table><tbody><tr><td><p>1</p><p>2</p></td><td><div><p><code>print(multiply(5,6))</code></p><p><code>print(multiply("5","6"))</code></p></div></td></tr></tbody></table>

```
<span>30
<strong>---------------------------------------------------------------------------</strong>
<strong>TypeError</strong>                                 Traceback (most recent call last)
<strong>&lt;ipython-input-8-051e65134284&gt;</strong> in &lt;module&gt;
      1 print<strong>(</strong>multiply<strong>(5,6))</strong>
<strong>----&gt; 2 </strong>print<strong>(</strong>multiply<strong>("5","6"))</strong>

<strong>&lt;ipython-input-7-9af0c4484b3c&gt;</strong> in multiply<strong>(a, b)</strong>
      1 <strong>def</strong> multiply<strong>(</strong>a<strong>,</strong> b<strong>):</strong>
<strong>----&gt; 2     return</strong> a <strong>*</strong> b

<strong>TypeError</strong>: can't multiply sequence by non-int of type 'str'</span>
```

In the above example, the expected datatype of the parameters are integers.  
But string values were passed.  
Now we will set the type hints for parameters.

<table><tbody><tr><td><p>1</p><p>2</p><p>3</p><p>4</p><p>5</p><p>6</p><p>7</p><p>8</p><p>9</p><p>10</p><p>11</p></td><td><div><p><code>def addition(a: int, b: int) -&gt; int:</code></p><p><code>&nbsp;&nbsp;&nbsp;&nbsp;</code><code>return a + b</code></p><p><code>def multiply(a: int, b: int) -&gt; int:</code></p><p><code>&nbsp;&nbsp;&nbsp;&nbsp;</code><code>return a * b</code></p><p><code>print(addition(5,6))</code></p><p><code>print(addition("5","6"))</code></p><p><code>print(multiply(5,6))</code></p><p><code>print(multiply("5","6"))</code></p></div></td></tr></tbody></table>

```
<span>11
56
30 

<strong>---------------------------------------------------------------------------</strong>
 TypeError                                 Traceback (most recent call last)
  in 
       1 print(multiply(5,6))
 ----&gt; 2 print(multiply("5","6"))
  in multiply(a, b)
       1 def multiply(a: int, b: int):
 ----&gt; 2     return a * b
       3 
       4 def addition(a: int, b: int):
       5     return a + b
 TypeError: can't multiply sequence by non-int of type 'str'</span>
```

As you can see, there is no change in the result.  
Type hints will only help the developer by giving an extra information about the expected type of the variable. Here, it is said to send only the integer values.  
It will not force the compiler to only allow the specified data type.  
Still the Dynamic Typing of Python will work.

 I hope you enjoyed learning Type Hints.

Lets explore more about Python in future tips.

### More interesting Python tips:

[A Tip A Day – Python Tip #9: 3 Interesting things about format {}](https://devskrol.com/index.php/2021/09/03/a-tip-a-day-python-tip-9-3-interesting-things-about-format/)

[A Tip A Day – Python Tip #6 – Pandas Merge](https://devskrol.com/index.php/2020/10/25/a-tip-a-day-python-tip-6-pandas-merge/)

[A Tip A Day – Python Tip #5 – Pandas Concat & Append](https://devskrol.com/index.php/2020/10/20/a-tip-a-day-python-tip-5-pandas-concat-append/)

[All Other Tips](https://devskrol.com/index.php/category/python-tips/)

### **Other interesting concepts:**

[SpaCy Vs NLTK – Basic NLP Operations code and result comparison](https://devskrol.com/index.php/2021/04/17/spacy-vs-nltk-basic-nlp-operations-code-and-result-comparison/)

[Best way to Impute NAN within Groups — Mean & Mode](https://devskrol.com/index.php/2020/08/09/best-way-to-impute-nan-within-groups-mean-mode/)
