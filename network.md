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

The WiFi network **must be 2.4Ghz**.

Even if any network configuration could be used, we here propose a convention for everyone to follow.
By default, the game controller will use `192.168.100.0` as network, with the subnet mask  `255.255.255.0`.
If you want to use another network/subnet, please provide them explicitly while running the game controller as follow:

```bash
# Providing explicit network and subnet
python -m rsk.game_controller \
       --wifi-network 192.168.1.0 \
       --wifi-subnet 255.255.255.0
```

# Single WiFi network

Here is the proposed network configuration when using only one router:

<center>
<a href="/assets/imgs/network.svg" target="_blank">
<img src="/assets/imgs/network.svg" width="80%" />
</a>
</center>

<div class="alert alert-info">
<b>Notes</b>:
<ul>
<li>
IP address of the robots are set in the
<a href="https://github.com/robot-soccer-kit/robot-soccer-kit/blob/master/firmware/src/config.h">firmware</a>.
They don't have to be the one specified above since the robots are auto-discovered by the Game Controller.
SSID and password are also set in the firmware and should match the Robot Soccer Kit network router configuration.
</li>
<li>
Although the Game Controller can use DHCP, it is recommended to set it to a static IP address to make it easier
to connect to it.
</li>
</ul>
</div>

<div class="alert alert-warning">
<b>Drawbacks</b>:
<ul>
<li>
With this setup, the robots and the end users are on the same network. This means that the users can communicate
directly with the robots via UDP. This can lead to security issues or misuses.
</li>
<li>
If we want to use this setup in a classroom, it implies that the router will be connected to the school network.
This is in general not allowed.
</li>
</ul>
</div>

# Dual-network Game Controller

In the setup below, the Game Controller is connected to two networks: the Robot Soccer Kit network and an
external network. It requires the Game Controller to have two network interfaces.

<center>
<a href="/assets/imgs/dual_network.svg" target="_blank">
<img src="/assets/imgs/dual_network.svg" width="80%" />
</a>
</center>

<div class="alert alert-info">
<b>Note</b>:
In a classroom, an easy way to achieve this is to add a USB-to-Ethernet adapter to the Game Controller for the
"RSK ethernet" interface. The "external ethernet" interface represents the school interface that is already
present.
</div>

# NAT bridge 

Another solution is to use a NAT bridge.
The concept is simply to wire the Robot Soccer Kit router to an external network, and use the port forwarding feature
to forward TCP ports ``7557`` and ``7558`` to the Game Controller.

This way, the users will be able to communicate with the Game Controller, by using the IP address of the
Robot Soccer Kit router.

<center>
<a href="/assets/imgs/2network.svg" target="_blank">
<img src="/assets/imgs/2network.svg" width="80%" />
</a>
</center>

<div class="alert alert-info">
<b>Note</b>: The Robot Soccer Kit router can be set to DHCP on the WAN interface, but it is advised to set it to a
static IP address to make it easier to connect to it.
</div>
