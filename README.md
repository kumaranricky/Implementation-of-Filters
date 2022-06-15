# Implementation-of-Filters
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import the necessary modules.
### Step2
For performing smoothing operation on a image use average filter,weighted average filter,gaussian blur,median blur.

### Step3
For performing sharpening on a image use laplacian kernel and laplacian operator.

### Step4
Display all the images with their respective filters.

## Program:
### Developed By   :Kumaran.B
### Register Number:212220230026
```Python
import cv2
import numpy as np
img=cv2.imread("water.jpg")
img=cv2.resize(img,(500,400))
img2=cv2.cvtColor(img,cv2.COLOR_BGR2RGB)
```
### 1. Smoothing Filters
i) Using Averaging Filter
```Python

kernel=np.ones((11,11),np.float32)/121
img3=cv2.filter2D(img2,-1,kernel)
cv2.imshow("Original",img2)
cv2.imshow("Average filter",img3)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
ii) Using Weighted Averaging Filter
```Python
kernel2=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
img4=cv2.filter2D(img2,0,kernel2)
cv2.imshow("Original",img2)
cv2.imshow("Weighted Average filter",img4)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

iii) Using Gaussian Filter
```Python
gf=cv2.GaussianBlur(src=img2,ksize=(11,11),sigmaX=0,sigmaY=0)
cv2.imshow("Original",img2)
cv2.imshow("Gaussian filter",gf)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

iv) Using Median Filter
```Python
median=cv2.medianBlur(src=img2,ksize=11)
cv2.imshow("Original",img2)
cv2.imshow("Median filter",median)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```Python
kernel3=np.array([[0,1,0],[1,-4,1],[0,1,0]])
lk=cv2.filter2D(img2,-1,kernel3)
cv2.imshow("Original",img2)
cv2.imshow("Laplacian Kernel filter",lk)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
ii) Using Laplacian Operator
```Python
lo=cv2.Laplacian(img2,cv2.CV_64F)
cv2.imshow("Original",img2)
cv2.imshow("Laplacian Operator",lo)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

## OUTPUT:
### 1. Smoothing Filters
i) Using Averaging Filter
![Screenshot (301)](https://user-images.githubusercontent.com/75243072/173770624-6bba9b8b-aef5-43f1-b3ec-e4c59c4920a7.png)


ii) Using Weighted Averaging Filter
![Screenshot (302)](https://user-images.githubusercontent.com/75243072/173770705-c689a536-8eb8-4cbf-a3ae-e9522c149a1c.png)


iii) Using Gaussian Filter
![Screenshot (303)](https://user-images.githubusercontent.com/75243072/173770818-25c31261-243c-47f3-aa7b-28d63531cffb.png)


iv) Using Median Filter
![Screenshot (304)](https://user-images.githubusercontent.com/75243072/173770852-f521d984-4933-4db0-8c42-0836b7cfce7f.png)


### 2. Sharpening Filters
i) Using Laplacian Kernal
![Screenshot (305)](https://user-images.githubusercontent.com/75243072/173770903-0a74b938-14dd-4182-a51c-e115afd7bf87.png)


ii) Using Laplacian Operator
![Screenshot (306)](https://user-images.githubusercontent.com/75243072/173771026-21640025-5610-4384-b4c7-301552ec80a9.png)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
