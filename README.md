# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the required libraries like OpenCV, NumPy, and Matplotlib.

### Step2:
Read the input image from the file and convert it to grayscale using OpenCV.

### Step3:
Apply different thresholding techniques:
Global thresholding (binary, binary inverse, truncate, to zero, to zero inverse). Otsu’s thresholding. Adaptive thresholding (mean, Gaussian).

### Step4:
Store the results of each thresholding operation in a list for easy visualization.

### Step5:
Display the original grayscale image and the thresholded images side by side using Matplotlib to compare results.


## Program

```python
# Load the necessary packages

import cv2
import numpy as np
import matplotlib.pyplot as plt

```

```python
# Read the Image and convert to grayscale

# Read the image
image = cv2.imread('cat8.jpg')
plt.imshow(image)
plt.title('Original Image')
plt.xticks([]), plt.yticks([])
plt.show()
# Convert to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Display the original grayscale image
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.xticks([]), plt.yticks([])
plt.show()

```

```python
# Use Global thresholding to segment the image

ret_global, th_global = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Display the global thresholding result
plt.imshow(th_global, cmap='gray')
plt.title('Global Thresholding (v=127)')
plt.xticks([]), plt.yticks([])
plt.show()
```

```python
# Use Adaptive thresholding to segment the image

th_adaptive = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
                                    cv2.THRESH_BINARY, 11, 2)

# Display the adaptive thresholding result
plt.imshow(th_adaptive, cmap='gray')
plt.title('Adaptive Gaussian Thresholding')
plt.xticks([]), plt.yticks([])
plt.show()
```

```python
# Use Otsu's method to segment the image 

ret_otsu, th_otsu = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Display the Otsu thresholding result
plt.imshow(th_otsu, cmap='gray')
plt.title("Otsu's Thresholding")
plt.xticks([]), plt.yticks([])
plt.show()
```

## Output

### Original Image

![image](https://github.com/user-attachments/assets/df1b6ef3-c5a3-4fa9-9e09-ceed421dd1b6)

### Grayscale Image

![image](https://github.com/user-attachments/assets/ab077dfd-cb96-4c93-8aa3-d3496147af88)

### Global Thresholding

![image](https://github.com/user-attachments/assets/51223a6b-8b00-42da-b2a4-4b3e4a6554f9)

### Adaptive Thresholding

![image](https://github.com/user-attachments/assets/4a0e84bc-b891-471c-ba66-92047118fcb7)

### Optimum Global Thesholding using Otsu's Method

![image](https://github.com/user-attachments/assets/14b2e32a-2b76-4958-a94a-510d001718c3)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
