# navigation-assistant

## About
My goal with this project was to create a novel navigational aid that offers a large amount of information about the user’s surroundings, while also being simple to learn to use and understand. This innovative device  offers both reliable object detection and an intuitive feedback mechanism to communicate the information to the user. The device is able to process images from two, front-facing cameras in order to both detect objects and their distances from the user, and output this information to the user through a series of vibration motors in a glove. Ultimately, the device will give blind or visually impared people a more complete picture of their environment to help them travel more safely and efficiently.

<img src="https://user-images.githubusercontent.com/36171993/97319353-cb206600-183a-11eb-9702-6f4088a397d3.png" width="200">

## Image Processing

1. Calibrate cameras for distortion by finding some specific points of which we already know the relative positions (e.g. square corners in the chess board). We know the coordinates of these points in real world space and we know the coordinates in the image, so we can solve for the distortion coefficients.

<img src="https://user-images.githubusercontent.com/36171993/97322186-89dd8580-183d-11eb-9061-e2cba4994523.png" width="200">


