---
title: Programming
layout: default
mathjax: true
permalink: /programming
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

## Getting started

Here is simple example creating a client for the API and getting the robot green1 kicking:

```python
import rsk

with rsk.Client() as client:
    client.green1.kick()
```

Here:

* `import rsk` imports the relevant Python package
* The `with` statement ensures that the client will be properly closed at the end of the session.
  Especially, it forces the robots to stop moving at the end of the program.
* `client.green1.kick()` asks the robot `green1` to kick

When creating a client, you can also provide the following arguments:

```python
import rsk

with rsk.Client(host='127.0.0.1', key='') as client:
    client.robots['green'][1].kick()

```

Where

* `host` is the IP address of the computer running the Game Controller
* `key` is the team access key (by default, blank) that can be set in the Game Controller to prevent a team from
  controlling opponents robots

## Accessing robots

Robots can be accessing using the following syntax:

```python
# Shortcuts to access a robot
client.green1
client.green2
client.blue1
client.blue2

# Full syntax allowing dynamic access
client.robots['green'][1]
client.robots['green'][2]
client.robots['blue'][1]
client.robots['blue'][2]
```

## Localization informations

Localization is polled using a thread and can be continuously accessed through the following variables:

```python
# Robot position (x [m], y [m]):
client.green1.position
# Robot orientation (theta [rad]):
client.green1.orientation
# Position + orientation (x [m], y [m], theta [rad])
client.green1.pose
# Ball's position (x [m], y [m])
client.ball
```

The field frame is detailed in the [coordinates and markers](/coordinates-field-markers) section 

Note: arrays are *numpy array*

## Accessing constants

The module `rsk.constants` provide some useful constants (field dimensions, rules limitations etc.):

```python
from rsk import constants

# Field length (x axis)
constants.field_length
# Field width (y axis)
constants.field_width

# Goal width
constants.goal_width

# Side of the (green) border we should be able to see around the field
constants.border_size
```

See more constants in the [source file](https://github.com/robot-soccer-kit/robot-soccer-kit/blob/master/rsk/constants.py).

## Controlling the robots

### Basic commands

To control the robots, you can use the following functions:

```python
# Kicks, takes an optional power parameter between 0 and 1
robot.kick()

# Controls the robots in its own frame, arguments are x speed [m/s],
# y speed [m/s] and rotation speed [rad/s]

# Go forward, 0.25 m/s
robot.control(0.25, 0., 0.)

# Rotates 30 deg/s counter-clockwise
robot.control(0., 0., math.radians(30))
```

### Handling errors

If a command fails, a `rsk.ClientError` exception will be raised. You can catch it using:

```python
try:
    robot.kick()
    robot.control(0.1, 0, 0)
except rsk.ClientError:
    print('Error during a command!')
```

Such an exception will also happen if the robot you want to control was preempted by the Game Controller.

### Goto

You can also use the `goto` method to send the robot to an arbitrary position on the field:

```python
# Sending a robot to x=0.2m, y=0.5m, theta=1.2 rad
robot.goto((0.2, 0.5, 1.2))
```

Sends the robot to the position `x=0.2`, `y=0.5` and `theta=1.2` on the field.

### Non-blocking goto

You can use the second argument of `goto` (which is `wait`, a *boolean* value) to tell goto not to
block the execution of the program. This way, you can do something else at the same time without threading.
Here is an example placing two robots:

```python
# Placing two robots, the loop will block until both robots are placed
arrived = False
while not arrived:
    robot_1_arrived = client.green1.goto((0.2, 0.3, 0.), wait=False)
    robot_2_arrived = client.green2.goto((0.2, -0.3, 0.), wait=False)
    arrived = robot_1_arrived and robot_2_arrived
```

The second argument of `goto` is a *boolean* (`wait`, default `True`). When `wait` is `True`, the call to `goto` will
block the execution of the program until the robot reaches its destination. When `wait` is `False`, the
`goto` call will return immediately, after updating the instant velocity of the controlled robot, and return
`True` if the robot reached, `False` else.

## Use `on_update` callback

If you want to run some code everytime new information is obtained from the detection, you can register
a method with the `on_update` field in `client`:

```python
def print_the_ball(client, dt):
    print(client.ball)

# This will print the ball everytime a new information is obtained from the client
client.on_update = print_the_ball
```

This can be convenient if you want to log data for further analysis, because you will log all information exactly
once, and once it is received.