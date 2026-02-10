# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1
Import the necessary libraries (cv2, numpy, matplotlib.pyplot) and read the input image using cv2.imread().
</br>
</br> 

### Step 2
Define the kernels for the filters, such as an averaging kernel for smoothing (e.g., a 5x5 matrix of ones divided by 25) and a Laplacian kernel for sharpening.
</br>
</br> 

### Step 3
Apply the smoothing filters to the original image using functions like cv2.filter2D() for the averaging filter, cv2.GaussianBlur() for Gaussian blur, and cv2.medianBlur() for median blur.
</br>
</br> 

### Step 4
Apply the sharpening filter using cv2.filter2D() with the Laplacian kernel, and then add this filtered output to the original image to create the final sharpened image.
</br>
</br> 

### Step 5
Display the original, smoothed, and sharpened images side-by-side using matplotlib.pyplot.imshow() and plt.subplot() for comparison.
</br>
</br> 

## Program
### Developed By   : HARISHBALA J
### Register Number: 212224223002
</br>

### 1. Smoothing Filters

i) Using Averaging Filter
```Python

import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("dipt.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()





```
ii) Using Weighted Averaging Filter
```Python


kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
image3=cv2.filter2D(image2,-1,kernel1)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()



```
iii) Using Gaussian Filter
```Python



gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()

```
iv)Using Median Filter
```Python


median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()


```

### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```Python



kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()

```
ii) Using Laplacian Operator
```Python


laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()


```

## OUTPUT:
## 1. Smoothing Filters

### i) Using Averaging Filter

<img width="901" height="303" alt="image" src="https://github.com/user-attachments/assets/6fe248fe-c731-45e4-805a-f02bdade7c0f" />




### ii)Using Weighted Averaging Filter

<img width="699" height="235" alt="image" src="https://github.com/user-attachments/assets/b7e76d5a-cec1-4fe2-b096-2d861a528bb3" />



### iii)Using Gaussian Blur

<img width="676" height="222" alt="image" src="https://github.com/user-attachments/assets/24bd4f63-4bee-42e8-a89d-00d1bda6293f" />



### iv) Using Median Filter

<img width="896" height="309" alt="image" src="https://github.com/user-attachments/assets/57a7a6ff-9247-4a93-ae95-b89fe5bbd826" />



## 2. Sharpening Filters
### i) Using Laplacian Kernal

<img width="651" height="231" alt="image" src="https://github.com/user-attachments/assets/fe2602bf-0ad6-4bf0-b6d9-455eea2886af" />


### ii) Using Laplacian Operator

<img width="680" height="230" alt="image" src="https://github.com/user-attachments/assets/96deb3b2-ebcc-469d-ae7e-ed282f21d254" />



## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
