# The Robot Arm project

## Part 1 - Servo control

### Principle 

*Servo motor circuit diagram:*
https://github.com/rdgrainger/roco222-journal/blob/master/DC-Motor-Project%20resources/Servo%20motor%20design.JPG

A servo motor utilises position feedback control- The position targeted by the arduino code is compared to the current output position using the error amp. If these are different, an error signal is generated and the motor moves in a direction to compensate. A control pusle provides the intended position. When the comparison is zero (i.e. there is no difference betwenn intended position and current position) the motor stops moving. This lets us contol the exact anlge of the motor using arduino commands- demonstrated in the ROS section.

'photo of connected servo'

### Operation

The first step is to control a servo motor with arduino so that its movement follows a sine wave of frequency 0.2Hz.

*Code:*
https://github.com/rdgrainger/roco222-journal/blob/master/DC-Motor-Project%20resources/ros%20lab%20screenshot%201.jpeg

Now to write code to allow us to move the servo with a potentiometer.

'code to do this'
'video of this'

## Part 2 - Robot Arm

### Solidworks design

*Solidwaorks screenshots:*
https://github.com/rdgrainger/roco222-journal/blob/master/DC-Motor-Project%20resources/arm1.JPG

https://github.com/rdgrainger/roco222-journal/blob/master/DC-Motor-Project%20resources/arm2.JPG


### Getting started with ROS

With ROS setup on the system, I can control the servo motors using the terminal, and later with rviz.

Using the given code sample:

1  #include <ros.h>
2  #include <std_msgs/UInt16.h>
3  #include <Servo.h>
4
5  using namespace ros;
6
7  NodeHandle nh;
8  Servo servo;
9
10  void cb( const std_msgs::UInt16& msg){
11 	 servo.write(msg.data); // 0-180
12  }
13
14  Subscriber<std_msgs::UInt16> sub("servo", cb);
15
16  void setup(){
17  	nh.initNode();
18  	nh.subscribe(sub);
19
20 	servo.attach(9); //attach it to pin 9
21  }
22
23  void loop(){
24  	nh.spinOnce();
25 	delay(1);
26  }

And using in terminal: > rosrun rosserial_python serial_node.py /dev/ttyACM0
I can control the servo motor's angle using a ros command: rostopic pub. The parameter needed is:--once servo std_msgs/UInt16 90 (to move 90 degrees, for example).

*Controlling with terminal:*
https://github.com/rdgrainger/roco222-journal/blob/master/DC-Motor-Project%20resources/controllingservo_%20rostopicpub.png

The function defined at line 10 
The object instantiated at line 14 

### 3D modelling the Arm

Our Arm has three degrees of freedom in a simple design. The first servo motor control the direction- attached to a ground plate, it rotates the rest of the arm 180 degrees. The second servo motor corresponds to the first joint- the 'shoulder'. It rotates the next segment 180 degrees. The third servo rotates the last segment 180 degrees in such as way that the arm can fold in on itself.

URDF for Arm:



### Controlling the Arm:

Connceting the three servos up to the arduino, it is now possible to use the joint_state sliders to interface with the servos. We first tried controlling the URDF model on rviz.
The arm on rviz can be controlled with the joint-state publisher node- sliders control each servo position.

*rviz image and video:*
https://github.com/rdgrainger/roco222-journal/blob/master/DC-Motor-Project%20resources/rvizinitial.png

https://github.com/rdgrainger/roco222-journal/blob/master/DC-Motor-Project%20resources/20180110_141118000_iOS.MOV

Now to create code that will enable us to control the arm servos themselves. We realised we would have to setup more servos in the code as we are now working with three. I have named them after the URDF servo names.

*Code:*

*Video of operation:*





