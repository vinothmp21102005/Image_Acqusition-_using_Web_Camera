# Image_Acqusition-_using_Web_Camera
## Aim

To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import OpenCV Package.

### Step 2:
Capture Video from Webcam. Use VideoCapture(0) to access the webcam and start capturing video.
### Step 3:Use cv2.imread to read the video or image
<br>

### Step 4:Use cv2.imshow to show the video
<br>

### Step 5:End the program and close the output video window by pressing 'q'.
<br>

## Program:
``` Python
### Developed By:VINOTH M P
### Register No:212223240182

## i) Write the frame as JPG file

import cv2
videoCaptureObject = cv2.VideoCapture(0)

while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("NewPicture.jpg",frame)
    
    result = False
videoCaptureObject.release()
cv2.DestroyAllWindows()


## ii) Display the video

import cv2
videoCaptureObject = cv2.VideoCapture(0)

while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()





## iii) Display the video by resizing the window


import cv2
import numpy as np
cap  = cv2.VideoCapture(0)
while True:
    ret,frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8)
    small_frame = cv2.resize(frame,(0,0),fx =0.5, fy = 0.5)
    image[:height//2, :width//2]=small_frame
    image[height//2:, :width//2]=small_frame
    image[:height//2, width//2:]=small_frame
    image[height//2:, width//2:]=small_frame
    cv2.imshow('myimage',image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()



## iv) Rotate and display the video



import cv2
import numpy as np
cap  = cv2.VideoCapture(0)
while True:
    ret,frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8)
    small_frame = cv2.resize(frame,(0,0),fx =0.5, fy = 0.5)
    image[:height//2, :width//2]=cv2.rotate(small_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=small_frame
    image[:height//2, width//2:]=small_frame
    image[height//2:, width//2:]=cv2.rotate(small_frame,cv2.ROTATE_180)
    cv2.imshow('myimage',image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()





```
## Output

### i) Write the frame as JPG image



![WhatsApp Image 2024-03-08 at 08 44 18_2fa8e912](https://github.com/VarshaAjith1110/Image_Acqusition-_using_Web_Camera/assets/94222288/e2ab2692-6393-4928-9d0a-5850fd650408)



### ii) Display the video
![WhatsApp Image 2024-03-08 at 08 40 46_fc586d47](https://github.com/VarshaAjith1110/Image_Acqusition-_using_Web_Camera/assets/94222288/d2fe9987-b537-49e2-85bd-ddf7dc93473a)




### iii) Display the video by resizing the window

![WhatsApp Image 2024-03-08 at 08 44 18_5489b7bb](https://github.com/VarshaAjith1110/Image_Acqusition-_using_Web_Camera/assets/94222288/b5c3e782-53b0-47b9-8c0f-afbe63798d61)







### iv) Rotate and display the video

![WhatsApp Image 2024-03-08 at 08 44 18_05942d88](https://github.com/VarshaAjith1110/Image_Acqusition-_using_Web_Camera/assets/94222288/a2e91475-e1df-4c71-8b08-708de719b888)





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
