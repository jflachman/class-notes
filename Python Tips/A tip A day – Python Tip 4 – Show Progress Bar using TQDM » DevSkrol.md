---
created: 2024-03-12T19:34:28 (UTC -06:00)
tags: []
source: https://devskrol.com/2020/10/18/a-tip-a-day-python-tip-4-show-progress-bar-using-tqdm/
author: Asha Ponraj
---

# A tip A day – Python Tip #4 – Show Progress Bar using TQDM » DevSkrol

> ## Excerpt
> A tip A day – Python Tip #4 – Show Progress Bar using TQDM » Python Tips » How to use TQDM when executing for loops that take long time

---
Have you ever wished to see a progress bar in Jupyter Notebook when executing a complex function in for loop?

Its possible in Python.

![](A%20tip%20A%20day%20%E2%80%93%20Python%20Tip%204%20%E2%80%93%20Show%20Progress%20Bar%20using%20TQDM%20%C2%BB%20DevSkrol/image-3-1024x409.png)

Photo by [Gaelle Marcel](https://unsplash.com/@gaellemarcel?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/s/photos/progress?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

There is a package tqdm which allows us to show progress bar.  
Also it is simple to use!!!

While implementing a for loop wrap around the iterable object using the function tqdm to show the progress of the for loop execution.

Lets see how to do it.

As we are going to use a simple for loop of 10 numbers using range(), lets use a sleep method to slower the process. So that we can see the use of progress bar.

```
from tqdm import tqdm
from time import sleep
```

```
sum = 0
for i in tqdm(range(10)):
    sum = sum + i
    sleep(0.25)
```

![](A%20tip%20A%20day%20%E2%80%93%20Python%20Tip%204%20%E2%80%93%20Show%20Progress%20Bar%20using%20TQDM%20%C2%BB%20DevSkrol/image-1024x55.png)

Another example with list object:

```
st = ''
for char in tqdm(['a', 'b', 'c', 'd', 'e']):
    sleep(0.25)
    st = st + char
```

![](A%20tip%20A%20day%20%E2%80%93%20Python%20Tip%204%20%E2%80%93%20Show%20Progress%20Bar%20using%20TQDM%20%C2%BB%20DevSkrol/image-1-1024x53.png)

Add a description to the progress bar:

```
st = ''
for char in tqdm(['a', 'b', 'c', 'd', 'e'], desc = 'Concatenating Characters'):
    sleep(0.25)
    st = st + char
```

![](A%20tip%20A%20day%20%E2%80%93%20Python%20Tip%204%20%E2%80%93%20Show%20Progress%20Bar%20using%20TQDM%20%C2%BB%20DevSkrol/image-2-1024x53.png)

Hope you enjoyed the learning.

For more information on using tqdm and to customize the progress bar, please refer their documentation here ([https://tqdm.github.io/](https://tqdm.github.io/), [https://github.com/tqdm/tqdm](https://github.com/tqdm/tqdm)).

We will meet with a new tip in Python. Thank you! 👍

Like to support? Just click the heart icon ❤️.

Happy Programming!🎈
