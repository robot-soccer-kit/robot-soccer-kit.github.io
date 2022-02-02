---
title: Robots design and electronics
layout: default
mathjax: true
permalink: /robots/
---

**Disclaimer: robots used in Robot Soccer Kit are a fork of a previous project (holo). Current prototypes
were hacked to add a kicker. In the future, this kicker will be integrated in the robot itself,
this is STILL A WORK IN PROGRESS**

<div class="text-center">
    <img src="/assets/imgs/robots.jpg" />
</div>

<div class="alert alert-secondary m-3 text-center">
    <img src="/assets/imgs/onshape.png" width="32" />

    <a target="_blank" href="https://cad.onshape.com/documents/c5fe05581d14c59bfb08f79e/w/a8cb82e3a358c0b06e1cbf91/e/f45372d8263c18466905bd9b?renderMode=0&uiState=616d8b41f463de7ef1eedc0f">
        The full robot CAD can be found here (OnShape)
    </a>
</div>

## Items

<table class="table table-striped table-responsive">
    <tr>
        <th>
        Part
        </th>
        <th style="min-width:25%">
        Reference
        </th>
        <th>
        Comment
        </th>
    </tr>
    <tr>
        <td>
            <img src="/assets/imgs/pcb.png" width="128" /><br/>
        </td>
        <td>
            Mainboard
        </td>
        <td>
            <a href="https://github.com/robot-soccer-kit/robot-soccer-kit/tree/master/electronics">
            Mainboard assembled PCB
            </a>
        </td>
    </tr>
    <tr>
        <td>
            <img src="/assets/imgs/screws.png" width="128" /><br/>
        </td>
        <td>
            Structural screws
        </td>
        <td>
            <ul>
                <li>6x M3x35</li>
                <li>6x M3x10 female-female spacer</li>
                <li>6x M3x8 female-male spacer</li>
                <li>6x M3x20 female-male spacer</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>
            <img src="/assets/imgs/n20.png" width="128" /><br/>
        </td>
        <td>
            <kbd>GA12-N20</kbd>
            <br/>
            <small><code>
            1:210 reduction<br/>
            Hall encoders (7 CPR)<br/>
            6p JST-ZH connector
            </code></small>
            <br/>
        </td>
        <td>
            3x motors
            <br/>
            <small><em>
            The current reduction trade-off offers a high torque and the speed of the robots are thus limited.
            This is however not an issue in adversarial game where precision counts more than velocity.
            </em></small>
        </td>
    </tr>
    <tr>
        <td>
            <img src="/assets/imgs/hc-05.png" width="128" /><br/>
        </td>
        <td>
            <kbd>HC-05</kbd>
        </td>
        <td>
            HC-05 modules are soldered on the robot PCB and allowing Bluetooth to on-board UART communication.
        </td>
    </tr>
    <tr>
        <td>
            <img src="/assets/imgs/wheel-parts.png" width="128" /><br/>
        </td>
        <td>
            Wheel 3D parts
        </td>
        <td>
            3x 
            <a href="https://cad.onshape.com/documents/beccbfab729802507eb805eb/w/eea13ac7371464cd172aefcf/e/76e58097a54be25b6c68caca?renderMode=0&uiState=616d8c2f00cc7207a3c8ae7b">3D printed parts</a>
            <br/>
            <small>
                <a href="https://github.com/robot-soccer-kit/robot-soccer-kit/raw/master/mechanics/stack_collet_tied_export.stl">
                (packed version for SLS)
                </a>
            </small>
        </td>
    </tr>
    <tr>
        <td>
            <img src="/assets/imgs/screws.png" width="128" /><br/>
        </td>
        <td>
            Wheel screws
        </td>
        <td>
            <ul>
                <li>18x M3x8 screws</li>
                <li>18x M3 nuts</li>
                <li>9x M3x8 screws</li>
                <li>9x M3 square nuts</li>
                <li>60x M3x6 cylindrical shaft</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>
            <img src="/assets/imgs/bearing.jpeg" width="128" /><br/>
        </td>
        <td>
            <kbd>V623ZZ</kbd>
        </td>
        <td>
            60x Bearings for passive wheels
        </td>
    </tr>
    <tr>
        <td>
            <img src="/assets/imgs/oring.png" width="128" /><br/>
        </td>
        <td>
            O-ring<br/>
            <code>
            8mm ID, 2mm thick
            </code>
        </td>
        <td>
            60x O-ring for passive wheels
        </td>
    </tr>
    <tr>
        <td>
            <img src="/assets/imgs/frame.png" width="128" /><br/>
        </td>
        <td>
            Robot frame
        </td>
        <td>
            The <a href="https://github.com/robot-soccer-kit/robot-soccer-kit/raw/master/mechanics/frame.dxf">robot frame</a> can be cut in 3mm MDF or PMMA
        </td>
    </tr>
    <tr>
        <td>
            <img src="/assets/imgs/marker.png" width="128" /><br/>
        </td>
        <td>
            Marker
        </td>
        <td>
            The <a href="https://github.com/robot-soccer-kit/robot-soccer-kit/raw/master/mechanics/marker.dxf">marker</a> can be cut in 3mm MDF or PMMA
        </td>
    </tr>
    <tr>
        <td>
            <img src="/assets/imgs/solenoid.png" width="128" /><br/>
        </td>
        <td>
            <kbd>JF-0530B</kbd>
            <br/>
            <code>6V</code>
            <br/>
        </td>
        <td>
            A small plunger that can be sourced from many online. Used to kick the ball.
        </td>
    </tr>
    <tr>
        <td>
            <img src="/assets/imgs/screws.png" width="128" /><br/>
        </td>
        <td>
            Kicker screws
        </td>
        <td>
            <ul>
                <li>2x M3x5 screws</li>
                <li>2x M3 square nuts DIN 562</li>
            </ul>
        </td>
    </tr>
</table>
