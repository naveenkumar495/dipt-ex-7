# EXP NO : 07-Edge-Linking-using-Hough-Transformm
# Name : Naveenkumar M
# Reg NO: 212224230183
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

## program:
~~~python
import cv2
import numpy as np
import matplotlib.pyplot as plt
mage = cv2.imread('naveen.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line[0]  # Unpacking the line coordinates
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2) 
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')





~~~

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.
## Output

### Input image and grayscale image
<img width="754" height="553" alt="image" src="https://github.com/user-attachments/assets/31ced14e-dc5b-4a9b-af43-b33fcb91e167" />
<img width="793" height="546" alt="image" src="https://github.com/user-attachments/assets/0a8f5d4f-d6da-4b56-b317-76f0ed352b3d" />


### Canny Edge detector output
<img width="716" height="557" alt="image" src="https://github.com/user-attachments/assets/3020d1b0-527b-4c8e-942f-520c333ca78a" />


### Display the result of Hough transform
<img width="798" height="541" alt="image" src="https://github.com/user-attachments/assets/5a2fb464-eb1a-40d1-addf-275ddbf77d67" />

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
