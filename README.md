# Thresholding of Images
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
Use Global thresholding to segment the image

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image.

### Step6:
Display the results.


## Program

```python
NAME:YASHASWI MITTA
REG NO: 212221230062

# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2



# Read the Image and convert to grayscale

image = cv2.imread("shinchan.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("shinchan.jpg",0)


# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)


# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)


# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)


# Display the results

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
![dip 9-1](https://user-images.githubusercontent.com/94619247/234524490-a3664631-dc91-4513-943f-27bb2fe4318f.jpg)


### Global Thresholding

![dip 9-2](https://user-images.githubusercontent.com/94619247/234525624-d6a17ea7-8812-4398-a467-26ad34f6e551.jpg)
![dip 9-3](https://user-images.githubusercontent.com/94619247/234525618-b8414928-3f60-4f75-b239-c41ea7053930.jpg)
![dip 9-4](https://user-images.githubusercontent.com/94619247/234525612-506e782b-7457-4bb8-b5b0-703a38db4e67.jpg)
![dip 9-5](https://user-images.githubusercontent.com/94619247/234525609-bcce6ef6-4689-4953-8e93-8680a9688240.jpg)
![dip 9-6](https://user-images.githubusercontent.com/94619247/234525592-93f197bd-1aa6-4192-bf11-b7f21246fa17.jpg)

### Adaptive Thresholding



![dip 9-8](https://user-images.githubusercontent.com/94619247/234524938-e3574d54-a9f1-4c44-8e12-3880f94a4b41.jpg)

![dip 9-9](https://user-images.githubusercontent.com/94619247/234525022-ab70df29-5f47-430e-bded-c4e1fdde0c83.jpg)


### Optimum Global Thesholding using Otsu's Method

![dip 9-7](https://user-images.githubusercontent.com/94619247/234524947-2683a1c3-ce90-4ae9-8bd0-5304558443c2.jpg)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

