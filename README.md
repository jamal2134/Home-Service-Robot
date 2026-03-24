
# Home Service Robot

In this project, you will use everything you learned in the Nanodegree Program to build a Home Service Robot in ROS

##  System Requirements

- Ubuntu 20.04  
- ROS Noetic  
- Gazebo  
- Git  

---

## ⚠️ Important Note

This project was implemented using **TurtleBot3** instead of TurtleBot2.

The original project instructions are based on TurtleBot2, but it is not fully compatible with **ROS Noetic (Ubuntu 20.04)** due to deprecated dependencies.

Therefore, TurtleBot3 was used as a fully supported and stable alternative for ROS Noetic.

All functionalities such as SLAM, navigation, and visualization were implemented successfully using TurtleBot3.

## Dependencies
The project relies on the following dependencies to run successfully:

```bash
sudo apt-get update && sudo apt-get upgrade -y
sudo apt-get install ros-noetic-turtlebot3
sudo apt-get install ros-noetic-teleop-twist-keyboard
sudo apt-get install ros-noetic-openslam-gmapping
sudo apt-get install ros-noetic-navigation
```

The provided scripts launch multiple ROS nodes using the **xterm** terminal emulator.  
If it is not already installed, you can install it using the following command:

```bash
sudo apt-get install xterm
```

## Create Catkin Workspace
To set up a new Catkin workspace, run the following commands:

```bash
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws
catkin_make
source devel/setup.bash
```

## Clone Repository
lone the project repository into the `src` directory of your Catkin workspace:
```bash
cd ~/catkin_ws/src
git clone https://github.com/jamal2134/Home-Service-Robot.git
sudo mv Home-Service-Robot/* ./
rm -rf Home-Service-Robot
```

## Build Workspace
Navigate to your Catkin workspace and build the project:

```bash
cd ~/catkin_ws
catkin_make
source devel/setup.bash
```

## Make the scripts executable
Ensure all script files have execution permissions:
```bash
cd ~/catkin_ws/src/Robot_home_service/scripts
sudo chmod +x *.sh
```


## SLAM Testing
Run the SLAM test script:

```bash
cd ~/catkin_ws/src/Robot_home_service/scripts
./test_slam.sh
```
After completing the mapping process, save the generated map in the map directory:

```bash
rosrun map_server map_saver -f ../map/map
```


## Localization and Navigation Testing
Run the navigation test to verify localization and path planning:

```bash
cd ~/catkin_ws/src/Robot_home_service/scripts
./test_navigation.sh
```

## Home Service Robot
Execute the main script to run the complete home service scenario (pickup and drop-off):
```bash
cd ~/catkin_ws/src/Robot_home_service/scripts
./home_service.sh
```




