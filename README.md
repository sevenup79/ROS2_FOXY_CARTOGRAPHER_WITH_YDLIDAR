# ROS2_FOXY_CARTOGRAPHER_WITH_YDLIDAR
try to cartographer with YDLidar X2

<Setup the Environment>
sudo apt install cmake pkg-config
sudo apt-get install python3 swig
sudo apt-get install python3-pip

sudo apt install ros-$ROS_DISTRO-cartographer-ros

mkdir row2wk1
cd ros2wk1

git clone https://github.com/YDLIDAR/YDLidar-SDK.git
mkdir YDLidar-SDK/build
cd YDLidar-SDK/build
cmake ..
make
sudo make install

cd ~/YDLidar-SDK/
pip3 install .

cd
cd ros2wk1
colcon build --symlink-install

<Run commands>
source ./install/setup.bash
source /opt/ros/foxy/setup.bash

sudo chmod 777 /dev/ttyUSB0
ros2 launch ydlidar_ros2_driver ydlidar_launch_view.py 
