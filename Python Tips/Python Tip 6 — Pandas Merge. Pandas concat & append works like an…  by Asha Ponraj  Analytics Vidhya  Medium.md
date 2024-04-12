---
created: 2024-03-12T19:28:20 (UTC -06:00)
tags: []
source: https://medium.com/analytics-vidhya/python-tip-6-pandas-merge-dev-skrol-bf0be41f29b7
author: Asha Ponraj
---

# Python Tip #6 — Pandas Merge. Pandas concat & append works like an… | by Asha Ponraj | Analytics Vidhya | Medium

> ## Excerpt
> But Merge & Join works similar to Database table joins. Lets see Merge in this article and learn about Join in next post! So, Merge can be used when we need to join two data frames having different…

---
[

![Asha Ponraj](Python%20Tip%206%20%E2%80%94%20Pandas%20Merge.%20Pandas%20concat%20&%20append%20works%20like%20an%E2%80%A6%20%20by%20Asha%20Ponraj%20%20Analytics%20Vidhya%20%20Medium/12aod-Nk7hpuRI5G208BNfg.jpeg)



](https://medium.com/@aasha01?source=post_page-----bf0be41f29b7--------------------------------)[

![Analytics Vidhya](Python%20Tip%206%20%E2%80%94%20Pandas%20Merge.%20Pandas%20concat%20&%20append%20works%20like%20an%E2%80%A6%20%20by%20Asha%20Ponraj%20%20Analytics%20Vidhya%20%20Medium/1miCA9MEw8TjpXyR0xY1w-A.png)



](https://medium.com/analytics-vidhya?source=post_page-----bf0be41f29b7--------------------------------)

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

![](Python%20Tip%206%20%E2%80%94%20Pandas%20Merge.%20Pandas%20concat%20&%20append%20works%20like%20an%E2%80%A6%20%20by%20Asha%20Ponraj%20%20Analytics%20Vidhya%20%20Medium/0ZGDgg-0SznYlwiij.png)

```
<span id="421e" data-selectable-paragraph="">import pandas as pd shop = { 'Shop_id' : ['SP01', 'SP02', 'SP03', 'SP04'], 'City' : ['Chennai', 'Madurai', 'Trichy', 'Coimbatore'], 'ZipCode' : [600001, 625001, 620001, 641001] } shop = pd.DataFrame(shop) shop</span><span id="3da3" data-selectable-paragraph="">product = { 'Shop_id' : ['SP01', 'SP02', 'SP02', 'SP03', 'SP03', 'SP03', 'SP05'], 'product_id' : ['p01', 'p02', 'p03', 'p01', 'p02', 'p03', 'p02'], 'price' : [220, 500, 145, 225, 510, 150, 505] } product = pd.DataFrame(product) product</span>
```

## ‘left’ -> Collects all data from left dataframe and common data of left and right.

```
<span id="d5f5" data-selectable-paragraph="">pd.merge(shop, product, how = 'left', on = 'Shop_id')</span>
```

## ‘right’ -> Collects all data from right dataframe and common data of left and right.

```
<span id="1bf0" data-selectable-paragraph="">pd.merge(shop, product, how = 'right', on = 'Shop_id')</span>
```

## ‘inner’ -> Collects only the common data from both the left and right dataframes. This more like an intersection.

```
<span id="afd3" data-selectable-paragraph="">pd.merge(shop, product, how = 'inner', on = 'Shop_id')</span>
```

## ‘outer’ -> Collects all from left and right including common.

```
<span id="59c1" data-selectable-paragraph="">pd.merge(shop, product, how = 'outer', on = 'Shop_id')</span>
```

Excited to try this? Enjoy!

We will meet with a new tip in Python. Thank you! 👍

Like to support? Just click the heart icon ❤️.

Happy Programming!🎈.
