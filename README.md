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

## Usage

To use this software you must follow the next steps:

1. Open two terminals
2. $ cd ~/

## Support
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
