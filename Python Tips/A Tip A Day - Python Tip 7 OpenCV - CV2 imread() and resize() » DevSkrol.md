---
created: 2024-03-12T19:31:52 (UTC -06:00)
tags: []
source: https://devskrol.com/2021/02/11/atipaday-pythontip7/
author: Asha Ponraj
---

# A Tip A Day - Python Tip #7: OpenCV - CV2: imread() and resize() » DevSkrol

> ## Excerpt
> In this article we are going to learn some of the major use of OpenCV or CV2.

---
In this article we are going to learn some of the major use of OpenCV or CV2.

OpenCV is a library mainly used to read/write and manipulate images.

You can find the official page here [https://pypi.org/project/opencv-python/](https://pypi.org/project/opencv-python/).

_**Installation:**_ pip install opencv-python

_**Importing Library:**_ import cv2

_**Supported Versions:**_ 3.6, 3.7, 3.8, 3.9

## Basic understanding of image:

We all know that an image is nothing but an array of pixels.  
Each pixel is a number.

Based on the number the color of the pixel will be.

Example: 0 – Black and 1 – White.

## Read Image: cv2.imread()

Lets consider we have a small image of 28 X 28 pixels.

```python
import cv2 ##Read image image_path="4.png" img=cv2.imread(image_path,0) #Now we have the image in img variable. #To visualize the image we can use matplotlib.pyplot import matplotlib.pyplot as plt plt.imshow(img, cmap="gray")
```

![](A%20Tip%20A%20Day%20-%20Python%20Tip%207%20OpenCV%20-%20CV2%20imread()%20and%20resize()%20%C2%BB%20DevSkrol/ATipADay4_bwimg.png)

From the above program, you can see that we have a image “4.png”.  
cv2.imread(filename, 0) – Read and returns the image.

0 mentions the color of the image. 0 as second parameter will read the image in gray-scale mode. i.e. the image will only be a 2D array and the 3rd dimension for color will not be added.

Other available Flags are given below:

> cv::IMREAD\_UNCHANGED = -1,  
> cv::IMREAD\_GRAYSCALE = 0,  
> cv::IMREAD\_COLOR = 1,  
> cv::IMREAD\_ANYDEPTH = 2,  
> cv::IMREAD\_ANYCOLOR = 4,  
> cv::IMREAD\_LOAD\_GDAL = 8,  
> cv::IMREAD\_REDUCED\_GRAYSCALE\_2 = 16,  
> cv::IMREAD\_REDUCED\_COLOR\_2 = 17,  
> cv::IMREAD\_REDUCED\_GRAYSCALE\_4 = 32,  
> cv::IMREAD\_REDUCED\_COLOR\_4 = 33,  
> cv::IMREAD\_REDUCED\_GRAYSCALE\_8 = 64,  
> cv::IMREAD\_REDUCED\_COLOR\_8 = 65,  
> cv::IMREAD\_IGNORE\_ORIENTATION = 128

This image can be visualized using matplotlib.pyplot imshow(img). If we do not mention the cmap value, matplotlib will automatically assign a colormap to it.

The shape of this image can be found using the shape attribute as it is an array of pixels(again numbers).

```python
img.shape
```

> (28, 28)

## Resize Image using cv2.resize()

Lets explore the values of the array.

The array shape is 2D 28 X 28. To have a good view of array in notebook result, I have resized the image to 18 X 18.

```python
import numpy as np number_arr = np.asarray(img) img_resized = cv2.resize(img, (18,18)) print(np.asarray(img_resized))
```

![](A%20Tip%20A%20Day%20-%20Python%20Tip%207%20OpenCV%20-%20CV2%20imread()%20and%20resize()%20%C2%BB%20DevSkrol/ATipADayarray.png)

You can see that there is a 4 shape in the array where numbers are > 0.

Interesting! isn’t it? Enjoy!

We will meet with a new tip in Python. Thank you! 👍

Like to support? Just click the heart icon ❤️.

Happy Programming!🎈.
