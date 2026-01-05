---
layout: project
type: project
title: ABU ROBOCON 2023
image: images/R1.jpeg
permalink: /projects/robocon2023
date: 2023-03-01
labels:
  - Robotics
  - ESP32
  - Embedded C
  - PCB Design
  - Control Systems
summary: Design and development of competition robots for ABU ROBOCON 2023.
---

<div class="ui small rounded images uniform-project-images">
  <img class="ui image" src="{{ site.baseurl }}/images/robocon20233.jpeg">
  <img class="ui image" src="{{ site.baseurl }}/images/robocon20234.jpeg">
  <img class="ui image" src="{{ site.baseurl }}/images/Robocon2023.jpeg">
  <img class="ui image" src="{{ site.baseurl }}/images/robocon20232.jpeg">
</div>

## Overview

ABU ROBOCON 2023 was a continuation of our competitive robotics efforts, focusing on high-speed coordination, robust embedded control, and reliable mechanical actuation under match conditions.
ABU Robocon 2023 was based on the Angkor Wat theme, where teams were required to design robotic systems capable of collecting rubber rings and accurately launching them onto vertical poles of varying heights, each pole carrying different point values. The game emphasized precision, speed, coordinated multi-robot operation, and repeatable mechanical performance, all under strict field and rule constraints.

To address these requirements, our team developed two coordinated robots, each optimized for a specific role in the gameplay. My primary focus was on the smaller, highly maneuverable robot, while also contributing to the overall system integration and control strategy.

Primary Robot – Ring Collection and Precision Shooting

The primary robot, approximately 500 × 500 mm in footprint, was designed to operate close to the scoring poles and perform ring pickup, transportation, and precision shooting. One of the key challenges was enabling the robot to traverse stepped terrain on the field. To achieve this, we implemented a ball-screw-based vertical actuation mechanism, allowing the robot to climb steps reliably while maintaining stability and alignment.

For ring collection, we designed a thin aluminum sheet-based pickup mechanism that could slide underneath a stacked set of rubber rings. This mechanism allowed the robot to lift and transport up to five rings simultaneously, significantly reducing cycle time while maintaining consistent ring orientation. The collected rings were then transferred onto a shooting plate assembly.

The shooting mechanism was based on a hybrid spring–electromagnet system. A lead-screw-driven actuator was used to compress the spring to a calibrated length based on the required shooting distance. Once the robot reached a predefined position relative to the target pole, the electromagnet disengaged, releasing the spring and launching the rings with controlled force and repeatable trajectory. This design allowed us to finely tune the launch energy for poles of different heights without requiring complex motor-driven shooting systems.

Given the mass of the robot and the precision required during approach and shooting, I implemented PID-based closed-loop control for locomotion using encoder feedback. This significantly improved motion smoothness, reduced oscillations during acceleration and braking, and ensured consistent stopping distances, which was critical for reliable scoring.

Secondary Robot – Long-Range Ring Launching

The second robot was larger in size (approximately 1000 × 1000 mm) and was designed specifically for long-range ring launching. Due to competition rules, this robot was not allowed to traverse the entire field, so its role was to launch rings over longer distances from a fixed or limited operating zone.

For this robot, we developed a clay-pigeon-thrower-inspired launching mechanism. The system used a spring-based energy storage unit combined with a one-way bearing mechanism, similar in principle to a bicycle freewheel. This allowed the spring to be tensioned efficiently in one rotational direction while preventing reverse motion, ensuring safe and repeatable energy buildup. Upon release, the stored energy was transferred to the throwing arm, enabling high-energy, long-distance ring launches toward scoring poles.

Outcome and Learning

Through ABU Robocon 2023, I gained extensive hands-on experience in mechanism design, spring-based energy storage systems, precision actuation, PID-controlled locomotion, and multi-robot task allocation. The project strengthened my ability to design robust electromechanical systems that operate reliably under competitive constraints, tight timelines, and real-world variability.
