---
title: Electronics and firmware
layout: default
mathjax: true
permalink: /electronics
---

The robots board files can can be found on the [GitHub project](https://github.com/robot-soccer-kit/robot-soccer-kit/tree/master/electronics/), current revision is `rev2`. This board is also the base support frame for the robots.

<div class="alert alert-warning">
    Please, note that this section is only relevant for people wanting to build their own kit from scratch,
    or to dig further in the design details. If you have a kit and want to program the robots using Python,
    you can skip this part.
</div>

<img src="/assets/imgs/pcb.png" width="200" style="float:right;z-index:1000000" />

## Links

* [Schematics](https://github.com/robot-soccer-kit/robot-soccer-kit/raw/master/electronics/schematics.pdf)
* [Components (full BOM)](https://github.com/robot-soccer-kit/robot-soccer-kit/raw/master/electronics/rev2/BOM.xlsx)
* [Gerber files](https://github.com/robot-soccer-kit/robot-soccer-kit/raw/master/electronics/rev2/rsk-rev2.zip)
* [Eagle files](https://github.com/robot-soccer-kit/robot-soccer-kit/tree/master/electronics/rev2)
* [Firmware sources](https://github.com/robot-soccer-kit/robot-soccer-kit/tree/master/firmware)

## Firmware

Robot's firmware can be found in the [firmware/](https://github.com/robot-soccer-kit/robot-soccer-kit/tree/master/firmware)
directory of the GitHub repository.

You first need to install [PlatformIO](https://platformio.org/), that is used to bring you the full build chain,
along with the tools required to flash the robot. Simply run:

```bash
pio run
```

In the `firmware/` directory to start the build. And:

```bash
pio run -t upload
```

To start uploading your firmware on the robot (via USB).

<div class="alert alert-info">
    You might want to check the
    <a href="https://github.com/robot-soccer-kit/robot-soccer-kit/blob/master/firmware/src/config.h">src/config.h</a>
    file to configure the firmware according to your hardware.
</div>

## Commented design

**ESP32 & Bluetooth**

Robots are based on `ESP32-WROOM-32E-N8` micro-controller, featuring *270Mhz* dual-core with *32bit* registers, integrated
*Bluetooth* and *WiFi* controller.

An USB to UART adapter is used (namely `FT232RL-REEL`) to allow direct USB communication for the robot, making it
possible to flash the on-board firmware without additional hardware. An USB type B connector was chosen because it
is robust (in the case you want to do some tests with the robot on the floor and the USB cable plugged).

<div class="alert alert-info">
    USB connection is only useful to flash the robot. In a normal pedagogical sequence, there is no need fo USB
    at all, since the programming for the robots behaviours actually happens in the PC controlling them by
    Bluetooth.
</div>

<center>
    <a href="/assets/imgs/schematics/page1.svg" target="_blank"><img src="/assets/imgs/schematics/page1.svg" width="500" /></a>
</center>

**Power**

Robots are designed to be powered by a 2-cells lithium ion battery, through the on-board Jack 2.35mm barrel connector.
To avoid short-circuits or battery under-discharge, the board features a `S-8252AAL-M6T1U` battery protection IC.

When the battery voltage drops too low, the robot will first blink red and start beeping (which is the behaviour
from its firmware), and eventually the BMS will cut the power.

In case of shortcut, the BMS will cut the power as well, you'll have to turn the robot off and on again to get it
restarting.

<center>
    <a href="/assets/imgs/schematics/page2.svg" target="_blank"><img src="/assets/imgs/schematics/page2.svg" width="500" /></a>
</center>

**Buzzer**

The buzzer is controlled by the micro-controller through an NPN transistor:

<center>
    <a href="/assets/imgs/schematics/page3.svg" target="_blank"><img src="/assets/imgs/schematics/page3.svg" width="250" /></a>
</center>

**Leds**

The board features 6 RGB LEDs (3 on the top and 3 on the bottom) that can be controlled individually.
They are sold under the name `COM-16346` or `WS2812B`.

Only one wire is necessary to control them all. The [FastLED](https://fastled.io/) library is used for that purpose.

<center>
    <a href="/assets/imgs/schematics/page4.svg" target="_blank"><img src="/assets/imgs/schematics/page4.svg" width="600" /></a>
</center>

**H bridges**

Robots features `TB67H450FNG,EL` all-in-one motor drivers. Those IC come with integrated mosfets, mosfet drivers and
current limiting features offering another protection against short-circuits.

<center>
    <a href="/assets/imgs/schematics/page5.svg" target="_blank"><img src="/assets/imgs/schematics/page5.svg" width="500" /></a>
</center>

**Booster (Kicker)**

To kick, the voltage is elevated to 20V using a `MT3608` step-up converter. Two 25V 2200µF are then loaded, through a
270 ohm resistor to limit the current rush.

The kick consist in releasing all the current in a solenoid through a power 

<center>
    <a href="/assets/imgs/schematics/page6.svg" target="_blank"><img src="/assets/imgs/schematics/page6.svg" width="600" /></a>
</center>