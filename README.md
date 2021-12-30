# Lane Detector using Hough Transform

Our approach in this method is to detect prominent straight lines through edge detection.

## Pipeline Model Used :-

Input Frame    -> Greyscale -> Gaussian Blur -> Canny  -> Segment    -> Hough Transform    -> Paste Results on output frame.

## Setting up environment :-

If you want to use or test the code , you are going to need OpenCV. To Install , open terminal and run,
```
pip install opencv-python
```

### Canny

The Canny Detector is a multi-stage algorithm optimized for fast real-time edge detection. The fundamental goal of the algorithm is to detect sharp changes in luminosity (large gradients), such as a shift from white to black, and defines them as edges, given a set of thresholds. 

### Gaussian Blur

A Gaussian filter is applied to convolve (smooth) the image to lower the detector’s sensitivity to noise. This is done by using a kernel (in this case, a 5x5 kernel) of normally distributed numbers to run across the entire image, setting each pixel value equal to the weighted average of its neighboring pixels.

### Segmenting lane area
We create a triangular mask to segment the lane area and discard the irrelevant areas in the frame to increase the effectiveness of our later stages.

### Hough Transform
We apply Hough Transform to identify two straight lines — which will be our left and right lane boundaries

### Paste Results in output Frame
The lane is visualized as two light green, linearly fitted polynomials which will be overlayed on our input frame.

## Disadvantages of the approach
> Approach breaks when urved lanes appear.
> Lanes with dotted markings or with no clear markings at all are also ignored by the lane detector since there are no continuous straight lines that satisfy the Hough transform threshold. 
> Weather and lighting conditions affecting the visibility of the lines will be an issue