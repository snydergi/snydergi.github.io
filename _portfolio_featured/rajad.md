---
title: "Hybrid Locomotion Robot"
author_profile: true
key: 3
toc: true
excerpt: "Sensing, CAD, Prototyping"
header:
  teaser: /assets/images/projectImages/rajad/stair_climb.gif
classes: wide
---
## Featured Video
<iframe width="1280" height="720" src="https://www.youtube.com/embed/Cmba8ZEuzpo" title="NU_MSR_Winter_Project" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Goals
This project aims to create a robot with the advantageous
qualities of both a quadrotor and a wheeled robot, with the ability to roll, jump, and hover briefly if necessary to explore its environment. 
Where traditional wheeled robots are limited to the ground plane, this robot is capable of additional actuation to allow for vertical travel. 
Where quadrotors typically are constrained by flight time due to power consumption and battery weight capacity, having the robot ground-based allows
for improved battery capacity and active time by reducing propellor output substantially.

The must-have goal of this project is to be able to move successfully in an ideal environment: a smooth flat floor.
Accomplishing this is the first step toward improving the robot to be able to navigate uneven surfaces and jump.

The core goal of this project is to produce a robot capable of navigating uneven surfaces, with the ability to jump at least one foot vertically.
This allows for climbing stairs or over debris to broaden applicability.

## Mechanical Development
Throughout the development of this project, a key consideration was the overall mass of the robot. Due to their incredibly small form factor as a quadrotor,
the standard Crazyflie 2.1+ has a relatively small payload capacity, at a recommended 15 grams. To improve this capacity, I utilized the Crazyflie Thrust Upgrade,
which provided stronger DC motors and higher thrust propellers. The final thrust was measured by placing the robot on a scale and putting slightly more mass attached
than it was expected to lift then operating the propellers at maximum thrust to collect data on the difference in measured mass before and after, with the difference
being the maximum mass the thrust would be able to counteract. The absolute maximum mass is approximately 60 grams based on the experiment. 

<div>
  <div style="display: inline-block; width: 48%; margin-right: 1%;">
    <img src="/assets/images/projectImages/rajad/rajad_77pt3.png" alt="Mass with no thrust." style="width: 100%; height: auto;">
    <p style="text-align: center; font-style: italic; margin-top: 8px;">
      ~77.3g - No Thrust Applied
    </p>
  </div>
  <div style="display: inline-block; width: 48%; margin-left: 1%;">
    <img src="/assets/images/projectImages/rajad/rajad_16pt8.png" alt="Mass with thrust" style="width: 100%; height: auto;">
    <p style="text-align: center; font-style: italic; margin-top: 8px;">
      ~16.8g - Thrust Applied
    </p>
  </div>
</div>

The final iteration of the custom fabricated parts combined with the quadrotor achieves a sum mass of ~55 grams, making it within the necessary requirement for liftoff. The assembly structure around the Crazyflie consists of a hub and two wheels. The hub is designed to integrate directly into the Crazyflie's structure. The hub is stabilized by wrapping around the two sets of header pins then connecting across the center. Threaded heat inserts on the left and right of the quadrotor also allow for screws to connect while using O-Rings as flexible spacers through two holes that already exist on the PCB of the Crazyflie. The arms that stick out from the hub then have space for two ball bearings to be inserted on each side via heating the bearing and fusing it into the 3D printing space that is slightly undersized for it. The use of two bearings per shaft helps ensure axial allignment between the two wheels.

<div>
  <div style="display: inline-block; width: 48%; margin-right: 2%;">
    <img src="/assets/images/projectImages/rajad/isoViewCAD.png" alt="Isometric View in CAD" style="width: 100%; height: auto;">
    <p style="text-align: center; font-style: italic; margin-top: 8px;">
      Isometric View in CAD
    </p>
  </div>
  <div style="display: inline-block; width: 48%;">
    <img src="/assets/images/projectImages/rajad/final_weight.jpg" alt="Total Mass of Robot" style="width: 100%; height: auto;">
    <p style="text-align: center; font-style: italic; margin-top: 8px;">
      Total Mass of Robot
    </p>
  </div>
</div>

<div>
  <div style="display: inline-block; width: 48%; margin-right: 2%;">
    <img src="/assets/images/projectImages/rajad/mounting_top.jpeg" alt="Top View of Mount" style="width: 100%; height: auto;">
    <p style="text-align: center; font-style: italic; margin-top: 8px;">
      Top View of Mount
    </p>
  </div>
  <div style="display: inline-block; width: 48%;">
    <img src="/assets/images/projectImages/rajad/mounting_bottom.jpeg" alt="Bottom View of Mount" style="width: 100%; height: auto;">
    <p style="text-align: center; font-style: italic; margin-top: 8px;">
      Bottom View of Mount
    </p>
  </div>
