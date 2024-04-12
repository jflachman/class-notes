---
created: 2024-03-12T19:28:55 (UTC -06:00)
tags: []
source: https://devskrol.com/2020/10/25/a-tip-a-day-python-tip-6-pandas-merge/
author: Asha Ponraj
---

# A Tip A Day – Python Tip #6 – Pandas Merge » DevSkrol

> ## Excerpt
> Pandas Merge - Merge & Join works similar to Database table joins. Lets see Merge in this article - When to use Merge - Examples

---
Pandas concat & append works like an array concatenation either column wise or row wise.

But Merge & Join works similar to Database table joins. Lets see Merge in this article and learn about Join in next post!

So, Merge can be used when we need to join two data frames having different columns and there is a key column in both the data frames.

For example, if we have two data frames, one with store details and another with product details of all the stores, we can merge the data frames using shop Id.

**Signature:**  
pd.merge(left,  
right,  
how: str = ‘inner’,  
on=None,  
left\_on=None,  
right\_on=None,  
left\_index: bool = False,  
right\_index: bool = False,  
sort: bool = False,  
suffixes=(‘\_x’, ‘\_y’),  
copy: bool = True,  
indicator: bool = False,  
validate=None,  
)

-   left & right params are data.
-   how -> mentions how the merge should happen. It takes values ‘left’, ‘right’, ‘inner’, ‘outer’. default value is ‘inner’.
    -   ‘left’ -> Collects all data from left dataframe and common data of left and right.
    -   ‘right’ -> Collects all data from right dataframe and common data of left and right.
    -   ‘inner’ -> Collects only the common data from both the left and right dataframes. This more like an intersection.
    -   ‘outer’ -> Collects all from left and right including common.
-   on -> Mentions which column should be taken as key column that exists in both the left and right dataframe.

![Pandas Merge](A%20Tip%20A%20Day%20%E2%80%93%20Python%20Tip%206%20%E2%80%93%20Pandas%20Merge%20%C2%BB%20DevSkrol/mERGE.png)

Pandas Merge – Image by Author

```
import pandas as pd
shop = {
    'Shop_id' : ['SP01', 'SP02', 'SP03', 'SP04'],
    'City' : ['Chennai', 'Madurai', 'Trichy', 'Coimbatore'],
    'ZipCode' : [600001, 625001, 620001, 641001]
}

shop = pd.DataFrame(shop)
shop
```

|  | Shop\_id | City | ZipCode |
| --- | --- | --- | --- |
| 0 | SP01 | Chennai | 600001 |
| 1 | SP02 | Madurai | 625001 |
| 2 | SP03 | Trichy | 620001 |
| 3 | SP04 | Coimbatore | 641001 |

```
product = {
    'Shop_id' : ['SP01', 'SP02', 'SP02', 'SP03', 'SP03', 'SP03', 'SP05'],
    'product_id' : ['p01', 'p02', 'p03', 'p01', 'p02', 'p03', 'p02'],
    'price' : [220, 500, 145, 225, 510, 150, 505]
}

product = pd.DataFrame(product)
product
```

|  | Shop\_id | product\_id | price |
| --- | --- | --- | --- |
| 0 | SP01 | p01 | 220 |
| 1 | SP02 | p02 | 500 |
| 2 | SP02 | p03 | 145 |
| 3 | SP03 | p01 | 225 |
| 4 | SP03 | p02 | 510 |
| 5 | SP03 | p03 | 150 |
| 6 | SP05 | p02 | 505 |

#### ‘left’ -> Collects all data from left dataframe and common data of left and right.

```
pd.merge(shop, product, how = 'left', on = 'Shop_id')
```

|  | Shop\_id | City | ZipCode | product\_id | price |
| --- | --- | --- | --- | --- | --- |
| 0 | SP01 | Chennai | 600001 | p01 | 220.0 |
| 1 | SP02 | Madurai | 625001 | p02 | 500.0 |
| 2 | SP02 | Madurai | 625001 | p03 | 145.0 |
| 3 | SP03 | Trichy | 620001 | p01 | 225.0 |
| 4 | SP03 | Trichy | 620001 | p02 | 510.0 |
| 5 | SP03 | Trichy | 620001 | p03 | 150.0 |
| 6 | SP04 | Coimbatore | 641001 | NaN | NaN |

#### ‘right’ -> Collects all data from right dataframe and common data of left and right.

```
pd.merge(shop, product, how = 'right', on = 'Shop_id')
```

|  | Shop\_id | City | ZipCode | product\_id | price |
| --- | --- | --- | --- | --- | --- |
| 0 | SP01 | Chennai | 600001.0 | p01 | 220 |
| 1 | SP02 | Madurai | 625001.0 | p02 | 500 |
| 2 | SP02 | Madurai | 625001.0 | p03 | 145 |
| 3 | SP03 | Trichy | 620001.0 | p01 | 225 |
| 4 | SP03 | Trichy | 620001.0 | p02 | 510 |
| 5 | SP03 | Trichy | 620001.0 | p03 | 150 |
| 6 | SP05 | NaN | NaN | p02 | 505 |

#### ‘inner’ -> Collects only the common data from both the left and right dataframes. This more like an intersection.

```
pd.merge(shop, product, how = 'inner', on = 'Shop_id') 
```

|  | Shop\_id | City | ZipCode | product\_id | price |
| --- | --- | --- | --- | --- | --- |
| 0 | SP01 | Chennai | 600001 | p01 | 220 |
| 1 | SP02 | Madurai | 625001 | p02 | 500 |
| 2 | SP02 | Madurai | 625001 | p03 | 145 |
| 3 | SP03 | Trichy | 620001 | p01 | 225 |
| 4 | SP03 | Trichy | 620001 | p02 | 510 |
| 5 | SP03 | Trichy | 620001 | p03 | 150 |

#### ‘outer’ -> Collects all from left and right including common.

```
pd.merge(shop, product, how = 'outer', on = 'Shop_id')
```

|  | Shop\_id | City | ZipCode | product\_id | price |
| --- | --- | --- | --- | --- | --- |
| 0 | SP01 | Chennai | 600001.0 | p01 | 220.0 |
| 1 | SP02 | Madurai | 625001.0 | p02 | 500.0 |
| 2 | SP02 | Madurai | 625001.0 | p03 | 145.0 |
| 3 | SP03 | Trichy | 620001.0 | p01 | 225.0 |
| 4 | SP03 | Trichy | 620001.0 | p02 | 510.0 |
| 5 | SP03 | Trichy | 620001.0 | p03 | 150.0 |
| 6 | SP04 | Coimbatore | 641001.0 | NaN | NaN |
| 7 | SP05 | NaN | NaN | p02 | 505.0 |

Excited to try this? Enjoy!

We will meet with a new tip in Python. Thank you! 👍

Like to support? Just click the heart icon ❤️.

Happy Programming!🎈.
