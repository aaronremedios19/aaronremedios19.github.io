---
layout: essay
type: essay
title: 
# All dates must be YYYY-MM-DD format!
date: 2025-02-06
labels:
  - Engineering
  - High Voltage systems
  - Battery design
  - Battery Chemistry
  - Power calculations
---

While working at Aventrex Industries on a solar panel planting AGV, one of the main challenges I encountered was integrating industrial 400 V AC equipment with high-current 72 V DC traction systems on a single, battery-powered mobile platform. The robot had to support a 400 V AC, 50 Hz robotic arm driven by a KUKA KRC5 controller, a 400 V AC vacuum compressor for the suction-based pick-and-place mechanism, and multiple 72 V DC motors responsible for AGV locomotion. Since the onboard energy source was a battery, the first fundamental issue was that batteries naturally supply DC power, whereas the robotic arm and compressor required three-phase AC, making direct integration impractical.

To solve this, I studied and designed a multi-domain power conversion architecture. The approach was to convert DC energy from the battery into three-phase AC using a high-power inverter, while simultaneously supplying DC power to the traction motors through dedicated motor controllers. I calculated the inverter requirements by summing the continuous power demand of the robotic arm (approximately 11.2 kW) and the compressor system, and then factoring in efficiency losses, power factor, and startup currents. Using standard three-phase power equations, I estimated the arm’s operating current to be around 29 A, while each compressor motor drew approximately 3.7 A. These calculations helped define the minimum inverter rating and its thermal and current margins. One practical challenge was that off-the-shelf inverters capable of reliably supplying 400 V AC at this power level were difficult to source for mobile applications. This pushed me to dig deeper into the internal architecture of industrial robot controllers and VFDs, where I learned that both the robotic arm and the compressor already had their own motor control electronics. As a result, the inverter’s role was limited to providing a stable three-phase AC supply, rather than directly controlling the motors, which significantly simplified the system design.

In parallel, I analyzed the 72 V DC locomotion system, where each traction motor was rated at 150 A continuous and 300 A peak, corresponding to 11.2 kW continuous and 21.6 kW peak power. Using basic DC power relationships, I sized the motor controllers, cabling, and protection components to safely handle peak torque conditions such as startup, turning, and uneven terrain. Once the power architecture was defined, I moved on to battery sizing. By estimating the total energy consumption of the AC and DC subsystems, I arrived at a required battery capacity of approximately 99 kWh, or roughly 1380 Ah. At this point, the scale of the challenge became very clear: delivering this amount of energy onboard would result in a battery that was large, heavy, and expensive, directly affecting vehicle stability, efficiency, and overall feasibility.

To address this, I spent considerable time researching battery chemistries and cell formats, including lithium-ion (NMC) and NiMH, with a strong emphasis on energy density and how much capacity could realistically be packaged into a constrained volume. I found that cell format was just as important as chemistry. Larger, high-density cells reduce the total cell count, simplify pack construction, and improve reliability. From a purely technical standpoint, 4680 cells were the most attractive option, offering excellent energy density and lower overall pack weight. However, limitations related to cost and availability made them impractical for the project. As a result, we narrowed the design to 21700 lithium-ion cells, which provided a reasonable balance between performance, availability, and cost.

Despite this optimization, the overall power demand remained extremely high, and the resulting battery system was still too large to be practical for a mobile AGV. Based on these insights, we ultimately made the decision to transition from an electrically driven suction system to a hydraulic solution, which significantly reduced the electrical load and made the system more feasible. This experience taught me the importance of system-level thinking in robotics—understanding when a technically viable solution is no longer practical, and knowing when to pivot the design to achieve a more robust and scalable outcome.
