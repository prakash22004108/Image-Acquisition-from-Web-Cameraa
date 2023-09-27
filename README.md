# Image-Acquisition-from-Web-Cameraa
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
<br>
Import cv2 and capture the video using cv2.VideoCapture(0).

### Step 2:
<br>
Write the captured image using cv2.imwrite("imagename",frame).

### Step 3:
<br>
Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5).

### Step 4:
<br>
Display the image until the loop gets over.
### Step 5:
<br>
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180).

## Program:
``` Python
### Developed By:Mourise jane
### Register No:212222240074

## i) Write the frame as JPG file
import cv2
video = cv2.VideoCapture(0)
while(True):
    t,frame = video.read()
    cv2.imwrite("212222240077_praveens.jpg",frame)
    result=False
    if cv2.waitKey(1) == ord('b'):
        break
video.release()
cv2.destroyAllWindows()



## ii) Display the video

import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('image',frame)
    if cv2.waitKey(1) == ord('q'):
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
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('image', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()


## iv) Rotate and display the video

import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('image', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
</br>

![dipt](https://github.com/praveenst13/Image-Acquisition-from-Web-Cameraa/assets/118787793/2f0f67fc-1a41-493e-b537-738e12816f15)

</br>


### ii) Display the video
</br>

![dipt1](https://github.com/praveenst13/Image-Acquisition-from-Web-Cameraa/assets/118787793/5902e811-f773-416f-9827-06da859cc601)

</br>


### iii) Display the video by resizing the window
</br>

![dipt2](https://github.com/praveenst13/Image-Acquisition-from-Web-Cameraa/assets/118787793/b45d2f30-0015-4909-9dd8-39a9e121ab05)

</br>



### iv) Rotate and display the video
</br>


![dipt3](https://github.com/praveenst13/Image-Acquisition-from-Web-Cameraa/assets/118787793/c1d61871-f77c-44c5-9c8b-9aa759d55ede)

</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
