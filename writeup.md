# **Finding Lane Lines on the Road** 

**Finding Lane Lines on the Road**

The goals  of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./resualt/solidYellowCurve.jpg "lanes"

---

## Reflection

My pipeline consisted of 7 steps: 
1. I converted the images to grayscale
2. I smoothed the gray images by gaussian_blur function
3. I detected the line in the gray image by canny function
4. I choosed the region which I'm interested
5. I turned the correct parameters of hough_lines function then find available lines in the region of interest
6. I draw the lines in the initial image
7. I output the image to the screen    

In order to draw a single line instand of segments, I modified the draw_lines() function by add two function: clean_lines and calc_lane_vertices. The first function could delete the lines whoes slope is much different from the mean. Then the second function calculate the slope and intercept which could fit the rest of lines. At last, I draw a singal line according to the slope and intercept.  

In order to draw a single line instand of segments, I modified the draw_lines() function by add two function: clean_lines and calc_lane_vertices. The
 first function could delete the lines whoes slope is much different from the mean. Then the second function calculate the slope and intercept which c
ould fit the rest of lines. At last, I draw a singal line according to the slope and intercept.  

###The performence of my pipline 

![alt text][image1]


### 2. potential shortcomings 


One potential shortcoming would be that the annotated video will inaccurate when we choose a different video. So we must turning the parameters of hougn_lines function for every video and This operation will spand a lot of time.
 
Another shortcoming could be that the grayscale function may make the image difficult to find edges. When I use my pipeline process the challenge task, the yellow lines become difficult to detect.


### 3. Possible improvements

A possible improvement would be find a more efficient way to choose the parameters of hough_lines function. For example, I could select several value of every parameter. Then compare the slope and the intercept of lanes in different frame of video. If we get a similar lanes from different frames, it is more likely to be an appropriate lane.  

Another potential improvement could be convert the image to different colorspace instand of grayscale, So that, we could detect the lines more accurate.  
