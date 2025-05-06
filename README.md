# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step-1:
Create a black image of size 100x600 pixels.
### Step-2:
Use a specified font to write the word "Lifestyle" on the image at a defined position.
### Step-3:
Show the image containing the text without axis labels.
### Step-4:
Define a structuring element for morphological operations (e.g., a cross-shaped kernel).
### Step-5:
Apply erosion to the image using the defined structuring element to reduce the size of white regions.
### Step-6:
Apply dilation to the original image using the same structuring element to increase the size of white regions.
 
## Program:
```
Developed By: MOHAN S
Reg.No: 212223240094
```
``` Python
# Import the necessary packages
import numpy as np
import cv2
import matplotlib.pyplot as plt

def load_img():
    blank_img = np.zeros((600,600), dtype=np.uint8)
    front = cv2.FONT_HERSHEY_SIMPLEX
    cv2.putText(blank_img, text='MOHAN', org=(50, 300), fontFace=front, 
                fontScale=5, color=(255, 255, 255), thickness=25, lineType=cv2.LINE_AA)
    return blank_img

def display_img(img):
    fig=plt.figure(figsize=(12,10))
    ax=fig.add_subplot(111)
    ax.imshow(img,cmap='gray')
    plt.show()

img = load_img()
display_img(img)
```
![Screenshot 2025-05-06 084643](https://github.com/user-attachments/assets/b1f1ad33-80b6-49e0-a19a-47e1709bcd6c)

```
# Create the structuring element
kernal = np.ones((5,5),dtype=np.uint8)
```
```
# Erode the image

IMG = cv2.erode(img,kernal,iterations = 2)
display_img(IMG)

```
### Display the Eroded Image

![Screenshot 2025-05-06 084656](https://github.com/user-attachments/assets/35eb388c-f72e-432a-a851-1e1e4ba6920f)


```
# Dilate the image
dilate = cv2.dilate(img,kernal,iterations = 3)
display_img(dilate)

```
### Display the Dilated Image

![Screenshot 2025-05-06 084706](https://github.com/user-attachments/assets/a80525fe-bb35-4cfd-b038-f2335e477a26)

## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
