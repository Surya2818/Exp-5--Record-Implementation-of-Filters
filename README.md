# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
</br>
Import the necessary libraries (cv2, numpy, matplotlib.pyplot) and read the input image using cv2.imread().

 

### Step 2
Define the kernels for the filters, such as an averaging kernel for smoothing (e.g., a 5x5 matrix of ones divided by 25) and a Laplacian kernel for sharpening.

 

### Step 3
Apply the smoothing filters to the original image using functions like cv2.filter2D() for the averaging filter, cv2.GaussianBlur() for Gaussian blur, and cv2.medianBlur() for median blur.

 

### Step 4
Apply the sharpening filter using cv2.filter2D() with the Laplacian kernel, and then add this filtered output to the original image to create the final sharpened image.

 

### Step 5
Display the original, smoothed, and sharpened images side-by-side using matplotlib.pyplot.imshow() and plt.subplot() for comparison.

 
</br> 



## Program:
### Developed By   : SURYA D
### Register Number: 212224220115
</br>

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("beach.jpg")
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
<img width="683" height="435" alt="image" src="https://github.com/user-attachments/assets/d255d051-7035-483e-a743-07a1906885be" />



ii) Using Weighted Averaging Filter
```Python
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
<img width="293" height="389" alt="image" src="https://github.com/user-attachments/assets/6e647947-4e68-4df0-a480-14bbca968af9" />


iii) Using Gaussian Filter
```Python
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```
<img width="280" height="389" alt="image" src="https://github.com/user-attachments/assets/50e6af65-ced5-47f0-bd74-974a5232e795" />

iv)Using Median Filter
```Python


median = cv2.medianBlur(image2, 13)

plt.imshow(cv2.cvtColor(median, cv2.COLOR_BGR2RGB))
plt.title("Median Blur")
plt.axis("off")
plt.show()
```

<img width="271" height="381" alt="image" src="https://github.com/user-attachments/assets/746e15f1-345b-4f41-99c6-ac3cbf74d43c" />


### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```Python

kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()



```
<img width="267" height="376" alt="image" src="https://github.com/user-attachments/assets/91474cb1-3bc4-48df-a37a-e0dd90edb411" />

ii) Using Laplacian Operator
```Python

laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()



```


<img width="271" height="381" alt="image" src="https://github.com/user-attachments/assets/974bf57a-f5c9-4a34-8d9a-c80ee30d96c7" />





## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
