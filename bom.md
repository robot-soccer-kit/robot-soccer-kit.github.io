---
title: Bill of materials
layout: default
mathjax: true
permalink: /bom
---

<div class="alert alert-danger">
    Disclaimer: this is a WORK IN PROGRESS, not everything is yet well documented, and some parts are still
    evolving, do not try to build this for now
</div>

## Robots

Below is the list of items for one robot:

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
                <li>6x M3x15 female-male spacer</li>
                <li>12x M3 nuts</li>
            </ul>
            Here, M3 nuts are used on the top of M3x15 spacers so that the spacer is both longer and doesn't
            damage the marker sheet after getting through the 3mm of that part.
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
            <img src="/assets/imgs/jst-zh-cable.png" width="128" /><br/>
        </td>
        <td>
            Motor cables
        </td>
        <td>
            3x JST-ZH cables, 6 pins, length: 5cm
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
            <img src="/assets/imgs/bearing.png" width="128" /><br/>
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
            <br/>
            Then, print the relevant <a href="/coordinates-field-markers">markers</a> and stick them on it.
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
    <tr>
        <td>
            <img src="/assets/imgs/18650.png" width="128" /><br/>
        </td>
        <td>
            <kbd>18650 VT6</kbd>
        </td>
        <td>
            2x 18650 batteries
        </td>
    </tr>
    <tr>
        <td>
            <img src="/assets/imgs/holder.png" width="128" /><br/>
        </td>
        <td>
            2x18650 holder
        </td>
        <td>
            Holder for 2 18650 batteries with jack output
        </td>
    </tr>
</table>

## Setup

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
            <img src="/assets/imgs/field.png" width="128" /><br/>
        </td>
        <td>
            Field
        </td>
        <td>
            <span class="text-danger">It must be made of a thick carpet, so that the ball is stopped enough.
            Else, the game experience will be very poor.</span>
            <br/>
            You can buy a thick green carpet of 2x2.5m, paint it, and print and stick
            <a href="/coordinates-field-markers">field markers</a>.
        </td>
    </tr>
    <tr>
        <td>
            <img src="/assets/imgs/spedal.png" width="128" /><br/>
        </td>
        <td>
            <kbd>Spedal MF920Pro</kbd>
            <br/>
            <code>
            1080p<br/>
            30fps<br/>
            120° angle
            </code>
        </td>
        <td>
            You can source other cameras, but the opening angle should be wide enough to see the whole field
        </td>
    </tr>
    <tr>
        <td>
            <img src="/assets/imgs/balls.png" width="128" /><br/>
        </td>
        <td>
            PU Orange ball
        </td>
        <td>
            Those are golf-size balls made of some foam material called PU. It weights around 8g.
        </td>
    </tr>
    <tr>
        <td>
            <img src="/assets/imgs/zexmte.png" width="128" /><br/>
        </td>
        <td>
            ZEXMTE Bluetooth adapter
        </td>
        <td>
            You can give a try to your computer integrated Bluetooth, but there are chances that the quality
            of communication will not be good enough. This dongle was tested to work well with the kit.
        </td>
    </tr>
    <tr>
        <td>
            <img src="/assets/imgs/extension.png" width="128" /><br/>
        </td>
        <td>
            3m USB extension
        </td>
        <td>
            The camera will be attached to the field structure, so you need an extension cable to connect it
            to your computer. 3m is a good length.
        </td>
    </tr>
    <tr>
        <td>
            <img src="/assets/imgs/field.png" width="128" /><br/>
        </td>
        <td>
            PVC tubes
        </td>
        <td>
            For the field structure, you can use PVC tubes, we recommend (all 50mm diameter):
            <ul>
                <li>2x 50cm tube</li>
                <li>6x 100cm tube</li>
                <li>5x L-shape connector</li>
                <li>3x T-shape connector</li>
                <li>2x female-female extension connector</li>
            </ul>
        </td>
    </tr>
</table>