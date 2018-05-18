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
Over the course of this project, we had refine our end goal a lot. Initially we expected to be working with object detection of the astrobee and navigation of the robot. We underestimated the difficulty of deciphering software written by an outside party to be able to use as we pleased. Between set up and getting the data we needed, time was not in our favor to tackle it all. By the end of this project we accomplished:
* Setting up and running the simulation software
* Accessing the saved images from the simulator
* Finding the location data that corresponds with the image received 

#### Direction for further Research

##### Genetic algorithms steps and how we would implement them
![GA](https://s3-ap-south-1.amazonaws.com/av-blog-media/wp-content/uploads/2017/07/22154007/steps.png)
1. Initialization
* Dataset:
> * Create an image dataset and label each image with the corrispoinding location data from simulation
* Initial Population of detection algorithms:  
> * Create a population of different, rudimentary location detection algorithms based on existing image recognition software
> * This will likely be the hardest stage as this part of Genetic algorithms does not easily work with image detection
2. Fitness Function
* Define what is more fit:
> * the closer the guess is to the actual coordinates the more fit the algorithm
3. Selection
* Weighted Selection Criteria:
> * Use the fitness from coordinate data to increase the chance of reproduction
* Source of randomness:
> * Roulette Wheel Selection
> * Fitness increases the chance but reproduction is still ultimately rando
![roulette](https://s3-ap-south-1.amazonaws.com/av-blog-media/wp-content/uploads/2017/07/22171149/roulette.png)
4. Crossover
* Mix the traits of the parents
> * Could increase ammount of crossover based on relative fitness
5. Mutation
* Add in random weighting
> * change the weighting of a certain aspect the image detection in some of the offspring
