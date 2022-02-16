# Single Axis Face Tracker

[![forthebadge](https://forthebadge.com/images/badges/powered-by-electricity.svg)](https://forthebadge.com)     [![forthebadge](https://forthebadge.com/images/badges/for-robots.svg)](https://forthebadge.com)        


[![forthebadge](https://forthebadge.com/images/badges/made-with-python.svg)](https://forthebadge.com)  [![forthebadge](https://github.com/28anmol/FaceTracker/blob/main/UniAxisFaceTracker/made-with-depthai.svg)](https://forthebadge.com) [![forthebadge](https://github.com/28anmol/FaceTracker/blob/main/UniAxisFaceTracker/made-with-opencv.svg)](https://forthebadge.com)

[![forthebadge](https://github.com/28anmol/FaceTracker/blob/main/UniAxisFaceTracker/raspberrypi-3b.svg)](https://forthebadge.com) [![forthebadge](https://github.com/28anmol/FaceTracker/blob/main/UniAxisFaceTracker/oak-d-lite-camera.svg)](https://forthebadge.com)



## Hardware requirements
- Raspberry pi 3 Model B(with accessories: monitor,keyboard,mouse,SD card,power adapter)
- 1 OAK-D Lite Camera
- 1 MG90S Micro Servo motor(and its accessories)
- USB to USB-C cable for the oak-d camera
- 3 Male to female jumper wires

If powering up the motor is not desired from the raspberry pi then additional components can be used:
- 15V battery
- Buck Convertor(15V to 5V)
- Breadboard
- Extra jumper wires 

## About the code
YuNet face detection model is used to detect faces in the frame. The neural network inference is carried out by oak d lite camera connected to the rpi mounted upon a servo motor which in turn is also controlled by the raspberry pi. The aim of this code is to detect a face, track and keep it in the center of the camera frame within a certain threshold range of pixels values. Simultaenously, computer vision based feedback instructions for motor actuation, bounding boxes, relevant coordinates for reference and tracking are displayed in the frame itself while the code is running to make it more comprehensive and intuitive. As only one motor is controlled, the camera tracks faces about z axis(yaw movement). Also, the code is designed to track only one object at a time and the workspace of the camera is a semi-circle due to the servo motor rotation limitations.

## Tips to run the code
In order to deploy the code, certain steps have to be followed. A virtual environment for python has to be setup, in which the dependencies given in the facetrackreq.txt file has to be installed. Once this is done the drone.py file can be executed directly to view the results.

While deploying the code, make sure to give the correct path to the blob file here in the Drone.py according to the file structured followed.
line 50: parser.add_argument("-nn", "--nn_model", help="select model path for inference", default='/home/pi/Desktop/Facetracker/face_detection_yunet_120x160.blob', type=str)

## Prerequisites
Complete setup of raspbian on raspberrypi 3B/3B+/4B. It should be up and running connected via monitor,keyboard,mouse,wifi/ethernet.
Note: The live face detection feed and face tracking won't be displayed if the raspberrypi is connected via ssh.

## Steps

## Face Tracking Results
![Face Tracking](https://github.com/28anmol/FaceTracker/blob/main/UniAxisFaceTracker/TrackingFace.mp4)
## Contributors
* [Anmol Singh](https://github.com/28anmol)
* [Luxonis Depthai Experiments](https://github.com/luxonis/depthai-experiments/tree/master/gen2-face-detection)
(The face detection model and its deployment code on oak d lite camera is taken from the given link.)
