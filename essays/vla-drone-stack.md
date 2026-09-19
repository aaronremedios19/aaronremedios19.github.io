---
layout: essay
type: essay
title: Autonomous Inspection Drone — Tech Stack
# All dates must be YYYY-MM-DD format!
date: 2026-09-01
labels:
  - PX4
  - ROS2
  - Jetson Orin
  - LiDAR
  - VLA
  - Python
---

A quick rundown of the hardware and software I'm using to build an autonomous inspection drone powered by a vision-language-action (VLA) model.

**Airframe & Flight Controller**
- Holybro X500 V2 devkit (frame, GPS, RC receiver)
- Pixhawk 6C flight controller running PX4

**Companion Computer**
- NVIDIA Jetson Orin, for onboard autonomy and VLA inference

**Sensors**
- LiDAR, for SLAM-based localization (FAST-LIO2)
- ARK Flow optical-flow + rangefinder module (PAW3902-based), connected via DroneCAN/CAN bus

**Middleware & Software**
- ROS 2, bridged to PX4 over a dedicated UART link using PX4's native uXRCE-DDS client
- PX4 EKF2 state estimator, fused with LiDAR odometry and optical-flow/rangefinder data
- Python, for bridge nodes and data processing
- QGroundControl, for configuration and ground-station monitoring

**Planned**
- A vision-language-action model running on the Orin, consuming live sensor/state data to make autonomous inspection decisions
