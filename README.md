# ROS2_FOXY_CARTOGRAPHER_WITH_YDLIDAR
Try to cartographer with YDLidar X2
>Referred to https://zenn.dev/tasada038/articles/c4fff08deae9dd

## Setup the Environment
```
sudo apt install cmake pkg-config
sudo apt-get install python3 swig
sudo apt-get install python3-pip
```
```
sudo apt install ros-$ROS_DISTRO-cartographer-ros
```
### Install YDLidar
```
cd
mkdir row2wk1
cd ros2wk1
git clone https://github.com/YDLIDAR/YDLidar-SDK.git
mkdir YDLidar-SDK/build
cd YDLidar-SDK/build
cmake ..
make
sudo make install
```
```
cd ~/YDLidar-SDK/
pip3 install .
```
#### After this setup,add or modify the config files.
###### /ydlidar_ros2_drive/launch
######  ydlidar_cartographer.launch.py
###### /ydlidar_ros2_drive/config
######  ydlidar_cartographer.rviz
######  ydlidar_cartographer.lua 

### Build
```
cd
cd ros2wk1
colcon build --symlink-install
```

## Run Cartographer
### Setup bash and USB
```
source ./install/setup.bash
source /opt/ros/foxy/setup.bash
sudo chmod 777 /dev/ttyUSB0
```
### Launch
```
ros2 launch ydlidar_ros2_driver ydlidar_cartographer.launch.py
```
