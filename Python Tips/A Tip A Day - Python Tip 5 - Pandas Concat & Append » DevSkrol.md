---
created: 2024-03-12T19:29:06 (UTC -06:00)
tags: []
source: https://devskrol.com/2020/10/20/a-tip-a-day-python-tip-5-pandas-concat-append/
author: Asha Ponraj
---

# A Tip A Day - Python Tip #5 - Pandas Concat & Append » DevSkrol

> ## Excerpt
> A Tip A Day - Python Tip #5 - Pandas Concat & Append | Examples

---
In this article we are going to learn about Concat & Append and the comparision between these two functions.

![Concat Vs Append](A%20Tip%20A%20Day%20-%20Python%20Tip%205%20-%20Pandas%20Concat%20&%20Append%20%C2%BB%20DevSkrol/image-17-1024x468.png)

Concat Vs Append – Image by Author

```
import pandas as pd
```

Lets take 2 dataframes of fruits.

```
fruit = {
    'orange' : [3,2,0,1],
    'apple' : [0,3,7,2],
    'grapes' : [7,14,6,15]
}
df1 = pd.DataFrame(fruit)
df1
```

Output:

|  | orange | apple | grapes |
| --- | --- | --- | --- |
| 0 | 3 | 0 | 7 |
| 1 | 2 | 3 | 14 |
| 2 | 0 | 7 | 6 |
| 3 | 1 | 2 | 15 |

```
fruit = {
    'grapes' : [13,12,10,2,55,98],
    'mango' : [10,13,17,2,9,76],
    'banana' : [20,23,27,4,0,9],
    'pear' : [21,24,28,51,22,25],
    'pineapple' : [30,33,38,30,36,31]
}
df2 = pd.DataFrame(fruit)
df2
```

Output:

|  | grapes | mango | banana | pear | pineapple |
| --- | --- | --- | --- | --- | --- |
| 0 | 13 | 10 | 20 | 21 | 30 |
| 1 | 12 | 13 | 23 | 24 | 33 |
| 2 | 10 | 17 | 27 | 28 | 38 |
| 3 | 2 | 2 | 4 | 51 | 30 |
| 4 | 55 | 9 | 0 | 22 | 36 |
| 5 | 98 | 76 | 9 | 25 | 31 |

```
df2 = df2.drop(df2.index[2]) 
df2
```

Output:

|  | grapes | mango | banana | pear | pineapple |
| --- | --- | --- | --- | --- | --- |
| 0 | 13 | 10 | 20 | 21 | 30 |
| 1 | 12 | 13 | 23 | 24 | 33 |
| 3 | 2 | 2 | 4 | 51 | 30 |
| 4 | 55 | 9 | 0 | 22 | 36 |
| 5 | 98 | 76 | 9 | 25 | 31 |

Concat function takes the main argument “objs” as a set of objects.

Another key argument is axis.

If axis = 0 then concatenates the given two dataframes in row wise.

If both the dataframes contains rows with same index then both the rows will be retained without any change or reset in indexes.

```
pd.concat((df1, df2), axis = 0)
```

Output:

|  | orange | apple | grapes | mango | banana | pear | pineapple |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | 3.0 | 0.0 | 7 | NaN | NaN | NaN | NaN |
| 1 | 2.0 | 3.0 | 14 | NaN | NaN | NaN | NaN |
| 2 | 0.0 | 7.0 | 6 | NaN | NaN | NaN | NaN |
| 3 | 1.0 | 2.0 | 15 | NaN | NaN | NaN | NaN |
| 0 | NaN | NaN | 13 | 10.0 | 20.0 | 21.0 | 30.0 |
| 1 | NaN | NaN | 12 | 13.0 | 23.0 | 24.0 | 33.0 |
| 3 | NaN | NaN | 2 | 2.0 | 4.0 | 51.0 | 30.0 |
| 4 | NaN | NaN | 55 | 9.0 | 0.0 | 22.0 | 36.0 |
| 5 | NaN | NaN | 98 | 76.0 | 9.0 | 25.0 | 31.0 |

If axis = 1 then concatenates in column wise. If no data available with same index, then NaN will be filled.

For example, the second dataframe df2 does not contain record with index 2. So, After concatenation, the records of df2 will have NaN for index 2 record as df1 has record with index 2.

If both the dataframes contains same columns then both the columns will be retained without any change in column name.

```
pd.concat((df1, df2), axis = 1)
```

Output:

