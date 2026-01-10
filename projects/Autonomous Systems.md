---
layout: project
type: project
image: images/AS2.jpeg
title: Autonomous Systems

permalink: /projects/Autonomous Systems
# All dates must be YYYY-MM-DD format!
date: 2021-06-06
labels:
  - Controls
  - Esp32
  - Embedded C
  - Pcb Design
  - Stm32
summary: Built a fully autonomous robot capable of mapping unknown environments, navigating safely, and detecting objects without human control.
---



<div class="ui small rounded images uniform-project-images">
  <img class="ui image" src="/images/AS2.jpeg">
  <img class="ui image" src="/images/Hook_2_pcb.jpeg">
  <img class="ui image" src="/images/Hool_3_Test_resized_resized.jpeg">
  <img class="ui image" src="/images/hookab.jpeg">
  
</div>



Autonomous Systems (ME597, Purdue University) — TurtleBot4 (ROS2)

Autonomous Systems at Purdue University, where I developed and deployed autonomy software on a TurtleBot4 using ROS2 and Gazebo, and validated key components on real hardware. The course was organized into progressive modules covering ROS fundamentals, control, navigation, perception, and a final integrated autonomy project. A major focus throughout was addressing the sim-to-real gap, where algorithms that worked in simulation required improved feedback control, safety logic, and robustness to perform reliably on the physical robot.

1 – ROS 2 Basics

In this module, I worked with core ROS2 concepts, including nodes, topics, publishers/subscribers, and message passing. I developed basic ROS nodes to interface with TurtleBot sensors and actuators, visualized data in RViz, and established a reliable software pipeline for commanding motion and receiving sensor feedback. This module built familiarity with ROS2 architecture and debugging workflows.

2 – Kinematics & Control

This module focused on closed-loop motion control. I implemented PID-based control to regulate robot motion using LiDAR feedback, including stopping the robot at a target distance from an obstacle with minimal oscillation. This work highlighted the importance of tuning control gains and handling sensor noise, especially when transitioning from simulation to real hardware.

3 – Navigation

In the navigation module, I implemented global path planning using A* and Dijkstra on occupancy grids to move the robot from a start pose to a goal pose. After validating the planners in Gazebo, the same algorithms were deployed on the real robot. To address instability and oscillations observed on hardware, I implemented pure-pursuit path tracking with real-time LiDAR feedback, allowing the robot to move smoothly from waypoint to waypoint and handle real-world uncertainties such as wheel slip and imperfect localization. I also used AMCL pose(Particle filter) for position estimation.

4 – Perception

This module focused on sensor-based perception and object interaction. I implemented camera-based color detection using HSV color-space segmentation, which is more robust than RGB under changing lighting conditions because hue and saturation are decoupled from brightness.
To safely approach detected objects, I implemented closed-loop control using Model Predictive Control (MPC) to regulate robot velocity based on depth and LiDAR measurements, allowing the robot to stop precisely at a fixed stand-off distance before the colored object. MPC was used to anticipate stopping behavior while respecting velocity constraints, while PID provided simpler feedback stabilization. Detected object positions were published via ROS topics for downstream navigation and decision-making.

Final Project — Integrated Autonomous Robot

(ROS2, TurtleBot3, Gazebo)

The final project was made up of 3 tasks combined mapping, navigation, and object detection into a single fully autonomous system operating in a random, unknown environment. The robot explored the space on its own, built a map while moving (SLAM, occupancy grid), avoided obstacles, and searched for colored objects. It planned safe paths toward unexplored areas using global path planning (A*), slowed down in narrow passages to improve map quality and localization stability, and automatically recovered from failure cases using reverse-and-replan behaviors. During exploration, the robot also detected colored balls using camera-based perception (HSV vision) and published their estimated locations using ROS topics.

Task 1 — Autonomous Mapping

(Frontier Exploration, A*, Pure Pursuit)

In Task 1, the robot’s goal was to map an unknown environment with maximum coverage within a limited time. I implemented an A*-based frontier exploration strategy where the robot identified unexplored regions in the occupancy grid and navigated toward them intelligently. To improve safety and robustness, I added obstacle inflation, a 0.3 m safety margin, and stuck detection with automatic reverse and replanning. The robot also reduced speed in narrow spaces to prevent mapping gaps. Pure-pursuit path tracking was used to ensure smooth motion and reduce zig-zag behavior that can degrade SLAM performance.

Task 2 — Navigation with Static Obstacles

(Global Planning, Path Smoothing, Reactive Safety)

For Task 2, the robot navigated to multiple goal locations using a previously generated map while avoiding unmapped static obstacles. I used A* global planning on a grid map and applied rubber-band–style path smoothing to convert grid-based paths into straighter, more drivable trajectories. A reactive obstacle-avoidance check using LiDAR data ensured the robot reversed when it approached obstacles too closely, enabling collision-free navigation even in partially unknown conditions.

Bonus — Dynamic Replanning

(RRT*, Local Replanning)

As a bonus, I added RRT* as a local replanning method. When an obstacle appeared along the planned path, the robot temporarily switched to RRT* to find an alternative route and then continued toward the goal. This improved robustness in dynamic scenarios while maintaining safety.

Task 3 — Search and Localize Colored Objects

(Computer Vision, HSV Segmentation, Sensor Fusion)

In Task 3, the robot searched for colored balls (red, blue, green) while continuing to navigate safely. At predefined waypoints, the robot entered a detection mode and used camera and LiDAR data for object localization. I implemented HSV color-space segmentation, which is more robust than RGB under changing lighting conditions. Once detected, the robot approached the object in a controlled manner and published its estimated (x, y) position to dedicated ROS topics (/red_pos, /blue_pos, /green_pos).



I learned how to design complete autonomous robot systems by integrating mapping, navigation, perception, and safety into a single working pipeline. I gained practical experience handling real-world challenges such as sensor noise, localization drift, and the sim-to-real gap using feedback control and recovery behaviors. I implemented global and local planning methods, including A*, frontier exploration, path smoothing, and dynamic replanning, to achieve reliable navigation. I also developed closed-loop control strategies using PID and MPC with LiDAR and depth data for smooth and safe motion. Overall, the project taught me how to turn individual algorithms into dependable, real-world autonomous robot behavior.





