# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.
## Program & Output:
```
DEVELOPED BY: HYCINTH D
REGISTER NO:: 21222324055
```
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('imagee.jpeg')  # Replace with your image path
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
```
![Screenshot 2024-10-05 092303](https://github.com/user-attachments/assets/44acde71-e84b-468d-8afa-f6a1fe4a6c58)
### Input image and grayscale image
```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
```
![Screenshot 2024-10-05 092314](https://github.com/user-attachments/assets/2ddf53f7-d720-45a4-b753-ef9f7c3075fe)
### Canny Edge detector output
```
canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
```
![Screenshot 2024-10-05 092323](https://github.com/user-attachments/assets/a34a3ea7-8e3e-4e9b-b9b1-053cb63f8d70)
### Display the result of Hough transform
```
lines = cv2.HoughLinesP(canny_edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=100, maxLineGap=100)
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')
```
![Screenshot 2024-10-05 092332](https://github.com/user-attachments/assets/a82b82dc-3c75-4dc4-a6c1-70aed26744a5)


### Result:
Thus,The Python program to detect the lines using Hough Transform runs successfully.
