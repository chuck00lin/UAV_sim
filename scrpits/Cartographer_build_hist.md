### Dependency On Ubuntu Focal with ROS Noetic
```
sudo apt-get update
sudo apt-get install -y python3-wstool python3-rosdep ninja-build stow
```
### workspace create
```
cd catkin_ws
wstool init src
```
```
Error: There already is a workspace config file .rosinstall at "src". Use wstool install/modify.
```
- this is because we've used wstool for mavros before. Let us just ignore it

- use wstool merge to add rosinstall file to our workspace
```
wstool merge -t src https://raw.githubusercontent.com/cartographer-project/cartographer_ros/master/cartographer_ros.rosinstall
wstool update -t src #clone the repository
```

### Cartograper_ROS dependency
```
sudo rosdep init
rosdep update
rosdep install --from-paths src --ignore-src --rosdistro=${ROS_DISTRO} -y

src/cartographer/scripts/install_abseil.shsudo #however i didnt install in rpi and still work
apt-get remove ros-${ROS_DISTRO}-abseil-cpp
```

### Build Cartographer
[offical]
```
catkin_make_isolated --install --use-ninja
```
[mine]
```
catkin build #cant use ninja cause catkin tool haven't supported it 
```

result
```
[build] Found '11' packages in 0.0 seconds.
Finished  <<< iq_sim                               [ 0.1 seconds ]
Finished  <<< mavlink                              [ 0.9 seconds ]
Finished  <<< mavros_msgs                          [ 1.2 seconds ]
Finished  <<< libmavconn                           [ 0.1 seconds ]
Finished  <<< mavros                               [ 0.8 seconds ]
Finished  <<< cartographer_ros_msgs                [ 3.8 seconds ]
Finished  <<< mavros_extras                        [ 2.5 seconds ]
Finished  <<< test_mavros                          [ 0.3 seconds ]
Finished  <<< cartographer                         [ 1 minute and 54.8 seconds ]
Finished  <<< cartographer_ros                     [ 33.2 seconds ]
Finished  <<< cartographer_rviz                    [ 16.6 seconds ]
```
