# Webotes-2021

![banner](https://user-images.githubusercontent.com/79165532/174826023-6f9b388b-36e1-412d-8620-2b2e11671143.png)

This challenge has the objective of making a controller to a PAIONEER robot.
The controller must be able to guide the robot through the desired path, avoiding obstacles and stopping at a certain location.

## Repository organization 
This repository was divided in two branches:

- controller --> is where the code for the controllers are.
- World --> is where the code for the world is.

## The challenge 

##### Robot
 The robot used in this challenge is the Paioneer 3-DX 
 
 ![image](https://user-images.githubusercontent.com/79165532/174912517-68dcb875-c5e6-4a9e-89c5-cf4ae0e5bfb1.png)

Pioneer 3-DX is a small lightweight two-wheel two-motor differential drive robot. The robot comes complete with front SONAR, one battery, wheel encoders,
a microcontroller with ARCOS firmware, and the Pioneer SDK advanced mobile robotics software development package. 

#### Sensors 

The Pioneer contains 16 distance sensors arranged around its structure

![image](https://user-images.githubusercontent.com/79165532/174913369-b1471ce5-d638-47b4-833f-13dddfb0b12b.png)

They are responsable for the environment information, thus making the robot able to dodge obstacles.

For this challenge, the robot mission is to reach a region illuminated by a lamp. For that, a Light Sensor was added to the robot, so that it is possible to identify when that region was reached.

## Controller 

the controller is responsible for the robot's behavior, and what it needs to do to avoid the obstacles and reach the goal. To enable the robot to reach the goal the 16 distence sensors are used, and each of then has a value that affects the direction of the robot.

The contorller is based in a State Machine, that conts with four states, FORWARD, LEFT, RIGHT and STOP.

- FORWARD -> Moves forward, and begins to turn in either direction when an obstacle is close enough, to avoid it, changing the State to LEFT or RIGHT;
- LEFT -> Turn left until no more obstacle are in sight;
- RIGHT -> Turn right until no more obstacle are in sight;
- STOP -> When the robot reaches the goal, the robot stop.

## Results

https://user-images.githubusercontent.com/79165532/175108791-9b0810ac-32f8-4841-8dd0-2041e1face7d.mp4

As it is posible to see in the video the controller was not able to stop the robot at the correct spot, but the robot was able to dodge the obstacles.



