**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. 

Step1   First, I converted the images to grayscale.

Step2   use GaussianBlur to smooth the image.

Step3   use cv2.Canny to find the gradient(big change rate) of the picture

Step4   define a polygon mask area. using cv2.fillPoly

Step5   use cv2.HoughLinesP to find the line. Depending the parameter, i find several lines in the image.

Step6   I write a function "line_to_point", find point from lines, add these point to a list.

Step7   Analyze these HoughLines, if slope too big or too small ,ignore the line.
        Classify the lines into left/right.Using "line_to_point" funciton to make a data list.
        Run np.polyfit in these data. Then a got too average line.

Step8   add the line to the original image.
        all step1 - 8 is in the function"Process_image"

Step9   use the pipeline to process an video.
        


In order to draw a single line on the left and right lanes, I modified the draw_lines() function by Analyze these HoughLines, if slope too big or too small ,ignore the line. Classify the lines into left/right.Using "line_to_point" funciton, make a data list. Run np.polyfit in these data. Then a got too average line.


###2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be when the camera position change, i should modify the mask area.



###3. Suggest possible improvements to your pipeline

A possible improvement would be to define the mask size according to the image size.

Another potential improvement could be to optimize the code.  
