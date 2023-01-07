---
title: Windows installation and setup
layout: default
mathjax: true
permalink: /install-windows/
---

## Installing Python

You need to have Python version 3.8 or newer.

* You can install Python from the [Windows Store](https://apps.microsoft.com/store/detail/python-39/9P7QFQMJRFP7?hl=fr-fr&gl=FR)
* Or download the [installer for Python 3.9](https://www.python.org/ftp/python/3.9.0/python-3.9.0-amd64.exe)

## Installing/Updating `robot-soccer-kit` package (Windows scripts)

You can download the following repository:

* [Download installer scripts (Getting started)](https://github.com/robot-soccer-kit/getting-started/archive/refs/tags/getting-started-v1.0.2.zip)

Then, un-zip it, and run:

* `install.bat` to start installing Python package (with Game Controller)
* `install_client.bat` to start installing Python package (client only)
* `game_controller.bat` to run the Game Controller

## Installing/Updating `robot-soccer-kit` package (command lines)

If you use the *Getting started* scripts, you can skip this section. Here are the command lines that are
actually run by

*Note: If `python` command is not working, use `py` instead*

If you want to install only the client, run:

```bash
python -m pip install -U robot-soccer-kit
```

If you also want the game controller:

```bash
python -m pip install -U robot-soccer-kit[gc]
```

## Running the Game Controller

To run the game controller: enter the following command:

```bash
python -m rsk.game_controller
```

## Pairing the robots

We recommend using USB external [ZEXMTE Bluetooth adapter](https://www.amazon.fr/gp/product/B08SC9M9K3/). On Windows,
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