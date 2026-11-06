# Experiment 3 : Histogram Processing

### Developed By : LOKESH S
### Register Number : 212224240079

### Aim :
To study and implement histogram equalization for grayscale and color images using Python, OpenCV, NumPy, and Matplotlib to improve image contrast.

### Requirements :

* Jupyter Notebook / Anaconda Navigator
* Computer or laptop
* Sufficient storage space for Python libraries and image files
* Input image file: eagle.jpg

### Procedure
1. Import the required Python libraries: OpenCV (cv2), NumPy, and Matplotlib (pyplot).
2. Read the input image (eagle.jpg) in grayscale mode using OpenCV.
3. Display the original grayscale image using Matplotlib.
4. Calculate and plot the histogram of the original grayscale image using plt.hist().
5. Apply histogram equalization to the grayscale image using cv2.equalizeHist().
6. Display the equalized grayscale image and plot its histogram.
7. Read the input image again in color mode.
8. Convert the color image from BGR to HSV color space using cv2.cvtColor().
9. Apply histogram equalization to the Value (brightness) channel of the HSV image.
10. Convert the equalized HSV image back to BGR color space.
11. Display the original and equalized color images for comparison.
12. Plot the original and equalized image histograms to observe the changes in intensity distribution.

### Program : 

### Step1 : Histogram Equalization for Grayscale Images

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('eagle.jpg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```
```python
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
```python
img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
```

```python
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```

### Step2 : Histogram Equalization for Color Images

```python
img = cv2.imread('eagle.jpg', cv2.IMREAD_COLOR)

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])

img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
```
```python
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
```
```python
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
```
```python
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

### Output : 

### Step1 : Histogram Equalization for Grayscale Images

<br><img width="401" height="443" alt="image" src="https://github.com/user-attachments/assets/ab0086bf-df73-40be-9e1d-9d223915906c" />
</br>

<br><img width="643" height="457" alt="image" src="https://github.com/user-attachments/assets/8cb04d20-1523-4c8c-86cd-08593f854501" />
</br>

<br><img width="596" height="443" alt="image" src="https://github.com/user-attachments/assets/e120be59-e973-45d9-9470-df13454cf872" />
</br>

<br><img width="370" height="451" alt="image" src="https://github.com/user-attachments/assets/b6996cfc-dea9-45c2-97b7-0e84b9fd0fb7" />
</br>




### Step2 : Histogram Equalization for Color Images

<br><img width="368" height="437" alt="image" src="https://github.com/user-attachments/assets/92f950bf-b032-40ff-b2c6-293f4dec62df" />
</br>

<br><img width="602" height="431" alt="image" src="https://github.com/user-attachments/assets/e2d5d649-beb7-4d1b-9005-964a1a194a9b" />
</br>

<br><img width="838" height="297" alt="image" src="https://github.com/user-attachments/assets/88d03b7c-3307-4a52-aae7-fc8da5489744" />

</br>

<br><img width="801" height="249" alt="image" src="https://github.com/user-attachments/assets/4650e654-1929-422c-af1d-301caebf59ff" />
</br>

















### Result :

Thus , the Histogram equalization was successfully performed, improving the contrast of grayscale and color images.












            
