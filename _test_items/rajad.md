---
title: "Rolling and Jumping Automonous Drone"
author_profile: true
key: 4
toc: true
excerpt: ""
header:
  teaser: /assets/images/projectImages/rajod/gyroscopeWithDrone.jpeg
classes: wide
---
<img src="/assets/images/projectImages/rajod/gyroscopeWithDrone.jpeg" width="400">

## Project Objective
The goal of this project is to create a rolling and jumping autonomous drone (RAJAD) that would blend the abilities of a conventional drone with the 
simplicity of a wheeled robot. This project aims to create a robot with the advantageous
qualities of both a quadrotor and a wheeled robot, with the ability to roll, jump, and hover briefly if necessary to explore its environment. 
Where traditional wheeled robots are limited to the ground plane, this robot is capable of additional actuation to allow for vertical travel. 
Where quadrotors typically are limited in flight time due to power consumption and battery weight capacity, having the robot ground-based will allow
for improved battery capacity and active time by reducing propellor output substantially.

## Outline

### Goals
The must-have goal of this project was to be able to move successfully in an ideal environment, a smooth flat floor. Accomplishing that was the first step toward improving the robot to be able to navigate uneven surfaces and jump.

The core goal of this project was to produce a robot capable of navigating uneven surfaces, with the ability to jump at least one foot vertically, allowing for climbing stairs or over debris.

### Resources and References
#### Hardware
- 1 Crazyflie 2.1+ (https://store.bitcraze.io/products/crazyflie-2-1-plus)
- 1 Crazyradio 2.0 (https://store.bitcraze.io/products/crazyradio-2-0)
- 1 Crazyflie Flow Deck V2 (https://www.bitcraze.io/products/flow-deck-v2/)
- 1 Crazyflie Multi-Ranger Deck (https://www.bitcraze.io/products/multi-ranger-deck/)
- 4 2mm Ball Bearings
- 2 2mm Shafts
- 2 2mm Shaft Collars
- 1 XBox USB Controller

#### Software
Because this is a hardware-oriented project, with the goal being the creation and fabrication of the robot, I will be using as much software that is pre-made as possible, though
it is likely that some custom functions and libraries will be written.
- Crazyflie Python Library (https://github.com/bitcraze/crazyflie-lib-python)
- Pycamera Python Library (https://picamera.readthedocs.io/en/release-1.13/)

#### Reference Material
- Pi Camera with Crazyflie (https://www.bitcraze.io/2017/07/crazyflie-based-quadcopter-with-raspberrypi-camera/)
- Droneball Inspiration (https://imazetech.com/)
- Gyroscope Inspiration (https://www.thingiverse.com/thing:802145)
- Spherical Robot Literature Review (https://doi.org/10.1016/j.robot.2024.104657)