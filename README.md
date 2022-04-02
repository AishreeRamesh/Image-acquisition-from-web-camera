# Image-Acquisition-from-Web-Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7

## Algorithm
### Step 1:
Import cv2 and capture the video using cv2.VideoCapture(0)

### Step 2:
Write the captured image using cv2.imwrite("NewPicture.jpg",frame)

### Step 3:
Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)

### Step 4:
Display the image until the loop gets over

### Step 5:
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)

## Program:
``` Python
### Developed By: Aishree Ramesh
### Register No: 212220230003

## i) Write the frame as JPG file

import cv2

videoCaptureObject = cv2.VideoCapture(0)

ret,frame = videoCaptureObject.read()
cv2.imwrite("NewPicture.jpg",frame)

videoCaptureObject.release()
cv2.destroyAllWindows()

## ii) Display the video

import cv2
import numpy as np

cap = cv2.VideoCapture(0)


while True:
    ret, frame = cap.read()

    cv2.imshow("NewPicture",frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

videoCaptureObject.release()
cv2.destroyAllWindows()

## iii) Display the video by resizing the window

import cv2
import numpy as np

cap = cv2.VideoCapture(0)


while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)

    cv2.imshow("NewPicture.jpg",smaller_frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

videoCaptureObject.release()
cv2.destroyAllWindows()

## iv) Rotate and display the video
import cv2
import numpy as np

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()

    frame = cv2.rotate(frame,cv2.cv2.ROTATE_180)

    cv2.imshow("NewPicture.jpg",frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

videoCaptureObject.release()
cv2.destroyAllWindows()


```
## Output

### i) Write the frame as JPG image
![image](https://user-images.githubusercontent.com/70213227/161396260-bfeed190-1556-4f1c-b6b5-7e8fad1e4aa9.png)


### ii) Display the video
![image](https://user-images.githubusercontent.com/70213227/161396299-cea5ee59-c701-4dfa-ab87-41b448e83429.png)


### iii) Display the video by resizing the window
![image](https://user-images.githubusercontent.com/70213227/161396345-74f19edb-51c6-4014-b29d-cbf66884b830.png)


### iv) Rotate and display the video
![image](https://user-images.githubusercontent.com/70213227/161396386-b11c71ac-8594-436e-b5bf-6686d2bfc32f.png)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
