# Aerothon-cse
## Overview : 

We, the Control System team, work on the simulation and the software system that allows our quadcopter to be controlled remotely and operable autonomously. 
Our mission is to provide a robust, reliable and modular software elements to implement different functions of our drone that enables basic flight, fail safes, payload delivery and autonomy. Using concepts of we tailor each of the algorithms to achieve stable and time efficient flight.




## Hardware and Firmware : 

We analyzed some of top drone controllers of the market by gathering information for factors like:
1. Affordability
2. Open Source Firmware
3. FPV Racing friendly
4. Autonomous functionality
5. Linux or microcontroller based environment
6. Typical frame size
7. Popularity (Higher popularity means more online resources and help)
8. Processor




                                                                 COMPARING BOARDS 

|  Board        |   Weight (in gms)  | Open Source Firmware                |  FPV  |  Autonomous Functionality  |  Typical Frame Size  |  Popularity  |  Processor  |
| ---------     |  ----------------  |  -------------------                |  ---  |  ------------------------  |  ------------------  |  ----------  |  ---------  |
|  Pixhawk      |      39            | ArduPilot, PX4                      |  Yes  |         Yes                |   82 x 16 x 50 mm    |   High       | 32          |   
|     CC3D      |       9            |  CleanFlight,BetaFlight,ArduPilot   |  Yes  |         Yes                |   40 x 40 x 18       |   High       | 32          |
|  Navio2       |       23           |  ArduPilot,PX4                      |  No   |         Yes                |   55 x 65 mm         |   Medium     |  32         |
|               |                    |                                     |       |                            |                      |              |             |


                                                          
                                                          
                                                          
   COMPARING ArduPilot and PX4
                                                                                                                 

  | Specifications  |  ArduPilot    |  PX4  |
  |:---             |:---           |:---   |
  |License          |  GPL          |  BSD  |
  | Sources         |  Open-Source  | Open-Source|
  | Form-Factor     | High          |High   |
  




**The main difference between Ardupilot and PX4 arises in License Factor. GPL ( General Public License) is a copy left open-source license. This means that all derivatives of Ardupilot must also be released in GPL. Where PX4 is BSD (Berkeley Source Distribution) for which we don't have to openly release the source.**





***Based on the above data, we've decided to use Pixhawk along with PX4***

# Features of drone
3
R C Controlled : 
4
​
5
1. Throttle
6
2. Pitch 
7
3. Yaw
8
4. Altitude hold
9
5. Hover
10
6. Geographical fence
11
​
12
<br>
13
​
14
> **1. Throttle**
15
​
16
<br>
17
​
18
Throttle is just a upward (or downward) movment of quadcopter which can be achived by increasing (or decreasing) all the propeller speeds by the same amount. It leads to a vertical force with respect to body-fixed frame which raises or lowers the quad-rotor.
19
```
20
 arm_and_takeoff(aTargetAltitude): #Arms vehicle and fly to aTargetAltitude.
21
    # Don't let the user try to arm until autopilot is ready
22
 print("Basic pre-arm checks")
23
 while not vehicle.is_armable:
24
  print(" Waiting for vehicle to initialise...")
25
  time.sleep(1)
26
 print("Arming motors")
27
    # Copter should arm in GUIDED mode
28
 vehicle.mode = VehicleMode("GUIDED")
29
 vehicle.armed = True
30
 
31
 while not vehicle.armed:      
32
   print(" Waiting for arming...")
33
   time.sleep(1)
34
​
35
 print("Taking off!")
36
   vehicle.simple_takeoff(aTargetAltitude) # Take off to target altitude
37
​
38
 while True:
39
   print(" Altitude: ", vehicle.location.global_relative_frame.alt)      
40
      if vehicle.location.global_relative_frame.alt>=aTargetAltitude*0.95: #Trigger just below target alt.
41
         print("Reached target altitude")
42
         break
43
   time.sleep(1)

