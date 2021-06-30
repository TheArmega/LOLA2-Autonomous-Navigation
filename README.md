# LOLA2-Autonomous-Navigation

## Description
This project build with ROS and Python provide a whole nodes structure that makes a robotic platform able to navigate autonomously using RVIZ as a 3D map viewer where the point and orientation in which the platform is to be located is indicated. this proyect is optimized for a platform designed by the research group of the University of Alcalá GRAM. 

## Visuals
https://user-images.githubusercontent.com/38068010/123829900-1e374500-d903-11eb-9b3e-be9fd4f85a9e.mp4

## Installation
To use this software you must have ROS installed in your platform. We have been using ROS Melodic cause our platform runs Ubuntu 18.04, in case that you are runinng Ubuntu 16.04 you have to install ROS Kinetic. There are not any differences between this two versions, ROS Melodic is an adaptation of ROS Kinetic for Ubuntu 18.04.

To install ROS:

Setup the sources.list

$ sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

Setup the keys

$ curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -


$ sudo apt update

I recommend to install the full version with all the libraries as RVIZ, we will need them for runing the project.

$ sudo apt install ros-melodic-desktop-full

Environment setup

$ echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc

$ source ~/.bashrc

Dependencies for building packages

$ sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential

$ sudo apt install python-rosdep

$ sudo rosdep init

$ rosdep update

It is necessary to install a library that may not be installed with the ROS installation. This library is used to display a layer in RVIZ that shows the obstacles in the map. 

$ sudo apt-get install ros-melodic-spatio-temporal-voxel-layer

## Usage

To use this software you must follow the next steps:

Open a terminal
1. $ cd ~/catkin_lola2
2. $ catkin_make
3. $ . deves/setup.bash
4. $ cd src
5. $ rosrun lola2_global hwinterface_script_lola2

Open another terminal
1. $ cd ~/catkin_lola2
2. $ catkin_make
3. $ . deves/setup.bash
4. $ cd src 
5. $ roslaunch lola2_global rviz_navigation.launch

We have to start runing the hwinterface_script_lola2.py first cause if not it will be waiting for the rviz_navigation.launch to finish. After we launch the hwinterface we launch the rviz_navigation.launch that will start all the nodes structure that we need to start the navigation.

After this we will see in the screen that RVIZ opens.

<img width="1096" alt="Screenshot 2021-06-30 at 10 45 57" src="https://user-images.githubusercontent.com/38068010/123930814-5d5fa780-d990-11eb-8532-db4bb158d046.png">

The platform will be displayed in a predetermined point in the map, to change that we just have to click in the "2D Pose Estimate" option and click in the map where the platform is located.

https://user-images.githubusercontent.com/38068010/123932843-212d4680-d992-11eb-94fb-80aa0db5e3a2.mp4

When we have the platform in where in the real world is we just have to indicate the point where we want the platform to go. To do that we just have to select the "2D Nav Goal" option and click in the map where you want the platform to be. While you click in the map to select the point you have to drag the cursor indicating the orientation that you want the platform to have when it reaches the point.

https://user-images.githubusercontent.com/38068010/123990523-1ee6de80-d9ca-11eb-8975-39ca9b45680e.mp4

## Support
In the project there is a folder called "config" where the parameter files reside. Therer a a lot of parameters and all of them are optimized for our platfor, you are free to modify any of them. The most important ones are:

- 'max_velocity' and 'min_celocity'
- 'yaw_goal_tolerance' and 'xy_goal_tolerance'
- 'occdist_scale'
- 'sim_granularity'
- 'inflation_radius'
- 'cost_scaling_factor'

The best support that you can get is the wiki of ROS http://wiki.ros.org/Documentation
Anyway here it is my personal email to contact me in case that you need some help sanmasja@gmail.com

## Roadmap
Right now we have two robotic platforms working perfectly using this software. In the future the idea is to improve the movement and times of the robot, cause sometimes it can take a while to calculate where it is exactly in the map. 

Another interesting thing to maybe implement in the future could be moving all this nodes structure to ROS 2 that makes everthing much easier and it could probably improve the efficiency of the platform while navigating.

## Authors and acknowledgment
Jaime Mas Santillán, Francisco Javier Acevedo Rodríguez y Roberto Javier López Sastre.

## License
[MIT](https://choosealicense.com/licenses/mit/)

## Project status
Right now we continue working in the project to improve it.
