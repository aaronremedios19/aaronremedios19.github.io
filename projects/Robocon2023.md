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
  <img class="ui image" src="{{ site.baseurl }}/images/R2.jpeg">
  <img class="ui image" src="{{ site.baseurl }}/images/R3.jpeg">
  <img class="ui image" src="{{ site.baseurl }}/images/Robocon2023.jpeg">
  <img class="ui image" src="{{ site.baseurl }}/images/R1.jpeg">
</div>

## Overview


ABU Robocon 2023 was based on the Angkor Wat theme, where teams were required to design robotic systems capable of collecting rubber rings and accurately launching them onto vertical poles of varying heights, each pole carrying different point values. The game emphasized precision, speed, coordinated multi-robot operation, and repeatable mechanical performance, all under strict field and rule constraints.

To address these requirements, our team developed two coordinated robots, each optimized for a specific role in the gameplay. My primary focus was on the smaller, highly maneuverable robot, while also contributing to the overall system integration and control strategy.

Primary Robot – Ring Collection and Precision Shooting

The primary robot, with a compact footprint of about 500 × 500 mm, was designed to operate close to the scoring poles. Its main tasks were picking up rings, carrying them, and shooting them accurately into the target.



One of the biggest challenges was making the robot climb stepped terrain without losing balance. To solve this, we designed a vertical lifting system using a ball screw. This mechanism allowed the robot to lift its body smoothly and stay stable while climbing.

Once the robot reached the height of the step, the locomotion wheels were activated, which pulled the robot forward and onto the step safely.



To reduce time wasted in collecting rings one by one, we designed a thin aluminum sheet pickup mechanism, inspired by a forklift. This sheet could slide underneath a stack of rubber rings and lift up to five rings at once, keeping them neatly aligned.

The rings were then moved toward the shooting area using a simple but effective pulley system made from elastic bands. These elastic bands continuously rotated and gently pulled each ring forward until it reached the shooting position.

The pickup plate itself was connected to a lead screw, allowing it to move up and down. Whenever we wanted to feed a ring into the shooter, we simply raised the plate until it touched the rotating elastic bands, which then guided the ring forward.

This approach may seem longer compared to a direct path, but it solved a major constraint:

The robot’s starting size was limited to 500 × 500 mm,

During gameplay, expansion up to 600 × 600 mm was allowed.

We used this rule cleverly. The pickup plate folded out only during the game, allowing us to collect multiple rings instead of just one. This simple idea gave us a clear advantage during play.



The shooting system used a combination of a spring and an electromagnet. A lead screw compressed the spring to different lengths depending on how far the robot was from the target pole.

Once the robot reached the correct position, the electromagnet released the spring, launching the ring with a controlled and repeatable force. This allowed us to adjust shooting power for different pole heights without using complex motor-driven shooters.

Smooth and precise movement

Because the robot was heavy and needed precise positioning before shooting, I implemented PID-based closed-loop control using wheel encoders. This made the robot’s movement smoother, reduced jerks while stopping, and ensured it stopped at the same distance every time—critical for consistent scoring.

Secondary Robot – Long-Range Ring Launching

The secondary robot was much larger, approximately 1000 × 1000 mm, and was designed for long-range ring launching. Competition rules limited where this robot could move, so its role was to shoot rings from a fixed or restricted area.


For this robot, we built a mechanism inspired by a clay pigeon thrower. It used a spring to store energy and a one-way bearing system, similar to a bicycle’s freewheel.

This design allowed the spring to be wound in one direction while preventing it from slipping backward. Once released, the stored energy powered a throwing arm that could launch rings over long distances with good repeatability.

The ring pickup system on this robot was similar to the one used on the primary robot.

Control and Communication

Both robots were manually controlled using PS4 controllers. We initially tested ESP32-to-ESP32 Wi-Fi communication, but it introduced noticeable lag. To solve this, we directly paired the PS4 controllers to the ESP32 using Bluetooth Low Energy (BLE).

By using the controller’s MAC address, we achieved a fast and reliable connection. The ESP32 acted as the main controller (the “brain”) for both robots, ensuring responsive and smooth operation during the match.

Outcome and Learning

Through ABU Robocon 2023, I gained strong hands-on experience in designing and building real robotic systems under strict size, weight, and performance constraints.

I developed a practical understanding of spring design and calculations, learning how to select and tune springs for controlled energy storage and repeatable motion. I also applied basic kinematics and projectile motion to predict and fine-tune ring trajectories for accurate shooting at different distances.

On the control side, I learned how to implement PID-based motion control, using encoder feedback to improve stability, smoothness, and stopping accuracy of heavy robots. This experience helped me understand how theoretical control concepts translate into real-world behavior.

I also worked with multiple communication protocols, comparing wireless options such as Wi-Fi and Bluetooth, and understanding their trade-offs in terms of latency, reliability, and control responsiveness.

In addition, I gained exposure to material selection, choosing components based on strength, weight, and manufacturability, as well as pneumatic systems for actuation. I was involved in electrical control unit design, including motor drivers, power distribution, and system integration, which gave me a holistic view of how mechanical, electrical, and software systems come together in a working robot.
