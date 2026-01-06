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
  <img class="ui image" src="{{ site.baseurl }}/images/R12022.jpeg">
  <img class="ui image" src="{{ site.baseurl }}/images/Hook_2_pcb.jpeg">
  <img class="ui image" src="{{ site.baseurl }}/images/Hool_3_Test_resized_resized.jpeg">
  <img class="ui image" src="{{ site.baseurl }}/images/R2022.jpeg">
</div>

## OverviewABU Robocon 2022 was based on the traditional Indian game Lagori (Seven Stones). The competition required teams to design and operate two coordinated robots that could knock down a stack of Lagori discs and then quickly retrieve, stack, and place them back while competing against an opposing team. The challenge demanded fast movement, precise control, reliable gripping, and smooth coordination under strict time and size limits.

This competition marked my first serious entry into competitive robotics, where I learned the fundamentals of control systems, mechanical design, and hardware integration through hands-on experience.

Robot Strategy and My Role

Our team, Team RAW (SFIT), developed two hitter robots and two seeker robots, each optimized for a specific phase of the game. I played a major role in the mechanical and pneumatic system design, especially for the Lagori pickup and stacking mechanisms.

The hitter robot was responsible for breaking the Lagori stack using a high-speed shooting system.

The seeker robot focused on collecting scattered discs and restacking them accurately.

Lagori Pickup and Stacking Mechanism

The Lagori retrieval robot used a pneumatic gripper system combined with a belt-and-pulley assisted lifting mechanism to pick up multiple discs reliably.

A key challenge was that Lagori discs could land:

Flat on the ground, or

Standing vertically on their curved edge

To handle both cases, we added a compressed-air nozzle that gently knocked vertically standing discs flat, ensuring consistent pickup conditions.

The gripper used variable-pressure pneumatic actuation, allowing it to grip one to five discs securely without damaging them. To protect the discs and improve grip, we added thin foam padding inside the gripper claws, balancing holding force and surface safety.

Pneumatic Control and Electronics Design

The pneumatic system was controlled using solenoid valves, specifically Janatics 5-port, 2-position valves, which regulated airflow to the actuators.

To manage this system cleanly, I designed a dedicated ESP32-based control unit:

Designed a 2-layer PCB in Altium

Reduced wiring complexity and improved reliability

This PCB acted as a child board, communicating with the main PCB using the I²C protocol

The same ESP32-controlled system was also used for the ball pickup pneumatic gripper

This experience introduced me to practical PCB design, signal routing, and electrical system organization in real robots.

Failure, Learning, and Design Philosophy

Although pneumatic systems are powerful and easy to control, we learned a critical lesson:

One small air leak can shut down the entire system.

During the competition, a leak in the plastic air tank tubing rendered the whole pneumatic system unusable at a crucial moment. This failure taught me the importance of:

Robust fittings

Redundancy

Mechanical safety margins

Because of this experience, in later projects I became more cautious with pneumatics and often preferred mechanical or motor-driven solutions unless pneumatics offered a clear advantage.

Hitter Robot and Locomotion

The hitter robot used a roller-based shooting mechanism, where balls were accelerated using motor-driven rollers, assisted by a pneumatic feeding system. Shooting speed and trajectory were refined through mechanical tuning and repeated testing.

Both robots used an X-configuration omni-wheel drive, allowing fast and smooth movement in all directions. To achieve precise control, we implemented PID-based closed-loop locomotion using encoder feedback. This improved motion stability and accuracy, which was essential during alignment for both shooting and stacking.

Outcome and Learning

This project gave me strong hands-on experience in:

Pneumatic system design and control

PID-based locomotion

Multi-robot coordination

Mechanical and electrical system integration

PCB design and structured electrical wiring

Most importantly, it taught me how to convert theoretical concepts into reliable, competition-ready robotic systems, and how small design oversights can have large real-world consequences.
