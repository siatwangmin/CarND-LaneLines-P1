# **Finding Lane Lines on the Road** 

## How to Run
Please review the installation instruction [here](https://github.com/udacity/CarND-LaneLines-P1/blob/master/README.md)

---

**Finding Lane Lines on the Road**

The goals of this project are the following:
* Make a pipeline that finds lane lines on the road

[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

My pipeline consisted of 5 steps
* Selecting the lane color by white and yellow color threshold
* Converting the image into gray
* Applying Guassian blur on the gray image and then detecting edges by Canny edges detection
* Selecting the interested region
* Using Hough Transform line deteion

In order to draw a single line on the left and right lanes, there should be some modification of draw_line()
* Dividing lines into left and right line by its slope $k=(y2 - y1) / (x2 - x1)$
* Dropping lines whose slope angle is too small or too large
* Calculating left lanes and right  average slopes, and draw lines


![alt text][image1]


### 2. Identify potential shortcomings with current pipeline


One potential shortcoming is that Detecting lanes fails when lightness is changed OR the lanes don't fall into the region of interest


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to detect curve lanes

Another potential improvement could be to make the detection more robust to lightness change
