
# Advancing Speech Impairment Treatment through Image Processing Innovation

Research project utilizes the MediaPipe library to perform real-time holistic human pose and landmark detection using a webcam feed. It captures video frames from the webcam, processes them using the MediaPipe Holistic model, and then draws landmarks and connections on the video frames. The script also includes functionality to collect and export keypoints (landmarks) of detected poses to a specified directory.


## Requirements

To run this project, you will need to install the following libraries:

    OpenCV (cv2)
    NumPy (numpy)
    Matplotlib (matplotlib)
    MediaPipe (mediapipe)

`!pip install opencv-python-headless numpy matplotlib mediapipe
`

## Code Structure
The code can be divided into the following main sections:

    Importing Required Libraries:
        Imports the necessary libraries, including OpenCV, NumPy, Matplotlib, and MediaPipe.

    MediaPipe Configuration:
        Sets up the MediaPipe Holistic model with specified confidence thresholds for detection and tracking.

    Webcam Capture Loop:
        Opens the webcam for video capture (cv2.VideoCapture).
        Enters a loop that continuously captures frames from the webcam and processes them.

    MediaPipe Detection:
        Converts the captured frame to RGB format.
        Uses the MediaPipe Holistic model to detect poses and landmarks in the frame.
        Converts the frame back to BGR format.

    Drawing Landmarks:
        Draws facial landmarks, pose landmarks, and hand landmarks on the frame using the mp_drawing.draw_landmarks function.

    Styling Landmarks (Optional):
        Provides the option to draw styled landmarks with different colors and styles for better visualization.

    Frame Export (Optional):
        Contains code for exporting keypoints (landmarks) and frames to a specified directory. This part of the code is commented out but can be used to collect data for machine learning applications.

    User Interface:
        Displays the processed frame with landmarks on the screen using cv2.imshow.
        Allows the user to exit the loop by pressing the 'q' key.

    Cleanup:
        Releases the webcam capture and closes all OpenCV windows when the loop is exited.

## Usage

To use this script, follow these steps:

    1. Make sure you have the required dependencies installed.
    2. Copy the code into a Python script file (e.g., main.ipynb).
    3. Run the script.
    4. The webcam feed will open, and you will see real-time pose and landmark detection on the video.
    5. Press the 'q' key to exit the application.

## Results

|   Model          | Training Accuracy | Training Loss | Training AUC | Validation Accuracy | Validation Loss | Validation AUC | F1 Score | Precision | Recall   |
|------------------|-------------------|---------------|--------------|--------------------|-----------------|----------------|----------|-----------|----------|
| CNN              | 0.994             | 0.018         | 0.999        | 0.943              | 0.172           | 0.996          | 0.943    | 0.947     | 0.943    |
| VGG16            | 0.999             | 0.009         | 0.999        | 0.956              | 4.386           | 0.975          | 0.954    | 0.958     | 0.956    |
| EfficientNetB0   | 0.951             | 0.169         | 0.997        | 0.951              | 0.169           | 0.997          | 0.949    | 0.957     | 0.951    |
| MobileNetV2      | 0.946             | 1.195         | 0.975        | 0.946              | 1.195           | 0.975          | 0.945    | 0.949     | 0.946    |


## Note

The code includes options for drawing styled landmarks with different colors and styles, which can be customized as needed.
The script captures frames continuously until the user presses the 'q' key to exit. Make sure to exit the script gracefully to release the webcam resources.
This code provides a foundation for real-time pose and landmark detection and can be extended for various applications, including gesture recognition, fitness tracking, and more.