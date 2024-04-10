# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step1:
Load the necessary packages.
### Step2:
Read the Image and convert to grayscale.
### Step3:
Use Global thresholding to segment the image.
### Step4:
Use Adaptive thresholding to segment the image.
### Step5:
Use Otsu's method to segment the image and display the results.
## Program
### Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```
image = cv2.imread("kong.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("kong.jpg",0)
```
### Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
### Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
### Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
### Display the results
```
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
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
![image](https://github.com/Praveen22042005/THRESHOLDING-/assets/112475766/2ed9df05-9708-4da2-98e0-6e98e5ab4909)


### Global Thresholding
![image](https://github.com/Praveen22042005/THRESHOLDING-/assets/112475766/ba237ab6-227b-4365-a3c1-a319263672ab)
![image](https://github.com/Praveen22042005/THRESHOLDING-/assets/112475766/87c3d91b-413d-4568-99a2-24c0c7bd27bf)
![image](https://github.com/Praveen22042005/THRESHOLDING-/assets/112475766/8795a3e7-5aac-485c-a7c9-991740812f27)
![image](https://github.com/Praveen22042005/THRESHOLDING-/assets/112475766/60b0c983-77a5-4c01-9992-f29b62c89a13)
![image](https://github.com/Praveen22042005/THRESHOLDING-/assets/112475766/7f77cedc-5852-4486-b7b9-5e8580f558b5)




### Adaptive Thresholding
![image](https://github.com/Praveen22042005/THRESHOLDING-/assets/112475766/7a815ac9-8fd1-4d92-8b25-d4cf11334e01)
![image](https://github.com/Praveen22042005/THRESHOLDING-/assets/112475766/bef6de32-5367-4910-a4de-1b79f4fb9838)




### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/Praveen22042005/THRESHOLDING-/assets/112475766/cd164417-cf0f-4535-8ed5-b821f3b87aaa)




## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
