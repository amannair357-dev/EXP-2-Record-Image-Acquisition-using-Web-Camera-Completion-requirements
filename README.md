# EXP-2-Record-Image-Acquisition-using-Web-Camera-Completion-requirements

## Image Capture and Video Processing Using OpenCV

---

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file  
2. Display the video  
3. Display the video by resizing the window  
4. Rotate and display the video  

---

## 🛠️ Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  

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

## 💻 Program

### Developed By:
**Name:** Aman Nair

### Register No:
212225240008

---

~~~python
import cv2

# Step 1: Initialize the webcam
cap = cv2.VideoCapture(0)

if not cap.isOpened():
    print("Error: Cannot access webcam")
    exit()

# Step 2: Capture frames continuously
while True:
    ret, frame = cap.read()

    if not ret:
        print("Error: Cannot capture frame")
        break

    # Step 3: Save a frame as a JPG image
    cv2.imwrite("captured_image.jpg", frame)

    # Step 4: Display the live video stream
    cv2.imshow("Live Video", frame)

    # Step 5: Resize and rotate the frame
    resized_frame = cv2.resize(frame, (640, 480))

    rotated_frame = cv2.rotate(
        resized_frame,
        cv2.ROTATE_90_CLOCKWISE
    )

    # Display the processed frames
    cv2.imshow("Resized Frame", resized_frame)
    cv2.imshow("Rotated Frame", rotated_frame)

    # Press 'q' to exit
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

# Release the webcam and close windows
cap.release()
cv2.destroyAllWindows()
~~~


## Output

### i) Write the frame as JPG image
Captured image is saved as `captured_image.jpg`

### ii) Display the video
Live webcam video is displayed

### iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)

### iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)

---

## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
