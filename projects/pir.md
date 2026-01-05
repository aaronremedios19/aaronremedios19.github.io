---
layout: project
type: project
image: images/PIR3_resized (2).jpeg
title: Pipe Inspection Robot 
permalink: projects/PIR
# All dates must be YYYY-MM-DD format!
date: 2024-08-01
labels:
  - Embedded Systems
  - Esp32
  - PCB design
  - Altium
  - Control Systems
  - PID
  - EKF
  - GitHub
summary: A pipe inspection robot capeable of scaling pipes as small as 50mm dia
---
 <div class="ui small rounded images uniform-project-images">
  <img class="ui image" src="{{ site.baseurl }}/images/PIR1.jpeg">
  <img class="ui image" src="{{ site.baseurl }}/images/PIR2_resized (2).jpeg">
  <img class="ui image" src="{{ site.baseurl }}/images/PIRPCB.png">
  <img class="ui image" src="{{ site.baseurl }}/images/PIR3_resized (2).jpeg">
  

  </div>




At Aventrex Industries Pvt. Ltd., I led the development of a compact in-pipe inspection robot designed to operate within gas pipelines having an internal diameter of only 50 mm. The primary engineering challenge was integrating sensing, computation, and communication hardware within the confined mechanical envelope while maintaining reliability and signal integrity. I designed a 30 mm × 50 mm multilayer PCB incorporating an ESP32 controller, MCP23S17 I/O expander, and BNO055 IMU, together with a Blue Robotics camera for internal visual inspection. Because RF signals attenuate heavily inside metallic pipelines, wireless communication was not feasible, so I evaluated multiple wired communication standards including RS-232, RS-485, optical fibre, and Ethernet. An RJ45-based Ethernet architecture was ultimately selected as it supported simultaneous video and control-data transmission over distances up to 200 meters with high noise immunity.

For localization, I implemented a dead-reckoning framework that fused encoder and IMU feedback via an Extended Kalman Filter. Significant development effort was focused on stabilizing the IMU data, as drift and noise effects were amplified in the constrained pipe environment. I incorporated angle-wrapping and quaternion-based filtering techniques to ensure heading continuity and minimize cumulative error during long-distance traversal. This allowed accurate mapping of defect locations within the pipeline despite the absence of external references such as GPS.

This project was executed as a two-member team, where my colleague focused on the mechanical design and drivetrain layout, while I was responsible for the complete electronics architecture, PCB design, wired communication system, and implementation of the control and sensor-fusion algorithms.





