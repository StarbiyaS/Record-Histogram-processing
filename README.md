
## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot image.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---

## Program

### Developed By:
**Name: STARBIYA S**  
### Register No: 212223040208

---

## Import Python necessary libraries

```
import cv2
import numpy as np
import matplotlib.pyplot as plt

```
## Histogram Equalization for Grayscale Images
```
img = cv2.imread('parrot image.jpg', cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

```
## Output

<img width="400" height="548" alt="image" src="https://github.com/user-attachments/assets/f933b018-bf54-4211-a0e6-1a9c302fb552" />



```
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
## Output

<img width="780" height="566" alt="image" src="https://github.com/user-attachments/assets/a7a5cae2-2d88-4871-a78c-182256df4754" />


```
img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
```
## Output

<img width="753" height="591" alt="image" src="https://github.com/user-attachments/assets/7a24327b-4b91-4aca-9d57-faf7896f79e8" />


```
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```
## Output

<img width="470" height="570" alt="image" src="https://github.com/user-attachments/assets/03733266-c306-4a06-ae23-94e1217de307" />

## Histogram Equalization for Color Images

```
img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
 plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show() 
```
## Output

<img width="406" height="545" alt="image" src="https://github.com/user-attachments/assets/243065cf-e27d-4895-adaf-014f2ca32341" />


```
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
```
## Output

<img width="792" height="566" alt="image" src="https://github.com/user-attachments/assets/26ea9830-8850-406d-8ead-6d9e7baca539" />

```
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
```
## Output

<img width="1367" height="512" alt="image" src="https://github.com/user-attachments/assets/0cf1188c-ffe2-47b3-a0cb-63aad1b06e7a" />


```
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

## Output

<img width="1377" height="443" alt="image" src="https://github.com/user-attachments/assets/06edeeef-1ab3-49cb-bea8-6178c1e28537" />


### Grayscale Histogram Equalization

- Original grayscale image is displayed  
- Histogram of original grayscale image is plotted  
- Enhanced image after histogram equalization is displayed  
- Histogram of enhanced grayscale image shows improved contrast  

### Color Image Histogram Equalization

- Original color image is displayed  
- Histogram of B, G, R channels is plotted  
- Enhanced image after HSV-based equalization is displayed  
- Histogram of enhanced image shows better intensity distribution 

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
