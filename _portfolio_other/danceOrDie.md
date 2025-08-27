---
title: "Pose-Comparison Dancing"
author_profile: true
key: 2
toc: true
excerpt: "Computer Vision, YOLO, MediaPipe"
header:
  teaser: /assets/images/projectImages/danceOrDie/danceOrDie.gif
classes: wide
---

## Featured Video
<iframe width="1208" height="688" src="https://www.youtube.com/embed/VxFWTcPtr0w" title="IntroToCV_FinalProjectDemo" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
We used a custom made dance for this demonstration to ensure no copyright was infringed.

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

## Media
While conversion from mp4 to gif slowed all videos somewhat, take note of how much slower the MediaPipe iterations are.
<div>
  <div style="display: inline-block; width: 48%; margin-right: 2%;">
    <img src="/assets/images/projectImages/danceOrDie/CVdynamicPort.gif" alt="Dynamic Compare, YOLO" style="width: 100%; height: auto;">
    <p style="text-align: center; font-style: italic; margin-top: 8px;">
      Two figures, YOLO
    </p>
  </div>
  <div style="display: inline-block; width: 48%;">
    <img src="/assets/images/projectImages/danceOrDie/CVdynamicMPPort.gif" alt="Dynamic Compare, MediaPipe" style="width: 100%; height: auto;">
    <p style="text-align: center; font-style: italic; margin-top: 8px;">
      Two figures, MediaPipe
    </p>
  </div>
</div>

<div style="text-align: center;">
  <img src="/assets/images/projectImages/danceOrDie/CVimgComparePort.gif" alt="Image Comparison, YOLO" style="width: 100%; height: auto;">
</div>
<p style="text-align: center; font-style: italic; margin-top: 8px;">Image comparison with YOLO</p>

<div style="text-align: center;">
  <img src="/assets/images/projectImages/danceOrDie/CVdanceMPPort.gif" alt="Dance Comparison, MediaPipe" style="width: 100%; height: auto;">
</div>
<p style="text-align: center; font-style: italic; margin-top: 8px;">Dance comparison with MediaPipe</p>

## Source code
[Github Repository](https://github.com/snydergi/pose-assisted-dancing)
