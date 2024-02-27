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
### Step 1:Use cv2.VideoCapture(0) to access web camera

<br>

### Step 2:Use cv2.imread to read the video or image


<br>

### Step 3:Use cv2.imwrite to save the image

<br>

### Step 4:Use cv2.imshow to show the video


<br>

### Step 5:End the program and close the output video window by pressing 'q'.


<br>

## Program:
``` Python
### Developed By:ARAVIND SAMY.P
### Register No:212222230011
```

## i) Write the frame as JPG file

```

import cv2
videoCaptureObject = cv2.VideoCapture(0)
frame_count = 0
while(True):
    ret, frame = videoCaptureObject.read()
    cv2.imwrite(f"frame_{frame_count}.jpg", frame)
    frame_count += 1
    
    if frame_count >= 100:
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
```

## ii) Display the video
```

import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('OUTPUT',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## iii) Display the video by resizing the window

```
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
    cv2.imshow('ARAVIND',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```


## iv) Rotate and display the video

```

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
    cv2.imshow('ARAVIND',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()





```
## Output

### i) Write the frame as JPG image
![OP01](https://github.com/Aravindsamy04/Image_Acqusition-_using_Web_Camera/assets/113497037/aeef0405-c96b-45bc-86d9-b79adb06940c)


</br>

</br>


### ii) Display the video

![OP01](https://github.com/Aravindsamy04/Image_Acqusition-_using_Web_Camera/assets/113497037/1d095ea7-6395-47e1-9c88-8bac251e7c16)

</br>

</br>


### iii) Display the video by resizing the window


![OP02](https://github.com/Aravindsamy04/Image_Acqusition-_using_Web_Camera/assets/113497037/302989fa-b2ec-46b0-b688-a087e5501c12)

</br>

</br>



### iv) Rotate and display the video

![OP03](https://github.com/Aravindsamy04/Image_Acqusition-_using_Web_Camera/assets/113497037/d75285e5-4bb3-41c3-a408-b7305daf7de0)

</br>
</br>

### Result:
Thus the image is accessed from webcamera and displayed using openCV



## Result:
Thus the image is accessed from webcamera and displayed using openCV.
