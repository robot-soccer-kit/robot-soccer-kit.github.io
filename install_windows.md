---
title: Windows installation and setup
layout: default
mathjax: true
permalink: /install-windows/
---

## Installing Python

You need to have Python version 3.8 or newer.

* You can install Python from the [Windows Store](https://www.microsoft.com/store/productId/9NRWMJP3717K?hl=fr-fr&gl=fr)
* Or download the [installer for Python 3.11](https://www.python.org/ftp/python/3.11.6/python-3.11.6-arm64.exe)

## Installing/Updating `robot-soccer-kit` package (Windows scripts)

You can download the following repository:

* [Download installer scripts (Getting started)](https://github.com/robot-soccer-kit/getting-started/archive/refs/tags/getting-started-v1.0.3.zip)

Then, un-zip it, and run:

* `install.bat` to start installing Python package (with Game Controller and Simulator)
* `install_client.bat` to start installing Python package (client only)
* `game_controller.bat` to run the Game Controller with the real system
* `simulator.bat` to run the Game Controller with the simulated environment


## Installing IDE (Integrated Development Environment)

* You can install VSCode (Visual Studio Code) from the [Windows Store](https://apps.microsoft.com/store/detail/XP9KHM4BK9FZ7Q?hl=fr-fr&gl=fr)
* Or download the [installer for VSCode](https://code.visualstudio.com/)

## Installing/Updating `robot-soccer-kit` package (command lines)

If you use the *Getting started* scripts, you can skip this section. Here are the command lines that are
actually run by

*Note: If `python` command is not working, use `py` instead*

If you want to install only the client, run:

```bash
python -m pip install -U robot-soccer-kit
```

If you also want the game controller and the simulator:

```bash
python -m pip install -U robot-soccer-kit[gc]
```

## Running the Game Controller

To run the game controller with the real system: enter the following command:

```bash
python -m rsk.game_controller
```

To run the game controller with the simulated environment: enter the following command:

```bash
python -m rsk.game_controller -s
```

## Pairing the robots

We recommend using USB external [ZEXMTE Bluetooth adapter](https://amzn.eu/d/7ykCiar). On Windows,
the drivers are automatically installed from internet.

If you already have native Bluetooth on your computer, you can give it a try. If it doesn't work well, don't forget
to disable it before using the USB dongle by going to "Devices Manager".

To pair the robots, simply go to your Bluetooth menu and pair them one by one. If you encounter issues, do not hesitate
to disable and re-enable your Bluetooth.

*Note: default Bluetooth PIN for robots is always 1234. (No PIN is required for robots named "RSK")*

*Note 2: You will NOT have to pair the robots again after each restart of your computer, only if you bring in new robots.*

### Step-by-step pairing

Click on 


## Camera

Simply plug the camera on your computer's USB, it should work natively.