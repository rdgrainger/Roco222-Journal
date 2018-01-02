# The Robot Arm project

## Part 1 - Servo control

### Principle 

'diagram of servo motor'

A servo motor utilises position feedback control- The position targeted by the arduino code is compared to the current output position using the error amp. If these are different, an error signal is generated and the motor moves in a direction to compensate. A control pusle provides the intended position. When the comparison is zero (i.e. there is no difference betwenn intended position and current position) the motor stops moving. This lets us contol the exact anlge of the motor using arduino commands- demonstrated in the ROS section.

'photo of connected servo'

### Operation

The first step is to control a servo motor with arduino so that its movement follows a sine wave of frequency 0.2Hz.

'code to do this'

Now to write code to allow us to move the servo with a potentiometer.

'code to do this'
'video of this'

## Part 2 - Robot Arm

### Getting started with ROS

Using the given code sample:

'code from STEP 5'

I can control the servo motor's angle using a ros command: rostopic pub. The parameter needed is:





