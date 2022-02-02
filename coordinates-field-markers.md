---
title: Coordinates, field and markers
layout: default
mathjax: true
permalink: /coordinates-field-markers/
---

# Coordinates and markers

* [Field](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/field.pdf)
* [Field corner markers](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/field-markers.pdf)
* [Green team markers](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/green-markers.pdf)
* [Blue team markers](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/blue-markers.pdf)

## Field

### Building the field

You can either:

* Print the [whole field](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/field.pdf)
* Print only the [corner markers](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/field-markers.pdf) to stick them on existing field

In the second case, this is where they are placed:

<div class="text-center">
    <img src="/assets/imgs/field-markers-explain.png" />
</div>

### Coordinates

The field coordinates are the following:

<div class="text-center">
    <img src="/assets/imgs/field-frame.png" />
</div>

The frame's origin is the middle of the field, and robots orientation are angle formed by
field x axis and front of the robot.

Roughly, the coordinates of the blue robot above will look like *(x=0.4, y=0.4, alpha=45 deg)*.

## Robots

You can print [green](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/green-markers.pdf) and [blue](https://raw.githubusercontent.com/robot-soccer-kit/robot-soccer-kit/master/docs/blue-markers.pdf) markers and
place them on the robots:

<div class="text-center">
    <img src="/assets/imgs/robots-markers-explain.png" />
</div>

## Camera

The camera can be any USB camera that works with OpenCV, and it should be able to see the whole field

We recommend using [Spedal MF920Pro, 1080p and 120° angle](https://www.amazon.com/Spedal-Conference-Streaming-Microphone-Desktop/dp/B07TDQ8NL3)

To assemble the structure, you can use 50mm PVC pipes, and attach the camera with a Ziptie:

<div class="text-center">
    <img src="/assets/imgs/camera_ziptie.png" />
</div>

(here, zip tie is a 7.5 x 300mm)

## Bluetooth

We recommend using USB external [ZEXMTE Bluetooth adapter](https://www.amazon.fr/gp/product/B08SC9M9K3/)

On Linux, you might need to run the `./install.sh` script located in the [bluetooth directory](/bluetooth) of this
repository to get it working.

## Markers

Markers are ArUco 4x4, you can use tool like [this one](https://chev.me/arucogen/), printed with a scale
of 8 cm. The PDF provided previously are 1:1 scale. The ArUco ids are:

* `0`: field corner 1
* `1`: field corner 2
* `2`: field corner 3
* `3`: field corner 4
* `4`: robot green 1
* `5`: robot green 2
* `6`: robot blue 1
* `7`: robot blue 2
* `8-15`: generic objects

## Ball

<div class="text-center">
    <img src="/assets/imgs/balls.png" />
</div>

For the ball, we use orange gold ball in PU (foam) material

## Field

The field material can be anything, but we strongly recommend that you use thick carpet. If you don't, the ball will
not be stopped enough and the game experiences will be very poor.