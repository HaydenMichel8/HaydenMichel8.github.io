---
layout: default
title: MCG
permalink: /MCG/
---
[Return to Projects](/projects/)


Currently a work in progress.
The end goal is to allow people to wear the Magnetocardiography (MCG) sensor and move. Our current test setup requires the patients to be sitting still. To reduce motion artifacts, I'm working on integrating an IMU into the sensor. After synchronizing timing, I can use the acceleration from the IMU to approximate the motion of breathing. With this signal, I can reduce the motion noise from breathing in the heart signal being pulled from the MCG. Since this is a passive sensor and the heart's magnetic field is very weak, the signal is very weak so any small improvement is beneficial. Hopefully after demonstrating that noise from just respiration can be eliminated, I can start analyzing noise from talking, walking, and any other type of motion and try to eliminate it so that the heart signal can be extracted in any situation.
