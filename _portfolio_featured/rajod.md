---
title: "Rolling and Jumping Orb Drone"
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
The goal of this project is to create a rolling and jumping orb drone (RAJOD), similar to robots such as
Sphero, BB-8, or Droneball. This project aims to create a robot with the advantageous
qualities of both a quadrotor and a wheeled robot, with the ability to roll, jump, and po-
tentially hover briefly if necessary to explore its environment. Where traditional spher-
ical robots are limited to planar surfaces, this will be capable of many terrains. Where
quadrotors typically have minimal flight time, having the robot ground-based will allow
for larger battery capacity and active time.

## Outline

### Goals
The goals of this project are outlined in three sections: Fallback, Core, and Reach.

The fallback goal of this project is to be able to move successfully in an ideal environ-
ment, a smooth flat floor. Accomplishing this is the first step toward improving the robot
to be able to navigate uneven surfaces and jump.

The core goal of this project is to produce a robot capable of navigating uneven surfaces, with the ability to jump at least one foot vertically, allowing for climbing stairs or
over debris.

The reach goal of this project is to add a camera to allow remote control from a position
where the robot is not visible. This would also ultimately create capability for limited
SLAM applications.

### Tasks
For goal oriented work to be accomplished, the project has been divided into anticipated tasks in an approximate timeline following the Northwestern 10-week schedule.
1. Design gyroscope (Week 1)
2. Build cage and robot exterior (Week 2)
3. Assemble full robot (Week 3)
4. Tune Crazyflie to only roll, develop software (Week 4-6)
5. Create jumping functionality (Week 7)
6. Test longevity, exploration capabilities, and perform benchmarking (Week 8)
7. Add camera hardware and software (Week 9-10)

### Risks, Challenges, and Uncertainties
I see the highest risk of failure for this project being the structure surrounding the in-
ternal quadrotor. Creating a wire mesh sphere that is robust enough to provide structure
but not overdone to the point of weighing down the robot and preventing motion will
be difficult to achieve. In addition, the design and creation, as well as balancing, of the
quadrotor on the internal gyroscope will prove challenging.
The parts of the project I am least sure on how to approach is the software aspects. I
have little experience with quadrotors and the controls that go into them, so I will need to
do more research to understand how to alter its performance to get the proper thrust and
mobility I want from the robot. I plan on addressing this potential issue and uncertainty
through experimentation with the quadrotor, and examination of the current library.

### Anticipated Necessities and References
#### Hardware
- 1 Crazyflie 2.1+ (https://store.bitcraze.io/products/crazyflie-2-1-plus)
- 1 Crazyradio 2.0 (https://store.bitcraze.io/products/crazyradio-2-0)
- 1 XBox USB Controller
- Wire for spherical shell
- Raspberry Pi Zero-W (https://a.co/d/8pbOcCn)
- Raspberry Pi Standard Camera (https://a.co/d/hpUwEWQ)
- Raspberry Pi 160 FOV Camera (if standard camera not adequate) (https://a.co/d/5NxLklM)

#### Software
Because this is a hardware-oriented project, with the goal being the creation and fabri-
cation of the robot, I will be using as much software that is pre-made as possible, though
it is likely that some custom functions and libraries will be written.
- Crazyflie Python Library (https://github.com/bitcraze/crazyflie-lib-python)
- Pycamera Python Library (https://picamera.readthedocs.io/en/release-1.13/)

#### Reference Material
- Pi Camera with Crazyflie (https://www.bitcraze.io/2017/07/crazyflie-based-quadcopter-with-raspberrypi-camera/)
- Droneball Inspiration (https://imazetech.com/)
- Gyroscope Inspiration (https://www.thingiverse.com/thing:802145)
- Spherical Robot Literature Review (https://doi.org/10.1016/j.robot.2024.104657)