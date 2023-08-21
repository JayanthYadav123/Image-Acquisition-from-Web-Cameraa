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
Step 1:
Use VideoCapture(0) to access web camera

Step 2:
Use imread to read the video or image

Step 3:
Use imwrite to save the image

Step 4:
Use imshow to show the video

Step 5:
End the program and close the output video windows by pressing 'q'.


## Program:
```
### Developed By:G.Jayanth
### Register No:212221230030
```
## i) Write the frame as JPG file
```
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while (True):
ret,frame = videoCaptureObject.read()
cv2.imwrite("1.jpg",frame)
result = False
videoCaptureObject.release()
cv2.destroyAllWindows()
```


## ii) Display the video
```
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
ret,frame = videoCaptureObject.read()
cv2.imshow('myimage',frame)
if cv2.waitKey(1) == ord('q'):
 break
videoCaptureObject.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```
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
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video

```
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
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```







## Output

### i) Write the frame as JPG image

<img width="960" alt="first" src="https://github.com/JayanthYadav123/Image-Acquisition-from-Web-Cameraa/assets/94836154/e827d1a8-a781-40bf-a790-8a6417b29acf">


### ii) Display the video

<img width="479" alt="Video" src="https://github.com/JayanthYadav123/Image-Acquisition-from-Web-Cameraa/assets/94836154/4c5b175e-9b66-4596-a2c3-7585920f4efd">


### iii) Display the video by resizing the window

<img width="479" alt="4Videos" src="https://github.com/JayanthYadav123/Image-Acquisition-from-Web-Cameraa/assets/94836154/8bde9684-7df8-40dc-83a9-2bb57cd72289">


### iv) Rotate and display the video

<img width="477" alt="Inverted" src="https://github.com/JayanthYadav123/Image-Acquisition-from-Web-Cameraa/assets/94836154/cd7700f3-306f-474b-87da-0778da210aa2">

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
