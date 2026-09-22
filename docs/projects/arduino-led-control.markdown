---
layout: default
title: Arduino Led Control
permalink: /arduino-led-control/
---
[Return to Projects](/projects/)

This project is a full stack app to control Arduino LEDs (among other things) through BLE using a javascript website with a python backend. The website allows experimenters to do a lot of things like make light blinking patterns (stimuli) and save them, play these stimuli later, stop them early, or make sequences of them to play one after another. All of these stimuli and anything else input to the website is stored in SQL. This allows experimenters to make otherwise impossible light patterns to judge subject's spatial perception in our completely dark room. Python connects to all of the Arduino at once using BLE, and sends them encoded commands that the Arduino then decodes and executes. 

This app can also be used for position tracking using VR trackers. It is also of interest to track where a subject may walk, so they have some VR trackers attached to them while they are undergoing the experiment. These trackers output data over BLE which is processed by the python backend and fused with the rest of the data. The app can also play music from a set of downloaded tracks during trials to help the subject relax in the dark room.

Lidar are currently being integrated into this app. The end goal is to have a system where we can specify how far or close to the lidar a subject can be and still have the lights be on. So for example, to ensure that a subject is sufficiently far from the lights being tested, the lidar could have a minimum distance of 20cm set, and if any object (the subject) is closer than 20cm it will send a command to python telling it to turn off the lights. Unfortunately there are a few limitations that I'm still working on. For one it would be much better to have the lidar Arduino talk to the LED Arduino but I have not yet found a way to do this. Additionally, we would like to store all of the data the lidar is measuring so that we can check where the subject was standing throughout the trial, but there is too much data to be able to send over BLE in time with the sampling rate being used and the internal memory of the arduino can only record about 10 seconds of this data so I'm looking into other ways of handling this data such as using an SD card attached to the arduinos.

(Pictures/Videos coming soon!)
