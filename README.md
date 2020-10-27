# navigation-assistant

## About
My goal with this project was to create a novel navigational aid that offers a large amount of information about the user’s surroundings, while also being simple to learn to use and understand. This innovative device  offers both reliable object detection and an intuitive feedback mechanism to communicate the information to the user. The device is able to process images from two, front-facing cameras in order to both detect objects and their distances from the user, and output this information to the user through a series of vibration motors in a glove. Ultimately, the device will give blind or visually impared people (BIV) a more complete picture of their environment to help them travel more safely and efficiently.

<img src="https://user-images.githubusercontent.com/36171993/97319353-cb206600-183a-11eb-9702-6f4088a397d3.png" width="200">

## Materials
* 2 720p/1080p cameras
* Raspberry Pi
* Arduino Uno
* 12 Vibration Motors

## Software Packages
* OpenCV
* TensorFlow
* NumPy

## Image Processing

1. Calibrate cameras for distortion by finding some specific points of which we already know the relative positions (e.g. square corners in the chess board). We know the coordinates of these points in real world space and we know the coordinates in the image, so we can solve for the distortion coefficients.

<img src="https://user-images.githubusercontent.com/36171993/97322186-89dd8580-183d-11eb-9061-e2cba4994523.png" width="200">

2. If we know the distance between two cameras (B) and the focal length of camera (f), then the depth of a point in a scene is inversely proportional to the difference in distance of corresponding image points (x and x') and their camera centers. Ultimately, with this information, we can derive the depth of all pixels in an image.
<img src="https://user-images.githubusercontent.com/36171993/97323574-f1e09b80-183e-11eb-931d-3e41d439edeb.png" width="200">

3. Setup object detection and train on indoor objects that BIV's use as landmarks or have frequent accidents (i.e. lamps, chairs, hand-rails, etc.) by following Google's tutorial on using MobileNet SSdv3 (https://github.com/tensorflow/models)

4. Combine object detection and depth map in order to relay vibrational information to glove
<p float="left">
  <img src="https://user-images.githubusercontent.com/36171993/97324296-ad093480-183f-11eb-80f6-aab20d982bdb.png" width="400">
  <img src="https://user-images.githubusercontent.com/36171993/97324458-d9bd4c00-183f-11eb-89ef-a4a2308724b3.png" width="300">
  <img src="https://user-images.githubusercontent.com/36171993/97325799-5a307c80-1841-11eb-9c64-4bed89fb1fee.png" width="100">
</p>
Left image indicates real world picture with highlighted areas indicating portions of the image that are physically close to the user and bounding boxes of common objects recognized by the object detection model. Center image represents the depth map of the left image where the brighter the pixel, the closer it is to the user. Right image is the vibrational feedback sent to vibrational motors where the colors represent intensity of vibration: red is high, yellow is medium, and green is none.

## Conclusion
Currently no other device is able to capture a combination of direction, depth, and object recognition. By running the input from the 2 stereo cameras through visual processing software, we are able to identify common indoor objects as well as relative direction and distance away from a user. Practically, this means if a user was to walk into a room, they would be able to not only identify a hanging lamp 6 feet to their left for example, but also receive feedback that classifies an object in front of them like a door. 






