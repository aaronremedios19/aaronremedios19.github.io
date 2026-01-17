---
layout: essay
type: essay
title: Chamfering Machine for Rack and Pinion gears
# All dates must be YYYY-MM-DD format!
date: 2024-09-08
labels:
  - Product Development
  - Automation
  - Reverse Engineering Products
  - HMI
  - Python
  - Embedded systems
---

As my bachelor’s major project, I worked with Gears & Gears Manufacturing Co., Mumbai, to research ,reverse engineer  and build a servo-driven automated chamfering machine specifically for rack and pinion gears. The core challenge was that commercially available chamfering machines largely imported from China and Germany were designed for spur gears and relied on expensive PLC-based automation, making them unsuitable for small-scale manufacturers focused on rack gears.

System Architecture and Mechanical Design

The machine was designed around a servo-based heavy-load linear ball-screw slide (1000 mm travel) driven by a three-phase AC servo motor and servo drive. This linear axis formed the primary motion bed that translated the rack gear during chamfering. Precise velocity and directional control of this bed was critical, as the chamfering operation had to remain synchronized with the gear tooth pitch.

For material removal, we selected a Bosch linear grinder fitted with a diamond cutting bit. Since the grinder was not originally designed for this application, I designed a custom mounting and actuation attachment in SolidWorks to rigidly hold the grinder while allowing controlled vertical motion. This attachment was first prototyped using 3D printing to validate fit, stiffness, and alignment. After multiple iterations, the finalized design was machined in aluminum to ensure rigidity, vibration resistance, and long-term durability under continuous operation.

The grinder assembly was mounted on a servo stepper motor–driven vertical axis, allowing controlled lift and engagement of the cutting tool with the rack teeth. This vertical axis was mechanically coupled to the grinder mount and electrically driven via a servo stepper drive.

Control Architecture and Synchronization Logic

The entire system was controlled using a Raspberry Pi, which coordinated both the linear bed motion and the vertical grinder actuation. Communication with the servo drives was implemented using Modbus, providing reliable control over speed, direction, and positional behavior without the need for a PLC.

One of the primary technical challenges was synchronizing the horizontal motion of the rack bed with the vertical engagement of the grinder. To address this, I developed a mode-based control architecture, where each mode corresponded to a specific rack gear size. These modes encoded parameters such as:

Rack tooth pitch

Required chamfer depth

Grinder engagement height

Bed traversal speed

For each selected mode, the control algorithm computed the bed displacement per tooth and coordinated it with timed vertical tool engagement, ensuring that each tooth was chamfered consistently. The vertical axis lifted and lowered the grinder in synchronization with the linear motion of the rack, allowing continuous chamfering without stopping the bed between teeth.

This synchronization logic was implemented as a simple, deterministic control loop, prioritizing repeatability and robustness over complexity. By keeping the algorithm lightweight and predictable, the system remained reliable even under industrial operating conditions.

Operator Interface and Automation

To minimize reliance on skilled operators, I developed a locally hosted React-based HMI, running directly on the Raspberry Pi. The interface allowed the operator to select one of three predefined rack sizes, after which the machine automatically executed the corresponding chamfering sequence. No manual parameter tuning was required at runtime.

This approach eliminated setup errors, reduced training requirements, and ensured consistent output quality across different operators and production batches.
Outcome and Impact
By replacing PLC-based automation with an embedded, software-driven control architecture, we achieved reliable and repeatable chamfering performance at a fraction of the cost of commercial machines. The entire system was developed for under $1000, representing a smarter and more efficient solution customized for the specific rack gear use case.




<div class="ui small rounded images uniform-project-images">
  
  <img class="ui image" src="{{ site.baseurl }}/images/p3.jpeg">

  <img class="ui image" src="{{ site.baseurl }}/images/p4.jpeg">
  <img class="ui image" src="{{ site.baseurl }}/images/p2.jpeg">
  <img class="ui image" src="{{ site.baseurl }}/images/p1.jpeg">
</div>
 <img class="research-hero" src="{{ site.baseurl }}/images/p5.png" alt="">


