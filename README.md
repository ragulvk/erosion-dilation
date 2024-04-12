# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import necessary packages

### Step2:
Create an empty window and add text to it

### Step3:
create a structuring element

### Step4:
Do the operation

### Step5:
Print the output images

 
## Program:

``` Python
import cv2
import numpy as np
from matplotlib import pyplot as plt

#to read the color image
input_image_path='shiba.jpg'
color_image=cv2.imread(input_image_path)

#convert the color image to grayscale
gray_image=cv2.cvtColor(color_image,cv2.COLOR_BGR2GRAY)

#perform edge detection using Canny
edges=cv2.Canny(gray_image,100,200)

#define the kernel size for erosion and dilation
kernel_size=5
kernel=np.ones((kernel_size,kernel_size),np.uint8)

#perform erosion
erosion=cv2.erode(edges,kernel,iterations=1)

#perform dilation
dilation=cv2.dilate(edges,kernel,iterations=1)

#display all images
plt.figure(figsize=(15,10))

plt.subplot(2,3,1)
plt.imshow(cv2.cvtColor(color_image,cv2.COLOR_BGR2RGB))
plt.title('Original Color Image')
plt.axis('on')

plt.subplot(2,3,2)
plt.imshow(gray_image,cmap='gray')
plt.title('Black and White Image')
plt.axis('on')

plt.subplot(2,3,3)
plt.imshow(edges,cmap='gray')
plt.title('Edge Segmentation')
plt.axis('on')

plt.subplot(2,3,4)
plt.imshow(erosion,cmap='gray')
plt.title('Erosion')
plt.axis('on')

plt.subplot(2,3,5)
plt.imshow(dilation,cmap='gray')
plt.title('Dilation')
plt.axis('on')

plt.show()

```
## Output:

### Display the input Image
![image](https://github.com/EASWAR17/erosion-dilation/assets/94154683/3cb53a3d-4bb2-405e-b39e-aeb9132e6fa6)


### Display the Eroded Image
![image](https://github.com/EASWAR17/erosion-dilation/assets/94154683/8c92ac0e-376a-48f6-97da-50de6066e736)


### Display the Dilated Image
![image](https://github.com/EASWAR17/erosion-dilation/assets/94154683/ec501222-15a6-44d2-bb9f-ff7f8ac0087e)

### Final Output
![image](https://github.com/EASWAR17/erosion-dilation/assets/94154683/10969f5a-4057-44ad-9a52-04d2bd3465e1)


## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
