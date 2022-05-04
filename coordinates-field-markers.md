---
title: Coordinates, field and markers
layout: default
mathjax: true
permalink: /coordinates-field-markers
---

## PDFs

* [Full field (PDF)](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/field.pdf)
* Field markers:
    * [Marker 1 (PDF)](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/field-marker-1.pdf)
    * [Marker 2 (PDF)](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/field-marker-2.pdf)
    * [Marker 3 (PDF)](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/field-marker-3.pdf)
    * [Marker 4 (PDF)](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/field-marker-4.pdf)
* [Green team markers (PDF)](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/green-markers.pdf)
* [Blue team markers (PDF)](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/blue-markers.pdf)

## Coordinates

The field coordinates are the following:

<div class="text-center">
    <img width="350" src="/assets/imgs/field-frame.svg" />
</div>

The frame's origin is the middle of the field, and robots orientation are angle formed by
field x axis and front of the robot.

Roughly, the coordinates of the blue robot above will look like *(x=0.4, y=0.4, alpha=45 deg)*.

## Robots

You can print [green](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/green-markers.pdf) and [blue](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/blue-markers.pdf) markers and
place them on the robots:

<div class="text-center">
    <img width="350" class="responsive" src="/assets/imgs/robot-markers-explain.svg" />
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
