# Thresholding of Images
## AIM:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## SOFTWARE REQUIRED:
1. Anaconda - Python 3.7
2. OpenCV

## ALGORITHM:

### Step 1:
Load the necessary packages.

### Step 2:
Read the Image and convert to grayscale.

### Step 3:
Use Global thresholding to segment the image.

### Step 4:
Use Adaptive thresholding to segment the image.

### Step 5:
Use Otsu's method to segment the image.

### Step 6:
Display the results.


## PROGRAM:
```python
# Load the necessary packages
import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read the Image and convert to grayscale
image = cv2.imread("rapunzel.png",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("rapunzel.png",0)

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

## OUTPUT:

### Original Image
![output](https://user-images.githubusercontent.com/93427264/170813790-36b6e624-c3d2-495c-b3cd-73b4dc1c9d0d.png)
<br>

### Global Thresholding
![binary_thresh](https://user-images.githubusercontent.com/93427264/170813799-dc2506a2-065e-4ece-bbcc-9de58c2039c4.png)
<br>

![binaryinv_thresh](https://user-images.githubusercontent.com/93427264/170813807-0dea24e2-48c8-4666-a5ec-229d545075e0.png)
<br>

![tozero_thresh](https://user-images.githubusercontent.com/93427264/170813812-668cb37d-3ed6-47b1-8491-93ac7f927a5d.png)
<br>

![tozeroinv_thresh](https://user-images.githubusercontent.com/93427264/170813817-4b68cc51-7f04-406d-8c0e-534575fcd754.png)
<br>

![truncate_thresh](https://user-images.githubusercontent.com/93427264/170813823-a4754866-a5a8-4852-9180-d65fe4a83c48.png)
<br>

### Adaptive Thresholding
![mean_athresh](https://user-images.githubusercontent.com/93427264/170813828-11d37334-ec08-4b2a-80a1-743c1b95f5c1.png)
<br>

![gaussian_athresh](https://user-images.githubusercontent.com/93427264/170813834-c3b08f1a-df80-44aa-bd44-c0a9889d9e69.png)
<br>


### Optimum Global Thesholding using Otsu's Method
![otsu_thresh](https://user-images.githubusercontent.com/93427264/170813837-51c49eed-e370-4d9c-a68e-da4252d7b9c0.png)

<br>



## RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

