---
layout: single
permalink: /portfolio/reaction-wheel/
author_profile: true
classes: wide
title: Reaction Wheel
excerpt: Satellite-inspired single-axis attitude controller
header:
  overlay_image: /assets/reaction-wheel/images/kepler-reaction-wheels.jpg
  teaser: /assets/reaction-wheel/images/kepler-reaction-wheels.jpg
date: 2026-02-27
---

## Understanding the Problem
<small>February 27, 2026</small>

Attitude control is an important part of spacecraft guidance, navigation, and control (GNC). To perform fundamental operations like pointing antennas toward earth, aiming cameras, aligning telescopes, and optimizing solar exposure, spacescraft must be able to reorient themselves. 

In space, small external disturbances such as gravity-gradient torque and solar radiation pressure as well as internal momentum changes can cause non-negligible changes in spacecraft attitude.

Reaction wheels can counteract these changes in spacecraft attitude, a process that is governed by the conservation of angular momentum. As the reaction wheel is attached to the spacecraft, changing the rotation speed of the reaction wheel causes a proportional counter-rotation in the spacecraft.

Thrusters can also be used for attitude control, but as fuel is both heavy and finite, thrusters are generally less desirable than reaction wheels for this purpose.

By doing some rough hand calculations, we can get a better feel for the problem. These calculations also provide a jumping-off point for further analysis.

![Hand Calculations (Rough)](/assets/reaction-wheel/images/rough-calcs.png)