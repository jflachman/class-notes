---
created: 2024-03-12T19:29:26 (UTC -06:00)
tags: []
source: https://devskrol.com/2020/10/17/a-tip-a-day-python-tip-3-pandas-apply-function/
author: Asha Ponraj
---

# A tip A day – Python Tip #3 - Pandas Apply Function » DevSkrol

> ## Excerpt
> Apply function takes a function as an argument and execute the function in all the elements of the dataframe.

---
> Apply function takes a function as an argument and execute the function in all the elements of the dataframe.

For example, if we want to create a new column which is the square root of another column’s values or apply a complex function and combine one or more columns or when creating new features using the existing features for feature engineering.

> Syntax: df.apply(func, axis=0, broadcast=None, raw=False, reduce=None, result\_type=None, args=(), \*\*kwds)

df – a pandas series.

func – A lambda function or a normal function

axis – 0 – rows which is default, 1 – columns

```
import pandas as pd
import numpy as np

```

Lets try this using an example.

```
fruit = {
    'orange' : [3,2,0,1],
    'apples' : [0,3,7,2]
}
df = pd.DataFrame(fruit)
df
```

Output:

|  | orange | apples |
| --- | --- | --- |
| 0 | 3 | 0 |
| 1 | 2 | 3 |
| 2 | 0 | 7 |
| 3 | 1 | 2 |

For example, we need to create a new series by taking square root of another column. The below code does this.

```
lst= []
print("Original values in Orange column:")
print(df['orange'])
for i in df['orange']:
    lst.append(np.sqrt(i))
    
print("Square root value if Orange column:")
print(lst)
```

Output:

```
Original values in Orange column:
0    3
1    2
2    0
3    1
Name: orange, dtype: int64

Square root value if Orange column:
[1.7320508075688772, 1.4142135623730951, 0.0, 1.0]
```

### Apply function simplifies this.

```
df['orange_sqrt'] = df['orange'].apply(np.sqrt)
df
```

Output:

|  | orange | apples | orange\_sqrt |
| --- | --- | --- | --- |
| 0 | 3 | 0 | 1.732051 |
| 1 | 2 | 3 | 1.414214 |
| 2 | 0 | 7 | 0.000000 |
| 3 | 1 | 2 | 1.000000 |

We have done the same functionality with less code.

### Using Lambda function:

```
df['orange_sq'] = df['orange'].apply(lambda x: x*x)
df
```

Out\[25\]:

|  | orange | apples | orange\_sqrt | orange\_sq |
| --- | --- | --- | --- | --- |
| 0 | 3 | 0 | 1.732051 | 9 |
| 1 | 2 | 3 | 1.414214 | 4 |
| 2 | 0 | 7 | 0.000000 | 0 |
| 3 | 1 | 2 | 1.000000 | 1 |

Today we learned about Apply function.

Hope you are excited to practice what we have learned now.

We will meet with a new tip in Python. Thank you! 👍

Like to support? Just click the heart icon ❤️.

Happy Programming!🎈
