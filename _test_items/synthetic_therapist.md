---
title: "Synthetic Therapist Exoskeleton with LSTM"
author_profile: true
key: 10
toc: true
excerpt: "PyTorch, ROS, Real-Time"
header:
  teaser: /assets/images/misc/underConstruction.jpg
classes: wide
---

## Featured Video
<!-- <iframe width="1208" height="688" src="https://www.youtube.com/embed/VxFWTcPtr0w" title="IntroToCV_FinalProjectDemo" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
We used a custom made dance for this demonstration to ensure no copyright was infringed. -->

### Collaborators

This project was done under the guidance of [Lorenzo Vianello](https://github.com/LorenzoVianello95), a post-doc in the Neurorehabilitation and Neural Engineering Laboratory, led by [Dr. José L. Pons](https://www.sralab.org/researchers/jose-l-pons-phd) at the [Shirley Ryan AbilityLab Legs + Walking Lab](https://www.sralab.org/research/abilitylabs/legs-walking-lab).

## Project Objective

This project aimed to improve patient post-stroke gait rehabilitation using a lower-limb exoskeleton with implementation of a machine learning model trained on patient-therapist interactions. The 'Synthetic Therapist' would take the place of the human therapist in an exoskeleton dyad rehabilitation system (link or explanation?), providing predictions from the model as inputs to the patient exoskeleton control loop.

## Results

The Synthetic Therapist successfully utilizes a Long Short-Term Memory (LSTM) model to accurately predict therapist reactions to patient joint inputs. While active, the wearer of the exoskeleton (ExoMotus-X2, Fourier Intelligence) has their gate assisted and corrected based on outputs of the LSTM being fed into the patient exoskeleton control loop. The Synthetic Therapist runs on a ROS1 Noetic node within the workspace. The model receives input from the subject exoskeleton at ~333Hz via subscriptions to ROS topics, then publishes the output of the LSTM on a ROS topic at ~333Hz, maintaining the real-time requirements of the human-exoskeleton interaction. This allows for a smooth adjustment to the wearers gait.

<div style="text-align: center;">
  <img src="/assets/images/projectImages/syntheticTherapist/SyntheticTherapistControlLoop.png" alt="Control Loop Block Diagram" style="width: 100%; height: auto;">
</div>
<p style="text-align: center; font-style: italic; margin-top: 8px;">Control loop for Synthetic Therapist rehabilitation system.</p>

The model predicts therapist interactions for the patient with a high degree of accuracy. Models typically predict with less than 0.1 radian (~5.7 degrees) root mean square error when compared to therapist data from various patients. Most deviation in the model predictions from true data is seen in the lower amplitude peaks of the gait phase, which already often occur from the exoskeleton inertia causing small oscillation rather than it being a part of the true gait. Like any machine learning model, erroneous predictions may occur with a large error. Protections are established within the code to prevent large predictions that may be out of the range of motion from occurring.

## Methodology


## Source code
[Github Repository](https://github.com/snydergi/SRALabProject)
