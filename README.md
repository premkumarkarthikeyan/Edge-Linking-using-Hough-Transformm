# Edge-Linking-using-Hough-Transform
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

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.


## Program 

### Developed by : PREM KUMAR K
### Reg.No. 212222230111

### Image Processing

```py
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("abd.jpg",0)
img_c=cv2.imread("abd.jpg",1)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)

```

```py
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
```
```py
plt.figure(figsize=(13,13))
plt.subplot(1,2,1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")
plt.show()
```
### Canny Edge Detection

```py
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
### Hough Transform

```py
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```


## Output

### Input image and grayscale image

![Screenshot 2024-04-02 232535](https://github.com/DINESH18032004/Edge-Linking-using-Hough-Transformm/assets/119477784/65383f47-5459-4bd6-8739-5fa54f49f757)


### Canny Edge detector output


![Screenshot 2024-04-02 232558](https://github.com/DINESH18032004/Edge-Linking-using-Hough-Transformm/assets/119477784/d2c5a770-ac2f-47a5-816f-18ceb5541c72)


### Display the result of Hough transform

![Screenshot 2024-04-02 232608](https://github.com/DINESH18032004/Edge-Linking-using-Hough-Transformm/assets/119477784/52640a46-e48f-4424-a716-2f791555f033)

## Result:

### Thus the program is written with python and OpenCV to detect lines using Hough transform.
