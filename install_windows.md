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

## Camera

Simply plug the camera on your computer's USB, it should work natively.
