# Real-Time Hand Detection using OpenCV and MediaPipe
This project implements real-time hand detection using a webcam feed. The application utilizes OpenCV for capturing video and MediaPipe for detecting hand landmarks, making it easy to track hand movements in real-time.

# Features
    Detects hands and displays hand landmarks in real-time from a webcam feed.
    Draws connections between hand landmarks to visualize hand movement.
# Requirements
Make sure you have the following dependencies installed:

    Python 3.x
    OpenCV
    MediaPipe

# How to Run
    Clone or download this repository to your local machine.
    Open a terminal and navigate to the project folder.
    Run the Python script
    The webcam feed will open, and the hand detection will begin in real-time.
# Code Explanation
1. Import Libraries
The script imports OpenCV for handling video input and display and MediaPipe for hand detection.
2. Initialize Hand Detection
mp.solutions.hands is used to initialize the hand detection solution from MediaPipe.
Hands() processes each frame to detect hand landmarks.
3. Capture Video from Webcam
cap = cv2.VideoCapture(0) opens the default webcam for video input.
A loop continuously captures each frame of the video feed.
4. Convert Frame to RGB
OpenCV captures frames in BGR format, but MediaPipe requires frames to be in RGB format. This conversion is done using:
frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
5. Detect Hands
The frame is passed to the hand detection model, which processes the frame and returns landmarks if hands are detected:results = hands.process(frame_rgb)
6. Draw Hand Landmarks
If hand landmarks are detected, they are drawn on the frame using mp_drawing.draw_landmarks.
7. Display the Frame
The frame with the detected hand landmarks is displayed using OpenCV’s cv2.imshow.
8. Exit Condition
The loop continues until the 'ESC' key (27 ASCII code) is pressed:
if cv2.waitKey(1) & 0xFF == 27:
    break

