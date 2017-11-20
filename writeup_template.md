# **Finding Lane Lines on the Road** 

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale. Next I smoothed the images using a guassian blur.  The canny edge detection algorithm was applied for edge detection. Then a region of interest was created i.e. a quadrilateral.  Next the houghlines were computed.  

In order to draw a single line on the left and right lanes, I created a process_hough function which does the bulk of applying the slope-intercept form to the hough lines and identifies the lanes.

### 2. Identify potential shortcomings with your current pipeline
One potential shortcoming would be what would happen if we encouter a continous curve.  
This approach may not be ideal to handle varying degress of curves on the highway.
Another shortcoming could be if there was a dip on the on the highway.  What I mean by a dip refers to a raised/elevated segment of the highway i.e. iimited sight distance. How would computer handle/correct for this ?
Finally another potential shortcoming, in my opinion, is the scenario where the lane on the highway has completely disappeared - yes this can happen if road crews are working on the highway lane and several times you will see that the lanes are not clearly marked.  Humans can quickly determine this problem of absence of lane marking.  However the computer would need to rely on a different algorithm to determine its lane and avoid colliding with the rest of the traffic on the road in the absence of lane markings. 

### 3. Suggest possible improvements to your pipeline
There is still some extra noise/fuzziness with my pipleine that can be improved.  This creates a somewhat erratic lane detection as seen from the jumpiness.