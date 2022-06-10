https://github.com/Slamtec/rplidar_sdk

frame_grabber (Legacy)

This demo application can show real-time laser scans in the GUI and is only available on Windows platform.

We have stopped the development of this demo application, use https://www.slamtec.com/robostudio  instead.


If you are using ROS (Robot Operating System), please use our open-source ROS node directly: https://github.com/slamtec/rplidar_ros

*************************** QUICK TEST - UBUNTU18.04 ROS1 Melodic ******************************
```
source /opt/ros/melodic/setup.bash
mkdir -p catkin_ws/src
cd catkin_ws/src
git clone https://github.com/slamtec/rplidar_ros
cd ..
catkin_make
source devel/setup.bash
roslaunch rplidar_ros view_rplidar.launch
```
```diff
- If the following shows up:
- Error, cannot bind to the specified serial port /dev/ttyUSB0.
- This error is due to a BAD USB-MicroUSB cable!!!!
- After fixing cable device should show under ttyUSB0 doing >ll /dev
- It should also show up when doing > lsusb
```

*********************** PYTHON TEST - WINDOWS **********************************

https://www.youtube.com/watch?v=dR2XIwRIseY

https://github.com/lakshmanmallidi/PyLidar3

*******************************************************************************
