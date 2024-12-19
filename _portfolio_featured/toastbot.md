---
title: "7-DOF Food Preparation"
author_profile: true
key: 1
toc: true
excerpt: "ROS2, MoveIt, RealSense"
header:
  teaser: /assets/images/projectImages/toastImages/toast.jpg
classes: wide
---
## Featured Video
<!-- <iframe width="560" height="315" src="/assets/images/projectImages/toastImages/toastDemo.mp4" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe> -->

## Project Objective
The goal of this project, more simply referred to as ToastBot, was to use an Emika Franka Panda robot arm to pick up a piece of bread, put it in a toaster, start the toaster, and place it on a plate.

### Collaborators

This project was done in collaboration with the following students:

* Sharwin Patil (<https://github.com/Sharwin24>)
* Asa Rogers (<https://github.com/asarogers>)
* Tony Shilati (<https://github.com/tony-shilati>)

## Outline

### MoveIt API

Prior to the start of the ToastBot project, the group developed an API to to simply interface new ROS2 nodes with the Emika Franka Panda robot's MoveIt package. The API consists of three main subcomponents: RobotState, ScenePlanner, and MotionPlanner. The three are abstracted within the MotionPlanningInterface, which can be imported into ROS2 nodes to make motion requests of the robot arm.

<b>Subcomponent Breakdown</b>

The ScenePlanner component can be used to update the move group planning scene. It allows users to add and remove boxes, attach and detach collision objects from the end effector, and load multiple collision objects at once. It is capable of adding objects of different shapes and dimensions as specified by the user for each function. Use of the ScenePlanner is critical particularly in instances where the robot is grasping a solid object and must plan paths around obstacles, accounting for said object in its grasp.

The RobotState component performs forward and inverse kinematic caluclations for the Emika Franka Panda robot arm for use in determining current or desired poses, or the angles required to achieve them.

The MotionPlanner component contains the bulk of the API's functionality. It provides utilities to plan, execute, and manage robot trajectories using joint configurations, Cartesian paths, and predefined named configurations. Additionally, it allows for control of the robot end-effector. The MotionPlanner serves as a ROS2 Action Client to he MoveGroup node running on the robot arm.

The key components of the API used in the ToastBot project are the RobotState and MotionPlanner.

### Workspace Planning

With limited workspace, designing and arranging the components of the task was an important consideration. To aid in this, we created many 3d-printed fixtures including a bread holder, toaster lever extension, plate, brush holder, and butter dish holder. Each model was designed to have a slot for an April Tag such that offsets to points of interest on the model would be quick to determine. In early stages of the project, a virtual recreation of the scene using the MoveItAPI ScenePlanner was considered, but due to the reliability of the April Tag positioning and the desired poses, collisions were not of major concern and it was ultimately unused.

### Computer Vision

Vision was a key aspect to the success of this project. We used an Intel RealSense D435i camera mounted outside the workspace of the arm on a tripod to capture the entire scene. With the camera in place, we used April Tags to create transforms between each object in the scene and the robot.

### Multi-Threaded Executor


## Source code
[Github Repository](https://github.com/snydergi/ToastBot)