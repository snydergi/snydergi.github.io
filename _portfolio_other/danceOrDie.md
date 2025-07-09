---
title: "Pose-Assisted Dancing"
author_profile: true
key: 1
toc: true
excerpt: "Computer Vision,"
header:
  teaser: /assets/images/projectImages/recipeRoulette/globeSpin.gif
classes: wide
---

![TEMP](/assets/images/misc/underConstruction.jpg)


### Collaborators

This project was done in collaboration with the Joseph Blom (<https://github.com/jrblom2>).

## Project Objective
Inspired by a lineage of dancing games from 'Dance Dance Revolution' to 'Just Dance', we sought to build a project that would utilize Computer Vision for pose comparison. Within this game, a camera is used in synchronization with a trained machine learning model that performs live joint estimation. 
<!-- This model is applied both to a prerecorded video that the live dancer wishes to emulate, as well as to the dancer or dancers in view of the camera. The result is a side-by-side of the recorded video and the live video, and each haves pose tracking applied over top of them. With the simultaneous pose tracking, a current score and an average score is displayed on the screen for each dancer present in the frame to gauge how well they are following the dance. -->

## Outline
This project implements two methods of pose detection to allow for experience in a variety of models. We chose to use YOLO11n from Ultralytics and Google MediaPipe. Both methods are functional in the final product, though the performance of YOLO in our use case is much better. 

The internals of the program are setup as a pipeline. When the user begins the program, a video stream from a webcam is captured. For the main program mode, this feed will be streamed side-by-side with a pre-recorded dance video. At this point, the selected model, YOLO or MediaPipe, will be run with the current frame from each video and overlay the detected frame onto it for visual feedback. With pose data captured, it is normalized to account for different frame sizes, then we use cosine similarity for comparison of the poses. This angle-based comparison is pertinent to this use, as the orientation of the wire-frame is to be comparied more heavily than the position. With the score metric calculated, it is printed to the screen for the user to see.
