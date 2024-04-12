---
created: 2024-03-12T19:29:51 (UTC -06:00)
tags: []
source: https://devskrol.com/2020/09/01/a-tip-a-day-python-tip-1-loc/
author: Asha Ponraj
---

# A tip A day - Python Tip #1 - loc » DevSkrol

> ## Excerpt
> A tip A day - Various usages of loc for Pandas DataFrame - Retrieve data using labels, boolean arrays & conditions, Get by a list of columns.

---
![](A%20tip%20A%20day%20-%20Python%20Tip%201%20-%20loc%20%C2%BB%20DevSkrol/Tip1-1.png)

Source: DevSkrol

A Tip A Day? Yes! We know that this website mostly speaks about #MachineLearning, #DataScience, #Python & related topics.

Now we are going to start a series of crisp and precise posts related to Python, Pandas, Numpy, Visualization and related tips and topics everyday.

Most of the tips may be familiar to you or it may be useful to beginners in data science. May be it will be useful to brush-up our knowledge in Python.

## Here’s our Tip #1 – Loc:

-   .loc is used to select/retrieve rows or columns from a pandas dataframe.
-   .loc is strictly label based, we cannot use index to look for a column.
-   Arguments – Accepts either labels or boolean arrays.

![](A%20tip%20A%20day%20-%20Python%20Tip%201%20-%20loc%20%C2%BB%20DevSkrol/image-3.png)

In the above data frame we have 4 columns and 5 rows.

## Usage #1: Retrieve data using labels

![](A%20tip%20A%20day%20-%20Python%20Tip%201%20-%20loc%20%C2%BB%20DevSkrol/image-4.png)

The first argument of loc “1:3” mentions to get rows from label having 1 to row with label 3.

The second argument ‘orange’:’grapes’ mentions to get columns from ‘orange’ to ‘grapes’.

Note that, both start and end rage is included in the result.

## Usage #2: Retrieve from a label to the end of the list

If we do not give a range for rows or columns then the remaining all items from the list will be returned.

![](A%20tip%20A%20day%20-%20Python%20Tip%201%20-%20loc%20%C2%BB%20DevSkrol/image-5.png)

In the above code, start range for rows is mentioned but nothing is mentioned for end range. So the rows start from ‘2’ to the end of the dataframe will be returned.

For the columns label, the start range is not mentioned but the end is mentioned. So it will start from the first column and return all columns till ‘apples’.

Note that, both start and end rage is included in the result.

If both start and end are not mentioned then all the rows/columns will be returned.

![](A%20tip%20A%20day%20-%20Python%20Tip%201%20-%20loc%20%C2%BB%20DevSkrol/image-6.png)

Usually we use this to get an entire column with all rows from a dataframe.

## Usage #3: Get a list of columns

A list can be used to mention the columns.

![](A%20tip%20A%20day%20-%20Python%20Tip%201%20-%20loc%20%C2%BB%20DevSkrol/image-7.png)

We know that df.columns has a list of columns. The same can be used too.

![](A%20tip%20A%20day%20-%20Python%20Tip%201%20-%20loc%20%C2%BB%20DevSkrol/image-9.png)

## Usage #4: Using boolean to get values

We can use boolean array either as a direct array or with a condition.

We can use this technique when we need to check the number of rows having numbers > a value or to get a specific value.

![](A%20tip%20A%20day%20-%20Python%20Tip%201%20-%20loc%20%C2%BB%20DevSkrol/image-10.png)

This internally works as a boolean array.

The condition df\[‘apples’\] > 5 will be validated for each data in the rows and come up with the array. Here it is \[False, False, True, False, True\]. And so the row with label 2 and 4 are returned as it is True. i.e. 7 > 5 & 8 > 5.

Today we learned about loc.

Hope you are excited to practice what we have learned now.

We will meet with a new tip in Python. Thank you! 👍

Like to support? Just click the heart icon ❤️.

Happy Programming!🎈
