# Implementation-of-Filters
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
</br>
</br> 

### Step2
</br>
</br> 

### Step3
</br>
</br> 

### Step4
</br>
</br> 

### Step5
</br>
</br> 

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


ii) Using Weighted Averaging Filter


iii) Using Weighted Averaging Filter


iv) Using Median Filter


### 2. Sharpening Filters


i) Using Laplacian Kernal


ii) Using Laplacian Operator


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
