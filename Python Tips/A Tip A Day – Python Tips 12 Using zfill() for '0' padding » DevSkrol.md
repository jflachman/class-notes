---
created: 2024-03-12T19:33:06 (UTC -06:00)
tags: []
source: https://devskrol.com/2021/10/17/a-tip-a-day-python-tip-12-using-zfill-for-0-padding/
author: Asha Ponraj
---

# A Tip A Day – Python Tips #12: Using zfill() for '0' padding » DevSkrol

> ## Excerpt
> Python Tip tha helps in string manipulation, data processings etc. zfill() function is type of padding function.

---
Lets learn a Python Tip which can help you in string manipulation. It is very useful various data processings.

## zfill() function:

zfill() function is type of padding function.

This function fills only with ‘0’. Takes the resultant width of the string as argument.

This is useful to pad a numeric string values.

<table><tbody><tr><td><p>1</p><p>2</p></td><td><div><p><code>string = "10"</code></p><p><code>string.zfill(10)</code></p></div></td></tr></tbody></table>

Output:

```
'0000000010'
```

## A realtime scenario of usage:

In some of the applications we may have a 5 digit numeric string to represent any ID.

In that case, we can pad with zeros for the desired length of the string and do the increment by 1 (convert to int and increase 1).

<table><tbody><tr><td><p>1</p><p>2</p><p>3</p><p>4</p><p>5</p><p>6</p></td><td><div><p><code>ID = "15"</code></p><p><code>ID = ID.zfill(5)</code></p><p><code>print("Original ID:" + ID)</code></p><p><code>next_ID = str(int(ID)+1).zfill(5)</code></p><p><code>print("Next ID:" + next_ID)</code></p></div></td></tr></tbody></table>

Output:

```
Original ID:00015
Next ID:00016
```

I hope you enjoyed learning various types of split functions in python.

Lets explore more about Python in future tips.

### More interesting Python tips:

[A Tip A Day – Python Tip #9: 3 Interesting things about format {}](https://devskrol.com/index.php/2021/09/03/a-tip-a-day-python-tip-9-3-interesting-things-about-format/)

[A Tip A Day – Python Tip #11: Split string using partition, rpartition & splitlines](https://devskrol.com/index.php/2021/10/16/a-tip-a-day-python-tip-11-split-string-using-partition-rpartition-splitlines/)

[A Tip A Day – Python Tip #10: 2 reasons to use Python Type Hints](https://devskrol.com/index.php/2021/09/11/a-tip-a-day-python-tip-10-2-reasons-to-use-python-type-hints/)

[All Other Tips](https://devskrol.com/index.php/category/python-tips/)

### **Other interesting concepts:**

[SpaCy Vs NLTK – Basic NLP Operations code and result comparison](https://devskrol.com/index.php/2021/04/17/spacy-vs-nltk-basic-nlp-operations-code-and-result-comparison/)

[Best way to Impute NAN within Groups — Mean & Mode](https://devskrol.com/index.php/2020/08/09/best-way-to-impute-nan-within-groups-mean-mode/)
