Fork of [AMZ-Driverless/fsd_skeleton](https://github.com/AMZ-Driverless/fsd_skeleton) adapted to run under ROS melodic and Mint 19 (Ubuntu Bionic).

# General Instruction for ROS

## Installation of ROS on Mint 19 (based on Ubuntu 18.04 bionic):

```bash
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu bionic main" > /etc/apt/sources.list.d/ros-latest.list'
sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 421C365BD9FF1F717815A3895523BAEEB01FA116
sudo apt-get update
sudo apt-get install ros-melodic-desktop-full python-catkin-tools
```

## Other useful stuff:
Use tmux to subdivide your terminal window instead of opening multiple terminal windows or tabs.

# Setting up the Workspace
## First install [this fork of AMZ-Driverless/fssim](https://github.com/Ungetym/fssim/edit/master/README.md)
## Clone the repository and install dependencies
```bash
git clone https://github.com/Ungetym/fsd_skeleton.git
cd ~/fsd_skeleton
./update_dependencies.sh
```
## Source [fssim](https://github.com/Ungetym/fssim) and build workspace
```bash
source ../my_ws_name/devel/setup.bash
catkin_make -j1
```

## Source environment and start simulation
```bash
source devel/setup.bash
roslaunch fsd_common_meta trackdrive.launch
```
Wait a few seconds until the simulation is fully loaded and execute in another terminal(tab)
```bash
cd fsd_skeleton
source devel/setup.bash
roslaunch control_meta trackdrive.launch
```
