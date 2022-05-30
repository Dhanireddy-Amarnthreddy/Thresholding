# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Import required packages

### Step2:
Import the image to operate on.

### Step3:
Convert the image to grayscale image.

### Step4:
Apply threshold operators on the image.

### Step5:
Display the output.

## Program
## Developed by:D.Amarnath reddy
## Regester no: 212221240012
```python

import cv2
import matplotlib.pyplot as plt
image = cv2.imread("parrot.jpeg")


# Read the Image and convert to grayscale

grayImage = cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)


# Use Global thresholding to segment the image


ret,thresh = cv2.threshold(grayImage,100,200,cv2.THRESH_BINARY)
ret1,thresh1 = cv2.threshold(grayImage,100,200,cv2.THRESH_BINARY_INV)
ret2, thresh2 = cv2.threshold(grayImage,100,200,cv2.THRESH_TRUNC)
ret3, thresh3 = cv2.threshold(grayImage,100,200,cv2.THRESH_TOZERO)
ret4, thresh4 = cv2.threshold(grayImage,100,200,cv2.THRESH_TOZERO_INV)





# Use Adaptive thresholding to segment the image

th1 = cv2.adaptiveThreshold(grayImage,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
th2 = cv2.adaptiveThreshold(grayImage,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
titles = ["Original Image","Adaptive Mean Thresholding","Adaptive Gaussian Thresholding"]
imgs = [grayImage,th1,th2]




# Use Otsu's method to segment the image 
ret5,th3 = cv2.threshold(grayImage,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)



# Display the results

cv2.imshow("Original Image",image)
cv2.imshow("Gray Image",grayImage)
cv2.imshow("THRESH_BINARY",thresh)
cv2.imshow("THRESH_BINARY_INV",thresh1)
cv2.imshow("THRESH_TRUNC",thresh2)
cv2.imshow("THRESH_TOZERO",thresh3)
cv2.imshow("THRESH_TOZERO_INV",thresh4)

for i in range(3):
    plt.subplot(3,1,i+1)
    plt.imshow(imgs[i],'gray')
    plt.title(titles[i])
    plt.xticks([]),plt.yticks([])
plt.show()


cv2.imshow("Otsu method",th3)


```
## Output

### Original Image
<img width="365" alt="bird 1" src="https://user-images.githubusercontent.com/94165103/171021664-67d92fbd-f6d7-4035-8d5a-142404fe328b.png">

<img width="365" alt="image 2" src="https://user-images.githubusercontent.com/94165103/171022012-a70049d7-d8e0-4c3a-a825-eebceeb316bc.png">

### Global Thresholding

<img width="368" alt="img 3" src="https://user-images.githubusercontent.com/94165103/171022140-28c909fb-1169-4273-9227-827304d2fc32.png">

<img width="362" alt="bird 4" src="https://user-images.githubusercontent.com/94165103/171022270-859af366-804f-45da-9952-3477eac05b37.png">



<img width="363" alt="bird 6" src="https://user-images.githubusercontent.com/94165103/171022494-c5e624d9-435e-418a-bc1f-840c1d8d5095.png">

### Adaptive Thresholding

<img width="272" alt="bird 8" src="https://user-images.githubusercontent.com/94165103/171022598-0be3feb4-e582-48ee-8cf5-7ec0d5325ecd.png">

### Optimum Global Thesholding using Otsu's Method


<img width="374" alt="bird" src="https://user-images.githubusercontent.com/94165103/171023375-bbc43974-f5a4-4dba-928a-9725418c4dfc.png">

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

