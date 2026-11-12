# EX.NO:06 - edge-detection-opencv

## Aim

To perform edge detection using Sobel, Roberts, Prewitt, Laplacian, and Canny edge detectors.

---

## Software Required

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

## ⚙️ Algorithm

### Step 1:
Import all the necessary modules for the program.

### Step 2:
Load an image using `cv2.imread()`.

### Step 3:
Convert the image to grayscale.

### Step 4:
Apply **Sobel operator** using OpenCV to detect edges.

### Step 5:
Apply **Prewitt operator** using custom kernels.

### Step 6:
Apply **Roberts operator** using custom kernels.

### Step 7:
Apply **Laplacian operator** using OpenCV.

### Step 8:
Apply **Canny edge detector** using OpenCV.

### Step 9:
Display all edge-detected images for comparison.

---

## Program & Output:

## Developed By

- **Name:** Rahul Krishna
- **Register No:** 212223040162


```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('me.jpg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
```

<img width="431" height="410" alt="1286cb7f-8571-4d9d-bb71-21ba219f3bd0" src="https://github.com/user-attachments/assets/b18fc1c8-3035-445c-80de-4b7f9b0c33d2" />

```
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')
```

<img width="431" height="410" alt="51dc7de6-70aa-4bf7-ba4a-b9c4379c405d" src="https://github.com/user-attachments/assets/51fd8685-9926-4467-b8e5-57f1ae630d8f" />

```
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')
```

<img width="431" height="410" alt="30ef62f7-a0b4-4630-86c6-5e4f723be9f7" src="https://github.com/user-attachments/assets/98824855-ee48-4b22-8207-13b696ec601e" />


```
canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')  
```

<img width="431" height="410" alt="2e84645d-db5f-4c25-adc2-5bf7d6fda712" src="https://github.com/user-attachments/assets/7f524c95-81f4-49a8-bd09-7140580683cb" />

---


## Result

Thus, edges are successfully detected using Sobel, Prewitt, Roberts, Laplacian, and Canny edge detection techniques. Each method highlights edges differently based on gradient and intensity variations, improving feature extraction and analysis.
