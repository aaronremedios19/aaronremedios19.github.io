---
layout: project
type: project
title: ABU ROBOCON 2022
image: images/R2022.jpeg
permalink: /projects/robocon/
date: 2022-03-01
labels:
  - Robotics
  - ESP32
  - Embedded C
  - PCB Design
  - Control Systems
summary: Design and development of competition robots for ABU ROBOCON 2022.
---

<div class="ui small rounded images uniform-project-images">
  <img class="ui image" src="{{ site.baseurl }}/images/Hook_!_open.jpeg">
  <img class="ui image" src="{{ site.baseurl }}/images/Hook_2_pcb.jpeg">
  <img class="ui image" src="{{ site.baseurl }}/images/Hool_3_Test_resized_resized.jpeg">
  <img class="ui image" src="{{ site.baseurl }}/images/hookab.jpeg">
</div>

## Overview
ABU Robocon 2022 revolved around the traditional Indian game Lagori (Seven Stones), where teams were required to design and deploy two coordinated autonomous robots to knock down a stack of Lagori discs and then accurately retrieve, stack, and place them back while competing against an opposing team. The challenge demanded precise locomotion, fast actuation, robust manipulation, and seamless coordination between multiple robots under strict time and space constraints.

Our team, Team RAW (SFIT), developed two seeker robots and two hitter robots, each optimized for a specific phase of the game. I played a major role in the mechanical and pneumatic system design, particularly focusing on the Lagori pickup and stacking mechanisms. One robot was dedicated to breaking the Lagori stack using a high-speed shooting mechanism, while the second robot was responsible for picking up scattered Lagori discs and restacking them accurately.

The Lagori retrieval robot employed a pneumatic gripper system combined with a belt-and-pulley assisted mechanism to reliably grasp and lift multiple discs. Since Lagori discs could land either flat or on their curved edge after being knocked down, the system was designed to handle both orientations. A compressed-air nozzle was used to topple vertically standing discs, ensuring consistent pickup conditions. The gripper itself utilized variable-pressure pneumatic actuation, allowing it to adaptively grip between one to five discs without damaging them. Thin foam padding was integrated inside the gripper claws to balance grip force and prevent surface wear on the discs.

In parallel, the striking robot used a roller-based shooting mechanism, where Lagori-breaking balls were accelerated using motor-driven rollers combined with a pneumatic feeding system. Ball velocity and trajectory were carefully tuned through mechanical design and empirical testing. Both robots employed an omni-wheel drive in an X-configuration, enabling fast omnidirectional motion across the field. Closed-loop PID control, based on encoder feedback, was implemented to achieve smooth, stable, and accurate locomotion, which was critical during precise alignment for shooting and stacking tasks.

This project gave me deep hands-on experience in pneumatic system design, multi-robot coordination, PID-controlled locomotion, and mechanism optimization under competition constraints. It also strengthened my ability to translate theoretical mechanical and control concepts into reliable, competition-grade robotic systems operating in a dynamic, adversarial environment.
