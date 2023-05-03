---
layout: page
title: "Blog"

---

This project aims at understanding the creation, experimentation and deployment of Convolutional 
Neural Networks based YOLO algorithm for mask detection to a turtle bot 4. The application we will
be using this for is to detect the presence of a face mask on a person or not. 

The project we have in mind is as follows: 
The main implementation we are targeting is face mask detection. We plan on using the YOLO initially for training. Apart from YOLO, we also plan on collecting data using the OAK-D camera. The dataset we plan on creating will have images that have a person with a mask and images of a person without mask and these images are labeled accordingly. 
The robot moves in a room (movement maybe manual or autonomous) for the detection of a face mask presence. For autonomous movement, we need to implement SLAM. But implementing SLAM and face mask detection might be challenging given the time frame. So, any help in implementing SLAM completely would be much appreciated. If we are not able to implement SLAM, we will use manual movement of the Turtlebot.
In a nutshell, our project implements detection of faces and preferentially moves towards those faces that do not have a face mask (Obstacle avoidance is dependent on SLAM implementation). Once near the person with no face mask, the robot stops and displays a message somewhere along the lines of: “ Please use a face mask/ face covering.” Ideally, the robot should have a pack of face masks available on board, so that people who need it can take the masks from there.
We plan on mastering data collection and data communication through ROS nodes. We also plan to process the data received and implement it in real time. We plan on training the CNN model in the host machine and then deploying it to the turtlebot. Essentially, we will be transferring the weights learnt to the program being used by the turtle bot. Apart from implementing this transfer learning, we also plan on getting real time data so that the robot drives towards the person(goal) with no mask using ROS communication. 
On a whole, we plan on using Data Collection , Communication, robot movement, Image Data Processing with YOLO and SLAM if possible.

<span style="color:green;font-weight:700;font-size:30px">
    Milestones:
</span>

<span style="color:green;font-weight:700;font-size:20px">
    Week 15
</span>
We hope to collect the data required containing the necessary images of people with and without face masks and label them accordingly. We also plan to try to get a CNN model trained using YOLO and test with some part of the data collected as well which is not used for training. Ideally we hope to complete the entire process of training the model on the host machine and getting the weights so that they are ready for deployment.
<span style="color:green;font-weight:700;font-size:20px">
   Week 16:
</span>
In the final week, We’ll work on implementing the model on real time data by using  ROS publisher and subscriber nodes up by the turtle bot. The model that we learnt earlier will be deployed to the turtle bot.We try to deal with any misclassification or accuracy issues due to any training constraints. If we are successfully able to do real time detection without any issues we may try a basic level of autonomous driving of the bot implementing obstacle avoidance. 
For implementing the deployment, we need to understand how darknet_ros helps to implement neural networks over ROS. Darknet provides a ROS interface for running the YOLO detection as a ROS node.
Sensor Integration:
We are primarily interested in working with the OAK-D camera because we feel we have worked on it throughout the semester and will be comfortable with working more on the camera. But we have only worked with blob detection in the past. Here we try to implement face detection using data being collected from color/preview/image and train our models.
The data obtained from the OAK-D camera will be used initially for training and testing the CNN. We plan on making a 80-20 split of the data collected.This ratio is tentatively dependent upon how much we’ll be able to collect and train on the algorithm. 
Once we achieve a decent accuracy on the testing set, we will deploy the model learnt for real time detection.If there are any latency issues or some other unexpected issues, we’ll collect more data and demonstrate on fresh unused dataset.


<span style="color:green;font-weight:700;font-size:20px">
    Final Demonstration:
</span>
<span style="color:green;font-weight:700;font-size:20px">
   Resources needed:
</span>
Idealab network and your Turtlebot. We’ll bring masks required for the detection.
Classroom Setup requirements:  We need a fairly decent amount of space in the classroom for the movement of the bot. Preferably move the table and chairs a bit. 
We plan to utilize the classroom space and would require the help of the other students as well. Some students would need to wear a face mask and some need not for real time detection.
The biggest issue we hope to encounter during the demonstration is that the camera is so low. This would require people to bend down in order for their face to be seen. This is dependent on how we train the model and extract the features of near or far standing people.
Testing and evaluation:
We use camera data over the turtlebot and detect the faces with masks and without masks in real time using trained CNN models. If we are able to implement SLAM, it’ll automatically move towards the faces with no masks, otherwise we’ll  move the bot using a teleop node and it just detects. 
Exception: If the issue persists in real time then we get a fresh dataset for the offline detection.


<span style="color:green;font-weight:700;font-size:20px">
    Preparation Needs:
</span>
We need to check how to capture direct images instead of saving shots from video streaming through an OAK-D camera.
We need to know how we can implement YOLO in ROS with understanding of the math behind the algorithm.
We need to know how we can transfer the weights learnt (ONNX file) from the host machine to the model we deploy for real time detection. From various documentation, we understand that there is a package called darknet_ros package. Further, we also need to know how to create the launch file needed for this.
We need to check the computation time over the real time network.
If possible, we would like to know the implementation of SLAM. Ideally, we need just the code for implementation(basic level) so that we can directly deploy it as it is not our primary project. This way, we can make the bot completely autonomous.


<span style="color:green;font-weight:700;font-size:20px">
    Topics to be covered in class:
</span>
Basic implementation of SLAM on robot detecting the surrounding environment and creating maps.  
Live example of creating maps using LIDAR data and describing constraints of various LIDARs available currently.
Export the model learnt in CNN and get weights learnt using the ONNX file.
Working example of darknet_ros would be much appreciated. Including the creation of a darknet_ros specific launch file.
Different applications of rosbags by data learnt from different sensors not simultaneously at different frequencies and then overlapping all the bags as a single rosbag and using it.

<span style="color:green;font-weight:700;font-size:20px">
    Impacts:
</span>
The project we are proposing ideally would need the usage of collection of camera data, processing to CNN implementation, driving robots by communication over ROS and LIDAR data and IMU for object detection, SLAM usage as well.And if successful, this model can be deployed on a much larger scale, even outdoors in which case we can even use GPS.  We believe that using multiple sensors for different purposes simultaneously would be something very interesting to work on. 
Not only are we learning a map of the environment, we can also detect certain features (colors or shapes or edges detection) and thus their location as well. There are a number of applications in which such a combination would be very useful: for example we can adapt this for surveying or surveillance as well. 
We chose a project which involves mastery of what we learnt in the course and touching on some other topics which may be yet to learn.We are trying to  solve the problems which need to be attended in the future course topics and making better paths for the course development.
Learning usage of LIDAR would be a great benefit. Like the exercises we practiced for camera, it would be interesting to work equally on LIDAR as well.It’d be really encouraging to learn LIDARs and some other event cameras as well for better detection without latency and ambiguity with respect to distance of the object from the camera.
As some of the things are not discussed yet in the course, the overcoming of current drawbacks using different hardware products to learn new things gives some future scope.
