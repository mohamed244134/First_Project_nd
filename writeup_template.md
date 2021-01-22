# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I applied gaussian filter to the grey image in order to remove the noise in the grey image using a kernel size of 5, then I have detected the edges in the filtered image using the canny method with a minimum threshold of 100 and a maximum threshold of 250 i chosed those thresholds based on trial and error and then those numbers was suited for me , then i have focused on the region of interest to draw the lanes by using the function region of interest and then i have weighted the final image with the the hough lines of region of interest and the original image.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by splitting the lines into two groups a group for the right lines and a group for the left lines , In order to determine which line corresponds to one of the groups i have used the slope of the line so if the slope is positive it  means that the line is a right one and if the slope is negative it means that the line is a left one and then i have averaged the line segment in order to apply the most suitable line segment to the image.
![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the lane is more curved my current pipline won't work effectively also if the lane segments have different gaps i think that my algorithm won't either work effectively .also sometimes my line gets out of the region of interest .



### 3. Suggest possible improvements to your pipeline

A possible improvement would be to use the applications of deeplearning in order to adapt with the lane changes 

Another potential improvement could be to use more advanced algorithms for computer vision.
