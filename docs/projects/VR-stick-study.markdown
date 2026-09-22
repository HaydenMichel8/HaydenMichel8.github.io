---
layout: default
title: VR Stick Study
permalink: /VR-stick-study/
---
In vision therapy, a [Brock String](https://en.wikipedia.org/wiki/Brock_string) is a well proved method for helping people fixate on objects close to their face. The aim of this VR project was to develop games with a similar purpose to allow people to improve their vision without needing a trained optometrist present. The environment was made in Unity using C# and has the subject wear a VR headset with built in eye trackers. This eye data is used in real time to judge whether they are looking at a sphere or not and to move it towards them or not, among other things.

The VR project has a full environment that can be teleported around, 4 different games with customizable settings, and lots of adjustable parameters to allow experimenters to adjust on the fly. All of the data from the eye trackers was saved over the subjects many visits over a few weeks to try and find improvement from the VR games.

Developing this project was pretty difficult, I had little VR experience before working on it and a lot was already implemented so adding my own features was difficult. But I eventually figured things out and made some improvements to the testing environment and handled processing all the data and generating tons of different plots showing things like performance in a single trial, number of fixation losses, and patient performance over time.

<iframe
  src="/assets/vr-stick-study.png"
  width="100%"
  height="1000px">
</iframe>

A screenshot showing one of the games in progress. The subject has to fixate on the far sphere and move it towards the close sphere by changing where they are looking.
