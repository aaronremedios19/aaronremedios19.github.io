---
layout: project
type: project
title: IIT Bombay e-Yantra Robotics Competition (eYRC) 2023–24 — Rank 1 hiiii
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
  <!-- Add more eYRC images here (recommended, not PIR images) -->
</div>

## Overview

In the IIT Bombay **e-Yantra Robotics Competition (eYRC) 2023–24**, we developed an autonomous logistics workflow that combined **mobile navigation** and **robotic manipulation** to complete task objectives under competition constraints.

## What We Built

- A navigation stack for robust localization and path planning using **ROS2 + Nav2**
- A manipulation pipeline for pick-and-place using **MoveIt2** (UR5)
- Vision-based localization for objects using **OpenCV** (e.g., ArUco markers / object cues)
- System integration across sensing, planning, and actuation for repeatable task execution

## My Contribution

- Owned key parts of system integration and debugging across autonomy + manipulation
- Tuned navigation behavior for reliability under dynamic competition conditions
- Contributed to perception/manipulation pipeline to improve success rate and cycle time
