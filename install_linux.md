---
title: Linux installation and setup
layout: default
mathjax: true
permalink: /install-linux/
---

## Installing Python

Use the following command to install python3 and pip packages manager:

```bash
sudo apt-get install python3 python3-pip
```

## Installing `robot-soccer-kit` package

If you want to install only the client, run:

```bash
# Client only
pip install -U robot-soccer-kit
```

If you also want the game controller:

```bash
# Full (with game controller)
pip install -U robot-soccer-kit[gc]
```

## Running the Game Controller

To run the game controller: enter the following command:

```bash
python -m rsk.game_controller
```

## Camera

Simply plug the camera on your computer's USB, it should work natively.
