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

|  Board     |   Weight (in gms)  | Open Source Firmware  |  FPV  |  Autonomous Functionality  |  Typical Frame Size  |  Popularity  |  Processor  |
| ---------  |  ----------------  |  -------------------  |  ---  |  ------------------------  |  ------------------  |  ----------  |  ---------  |
|            |      39            | ArduPilot, PX4        |  Yes  |         Yes                |   82 x 16 x 50 mm    |   High       | 32          |   
| Pixhawk    |                    |                       |       |                            |                      |              |             |
|            |                    |                       |       |                            |                      |              |             |
|  OpenPilot |       9            |  CleanFlight,         |  Yes  |                            |                      |              | 32          |
|    CC3D    |                    |  BetaFlight,          |       |         Yes                |   40 x 40 x 18       |  High        |             |
|            |                    |   ArduPilot           |       |                            |                      |              |             |
|            |                    |                       |       |                            |                      |              |             |
|  Navio2    |       23           |  ArduPilot,           |  No   |         Yes                |   55 x 65 mm         |              |  32         |
|            |                    |  PX4                  |       |                            |                      |  Medium      |             |
|            |                    |                       |       |                            |                      |              |             |







