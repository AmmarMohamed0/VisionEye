# VisionEye

### Import Necessary Libraries:

- **cv2:** OpenCV library for computer vision tasks.
- **YOLO:** YOLOv8 object detection model from the ultralytics library.
- **colors, Annotator:** Utilities for visualization from the ultralytics.utils.plotting module.

### Load YOLOv8 Model:

- The YOLOv8 model is loaded 

### Prepare Video Capture:

- The script opens a video file named 'sample.mp4' using OpenCV's VideoCapture class.
- It retrieves the width, height, and frames per second (fps) of the video using cap.get() method.

### Set up Video Writer:

- It initializes a VideoWriter object to write the processed frames into an output video file named 'visioneye-avi'.
- It specifies the codec (MJPG) and the output video's frame size and fps.

### Define the Center Point:

- A variable center_point is defined with a tuple representing the center point coordinates of the bounding boxes. However, the coordinates seem incorrect as the y-coordinate is set to h (height), which may cause issues.

### Process Video Frames:

- A while loop reads frames from the video file until there are no more frames (ret is False).
- Inside the loop, each frame is passed through the YOLOv8 model for object detection.
- Detected bounding boxes and their corresponding classes are obtained from the model's output.
- An Annotator object is created for each frame with a line width of 2 pixels.
- Bounding boxes with labels are drawn on the frame using the box_label method of the annotator. However, there's an attempt to call a non-existent visioneye method of the annotator, which will raise an error.

### Display and Process Key Presses:

- The processed frame is displayed using cv2.imshow.
- The script listens for key presses, and if 'q' is pressed, it breaks out of the loop.

### Release Resources:

- After the loop, the video writer, video capture, and OpenCV windows are released using out.release(), cap.release(), and cv2.destroyAllWindows() respectively.
