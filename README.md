# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images_output/solidWhiteCurve.jpg "solidWhiteCurve output"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps.


1. Images were grayscaled for easy analysis

2. Gaussian blur was used to reduce noise. Kernel_size is set to 5.

3. The edges were obtained by canny-edge-detection.

4. The image was masked into the parts of interest.

5. Through the hough transform we were able to get lines containing edges.   


In order to draw a single line on the left and right lanes, I modified the draw_lines() function.

A straight line was drawn by averaging all the slope and bias values ​​obtained through the hough transform.


![alt text][image1]

Due to lack of time to submit the project, the optional challenge was not completed.

### 2. Identify potential shortcomings with your current pipeline

1. Since the images used were images of similar brightness, the lane detection was good. However, if the brightness changes (due to the shadows by the trees ... etc), the detection may not be done properly.

2. My pipeline does not recognize curve paths because it proceeds in a way that it averages the slopes and draw a straight line.

3. My pipeline can not handle large noises. During detection, pipeline detect the edges that should not be detected.

### 3. Suggest possible improvements to your pipeline

1. If other factors are added for detection, pipeline may properly detect lane lines even during the brightness changes.

2. Add an algorithm that can calculate curvature and draw a curve, pipeline will detect a curved path.

3. If an edge with a large difference in slope is founded, exclude it from the calculation. It can reduce noises. 
