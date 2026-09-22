---
layout: page
title: Line Image Processing
permalink: /line-finder/
---
[Return to Projects](/projects/)

For one of our experiments in the Vision Lab, subjects were shown a few floating lights in an otherwise totally dark room. These lights were arranged in a way to "trick" the brain into seeing things that aren't physically happening such as lights that are curved appearing straight. These phenomenon happen because in the dark room there is nothing to reference these floating lights to and our brains get confused. (These "floating lights" are really just LEDs on stands at various heights but since it's pitch dark they appear floating to the subject.)

After seeing the lights, subjects were instructed to draw a curve showing what they saw and draw a circle for each light. I had to use computer vision to process these drawn curves after they were scanned and uploaded. I ended up having to make a relatively complicated GUI that allows the user to tune a few parameters for image processing because finding all the points on the curve while using the same parameters every time proved difficult. A major challenge with this projects was detecting the numbers on the graph paper. These numbers give the distance in meters so they were necessary to convert from pixels to meters so the curve was in a useable form. I finally got it working consistently by using Pytesseract to detect the numbers, and learned about which numbers are easy or hard to detect among other things. This project was a great success and people in my lab with no programming experience were able to use the GUI to process the large amounts of papers into .csv files with the curve coordinates in meters.

<iframe
  src="/assets/line-image-processing.PNG"
  width="100%"
  height="400px">
</iframe>

Tuning all of these different image processing parameters is tricky, so I developed a [genetic algorithm](https://en.wikipedia.org/wiki/Genetic_algorithm) to try and get a good guess. It takes a "population" of a few sets of parameters, and sees how much of the curve they cover. It then allows the best ones to reproduce while adding in more random individuals throughout the process. The end result almost always finds a good match for the curve, and due to its random nature can be ran multiple times to try and find the best result possible.


