---
title: Network configuration
layout: default
mathjax: true
permalink: /network
---

# Switching to Bluetooth

By default, with latest firmware version, the robots boot to WiFi.
You can switch the Bluetooth by **rotating manually any wheel by more than one turn** (any direction), and this
**before** the robot got any packet from WiFi.
If it is added with a Game Controller, either stop the Game Controller or remove it from the list of rebots.

# Addressing

When flashing the robots, a WiFi network configuration is set in the firmware.
This can be configured in the [config.h](https://github.com/robot-soccer-kit/robot-soccer-kit/blob/master/firmware/src/config.h)
file while building the firmware.

Even if any network configuration could be used, we here propose a convention for everyone to follow.

<div class="alert alert-info">
The WiFi network must be 2.4Ghz
</div>

# Proposed network

Here is the proposed network configuration when using only one router:

<center>
<a href="/assets/imgs/network.svg" target="_blank">
<img src="/assets/imgs/network.svg" width="80%" />
</a>
</center>

<div class="alert alert-info">
<b>Note</b>: IP address of the robots are set in the
<a href="https://github.com/robot-soccer-kit/robot-soccer-kit/blob/master/firmware/src/config.h">firmware</a>.
They don't have to be the one specified above since the robots are auto-discovered by the Game Controller.
SSID and password are also set in the firmware and should match the Robot Soccer Kit network router configuration.
</div>

<div class="alert alert-info">
<b>Note</b>: although the Game Controller can use DHCP, it is recommended to set it to a static IP address to make it easier
to connect to it.
</div>

# Proposed network (separated)

Here are two drawbacks from the previous network configuration:

* In a classroom, where user computers are already on a network, it is unlikely to rewire the whole network to the
Robot Soccer Kit network.
* In the case of a competition, the users should not be able to communicate directly with the robots via UDP.
This would lead to security issues.

To tackle those problems, a slightly more complex architecture can be considered. The concept is simply to wire the
Robot Soccer Kit router to an external network, and use the port forwarding feature to forward TCP ports
``7557`` and ``7558`` to the game controller.

This way, the users will be able to communicate with the Game Controller, by using the IP address of the
Robot Soccer Kit router.

<center>
<a href="/assets/imgs/2network.svg" target="_blank">
<img src="/assets/imgs/2network.svg" width="80%" />
</a>
</center>

<div class="alert alert-info">
<b>Note</b>: again, the Robot Soccer Kit router can be set to DHCP on the WAN interface, but it can also be set as
 a static IP address.
</div>
