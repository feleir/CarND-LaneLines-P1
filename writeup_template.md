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

[solidwhite]: ./test_images_output/solidWhiteRight.jpg 
[solidyellow]: ./test_images_output/solidYellowLeft.jpg
[curved1]: ./test_images_output/solidWhiteCurve.jpg
[curved2]: ./test_images_output/solidYellowCurve.jpg


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
