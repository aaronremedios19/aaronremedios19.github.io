---
layout: project
type: project
title: IIT Bombay e-Yantra Robotics Competition (eYRC) 2023–24 — Rank 1 
image: images/EY1.jpeg
permalink: /projects/eyantra-eyrc/
date: 2024-04-01
labels:
  - Robotics
  - ROS2
  - Nav2
  - MoveIt2
  - OpenCV
summary: Built an autonomous warehouse logistics system integrating a mobile robot and UR5 arm using ROS2, Nav2, and MoveIt2.
---

<div class="ui small rounded images uniform-project-images">
  <img class="ui image" src="{{ site.baseurl }}/images/EY1.jpeg">
</div>
During the e-Yantra Robotics Competition (Cosmo Logistics Theme), I worked on an autonomous warehouse logistics system that integrated a UR5 robotic arm with a Goat Robotics Autonomous Guided Vehicle (AGV). The objective of the challenge was to autonomously identify storage racks, pull them into a designated manipulation zone, detect boxes using visual markers, and accurately pick and place the boxes onto target racks.

The system was developed entirely in ROS 2, with simulation and validation carried out in Gazebo. For navigation and localization, the AGV used AMCL-based pose estimation combined with a 2D LiDAR, which was used to generate a local occupancy map and enable reliable navigation within the warehouse environment. The robot was required to approach racks with high positional accuracy, as any misalignment would directly affect the arm’s ability to pick boxes.

A key part of the task involved physically attaching to a rack using an electromagnet, pulling the rack toward the manipulation zone, and ensuring that the rack remained aligned with the robot throughout the motion. My primary responsibility was the development of the locomotion and rack-pulling control algorithm for the AGV. I implemented a PID-based control strategy to regulate the robot’s motion while towing the rack, ensuring smooth and stable movement.

To maintain proper alignment during rack pulling, I used ultrasonic sensors mounted on the front of the AGV. These sensors continuously measured the distance between the robot and the rack. The control logic enforced a tight distance band: if the robot began turning beyond a specified angular threshold or if distance asymmetry was detected, corrective action was taken. In extreme cases, the electromagnet was partially disengaged to prevent mechanical stress or misalignment. This sensor-based feedback loop was critical for preventing rack skewing and ensuring consistent positioning before manipulation.

Once the rack was positioned correctly, the UR5 robotic arm was controlled using MoveIt for motion planning and execution. An Intel RealSense depth camera was used in conjunction with OpenCV-based ArUco marker detection to identify box poses in real time. The detected poses were transformed into the robot’s coordinate frame, allowing the arm to accurately plan grasp trajectories and perform reliable pick-and-place operations.

This project gave me hands-on experience in multi-robot system integration, ROS 2 navigation and manipulation, PID-based locomotion control, and sensor-driven feedback loops for physical interaction tasks. It also strengthened my understanding of coordinating mobile manipulation systems where navigation accuracy, perception, and mechanical constraints are tightly coupled.
