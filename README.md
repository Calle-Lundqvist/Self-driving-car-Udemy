# The Complete Self-Driving Car Course - Applied Deep Learning from Udemy
Done together with a colleague at YABS and a mentor from Sylog. The course goes through Python, NumPy, Computer Vision with OpenCV, Neural networks with PyTorch and more.

The course went through a couple of different sections, the most interesting ones were "Finding Lane Lines" and the project on self-driving car. 

## Finding Lane Lines
![image](https://github.com/Calle-Lundqvist/Self-driving-car-Udemy/assets/85300362/08a4a40b-8a20-405f-8a72-e57a2fad9ad2)

We used OpenCV to find lane lines in this image, and then in a video from the same road. We did the following operations:
* Converted image to grayscale to simplify the problem. Only one color channel instead of three (RGB).
* Smoothed image with Gaussian blur, reduces noise in the image. Each pixel is set to an average of its neighbours.
* Canny edge detection to detect edges in the image. Finds the edges by finding where the gradients are strongest.
* Defined a region of interest.
* Used Hough transform to find lines in the image.

  End results is this:
  ![image](https://github.com/Calle-Lundqvist/Self-driving-car-Udemy/assets/85300362/e54aa259-e6df-4f89-9971-da5080888f61)

![video](Section_5_finding-lanes/output.mp4)



## Self-driving car project

