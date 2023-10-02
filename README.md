# The Complete Self-Driving Car Course - Applied Deep Learning from Udemy
Done together with a colleague at YABS and a mentor from Sylog, the mentor worked with autonomous driving and could give us insights and information from how it is done in the industry. The course goes through Python, NumPy, Computer Vision with OpenCV, Neural networks with PyTorch and more.

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




## Self-driving car project

In the course project we trained a neural network to drive a car in a car driving simulator.
![image](https://github.com/Calle-Lundqvist/Self-driving-car-Udemy/assets/85300362/6b95e9e5-25b4-4c23-be80-449387315b73)

We created our own training data by manually driving the car around the map, and on each frame we saved: 
* An image of what the car's front camera sees.
* The current steering angle of the car.

To increase our amount of training data we used data augmentation, the following augmentations were done:
* Zooming.
* Panning.
* Altering the brightness.
* Flipping the image.

![image](https://github.com/Calle-Lundqvist/Self-driving-car-Udemy/assets/85300362/5c2a25f8-e8a3-4605-be6f-3da5a3a2b7b5)

We split our data into training and validation datasets. We then trained a neural network on our data. The chosen neural network was Nvidia's Neural Network for vehicle control:

![image](https://github.com/Calle-Lundqvist/Self-driving-car-Udemy/assets/85300362/c3deaa56-e9bc-49cc-b655-438c62f494b8)

Input is an image of what the car sees. Output is steering angle that the car should apply. 

By using Flask in Python we were able to control the car with our neural network. Each frame we send the image of what the car sees to our neural network and it returns the steering angle to apply.

Our neural network is able to drive the car along the path very nicely, our model is also generalizable enough to allow the model to drive a car along a path that it has never before seen. 

Demo can be seen in this video: https://github.com/Calle-Lundqvist/Self-driving-car-Udemy/blob/main/demo_car.mp4 
