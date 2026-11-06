# Experiment 5: Implementation of Filters

### Name: Parani Bala M
### Reg.no: 212224230192

## Aim
To implement different image filtering techniques using Python and OpenCV to smooth images, reduce noise, and detect image features.

## Objectives
- To read and display an input image.
- To implement an Average Filter.
- To implement a Weighted Average Filter.
- To apply Gaussian Blur.
- To apply Median Blur.
- To implement a Laplacian Kernel.
- To apply the Laplacian Operator.
- To compare the original image with the filtered images.

## Software Requirements
- Python 3.x
- Jupyter Notebook
- OpenCV (`cv2`)
- NumPy
- Matplotlib
- Input image: `My_Image.png`

## Algorithm
1. Start the program.
2. Import OpenCV, Matplotlib, and NumPy libraries.
3. Read the input image using `cv2.imread()`.
4. Convert the image from BGR to RGB color format.
5. Create an average filter kernel and apply it using `cv2.filter2D()`.
6. Create a weighted average filter kernel and apply it to the image.
7. Apply Gaussian Blur using `cv2.GaussianBlur()`.
8. Apply Median Blur using `cv2.medianBlur()`.
9. Create a Laplacian kernel and apply it using `cv2.filter2D()`.
10. Apply the Laplacian Operator using `cv2.Laplacian()`.
11. Display the original and filtered images using Matplotlib.
12. Stop the program.

## Program

### 1. Import Libraries and Apply Average Filter

```python
import cv2
import matplotlib.pyplot as plt
import numpy as np

image1=cv2.imread("My_Image.png")
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

### Output:
<img width="1502" height="595" alt="image" src="https://github.com/user-attachments/assets/571573c8-3d91-4459-9c02-0e777f7a8633" />


### 2. Weighted Average Filter

```python
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
image3=cv2.filter2D(image2,-1,kernel1)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```

### Output:
<img width="1508" height="433" alt="image" src="https://github.com/user-attachments/assets/8fc4d3eb-8aa1-4bed-88f5-5e1f4fbfad63" />

### 3. Gaussian Blur

```python
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```

### Output:
<img width="1505" height="432" alt="image" src="https://github.com/user-attachments/assets/2b3864c5-5598-4897-961c-d0ebe85fa8f2" />


### 4. Median Blur

```python
median=cv2.medianBlur(image2,13)

plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```

### Output:
<img width="1505" height="592" alt="image" src="https://github.com/user-attachments/assets/1c2fec67-f61a-4c1e-b55d-333d8d31856d" />

### 5. Laplacian Kernel

```python
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```

### Output:
<img width="1511" height="436" alt="image" src="https://github.com/user-attachments/assets/1a140679-d7b6-4e9b-9454-87bcefe17971" />


### 6. Laplacian Operator

```python
laplacian=cv2.Laplacian(image2,cv2.CV_64F)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

### Output:
<img width="1512" height="468" alt="image" src="https://github.com/user-attachments/assets/13e40f60-335f-4856-8595-259e4c18152b" />


## Result
Different image filtering techniques were implemented successfully using OpenCV. Average, Weighted Average, Gaussian Blur, Median Blur, Laplacian Kernel, and Laplacian Operator were applied to the input image. The original and filtered images were displayed and compared using Matplotlib.
