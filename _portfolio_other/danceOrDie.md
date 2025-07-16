---
title: "Pose-Assisted Dancing"
author_profile: true
key: 1
toc: true
excerpt: "Computer Vision, YOLO, MediaPipe"
header:
  teaser: /assets/images/projectImages/danceOrDie/danceOrDie.gif
classes: wide
---

## Featured Video
<iframe width="1208" height="688" src="https://www.youtube.com/embed/VxFWTcPtr0w" title="IntroToCV_FinalProjectDemo" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


### Collaborators

This project was done in collaboration with the Joseph Blom (<https://github.com/jrblom2>).

## Project Objective
Inspired by a lineage of dancing games from 'Dance Dance Revolution' to 'Just Dance', we sought to build a project that would utilize Computer Vision for pose comparison. Within this game, a camera is used in synchronization with a trained machine learning model that performs live joint estimation. 

## Outline
This project implements two methods of pose detection to allow for experimenting with different models.
We chose to use YOLO11n from Ultralytics and Google MediaPipe. Both methods are functional in the final product,
though the performance of YOLO in our use case is much better. 

The internals of the program are setup as a pipeline. When the user begins the program,
a video stream from a webcam is captured. For the main program mode, this feed will be streamed side-by-side with a
pre-recorded dance video. At this point, the selected model, YOLO or MediaPipe, will be run with the current frame from
each video and overlay the detected frame onto it for visual feedback. With pose data captured, it is normalized to account
for different frame sizes, then we use cosine similarity for comparison of the poses. This angle-based comparison is pertinent
to this use, as the orientation of the wire-frame should be weighted more heavily than the position for comparisons. With the score metric calculated,
it is printed to the screen for the user to see.

This project has functionality beyond the dancing game. It may also be used in different modes to compare a live pose to a still image, or to compare two figures on screen to each other.