|  | orange | apple | grapes | grapes | mango | banana | pear | pineapple |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | 3.0 | 0.0 | 7.0 | 13.0 | 10.0 | 20.0 | 21.0 | 30.0 |
| 1 | 2.0 | 3.0 | 14.0 | 12.0 | 13.0 | 23.0 | 24.0 | 33.0 |
| 2 | 0.0 | 7.0 | 6.0 | NaN | NaN | NaN | NaN | NaN |
| 3 | 1.0 | 2.0 | 15.0 | 2.0 | 2.0 | 4.0 | 51.0 | 30.0 |
| 4 | NaN | NaN | NaN | 55.0 | 9.0 | 0.0 | 22.0 | 36.0 |
| 5 | NaN | NaN | NaN | 98.0 | 76.0 | 9.0 | 25.0 | 31.0 |

## Append

Append is the specific case of concat which concats the second dataframe’s records at the end of first dataframe.

Append has no axis argument.

Syntax of Append is different from Concat. Append considers the calling dataframe as main object and adds rows to that dataframe from the dataframes that are passed to the function as argument.

If any of the dataframe contains new columns that is not existing in calling dataframe, then it will be added as new column

> **Syntax:** DataFrame.append(other, ignore\_index=False, verify\_integrity=False, sort=False)

```
df1
```

Output:

|  | orange | apple | grapes |
| --- | --- | --- | --- |
| 0 | 3 | 0 | 7 |
| 1 | 2 | 3 | 14 |
| 2 | 0 | 7 | 6 |
| 3 | 1 | 2 | 15 |

```
df2
```

Output:

|  | grapes | mango | banana | pear | pineapple |
| --- | --- | --- | --- | --- | --- |
| 0 | 13 | 10 | 20 | 21 | 30 |
| 1 | 12 | 13 | 23 | 24 | 33 |
| 3 | 2 | 2 | 4 | 51 | 30 |
| 4 | 55 | 9 | 0 | 22 | 36 |
| 5 | 98 | 76 | 9 | 25 | 31 |

```
df1.append(df2)
```

Output:

|  | orange | apple | grapes | mango | banana | pear | pineapple |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | 3.0 | 0.0 | 7 | NaN | NaN | NaN | NaN |
| 1 | 2.0 | 3.0 | 14 | NaN | NaN | NaN | NaN |
| 2 | 0.0 | 7.0 | 6 | NaN | NaN | NaN | NaN |
| 3 | 1.0 | 2.0 | 15 | NaN | NaN | NaN | NaN |
| 0 | NaN | NaN | 13 | 10.0 | 20.0 | 21.0 | 30.0 |
| 1 | NaN | NaN | 12 | 13.0 | 23.0 | 24.0 | 33.0 |
| 3 | NaN | NaN | 2 | 2.0 | 4.0 | 51.0 | 30.0 |
| 4 | NaN | NaN | 55 | 9.0 | 0.0 | 22.0 | 36.0 |
| 5 | NaN | NaN | 98 | 76.0 | 9.0 | 25.0 | 31.0 |

Result

___

## Performance: Which is faster pandas concat or append?

Well, both are almost equally faster.

However there will be a slight change depending on the data.

1.  Append function will add rows of second data frame to first dataframe iteratively one by one. Concat function will do a single operation to finish the job, which makes it faster than append().

2\. As append will add rows one by one, if the dataframe is significantly very small, then append operation is fine as only a few appends will be done for the number of rows in second dataframe.

<table><tbody><tr><td><p>1</p><p>2</p><p>3</p><p>4</p></td><td><div><p><code>%%time</code></p><p><code>df = pd.DataFrame(columns=['A'])</code></p><p><code>for i in range(30):</code></p><p><code>&nbsp;&nbsp;&nbsp;&nbsp;</code><code>df = df.append({'A': i*2}, ignore_index=True)</code></p></div></td></tr></tbody></table>

Wall time: 51.4 ms

<table><tbody><tr><td><p>1</p><p>2</p></td><td><div><p><code>%%time</code></p><p><code>df = pd.concat([pd.DataFrame([i*2], columns=['A']) for i in range(30)], ignore_index=True)</code></p></div></td></tr></tbody></table>

Wall time: 9.93 ms

3\. Append function will create a new resultant dataframe instead of modifying the existing one. Due to this buffering and creating process, Append operation’s performance is less than concat() function. However Append() is fine if the number of append operation is a very few. If there are a multiple append operations needed, it is better to use concat().

___

We will meet with a new tip in Python. Thank you! 👍

Like to support? Just click the heart icon ❤️.

Happy Programming!🎈.
