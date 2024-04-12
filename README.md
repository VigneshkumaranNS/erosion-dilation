# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import the image

### Step2:
Read the colour image and convert it into grayscale

### Step3:
Perform edge detection using canny

### Step4:
Define the kernel size for erosion and dilation

### Step5:
Display all images

## Program:

```python
import cv2
import numpy as np
from matplotlib import pyplot as plt

input_image_path = 'id card 2.jpg'
color_image = cv2.imread(input_image_path)

gray_image = cv2.cvtColor(color_image, cv2.COLOR_BGR2GRAY)

edges = cv2.Canny(gray_image, 180, 200)  

kernel_size = 5
kernel = np.ones((kernel_size, kernel_size), np.uint8)

erosion = cv2.erode(edges, kernel, iterations=1)

dilation = cv2.dilate(edges, kernel, iterations=1)

plt.figure(figsize=(15, 10))

plt.subplot(2, 3, 1)
plt.imshow(cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB))
plt.title('Original Color Image')
plt.axis('on')

plt.subplot(2, 3, 2)
plt.imshow(gray_image, cmap='gray')
plt.title('Black and White Image')
plt.axis('on')

plt.subplot(2, 3, 3)
plt.imshow(edges, cmap="gray")
plt.title('Edge Segmentation')
plt.axis('on')

plt.subplot(2, 3, 4)
plt.imshow(erosion, cmap='gray')
plt.title('Erosion')
plt.axis('on')

plt.subplot(2, 3, 5)
plt.imshow(dilation, cmap='gray')
plt.title('Dilation')
plt.axis('on')

plt.show()

```

## Output:

![DIPT-EX9](https://github.com/VigneshkumaranNS/erosion-dilation/assets/119484483/13494c7d-4020-49f2-a80e-ffc39d459380)


## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
