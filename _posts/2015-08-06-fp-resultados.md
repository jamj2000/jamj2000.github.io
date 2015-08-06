---
layout: post
title: Aplicación web para calificación en FP por Resultados de Aprendizaje
link: https://github.com/jamj2000/fp-resultados
link-alt: GitHub repository
img: fp-resultados.png
alt: fp-resultados
date: 2015-08-06
category: portfolio
description: 
article: yes

---

<!-- #### Reference paper: _Gaze Stabilization for Humanoid Robots: a Comprehensive Framework_ -->

#### Authors: _Alessandro Roncone, Matej Hoffmann, Ugo Pattacini, Luciano Fadiga, and Giorgio Metta_

<!-- #### Submission: _2014 IEEE-RAS International Conference on Humanoid Robots, Madrid, Spain, November 18-20, 2014_ -->

<!-- ## Video

Here is a video that summarizes the behavior:

 -->

## Description

In this work, the tactile system has been used in order to build a representation of space immediately surrounding the body - peripersonal space. In particular, the iCub skin has been used as a reinforcement for the visual system, with the goal of enhancing the perception of the surrounding world. By exploiting a temporal and spatial congruence between a purely visual event (e.g. an object approaching the robot's body) and a purely tactile event (e.g. the same object eventually touching a skin part), a representation has been learned that allows the robot to autonomously establish a *margin of safety* around its body through interaction with the environment  - _extending its cutaneous tactile space into the space surrounding it_.

We considered a scenario where external objects were approaching individual skin parts. An illustration is depicted in the introductory Figure. A volume was chosen to demarcate a theoretical visual _"receptive field"_ around every taxel. Learning then proceeded in a distributed, event-driven manner - every taxel stored and continuously updated a record of the count of positive (resulting in contact) and negative examples it has encountered for every combination of distance (D) and time to contact (TTC). 
    

## Results

Selected results - for one taxel of left forearm - are shown in Figure 2. They show the representation after learning and smoothing using adapted Parzen Window method with color coding the third dimension (the estimated probability of contact). A clear "ridge" can be seen in the plot which corresponds to the trajectories of objects as they approach the taxel and both D and TTC are decreasing. The contact with the taxel occurs at both D and TTC approximatively equal to 0.


This method can be employed for *life-long incremental learning* in the robot, automatically incorporating robot's new experiences or changes to its body or sensory apparatus. The robot can profit from this representation in that it provides a prediction of contacts with the skin prior to the actual contact. We have thus devised a controller that capitalizes on this prediction and generates avoidance behaviors. Furthermore, a simple reversal of the controller sign generates "catching" of approaching objects.  All these behaviors take automatically the whole body surface (or skin surface) into consideration.
