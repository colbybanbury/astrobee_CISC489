# Instructions for generating image data with Astrobee

Install [the latest version of Astrobee](https://github.com/nasa/astrobee/blob/master/INSTALL.md) according to the instructions on NASA's github. You will need 3 GBs of RAM to compile the software. Astrobee runs best on a native install of Ubuntu 16.04 LTS.

## Running a simution

In every terminal you use during data collection, the environment needs to be built so ROS knows about the Astrobee fight software packages. Run the following command given that the ROS installation folders are in the current directory.

    source freeflyer_build/native/devel/setup.bash

The following command will launch ROS with a single Astrobee robot in the ISS.

    roslaunch astrobee sim.launch dds:=false robot:=sim_pub rviz:=true

## Controlling Astrobee

Astrobee takes movement commands from a movement module which uses teleop to communicate with the simulated hardware. Use the following command to move Astrobee to the location (x,y,z) = (0,0,5) while maintaining the dock cam in the forward direction.

	rosrun mobility teleop -move -pos "0.0 0.0 5.0" -ff

Using [these commands](https://github.com/nasa/astrobee/tree/master/mobility) and general bounds on robot movement, we can generate a series of locations and positions on the ISS which can either be saved to a text file, or fed as input to a python script to annotate images.

## Saving camera data

Astrobee publishes camera data to the `/hw/cam_nav` and `/hw/cam_dock` image topics. See `ros_image_saver.py` for an example of a python script used to save camera data. The script functions by first creating the node, then initializing a subscriber.

	import rospy
	from sensor_msgs.msg import Image
	rospy.init_node('image_listener')
    image_topic = "/hw/cam_nav"
    rospy.Subscriber(image_topic, Image, image_callback)

The `image_callback` function is called every time the Subscriber receives an image topic. The following function saves the message to a jpeg file using `CvBridge`.

	from cv_bridge import CvBridge, CvBridgeError
	import cv2
	bridge = CvBridge()

	def image_callback(msg):
	    print("Received an image!")
	    try:
	        # ROS byte array image to cv2
	        cv2_img = bridge.imgmsg_to_cv2(msg, "passthrough")
	    except CvBridgeError, e:
	        print(e)
	    else:
	        # cv2 to jpeg
	        cv2.imwrite('camera_image.jpeg', cv2_img)

Alternatively, this function can save the images as byte arrays and annotate the files with location and position stamps, so long as the relevant data is passed into the script upon running it. An image created with the above python code can be found below.

![/hw/cam_nav](https://github.com/colbybanbury/astrobee_CISC489/raw/master/camera_image.png)