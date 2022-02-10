---
title: Game controller
layout: default
mathjax: true
permalink: /game-controller
---

<div class="text-center">
    <a class="btn btn-secondary" href="/install-windows">
        <img src="/assets/imgs/win.png" width="24" />
        Install (Windows) &raquo;
    </a>
    <a class="btn btn-secondary" href="/install-linux">
        <img src="/assets/imgs/linux.png" width="24" />
        Install (Linux) &raquo;
    </a>
</div>

## Starting

Once you've installed the Python package, paired the robots and the camera, you can start the game controller. You
should see such a message appearing:

```
[INFO] 2022-02-02 15:49:54,117 - robot-soccer-kit - Starting robot-soccer-kit Game Controller
[INFO] 2022-02-02 15:49:54,119 - waitress - Serving on http://127.0.0.1:7070
```

Meaning that the game controller is now running and serving at a local web server on port 7070. If it is not already
opened, a browser should appear with the game controller's interface:

<div class="text-center">
    <img src="/assets/imgs/game_controller.png" />
</div>

## Configuring vision

To configure the vision, first select your camera in the list. If you plug/unplug new cameras while the software is
running, press "Refresh cameras" button.

Once you've selected the camera, click "Start" to start the capture.

You can adjust several parameters vision using the interface. The image will be annotated with the output from the
detection.

For good games quality, you should aim at reaching about 30 FPS for detection.

## Configuring robots

First, add your COM ports in the manager and just wait to check if the robots are responding. When they do, they emit
a small beep and their battery level becomes available in the interface.

You can then assign them the corresponding marker, or alternatively click the "Identify" button that will get them
moving a little bit to auto-assign the markers to them.

## Allowing API control

In the "Control" tab, you can allow or disallow the control of robots through API/clients (see below). By default, the
control boxes are ticked, allowing the control for both teams.

If you fill the "key" field with a value, it will become a key (a password) required by the teams that want to control
their robots (preventing teams to control opponent robots).

If you press the "emergency" button, all the robots will stop moving, and the control boxes will be un-ticked
automatically to prevent the clients to send some controls for the robot.
