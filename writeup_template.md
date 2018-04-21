# **Finding Lane Lines on the Road** 

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I used gaussian blur to make the image smooth and reduce noise, with a gaussian blur kernel size of 15.

Next, I use canny detection to find the edges of the image applying a low threshold of 50 and high threshold of 150 which seem to be provide the best output (based on trial and error).

Then I find the region on interest out of the image (considering the camera is in the middle of the dashboard) and applied hough algorithm to detect lines in the image

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by to compute all the slope to detect if they are the left of right line and remove not reasonable results based on the values of k and b (as described in the section videos) and finally draw those lines.

![Solid white lane input](https://github.com/feleir/CarND-LaneLines-P1/raw/master/test_images/solidWhiteCurve.jpg)
![Solid white lane output](https://github.com/feleir/CarND-LaneLines-P1/raw/master/test_images_output/solidWhiteCurve.jpg)

![Solid yellow curve input](https://github.com/feleir/CarND-LaneLines-P1/raw/master/test_images/solidYellowCurve.jpg)
![Solid yellow curve output](https://github.com/feleir/CarND-LaneLines-P1/raw/master/test_images_output/solidYellowCurve.jpg)


### 2. Identify potential shortcomings with your current pipeline

One potential shortcoming is that the parameters are tuned for the conditions of the images/videos so they can be some failures while running this code in real time conditions.

Another shortcoming would be that the paramters to limit slope and remove not needed points are based on trial and error.

Another shortcoming is that the curves are potentially not being properly detected and dark shadows or bright shadows can be found as lanes or create unrequired changes in the lane lines.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to draw the lines in segments instead of a full line to be able to easy detect curves and also find probably better values or adapt the values for the different phases of the pipelines according to light conditions.