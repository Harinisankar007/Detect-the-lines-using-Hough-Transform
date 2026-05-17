# Detect-the-lines-using-Hough-Transform

## DEVELOPED BY: HARINI S
## REGISTER NUMBER: 212224240049
## EX No: 7

## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
Step1:Read image and convert it to grayscale image.

Step2:Find the edges in the image using canny detector and display.

Step3:Detect points that form a line using HoughLinesP.

Step4:Draw lines on the image.

Step5:
Display the result.

## Program:

## Read image and convert it to grayscale image
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('Qn_7_.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```
## Find the edges in the image using canny detector and display
```
edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off') 
```
## Detect points that form a line using HoughLinesP
```
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap
for line in lines:
    x1, y1, x2, y2 = line[0]  # Unpacking the line coordinates
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)  # Draw green lines with thickness of 2

```

## Display lines on the image
```
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
```
## OUTPUT 
## Original image 

<img width="580" height="413" alt="image" src="https://github.com/user-attachments/assets/348e4355-f840-4638-a6b5-b9727a6b62c5" />

## Grayscale image

<img width="602" height="425" alt="image" src="https://github.com/user-attachments/assets/89288425-302a-4526-8957-eb3f994313aa" />

## Canny Edge Detector

<img width="606" height="429" alt="image" src="https://github.com/user-attachments/assets/3b3bfb87-7999-4722-a94b-f16b143e4fb7" />

## Result of Hough Transform

<img width="578" height="423" alt="image" src="https://github.com/user-attachments/assets/709af1ce-e849-4cce-8434-0b1498722b15" />

## Result
Thus, the Python program to detect lines using the Hough Transform was implemented successfully. The input image was converted into grayscale, edges were detected using the Canny Edge Detector, and the lines present in the image were identified and displayed using the Probabilistic Hough Transform (HoughLinesP). The detected lines were successfully drawn on the original image.


