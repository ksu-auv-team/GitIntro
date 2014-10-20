Thruster Control
================

Forward
-------
The thrusters on the SPSU AUV Vehicle are controled through the `rosserial-python` node.
The node relays `spsu-auv-core/ArdMPower` messages to the microcontroller onboard the Hercules motor drivers.
The format of the message is as follows:
```
int16 left
int16 right
int16 front
int16 back
int16 top
int16 bottom
```
There are three Hercules motor drivers onboard the vehicle.
Each driver controls one set of thrusters: vertical, horizontal, and strafing.

Command-Line Control
--------------------


Knowledge Required | Estimated Time
---|---
Basic ROS, Basic Electric | 5 Minutes


To control the thrusters via command line, your shell(s) must be connected to a running ROS master.
Also a `rosserial-python` instance must be running and configured for each Hercules driver you want to control.
The `rosserial-python` nodes must run on the same computer that the Hercules drivers are connected to.
After everything is set up you can run the following command, replacing the values (currently 0) with the power percentage you want to use (-100 - 100).
```Bash
rostopic pub /ard_motors spsu_auv_core/ArdMPower "{left: 0, right: 0, front: 0, back: 0, top: 0, bottom: 0}"
```
