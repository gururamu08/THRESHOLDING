# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.
<br>

### Step2:
Read the Image and convert to grayscale.
<br>

### Step3:
Use Global thresholding to segment the image.
<br>

### Step4:
Use Adaptive thresholding to segment the image.
<br>

### Step5:
Use Otsu's method to segment the image.
<br>
### Step 6:
Display the results.
<br>

## Program
```
DEVELOPED BY : GURUMOORTHI R
REG NO : 212222230042
```


# Load the necessary packages
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```





# Read the Image and convert to grayscale
```
image=cv2.imread("dipt.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("dipt.jpg",0)
```




# Use Global thresholding to segment the image
```
ret,thresh_dipt1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_dipt2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_dipt3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_dipt4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_dipt5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```




# Use Adaptive thresholding to segment the image
```
ret,thresh_dipt6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```




# Use Otsu's method to segment the image 
```
thresh_dipt7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_dipt8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```




# Display the results
```
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_dipt1,thresh_dipt2,thresh_dipt3,thresh_dipt4,thresh_dipt5,thresh_dipt6,thresh_dipt7,thresh_dipt8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```




## Output

### Original Image

![1](https://github.com/gururamu08/THRESHOLDING/assets/118707009/8d749e24-6f28-46ac-8e63-fe6ef0da4b94)

<br>

### Global Thresholding

![2 1](https://github.com/gururamu08/THRESHOLDING/assets/118707009/0254bf29-2bf6-4e0a-8357-695908ee5a9a)

![2 2](https://github.com/gururamu08/THRESHOLDING/assets/118707009/cbbf3cee-eab0-474c-b3cc-91059cbce3af)

<br>

### Adaptive Thresholding

![3](https://github.com/gururamu08/THRESHOLDING/assets/118707009/b3394278-54d3-4ec9-8f54-0eacf6984070)

<br>

### Optimum Global Thesholding using Otsu's Method

![4](https://github.com/gururamu08/THRESHOLDING/assets/118707009/8add5af2-3d77-494f-a3de-57db0b1aac33)

<br>


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

