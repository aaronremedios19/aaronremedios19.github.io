---
layout: essay
type: essay
title: Autonomous Drone Inspection with Vision-Language-Action Models
# All dates must be YYYY-MM-DD format!
date: 2026-09-01
labels:
  - Robotics
  - PX4
  - ROS2
  - LiDAR SLAM
  - Sensor Fusion
  - Vision-Language-Action Models
  - Autonomous Systems
---

I'm building an autonomous drone platform intended to perform inspection tasks using a vision-language-action (VLA) model as its high-level decision-maker, with the current focus on getting a solid, fully autonomous flight and sensing stack in place as the foundation the VLA will eventually run on top of.

The platform is a Holybro X500 V2 devkit (frame, GPS, and RC receiver) built around a Pixhawk 6C flight controller paired with an NVIDIA Jetson Orin as the companion compute for onboard autonomy and, eventually, VLA inference.

## Building the PX4 ↔ ROS 2 bridge

The first major milestone was establishing a clean, dedicated communication link between the flight controller and the companion computer. Rather than sharing the existing USB connection (needed for QGroundControl), I set up a dedicated UART link between the Pixhawk's TELEM2 port and the Orin's 40-pin header (`/dev/ttyTHS1`), running PX4's native `uXRCE-DDS` client over it so the Orin talks to PX4 as real ROS 2 topics instead of raw MAVLink.

This required freeing TELEM2 from its default MAVLink role and dedicating it entirely to the DDS client:

| Parameter | Value | Purpose |
|---|---|---|
| `MAV_1_CONFIG` | 0 (Disabled) | Frees MAVLink off TELEM2 |
| `UXRCE_DDS_CFG` | 102 (TELEM2) | Assigns the DDS client to TELEM2 |
| `SER_TEL2_BAUD` | 921600 | Matches baud rate on both ends |

Getting this working end-to-end involved real hardware debugging: after configuration looked correct on both sides but no data was flowing, I used PX4's own MAVLink shell (over the still-functional USB link) to directly query the `uxrce_dds_client` module status, which confirmed the client was running and using serial transport but exchanging zero bytes — pointing at the physical wiring rather than software. The root cause turned out to be TX/RX wired straight-through instead of crossed between the Pixhawk and the Orin's header. Once corrected, the DDS handshake completed cleanly, exposing 65 live PX4 topics (`/fmu/in/...` to command the vehicle, `/fmu/out/...` to read its state) with confirmed live data — attitude quaternions, vehicle status, and more, streaming in real time.

## Sensor fusion for state estimation

With the ROS 2 bridge working, the next step is feeding better position and velocity estimates into PX4's own EKF2 estimator:

- **LiDAR SLAM odometry fusion** — publishing FAST-LIO2's `/Odometry` output into PX4's `/fmu/in/vehicle_visual_odometry` topic, so the flight controller can fuse LiDAR-based position estimates into its state estimate. Getting the NED/ENU frame and quaternion convention conversions right matters a lot here, since an error would silently corrupt the estimator, so I'm using PX4's own reference transform implementation (from `px4_ros_com`) rather than re-deriving the math by hand.
- **Optical flow and rangefinder fusion** — adding an ARK Flow sensor (a PAW3902-based optical-flow and rangefinder module) over the Pixhawk's CAN bus via DroneCAN, giving PX4 an additional velocity and height source that's especially useful in GPS-denied conditions. This is configured through `UAVCAN_ENABLE`, `EKF2_OF_CTRL`, `EKF2_RNG_CTRL`, and `UAVCAN_SUB_RNG`.

## Where this is headed

The autonomy stack — flight controller, companion computer, ROS 2 bridge, and multi-sensor state estimation — is the foundation the inspection system will run on. The next layer is a VLA model running on the Orin that consumes this sensor and state data to make high-level inspection decisions autonomously; the specific model architecture, training approach, and inspection targets are still being worked out and will be documented here as that work develops.
