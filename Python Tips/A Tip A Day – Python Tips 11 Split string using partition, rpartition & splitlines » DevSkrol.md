---
created: 2024-03-12T19:32:56 (UTC -06:00)
tags: []
source: https://devskrol.com/2021/10/16/a-tip-a-day-python-tip-11-split-string-using-partition-rpartition-splitlines/
author: Asha Ponraj
---

# A Tip A Day – Python Tips #11: Split string using partition, rpartition & splitlines » DevSkrol

> ## Excerpt
> Apart from the popular split functions split(), rsplit(), there are a few more functions that is very useful in string manipulations.

---
There are various ways to split strings.

The popular split function we use often is split(), rsplit()

Apart from these 3 there are a few more functions that is very useful in string manipulations.

## 1\. Split string using partition() function

The partition function splits the entire string into 3 parts and returns it as a tuple of 3 elements.

1.  The string before the separator
2.  The separator
3.  The string after the separator

This function splits only once and it will not split iteratively. So it splits at the first occurance of the separator.

### Syntax:

#### string.partition(separator)

<table><tbody><tr><td><p>1</p><p>2</p><p>3</p><p>4</p><p>5</p></td><td><div><p><code>fullstring = "partition function is a type of split function in python."</code></p><p><code>result = fullstring.partition("function")</code></p><p><code>print(result)</code></p><p><code>print(type(result))</code></p></div></td></tr></tbody></table>

**Output:**

```
('partition ', 'function', ' is a type of split function in python.')
&lt;class 'tuple'&gt;
```

This function works similar to partition() except that it considers the last occurance of the separator.

<table><tbody><tr><td><p>1</p><p>2</p><p>3</p></td><td><div><p><code>fullstring = "partition function is a type of split function in python."</code></p><p><code>result = fullstring.rpartition("function")</code></p><p><code>print(result)</code></p></div></td></tr></tbody></table>

**Output:**

```
('partition function is a type of split ', 'function', ' in python.')
```

## 3\. splitlines()

This functions splits only by the line breaks.

This will not accept any separator, instead it will accept another optional boolean argument “keepends”.

If keepends is True then it will return the linebreak character along with the left part of the line breaks.

By default keepends is set to False.

<table><tbody><tr><td><p>1</p><p>2</p><p>3</p></td><td><div><p><code>fullstring = "partition function splits a string.\n This splits by separator.\n Returns tuple of 3 elements.\n Lets learn it."</code></p><p><code>result = fullstring.splitlines()</code></p><p><code>print(result)</code></p></div></td></tr></tbody></table>

**Output:**

```
['partition function splits a string.', ' This splits by separator.', ' Returns tuple of 3 elements.', ' Lets learn it.']
```

<table><tbody><tr><td><p>1</p><p>2</p><p>3</p></td><td><div><p><code>result = fullstring.splitlines(keepends=True)</code></p><p><code>print(result)</code></p><p><code>type(result)</code></p></div></td></tr></tbody></table>

**Output:**

```
['partition function splits a string.\n', ' This splits by separator.\n', ' Returns tuple of 3 elements.\n', ' Lets learn it.']
list
```

 I hope you enjoyed learning various types of split functions in python.

Lets explore more about Python in future tips.

### More interesting Python tips:

[A Tip A Day – Python Tip #9: 3 Interesting things about format {}](https://devskrol.com/index.php/2021/09/03/a-tip-a-day-python-tip-9-3-interesting-things-about-format/)

[A Tip A Day – Python Tip #6 – Pandas Merge](https://devskrol.com/index.php/2020/10/25/a-tip-a-day-python-tip-6-pandas-merge/)

[A Tip A Day – Python Tip #5 – Pandas Concat & Append](https://devskrol.com/index.php/2020/10/20/a-tip-a-day-python-tip-5-pandas-concat-append/)

[All Other Tips](https://devskrol.com/index.php/category/python-tips/)

### **Other interesting concepts:**

[SpaCy Vs NLTK – Basic NLP Operations code and result comparison](https://devskrol.com/index.php/2021/04/17/spacy-vs-nltk-basic-nlp-operations-code-and-result-comparison/)

[Best way to Impute NAN within Groups — Mean & Mode](https://devskrol.com/index.php/2020/08/09/best-way-to-impute-nan-within-groups-mean-mode/)
