# Image-Acquisition-from-Web-Camera
## AIM:

To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## SOFTWARE USED:
Anaconda - Python 3.7
## ALGORITHM:
### Step 1:
Use cv2.VideoCapture(0) to access web camera
<br>

### Step 2:
Use cv2.imread to read the video or image
<br>

### Step 3:
Use cv2.imwrite to save the image
<br>

### Step 4:
Use cv2.imshow to show the video
<br>

### Step 5:
End the program and close the output video window by pressing 'q'.
<br>

## PROGRAM:
``` Python
### Developed By: JAGAN A
### Register No: 212221230037

## i) Write the frame as JPG file
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("jai.jpeg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()



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
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()








```
## OUTPUT:

### i) Write the frame as JPG image
<img width="500" alt="Screenshot 2024-05-09 at 9 40 28 AM" src="https://github.com/saijaganv1618/Image_Acqusition-_using_Web_Camera/assets/59290560/b63d5a13-2e17-4954-b85a-af03cf1e5a74">




</br>
</br>


### ii) Display the video
<img width="502" alt="Screenshot 2024-05-09 at 9 40 36 AM" src="https://github.com/saijaganv1618/Image_Acqusition-_using_Web_Camera/assets/59290560/e794a2ce-6cf5-4b74-bdaf-cbb8c7574f12">



</br>
</br>


### iii) Display the video by resizing the window
<img width="496" alt="Screenshot 2024-05-09 at 9 40 48 AM" src="https://github.com/saijaganv1618/Image_Acqusition-_using_Web_Camera/assets/59290560/c02f4810-ed4d-4e25-9d21-e71c182cfd2f">




</br>
</br>



### iv) Rotate and display the video
<img width="499" alt="Screenshot 2024-05-09 at 9 40 56 AM" src="https://github.com/saijaganv1618/Image_Acqusition-_using_Web_Camera/assets/59290560/583361f0-e817-494b-a905-7a488f4629cf">




</br>
</br>


## RESULT: 
Thus the image is accessed from webcamera and displayed using openCV.
