# Home-Service-Robot
This project is a part of the Udacity Robotics Software engineer nanodegree

https://user-images.githubusercontent.com/92162018/204540114-0a0f4f7b-1716-4ec9-9021-a87ab6ba539b.mp4

## Mapping & Localization

For localization we used the AMCL package which utilizes Adaptive Monte Carlo Localization (AMCL) which uses a particle filter to track the pose of a robot against a known map. 

For mapping we used RTAB-Map (Real-Time Appearance-Based Mapping), a RGB-D SLAM approach based on a global loop closure detector with real-time constraints. This package can be used to generate a 3D point clouds of the environment and/or to create a 2D occupancy grid map for navigation.

We also used the ROS Teleop package in conjuction with RTAB-Map to help create the map which the AMCL package could then use for localization.
Teleop was used to control the robot and navigate it around our enviornment so that it can map out the environment using the RTAB-Map package.

## Navigation

For navigation we used the ROS navigation stack which creates a path for the robot based on Dijkstra's algorithm which is a variant of the Uniform Cost Search algorithm, which creates a path to the goal position while avoiding obstacles on the path.

The code for sending a goal to the robot is added to the pick_objects.cpp.

The first goal is our desired pickup position and the second goal is our desired drop off position. The robot travels to the desired pickup zone, displays a message that it reached its destination, waits 5 seconds, travels to the desired drop off zone, and displays a message that it has reached the drop off zone. 

## Additional info
Add_markers package was used to show the green cube which represents a package which the robot is supposed to pick up and drop off. Add_markers shows the pick up marker until the robot reaches its position which add_markers node knows because it receives information from the pick_objects node when the robot reaches a certain position, after the robot picks up the package it navigates to the drop off position and once the drop off position is reached add_markers node shows the second marker at the drop off position.




