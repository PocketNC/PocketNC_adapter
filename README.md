# PocketNC_adapter
An implementation of the PocketNC adapter.

Quickstart
----------

ssh to the PocketNC.

```
git clone https://github.com/PocketNC/PocketNC_adapter
sudo systemctl enable /home/pocketnc/PocketNC_adapter/mtconnect.service
sudo reboot
```

This will start the MTConnect server on port 7878 when the Pocket NC powers back up.

Introduction
------------
A python adapter "adapter.py" for PocketNC is shared which provides an interface for the PocketNC to become MTConnect compliant. The adapter allows the use of MTConnect agent to make the PocketNC MTconnect compliant. The steps to install and implement MTConnect agent can be found at https://github.com/mtconnect/cppagent. This adapter was developed and tested on a PocketNC v1.

Implementation
--------------
Download the files in the beaglebone black Debian OS of PocketNC. update the port information in the "adapter.py" to the port number available on your device.

`PORT = 7878`

Once the information in the "adapter.py" file is updated, this python script needs to be used as a service so that the adapter is active everytime the PocketNC is powered on. In order to enable this enter the following code in the beaglebone terminal:

`sudo systemctl enable /home/pocketnc/PocketNC_adapter/mtconnect.service`

Next time when the PocketNC is restarted, the adapter will be running as a service behind the scenes.

For implementation of the MTConnect agent, the steps are clearly defined on the MTConnect agent github repository (https://github.com/mtconnect/cppagent). The "PocketNC.xml" can be used as device file for the MTConnect agent.

DataItems
---------
Following Data Items have been included in the adapter:

1.  Accumulated Time : Total Time
2.  Accumulated Time : Auto Time
3.  Accumulated Time : Cut Time
4.  Absolute X position
5.  Absolute Y position
6.  Absolute Z position
7.  Absolute A position
8.  Absolute B position
9.  Rotary Velocity 
10. Emergency Stop
11. Execution State
12. Power State
13. Line
14. Program
15. Path Feed Override
16. Spindle Feed Override
17. Tool Number
18. Controller Mode

MTConnect
---------
For more information on the MTConnect standard and the dataitems included within the standard please visit
http://www.mtconnect.org/

PocketNC
---------
The PocketNC is a desktop 5-axis CNC mill. This project is not affiliated with the PocketNC Company. Please visit
http://www.pocketnc.com/
