# Technical Requirements for a Simulated Competition

## Physics Engine

There needs to be a realistic physics model which can:

* Plausible boat speeds for a given sail position. 
* Realistic turning speeds from rudder movement.


### Nice to have

* Waves
* Tides and Currents
* Wind gusts and shifts

## Interfacing

* NMEA0183, using GP, HD and II strings for simulated boat position (GPS), orientation (compass) and wind direction sensors. Accept autopilot style commands for setting rudder and sail positions.
* Mavlink
* ROS
* REST API

## Graphical Output

Graphical output showing a representation of the boat(s) in a 2D or 3D world. Ideally it should be possible to show some simulated terrain too.

## Mapping Application Output

* ROS applications, Rosviz
* Mavlink, QGroundcontrol/APM planner
* OpenCPN, use NMEA GPS or AIS
* WRSC Tracking API

## Multi-robot Simulation

* Simulate AIS messages to make boats aware of each other's position.
* Use the tracking API to access other boat's position or do a collaborative area scan. 
* Simulate a RADAR or LIDAR sensor to find another boat.
* Simulate a camera view to detect another boat visually.

It would be more visually appealing to see multiple boats in the simulation environment's video output. Failing that it could be shown on a tracking map with each boat running in its own simulator.


## Recording Output and Judging

### Live Streaming

* Stream live video of the simulation software and/or a map 
* Use the same web based mapping interface as we've run at competitions?

## Hosting Environment

How should a competitor run their code? 
* Run on a server provided by the organisers?
* or should it interact with a simulator over the internet? 
* Will latency/speed of the computer provide some teams with an unfair advantage/disadvantage?

* We could run everything on a cloud instance. Competitors will need to have a way to launch their code. Do they get SSH access or does code get executed on their behalf?
* If SSH access is granted how do you stop somebody running when they shouldn't?
* What are the computing requirements for running this on a cloud instance? How much will it cost? Are the free tiers which offer a single low end CPU and 600-1000MB of RAM enough?

### Testing Environment

* Competitors need to test their code outside of the main competition environment. 
* Need to be able to run the simulator on their own computers. 
* Should we provide a constantly running test environment in the cloud? 

## Competition Events

* Triangular course. Will everyone do it in the same time if their code works ok? Different tacking strategies as a differentiator?
* Station keeping. Keep the boat within X metres of a given point for Y minutes.
* Area scan. Visit a set of (every??) square in a grid. 
* Collaborative area scan. Do the above with another boat. Communicate to split up the task? Just watch where they are?
* Collision Avoidance. Use simulated AIS/RADAR/LIDAR/camera to avoid another boat. Attempt to navigate across a busy shipping lane?
* Sail in convoy. Keep a target distance from another boat.

