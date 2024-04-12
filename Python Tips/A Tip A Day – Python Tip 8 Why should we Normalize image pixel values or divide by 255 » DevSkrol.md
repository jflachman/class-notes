---
created: 2024-03-12T19:31:41 (UTC -06:00)
tags: []
source: https://devskrol.com/2021/02/20/a-tip-a-day-python-tip-8-normalize-image-pixel-values-or-divide-by-255/
author: Asha Ponraj
---

# A Tip A Day – Python Tip #8: Why should we Normalize image pixel values or divide by 255? » DevSkrol

> ## Excerpt
> why divide image by 255? OpenCV Normalize image in Python, Explained with an example

---
In our previous post [A Tip A Day – Python Tip #7: OpenCV – CV2: imread() and resize()](https://devskrol.com/index.php/2021/02/11/atipaday-pythontip7/), we have explored a simple image and its pixel values.

The pixel values can range from 0 to 256. Each number represents a color code.  
When using the image as it is and passing through a Deep Neural Network, the computation of high numeric values may become more complex.  
To reduce this we can normalize the values to range from 0 to 1.

In this way, the numbers will be small and the computation becomes easier and faster.  
As the pixel values range from 0 to 256, apart from 0 the range is 255. So dividing all the values by 255 will convert it to range from 0 to 1.

```
import cv2 
import matplotlib.pyplot as plt

##Read image
image_path="4.png"
img=cv2.imread(image_path,0)

plt.imshow(img, cmap="gray")
```

**Output:**

![](A%20Tip%20A%20Day%20%E2%80%93%20Python%20Tip%208%20Why%20should%20we%20Normalize%20image%20pixel%20values%20or%20divide%20by%20255%20%C2%BB%20DevSkrol/image.png)

lets take a look at one of the white pizel’s value.

```
img[17,14]

Output:
253
```

I gave it a try to visualize the array values using seaborn heatmap and below is the result.

```
import seaborn as sns

plt.figure(figsize=(30,30))
sns.heatmap(img, annot= True, cmap="binary")
```

Output:

![](A%20Tip%20A%20Day%20%E2%80%93%20Python%20Tip%208%20Why%20should%20we%20Normalize%20image%20pixel%20values%20or%20divide%20by%20255%20%C2%BB%20DevSkrol/image-1-941x1024.png)

In the above output the values range from 0 to 256.

## Normalization:

```
import seaborn as sns

img = img/255

plt.figure(figsize=(30,30))
sns.heatmap(img, annot= True, cmap="binary")
```

Output:

![](A%20Tip%20A%20Day%20%E2%80%93%20Python%20Tip%208%20Why%20should%20we%20Normalize%20image%20pixel%20values%20or%20divide%20by%20255%20%C2%BB%20DevSkrol/image-3-958x1024.png)

In this result, you can see that pixels that make the strokes in “4” image are 0.93 or 0.99 or near by values.

Hope you can understand why and how we do normalize simple images.

Lets explore more about images in upcoming posts.

### More interesting Python tips:

[A Tip A Day – Python Tip #6 – Pandas Merge](https://devskrol.com/index.php/2020/10/25/a-tip-a-day-python-tip-6-pandas-merge/)

[A Tip A Day – Python Tip #5 – Pandas Concat & Append](https://devskrol.com/index.php/2020/10/20/a-tip-a-day-python-tip-5-pandas-concat-append/)

[Best way to Impute NAN within Groups — Mean & Mode](https://devskrol.com/index.php/2020/08/09/best-way-to-impute-nan-within-groups-mean-mode/)

[https://devskrol.com/index.php/category/python/](https://devskrol.com/index.php/category/python/)
