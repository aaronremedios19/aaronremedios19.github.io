---
layout: project
type: project
image: images/Hook_4_product.jpeg
title: Electronics Subsystem & Access Control Development – Hook EV Systems

permalink: /projects/hook_ev

# All dates must be YYYY-MM-DD format!
date: 2021-06-06
labels:
  - Controls
  - Esp32
  - Embedded C
  - Pcb Design
  - Stm32
summary: Electronics Subsystem & Access Control Development – Hook EV Systems
---



<div class="ui small rounded images uniform-project-images">
  <img class="ui image" src="/images/Hook_!_open.jpeg">
  <img class="ui image" src="/images/Hook_2_pcb.jpeg">
  <img class="ui image" src="/images/Hool_3_Test_resized_resized.jpeg">
  <img class="ui image" src="/images/hookab.jpeg">
  
</div>



While at Hook EV Systems, I was tasked with the design and implementation of the core embedded electronics for the EV bicycle conversion kit, focusing on compactness, connectivity, and secure access. The system enabled conventional bicycles to be converted into electric bicycles with real-time data connectivity and adaptive mode-based control.

I architected and developed a custom ESP32-based control PCB that formed the backbone of the conversion kit’s electronics. This controller interfaced with a custom 4-layer ESC, capturing motion feedback and managing BLDC motor activation. I implemented three riding modes—Assist, Stroll, and Sport—using a PPM-guided control strategy, and designed a PID-based adaptive control algorithm to dynamically adjust motor RPM. This ensured that the bicycle maintained the selected speed even on uphill or downhill terrain, improving ride consistency, adaptability, and overall user experience.

To support secure vehicle interaction and kiosk infrastructure, I integrated a PN532 NFC/RFID module for tag-based authentication, enabling reliable access control at docking stations and service points. For kiosk location tracking and backend telemetry, I integrated a SIM808 GSM/GPRS/GPS module with an external antenna, providing real-time geographic coordinates with sub-3-meter accuracy to the backend system for operational monitoring and fleet management.

Battery status was communicated to users and technicians via an onboard LED indicator, providing instantaneous visibility of charge levels. My primary contributions focused on embedded control PCB design, adaptive PID motor control, wireless integration for NFC access, and GPS-based kiosk tracking, all critical to the kit’s operational efficiency and user experience.





