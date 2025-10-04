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
## Output

### Original Image

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("C:\\Users\\admin\\Downloads\\4mmxf65h2ez01.jpeg")  
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Input Image")
plt.axis('off')
```


<img width="868" height="385" alt="image" src="https://github.com/user-attachments/assets/d752dfb8-0feb-4125-935b-04b1df2fab3d" />

### Input image and grayscale image

```

plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')

```

<img width="1020" height="388" alt="image" src="https://github.com/user-attachments/assets/2085b4b4-6832-4aae-884b-e044ef25b4eb" />

### Canny Edge detector output

```

edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')

```

<img width="840" height="380" alt="image" src="https://github.com/user-attachments/assets/5040f959-943a-4b90-bc8f-7122307ce5a8" />

### Display the result of Hough transform

```

lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line[0]  
    cv2.line(image, (x1, y1), (x2, y2), (90, 250, 79), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Result of Hough Transform")
plt.axis('off')

```

<img width="997" height="403" alt="image" src="https://github.com/user-attachments/assets/145972de-639b-46c8-8e1f-7ae20b81b00d" />

## Result

Thus,The Python program to detect the lines using Hough Transform run successfully.


