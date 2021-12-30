Lane Detector using Hough Transform

Our approach in this method is to detect prominent straight lines through edge detection.

Pipeline Model Used :-

Input Frame 
     |
     v
Greyscale
     |
     v
Gaussian Blur
     |
     v
Canny
     |
     v
Segment
     |
     v
Hough Transform
     |
     v
Paste Results on output frame.

Setting up environment :-

If you want to use or test the code , you are going to need OpenCV. To Install , open terminal and run,

pip install opencv-python






---

## Updates

**12/17/2018**</br>
Article published on Medium.
