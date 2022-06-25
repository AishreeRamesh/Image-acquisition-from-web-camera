### EX NO : 02
### DATE  : 08.04.2022
# <p align="center">Image-Acquisition-from-Web-Camera</p>
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

Developed by: Aishree Ramesh
<br>
Register Number: 212220230003

## i) Write the frame as JPG file
```python
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
ret,frame=cap.read()
cv2.imwrite("pic_1.jpg",frame)
cap.release()
cv2.destroyAllWindows()
```

## ii) Display the video

```python
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('frame',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## iii) Display the video by resizing the window

```python
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2,:width//2]=smaller_frame
    image[height//2: , :width//2]=smaller_frame
    image[:height//2,width//2:]= smaller_frame
    image[height//2:,width//2:]=smaller_frame
    cv2.imshow('frame',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## iv) Rotate and display the video
```python
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2,:width//2]=image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[height//2: , :width//2]=smaller_frame
    image[:height//2,width//2:]= image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[height//2:,width//2:]=smaller_frame
    cv2.imshow('frame',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```
## Output

### i) Write the frame as JPG image
![image](https://user-images.githubusercontent.com/70213227/161396260-bfeed190-1556-4f1c-b6b5-7e8fad1e4aa9.png)


### ii) Display the video
![image](https://user-images.githubusercontent.com/70213227/161396299-cea5ee59-c701-4dfa-ab87-41b448e83429.png)


### iii) Display the video by resizing the window
![image](https://user-images.githubusercontent.com/70213227/163848734-0d87d2c7-2020-4abe-8d24-bc35747add5e.png)


### iv) Rotate and display the video
![image](https://user-images.githubusercontent.com/70213227/163848843-55fe54c7-f0c2-488c-bad2-4b250fcc061a.png)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
