---
layout: project
type: project
image: images/Hook_4_product.jpeg
title: ISRO IRoC-U 2024

permalink: /projects/ISRO_IRoC

# All dates must be YYYY-MM-DD format!
date: 2021-06-06
labels:
  - Controls
  - Esp32
  - Embedded C
  - Pcb Design
  - Stm32
summary: Electronics Subsystem & Access Control Development – Hook EV Systems
---



<div class="ui small rounded images uniform-project-images">
  <img class="ui image" src="/images/Hook_!_open.jpeg">
  <img class="ui image" src="/images/Hook_2_pcb.jpeg">
  <img class="ui image" src="/images/Hool_3_Test_resized_resized.jpeg">
  <img class="ui image" src="/images/hookab.jpeg">
  
</div>


I led a 10-member multidisciplinary engineering team in the design, integration, and validation of a fully autonomous robotic rover, focusing on real-world system engineering across mechanical design, embedded electronics, perception, control, and ROS2-based software architecture. The rover employed a six-wheel rocker-bogie suspension driven by high-torque motors with encoder feedback, enabling synchronized wheel velocity control and stable traversal over uneven terrain.

The perception stack integrated a 360° YD LiDAR, IMU, wheel encoders, and an Intel RealSense RGB-D camera, all interfaced through ROS2 on a Raspberry Pi 5, with low-level motor and actuator control handled by microcontroller-based subsystems. For perception and object identification, we implemented image-processing pipelines using RGB and HSV color-space segmentation to detect and localize test-tube payloads and obstacles, combining 2D visual cues with depth measurements from the RGB-D camera. Closed-loop obstacle avoidance was achieved by fusing LiDAR range data with depth camera information, allowing continuous regulation of linear and angular velocities based on proximity feedback and real-time trajectory adjustment. The navigation and control architecture was built around ROS2 and Nav2, incorporating probabilistic localization modules, local planning, rule-based recovery behaviors (e.g., backing up and replanning when blocked), and safety-critical mechanisms such as a hardware kill switch and emergency override logic.

Beyond team leadership, my primary technical responsibility was the integration of the locomotion system with a 6-DOF robotic manipulator, ensuring coordinated motion between the mobile base and the arm. The manipulator was driven by high-torque (≈12 kg-cm) stepper motors, with the Raspberry Pi 5 acting as the central planner and coordinator, and an STM32 microcontroller handling real-time stepper driver control for precise joint actuation. This required designing reliable communication and control interfaces between high-level ROS motion commands and low-level motor drivers, managing timing, synchronization, and safety constraints.









