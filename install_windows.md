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

## Installing/Updating `robot-soccer-kit` package

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

<div class="container text-center">
    <button class="btn btn-secondary text-center" type="button" data-bs-toggle="collapse" data-bs-target="#SbS_BL" aria-expanded="false" aria-controls="SbS_BL">
    Step-by-step - Disable intern Bluetooth
    </button>
</div>

<div class="collapse" id="SbS_BL">
    <div class="row text-center justify-content-center">
        <div class="col-6">
            <b>Step 1</b>
            <img class="w-100" src="/assets/imgs/BL-0.jpg" />
        </div>
        <div class="col-6">
            <b>Step 2</b>
            <img class="w-100" src="/assets/imgs/BL-1.jpg"/>
        </div>
    </div>
</div>

To pair the robots, simply go to your Bluetooth menu and pair them one by one. If you encounter issues, do not hesitate
to disable and re-enable your Bluetooth.

*Note: If a Bluetooth PIN is asked it is always 1234. (No PIN is required for robots named "RSK_XX")*

*Note 2: You will NOT have to pair the robots again after each restart of your computer, only if you bring in new robots.*

<div class="container text-center">
    <button class="btn btn-secondary text-center" type="button" data-bs-toggle="collapse" data-bs-target="#SbS_Pairing" aria-expanded="false" aria-controls="SbS_Pairing">
    Step-by-step - Robots Pairing
    </button>
</div>

<div class="collapse" id="SbS_Pairing">
    <div class="row text-center justify-content-center">
        <div class="col-6">
            <b>Step 1</b>
            <img class="w-100" src="/assets/imgs/Pair-0.jpg" />
        </div>
        <div class="col-6">
            <b>Step 2</b>
            <img class="w-100" src="/assets/imgs/Pair-1.jpg" />
        </div>
    </div>
    <div class="row text-center justify-content-center">
        <div class="col-4">
            <b>Step 3</b>
            <img class="w-100" src="/assets/imgs/Pair-2.jpg" />
        </div>
        <div class="col-4">
            <b>Step 4</b>
            <img class="w-100" src="/assets/imgs/Pair-3.jpg" />
        </div>
        <div class="col-4">
            <b>Step 5</b>
            <img class="w-100" src="/assets/imgs/Pair-4.jpg" />
        </div>
    </div>
</div>

## Camera

Simply plug the camera on your computer's USB, it should work natively.