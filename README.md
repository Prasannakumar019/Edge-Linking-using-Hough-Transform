## EX NO:08
## DATE:18.5.22
# <p align="center">Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale.

### Step4:
Using Canny operator from cv2,detect the edges of the image.

### Step5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.


## Program:
```python
Developed By: Prasannakumar M
Register Number : 212220230035
# Read image and convert it to grayscale image
import cv2
import numpy as np
import matplotlib.pyplot as plt
from cv2 import cvtColor
image=cv2.imread("eye.webp")
cv2.imshow("ORIGINAL",image)
#gray=cv2.cvtColor(image,cv2.COLOR_RGB2GRAY)

plt.figure(1)
plt.subplot(1,2,1)
plt.imshow(image)
plt.title('Original')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(image)
plt.title('gray')
plt.axis('off')


# Find the edges in the image using canny detector and display

edges = cv2.Canny(image, 120, 150)
plt.imshow(edges)
plt.title('EDGES')
plt.axis('off')

# Detect points that form a line using HoughLinesP

lines=cv2.HoughLinesP(edges,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)


# Draw lines on the image

for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(image,(x1,y1),(x2,y2),(0,0,205),2)

# Display the result

plt.imshow(image)
plt.title('HOUGH')
plt.axis('off')



```
## Output

### Input image and grayscale image
![image](https://user-images.githubusercontent.com/75235090/169021842-46ab11bc-0cf3-433d-8156-1b7baad8bb96.png)


### Canny Edge detector output
![image](https://user-images.githubusercontent.com/75235090/169021909-0da9c53c-169b-4861-b54b-5e9b8e0d854d.png)


### Display the result of Hough transform
![image](https://user-images.githubusercontent.com/75235090/169021979-b1d65fb2-3a69-4a60-9945-b173f9de00ca.png)


## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
