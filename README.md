BasicCV
============

Contains the computer vision foundation packages, nodes, topics in ROS for RaspberryPi. Based on OpenCV and ArUco libraries.

# Nodes
aruco_detection: subscribes to "/cv_camera/image_raw" topic from cv_camera and detects aruco markers, publishes "markers_stream" topic


# Instructions and Camera Calibration
Aruco_detection needs camera intrinsic parameters (camera matrix and distortion coefficients) to perform marker detection and pose estimation correctly. These params must be set in launch file. The simplest way to obtain them is by using aruco calibration tool. Download aruco sources and run build with cmake in "build" folder. In build/utils_calibration run:
```
./aruco_calibration live -size <size of markers in calibration board (in meters)>
```
For more informations, check aruco-2.x.x/utils_calibration/REAME_CALIBRATION

# Dependencies:
Install these dependencies:
- yaml-cpp:
```
$ sudo apt-get install libyaml-cpp-dev
```

- bond_core: [https://github.com/ros/bond_core](https://github.com/ros/bond_core)
```
$ git clone https://github.com/ros/bond_core.git
```
- dynamic_reconfigure: [https://github.com/ros/dynamic_reconfigure](https://github.com/ros/dynamic_reconfigure)
```
$ git clone https://github.com/ros/dynamic_reconfigure.git
```
- roslint: [https://github.com/ros/roslint](https://github.com/ros/roslint)
```
$ git clone https://github.com/ros/roslint.git
```
- nodelet: [https://github.com/ros/nodelet_core](https://github.com/ros/nodelet_core)
```
$ git clone https://github.com/ros/nodelet_core.git
```
- image_common: [https://github.com/ros-perception/image_common](https://github.com/ros-perception/image_common)
```
$ git clone https://github.com/ros-perception/image_common.git
```
- cv_camera: [https://github.com/OTL/cv_camera](https://github.com/OTL/cv_camera)
```
$ git clone https://github.com/OTL/cv_camera.git
```


# Cleaning up
You can delete the following testings folders:
* src/dependencies/bond_core/test_bond
* src/dependencies/nodelet_core/test_nodelet
* src/dependencies/nodelet_core/test_nodelet_topic_tools
