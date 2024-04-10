# EX-08 THRESHOLDING
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
```
DEVELOPED BY: PRAVINRAJJ G.K
REGISTER NO: 212222240080
```
### Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```
image = cv2.imread("LOKI.png",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("dark.jpeg",0)
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
![image](https://github.com/Pravinrajj/THRESHOLDING-/assets/117917674/b7a424d2-7a68-4f41-b98e-1b3fab8ee306)

### Global Thresholding
![image](https://github.com/Pravinrajj/THRESHOLDING-/assets/117917674/4f60ee6d-ac05-4648-9d11-a24876663342)
![image](https://github.com/Pravinrajj/THRESHOLDING-/assets/117917674/7641ff27-b675-4c2c-880d-b313f29e4fa5)
![image](https://github.com/Pravinrajj/THRESHOLDING-/assets/117917674/24ee5d56-cc8e-42df-ab4c-9770910cd851)
![image](https://github.com/Pravinrajj/THRESHOLDING-/assets/117917674/479bf828-8d33-46f8-b9f5-bbb8e8636138)
![image](https://github.com/Pravinrajj/THRESHOLDING-/assets/117917674/00324532-753a-4b9d-b0a9-ad8e373d514c)


### Adaptive Thresholding
![image](https://github.com/Pravinrajj/THRESHOLDING-/assets/117917674/50e96b6c-7731-4670-ab38-e0960d4f60f4)
![image](https://github.com/Pravinrajj/THRESHOLDING-/assets/117917674/ae1bb42b-bc34-4e92-a9f7-ddaeec4a27a6)

### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/Pravinrajj/THRESHOLDING-/assets/117917674/90e54b97-516a-4b0e-bf3a-138f1bac6bdf)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
