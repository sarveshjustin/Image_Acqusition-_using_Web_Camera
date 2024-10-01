# Image_Acqusition-_using_Web_Camera
## Aim:
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.

i) Write the frame as JPG 

ii) Display the video 

iii) Display the video by resizing the window

iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import necessary libraries (cv2).
<br>

### Step 2:
Open the camera using cv2.VideoCapture(0).
<br>

### Step 3:
Enter a loop to continuously capture frames from the camera.
<br>

### Step 4:
Resize each frame, create a blank image, divide it into quadrants, and assign resized frames accordingly. Rotate specific frames if needed.
<br>

### Step 5:
Display processed frames on the screen using cv2.imshow(), and continuously check for a termination signal (e.g., pressing 'q' key) to break out of the loop.
<br>

## Program:
```
Name : SARVESH S
reg.no : 212222230135
```
## i) Write the frame as JPG file
```python
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("image.jpg",frame)
    result=False
viedoCaptureObject.release()
cv2.destroyAllWindows()
```
## ii) Display the video
```python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('Video Capture',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('Video Capture',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('Video Capture',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
</br>

<img src ="https://github.com/Adhithyaram29D/Image_Acqusition-_using_Web_Camera/assets/119393540/4f7c834d-7ad8-4cc6-a9a8-62bec1d35d31" width="500">

</br>

### ii) Display the video
</br>

<img src="https://github.com/Adhithyaram29D/Image_Acqusition-_using_Web_Camera/assets/119393540/d88c65d8-de94-47d4-a88d-10d890af6f2c" width="500">

</br>

### iii) Display the video by resizing the window
</br>

<img src="https://github.com/Adhithyaram29D/Image_Acqusition-_using_Web_Camera/assets/119393540/ae8a505b-18d6-4e77-9e63-da7f54a8f749" width="500">
</br>

### iv) Rotate and display the video
<br>
<img src="https://github.com/Adhithyaram29D/Image_Acqusition-_using_Web_Camera/assets/119393540/38c55213-3f90-4162-901d-0a88fdc5fb54" width="500">



## Result:
Thus the image is accessed from webcamera and displayed using openCV.
