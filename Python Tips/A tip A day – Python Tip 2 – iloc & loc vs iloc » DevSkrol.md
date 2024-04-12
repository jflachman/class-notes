---
created: 2024-03-12T19:29:39 (UTC -06:00)
tags: []
source: https://devskrol.com/2020/09/02/a-tip-a-day-python-tip-2-iloc-loc-vs-iloc/
author: Asha Ponraj
---

# A tip A day – Python Tip #2 – iloc & loc vs iloc » DevSkrol

> ## Excerpt
> we are going to learn how to use iloc to get values from Pandas DataFrame and we are going to compare iloc with loc. To learn about loc, check Tip #1 – loc.

---
![](A%20tip%20A%20day%20%E2%80%93%20Python%20Tip%202%20%E2%80%93%20iloc%20&%20loc%20vs%20iloc%20%C2%BB%20DevSkrol/image-14.png)

Today we are going to learn how to use iloc to get values from Pandas DataFrame and we are going to compare iloc with loc.

To learn about loc, please check [A tip A day – Python Tip #1 – loc](https://devskrol.com/index.php/2020/09/01/a-tip-a-day-python-tip-1-loc/).

## Using iloc:

-   iLoc uses only numbers/indexes (strictly numerical values) to get values from a Pandas DataFrame.
-   Apart from numerical values, it accepts boolean arrays similar to Loc

![](A%20tip%20A%20day%20%E2%80%93%20Python%20Tip%202%20%E2%80%93%20iloc%20&%20loc%20vs%20iloc%20%C2%BB%20DevSkrol/image-11.png)

Consider the above dataframe. It has Named index.

If a slice object is given as argument in iloc, then it returns data from starting index upto ending index, **_but excluding the ending index._**

**_Also the indexes will start from 0 (Not 1)._**

![](A%20tip%20A%20day%20%E2%80%93%20Python%20Tip%202%20%E2%80%93%20iloc%20&%20loc%20vs%20iloc%20%C2%BB%20DevSkrol/image-12.png)

See that the slice object “0:2” points the indexes from June (Index = 0) till July (Index = 1), but the third row August (Index = 2) was not returned.

Similarly, the index of the second column ‘apples’ is 1 and third columns ‘grapes’ (Index = 2) is returned but ‘pear’ is not returned.

![](A%20tip%20A%20day%20%E2%80%93%20Python%20Tip%202%20%E2%80%93%20iloc%20&%20loc%20vs%20iloc%20%C2%BB%20DevSkrol/image-13.png)

As mentioned above, iloc can accept boolean list / condition statements too.

| ****Loc**** | **iLoc** |
| --- | --- |
| Strictly **label** based | Strictly **index** based |
| Accepts Boolean Array/ Conditions | Accepts Boolean Array/ Conditions |
| **Includes** both the ranges in slice object. Example: ‘a’:’b | **Excludes** the end range in slice object as it uses index.  
Example: 0:3 returns 0,1,2 not 3 |

Today we learned about iloc.

We will meet with a new tip in Python. Thank you! 👍

Like to support? Just click the heart icon ❤️.

Happy Programming!🎈

[

Previous Post A tip A day – Python Tip #1 – loc

](https://devskrol.com/2020/09/01/a-tip-a-day-python-tip-1-loc/)[

Next Post Optimizers in Neural Network

![Optimizers](A%20tip%20A%20day%20%E2%80%93%20Python%20Tip%202%20%E2%80%93%20iloc%20&%20loc%20vs%20iloc%20%C2%BB%20DevSkrol/Optimizers-300x232.jpg)

](https://devskrol.com/2020/09/05/optimizer-in-neural-network/)
