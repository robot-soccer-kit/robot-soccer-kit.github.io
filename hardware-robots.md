---
title: Robots
layout: default
mathjax: true
permalink: /hardware-robots
---

<div class="text-center mb-2">
    <img src="/assets/imgs/robot_green1.svg" width="200" />
    <img src="/assets/imgs/robot_green2.svg" width="200" />
    <img src="/assets/imgs/robot_blue1.svg" width="200" />
    <img src="/assets/imgs/robot_blue2.svg" width="200" />
</div>

<div class="alert alert-secondary text-center">
    <img src="/assets/imgs/onshape.png" width="32"/>
    <a href="https://cad.onshape.com/documents/c5fe05581d14c59bfb08f79e/w/a8cb82e3a358c0b06e1cbf91/e/f45372d8263c18466905bd9b?renderMode=0&uiState=616d8b41f463de7ef1eedc0f">
        See the full robot 3D assembly (OnShape)
    </a>
</div>

# Structure

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
            <img src="/assets/imgs/frame.png" width="128" /><br/>
        </td>
        <td>
            Robot frame
        </td>
        <td>
            The robot frame can be cut in 3mm MDF or PMMA
            <ul>
            <li>
            <a href="https://github.com/robot-soccer-kit/robot-soccer-kit/raw/master/mechanics/frame.dxf">
                <code>frame.dxf</code>
            </a>
            </li>
            </ul>
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
            The marker part can be cut in 3mm MDF or PMMA
            <br/>
            Then, print the relevant robot markers and stick them on it.
            <ul>
            <li>
            <a href="https://github.com/robot-soccer-kit/robot-soccer-kit/raw/master/mechanics/marker.dxf">
                <code>marker.dxf</code>
            </a>
            </li>
            <li>
            <a href="/coordinates-field-markers#robots">
                Robot markers
            </a>
            </li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>
            <img src="/assets/imgs/pcb.png" width="128" /><br/>
        </td>
        <td>
            Mainboard
        </td>
        <td>
            Mainboard assembled PCB
            <br/>
            <a href="/electronics">Click here for more details on electronics</a>
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
                <li>
                    Those screws are used to fix the motors
                    <ul>
                        <li>6x M3x30</li>
                        <li>6x M3x8 female-male spacer</li>
                        <li>6x M3x20 female-male spacer</li>
                        <li>12x M3 nuts</li>
                    </ul>
                </li>
                <li>
                    All around the board, we use spacers to protect the robot
                    <ul>
                        <li>10x M3x30 female-male spacer</li>
                        <li>10x M3x8</li>
                    </ul>
                </li>
            </ul>
        </td>
    </tr>
</table>

# Motors and wheels

<table class="table table-striped table-responsive">
    <tr>
        <td>
            <img src="/assets/imgs/n20.png" width="128" /><br/>
        </td>
        <td>
            <kbd>GA12-N20</kbd>
            <br/>
            <small><code>
            rated 6V<br/>
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
            <img src="/assets/imgs/coupler.png" width="128" /><br/>
        </td>
        <td>
            Motor couplers
        </td>
        <td>
            Those couplers have internal diameter of 3mm, the small part of the ring is 10mm, the
            big part is ~22mm and the screw spacing is 16mm.
        </td>
    </tr>
    <tr>
        <td>
            <img src="/assets/imgs/wheel-parts.png" width="128" /><br/>
        </td>
        <td>
            3D parts
        </td>
        <td>
            <b>Option 1</b>, use FDM 3D printer and print the following:
            <ul>
                <li>
                3x
                <a href="https://github.com/robot-soccer-kit/robot-soccer-kit/blob/master/mechanics/wheel1.stl">
                    Half-wheel part1 (wheel1.stl)
                </a>
                </li>
                <li>
                3x
                <a href="https://github.com/robot-soccer-kit/robot-soccer-kit/blob/master/mechanics/wheel2.stl">
                    Half-wheel part2 (wheel2.stl)
                </a>
                </li>
                <li>
                3x
                <a href="https://github.com/robot-soccer-kit/robot-soccer-kit/blob/master/mechanics/motorbox_top.stl">
                    Motorbox-top (motorbox_top.stl)
                </a>
                </li>
                <li>
                3x
                <a href="https://github.com/robot-soccer-kit/robot-soccer-kit/blob/master/mechanics/motorbox_bottom.stl">
                    Motorbox-bottom (motorbox_bottom.stl)
                </a>
                </li>
            </ul>
            <b>Option 2</b>, print 
            <a href="https://github.com/robot-soccer-kit/robot-soccer-kit/blob/master/mechanics/stack.stl">
            this pack using SLS
            </a>
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
                <li>30x M3x8 screws</li>
                <li>30x M3 nuts</li>
                <li>60x M3x6 cylindrical shaft</li>
            </ul>
            <a href="https://cad.onshape.com/documents/beccbfab729802507eb805eb/w/cfcb9ed7f156d2b4ab0a6a83/e/76e58097a54be25b6c68caca?explodedView=MKC8py8%2FfMHkcshYX&renderMode=0&rightPanel=explodedViewPanel&uiState=620185090f3755693d197f24">See the 3D view</a>
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
            60x O-ring for passive wheels, those are optional (without them it works as well)
        </td>
    </tr>
</table>

# Kicker

<table class="table table-striped table-responsive">
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
            <img src="/assets/imgs/kicker_tip.png" width="128" /><br/>
        </td>
        <td>
            Kicker tip
        </td>
        <td>
        Can be cut using laser cutter out of MDF or PMMA:
            <ul>
                <li>
                <a href="https://github.com/robot-soccer-kit/robot-soccer-kit/raw/master/mechanics/kicker_tip_1.dxf">
                <code>kicker_tip_1.dxf</code>
                </a>
                : Front for laser, requires engraving for the nut
                </li>
                <li>
                <a href="https://github.com/robot-soccer-kit/robot-soccer-kit/raw/master/mechanics/kicker_tip_1.step">
                <code>kicker_tip_1.step</code>
                </a>
                : Front for CNC
                </li>
                <li>
                <a href="https://github.com/robot-soccer-kit/robot-soccer-kit/raw/master/mechanics/kicker_tip_2.dxf">
                <code>kicker_tip_2.dxf</code>
                </a>
                : Bottom
                </li>
            </ul>
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
                <li>2x M3x4 screws</li>
                <li>2x M3 lockwasher</li>
                <li>2x M3 square nuts DIN 562</li>
            </ul>
        </td>
    </tr>
</table>

# Powering

<table class="table table-striped table-responsive">
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
            Holder for 2x18650 batteries with jack 2.35mm output
        </td>
    </tr>
</table>
