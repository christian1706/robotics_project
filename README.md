# ROBOTICS PROJECT
 
This github presents the second part of our project which consists of doing visual SLAM using the orb_slam_2_ros algorithm to generate a map of our environment and allow the robot to navigate it completely autonomously.
## SETUP
 
To clone the turtlebot3 packages:
 
```bash
git clone https://github.com/ROBOTIS-GIT/turtlebot3.git
```
 
To clone the teleop keyboard:
 
```bash
git clone https://github.com/ros-teleop/teleop_twist_keyboard.git
```
 
## LAUNCH OUR PROGRAMS
 
Launch the gazebo autorace environement:
 
```bash
roslaunch turtlebot3_gazebo turtlebot3_autorace_2020.launch
```
Apply transformation between camera link and base link:
 
```bash
roslaunch orb_slam2_ros camera_tf_publisher.launch
```
Launch VSLAM node:
```bash
roslaunch orb_slam2_ros orb_slam2_r200_mono.launch 
```
Launch the teleop keyboard and teleoperate the robot to get key points:
```bash
rosrun teleop_twist_keyboard teleop_twist_keyboard.py 
```
 
Save the map after one loop of the autorace by calling this service:
```bash
rosservice call /orb_slam2_mono/save_map map.bin
```
## RESULT
 
## REFERENCES
 
[ orb_slam_2_ros](https://wiki.ros.org/orb_slam2_ros)
 
[Turtlebot3 manual](https://emanual.robotis.com/docs/en/platform/turtlebot3/overview/)