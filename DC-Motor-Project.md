## Build a DC Motor
 

We have been tasked with building a DC motor, testing it and then creating a better iteration. The initial design included one enameled coil of wire, copper tape as a commutator, a cork to function as a core and a suppport structure.
 
### The original motor:
 
*Original Cork motor:*
https://github.com/rdgrainger/roco222-journal/blob/master/DC-Motor-Project%20resources/corkmotor1.jpg

The basic motor is simply one coil of wire wound around a cork with a copper tape commutator. This commutator has two segments protuding from the cork, one for negative and the other, positive. The ends of the coil of wire is stripped and soldered onto the segments so current can be conducted. 
The whole motor structure is supported by a basic frame with two magnets either side. The coil has 118 turns of copper.

This motor operates by touching positive and ground wires to the commutator- one on each side. This supplies a current to the wire. Since the wire is enameled except for the conducting ends, the current flows from one end to the other. Magnets on either side of the coil create a north-south field for the coil to pass through. We know form the principles of DC motor operation that a current-carrying wire inside a magnetic field will feel a magmnetic force. This force is given by F = iLB. Where i = current, L = wire length nad B = flux density. The result magnetic force on this coil will move it in a certain direction - this can be easily found using the right hand rule.

One of the issues we had with this motor was the small size, only allowing for one coil. Having only one coil will not give us the operation we would like to see from the motor. with only one coil moving through the magnetic field, there is current reversal in the wire only once per turn and so the motor cannot easily overcome the weight to turn. The motor needs more torque This is why this cork motor struggles to rotate and requires a push start. It was also difficult to wind the wire around such a small armature.

The commutator was fragile and crumpled too much to use effectively.

One of the issues we had with this motor was the small size, only allowing for one coil. It was also difficult to wind around. The commutator was fragile and crumpled too much to use effectively. By adding more magnets and more coils we can increase the effectiveness of our motor.
 
### Improving the design
 
Some of the major improvements to be made (without considering design changes):

 1. Increase the number of coils
 2. Create a more stable commutator
 3. A larger armature for the coils to wind around
 4. More magnets to create a stronger magnetic field. 


### First Iteration

*Original design:*
https://github.com/rdgrainger/roco222-journal/blob/master/DC-Motor-Project%20resources/first%20iteration%20motor%201.jpg

We first decided to use 16 coils of wire, each with 100 turns. The commutator would have 32 segments to accomodate this. The wire is coiled around an airbed pump. Our intital idea was to have long but narrow loops from one edge of the shaft to the other- this way there is no stacking of coils on the ends of the motor and the loops do not interfere with the commutator. 

'Diagram on coil structure'

 The commutator would comprise of 32 segments in a circle around the end of the shaft. Magnets are to be placed on a support structure wither side of the motor, and would be of a greater number than the original design.

In practice, this motor would not spin. The major problem is the coils of wire- by making them so narrow there would not be a large enough air gap between.

### Second Iteration
 
The design was changed to use 8 coils of wire, each with 100 turns. The commutator has 16 segments to accomodate this. The wire is coiled around an airbed pump. To improve on the previous design, the coils will be widened so that they form a roughly rectangular shape. This allows us to mantain the same principle of not stacking coils, but now the coils can function correctly.

*diagram on improved coil structure:*

*Picture of improved coil structure:*
https://github.com/rdgrainger/roco222-journal/blob/master/DC-Motor-Project%20resources/first%20iteration%20motor%20big%20commutator.jpg

One of the key elements of this design was the magnet arrangement. The idea was to have an unmoving shaft running through the armature with magnets attached. This shaft would not rotate, rather the armature would rotate around it. Surrounding the armature were two arcs (made of thin plastic) with multiple small magnets attached. This formed a 'shell' that almost surrounded the motor and so a magnetic field would be present for most of each coil's rotation.

*Picture of magnet arrangement:*
https://github.com/rdgrainger/roco222-journal/blob/master/DC-Motor-Project%20resources/second%20iteration%20motor%20shell.jpg

This arrangement of magnets proved to be an issue. The outer 'shell' crumpled due to the plastic not being rigid enough to withstand the strong magnetic pull from the internal motor shaft magnets. It also left us with little space for the encoder.

### Third Iteration

Our working motor improved on the second design with a much more stable magnet arrangement. The motor now has two commutators- one for positive (middle of armature, no gaps) and one for negative connections (attached to end of armature). The negative section is wider to allow for easier connection to the power supply, and is made of copper plates for durability. The brush wires are attached to zip ties- the elastic nature of these allows the brushes to continually touch the commutators without need for human interaction.

This design uses frictionless bearings for stability when rotating around the inner shaft. Additionally, all the magnets are attached to this shaft. None are present outside the motor, as apposed to the second design iteration. There are six of these magnets and they have 12kg of pull.

*Inner shaft of the motor:*
https://github.com/rdgrainger/roco222-journal/blob/master/DC-Motor-Project%20resources/second%20motor%20design%20core.jpg

*Motor Operation video:*
https://github.com/rdgrainger/roco222-journal/blob/master/DC-Motor-Project%20resources/Motor%20operation.mp4

## Build an encoder

Our encoder wheel was 3D-printed. The circuit has been made with assistance from the diagram in the dle lab notes

*Circuit diagram for encoder:*
https://github.com/rdgrainger/roco222-journal/blob/master/DC-Motor-Project%20resources/encoder%20circuit.JPG

*An example of an encoder wheel:*
https://github.com/rdgrainger/roco222-journal/blob/master/DC-Motor-Project%20resources/Screenshot%20from%202017-12-12%2019-19-38.png

The encoder we are using is 32 bit.
*Picture of encoder wheel:*
https://github.com/rdgrainger/roco222-journal/blob/master/DC-Motor-Project%20resources/encoder%20printed.jpeg

To measure the angular velocity of our motor we created the following arduino code:

'arduino code for angular velocity'

## Controlling the DC Motor

Due to the size of our motor and nature of its design (weight, magnetic flux), we were drawing more current than the arduino's motor shield could handle. To account for this we built a mosfet circuit. An arduino PWM pin controls the motor duty through this circuit to avoid large ampage and not risk breaking the motor shield.

An added element is the use of an lcd screen to display the motor's speed when we control it. The speed will be controlled with an infrared remote, this has been initialised in the code to choose between 3 different motor speeds using the IR remote's push buttons.

*Diagrams for DC motor:*
*Code for DC motor:*
