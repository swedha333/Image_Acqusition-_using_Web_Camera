# Image_Acqusition-_using_Web_Camera
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
Use cv2.VideoCapture(0) to access web camera
### Step 2:
Use cv2.imread to read the video or image
### Step 3:
Use cv2.imwrite to save the image
### Step 4:
Use cv2.imshow to show the video
### Step 5:
End the program and close the output video window by pressing 'q'.
## Program:
``` Python
### Developed By:premkumar k
### Register No:212222230111

## i) Write the frame as JPG file
```py
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("PREM.jpg",frame)
    result=False
viedoCaptureObject.release()
cv2.destroyAllWindows()
```

## ii) Display the video
```py
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('Hibiscus',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## iii) Display the video by resizing the window
```py
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
    cv2.imshow('212222230111-premkumar k',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## iv) Rotate and display the video
```py
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
    cv2.imshow('212222230111_prenkumar k',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
![dip exp 2 i](https://github.com/swedha333/Image_Acqusition-_using_Web_Camera/assets/119476243/3ba1d294-3c3d-4d86-bf2d-18722dfb83ef)

### ii) Display the video
![dip exp 2 2](https://github.com/swedha333/Image_Acqusition-_using_Web_Camera/assets/119476243/67b2920c-a88c-406e-a8e4-b6c5fddadc65)

### iii) Display the video by resizing the window
![dip exp 2 3](https://github.com/swedha333/Image_Acqusition-_using_Web_Camera/assets/119476243/7d672d8c-4a66-4a63-90b7-22bcfab9681e)

### iv) Rotate and display the video
![dip exp 2 4](https://github.com/swedha333/Image_Acqusition-_using_Web_Camera/assets/119476243/0539bc2c-f5ee-4fea-8d8b-2414913eb8c0)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
