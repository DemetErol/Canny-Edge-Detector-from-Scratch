# Canny-Edge-Detector-from-Scratch

1. Overview

Canny Edge Detection is one of the most commonly used edge detection algorithms. Vision
libraries will not be used for this algorithm and edge detection will be done step by step on the
image [1].

2.Details

Canny Edge Detection consists of 6 main steps. In these steps, opencv, matplotlib and numpy
libraries have been used. First, the image should be gray-scale. Then the Gaussian filter
algorithm is used. This algorithm reduces noise by making the image blur. In this way, it will
be easier to detect the edges. Later, gradient is calculated in order to determine the density and
direction of the edges with the help of Sobel filter. In the next step, Extra edges formed in the
previous stage will negatively affect our algorithm. For this reason, we use non-maximum
suppression to ensure there is only one line for the same edge. In order to minimize the noise,
double threshold is applied. Each pixel is examined and determined as strong and weak,
depending on whether they are smaller or larger than a certain value. If smaller than the
specified low value, they will be ignored. The final stage is Edge Tracking by Hysteresis. This
method is based on the logic that if there is a strong pixel between the neighbors of a weak
pixel, the weak pixel is also strong. If it does not have a strong neighbor, it will be ignored [2].
These steps were applied sequentially and results were obtained on an image. You can review
the results in section 3.

3.Results

Start;

![image](https://user-images.githubusercontent.com/45537416/116095874-78245000-a6b1-11eb-9b00-af001798f470.png)

Step 1 gray-scale;
With the help of Opencv library, the image was converted into grayscale.

![image](https://user-images.githubusercontent.com/45537416/116095990-8f633d80-a6b1-11eb-84db-0ab95e2df290.png)

Step 2 Gaussian Filter;
The noise was reduced by blurring the image with the Gaussian Filter.

![image](https://user-images.githubusercontent.com/45537416/116096063-a0ac4a00-a6b1-11eb-9ec6-87e7f7ad8239.png)

Step 3 Sobel Filter;
Edge intensity and direction were calculated using the Sobel filter.

![image](https://user-images.githubusercontent.com/45537416/116096123-af92fc80-a6b1-11eb-9b48-04ffd362a830.png)

![image](https://user-images.githubusercontent.com/45537416/116096190-bfaadc00-a6b1-11eb-8ec4-2320f99042b9.png)

Step 4 non-maximum suppression;
In this step, it is aimed to remove the excess lines formed in the previous stage.

![image](https://user-images.githubusercontent.com/45537416/116096246-cd606180-a6b1-11eb-854e-698a264bcdb4.png)

Step 5 double threshold;
The determined low and high parameters were compared with the pixels. As a result, while
those less than low are ignored, those above high are grouped as "strong", and those less than
high and higher than low are grouped as "weak".

![image](https://user-images.githubusercontent.com/45537416/116096312-dc471400-a6b1-11eb-9b8a-178439e01716.png)

Step 6 hysteresis;
When the pixels called "weak in the previous stage were examined, those who were "strong"
among their neighbors became "strong" themselves. Others were ignored. In this way, the
noises were cleaned and the Canny Edge Detector algorithm was completed.

![image](https://user-images.githubusercontent.com/45537416/116096363-e9640300-a6b1-11eb-9d52-e1e25c9387bb.png)

4.References

1- https://docs.opencv.org/master/da/d22/tutorial_py_canny.html

2- https://en.wikipedia.org/wiki/Canny_edge_detector
