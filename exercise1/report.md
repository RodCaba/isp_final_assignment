## Exercise 1 Report

### Techniques used
The techniques used in this exercise were Background Subtraction and Frame Differencing. To combine these techniques together, we apply both techniques to the video and combine the results in a combined mask using the `cv2.bitwise_or()` function. We use this combined mask in the `cv2.findContours()` function.

### Background Subtraction
Background subtraction models the static background of the scene and identifies moving objects as deviations of the background model. In OpenCV, the `cv2.createBackgroundSubtractorMOG2()` function creates the background subtractor object and we apply that object to the ROI (Region of Interest) to detect moving objects.

We also apply the functions `cv2.erode()` and `cv2.dilate()` to remove noise from the image.

#### Frame Differencing
In the frame differencing technique, we apply the absolute difference between two consecutive frames to detect moving objects. We then apply a threshold to the difference, so any pixel value above the threshold is considered a moving object.

To improve the accuracy of the technique, we apply a Gaussian blur filter to a grayscaled image of the frame.

### Application Description
The application sets the video file path, then this path is passed to the `analyze_frame` function, which is responsible for reading the video file, applying the background subtraction and frame differencing techniques, and drawing the contours of the moving objects in the video.

### Task 2 Table
| | Total Number of Cars | Cars Per Minute |
| --- | --- | --- |
| Traffic_Laramie_1.mp4 | 6 | 2.02 |
| Traffic_Laramie_2.mp4 | 4 | 2.27 |