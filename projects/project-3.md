---
layout: project
type: project
image: images/cotton-square.png
title: Pipe Inspection Robot 
permalink: projects/PIR
# All dates must be YYYY-MM-DD format!
date: 2014-04-12
labels:
  - Embedded Systems
  - Esp32
  - PCB design
  - Altium
  - Control Systems
  - PID
  - EKF
  - GitHub
summary: A text adventure game I developed for ICS 313.
---

<img class="ui image" src="{{ site.baseurl }}/images/cotton-header.png">

At Aventrex Industries Pvt. Ltd., I led the development of a compact in-pipe inspection robot designed to operate within gas pipelines having an internal diameter of only 50 mm. The primary engineering challenge was integrating sensing, computation, and communication hardware within the confined mechanical envelope while maintaining reliability and signal integrity. I designed a 30 mm × 50 mm multilayer PCB incorporating an ESP32 controller, MCP23S17 I/O expander, and BNO055 IMU, together with a Blue Robotics camera for internal visual inspection. Because RF signals attenuate heavily inside metallic pipelines, wireless communication was not feasible, so I evaluated multiple wired communication standards including RS-232, RS-485, optical fibre, and Ethernet. An RJ45-based Ethernet architecture was ultimately selected as it supported simultaneous video and control-data transmission over distances up to 200 meters with high noise immunity.

For localization, I implemented a dead-reckoning framework that fused encoder and IMU feedback via an Extended Kalman Filter. Significant development effort was focused on stabilizing the IMU data, as drift and noise effects were amplified in the constrained pipe environment. I incorporated angle-wrapping and quaternion-based filtering techniques to ensure heading continuity and minimize cumulative error during long-distance traversal. This allowed accurate mapping of defect locations within the pipeline despite the absence of external references such as GPS.

This project was executed as a two-member team, where my colleague focused on the mechanical design and drivetrain layout, while I was responsible for the complete electronics architecture, PCB design, wired communication system, and implementation of the control and sensor-fusion algorithms.

<hr>

<pre>
You open your eyes, and you are greeted by an unfamiliar ceiling.
Startled, you get to your feet and quickly scan your surroundings. It's
dark except for the stream of light coming from a crack on the only boarded
window in the room. You try to peek through the crack, but you cannot see
anything. You wonder where you are and who could have possibly brought you here.

<--------------------help------------------------>
Enter quit or one of the following commands -
Weld light look walk pickup inventory help h ?
<------------------------------------------------>

look
The room is a picture of decay with only a faded number identifying it as room-4. The bed you were
 lying on is stained with what looks like dried blood. Could it be your blood? No - it is not. The
 only way out of the room aside from the door to the corridor is a window that is boarded shut. It
 looks like it has been like that for decades. There is a door going west from here. You see a candle
 on the floor. You see a match on the floor.

pickup candle
- you are now carrying the candle -

pickup match
- you are now carrying the match -

light match candle

The candle is now lit. It illuminates everything in the room.

walk west
The corridor is lit with the candle. It is so long that you cannot see to the end. You notice that
 there are words written on the wall. There is a door going east from here. There is a way going north
 from here. There is a door going south from here.
</pre>

<hr>

Source: <a href="https://github.com/jogarces/ics-313-text-game"><i class="large github icon "></i>jogarces/ics-313-text-game</a>

