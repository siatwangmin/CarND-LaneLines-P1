# **Finding Lane Lines on the Road** 

## How to Run
Please review the installation instruction [here](https://github.com/udacity/CarND-LaneLines-P1/blob/master/README.md)

---

**Finding Lane Lines on the Road**

The goals of this project are the following:
* Make a pipeline that finds lane lines on the road

[//]: # (Image References)

[image1]: ./report_images/solidWhiteRight.jpg "Original Image"
[image2]: ./report_images/color_masked_image.jpg "Color-Masked Image"
[image3]: ./report_images/gray.jpg "Gray Image"
[image4]: ./report_images/edges.jpg "Edge Image"
[image5]: ./report_images/masked_edges.jpg "Masked_edges Image"
[image6]: ./report_images/LinesolidWhiteRight.jpg "Final"

---

### Reflection

My pipeline consisted of 5 steps:

![alt text][image1]

* Selecting the lane color by white and yellow color threshold

![alt text][image2]

* Converting the image into gray

![alt text][image3]

* Applying Guassian blur on the gray image and then detecting edges by Canny edges detection

![alt text][image4]

* Selecting the interested region

![alt text][image5]

* Using Hough Transform line deteion

![alt text][image6]

In order to draw a single line on the left and right lanes, there should be some modification of draw_line()
* Dividing lines into left and right line by its slope k=(y2 - y1) / (x2 - x1)
* Dropping lines whose slope angle is too small or too large
* Calculating left lanes and right  average slopes, and draw lines


### 2. Identify potential shortcomings with current pipeline


One potential shortcoming is that Detecting lanes fails when lightness is changed OR the lanes don't fall into the region of interest


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to detect curve lanes

Another potential improvement could be to make the detection more robust to lightness change
