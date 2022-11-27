---
title: Coordinates, field and markers
layout: default
mathjax: true
permalink: /coordinates-field-markers
---

The whole scene is tracked by a **camera** in order to provide a localization for the robots and the ball.
We use visual codes named *ArUco* as fiducial markers to detect the corner of the fields and the robots.

The ball is detected using its color (orange).

## Markers PDFs

* [Full field (PDF)](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/field.pdf)
* Field markers:
    * [Marker 1 (PDF)](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/field-marker-1.pdf)
    * [Marker 2 (PDF)](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/field-marker-2.pdf)
    * [Marker 3 (PDF)](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/field-marker-3.pdf)
    * [Marker 4 (PDF)](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/field-marker-4.pdf)
* [Green team markers (PDF)](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/green-markers.pdf)
* [Blue team markers (PDF)](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/blue-markers.pdf)

## Field dimensions

Here are the main field dimensions:

<div class="text-center">
    <img width="550" src="/assets/imgs/dimensions.png" />
</div>

If you want to deploy the kit, we recommend a floor footprint of about *2.5m x 2.5m*. Indeed, you need some extra
space around the field to deploy the structure for hold the camera.

## Coordinates system

The field coordinates used in the software are the following:

<div class="text-center mb-2">
    <img width="450" src="/assets/imgs/field-frame.svg" />
</div>

* The frame's origin is the middle of the field, and robots orientation are angle formed by
field x axis and front of the robot.
* We use [international system units](https://en.wikipedia.org/wiki/International_System_of_Units),
distances are then expressed in meters and orientations in radians.

<div class="alert alert-info">
    Roughly, the coordinates of the blue robot above will look like 
    <code>(x=0.4 m, y=0.4 m, alpha=pi/4 rad)</code>.
</div>

## Robots

You can print [green](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/green-markers.pdf) and [blue](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/blue-markers.pdf) markers and
place them on the robots:

<div class="text-center">
    <img width="350" class="responsive" src="/assets/imgs/robot-markers-explain.png" />
</div>

## Markers

Markers are ArUco 4x4, you can use tool like [this one](https://chev.me/arucogen/), printed with a scale
of of 8 cm for the robots and 16cm for field corners. The PDF provided previously are 1:1 scale. The ArUco ids are:

* `0`: field corner 1
* `1`: field corner 2
* `2`: field corner 3
* `3`: field corner 4
* `4`: robot green 1
* `5`: robot green 2
* `6`: robot blue 1
* `7`: robot blue 2
* `8-15`: generic objects
