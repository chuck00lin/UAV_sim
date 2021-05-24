# UAV_sim
Most are scripts, with some code for UAV Gazebo simulation

## Environment 
- clean ubuntu 20.04
- Gazebo 11
- ROS noetic full
- Ardupilot Copter 4.1
- Python 3.8.5

## Package Used
- Ardupilot_gazebo: https://github.com/khancyr/ardupilot_gazebo.git
- ROS_gazebo_Ardupilot: https://github.com/Intelligent-Quads/iq_sim.git
- Cartographer SLAM: https://github.com/cartographer-project/cartographer_ros

## Cheat sheet
**source**
cp to workspace
```
source devel/setup.bash
```
**Running simulation** 
``` 
roslaunch iq_sim greenhouse.launch 
cd ~/ardupilot/ArduCopter/ && sim_vehicle.py -v ArduCopter -f gazebo-iris --console
```
**download from google drive**
```
#https://drive.google.com/file/d/xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx/view
gdown --id 'xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'
```
## Used additional tools
ROS topic visualize tool
```
sudo apt-get install ros-noetic-rqt
sudo apt-get install ros-noetic-rqt-common-plugins
```
Python package
```
sudo apt install python3-pip
pip install gdown
```
## Testing
RTAB-MAP
```
sudo apt install ros-noetic-rtabmap-ros 
roslaunch rtabmap_ros demo_robot_mapping.launch
rosbag play --clock demo_mapping.bag  
```
