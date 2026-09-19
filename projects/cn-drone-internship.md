---
layout: project
type: project
image: images/CN1.jpeg
title: Drone Internship at Canadian National Railways
permalink: /projects/cn-drone-internship
date: 2026-05-01
labels:
  - Drones
  - UAV
  - Photogrammetry
  - Machine Learning
  - LiDAR
  - Python
  - SQL
  - FAA Part 107
  - Internship
summary: Drone Engineer intern who built a LiDAR-based algorithm to automatically detect defective concrete rail ties, alongside fleet management, rail-inspection analytics, and ML-based maintenance prediction.
---

<style>
.cn-drone-gallery {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
  gap: 16px;
  margin: 1.2em 0;
}
.cn-drone-gallery > img {
  width: 100%;
  height: 240px;
  object-fit: cover;
  display: block;
  border-radius: 10px;
}
</style>
<div class="cn-drone-gallery">
  <img src="{{ site.baseurl }}/images/CN1.jpeg">
  <img src="{{ site.baseurl }}/images/CN2.jpeg">
  <img src="{{ site.baseurl }}/images/CN3.jpg">
  <img src="{{ site.baseurl }}/images/CN4.jpg">
  <img src="{{ site.baseurl }}/images/CN5.png">
</div>

## Overview

As a Drone Engineer Intern at Canadian National Railways (May 2026 – August 2026), I worked across drone fleet operations, autonomous rail-inspection data analysis, and predictive maintenance modeling.

- Led the evaluation, selection, and implementation of fleet management software for a fleet of 104 drones, gathering operational requirements, conducting vendor meetings, comparing platforms, and coordinating deployment with internal stakeholders and software providers.
- Analyzed ATIP autonomous rail-inspection data to identify trends, operational insights, and opportunities to improve track-monitoring and inspection processes.
- Processed and analyzed drone photogrammetry data using CloudCompare, working with 3D point clouds to evaluate captured infrastructure and support inspection workflows.
- Earned an FAA Part 107 Remote Pilot Certification, enabling compliant commercial UAS operations and supporting safe drone flight planning and field operations.
- Developed machine learning prediction models using ATIP autonomous rail-inspection data to detect deteriorating rail assets and identify potential maintenance risks for proactive infrastructure monitoring.
- Identified and diagnosed a bad batch of manufacturing-defective concrete rail ties, then designed a Python and SQL-based algorithm to automatically detect them from LiDAR cant and gauge measurements, replacing a manual inspection process.

## Highlight Project: Automated Defective Concrete Tie Detection

One of the most impactful projects during my internship started with a real operational problem: a batch of concrete rail ties had a manufacturing defect, and there was no efficient way to know which ties in the network were affected without inspecting them manually — a slow, labor-intensive process across a huge rail network.

To solve this, I worked with LiDAR data collected by CN's ATIP autonomous rail-inspection system, focusing on the track geometry metrics of **cant** (the cross-level/tilt of the rail) and **gauge** (the spacing between rails). Defective ties produced characteristic, measurable deviations in these values that weren't obvious to a human reviewer scanning the data by eye, but were detectable through systematic analysis.

I built a data pipeline that:

- Used **SQL** to query and extract the relevant LiDAR-derived cant and gauge measurements from CN's rail-inspection databases at scale.
- Used **Python** to process and analyze this data, developing an algorithm that flagged ties whose cant/gauge signatures matched the pattern of the known manufacturing defect.
- Converted what had been a fully manual, ties-by-tie visual inspection process into an automated, data-driven detection method, allowing the affected ties to be located quickly and accurately across the network.

This project let me apply data analysis and software engineering directly to a real infrastructure safety problem, and demonstrated how sensor data already being collected for other purposes (LiDAR track geometry scans) could be repurposed to solve an unrelated but critical maintenance issue.
