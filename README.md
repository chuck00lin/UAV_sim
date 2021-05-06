# UAV_sim

## Environment 
- ubuntu 20.04 
- Gazebo 11
- ROS noetic full
- Ardupilot Copter 4.1
- Python 3.8.5

## Package Used
- Ardupilot_gazebo: https://github.com/khancyr/ardupilot_gazebo.git
- ROS_gazebo_Ardupilot: https://github.com/Intelligent-Quads/iq_sim.git

## Cheat sheet
**Running simulation** 
``` 
roslaunch iq_sim greenhouse.launch 
cd ~/ardupilot/ArduCopter/ && sim_vehicle.py -v ArduCopter -f gazebo-iris --console
```

## Used additional tools
ROS topic visualize tool
```
sudo apt-get install ros-noetic-rqt
sudo apt-get install ros-noetic-rqt-common-plugins
```
