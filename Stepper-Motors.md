#Stepper Motors and Arduino

## Part 1 - Background

The stepper motor we are using in this lab is a hybrid stepper motor - meaning it consists of permanent magnets and metal teeth. The benefit of this configuaration is that it can use the same control method as a permanent magnet motor, while also recieving the benefits of having rotor teeth. One benefit is an improved torque due to a smaller magnetic circuit resistance.

"Diagram of stepper motor"

When a winding is supplied current, poles are created. These ploes attract the permanent poles on the rotor teeth. This causes the rotor to move (a step) to align the poles. 

There are two types of these stepper motors: Unipolar and Bipolar. The one we are using is a unipolar, but we are leaving two wires loose to make it behave as a bipolar.

## Part 2 - Operation

There are four modes of operation to implement for this stepper motor:

### Full-step mode

Only one winding of the four is acivated at a time in this mode. Therefore the motor will turn 90 degrees per step- and there are four possible orientations.

