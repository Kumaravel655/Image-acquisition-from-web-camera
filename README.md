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
Use VideoCapture(0) to access web camera

### Step 2:
Use imread to read the video or image

### Step 3:
Use imwrite to save the image
### Step 4:
Use imshow to show the video

### Step 5:
End the program and close the output video windows by pressing 'q'.

## Program:
``` Python
### Developed By: KUMARAVEL V
### Register No: 212220230027

## i) Write the frame as JPG file

import cv2
videoCaptureObject = cv2.VideoCapture(0)
ret,frame = videoCaptureObject.read()
cv2.imwrite("apple.jpg",frame)
videoCaptureObject.release()
cv2.destroyAllWindows()


## ii) Display the video
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret,frame = cap.read()
    cv2.imshow('frame', frame)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()



## iii) Display the video by resizing the window

import cv2
import numpy as np
cap=cv2.VideoCapture(0)

while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()



## iv) Rotate and display the video

import cv2
import numpy as np
cap=cv2.VideoCapture(0)

while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=image[height//2:, width//2:] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()









```
## Output

### i) Write the frame as JPG image

![Screenshot (42)](https://user-images.githubusercontent.com/75235334/162357670-7ba6ff9d-907a-45c8-aa15-c1911682a551.png)

### ii) Display the video

![WhatsApp Image 2022-04-07 at 7 30 09 PM](https://user-images.githubusercontent.com/75235334/162357797-6cfcd245-75a2-4971-ba08-db9752a5dfe3.jpeg)


### iii) Display the video by resizing the window


![WhatsApp Image 2022-04-07 at 7 30 10 PM](https://user-images.githubusercontent.com/75235334/162357907-1ffd6a8c-07e0-4405-90a6-8ad5d66e7eed.jpeg)



### iv) Rotate and display the video

![WhatsApp Image 2022-04-08 at 3 09 35 PM](https://user-images.githubusercontent.com/75235334/162411456-03d53e75-612a-4463-9a21-df8c78efb966.jpeg)





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
