# **Finding Lane Lines on the Road** 

[image1]: ./test_images_output/solidWhiteCurve.jpg "solidWhiteCurve output"

### PipeLine

My pipeline consisted of 5 steps.

1. **Grayscale** image.
2. **Gaussian_Blur** for reduce noise (Kernel_size == 5). 
3. Get edges with **Canny_Edge**.
4. **Mask image** and get ROI (Region Of Interest).
5. Get lines containing edges with **hough transform** .   

In order to draw a single line on the left and right lanes, I modified the draw_lines() function.

A straight line was drawn by averaging all the slope and bias values ​​obtained through the hough transform.

![alt text][image1]

### Shortcomings

1. Since the images used were images of similar brightness, the lane detection was good. However, if the brightness changes (due to the shadows by the trees ... etc), the detection may not be done properly.
2. Pipeline does not recognize curve paths because it proceeds in a way that it averages the slopes and draw a straight line.
3. Pipeline can not handle large noises. During detection, pipeline detect the edges that should not be detected.

### Possible Improvements

1. If other factors are added for detection, pipeline may properly detect lane lines even during the brightness changes.
2. Add an algorithm that can calculate curvature and draw a curve, pipeline will detect a curved path.
3. If an edge with a large difference in slope is founded, exclude it from the calculation. It can reduce noises. 
