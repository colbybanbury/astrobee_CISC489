# Astrobee Research CISC 489
##### Steven Kuntz, Colby Banbury, Evan DeAngelis
#


#### Abstract

  - Initial Goal: Adapting NASA Astrobee Robot Software for object detection and collision avoidance
  - Final Goal: Using a genetic algorith to determine position using the camera suite alone
  
  #### Introduction
* NASA intends to send these Astrobee Robots to the ISS for research assistance
* Astrobee Robot Software is a simulation of the ISS and the Astrobee Robot
* Allows Scientists to simulate experiments and commands on Earth before sending them to be executed by the actual Astrobee on the ISS
* 

#### Subjects, Methods, and Analysis
* NASA has the Astrobee Robot Software listed on Github
* The software uses ROS in order to operate the simulation and handle the image collection
* Using genetic algorithms we can provide ros commands to move the simulated astrobee to the desired coordinate location
* 
#### Research and Purpose
https://ntrs.nasa.gov/archive/nasa/casi.ntrs.nasa.gov/20160007769.pdf
* Astrobees used for three scenarios: research, camera, and search
* Allows for autonomous research, monitoring, and location of tools on the ISS

https://www.cc.gatech.edu/faculty/ashwin/papers/er-94-01.pdf
* Genetic algorithms can be used to teach a robots its paths to take for its destination
* good for unsupervised learning 
https://github.com/nasa/astrobee
* Source Code for astrobee software

#### Results
##### Initial Gazebo simulation
![gazebo](https://github.com/colbybanbury/astrobee_CISC489/raw/master/astrobee_gazebo.png)

##### RVIZ Simulation
![reviz](https://github.com/colbybanbury/astrobee_CISC489/raw/master/astrobee_rviz.png)

##### Depth Camera and Area Mapper
![depth](https://github.com/colbybanbury/astrobee_CISC489/raw/master/astrobee_ros_0.3.0.png)

##### Image From Astrobee Camera
![gazebo](https://github.com/colbybanbury/astrobee_CISC489/raw/master/camera_image.jpeg)

##### Astrobee Movement from ROS Commands 
![gazebo](https://github.com/colbybanbury/astrobee_CISC489/raw/master/itsalive0.png)
![gazebo](https://github.com/colbybanbury/astrobee_CISC489/raw/master/itsalive1.png)
![gazebo](https://github.com/colbybanbury/astrobee_CISC489/raw/master/itsalive2.png)





#### Conclusions

#### Direction for further Research
