# 8-THRESHOLDING
Name : SANJEV R M

Reg no : 212223040186

## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

Step1:
Load the necessary packages.

Step2:
Read the Image and convert to grayscale.

Step3:
Use Global thresholding to segment the image.

Step4:
Use Adaptive thresholding to segment the image.

Step5:
Use Otsu's method to segment the image and display the results.

## Program

```python
# developed by : SANJEV R M
# Reg no : 212223040186

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale

image = cv2.imread("/content/Screenshot 2025-11-05 191144.png")  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')

# Use Global thresholding to segment the image

_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Use Adaptive thresholding to segment the image

adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

# Use Otsu's method to segment the image 

_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)


# Display the results

# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show the plot
plt.tight_layout()
plt.show()


```
## Output

### Original Image
<img width="487" height="338" alt="image" src="https://github.com/user-attachments/assets/31def280-c8b0-4717-a7fa-43d3c167ed8f" />

### Global Thresholding
<img width="455" height="350" alt="image" src="https://github.com/user-attachments/assets/9e638ac4-aa76-47e9-bb32-45a608293b64" />


### Adaptive Thresholding
<img width="483" height="350" alt="image" src="https://github.com/user-attachments/assets/8d1eade2-cfb1-4a61-9d58-ccfb74a1ddf5" />


### Optimum Global Thesholding using Otsu's Method
<img width="463" height="336" alt="image" src="https://github.com/user-attachments/assets/bb85cb78-1607-4e10-a2e6-5bcf9576f6eb" />



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
