# Thresholding
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

</br>
</br>
</br>

# PROGRAM:
## Developed By: P.Sanjay
## Resiter Number:212220230042

# Load the necessary packages
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

# Read the Image and convert to grayscale
````
image=cv2.imread("army.webp",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("army.webp",0)
````

# Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```

# Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
# Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
# Display the results
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

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>


## OUTPUT:

### Original Image and Grayscale Image

![sa1](https://user-images.githubusercontent.com/75235426/169643174-08c03f49-3da7-4ca0-8f20-7ff7cc563666.jpg)
### Global Thresholding

![sa2](https://user-images.githubusercontent.com/75235426/169643178-fab5b58a-8f57-4a08-a1d6-01fc84db04bd.jpg)

![sa3](https://user-images.githubusercontent.com/75235426/169643181-0f84fbcd-f857-468d-9b37-b8810bf2d9a1.jpg)

![sa4](https://user-images.githubusercontent.com/75235426/169643184-dd81669e-4b53-40c4-a6fd-7efdea202ff7.jpg)

![sa5](https://user-images.githubusercontent.com/75235426/169643189-fbb47879-50e5-4e01-850c-22a29fee5559.jpg)

![sa6](https://user-images.githubusercontent.com/75235426/169643191-4f78969d-5fa5-4b99-a2a2-70b37f6ec39f.jpg)

### Adaptive Thresholding

![sa7](https://user-images.githubusercontent.com/75235426/169643194-fcab799c-c4f9-4996-880c-00da5ea62a0f.jpg)

![sa8](https://user-images.githubusercontent.com/75235426/169643196-d2d2dd5f-7926-461e-8aeb-32c041340020.jpg)

### Optimum Global Thesholding using Otsu's Method

![sa9](https://user-images.githubusercontent.com/75235426/169643228-13ce652a-443c-4105-b273-6a4314f2a57f.jpg)

## RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
