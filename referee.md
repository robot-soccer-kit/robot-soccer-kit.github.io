---
title: Referee
layout: default
mathjax: true
permalink: /referee
---

# Referee rules

At the beginning of a match (after clicking on "Start Game") the referee is able to take control of the operation of the robots as soon as the need arises. This therefore means that each time the referee takes over, you will no longer be able to control the robots during this period of time and any attempt to control the robots will result in an exception explaining globally why you cannot control the robots. 

A global presentation of the different cases of what will be called "preemption" of robots (when the referee takes control of robots) is therefore made below:

1. When starting a match, the referee waits for the ball to be placed in the center of the field for at least 1s to start the match. (**game start**)

1. Robots cannot get out of the grass, if they try to get out they will be automatically redirected inside the grass. (**out-of-game-‘nameofrobot’**)

1. If the ball leaves the field (white lines) the game is then paused and the referee waits for the ball to be placed on the neutral point closest to the exit zone. As soon as the referee waits for a ball to be placed back on the court, an orange circle appears on the image, representing the area where the ball must be placed. (**sideline-crossed**)

1. If a goal is scored by a team, a notification appears in the refereeing history, and requests a manual validation of the goal by the referee. (**goal**)
    - If the goal is validated, the robots go back to the start of the match position, then wait for the ball to be returned to the center of the field to restart the match.
    - If the goal is invalidated, the match resumes instantly, just after clicking "cancel".
<br><br>

1. If there is more than one robot from the same team in the defending area, the robot being geometrically closest to the center of the field will be penalized for 5s. (**penalty-‘nameofrobot’ + abusive_defense**)

1. If a robot enters the opponent's defense zone, it will be penalized for 5s in the same way as for the previous point. (**penalty-‘nomdurobot’ + abusive_attack**)

1. If a robot stays more than 3s within a 25cm radius of the ball, then it will be penalized for 5s. (**penalty-‘nameofrobot’ + ball_abuse**)

1. If the referee operator judges that a robot should be penalized, he can manually penalize it by 5s or more by clicking one or more times on the ![5s button](/assets/imgs/5s.png "5s button") button of the corresponding robot. He can also unpenalize it by clicking on ![cancel button](/assets/imgs/cancel.png "cancel button") . (**penalty-‘nameofrobot’ + manually penalized**)

1. The robot is preempted throughout the half-time, so it is not possible to communicate with it during this time. (**half-time**)

*When a robot is "penalized", it means that it is sent off the field, closest to where it committed the fault.*

# Access to referee information ![image](/assets/imgs/referee-dict.png "5s button"){: style="float: right; margin-left: 1em; width: 35%"}


All current match information is available in a "referee" dictionary which can be accessed directly from the client with the following command: client.referee

You can see opposite a print of the dictionary during a match.

For example, to access the dictionary entry that lets you know if *robot 1* of the *blue team* is *penalized*, just enter the following command:
```python
client.referee["teams"]["blue"]["robots"]["1"]["penalized"]
```

which in the case of the example returns: `False`

In this dictionary you have access to information to know if a robot is preempted as well as to know the reason of this preemption.
In addition, you can also know if a robot is penalized and know the reason of this penalty.

In the [previous part](#referee-rules), you will find at the end of each paragraph, in bold, the name of the corresponding preemption/penalty.
