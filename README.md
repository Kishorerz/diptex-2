# Image Capture and Video Processing Using OpenCV
## Name : Kishor kumar B
## Reg No: 212223240072

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

- Write the frame as a JPG file
- Display the video
- Display the video by resizing the window
- Rotate and display the video

---

## 🛠️ Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)

---

## ⚙️ Algorithm

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture frames continuously from the webcam.

### Step 3:
Save a frame as a JPG image using `cv2.imwrite()`.

### Step 4:
Display the live video stream using `cv2.imshow()`.

### Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

---

# Code

```python

import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()

captured_image = cv2.imread('captured_frame.jpg')

plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()


cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```


---

## Output

### i) Write the frame as JPG image

Captured image is saved as **captured_image.jpg**

<img width="496" height="376" alt="image" src="https://github.com/user-attachments/assets/357e1356-6830-46fc-9475-9a769dfdd1a5" />


---

### ii) Display the video

Live webcam video is displayed.

<img width="498" height="369" alt="image" src="https://github.com/user-attachments/assets/b30f77ee-7032-4d5d-a742-cf9eb20aebb0" />

---

### iii) Display the video by resizing the window

Video is displayed in resized resolution (640 × 480).

<img width="251" height="376" alt="image" src="https://github.com/user-attachments/assets/39861b04-ec8a-4b97-a164-835a51d69ac6" />

---

### iv) Rotate and display the video

Video is displayed after rotating the frame (90° clockwise).

<img width="280" height="368" alt="image" src="https://github.com/user-attachments/assets/81275f6d-947a-4c22-bd47-586a5a45e05c" />

---

## Result

Thus, the image was successfully captured from the webcam, and various video processing operations such as saving the captured frame, displaying the live video, resizing the display window, and rotating the video frame were successfully performed using OpenCV.