</div>

## Locomotion Benchmarking
To test the benefit of mixed modality locomotion, I performed a test to compare power consumption between the two movement methods. The robot began with a fresh, fully charged battery for each experiment. The robots were commanded to move forward and backward half a meter, one rolling, and one maintaing a hover height of 0.2 meters. The timer began as soon as the propellers began moving and stopped upon their halting when the battery discharged all power. This rudimentary test indicates that the rolling motion is four times as power efficient as flying.

| Locomotion Method | Operating Time | Improvement |
| :---------------- | :------------- | :---------- |
| Flying            | 117 seconds    | N/A         |
| Rolling           | 468 seconds    | 400%        |

## Control Scheme
The robot's control scheme consists of two distinct pipelines: teleoperation and autonomous. In the teleoperation pipeline, control inputs are sent from a laptop (running cfclient) via a Crazyradio 2.0 to the robot, allowing for manual remote operation. In the autonomous pipeline, commands are generated by a Python script and transmitted to the robot through the same Crazyradio 2.0, enabling independent operation without human intervention. This dual-pipeline design provides flexibility for both user-controlled and automated robot functionality.

<div style="text-align: center;">
  <img src="/assets/images/projectImages/rajad/WinterProject.drawio.png" alt="Block Diagram" style="width: 80%; height: auto;">
</div>
<p style="text-align: center; font-style: italic; margin-top: 8px;">Information Flow for Teleoperation and Autonomous Control</p>

## Future Work
While further design iteration would be necessary, future work would be the addition of varying sensors or a camera. This would allow for ability to perform visual Simultaneous Localization and Mapping (SLAM) for exploration spaces. A Crazyflie SLAM library using the current sensors, 4 Time of Flight sensors, is also available on [GitHub](https://github.com/khazit/CrazySLAM), though was not extensively tested or used with the current robot.

Additionally, the same concepts could be applied to a larger, more robust quadrotor platform to increase payload and sensing capacity at the expense of the current small form-factor and cost.

## Resources and References
### Hardware
The hardware for this project is a mix of off-the-shelf components and custom designed hardware to combine components.
<div style="display: flex;">
  <div style="flex: 1;">
    <ul>
      <li>1 <a href="https://store.bitcraze.io/products/crazyflie-2-1-plus">Crazyflie 2.1+</a></li>
      <li>1 <a href="https://store.bitcraze.io/products/crazyradio-2-0">Crazyradio 2.0</a></li>
      <li>1 <a href="https://www.bitcraze.io/products/flow-deck-v2/">Crazyflie Flow Deck V2</a></li>
      <li>1 <a href="https://www.bitcraze.io/products/multi-ranger-deck/">Crazyflie Multi-Ranger Deck</a></li>
      <li>1 <a href="https://store.bitcraze.io/products/thrust-upgrade-bundle-for-crazyflie-2-x">Thrust Upgrade Bundle</a></li>
      <li>4 <a href="https://www.mcmaster.com/57155K416/">2mm Ball Bearings</a></li>
      <li>2 <a href="https://www.mcmaster.com/1265K17/">2mm Shafts</a></li>
    </ul>
  </div>
  <div style="flex: 1;">
    <ul>
      <li>1 <a href="https://a.co/d/dDdpf5L">XBox USB Controller</a></li>
      <li>2 <a href="https://a.co/d/4i0yvj9">M2 Threaded Inserts</a></li>
      <li>2 <a href="https://www.mcmaster.com/91292A833/">M2 Screws</a></li>
      <li>2 <a href="https://www.mcmaster.com/9262K101/">2mm O-Rings</a></li>
      <li>1 3D Printed Hub</li>
      <li>2 3D Printed Wheels</li>
      <li>1 Laptop</li>
    </ul>
  </div>
</div>

<!-- Add picture of full setup here -->

### Software
Due to the community-development-based nature of the Crazyflie system, many software libraries and support already existed.
The following libraries were used for this project:
- Crazyflie Python Library (https://github.com/bitcraze/crazyflie-lib-python)
- Crazyflie Firmware Library (https://github.com/bitcraze/crazyflie-firmware)

### Reference Material
<!-- - Pi Camera with Crazyflie (https://www.bitcraze.io/2017/07/crazyflie-based-quadcopter-with-raspberrypi-camera/) -->
- Cylindrical Drone (https://ieeexplore.ieee.org/document/6868259)
- Droneball Inspiration (https://imazetech.com/)
- Spherical Robot Literature Review (https://doi.org/10.1016/j.robot.2024.104657)

## Source code
[Github Repository](https://github.com/snydergi/msr_winter_project)
