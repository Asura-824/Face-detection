# 📸 Real-Time Face Detection with OpenCV

This is a simple Python script that demonstrates **real-time face detection** using the **OpenCV (cv2)** library and the pre-trained Haar Cascade classifier for frontal faces. The script opens your default webcam, processes the video stream, and draws a green bounding box around any detected faces.

## ✨ Features

* **Real-time** processing of video feed from the webcam.
* Uses the **Haar Cascade classifier** (`haarcascade_frontalface_default.xml`) for fast face detection.
* Draws a **green rectangle** around each detected face.
* The application runs until the user presses the **'q'** key.

## 🛠️ Prerequisites

To run this script, you need to have **Python** installed on your system, along with the **OpenCV (cv2)** library and its dependencies.

* **Python 3.x**
* **OpenCV (`cv2`)**

## 💻 Installation

1.  **Clone the repository** (if you're hosting this on GitHub):
    ```bash
    git clone https://github.com/Asura-824/Face-detection.git
    cd face-detection-opencv
    ```

2.  **Install OpenCV:**
    You can easily install OpenCV using `pip`:
    ```bash
    pip install opencv-python
    ```
    *(Note: This package includes the necessary Haar Cascade XML files, which are accessed via `cv2.data.haarcascades`.)*

3.  **Ensure a working webcam:**
    The script requires access to your system's default camera (indexed as `0`).

## 🚀 How to Run

1.  Save the provided code as a Python file (e.g., `detect_faces.py`).
2.  Run the script from your terminal:
    ```bash
    python detect_faces.py
    ```

3.  A new window titled **'Face Detection'** will open, displaying the live video feed from your webcam with the bounding boxes around faces.

4.  To **stop** the application, ensure the video window is active and press the **`q`** key.

## ⚙️ Key Code Explanation

| Line/Section | Purpose |
| :--- | :--- |
| `face_cascade = cv2.CascadeClassifier(...)` | **Loads the trained model** (Haar Cascade XML file) responsible for recognizing the facial features. |
| `cap = cv2.VideoCapture(0)` | **Initializes the connection** to the default webcam (`0`). |
| `gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)` | **Converts the frame** to grayscale. Detection often works better and faster on grayscale images. |
| `faces = face_cascade.detectMultiScale(...)` | The **core detection function**. It scans the grayscale image and returns a list of bounding boxes (x, y, w, h) for every detected face. |
| `cv2.rectangle(...)` | **Draws the green rectangle** on the original color frame using the coordinates found by `detectMultiScale`. |
| `cv2.imshow(...)` | **Displays the video frame** with the rectangles in a dedicated window. |
| `if cv2.waitKey(1) & 0xFF == ord('q'):` | **Handles the exit condition.** Waits 1 millisecond for a key press and checks if the key is 'q'. |

## 🤝 Contributing

Feel free to fork this repository, suggest improvements, or submit pull requests. For example, you could enhance this by:

* Adding eye or smile detection.
* Implementing a performance counter (FPS).
* Using more modern and accurate deep learning models (like YOLO or SSD) via OpenCV's DNN module.
