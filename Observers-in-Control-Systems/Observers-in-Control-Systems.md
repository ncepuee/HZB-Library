Observers in
Control Systems

Observers in
Control Systems
A Practical Guide
George Ellis
Danaher Corporation
| Amsterdam | Boston London | New York         | Oxford Paris |
| --------- | ------------- | ---------------- | ------------ |
| San Diego | San Francisco | Singapore Sydney | Tokyo        |

This book is printed on acid-free paper.
Copyright 2002,Elsevier Science (USA).
All rights reserved.
No part of this publication may be reproduced or transmitted in any form or by any
means,electronic or mechanical,including photocopy,recording,or any information
storage and retrieval system,without permission in writing from the publisher.Requests
for permission to make copies of any part of the work should be mailed to the
following address:Permissions Department,Harcourt,Inc.,6277 Sea Harbor Drive,
Orlando,Florida,32887-6777.
ACADEMIC PRESS
| An imprint of | Elsevier Science |     |     |
| ------------- | ---------------- | --- | --- |
525 B Street,Suite 1900,San Diego,CA 92101-4495,USA
http://www.academicpress.com
Academic Press
84 Theobald’s Road,London WC1X 8RR,UK
http://www.academicpress.com
| Library of | Congress Control Number:2002104256 |     |     |
| ---------- | ---------------------------------- | --- | --- |
International Standard Book Number:0-12-237472-X
| Printed in the United States of |             | America   |         |
| ------------------------------- | ----------- | --------- | ------- |
| 02 03 04                        | 05 06 07 MB | 9 8 7 6 5 | 4 3 2 1 |

To LeeAnn, my loving wife, and our daughter Gretchen,who makes us both proud.

Observers in Control Systems.......................................... ?
Acknowledgments.............................................................. xi
Safety .................................................................................. xiii
1 Control Systems and the Role of Observers................ 1
1.1 Overview................................................................................... 1
1.2 Preview of Observers............................................................... 2
1.3 Summary of the Book............................................................... 4
2 Control-System Background.......................................... 5
2.1 Control-System Structures ....................................................... 5
2.2 Goals of Control Systems......................................................... 13
2.3 Visual ModelQ Simulation Environment................................... 17
2.4 Software Experiments: Introduction to Visual ModelQ............. 18
2.5 Exercises.................................................................................. 39
3 Review of the Frequency Domain.................................. 41
3.1 Overview of the s-Domain........................................................ 41
3.2 Overview of the z-Domain........................................................ 54
3.3 The Open-Loop Method ........................................................... 59
3.4 A Zone-Based Tuning Procedure............................................. 62
3.5 Exercises.................................................................................. 66
4 The Luenberger Observer: Correcting Sensor
Problems............................................................................. 67
4.1 What Is a Luenberger Observer?............................................. 67
4.2 Experiments 4A-4C: Enhancing Stability with an Observer...... 72
4.3 Predictor-Corrector Form of the Luenberger Observer............ 77

4.4 Filter Form of the Luenberger Observer................................... 78
4.5 Designing a Luenberger Observer ........................................... 82
4.6 Introduction to Tuning an Observer Compensator ................... 90
4.7 Exercises.................................................................................. 95
5 The Luenberger Observer and Model Inaccuracy........ 97
5.1 Model Inaccuracy..................................................................... 97
5.2 Effects of Model Inaccuracy ..................................................... 100
5.3 Experimental Evaluation........................................................... 102
5.4 Exercises.................................................................................. 114
6 The Luenberger Observer and Disturbances............... 115
6.1 Disturbances............................................................................. 115
6.2 Disturbance Response............................................................. 123
6.3 Disturbance Decoupling ........................................................... 129
6.4 Exercises.................................................................................. 138
7 Noise in the Luenberger Observer ................................ 141
7.1 Noise in Control Systems......................................................... 141
7.2 Sensor Noise and the Luenberger Observer............................ 145
7.3 Noise Sensitivity when Using Disturbance Decoupling............ 156
7.4 Reducing Noise Susceptibility in Observer-Based Systems .... 161
7.5 Exercises.................................................................................. 170
8 Using the Luenberger Observer in Motion Control...... 173
8.1 The Luenberger Observers in Motion Systems........................ 173
8.2 Observing Velocity to Reduce Phase Lag................................ 185
8.3 Using Observers to Improve Disturbance Response............... 202

8.4 Exercises.................................................................................. 212
References.......................................................................... 213
A Observer-Based Resolver Conversion in Industrial
Servo Systems1 ................................................................. 217
B Cures for Mechanical Resonance in Industrial
Servo Systems1 ................................................................. 227
Introduction..................................................................................... 227
Two-Part Transfer Function............................................................ 228
Low-Frequency Resonance............................................................ 229
Velocity Control Law....................................................................... 230
Methods of Correction Applied to Low-Frequency Resonance...... 231
Conclusion...................................................................................... 235
Acknowledgments .......................................................................... 235
References..................................................................................... 235
C European Symbols for Block Diagrams....................... 237
Part I: Linear Functions.................................................................. 237
Part II: Nonlinear Functions............................................................ 238
D Development of the Bilinear Transformation............... 241
Bilinear Transformation.................................................................. 241
Prewarping ..................................................................................... 242
Factoring Polynomials.................................................................... 243
Phase Advancing............................................................................ 243
Solutions to Exercises....................................................... 245
Chapter 2........................................................................................ 245

Chapter 3........................................................................................ 245
Chapter 4........................................................................................ 246
Chapter 5........................................................................................ 246
Chapter 6........................................................................................ 247
Chapter 7........................................................................................ 248
Chapter 8........................................................................................ 249
Index.................................................................................... 251

Acknowledgments
Writing a book is a large task and requires support from numerous people,and those
people deserve thanks.First,I thank LeeAnn,my devoted wife of more than 20 years.
She has been an unflagging fan,a counselor,and a demanding editor.She taught me
much of what I have managed to learn about how to express a thought in ink.Thanks
to my mother who was sure I would grow into someone in whom she would be proud
when facts should have dissuaded her.Thanks also to my father for his insistence that
I obtain a college education;that privilege was denied to him,an intelligent man born
into a family of modest means.
I am grateful for the education provided by Virginia Tech. Go Hokies. The basics
of electrical engineering imparted to me over my years at school allowed me to grasp
the concepts I apply regularly today. I am grateful to Mr. Emory Pace, a tough
professor who led me through numerous calculus courses and, in doing so, gave
me the confidence on which I would rely throughout my college career and beyond.
I am especially grateful to Dr. Charles Nunnally; having arrived at university from
a successful career in industry, he provided my earliest exposure to the practical
application of the material I strove to learn. I also thank Dr. Robert Lorenz of the
University of Wisconsin at Madison,who introduced me to observers some years ago.
His instruction has been enlightening and practical.Several of his university courses
are available in video format and are recommended for those who would like to
extend their knowledge of controls. In particular, readers should consider ME 746,
which presents observers and numerous other subjects.
I thank those who reviewed the manuscript for this book. Special thanks goes to
Dan Carlson for his contributions to almost every chapter contained herein.Thanks
also to Eric Berg for his numerous insights. Thanks to the people of Kollmorgen
Corporation (now,Danaher Corporation),my long-time employer,for their continu-
ing support in writing this book.Finally,thanks to Academic Press,especially to Joel
Claypool, my editor, for the opportunity to write this edition and for editing, print-
ing,distributing,and performing the myriad other tasks required to publish a book.
xi

Safety
This book discusses the operation, commissioning, and troubleshooting of control
systems. Operation of industrial controllers can produce hazards such as the
generation of
• large amounts of heat,
• high voltage potentials,
• movement of objects or mechanisms that can cause harm,
• the flow of harmful chemicals,
• flames,and
• explosions or implosions.
Unsafe operation makes it more likely for accidents to occur.Accidents can cause
personal injury to you,your co-workers,and other people.Accidents can also damage
or destroy equipment.By operating control systems safely,you decrease the likelihood
that an accident will occur. Always operate control systems safely!
You can enhance the safety of control-system operation by taking the following
steps:
1. Allow only people trained in safety-related work practices and lock-out/
tag-out procedures to install,commission,or perform maintenance on control
systems.
2. Always follow manufacturer recommended procedures.
3. Always follow national, state, local, and professional safety code regula-
tions.
4. Always follow the safety guidelines instituted at the plant where the equipment
will be operated.
xiii

xiv (cid:2) SAFETY
5. Always use appropriate safety equipment. Examples of safety equipment are
protective eyewear, hearing protection, safety shoes, and other protective
clothing.
6. Never override safety devices such as limit switches,emergency stop switches,
light curtains,or physical barriers.
7. Always keep clear from machines or processes in operation.
Remember that any change of system parameters (for example, tuning gains or
observer parameters), components, wiring, or any other function of the control
system may cause unexpected results such as system instability or uncontrolled system
excitation.
Remember that controllers and other control-system components are subject to
failure. For example, a microprocessor in a controller may experience catastrophic
failure at any time. Leads to or within feedback devices may open or short closed
at any time. Failure of a controller or any control-system component may cause
unanticipated results such as system instability or uncontrolled system excitation.
The use of observers within control systems poses certain risks including that
the observer may become unstable or may otherwise fail to observe signals to an
accuracy necessary for the control system to behave properly.Ensure that,on control-
system equipment that implements an observer, the observer behaves properly in all
operating conditions; if any operating condition results in improper behavior of the
observer,ensure that the failure does not produce a safety hazard.
If you have any questions concerning the safe operation of equipment,contact the
equipment manufacturer,plant safety personnel,or local governmental officials such
as the Occupational Health and Safety Administration.
Always operate control systems safely!

Chapter 1
Control Systems and the
Role of Observers
In this chapter...
• Introduction to observer operation and benefits
• Summary of this book
1.1 Overview
Control systems are used to regulate an enormous variety of machines,products,and
processes.They control quantities such as motion,temperature,heat flow,fluid flow,
fluid pressure,tension,voltage,and current.Most concepts in control theory are based
on having sensors to measure the quantity under control. In fact, control theory is
often taught assuming the availability of near-perfect feedback signals.Unfortunately,
such an assumption is often invalid. Physical sensors have shortcomings that can
degrade a control system.
There are at least four common problems caused by sensors. First, sensors
are expensive. Sensor cost can substantially raise the total cost of a control system.
In many cases,the sensors and their associated cabling are among the most expensive
components in the system. Second, sensors and their associated wiring reduce the
reliability of control systems. Third, some signals are impractical to measure. The
objects being measured may be inaccessible for such reasons as harsh environ-
ments and relative motion between the controller and the sensor (for example, when
trying to measure the temperature of a motor rotor). Fourth, sensors usually
induce significant errors such as stochastic noise, cyclical errors, and limited
responsiveness.
1

2 (cid:2) CHAPTER 1 CONTROLSYSTEMSAND THE ROLEOFOBSERVERS
Observers can be used to augment or replace sensors in a control system.
Observers are algorithms that combine sensed signals with other knowledge of the
control system to produce observed signals. These observed signals can be more
accurate, less expensive to produce, and more reliable than sensed signals. Observers
offer designers an inviting alternative to adding new sensors or upgrading existing
ones.
This book is written as a guide for the selection and installation of observers in
control systems.It will discuss practical aspects of observers such as how to tune an
observer and what conditions make a system likely to benefit from their use.Ofcourse,
observers have practical shortcomings,many of which will be discussed here as well.
Many books on observers give little weight to practical aspects of their use. Books
on the subject often focus on mathematics to prove concepts that are rarely helpful
to the working engineer. Here the author has minimized the mathematics while
concentrating on intuitive approaches.
The author assumes that the typical reader is familiar with the use of traditional
control systems,either from practical experience or from formal training.The nature
of observers recommends that users be familiar with traditional (nonobserver-based)
control systems in order to better recognize the benefits and shortcomings of
observers. Observers offer important advantages: they can remove sensors, which
reduces cost and improves reliability, and improve the quality of signals that come
from the sensors, allowing performance enhancement. However, observers have
disadvantages:they can be complicated to implement and they expend computational
resources. Also, because observers form software control loops, they can become
unstable under certain conditions. A person familiar with the application of
control systems will be in a better position to evaluate where and how to use an
observer.
The issues addressed in this book fall into two broad categories: design and
implementation. Design issues are those issues related to the selection of observer
techniques for a given product. How much will the observer improve performance?
How much cost will it add? What are the limitations of observers? These issues will
help the control-systems engineer in deciding whether an observer will be useful and
in estimating the required resources. On the other hand, implementation issues are
those issues related to the installation of observers.Examples include how to tune an
observer and how to recognize the effects of changing system parameters on observer
performance.
1.2 Preview of Observers
Observers work by combining knowledge of the plant, the power converter output,
and the feedback device to extract a feedback signal that is superior to that which can
be obtained by using a feedback device alone.An example from everyday life is when
an experienced driver brings a car to a rapid stop.The driver combines knowledge of
the applied stopping power (primarily measured through inertial forces acting on the

1.2 PREVIEW OFOBSERVERS (cid:3) 3
driver’s body) with prior knowledge of the car’s dynamic behavior during braking.
An experienced driver knows how a car should react to braking force and uses that
information to bring a car to a rapid but controlled stop.
The principle of an observer is that by combining a measured feedback signal with
knowledge of the control-system components (primarily the plant and feedback
system),the behavior of the plant can be known with greater precision than by using
the feedback signal alone.As shown in Figure 1-1,the observer augments the sensor
output and provides a feedback signal to the control laws.
In some cases, the observer can be used to enhance system performance. It can
be more accurate than sensors or can reduce the phase lag inherent in the sensor.
Observers can also provide observed disturbance signals, which can be used to
improve disturbance response. In other cases, observers can reduce system cost by
augmenting the performance of a low-cost sensor so that the two together can provide
performance equivalent to a higher cost sensor. In the extreme case, observers can
eliminate a sensor altogether, reducing sensor cost and the associated wiring. For
example, in a method called acceleration feedback, which will be discussed in
Chapter 8, acceleration is observed using a position sensor and thus eliminating the
need for a separate acceleration sensor.
Observer technology is not a panacea. Observers add complexity to the system
and require computational resources.They may be less robust than physical sensors,
especially when plant parameters change substantially during operation. Still, an
observer applied with skill can bring substantial performance benefits and do so, in
many cases,while reducing cost or increasing reliability.
Disturbance Response
Command
+ Control Power +
Plant Sensor
_ laws conversion
+
Break connection of measured Measured Feedback
feedback in traditional system
Knowledge
of Plant/Sensor
Observed
Feedback
Observer
Measured
Feedback
Figure 1-1. Role of an observer in a control system.

4 (cid:2) CHAPTER 1 CONTROLSYSTEMSAND THE ROLEOFOBSERVERS
1.3 Summary of the Book
This book is organized assuming that the reader has some familiarity with controls
but understanding that working engineers and designers often benefit from review of
the basics before taking up a new topic.Thus,the next two chapters will review control
systems. Chapter 2 discusses practical aspects of control systems, seeking to build a
common vocabulary and purpose between author and reader. Chapter 3 reviews the
frequency domain and its application to control systems. The techniques here are
discussed in detail assuming the reader has encountered them in the past but may
not have practiced them recently.
Chapter 4 introduces the Luenberger observer structure,which will be the focus of
this book. This chapter will build up the structure relying on an intuitive approach
to the workings and benefits of observers. The chapter will demonstrate the key
advantages of observers using numerous software experiments.
Chapters 5, 6, and 7 will discuss the behavior of observer-based systems in the
presence of three common nonideal conditions. Chapter 5 deals with the effects of
imperfect knowledge of model parameters, Chapter 6 deals with the effects of dis-
turbances on observer-based systems, and Chapter 7 discusses the effects of noise,
especially sensor noise, on observer-based systems.
Chapter 8 discusses the application of observer techniques to motion-control
systems.Motion-control systems are unique among control systems,and the standard
Luenberger observer is normally modified for those applications. The details of the
necessary changes,and several applications, will be discussed.
Throughout this book, software experiments are used to demonstrate key points.
A simulation environment, Visual ModelQ, developed by the author to aid those
studying control systems, will be relied upon. More than two dozen models have
been developed to demonstrate key points and all versions of Visual ModelQ can
run them. Visit www.qxdesign.com to download a limited-capability version free
of charge; detailed instructions on setting up and using Visual ModelQ are given in
Chapter 2.
Readers wishing to contact the author are invited to do so. Write
gellis@qxdesign.com or visit the Web site www.qxdesign.com. Your comments are
most welcome.Also,visit www.qxdesign.com to review errata,which will be regularly
updated by the author.

Chapter 2
Control-System
Background
In this chapter...
• Common control-system structures
• Eight goals of control systems and implications of observer-based methods
• Instructions for downloading VisualModelQ,a simulation environment that is
used throughout this book
• Introductory VisualModelQsoftware experiments
2.1 Control-System Structures
The basic control loop includes four elements: a control law, a power converter, a
plant, and a feedback sensor. Figure 2-1 shows the typical interconnection of these
functions. The command is compared to the feedback signal to generate an error
signal.This error signal is fed into a control law such as a proportional-integral (PI)
control to generate an excitation command. The excitation command is processed
by a power converter to produce an excitation. The excitation is corrupted by a dis-
turbance and then fed to a plant.The plant response is measured by a sensor,which
generates the feedback signal.
There are numerous variations on the control loop of Figure 2-1.For example,the
control-law is sometimes divided in two with some portion placed in the feedback
path. In addition, the command path may be filtered. The command path may be
differentiated and added directly (that is,without passing through the control laws) to
the excitation command in a technique known as feed-forward. Still, the diagram of
Figure 2-1 is broadly used and will be considered the basic control loop in this book.
5

| 6 (cid:2) | CHAPTER 2 | CONTROL-SYSTEM | BACKGROUND |     |     |
| --------- | --------- | -------------- | ---------- | --- | --- |
Commanded
|     |     | Error | Excitation | Power | Disturbance |
| --- | --- | ----- | ---------- | ----- | ----------- |
Command
Excitation Response
+
|     |     | Control |     | Power  |     |
| --- | --- | ------- | --- | ------ | --- |
Plant
|     | +   | -   | law | converter |     |
| --- | --- | --- | --- | --------- | --- |
+
|     |     | Feedback |     |     | Feedback |
| --- | --- | -------- | --- | --- | -------- |
sensor
|     |       |              |     | Figure 2-1. Basic control loop. |     |
| --- | ----- | ------------ | --- | ------------------------------- | --- |
|     | 2.1.1 | Control Laws |     |                                 |     |
Control laws are algorithms that determine the desired excitation based on the error
signal. Typically, control laws have two or three terms: one scaling the present value
of the error (the proportional term), another scaling the integral of the error (the
integral term),and a third scaling the derivative of the error (the derivative term).In
most cases a proportional term is used;an integral term is added to drive the average
value of the error to zero.That combination is called a PI controller and is shown in
Figure 2-2.
When the derivative or D-term is added, the PI controller becomes PID. Deriva-
tives are added to stabilize the control loop at higher frequencies.This allows the value
of the proportional term to be increased,improving the responsiveness of the control
loop.Unfortunately,the process of differentiation is inherently noisy.The use of the
D-term usually requires low-noise feedback signals and low-pass filtering to be
effective. Filtering reduces noise but also adds phase lag, which reduces the ultimate
effectiveness of the D-term. A compromise must be reached between stabilizing the
loop, which requires the phase advance of differentiation, and noise attenuation,
which retards phase. Usually such a compromise is application specific. Note that
dt K
Ú
I
Command
|     |     | Error |     | +   |     |
| --- | --- | ----- | --- | --- | --- |
Commanded
K
P Excitation
- +
PI Control Law
Feedback
|     |     |     |     | Figure 2-2. PI control law. |     |
| --- | --- | --- | --- | --------------------------- | --- |

2.1 CONTROL-SYSTEM STRUCTURES (cid:3) 7
Commanded
Ú dt K I Excitation
Command
Error
+
K
P
- +
+
d Low-pass
K
Feedback dt D filter
Lead term
PID Control Law
Figure 2-3. PID control law.
when a derivative term is placed in series with a low-pass filter,it is sometimes referred
to as a leadnetwork.A typical PID controller is shown in Figure 2-3.
Other terms may be included in the control law. For example, a term scaling the
second derivative can be used to provide more phase advance; this is equivalent
to two lead terms in series. Such a structure is not often used because of the noise
that it generates.In other cases,a second integral is added to drive the integral of the
error to zero. Again, this structure is rarely used in industrial controls. First, few
applications require driving the integral of error to zero; second, the additional
integral term makes the loop more difficult to stabilize.
Filters are commonly used within control laws. The most common purpose is to
reduce noise.Filters may be placed in line with the feedback device or the control-law
output. Both positions provide similar benefits (reducing noise output) and similar
problems (adding phase lag and thus destabilizing the loop). As discussed above,
low-pass filters can be used to reduce noise in the differentiation process. Filters can
be used on the command signal,sometimes to reduce noise and other times to improve
step response. The improvement in step response comes about because, by removing
high-frequency components from the command input,overshoot in the response can
be reduced. Command filters do not destabilize a control system because they are
outside the loop.A typical PI control law is shown in Figure 2-4 with three common
filters.
While low-pass filters are the most common variety in control systems,other filter
types are used. Notch filters are sometimes employed to attenuate a narrow band of
frequencies. They may be used in the feedback or control-law filters to help stabilize
the control loop in the presence of a resonant frequency, or they may be used to
remove a narrow band of unwanted frequency content from the command. Also,
phase-advancing filters are sometimes employed to help stabilize the control loop
similar to the filtered derivative path in the PID controller.
Control laws can be based on numerous technologies. Digital control is common
and is implemented by programmable logic controllers (PLCs), personal computers

8 (cid:2) CHAPTER 2 CONTROL-SYSTEM BACKGROUND
Ú dt K I C E o x m c m ita a t n io d n ed
Command
Error
+
Command Control-law
K
filter + - + P filter
PI Control Law
Feedback
Feedback
filter
Figure 2-4. PI control law with several filters in place.
(PCs), and other computer-based controllers. Because the flexibility of digital
controllers is almost required for observer implementation and because the control
law and observer are typically implemented in the same device,examples in this book
will assume control laws are implemented digitally.
2.1.2 Power Conversion
Power conversion is the process of delivering power to the plant as called for by the
control laws.Four common categories of power conversion are chemical heat,electric
voltage, evaporation/condensation, and fluid pressure. Note that all these methods
can be actuated electronically and so are compatible with electronic control laws.
Electronically or electrically controlled voltage can be used as the power source for
power supplies, current controllers for motors, and heating. For systems with high
dynamic rates, power transistors can be used to apply voltage. For systems with low
dynamic rates, relays can be used to switch power on and off. A simple example of
such a system is an electric water heater.
Pressure-based flow-control power converters often use valves to vary pressure
applied to a fluid-flow system. Chemical power conversion uses chemical energy
such as combustible fuel to heat a plant. A simple example of such a system is a
natural-gas water heater.
2.1.3 Plant
The plant is the final object under control. Most plants fall into one of six major
categories: motion, navigation, fluid flow, heat flow, power supplies, and chemical
processes. Most plants have at least one stage of integration. That is, the input to
the plant is integrated at least once to produce the system response.For example,the
temperature of an object is controlled by adding or taking away heat; that heat is

|     |     | 2.1 CONTROL-SYSTEM | STRUCTURES | (cid:3) 9 |
| --- | --- | ------------------ | ---------- | --------- |
TABLE 2-1 TRANSFER FUNCTIONS OF TYPICALPLANTELEMENTS
Electrical
Voltage (E) and current (I)
| Inductance (L)  | E(s)=Ls¥I(s)    | e(t)=L¥di(t)/dt    |     |     |
| --------------- | --------------- | ------------------ | --- | --- |
| Capacitance (C) | E(s)=1/C¥I(s)/s | e(t)=e +1/CÚi(t)dt |     |     |
0
| Resistance (R) | E(s)=R¥I(s) | e(t)=R¥i(t) |     |     |
| -------------- | ----------- | ----------- | --- | --- |
Translational mechanics
Position (P),Velocity (V),and Force (F)
| Spring (K) | V(s)=s/K¥F(s) or | v(t)=1/K¥df(t)/dtor |     |     |
| ---------- | ---------------- | ------------------- | --- | --- |
|            | P(s)=1/K¥F(s)    | p(t)=p +1/K¥f(t)    |     |     |
0
| Mass (M) | V(s)=1/M¥F(s)/s | v(t)=v +1/MÚf(t)dt |     |     |
| -------- | --------------- | ------------------ | --- | --- |
0
| Damper (c) | V(s)=F(s)/c | v(t)=f(t)/c |     |     |
| ---------- | ----------- | ----------- | --- | --- |
Rotational mechanics
Rotary position (q),Rotary velocity (w),and Torque (T)
| Spring (K) | w(s)=s/K¥T(s) or | w(t)=1/K¥dT(t)/dtor |     |     |
| ---------- | ---------------- | ------------------- | --- | --- |
|            | q(s)=1/K¥T(s)    | q(t)=q +1/K¥T(t)    |     |     |
0
| Inertia (J) | w(s)=1/J¥T(s)/s | w(t)=w +1/JÚT(t)dt |     |     |
| ----------- | --------------- | ------------------ | --- | --- |
0
| Damper (b) | w(s)=T(s)/b | w(t)=T(t)/b |     |     |
| ---------- | ----------- | ----------- | --- | --- |
Fluid mechanics
Pressure (P) and fluid flow (Q)
| Inertia (I)     | P(s)=sI¥Q(s)    | p(t)=I¥dq(t)/dt    |     |     |
| --------------- | --------------- | ------------------ | --- | --- |
| Capacitance (C) | P(s)=1/C¥Q(s)/s | p(t)=p +1/CÚq(t)dt |     |     |
0
| Resistance (R) | P(s)=R¥Q(s) | p(t)=R¥q(t) |     |     |
| -------------- | ----------- | ----------- | --- | --- |
Heat flow
Temperature difference (J) and heat flow (Q)
| Capacitance (C) | J(s)=1/C¥Q(s)/s | j(t)=j +1/CÚq(t)dt |     |     |
| --------------- | --------------- | ------------------ | --- | --- |
0
| Resistance (R) | J(s)=R¥Q(s) | j(t)=R¥q(t) |     |     |
| -------------- | ----------- | ----------- | --- | --- |
integrated  through  the  thermal  mass  of the  object  to  produce  the  object’s
temperature.Table 2-1 shows the relationships in a variety of ideal plants.
The pattern of force,impedance,and flow is repeated for many physical elements.
In Table 2-1,the close parallels between the categories of linear and rotational force,
fluid mechanics, and heat flow are evident. In each case, a forcing function (voltage,
force,torque,pressure,or temperature difference) applied to an impedance produces
a flow (current,velocity,fluid flow,or thermal flow).The impedance takes three forms:
resistance to the integral of flow (capacitance or mass),resistance to the derivative of
flow (spring or inductance),and resistance to the flow rate (resistance or damping).

| 10 (cid:2) | CHAPTER 2 CONTROL-SYSTEM | BACKGROUND |     |     |     |     |
| ---------- | ------------------------ | ---------- | --- | --- | --- | --- |
Table 2-1 reveals a central concept of controls.Controllers for these elements apply
a forceto control a flow.When the flow must be controlled with accuracy,a feedback
sensor is often added to measure the flow; control laws are required to combine the
feedback and command signals to generate the force. This results in the structure
shown in Figure 2-1; it is this structure that sets control systems apart from other
|     | disciplines of         | engineering. |     |     |     |     |
| --- | ---------------------- | ------------ | --- | --- | --- | --- |
|     | 2.1.4 Feedback Sensors |              |     |     |     |     |
Feedback sensors provide the control system with measurements of physical quantities
necessary to close control loops. The most common sensors are for motion states
(position, velocity, acceleration, and mechanical strain), temperature states (temper-
ature and heat flow), fluid states (pressure, flow, and level), and electromagnetic
states (voltage, current, charge, light, and magnetic flux). The performance of most
traditional (nonobserver) control systems depends,in large part,on the quality of the
sensor. Control-system engineers often go to great effort to specify sensors that will
provide responsive, accurate, and low-noise feedback signals. While the plant and
power converter may include substantial imperfections (for example, distortion and
noise),such characteristics are difficult to tolerate in feedback devices.
|     | 2.1.4.1 Errors in Feedback Sensors |     |     |     |     |     |
| --- | ---------------------------------- | --- | --- | --- | --- | --- |
Feedback sensors measure signals imperfectly.The three most common imperfections,
as shown in Figure 2-5, are intrinsic filtering,noise,and cyclical error.
The intrinsic filtering of a sensor limits how quickly the feedback signal can follow
the signal being measured.The most common effect of this type is low-pass filtering.
For all sensors there is some frequency above which the sensor cannot fully respond.
This may be caused by the physical structure ofthe sensor.For example,many thermal
sensors have thermal mass; time is required for the object under measurements
|     |          | +   | Control      | Power      |               |          |
| --- | -------- | --- | ------------ | ---------- | ------------- | -------- |
|     | Command  |     |              |            | Plant         | Response |
|     |          | _   | laws         | conversion |               |          |
|     |          |     | +            | +          |               |          |
|     | Feedback |     | Intrinsic    |            | Ideal         |          |
|     |          |     | filter       |            | sensor        |          |
|     |          |     | +            | +          |               |          |
|     |          |     | Sensor noise |            | Sensor cyclic |          |
error
Practical sensor
Figure 2-5. Apractical sensor is a combination of an ideal sensor and error sources.

2.1 CONTROL-SYSTEM STRUCTURES (cid:3) 11
to warm and cool the sensor’s thermal mass. Filtering may also be explicit as in the
case of electrical sensors where passive filters are connected to the sensor output to
attenuate noise.
Whatever the source of the filtering, its primary effect on the control system is to
add phase lag to the control loop.Phase lag reduces the stability margin of the control
loop and makes the loop more difficult to stabilize. The result is often that system
gains must be reduced to maintain stability in order to accommodate slow sensors.
Reducing gains is usually undesirable because both command and disturbance re-
sponse degrade.
Cyclical error is the repeatable error that is induced by sensor imperfections.
For example, a strain gauge measures strain by monitoring the change in electrical
parameters of the gauge material that is seen when the material is deformed. The
behavior of these parameters for ideal materials is well known. However, there are
slight differences between an ideal strain gauge and any sample. Those differences
result in small, repeatable errors in measuring strain. Since cyclical errors are
deterministic,they can be compensated out in a process where individual samples of
sensors are characterized against a highly accurate sensor. However, in any practical
sensor some cyclical error will remain.Because control systems are designed to follow
the feedback signal as well as possible,in many cases the cyclical error will affect the
control-system response.
Stochastic or nondeterministic errors are those errors that cannot be predicted.The
most common example of stochastic error is high-frequency noise. High-frequency
noise can be generated by electronic amplification of low-level signals and by con-
ducted or transmitted electrical noise commonly known as electromagnetic interfer-
ence (EMI).High-frequency noise in sensors can be attenuated by the use of electrical
filters;however,such filters restrict the response rate of the sensor as discussed above.
Designers usually work hard to minimize the presence of electrical noise,but as with
cyclical error, some noise will always remain. Filtering is usually a practical cure for
such noise;it can have minimal negative effect on the control system if the frequency
content is high enough so that the filter affects only frequency ranges well above where
phase lag is a concern in the application.
The end effect of sensor error on the control system depends on the error type.
Limited responsiveness commonly introduces phase lag in the control system,reduc-
ing margins of stability.Noise makes the system unnecessarily active and may reduce
the perceived value of the system or keep the system from meeting a specification.
Deterministic errors corrupt the system output.Because control systems are designed
to follow the feedback signal (including its deterministic errors) as well as possible,
deterministic errors will carry through,at least in part,to the control-system response.
2.1.5 Disturbances
Disturbances are undesired inputs to the control system.Common examples include
load torque in a motion-control system, changes in ambient temperature for a
temperature controller, and 50/60-Hz noise in a power supply. In each case, the

12 (cid:2) CHAPTER 2 CONTROL-SYSTEM BACKGROUND
primary concern is that the control law generate plant excitation to reject (i.e.,prevent
response to) these inputs.A correctly placed integrator will totally reject direct-current
(DC) disturbances. High tuning gains will help the system reject alternating-current
(AC) disturbance inputs,but will not reject those inputs entirely.
Disturbances can be either deterministic or stochastic.Deterministic disturbances
are those disturbances that repeat when conditions are duplicated.Such disturbances
are predictable.Stochastic disturbances are not predictable.
The primary way for control systems to reject disturbances is to use high gains in
the control law.High gains force the control-system response to follow the command
despite disturbances. Of course, there is an upper limit to gain values because high
gains reduce system stability margins and,when set high enough,will cause the system
to become unstable.
2.1.5.1 Measuring Disturbances
In the case where the control-system gains have been raised as high as is practical,
disturbance rejection can still be improved by using a signal representing the distur-
bance in a technique known as disturbance decoupling [11, Chap. 7; 26; 27]. Distur-
bance decoupling,as shown in Figure 2-6,is a cancellation technique where a signal
representing the disturbance is fed into the power converter in opposition to the effect
of the disturbance. For the case of ideal disturbance measurement and ideal power
Disturbance
Disturbance
decoupling inverts the
measured disturbances
and adds it to the Disturbance
control law output. measurement
Commanded
excitation
Excitation
Command Error _ + Response
Control Power
Plant
+ _ laws + converter +
Feedback
Feedback sensor
Figure 2-6. Typical use of disturbance decoupling.

2.2 GOALSOFCONTROLSYSTEMS (cid:3) 13
conversion, disturbance decoupling eliminates the effects of the disturbance entirely.
However,for practical systems,the effect of disturbance decoupling is to improve,but
not eliminate,response to disturbances;this is especially true in the lower frequencies
where the disturbance sensor and the power converter are often close to ideal.
For most control systems, direct measurement of disturbances is impractical.
Disturbances are usually difficult to measure and physical sensors carry with them
numerous disadvantages, especially increasing system cost and reducing reliability.
One of the key benefits of observers is that disturbance signals can often be observed
with accuracy without requiring additional sensors. For many applications, only
modest computational resources must be added to implement such an observer.This
topic will be discussed in detail in Chapters 6 and 8.
2.2 Goals of Control Systems
Control systems must fulfill a complicated combination of requirements. A large set
of goals must be considered because no single measure can provide a satisfactory
assessment. In fact, no single set of goals can be defined for general use because of
the variation between applications. However, many common goals are broadly used
in combination. In this section, eight common goals for control systems will be
discussed. In addition, the role of observers in helping or, in some cases, hindering
the realization of those goals will be discussed.
2.2.1 Competitively Priced
Control systems, like almost all products in the industrial market, must be delivered
at competitive prices. The virtues of a control system will be of little value if the
application can be served equally well by a less expensive alternative. This is not to
say that a customer will not pay a premium for enhanced performance.However,the
manufacturer offering premium products must demonstrate that the premium will
improve the cost–value position of the final product.
Arguments for observer-based methods can be at either end of the cost–value
spectrum.For example,if an observer is used to help replace an existing sensor with
one that is less expensive, the argument may be that for a modest investment in
computational resources,sensor cost can be reduced.In other cases,it can be argued
that observers increase value; for example, value could be increased by providing a
more reliable feedback signal or a more accurate feedback signal that will lead to
improved performance.
Those readers who are leading their companies in the use of observers should
expect that they will have to demonstrate the practical advantages of observers if
they want the methods to be adopted. Bear in mind that observers often produce
undesirable characteristics, such as increased computational costs. At the very least,
they require time to develop and training for staff or customers to learn new methods.

14 (cid:2) CHAPTER 2 CONTROL-SYSTEM BACKGROUND
2.2.2 High Reliability
Control systems must be reliable. A proven way to enhance reliability is by reducing
component count,especially connectorized cables.Electrical contacts are among the
least reliable components in many systems. Observers can increase reliability when
they are used to eliminate sensors and their cables.
Observers are not the only alternative for removing sensors.There is a wide variety
of techniques to remove sensors, usually by measuring ancillary states; for example,
the hard-disk-drive industry long ago began employing sensorless technology, elimi-
nating commutation-position1 sensors in PC hard disks by measuring the electrical
parameters of the motor driving the disk. This points out that sensorless is actually
a misnomer; sensorless applications normally eliminate one sensor by relying on
another.Still,the results are effective.In the case of sensorless hard drives,the posi-
tion sensor and its cabling eliminated.
Observers offer a key enhancement for sensorless operation. The problem with
most sensorless schemes is that the signals being measured usually have poor
signal-to-noise characteristics, at least in some operating conditions. Returning to
the example of a hard-disk controller, direct (that is, nonobserver-based) voltage
measurement works well in the disk-drive industry where motor speeds are high so
that the voltages created by the motor are relatively large.These same techniques work
poorly at low speeds so that they cannot be used in many applications.2 Because
observers combine the sensed signals (which may have high noise content) with the
model signals (which are nearly noise free),they can remove noise from the calculated
output, greatly extending the range of sensorless operation. So observers can be the
best alternative to allow the elimination of sensors in some applications, and thus,
they can be an effective way to simultaneously increase system reliability and reduce
cost.
2.2.3 Stability
Control systems should remain stable in all operating conditions. The results of
unstable operation are unpredictable;certainly,it is never desirable and in many cases,
people may be injured or equipment damaged. In addition to maintaining absolute
stability, systems must maintain reasonable margins of stability. For example, a
temperature controller with low margins of stability may respond to a commanded
1Note that this discussion relates to position sensing for commutation,the process of channeling current
to produce torque in a motor. Commutation requires only coarse sensing, often just a dozen or so
positions around the disk.Hard-disk drives use an additional track on the disk itself for the fine position
sensing,which allows the much more accurate location of data on the disk surface.
2This voltage,called the back-electro-motive force or back-EMF,is produced by motors in proportion to
the moving magnetic field of the motor.In most cases,the back-EMF is proportional to the speed of the
motor.Thus,at low speed,the back-EMF signal is low and noise has a greater effect.

2.2 GOALSOFCONTROLSYSTEMS (cid:3) 15
temperature change of 5° by generating oscillatory changes of 5° or 10° that die
out only after minutes of ringing. Such a system may meet an abstract definition of
stability, but it would be unacceptable in most industrial applications. Margins of
stability must be maintained so that performance can be predictable. Two common
measures of stability,phase margin and gain margin, will be discussed in Chapter 3.
Observers can improve stability by reducing the phase lag within the control loop.
For example,the process of converting a sensor signal often involves filtering or other
sources of phase lag.In the motion-control industry,it is common to use the simple
difference of two position samples to create a velocity signal. Such a process is well
known to inject a time delay of half the sample time.By using an observer this phase
delay can be removed.In applications requiring the highest performance,the removal
of this phase lag can be significant.
2.2.4 Rapid Command Response
Command response measures how well the response follows a rapidly changing
command.Most control systems follow slowly changing commands well but struggle
to follow more rapidly changing signals.In most cases,it is considered an advantage
for a control system to follow rapid commands accurately.
A key measure of system response is bandwidth. The bandwidth is defined as the
frequency where the small signal response falls to 70.7% of the DC response.To find
the bandwidth of a control system, create a sinusoidal command at a relatively low
frequency and measure the amplitude of the response. Increase the frequency until
the amplitude of the response falls to 70% of the low-frequency value;this frequency
is the bandwidth.
The most common way to improve command response is to raise the gains of the
control laws. Higher gains help the system follow dynamic commands but simulta-
neously reduce margins of stability. Tuning, the process of setting control-law gains,
is often a compromise between command response and margins of stability. As
discussed above, observers can increase margins of stability and thus allow in-
crementally higher gains in the control law.
2.2.5 Disturbance Rejection
Disturbance rejection is a measure of how well a control system resists the effect
of disturbances. As with command response, higher gains help the system reject
disturbances, but they reduce margins of stability. Again, tuning control-law gains
requires a compromise of response and stability.
Observers can help disturbance rejection in two ways.As with command response,
disturbance response can be improved incrementally through higher control-law gains
when the observer allows the removal of phase lag. Second, as discussed in
Section 2.1.5.1, observers can be used to observe disturbances, allowing the use of
disturbance decoupling where it otherwise might be impractical.

16 (cid:2) CHAPTER 2 CONTROL-SYSTEM BACKGROUND
2.2.6 Minimal Noise Response
Noise response is a measure of how much the control system responds to noise inputs.
The problem may be in the plant response where the concern is that the noise unduly
corrupts the system output. On the other hand, the concerns may be with noise
generated by the power converter. Noise fed into the control law via the command,
feedback, and control-laws calculations is transferred to the power converter where
it can create high-frequency perturbations in the power output. That noise can be
objectionable even if the plant filters the effect so much that it does not measurably
affect the system response.For example,noise in a power supply may generate high-
frequency current perturbations that cause audible noise. Such noise may make the
noise generation unacceptable, even if final filtering components on the power
supply output remove the effect of the noise on the power supply’s output voltage.
The concern with noise response is usually focused on response to high-frequency
signals. High system gain is desirable at lower frequencies. A control system is
expected to be responsive to signals at and below the system bandwidth. Well above
the bandwidth, high gain becomes undesirable. The output does not respond to the
input in any useful way (because it is greatly attenuated), but it still passes high-
frequency noise,generating undesirable perturbations,audible noise,and unnecessary
power dissipation. Lower gain at frequencies well above the bandwidth is equivalent
to improved (reduced) noise response.
The first step to reducing noise response is reducing the amplitude of the noise
feeding the control system. This may come by improving system wiring, increasing
resolution of digital processes,or improving power supply quality to the sensors and
control laws.After this path has been exhausted,the next step is usually to filter noise
inputs.Filters are effective in reducing noise,but when filters are in the control loop,
they add phase lag, reducing margins of stability; control-law gains often must be
reduced to compensate. Since margins of stability must be maintained at an accept-
able level,the end effect is that filtering often forces control-law gains down.
Observers can exacerbate problems with sensor-generated noise.One reason is that
one of the primary benefits of observers is supporting increased control-law gains
through the reduction of phase lag. The increase of control-law gains will directly
increase the noise susceptibility of the typical control system. In addition, observers
often amplify sensor noise above the bandwidth of the sensor.The details of this effect
are complicated and will be explained in Chapter 7. For the present, readers should
be aware that observers often will not work well in systems where sensor noise is a
primary limitation.
2.2.7 Robustness
Robustness is a measure of how well a system maintains its performance when system
parameters vary. The most common variations occur in the plant. As examples, the
capacitance of a power supply storage capacitor may vary over time, the rotational

2.3 VISUAL MODELQSIMULATION ENVIRONMENT (cid:3) 17
inertia of a mechanism may vary during different stages of machine operation, and
the amount of fluid in a fluid bath may vary and change the thermal mass of the bath.
The control system must remain stable and should maintain consistent performance
through these changes.One challenge of observer-based techniques is that robustness
can be reduced by their use. This is because observers rely on a model; when the
plant changes substantially and the model is not changed accordingly, instability
can result. Thus, robustness should be a significant concern any time observers are
employed.
2.2.8 Easy Setup
Control systems should be easy to set up. One of the realities of modern industry is
that the end users of control systems are often unfamiliar with the principles that
make those systems work.This can be hard for control-system designers to accept.It
limits the use of novel control methods because those people further down the
product-use chain (for example,technicians,salespeople,and end users) may not fully
understand why these methods are useful or how they should be configured.Certainly,
observers fit into this class of solutions. In many cases, after they have been imple-
mented, tested, and shown to be effective, they still must be clearly explained to be
ultimately successful.In addition,designers must strive to keep observers easy to set
up. Observers are software-based closed loops with control laws that must be tuned;
as will be discussed, this process can be simplified by careful design.
2.3 Visual ModelQ Simulation Environment
When learning control-system techniques, finding equipment to practice on is
often difficult.As a result,designers must often rely on computer simulations.To this
end, the author developed Visual ModelQ, a stand-alone, graphical, PC-based
simulation environment, as a companion to this book. The environment provides
time-domain and frequency-domain analysis of analog and digital control systems.
Visual ModelQ is an enhancement of the original ModelQ in that Visual ModelQ
allows readers to view and build models graphically. More than two dozen Visual
ModelQ models were developed for this book. These models are used extensively
in the chapters that follow. Readers can run these experiments to verify results
and then modify parameters and other conditions so they can begin to experiment
with observers.
Visual ModelQ is written to teach control theory. It makes convenient those
activities that are necessary for studying controls. Control-law gains are easy to
change.Plots of frequency-domain response (Bode plots) are run with the press of a
button. The models in Visual ModelQ run continuously, similar to the way real-time
controllers run. The simulated measurement equipment runs independently so
parameters can be changed and the effects seen immediately.

18 (cid:2) CHAPTER 2 CONTROL-SYSTEM BACKGROUND
2.3.1 Installation of Visual ModelQ
Visual ModelQ is available at www.qxdesign.com. The unregistered version is
available free of charge. While the unregistered version lacks several features, it can
execute all the models used in this book.Readers may elect to register their copies of
Visual ModelQat any time;see www.qxdesign.com for details.
Visual ModelQ runs on PCs using Windows 95, Windows 98, Windows 2000,
or Windows NT. Download and run the executable file setup.exe for Visual ModelQ
V6.0 or later. Be aware that the original version of ModelQ is not compatible with
Visual ModelQ. Note that Visual ModelQ comes with an online help manual. After
installation, read this manual. Finally, check the Web site from time-to-time for
updated software.
2.4 Software Experiments: Introduction to Visual ModelQ
The following section will review a few models to introduce the reader to Visual
ModelQ.
2.4.1 Default Model
When Visual ModelQ is launched, the default model is automatically loaded. The
purpose of this model is to provide a simple system and to demonstrate a few
functions. The default model and the control portion of the Visual ModelQ
environment are shown in Figure 2-7.
The model compilation and execution are controlled with the block of three
buttons at the upper left of the screen: compile (green circle), stop execution (black
Default model
Figure 2-7. Screen capture of Visual ModelQenvironment showing the default model.

2.4 SOFTWARE EXPERIMENTS:INTRODUCTION TOVISUALMODELQ (cid:3) 19
Figure 2-8. Compile and run controls.
square),and start execution (black triangle).These blocks,with the current execution
time (here, 9.16051seconds), are shown in Figure 2-8. If a model must be compiled
before it can be run, the green circle will turn red. The circle will turn red at launch
and anytime either a block or a wire is added to or taken away from the model.Any
time a model is recompiled, the model timer will return to 0 seconds and all default
values of model blocks will be reloaded.
The default model is detailed in Figure 2-9. There are four blocks, two of which
are connected with a wire:
• Solver: The solver configures the differential-equation solver used to simulate
system components. Note: One and only one solver is required for every
model.
• Scope: The main scope provides a display for up to eight channels of input.
The workings of the scope and its trigger mechanism are similar to those of a
physical oscilloscope.Note:At least one scope is required for every model.
• Waveform Generator: The waveform generator can be used to generate
standard waveforms such as sine waves and triangle waves. Frequency, ampli-
tude, and phase are all adjustable while the model is running. The generator
here is set to produce a square wave at 10Hz.
Wire
Solver Scope Waveform
block block generator
On-screen
scope
Figure 2-9. Detail of default model.

20 (cid:2) CHAPTER 2 CONTROL-SYSTEM BACKGROUND
hnode Documentation node
Name
Figure 2-10. Detail of Solvernode.
• Live Scope: The Live Scope displays its output on the block diagram. Live
Scopevariables automatically display on all main scope blocks as well.Notice
in Figure 2-7 that a short wire connects the output of the waveform generator
to the input of the scope; this connection specifies that the Live Scope should
plot the output of the waveform generator.
2.4.1.1 Viewing and Modifying Node Values
Blocks have nodes,which are used to configure and wire the elements into the model.
For example, the solver block, shown in Figure 2-10, has two nodes. There is a con-
figuration node (a green diamond) at the left named h.This node sets the sample time
of the differential-equation solver. The sample time is set to 10ms by default.
The solver block includes a documentation node (a rectangle) at the right. The
documentation node, which is provided on almost all Visual ModelQ blocks, allows
the user to enter notes about the block for reference. The name of the block, Solver
in this case, is shown immediately below the block. The user can change the
name of any Visual ModelQ block by positioning the cursor within the name and
double-clicking.
There are several ways to read the values of nodes such as the hnode of the sample
block. The easiest is to use fly-over help. After the model is compiled, position the
cursor over the node and the value will be displayed in a fly-over block for about a
second,as shown in Figure 2-11.
The value of configuration nodes can be set in two ways. One way is to place the
cursor over the node and double-click.The Change/Viewdialog box is then displayed
as shown at the top right of Figure 2-12.The value can be viewed and changed from
this dialog box.
The second way to set values is to use the Block set-up dialog box. Right-click in
the body of the block; this brings up a pop-up menu as is shown center left in
Figure 2-11. Visual ModelQprovides fly-over help for nodes.

2.4 SOFTWARE EXPERIMENTS:INTRODUCTION TOVISUALMODELQ (cid:3) 21
Double-click on
the hnode (green diamond)...
…change the node
OR value using the
Change/View
Right-click dialog box
inside the
solver block
for the pop-up
menu...
…click on the
value to see
the Change/View
dialog box...
…click on “properties”
for the block set-up dialog box...
Figure 2-12. Two ways to change the h parameter of the solver block.
Figure 2-12.Select the Propertiesitem in that menu to bring up the Block set-updialog
box.This box will show the value of all the nodes in the block.Click on the value to
bring into view the Change/Viewdialog box.
2.4.1.2 The WaveGen Block
The WaveGen block has ten nodes,as shown in Figure 2-13. The nodes are:
• Waveform:Select initial value from several available waveforms such as sine or
square waves.
• Frequency:Set initial frequency in Hertz.
• Amplitude: Set initial value of peak amplitude. For example, setting the
amplitude to 1 produces an output of ±1.
• Enable:Allows automatic disabling of the waveform generator.When the value
is 1, the generator is enabled. When 0, the generator is disabled. For digital
inputs such as this node, Visual ModelQ considers any value greater than 0.5
to be equivalent to 1 (true); all values less than or equal to 0.5 are considered
equivalent to 0 (false).This function will be especially useful when taking Bode
plots since all waveform generators should be disabled in this case.
• Output:Output signal of waveform generator.

22 (cid:2) CHAPTER 2 CONTROL-SYSTEM BACKGROUND
Frequency Amplitude
Enable
Waveform
Output
Documentation
Offset
Multiplier
Phase Duty Cycle
Figure 2-13. The waveform generator has 10 nodes.
• Offset:Initial value by which the waveform generator output should be offset.
• Phase:Initial value of waveform phase,in degrees,of the waveform generator.
For example,if the output is a sine wave, the output will be:
Output=Amplitude*sin(Frequency¥2p ¥t+Phase¥p 180)+Offset.
• Duty cycle:Initial value of percentage duty cycle for pulse waveforms.
• Multiplier: Value by which to multiply waveform generator output. This is
normally used for unit conversion. For example, most models are coded in
Systeme International (SI) units. If the user finds RPM more convenient for
viewing than the SI radians/second,the multiplier can be set to 0.105 to convert
RPM (the user units) to radians/second (SI units). The multiplier node is
present in most instruments such as scopes and waveform generators to
simplify conversion to and from user to SI units.
The Enable node of the WaveGen block is an input node, as the inward-pointing
triangle indicates. Input nodes can be changed while the model is running and they
can be wired in the model. Neither of these characteristics is true of configuration
nodes (those shaped like diamonds).
Using the block set-up dialog box can speed the setup of more complicated
blocks such as the WaveGen. The WaveGen block set-up dialog is shown in
Figure 2-14. The benefit of the block set-up dialog is that all of the parameters are
identified by name and can be set one after the other. Notice that the first node in
the dialog, Output, cannot be changed (the button at right allows only “View...”).
This is necessary because some nodes, such as output nodes, cannot be configured
manually.

2.4 SOFTWARE EXPERIMENTS:INTRODUCTION TOVISUALMODELQ (cid:3) 23
Figure 2-14. Block set-up dialog box for the waveform generator.
The parameters of the waveform generator set in the nodes are only initial
(precompiled) values.To change the configuration of the waveform generator when the
model is running, double-click anywhere inside the block and bring up the real-time
WaveGen control panel. This panel, shown in Figure 2-15, allows six parameters of
the waveform to be changed while the model is running.The buttons marked “<”and
Figure 2-15. Waveform generator control panel which is displayed by double-clicking on the WaveGen
block after the model has been compiled.

24 (cid:2) CHAPTER 2 CONTROL-SYSTEM BACKGROUND
“>”move the value up and down by about 20% for each click.Changing these values
has no permanent affect on the model;each time the model is recompiled,these values
will be returned to the initial values as specified by the nodes.
2.4.1.3 The Scope Block
The Scope block,with a list of its nodes,is shown in Figure 2-16.Most of the nodes
set functions that are consistent with laboratory oscilloscopes and thus will be
familiar to most readers. One node that should be discussed is the Trigger Source
node. This node sets the initial variable that will trigger the scope when the scope
mode is set to Auto or Normal. If this variable is not set prior to compiling the
model,a warning will be generated.To eliminate this warning,simply double-click on
the node and select a variable from a drop-down list to trigger the scope.Choose from
any Variableor Live Scope,as shown in Figure 2-16.
The scope display is normally not visible. However, it can be made visible by
double-clicking inside the scope block after the model has been compiled.The block
can be made not visible by clicking the “X”icon at the top right of the scope window.
The scope display provides two tabs: Scale and Trigger. The Scale tab (shown in
Figure 2-17) provides control of the horizontal and vertical scaling. The Trigger tab
provides various trigger settings.At the bottom of the scope there are a few controls.
Starting at the bottom left of Figure 2-17:
Trigger Slope Trigger Position
Trigger Level Trigger Mode
Roll?
Trigger Source
Documentation
OR
Time/division
Single Shot
x vs. y? Horizontal Channel (for x vs. y)
Figure 2-16. The Trigger Sourceof a Scopecan be set to any variable (such as Variable6) or any
Live Variable(such as LiveVariable3).

2.4 SOFTWARE EXPERIMENTS:INTRODUCTION TOVISUALMODELQ (cid:3) 25
Figure 2-17. Output of main scope in default model.
• the Trig button flashes green for each trigger event;
• the sunglasses button hides the control panel at left, maximizing the display
area of the plot;
• the single-shot check box enables single-shot mode;
• the scale-legend control button turns the scale legend (immediately below the
plot) on and off;
• the three cursor buttons select 0, 1,or 2 cursors.
Note that single-shot mode stops the model from running after the scope screen
has filled up. Restart the model using the Run (black triangle) button after each
single-shot event.
2.4.1.4 The Live Scope Block
The default model also includes a Live Scope block, as shown in Figure 2-18. The
input comes in at top left, with the scale, offset, and time scale set in the nodes just
below that. The Show node determines whether the variable in the Live Scope is
displayed in the main scopes after each compile (note that variables that display in a

26 (cid:2) CHAPTER 2 CONTROL-SYSTEM BACKGROUND
Input
Time/ Scale
Offset
Div
Show
Mult
Source
Level
Slope
Pos.
Mode
Size
(W,H)
Trigger Nodes
Figure 2-18. Detail of the Live Scopenodes.
Live Scope also can be displayed in any main scope block). The Mult node specifies
a multiplier,which scales the variable before plotting.
The next five nodes are trigger nodes.The Trigger Sourcenode specifies the signal
that triggers the Live Scope. If this variable is unwired, the Input (first) node will
be used as the trigger. Most of the remaining nodes have equivalent functions on
standard oscilloscopes except the last two nodes, Width and Height, which set the
size of the LiveScopeblock in pixels.
LiveScopesprovide simple display features compared to the main scope block,and
there are several limitations.No more than two channels can be displayed using a Live
Scope. There are fewer trigger options. Another limitation is that Live Scopes only
show input vs time;there is no option for Input1 vs Input2 (xvs y) as there is for the
main Scopeblocks.
The Live Scopealso has several advantages.First,the wiring to a LiveScopemakes
it clear which variable is being plotted; this makes the display more intuitive, espe-
cially in larger models.Second,because the result is displayed on the model,it is often
easier to convey information to others using the Live Scope. It is this reason that
caused the author to prefer the Live Scope to the standard scope throughout this
book.Finally,almost all of the LiveScopeparameters are input nodes,and all input
nodes can be wired into the circuit. This means that a model can be constructed to
automatically change those values as the model executes.
2.4.2 Experiment 2A: Simple Control System
The remainder of this chapter will discuss three experiments written to introduce
the reader to control-system modeling in Visual ModelQ.Experiment 2A is a simple
control system.The model diagram is shown in Figure 2-19.The model is comprised
of several elements:

2.4 SOFTWARE EXPERIMENTS:INTRODUCTION TOVISUALMODELQ (cid:3) 27
Power converter:
Plant: Integral
PI Control law Filter set to 800 Hz with gain of 500
Waveform
generator for
command
Feedback filter
set to 350 Hz
A solver and a Two-channel
scope are required live scope
Figure 2-19. Experiment 2A: Visual ModelQmodel of a simple control system.
• A waveform generator, which produces the command.
• A summing junction,which compares the command and the feedback (output
from the feedback filter) and produces an error signal.
• A PI control law,which is configured with two LiveConstants,a proportional
gain,K ,and an integral gain,K.These blocks will be discussed shortly.
P I
• A filter simulating the power converter.The power converter is a two-pole low-
pass filter set for a bandwidth of800Hz and with a zeta (damping ratio) of0.707.
• An integrating plant with an intrinsic gain of 500.
• A filter simulating the feedback conversion process.The feedback filter is a two-
pole low-pass filter set with a bandwidth of 350Hz and with a zeta of 0.707.
• A two-channel Live Scope that plots command (above) against actual plant
output (below).
• A solver and scope, both of which are required for a valid Visual ModelQ
model.
2.4.2.1 Visual ModelQ Constants: Many Ways to Change Parameters
VisualModelQprovides numerous ways to change model parameters.Of course,any
unwired node can be changed by double-clicking on a node or right-clicking and
bringing up the Block set-updialog box (see Figure 2-12).However,numerous blocks
are provided to simplify the task of changing node values.

28 (cid:2) CHAPTER 2 CONTROL-SYSTEM BACKGROUND
String
Simple constant Live Constant
Live Constant Inverse scale-by
Live Constant
Inverse
Live Constant
Scale-by
Simple scale-by Live Constant
constant
Figure 2-20. Selecting from among the many constants available in Visual ModelQ.
The Constants tab in the VisualModelQenvironment (top of Figure 2-7) currently
provides seven constant types:simple constants,standard and inverse LiveConstants,
simple scaling constants,standard and inverse scaling LiveConstants,and string con-
stants. The selection buttons for each of these constants are shown in Figure 2-20,
which is a screen capture of the top portion of the VisualModelQenvironment.
Live Constants,such as K and K in the PI controller of Figure 2-19,provide the
P I
most control.The icons of blocks have a “<< >>”symbol.After the model has com-
piled,double-click anywhere inside the block and the adjustment box of Figure 2-21
will appear. Using the adjustment box, the value of the parameter can be changed
while the model runs.A new value can be typed in with the keyboard by clicking the
cursor in the value edit box.(Note that when using the keyboard,the new value does
not take effect until the enter key is hit.) In addition,there are six logarithmic adjust-
ment buttons in the adjustment box.The double less-than block (<<) reduces the value
to the next lowest value with the first digit being 1,2,or 5.For example,if the value
of the variable is 1.75, clicking “<<” will change the value to 1, clicking again will
reduce it to 0.5, clicking again will reduce it to 0.2, and so on. Each click reduces
the value approximately by half. The double greater-than (>>) performs a similar
function except it moves to the next higher value: 1,2, 5, 10,20, and so on.
Edit box with
current value
Change sign
of constant
(disabled for
this constant) Logarithmic
adjust buttons
Figure 2-21. Adjustment box appears when double-clicking a Live Constantany time after
the model has been compiled.

2.4 SOFTWARE EXPERIMENTS:INTRODUCTION TOVISUALMODELQ (cid:3) 29
Minimum value Maximum value
Initial value Mult
Output
Documentation
Constant name
Figure 2-22. Detail of a Live Constant.
The remaining adjust buttons are straightforward.The bold single less-than button
reduces the value of the variable by about 20% for each click;the nonbold single less-
than button reduces the value by about 4%.The bold and nonbold single greater-than
blocks perform a similar function, only raising the value. If the parameter can take
on values of both signs, the +/- button will be enabled, allowing a change in sign at
the click of a button.
The LiveConstantmodel block and its nodes are shown in Figure 2-22.The initial
value node specifies the value that the constant is reset to after each compile. The
minimum and maximum nodes specify the range that the input can take on. The
multiplier and documentation nodes are standard Visual ModelQnodes.The output
makes available the value of the Live Constant so it can be wired in the model. The
value displayed in text inside the block is not scaled by the Multnode,while the value
in the output node is.
2.4.2.2 Inverse Live Constants
The inverse Live Constantworks like the standard LiveConstantexcept the output is
one divided by the parameter value and then multiplied by the value of the Multnode
(Figure 2-23).This constant is used when the model needs to scale by the inverse (1/x)
of the parameter value such as is usually the case for mass,moment of inertia,thermal
mass,capacitance,inductance,and many other physical parameters.The inverse Live
Constant is a space-saving alternative to combining a standard Live Constant and a
1/xblock.
1/K indicates
“InverseLive Constant.”
Figure 2-23. Inverse Live Constantgenerates divided output.

30 (cid:2) CHAPTER 2 CONTROL-SYSTEM BACKGROUND
Input Node Input Node
(a) (b)
Figure 2-24. Standard (a) and inverse (b) scale-by Live Constants.
2.4.2.3 Scale-by Live Constants
Scale-by Live Constants are similar to Live Constants except that the output
node is the product of an input node and the value of the constant. In fact, if the
input node is set to one, scale-by Live Constants behave identically to standard
Live Constants. The two scale-by Live Constants (standard and inverting) are shown
in Figure 2-24.
2.4.2.4 String Constants
String constants allow the model constants to be adjusted as strings.The user selects
a string from a list and the string LiveConstantblock outputs an integer value accord-
ing to the position in the list occupied by the selected string.For example,the string
LiveConstantnamed Select XNin Figure 2-25 is configured to allow the user to select
one of four strings:X0,X1,X2,and X3.Depending on which constant the user selects,
the output node will be 0,1,2,or 3,according to the position of the string within the
list.
The string Live Constant node is configured with two input nodes on the left side
of the block. The Strings node should be filled first; double-click on this node and
type in a list of string constants. The Strings node dialog box for the block of
Figure 2-25 is shown in Figure 2-26. There is no specific limit on constant length or
on the number of strings that one string LiveConstantcan hold.Next,select the Live
Constant’sinitial string by double-clicking on the upper left node.
The string Live Constant is often used with an analog switch, as is the case in
Figure 2-25. The switch has a control node at top center, the value of which deter-
mines which of the four inputs at left is routed to the output: moving from top to
bottom,0 selects the first input,1 the second,and so on.In the case of Figure 2-25,
Select XN is equal to X1, as is indicated inside the string Live Constant block. This
produces an output of 1, which is fed to the switch control node. That causes the
Position-1 (second) input node to be connected to the output node ofthe switch block.
Figure 2-25 also has an Inspector block, which can display the value of any node.
Here,the inspector shows that output of Switch4is 10.01,matching the value of the
Live Constant X1 which is connected to the Position-1 input node. Note that the
naming of the four Live Constants at left to match the list of strings in Select XN is
for clarity and has no effect on the operation of the model.

2.4 SOFTWARE EXPERIMENTS:INTRODUCTION TOVISUALMODELQ (cid:3) 31
Double click
String anywhere in string Live
Live Constant Constant blockfor the string
output node adjustment box
(current
value = 1)
Initial Value
Strings
Switch4outputs 10.01,
the value of X1, because
X1is selected by the
string Live Constant.
Figure 2-25. Astring Live Constantoutputs an integer based on user-selected character strings.
2.4.2.5 Simple Constants
The last Visual ModelQconstants are the simple constants.These constants are similar
to the Live Constant. However, the simple constants do not support the adjustment
box of Figure 2-21; changes to the value are made via double-clicking on the input
Since X1
Position occupies
0 Position 1
in the list,
1
selecting X1
2
causes “1”
3 to be output
from the
output node
Figure 2-26. The user types in a string list to configure the string Live Constantblock.

32 (cid:2) CHAPTER 2 CONTROL-SYSTEM BACKGROUND
Mult node
Input node Output node
Figure 2-27. The simple constant.
node.(Note that changing a node value is permanent after the model is saved.) Also,
neither maximum nor minimum limits can be set. The simple constants take a little
less screen space than a LiveConstantin the model diagram.Use the simple constant
for parameters that are changed only occasionally. The simple constant is shown in
Figure 2-27;the simple scale-by constant adds scaling.
2.4.2.6 Hot Connections on a Live Scope
The Live Scope supports a feature called hot connection. Anytime the model is run-
ning, double-click on the Live Scope and a Live Scope control panel will appear.
Click “Hot Connect” to close the dialog box; move the mouse over any wire or
input–output node in the model and click.The Live Scope will temporarily graph the
value of that node or wire;the scope outline will turn green to indicate that the scope
is in hot connectmode.(For two-channel LiveScopes,Channel 1 displays the hot con-
nection; Channel 2 is unaffected.) Click “Restore Scope”in the Live Scope control
panel or recompile the model to restore the scope to its original display.Note that the
scope scale and offset nodes may need to be adjusted to view the signal;any changes
to scaling and offset will be restored when the scope is restored.The operation of hot
connection is displayed in Figure 2-28. Hot connections are especially useful when
debugging a model,as wires and nodes can be viewed without adding a scope,which
forces recompilation.
2.4.3 Command Response and Control-Law Gains
Visual ModelQ is designed to simplify the process of evaluating the effects of para-
meter value variation. This is a common need when modeling control systems, for
example, in the tuning process. Tuning is the adjustment of control-loop gains to
achieve optimal performance. It is often carried out in working systems (and in
models) by observing the effect of numerous incremental changes of control-law
gains. For example, in Experiment 2A, K might be adjusted up and down in small
P
steps while observing the effect on the step response. Experiment 2A is constructed
to make this process fast and simple.
The two components of Experiment 2A that simplify tuning are the Live Constant
and the Live Scope. After model compilation, double-clicking on the Live Constant
named K brings up the K adjustment box, which allows rapid changes of value,
P P

2.4 SOFTWARE EXPERIMENTS:INTRODUCTION TOVISUALMODELQ (cid:3) 33
TheLive Scope normallyshowsCommand,
butHotConnectcan temporarily display power converter output,
without recompiling or even stopping the model.
Scope outline turns green to
indicate Hot Connectmode.
Figure 2-28. Hot connect allows temporary reconfiguration of Live Scopeswhile the model executes.
perhaps one per second.Compare this to standard modeling environments where the
model must be stopped,modified,and recompiled.A simple change can take on the
order of a minute.In addition,the Live Scopegives immediate feedback of the effect
of the new parameter,without the need for the user to issue a command to display a
plot. To experiment, launch Visual ModelQ. Click File, Open...to open the model
Experiment_2A.mqd.Click Run.Double-click on the K block and use the << and >>
P
buttons to move the value up and down. The results should be equivalent to those
shown in Figure 2-29.
2.4.4 Frequency Domain Analysis of a Control System
Control systems often need to be analyzed in the frequency domain. The most
intuitive method of frequency-domain analysis for most people is the Bode plot,
which graphs gain and phase across a range of frequencies. A gain plot displays the
amplitude of an output signal divided by the amplitude of the input signal at many
frequencies as if sine waves at many frequencies had been applied to the model. A
phase plot displays the time lag of the output compared to the input for many sine
waves.In the laboratory,the instrument that is commonly used to generate Bode plots
is called a dynamic signal analyzer (DSA).Visual ModelQprovides a DSA,which is
used regularly in Chapters 4 through 8. Experiment 2B, shown in Figure 2-30, is

| 34 (cid:2) | CHAPTER 2 | CONTROL-SYSTEM BACKGROUND |     |     |
| ---------- | --------- | ------------------------- | --- | --- |
Command
Response
|     | a)  K |  = 1         | b)  K  = 2                             | b)  K  = 0.5 |
| --- | ----- | ------------ | -------------------------------------- | ------------ |
|     |       | P            | P                                      | P            |
|     |       | Figure 2-29. | Results of varying K in Experiment 2A. |              |
P
Experiment 2A modified to include a DSA, which is shown just right of the wave-
form generator.
|     | 2.4.4.1 | The Visual ModelQ | DSA |     |
| --- | ------- | ----------------- | --- | --- |
The DSA is wired in line with the excitation path.In most cases,the DSA is used to
analyze command response and so will normally be inserted in line with the command
as it is in Figure 2-30. All DSAs read all model variables, no matter how they are
wired.In VisualModelQ,the term variablesincludes three types of signals:
|     |     | Figure 2-30. Experiment 2B: Experiment 2Awith a DSA. |     |     |
| --- | --- | ---------------------------------------------------- | --- | --- |

2.4 SOFTWARE EXPERIMENTS:INTRODUCTION TOVISUALMODELQ (cid:3) 35
• The input to 1-channel LiveScopes,
• The input to Channel 1 of 2-channel Live Scopes, such as Command in
Figure 2-30,and
• ModelQ variables blocks such as Feedbackin Figure 2-30.
The DSA here will be used to show the relationship between command and feedback.
Notice that Experiment 2B required the addition of the variable block Feedback at
top right.In Experiment 2A that node was not connected to a variable block as it was
only needed for display as Channel 2 of a Live Scope. In Experiment 2B, an explicit
variable block named Feedbackis required to grant access of the signal to the DSA.
2.4.4.2 DSANodes
The complete details on configuring a DSA go beyond the scope of this chapter.
However, a few details should be mentioned to prepare the reader for the use of
DSAs in this book. The four most important nodes of a DSA block are shown in
Figure 2-31. At left is the input node. Normally, the DSA is inactive and the input
node passes directly to the output node. However, when the user wants a new Bode
plot, the DSA is commanded to excite the model. This temporarily disconnects the
input node and replaces it with a random signal excitation.The Excitation Amplitude
and DSA Inactivenodes will be discussed in Section 2.4.4.5.
2.4.4.3 The DSADisplay
A Bode plot from a DSA is shown in Figure 2-32.This shows the relationship between
command and feedback, commonly called the closed-loop response, for Experiment
2B where K =1 and K =2;the gain plots are above and the phase plots below.Most
P P
of the time,the closed-loop gain plot will be of primary interest.The two cases here
behave similarly at low frequency (shown at left) and the plots below about 100Hz
are nearly indistinguishable.However,above 100Hz,there are significant differences,
especially where the gain of the K =2 case sharply rises before falling,displaying an
P
undesirable characteristic called peaking. The purpose of this section is to introduce
Visual ModelQ, so a detailed discussion of resulting waveforms is outside the scope
Excitation Amplitude Node
Input Node Output Node
DSA Inactive Node
Figure 2-31. Detail of DSAnodes.

36 (cid:2) CHAPTER 2 CONTROL-SYSTEM BACKGROUND
Gain 7 dB peaking in
gain at 200 Hz
Gain with K = 2
P
(Figure 2-29b)
Gain with K = 1 (Figure 2-29a)
P
2 Hz 10 Hz 100 Hz 1000 Hz
Phase Phase with K = 2
P
Phase with K = 1
P
Figure 2-32. Output of DSAfor K =1 and K =2.
P P
of this discussion. However, it may be interesting to readers to notice that the two
cases plotted in Figure 2-32 match the time-domain plots for Figures 2-29a and
2-29b,where the less stable Figure 2-29b corresponds to the plot in Figure 2-32 with
peaking.Peaking and ringing are both indicators of inadequate margins of stability.
Stability issues will be discussed in Chapter 3.
Like the Scope display,the DSA display is normally not visible when a model starts
to run.The DSA display can be made visible by double-clicking inside the DSA block
after the model has been compiled.
2.4.4.4 DSAControls
The user can request a new Bode plot when the model is running by clicking on the
GO button at bottom left of the DSA. This starts a new excitation period. For the
experiments in this book,this process will continue for roughly 1s of simulation time.
After that, a new Bode plot will be displayed. Up to four plots can be saved. Right-
click in the graph area of the DSA to bring up a pop-up menu and select Save asto
save the most recent plot.Pressing the GObutton a second time during the excitation
period cancels the command for a new Bode plot.
To the right of the GObutton,the sunglasses button hides the control panel.The
gear button brings to view a dialog box for setting up the DSA excitation signal.The

2.4 SOFTWARE EXPERIMENTS:INTRODUCTION TOVISUALMODELQ (cid:3) 37
autofind button places a cursor according to the criteria in the adjoining combo box,
which is set to 3dB in Figure 2-32. The last three buttons control the number of
cursors visible,allowing no cursors,one cursor,or two cursors.
2.4.4.5 The DSAExcitation Signal
The DSA works by generating a random command for a short period of time. The
random signal is rich—it contains all the frequencies of the Bode plot. During
the period of excitation, the DSA monitors all variables in the model. After the
excitation,the DSA executes a fast Fourier transform (FFT) to convert the recorded
data to a frequency-domain plot. When the random signal is applied to the model,
the richness of the signal allows it to excite all frequencies at once.This is ideal for a
modeling environment because it minimizes the time the DSA must excite the system.
However,it also presents problems.First,the system must remain out of saturation—
the power converter must not be driven beyond its maximum during the excitation.
If a system is driven into saturation, the excitation amplitude can be reduced using
the Excitation Amplitudenode at the top left of the DSA (see Figure 2-31).However,
if the amplitude is set too low, the signal-to-noise ratio of the system will be insuffi-
cient and the Bode plot will be distorted at high frequencies. Setting the amplitude
of the excitation is sometimes a matter of experimentation. When doing so, always
monitor the power converter output to ensure the system remains out of saturation
for the entire excitation period. For all models in this book, the amplitude is set
appropriately and users normally need not be concerned about this.
All commands except the DSA excitation must be shut off during the excitation
period. The DSA will automatically disconnect the input node so that any signals
connected to the input are disabled during DSA excitation; this is the case with the
waveform generator in Figure 2-30. If there are waveform generators connected to
other parts of the model,the DSA Inactivenode at the lower right of Figure 2-31 can
be wired to disable those generators. The DSA Inactive node is set to zero during
the excitation period; when wired to a waveform generator Enable node, the desired
behavior is realized.
2.4.5 Modeling Digital Control Systems
Experiment 2C, the final model of this chapter, will demonstrate how to model a
simple digital control system in VisualModelQ.This model,shown in Figure 2-33,is
similar to Experiment 2B except that three blocks have been added. First, the PI
controller, just below K and K, is now digital. The border area of this block is
P I
yellow in the Visual ModelQ environment and prints gray in the monochrome
Figure 2-33.
Digital PI controllers sample the error at regular periods of time. The sample
period for digital blocks is set via the controller node,the diamond at the bottom left
of the PI block.The controller can be selected from multiple digital controllers,which

38 (cid:2) CHAPTER 2 CONTROL-SYSTEM BACKGROUND
Figure 2-33. Experiment 2C: Experiment 2B with digital control.
can be running simultaneously in a VisualModelQmodel.Fortunately,most models
are simple enough that one controller is sufficient. That controller is called Main in
Experiment 2C and is near the center-left of Figure 2-33.The sole input node of the
controller block is the sample time,which can be changed while the model is running.
In Experiment 2C, that parameter is connected to a Live Constant named TSample
to simplify changing the value.
Notice that the step response in Figure 2-33 overshoots and rings in Experiment
2C.All the parameters of Experiments 2B and 2C have identical defaults so one might
have expected them to have a similar step response. Obviously, something is signifi-
cantly different.
The difference between the two models is that Experiment 2C is the digital
equivalent of Experiment 2B.The problem in Experiment 2C is that the sample time
is too long for the dynamics of the system.As a result,the system is nearly unstable.
Some experimentation can prove the point. Launch Visual ModelQ and load the file
Experiment_2C.mqd. Click Run. Now, double-click on the Live Constant named
TSample. Reduce the sample time by repeatedly clicking on the Live Constant “<<”
button. When the sample time falls below about 0.0002s, the response is equivalent
to the analog performance.This is shown in Figure 2-34.
2.4.6 Visual ModelQ and This Book
This section has introduced several functions of Visual ModelQ used in this
book.All key points of this book are demonstrated in Visual ModelQmodels.Readers
are encouraged to run these experiments and work the exercises at the end of each
chapter.

2.5 EXERCISES (cid:3) 39
Command
Response
(a) (b)
Figure 2-34. From Experiment 2C: Reducing sample time can stabilize a system. (a) TSample =0.002s;
(b) TSample =0.0002s.
2.5 Exercises
1. Open Experiment_2A.mqd and click the Runbutton.
A. Change the gain K from 1 to 2, and then raise it to 5. Describe what
P
happens in the command response.What conclusion could you draw?
B. Set K =2 and change waveform to triangle. Are signs of marginal stabil-
P
ity easier or harder to recognize? Repeat for sine wave and s-curve. What
conclusion could you draw?
C. Restore K to 1. Set K to 0. Describe what happens in the command
P I
response. Set K to a range of values from 10 to 1000. Describe what
I
happens in the command response. What conclusion could you draw?
2. Open Experiment_2B.mqdand click the Runbutton.
A. Run a Bode plot.Find the -3dB frequency (the frequency where the gain
falls to -3dB) using the autofind combo box at the bottom of the DSA
display window.
B. Reduce control-loop gains.Set K to 0.5 and set K to 50.What is the gain
P I
at the frequency from 2A.
C. Compare 2A and 2B. What conclusion could you draw?
3. Open Experiment_2C.mqdand click the Runbutton.
A. Change TSample to several values spanning the range between 0.002 and
1¥10-5s. Over what range does the sample time significantly affect
command response as viewed in the Live Scope?
B. Does faster sampling make the system more stable or less stable?
C. Set the sample time to 0.0001s. Compare the step response of the digital
system in Experiment 2C to the analog system in Experiment 2B. Repeat
with K =2.What conclusion could you draw?
P

Chapter 3
Review of the
Frequency Domain
In this chapter...
• Overview of the s-domain and the z-domain
• Detailed presentation of Mason’s signal flow graphs
• Bode plots
• Measuring command response and stability
• The open-loop method
• A zone-based tuning procedure
This chapter will review the frequency domain, which is the basis for most
analysis performed on control systems. The principles reviewed in this chapter are
commonly taught in control-systems books,courses,and seminars so that many readers
will find much of it familiar. In addition to the review, the final section provides
a process for consistent tuning of controller gains; this process will be necessary
to measure performance objectively, for example, when comparing traditional and
observer-based systems. In addition, the same process will be applied to tuning
observers in later chapters. For reference, most of this discussion is taken from
[11, Chaps.2–5].
3.1 Overview of the s-Domain
The Laplace transform underpins classic control theory [17, 37] and is defined in
Equation3.1 [7,p.102] as
41

42 (cid:2) CHAPTER 3 REVIEW OF THE FREQUENCY DOMAIN
•
F(s)=Ú f(t)e-stdt, (3.1)
o
where f(t) is a function of time,sis the Laplace operator,and F(s) is the transformed
function.The terms F(s) and f(t),commonlyknown as a transformpair,represent the
same function in the two domains.For example,if f(t)=sin(wt),then F(s)=w/(w2+s2).
The Laplace transform moves functions between the time and the frequency domains.
The most important benefit of the Laplace transform is that it provides s,the Laplace
operator,and through that the frequency-domain transfer function.
3.1.1 Transfer Functions
Frequency-domain transfer functions describe the relationship between two signals
as a function of s. For example, consider an integrator as a function of time. From
Table 3-1, the integrator has an s-domain transfer function of 1/s. So, it can be said
for a system that produced an output,V ,which was equal to the integral of the input,
O
V,that:
I
V (s) 1
O = . (3.2)
V (s) s
I
The Laplace operator is a complex (as opposed to real or imaginary) variable. It
is defined as
s ∫s+jw. (3.3)
The constant j is -1. The w term translates to a sinusoid in the time domain; s
translatesto an exponential (est) term.The primary concern here is with steady-state
sinusoidal signals, in which case s=0. So in this book, s will be ignored. To evaluate
the DC response of a transfer function, set sto zero.
3.1.2 Linearity and the Frequency Domain
A frequency-domain transfer function is limited to describing elements that are linear
and time invariant. These are severe restrictions and, in fact, virtually no real-world
system fully meets them.The three criteria that follow define these attributes,the first
two defining linearity and the third defining time invariance.
1. Homogeneity.Assume that an input to a system r(t) generates an output c(t).
For an element to be homogeneous,an input k¥r(t) would have to generate an output
k¥c(t),for any value of k.An example of homogeneous behavior is an ideal resistor
where V=IR.An example of nonhomogeneous behavior is saturation where twice as
much input delivers less than twice as much output.

|     |     | 3.1 OVERVIEW | OF THE s-DOMAIN | (cid:3) 43 |
| --- | --- | ------------ | --------------- | ---------- |
2. Superposition.Assume that an element,when subjected to the input r(t) will  1
generate the output c (t). Further, assume that this same element, when subjected
1
to  the  input  r(t)  will  generate  the  output  c (t). Superposition  requires  that  if
2 2
the  element  is  subjected  to  the  input, r (t)+r (t), it  will  produce  the  output,
1 2
c (t)+c (t) [16,p.93;36].
1 2
3. Time invariance. Assume that an element has an input r(t) that generates
an output c(t). Time invariance requires that r(t-t) will generate c(t-t) for all
t>0.
So the controls engineer faces a dilemma: transfer functions, the basis of classic
control theory,require linear,time invariant (LTI) systems,but no real-world system
is completely LTI.This is a complex problem that is dealt with in many ways.However,
for most control systems, the solution is simple: design components close enough to
being LTI that the non-LTI behavior can be ignored or avoided.
3.1.3 Examples of s-Domain Transfer Functions
Examples of transfer functions used in control laws are shown in Table 3-1. These
functions can all be derived from Equation 3.1.
Integration and differentiation are the simplest operations. The s-domain opera-
tion of integration is 1/s and of differentiation is s. Filters are commonly used
by control-systems designers such as when low-pass filters are added to reduce noise.
Table 3-1 lists the s-domain representation for a few common examples. A compen-
sator is a specialized filter: one that is designed to provide a specific gain and phase
shift at one frequency. The effects on gain and phase either above or below that
TABLE 3-1 TRANSFER FUNCTIONS OF CONTROLLER ELEMENTS
| Operation       | Transfer function |     |     |     |
| --------------- | ----------------- | --- | --- | --- |
| Integration     | 1/s               |     |     |     |
| Differentiation | s                 |     |     |     |
e-sT
Delay
Simple filters
| Single-pole low-pass filter         | K/(s+K)               |        |     |     |
| ----------------------------------- | --------------------- | ------ | --- | --- |
| Double-pole low-pass filter         | w2/(s2+2zws+w2)       |        |     |     |
| Notch filter                        | (s2+w2)/(s2+2zws+w2)  |        |     |     |
|                                     | (s2+2zw s+w2)/(s2+2zw | s +w2) |     |     |
| Bilinear-quadratic (bi-quad) filter | N N                   | D      | D   |     |
Compensators
| Lag | K(t s+1)/(t s+1),t | >t  |     |     |
| --- | ------------------ | --- | --- | --- |
|     | Z P                | P Z |     |     |
| PI  | (K/s+1)K           |     |     |     |
I P
| PID  | (K/s+1+K s)K            |                  |        |     |
| ---- | ----------------------- | ---------------- | ------ | --- |
|      | I D                     | P                |        |     |
| Lead | 1+K D s/(t D s+1)or [(t | D +K D )s +1]/(t | D s+1) |     |

44 (cid:2) CHAPTER 3 REVIEW OF THE FREQUENCY DOMAIN
frequency are secondary.Table 3-1 shows a lag compensator,a proportional-integral
(PI) compensator,and a lead compensator.
Delays add time lag without changing amplitude. Since microprocessors have
inherent delays for sampling,the delay function is especially important when analyz-
ing digital controls.A delay of Tseconds is defined in the time domain as
c(t)=r(t-T). (3.4)
The corresponding function in the frequency domain is
T (s)=e-sT. (3.5)
Delay
3.1.4 Block Diagrams
Block diagrams are graphical representations developed to make control systems
easier to understand. Blocks are marked to indicate transfer functions. In North
America,transfer functions are usually indicated with their s-domain representation.
The convention in Europe is to use schematic representation of a step response;
AppendixC provides a listing of many North American and European block-diagram
symbols.
Block diagrams can be simplified by combining blocks.Two blocks in parallel can
be combined as their sum; two blocks in series can be represented as their product.
When blocks are arranged to form a loop,they can be reduced using the G/(1+GH)
rule. The forward path is G(s) and the feedback path is H(s). The transfer function
of the loop is G(s)/(1+G(s)H(s)) as shown in Figure 3-1.
The G/(1+GH) rule can be derived by observing in Figure 3-1a that the error signal
(E(s)) is formed from the left as:
E(s)=R(s)-C(s)¥H(s).
E(s) can also be formed from the right side (from C(s) back through G(s)) as
E(s)=C(s) G(s).
+ E(s)
R(s) G(s) C(s) G(s)
_ R(s) C(s)
1 + G(s)H(s)
H(s)
(a) (b)
Figure 3-1. Simple feedback loop in equivalent forms.

|     |     | 3.1 OVERVIEW | OF THE s-DOMAIN | (cid:3) 45 |
| --- | --- | ------------ | --------------- | ---------- |
So,
| R(s)-C(s)¥H(s)=C(s) | G(s). |     |     |     |
| ------------------- | ----- | --- | --- | --- |
One or two steps of algebra produce:
C(s) G(s)
|     | .   |     | (3.3b) |     |
| --- | --- | --- | ------ | --- |
=
R(s) 1+G(s)H(s)
3.1.4.1 Mason’s Signal Flow Graphs
An alternative to the G/(1+GH) rule developed by Mason [10,p.69;7,p.162;28;29;
31] provides graphical means for reducing block diagrams with multiple loops. The
formal process begins by redrawing the block diagram as a signal flow graph.1 The
control system is redrawn as a collection of nodes and lines.Nodes define where three
lines meet; lines represent the s-domain transfer function of blocks. Lines must be
unidirectional;when drawn,they should have one and only one arrowhead.A typical
block diagram is shown in Figure 3-2, and its corresponding signal flow graph is
shown in Figure 3-3.
Step-by-step procedure. This section will present a step-by-step procedure to produce
the transfer function from the signal flow graph based on Mason’s signal flow graphs.
The signal flow graph of Figure 3-3 will be used for an example.This graph has two
independent inputs, R(s) and D(s). The example will find the transfer function from
these two inputs to D (s).
O
D(s) C(s)
+
| G (s) | G (s) | Y(s) |     |     |
| ----- | ----- | ---- | --- | --- |
| P     | S     |      |     |     |
+
| D (s) |     | +   |     |     |
| ----- | --- | --- | --- | --- |
R(s)
| O G | (s) |     |     |     |
| --- | --- | --- | --- | --- |
| CO  |     | _   |     |     |
+
| G (s) | G (s) | Y (s) |     |     |
| ----- | ----- | ----- | --- | --- |
| PEst  | SEst  | O     |     |     |
+
C
(s)
O
Figure 3-2. An example control-loop block diagram.
1For convenience,this step will be omitted in most cases and the block diagram will be used directly.

| 46 (cid:2) | CHAPTER 3 REVIEW | OF THE FREQUENCY | DOMAIN |     |     |     |
| ---------- | ---------------- | ---------------- | ------ | --- | --- | --- |
D(s)
C(s)
Y(s)
|     |     |     | G (s) | G     | (s) |     |
| --- | --- | --- | ----- | ----- | --- | --- |
|     |     |     | P     |       | S   |     |
|     |     |     |       | G (s) |     |     |
CO
R(s)
|     |     |     |     | D (s) |     |     |
| --- | --- | --- | --- | ----- | --- | --- |
|     |     |     |     | O     |     | -1  |
Y (s)
O
|     |     |     | G (s) | G    | (s) |     |
| --- | --- | --- | ----- | ---- | --- | --- |
|     |     |     | PEst  | SEst |     |     |
C (s)
O
Figure 3-3. Signal flow graph for Figure 3-2.
Step 1:Find the loops. Locate and list all loop paths.For the example of Figure 3-3,
there is one loop:
|     |     | L   | =-G (s)¥G | (s)¥G | (s). |     |
| --- | --- | --- | --------- | ----- | ---- | --- |
|     |     |     | 1 PEst    | SEst  | CO   |     |
Step 2: Find the determinant of the control loop. Find the determinant, D, of the
control loop,which is defined by the loops:
D=1-(sum of all loops)
+(sum of products of all combinations of two nontouching loops)
-(sum of products of all combinations of three nontouching loops)
+....
Two loops are said to be touching if they share at least one node.For this example
there is only one loop:
|     |     | D=1+G | (s)¥G | (s)¥G | (s). |     |
| --- | --- | ----- | ----- | ----- | ---- | --- |
|     |     |       | PEst  | SEst  | CO   |     |
Step 3:Find all the forward paths. The forward paths are all the different paths that
flow from the inputs to the output.For the example of Figure 3-3,there is one forward
|     | path from D(s) to D | (s) and two from R(s): |     |     |     |     |
| --- | ------------------- | ---------------------- | --- | --- | --- | --- |
O
|     |     | P =D(s)¥G | (s)¥G | (s)¥G    | (s) |      |
| --- | --- | --------- | ----- | -------- | --- | ---- |
|     |     | 1         | P     | s        | CO  |      |
|     |     | P =R(s)¥G | (s)¥G | (s)¥G    | (s) |      |
|     |     | 2         | P     | s        | CO  |      |
|     |     | P =R(s)¥G | (s)¥G | (s)¥-1¥G |     | (s). |
|     |     | 3         | PEst  | SEst     |     | CO   |

|     |     |     |     |     |     |     | 3.1 OVERVIEW |     | OF THE | s-DOMAIN | (cid:3) 47 |
| --- | --- | --- | --- | --- | --- | --- | ------------ | --- | ------ | -------- | ---------- |
Step 4: Find the cofactors for each of the forward paths. The cofactor (D ) for a
K
particular path (P ) is equal to the determinant (D) less loops that touch that path.
K
For the example of Figure 3-3,all cofactors are 1 because every forward path includes
G (s), which is in L,the only loop.
| CO  |     | 1   |     |      |        |     |     |     |     |     |     |
| --- | --- | --- | --- | ---- | ------ | --- | --- | --- | --- | --- | --- |
|     |     |     |     | D =D | =D =1  |     |     |     |     |     |     |
|     |     |     |     | 1    | 2 3    |     |     |     |     |     |     |
Step 5:Build the transfer function. The transfer function is formed as the sum of all
the paths multiplied by their cofactors,divided by the determinant:
|     |     |     |     | Â(P | D   | )   |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
K K
|     |     |     | T(s)= |     | K   | .   |     |     | (3.6) |     |     |
| --- | --- | --- | ----- | --- | --- | --- | --- | --- | ----- | --- | --- |
D
| For the example of |     | Figure 3-3,the signal D |     |     | (s) is |     |     |     |     |     |     |
| ------------------ | --- | ----------------------- | --- | --- | ------ | --- | --- | --- | --- | --- | --- |
O
|            | (G  | (s)G (s)-G | (s)G | (s))G | (s) |       | G   | (s)G (s)G | (s) |     |     |
| ---------- | --- | ---------- | ---- | ----- | --- | ----- | --- | --------- | --- | --- | --- |
| D (s)=R(s) | P   | S          | PEst | SEst  | CO  | +D(s) | P   | S         | CO  | .   |     |
O
|     |     | 1+G  | (s)G | (s)G | (s) |     | 1+G  | (s)G | (s)G | (s) |     |
| --- | --- | ---- | ---- | ---- | --- | --- | ---- | ---- | ---- | --- | --- |
|     |     | PEst | SEst | CO   |     |     | PEst | SEst | CO   |     |     |
Using a similar process, C (s) can be formed as a function of C(s) and D(s):
O
|            |     | G (s)(1+G | (s)G | (s)G | (s))  | G   | (s)G   | (s)G (s)G | (s) |     |     |
| ---------- | --- | --------- | ---- | ---- | ----- | --- | ------ | --------- | --- | --- | --- |
|            |     | PEst      | P    | S    | CO    |     | PEst P | S         | CO  |     |     |
| C (s)=R(s) |     |           |      |      | +D(s) |     |        |           |     | .   |     |
| O          |     | 1+G       | (s)G | (s)G | (s)   | 1+G | (s)G   | (s)G      | (s) |     |     |
|            |     | PEst      | SEst | CO   |       |     | PEst   | SEst      | CO  |     |     |
As will be discussed in later chapters, a great deal of insight can be gained from
transfer functions of this sort. Using Mason’s signal flow graphs, transfer functions
of relatively  complex  block  diagrams  can  be  written  by  inspection. Using  the
G/(1+GH) rule to derive transfer functions from multiple-loop block diagrams will
work but is more tedious.
It may be of interest that Figure 3-2 is an observer. The two blocks above repre-
sent the plant (G (s)) and the sensor (G (s)); those below are the approximations of
|     | P   |     |     | S   |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
those functions: the estimated plant, G (s), and the estimated sensor, G (s). The
|     |     |     |     | PEst |     |     |     |     | SEst |     |     |
| --- | --- | --- | --- | ---- | --- | --- | --- | --- | ---- | --- | --- |
error between the actual and the estimated functions is fed through the observer com-
pensator, G (s), which has high gains and will drive the output of the model (that
CO
is,the estimated plant and sensor) toward the output of the actual system.This form
and its associated transfer functions will be the subject of the remaining chapters of
this book.
3.1.5 Phase and Gain
The sine wave is unique among repeating waveforms;it is the only waveform that does
not change shape when passing through LTI blocks. A sine-wave input generates a
sine-wave output at the same frequency; the only differences possible between input

| 48 (cid:2) | CHAPTER 3 REVIEW | OF THE FREQUENCY | DOMAIN |     |     |     |
| ---------- | ---------------- | ---------------- | ------ | --- | --- | --- |
and output are the gain and the phase. In other words, the response of an LTI
system to any one frequency can be characterized completely, knowing only phase
and gain.
Gain measures the difference in amplitude of input and output. Gain is often
expressed in decibels or dB,which is defined as
|     |     |     | Gain∫20*Log | 10 (OUT | IN), | (3.7) |
| --- | --- | --- | ----------- | ------- | ---- | ----- |
where OUT and IN are the magnitudes of the output and input sine waves. This is
shown in Figure 3-4. Phase describes the time shift between input and output. This
lag can be expressed in degrees, where 360° is equivalent to one period of the input
sine wave.Usually the output is considered as lagging (to the right of) the input.So,
phase is defined as
|     |     |     | Phase ∫-360¥F¥t |     | °.  | (3.8) |
| --- | --- | --- | --------------- | --- | --- | ----- |
DELTA
Frequently, the gain and phase of a transfer function are shown as a phasor, using
the form gaindB–-Phase°;for example,-3dB–-45°.
Phase and gain can be calculated from the transfer function by setting s=j¥2pf,
where Fis the excitation frequency in Hertz.The response of a transfer function can
be converted from a complex number to a phasor by using the magnitude of the
number in decibels and taking the arc-tangent of the imaginary portion over the real,
|     | adding 180°if | the real part is negative. |     |     |     |     |
| --- | ------------- | -------------------------- | --- | --- | --- | --- |
|     |               | IN                         |     |     | t   |     |
delta
Voltage
OUT
|     |     |     | Input(t) | Output(t) |     |     |
| --- | --- | --- | -------- | --------- | --- | --- |
time
|     |     | Gain = 20 Log | (OUT/IN)    | Phase = -360 xFxt |       |     |
| --- | --- | ------------- | ----------- | ----------------- | ----- | --- |
|     |     |               | 10          |                   | delta |     |
|     |     |               | Figure 3-4. | Gain and phase.   |       |     |

3.1 OVERVIEW OF THE s-DOMAIN (cid:3) 49
20 dB
-3dB @ 10 Hz
0 dB
-20 dB
Gain -40 dB
10 Hz 100 Hz
90 deg Phase
0 deg -45 d eg @ 10 Hz
-90 deg
-180 deg
Figure 3-5. Typical Bode plot.
3.1.6 Bode Plots
Bode plots display phasors graphically; the gain in decibels and phase in degrees
are plotted against the frequency in Hertz. The horizontal scale is logarithmic and
the vertical scales are linear. Figure 3-5 shows a typical Bode plot. The frequency
spans from 2 to 500Hz (see legend just below the plot). The gain is shown in the
top graph scaled at 20dB per division with 0dB at the solid center line. Phase is
shown in the bottom graph scaled at 90°per division,again with 0°at the solid center
line.
3.1.7 Measuring Performance
Objective performance measures provide a path for problem identification and
correction. This section will discuss the two most common performance measures:
command response and stability.
3.1.7.1 Experiment 3A: Measuring Performance
Experiment 3A (Figure 3-6) will be used to discuss performance issues. Experiment
3A is similar to Experiment 2B with two exceptions. First, the Live Scope has been
enlarged slightly to show more detail.The two nodes at the bottom left of the block
determine the size of the display. Second, a variable block Error has been added to
give the DSA access to this signal;the DSA needs access to the loop error to support
the open-loop method,which will be discussed later in this chapter.

50 (cid:2) CHAPTER 3 REVIEW OF THE FREQUENCY DOMAIN
Figure 3-6. Experiment 3A, used to demonstrate performance measurement.
3.1.7.2 Command Response
Command response measures how quickly a system follows the command.In the time
domain, the most common measure of command response is probably settling time
to a step.True,few systems are subjected to step commands in normal operation.Still,
the step response is useful because responsiveness can be measured on a scope more
easily from a step than from most other waveforms.
Settling time is measured from the front edge of the step to the point where the
feedback is within a certain value (typically between 1 and 10%) of the commanded
value. If the response overshoots by more than the settling criterion, the system is
considered settled only after the feedback has returned to within the settling criterion.
For example, Figure 3-7a shows the step response of a control system to ±1 unit
command. The excursion is 2 units so the system will be settled when the command
is within 5% (0.1 units) of the final command or 1.0 ± 0.1 units. Since the feedback
overshoots by more than 0.1 units, the system is settled well after the peak of the
overshoot, when the feedback falls to 1.1 units. That time, shown in Figure 3-7a, is
about 0.02s.
Figure 3-7b shows a comparatively sluggish system; it requires 0.075s to settle to
5%.To create a system with these characteristics,the control-law gains of Experiment
3A were reduced from their default values: K was reduced from 1.0 to 0.25 and
P
K was reduced from 100 to 25. As expected, lower control-law gains produce less
I
responsive performance.

3.1 OVERVIEW OF THE s-DOMAIN (cid:3) 51
Command
Signal returns to
5% after overshoot
ª 0.02s Feedback ª 0.075s
(a) (b)
Figure 3-7. Step response of (a) responsive (K =1, K =100) and (b) sluggish systems.
P I
(K =0.25, K =25).
P I
Response can also be measured in the frequency domain by inspecting the gain
plot. Most control systems demonstrate good command response at low frequencies
but become unresponsive at high frequencies.At low frequencies,the controller is fast
enough to govern the system. As the frequency increases, the controller cannot keep
up. Thinking of the transfer function, this means the gain at low frequencies will be
approximately unity (1) but will be much less than unity at high frequencies.Consider
a power supply that is advertised to produce sine-wave voltages up to 100Hz.Such a
power supply should be nearly perfect at low frequencies such as 1Hz,begin to struggle
as the frequency increases to its rated 100Hz, and produce very low amplitude
sinusoids at high frequencies, say, above 10kHz. Translating this to a Bode plot, the
gain would be about unity (0dB) at low frequencies, start falling at mid-range
frequencies,and continue falling to very low values at high frequencies.This is typical
for control-system Bode plots.
Figure 3-8a shows the Bode plot for the system evaluated in Figure 3-7a. The
frequency range spans from 2 to 1000Hz. At low frequency, the gain is unity (0dB).
As the frequency increases,the gain rises a bit and then begins to fall.At the highest
frequency shown, the gain has fallen more than two divisions, or -40dB, which is
equivalent to a gain of less than 1%. As the frequency increases, the gain will con-
tinue to fall. Closed-loop responsiveness is commonly measured in the frequency
domain as the bandwidth, the frequency where the gain has fallen to -3dB, or to a
gain of about 70%.In Figure 3-8a,the bandwidth is about 180Hz.
Figure 3-8b shows the Bode plot for the system of Figure 3-7b. The Bode plot
for the sluggish system shows the bandwidth has fallen to 27.2Hz. The bandwidth,
like the settling time, shows the system in Figures 3-7a and 3-8a to be much more
responsive.

52 (cid:2) CHAPTER 3 REVIEW OF THE FREQUENCY DOMAIN
-3dB at 180 Hz -3dB at 27.2 Hz
Gain Gain
Phase Phase
(a) (b)
Figure 3-8. Frequency response (Bode plot) of (a) responsive and (b) sluggish systems.
3.1.7.3 Stability
Stability describes how predictably a system follows a command.In the time domain,
stability is most commonly measured from the step response. The key characteristic
is overshoot: the ratio of the peak of the response to the commanded change. The
amount of overshoot that is acceptable in applications varies from 0 to perhaps 40%.
Figure 3-9 shows the step response of two controllers. In Figure 3-9a, which is
identical to the system from Figure 3-7a, the overshoot is a modest 20%.
A system with lower margins of stability is created in Figure 3-9b by changing the
gains:K is reduced to 0.25 and K is increased to 250.In Figure 3-9b,the overshoot
P I
is more than 50%; worse, the overshoot is followed by ringing. Both systems are
stable, but the margin of stability for the system on the right is too small for most
applications.
Stability can also be measured from a system Bode plot; again the information is
in the gain plot. As discussed above, at low frequencies, the gain will be at 0dB for
most control systems and will fall off as the frequency increases. If the gain rises
significantly before it starts falling, it indicates marginal stability. This phenomenon
is called peaking. The amount of peaking is a measure of stability. For practical
systems,allowable peaking ranges from 0 to perhaps 4dB.The two systems that were
measured in the time domain in Figure 3-9 are measured again in Figure 3-10 using
the frequency domain. Note Figure 3-10b with high peaking corresponds to the
scope trace in Figure 3-9b with high overshoot.
The correlation between time and frequency domains can be seen by viewing the
systems shown in Figures 3-7 through 3-10.Settling time correlates to bandwidth and
overshoot correlates to peaking.For these simple systems,measures in either domain

3.1 OVERVIEW OF THE s-DOMAIN (cid:3) 53
Command
ª20% ª55%
Overshoot Overshoot
Feedback
Ringing
(a) (b)
Figure 3-9. Step response of (a) stable (K =1, K =100) and (b) marginally stable
P I
(K =0.25, K =250) systems.
P I
work well.The natural question is why both measures are needed.The answer is that
in realistic systems the time domain is more difficult to interpret. Many phenomena
in control systems occur in combinations of frequencies; for example, there may
simultaneously be a mild resonance at 400Hz and peaking at 60Hz. Also, feedback
resolution may limit the ability to interpret the response to small-amplitude steps.
In real-world control systems,gleaning precise quantitative data from a step response
is often impractical.
≈7 dB peaking
≈1 dB peaking
Gain Gain
Phase Phase
(a) (b)
Figure 3-10. Frequency response (Bode plot) of (a) stable and (b) marginally stable systems.

54 (cid:2) CHAPTER 3 REVIEW OF THE FREQUENCY DOMAIN
Bode plots display effects at multiple frequencies with ease; correctly measured,
Bode plots are less sensitive to resolution limitations. Thus, Bode plots can be relied
upon to provide accurate measurements in real-world systems.However,time-domain
plots are still often the preferred measurement because the equipment to make these
measurements (chiefly, the oscilloscope) is readily available. Bode plots require a
dynamic-signal analyzer (DSA),a device rarely found in laboratories.
3.2 Overview of the z-Domain
Thez-domain is used to analyze digital controllers.The key feature of thez-domain
is that it allows delays resulting from sampling to be accounted for easily.Thes- and
z-domainsare so closely related that it may be a misnomer to refer to them as being
in different domains.The basic principles—transfer functions,phase and gain,block
diagrams,and Bode plots—are the same for both.
Digital controllers process data in regular intervals. The length of the intervals
is referred to as T, the cycle or sample time. The z-domain is an extension of the
s-domain [17]. It is based on the s-domain delay operation, which was shown in
Equation 3.5 to be e-sT.If f(t) is delayed N¥Tseconds,then its Laplace transform is
e-sNTF(s) or (e-sT)NF(s).
3.2.1 Definition of z
The term z is defined as e+sT [16, p. 127], which implies that 1/z is e-sT, the delay
operation. Developing the z-domain based on this simple equality may appear to
require unwarranted effort. However, digital systems need to include the effects of
delays so frequently that the effort is justified.
In the strictest sense,thes-domain is for continuous (not analog) systems andz is
for sampled (not digital) systems.Sampledis synonymous with digitalbecause digital
systems normally are sampled;computers,the core of most digital controllers,cannot
process data continuously. On the other hand, most analog systems are continuous.
Recognizing this, digital in this book will imply sampled and analog will imply
continuous.
3.2.2 z-Domain Transfer Functions
Transfer functions in z are similar to those in sin that both are usually ratios of poly-
nomials.Several z-domain transfer functions are provided in Table 3-2.For example,
consider a single-pole low-pass filter with a break frequency of 100Hz (628rad/s) and
a sample time (T) of 0.001s.From Table 3-2, the transfer function would be:
C(z) z(1-e-0.628) 0.4663z
=T(z)= = . (3.9)
R(z) z-e-0.628 z-0.5337

|     |     |     |     |     |     | 3.2 OVERVIEW | OF THE z-DOMAIN | (cid:3) 55 |
| --- | --- | --- | --- | --- | --- | ------------ | --------------- | ---------- |
TABLE 3-2 UNITY-DC-GAIN S-DOMAIN AND Z-DOMAIN FUNCTIONS
| Operation   | s-Domain transfer |     |     | z-Domain transfer function |     |     |     |     |
| ----------- | ----------------- | --- | --- | -------------------------- | --- | --- | --- | --- |
| Integration | 1/s               |     |     | Tz/(z-1)                   |     |     |     |     |
(accumulation)
TÊz+1ˆ
| Trapezoidal | 1/s |     |     |     |     |     |     |     |
| ----------- | --- | --- | --- | --- | --- | --- | --- | --- |
2Ëz-1¯
integration
| Differentiation | s   |     |     | (z-1)/Tz |     |     |     |     |
| --------------- | --- | --- | --- | -------- | --- | --- | --- | --- |
(simple
difference)
1+aÊz-1ˆ,0<a<1
| Inverse trapezoidal | s   |     |     |     |     |     |     |     |
| ------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
T Ëz+a¯
differentiation
| Delay Tseconds | e-sT |     |     | 1/z |     |     |     |     |
| -------------- | ---- | --- | --- | --- | --- | --- | --- | --- |
Simple filters
(w=2pF)
| Single-pole | w/(s+w) |     |     | z(1-e-wT)/(z-e-wT) |     |     |     |     |
| ----------- | ------- | --- | --- | ------------------ | --- | --- | --- | --- |
low-pass
|           | w2/(s2+2zws+w2) |     |     | Az2/(z2+Bz+B) |                |         |     |     |
| --------- | --------------- | --- | --- | ------------- | -------------- | ------- | --- | --- |
| Two-pole  | n               |     | n n |               | 1              | 2       |     |     |
| low-passa |                 |     |     | B             | =-2e-VwNTcos(w | T 1-z2) |     |     |
|           |                 |     |     | 1             |                | N       |     |     |
|           |                 |     |     | B             | =e-2zwNT       |         |     |     |
2
|     |     |     |     | A=1+B | +B  |     |     |     |
| --- | --- | --- | --- | ----- | --- | --- | --- | --- |
|     |     |     |     |       | 1   | 2   |     |     |
z=Damping
| Two-pole | (s2+w2)/     |     |     | K(z2+Az+A)/(z2+Bz+B) |                |         |     |     |
| -------- | ------------ | --- | --- | -------------------- | -------------- | ------- | --- | --- |
|          |              | n   |     |                      | 1              | 2 1     | 2   |     |
| notcha   | (s2+2zws+w2) |     |     | B                    | =-2e-VwNTcos(w | T 1-z2) |     |     |
|          |              | n   | n   | 1                    |                | N       |     |     |
|          |              |     |     | B                    | =e-2zwNT       |         |     |     |
2
|     |     |     |     | A 1 | =-2cos(w | N T) |     |     |
| --- | --- | --- | --- | --- | -------- | ---- | --- | --- |
|     |     |     |     | A   | =1       |      |     |     |
2
|     |     |     |     | K=(1+B | +B)/(1+A | +A) |     |     |
| --- | --- | --- | --- | ------ | -------- | --- | --- | --- |
|     |     |     |     |        | 1        | 2 1 | 2   |     |
z=Damping
Compensators
| PI   | (K/s+1)K I | P         |     | (KTz/(z-1)+1)K I |                             | P   |     |     |
| ---- | ---------- | --------- | --- | ---------------- | --------------------------- | --- | --- | --- |
| Lead | 1+K        | s·w/(s+w) |     | 1+K              | (z-1)/Tz·z(1-e-wT)/(z-e-wT) |     |     |     |
|      |            | D         |     |                  | D                           |     |     |     |
a If z>1,negate the term under the radical and substitute hyperbolic cosine for cosine.
The  filters  in  Table  3-2  are  developed  by  replacing  polynomials  of s-domain
functions with the equivalent z-domain polynomials. For example, the term (s-a) is
replaced by (z−e-aT);
|     | this process is repeated until all terms of |     |     |     |     | s are replaced by z. |     |     |
| --- | ------------------------------------------- | --- | --- | --- | --- | -------------------- | --- | --- |
Finally, a constant term is added so that the amplitude of the function at DC2(z=1)
is 1.
2The DC gain of a transfer function of z is evaluated by setting z to 1, which is equivalent to setting
sto 0.

| 56 (cid:2) | CHAPTER 3 REVIEW         | OF THE FREQUENCY | DOMAIN |     |     |
| ---------- | ------------------------ | ---------------- | ------ | --- | --- |
|            | 3.2.3 Bilinear Transform |                  |        |     |     |
An alternative to Table 3-2 for determining the z-domain equivalent of an s-domain
|     | transfer function is to approximate sas a function of |     |     | z:  |     |
| --- | ----------------------------------------------------- | --- | --- | --- | --- |
2Êz-1ˆ
|     |     |     | sª      | .   | (3.10) |
| --- | --- | --- | ------- | --- | ------ |
|     |     |     | T Ëz+1¯ |     |        |
This is called the bilinear transformation and is developed in Appendix D. This
text will rely on Table 3-2 because it is usually less tedious than use of the bilinear
transformation.
|     | 3.2.4 z | Phasors |     |     |     |
| --- | ------- | ------- | --- | --- | --- |
Phasors in zare similar to phasors in s.Again,the transfer function is evaluated with
complex (versus real) math to determine the phase and gain at one frequency. The
resulting complex number represents gain and phase as it did in the s-domain; the
|     | only difference is that zmust be evaluated instead of |     |     | s.  |     |
| --- | ----------------------------------------------------- | --- | --- | --- | --- |
Evaluating zrequires the following identity:
|     |     | ejx =cos(x)+ | j ¥sin(x), | where j = -1. |     |
| --- | --- | ------------ | ---------- | ------------- | --- |
Substituting zat steady state (s=-jw),
|     |                  | z=e+sT            | =e+jwT =cos(wT)+      | j ¥sin(wT). |     |
| --- | ---------------- | ----------------- | --------------------- | ----------- | --- |
|     | The magnitude of | this equation is: |                       |             |     |
|     |                  |                   | z = cos2(wT)+sin2(wT) | =1.         |     |
And the angle is
Êsin(wT)ˆ
–(z)=tan-1
Ëcos(wT)¯
=tan-1(tan(wT))
=wT.
This implies that the phasor representation for zis
|     |     |     | z=e+sT| =1–+wT. |     | (3.11)  |
| --- | --- | --- | --------------- | --- | ------- |
s=jw
The results of the equivalent filters in the s- and z-domains are similar but not
identical.Digital functions are never identical to their analog counterparts,but they can

3.2 OVERVIEW OF THE z-DOMAIN (cid:3) 57
be designed to be equivalent in a single facet of operation. A key advantage of the
bilinear transformation is that it can be used to establish exact equivalence between
the s-domain and the z-domain functions at one frequency; this requires the use of
prewarping,a technique covered in Appendix D.
3.2.5 Bode Plots and Block Diagrams in z
Bode plots in the digital systems (that is, the z-domain) are the same as those in
the s-domain.Block diagrams in the z- and s-domain are also the same.They can be
combined with the G/(1+GH) rule or Mason’s signal flow graphs.
3.2.6 Sample-and-Hold
Digital controllers calculate the output once each cycle and hold it constant until the
next cycle.This sample-and-hold (S/H) is present in virtually all digital systems.The
effect of holding the output constant introduces phase lag because the output is aging
from the time it is stored.At the start of the cycle the data is fresh,but by the end of
the cycle,the output is a full cycle old.Since the stored data are,on average,one-half
cycle old,the S/H acts approximately like a delay of a half cycle
T (z)ªe-sT2 =1–(-wT 2)rad (3.12)
SH
or,in degrees and Hz,
T (s)ª1–(-180¥F ¥T)∞. (3.13)
SH
At higher frequencies, the S/H also begins attenuating the input. The more exact
transfer function for S/H is
z-1Ê1ˆ
T (z)= , (3.14)
SH Tz Ës¯
which is digital differentiation in series with analog integration. This form is shown
as a zero-order hold in [7, p. 754], although the T is not included. Few textbooks
include the T, although it is required to reflect the sample-and-hold’s intrinsic unity
DC gain.Recognizing that z=esT,some algebra can provide Equation 3.14 in a simpler
form for sinusoidal excitation:
z-1Ê1ˆ
T (z)=
SH Tz Ës¯
esT-1Ê 1 ˆ
=
esT ËTs¯
esT2 -e-sT2 Ê 1 ˆ
= .
esT2 ËTs¯

| 58 (cid:2) | CHAPTER 3 REVIEW | OF THE FREQUENCY | DOMAIN |     |     |
| ---------- | ---------------- | ---------------- | ------ | --- | --- |
To apply steady-state sinusoids,set s=jw,
|     |     |     | ejwT 2 -e-jwT | 2   |     |
| --- | --- | --- | ------------- | --- | --- |
Ê 1 ˆ
|     |     | T   | (z)= |         |     |
| --- | --- | --- | ---- | ------- | --- |
|     |     | SH  | ejwT | 2 ËTjw¯ |     |
ejwT 2 -e-jwT 2 1
=e-jwT 2 ¥ ¥
2j wT 2
sin(wT 2)
=e-jwT 2
¥
wT 2
|     |     |     | Êsin(wT | 2)ˆ          |        |
| --- | --- | --- | ------- | ------------ | ------ |
|     |     |     | =       | –(-wT 2)rad. | (3.15) |
|     |     |     | Ë wT 2  | ¯            |        |
So, the  precise  sample-and-hold  (Equation  3.15)  and  the  approximation
(Equation 3.12) have the identical phase lag, but different gains. The gain term,
sin(wT/2)/(wT/2), also known as the sync function, is nearly unity for most frequen-
cies of interest.For example,at one fourth the sample frequency (w=2p/4T),the sync
function evaluates to 0.9dB, which is a value so close to 0dB that it can usually be
ignored. And recognizing that usually the system bandwidth will be at much lower
frequencies, say  one  tenth  the  sample  frequency, there  is  rarely  much  interest
in the precise gain at so high a frequency. This is why the simpler Equation 3.12 is
accurate enough to use in most control systems problems.
|     | 3.2.7 Quantization |     |     |     |     |
| --- | ------------------ | --- | --- | --- | --- |
Quantization is a nonlinear effect of digital control systems. It can come from
resolution limitations of transducers or of internal calculations. One example is a
12-bit analog-to-digital converter (ADC) that converts a continuous range of 10V
to 4096 different values.Quantization also occurs in integer multiplications since the
|     | resultant of | a multiplication is usually rounded. |     |     |     |
| --- | ------------ | ------------------------------------ | --- | --- | --- |
If the resolution of sensors and the control-system mathematics is fine enough,
quantization can be ignored. Otherwise it must be taken into account either in
modeling or by use of statistical methods. Quantization is nonlinear and cannot be
represented in the z-domain.One effect of quantization is called limit cycles [2,p.367;
16].Limit cycles are low-level oscillations that occur because of quantization error in
digital mathematics. Limit cycles can produce sustained oscillations that are low in
frequency and many times larger than the quantization level.
An ADC converts a voltage to an integer, where the value of the integer is
proportional to the amount of voltage.Similarly,digital-to-analog converters (DACs)
convert integers to voltages.A sample-and-hold is an implicit part of the output DAC.
That is, a DAC can be modeled with two sections: a constant in volts per bit and a
S/H.In general,the model for DACs and ADCs is the ratio of the integer range and
the voltage range.When studying the effects of phase lag on stability,the sample-and-
hold usually can be placed anywhere in the loop.

3.3 THE OPEN-LOOP METHOD (cid:3) 59
3.3 The Open-Loop Method
The open-loop method is a technique that analyzes margins of stability. It simplifies
the complex task of evaluating the stability of a control system to calculations based
on the phase and gain at two key frequencies. Many competing methods of stability
analysis, such as the popular root locus method, rely on subjective measures of
stability margins such as evaluating graphical patterns within complex plots. Such
methods are often impractical in realistic systems because the graphs grow increas-
ingly difficult to interpret as system models are augmented to take into account more
detailed behavior of the system. The open-loop method allows any known LTI
behavior to be accounted for, and it does so without significantly increasing the
difficulty of executing the method.
The open-loop method simplifies any control loop to the diagram shown in
Figure 3-11.All components in the forward path,including the control law,the power
converter,and the plant,are combined to form G(s).H(s)includes all components in
the feedback path.
The closed-loop transfer function is the relationship between the command, R(s),
and plant output, C(s), which is equivalent to G/(1+GH). (For convenience, the
closed-loop function is often taken substituting F(s) for C(s) because C(s) cannot be
measured directly in physical systems.) The open-loop transfer function is defined
as the loop gain, which is the path from E(s) to F(s). This is equivalent to GH.
Figure 3-12 shows a closed-loop (G/(1+GH)) and Figure 3-13 shows the open-loop
(GH) transfer function for the model of Experiment 3A with default parameters.
The open-loop method provides two margins of stability, gain margin and phase
margin. Both are based on the understanding that instability occurs when the open-
loop gain is unity (0dB) and the phase is -180°.This can be seen with the G/(1+GH)
rule which reduces to G/0 when GH=0dB –-180°since 0dB –-180°is equivalent to
-1. The open-loop method measures by how much of a margin the control system
avoids instability.
The Visual ModelQ DSA in Experiment 3A is configured to make convenient
the display of both the open-loop and the closed-loop plots. The closed loop is the
relationship between the command and feedback signals.Accordingly,the input and
G(s)includes all blocks
in the forward path
E(s)
R(s) G(s) C(s)
+ _
F(s)
H(s)
H(s)includes all blocks
in the feedback path
Figure 3-11. The open-loop method simplifies the control loop to two transfer functions.

60 (cid:2) CHAPTER 3 REVIEW OF THE FREQUENCY DOMAIN
Gain starts at 0dB, then falls.
Note that when
Phase starts at 0o, then falls. phase is -270°,
it shows as +90
because it is
offset by +360 °
Figure 3-12. Characteristics of closed-loop Bode plot on a stable system.
Gain starts high,
then falls.
Phase starts at -180o,
rises and then falls
Figure 3-13. Characteristics of an open-loop Bode plot corresponding to Figure 3-12.

3.3 THE OPEN-LOOP METHOD (cid:3) 61
output channels of the DSA are selected as Command and Feedback in the upper
left of Figure 3-12. The open loop describes the path around the loop. Referring to
Figure 3-6, this path starts at the variable block Error, which is just right of the
summing junction,and follows the loop back around to the Feedbackvariable block.
Thus,the DSA in Figure 3-13 shows the input channel for the open-loop plot as Error.
The DSA in Experiment 3A is configured to have two buttons, Closed and Open,
which select the appropriate input and output channels for the two plots. The DSA
buttons are configured with the button setup node at the top right of the DSA block.
Phase margin or PM [4, 36] is the margin of stability measured at the frequency
where the gain around the loop falls to 0dB.As shown in Figure 3-13,control systems
usually have a large open-loop gain (>>0dB) at low frequencies and a small loop gain
(<<0dB) at high frequencies. For at least one frequency, the gain will pass through
0dB; that frequency is called the gain-crossover frequency. Were the phase equal to
-180°at that frequency,the system would be unstable.The further the phase is from
-180°, the greater the margin of stability. The PM is defined as the difference of the
actual phase and -180°. Figure 3-14 shows the open-loop plot of Figure 3-13 with
the gain-crossover frequency and PM identified as 81Hz and 52°, respectively.
Gain margin or GM is the margin of stability measured at the frequency where the
phase around the loop falls to -180°. As shown in Figure 3-14, the loop phase will
GM=10 dB
0 dB
Gain crossover
frequency
(81 Hz)
PM
=52o
-180 ∞
Phase crossover
(240 Hz)
Figure 3-14. Open-loop Bode plot showing how to calculate phase and gain margins.

62 (cid:2) CHAPTER 3 REVIEW OF THE FREQUENCY DOMAIN
usually be greater than -180° at the gain-crossover frequency and start falling at
higher frequencies.At one frequency,the gain will pass through -180°;that frequency
is called the phase-crossover frequency.Were the gain equal to 0dB at that frequency,
the system would be unstable.The further the gain is from 0dB,the greater the margin
of stability. The GM is defined as the negative of the actual gain at the phase
crossover. The system in Figure 3-14 identifies the GM as 10dB and the phase-
crossover frequency as 240Hz.
3.3.1 Specifying the Target GM and PM
Although the measurement of PM and GM is objective, determining the desired
values for these measures requires judgment. One reason is that applications vary
in the amount of margin they require. For example, some applications must follow
commands like the step that will generate overshoot in all but the most stable systems.
These applications often require higher margins of stability than those systems
that respond only to gentler commands. Also, some applications can tolerate more
overshoot than others. Finally, some control laws require more PM or GM than
others for equivalent response. For example, a PI controller requires typically
about 55° of PM to achieve 20% overshoot to a step, while a PID (proportional-
integral-differential) controller might be able to eliminate all overshoot with just
40°PM.
In practice,the GM of a well-tuned system will fall between 6 and 20dB,depend-
ing on the application and the controller type;PM will fall between 35°and 80°.All
things being equal, more PM is better. This teaches one of the most basic rules in
controls: Eliminate unnecessary phase lag! Every noise filter, feedback device, and
power converter contributes to phase lag around the loop and each erodes the PM.
Unnecessary lags limit the ultimate performance of the control system.
3.4 AZone-Based Tuning Procedure
One challenge of tuning is that multiple gains must be varied and each affects many
of the performance measures. The goal of the zone-based tuning process is to tune
the multiple tuning gains one at a time. This can be done by considering the effects
of each gain term as being dominant over a certain zone of frequency [25,26].A PI
controller has two zones,one for the proportional term and the other for the integral
term.Consider the PI control loop in Figure 3-15.
The frequency zones are easiest to see when the effects of the power converter and
feedback filter are ignored.So,setting those two blocks to 1 and using the G/(1+GH)
rule with some algebra,the simplified closed-loop transfer function is
C(s) sK +K K
= P I P . (3.16)
R(s) s2 G+sK +K K
P I P

3.4 A ZONE-BASED TUNING PROCEDURE (cid:3) 63
E(s)
+
R(s)
+ Power G
K C(s)
K /s P converter s
- I +
PI control law
Feedback
filter
Figure 3-15. Asimplified PI controller.
To consider (3.16) in terms of frequency zones,focus on the denominator.At high
frequencies s is large and s2/G dominates the denominator. This is intuitive; at very
high frequencies, almost all control systems respond according to the plant gain
(inductance, capacitance, inertia, etc.); at those frequencies, the response is beyond
the reach of the controller.
As the frequency declines,the s¥K term will become dominant.This is the middle-
P
frequencyrange.In the control law,the proportional gain dominates;the frequency is
still too high for the integral gain to have much effect. As the frequency declines
further, the integral term will dominate because a low value of the s terms will leave
only the constant KK term in the numerator and denominator of Equation 3.16.
I P
This is the low-frequency zone.
Understanding the concept of frequency zones, a tuning procedure can be
developed where one gain is tuned at a time.This eliminates the problems associated
with tuning multiple gains simultaneously.The method that follows assumes the user
has only time-domain measurements, as this is common in industry. The frequency-
domain plots are shown for reference.
3.4.1 Zone One: Proportional
To apply the zone-based approach to tuning, tune the highest frequency term
first. Assuming the plant gain, G, cannot be changed, start by tuning K . If the
P
application can tolerate it, set K to zero and set K very low. Note that some
I P
applications cannot tolerate the lack of an integral such as in motion control, when
a velocity loop is applied to a vertical load (the load can fall). Apply a square
wave and raise K until significant overshoot is generated. How much overshoot is
P
significant depends on the application. Many applications can tolerate 10 or 15%,
while others can tolerate none at all. For applications that demand high responsive-
ness,it is important to raise K as high as possible.In Figure 3-16,a very small amount
P
of overshoot is assumed to be tolerable and the result is K =1.
P
By looking at the open-loop gain,the advantage of setting K to 0 when tuning K
I P
is apparent.Notice that at low frequencies the open-loop phase is -90°compared to

64 (cid:2) CHAPTER 3 REVIEW OF THE FREQUENCY DOMAIN
Command
Gain crossover
at 80 Hz
Phase ~ -900
Feedback PM=630
(a) (b)
Figure 3-16. From Experiment 3A: Tuning Zone 1 using (a) step response and (b) open-loop plot of
P-controller for K =1, K =0.
P I
the -180°seen in the PI controller of Figure 3-14.So,when K =0,no matter how low
I
K is set, the system will not become unstable. In the PI controller of Figure 3-14,
P
when the gain crossover frequency is well above or well below the phase “hump”
(about 50Hz), the PM falls so that the system is not sufficiently stable. One
advantage of starting with a P controller is that the designer can start with K very
P
low and have little risk of instability.
A natural question is what causes instability seen with high K ? As always, insta-
P
bility is caused by phase lag accumulating to -180° with 0dB gain. Phase from the
plant here is fixed at -90°,but phase lag from the power converter and feedback filter
increases as frequency rises; this accounts for decline in open-loop phase after the
gain-crossover frequency shown in Figure 3-16b.K is raised to provide the maximum
P
responsiveness possible within a minimum margin of stability. If the maximized K
P
is insufficient, the designer must look toward reducing phase lag in the components
of the loop, for example, by increasing the responsiveness of the power converter or
the feedback device.
3.4.2 Zone Two: Integral
After K is maximized, attention should be turned to the next zone, which is
P
served by the integral term. Integral gain is important because it removes the long-
term error. When tuning, the value of integral gain will have little bearing on the
stability of the next higher frequency (K ) zone; the implication is that changing K
P I
will not require returning to change K . Continuing from above, raise K from zero
P I

3.4 A ZONE-BASED TUNING PROCEDURE (cid:3) 65
Gain
Command crossover
still 80 Hz
Feedback
Phase ~ -180o PM=52o
(a) (b)
Figure 3-17. (a) Step response and (b) open-loop plot of PI controller with K =100, K =1.
I P
until overshoot is excessive—usually between 10 and 30%.For example,the overshoot
is about 10% when K =100 in Figure 3-17a; the open-loop Bode plot is shown in
I
Figure 3-17b.
Notice in Figure 3-17b that the gain crossover remained at 80Hz, but the PM
dropped 10°. Both are expected; the integral did not change the crossover frequency
because its frequency zone is well below 80Hz. So, K has little effect on gain at the
I
gain-crossover frequency, but it still contributes 10° of phase lag at that frequency,
reducing the PM by that same amount. Notice that the PI controller has overshoot.
All PI controllers generate some overshoot in response to a square wave; it is one of
the weaknesses of the method.
The zone-based procedure shown here can be extended to more complicated con-
trollers. For example, if a double integral is added to the control law, it becomes a
third zone, which becomes the lowest frequency zone and is tuned after the first two
zones are tuned. The key is to divide the control laws into multiple zones and then
tune the terms, starting with the highest zone and moving to the lowest.
One exception to this rule is when a PID controller is used to regulate a single-
integrating plant. In this case, the proportional and derivative terms form a single
zone. When tuning such a controller, zero the integral and derivative gains and tune
the proportional term for lower-than-normal margins of stability, allowing perhaps
10 or 20% more overshoot than will be acceptable in the final tuning. Then add a
small amount of derivative gain to increase the stability margins. In this way, the
derivative and proportional gains combine to form the highest frequency zone. The
integral zone, which is the next lower zone, is tuned the same way as it would be in
the PI controller.

| 66 (cid:2) | CHAPTER 3 REVIEW | OF THE FREQUENCY | DOMAIN |
| ---------- | ---------------- | ---------------- | ------ |
|            | 3.5 Exercises    |                  |        |
1. Confirm that the zone-based method provides consistent margins of stability.
|     | Open Experiment_3A.mqd |     | and click the Runbutton. |
| --- | ---------------------- | --- | ------------------------ |
A. Set the feedback filter frequency (FGfb) to 200 and retune the system using
the zone-based procedure of this chapter;do not allow any overshoot with
K and allow only 10% overshoot with K.Measure PM and GM.
P I
|     | B. Repeat for FGfb=350.  |     |     |
| --- | ------------------------ | --- | --- |
|     | C. Repeat for FGfb=500.  |     |     |
|     | D. Repeat for FGfb=1000. |     |     |
E. Relate the time-domain data of parts A–D to GM and PM for the system
of Experiment_3A.mqd.
F. How could you modify the procedure to generate somewhat lower margins
of stability?
2. Closed-loop bandwidth.
A. Measure the closed-loop bandwidth (-3dB frequency) for each of the cases
in 1A–1D.
B. What is the relationship between low-pass filters in the loop and maximum
command response?
3. Create a zone-based tuning procedure that produces tuning gains in Experi-
|     | ment 3A so margins of    |     | stability are GM=10dB and PM=50°. |
| --- | ------------------------ | --- | --------------------------------- |
|     | A. What tuning values (K |     | ,K) are produced for FGfb=200?    |
P I
|     | B. Repeat for FGfb=350.  |     |     |
| --- | ------------------------ | --- | --- |
|     | C. Repeat for FGfb=500.  |     |     |
|     | D. Repeat for FGfb=1000. |     |     |
4. Closed-loop bandwidth.
A. Measure the closed-loop bandwidth (-3dB frequency) for each of the cases
in 3A–3D.
B. Compare bandwidths in 4A to those in 2A. What is the relationship
between more aggressive tuning (lower PM and GM) and maximum
command response?

Chapter 4
The Luenberger Observer:
Correcting Sensor
Problems
In this chapter...
• Development of the Luenberger observer
• Experiments demonstrating how observers enhance stability
• Practical aspects of designing and tuning observers
This chapter will introduce the Luenberger observer. It will focus on the predictor–
corrector structure where the observer uses a model to predict system operation and
then uses the feedback signal to correct deviations between the model and the actual
system. Also, a filter form of the observer will be discussed; this representation
provides additional insight into the operation of observers.This chapter will conclude
with a step-by-step procedure for designing a Luenberger observer.
4.1 What Is a Luenberger Observer?
An observer is a mathematical structure that combines sensor output and plant
excitation signals with models of the plant and sensor.An observer provides feedback
signals that are superior to the sensor output alone. The topic of this book is the
Luenberger observer,which combines five elements:
• a sensor output, Y(s),
• a power converter output (plant excitation), P (s),
C
• a model (estimation) of the plant,G (s),
PEst
67

68 (cid:2) CHAPTER 4 THE LUENBERGER OBSERVER:CORRECTING SENSORPROBLEMS
Y(s) Actual
C(s)
sensor
| P (s) |     | G (s) |        | G (s)  |        |
| ----- | --- | ----- | ------ | ------ | ------ |
| C     |     | P     | Actual | S      | output |
| Plant |     |       | state  |        |        |
|       |     | Plant |        | Sensor |        |
excitation
Physical system
E (s)
|     |     |     |       | O         | +   |
| --- | --- | --- | ----- | --------- | --- |
|     |     |     | G (s) |           |     |
|     |     |     | CO    | Observer  | _   |
error
Observer
compensator
|     | +   |       | C (s)    |       |          |
| --- | --- | ----- | -------- | ----- | -------- |
|     |     | G (s) | O        | G (s) | Observed |
|     |     | PEst  |          | SEst  |          |
|     | +   |       | Observed |       | sensor   |
Y (s)
|     |     |       | state |        | O      |
| --- | --- | ----- | ----- | ------ | ------ |
|     |     | Plant |       | Sensor | output |
Modeled system
|              | Figure4-1.  | General form of the Luenberger observer. |     |     |     |
| ------------ | ----------- | ---------------------------------------- | --- | --- | --- |
| • a model of | the sensor, | G (s),                                   | and |     |     |
SEst
•
| a PI or PID observer compensator, |     |     | G (s). |     |     |
| --------------------------------- | --- | --- | ------ | --- | --- |
CO
The general form of the Luenberger observer is shown in Figure 4-1.
4.1.1 Observer Terminology
The following naming conventions will be used. Estimated will describe components
of the system model.For example,the estimated plant is a model of the plant that is
run by the observer.Observedwill apply to signals derived from an observer;thus,the
state (C O ) and the sensor (Y O ) signals are observedin Figure 4-1.Observer models and
their parameters will be referred to as estimated.Transfer functions will normally be
named G(s) with identifying subscripts:G (s)is the plant transfer function and G (s)
P PEst
is the estimated or modeled plant.
4.1.2 Building the Luenberger Observer
This section describes the construction of a Luenberger observer from a traditional
control system, adding components step by step. Start with the traditional control
system shown in Figure 4-2.Ideally,the control loop would use the actual state,C(s),
as feedback. However, access to the state comes through the sensor, which produces

|      |      |       |     |       | 4.1 | WHAT | IS A LUENBERGER | OBSERVER? | (cid:3) 69 |
| ---- | ---- | ----- | --- | ----- | --- | ---- | --------------- | --------- | ---------- |
| R(s) | E(s) | P (s) |     | P (s) |     | C(s) |                 | Y(s)      |            |
|      |      | R     |     | C     |     |      |                 |           |            |
+
|     | G       | (s) | G          | (s)                         | G (s) |     | G (s)  |     |     |
| --- | ------- | --- | ---------- | --------------------------- | ----- | --- | ------ | --- | --- |
|     | _ C     |     | PC         |                             | P     |     | S      |     |     |
|     | Control |     | Power      |                             | Plant |     | Sensor |     |     |
|     | law     |     | converter  |                             |       |     |        |     |     |
|     |         |     | Figure4-2. | Traditional control system. |       |     |        |     |     |
Y(s), the feedback variable. The sensor transfer function, G (s), often ignored in the
S
presentation of control systems,is the focus here.Typical problems caused by sensors
| are phase lag, | attenuation, | and noise. |     |     |     |     |     |     |     |
| -------------- | ------------ | ---------- | --- | --- | --- | --- | --- | --- | --- |
Phase lag and attenuation can be caused by the physical construction of the sensor
or by sensor filters,which are often introduced to attenuate noise.The key detriment
of phase lag is the reduction of loop stability. Noise can be generated by several
forms of electromagnetic interference (EMI). Noise causes random behavior in the
control system, corrupting the output and wasting power. All of these undesirable
characteristics are represented by the term G (s) in Figure 4-2. The ideal sensor can
S
| be defined as G |     | (s)=1. |     |     |     |     |     |     |     |
| --------------- | --- | ------ | --- | --- | --- | --- | --- | --- | --- |
S-IDEAL
The first step in dealing with sensor problems is to select the best sensor for the
application.Compared to using an observer,selecting a faster or more accurate sensor
will provide benefits that are more predictable and more easily realized. However,
limitations such as cost, size, and reliability will usually force the designer to accept
sensors with undesirable characteristics, no matter how careful the selection process.
The assumption from here forward will be that the sensor in use is appropriate for
a given machine or process; the goal of the observer is to make the best use of
that sensor.In other words,the first goal of the Luenberger observer will be to min-
| imize the effects of |     | G (s)π1. |     |     |     |     |     |     |     |
| -------------------- | --- | -------- | --- | --- | --- | --- | --- | --- | --- |
S
For the purposes of this development, only the plant and sensor, as shown in
Figure 4-3, need to be considered. Note that the traditional control system ignores
the effect of G (s)π1; Y(s), the sensor output, is used in place of the actual state
S
under control, C(s). But Y(s) is not C(s); the temperature of a component is not the
temperature indicated by the sensor. Phase lag from sensors often is a primary
contributor to loop instability; noise from sensors often demands correction by the
addition of filters in the control loop, again contributing phase lag and ultimately
| reducing margins of |     | stability. |     |      |     |      |     |     |     |
| ------------------- | --- | ---------- | --- | ---- | --- | ---- | --- | --- | --- |
|                     |     | P (s)      |     | C(s) |     | Y(s) |     |     |     |
C
|     |     |     | G (s)      |                   | G (s) |     |     |     |     |
| --- | --- | --- | ---------- | ----------------- | ----- | --- | --- | --- | --- |
|     |     |     | P          |                   | S     |     |     |     |     |
|     |     |     | Figure4-3. | Plant and sensor. |       |     |     |     |     |

70 (cid:2) CHAPTER 4 THE LUENBERGER OBSERVER:CORRECTING SENSORPROBLEMS
| P (s) |       | C(s) |       | Y(s) |      | C (s) |
| ----- | ----- | ---- | ----- | ---- | ---- | ----- |
| C     |       |      |       |      | G-1  | Est   |
|       | G (s) |      | G (s) |      |      | (s)   |
|       | P     |      | S     |      | SEst |       |
Figure4-4. An impractical way to estimate C(s): Adding the inverse sensor transfer function.
| 4.1.2.1 Two Ways to Avoid G |     |     | (s)π1 |     |     |     |
| --------------------------- | --- | --- | ----- | --- | --- | --- |
S
So,how can the effects of G S (s) π1 be removed? One alternative is to follow the sensed
signal with the inverse of the sensor transfer function: G-1 (s). This is shown in
SEst
Figure 4-4. On paper, such a solution appears workable. Unfortunately, the nature
of G (s) makes taking its inverse impractical. For example, if G (s) were a low-pass
S S
filter, as is common, its inverse would require a derivative as shown in Equation 4.1.
Derivatives are well known for being too noisy to be practical in most cases; high-
frequency noise, such as that from quantization and EMI, processed by a derivative
generates excessive high-frequency output noise.
|     |          | K   |         |        |     | s     |
| --- | -------- | --- | ------- | ------ | --- | ----- |
|     |          | EST | thenG-1 |        |     | (4.1) |
|     | IfG (s)= |     | ,       | (s)=1+ |     | .     |
|     | SEst     | s+K |         | SEst   | K   |       |
|     |          |     | EST     |        |     | EST   |
Another alternative to avoid the effects of G S (s)π1 is to simulate a model of the
plant in software as the control loop is being executed. The signal from the power
converter output is applied to a plant model,G (s),in parallel with the actual plant.
PEst
This is shown in Figure 4-5.Such a solution is subject to drift because most control-
system plants contain at least one integrator; even small differences between the
physical plant and the model plant will cause the estimated state,C Est (s),to drift.As
a result,this solution is also impractical.
The solution of Figure 4-4, which depends wholly on the sensor, works well at
low  frequency  but  produces  excessive  noise  at  high  frequency. The  solution  of
Figure 4-5,which depends wholly on the model and the power converter output signal,
works well at high frequency but drifts in the lower frequencies. The Luenberger
observer, as will be shown in the next section, can be viewed as combining the best
parts of these two solutions.
|     |     |     |       | C(s) |       | Y(s) |
| --- | --- | --- | ----- | ---- | ----- | ---- |
| P   | (s) |     | G (s) |      | G (s) |      |
|     | C   |     | P     |      | S     |      |
C (s)
Est
G (s)
PEst
Figure4-5. Another impractical solution: Deriving the controlled state from a model of the plant.

4.1 WHAT IS A LUENBERGER OBSERVER? (cid:3) 71
4.1.2.2 Simulating the Plant and Sensor in Real Time
Continuing the construction of the Luenberger observer, augment the structure of
Figure 4-5 to run a model of the plant and sensor in parallel with the physical plant
and sensor. This configuration, shown in Figure 4-6, drives a signal representing the
power conversion output through the plant model and through the sensor model to
generate the observed sensor output,Y (s).Assume for the moment that the models
O
are exact replicas of the physical components. In this case, Y (s)=Y(s), or, equiva-
O
lently,E (s)=0.In such a case,the observed state,C (s),is an accurate representation
O O
of the actual state.So C (s) could be used to close the control loop;the phase lag of
O
G (s) would have no effect on the system.This achieves the first goal of observers,the
S
elimination of the effects of G (s) π1,but only for the unrealistic case where the model
S
is a perfect representation of the actual plant.
4.1.2.3 Adding the Observer Compensator
In any realistic system E (s) will not be zero because the models will not be perfect
O
representations of their physical counterparts and because of disturbances.The final
step in building the Luenberger observer is to route the error signal back to the model
to drive the error toward zero. This is shown in Figure 4-7. The observer compen-
sator, G (s), is usually a high-gain PI or PID control law.
CO
The gains of G (s) are often set as high as possible so that even small errors drive
CO
through the observer compensator to minimize the difference between Y(s) and Y (s).
O
If this error is small, the observed state, C (s), becomes a reasonable representation
O
of the actual state, C(s); certainly, it can be much more accurate than the sensor
output,Y(s).
One application of the Luenberger observer is to use the observed state to close
the control loop;this is shown in Figure 4-8,which compares to the traditional control
system of Figure 4-2. The sensor output is no longer used to close the loop; its sole
function is to drive the observer to form an observed state. Typically, most of the
C(s) Y(s)
P (s) G (s) G (s)
C P S
+
E (s)
O
_
G (s) G (s)
PEst SEst
C (s) Y (s)
O O
Figure4-6. Running models in parallel with the actual components.

72 (cid:2) CHAPTER 4 THE LUENBERGER OBSERVER:CORRECTING SENSORPROBLEMS
|     |     |     |     |     | C(s) |       | Y(s) |     |     |
| --- | --- | --- | --- | --- | ---- | ----- | ---- | --- | --- |
|     |     | P   | (s) | G   | (s)  | G (s) |      |     |     |
|     |     | C   |     | P   |      | S     |      |     |     |
E (s)
|     |     |     | +   |     |     |     |     | +   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
O
G (s)
|     |     |     |     |     | CO  |     |     | _   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
+
|     |     |     |     | G          | (s)                      | G    | (s) |     |     |
| --- | --- | --- | --- | ---------- | ------------------------ | ---- | --- | --- | --- |
|     |     |     |     | PEst       |                          | SEst |     |     |     |
|     |     |     |     |            | C (s)                    |      | Y   | (s) |     |
|     |     |     |     |            | O                        |      |     | O   |     |
|     |     |     |     | Figure4-7. | The Luenberger observer. |      |     |     |     |
phase lag and attenuation of the sensor can be removed, at least in the frequency
range of interest for the control loop.
4.2 Experiments 4A–4C: Enhancing Stability with an Observer
Experiments 4A–4C are VisualModelQmodels that demonstrate one of the primary
benefits of Luenberger observers:the elimination of phase lag from the control loop
and the resulting increase in margins of stability. Experiment 4A represents the
traditional system.Experiment 4B restructures the loop so the actual state is used as
the feedback variable.Of course,this is not practical in a working system (the actual
state is not accessible) and is only used here to demonstrate the negative effects of the
sensor.Experiment 4C adds a Luenberger observer to the control system.The result
will be that the system performance will be equal to that of Experiment 4B where the
| R(s) | E(s) |     | P (s) |     | P (s) |     | C(s) |     | Y(s) |
| ---- | ---- | --- | ----- | --- | ----- | --- | ---- | --- | ---- |
|      |      |     | R     |     | C     |     |      |     |      |
+
|     |     | G (s) |     | G (s) |     | G (s) |     | G (s) |     |
| --- | --- | ----- | --- | ----- | --- | ----- | --- | ----- | --- |
|     | _   | C     |     | PC    |     | P     |     | S     |     |
|     |     |       |     |       |     |       |     | E (s) |     |
+
O
|     |     |     |     |     |     |     | G (s) |     |     |
| --- | --- | --- | --- | --- | --- | --- | ----- | --- | --- |
|     |     |     |     |     |     |     | CO    |     | _   |
+
|     |     |     |     |     |     |     | C (s) |     |     |
| --- | --- | --- | --- | --- | --- | --- | ----- | --- | --- |
O
|     |     |     |     |     |     | G (s) |     | G (s) |       |
| --- | --- | --- | --- | --- | --- | ----- | --- | ----- | ----- |
|     |     |     |     |     |     | PEst  |     | SEst  |       |
|     |     |     |     |     | +   |       |     |       | Y (s) |
O
|     |     |     | Figure4-8. | ALuenberger observer-based control loop. |     |     |     |     |     |
| --- | --- | --- | ---------- | ---------------------------------------- | --- | --- | --- | --- | --- |

|     |            | 4.2 EXPERIMENTS                             | 4A–4C:ENHANCINGSTABILITY | WITH ANOBSERVER | (cid:3) 73 |
| --- | ---------- | ------------------------------------------- | ------------------------ | --------------- | ---------- |
|     | Figure4-9. | Experiment 4A: Atraditional control system. |                          |                 |            |
actual state was used. In other words, the effects of the imperfect sensor will be
eliminated by the observer.
The model of Experiment 4A is shown in Figure 4-9.The loop includes a PI com-
pensator,a 50-Hz bandwidth power converter,and a 20-Hz bandwidth sensor.The PI
compensator is tuned aggressively so that the margins of stability are too low. The
sensor is the primary contributor to phase lag in the control loop and thus the primary
cause of low margins of stability.Starting from the left,there are ten components in
this model:
Command A waveform generator used to excite the system with a 2-Hz square
|     | wave at an amplitude of | ±1. |     |     |     |
| --- | ----------------------- | --- | --- | --- | --- |
R A variable block for R,the command.R is not used in this discussion;
it and several other variables are provided for readers who wish to
explore the model independently.To view these variables,run the model
and double-click on the main scope block to see the main scope display,
which will display all variables.
| Subtraction | A subtraction block to form the error, |     | R-Y. |     |     |
| ----------- | -------------------------------------- | --- | ---- | --- | --- |
G A digital PI control law operating on the error signal.The PI gains are
C
set high enough to cause overshoot and ringing:K I =30.0 and K P =1.5.
G The power converter modeled by a two-pole low-pass filter with a
PC
|     | bandwidth of | 50Hz and a zof | 0.707. |     |     |
| --- | ------------ | -------------- | ------ | --- | --- |
K A scaling gain representing part of the plant transfer function.The gain
here is 50.
G P An integrator that, together with K,represents the plant.
G A single-pole low-pass filter representing the sensor. The bandwidth
S
of the filter is 20Hz. This bandwidth is so low that the sensor is the
|     | predominant source of                     | phase lag in the control loop. |     |     |     |
| --- | ----------------------------------------- | ------------------------------ | --- | --- | --- |
| Y   | A variable block for Y,the system output. |                                |     |     |     |
| C   | A LiveScopefor C,the actual state.        |                                |     |     |     |
The model includes a Live Scope display of C, the actual state. This signal is the
system response to R, the square-wave command. The signal C shows considerable

74 (cid:2) CHAPTER 4 THE LUENBERGER OBSERVER:CORRECTING SENSORPROBLEMS
Figure4-10. From Experiment 4B: An idealized system, which uses the actual state for feedback,
has conservative margins of stability.
overshoot and ringing, which indicates marginal stability. The gains of G , the PI
C
controller (K =1.5 and K =30), are set too aggressively for the phase lag of this
P I
loop.
The marginal stability of Figure 4-9 is caused in large part by the phase lag created
by G .Were G an ideal sensor (G =1.0),the system would behave well with the gains
S S S
used in that model. This is demonstrated in Experiment 4B (see Figure 4-10), which
is identical in all respects to Figure 4-9 except that the loop feedback is the actual
state (C),not the measured output (Y).Of course,this structure is impractical;loops
must be closed on measured signals.In traditional control systems,the use of sensors
with significant phase lag1usually requires reducing control-law gains,which implies
a reduction in system performance. In other words, the most common solution
for the problems of Figure 4-9 is to reduce the PI gains and accept the lower level of
performance.An observer can offer a better alternative.
Experiment 4C (see Figure 4-11) is Experiment 4A with an observer added.Several
new blocks are used to construct the observer of Figure 4-7:
Subtraction A subtraction block is added on the right to take the difference of Y,
the actual feedback signal, and Y, the observed feedback signal. This
o
forms the observer error signal.
G A PID control law is used as the observer compensator.G was tuned
CO CO
experimentally using a process that will be described later in this
chapter. G samples at 1kHz, as do the other digital blocks (Delay,
CO
G ,and G ).
PEst SEst
Addition An addition block is added to combine the output of the observer
compensator and the power converter output.
K An estimate of the gain portion of the plant. Here, the gain is set to
Est
50,the gain of the actual plant (K =K).
Est
1Significant in comparison to the other sources of phase lag in the loop such as internal filters and the
power converter.

4.2 EXPERIMENTS 4A–4C:ENHANCINGSTABILITY WITH ANOBSERVER (cid:3) 75
Figure4-11. Model of observer-based control system, from Experiment 4C.
G A digital integrator, which is a summation scaled by 1/T. It is used to
PEst
estimate the second part of the plant,G .
P
G A digital filter used to model the sensor transfer function. This is
SEst
a single-pole, low-pass filter with a bandwidth of 20Hz. This is an
accurate representation of the sensor.
C Variable block C ,the observed state.
O O
Delay A delay of one sample time. This delay recognizes that there must be
a sample–hold delay at some position in the digital-observer loop. In
this case, it is assumed that during each cycle of the observer, Y is
O
calculated to be used in the succeeding cycle.
The other significant change in Experiment 4C is that the feedback for the control
loop is taken from the observed state, not the sensor output, as was the case in
Experiment 4A. The results of these changes are dramatic. The actual state shown
in Figure 4-11 shows none of the signs of marginal stability that were evident in
Figure 4-9.This improvement is wholly due to reduction of phase lag from the sensor.
In fact,the response is so good,it is indistinguishable from the response of the system
closed using the actual state as shown in Figure 4-10 (the desirable,albeit impractical,
alternative).
Here,the Luenberger observer provided a practical way to eliminate the effects of
sensor phase lag in the loop. Further, these benefits could be realized with a modest
amount of computational resources:a handful of simple functions running at 1kHz.
Altogether, these calculations represent a few microseconds of computation on a
modern DSP and not much more on a traditional microprocessor. In many cases,
the calculations are fast enough that they can be run on existing hardware using
uncommitted computational resources.

76 (cid:2) CHAPTER 4 THE LUENBERGER OBSERVER:CORRECTING SENSORPROBLEMS
4.2.1 Experiment 4D: Elimination of Phase Lag
A brief investigation can verify the elimination of phase lag demonstrated with
Experiments 4A–4C. Experiment 4D (see Figure 4-12) displays three signals on Live
Scopes:C,the actual state,Y,the measured state,and C ,the observed state.At first
O
glance, all three signals appear similar. However, upon closer inspection, notice that
Y (rightmost) lags C (top) by about a division. For example, C crosses two vertical
divisions at two time divisions after the trigger time, which is indicated by a small
triangle; Y requires three time divisions to cross the same level, about 10ms longer.
Note that the time scale has been reduced to 0.01s in Experiment 4D to show this
detail. Note also that all three Live Scopes are triggered from R, the command, and
so are synchronized.
Now compare the observed state,C ,to the actual state.These signals are virtually
O
identical. For example, C crosses through two vertical divisions at the second time
O
division,just like the actual state.The phase lag from the sensor has been eliminated
by the observer. This explains why the margins of stability were the same whether
the system used the actual state (Experiment 4B) or the observed state (Experiment 4C)
for feedback and why the margins were lower in the system using the measured state
(Experiment 4A).
It should be pointed out that this observer has several characteristics that will not
be wholly realized in a practical system:the plant and sensor models are near-perfect
The actual state takes
0.02 seconds to
cross 2 divisions.
The sensor output
takes 0.03 seconds
to cross 2 divisions.
The observed state
takes 0.02 seconds
to cross 2 divisions.
Figure4-12. Experiment 4D: Three signals in an observer-based system.

|     |     | 4.3 PREDICTOR–CORRECTORFORM |     | OFTHE LUENBERGEROBSERVER |     | (cid:3) 77 |
| --- | --- | --------------------------- | --- | ------------------------ | --- | ---------- |
representations of the actual plant and system, there are no disturbances, and the
sensor signal is noiseless. Certainly, these imperfections will limit the benefits of
observers in real-world control systems. Even so, the principle shown here is reliable
in working machines and processes:the Luenberger observer can produce substantial
benefits  in  the  presence  of sensor  phase  lag, and  it  can  do  so  with  modest
computational resources.
4.3 Predictor–Corrector Form of the Luenberger Observer
Observers are often described as being in the class of predictor–corrector methods.
The Luenberger observer of Figure 4-8 is shown in Figure 4-13 in two sections. The
model of the plant,G (s),predicts the state,C (s),from the power converter output
|     | PEst |     | O   |     |     |     |
| --- | ---- | --- | --- | --- | --- | --- |
signal, P (s). Were the model of the plant a perfect representation of the physical
C
plant and the power conversion signal a perfect representation of the power converter
output, the prediction would be perfect. Of course, this is not realistic. The model
is only an approximation to the plant. In addition, disturbances, which feed into
the plant after the power conversion signal, usually are unknown to the controller.
Disturbances are shown as D(s) in Figure 4-13;note that disturbances are present in
most control systems.(The effect of disturbances on the Luenberger observer will be
discussed in detail in Chapter 6.) All of these effects could cause the prediction of
C (s) to deviate substantially from C(s).However,the observer compensator corrects
O
most of those deviations.
The corrector section processes C (s) with the estimated sensor transfer function,
O
G (s),to derive the observed sensor output,Y (s).When the observed sensor output
| SEst |     |     | O   |     |     |     |
| ---- | --- | --- | --- | --- | --- | --- |
D(s)
|       | +   |       | C(s) |       | Y(s) |     |
| ----- | --- | ----- | ---- | ----- | ---- | --- |
| P (s) |     | G (s) |      | G (s) |      |     |
| C     |     | P     |      | S     |      |     |
+
|     |     | D (s) |     | E (s) | +   |     |
| --- | --- | ----- | --- | ----- | --- | --- |
O
|     |     | O   | G (s) |     |     |     |
| --- | --- | --- | ----- | --- | --- | --- |
CO
_
+
|     |     | G (s) |       | G (s) |       |     |
| --- | --- | ----- | ----- | ----- | ----- | --- |
|     |     | PEst  | C (s) | SEst  |       |     |
|     | +   |       | O     |       | Y (s) |     |
O
|     |     | Predictor | Corrector |     |     |     |
| --- | --- | --------- | --------- | --- | --- | --- |
Observer
Figure4-13. Predictor–corrector form of the Luenberger observer.

78 (cid:2) CHAPTER 4 THE LUENBERGER OBSERVER:CORRECTING SENSORPROBLEMS
is compared to the actual sensor output, the observer error, E O (s), is formed. This
error is fed into the observer compensator,G (s),to create the signal D (s).The gains
|     |     |     | CO  |     | O   |     |
| --- | --- | --- | --- | --- | --- | --- |
of G (s) are usually set high so that even small errors cause a substantial value of
CO
D (s).D (s) is driven through the plant and sensor models;if the observer is applied
O O
properly, the error signal will be held to near zero. Since the correction signal feeds
through the plant and the sensor models, it corrects the observed state, C O (s), as it
| corrects the observed sensor output,Y |     |     | (s). |     |     |     |
| ------------------------------------- | --- | --- | ---- | --- | --- | --- |
O
4.4 Filter Form of the Luenberger Observer
The Luenberger observer can be analyzed by representing the structure as a transfer
function. This method will be used throughout this book to investigate system
response to nonideal conditions:disturbances,noise,and model inaccuracy.The form
is not normally used for implementation because of practical limitations, which will
be discussed. However, the filter form is useful because it provides insight into the
operation of observers.
The observer transfer function has two inputs, P (s) and Y(s), and one output,
C
C (s). In this analysis, the actual model and sensor are considered a black box. This
O
is shown in Figure 4-14. The focus is on understanding the relationship between the
inputs to the observer and its output. Signals internal to the observer, such as E O (s)
and Y (s),are ignored.In fact,they will become inaccessible as the block diagram is
O
reduced to a single function.
Using Mason’s signal flow graphs to build a transfer function from Figure 4-14
produces Equation 4.2. There is a single path, P (see Figure 4-14), from Y(s) to the
1
observed state,C O (s).Also,there is one path,P 2 ,from P C (s) to the C O (s).Finally,there
D(s)
|     |     |     | C(s) |     | Y(s) |     |
| --- | --- | --- | ---- | --- | ---- | --- |
+
| P (s) |     | G (s) |     | G (s) |     |     |
| ----- | --- | ----- | --- | ----- | --- | --- |
| C     |     | P     |     | S     |     |     |
| P     | 2 + |       |     |       | P 1 |     |
P
2
Treat physical system as a “black box”
P
|     | P   |     |         | E   | (s) + 1 |     |
| --- | --- | --- | ------- | --- | ------- | --- |
|     | 2   |     | P       | P O |         |     |
|     |     |     | 1 G (s) | 1   |         |     |
CO
|     |     |     | L   | L   | _ L |     |
| --- | --- | --- | --- | --- | --- | --- |
|     |     |     | 1   | 1   | 1   |     |
|     | P   | L   |     |     |     |     |
|     | P   | 1 1 |     |     |     |     |
2
|             | +                                                        | L    | L     |      | L          |       |
| ----------- | -------------------------------------------------------- | ---- | ----- | ---- | ---------- | ----- |
|             |                                                          | 1 G  | (s) 1 | G    | (s) 1      |       |
|             | P                                                        | PEst | C (s) | SEst |            | Y (s) |
|             | 2 +                                                      | P P  | P P O |      |            | O     |
|             |                                                          | 1 2  | 1 2   |      |            |       |
| Figure4-14. | Luenberger observer as transfer function between Y(s), P |      |       |      | (s), and C | (s).  |
|             |                                                          |      |       |      | C          | O     |

|     |     |     |     |     |     | 4.4 | FILTER FORM | OFTHE LUENBERGER |     | OBSERVER | (cid:3) 79 |
| --- | --- | --- | --- | --- | --- | --- | ----------- | ---------------- | --- | -------- | ---------- |
is a single loop, L. 1 The equations for P, 1 P, 2 and L 1 can be read directly from
Figure 4-14:
|     |     |     |     | P =G  | (s)¥G | (s)   |      |     |     |     |     |
| --- | --- | --- | --- | ----- | ----- | ----- | ---- | --- | --- | --- | --- |
|     |     |     |     | 1     | CO    | PEst  |      |     |     |     |     |
|     |     |     |     | P =G  | (s)   |       |      |     |     |     |     |
|     |     |     |     | 2     | PEst  |       |      |     |     |     |     |
|     |     |     |     | L =-G | (s)¥G | (s)¥G | (s). |     |     |     |     |
|     |     |     |     | 1     | CO    | PEst  | SEst |     |     |     |     |
Using Mason’s signal flow graphs, Equation 4.2 can be written by inspection.
|     |     |     |     |     | Y(s)¥P | +P (s)¥P |     |     |       |     |     |
| --- | --- | --- | --- | --- | ------ | -------- | --- | --- | ----- | --- | --- |
|     |     |     |     | C   | (s)=   | 1 C      | 2   |     | (4.2) |     |     |
O
1-L
1
|     |      | Y(s)¥G | (s)¥G |      | (s)+P (s)¥G | (s)  |     |     |     |     |     |
| --- | ---- | ------ | ----- | ---- | ----------- | ---- | --- | --- | --- | --- | --- |
| C   | (s)= |        | CO    | PEst | C           | PEst |     |     |     |     |     |
O
|     |       | 1+G |      | (s)¥G | (s)¥G | (s)    |      |             |      |      |     |
| --- | ----- | --- | ---- | ----- | ----- | ------ | ---- | ----------- | ---- | ---- | --- |
|     |       |     | PEst |       | CO    | SEst   |      |             |      |      |     |
|     |       |     | G    | (s)¥G | (s)   |        |      | G (s)       |      |      |     |
|     | =Y(s) |     |      | PEst  | CO    | +P (s) |      | PEst        |      | .    |     |
|     |       | 1+G |      | (s)¥G | (s)¥G | (s) C  | 1+G  | (s)¥G (s)¥G |      | (ss) |     |
|     |       |     | PEst | CO    | SEst  |        | PEst | CO          | SEst |      |     |
(4.3)
Equation  4.2  is  the  sum  of two  factors. These  factors  are  separated  in
Equation 4.3. The first factor, dependent on the sensor output, Y(s), is shown in
Equation 4.4; note the term G (s) has been multiplied through the fractional term
SEst
and divided out of the scaling term, Y(s). Equation 4.4 can be viewed as the sensor
output,multiplied by the inverse estimated sensor transfer function,and then filtered
by the term on the far right;as will be shown,the term on the right is a low-pass filter.
So, Equation 4.4 is the form shown in Figure 4-4 followed by a low-pass filter.
|     |     |     |          |     | G        | (s)¥G (s)¥G |      | (s) |       |     |     |
| --- | --- | --- | -------- | --- | -------- | ----------- | ---- | --- | ----- | --- | --- |
|     |     |     | Y(s)¥G-1 |     | (s) PEst | CO          | SEst |     | (4.4) |     |     |
SEst
|     |     |     |     |     | 1+G | PEst (s)¥G CO (s)¥G | SEst | (s) |     |     |     |
| --- | --- | --- | --- | --- | --- | ------------------- | ---- | --- | --- | --- | --- |
The second factor of Equation 4.3, dependent on the power converter output, is
shown in Equation 4.5.Here the estimated plant transfer function,G (s),has been
PEst
pulled out to scale the filter term. The scaling term is equivalent to the form shown
in Figure 4-5 used to calculate C (s).As will also be shown,the term on the right is
Est
a high-pass filter. So, equation (4.5) is the form shown in Figure 4-5 followed by a
high-pass filter.
1
|     |     |     | P (s)¥G |      | (s) |         |       |      | (4.5) |     |     |
| --- | --- | --- | ------- | ---- | --- | ------- | ----- | ---- | ----- | --- | --- |
|     |     |     | C       | PEst |     |         |       |      |       |     |     |
|     |     |     |         |      | 1+G | (s)¥G   | (s)¥G | (s)  |       |     |     |
|     |     |     |         |      |     | PEst CO |       | SEst |       |     |     |
4.4.1 Low-Pass and High-Pass Filtering
The rightmost term in Equation 4.4 can be shown to be a low-pass filter. That term
is shown in Equation 4.6.To see this,first consider the individual terms of Equation
4.6. G (s) is a model of the plant. Plants for control systems almost uniformly
PEst

80 (cid:2) CHAPTER 4 THE LUENBERGER OBSERVER:CORRECTING SENSORPROBLEMS
involve one or more integrals.At high frequencies,the magnitude of this term declines
to near zero.G (s) is a model of the sensor.Sensor output nearly always declines at
SEst
high frequencies because most sensors include low-pass filters, either implicitly or
explicitly.The term G (s) is a little more difficult to predict.It is constructed so the
CO
open-loop gain of the observer (G (s)¥G (s)¥G (s)) will have sufficient phase
SEst PEst CO
margin at the observer crossover frequencies. Like a physical control loop, the com-
pensator has a high enough order of differentiation to avoid 180°of phase shift while
the open-loop gain is high. However, the maximum order of the derivative must be
low enough so that the gain at high frequency declines to zero. So, evaluating the
product of G (s), G (s), and G (s) at high frequency yields a small magnitude;
PEst SEst CO
by inspection, this will force the magnitude of Equation 4.6 to a low value at high
frequency. This is seen because the “1” will dominate the denominator, reducing
Equation 4.6 to its numerator.
G (s)¥G (s)¥G (s)
PEst CO SEst (4.6)
1+G (s)¥G (s)¥G (s)
PEst CO SEst
Using similar reasoning, it can be seen that Equation 4.6 will converge to “1”at
low frequencies.As has been established,G (s) will usually have one order of inte-
PEst
gral; at low frequencies, this term will have a large magnitude. G (s) will add one
CO
order of integration or will at least have a proportional term. Typically, G (s)
SEst
will be a low-pass filter with a value of unity at low frequencies. Evaluating the
product of G (s),G (s),and G (s) at low frequency yields a large magnitude;by
PEst SEst CO
inspection, this will force the magnitude of Equation 4.6 to 1. (This can be seen
because the “1”in the denominator will be insignificant, forcing Equation 4.6 to 1.)
These two characteristics, unity gain at low frequency and near-zero gain at high
frequency,are indicative of a low-pass filter.
The right-hand term of Equation 4.5 can be investigated in a similar manner.This
term, shown in Equation 4.7, has the same denominator as Equation 4.6, but with
a unity numerator. At high frequency, the denominator reduces to approximately 1,
forcing Equation 4.7 to 1.At low frequencies,the denominator becomes large,forcing
the term low.This behavior is indicative of a high-pass filter.
1
(4.7)
1+G (s)¥G (s)¥G (s)
PEst CO SEst
4.4.2 Block Diagram of the Filter Form
The filter form of the Luenberger observer is shown as a block diagram in
Figure 4-15. This demonstrates how the observer combines the input from Y(s) and
P (s). Both of these inputs are used to produce the observed state. The term from
C
Y(s) provides good low-frequency information but is sensitive to noise; thus, it is
intuitive that this term should be followed by a low-pass filter. The term from P (s)
C

|     |     |     |     | 4.4 FILTER | FORM OFTHE | LUENBERGER | OBSERVER | (cid:3) 81 |
| --- | --- | --- | --- | ---------- | ---------- | ---------- | -------- | ---------- |
Estimating C(s)
solely based on Y(s)
(see Figure 4-4)
|      |         | G                              | (s)×G | (s)×G | (s) |     |     |     |
| ---- | ------- | ------------------------------ | ----- | ----- | --- | --- | --- | --- |
|      |         | PEst                           | CO    | SEst  |     |     |     |     |
| Y(s) | G -1(s) |                                |       |       |     |     |     |     |
|      | SEst    | 1+G                            | (s)×G | (s)×G | (s) |     |     |     |
|      |         | PEst                           | CO    | SEst  |     |     |     |     |
|      |         | Low-pass filter (Equation 4.6) |       |       |     | +   |     |     |
C (s)
O
+
1
| P (s) | G (s) |                                 |       |       |     |                |     |     |
| ----- | ----- | ------------------------------- | ----- | ----- | --- | -------------- | --- | --- |
| C     | PEst  | 1+G                             | (s)×G | (s)×G | (s) |                |     |     |
|       |       | PEst                            | CO    | SEst  |     |                |     |     |
|       |       | High-pass filter (Equation 4.7) |       |       |     | The Luenberger |     |     |
observer combines Y(s)
Estimating C(s)
| solely based on P |     | (s) |     |     | and P | (s)with filtering |     |     |
| ----------------- | --- | --- | --- | --- | ----- | ----------------- | --- | --- |
|                   |     | C   |     |     |       | C                 |     |     |
| (see Figure 4-5)  |     |     |     |     |       | to get the best   |     |     |
estimate of C(s).
|     |     | Figure 4-15. Filter form of the Luenberger observer. |     |     |     |     |     |     |
| --- | --- | ---------------------------------------------------- | --- | --- | --- | --- | --- | --- |
provides poor low-frequency information because it is subject to drift when integral
gains are even slightly inaccurate.On the other hand,this term is not as prone to gen-
erate high-frequency noise as was the Y(s) term.This is because the plant,which nor-
mally contains at least one integral term, acts as a filter, reducing the noise content
commonly present on the power converter output.It is intuitive to follow such a term
with a high-pass filter.The observed state is formed two different ways from the two
different sources and uses filtering to combine the best frequency ranges of each into
a single output.
One detail that bears discussion is that the two filters of Equations 4.6 and 4.7 sum
to unity. This leads to the more computationally efficient version of the filter form
that is shown in Figure 4-16.It is based on the understanding that 1-Equation 4.6=
Equation 4.7,which can be seen with a little algebra.
|      |      | +     | G (s)¥    | G (s)¥ | G (s) | +   |       |     |
| ---- | ---- | ----- | --------- | ------ | ----- | --- | ----- | --- |
| Y(s) | G    | -1(s) | PEst      | CO     | SEst  |     | C (s) |     |
|      | SEst |       |           |        |       |     | O     |     |
|      |      | _     | 1+ G (s)¥ | G (s)¥ | G (s) |     |       |     |
|      |      |       | PEst      | CO     | SEst  |     |       |     |
+
Low-pass filter (Equation 4.6)
| P (s) | G    | (s) |     |     |     |     |     |     |
| ----- | ---- | --- | --- | --- | --- | --- | --- | --- |
| C     | PEst |     |     |     |     |     |     |     |
Figure 4-16. Computationally efficient filter form of the Luenberger observer.

82 (cid:2) CHAPTER 4 THE LUENBERGER OBSERVER:CORRECTING SENSORPROBLEMS
4.4.3 Comparing the Loop and Filter Forms
The filter form (Figures 4-15 and 4-16) of the Luenberger observer is presented to aid
understanding.The loop form (Figure 4-7) is more practical for several reasons.First,
in most cases, it is computationally more efficient. Also, the loop form observes not
only the plant state, but also the disturbance; the value of disturbance observation
will be discussed in Chapter 6. The filter form does offer at least one advantage
over the traditional form: the process of tuning the observer is exchanged for a
configuration of a filter; for some designers, this process might be more familiar.
The standard form of the Luenberger observer requires the tuning of theG (s)-
CO
G (s)-G (s) loop. This process is like tuning a physical control loop. Like a
PEst SEst
physical control loop, the loop form of observers can become unstable. Assuming
the low-pass filter of Figure 4-16 is implemented in the z-domain as a ratio of two
polynomials,this type of instability can be avoided entirely.However,this advantage
is small as the instability in the loop form is easily avoided. This book will focus on
the loop form but use the filter form for analysis.
4.5 Designing a Luenberger Observer
Section 4.2 provided experiments that demonstrated performance of the Luenberger
observer.In that section,a fully configured observer was provided as part of a control
system. Before the model for that system could be used, several steps were required
to design that observer.Those steps are the focus of this section.There are four major
components of observer design: modeling the sensor, modeling the plant, selecting
the observer compensator, and tuning that compensator. This section will provide
details on each of those components and then conclude with a step-by-step
procedure.
The presentation of observers in this book is based on classical controls: block
diagrams and transfer functions in the s-domain. Readers may have considered that
observers are commonly presented in the matrix-based state-space form. State space
is a useful means of representing observer-based systems,especially when the system
is complex,for example,when high-order plants are used.The weakness of the state-
space representation is that it hinders intuition. The abstract form simplifies mathe-
matical manipulation but leaves most designers puzzled: How can I implement this?
Under what conditions will I see benefit and in what quantity? How do I debug it?
This book presents observers in the classical form, even though the approach is
limited to lower order systems. This approach is well used in application-oriented
writing concerning observers [15; 33, p. 345; 35; 40; 41], even though it is generally
eschewed by authors of academic texts [16,p.299;18,p.70;19,p.400;34,p.653] in
favor of the more general state-space form.The classical approach is used here in the
belief that a great deal of benefit can be gained from the application of observers to
common control systems, but the dominance of the state-space representation has
limited its application by working engineers.

4.5 DESIGNING A LUENBERGER OBSERVER (cid:3) 83
4.5.1 Designing the Sensor Estimator
The task of designing the sensor estimator is to derive the transfer function of the
sensor. The key parameters are filtering and scaling. For example, the model in
Section 4.2 used a low-pass filter with unity gain to model the effects of the sensor.
One benefit of modeling the entire control system (as was done in Section 4.2 and
throughout this book) is that the transfer function of the sensor is known with
complete certainty.In the system of Section 4.2,the sensor was selected as a low-pass
filter so that designing the sensor estimator was trivial (G (s)=G (s)). Of course
SEst S
in a practical system, the sensor transfer function is not known with such precision.
The designer must determine the sensor transfer function as part of designing the
observer.
4.5.1.1 Sensor Scaling Gain
The scaling gain of a sensor is of primary importance. Errors in sensor scaling will
be reflected directly in the observed state. Most sensor manufacturers will provide
nominal scaling gains.However,there may be variation in the scaling,either from one
unit to another or in a particular unit during operation. (If unit-to-unit variation is
excessive,the scaling of each unit can be individually measured.) Fortunately,sensors
are usually manufactured with minimum variation in scaling gains so that with modest
effort,these devices can often be modeled with accuracy.
Offset, the addition of an erroneous DC value to the sensor output, is another
problem in sensors.If the offset is known with precision,it can be added to the sensor
model;in that case,the offset will not be reflected in the observed state.Unfortunately,
offset commonly varies with operating conditions as well as from one unit to another.
Offset typically will not affect the dynamic operation of the observer; however, an
uncompensated offset in a sensor output will be reflected as the equivalent DC offset
in the observed state.The offset then will normally have the same effect,whether the
loop is closed on the sensor output or the observed state:the offset will be transferred
to the actual state;in that sense,the offset response of the observer-based system will
be the same as that of the traditional system.
4.5.2 Sensor Filtering
The filtering effects in a sensor model may include explicit filters, such as when elec-
trical components are used to attenuate noise.The filtering effects can also be implicit
in the sensor structure such as when the thermal inertia of a temperature sensor
produces phase lag in sensor output.The source of these effects is normally of limited
concern at this stage; here, attention is focused on modeling the effects as accurately
as possible,whatever the source.The filtering effects can be thought of more broadly
as the dynamic performance:the transfer function of the sensor less the scaling gain.
As was the case with scaling gains,most manufacturers will provide nominal dynamic

84 (cid:2) CHAPTER 4 THE LUENBERGER OBSERVER:CORRECTING SENSORPROBLEMS
performance in data sheets, perhaps as a Bode plot or as an s-domain transfer
function.Again,there can be variation between the manufacturer’s data and the parts.
If the variation is excessive,the designer must evaluate the effects of these variations
on system performance.
In some cases, varying parameters can be measured. Since gain and offset terms
can be measured at DC, the process to measure these parameters is usually straight-
forward. Measuring the dynamic performance of a sensor can be challenging. It
requires that the parameter under measurement be driven into the sensor input; the
sensor is then calibrated by comparing the sensor output to the output of a calibrat-
ing sensing device, which must be faster and more accurate than the sensor.
Fortunately,such a procedure is rarely needed.Small deviations between the filtering
parameters of the actual and model sensor have minimal effect on the operation of
the observer.The evaluation of errors in sensor estimation will be considered in detail
in the following chapter. For the purposes of this discussion, the assumption is that
sensor model is known with sufficient accuracy.
Since most observers are implemented digitally,filtering effects usually need to be
converted from the s-domain to the z-domain. This was the case in Experiment 4C;
note that G (s) and G (s)are digital equivalents to their analog counterparts.The
PEst SEst
conversion can be accomplished using Table 3-2. This table gives the conversion for
one- and two-pole filters;higher order filters can be converted to a product of single-
and double-pole filters.The conversion to the z-domain is not exact;fortunately,the
z-domain filters in Table 3-2 provide a slight phase lead compared to their s-domain
equivalents, so that the digital form can be slightly phase advanced from the analog
form.However,when adding the delay introduced by sampling,which affects only the
digital form, the result is that both the digital and the analog forms have about the
same phase lag below half the sample frequency (the Nyquist frequency).
4.5.3 Designing the Plant Estimator
The task of designing the plant estimator is similar to that of designing the sensor
estimator:determine the transfer function of the plant.Also like the sensor,the plant
can be thought of as having DC gain and dynamic performance. The plant often
provides more challenges than the sensor. Plants are usually not manufactured with
the precision of a sensor.The variation of dynamic performance and scaling is often
substantial. At the same time, variation in the plant is less of a concern because an
appropriately designed observer compensator will remove most of the effects of such
variations from the observed state. The following discussion will address the process
of estimating the plant in three steps: estimating the scaling gain, the order of
integration, and the remaining filtering effects. In other words, the plant will be
assumed to have the form
1
G (s)=K ¥ ¥G (s), (4.8)
P sN PF

4.5 DESIGNING A LUENBERGER OBSERVER (cid:3) 85
where G (s) is the total plant transfer function, K is the scaling gain, N is the order
P
of integration,and G (s) is the plant filtering.The task of estimating the plant is to
PF
determine these terms.
4.5.3.1 Plant Scaling Gain (K)
The scaling gain, K, is the overall plant gain. As with sensors, the nominal gain of
a plant is usually provided by the component manufacturer. For example, a current
controller using an inductor as a plant has a gain 1/Ls where L is the inductance so
that the plant gain,K,is 1/L;since inductor manufacturers provide inductance on the
data sheet, determining the gain here seems simple. However, there is usually more
variation in the gain of a plant than in that of a sensor. For example, inductance
often is specified only to ±20% between one unit and another. In addition, the gain
of the plant during operation often varies considerably over operating conditions.
Saturation can cause the incremental inductance of an iron-core inductor to change
by a factor of five times or more when current is increased from zero to full current.
This magnitude of variation is not common for sensors.
Another factor that makes determination of K difficult is that it may depend on
multiple components of the machine or process;the contributions from some of those
components may be difficult to measure. For example, in a servo system, the plant
gain Kis K /J,where K is the motor torque constant (the torque per amp) and Jis
T T
total inertia of the motor and the load. The K is usually specified to an accuracy
T
of about 10% and the motor inertia is typically known to within a few percentage
points; this accuracy is sufficient for most observers. However, the load inertia is
sometimes difficult to calculate and even harder to measure. Since it may be many
times greater than the motor inertia, the total plant gain may be virtually unknown
when the observer is designed.Similarly,in a temperature-controlled liquid bath,the
gain K includes the thermal mass of the bath, which may be difficult to calculate
and inconvenient to measure; it might also vary considerably during the course of
operation.
The problems of determining K, then, fall into two categories: determining
nominal gain and accounting for variation.For the cases when nominal gain is diffi-
cult to calculate,it can be measured using the observer with modest effort.A process
for this will be the subject of Section 4.5.3.4.The problems of in-operation variation
are another matter. Normally, if the variation of the plant is great, say, more than
20–50%,the benefits of the observer may be more difficult to realize.Of course,if the
variation of the gain is well known, and the conditions that cause variation are
measured or can otherwise be determined,the estimated scaling gain can be adjusted
to follow the plant. For example, the variation of inductance is repeatable and
relatively easy to measure.In addition,the primary cause of the variation,the current
in the inductor,is often measured in the control system;in such a case,the variation
of the gain can be coded in the observer’s estimated plant. However, in other cases,
accounting for such variation may be impractical.

86 (cid:2) CHAPTER 4 THE LUENBERGER OBSERVER:CORRECTING SENSORPROBLEMS
4.5.3.2 Order of Integration
Most control-system plants have one order of integration, as is the case with all the
plants of Table 2-1.In other cases,the plant may be of higher order because multiple
single-order plants are used such as when a capacitor and inductor are combined
into a second-order “tank” circuit. Higher order plants are common in complex
systems.In any event,the order of the plant should be known before observer design
begins. This is a modest requirement for observers since even a traditional control
system cannot be designed without knowledge of the order of the plant. The
assumption here is that the order of the plant (Nin Equation 4.8) is known.
4.5.3.3 Filtering Effects
After the scaling gain and integration have been removed, what remains of the
plant is referred to here as filtering effects. The plants considered in this book will
normally be simple single- and double-order integrators with scaling. These are the
predominant plant types in industry as demonstrated in Table 2-1. Other dynamic
effects are presumed to be secondary. As with sensors, filtering effects need to be
converted to the z-domain.
Like sensors, the filtering effects of plants can generally be determined through
manufacturer’s data. In most cases, these effects are small or occur at high enough
frequencies that they have little influence on the operation of the control system.For
example, servomotors have two filtering effects which are generally ignored: viscous
damping and interwinding capacitance. Viscous damping contributes a slight
stabilizing effect below a few Hertz. It has so little effect that it is normally ignored
(this should not be confused with Coulomb and static friction, both effects that are
significant but highly nonlinear around zero speed where they cause serious
problems). Parasitic capacitance that connects windings is an important effect but
usually has little to do directly with the control system, because the frequency range
of the effect is so far above the servo controller bandwidth.
4.5.3.4 Experiment 4E: Determining the Gain Experimentally
As discussed in Section 4.5.3.1, the plant scaling gain often must be determined
experimentally.The process to do this is simple and can be executed with an ordinary
Luenberger observer assuming the observer error signal (the input to the observer
compensator) is available and that there are no significant disturbances to the control
loop during this process.The system should be configured as follows:
1. Configure the observer estimated sensor and plant. Use the best guess avail-
able for the estimated plant scaling gain.
2. Configure the system to close the control loop on the sensor feedback.

4.5 DESIGNING A LUENBERGER OBSERVER (cid:3) 87
3. Set the observer gains to very low values.
4. Minimize disturbances or operate the product–process in regions where
disturbances are not significant. (Disturbances reduce the accuracy of this
procedure.)
5. Excite the system with fast changing commands.
6. Monitor E (s),the observer error.
O
7. Adjust the estimated plant scaling gain until the observer error is minimized.
Experiment 4E modifies the model of Experiment 4C for this procedure. The
estimated sensor is accurate;the estimated plant less the scaling gain is also configured
accurately.Only the scaling gain is in error (20 here,instead of 50).The observer error,
E (s), has large excursions owing to the erroneous value of K . The result is shown
O Est
in Figure 4-17.
The effect of changing the estimated scaling gain is shown in Figure 4-18. If K
Est
is either too large (a) or too small (c), the error signal grows. The center (b) shows
K adjusted correctly (K =50). Only when K is adjusted correctly is E
Est Est Est O
minimized.
The process to find K is demonstrated here with a near-perfect sensor estimator
Est
(G (s)=G (s)). However, it is still effective with reasonable errors in the estimated
S SEst
sensor filtering effects. The reader is invited to run Experiment 4E and to introduce
error in the estimated sensor and to repeat the process. Set the bandwidth of the
estimated sensor to 30Hz, a value 50% high (double-click on the node at the top
center of G and set the value to 30). Notice that the correct value of K still
SEst Est
minimizes error,though not to the near-zero value that was attained with an accurate
estimated sensor in Figure 4-18.
Figure 4-17. Output of Experiment 4E with K inaccurate (K =20 and K=50).
Est Est

88 (cid:2) CHAPTER 4 THE LUENBERGER OBSERVER:CORRECTING SENSORPROBLEMS
Error is minimized
with correct gain.
(a) (b) (c)
Figure 4-18. Effect of changing K on E (s)for three settings of K : (a) K =30; (b) K =50; (c) K =85.
Est O Est Est Est Est
Notice in Figure 4-18 that the signal is triggered by the rising edge of the command
signal, which correlates to the rising edge of plant response. Notice that in
Figure 4-18a, where K is low, the initial error (synchronized with a positive-going
Est
plant) is positive; that is, when the gain is low, the action from the actual plant is
greater than that of the observer model. This is intuitive; if the model gain is low, it
will react to the excitation less than the actual plant. On the other hand, when K
Est
is high, as in Figure 4-18c, the gain will be in the opposite direction of plant action
indicating that the model reacts more than the actual plant.This can lead to a more
automated process where the sign of the error (in comparison to plant action)
indicates the direction to adjust K .
Est
The procedure that started this section stated that low gains should be placed
in the compensator. Experiment 4E used K =0, K =0, and K =0.1, low values
IO DO PO
indeed. The only purpose here is to drive the DC error to zero. Otherwise,
the fully integrating plant would allow a large offset in E even if K were correct.
O Est
Another requirement of compensator gains is that they provide a stable loop. A
single integrator in the combined estimated plant and sensor can be stabilized with a
proportional gain.This explains why Experiment 4E has K as its only nonzero gain.
PO
A double integration in that path requires some derivative term.In all cases,the gains
should be low;the low gains allow the designer to see the observer error.High gains
in a well-tuned compensator drive the observer error to zero too rapidly for this
process.
4.5.4 Designing the Observer Compensator
Observer-compensator design is the process of selecting which gains will be used in
the compensator; here, this amounts to selecting which combination of P, I, and D
gains will be required. The derivative gain is used for stabilization. The order of

4.5 DESIGNING A LUENBERGER OBSERVER (cid:3) 89
integration in the G -G path determines the need for a derivative gain in
PEst SEst
G . If the order is two, a derivative gain in G will normally be necessary;
CO CO
without it, the fixed 180° phase lag of double integration makes the loop difficult
to stabilize. In addition, the phase lag of the G -G path at and around the
PEst SEst
desired bandwidth of the observer must be considered.If the phase lag is about 180°
in that frequency range, a derivative term will normally be required to stabilize the
loop.
The need for a derivative term and its dependence on the behavior of G -G
PEst SEst
is demonstrated by comparing the compensators of Experiments 4C and 4E. In
Experiment 4E, the derivative gain is zeroed because the single-integrating plant did
not require a derivative term.In Experiment 4C,a derivative term was required.The
reason for the difference is the change in observer bandwidth.In Experiment 4E,the
observer bandwidth is purposely set very low, well under the sensor bandwidth. In
Experiment 4C, the observer is configured to be operational and its bandwidth is
well above the 20-Hz bandwidth of the sensor;well above the sensor bandwidth,the
single-pole low-pass filter of the sensor has a 90° phase lag like an integrator. That,
combined with the 90° phase lag of a single-integrating plant, generates 180° in the
G -G path and so must be compensated;the derivative gain of G (s) is a simple
PEst SEst CO
way to do so.
Beyond the cases where a derivative gain is required in the compensator,derivative
gains can be used to enhance stability of the loop (this is generally the case in control
systems).However,derivative gains amplify noise.As will be discussed in Chapter 7,
observers are particularly sensitive to noise and the derivative gains can needlessly
increase that sensitivity.
The goal of the observer compensator is to drive observer error to zero. A fully
integrating plant will normally require an integral gain for this purpose. Without
the integral gain, disturbances will cause DC errors in the observed state. Because
disturbances are present in most control systems and because most applications will
not tolerate an unnecessary DC error in the observed state,an integral gain is required
in most observer-based systems. If an integral gain is used, a proportional gain is
virtually required to stabilize the loop. Thus, most systems will require a PID or, at
least,a PI compensator.
The PI–PID compensator is perhaps the simplest compensator available.However,
other compensators can be used. The goal is to drive the observer error to zero and
to do so with adequate margins of stability.Any method used to stabilize traditional
control loops is appropriate for consideration in an observer loop.This book focuses
on relatively simple plants and sensors so the PID compensator will be adequate for
the task.
One final subject to consider in the design of G is saturation.Traditional control-
CO
loop compensators must be designed to control the magnitude of the integral when
the power converter is heavily saturated. This is because the command commonly
changes faster than the plant can respond and large-scale differences in command and
response can cause the integrator to grow to very large values, a phenomenon
commonly called wind-up.If wind-up is not controlled,it can lead to large overshoot

90 (cid:2) CHAPTER 4 THE LUENBERGER OBSERVER:CORRECTING SENSORPROBLEMS
when the saturation of the power converter ends.This is not normally a concern with
observers. Since they follow the actual plant, they are usually not subjected to the
conditions that require wind-up control. For these reasons, PID observer compen-
sators normally do not need wind-up control. When working in Visual ModelQ be
aware that all of the standard VisualModelQcompensators have wind-up control.Be
sure to set the integral saturation levels in the compensator very high so they do not
inadvertently interfere with the operation of the observer.
4.6 Introduction to Tuning an Observer Compensator
Tuning an observer compensator is much like tuning a traditional control system.
Higher gains give faster response but greater noise susceptibility and, often, lower
margins of stability. A major difference is that the observer plant and sensor
parameters are set in software;thus,they are known accurately and they do not vary
during operation. This allows the designer to tune observers aggressively, setting
margins of stability lower than might be acceptable in traditional control loops.
In many cases the gains of the observer compensator are set as high as margins of
stability will allow. As observers are almost universally implemented digitally, the
main cause of instability in the observer is delay from the sample time of the observer
loop. Typically, the observer should operate at a bandwidth much higher than the
control loop for which it provides feedback. For this reason, the observer will
sometimes need to sample faster than the control loop.
Other issues in observer tuning that must be taken into consideration include noise,
disturbances, and model inaccuracy. These are discussed briefly here and will be
discussed in detail in the following three chapters. Noise considerations must be
considered when tuning an observer. Like any control system, higher gains cause
increased noise susceptibility. Further, because of the structure of Luenberger
observers, they are often more susceptible to sensor noise than are most control
systems.In many cases,sensor noise,not stability concerns,will be the primary upper
limit to observer gains.
As with any control system, higher gains provide faster response. The primary
advantage to tuning the observer loop with high gains is fast response to disturbances
and model inaccuracy, reducing the effects of those problems on the observed state.
These subjects will be discussed in detail in Chapters 5 and 6. For the purposes
of this discussion, the assumed goal is to tune the observer for maximum gains
attainable with adequate margins of stability.
In order to provide intuition to the process of tuning,the Luenberger observer of
Figure 4-14 can be drawn as a traditional control loop,as shown in Figure 4-19.Here,
the sensor output, Y(s), is seen as the command to the observer loop. The loop is
closed on the observed sensor output, Y (s); the power converter output, P (s),
O C
appears in the position of feed-forward term.(Just to be clear,this diagram shows the
observer and no other components of the control system.) Accordingly, the process

|       |       |       | 4.6 | INTRODUCTIONTO | TUNING AN OBSERVER | COMPENSATOR | (cid:3) 91 |
| ----- | ----- | ----- | --- | -------------- | ------------------ | ----------- | ---------- |
| P (s) |       |       |     |                |                    | C (s)       |            |
| C     |       |       |     |                |                    | O           |            |
|       | E (s) |       | +   |                |                    | Y (s)       |            |
|       | + O   |       |     |                |                    | O           |            |
| Y(s)  |       | G (s) |     | G (s)          | G (s)              |             |            |
|       |       | CO    |     | PEst           | SEst               |             |            |
|       | _     |       | +   |                |                    |             |            |
Figure 4-19. Luenberger observer drawn as a traditional control loop.
of tuning the observer loop is similar to tuning a traditional control system with
feed-forward.
The procedure here is:
1. Temporarily configure the observer for tuning.
2. Adjust the observer compensator for stability.
3. Restore the observer to the normal Luenberger configuration.
4.6.1 Step 1: Temporarily Configure the Observer for Tuning
The observer should be temporarily configured with a square-wave command in place
of Y and without the feed-forward (P ) path. This is done in Experiment 4F and is
C
shown in Figure 4-20. The command square-wave generator, R, has been connected
in the normal position for Y.The estimated sensor output,Y ,is the primary output
O
for this procedure.
The square-wave generator is used because it excites the observer with a broader
range of frequencies than the physical plant and sensor normally can. The rate of
|     | Figure 4-20. | Experiment 4F: Tuning an observer compensator. |     |     |     |     |     |
| --- | ------------ | ---------------------------------------------- | --- | --- | --- | --- | --- |

92 (cid:2) CHAPTER 4 THE LUENBERGER OBSERVER:CORRECTING SENSORPROBLEMS
change of a sensor is limited by physics: inertia makes instantaneous changes un-
attainable. There is no such limitation on command generators. The use of the
square-wave command to excite the observer allows the designer to more clearly see
its response to high frequencies.The sharper edges of a square wave reveal more about
the observer’s margins of stability than do the gentler output signals of a physical
sensor.
4.6.2 Step 2: Adjust the Observer Compensator for Stability
As with physical loops, the observer compensator can be tuned experimentally with
a zone-based tuning procedure (see Section 3.4). For a PID observer compensator,
this implies that the proportional and integral terms are zeroed while the derivative
gain is tuned. The proportional gain is tuned and then, finally, the integral term
it tuned. For a PI observer compensator, zero the I-term and tune the P-term; then
tune the I-term. The results of applying this method to the PID compensator in
Experiment 4F are shown in Figure 4-21. Note that in many cases, a DC offset will
appear in the feedback signal when K is zero; if the offset is large, it can move
PO
the error signal off screen.If this occurs,temporarily set K PO to a low value until the
| offset is eliminated;in Experiment 4F,use K |     |     |     |     | =0.1 for this effect. |     |     |     |
| ------------------------------------------- | --- | --- | --- | --- | --------------------- | --- | --- | --- |
PO
During the process of tuning, the term driven by P should be zeroed. This is
C
because the P term acts like a feed-forward to the observer loop, as shown in
C
Figure  4-19. Zone-based  tuning  recommends  that  all  feed-forward  paths  be
temporarily eliminated because they mask the performance of the loop gains. After
| the loop is tuned,the path from P |     |     |     | can be restored. |     |     |     |     |
| --------------------------------- | --- | --- | --- | ---------------- | --- | --- | --- | --- |
C
1. Raise K for no or  2. Raise K for up  3. Raise K for no or
|                   | DO  |         |                  | PO  |          |                 | IO  |            |
| ----------------- | --- | ------- | ---------------- | --- | -------- | --------------- | --- | ---------- |
| minimal overshoot |     |         | to 25% overshoot |     |          | minimal ringing |     |            |
|                   |     | K = 0.1 |                  |     | K = 0.1  |                 |     | K = 0.1    |
|                   |     | DO      |                  |     | DO       |                 |     | DO         |
|                   |     | K = 0.0 |                  |     | K = 60.0 |                 |     | K = 60.0   |
|                   |     | PO      |                  |     | PO       |                 |     | PO         |
|                   |     | K       |                  |     | K        |                 |     | K          |
|                   |     | = 0.0   |                  |     | = 0.0    |                 |     | = 10,000.0 |
|                   |     | IO      |                  |     | IO       |                 |     | IO         |
|                   | (a) |         |                  | (b) |          |                 | (c) |            |
Figure 4-21. Tuning the observer of Experiment 4F in zones. Start with zero gains. (a) Raise K , but avoid
DO
|     | overshoot. (b) Raise K |     | for about 25% overshoot. (c) Raise K |     |     | until ringing just starts. |     |     |
| --- | ---------------------- | --- | ------------------------------------ | --- | --- | -------------------------- | --- | --- |
|     |                        |     | PO                                   |     |     | IO                         |     |     |

4.6 INTRODUCTIONTO TUNING AN OBSERVER COMPENSATOR (cid:3) 93
4.6.2.1 Modifying the Tuning Process for Nonconfigurable Observers
If it is not possible to reconfigure the observer to the form shown in Figure 4-20,
the observer can still be tuned by selecting the gain margin.First the system must be
configured so the control loop is closed on the sensed signal since this method will
temporarily generate instability in the observer. The low-frequency gains are zeroed
and the high-frequency gain (typically K ) is raised until the observer becomes unstable,
DO
indicating 0dB gain margin. The gain is then lowered to attain the desired gain
margin. For example, raise K in steps of 20% until the observer oscillates, and
DO
then reduce it by, say, 12dB (a factor of 4) to yield 12dB of gain margin for the
observer.
The interested reader may wish to verify this with Experiment 4F. Configure the
waveform generator Command(right-click on the waveform generator block to adjust
its properties) for gentler excitation,similar to what might come from a physical plant
and sensor:set Waveform to “s-curve”and set Frequency to 20Hz.Zero K and K .
PO IO
(Temporarily set K to 0.1 to eliminate DC offset if necessary.) Raise K in small
PO DO
steps until the observer becomes unstable—this occurs at K (cid:2)0.32. Notice that
DO
there are no signs of instability with the s-curve command until the system becomes
self-oscillatory. Reduce K by 12dB or a factor of 4 to 0.08 to get 12dB of gain
DO
margin; this is essentially the same value that was found with the tuning procedure
above (K =0.1).Repeat for the remaining gains.
DO
4.6.2.2 Tuning the Observer Compensator Analytically
Observers can be tuned analytically; this is generally easier than tuning a physical
system analytically because the transfer function of the observer is known precisely.
After the transfer function is found, the gains can be set to modify the poles of the
transfer function.Pole placement methods are presented in [16, p. 308].
4.6.2.3 Frequency Response of Experiment 4G
This section will investigate the frequency response of the observer. Experiment
4G is reconfigured to include a dynamic signal analyzer or DSA (see Figure 4-22).
The DSA is placed in the command path; this means the DSA will inject random
excitation into the command and measure the response of certain signals.The closed-
loop response is shown by the DSA as the relationship of Y to R.A variable block
O
has been added for E ,the observer error,so the open-loop response of the observer
O
can be displayed. The relationship of Y to E in the DSA is the open-loop gain of
O O
the observer.
The closed-loop Bode plot taken from Experiment 4G is shown in Figure 4-23.
The plot shows the closed-loop response as having high bandwidth compared to the
sample rate. The observer is sampled at 1000Hz as defined by the digital controller

94 (cid:2) CHAPTER 4 THE LUENBERGER OBSERVER:CORRECTING SENSORPROBLEMS
Figure 4-22. Experiment 4G, adding a DSAto Experiment 4F.
(not shown in Figure 4-22). However, the response is still 0dB at 250Hz, one-fourth
of the sample rate.(The performance above 250Hz is difficult to determine here since
the FFT also samples at 1000Hz and does not provide reliable data above one-fourth
of its sample frequency.) There is about 4dB of peaking at 100Hz, a substantial
amount for a physical control system but reasonable for an observer. Recall that
The observer
has good
response up to
and beyond
250 Hz, 1/4 of
the sample
frequency,
demonstrating
that the
observer is
tuned
aggressively.
Figure 4-23. Frequency response of the Luenberger observer of Experiment 4G.

4.7 EXERCISES (cid:3) 95
observers do not need robustness for dealing with parameter changes as do
ordinary control systems and so stability margins can be lower than physical control
systems.
Experiment 4G confirms that the observer gains are set quite high for the sample
rate. In fact, the only limitation is the sample rate itself. Were the observer sampled
faster,the gains could be raised.The reader may wish to experiment here.The sample
time (TSample) can be reduced to 0.00025. Using the same procedure as above, the
gains can be raised to approximately K =0.6, K =500, and K =500,000. In
DO PO IO
this case the observer bandwidth is about 1000Hz, still one-fourth of the sample
frequency.
One point that needs to be reinforced is that it is often not appropriate to
maximize the bandwidth of the observer. High observer bandwidth maximizes the
response to sensor noise.(None of the experiments in this chapter have noise sources.)
One strength of observers is that they can be used to filter sensor noise while using
the power converter signal to make up for any phase lag. So, sensor noise will often
be the dominant limitation on observer bandwidth,in which case the observer band-
width may be intentionally set lower than is possible to achieve based on stability
margins.So this procedure reaches the upper limit of observer loop response;be pre-
pared to return and lower the response, for example by lowering K and reducing
DO
the other gains according to Figure 4-21.
4.6.3 Step 3: Restore the Observer to the Normal Luenberger Configuration
Restore the observer to the normal Luenberger configuration as shown in
Figure 4-8. Remove the connection to the waveform generator and reconnect Y (s).
O
Reconnect the path from P (s).The observer should be ready to operate.
C
4.7 Exercises
1. Compare the rise time of observer- and nonobserver-based systems to a step
command.
A. Open Experiment 4A and retune the system for reasonable margins of
stability (e.g., find maximum K without overshoot and maximum K for
P I
30% overshoot to step).
B. What is the settling time?
C. Repeat A and B using the observer-based system of Experiment 4C.
D. Why is there a large difference in settling times? How does that difference
relate to the observer?
2. Retune an observer for a lower bandwidth.
A. Open Experiment 4G and retune the system starting with K =0.05,
DO
K =0, and K =0. For limits allow 15% overshoot with K and slight
PO IO PO
ringing with K .
IO

96 (cid:2) CHAPTER 4 THE LUENBERGER OBSERVER:CORRECTING SENSORPROBLEMS
B. What is the bandwidth of the observer?
C. Using Experiment 4C, place the values of part A in the observer and see
the effect on command response. Evaluate settling time and compare to
results with original observer gains (see Problem 1C). Explain the differ-
ence (or lack of difference).
3. Using hot connection on the LiveScopein Experiment 4C,compare the plant
output (C) to the sensor output (Y).
A. Are they similar?
B. If so,does this imply sensor phase lag is not a significant factor in closed-
loop performance?
4. Show that having the correct value for estimated sensor bandwidth does not
affect the experimental process to find K discussed in Section 4.5.3.4.
Est
Corrupt the value of the sensor bandwidth by changing it from 20 to 30Hz
(top node of G block); be careful to restore the value to 20 before saving
SEst
the file as changing the value of a node permanently modifies the mqdfile.
A. Adjust K to minimize error signal,E .
Est O
B. What conclusion could you draw?

Chapter 5
The Luenberger Observer
and Model Inaccuracy
In this chapter...
• Common sources of model inaccuracy
• Effects of model inaccuracy on observer-based systems
• Several software experiments demonstrating results of inaccuracy
This chapter continues the discussion of Chapter 4, analyzing and experimenting
with the Luenberger observer.Several important aspects of observer performance are
presented, especially how observers behave in the presence of errors in the observer
model. Key points are developed analytically and demonstrated in software
experiments.
In the previous chapter, the observer structure was developed largely assuming
ideal conditions.Of course,in practical systems,conditions are not ideal.The control-
system designer needs to understand the effects ofnonideal conditions on the observer
and on the control system as a whole. The main sources of nonideal conditions
are model inaccuracy, disturbances, and noise. This chapter will discuss problems of
model inaccuracy, Chapter 6 will discuss disturbances, and Chapter 7 will deal with
the effects of noise.
5.1 Model Inaccuracy
Model inaccuracy describes the different types of error that can be present in plant
and sensor models; these models form the observer’s model system as shown in
Figure 5-1.Observers produce the observed state,C ,by driving two signals,the power
O
97

| 98 (cid:2) | CHAPTER 5 | THE LUENBERGER | OBSERVER | ANDMODELINACCURACY |     |     |     |
| ---------- | --------- | -------------- | -------- | ------------------ | --- | --- | --- |
C(s)
|     | P (s) |     |     | G (s) |     | G (s) | Y(s) |
| --- | ----- | --- | --- | ----- | --- | ----- | ---- |
|     | C     |     |     | P     |     | S     |      |
Actual
Actual
|     | Plant |     |     |       | state |        |        |
| --- | ----- | --- | --- | ----- | ----- | ------ | ------ |
|     |       |     |     | Plant |       | Sensor | sensor |
excitation
|     |     |     |     |     | Physical system |     | output |
| --- | --- | --- | --- | --- | --------------- | --- | ------ |
E (s)
|     |     |     | D (s) |     |       |           | +   |
| --- | --- | --- | ----- | --- | ----- | --------- | --- |
|     |     |     | O     |     | G (s) | O         |     |
|     |     |     |       |     | CO    | Observer  | _   |
error
Observer
compensator
|     |     |     | +   |       | C (s)    |       |       |
| --- | --- | --- | --- | ----- | -------- | ----- | ----- |
|     |     |     |     | G     | (s) O    | G (s) | Y (s) |
|     |     |     |     | PEst  | Observed | SEst  | O     |
+
|     |     |     |     |       | state |        | Observed |
| --- | --- | --- | --- | ----- | ----- | ------ | -------- |
|     |     |     |     | Plant |       | Sensor |          |
sensor
|     |     |     |     |             | Modeled system           |     | output |
| --- | --- | --- | --- | ----------- | ------------------------ | --- | ------ |
|     |     |     |     | Figure 5-1. | The Luenberger observer. |     |        |
converter output and sensor output,through the plant and sensor models.Of course,
the accuracy of the estimated state is directly linked to the accuracy of those models.
|     | 5.1.1 | Sources of Model Inaccuracy |     |     |     |     |     |
| --- | ----- | --------------------------- | --- | --- | --- | --- | --- |
There are many sources of model inaccuracy.Acquiring data from manufacturers and
making independent measurements of control-system components can minimize that
inaccuracy.Fine-tuning observer parameters will further reduce inaccuracy.However,
in practical systems,some inaccuracy in plant and sensor models will be present.The
following sections will address some of the effects of those inaccuracies. The good
news,as will be shown in the remainder of this chapter,is that observer-based systems
are often no more sensitive to parametric variation than are traditional control
systems.
The most common source of model error is probably that the complexity of
implementing an accurate model in real time is too great for most systems. Nonlinear
effects can be difficult to model in terms of both design effort and requirements
for computational resources.For example,friction in motion systems can be modeled
as simple viscous damping, which is represented as a force proportional to velocity.
A term for Coulomb or sliding friction can be added, which is usually represented
as a fixed-magnitude force in opposition to the velocity. For greater accuracy at
low speeds, the Stribeck effect, which is the cause of stiction, can be modeled.
Unfortunately, the  Stribeck  effect  requires  considerable  computational  resources
to  model  [3, 25]. Given  the  complexity  of modeling  friction  accurately, many
motion-system observers rely simply on viscous damping or ignore friction altogether.

5.1 MODELINACCURACY (cid:3) 99
Another source of model inaccuracy is the reliance on lumped-parameter models,
which reduce model complexity by combining states. For example, the temperature
of an object varies across the volume of that object. Modeling only the average
temperature lumps the various regions of the object into a single thermal mass,which
can be represented by one state.The model’s accuracy can be improved by modeling
the mass in many discrete regions where each region requires an independent
state. However, coarse lumped-parameter models are commonly used because the
disadvantage of reduced accuracy is usually offset by the advantages of reduced
computational resources and reduced effort to code and configure the observer.
Manufacturers often provide scant detail on the dynamic operation of their
products.The responsiveness of a sensor may be given simply as phase lag at a certain
frequency or as bandwidth (the -3dB frequency), both of which are inadequate
representations for an observer model. Observer models require knowledge of
component behavior across a broad range of frequencies. Ideally, this would be
provided as an s-domain equation or, perhaps, as a Bode plot. However, many
manufacturers do not invest the resources to produce such detailed information for
their customers.
When characterizing a manufacturer’s components, consider contacting the com-
pany. Manufacturers may be willing to provide data beyond what they normally
publish.In most cases,only a fraction of a manufacturer’s customers will require the
detailed information needed by someone implementing an observer. If the manu-
facturer is unable to provide the necessary information on their components,consider
making independent measurements. With proper equipment, the dynamic perfor-
mance of a component can be thoroughly measured.Of course,one disadvantage of
making independent measurements is that manufacturers will not stand behind the
results.Should the process or materials used to manufacture the components change,
the performance of the component may change, possibly rendering the independent
measurements inaccurate.
Parametric errors produce errors in the observed state, even when model struc-
tures are accurate. This is especially true in complex models because the comple-
xity of measuring or calculating multiple parameters increases with the complexity
of the model. Unit-to-unit variation causes parametric inaccuracy. In practical
systems, virtually every parameter of a component will vary due to manufacturing
tolerances. For example, the torque constant (the relationship between current and
torque) of a servomotor will typically vary ±10% from one motor to the next. The
values of passive electronic components,such as capacitors and inductors,often vary
±20%.The loss of accuracy in observer models due to unit-to-unit tolerances can be
significant.
The variation of sensors is usually more closely controlled than that of plants.
Most sensor manufacturers control the variation of key parameters such as DC gain
and offset. However, variation in dynamic performance is more difficult to control
and generally less important for most control-system applications. As a result, the
dynamic behavior of a sensor product line may vary significantly from one unit to
another.

100 (cid:2) CHAPTER 5 THE LUENBERGER OBSERVER ANDMODELINACCURACY
One way to compensate for unit-to-unit variation is to fine-tune or “tweak in”the
model. However, implementing a process to manually tune every system is usually
practical only for low-volume, high-value control systems. It might make sense for
a rolling mill, but it probably will not for a power supply. Even when fine-tuning is
practical, it adds complications. The process may have to be repeated in the field
when components are replaced as part of system maintenance or repair.If the control
system is being built for resale, the requirement of field adjustment should be
considered carefully as the ability of a company to reliably implement a fine-tuning
procedure outside its factory is often limited.
Although the problems of manual fine-tuning make it impractical for many
systems, it should be noted that some facets of fine-tuning can be carried out auto-
matically.For example,a method based on zeroing the product of observer error and
sensor output (E ¥Y) can be executed by the controller to fine-tune the scaling
O
constant of the plant model.The use of automated procedures can make fine-tuning
practical on high-volume products and for in-field procedures. The E ¥Y method is
O
demonstrated in Experiment 5B.
Another source of model inaccuracy is component variation during operation.
For example, temperature changes the resistance of conductive materials, and the
capacitance of electrolytic capacitors varies as the components age. So, the
operation of a plant or sensor may change over years of service or just over the time
it takes the temperature to change. If these changes are large enough, the accuracy
of the observer will be affected, no matter how well the manufacturer’s data
describe the component or how accurately the model parameters were originally
fine-tuned.
While the changes in component behavior with temperature and aging are often
small, some operation-dependent system changes are dramatic. For example, the
inertia of a reel from which material is unwound may vary by a factor of ten or more
over the course of just a few minutes.The liquid level,and thus the thermal mass,of
a temperature bath can vary rapidly. These changes can result in variation large
enough to cause instability in the control system. In such a case, the condition that
causes the change usually must be monitored and the control system adjusted for its
effect. Of course, when a parameter varies by an order of magnitude, attempting to
characterize it to a few percentage points over the entire operating range is normally
impractical.
5.2 Effects of Model Inaccuracy
The effects of model inaccuracy will be evaluated both analytically and experimen-
tally. The strength of analysis is that it allows broad predictions. Unfortunately,
analysis is often limited to straightforward effects.The experimental approach offers
the ability to investigate a broader combination of effects. The weakness of an
experimental approach is that it does not directly yield principles;the ability to predict
effects relies on performing experiments under sufficiently broad conditions. The

|     |     | 5.2 EFFECTS OFMODELINACCURACY | (cid:3) 101 |
| --- | --- | ----------------------------- | ----------- |
approach in this chapter will be to start with analysis and then experiment with Visual
ModelQ models.
5.2.1 Analytical Evaluation
The analytical evaluation will be divided into two parts.The first section will discuss
the effects of plant-model inaccuracy;the next will look at sensor-model inaccuracy.
The focus in this section will be inaccuracy in the scaling gain, here called K . This
Est
term is often difficult to characterize in the plant model.
5.2.1.1 Plant Inaccuracy
The effect of estimated-plant inaccuracy on the observed state, C , can be seen
O
by  considering  Equation  5.1. (Equation  5.1  was  developed  in  Section  4.4  as
Equation 4.3.) The sensor (first) term is followed with a low-pass filter;that filter has
a bandwidth equal to that of the observer. Thus, it would be expected that errors
in the sensor model would be most significant at frequencies below the observer
bandwidth. On the other hand, the power converter (second) term, which relies
directly on the plant model, is followed with a high-pass filter. Thus, it would be
expected that errors in the plant model would be most significant at frequencies above
the observer bandwidth.That is,in fact,the case.
|             | G (s)¥G   | (s)¥G (s) |     |
| ----------- | --------- | --------- | --- |
| C =Y(s)¥G-1 | (s) PEst  | CO SEst   |     |
| O           | SEst      |           |     |
|             | 1+G (s)¥G | (s)¥G (s) |     |
|             | PEst      | CO SEst   |     |
1
| +P (s)¥G | (s)  |                 | (5.1) |
| -------- | ---- | --------------- | ----- |
| C        | PEst |                 |       |
|          | 1+G  | (s)¥G (s)¥G (s) |       |
PEst CO SEst
5.2.1.2 Corruption of Observed-State Gain Caused by Plant Gain Errors
The power converter (second) term in Equation 5.1 is the product of the power con-
verter output and the plant model, processed by a high-pass filter. Well above the
observer bandwidth, the filter gain approaches unity because the denominator term
of G (s)¥G (s)¥G (s)  diminishes; this  leaves  the  power  converter  term  as
PEst CO SEst
approximately P (s)¥G (s).Here,errors in the plant model,G (s),are translated
| C PEst |     | PEst |     |
| ------ | --- | ---- | --- |
directly to the observed state. By this reasoning, errors in K will translate directly
Est
to the output well above the observer bandwidth.
5.2.1.3 Corruption of Observed-State Phase Caused by Plant Gain Errors
A second effect of inaccurate estimated-plant gain is in the phase of the observed
state. This effect can also be seen in Equation 5.1. First, consider the actual plant.
As discussed in Section 4.1.2, in the absence of inaccuracy, C(s) is equal to both

| 102 (cid:2) | CHAPTER 5 | THE LUENBERGER | OBSERVER ANDMODELINACCURACY |     |     |     |
| ----------- | --------- | -------------- | --------------------------- | --- | --- | --- |
P (s)¥G (s) and Y(s)¥G-1(s),so that P (s)¥G (s)=Y(s)¥G-1(s).Accordingly,in the
|     | C                | P     | S            | C    | P   | S   |
| --- | ---------------- | ----- | ------------ | ---- | --- | --- |
|     | ideal observer,P | (s)¥G | (s)=Y(s)¥G-1 | (s). |     |     |
|     |                  | C     | PEst         | SEst |     |     |
Now consider the filtering terms in Equation 5.1. They are low- and high-pass
filters  with  identical  bandwidths. Thus, the  phase  from  the  filter  terms  will  be
equal in magnitude and opposite in sign at all frequencies. In the ideal case, where
P (s)¥G (s)=Y(s)¥G-1 (s), the phase from the two filtering terms will cancel;
|     | C   | PEst | SEst |     |     |     |
| --- | --- | ---- | ---- | --- | --- | --- |
thus, the phase from the filters will not affect the observed state. However, when
K is inaccurate,it forces P (s)¥G (s) high or low;P (s)¥G (s) is no longer equal
|     | Est |     | C PEst |     | C   | PEst |
| --- | --- | --- | ------ | --- | --- | ---- |
to Y(s)¥G-1 (s), and the phase terms from the two filters no longer cancel. The net
SEst
effect is that errors in K cause phase distortion in the observed state around the
Est
observer bandwidth.Scaling errors do not cause phase errors well above the observer
bandwidth because the magnitude of the low-pass filter term is so low it has little
effect on the observed state;also,K does not affect the phase of the high-frequency
Est
term.
|     | 5.2.2 | Effects of Inaccuracy in the Sensor Model on C |     |     |     |     |
| --- | ----- | ---------------------------------------------- | --- | --- | --- | --- |
O
The  effects  of sensor-model  inaccuracy  can  also  be  understood  by  considering
Equation 5.1.The sensor model appears mainly in the sensor (first) term,which is the
dominant term at low frequency. Thus, the frequency range where inaccuracy in the
sensor model dominates is below the observer bandwidth. Consider from Figure 4-4
that C(s)=Y(s)¥G-1(s);from the discussion above,at frequencies below the observer
S
bandwidth, the observed state, C (s) (cid:2) Y(s)¥G-1 (s). Combining this equation and
|     |     |     | O   |     | SEst |     |
| --- | --- | --- | --- | --- | ---- | --- |
approximation, the observed state at low frequencies compared to the actual state
is C (s)/C(s) (cid:2) G (s)/G (s). Inaccuracy in G (s), which is in the denominator,
|     | O   | S   | SEst |     | SEst |     |
| --- | --- | --- | ---- | --- | ---- | --- |
causes the inverse effect in the observed state, C (s), which is in the numerator. For
O
example,phase lag in the estimated sensor model will cause phase advance in observer
output.
|     | 5.3 | Experimental Evaluation |     |     |     |     |
| --- | --- | ----------------------- | --- | --- | --- | --- |
Studying inaccuracy requires differentiating between two separate problems: inaccu-
rate modeling and the effects of variation.The difference is whether the error appears
before or after the system is configured. If an observer model is incorrect from
the start, the error is present before the observer is tuned. The second type of error,
variation, appears after the observer is configured. Here, the observer is tuned with
accurate models, but through time, operating parameters, or unit-to-unit variation,
the dynamics change. The investigation of variation will rely on varying the actual
plant and sensor parameters after the observer is configured. The investigation of
inaccurate modeling will be performed by varying observer-model parameters before
the observer is configured.

5.3 EXPERIMENTALEVALUATION (cid:3) 103
5.3.1 Precise Tuning Procedure
Before experiments can be run,a precise observer-tuning process must be developed.
The process that will be used in this section is similar to that developed in
Chapter 4, but measures of performance will be evaluated more accurately. This
effort is not normally required for observers in products—small differences in tuning
parameters have minimal effect on system performance.However,in this case,the goal
will be to demonstrate general principles using experimental data.Observer dynamic
performance should be held as constant as possible to ensure that the data show effects
genuinely caused by the error sources under study and not because of unintentional
changes in observer tuning.
The procedure that will be used in these sections is:
1. Configure the observer for tuning, similar to that shown in Figure 4-22
(Experiment 4G). Add the ability to adjust the actual sensor bandwidth. The model
for this procedure is Experiment 5A and is shown in Figure 5-2. (Note that this
model has an observer sample time of 0.0001s, much faster than the observers of
Chapter 4. The change was made to minimize the effects of the sample time so this
and the following experiments can focus on model inaccuracy.)
2. As before, start tuning K after zeroing K and K . Tune K for 120-Hz
DO PO IO DO
bandwidth. The value of bandwidth is somewhat arbitrary. In a physical system
it would often be set based on noise considerations, which will be discussed
in Chapter 7. For now, 120Hz will be assumed as a system requirement and all
observer tuning will conform to that measure within a few percentage points.Be aware
that the bandwidth is not simply the frequency where the observer gain falls to 3dB,
Figure 5-2. Experiment 5A: Observer configured for tuning.

104 (cid:2) CHAPTER 5 THE LUENBERGER OBSERVER ANDMODELINACCURACY
Figure 5-3. Experiment 5B: Adjusting K using an RMS meter on E ¥Y.
Est O
but where it falls 3dB below the DC gain. That distinction is important when K
DO
is adjusted with other gains zeroed because the DC gain is less than zero by a few
decibels.
3. Raise K until there is 15% overshoot in response to a step function. As it
PO
turns out,this will raise the bandwidth by approximately 30%.
4. Raise K until there is 25% overshoot in response to a step function. This
IO
will not substantially affect the bandwidth.
5. Configure a second model to adjust K .The system is similar to Figure 4-17
Est
(Experiment 4E) except an RMS meter has been added to monitor E ¥Y and so
O
allow more accurate adjustment of K through minimizing the meter output. This
Est
technique is based on the discussion in Section 4.5.3.4. Using this technique under
nominal conditions, K will adjust to K with accuracy. The model to adjust K is
Est Est
Experiment 5B and is shown in Figure 5-3.
This procedure was applied to the model system of Experiment 5A.The resulting
observer gains were K =0.1,K =45,and K =6400,values similar to those derived
DO PO IO
in Chapter 4.The resulting Bode plots of the observer,less the power converter path,
are shown in Figure 5-4.
5.3.2 Simulating Parameter Variation
The effects of plant gain error will be demonstrated by varying the value of K, and
the effect of sensor dynamic variation will be simulated by changing the sensor band-
width.The effects will be considered in two stages.First,observer inaccuracy will be
considered.In this case,the control loop will be closed based on sensor feedback.The

5.3 EXPERIMENTALEVALUATION (cid:3) 105
Non-zero K observer yields 0 dB at low
PO
frequency and raises bandwidth to 155 Hz.
K -only yields less than K -only gives a
DO DO
0 dB gain at low frequency. bandwidth of 120 Hz.
Figure 5-4. From Experiment 5A, gain (above) and phase of frequency response of observer less power
converter path for two conditions: K =0.1, K =K =0 and K =0.1, K =45, K =6400.
DO PO IO DO PO IO
primary concern will be the comparison of the actual and observed states. Second,
the effect on the stability of the overall control loop will be studied. Here, the loop
feedback will be taken from the observed state. The primary concern will be the
response of the actual state to the command.
5.3.2.1 Effects on the Observed State
The effect of variation on the observed state will be demonstrated using Experiment
5C,which is shown in Figure 5-5.This is a control system with an observer,but still
using the sensed signal for feedback;this allows variation in the observed state without
affecting control-loop operation. The observed and actual states are shown in Live
Scopes. Live Constants are provided for K (plant gain) and FG (sensor bandwidth).
S
While these displays are helpful,time-domain plots of the observed and actual states
are not reliable measures of observer performance because many of the effects
occur at high frequency.Thus,these experiments will rely mostly on the output of the
DSA, which can be brought to view by double-clicking on the DSA icon after the
model is compiled. Note also that the gains of the PI control law, G , have been
C
reduced (K =0.6,K =12) so the system will have reasonable margins of stability under
P I
nominal conditions.This is done to avoid the distraction caused by the control system
ringing.
The effects of varying Kare shown in Figure 5-6.Three plots are run for the cases
of K=25,50 (nominal),and 100.The observer accuracy with nominal values is nearly
perfect,as is shown with the center plots,which have 0dB gain and 0°phase lag.When

106 (cid:2) CHAPTER 5 THE LUENBERGER OBSERVER ANDMODELINACCURACY
Figure 5-5. Experiment 5C: Investigating the effects of variation on observer performance.
Observer bandwidth
Low K(or high K ) (150 Hz)
Est
translates to higher gain.
High K(or low K )
Est
translates to lower gain.
Nominal Kproduces
Low K(or high K ) ideal gain and phase.
Est
causes phase advance.
High K(or low K )
Est
causes phase lag.
Figure 5-6. From Experiment 5C, the effects on observer accuracy of varying Khigh (100) and
low (25) from nominal (50).

5.3 EXPERIMENTALEVALUATION (cid:3) 107
Kis raised above K ,the observer gain is low (that is,K is lower than K) and phase
Est Est
lag is injected near the observer bandwidth. When K it lowered, the opposite effects
occur. This is consistent with the analytical results above.
The effects of varying the sensor bandwidth,FG ,on observer accuracy are shown
S
in the Bode plot of Figure 5-7. These results are also from Experiment 5C. Three
plots are run for the cases of FG =10, 20 (nominal), and 40. When FG is nominal,
S S
the results are essentially ideal. When FG is low (10Hz), it causes phase lag
S
below the observer bandwidth.This is consistent with the analytical prediction since,
below the bandwidth, the C (s)/C(s)(cid:2)G (s)/G (s) (see Section 5.2.2). Thus, phase
O S SEst
lag in G (s) should be (and is) translated to phase lag in C (s). However, at higher
S O
frequencies,the effect of the filtering terms reverses this trend so that low FG causes
S
phase advance. Given that lowering FG both advances phase and attenuates gain
S
at higher frequencies,one might predict that the overall effect of this error on control-
loop stability would be positive. With similar reasoning, raising FG should harm
S
control-loop stability. In fact, that is the case when the control-system dynamics
are near the observer dynamics. However, that effect will not be demonstrated
in these experiments since the observer dynamics are well above the control-loop
dynamics.
Observer bandwidth
High FG (150 Hz)
S
Low FG causes
S
gain attenuation Nominal FG S. produces
at low frequency. ideal gain and phase.
High FG
S
Low FG causes
S
phase lag at low
frequency.
Figure 5-7. From Experiment 5C, the effects on observer accuracy of varying FG high (40) and
S
low (10) from nominal (20).

108 (cid:2) CHAPTER 5 THE LUENBERGER OBSERVER ANDMODELINACCURACY
5.3.2.2 Effects on Control-System Response and Stability
The effect of variation on the observed state will be demonstrated using Experiment
5D, which is shown in Figure 5-8. This is similar to Experiment 5C except for two
changes.First,the control law (G ) uses the observed state for feedback.Second,the
C
gains of the PI control law G have been raised to K =1.5 and K =30,the gains used
C P I
in Chapter 4.The higher control-law gains will make the effects of variation easier to
recognize.
The effects on control-loop stability of varying K are shown in Figure 5-9. The
bandwidth of the controller varies approximately in proportion to the variation of K.
K set to 25, 50 (nominal), and 100 produces about 12-, 25-, and 50-Hz bandwidth,
respectively. This variation is neither greater nor less than would be expected in a
traditional (nonobserver-based) system.The interested reader can use Experiment 5C
to verify this; the bandwidth of that system is 5, 10, and 20Hz for the cases of
K=25, 50, and 100, respectively, which is about 40% of the observer-based system
bandwidth in all cases.Also,notice that peaking did not increase substantially for any
of the three cases in Figure 5-9.Thus the observer-based system has about 2.5 times
the bandwidth of the traditional system and, in this case, is no more sensitive to
variation in plant gain.
The effects on control-loop stability of sensor variation are shown in Figure 5-10.
System bandwidth remains about constant, but peaking in the closed loop increases
considerably, ranging up to 7.5dB peaking (about 4dB over the nominal value of
3.2dB). This is not the result of observer dynamics in and around the observer
bandwidth, but rather the simple loss of phase margin at low frequencies as could
have been predicted from Figure 5-7.
Figure 5-8. Experiment 5D, designed to investigate the effects of variation on control-loop stability.

5.3 EXPERIMENTALEVALUATION (cid:3) 109
K=50 (Nominal),
BW=25 Hz
K=100 (High),
BW=50 Hz
K=25 (Low),
BW=12 Hz
Figure 5-9. From Experiment 5D, effects of varying Kon control-loop dynamics.
FG =10 (low ) causes 7.5 dB of peaking,
S
about 4 dB over nominal.
FG = 40 (high )reduces
S
peaking slightly.
Figure 5-10. From Experiment 5D, effects on control-loop dynamics of setting FG to 10, 20 (nominal), and 40Hz.
S

| 110 (cid:2) | CHAPTER 5 | THE LUENBERGER OBSERVER               | ANDMODELINACCURACY |     |
| ----------- | --------- | ------------------------------------- | ------------------ | --- |
|             | 5.3.3     | Simulating Inaccurate Sensor Modeling |                    |     |
The  problem  of inaccurate  modeling  is  fundamentally  different  than  that  of
variation.Variation is a problem of the actual plant and sensor that occurs after the
observer has been tuned;inaccurate modeling is a problem of the observer plant and
sensor that occurs before the observer is tuned.When studying variation,it is appro-
priate to vary the actual plant and sensor parameters (such as K and FG ) while the
S
model is running. When studying inaccurate modeling, it is appropriate to vary the
observer parameters. With inaccurate modeling, retuning the observer will mitigate
the effects of the inaccuracy.Retuning after introducing error represents the processes
that would occur in the application. Failing to retune in the simulation causes the
inaccuracy to corrupt the dynamics of the observer loop in a way that would
normally not occur and so is unrealistically negative.
Given that the system will be retuned after error is introduced into the observer
models,there is little need to investigate the inaccuracy of K .The reason is that K
Est Est
can usually be determined experimentally at the time of tuning so that modeling
inaccuracy is not an issue. On the other hand, when FG does not accurately
SEst
represent FG , problems will result. In the following sections, FG will be set to
S SEst
10,20 (nominal),and 40 to investigate the effects of modeling inaccuracy.
|     | 5.3.3.1 | Tuning with Different Values of FG |     |     |
| --- | ------- | ---------------------------------- | --- | --- |
SEst
The tuning procedure of Section 5.3.1 yields the values shown in Table 5-1.The values
of observer-compensation gains vary considerably to adjust for the changes in FG .
SEst
The key point is that for all values of FG , these gains produce observer dynamics
SEst
that are about the same.Finally,notice that the setting for K is accurate even when
Est
the value of FG is off by 2:1. This is further evidence that, for this structure at
SEst
least,the experimental method can be a reliable way of determining K ,even in non-
Est
ideal conditions.
|     | 5.3.3.2 | Effects on the Observed State |     |     |
| --- | ------- | ----------------------------- | --- | --- |
The effect of the sensor model on the accuracy of the observer is studied using Exper-
iment 5C,which is shown in Figure 5-5.The effects of the changes in FG are shown
SEst
in Figure 5-11 where FG is adjusted to 10, 20, and 40Hz. The effects are similar
SEst
|     | TABLE 5-1 | TUNING VALUES FROM THE PROCEDURE OF SECTION 5.3.1 FOR  |     |     |
| --- | --------- | ------------------------------------------------------ | --- | --- |
THREE VALUES OF FG
SEst
|     |     | FG =10 | FG =20 | FG =40 |
| --- | --- | ------ | ------ | ------ |
|     |     | SEst   | SEst   | SEst   |
|     | K   | 0.2    | 0.1    | 0.042  |
DO
|     | K PO | 70   | 45   | 35   |
| --- | ---- | ---- | ---- | ---- |
|     | K    | 9100 | 6400 | 3780 |
IO
|     | K   | 50  | 50  | 50  |
| --- | --- | --- | --- | --- |
Est

5.3 EXPERIMENTALEVALUATION (cid:3) 111
to what was found from changing FG except in the opposite directions.Raising FG
S SEst
(and retuning the observer) is approximately the same as lowering FG . From the
S
analytical discussion in Section 5.2.2,this is as expected since the key issue is the ratio
of G (s) and G (s); lowering one has much the same effect as raising the other.
S SEst
Note that, in Figure 5-11, for each value of FG , the tuning gains were adjusted
SEst
according to Table 5-1.
5.3.3.3 Effects on Control-System Response and Stability
Experiment 5D, as shown in Figure 5-8, is used to study the effect on control-loop
stability of erroneous values of FG . The results are shown in Figure 5-12. Again,
SEst
for each value of FG , the tuning gains were adjusted according to Table 5-1. The
SEst
effects are similar to changing FG (refer to Figure 5-10) except again the directions
S
of the two parameters are opposite. Also, because lowering FG causes the gain of
Est
the feedback signal to peak at and around 30Hz (see Figure 5-11), it induced sig-
nificant peaking in the closed-loop system,forcing reduction of K to 1.2.Without this
P
reduction, the change in FG with the higher loop gains (K =1.5, K =30) induced
Est P I
clear signs of marginal stability. The interested reader can confirm by reviewing the
Observer bandwidth
Low FG (150 Hz)
SEst
Nominal FG
High FG causes S
S produces
gain attenuation
ideal gain
at low frequency.
and phase.
Low FG
S
High FG causes
S
phase lag at low
frequency.
Figure 5-11. From Experiment 5C, effect of FG , including retuning the observer according to Table 5-1.
SEst

112 (cid:2) CHAPTER 5 THE LUENBERGER OBSERVER ANDMODELINACCURACY
High GF causes 5 dB of peaking,
SEst
about 2 dB over nominal.
Low GF reduces low-
SEst
frequency peaking slightly...
…but also creates peaking in the
feedback, which created system
peaking around 30 Hz.
Figure 5-12. From Experiment 5D, effect of varying FG .
SEst
step response in Experiment 5D with the following parameters: FG =10, K =1.5,
Est P
K =30,(from Table 5-1) K =0.2, K =70,K =9100.
I DO PO IO
5.3.3.4 Detecting Errors in Sensor Dynamics with the Observer
The observer can be used to indicate many parameter errors in the models.Recall that
Experiment 5B was used to set the value of K based on the RMS value of the term
Est
E ¥Y with the observer gains set low. This same model can be used to evaluate the
O
accuracy of FG . The output of this model is shown in Figure 5-13 where FG ,
SEst SEst
the estimated sensor bandwidth, is 10Hz (recall that the actual sensor, FG , was 20,
S
the nominal value). The error, E , is visably larger than when FG was correct, as
O SEst
shown in Figure 5-3.The error here can come from only two sources:K and FG .
Est SEst
However, it did not come from K because that value was adjusted to minimize the
Est
RMS meter.Therefore,it must be FG .
SEst
In Experiment 5B,FG can be set empirically by adjusting it until the error signal
SEst
is minimized. (The interested reader can return to Experiment 5B, set FG to 10,
SEst
and see that the only way to minimize E is for both K and FG to be set accu-
O Est SEst
rately.) This provides a process for configuring observers:Ensure that E is nearly zero
O
when observer-compensator gains are low to verify the model is correct. There are

5.3 EXPERIMENTALEVALUATION (cid:3) 113
Figure 5-13. From Experiment 5B, the signal E clearly indicates model errors. FG is 10 here, but the actual
O SEst
sensor has a bandwidth of 20Hz; K is 50, which is equal to K(compare to Figure 5-3).
Est
errors this process will not detect. It indicates only that G ¥G (cid:2)G ¥G , as
P S PEst SEst
opposed to either G (cid:2)G or G (cid:2)G . Also, it does not provide reliable
P PEst S SEst
results in the presence of strong disturbances. Still it can be a useful means of veri-
fying models as it will reveal many types of errors that will be present in practical
systems.
5.3.4 Caution About the Experimental Evaluation
The purpose of Section 5.3 was to demonstrate an experimental approach.
Experimentation allows designers to evaluate complex effects without mathematics.
Designers must be cautious to design experiments that are valid for their machines
or processes. Accurate representation of control-system performance and the
observer dynamics that will be used on the machine or process are necessary to
produce useful results.
This set of experiments has demonstrated at once the strength and weakness of
experimental analysis.On the one hand,experiments allow the designer to investigate
the effects of nearly any combination of factors. On the other hand, the results may
apply only to a narrow set of circumstances.For example,these experiments revealed
a system relatively insensitive to variation. However, had the observer bandwidth
been closer to the control-system bandwidth, the results would have been different.
The designer must be cautious to avoid the overly broad application of experimental
results.

| 114 (cid:2) | CHAPTER 5 | THE LUENBERGER OBSERVER | ANDMODELINACCURACY |
| ----------- | --------- | ----------------------- | ------------------ |
|             | 5.4       | Exercises               |                    |
1. Tune an observer according to the procedure of Section 5.3.1.
|     | A.  | Tune the observer of        | Experiment 5A for 80-Hz bandwidth. |
| --- | --- | --------------------------- | ---------------------------------- |
|     | B.  | Repeat for 60-Hz bandwidth. |                                    |
2. Adjust  K to  match  K as  well  as  possible  using  the  RMS  meter  in
Est
Experiment 5B.
|     | A.  | Using all the default parameter values, | adjust K . |
| --- | --- | --------------------------------------- | ---------- |
Est
B. Intentionally corrupt estimated sensor bandwidth by changing the actual
|     |     | sensor bandwidth to 25. | Repeat A. |
| --- | --- | ----------------------- | --------- |
3. Describe the change in observer performance for a system with varying sensor
dynamics using Experiment 5D.
A. Execute a Bode plot using DSA. Click the DSA button Obs C’Loop to
display observer closed-loop performance. When the plot is displayed,
right-click in the display area of the DSA and click “Save as...”and Red.
Using the Live ConstantFGs,change the actual sensor frequency to 30Hz.
Run a second Bode plot.Compare the two Bode plots.
|     | B.  | Repeat for FGs=14Hz. |     |
| --- | --- | -------------------- | --- |
C. Which error in FGswill likely induce stability problems in the control loop?
4. Evaluate robustness of observer-based system to traditional system.
A. Measure the nominal margins of stability for the observer-based control
loop of Experiment 5D.
B. Build a table showing gain crossover frequency, PM, phase crossover
frequency, and GM for the following values of K: 20, 50 (nominal), and
100.All other parameters should be at their nominal values.
C. Using Experiment 5C, build a table similar to that of problem 4B for a
traditional control loop.
|     | D.  | Compare the two tables and discuss. |     |
| --- | --- | ----------------------------------- | --- |

Chapter 6
The Luenberger Observer
and Disturbances
In this chapter...
• Common sources of disturbance to control systems
• Effects of disturbances on traditional and observer-based systems
• Observed disturbance signals and disturbance decoupling
• Software experiments demonstrating effects of disturbance
This chapter will discuss the sources and effects of system disturbances. Similar
to Chapter 5, the presentation will analyze the Luenberger observer using transfer
functions and confirm results through experimenting with models. In addition, the
principle of disturbance decoupling will be presented. This technique is not unique
to observer-based systems; however, it will be interesting for many readers in this
context because observers serve the method so well.
6.1 Disturbances
Disturbances enter a system between the power converter and the plant,as shown in
Figure 6-1 by the input D(s).Disturbances affect almost every type of control system.
In a furnace, heat disturbances from the atmosphere or from neighboring furnaces
make temperature more difficult to control.Torque disturbances in a motion system
generate velocity and position errors. Load currents can act like a disturbance to
a power supply, pulling the output voltage away from the target. In each case, an
undesired source of power is added to the power converter output and fed to the
plant;the result is that the plant state is disturbed.
115

| 116 (cid:2) | CHAPTER 6 | THE LUENBERGER OBSERVER | ANDDISTURBANCES |     |     |     |
| ----------- | --------- | ----------------------- | --------------- | --- | --- | --- |
D(s)
|     |     | +   |     | C(s) |     |     |
| --- | --- | --- | --- | ---- | --- | --- |
Disturbance
|     |     |     | G (s) |        | G (s) | Y(s) |
| --- | --- | --- | ----- | ------ | ----- | ---- |
|     |     |     | P     | Actual | S     |      |
+
|     |     |     |       | state |        | Actual |
| --- | --- | --- | ----- | ----- | ------ | ------ |
|     |     |     | Plant |       | Sensor |        |
sensor
P (s)
|     | C   |     | Physical system |     |     | output |
| --- | --- | --- | --------------- | --- | --- | ------ |
Plant
Observed
|     | excitation |       |             |     | E (s) |     |
| --- | ---------- | ----- | ----------- | --- | ----- | --- |
|     |            | D (s) | disturbance |     | O     | +   |
|     |            | O     | G           | (s) |       |     |
CO
|     |     |     |     |     | Observer  | _   |
| --- | --- | --- | --- | --- | --------- | --- |
error
Observer
compensator
|     |     | +   |       | C (s)    |        |          |
| --- | --- | --- | ----- | -------- | ------ | -------- |
|     |     |     | G (s) | O        | G (s)  | Y (s)    |
|     |     |     | PEst  |          | SEst   | O        |
|     |     | +   |       | Observed |        |          |
|     |     |     |       | state    |        | Observed |
|     |     |     | Plant |          | Sensor |          |
sensor
Modeled system
output
|     |     | Figure 6-1. The Luenberger observer in a system with disturbances. |     |     |     |     |
| --- | --- | ------------------------------------------------------------------ | --- | --- | --- | --- |
For  observers, disturbances  corrupt  the  observed  state, C (s). Recall  from
O
Chapter 4 that the command signal fed to an observer through two paths: (1) the
command, through a control law, driving the power converter feeds one path of the
observer, and  (2)  the  power  converter  also  drives  the  plant, which  then  drives
the sensor to feed the other path.This combination of prediction and correction gives
the observer many of its qualities because the two paths complement each other.
Unfortunately, disturbances affect only the sensor (correction) path; they do not
benefit from the power converter (prediction) path.
Disturbances cannot be included in the predictor portion of the observer because
they are generally unknown. With few exceptions, disturbances are not measured
other than indirectly,through their effect on the sensed output.There is normally no
way to create the equivalent of a prediction path for them. As a result, disturbances
corrupt C O (s) primarily in frequencies above the bandwidth of the observer, where
the correction path of the observer is not effective. Below the observer bandwidth,
disturbances have less effect on the accuracy of the observed state because the
observer compensator removes their effect.
|     | 6.1.1 | The Observed Disturbance Signal |     |     |     |     |
| --- | ----- | ------------------------------- | --- | --- | --- | --- |
The Luenberger observer shown in Figure 6-1 defines the signal exiting the observer
compensator as the observed disturbance,D (s)[26,27].The signal occupies the same
O
position in the observer as the actual disturbance occupies in the actual system,both
being added immediately after the power converter output. For the case where the

6.1 DISTURBANCES (cid:3) 117
|     | D(s) |     | P   |     |     |     |     |
| --- | ---- | --- | --- | --- | --- | --- | --- |
3
|     | P   | (s) + |     | C(s) |     |     |      |
| --- | --- | ----- | --- | ---- | --- | --- | ---- |
|     |     | C     | G   | (s)  | G   | (s) | Y(s) |
|     |     | +     |     | P    |     | S   |      |
P
|     | P   | 1D  | (s) |     |     |       |     |
| --- | --- | --- | --- | --- | --- | ----- | --- |
|     | 2   | O   |     |     |     |       | +   |
|     |     |     |     | G   | (s) |       |     |
|     |     |     |     | CO  |     | E (s) | _   |
O
L
1
|     |     |     |       | C   | (s) |      |       |
| --- | --- | --- | ----- | --- | --- | ---- | ----- |
|     |     | +   |       | O   |     |      |       |
|     |     |     | G     | (s) | G   | (s)  | Y (s) |
|     |     |     | PEst  |     |     | SEst | O     |
+
|     | Figure 6-2. |     | Luenberger observer drawn for Mason’s signal flow graphs. |     |     |     |     |
| --- | ----------- | --- | --------------------------------------------------------- | --- | --- | --- | --- |
plant and sensor models are exact duplicates of their physical counterparts,the only
errors in the observed state are those due to disturbances.
The observer compensator must observe the disturbance accurately to keep the
observed state accurate. The observer compensator can perform this function well
from DC up to the observer bandwidth.At frequencies above the observer bandwidth,
the output of G (s) no longer follows the actual disturbance well,and the observed
CO
disturbance becomes inaccurate;frequency content in the disturbance well above the
observer bandwidth translates directly to error in the observed state.
The transfer function from the power converter and actual disturbance to the
observed disturbance, D (s), can be formed. This construction considers the sensor
O
as being dependent on the disturbance and the power converter;those two signals are
the independent inputs in this construction. The observer, shown in Figure 6-2, is
redrawn from Figure 6-1 to show the loop and paths for Mason’s signal flow graphs.
There is one loop in this system:
|     |     |     | L =-G | (s)¥G |      | (s)¥G (s). |     |
| --- | --- | --- | ----- | ----- | ---- | ---------- | --- |
|     |     |     | 1     | PEst  | SEst | CO         |     |
There are three forward paths, two from the power converter and one from the
disturbance:
|     |     | P 1 | =P C (s)¥G | P (s)¥G    | S (s)¥G | CO (s)            |     |
| --- | --- | --- | ---------- | ---------- | ------- | ----------------- | --- |
|     |     | P 2 | =-P C      | (s)¥G PEst | (s)¥G   | SEst (s)¥G CO (s) |     |
|     |     | P 3 | =D(s)¥G    | P (s)¥G    | S (s)¥G | CO (s).           |     |
All paths “touch”the single loop so the transfer function is (P +P +P )/(1-L ).
1 2 3 1
|     | P (s)(G | (s)¥G | (s)-G | (s)¥G |      | (s))G (s)+D(s)G | (s)G (s)G (s) |
| --- | ------- | ----- | ----- | ----- | ---- | --------------- | ------------- |
|     | C       | P     | S     | PEst  | SEst | CO              | P S CO        |
D (s)=
| O   |     |     |     | 1+G  | (s)G | (s)G (s) |     |
| --- | --- | --- | --- | ---- | ---- | -------- | --- |
|     |     |     |     | PEst |      | SEst CO  |     |
(6.1)

| 118 (cid:2) | CHAPTER 6 | THE LUENBERGER | OBSERVER ANDDISTURBANCES |     |     |     |
| ----------- | --------- | -------------- | ------------------------ | --- | --- | --- |
For the ideal case where the plant and sensor models are accurate:
|     |     |     | G   | (s)@G (s) |     | (6.2) |
| --- | --- | --- | --- | --------- | --- | ----- |
P PEst
|     |     |     | G   | (s)@G (s). |     | (6.3) |
| --- | --- | --- | --- | ---------- | --- | ----- |
S SEst
Then,Equation 6.1 reduces to:
|     |     |     |            | G (s)G (s)G | (s) |       |
| --- | --- | --- | ---------- | ----------- | --- | ----- |
|     |     |     | D (s)@D(s) | P S CO      | .   | (6.4) |
O
|     |     |     |     | 1+G P (s)G S (s)G CO | (s) |     |
| --- | --- | --- | --- | -------------------- | --- | --- |
The right side of Equation 6.4 can be viewed as the actual disturbance followed
by a low-pass filter with a bandwidth equal to the observer bandwidth (refer to
Equation 4.6 for discussion on the filter term). So, if the models of the sensor and
plant are accurate, the observed disturbance approximates the actual disturbance
below the observer-compensator bandwidth.
|     | 6.1.1.1 | Experiment 6A: Investigating Observed Disturbance |     |     |     |     |
| --- | ------- | ------------------------------------------------- | --- | --- | --- | --- |
The observed-disturbance signal can be investigated using Experiment 6A, which is
shown in Figure 6-3. This system is similar to the system used in Chapters 4 and 5
with a few exceptions:
• The command is set to zero. This experiment is designed to investigate dis-
turbances so that there is little need for a time-varying command signal.
•
The waveform generator Disturbance has been connected to the disturbance
input. This generator is configured to output a square-wave disturbance. This
disturbance is used to trigger the scope.
• A DSA is connected through the disturbance input.The Bode plots generated
in this experiment will be related to the dynamics of disturbance observation.
•
The loop is closed on the actual feedback signal.The gains for the control law
|     | (K  | =0.6,K =12) are taken from Section 5.3.2.1. |     |     |     |     |
| --- | --- | ------------------------------------------- | --- | --- | --- | --- |
|     |     | P I                                         |     |     |     |     |
•
|     | The observed disturbance,D |     | ,is shown in a LiveScope. |     |     |     |
| --- | -------------------------- | --- | ------------------------- | --- | --- | --- |
O
As with earlier experiments, Live Constants are provided to simplify variation of
the plant gain and sensor low-pass filter. The observer-compensator gains are taken
|     | from Chapter 5,producing an observer bandwidth of |     |     |     | 154Hz. |     |
| --- | ------------------------------------------------- | --- | --- | --- | ------ | --- |
The Live Scope display of Experiment 6A shows the observed disturbance, D .
O
The actual disturbance, D, is a step and D looks very much like the step response
O
of a low-pass filter. This confirms Equation 6.4. To investigate the subject further,
Experiment 6A provides a Bode plot of the observed vs actual disturbance.The DSA
can be brought into view by double-clicking on the DSA block; then, click the GO
button on the lower left of the DSA display. The result, as shown in Figure 6-4,

6.1 DISTURBANCES (cid:3) 119
Figure 6-3. Experiment 6Ashowing observed disturbance signal in ideal conditions.
Observer
bandwidth
(154 Hz)
-3 dB
Observed disturbance
is accurate below
the observer bandwidth.
Figure 6-4. Bode plot of observed vs actual disturbance.

120 (cid:2) CHAPTER 6 THE LUENBERGER OBSERVER ANDDISTURBANCES
D /Dwith Kraised (100)
0
Ideal result:
D /Dwith Knominal
0
D /Dwith Klowered (25)
0
D /Dwith Kraised (100) Ideal result:
0
D /Dwith
0
Knominal
D /Dwith K
0
lowered (25)
Figure 6-5. Effect of varying Kon the accuracy of the observed disturbance.
demonstrates a near-equal ((cid:2)0dB) relationship between the two signals up to the
observer bandwidth (154Hz),which is consistent with Equation 6.4.
The close relationship between actual and observed disturbance follows
Equation 6.4 only when the plant and sensor models are accurate.Large inaccuracies
in the models corrupt the observed disturbance, as is indicated by Equation 6.1.
For example, Figure 6-5 shows the effects of K varying from nominal (50) to
both high (100) and low (25) values. The effect on the accuracy of the observed
disturbance is evident, causing as much as 9dB (almost 3 times) error in the middle
frequencies.
6.1.2 Disturbances and the Integral Term in the Observer Compensator
An integral term in the observer compensator is required to eliminate the effects
of steady-state disturbances on the accuracy of the observed-sensor output, Y (s).
O
Without the integral term, an offset will appear in the observed state in proportion
to the DC disturbance.Most control systems are adversely affected by such an offset.
This is why the integral term in the observer compensator is required for most
applications.
The effects of DC disturbances can be seen analytically.The goal is to remove DC
(s=0) error from the observed state (C (s)) and,thus,from the observed-sensor output
O

6.1 DISTURBANCES (cid:3) 121
|     | At DC, D | should equal Dto drive the observer model so E |     |     |     | = 0.  But... |     |
| --- | -------- | ---------------------------------------------- | --- | --- | --- | ------------ | --- |
|     |          | O                                              |     |     |     | O            |     |
D(0) 0
|     | π   |     | +      | C(0) |        |     |      |
| --- | --- | --- | ------ | ---- | ------ | --- | ---- |
|     |     |     | G (0)  | π 0  | G (0)  | π 0 | Y(0) |
|     |     |     | P      |      | S      |     |      |
+
P (0)
|     |     | D (0)=D(0) | 0   |     | E (0)=0 |     |     |
| --- | --- | ---------- | --- | --- | ------- | --- | --- |
| C   |     | O          | π   |     | O       |     | +   |
G (s)
|     |     |     |     | CO    |     |     | _   |
| --- | --- | --- | --- | ----- | --- | --- | --- |
|     |     |     | +   | C (0) |     |     |     |
O
|     |     |     | G (0)  | 0   | G    | (0)  0 | Y (0) |
| --- | --- | --- | ------ | --- | ---- | ------ | ----- |
|     |     |     | PEst   | π   | SEst | π      | O     |
+
|     |     |     | …an integral term is required for G |     |     | (0)to  |     |
| --- | --- | --- | ----------------------------------- | --- | --- | ------ | --- |
CO
|     |     |     | generate a non-zero D |     | when E | (0) = 0. |     |
| --- | --- | --- | --------------------- | --- | ------ | -------- | --- |
O O
Figure 6-6. Evaluating the ideal observer at DC with a disturbance shows why an integral term is needed in the
observer compensator.
(Y (s))  in  the  presence  of DC  disturbances. DC  errors  normally  generate
O
undesirable offsets in the observer output, which will be transferred to the actual
state when the observed state is used as the feedback signal to the main loop. From
Figure 6-1, the observed state is:
|     |     |     | C (s)=(P | (s)+D (s))G | (s)   |      |       |
| --- | --- | --- | -------- | ----------- | ----- | ---- | ----- |
|     |     |     | O        | C O         | PEst  |      |       |
|     |     |     | =(P      | (s)+G (s)¥E | (s))G | (s)  | (6.5) |
|     |     |     |          | C CO        | O     | PEst |       |
Similarly,the actual state is:
|     |     |     | C(s)=(P | (s)+D(s))G | (s). |     | (6.6) |
| --- | --- | --- | ------- | ---------- | ---- | --- | ----- |
|     |     |     |         | C          | P    |     |       |
Assuming that the plant model is accurate so that G (s)(cid:3)G (s), the error induced
|     |     |     |     |     | PEst | P   |     |
| --- | --- | --- | --- | --- | ---- | --- | --- |
by a disturbance is:
|     |     | C   | (s)-C(s)@(G | (s)¥E | (s)-D(s))G | (s). | (6.7) |
| --- | --- | --- | ----------- | ----- | ---------- | ---- | ----- |
|     |     |     | O           | CO    | O          | P    |       |
From Equation 6.7, the only way to eliminate all the DC error in the observed
state is for D(0)=D O (0)=G CO (0)¥E O (0). (This assumes that G P (s) is nonzero at zero
frequency, certainly a reasonable assumption for most practical control systems.)
Figure 6-6 shows the observer evaluated at zero frequency (s=0).From that figure,if
the disturbance, D(s), has a DC component (D(0)π0), then in order to eliminate

122 (cid:2) CHAPTER 6 THE LUENBERGER OBSERVER ANDDISTURBANCES
Figure 6-7. Experiment 6B: Investigating the need for integral gain in the observer compensator.
all DC error, G (s)¥E (s) must have an equal DC component. Thus, in order to
CO O
remove all DC error from the observed state, G (0)¥E (0)π0; however, removing
CO O
all error from the observed-sensor output (E (0)=Y (0)-Y(0)=0) implies E (0) can
O O O
have no DC component. Thus, G (s) must have an integral term; this is the only
CO
means for G (0)¥E (0)π0 while E (0)=0.This is diagrammed in Figure 6-6.
CO O O
The argument presented in Figure 6-6 can be extended to the case where the plant
and sensor models are not ideal. If there exists scaling error in one or both of those
models, the amount of D (s) required to cancel a nonzero D(s) will be proportional
O
to the scaling error(s); in any case, D (s) will be nonzero if D(s) is nonzero. In the
O
absence of an integral term in G (s), any nonzero output of G (0) will require a
CO CO
nonzero E (0). Again, the integral gain is required to remove DC inaccuracy in the
O
observed state.
Experiment 6B, shown in Figure 6-7, demonstrates the need for an integral term
in the observer compensator in the presence of DC error. This experiment is similar
to Experiment 6A with a few exceptions. The observer error, E , is shown on the
O
design.The scale on this display is small,0.02 units per division,because the amount
of DC error induced by the disturbance is small.The disturbance is a low-frequency
square wave;each half-period of the wave is long enough that the DC response of the
observer can be seen. The default settings of the observer compensator include an
integral gain (K =6400).As can be seen in the model,there is no DC component in
IO
the observer error signal,E .This is the desired behavior.
O

6.2 DISTURBANCERESPONSE (cid:3) 123
DC
Error
(a) (b)
Figure 6-8. Results of Experiment 6B, showing that integral gain is required in the observer compensator to
eliminate the effects of DC disturbances from the observer error, (a) K =6400, DC error is not tolerated in E .
IO O
(b) K =0, DC error is tolerated in E .
IO O
The results of Experiment 6B with nonzero and zero integral gain in the observer
compensator are shown in Figure 6-8.In Figure 6-8a,where K =6400 (the value used
IO
throughout most of the previous chapter), the effect of a disturbance pulse on
observer error is transient;after about two divisions (20ms),the error returns to zero.
In Figure 6-8b, the integral gain, K , has been zeroed. The observer error remains
IO
nonzero indefinitely when in the presence of a DC disturbance.This translates to the
equivalent DC error in the observed state in this case because the sensor has unity
gain. Were a system implemented using this observed state for feedback, the
behavior would be to generate drift when DC disturbances were applied. Such drift,
even in small amounts,is normally undesirable.
The reader may have noticed the use of a sample–hold block in Experiment 6B,
immediately to the right of the observer compensator. This is a detail more of
modeling than of observer operation.It was done to improve the display quality of E
O
and has no effect on the operation of the observer. The signal displayed without the
sample–hold showed as the comparison ofa continuous (Y) and a sampled (Y ) signal.
O
During the sample period,the continuous signal continued to vary while the sampled
signal was fixed. This caused the introduction of a high-frequency component in
the error signal. The high frequency aliased down to distort the scope output. The
sample–hold here remedied this by synchronizing the error signal to the main digital
controller sample time.This has no effect on the operation of the observer because the
observer compensator has an implicit sample–hold that performs this same function.
6.2 Disturbance Response
Disturbance response describes to what extent the plant state is perturbed by
disturbances. The transfer function of disturbance response is the ratio of the plant
perturbation to the disturbance that caused that perturbation: C(s)/D(s). The ideal

| 124 (cid:2) | CHAPTER | 6 THE | LUENBERGER | OBSERVER | ANDDISTURBANCES |     |     |     |     |     |
| ----------- | ------- | ----- | ---------- | -------- | --------------- | --- | --- | --- | --- | --- |
disturbance  response  is  0, an  unbounded  negative  number  when  expressed  in
decibels. So, control systems are usually structured to minimize the disturbance
response. At  any  given  frequency  except  DC, disturbances  will  cause  some
perturbation of the plant state.The goal for most control systems is for that effect to
be as small as possible; expressed in decibels, the more negative the disturbance
response,the better.
Disturbance response is sometimes described indirectly through the term stiffness.
Stiffness is the ratio of disturbance to plant perturbation: D(s)/C(s). It is the inverse
of disturbance response; accordingly, the higher the stiffness, the better. The terms
disturbance responseand stiffnessare,of course,equally able to describe the reaction
of a system to a disturbance.The former will normally be used in this book.
The primary way observers allow improved disturbance response is by supporting
higher control-law gains. As discussed in Chapter 4, the reduced phase lag brought
about by using the observed state as the feedback signal increases margins of stabil-
ity so that control-law gains can be raised.Higher gains improve both command and
disturbance response.Disturbance response can also be improved through the use of
disturbance decoupling,a technique that is served particularly well by observer-based
methods.Disturbance decoupling will be covered in Section 6.3.
6.2.1 Transfer Function of Disturbance Response for Traditional Systems
Disturbance response of a control system both with sensor feedback and with
observed-state feedback can be evaluated using transfer functions.The transfer func-
tion of the disturbance response of the traditional system shown in Figure 6-9 is easily
calculated since there is only one loop.
|     |     |     |     | L   | =-G (s)¥G |     | (s)¥G (s)¥G | (s) |     |     |
| --- | --- | --- | --- | --- | --------- | --- | ----------- | --- | --- | --- |
|     |     |     |     |     | 1 C       | PC  | P           | S   |     |     |
There is a single path from D(s) to C(s): G (s). The transfer function is then:
P
|     |     |     | C(s) |     |     |       | 1     |       |       |     |
| --- | --- | --- | ---- | --- | --- | ----- | ----- | ----- | ----- | --- |
|     |     |     |      | =G  | (s) |       |       |       | .     |     |
|     |     |     |      |     | P   |       |       |       | (6.8) |     |
|     |     |     | D(s) |     | 1+G | (s)¥G | (s)¥G | (s)¥G | (s)   |     |
|     |     |     |      |     |     | C     | PC    | P     | S     |     |
R(s)=0
|     |     |     |     |     |     |     | D(s) |     | C(s) |     |
| --- | --- | --- | --- | --- | --- | --- | ---- | --- | ---- | --- |
+
+
|     |     |     | G   | (s) | G (s) |     | G   | (s) | G (s) | Y(s) |
| --- | --- | --- | --- | --- | ----- | --- | --- | --- | ----- | ---- |
S
|     |     | _   | C   |     | PC  |     |     | P   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
+
|     |     |     |     |     | Figure 6-9. | Traditional control system. |     |     |     |     |
| --- | --- | --- | --- | --- | ----------- | --------------------------- | --- | --- | --- | --- |

6.2 DISTURBANCERESPONSE (cid:3) 125
An algebraic manipulation yields
| C(s) |        | G (s)¥G   |     | (s)¥G (s)¥G | (s)  |         |
| ---- | ------ | --------- | --- | ----------- | ---- | ------- |
|      | Ê      | C         | PC  | P           | S ˆ  |         |
| =G   | (s) 1- |           |     |             |      | . (6.9) |
| D(s) | P Ë    | 1+G (s)¥G |     | (s)¥G (s)¥G | (s)¯ |         |
|      |        | C         |     | PC P        | S    |         |
Equation 6.9 can be rewritten in terms of the control-law closed-loop transfer
function,G (s)=Y(s)/R(s):
CL
C(s)
|     |      | =G  | (s)(1-G | (s)). |     | (6.10) |
| --- | ---- | --- | ------- | ----- | --- | ------ |
|     | D(s) | P   |         | CL    |     |        |
Understanding that the ideal disturbance response is 0, the closer that G (s), the
CL
closed-loop response,is to unity,the better the disturbance response.The closed-loop
response will be closest to one at low frequency and,correspondingly,the disturbance
response will be the best.Raising the control-system bandwidth improves disturbance
by keeping G (s) approximately unity for a wider range of frequencies; the dis-
CL
turbance response of Equation 6.10 will be lower over a wider frequency range,
rejecting more of the disturbance input.
Well above the control-loop bandwidth,the closed-loop response will be near zero
and the disturbance response will be G (s); that is, the disturbances will be limited
P
only by the plant gain. At high frequencies, disturbance response is passive as, for
example, when a large capacitor in a power supply prevents high-frequency voltage
ripple or when a large inertia prevents high-frequency velocity ripple.
6.2.2 Transfer Function of Disturbance Response when Using
Observed-State Feedback
The  transfer  function  of the  system  with  observed-state  feedback  is  similar  to
Equation 6.10, although the evaluation is more tedious. Here there are three loops,
as shown in Figure 6-10:
| L -G (s)¥G |       | (s)¥G | (s)   |       |            |     |
| ---------- | ----- | ----- | ----- | ----- | ---------- | --- |
| 1 = C      | PC    | PEst  |       |       |            |     |
| L -G       | (s)¥G | (s)¥G | (s)   |       |            |     |
| 2 = CO     |       | PEst  | SEst  |       |            |     |
| L -G (s)¥G |       | (s)¥G | (s)¥G | (s)¥G | (s)¥G (s). |     |
| 3 = C      | PC    | P     |       | S CO  | PEst       |     |
All loops touch:L and L through G (s),L and L through G (s),and L and L
| 1   | 2   | PEst | 2   | 3   | CO  | 1 3 |
| --- | --- | ---- | --- | --- | --- | --- |
through G C (s). So,
|     |     | D=1-L | -L  | -L . |     |     |
| --- | --- | ----- | --- | ---- | --- | --- |
|     |     |       | 1 2 | 3    |     |     |
There is a single path from the disturbance to the actual state:
|     |     | P =G | (s). |     |     |     |
| --- | --- | ---- | ---- | --- | --- | --- |
|     |     | 1    | P    |     |     |     |

| 126 (cid:2) | CHAPTER | 6 THE LUENBERGER | OBSERVER | ANDDISTURBANCES |     |     |     |     |     |
| ----------- | ------- | ---------------- | -------- | --------------- | --- | --- | --- | --- | --- |
L
R(s)=0
|     |     |     |     | 3   |     |     | D(s) C(s) |     |     |
| --- | --- | --- | --- | --- | --- | --- | --------- | --- | --- |
+
|     |     | G (s) |     |     | G (s) |     | G (s) | G (s) | Y(s) |
| --- | --- | ----- | --- | --- | ----- | --- | ----- | ----- | ---- |
|     |     | C     |     |     | PC    |     | P     | S     |      |
|     |     | _     |     |     |       | +   |       |       |      |
+
+
|     |     |     |     | L   |     |     |     |     | +   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     | 1   |     | +   |     |     |     |
G (s)
CO
_
L
2
|     |     |     |     |     |     | G   | (s)  | G (s) |     |
| --- | --- | --- | --- | --- | --- | --- | ---- | ----- | --- |
|     |     |     |     |     |     |     | PEst | SEst  |     |
Figure 6-10. System with observed-state feedback.
|     | The path P                           | touches only loop L |     |     | (through G  | (s)),so   |             |           |     |
| --- | ------------------------------------ | ------------------- | --- | --- | ----------- | --------- | ----------- | --------- | --- |
|     |                                      | 1                   |     |     | 3           | P         |             |           |     |
|     |                                      |                     |     |     | D =1-L      | -L .      |             |           |     |
|     |                                      |                     |     |     | 1           | 1 2       |             |           |     |
|     |                                      |                     |     |     | (s)(cid:4)G |           | (s)(cid:4)G |           |     |
|     | Assuming accurate observer models (G |                     |     |     |             | (s) and G |             | (s)),then |     |
|     |                                      |                     |     |     | P           | PEst      | S           | SEst      |     |
(cid:4)
|     |     |     |     |     | L -L | ¥L . |     |     |     |
| --- | --- | --- | --- | --- | ---- | ---- | --- | --- | --- |
|     |     |     |     |     | 3    | 1 2  |     |     |     |
This leaves:
|     |     |     |     | C(s) | G (s)(1-L | -L     |     |        |     |
| --- | --- | --- | --- | ---- | --------- | ------ | --- | ------ | --- |
|     |     |     |     |      | P         | 1      | 2 ) |        |     |
|     |     |     |     |      | =         |        | .   | (6.11) |     |
|     |     |     |     | D(s) | (1-L      | -L -LL | )   |        |     |
|     |     |     |     |      |           | 1 2    | 1 2 |        |     |
Two algebraic manipulations provide:
|     |     |     | C(s) |     | Ê          | L ¥L      | ˆ         |        |     |
| --- | --- | --- | ---- | --- | ---------- | --------- | --------- | ------ | --- |
|     |     |     |      | =G  | (s) 1-     | 1         | 2         | (6.12) |     |
|     |     |     |      |     | P Ë        |           | )¯        |        |     |
|     |     |     | D(s) |     |            | (1-L 1 -L | 2 -LL 1 2 |        |     |
|     |     |     | C(s) |     |            | -L        | -L        |        |     |
|     |     |     |      | ªG  | (s) Ê 1- Ê | 1 ˆÊ      | 2 ˆˆ .    | (6.13) |     |
P
|     |     |     | D(s) |     | Ë Ë1-L | ¯Ë1-L | ¯¯  |     |     |
| --- | --- | --- | ---- | --- | ------ | ----- | --- | --- | --- |
1 2
The term -L/(1-L ) is the closed-loop transfer function of the control system.1
|     |     | 1   | 1   |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Similarly, the term -L /(1-L ) is the closed-loop transfer function of the observer.
2 2
Substituting these equations into Equation 6.13 provides a result similar in form to
Equation 6.10.
1Note that unlike the traditional system,the closed-loop transfer function of the observer-based system
does not include the sensor transfer function.That is because the effect ofthe sensor is removed when the
observer models are accurate.

6.2 DISTURBANCERESPONSE (cid:3) 127
C(s)
ªG (s)(1-G (s)¥G (s)) (6.14)
D(s) P CL OLPF
The disturbance response of the observed-state feedback depends on the
control-loop transfer function just as it did in the traditional system as shown in
Equation 6.10.As discussed in Chapter 4,the observer allows the control gains (G (s))
C
to be raised by virtue of reducing phase lag in the loop. This is the primary way in
which observers improve disturbance response.
Equation 6.14 also shows that the observer bandwidth can degrade disturbance
response.Notice that the form of Equation 6.14 is such that even if the control-loop
bandwidth is high (so that G (s) remains near unity for a wider frequency span),the
C
observer bandwidth can reduce the disturbance response.This is not a concern if the
observer bandwidth is substantially higher than the control-loop bandwidth, as it
normally is.
One misconception about observers is that the observer bandwidth can be set
arbitrarily low. This technique is sometimes suggested to reduce noise susceptibility
(as will be discussed in Chapter 7, noise susceptibility is indeed reduced by reducing
observer bandwidth). The reasoning comes from the correct notion that the phase
lag caused by the sensor can be removed independently of the observer bandwidth.
In that sense, control-law gains can be raised, even if the observer bandwidth is low.
In fact, it is possible to lower the observer bandwidth below the control-loop band-
width.However,the disturbance response is limited by the lower ofthe observer band-
width and the control-loop bandwidth,as demonstrated in Equation 6.14.When the
control-loop bandwidth is substantially higher than the observer bandwidth, raising
control-law gains higher will not benefit the disturbance response. In such cases,
higher gains benefit only the command response. This is of questionable benefit in
realistic systems,since during the time before the observer loop settles,the command
response will only be accurate in the absence of disturbances or model errors.
6.2.3 Improved Disturbance Response Through Control-Law Gains
The primary benefit of Luenberger observers in improving disturbance response is
indirect; through the elimination of phase lag from the sensor, the stability margins
of the loop are improved.Those improved margins of stability allow increased gains
in the main control law,increasing control-system bandwidth.That higher bandwidth
improves disturbance response as shown in Equation 6.14.
The benefit of higher control-law gains in improving disturbance response is
demonstrated in Experiment 6C,which is shown in Figure 6-11.This model is similar
to Experiment 6B,except the actual state is shown in a Live Scope.Also,the observed
state is used to close the feedback loop.This allows the control-law gains to be raised
from (K =0.6, K =12) to (K =1.5,K =30) as was discussed in Chapter 4.
P I P I
The results of Experiment 6C are shown in Figure 6-12. The improvement in
disturbance response is evident.The magnitude of the perturbation is increased about

128 (cid:2) CHAPTER 6 THE LUENBERGER OBSERVER ANDDISTURBANCES
Figure 6-11. Experiment 6C: Investigating disturbance response and control-law gains.
2.5 times when the gains are reduced by that same factor. In addition, the recovery
time increases from 0.1s (1 division) by a factor of, again, 2.5 when the lower gains
are used.This behavior is not specific to observers. Most techniques that allow for a
substantial increase of control-law gains without compromising stability margins
would produce the equivalent enhancement in disturbance response.
(a) (b)
Figure 6-12. Results of Experiment 6C: (a) the observer supports high gains (K =1.5, K=30) that provide
P I
superior disturbance response compared to (b) the lower gains of (K =0.6, K=12) the tradition system.
P I

|     |                        |     |     |     |     | 6.3 | DISTURBANCE | DECOUPLING | (cid:3) 129 |
| --- | ---------------------- | --- | --- | --- | --- | --- | ----------- | ---------- | ----------- |
| 6.3 | Disturbance Decoupling |     |     |     |     |     |             |            |             |
Disturbance decoupling[11,26,27,39] is a method of improving disturbance response.
As discussed above, raising control-law gains is effective at improving disturbance
response. However, those gains can be raised only so high because of stability
constraints.With disturbance decoupling,disturbance response can often be improved
beyond what is possible by raising loop gains.
Disturbance decoupling starts by determining the approximate disturbance. The
disturbance signals can be derived from measurement or from model-based methods
such as an observer. The disturbance is then decoupled from the system by subtract-
ing from the power converter command an amount equal to the disturbance. The
disturbance  is  then  reacted  to  as  quickly  as  the  measurement  (or  observation)
allows,within the ability of the power converter.With decoupling,the system reaction
to disturbances can be considerably faster than relying wholly on the control law.
Figure 6-13 shows the general form of disturbance decoupling.The actual distur-
bance is summed with the output of the power converter.Simultaneously,the distur-
bance is measured or observed.In practical systems,the disturbance can be measured
only imperfectly. The imperfection is represented in Figure 6-13 as being measured
to a specified accuracy and with a limited bandwidth, as indicated by G (s). (For an
D
ideal measurement,G (s)=1.) In traditional (nonobserver) systems,the accuracy and
D
speed of the measurement depends on the quality of the sensor. The disturbance-
decoupling path is scaled by a gain, K . This allows, among other things, the
DD
| decoupling to be turned on (K |     |     | =1) and off | (K  | =0). |     |     |     |     |
| ----------------------------- | --- | --- | ----------- | --- | ---- | --- | --- | --- | --- |
|                               |     |     | DD          | DD  |      |     |     |     |     |
Direct  measurement  of disturbances  is  impractical  for  most  control  systems
because of the increased cost and reduced reliability brought about by the addition
of a sensor. As an alternative to direct measurement, disturbances can be observed
[20, 23, 26, 32, 38] as shown in Figure 6-14. The observed signal, D (s), can be
O
accurate and fast if the observer bandwidth is high and the sensor and plant models
are accurate,as indicated by Equations 6.2–6.4.
If the observer models are accurate,the observer provides the observed disturbance
as a filtered version of the actual disturbance, D (s)=D(s)¥G (s), where G (s)
|     |     |     |     | O   |     | DLPF |     | DLPF |     |
| --- | --- | --- | --- | --- | --- | ---- | --- | ---- | --- |
is defined as the filtering term in Equation 6.4. In other words, the transfer function
| of T     | (s) in Figure 6-14 is assumed to simply be G |     |     |     |     | (s). |     |     |     |
| -------- | -------------------------------------------- | --- | --- | --- | --- | ---- | --- | --- | --- |
| OBSERVER |                                              |     |     |     |     | DLPF |     |     |     |
Disturbance decoupling
|     |     | K   | G (s) |     |     |     | path |     |     |
| --- | --- | --- | ----- | --- | --- | --- | ---- | --- | --- |
D(s)
| R(s) |     | DD  | D   |     |     |     |     |     |     |
| ---- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
_
| +   |       |              |                         | +   |     |     |       |      |     |
| --- | ----- | ------------ | ----------------------- | --- | --- | --- | ----- | ---- | --- |
|     | G (s) |              | G (s)                   |     | G   | (s) | G (s) | Y(s) |     |
| _   | C     |              | PC                      |     |     | P   | S     |      |     |
|     | +     |              |                         | +   |     |     |       |      |     |
|     |       | Figure 6-13. | Disturbance decoupling. |     |     |     |       |      |     |

| 130 (cid:2) | CHAPTER | 6 THE | LUENBERGER OBSERVER | ANDDISTURBANCES |       |      |      |     |
| ----------- | ------- | ----- | ------------------- | --------------- | ----- | ---- | ---- | --- |
|             |         |       | D (s)               | T               | (s) ª |      |      |     |
|             |         |       | O                   | OB SE R V E     | R     | D(s) |      |     |
|             | R(s)    |       |                     | G               | (s)   |      |      |     |
|             |         |       |                     | D L P           | F     |      | C(s) |     |
_
|     | +   |     |                                                                |       | +   |       |       |      |
| --- | --- | --- | -------------------------------------------------------------- | ----- | --- | ----- | ----- | ---- |
|     |     | G   | (s)                                                            | G (s) |     | G (s) | G (s) | Y(s) |
|     | _   | C   |                                                                | PC    |     | P     | S     |      |
|     |     |     | +                                                              |       | +   |       |       |      |
|     |     |     | Figure 6-14. Observer-based disturbance decoupling, assuming K |       |     |       | =1.   |      |
DD
The transfer function of the disturbance response of the system of Figure 6-14 can
be derived using Mason’s signal flow graphs and is shown in Equation 6.15. Upon
inspection of Equation 6.15,if the disturbance measurement and power converter are
ideal (unity),the response to the disturbance would be perfect:zero.This can be seen
by assuming G (s) and G (s) were both unity and noticing that the numerator
|     |     |     | DLPF | PC  |     |     |     |     |
| --- | --- | --- | ---- | --- | --- | --- | --- | --- |
becomes zero,the ideal response to a disturbance.
|     |     |     |      | C(s) | (1-G (s)G     | (s))G (s) |        |     |
| --- | --- | --- | ---- | ---- | ------------- | --------- | ------ | --- |
|     |     |     | T    | (s)= | DLPF          | PC P      |        |     |
|     |     |     | DIST | =    |               |           | (6.15) |     |
|     |     |     |      | D(s) | 1+G (s)G (s)G | (s)G (s)  |        |     |
|     |     |     |      |      | C PC          | P S       |        |     |
Of course, the assumption of an unlimited bandwidth observer and power con-
verter is unrealistic.However,Equation 6.15 does demonstrate that for the frequency
range below both the power converter and the observer bandwidths, where those
transfer functions are approximately unity,disturbance decoupling provides near ideal
disturbance response.
|     | 6.3.1 | Experiment 6D: ADisturbance-Decoupled System |     |     |     |     |     |     |
| --- | ----- | -------------------------------------------- | --- | --- | --- | --- | --- | --- |
Experiment 6D,shown in Figure 6-15,is a disturbance-decoupled system.This model
is almost identical to Experiment 6C,the sole exception being the subtraction of the
K -scaled observed disturbance, D , from the power converter input. Note that the
|     | DD  |     |     | O   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
two VisualModelQextenders named D are used to connect the observed disturbance
O
from the observer compensator to the scaling gain,K ,avoiding confusion that might
DD
be caused by crossing lines in the block diagram.
The results of Experiment 6D,as shown in Figure 6-16,demonstrate the improve-
ment available from disturbance decoupling.Figure 6-16a shows the system with K
DD
set to zero to disable disturbance decoupling;Figure 6-16b shows the results with dis-
turbances decoupled, which is done by setting K to unity and zeroing the control-
DD
law integrator (the zeroing of the integral will be discussed shortly).The improvement
in disturbance response is dramatic: the maximum excursion is cut by more than a
factor of two, and the duration of the perturbation is cut by a factor of four. Note
that both figures depict the system with the same control-law proportional gain,
K =1.5.
P

6.3 DISTURBANCE DECOUPLING (cid:3) 131
Figure 6-15. Experiment 6D: An observer-based disturbance-decoupled system.
The disturbance response with and without decoupling can be compared using
Bode plots.Using Experiment 6D,the Bode plots of disturbance response (C(s)/D(s))
are shown with and without disturbance decoupling (see Figure 6-17). At low
frequencies,the improvement is 20dB or a factor of 10.Such an improvement could
not be achieved by simply increasing the control-law gains.
(a) (b)
Figure 6-16. From Experiment 6D: Disturbance response (a) with a traditional control law (K =0, K=30,
DD I
K =1.5) and (b) with disturbance decoupling (K =1, K=0, K =1.5).
p DD I p

132 (cid:2) CHAPTER 6 THE LUENBERGER OBSERVER ANDDISTURBANCES
Disturbance decoupling provides significant
improvement in disturbance response below
the observer and power converter bandwidths.
Power converter
bandwidth (50 Hz)
Without decoupling
With decoupling
Observer
bandwidth (150 Hz)
Figure 6-17. From Experiment 6D: Bode plot showing dramatic improvement in disturbance response offered
by disturbance decoupling. Plots for two cases: without (K =0, K=30) and with (K =1, K=0) decoupling;
DD I DD I
K =1.5 in both cases.
P
6.3.2 Disturbance Decoupling Removes Need for Control-Law Integrator
The control law that produced Figure 6-16b is shown in Figure 6-18. Notice that
the control-law integrator has been removed (the control law is simply K ). With
P
disturbance decoupling, the control-law integrator is no longer necessary to provide
complete rejection of DC disturbances.This can be seen in the transfer function from
R(s) to C(s),which can be derived using Mason’s signal flow graphs.
The development that will be performed in this section is somewhat tedious, even
when using Mason’s signal flow graphs (it can be much more tedious when using
competing methods).Readers are encouraged to follow this development as it demon-
strates one way to derive and manipulate transfer functions from the block diagrams
typical of observer-based systems.
Recall from Section 3.1.4.1 the procedure for Mason’s signal flow graphs:
6.3.2.1 Step 1: Find the Loops
The first step is to locate the loops.Figure 6-19 shows Figure 6-18 marked with three
loops:L ,L,and L.There are two other loops which are not shown in Figure 6-19:
1 2 4
L and L. Loop L is a figure-eight curve that flows through the power converter,
3 5 3

|      |     |     |     |      |       |     |      | 6.3 | DISTURBANCE | DECOUPLING | (cid:3) 133 |
| ---- | --- | --- | --- | ---- | ----- | --- | ---- | --- | ----------- | ---------- | ----------- |
| R(s) |     |     |     | D(s) |       |     |      |     | N(s)        |            |             |
| +    |     | +   |     | P    | (s) + |     | C(s) |     | +           | +          |             |
C
|     | K   |     | G   | (s) |     | G (s) |     | G (s) |      | Z(s) |     |
| --- | --- | --- | --- | --- | --- | ----- | --- | ----- | ---- | ---- | --- |
| _   |     | P _ | PC  |     |     | P     |     | S     |      |      |     |
|     |     |     |     |     | +   |       |     |       | Y(s) |      |     |
+
|     |     |     | K   |     |     |       | G   | (s) |       |     |     |
| --- | --- | --- | --- | --- | --- | ----- | --- | --- | ----- | --- | --- |
|     |     |     | DD  |     |     |       | CO  |     |       |     |     |
|     |     |     |     |     |     | D (s) |     |     | E (s) | _   |     |
Disturbance
|     |     |     |     |     |     | O   |     |     | O   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
decoupling
|     | path eliminates   |     |     |     |     |       | C (s) |      |     |       |     |
| --- | ----------------- | --- | --- | --- | --- | ----- | ----- | ---- | --- | ----- | --- |
|     |                   |     |     |     | +   |       | O     |      |     |       |     |
|     | need for control- |     |     |     |     | G (s) |       | G    | (s) | Y (s) |     |
|     |                   |     |     |     |     | PEst  |       | SEst |     | O     |     |
|     | law integrator    |     |     |     | +   |       |       |      |     |       |     |
Figure 6-18. When disturbance decoupling is used (K =1), the control-law integral is no longer necessary.
DD
drops to flow through the observer loop,and then returns through K .Loop L starts
|     |     |     |     |     |     |     |     |     | DD  | 5   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
at the control law, flows through the power converter, plant, and sensor, drops into
the observer compensator,then flows through the estimated plant,and returns to the
control law.Note that all loops are negative except loop L ,which is positive since it
3
passes through two subtractions.
The five loops are:
| L   | -G (s)¥G |       | (s)¥G | (s)   |       |     |     |     |      |     |     |
| --- | -------- | ----- | ----- | ----- | ----- | --- | --- | --- | ---- | --- | --- |
| 1   | PEst     | SEst  |       | CO    |       |     |     |     |      |     |     |
| L   | -G (s)¥G | (s)¥G | (s)¥G |       | (s)¥K |     |     |     |      |     |     |
| 2   | PC       | P     | S     | CO    |       | DD  |     |     |      |     |     |
| L   | +G (s)¥G |       | (s)¥G | (s)¥G | (s)¥K |     |     |     |      |     |     |
| 3   | PC       | PEst  | SEst  |       | CO    | DD  |     |     |      |     |     |
|     |          |       |       | D(s)  |       | P   |     |     | N(s) |     |     |
R(s) P
|     | 1   |     |     |     |     | 2   |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
P (s)
| +   |     | +   |     |       | +   |       | C(s) |       | +    | +    |     |
| --- | --- | --- | --- | ----- | --- | ----- | ---- | ----- | ---- | ---- | --- |
|     | K   |     | G   | (s) C |     | G (s) |      | G (s) |      | Z(s) |     |
| _   |     | P _ | PC  |       | +   | P     |      | S     |      |      |     |
|     |     |     |     |       | L   |       |      |       | Y(s) |      |     |
2
+
|     |     |     | K   |     |     |       | G   | (s) |       |     |     |
| --- | --- | --- | --- | --- | --- | ----- | --- | --- | ----- | --- | --- |
|     |     |     | DD  |     |     |       | CO  |     |       |     |     |
|     |     |     |     |     |     | D (s) |     |     | E (s) | _   |     |
|     |     |     |     |     |     | O     |     |     | O     |     |     |
L
|     |     |     |     | L   |     |     |     | 1   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
4
|     |     |     |     |     | +   |     | C (s) |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | ----- | --- | --- | --- | --- |
O
|     |     |     |     |     |     | G (s) |     | G    | (s) | Y (s) |     |
| --- | --- | --- | --- | --- | --- | ----- | --- | ---- | --- | ----- | --- |
|     |     |     |     |     |     | PEst  |     | SEst |     | O     |     |
+
|     |     | Figure 6-19. |     | Figure 6-18 marked for Mason’s signal flow graphs. |     |     |     |     |     |     |     |
| --- | --- | ------------ | --- | -------------------------------------------------- | --- | --- | --- | --- | --- | --- | --- |

| 134 (cid:2) | CHAPTER | 6 THE   | LUENBERGER                                       | OBSERVER | ANDDISTURBANCES |       |      |     |     |     |
| ----------- | ------- | ------- | ------------------------------------------------ | -------- | --------------- | ----- | ---- | --- | --- | --- |
|             | L       | -K ¥G   | (s)¥G                                            | (s)      |                 |       |      |     |     |     |
|             | 4       | P       | PC                                               | PEst     |                 |       |      |     |     |     |
|             | L       | -K ¥G   | (s)¥G                                            | (s)¥G    | (s)¥G           | (s)¥G | (s). |     |     |     |
|             | 5       | P       | PC                                               | P        | S               | CO    | PEst |     |     |     |
|             |         | 6.3.2.2 | Step 2: Find the Determinant of the Control Loop |          |                 |       |      |     |     |     |
All loops share at least one node. L shares at least one node with L , L, and L
|     |     |     |     |     |     | 1   |     |     | 2 3 | 5   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
because all pass through G (s); L shares at least one node with L because both
|     |     |     |     |     | CO  | 1   |     |     | 4   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
share G (s). Since L through L all share G (s), they must all share at least one
|     |                                      | PEst    |                                    | 2   |       | 5                  | PC    |      |     |     |
| --- | ------------------------------------ | ------- | ---------------------------------- | --- | ----- | ------------------ | ----- | ---- | --- | --- |
|     | node.Thus,the determinant is made of |         |                                    |     |       | only single loops: |       |      |     |     |
|     |                                      |         |                                    |     | D=1-L | -L                 | -L -L | -L . |     |     |
|     |                                      |         |                                    |     |       | 1                  | 2 3   | 4 5  |     |     |
|     |                                      | 6.3.2.3 | Step 3: Find All the Forward Paths |     |       |                    |       |      |     |     |
There are two paths of concern: P from the command, R(s), and P from the
|     |     |     |     |     |     | 1   |     |     | 2   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
disturbance,D(s):
|     |     |         |                                                          |     | P =R(s)¥K |      | ¥G (s)¥G | (s) |     |     |
| --- | --- | ------- | -------------------------------------------------------- | --- | --------- | ---- | -------- | --- | --- | --- |
|     |     |         |                                                          |     | 1         | P    | PC       | P   |     |     |
|     |     |         |                                                          |     | P =D(s)¥G | (s). |          |     |     |     |
|     |     |         |                                                          |     | 2         | P    |          |     |     |     |
|     |     | 6.3.2.4 | Step 4: Find the Cofactors for Each of the Forward Paths |     |           |      |          |     |     |     |
The cofactor for each forward path is the determinant less the loops that share at least
one node with that path.P flows through G (s) and so shares at least one node with
|     |     |     |     |     | 1   |     | PC  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
all loops except L.P flows through G (s) and so shares at least one node with loops
|     |     |     |     | 1 2 |     | P   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
L and L.
2 5
D =1-L
|     |     |         |                                     |     |     | 1 1  |       |     |     |     |
| --- | --- | ------- | ----------------------------------- | --- | --- | ---- | ----- | --- | --- | --- |
|     |     |         |                                     |     | D   | =1-L | -L -L |     |     |     |
|     |     |         |                                     |     |     | 2 1  | 3 4   |     |     |     |
|     |     | 6.3.2.5 | Step 5: Build the Transfer Function |     |     |      |       |     |     |     |
The transfer function is then:
|     |     |     |     |     |       | P ¥D | +P ¥D |     |     |     |
| --- | --- | --- | --- | --- | ----- | ---- | ----- | --- | --- | --- |
|     |     |     |     |     | C(s)= | 1    | 1 2   | 2.  |     |     |
D
A few assumptions simplify the transfer function considerably. First consider
that the need for an integrator is best demonstrated at zero frequency.A control-law

|     |     |     |     |     |     | 6.3 | DISTURBANCE | DECOUPLING | (cid:3) 135 |
| --- | --- | --- | --- | --- | --- | --- | ----------- | ---------- | ----------- |
integrator would not normally be needed if a proportional control law forced C(s) to
follow R(s) perfectly at zero frequency, even in the presence of a DC disturbance.
At DC,it can be assumed that the power converter is nearly ideal (G (s)(cid:4)1) as are
PC
(s)(cid:4)G (s)(cid:4)1).Finally,assume the system is con-
the sensor and sensor model (G
S SEst
figured for disturbance decoupling, so that K =1. So, at zero frequency, L cancels
|                |     |     |       | DD    |     |     |     | 1   |     |
| -------------- | --- | --- | ----- | ----- | --- | --- | --- | --- | --- |
| L 3 in Dand D: | 2   |     |       |       |     |     |     |     |     |
|                |     |     | D=1-L | -L -L |     |     |     |     |     |
|                |     |     |       | 2 4   | 5   |     |     |     |     |
D =1-L .
2 4
Filling in the terms for C(s) from above,
|      | R(s)¥K | ¥G (s)¥(1+G |       | (s)G (s))+D(s)¥G |        | (s)¥(1+K |          | G (s))   |     |
| ---- | ------ | ----------- | ----- | ---------------- | ------ | -------- | -------- | -------- | --- |
| C(s) | =      | P P         |       | CO PEst          |        | P        |          | P PEst . |     |
| sÆ0  |        | 1+G (s)G    | (s)+K | G (s)+K          | G      | (s)G     | (s)G (s) |          |     |
|      |        | P           | CO    | P PEst           | P PEst | CO       | P        |          |     |
(6.16)
Now, assume the observer compensator has an integral term. Also, assume the
plant and its model are either integrating or nearly integrating,as is the most common
case in control systems. So, the functions G (s), G (s), and G (s) all become very
|     |     |     |     | CO  | P   | PEst |     |     |     |
| --- | --- | --- | --- | --- | --- | ---- | --- | --- | --- |
large as s approaches zero. Divide every term in Equation 6.16 by G (s)¥G (s)¥
|     |     |     |     |     |     |     |     | CO P |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ---- | --- |
G PEst (s). Now, to  approximate  the  behavior  of Equation  6.16  at  s=0, remove
every term in Equation 6.16 that has one or more of these three functions in the
denominator since those terms will become vanishingly small as sapproaches 0.The
disturbance term will be cancelled in this process. This yields C(s)=R(s) at DC,
the ideal result,showing that an integral in the control law is not necessary.
If the  process  is  repeated  for  non-integrating  plants, those  systems  where
neither G (s) nor G (s) becomes large without bound as s approaches 0, it leaves
|     | P   | PEst |     |     |     |     |     |     |     |
| --- | --- | ---- | --- | --- | --- | --- | --- | --- | --- |
Equation 6.17 at zero frequency:
|     |     |      |     | K ¥G    | (s)   |     |     |        |     |
| --- | --- | ---- | --- | ------- | ----- | --- | --- | ------ | --- |
|     |     | C(s) |     | =R(s) P | PEst  | .   |     |        |     |
|     |     |      | sÆ0 |         |       |     |     | (6.17) |     |
|     |     |      |     | 1+K     | G (s) |     |     |        |     |
|     |     |      |     | P       | PEst  |     |     |        |     |
So,at DC,the system follows the command,independent of the disturbance and very
accurately as long as K ¥G (0)>>1. If G (s) is a fully integrating model, the
|     |     | P PEst |     | PEst |     |     |     |     |     |
| --- | --- | ------ | --- | ---- | --- | --- | --- | --- | --- |
DC response of C(s) will be exactly C(s).Notice that there is no requirement that the
plant model be particularly accurate as is evidenced by the fact that nowhere in this
development was it required for G (s)(cid:4)G (s); in fact, the actual plant itself need
P PEst
not even be a true integrator to attain total DC accuracy,so long as the model plant
is an integrator.In many cases,plants are not true integrators at very low frequencies
because of losses.For example,capacitors have small leakage terms and temperature
baths have thermal losses.Both cases are examples of plants that integrate only above
some low frequency.However,an integrating model can often be used to simulate such
a plant.As long as an integrating model provides a reasonable representation of the

136 (cid:2) CHAPTER 6 THE LUENBERGER OBSERVER ANDDISTURBANCES
plant, it can be used with disturbance decoupling to eliminate the need for an
integrator in the control law.
The key step to take note of was where L cancelled L in D. Without this
1 3 2
cancellation, the disturbance term in Equation 6.16 would have a G (s) term so it
CO
would not have been overwhelmed by the command term at zero frequency.
The reader is encouraged to return to the development and disable disturbance
decoupling by setting K =0. In this case, the DC response for the nondecoupled
DD
system without an integral in the control law is:
D(s)
C(s) =R(s)+ . (6.18)
sÆ0 K
P
Without disturbances, the system will follow a DC command perfectly, even
without an integrator in the control law.However,the disturbance corrupts the output
as is shown in Equation 6.18.A larger proportional gain reduces,but does not elim-
inate, the error. The most common way to remove all error in the nondisturbance-
decoupled system is for the proportional control law, K in Equation 6.18, to be
P
replaced with an integrating control law, K +K /s, as shown in Equation 6.19.
P I
The magnitude of such a control law will grow without bound at zero frequency,
forcing the disturbance term to vanish from the output. This is the primary reason
integrating control laws are so popular in traditional control systems.
D(s)
C(s) =R(s)+ =R(s) (6.19)
sÆ0 K +K s
P I
6.3.3 Dynamic Improvement of Disturbance Response
A system employing disturbance decoupling rejects disturbances largely independent
of the control law. This is because the primary path to reject disturbances, which is
through K , does not pass through the control law; it proceeds directly from the
DD
observer to the power converter. Here, the bandwidths of the observer and power
converters are the primary dynamic limit to disturbance response, as indicated in
Equation 6.15. In traditional control systems, the control law is the primary source
of disturbance rejection and the control-loop bandwidth, which is usually much
lower than the observer or power converter bandwidths.
Experiment 6E,shown in Figure 6-20,will be used to demonstrate how the power
converter bandwidth limits disturbance response in disturbance-decoupled systems.
This experiment is similar to Experiment 6D, except the bandwidth of the power
converter (G ) is adjusted with the Live Constant F , both of which are above and
PC PC
left of the center of the figure.
The results of Experiment 6E are shown in Figure 6-21.When the power converter
bandwidth is raised from 50 (Figure 6-21a) to 100Hz (Figure 6-21b), disturbance
response improves dramatically.This is consistent with Equation 6.15.Note that the

|     |     | 6.3 DISTURBANCE | DECOUPLING | (cid:3) 137 |
| --- | --- | --------------- | ---------- | ----------- |
Figure 6-20. Experiment 6E: Investigate the effect of power converter frequency on disturbance response in a
disturbance-decoupled system.
| (a) | (b) | (c) |     |     |
| --- | --- | --- | --- | --- |
Figure 6-21. From Experiment 6E: Disturbance response with observer-based disturbance decoupling using
(a) low (50Hz), (b) high (100Hz), and (c) very high (200Hz) bandwidth power converters.

138 (cid:2) CHAPTER 6 THE LUENBERGER OBSERVER ANDDISTURBANCES
observer bandwidth is about 160Hz (from Section 5.3.1), so the power converter, in
both cases,is the lower of the two and thus the primary barrier.Accordingly,raising
this limit improves disturbance response significantly.Note that in the case where dis-
turbance decoupling is not used,increasing the power converter bandwidth does not
directly improve disturbance response to a significant extent.(It can reduce phase lag
in the loop,thus allowing higher servo gains,which do improve disturbance response.)
The interested reader is invited to confirm this with Experiment 6E using these
steps:
• Run Experiment 6E
• Turn disturbance decoupling off (set K =0,K =30)
DD I
• Adjust F up from 50Hz and observe that disturbance response does not
PC
improve significantly.Adjusting it down will affect response because the addi-
tional phase lag will cause instability in the control loop.
When the power converter bandwidth is raised further, the disturbance response
improves again. The power converter bandwidth of 200Hz (Figure 6-21c) provides
the best decoupling of the three cases in Figure 6-21.However,the benefits of raising
the bandwidth are diminishing because the observer bandwidth, which is about
160Hz, is now the primary limitation on disturbance response. Accordingly, raising
the power converter bandwidth from 200 to 500Hz produces almost no benefit,as the
reader will observe by executing Experiment 6E. At this point, the observer band-
width is the primary limit in Equation 6.15 and substantial improvement in
disturbance response can only be achieved by raising that barrier.
6.4 Exercises
1. Compare bandwidth of observed disturbance (D /D) and bandwidth of
O
observer. Measure the bandwidth of the observer using Experiment 5A. Use
default values for all parameters.
A. What is the bandwidth of the observed disturbance? (Hint: Use the DSA
in Experiment 6A.)
B. What is the bandwidth of the observer itself? (Hint: Use the DSA in
Experiment 5A.)
C. Repeat A and B for the observer tuning values K =0.06, K =25, and
DO PO
K =1400.
IO
D. Repeat A and B for the observer tuning values K =0.04, K =14, and
DO PO
K =700.
IO
E. Compare the observer bandwidth to the observed-disturbance bandwidth.
Discuss the implications of Equations 6.4 and 4.6.
F. Repeat problem 1D with K set to 20 (leave K set to 50). Compare and
Est
comment.

6.4 EXERCISES (cid:3) 139
2. Find the relationship between the DC error of disturbance in the absence
of an integral term in the compensator and the gain K . Use Experiment
PO
6B. Set K =0.0. Note that while the Live Scope gives approximate read-
IO
ings, a more accurate measure of error can be obtained with the main scope
display,which will come into view after compiling the model,double-clicking
on the main scope block (left), and turning on a single cursor (bottom of
scope).
A. Measure the error with the default value of K (45).
PO
B. Repeat with K =20,50,and 100.
PO
C. What is the relationship between the amount of error and K ?
PO
3. Evaluate disturbance response in the frequency and time domains for
three cases: the low gains of the traditional system, the high gains of the
observer-based system, and the disturbance-decoupled system. Use Experi-
ment 6D.
A. Run a Bode plot for the traditional system (K =0.6,K =12,and K =0.0).
P I DD
Save this plot as black. Repeat for the higher gains possible with an
observer-based system (K =1.5, K =30, and K =0.0). Save this plot as
P I DD
red. Finally, repeat for the disturbance-decoupled system (K =1.5, K =0,
P I
and K =1.0).
DD
B. Measure the disturbance response (gain) for all three cases at 3Hz. (Use
the single cursor with the cursor set at 3Hz;use radio buttons in the cursor
display box to set which waveform is measured in the DSA cursor window.)
C. How much does the disturbance response improve due to increased
loop gains allowed by the observer, according to the first two measure-
ments in part A?
D. How much does the disturbance response improve due to disturbance
decoupling,according to second two measurements in part A?
E. Make similar measurements to part B using the time domain. Set the
waveform generator to sine wave (double-click on WaveGen block after
compiling) and set the frequency to 3Hz.Repeat for all three gain sets used
in part A.Use the main scope block for the most accurate measurements.
F. Repeat part C using measurements from part E.
G. Repeat part D using measurements from part E.
H. Compare measurements made in C and D to those made in F and G.
4. Evaluate the improvement of disturbance response when the power converter
bandwidth is increased.
A. Modify Experiment 6E to view command response.Open Experiment 6E;
to avoid permanent changes to the file Experiment_6E.mqd, save as
Temp.mqd. Disconnect the disturbance source from the disturbance input
summing junction; disconnect the Live Constant R from the command
input.Connect the disturbance generator to the command input as shown
in Figure 6-22. Tune the nondecoupled system (K =0) for three power
DD
converter bandwidths (FP ):50,100,and 200Hz.Tuning criteria:no over-
C
shoot to step for K and 25% overshoot with K.
P I

| 140 (cid:2) | CHAPTER 6 | THE LUENBERGER OBSERVER                                                     | ANDDISTURBANCES |
| ----------- | --------- | --------------------------------------------------------------------------- | --------------- |
|             |           | Figure 6-22. Temporarily modified section of Experiment 6E for Exercise 4A. |                 |
B. Reopen Experiment 6E. What is the peak excursion of the disturbance
response for the three power–converter frequencies without disturbance
decoupling,using the tuning gains from part A.
|     | C.  | Repeat part B with disturbance decoupling (K | =1,K =0). |
| --- | --- | -------------------------------------------- | --------- |
DD I
D. For the 200-Hz power converter,does raising K from the values in part A
P
significantly affect the disturbance response in the disturbance-decoupled
system? Explain.

Chapter 7
Noise in the
Luenberger Observer
In this chapter...
• Common sources of noise in control systems
• Effects of noise on observers and observer-based systems
• Effects of noise on disturbance-decoupled systems
• Reducing noise in observer-based systems
• The modified Luenberger observer
This chapter will discuss noise in control systems, especially for systems that use
the observed state as a feedback signal.The effect of noise on systems using observer-
based disturbance decoupling will also be discussed. In addition, three common
methods used to reduce noise sensitivity will be presented: reducing observer band-
width, filtering the observed disturbance, and modifying the observer-compensator
structure. As in earlier chapters, key points will be demonstrated with simulation
experiments.
7.1 Noise in Control Systems
Noise sensitivity is an important consideration for most control-systems.Noise from
sensors and other sources can distort the control-system output, introducing
unwanted perturbations on the control variable and generating unacceptable levels of
acoustic noise.An understanding of noise is desirable for designers who use observers
because observer-based control systems are often more sensitive to sensor noise than
are traditional control systems. This section will provide background on noise,
141

142 (cid:2) CHAPTER 7 NOISEINTHE LUENBERGEROBSERVER
including different types and sources of noise and how noise enters the control
system.This background will aid the analytical development that follows in the later
sections.
7.1.1 White vs Colored Noise
Random noise is composed of harmonics from across the frequency spectrum.
Random noise is often referred to as white because, like the color white, it contains
all frequency harmonics in approximately equal magnitude. Noise can be filtered, a
condition where one or more bands of frequency have been attenuated;this is referred
to as colored noise. For example, if white noise feeds a low-pass filter, frequency
components at and above the filter bandwidth will be attenuated; the output of
such a filter will be colored noise.
In this chapter,all analytical and experimental development assumes that the noise
is white. The experiments use the unfiltered output of a pseudo-random number
generator to produce near-white noise. Bear in mind that noise above the Nyquist
frequency (half the sample frequency) aliases to lower frequencies.For those readers
studying the effects of colored noise, the results of the treatment of white noise are
easily modified to show the effects of colored noise. For analytical treatment, the
transfer function of the coloring filter can be cascaded with that of the white noise.
For experimental treatment,a coloring filter can be cascaded with the pseudo-random
number generator.
7.1.2 Quantization and Noise
Quantization is a common source of noise in digital control systems.Quantization is
the undesirable process of limiting resolution of a continuous signal. For example,
a 12-bit analog-to-digital converter (ADC) allows only 212 (4096) discrete values to
represent a voltage. Even though the voltage input to the ADC almost always falls
between these values, it will be assigned one of these discrete values. For the ideal
case,the value will be the closest discrete value to the actual value.Assuming that the
input (nonquantized) signal can take on any value, quantization is sometimes repre-
sented as a random noise added to the actual signal. The magnitude of the random
noise is half the resolution of the quantization process. For example, if the ADC
were quantized to 0.005V, the output of the ADC could be modeled as the actual
magnitude of the input signal summed with a random noise signal that had a
min/max of ±0.0025V.
Quantization comes from two primary sources. First, in digital control systems,
sensor output must be represented digitally. Since sensors usually monitor analog
processes, this implies that the sensor output must be quantized. This may occur
through standard analog-to-digital converters or through any of the myriad of
digital converters for specialized sensors. The second source for quantization is
through digital calculations. Many digital calculations generate quantized output

7.1 NOISEINCONTROLSYSTEMS (cid:3) 143
when the result is truncated. Practical limitations usually require that results of
arithmetic operations be truncated. Careful design of calculations can minimize
the effects of quantization in calculations, but in most cases, the effects cannot be
eliminated.
7.1.3 Noise Entry Points
Noise can be injected into a control system at many points. As shown in Figure 7-1,
three key entry points are through the command, through calculations (typically
in the control law), and through the sensor. This section will briefly discuss the
differences between these sources. The balance of this chapter will focus on noise
from the sensor,as it is probably the most common source of noise and often has the
greatest effect on observer-based systems.
| 7.1.3.1 Command Noise |     |     |     |
| --------------------- | --- | --- | --- |
Command noise is noise that is added to the command en route to the control-system
input or through noise generation in the command-input circuitry.In analog control
systems, command noise is a common problem. Noise can be radiated or conducted
from noise generators. For example, high-frequency pulse-modulated power con-
verters,often present in control systems,can radiate noise to neighboring equipment.
Ground loops and other forms ofground noise can conduct noise to command inputs.
Digital systems often eliminate command noise by digitally encoding the command
before transmitting it. Digital encoding is well known to greatly reduce or even
eliminate noise sensitivity.However,many digital systems such as programmable logic
| Command | Calculation |       |      |
| ------- | ----------- | ----- | ---- |
| noise   | noise       |       |      |
| R(s)    |             | Power | D(s) |
C(s)
| +   |         |        | +   |
| --- | ------- | ------ | --- |
|     | Control | Power  |     |
Plant
| + _ | law | converter | +   |
| --- | --- | --------- | --- |
D (s)
|     |     | O   | Z(s) Y(s) |
| --- | --- | --- | --------- |
Luen.
Feedback Sensor
|     |     | observer | + + |
| --- | --- | -------- | --- |
C (s)
O
Sensor
noise
Figure 7-1. Three points for noise to enter an observer-based control system.

144 (cid:2) CHAPTER 7 NOISEINTHE LUENBERGEROBSERVER
controllers (PLCs) and motor controllers accept commands in analog form and dig-
itally encode them after the transmission.Such systems are as sensitive to command
noise as their analog counterparts.
The system sensitivity to command noise is identical to the closed-loop command
response. Since the noise enters with the command, the system will respond to the
noise as it does to the command.
7.1.3.2 Calculation Noise
Calculation noise is caused by quantization in digital calculations. Most calculation
noise comes from the control law.Calculation noise generates a pseudo-random noise
with a magnitude of ±1/2 the resolution of the calculations. When control laws are
constructed carefully, calculation noise usually has minimal effect on the control
system.
7.1.3.3 Sensor Noise
Sensor noise is generated in a variety of ways.Quantization noise can be injected when
analog sensor signals are converted to a digital format. The sensor hardware can
generate noise,especially when sensors include analog electronics to amplify low-level
signals. Like command signals, sensor signals are sensitive to electromagnetic inter-
ference (EMI) such as ground loops, ground noise, and radiated emissions. Because
sensor noise is of particular interest to designers of observer-based systems, the
remainder of this chapter will focus on this source.
7.1.3.4 Analysis of Sensor Noise in This Chapter
Two methods of analysis will be applied in this chapter. First, an analytical
approach will be taken by constructing and evaluating transfer functions. Then an
experimental approach will be used to confirm and expand upon the findings of the
analytical approach. The experiments will use both the time and the frequency
domains.
First, the observer-based feedback structure will be examined. The sensitivity of
the observed state, C (s), will be considered. Those results will then be extended to
O
explain the effects of noise on the actual state,C(s).Readers should bear in mind that
the observed state is an internal state; while understanding its behavior provides
intuition about the operation of observer-based systems, the behavior of the actual
state is usually the measure of control-system performance.
After the observer-based feedback structure is discussed, systems using an
observer-based disturbance-decoupled structure will be examined.The effects ofnoise
on the observed disturbance, D (s), will be evaluated first. The effects of the actual
O
state, C(s),will be considered after that.

|     |     |     |     |     | 7.2 | SENSOR NOISEANDTHE |     | LUENBERGEROBSERVER |     | (cid:3) 145 |
| --- | --- | --- | --- | --- | --- | ------------------ | --- | ------------------ | --- | ----------- |
7.2 Sensor Noise and the Luenberger Observer
Noise is an important consideration when developing observer-based products. One
of the unfortunate characteristics of observers is that they often respond to sensor
noise more than nonobserver systems do. This is because, below the observer band-
width,the observer amplifies noise by effectively placing the inverse-estimated-sensor
transfer function (G-1
|     |     | (s)) in line with the sensor (see Figure 4-15). |     |     |     |     |     | Accordingly, | the |     |
| --- | --- | ----------------------------------------------- | --- | --- | --- | --- | --- | ------------ | --- | --- |
SEst
observer amplifies high-frequency components of sensor noise, often greatly. This
effect is magnified in systems that use disturbance decoupling.
7.2.1 Transfer Function Analysis of Co(s)/N(s)
The analytical approach begins with a heuristic discussion of the noise sensitivity
of the observed state. Refer to Figure 7-2, which is the Luenberger observer in the
presence of sensor noise, N(s). For this discussion, consider the frequencies below
the observer bandwidth.
| 1. From Figure 7-2,Y |     | (s)=C |     | (s)¥G | (s) and Y(s)=C(s)¥G |     |     | (s). |     |     |
| -------------------- | --- | ----- | --- | ----- | ------------------- | --- | --- | ---- | --- | --- |
|                      |     | O     | O   |       | SEst                |     |     | S    |     |     |
2. Assume that, in the range of frequencies below the observer bandwidth, the
observer compensator is able to drive the error,E (s), nearly to zero.
O
| 3. Driving E | (s)(cid:2)0 implies that Y |     |     | (s)(cid:2)Z(s), |     | so Y (s)(cid:2)Y(s)+N(s). |     |     |     |     |
| ------------ | -------------------------- | --- | --- | --------------- | --- | ------------------------- | --- | --- | --- | --- |
|              | O                          |     |     | O               |     | O                         |     |     |     |     |
(s)(cid:2)C(s)¥G
| 4. Combine 1 and 3:C                                |     |     | (s)¥G |      |     | (s)+N(s). |             |      |     |     |
| --------------------------------------------------- | --- | --- | ----- | ---- | --- | --------- | ----------- | ---- | --- | --- |
|                                                     |     | O   |       | SEst |     | S         |             |      |     |     |
| 5. Assume that the observer sensor model is ideal:G |     |     |       |      |     |           | (s)(cid:2)G | (s). |     |     |
|                                                     |     |     |       |      |     |           | SEst        | S    |     |     |
(s)(cid:2)C(s)¥G
| 6. Combine 4 and 5:C |     |     | (s)¥G |      |      | (s)+N(s). |     |      |     |     |
| -------------------- | --- | --- | ----- | ---- | ---- | --------- | --- | ---- | --- | --- |
|                      |     | O   |       | SEst |      | SEst      |     |      |     |     |
| D(s)                 |     |     |       |      |      |           |     | Y(s) |     |     |
|                      |     | +   |       |      | C(s) |           |     |      |     |     |
| Disturbance          |     |     | G (s) |      |      | G (s)     |     |      |     |     |
Z(s)
|     |     |     | P   |     | Actual | S   |     |     |        |     |
| --- | --- | --- | --- | --- | ------ | --- | --- | --- | ------ | --- |
|     | +   |     |     |     |        |     |     | + + | Actual |     |
state
|       |     |     | Plant |                 |     | Sensor |     |      | sensor |     |
| ----- | --- | --- | ----- | --------------- | --- | ------ | --- | ---- | ------ | --- |
| P (s) |     |     |       |                 |     |        |     | N(s) |        |     |
| C     |     |     |       | Physical system |     |        |     |      | output |     |
Noise
Plant
|            |       | O b     | s e r v ed |     |       | Ob s e r v | er  |     |     |     |
| ---------- | ----- | ------- | ---------- | --- | ----- | ---------- | --- | --- | --- | --- |
| excitation | D (s) |         |            |     |       |            | E   | (s) | +   |     |
|            | O     | d is tu | r b a n ce |     |       | e r r o r  |     | O   |     |     |
|            |       |         |            |     | G (s) |            |     |     |     |     |
|            |       |         |            |     | CO    |            |     |     | _   |     |
Observer compensator
|     |     | +   |     | C   | (s) |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
O
|     |     |     | G (s) |          |     | G (s) |     |     | Y (s) |     |
| --- | --- | --- | ----- | -------- | --- | ----- | --- | --- | ----- | --- |
|     |     |     | PEst  | Observed |     | SEst  |     |     | O     |     |
+
|     |     |     |       | state |     |        |     |     | Observed |     |
| --- | --- | --- | ----- | ----- | --- | ------ | --- | --- | -------- | --- |
|     |     |     | Plant |       |     | Sensor |     |     |          |     |
sensor
Modeled system
output
Figure 7-2. The Luenberger observer in the presence of sensor noise.

| 146 (cid:2) | CHAPTER 7 NOISEINTHE | LUENBERGEROBSERVER |     |     |     |     |
| ----------- | -------------------- | ------------------ | --- | --- | --- | --- |
(s)(cid:2)C(s)+N(s)
|     | 7. Dividing both sides of |     | step 6 by G | (s) reveals the problem: |     | C   |
| --- | ------------------------- | --- | ----------- | ------------------------ | --- | --- |
|     |                           |     |             | SEst                     |     | O   |
|     | ¥G-1 (s).                 |     |             |                          |     |     |
SEst
This demonstrates that, for frequencies below the observer bandwidth, noise is
scaled approximately by G-1 (s) and then added to the observed state. Since G (s)
SEst SEst
typically has the form of a low-pass filter, attenuating frequency components above
the sensor bandwidth,G-1 (s),will amplify components above the sensor bandwidth.
SEst
Another way to see noise amplification in observers is to consider the operation of
the observer loop in the presence ofnoise.Below the observer bandwidth,the observer
compensator drives the plant hard enough to remove almost all observer error.Again,
G (s) acts like a low-pass filter in practical systems. This means that the noise
SEst
content above the bandwidth of G (s) must be amplified in order to produce an
SEst
observed-sensor output (Y (s)) that will drive the observer error to zero.For example,
O
suppose at 100Hz,G SEst (s) provides -20dB (1/10th) gain.Suppose also thatZ(s) has
a 100-Hz noise component with a magnitude of 0.1V. Then, the observer compen-
sator would have to drive the estimated plant hard enough that a 100-Hz signal
with 1.0-V magnitude appeared at C (s). This is required for 0.1V to exit from
O
G (s) and cancel the 100-Hz noise component in Z(s). So, at 100Hz, the observed
SEst
feedback would contain the sensor noise amplified by a factor of ten. Again, the
observer compensator effectively amplifies the noise by the 1/G (s) or,equivalently,
SEst
G-1 (s).
SEst
The  noise  susceptibility  of an  observer  can  be  examined  more  carefully  by
analyzing the transfer function first discussed in Section4.3.Recall from Equation 4.4
that the observer output is a combination of the high-pass filtered power converter
signal and the low-pass filtered sensor signal.Rewritten with the noisy sensor output,
Z(s),Equation 4.4 becomes:
|     |     |              |      | G (s)¥G   | (s)¥G (s) |     |
| --- | --- | ------------ | ---- | --------- | --------- | --- |
|     |     | (s)=Z(s)¥G-1 |      | PEst      | CO SEst   |     |
|     |     | C O          | SEst | (s)       |           |     |
|     |     |              |      | 1+G (s)¥G | (s)¥G     | (s) |
|     |     |              |      | PEst      | CO SEst   |     |
1
|     |     | +P  | (s)¥G | (s)       |       | .     |
| --- | --- | --- | ----- | --------- | ----- | ----- |
|     |     |     | C     | PEst      |       | (7.1) |
|     |     |     |       | 1+G (s)¥G | (s)¥G | (s)   |
|     |     |     |       | PEst      | CO    | SEst  |
The fraction that appears in the first term of the right side of Equation 7.1 is the
closed-loop response of the observer. It behaves like a low-pass filter with a band-
width equal to that of the observer loop. The fractional portion of the second term
on the right side is the high-pass filter first discussed in Section 4.3. Recognizing the
|     | low-pass and high-pass filtering terms of |     |      | Equation 7.1 as |      |       |
| --- | ----------------------------------------- | --- | ---- | --------------- | ---- | ----- |
|     |                                           |     |      | G (s)¥G (s)¥G   | (s)  |       |
|     |                                           | G   | (s)= | PEst CO         | SEst | (7.2) |
OLPF
|     |     |     |     | 1+G (s)¥G (s)¥G | (s)  |     |
| --- | --- | --- | --- | --------------- | ---- | --- |
|     |     |     |     | PEst CO         | SEst |     |
1
|     |     | G   | (s)= |                 |      |       |
| --- | --- | --- | ---- | --------------- | ---- | ----- |
|     |     |     | OHPF |                 |      | (7.3) |
|     |     |     |      | 1+G (s)¥G (s)¥G | (s)  |       |
|     |     |     |      | PEst CO         | SEst |       |

|     |     |     | 7.2 SENSOR NOISEANDTHE | LUENBERGEROBSERVER | (cid:3) 147 |
| --- | --- | --- | ---------------------- | ------------------ | ----------- |
Eq. (7.1) can be rewritten as:
| C (s)=Z(s)¥G-1 | (s)¥G | (s)+P | (s)¥G (s)¥G | (s). (7.4) |     |
| -------------- | ----- | ----- | ----------- | ---------- | --- |
| O              | SEst  | OLPF  | C PEst      | HLPF       |     |
If the noise content of the power converter, P (s), and the nonnoise components
C
of the sensor output are ignored (Z(s)=N(s)),noise sensitivity is:
C (s)
|     |      | O =G-1 |            |       |     |
| --- | ---- | ------ | ---------- | ----- | --- |
|     |      |        | (s)¥G (s). | (7.5) |     |
|     | N(s) | SEst   | OLPF       |       |     |
Below the observer bandwidth,the term G (s) is approximately 1.Below the sensor
OPLF
bandwidth, G (s) is approximately 1; above that frequency, G (s) declines. Thus,
| SEst |     |     |     | SEst |     |
| ---- | --- | --- | --- | ---- | --- |
between the sensor bandwidth and the observer bandwidth, the sensor noise will be
amplified.
7.2.1.1 Transfer Function Analysis of C(s)/N(s)
This section will analyze the noise sensitivity of the actual state,C(s).In the end,the
sensitivity of the actual state is of more concern than that of the observed state;
the observed state is an internal signal while the actual state describes the response of
the machine or process.
This analysis begins by considering Figure 7-3, a block diagram of the control
system with observed feedback. The observer is represented in the filter form, which
was introduced in Section 4.3, using the definitions of Equations 7.2 and 7.3.
Evaluation of the noise sensitivity can be carried out by assuming zero command
(R(s)=0) and then evaluating the transfer function from the noise,N(s),to the actual
state, C(s).
Mason’s signal flow graphs can be used to develop the transfer function from N(s)
to C(s).In Figure 7-3,there is a single forward path from N(s) to C(s),and there are
two loops, which are both in contact with the forward path:
| L      |     |     |           | N(s) |     |
| ------ | --- | --- | --------- | ---- | --- |
| R(s) 1 |     |     |           |      |     |
|        |     |     | C(s) Y(s) | Z(s) |     |
+
+
| G (s) | G (s) | G (s) | G (s) | G -1 (s) |     |
| ----- | ----- | ----- | ----- | -------- | --- |
| C     | PC    | P     | S     | SEst     |     |
_
+
L
2
|     |     | G    | (s) G (s) | G (s) |     |
| --- | --- | ---- | --------- | ----- | --- |
|     |     | PEst | OHPF      | OLPF  |     |
+ +
C (s)
| L   |     |     |     | O   |     |
| --- | --- | --- | --- | --- | --- |
1
| Figure 7-3. | Block diagram of system with filter-form representation of observer. |     |     |     |     |
| ----------- | -------------------------------------------------------------------- | --- | --- | --- | --- |

| 148 (cid:2) | CHAPTER | 7   | NOISEINTHE | LUENBERGEROBSERVER |       |       |       |         |           |      |     |
| ----------- | ------- | --- | ---------- | ------------------ | ----- | ----- | ----- | ------- | --------- | ---- | --- |
|             |         |     | P          | =G-1               | (s)¥G | (s)¥G |       | (s)¥G   | (s)¥G (s) |      |     |
|             |         |     |            | 1 SEst             |       | OLPF  | C     |         | PC P      |      |     |
|             |         |     | L          | =-G                | (s)¥G | (s)¥G | (s)¥G | (s)¥G-1 | (s)¥G     | (s)  |     |
|             |         |     |            | 1                  | C     | PC    | P     | S       | SEst      | OLPF |     |
|             |         |     | L          | =-G                | (s)¥G | (s)¥G |       | (s)¥G   | (s).      |      |     |
|             |         |     |            | 2                  | C     | PC    | PEst  |         | OHPF      |      |     |
This yields the transfer function of Equation 7.6 or,equivalently,Equation 7.7.
P
|     |     |     |     |     |     | T(s)= |     | 1   |     |     |     |
| --- | --- | --- | --- | --- | --- | ----- | --- | --- | --- | --- | --- |
(7.6)
|     |     |     |     |     |     |     | 1-L | -L  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
1 2
|     | C(s) |     |           |     | G-1    | (s)¥G | (s)¥G   |      | (s)¥G (s)¥G | (s)   |            |
| --- | ---- | --- | --------- | --- | ------ | ----- | ------- | ---- | ----------- | ----- | ---------- |
|     |      | =   |           |     | SEst   |       | OLPF    | C    | PC          | P     |            |
|     | N(s) |     | 1+G (s)¥G |     | (s)¥(G | (s)¥G | (s)¥G-1 |      | (s)¥G       | (s)+G | (s)¥G (s)) |
|     |      |     | C         | PC  |        | P     | S       | SEst | OLPF        | PEst  | OHPF       |
(7.7)
Equation 7.7 can be simplified by assuming the observer plant and sensor models
are nearly ideal and by recognizing that the two filter terms from Equations 7.2 and
7.3 sum to 1:
|     |     |     |     |     |     |       | G    | (s)ªG  | (s) |     |     |
| --- | --- | --- | --- | --- | --- | ----- | ---- | ------ | --- | --- | --- |
|     |     |     |     |     |     |       |      | SEst   | S   |     |     |
|     |     |     |     |     |     |       | G    | (s)ªG  | (s) |     |     |
|     |     |     |     |     |     |       |      | PEst   | P   |     |     |
|     |     |     |     |     | G   | (s)+G |      | (s)=1. |     |     |     |
|     |     |     |     |     |     | OHPF  | OLPF |        |     |     |     |
These assumptions simplify Equation 7.7 to:
|     |     |     |     | C(s) |       |      |      | G (s)¥G | (s)¥G       | (s) |       |
| --- | --- | --- | --- | ---- | ----- | ---- | ---- | ------- | ----------- | --- | ----- |
|     |     |     |     |      |       |      |      | C       | PC          | P   |       |
|     | `   |     |     | ªG-1 | (s)¥G |      | (s)¥ |         |             | .   | (7.8) |
|     |     |     |     | N(s) | SEst  | OLPF |      | 1+G     | (s)¥G (s)¥G | (s) |       |
|     |     |     |     |      |       |      |      | C       | PC          | P   |       |
The result of Equation 7.8 is consistent with Equation 7.5,which demonstrated that
the  noise  sensitivity  of the  observed  state  was  G-1 (s)¥G (s). That  term  also
|     |     |     |     |     |     |     |     |     | SEst | OLPF |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ---- | ---- | --- |
appears in the right side of Equation 7.8. Further, notice that the remaining term on
the right side of Equation 7.8 is in the form G (s)/(1+G (s)),where G (s) is the open-
|     |     |     |     |     |     |     |     | OL  | OL  |     | OL  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
loop transfer function excluding the effects of the observer and sensor.Finally,recog-
nizing that the system closed-loop transfer function is G (s)/(1+G (s)), it becomes
|     |     |     |     |     |     |     |     |     | OL  | OL  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
apparent that the noise sensitivity of the actual state is simply the noise sensitivity of
the observed state cascaded with the control-law closed-loop transfer function.
C(s)
|     |     |     |     |     |     | ªG-1 | (s)¥G |      | (s)¥G (s) |     |       |
| --- | --- | --- | --- | --- | --- | ---- | ----- | ---- | --------- | --- | ----- |
|     |     |     |     |     |     | SEst |       | OLPF | CL        |     | (7.9) |
N(s)
|     |     | 7.2.1.2 | Comparison to Traditional (Nonobserver) Systems |     |     |     |     |     |     |     |     |
| --- | --- | ------- | ----------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
The noise sensitivity of the traditional and observer-based control systems can be
compared by analyzing the differences of their respective transfer functions. The
traditional control system with a noisy sensor is shown in Figure 7-4.

|     |     |     | 7.2 SENSOR NOISEANDTHE | LUENBERGEROBSERVER | (cid:3) 149 |
| --- | --- | --- | ---------------------- | ------------------ | ----------- |
N(s)
|     |     |     | C(s) | Y(s) |     |
| --- | --- | --- | ---- | ---- | --- |
_
| +    |       |       |             | Z(s) |     |
| ---- | ----- | ----- | ----------- | ---- | --- |
| R(s) | G (s) | G (s) | G (s) G (s) |      |     |
|      | _ C   | PC    | P S         |      |     |
+
Figure 7-4. Block diagram of traditional (nonobserver) system.
The noise sensitivity of the actual state, C(s), is written out from Mason’s signal
flow graphs:
|     | C(s) | G (s)¥G   | (s)¥G (s)       |        |     |
| --- | ---- | --------- | --------------- | ------ | --- |
|     |      | C         | PC P .          |        |     |
|     | =    |           |                 | (7.10) |     |
|     | N(s) | 1+G (s)¥G | (s)¥G (s)¥G (s) |        |     |
|     |      | C         | PC P S          |        |     |
Rearranging Equation 7.10 to isolate the closed-loop transfer function1yields:
|     | C(s) | G (s)¥G   | (s)¥G (s)       |        |     |
| --- | ---- | --------- | --------------- | ------ | --- |
|     |      | C         | PC P            |        |     |
|     | =    |           |                 | (7.11) |     |
|     | N(s) | 1+G (s)¥G | (s)¥G (s)¥G (s) |        |     |
|     |      | C         | PC P S          |        |     |
C(s)
|     | =G-1(s)¥G |      | (s). |     |     |
| --- | --------- | ---- | ---- | --- | --- |
|     | N(s)      | S CL |      |     |     |
At frequencies well below the control-law bandwidth, the open-loop gain will
dominate the “1”in the denominator and the noise susceptibility will be:
C(s)
|     |     | ªG-1(s). |     | (7.12) |     |
| --- | --- | -------- | --- | ------ | --- |
|     |     | N(s)     | S   |        |     |
A  similar  result  occurs  when  the  observer-based  transfer  function  of
(s)(cid:2)1) and
Equation 7.8 is evaluated below the observer bandwidth (where G
OLPF
the  control-law  bandwidth  (where  the  closed-loop  control-law  response(cid:2)1).
Equation 7.8 reduces to:
C(s)
|     |     | ªG-1 | (s). |        |     |
| --- | --- | ---- | ---- | ------ | --- |
|     |     |      | SEst | (7.13) |     |
N(s)
1The reader should notice that the forms of the open-loop transfer functions differed between the
traditional and observer-based feedback systems. The open loop of the traditional system includes the
sensor transfer function while the observer-based system does not.The reason for the difference is that
the observer removes the effects of the sensor transfer function when properly configured and thus its
| elimination accurately reflects the operation of |     | the control loop. |     |     |     |
| ------------------------------------------------ | --- | ----------------- | --- | --- | --- |

150 (cid:2) CHAPTER 7 NOISEINTHE LUENBERGEROBSERVER
So,at low frequencies,the noise susceptibility of the two systems is about the same.
However,there is a significant difference when the transfer functions are evaluated at
higher frequencies. In the traditional system, at frequencies higher than the control-
law bandwidth,the “1”in the denominator of Equation 7.11 dominates and the noise
sensitivity reduces to:
C(s)
=G (s)¥G (s)¥G (s). (7.14)
N(s) C PC P
However,the observer-based control system produces a different result.Above the
control-law bandwidth, where “1”dominates the denominator of Equation 7.8, that
equation reduces to:
C(s)
=G-1 (s)¥G (s)¥G (s)¥G (s)¥G (s). (7.15)
N(s) SEst OLPF C PC P
Comparing the noise susceptibility indicated by Equations 7.14 and 7.15, the
primary difference is the appearance of the term G-1 (s) in the observer-based
SEst
system. Since G (s) is normally a term that attenuates at high frequency, G-1 (s)
SEst SEst
will normally amplify at high frequency. Above the sensor bandwidth and below
the observer bandwidth, the observer-based system will be noisier by an amount
approximately equal to the attenuation provided by the sensor.
7.2.2 Experiment 7A: The Effects of Sensor Noise on the Observed State
This section and the next will use simulations to confirm the previous analytical
development. The simulations will start with Visual ModelQ Experiment 7A, shown
in Figure 7-5.This model is similar to the models of previous chapters.The key points
are:
• The control system is a PI loop with the feedback taken from the sensor.Similar
to Experiments 5C and 6A, the sensor is modeled as a single-pole low-pass
filter with a bandwidth of 20Hz,and the power converter is a double-pole low-
pass filter with a bandwidth of 50Hz.The PI gains are also the same as in those
experiments.
• There is an observer that is tuned to a bandwidth of about 155Hz (see
Section 5.3.1).The model parameters of the observer are accurate:K =50 and
Est
F =20Hz.
GsEst
• The model includes a noise source named “Sensor Noise”near the top center.
This is a pseudorandom number generator with an amplitude of ±1.The sum
of the noiseless sensor output and the noise source form Z,the sensor output.
• There is a DSA configured to inject the noise input of the control loop. This
instrument is used to measure the noise response of various signals in the

7.2 SENSOR NOISEANDTHE LUENBERGEROBSERVER (cid:3) 151
Figure 7-5. Experiment 7A: Evaluating the effects of noise on the observed state.
system.Note that the DSA disables the command waveform generator (at left)
through the VisualModelQExtender “DSA On.”This is done because the DSA
must zero other control-system inputs during its excitation to allow accurate
measurements.As usual,when the DSA is not exciting the system (the normal
case), it passes the output of the random generator Sensor Noise to the
summing junction that adds Yand Nto form Z.
• There are three LiveScopes:the actual state (C),the measured state after noise
is injected (Z),and the observed state (C ).
O
The results of Experiment 7A can be viewed in the time domain and in the fre-
quency domain.The time domain aids intuitive understanding of the observer behav-
ior in the presence of noise;the frequency domain provides quantitative comparisons.
The result in the time domain can be seen in the Live Scopes of Figure 7-5. The
actual state, C, at top right, is almost unaffected by noise in this system. That is
because the control-law gains are relatively low and the integrating plant provides
enough filtering to remove visible effects of the noise source.The effects of the noise
on the sensor output, Z, at bottom right, are apparent. Without the noise, Z would
be nearly identical to C,except for the phase lag of the sensor, G (s).
S
The observed state, C , at left, is much more affected than is the sensor output,
O
Z. In the absence of noise, C is almost identical to C (reference Figure 5-5 from
O
Experiment 5C). Of course, these signals are not the same in the presence of noise.
The noise,fed in through Z,has been amplified by the observer.The result is that the
observed state is corrupted by the noise to such an extent that the signal actual state
is difficult to see through the high-frequency noise. This is the expected result from
Equation 7.5.

152 (cid:2) CHAPTER 7 NOISEINTHE LUENBERGEROBSERVER
Sensor BW Observer BW
15 dB
Note: The modest gain at low Key point: The amplification at
frequency is also caused by medium and high frequencies is
peaking in the control law caused by the observer, consistent
and is unrelated to the with Equation 7.5.
observer.
Figure 7-6. From Experiment 7A: Bode plot of observed state vs noise.
A Bode plot of observed state vs noise, as shown in Figure 7-6, provides a quan-
titative evaluation of the effects of noise. In the middle frequencies (approximately
between the sensor bandwidth and the observer bandwidth) the gain is steadily rising.
This can be seen in Equation 7.5 because the amplification of G-1 (s) increases above
SEst
the sensor bandwidth.The level of amplification stabilizes around the observer band-
width.This can also be seen in Equation 7.5 because,above the observer bandwidth,
the observer (represented at G (s)) provides attenuation.
OLPF
The reader may notice an unexpected amplification of a few decibels below the
sensor bandwidth.This is not predicted by Equation 7.5.In fact,this results because
of peaking in the control loop; the cause of this effect is that the control system has
some peaking in this range so that noise signals, as well as commands, are modestly
amplified in this frequency range.
7.2.3 Experiment 7B: The Effects of Sensor Noise on the Actual State
Experiment 7B extends 7A to allow the evaluation of the effects of noise on the actual
state (see Figure 7.7).There are just a few differences:
• The feedback path is fed with a switch (at bottom left) that can be configured
to connect either sensor output or the observed state. The connection is the

7.2 SENSOR NOISEANDTHE LUENBERGEROBSERVER (cid:3) 153
Figure 7-7. Experiment 7B: Evaluating the effects of noise on the actual state.
controller with the LiveConstant“Feedback,”which can take on the values of
“Sensor”or “Observer.”
• The amplitude of the noise is controlled with a Live Constant named “Noise
Amplitude”at top right.
• The power converter output, P , is shown in a Live Scope at top center. The
C
power converter output is an indicator of noise susceptibility.
The effects of noise in the time domain are most easily seen by viewing the power
converter output. This is because an integrating plant smoothes the noise, making
evaluation based on the actual state difficult. Also, many noise issues are driven by
the power converter output rather than by the actual state. For example, some noise
in a hydraulic positioning system will be caused by the flow of hydraulic fluid rather
than by the position of the cylinder. Acoustic noise from a voltage supply will often
be caused by current that vibrates inductor winding, not by the output voltage.
The comparison of the power converter output of Experiment 7B is given in
Figure 7-8. In Figure 7-8a, where the sensor output is used for feedback, the effects
of noise are modest. In Figure 7-8b, where the observed state is used for feedback,
the effects are considerably greater. Note that the noise amplitude and control gains
(K , K) are identical in these plots; the increase in noise sensitivity is due solely to
P I
the use of the observed state.
The noise sensitivity of the actual state also can be viewed by comparing the actual
state with the loop configured for (1) observed-state feedback and (2) sensor output.

154 (cid:2) CHAPTER 7 NOISEINTHE LUENBERGEROBSERVER
(a) (b)
Figure 7-8. From Experiment 7B: Effects of noise on the power converter output (a) with sensor output as
feedback and (b) with observed state for feedback.
A comparison is shown in Figure 7-9. Again, the result is that the sensitivity of the
system with observer feedback (Figure 7-9a) is greater than that of the system with
sensor feedback (Figure 7-9b). The integrating plant smoothes noise, making it
difficult to discern in these plots. In fact, the amplitude of the noise source had to
be increased from 1 to 5 to show the effects even this much. The plots of Figure 7-9
are consistent with Equations 7.14 and 7.15;the effect of the term G-1 (s)¥G (s)
SESt OLPF
in Equation 7.15 will normally amplify high-frequency noise.
A quantitative measurement of noise sensitivity of the actual state can be seen
in a Bode plot generated by Experiment 7B and shown in Figure 7-10. The noise
sensitivity of the sensor-based system (Equation 7.14) and the observed-state-based
(a) (b)
Figure 7-9. From Experiment 7B: Effects of noise on the actual state (a) with sensor output as feedback and
(b) with observed state for feedback. Note that the noise amplitude has been increased to 5 for both cases.

7.2 SENSOR NOISEANDTHE LUENBERGEROBSERVER (cid:3) 155
Noise sensitivity of system
with observer feedback.
Noise sensitivity of system
with sensor feedback.
Difference caused by
G -1(s) xG (s)
SEst OLPF
in Equation 7.15.
Figure7-10. From Experiment 7B: Bode plot of noise sensitivity of actual state with observer feedback and
sensor feedback.
system (Equation 7.15) is plotted in this figure. The difference between the two
configurations is due to the term G-1 (s)¥G (s), which is the difference between
SEst OLPF
Equations 7.14 and 7.15.That term is the noise sensitivity of the observed state;it is
equal to Equation 7.5 and is plotted approximately in Figure 7-6. As expected, the
observed-state-based system is equivalent to the sensor-based system at frequencies
below the sensor bandwidth, but is more sensitive above that. The maximum
difference of about 15dB is present at and above the observer bandwidth,consistent
with Figure 7-6.
7.2.4 The Effects of Control-Law Gains on Noise Sensitivity
Equation 7.15 predicts that noise sensitivity of the observer-based system will increase
with increased control-law gains (G ). The comparisons of the previous sections
C
assumed the control-law gains were the same with and without the observer.However,
observers are often employed to allow increased control-law gains.Since the control-
law gains will often be higher in observer-based systems,noise sensitivity will increase
further.
The effect of raising control-law gains is shown in Figure 7-11. In Figure 7-11a,
the sensitivity with the original control-law gains (K =0.6, K =12) is shown; this is
P I

156 (cid:2) CHAPTER 7 NOISEINTHE LUENBERGEROBSERVER
(a) (b)
Figure 7-11. From Experiment 7B, the effects of control law gains on sensitivity of actual state in
observer-based system: (a) with low gains (K =0.6, K=12), and (b) with high gains (K =1.5, K=30).
P I P I
identical to Figure 7-9b.In Figure 7-11b,taking advantage of the reduction in phase
lag provided by the observer, the gains are raised to (K =1.5, K =30), which are
P I
the higher gains used in Chapter 5. The increase in sensitivity is apparent. This is
consistent with Equation 7.15, which shows noise sensitivity increasing with
control-law gains, as well as with other factors including the observer and power
converter bandwidths.
7.3 Noise Sensitivity when Using Disturbance Decoupling
Disturbance decoupling can greatly increase the noise sensitivity of a control system
for at least two reasons.First,as demonstrated in Section 6.3,disturbance-decoupled
systems can respond at higher frequencies than the control law. The structure of the
disturbance-decoupled system routes the observed disturbance directly to the power
converter; the primary limits on response are the observer bandwidth, the power
converter bandwidth, and the plant. This structure gives disturbance decoupling
its superior disturbance-rejection properties. Unfortunately, it brings with it higher,
often much higher,noise sensitivity.
The second reason for higher noise sensitivity is that, where observer-feedback
systems rely on the observed state,disturbance decoupling relies on the observed dis-
turbance.The observed disturbance is more sensitive to noise than the observed state.
In this context,the main difference between the two signals is that the observed state
passes through the model plant (reference Figure 7-2).In practical systems,the model
plant usually will be a combination of integrators and low-pass filters,both of which
will attenuate noise. For disturbance-decoupled systems, the unattenuated output of
the observer compensator is routed directly to the power converter, often increasing
the noise sensitivity by many times.

|     |     |     |     | 7.3 | NOISESENSITIVITY | WHENUSINGDISTURBANCEDECOUPLING |     |     |     | (cid:3) 157 |
| --- | --- | --- | --- | --- | ---------------- | ------------------------------ | --- | --- | --- | ----------- |
As was the case in Section 7.2,this section will start with an analytical discussion
of noise sensitivity based on transfer functions. First, the noise sensitivity of the
observed disturbance will be presented;a discussion of noise sensitivity of the actual
state will follow that.Finally,the key concepts from this section will be demonstrated
in VisualModelQexperiments.
| 7.3.1.1 | Transfer Function Analysis of D |     |     |     | /N  |     |     |     |     |     |
| ------- | ------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
O
The noise sensitivity of the observed disturbance can be derived from Figure 7-2 using
Mason’s signal flow graphs in a manner similar to how Equation 7.1 was derived.The
result is
|             |     | G     | (s)   |      |     | G (s)¥G   | (s)¥G |      | (s) |     |
| ----------- | --- | ----- | ----- | ---- | --- | --------- | ----- | ---- | --- | --- |
|             |     |       | CO    |      |     | PEst      | CO    | SEst |     |     |
| D (s)=Z(s)¥ |     |       |       |      | +P  | C (s)     |       |      | .   |     |
| O           | 1+G | (s)¥G | (s)¥G |      | (s) | 1+G (s)¥G | (s)¥G |      | (s) |     |
|             |     | PEst  | CO    | SEst |     | PEst      | CO    | SEst |     |     |
(7.16)
The Z(s) term is multiplied by G (s)¥G-1 (s) and by G (s)¥G-1 (s) in order to
|     |     |     | PEst |     | PEst | SEst | SEst |     |     |     |
| --- | --- | --- | ---- | --- | ---- | ---- | ---- | --- | --- | --- |
produce a factor of G (s) (see Equation 7.2).Then,Equation 7.16 can be in a form
OLPF
similar to Equation 7.4:
|     | D (s)=(Z(s)¥G-1 |     |      | (s)¥G-1 | (s)+P | (s))¥G | (s). | (7.17) |     |     |
| --- | --------------- | --- | ---- | ------- | ----- | ------ | ---- | ------ | --- | --- |
|     | O               |     | SEst |         | PEst  | C OLPF |      |        |     |     |
The  noise  sensitivity  of the  observer  can  be  written  in  a  form  similar  to
Equation 7.5:
|     |     | D (s) |      |         |       |      |     |        |     |     |
| --- | --- | ----- | ---- | ------- | ----- | ---- | --- | ------ | --- | --- |
|     |     | O     | =G-1 | (s)¥G-1 | (s)¥G | (s). |     | (7.18) |     |     |
|     |     |       | SEst |         | PEst  | OLPF |     |        |     |     |
N(s)
Comparing the noise sensitivity of the observed state (Equation 7.5) and of the
observed disturbance, the difference is that the observed disturbance adds the term
G-1 (s).If the plant is an integrator,as it commonly is,the inverse is a differentiator,
PEst
a function well known to be noise sensitive. The more that the simulated plant
attenuates noise, the greater the noise sensitivity of the observed disturbance.
7.3.1.2 Transfer-Function Analysis of C/N with Disturbance Decoupling
The sensitivity of the actual state to noise is the final measure on the control system.
The next step will be to investigate this by building the transfer function of C(s)/N(s).
To simplify transfer-function analysis, the disturbance-decoupled system is drawn in
Figure 7-12 by substituting Equation 7.17 in place of the common implementation
of the Luenberger observer. Just to be clear, the two implementations differ, but the
analysis is valid because transfer functions are the same.

| 158 (cid:2) | CHAPTER | 7 NOISEINTHE |       | LUENBERGEROBSERVER |       |       |      |       |       |      |
| ----------- | ------- | ------------ | ----- | ------------------ | ----- | ----- | ---- | ----- | ----- | ---- |
|             |         |              |       |                    |       |       |      | C(s)  | Y(s)  |      |
|             |         |              |       |                    |       |       | D(s) |       |       | N(s) |
|             |         |              |       |                    |       | P (s) |      |       |       | Z(s) |
|             |         | +            |       | +                  |       | C     | +    |       |       | +    |
|             |         |              | G (s) |                    | G (s) |       |      | G (s) |       |      |
|             | R(s)    |              |       |                    |       |       |      |       | G (s) |      |
|             |         |              | _ C   |                    | _ PC  |       |      | P     | S     |      |
|             |         |              |       |                    |       |       | +    |       |       | +    |
G -1 (s)
|     |     |     | Z(s) |     | D (s) |     |     |     |     | SEst |
| --- | --- | --- | ---- | --- | ----- | --- | --- | --- | --- | ---- |
O
|     |     |     |     | G    | (s) |     |     |     |     | -1    |
| --- | --- | --- | --- | ---- | --- | --- | --- | --- | --- | ----- |
|     |     |     |     | OLPF |     |     |     |     |     | G (s) |
|     |     |     |     |      |     |     |     |     | _   | PEst  |
+
Figure 7-12. Noise in an observer-based disturbance-decoupled system redrawn according to Equation 7.17.
The transfer function from N(s) to C(s) can be written using Mason’s signal flow
graphs.There are two paths from N(s) to C(s),one through the observer (P ) and the
1
other through the control law (P).There are three loops:one through the control law
2
|     | (L  | ) and two passing through the observer (L |          |         |           |         | and L). |           |      |            |
| --- | --- | ----------------------------------------- | -------- | ------- | --------- | ------- | ------- | --------- | ---- | ---------- |
|     | 1   |                                           |          |         |           |         | 2       | 3         |      |            |
|     |     | P                                         | =G-1     | (s)¥G-1 | (s)¥G     | (s)¥G   |         | (s)¥G (s) |      | (7.19)     |
|     |     |                                           | 1 SEst   |         | PEst      | OLPF    | PC      | P         |      |            |
|     |     | P                                         | =G (s)¥G |         | (s)¥G (s) |         |         |           |      |            |
|     |     |                                           | 2 C      | PC      | P         |         |         |           |      | (7.20)     |
|     |     | L                                         | =-G      | (s)¥G   | (s)¥G     | (s)¥G   | (s)     |           |      | (7.21)     |
|     |     |                                           | 1 C      |         | PC P      |         | S       |           |      |            |
|     |     |                                           |          |         |           | (s)¥G-1 | (s)¥G-1 |           |      |            |
|     |     | L                                         | =-G      | (s)¥G   | (s)¥G     |         |         | (s)¥G     |      | (s) (7.22) |
|     |     |                                           | 2 PC     |         | P S       |         | SEst    | PEst      | OLPF |            |
|     |     | L                                         | =G       | (s)¥G   | (s)       |         |         |           |      | (7.23)     |
|     |     |                                           | 3 PC     |         | OLPF      |         |         |           |      |            |
Since all loops touch (via G (s)), the denominator of the transfer function
PC
contains no combinations of loops.Since all forward paths touch all loops (again,via
G (s)), the cofactors, which appear in the numerator, are all 1. Thus, the transfer
PC
function is simply:
|     |     |     |     |     | C(s) |     | P +P |     |     |        |
| --- | --- | --- | --- | --- | ---- | --- | ---- | --- | --- | ------ |
|     |     |     |     |     |      |     | 1 2  | .   |     |        |
|     |     |     |     |     |      | =   |      |     |     | (7.24) |
|     |     |     |     |     | N(s) | 1-L | -L   | -L  |     |        |
|     |     |     |     |     |      |     | 1 2  | 3   |     |        |
Two assumptions simplify the transfer-function analysis. Assuming that the esti-
mated plant and estimated sensor are accurate, (G (s)(cid:2)G (s) and G (s)(cid:2)G (s)),
|     |     |     |     |     |     |     |     | P   | PEst | S SEst |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ---- | ------ |
L 2 and L 3 cancel in the denominator.Also, Equation 7.19 simplifies to:
|     |     |     |     |     | P ªG-1 | (s)¥G | (s)¥G | (s). |     | (7.25) |
| --- | --- | --- | --- | --- | ------ | ----- | ----- | ---- | --- | ------ |
|     |     |     |     |     | 1 SEst |       | OLPF  | PC   |     |        |

|     |     | 7.3 NOISESENSITIVITY | WHENUSINGDISTURBANCEDECOUPLING |     | (cid:3) 159 |
| --- | --- | -------------------- | ------------------------------ | --- | ----------- |
Figure 7-13. Experiment 7C: Noise in an observer-based disturbance-decoupled system.
The transfer function of noise sensitivity is then:
| C(s) | G-1 (s)¥G (s)¥G | (s)+G (s)¥G | (s)¥G | (s)    |     |
| ---- | --------------- | ----------- | ----- | ------ | --- |
|      | SEst OLPF       | PC C        | PC    | P .    |     |
| ª    |                 |             |       | (7.26) |     |
| N(s) | 1+G (s)¥G       | (s)¥G (s)¥G | (s)   |        |     |
|      | C               | PC P        | S     |        |     |
Equation 7.26 indicates that the disturbance-decoupled system has much greater
noise  sensitivity  than  does  the  system  with  observer  feedback  (Equation  7.8).
The denominators of Equations 7.8 and 7.26 are similar, but the first term in the
numerator of Equation 7.26, which represents the decoupling path from noise to
the actual state, bypasses the control law.2 The amplifying factor (G-1 (s)) lacks the
SEst
attenuating term G (s). In practice, the noise passing through the disturbance-
PEst
decoupling path,P,will normally be much larger than the noise passing through the
1
control-law path, P . (In fact, in many cases, P can be ignored.) This accounts for
|     | 2   | 2   |     |     |     |
| --- | --- | --- | --- | --- | --- |
the disturbance-decoupled system’s greatly increased noise sensitivity.
7.3.2 Experiment 7C: Noise Susceptibility and Disturbance Decoupling
This section will use Experiment 7C, shown in Figure 7-13, to demonstrate the
noise sensitivity of observer-based disturbance decoupling. This experiment is the
same as Experiment 7B with two exceptions. First, disturbance decoupling has
2The second term in the numerator represents the disturbance response of the control law based on
measured feedback.

160 (cid:2) CHAPTER 7 NOISEINTHE LUENBERGEROBSERVER
been added using the extenders named D to connect the output of the observer
O
compensator to the decoupling gain, K . The extender is preferred to a direct
DD
connection because it makes the diagram clearer by avoiding crossing wires.Second,
the LiveScopedisplay of C has been removed;a variable block,C ,has been added
O O
so the observed state can be plotted in the DSA and main scope.The greatly increased
noise sensitivity of the decoupled system is made readily apparent by the graph of
P , the power converter output, which is much noisier than it was in any of the
C
nondecoupled systems in earlier models (for example, in Figure 7-8).
The Bode plot of Experiment 7C shown in Figure 7-14 provides a measure of
the decoupled system’s noise sensitivity. This figure shows three configurations.
The traditional (nonobserver) configuration has the lowest sensitivity. The system
with observer feedback is more sensitive, as was demonstrated in Figure 7-10.
However, the disturbance decoupled system is the most sensitive. For example, at
100Hz, the decoupled system is 25dB (about 20 times) more sensitive than the
observer-based system and more than 40dB (100 times) more sensitive than the tra-
ditional system.Clearly,any consideration of observer-based disturbance decoupling
should include a thorough evaluation of noise sensitivity.
100 Hz
System using
observer-based
disturbance
decoupling
>40 dB
Traditional
system
System using
observed-state
for feedback
Figure 7-14. From Experiment 7C, noise sensitivity of the actual state for three configurations: traditional, the
observed-state feedback, and the observer-based disturbance-decoupled system.

7.4 REDUCINGNOISESUSCEPTIBILITYINOBSERVER-BASEDSYSTEMS (cid:3) 161
7.4 Reducing Noise Susceptibility in Observer-Based Systems
This section will review several techniques used to reduce noise susceptibility in
observer-based systems.
7.4.1 Lowering Observer Bandwidth
One technique to reduce noise sensitivity is to lower the observer bandwidth. While
the tuning procedures covered in earlier chapters focused on helping the designer tune
the compensator to get the maximum bandwidth available from the observer,in prac-
tical systems the observer’s target bandwidth may be reduced to attenuate noise.
Reducing the observer bandwidth will result in a direct benefit for noise suscepti-
bility. This is apparent upon inspection for systems using observed-state feedback
from Equation 7.9,understanding that reducing observer bandwidth is equivalent to
reducing the bandwidth of the equivalent filter G (s).It is also true for disturbance-
OLPF
decoupled systems according to Equation 7.26, assuming the first term in the
numerator of the right-hand side is dominant,as it normally will be.
The effect of lowering observer bandwidth is shown in Figure 7-15.This Bode plot
shows the noise susceptibility of the observer-based system (without disturbance
Observer system,
150 Hz observer bandwidth
Traditional system
(for reference)
Observer system,
90 Hz observer bandwidth
Figure 7-15. From Experiment 7B: Comparing the noise susceptibility of the observer-based system with
high- and low-observer bandwidth.

162 (cid:2) CHAPTER 7 NOISEINTHE LUENBERGEROBSERVER
decoupling) of Experiment 7C. There are three plots: (1) the 155-Hz observer loop
used through most of this chapter,(2) that same system with the observer loop tuned
down to 90Hz,and (3) the traditional system for reference.The observer-based system
compensated for 155Hz (K =0.1, K =45, K =6400) has the highest noise sus-
DO PO IO
ceptibility. The observer was tuned down to 90Hz (K =0.05, K =20, K =1400)
DO PO IO
using the procedure from Section 5.3.1, with K set to 0.05 to reduce noise. Tuning
DO
down the observer provided a modest reduction of 5dB (the ratio of the two observer
bandwidths,90/155) as is predicted by Equation 7.9.
The problem with reducing observer bandwidth is the system disturbance response
may worsen. For systems using the observed state for feedback, this is a concern
when the observer is near or below the control-loop bandwidth, as discussed in
Section 6.2.2. The reason is that the disturbance enters the control law only after
passing through the observer. Low-observer bandwidth will delay the perturbations
caused by the disturbance entering the observed state, which is the information the
control law has concerning the disturbance.
7.4.2 Reducing Noise in Disturbance-Decoupled Systems
Lowering the observer bandwidth will produce a similar benefit for systems with dis-
turbance decoupling,as is predicted by Equation 7.26.However,lowering the observer
bandwidth will degrade the disturbance response in the case where the observer
bandwidth is lower than the power converter bandwidth,as shown in Equation 6.15.
The primary limits on the disturbance response are the observer bandwidth, which
delays the disturbance signal, and the power converter, which delays the decoupling
signal entering the control system. The slower of the two will be the primary limit.
Lowering the primary limit will degrade the disturbance response.
An alternative means for reducing noise sensitivity when using disturbance de-
coupling is to add a low-pass filter in line with K , as in Experiment 7D as shown
DD
in Figure 7-16.The low-pass filter bandwidth is set with the LiveConstantDDLPF.
The improvement of noise susceptibility from the low-pass filter is demonstrated in
Figure 7-17. When the filter is reduced from 250 to 50Hz, the noise is attenuated
accordingly.
The degradation of disturbance response from the low-pass filter is shown in
Figure 7-18. The response to disturbances worsens (grows) with lower bandwidth
filtering on the observed disturbance. However, as long as the filter bandwidth is
more than about four times the power converter bandwidth,lowering the filter band-
width will have a negligible effect on disturbance response.
Adding a low-pass filter in line with the observed disturbance provides an observed
disturbance signal similar to that which would have been produced by lowering
the observer bandwidth. The primary benefit to the additional filter compared to
reducing observer bandwidth is that the filter can be used to lower the bandwidth
for decoupling, where noise susceptibility is so great, without reducing the observer
bandwidth. If observed-state feedback is used for other purposes, the benefits of

7.4 REDUCINGNOISESUSCEPTIBILITYINOBSERVER-BASEDSYSTEMS (cid:3) 163
Figure 7-16. Experiment 7D: Adding a low-pass filter in line with the observed disturbance in a
disturbance-decoupled system.
Noise susceptibility
with the low-pass
filter set at 250 Hz.
Noise susceptibility
with the low-pass
filter set at 50 Hz.
Figure 7-17. Noise susceptibility with the disturbance-decoupling filter set at 50 and 250Hz.

164 (cid:2) CHAPTER 7 NOISEINTHE LUENBERGEROBSERVER
Disturbance response
with the low-pass
filter set at 50 Hz.
Disturbance response
with the low-pass
filter set at 250 Hz.
Figure 7-18. Disturbance response with the disturbance-decoupling filter set at 50 and 250Hz.
high-observer bandwidth for that signal can be maintained.Since the noise sensitivity
of the observed-state feedback is so much less than that of the observed disturbance,
having the extra degree of design freedom brought by the decoupling filter will be of
benefit in some of the applications where both signals from the observer are used
simultaneously.
7.4.3 Modifying the Observer Compensator
Noise sensitivity can be reduced by modifying the observer compensator.This method
divides the observer compensator into two paths:high frequency and low frequency.
The high-frequency path is routed so that it does not contribute noise to the observed
disturbance or, optionally, to the observed state. (This is equivalent to the velocity
observer of [38,Figure 9].) This method provides similar benefits to reducing observer
bandwidth and to filtering the observed disturbance.The modified observer compen-
sator uses fewer computational resources than explicitly filtering the observed distur-
bance as shown in Figure 7-16. Like Figure 7-16, the restructured compensator has
the benefit of allowing the observed disturbance signal to be more heavily filtered than
the observed state.

7.4 REDUCINGNOISESUSCEPTIBILITYINOBSERVER-BASEDSYSTEMS (cid:3) 165
| 7.4.3.1 | Modified Structure |     |     |     |     |     |
| ------- | ------------------ | --- | --- | --- | --- | --- |
Modifying the observer compensator requires the following steps:
1. Divide G (s) into two components,a low-frequency component,G (s),and a
|     | CO  |     |     |     |     | COL |
| --- | --- | --- | --- | --- | --- | --- |
high-frequency component, G (s). Construct G (s) so that when multiplied
|     |     |     | COH | COH |     |     |
| --- | --- | --- | --- | --- | --- | --- |
by the simulated plant the product is a simple function such as a constant. The
two paths must sum to the original compensator:
|     |     | G   | (s)=G  | (s)+G (s). |     |     |
| --- | --- | --- | ------ | ---------- | --- | --- |
|     |     |     | CO COL | COH        |     |     |
For example, for an integrating plant, the D-path of the observer compen-
sator could form G (s) while the I-path and P-path would form G (s).Here,
|     |     | COH |     |     |     | COL |
| --- | --- | --- | --- | --- | --- | --- |
when G (s) (K ¥s) is multiplied by the plant (K /s),the result is the constant
|                                             | COH DO                                           |     |     |           | Est |     |
| ------------------------------------------- | ------------------------------------------------ | --- | --- | --------- | --- | --- |
| K ¥K                                        | ,which certainly qualifies as a simple function. |     |     |           |     |     |
| DO                                          | Est                                              |     |     |           |     |     |
| 2. Form the observed disturbance with the G |                                                  |     |     | (s) path. |     |     |
COL
3. Form the observed state with the G COL (s) path. An alternative is to form the
observed state with both paths of the observer compensator.Using this alterna-
tive will allow the equivalent of filtering the observed disturbance without affect-
ing the observed state.
The modified observer is shown in Figure 7-19.The compensator is divided in two
and each path proceeds through an independent simulated plant.As stated above,the
| D(s)        |     |       |      |       | Y(s) |      |
| ----------- | --- | ----- | ---- | ----- | ---- | ---- |
|             | +   |       | C(s) |       |      |      |
| Disturbance |     | G (s) |      | G (s) |      | Z(s) |
|             |     | P     |      | S     |      |      |
Actual
|     | +   |     |     |     | + + | Actual |
| --- | --- | --- | --- | --- | --- | ------ |
state
|       |     | Plant |                 | Sensor |      | sensor |
| ----- | --- | ----- | --------------- | ------ | ---- | ------ |
| P (s) |     |       |                 |        | N(s) |        |
| C     |     |       | Physical system |        |      | output |
Noise
Plant
| excitation | D   | (s) |       |     | E (s) | +   |
| ---------- | --- | --- | ----- | --- | ----- | --- |
|            |     | O   |       |     | O     |     |
|            |     |     | G (s) |     |       |     |
COL
|          |     |     |       | Two-path observer  | Observer  | _   |
| -------- | --- | --- | ----- | ------------------ | --------- | --- |
|          |     |     |       | compensation       | error     |     |
| Observed |     |     | G (s) |                    |           |     |
COH
disturbance
G (s)
PEst
|     | +   |       | C (s)    | +C (s)     |        |          |
| --- | --- | ----- | -------- | ---------- | ------ | -------- |
|     |     | G     | (s) OMod | O          | G (s)  | Y (s)    |
|     |     | PEst  |          |            | SEst   | O        |
|     | +   |       | Modified | + Standard |        |          |
|     |     |       |          | observed   |        | Observed |
|     |     | Plant | observed |            | Sensor |          |
|     |     |       |          | state      |        | sensor   |
state
output
Modeled system
|     | Figure 7-19. | Luenberger observer with modified observer compensator. |     |     |     |     |
| --- | ------------ | ------------------------------------------------------- | --- | --- | --- | --- |

| 166 (cid:2) | CHAPTER | 7 NOISEINTHE | LUENBERGEROBSERVER |     |     |     |     |     |     |     |
| ----------- | ------- | ------------ | ------------------ | --- | --- | --- | --- | --- | --- | --- |
product of G COH (s) and G PEst (s) should be a simple function such as a constant. In
the actual implementation, only the product of the two is evaluated to reduce com-
putations. A common case is where the estimated plant is fully integrating (K /s),
Est
and G (s) is the D-path (K ¥s) of the observer compensator. Here, the path
|     |           | COH |           |                                   | DO  |     |     |     |        |     |
| --- | --------- | --- | --------- | --------------------------------- | --- | --- | --- | --- | ------ | --- |
|     | through G |     | (s) and G | (s) is evaluated in one step as K |     |     |     |     | ¥K     | .   |
|     |           | COH |           | PEst                              |     |     |     |     | Est DO |     |
Note that there are two choices for the observed state.The modified observed state,
C (s), is derived using only G (s). The standard observed state, C (s), is con-
|     | OMod |     |     |     |     | OL  |     |     |     | O   |
| --- | ---- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
structed using the sum of G (s) and G (s). It is a straightforward matter to show
|     |     |     |     |     | OH  | OL  |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
that C (s) in Figure 7-19 is equivalent to C (s) in the traditional Luenberger observer
|     |     | O   |     |     |     |     | O   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
used throughout this book.
|     | 7.4.3.2 | Modifying the Compensator for Nonintegrating Plants |     |     |     |     |     |     |     |     |
| --- | ------- | --------------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
If the plant is something other than a pure integration, this method can still be
applied. For example, suppose the plant is a leaky integrator such as a temperature
bath that leaks heat to the atmosphere or a motion system with viscous damping.
Such a form is equivalent to a scaled low-pass filter as shown in Equation 7.27.Here
|     | K Leak is one over the time constant of |     |     |     |     | the leakage: |     |     |     |     |
| --- | --------------------------------------- | --- | --- | --- | --- | ------------ | --- | --- | --- | --- |
K
|     |     |     |     |     | G   | (s)= | Est | .   |     | (7.27) |
| --- | --- | --- | --- | --- | --- | ---- | --- | --- | --- | ------ |
PEst
s+K
Leak
Since the plant is not a pure integration,modifying the observer compensator with
G COH (s)=K DO ¥s fails to meet the criterion where G COH (s)¥G PEst (s) is to be a simple
function such as a constant.However,if a portion of the compensator’s proportional
gain is placed into G (s), then the criterion is met: G (s)=(1+K /s)¥K ¥s.
|     |     |     | COH |     |     |     |     |     | COH | Leak DO |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------- |
Since G (s) now contains a portion of the proportional gain (K ¥K ),the pro-
|     |     | COH |     |     |     |     |     |     |     | Leak DO |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------- |
portional gain in G (s) must be reduced by that same amount. So,
COH
Ê K Leakˆ
|     |     |     | G   | (s)= | 1+  | K    | ¥s  |     |     | (7.28) |
| --- | --- | --- | --- | ---- | --- | ---- | --- | --- | --- | ------ |
|     |     |     | COH |      | Ë   | ¯ DO |     |     |     |        |
s
|     |     |     | G   | (s)¥G | (s)=K |     | ¥K  |     |     | (7.29) |
| --- | --- | --- | --- | ----- | ----- | --- | --- | --- | --- | ------ |
|     |     |     | COH |       | PEst  | Est | DO  |     |     |        |
K
IO
|     |     |     | G   | (s)= | +(K | -K  | ¥K   | )   |     | (7.30) |
| --- | --- | --- | --- | ---- | --- | --- | ---- | --- | --- | ------ |
|     |     |     | COL |      | s   | PO  | Leak | DO  |     |        |
K
IO
|     |     |     | G   | (s)=G | (s)+G | (s)= |     | +K  | +K ¥s. | (7.31) |
| --- | --- | --- | --- | ----- | ----- | ---- | --- | --- | ------ | ------ |
|     |     |     | CO  |       | COH   | COL  | s   | PO  | DO     |        |
In this case,the two compensator paths still sum to the original G (s) as indicated
CO
by Equation 7.31.In addition,the evaluation of the high-frequency path observer is
still computationally efficient owing to Equation 7.29. The only complexity intro-
duced by the nonintegrating plant is that the proportional gain of the compensator
must be reduced as indicated in Equation 7.30.

7.4 REDUCINGNOISESUSCEPTIBILITYINOBSERVER-BASEDSYSTEMS (cid:3) 167
7.4.4 Transfer-Function Analysis
The transfer-function analysis provides an analytical understanding of modifying
the observer compensator. The observed state and observed disturbance can be
evaluated separately. Using Mason’s signal flow graphs, the observed state can be
written as:
C (s) G (s)¥G (s)
O = COL PEst . (7.32)
N(s) 1+(G (s)¥G (s)+G (s)¥G (s))¥G (s)
COH PEst COL PEst SEst
Making use of Equation 7.31,Equation 7.32 simplifies to:
C (s) G (s)¥G (s)
O = COL PEst . (7.33)
N(s) 1+G (s)¥G (s)¥G (s)
CO PEst SEst
Using some algebra,Equation 7.33 can be written as:
C (s) G (s) G (s)¥G (s)¥G (s)
O = COL ¥G-1 (s)¥ SEst CO PEst . (7.34)
N(s) G (s) SEst 1+G (s)¥G (s)¥G (s)
CO CO PEst SEst
Recalling the formula for G (s) as shown in Equation 7.2, Equation 7.34
OLPF
reduces to
C (s) G (s)
O = COL ¥G-1 (s)¥G (s). (7.35)
N(s) G (s) SEst OLPF
CO
Comparing Equation 7.35 to the standard sensitivity as shown in Equation 7.5,
the effect of modifying the observer amounts to cascading the transfer func-
tion G (s)/G (s). Since G (s) is the low-frequency path of G (s), the term
COL CO COL CO
G (s)/G (s) attenuates higher frequencies. In other words, the modified compen-
COL CO
sator is effectively a low-pass filter. The same effect can be seen when evaluating
the observed disturbance. Using a similar technique to that above, it can be shown
that
D (s) G (s)
O = COL ¥G-1 (s)¥G-1 (s)¥G (s). (7.36)
N(s) G (s) SEst PEst OLPF
CO
Comparing Equation 7.36 to the standard observer compensator of Equation 7.18,
the same filtering term (G (s)/G (s)) appears with the modified compensator.
COL CO
So, for both outputs of the observer, the difference between the standard and the
modified compensator is the introduction of a filtering term.

168 (cid:2) CHAPTER 7 NOISEINTHE LUENBERGEROBSERVER
7.4.5 Experiment 7E: Evaluating the Modified Observer Compensator
Experiment 7E, shown in Figure 7-20, is a system with an observer that can be con-
figured to feed back the standard or modified observed state. The modified observer
has a G (s) path using K and a K block and a G (s) path using G and a
COH DO Est COH CO
second K block. The control loop can be configured for one of three feedback
Est
signals:(1) the sensor,(2) the standard observed state,and (3) the modified observed
state;the configuration is selected with the LiveConstant“Feedback”which can take
on the values of “Sensor,”“Observer,”and “Mod.Obs.”The selected feedback signal
connects to the variable “F.”
Results of Experiment 7E are shown in Figure 7-21. The noise susceptibility of
the standard and modified observed states is plotted. As expected, the modified
observed state is similar to the standard observed state at low frequencies but is attenu-
ated above a frequency (about 70Hz). This is consistent with the modified observed
state being a filtered version of the standard observed state,as shown in Equation 7.35.
Incidentally, the disturbance response does not suffer measurably from the use of
the modified observed state,because 70Hz is still much greater than the control-loop
bandwidth (about 25Hz,from Figure 5-9).As demonstrated in Equation 6.14,in the
event of a wide separation of the control-loop bandwidth and the observer band-
width,the disturbance response of nondisturbance-decoupled systems will be limited
by the lesser of the two.
Figure 7-20. Experiment 7E: Modified observer compensator.

7.4 REDUCINGNOISESUSCEPTIBILITYINOBSERVER-BASEDSYSTEMS (cid:3) 169
Noise susceptibility of
standard observed state
Noise susceptibility of
modified observed state
Figure 7-21. From Experiment 7E: Noise susceptibility of feedback signal, with system configured for standard
and modified observed state feedback.
7.4.6 Using the Modified Observer Solely for D
O
One feature of the modified observer is that it can be applied solely to the observed
disturbance. Referring to Figure 7-19, if the standard observed state, C (s), is used
O
for feedback, only the observed disturbance will be affected by the modified com-
pensator.The benefit of this structure is that the observed disturbance is more heavily
filtered than the observed state. As demonstrated in the analysis and simulations
throughout this chapter,the observed disturbance is much more sensitive to noise than
is the observed state.Thus by taking the observed disturbance from the right side of
the summing junction, the implicit filtering offered by the modified compensator is
applied where it is most needed:to the observed disturbance.This will,in some cases,
eliminate the need to provide an explicit filter on the observed disturbance as shown
in Figure 7-16. For a system simultaneously using the observed disturbance and
the observed state, reducing the observer bandwidth still can be used to reduce the
sensitivity of both signals simultaneously. In this case, the observer-compensator
gains could be reduced until the sensitivity of the actual state is acceptable;then the
modified compensator could be applied to reduce the sensitivity of the observed
disturbance.

| 170 (cid:2) | CHAPTER 7 NOISEINTHE | LUENBERGEROBSERVER |     |      |       |     |      |     |
| ----------- | -------------------- | ------------------ | --- | ---- | ----- | --- | ---- | --- |
|             | D(s)                 |                    |     |      |       |     | Y(s) |     |
|             |                      | +                  |     | C(s) |       |     |      |     |
|             | Disturbance          |                    | G   | (s)  | G (s) |     |      |     |
Z(s)
|     |     |     | P   | Actual | S   |     |     |        |
| --- | --- | --- | --- | ------ | --- | --- | --- | ------ |
|     |     | +   |     |        |     |     | + + | Actual |
state
|     |       |     | Plant |                 | Sensor |     |      | sensor |
| --- | ----- | --- | ----- | --------------- | ------ | --- | ---- | ------ |
|     | P (s) |     |       |                 |        |     | N(s) |        |
|     | C     |     |       | Physical system |        |     |      | output |
Noise
Plant
E (s)
|     | excitation | D   | (s) |     |     |       | O   | +   |
| --- | ---------- | --- | --- | --- | --- | ----- | --- | --- |
|     |            |     | O   |     |     | G (s) |     |     |
COL
_
|     |     | +   |     | 1-Mod |     |     |     |     |
| --- | --- | --- | --- | ----- | --- | --- | --- | --- |
+
|     |     |     |     | Mod |     | G (s) |     |     |
| --- | --- | --- | --- | --- | --- | ----- | --- | --- |
COH
G (s)
PEst
|     |                                                    | +   |              |                              | +C       |        |     |          |
| --- | -------------------------------------------------- | --- | ------------ | ---------------------------- | -------- | ------ | --- | -------- |
|     |                                                    |     |              | C (s)+                       | (s)      |        |     |          |
|     |                                                    |     | G            | (s) OM                       | O        | G      | (s) | Y (s)    |
|     |                                                    |     | PEst         |                              |          | SEst   |     | O        |
|     |                                                    | +   |              | Modified                     | Standard |        |     |          |
|     |                                                    |     |              | observed                     | observed |        |     | Observed |
|     |                                                    |     | Plant        |                              |          | Sensor |     |          |
|     |                                                    |     |              | state                        | state    |        |     | sensor   |
|     |                                                    |     |              | Modeled system               |          |        |     | output   |
|     |                                                    |     | Figure 7-22. | Gradually modified observer. |          |        |     |          |
|     | 7.4.7 Modifying the Observer Compensator Gradually |     |              |                              |          |        |     |          |
This choice of using the modified observer at first appears to lack the option of partial
implementation. The designer can use the standard or the modified structure, but
nothing in between. However, the modified observer structure of Figure 7-19 can be
implemented gradually by routing only a portion of G (s) through the modified
COH
path. The remainder of G (s) is added to G (s). This is shown in Figure 7-22
|     |     |     | COH |     | COH |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
where the constant Mod controls the amount that the compensator is modified.
When Mod=0, the observer is configured as a standard Luenberger observer; when
Mod=1,the observer is equivalent to the modified structure of Figure 7-19.Any value
of Mod between 0 and 1 will be a combination of the two, having some portion of
the benefits and disadvantages of each. This technique can be used when some
filtering is needed but not so much filtering as is provided by the modified observer.
|     | 7.5 Exercises |     |     |     |     |     |     |     |
| --- | ------------- | --- | --- | --- | --- | --- | --- | --- |
1. Investigate the effects of observer bandwidth on the noise susceptibility of the
observed state to sensor noise.Use three sets of tuning gains for the following

7.5EXERCISES (cid:3) 171
exercise: high frequency (K =0.1, K =45, K =6400), medium frequency
DO PO IO
(K =0.05, K =17, K =2000), and low frequency (K =0.02, K =8.5,
DO PO IO DO PO
K =200).
IO
A. Use Experiment 5A to measure the observer bandwidth of all three sets of
gains.
B. Use the DSA in Experiment 7A to measure the noise susceptibility of the
observed state to sensor noise with all three sets of gains.
C. Monitor the noise as shown by the Live Scope for C in Experiment 7A.
O
Set the gains to the low-frequency set. Now, change the gains to the
medium-frequency set, one-by-one, monitoring the Live Scope display.
Repeat for high-frequency gain set.Can you determine the change in noise
sensitivity when changing the gains by watching the Live Scope? If so,
which of the three observer tuning gains has the predominant effect on
noise susceptibility?
2. Evaluate noise sensitivity of the power converter output. Recall from
Section 7.2.3 that the noise on the power converter output is often a good
indicator of audible noise coming from the controller. Use Experiment
7B.
A. Using the PC Live Scope display for an approximate measurement, what
are the peak-to-peak excursions of the power converter due to noise of the
traditional (sensor-feedback) system?
B. Change the feedback Live Constant (lower left) to Observer to convert
the feedback to observer based.Repeat part A with default (high frequency
from Exercise 7-1) observer gains.
C. Repeat part A after raising control-loop gains as would normally be done
to take advantage of the reduced phase lag of the observer-based system
(K =1.5,K =30).
P I
D. Using the DSA of Experiment 7B, run Bode plots and evaluate the high-
frequency sensitivity of the PC Output for all three cases. Compare the
results to parts A–C.
3. Compare observer-based disturbance-decoupled and nondecoupled systems
using Experiment 7D.Open the file Experiment_7D.mqdand save as Temp.mqd
to avoid permanent changes to the file. Disconnect the WaveGen block from
the command input and connect it to the unswitched input node of the dis-
turbance DSA (right column,bottom node).At this point,the waveform gen-
erator will inject a disturbance into the system.This allows you to monitor the
time-domain disturbance response in the LiveScopes.
A. Using the Live Scope, what is the peak-to-peak excursion of the
non-decoupled system when observer feedback is used and control-
loop gains are raised accordingly (K =1.5, K =30, K =0, Feedback=
P I DD
Observer)?
B. Use disturbance decoupling (set K =1 and K =0).What is the excursion?
DD I
C. Can you see signs of greater noise susceptibility when disturbance decou-
pling is enabled?

172 (cid:2) CHAPTER 7 NOISEINTHE LUENBERGEROBSERVER
D. Reduce the disturbance-decoupling low-pass filter (DD LPF) until the
excursion is equivalent to the nondecoupled system of part A.What is the
value of the filter?
E. Based on the noise and disturbance DSAs, compare the two systems and
comment.

Chapter 8
Using the Luenberger
Observer in
Motion Control
In this chapter...
• Overview of motion-control and motion-feedback sensors
• Applying observers to improve velocity sensing in encoder and resolver systems
• Applying observers to improve disturbance response in motion systems
• Implementing acceleration feedback based on observed signals
This chapter will discuss several applications of the Luenberger observer in
motion-control systems. First, an overview of the operation of motion-control
systems is provided. Applications that are likely to benefit from observer technology
are presented.The chapter then presents the use of the observer to improve two areas
of performance: command response and disturbance response. Command and
disturbance response are improved because observed feedback, with its lower phase
lag, allows higher loop gains. Disturbance response is further improved through the
use of two methods: disturbance decoupling and acceleration feedback. As with
earlier chapters,key points will be demonstrated with software experiments.
8.1 The Luenberger Observers in Motion Systems
Motion-control systems are used in a wide range of applications.These applications
fall into two broad categories: discrete and continuous operations. In discrete
operations,a part is being cut,processed,moved,assembled,or otherwise manufactured.
For example,a machine tool may cut metal away from a cast part or a form-fill-and-
seal machine might produce a bag ofpotato chips.Continuous operations run without
173

174 (cid:2) CHAPTER 8 USING THE LUENBERGEROBSERVER IN MOTION CONTROL
a definitive end. One example is a machine that produces masking tape, which pulls
a roll of paper through a process where adhesive and other coatings are applied.
Motion-control systems are implemented with a number of motor technologies.
The lowest cost applications are run open loop and do not rely on feedback control
loops. For example, stepper motors are usually controlled open loop; they provide
an inexpensive way to make discrete moves while controlling position.Variable-speed
drives for induction motors,often referred to as variable frequency ACor VFACdrives,
can control motor speed to within a few percentage points without requiring a feed-
back device. This technology is often used in applications where position control is
not needed,such as when controlling pumps and fans.
The motion-control applications that demand the highest performance are usually
implemented with closed-loop servo systems. The term servo here implies closing
velocity and position loops based on physical sensors. Servo systems are among the
most complicated motion-control systems to specify and install,and they are usually
the most expensive. Engineers select servo systems when the performance of the
application demands it.This chapter will focus wholly on servo systems.
8.1.1 Performance Measures
The main measures of performance in servo systems are noise generation,disturbance
response, command response, and stability. Servo systems excel in command and
disturbance response. Servomotors are often the technology of choice in discrete
operations, where the moves must be rapid, and in continuous operations, where the
system must hold constant speed in the presence of disturbances.
Noise susceptibility and stability are often problems for servo systems. The high
gains needed to respond to rapidly changing commands or high-frequency distur-
bances also respond to noise on the sensor and command inputs, often generating
considerable noise to the system output.Stability is a problem because designers often
push the loop gains as high as possible to maximize response and,in doing so,press
the limits of stability margins. As has been discussed in earlier chapters, Luenberger
observers are a practical way to deal with stability limitations and so indirectly allow
servo gains to be increased. On the other hand, as was the focus of Chapter 7,
observers can exacerbate problems with sensor noise.
8.1.2 Servo Control
This section will provide a brief overview of servo control. This material is covered
in detail in [11, Chapters 14 and 16]. Servo control here is defined as closed-loop
control of velocity or position. In this context, servo control does not include
the functions associated with generating torque such as current loops or electronic
commutation, the process of channeling current in multiple-winding motors. The
assumption here is that the servo loops generate the torque command and other
sections of the system control current in order to generate that torque.

|     |     |     |     |       | 8.1 | THE LUENBERGEROBSERVERS | INMOTIONSYSTEMS |     | (cid:3) 175 |
| --- | --- | --- | --- | ----- | --- | ----------------------- | --------------- | --- | ----------- |
|     |     | P   | V V |       |     | I                       | I               | P   |             |
|     |     | E   | C   | E K + |     | C Current               | F               | 1 M |             |
P
|      | C   | K   |     | VI  | K   | loops and   | K   |      |     |
| ---- | --- | --- | --- | --- | --- | ----------- | --- | ---- | --- |
|      | +   | P   | +   | s   | VP  |             | T   | J s2 |     |
| From |     | -   | -   | +   |     | commutation |     | T    |     |
V
| profile |     | P   | F   |     |     |     |     |     |     |
| ------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
F
| gen. |     |     | s   |     |     |     |     |     |     |
| ---- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
P
|     |     |     |     |     |     | F Position |     |     |     |
| --- | --- | --- | --- | --- | --- | ---------- | --- | --- | --- |
sensor
Simplified
|     | Position   |     |             | Velocity                                  |     |     |                |     |     |
| --- | ---------- | --- | ----------- | ----------------------------------------- | --- | --- | -------------- | --- | --- |
|     | controller |     | controller  |                                           |     |     | motor and load |     |     |
|     |            |     | Figure 8-1. | Traditional cascaded servo control loops. |     |     |                |     |     |
Figure 8-1 shows a cascaded servo loop.The position loop is in series or cascaded
with the velocity loop. In most servo applications the position command, P , is
C
generated by a profile or trajectory generator. The position command is compared
to the feedback to generate a position or following error. That error is scaled by a
position-loop proportional gain, K P , to create a velocity command, V C . The velocity
loop compares this command to the velocity feedback to create a velocity error.The
velocity feedback is commonly created by differentiating the position feedback signal.
The velocity control law, which is shown as a PI controller, generates the torque
command. For most servomotors, the magnitude of current is approximately pro-
portional to torque and so this signal is commonly used as a current command.
The current signal is fed to the motor control algorithms—current loops and com-
mutation algorithms for brushless motors—which produce motor current in order to
generate the torque that will satisfy the loops.The model of the motor here is a simple
motor torque constant, which converts current to torque, and a single rotational
inertia, J T .
There are variations of cascaded loops,for example,where the position loop uses
a PI law and the velocity loop uses a proportional law.The defining characteristic of
the cascaded structure is the use of position error to generate velocity command and
the use of velocity error to generate current command.The different variants provide
similar performance in similar applications, although the tuning procedures vary
considerably.
|     | 8.1.2.1 | Feed-Forward |     |     |     |     |     |     |     |
| --- | ------- | ------------ | --- | --- | --- | --- | --- | --- | --- |
Feed-forward is commonly used to improve command response. The command or,
more accurately,derivatives of the command are fed ahead of the position loop.This
is shown in Figure 8-2 where commanded velocity (V ) and acceleration (A ) are
|     |     |     |     |     |     | PC  |     | PC  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
fed ahead to the velocity and current loops, respectively. The profile generator can
usually provide commanded acceleration and velocity easily since these signals are

176 (cid:2) CHAPTER 8 USING THE LUENBERGEROBSERVER IN MOTION CONTROL
A
PC K
FA
Acceleration feed-forward path
V Velocity feed-forward
PC K FV path I C I F
P V V P
P C + E K + C E K VI K + lo C o u p r s re a n n t d K T 1 M
_ P + V + _ s + + VP + commutation J T s2
P F
F
s
From P
profile F Position
generator sensor
Figure 8-2. Cascaded servo loops with feed-forward.
required to calculate the position command.These signals are fed ahead of the loops
so that the inner control loops can respond immediately to the command rather than
having to wait for an error signal to percolate through the relatively slow position
loop.
Feed-forward is a well-proven technique for improving command response.It does
so without increasing the servo gains and thus does not aggravate stability problems
or problems from sensor noise.However,the technique is largely unrelated to the most
common uses of observers in servo systems and so will not be discussed in detail here.
8.1.2.2 Position vs Velocity Control
Position control is needed for almost all discrete processes. The execution of a dis-
crete process usually requires a mechanism to start and end in known positions.Such
motions might be needed to move a silicon wafer,wrap a candy bar,or sew a sequence
of stitches.In each case,position control is required to ensure that the sequence begins
at the correct position. However, for continuous processes, position control may not
be needed. A machine that coats photographic paper usually need not be synchro-
nized to the position of the roll from which the paper comes. Here the servo system
need only maintain a constant tension in the coating process, a function that often
requires only velocity control.In such cases,the position-loop portion of the cascaded
loops shown in Figure 8-1 can be eliminated.
Whether or not a position loop is present, most of the performance issues of a
servo system occur in the velocity loop. The velocity loop determines the maximum
bandwidth of the control system, even when a position loop is used. This is because
the velocity-loop bandwidth is the upper limit of the position-loop gain. High-gain
velocity loops are required for high-gain position loops to be stable. So, improving
the velocity loop is the primary challenge to those seeking to improve servo-system

|     |     |     |     | 8.1 | THE LUENBERGEROBSERVERS |     | INMOTIONSYSTEMS | (cid:3) 177 |
| --- | --- | --- | --- | --- | ----------------------- | --- | --------------- | ----------- |
A
| PC  | K   |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
FA
K
V
| PC  |     | FV  |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
1
K
|     |     | s PI |     |     |     | I   |     |     |
| --- | --- | ---- | --- | --- | --- | --- | --- | --- |
F
|     |     |     |     | +   | I C u r re n t  |     | P   |     |
| --- | --- | --- | --- | --- | --------------- | --- | --- | --- |
|     | + P |     | +   | +   | C               | K   | 1 M |     |
| P   | E   | K   |     |     |                 |     | T   |     |
| C   |     | PP  |     |     | l oo p s  a n d |     | s 2 |     |
|     |     |     | +   | +   |                 | J   |     |     |
|     | -   |     | +   |     | commutation     |     |     |     |
F r o m   P
|              |     | s K |     |     |     |     |     |     |
| ------------ | --- | --- | --- | --- | --- | --- | --- | --- |
| pr o f il e  | F   | PD  |     |     |     |     |     |     |
V
generator
|     |     | E   |     |     | P          |     |     |     |
| --- | --- | --- | --- | --- | ---------- | --- | --- | --- |
|     |     |     |     |     | F Position |     |     |     |
sensor
|     |     | Figure 8-3. |     | PID servo control. |     |     |     |     |
| --- | --- | ----------- | --- | ------------------ | --- | --- | --- | --- |
performance.Recognizing this,the discussion and examples of this chapter will focus
on the velocity loop.
8.1.2.3 PID Position Loop
A common alternative to the cascaded velocity control loop is the PID position loop.
Here there is no explicit velocity loop.Instead,the position error is operated on by a
single PID control law.This is shown in Figure 8-3,which includes feed-forward terms.
The PID position loop is quite similar in operation to the cascaded position–
velocity loop.For example,the gain K in Figure 8-3 operates on velocity error much
PD
as the gain K does in Figure 8-2.In fact,the high-frequency operation of both loops
VP
is almost identical when the two are tuned equivalently. The PID position loop will
not be discussed here in detail since its operation is so similar to the cascaded loop.
The focus here is the PI velocity loop of Figure 8-2, which is roughly equivalent to
| the gains K | and K in Figure 8-3. |     |     |     |     |     |     |     |
| ----------- | -------------------- | --- | --- | --- | --- | --- | --- | --- |
| PD          | PP                   |     |     |     |     |     |     |     |
8.1.3 Common Motion-System Sensors
This section will discuss the most common sensors used to close servo loops. This
material is covered in detail in [11,Chapter 13].
8.1.3.1 Tachometer
A tachometer is an electromagnetic device that produces an analog voltage that is
proportional to motor speed. Tachometers or tachs provide highly resolved, low-
phase-lag velocity signals that are ideal for closing velocity loops. In the past, most

178 (cid:2) CHAPTER 8 USING THE LUENBERGEROBSERVER IN MOTION CONTROL
servo systems relied on tachs for velocity feedback.Unfortunately,the tachometer has
numerous shortcomings that have eliminated it from most high-performance motion-
control systems.
The primary shortcoming of a tachometer is cost.Since most servo systems must
have a position sensor,using a tachometer implies the need for two sensors.The cost
of the tachometer itself is substantial,as is the cost of mounting the unit and cabling
to it.A second problem with tachometers is brush wear.Tachometers are essentially
DC generators,which require carbon brushes to carry voltage between the stator and
the rotor.Over time these brushes wear and must be replaced.
Analog tachs are commonly used in low-cost analog servo systems. Their cost is
offset by allowing the use of simple,low-cost analog controllers.A small brush motor
and a simple analog drive based on tach feedback often cost much less than a
digitally controlled brushless-DC servo system.
Tachs are also occasionally used for high-performance servo systems,especially for
very low-speed applications. Because a tach is an analog device, it has no explicit
resolution limitations in the way that a digital feedback device does. When tachs are
wound for high sensitivity (i.e.,high-voltage output at relatively low speeds),they can
provide high-quality speed signals for low-speed systems.
Tachs are applied at both ends of the servo-performance spectrum—in the lowest
cost analog servo systems and high-end systems where precision tachs are used to
provide high-resolution velocity feed back.However,most applications rely on a single
position sensor from which velocity is derived. Here, the position sensor has domi-
nated as it can feed back a position signal and,indirectly,a velocity signal.The most
popular position sensors are encoders and resolvers.
8.1.3.2 Encoders
The optical incremental encoder is probably the most popular position feedback
device in modern servo systems.Optical encoders affix an opaque mask to the motor
rotor; as the rotor changes position, the pattern of light passing through the mask
changes. The encoder produces electronic pulses as the light intensity varies up and
down through a certain set point. The optical mask is designed to produce a cyclic
pattern of variation that repeats hundreds or thousands of times for each revolution
of the motor. The result is that the incremental encoder produces typically between
250 and 5000 counts of position information for each motor revolution.These pulses
are produced in proportion to the distance traveled by the encoder. The pulses are
counted in the control system to determine how far the encoder rotor has moved.
8.1.3.3 Resolver
Resolvers are electromagnetic devices that are used to sense position. Resolvers, as
shown in Figure 8-4,are multiwinding transformers in which the transformation ratio
varies with the position of the rotor. A reference winding, REF, transmits power on

|     |     | 8.1 THE LUENBERGEROBSERVERS | INMOTIONSYSTEMS | (cid:3) 179 |
| --- | --- | --------------------------- | --------------- | ----------- |
Free-running
|     | REF = sin( | t)  |     |     |
| --- | ---------- | --- | --- | --- |
wRD sinusoidal
oscillator
Position
SIN=
feedback
|     | sin( t)xsin(P | )   |     |     |
| --- | ------------- | --- | --- | --- |
|     | wRD RES       |     | to  |     |
Resolver-to-
control
Digital
loops
|     |      | Converter  | .   |     |
| --- | ---- | ---------- | --- | --- |
|     | COS= | (RDC)      | .   |     |
.
|     | sin( wRD t)xcos(P | )   |     |     |
| --- | ----------------- | --- | --- | --- |
RES
| Stator Rotor |     |     |     |     |
| ------------ | --- | --- | --- | --- |
(Carrier) (AM signals)
Control system
Resolver
|     | Figure 8-4. Standard resolver connections. |     |     |     |
| --- | ------------------------------------------ | --- | --- | --- |
a  carrier  wave  of typically  about  5kHz  to  the  resolver  rotor. The  two  return
windings, SIN and COS, are coupled to the rotor winding where the magnitude
of coupling varies with the position of the rotor. The coupling between rotor and
SINwinding varies according to the sine of the resolver position;the coupling to the
COSwinding varies with the cosine.The SINand COSwindings are then amplitude-
modulated  (AM)  signals  encoding  the  position  of the  rotor  on  the  reference
carrier.
The conversion of resolver feedback windings to a position signal is more com-
plex than the conversion of incremental encoders.Incremental encoders require only
that pulses be counted over time. Resolvers require a scheme that can remove the
carrier and provide the necessary trigonometry to produce a measured position.The
most common scheme used today is probably the tracking or double-integrating con-
verter,shown in Figure 8-5.This is a depiction of a typical single integrated-chip (IC)
resolver-to-digital (R-D) converter where the conversion process is accomplished with
digital and analog components [1,8].
The double-integrating converter is a closed-loop control system in itself. First,
the SINand COSsignals are demodulated to remove the carrier.Simultaneously,an
up–down counter keeps track of the converted position, P . The demodulated SIN
RD
and COS signals represent the sine and cosine of the actual position, P RES . These
signals are multiplied by the cosine and sine, respectively, of the converted position
(P )  to  form  cos(P )¥sin(P )-sin(P )¥cos(P ). By  the  trigonometry
| RD  | RES RD | RES RD |     |     |
| --- | ------ | ------ | --- | --- |
identity  sin(A-B)=cos(B)¥sin(A)-sin(B)¥cos(A), this  can  be  seen  to  equal

180 (cid:2) CHAPTER 8 USING THE LUENBERGEROBSERVER IN MOTION CONTROL
Resolver windings
|       |       |       |     | sin(P -P   | )   |      |     |
| ----- | ----- | ----- | --- | ---------- | --- | ---- | --- |
| SIN   |       | sin(P | )   | RES  RD    |     |      |     |
|       |       | RES   |     | ≈P -P      |     |      |     |
| sin(ω | t)    |       | +   | RES  RD    | K   |      |     |
| RD    |       |       |     |            | IRD | +  K |     |
|       | Demod |       |     |            |     | PRD  | VCO |
| x     |       |       | _   | Converter  | s   |      |     |
| sin(P | )     |       |     | error      |     |      |     |
RES
|     |     |     |     | cos(P ) |     |     |     |
| --- | --- | --- | --- | ------- | --- | --- | --- |
REF
RD
| sin(ω | t)  |     |     |     | cos |     |     |
| ----- | --- | --- | --- | --- | --- | --- | --- |
RD
P
| COS |     | cos(P | )   |     |     | RD  |     |
| --- | --- | ----- | --- | --- | --- | --- | --- |
Up/Down
| sin(ω | t)  |     | RES  |     |     |     |     |
| ----- | --- | --- | ---- | --- | --- | --- | --- |
Counter
| RD  | Demod |     |     |     |     |     |     |
| --- | ----- | --- | --- | --- | --- | --- | --- |
x
| cos(P | )   |     |     | sin(P ) |     |     |     |
| ----- | --- | --- | --- | ------- | --- | --- | --- |
| RES   |     |     |     | RD      |     |     |     |
sin
|     |     | Figure 8-5. | Hardware R-D conversion. |     |     |     |     |
| --- | --- | ----------- | ------------------------ | --- | --- | --- | --- |
sin(P -P ). Assuming  the  converter  error, P -P , is  relatively  small,
| RES | RD  |     |     |     | RES | RD  |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
)(cid:2)P
| sin(P RES -P | RD RES -P | RD and thus represents the converter error. |     |     |     |     |     |
| ------------ | --------- | ------------------------------------------- | --- | --- | --- | --- | --- |
After the error signal is derived,it is compensated with a PI control law,shown in
Figure 8-5 as K /s+K .That error is fed to a voltage-controlled oscillator or VCO,
IRD PRD
which converts the error to a pulse train.VCOs produce pulses at a frequency in pro-
portion to the magnitude of an analog input.The pulses are counted in the up–down
| counter,which stores the converted position, |     |     |     | P RD . |     |     |     |
| -------------------------------------------- | --- | --- | --- | ------ | --- | --- | --- |
The dynamic response of the R-D converter can be derived from Figure 8-6,which
is a simplified diagram of Figure 8-5. Here, the demodulation, trigonometry, VCO,
and up–down counter have been reduced to their equivalent transfer functions.
The VCO and up–down counter behave like an integrator. The demodulation and
trigonometry act together to produce the error signal, P RES  -P RD , with few other
effects on the dynamic response.
Using the G/(1+GH) rule in Figure 8-6,the transfer function of the R-D converter
is:
K ¥s+K
|          |              |        |        | PRD IRD |           |     |       |
| -------- | ------------ | ------ | ------ | ------- | --------- | --- | ----- |
|          |              | G (s)= |        |         | .         |     | (8.1) |
|          |              | RD     | s2+K   | ¥s+K    |           |     |       |
|          |              |        |        | PRD     | IRD       |     |       |
|          |              | P      |        |         |           |     | P     |
|          | Demodulation |        | RES  P | -P      |           |     | 1 RD  |
| Resolver |              |        |        | RES  RD | K         |     |       |
|          | and          |        |        |         | I RD +  K |     |       |
| signals  |              |        | _      |         |           | PRD | s     |
|          |              |        | +      |         | s         |     |       |
trigonometry
Counter
|     |     | Figure 8-6. | Block diagram of R-D conversion. |     |     |     |     |
| --- | --- | ----------- | -------------------------------- | --- | --- | --- | --- |

8.1 THE LUENBERGEROBSERVERS INMOTIONSYSTEMS (cid:3) 181
Upon inspection,this is a low-pass filter.For example,when the frequency is low,the
s2term,which is in the denominator,is diminished and the transfer function is nearly
unity.Also,when the frequency is high,the s2term dominates,attenuating the signal
and injecting phase lag. The equivalent bandwidth of the process is determined by
the gains of the PI control law;these gains are set with passive,discrete components
that are connected to the R-D converter as part of a printed circuit board.
The selection of tuning constants generally results in conversion bandwidths of
between 300 and 1000Hz. Processes in the converter induce phase lags in the con-
version loop that form the upper bandwidth limit,which is usually 1000 or 1200Hz,
depending on the converter chip.However,in practical systems,noise considerations
often force the conversion bandwidth well below that upper limit.
A question often asked about resolvers is why not use an inverse tangent or its
equivalent for the conversion to position? This would avoid the complexity of tuning
the loop and would remove the phase lag induced by Equation 8.1.There are two key
reasons. First, taking an inverse tangent on an integrated circuit such as those used
for R-D conversion is more complicated than the approach of Figure 8-5. Second,
the noise present on the analog SIN and COS signals is often substantial; eliminat-
ing the double-integrating loop would pass that noise immediately to the position
signal. The benefit of the transfer function of Equation 8.1 is that it attenuates high
frequencies,albeit at the cost of inducing phase lag.
While the process discussed here is based on hardware R-D converters, a similar
process can be carried out in software [22]. Generally, the demodulation remains in
hardware,but the other functions are implemented in algorithms executed by a micro-
processor or digital signal processor (DSP). The digital converter has important
benefits such as reducing parts cost and simplifying adjustment of R-D converter
bandwidth. However, the basic principles are the same and the operation of the
converters is nearly identical.
8.1.3.4 Sine Encoders
The sine encoder has been gaining popularity in servo applications over the past
several years. This sensor is a variation on the incremental encoder. Where the
incremental encoder transmits digital (two-valued) pulses as position changes,the sine
encoder transmits sinusoidal signals that vary continuously as the motor rotates. A
typical sine encoder in a servo system produces sine waves with between 512 and 2048
cycles for each motor revolution. Those cycles can be interpolated with a typical
resolution of 256 to 1024 positions per sinusoid. So, while an incremental encoder
may feed back a few thousand discrete positions per motor revolution,a sine encoder
may feed back millions. Sine encoders greatly reduce resolution noise. For reference,
a typical resolver has finer resolution than a typical incremental encoder (perhaps 2
to 10 times finer),but both are much coarser than a sine encoder.
One interesting facet of sine encoders is that the signals are often processed in a
manner similar to how resolver signals are processed.Because the sine encoder feeds

182 (cid:2) CHAPTER 8 USING THE LUENBERGEROBSERVER IN MOTION CONTROL
back analog signals that are similar in form to demodulated resolver signals,a track-
ing loop is often applied to process those signals. As was the case with the resolver,
the tracking loop can inject phase lag in the sine encoder signals [6].
8.1.3.5 Deriving Velocity from Position
Most modern servo systems derive velocity information from the position sensor. As
stated earlier,this eliminates the need for a separate velocity sensor.The most common
method is simple differences:dividing the difference of the two most recently sampled
positions by the sample time. Unfortunately, compared to ideal differentiation, using
simple differences injects delay equal to half the sample time.This can be seen by eval-
uating the z-domain transfer function of simple differences ((z-1)/Tz,from Table 3-2)
and comparing the resulting phase to the ideal 90°advance of true differentiation.
8.1.3.6 Torque Transducers and Tension Control
A minority of servo applications use torque transducers to close servo loops. An
example application is high-performance coating machines where the control of
the tension of a web line is the most important measure of performance. The term
web indicates a band of material that is stretched across rollers to be processed. For
example, masking tape is produced on web-handling machines. A roll of paper is
unrolled onto the web where various coatings are applied;the paper is rewound onto
take-up rolls.
It is often critical to maintain a constant tension on the web when applying a
coating. Variation in web tension implies a variation in the thickness of the applied
coatings. For many processes, such variation lowers the quality of the end product.
For example, if the amount of photo emulsion on photographic film varies enough,
it can distort the image.
For coating applications, where the variation in coating thickness must be mini-
mized, a torque transducer is sometimes placed on the web. Servomotors control
numerous web rolls across which the web is stretched.Because the web is usually con-
structed of compliant material such as plastics or thin metal foil, tension in the web
causes the web material to stretch. For many materials, the stretching approximately
obeys Hooke’s law, which states that the amount of stretch is proportional to the
tension.In that sense,the torque transducer behaves very much like a position sensor.
The tension loop,as shown in Figure 8-7 is built as an outer loop to the velocity loop,
replacing the position loop of Figure 8-2.
8.1.4 Identifying Applications Most Likely to Benefit from Observers
This section will discuss how to identify motion systems that are most likely to benefit
from a Luenberger observer.

|     |     |     |     |     | 8.1 THE | LUENBERGEROBSERVERS | INMOTIONSYSTEMS |     | (cid:3) 183 |
| --- | --- | --- | --- | --- | ------- | ------------------- | --------------- | --- | ----------- |
V
C
Velocity
command
I
|         | T   |     | V   |     |     |             | F   | P    |     |
| ------- | --- | --- | --- | --- | --- | ----------- | --- | ---- | --- |
|         | E   | +   | E   |     |     | I Current   |     | M    |     |
| T       |     |     | K   | +   |     | C           |     | 1    |     |
|         | K   |     |     | VI  | K   | loops and   | K   |      |     |
| C       | T   |     | s   |     | VP  |             | T   | J s2 |     |
| Tension | +   | +   |     | +   |     |             |     | T    |     |
|         | -   | V   | -   |     |     | commutation |     |      |     |
| command | T   | F   |     |     |     |             |     |      |     |
F
s
P
|     |     |     |     |     |     | F Position |     |     |     |
| --- | --- | --- | --- | --- | --- | ---------- | --- | --- | --- |
sensor
Velocity
controller
| Tension    |                          |             |     |                               |     | Tension |     |     |     |
| ---------- | ------------------------ | ----------- | --- | ----------------------------- | --- | ------- | --- | --- | --- |
| controller |                          |             |     |                               |     | sensor  |     |     |     |
|            |                          | Figure 8-7. |     | Example tension control loop. |     |         |     |     |     |
| 8.1.4.1    | Performance Requirements |             |     |                               |     |         |     |     |     |
The  first  area  to  consider  is  the  performance  requirements  of the  application.
Machines that demand rapid response to command changes,stiff response to distur-
bances, or both will likely benefit from an observer. The observer can reduce phase
lag in the servo loop,allowing higher gains,which improve command and disturbance
response.Of course,for machines where responsiveness is not an issue,there may be
little reason to use an observer.
| 8.1.4.2 | Available Computational Resources |     |     |     |     |     |     |     |     |
| ------- | --------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
The second factor to consider is the availability of computational resources to imple-
ment the observer. Observers almost universally rely on digital control. If the actual
or planned control system is executed on a high-speed processor such as a DSP,where
computational resources sufficient to execute the observer are likely to be available,
an observer can be added without significant cost burden.In addition,if digital con-
trol techniques are already employed, the additional design effort to implement an
observer is relatively small. However, if the system uses a simple analog controller,
putting in place a hardware structure that can support an observer will require a large
effort.
| 8.1.4.3 | Controls Expertise in the User Base |     |     |     |     |     |     |     |     |
| ------- | ----------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
Another factor to consider is the user base—the engineers and technicians who pur-
chase, install, and maintain the equipment. Observers require some level of controls

184 (cid:2) CHAPTER 8 USING THE LUENBERGEROBSERVER IN MOTION CONTROL
expertise for installation and configuration.The user base must be capable of under-
standing the features of an observer if it is to provide benefit.
8.1.4.4 Sensor Noise
Luenberger observers are most effective when the position sensor produces limited
noise. Sensor noise is often a problem in motion-control systems. Noise in servo
systems comes from two major sources: EMI generated by power converters and
transmitted to the control section of the servo system, and resolution limitations in
sensors, especially in the feedback sensor. EMI can be reduced through appropriate
wiring practices [30] and through the selection of components that limit noise
generation such as those that comply with European CE regulations.
Noise from sensors is difficult to deal with. As was discussed in Chapter 7,
Luenberger observers often exacerbate sensor-noise problems. While some authors
have described uses of observers to reduce noise, in many cases the observer will
have the opposite effect. As discussed in Chapter 7, lowering observer bandwidth
will reduce noise susceptibility, but it also reduces the ability of the observer to
improve the system.For example,reducing observer bandwidth reduces the accuracy
of the observed disturbance signal. The availability of high-resolution feedback
sensors raises the likelihood that an observer will substantially improve system
performance.
8.1.4.5 Phase Lag in Motion-Control Sensors
The two predominant sensors in motion-control systems are incremental encoders and
resolvers.Incremental encoders respond to position change without substantial phase
lag.On the other hand,resolver signals are commonly processed with a tracking loop,
which generates substantial phase lag in the position signal.Because resolvers produce
more phase lag,their presence makes it more likely that an observer will substantially
improve system performance.The sine encoder is often processed in a manner similar
to the way resolver signals are processed.As was the case with the resolver,the track-
ing loop can inject substantial phase lag in the sine encoder signals.
Independent of the feedback sensor,most motion-control systems generate phase
lag in the control loop when they derive velocity from position.Velocity is commonly
derived from position using simple differences. It is well known to inject a phase
lag of half the sample time. This phase lag also provides an opportunity for the
Luenberger observer to improve system performance.
Five key guidelines for using the Luenberger observer in a motion system are:
• The need for high performance in the application.
• The availability of computational resources in the controller.
• The ability of the average user to install and configure the system.

8.2 OBSERVINGVELOCITY TOREDUCE PHASELAG (cid:3) 185
• The availability of a highly resolved position feedback signal.
• The presence of phase lag in the position or velocity feedback signals.
The first two guidelines are critical—without the need for an observer or a practical
way to execute observer algorithms, the observer would not be chosen. The remain-
ing guidelines are important.The more of these guidelines that an application meets,
the more likely the observer can substantially improve system performance.
8.2 Observing Velocity to Reduce Phase Lag
The remainder of this chapter will cover ways to use Luenberger observers in motion
systems. This section discusses the use of observers to reduce phase lag within the
servo loop; as has been discussed throughout this book, removing phase lag allows
higher control-law gains,improving command and disturbance response.A common
source of phase lag in digital velocity controllers is the use of simple differences to
derive velocity from position,as will be discussed in Section 8.2.1.In a resolver-based
system, additional phase lag often comes from the method employed to retrieve
position information from the resolver,as will be discussed in Section 8.2.2.
8.2.1 Eliminate Phase Lag from Simple Differences
The use of simple differences to derive velocity from position is common in digital
motor controllers that rely on a position sensor for feedback.The phase lag induced
by the simple differences can be quantified with its transfer function.
(P -P )
V = N N-1 (8.2)
N T
In the z-domain,this becomes
P(z)-P(z) z
V(z)= (8.3)
T
or
V(z) z-1
= . (8.4)
P(z) Tz
Equation 8.4 is a z-domain equivalent of differentiation. Ideal differentiation has
a phase lead of 90°at all frequencies.Equation 8.4 does produce phase lead,but less
than the ideal 90°.The difference between the ideal 90°and simple differences at any
given frequency is equivalent to halfthe sample time,as was discussed in Section 3.2.6.

186 (cid:2) CHAPTER 8 USING THE LUENBERGEROBSERVER IN MOTION CONTROL
At any given frequency, f, phase=T¥f¥360° so that this difference can be expressed
as:
Êz-1ˆ T
90∞-Phase = ¥ f ¥360. (8.5)
Ë Tz ¯ z
Equation 8.5 can be confirmed several ways, including by evaluating Equation
8.4 at several frequencies.For example,evaluate Equation 8.4 at T=0.001 and f=100
Hz.Recall that z=1–(T¥f¥360°), or here, z=1–36°. Equation 8.4 becomes:
V(z) 1–36∞-1 0.61803–108∞
= = =618.03–72∞. (8.6)
P(z) T–36∞ 0.001–36∞
T=0.001,f=100
Notice that Equation 8.6 lags the ideal 90° by 18°, which is, as predicted by
Equation 8.5,equal to half the sample time at 100Hz (18°=1000/2ms¥100Hz¥360°).
This evaluation can be made at any frequency and will produce the same result.
Incidentally,the magnitude of ideal differentiation is |s| or 2pf.For f=100Hz,that
is equivalent to 628.32rad/s.Equation 8.6 gives a magnitude of 618.03,which is accu-
rate to within 2%.The magnitude of the simple difference is reasonably accurate,but
the phase error is substantial. In fact, for most controls problems, the magnitude
of the simple differences is close enough to that of true differentiation that errors in
magnitude can be ignored. The phase error between simple differences and ideal
differentiation,on the other hand,is substantial at half a sample period and usually
must be considered.
8.2.1.1 Form of Observer
The observer structure that eliminates the phase lag generated by simple differences
is shown in Figure 8-8. The feedback current, I , is scaled by K to produce electro-
F T
magnetic torque, T , in the physical system, and by K to produce estimated
E TEst
electromagnetic torque, T . The term electromagnetic torque describes the torque
EEst
generated from the windings of the motor.In the actual system,the electromagnetic
torque is summed with the disturbance torque,T (s),to form the total torque.Total
D
torque is divided by inertia to produce motor acceleration; acceleration is integrated
twice to produce velocity and position. The model system is similar except integra-
tion,1/s,is replaced by its digital equivalent,Tz/(z-1),and the observed disturbance
is used in the calculation of observed torque.
The second integration of both the model and the actual system is considered
part of the sensor rather than the motor. Because the state of concern is velocity,
the assumption in this observer is that the velocity is the plant output, and the
integration stage that creates position is an artifact of the measuring system. This
observer assumes that the position sensor provides feedback without substantial
phase lag. This is a reasonable assumption for an incremental encoder. As has been

|             |     |       |                |     | 8.2           | OBSERVINGVELOCITY | TOREDUCE | PHASELAG | (cid:3) 187 |
| ----------- | --- | ----- | -------------- | --- | ------------- | ----------------- | -------- | -------- | ----------- |
| T (s)       |     |       |                |     |               |                   | P (s)    |          |             |
| D           |     | +     | + 1            | 1   | V (s)         | 1                 | M        |          |             |
| Disturbance |     |       |                |     | M             |                   |          |          |             |
|             | K   |       |                |     |               |                   |          | P (s)    |             |
| torque      |     | T     | J              | s   | A c tu a l    | s                 |          | F        |             |
|             |     | T (s) | T              |     |               |                   | + +      | Se nsor  |             |
|             |     | E     |                |     | v e lo c it y |                   |          |          |             |
|             |     |       |                |     |               | Sensor            |          | output   |             |
| I (s)       |     |       |                |     |               |                   | N(s)     |          |             |
| F           |     |       | Physicalsystem |     |               |                   |          |          |             |
Noise
Actual
| current |     | Observed    |     |     | Observer |       | P (s) |     |     |
| ------- | --- | ----------- | --- | --- | -------- | ----- | ----- | --- | --- |
|         |     |             |     |     |          |       | OE    | +   |     |
|         |     | disturbance |     | G   | (s)      | error |       |     |     |
|         |     |             |     | CO  |          |       |       | _   |     |
D (s)
O
Observercompensator
Observed
|       |     | + torque |     | 1    | Tz  | V (s)    | Tz     |          |     |
| ----- | --- | -------- | --- | ---- | --- | -------- | ------ | -------- | --- |
|       | K   |          |     |      |     | O        |        | P (s)    |     |
|       |     | TEst     |     |      |     | Observed |        | O        |     |
|       |     | +        | J   |      | z-1 |          | z-1    |          |     |
|       |     | T (s)    |     | TEst |     | velocity |        | Observed |     |
|       |     | EEst     |     |      |     |          | Sensor |          |     |
| V (s) |     |          |     |      |     |          |        | position |     |
F
Modeledsystem
Velocityfeedback
| Figure 8-8. | Using a Luenberger observer to observe velocity with a fast position sensor. |     |     |     |     |     |     |     |     |
| ----------- | ---------------------------------------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
discussed throughout this book, phase lag incurred when measuring the actual
state can be reduced using an observer. In this case, the goal of the observer is to
remove the phase lag of simple differences,which would otherwise be used to measure
velocity.
8.2.1.2 Experiment 8A: Removal of Phase Lag from Simple Differences
The benefits of the removal of phase lag from simple differences are demonstrated in
Experiment 8A.The block diagram of that model is shown in Figure 8-9.1 This model
will be reviewed in detail. The velocity command (Vc) comes from a command gen-
erator (Command) through a dynamic signal analyzer (Command Dsa).The command
velocity is compared to the feedback velocity and fed to a PI controller (Digital PI),
which is configured with two Live Constants, K and K . These parameters are set
|     |     |     |     |     | VP  | VI  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
high (K =4.2,K =850),yielding a bandwidth of about 660Hz and a 25% overshoot
| VP  | VI  |     |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
to a step command;this is responsive performance for the modest 4-kHz sample rate
used in this model. As will be shown, the observer is necessary to attain such a high
performance level.
The output of the velocity controller is a current command,which feeds the current
controller (Current Loop). The current controller is modeled as a two-pole low-pass
1Occasionally, Experiment 8A and some of the other models in Chapter 8 will become unstable. This
usually occurs when changing a control-loop gain. In some cases, restoring the model to its original
| settings will not restore stability.If |     | this happens,click File,Zero All Stored Outputs. |     |     |     |     |     |     |     |
| -------------------------------------- | --- | ------------------------------------------------ | --- | --- | --- | --- | --- | --- | --- |

188 (cid:2) CHAPTER 8 USING THE LUENBERGEROBSERVER IN MOTION CONTROL
Figure 8-9. Experiment 8A: Investigating the effects of reducing phase lag from simple differences.
filter with a bandwidth of 1200Hz, set by the constant (Current Loop BW), and a
fixed damping of 0.7. This is consistent with current-loop controllers used in the
motion-control industry.
The output of the current loop is torque-producing current. It feeds the motor
through the torque constant (K ) to create electromagnetic torque. Simultaneously,
T
a disturbance generator (Disturbance) feeds a second DSA (Dist Dsa) to create dis-
turbance torque (T ).The two torque signals are summed to create total torque.The
D
total torque is divided by the total inertia (J ) to produce motor acceleration. (Note
T
that the J block is an Inverse Live Constant,indicating the output is the input divided
T
by the constant value.) This signal is integrated once to create motor velocity (V )
M
and again to create motor position.
There is an optional resolution, which defaults to not-used. To enable resolution,
double click on Use Res?and select Yes.This model assumes an instantaneous feed-
back signal from the position sensor,which is consistent with the operation of encoder
systems. Accordingly, the units of resolution are encoder lines, where each line
translates into four counts via ¥4 quadrature, a common method used with optical
encoders.The scaling to convert encoder lines to radians (SI units of angle) is imple-
mented with the Mult node of the Live Constant named Encoder Lines being set to
4/2p or 0.6366, where the 4 accounts for quadrature and the 2p converts revolutions
to radians.

8.2 OBSERVINGVELOCITY TOREDUCE PHASELAG (cid:3) 189
The position signal feeds the observer loop,which uses a PID control law (Digital
PID (2)) configured with two Live Constants (K and K ). In the ideal case, the
PO IO
output of the PID controller is equal to acceleration caused by the disturbance torque.
The PID output is summed with the power-converter path of the observer, which is
the output current scaled by the estimated torque constant (K ) and divided by the
TEst
estimated total inertia (J ).The result is summed twice,approximating the two inte-
TEst
grals of the physical motor.The derivative gain is configured with K in this observer,
DO
which is configured as a modified Luenberger observer. The observer produces two
output signals: the modified observed velocity, taken just after the first digital inte-
gration (the leftmost Sum) and the standard observed velocity output, taken just
before the second digital integration (the rightmost Sum). As in earlier chapters, the
delay of one step is added to allow the observer to be constructed since the loop must
have some starting point.
One difference between the block diagram of Figure 8-8 and the model of
Figure 8-9 is that the observer has been reconfigured to remove the effects of inertia
from the observer loop.Notice that J is directly after K and outside the observer
TEst TEst
loop. This implies that the units of the observer PID output are acceleration, not
torque as in Figure 8-8. This will be convenient because changing estimated inertia
will not change the tuning of the observer loop; without this change, each time
estimated inertia is varied,the observer must be retuned.This observer structure will
be used in experiments throughout this chapter.
The model for Experiment 8A includes four Live Scopes. At center left is a dis-
play of the step response: the command (above) is plotted against the actual motor
velocity.Along the bottom are three scopes,from left to right,
(1) the actual motor velocity, V ,vs the sensed velocity,V ,
M S
(2) V vs the modified observed velocity,V ,and
M OMod
(3) V vs the observed velocity, V .
M O
The sensed velocity, V , lags the motor velocity just a bit because of the phase lag
S
injected by simple differences.As expected,the two observed velocities show no signs
of phase lag.
One of the features of the model in Experiment 8A is that it allows the selection
of any of the three velocity signals as the feedback signal for the control loop. The
switch Switch4 is controlled with the Live Constant named Feedback, which can be
set to V ,V ,and V .Double-click on Feedbackany time to change the feedback
S OMod O
signal.This feature will be used to show the benefit of using the observer to measure
velocity.
The key variables used in this and other experiments in this chapter are detailed in
Table 8-1.Most are similar to variables in earlier chapters except the general-purpose
variables (such as C and R) have been replaced by motion-specific variables (such
as V for velocity). Note that all velocity variables display in RPM although all
calculations are in radians/second (SI) units;the scaling is accomplished with Visual
ModelQ multiplication nodes.

190 (cid:2) CHAPTER 8 USING THE LUENBERGEROBSERVER IN MOTION CONTROL
TABLE 8-1 KEYVARIABLES OF EXPERIMENTS 8A–8F
| Variable | Description                      |     |              |
| -------- | -------------------------------- | --- | ------------ |
| A O      | Observed motor acceleration      |     |              |
| A        | Observed disturbance,in units of |     | acceleration |
DO
Current Loop BW Bandwidth of current loop which is modeled as a two-pole low-pass
|     | filter with a damping ratio of |     | 0.7 |
| --- | ------------------------------ | --- | --- |
I ,I Command and feedback (actual) current.Input and output of
C F
power converter
J ,J Actual and estimated total inertia of motor and load.This model
T TEst
assumes a rigid coupling between motor and load
| K ,K ,K  | Proportional,integral,and derivative gains of |     | observer |
| -------- | --------------------------------------------- | --- | -------- |
| PO IO DO |                                               |     |          |
K T ,K TEst Actual and estimated torque constant of motor.The torque output
of the motor windings is the actual current (I ) multiplied by the
F
torque constant
| K ,K | Proportional and integral gains of |     | velocity loop |
| ---- | ---------------------------------- | --- | ------------- |
VP VI
| P M | Actual motor position   |     |     |
| --- | ----------------------- | --- | --- |
| P   | Feedback motor position |     |     |
F
| P   | Observed motor position |     |     |
| --- | ----------------------- | --- | --- |
O
| P   | Observed motor position error |     |     |
| --- | ----------------------------- | --- | --- |
OE
| T   | Disturbance torque |     |     |
| --- | ------------------ | --- | --- |
D
| V C | Command velocity |     |     |
| --- | ---------------- | --- | --- |
| V   | Velocity error,V | –V  |     |
| E   |                  | C F |     |
V Feedback velocity,the velocity signal used to close the velocity loop,
F
|     | which can be set to V | ,V ,or V | at any time through the  |
| --- | --------------------- | -------- | ------------------------ |
|     |                       | S O      | OMod                     |
constant Feedback
| V   | Actual motor velocity |     |     |
| --- | --------------------- | --- | --- |
M
V Observed motor velocity using the standard Luenberger observer
O
V Observed motor velocity using the modified Luenberger observer
OMod
V Sensed velocity,the velocity derived from the feedback position
S
using simple differences
The results of Experiment 8A are shown in Figure 8-10.There are three plots,one
for the system configured using each of V ,V ,and V as velocity-loop feedback.
|     |     | S O | OMod |
| --- | --- | --- | ---- |
The sensed feedback signal has substantial phase lag, which produces ringing in
the step response.The two observed velocities produce nearly equivalent results,both
having conservative margins of stability. The difference in stability between sensed
and observed feedback is due wholly to the phase lag induced by simple differences
(Equation 8.5). The two observed feedback signals produce equivalent results as
expected;the command responses of the standard and of the modified observers are

8.2 OBSERVINGVELOCITY TOREDUCE PHASELAG (cid:3) 191
V
C
V
F
(a) (b) (c)
Figure 8-10. Results of Experiment 8A. Square-wave command (above) and response with feedback as
(a) sensed velocity (V), (b) standard (V ), and (c) modified (V ) Luenberger observer output. Gains are
S O OMod
K =4.2 and K =850 in all cases.
VP VI
normally equivalent, excepting response to noise and disturbances, neither of which
are simulated here. Note that the velocity-loop gains (K =4.2, K =850) were
VP VI
adjusted to maximize their values when observed velocity is used for feedback; the
same values are used in all three cases of Figure 8-10.
The improvement in stability margins can also be seen in Bode plots from
Experiment 8A, as seen in Figure 8-11. Here, the use of observed signals (either V
O
with sensor feedback
(15 dB peaking)
with observed feedback
(660 Hz b/w, <3 dB peaking)
Figure 8-11. Results of Experiment 8A. Bode plot of command response with sensed feedback and observed
(V ) feedback. Gains are K =4.2 and K =850 in both cases.
O VP VI

192 (cid:2) CHAPTER 8 USING THE LUENBERGEROBSERVER IN MOTION CONTROL
with modified Luenberger observer
with standard
Luenberger observer
Figure 8-12. Results of Experiment 8A. Disturbance response is degraded for the modified Luenberger
observer. Gains are K =4.2 and K =850 in both cases.
VP VI
or V ) reduces peaking by more than 10dB, allowing much higher command
OMod
response than can be supported by sensed feedback. Note that these Bode plots are
generated using the Command Dsa.
The disturbance response is degraded when using the modified Luenberger
observer, as was discussed in Chapter 7. This is demonstrated with the Dist Dsa as
shown in Figure 8-12.While the command response of both signals is about the same,
the disturbance response of the standard form is lower (better) than the modified form
below the observer bandwidth. As discussed in Chapter 7, the primary disadvantage
of the standard form is increased noise susceptibility,compared to the modified form.
8.2.1.3 Experiment 8B: Tuning the Observer
Experiment 8B isolates the observer to focus on tuning the observer loop.The model
is shown in Figure 8-12. The motor and the velocity controller have been removed.
The velocity command is summed (i.e., digitally integrated) to produce position
command. That command is fed into the observer loop. The observer feed-forward
path has been removed so that only the observer loop remains.The model includes a
DSA that can show the frequency-domain response of the observer loop. Two Live
Scopesshow the step velocity response of the standard and modified observed veloc-
ity. Finally, the variables V and V are used to display the open-loop response of
OE O2
the observer;these variables will be discussed later in this section.

|     |     |     | 8.2 OBSERVINGVELOCITY | TOREDUCE PHASELAG | (cid:3) 193 |
| --- | --- | --- | --------------------- | ----------------- | ----------- |
Figure 8-13. Experiment 8B: Observer used in Experiments 8A, 8E, and 8F.
The Live Scopes in Figure 8-13 show slight ringing for the selected tuning values
(K =5¥106,K =5¥109,K =3500).These values were determined experimentally,
| PO  | IO  | DO  |     |     |     |
| --- | --- | --- | --- | --- | --- |
tuning one observer gain at a time. The step response of the standard observer
(V O ) for each of the three gains is shown in Figure 8-14. K DO is set just below where
overshoot occurs.K is set for about 25% overshoot and K is set for a small amount
|     | PO  |     |     | IO  |     |
| --- | --- | --- | --- | --- | --- |
of ringing.
The frequency response of the standard observer velocity (V ) is shown in the Bode
O
plot of Figure 8-15. The bandwidth of the observer is greater than 1000Hz. In fact,
the bandwidth is too great to be measured by the DSA,which samples at 4kHz.There
is 4dB of peaking, verifying that the observer tuning gains are modestly aggressive.
V
C
V
O
|     | (a) |     | (b) | (c) |     |
| --- | --- | --- | --- | --- | --- |
Figure 8-14. Step response of V in the tuning of the observer of Experiment 8B and viewing the standard
O
|     | observer output. (a) K | =3500, (b) add K | =5¥106, (c) add K | =5¥109. |     |
| --- | ---------------------- | ---------------- | ----------------- | ------- | --- |
|     |                        | DO               | PO                | IO      |     |

194 (cid:2) CHAPTER 8 USING THE LUENBERGEROBSERVER IN MOTION CONTROL
4 dB
peaking
Bandwidth
>1000 Hz
Figure 8-15. Bode plot of observed velocity (V ) in Experiment 8B.
O
The frequency response of the modified observer velocity is shown in the Bode plot
of Figure 8-16. The bandwidth of the signal is just 500Hz, well under that of the
standard observer. This is consistent with the expected behavior of the modified
observer: lower response to both command and noise.
Plotting the open-loop response of the observer loop brings up some inter-
esting modeling issues. First, the loop command, as generated by the waveform
generator and DSA, is summed to create the position command to the observer. A
detail of this feature,found in Figure 8-13,is shown in Figure 8-17.The implication
is that the command is a commanded velocity, which is then integrated to create
commanded position. This is required to keep the position command continuous
over time. Large step changes in position create enormous swings in velocity and
thus can cause saturation in the observer. The integrator is intended to avoid this
problem.
A second feature of this model is the use of velocity signals (as opposed to
position signals) to provide a Bode plot of the open-loop transfer function of the
observer.This is done because the method used to create Bode plots in Visual ModelQ,
the fast-Fourier transform or FFT, requires the start and end values of each signal
being measured to be identical.The position generated from integration of the DSA
random number generator does not necessarily meet this requirement. However, the
model is configured to start and stop the Bode plot excitation at zero speed, so that
the velocities, which are the derivatives of the position signals, always start and stop

8.2 OBSERVINGVELOCITY TOREDUCE PHASELAG (cid:3) 195
4 dB
peaking
Bandwidth
500 Hz
Figure 8-16. Bode plot of modified observed velocity (V ) in Experiment 8B.
OMod
at zero. Velocity signals can be used in place of position signals because the transfer
function of two position signals is the same as the transfer function of their respec-
tive velocities.For example,P (s)/P (s)=V (s)/V (s).In the s-domain this would be
M C M C
equivalent to multiplying the numerator and denominator by s (s being differentia-
tion), which would produce no net effect. So the open-loop transfer function of the
observer,shown in a dashed line in Figure 8-18,is observer position error to observed
position; however, that is identical to the derivative of both those signals (shown by
the blocks “Derivative”),which produce V and V .The DSA is preset to show the
OE O2
open loop as V /V .
O2 OE
The open-loop Bode plot of the observer is shown in Figure 8-19. The gain
crossover is at about 700Hz and the phase margin is about 42°.There are two phase-
crossover frequencies,one at about 200Hz and the other at about 2000Hz.The gain
margin is 12dB at 200Hz,but only 6dB at 200Hz.The crossover at 200Hz generates
the peaking in Figures 8-15 and 8-16 and the slight ringing in Figure 8-14c.
Commanded velocity Commanded position
Digital integration
Figure 8-17. Detail of observer command for Experiment 8B (taken from Figure 8-13).

196 (cid:2) CHAPTER 8 USING THE LUENBERGEROBSERVER IN MOTION CONTROL
Observer position
Sensor position
error Differentiate to produce
velocity error (V )
OE
Open loop
Differentiate to produce
Observer position feedback
velocity feedback (V )
O2
Figure 8-18. Detail of signals for Bode plot from Experiment 8B (taken from Figure 8-13).
The crossover at 200Hz results because the low-frequency open-loop phase is
-270°,-90°from each of the two integrators in the observer loop (marked Sum) and
another -90°from the integral gain in the PID controller,which dominates that block
at low frequency.The gain margin at 200Hz is set almost entirely by the integral gain,
K .The interested reader can verify this using Experiment 8B (see Exercise 8-1).
IO
Gain
crossover
(~700 Hz)
12.5 dB gain 6 dB gain
margin margin
41∞
phase
margin
1ST phase
2ND phase
crossover
crossover
(~200 Hz)
(~2000 Hz)
Figure 8-19. Bode plot of observer open-loop gain and phase showing margins of stability.

|                                           |     |     |     |     | 8.2 | OBSERVINGVELOCITY | TOREDUCE |     | PHASELAG | (cid:3) 197 |
| ----------------------------------------- | --- | --- | --- | --- | --- | ----------------- | -------- | --- | -------- | ----------- |
| 8.2.2 Eliminate Phase Lag from Conversion |     |     |     |     |     |                   |          |     |          |             |
The observer of Figure 8-8 is designed with the assumption that there is not signifi-
cant phase lag induced in the measurement of position.This is valid for incremental
(A-quad-B) encoders,but not for most resolver and sine-encoder conversion methods.
Unlike incremental encoders,the conversion of resolver and sine-encoder inputs nor-
mally injects significant phase lag.For these sensors,the model needs to be augmented
to include the phase lag induced by the conversion of feedback signals. Such an
observer is shown in Figure 8-20. Here, the model system sensor includes the R-D
converter transfer function of Equation 8.1 as G (z).Of course,the model of the
RDEst
physical system has also been modified to show the effects of the actual R-D con-
| verter on the actual position,P |     |     | (s),using G |     | (s). |     |     |     |     |     |
| ------------------------------- | --- | --- | ----------- | --- | ---- | --- | --- | --- | --- | --- |
|                                 |     |     | M           |     | RD   |     |     |     |     |     |
The observer of Figure 8-20 assumes the presence of a hardware R-D converter.
Here,the process of creating the measured position takes place outside of the digital
control system.When the process of R-D conversion is done in the digital controller
[22], the observer can be incorporated into the R-D converter as is discussed in [14],
which is copied in Appendix A.
8.2.2.1 Experiment 8C: Verifying the Reduction of Conversion Delay
The effect of conversion delay is evaluated using Experiment 8C, as shown in
Figure 8-21.This experiment uses a two-pole filter as a model of R-D conversion both
in the physical system (the block R-D at the upper right of the figure) and in the
| D(s)        |     |     |       |                 |                |       | P (s) |     |        |     |
| ----------- | --- | --- | ----- | --------------- | -------------- | ----- | ----- | --- | ------ | --- |
|             |     | +   |       |                 |                |       | M     |     |        |     |
| Disturbance |     |     | 1     | V               | (s)            | 1     |       |     |        |     |
|             | K   |     |       | M               |                | G (s) |       |     | P (s)  |     |
|             | T   |     |       | Actual          |                | RD    |       |     | F      |     |
|             |     |     | J     | s               |                | s     |       |     |        |     |
|             |     | +   | T     | velocity        |                |       | +     | +   | Sensor |     |
|             |     |     | Motor |                 | Resolver & R-D |       |       |     | output |     |
| I (s)       |     |     |       |                 |                |       | N(s)  |     |        |     |
| F           |     |     |       | Physical system |                |       |       |     |        |     |
Noise
Actual
O b s e r v ed
| current |     |         |                  |     |       | Ob s e r v er  | E (s) |     |     |     |
| ------- | --- | ------- | ---------------- | --- | ----- | -------------- | ----- | --- | --- | --- |
|         |     | D (s) d | ist u r b a n ce |     |       | e r r o r      | O     | +   |     |     |
|         |     | O       |                  |     | G (s) |                |       |     |     |     |
CO
_
Observer compensator
|     |     | +   | Tz    1    | V   | (s) | Tz  |     |     |     |     |
| --- | --- | --- | ---------- | --- | --- | --- | --- | --- | --- | --- |
O
|     | K    |     |        |          |     | G (z)     |     |     | P (s)    |     |
| --- | ---- | --- | ------ | -------- | --- | --------- | --- | --- | -------- | --- |
|     | TEst |     | z-1  J | Observed |     | RDEst z-1 |     |     | O        |     |
|     |      | +   |        | TEst     |     |           |     |     |          |     |
|     |      |     |        | velocity |     |           |     |     | Observed |     |
|     |      |     | Plant  |          |     | Sensor    |     |     |          |     |
position
Modeled system
Figure 8-20. Using a Luenberger observer to observe velocity with resolver feedback.

198 (cid:2) CHAPTER 8 USING THE LUENBERGEROBSERVER IN MOTION CONTROL
Figure 8-21. Experiment 8C: Reducing phase lag from the R-D converter.
observer model (the block R-D Est at the center right of the figure). The filter used
to simulate the R-D converter is a low-pass filter with the form:
2zw +w2
R-D(s)= N N .
s2+2zw +w2
N N
This is an LPF2A block in Visual ModelQ. This filter has the same form as
Equation 8.1. The filter used in the observer, R-DEst(z), is the z-domain equivalent
of R-D(s).
The observer compensator must change from PID to PID-D2, where the D2 indi-
cates a second-derivative term. This second-derivative term is necessary because the
R-D Est block, being a low-pass filter, adds substantial phase lag. The phase lead
added by the derivative term improves stability margins allowing higher observer
gains. Without the second derivative, the observer gains are limited to low values as
can be verified using Experiment 8D,which will be discussed shortly.In Figure 8-21,
the scaling of the second derivative is named K .Note that the Visual ModelQblock
DDO
is a single derivative,but K has the same effect as a second derivative in the observer
DDO
control law because it is fed in after the first Sumblock.

|     |     |     | 8.2 OBSERVINGVELOCITY | TOREDUCE PHASELAG | (cid:3) 199 |
| --- | --- | --- | --------------------- | ----------------- | ----------- |
As with Experiment 8A (Figure 8-9), Experiment 8C includes four Live Scopes.
At center left is a display of the step response: the command (above) is plotted
against the actual motor velocity. Along the bottom are three scopes, from left to
right,
| (1) the actual motor velocity, |                                     | V M ,vs the sensed velocity,V |      | S , |     |
| ------------------------------ | ----------------------------------- | ----------------------------- | ---- | --- | --- |
| (2) V                          | vs the modified observed velocity,V |                               | ,and |     |     |
| M                              |                                     |                               | OMod |     |     |
| (3) V                          | vs the observed velocity,           | V .                           |      |     |     |
| M                              |                                     | O                             |      |     |     |
The sensed velocity,V ,lags the motor velocity by about one-third of a division,much
S
more than the lag seen in Experiment 8A.The phase lag here comes from two sources:
simple differences,which Experiment 8A also displayed,and the phase lag from R-D
conversion, which is the dominant source of phase lag in this model. As with
Experiment 8A, the two observed velocities show virtually no signs of phase lag.
Also as with Experiment 8A,Experiment 8C allows the selection of any of the three
measured velocities as feedback. Double-click on Feedback any time to change the
feedback signal.
The benefits of using observed velocity feedback are readily seen by changing
the control-loop feedback source via the LiveConstantnamedFeedback.By default,
the source is the modified observed velocity,V .By double-clicking on Feedback,the
OMod
feedback source can be set as the observed velocity, V O , or as the sensed velocity,
V , which is the simple difference of the output of the R-D converter. The step
S
response of the system with these three feedback signals is shown in Figure 8-22; in
all three cases,the control-loop PI gains are the same:K =2,K =420.These values
|     |     |     | VP  | VI  |     |
| --- | --- | --- | --- | --- | --- |
are similar to those used in Experiment 8A except that K was reduced to increase
VP
stability margins. The results are that the system using V S is unstable but that the
V
C
V
F
| (a) |     | (b) |     | (c) |     |
| --- | --- | --- | --- | --- | --- |
Figure 8-22. From Experiment 8C: Step response with three feedback signals. Both observer feedback
types give a similar response, but phase lag in the sensed feedback results in complete instability.
For all cases, K =2 and K =420. (a) Sensed feedback (V =V); (b) modified observer (V =V );
|     | VP VI |                          | F S   | F OMod |     |
| --- | ----- | ------------------------ | ----- | ------ | --- |
|     |       | (c) standard observer (V | =V ). |        |     |
F O

200 (cid:2) CHAPTER 8 USING THE LUENBERGEROBSERVER IN MOTION CONTROL
two observed signals produce about the same command response;both have reason-
able margins of stability. As has been discussed, the differences between using the
standard and modified observed feedback are that the system using standard observed
velocity will be more responsive to disturbances and more sensitive to sensor
noise.
The Bode plot of command response for the gains K =2 and K =420 is shown
VP VI
in Figure 8-23. It confirms the results of Figure 8-22. The system based on sensed
velocity feedback has over 20dB of peaking.In fact,the value K had to be reduced
VP
slightly (from 2.0 to 1.85) to provide sufficient stability margins so that a Bode plot
could be calculated (Bode plots cannot be generated from unstable systems). The
two cases using observed feedback have a modest 2–3dB peaking. The dramatic
difference in these plots is caused by the ability of the observer to provide a feedback
signal that does not include the delays of R-D conversion. In fact, for the observed
feedback, the value of K can be increased well above 2 while maintaining
VP
reasonable margins of stability.
For reference, the R-D converter filters are set for about a 400-Hz bandwidth,
which is a typical bandwidth of R-D conversion in industrial systems. Notice that,
for the systems based on observed feedback, the closed-loop bandwidth is about
250Hz. Attaining such high bandwidth with a 400-Hz R-D conversion is very
difficult without using observer techniques.
Sensed feedback Bandwidth of
(>20 dB peaking) observer-based
Note: K =1.85 systems: ~250 Hz
VP
Systems with standard and
modified observer feedback
are almost identical
Figure 8-23. From Experiment 8C: Command response with three feedback types
(K =2, K =420 except K was reduced to 1.85 for sensed feedback).
VP VI VP

8.2 OBSERVINGVELOCITY TOREDUCE PHASELAG (cid:3) 201
8.2.2.2 Tuning the Observer in the R-D-Based System
The R-D converter for Experiment 8C is tuned to about 400Hz. In industry, R-D
converters are commonly tuned to between 300 and 1000Hz. The lower the band-
width, the less susceptible the converter will be to noise; on the other hand, higher
bandwidth tuning gains induce less phase lag in the velocity signal. The bandwidth
of 400Hz was chosen as being representative of conversion bandwidths in industry.
The response of the model R-D converter is shown in Figure 8-24.The configuration
parameters of the filters R-D and R-D Est were determined by experimentation to
achieve 400-Hz bandwidth with modest peaking:Frequency=190 and Damping=0.7.
The process to tune the observer is similar to the process used in Experiment 8B,
with the exception that a second-derivative term, K , is added. Experiment 8D,
DDO
shown in Figure 8-25, isolates the observer from Experiment 8C, much as was done
in Experiment 8B.
The process to tune this observer is similar to that used to tune other observers.
First, zero all the observer gains except the highest frequency gain, K . Raise that
DDO
gain until a small amount of overshoot to a square-wave command is visible.In this
case, K is raised to 1, and the step response that results has a small overshoot as
DDO
shown in Figure 8-26a. Now, raise the next highest frequency gain, K , until signs
DO
of low stability appear. In this case, K was raised a bit higher than 3000 and then
DO
backed down to 3000 to remove overshoot.The step response is shown in Figure 8-26b.
Next, K is raised to 1¥106; the step response, shown in Figure 8-26c, displays
PO
400 Hz Bandwidth
Figure 8-24. From Experiment 8D: Bode plot of R-D converter response showing 400Hz bandwidth.

202 (cid:2) CHAPTER 8 USING THE LUENBERGEROBSERVER IN MOTION CONTROL
Figure 8-25. Experiment 8D: Tuning the R-D converter.
some overshoot. Finally, K is raised to 2¥108, which generates a slight amount of
IO
ringing as shown in the LiveScopeof Figure 8-25.The Bode plot of the response of
the observer gains is shown in Figure 8-27.The bandwidth of the observer is approx-
imately 880Hz.
8.3 Using Observers to Improve Disturbance Response
Observers in motion systems provide two distinct ways to improve disturbance
response. First, as discussed in Chapter 6, disturbance decoupling can be used to
reduce the perturbations caused by disturbances. Second, acceleration feedback can
V
C
V
O
6
(a) (b) (c)
Figure 8-26. From Experiment 8D: Step response in the tuning of the observer. (a) K =1,
DDO
(b) add K =3000, (c) add K =1¥106.
DO PO

8.3 USINGOBSERVERS TOIMPROVEDISTURBANCERESPONSE (cid:3) 203
Bandwidth
= 880 Hz
Figure 8-27. From Experiment 8D: Bode plot of response of R-D-based observer tuned for 880Hz bandwidth
(K =1, K =3000, K =1¥106, K =2¥108).
DDO DO PO IO
be used for the same purpose. As will be discussed, while the two methods at first
seem unrelated, the structures are similar,as are the benefits.
8.3.1 Disturbance Decoupling in Motion Systems
From Chapter 5,observed disturbance can be used to support disturbance decoupling
[25–27, 35, 39]. A configuration that supports disturbance decoupling in motion
systems is shown in Figure 8-28. This system is based on a very low phase-lag posi-
tion sensor,such as an encoder;this can be seen by noticing that the sensor model is
the ideal 1/s (between V and P , at upper right). This structure can be adapted for
M M
a sensor with significant lag,such as a resolver,by adding the appropriate filter blocks
as was discussed in the previous section.
The observer in Figure 8-28 is a standard Luenberger observer in that all three
observer-compensation terms are used to form a single signal (the modified observer
typically has one path for the derivative term and another for the integral and pro-
portional terms). The output of the observer, A in Figure 8-28, is the disturbance
DO
torque,but in units of acceleration.This can be seen by noticing that the output flows
to two integrators to form position (P ); a signal that integrates twice to form
O
position must have units of acceleration. Accordingly, the feedback current, I , is
F

204 (cid:2) CHAPTER 8 USING THE LUENBERGEROBSERVER IN MOTION CONTROL
| V   |     |     |     |     | T   |     |     |     |      |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ---- |
| C   |     |     |     |     | D   |     |     |     |      |
|     | V   | I   | I   |     |     |     | V   |     | P =P |
| +   | E   | + C | F   | +   | +   | 1   | M   | 1   | M F  |
Current
|     | PI  |         |     | K   |     |     |     |     |     |
| --- | --- | ------- | --- | --- | --- | --- | --- | --- | --- |
| _   |     | _ _loop |     | T   |     | J s |     | s   |     |
T
Control
|     |     |     |     |     |     | Motor |     | Sensor |     |
| --- | --- | --- | --- | --- | --- | ----- | --- | ------ | --- |
V
| F   | law | K   |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
DD
|     |     | J      | Decoupling path |     |     |     |                |     | +   |
| --- | --- | ------ | --------------- | --- | --- | --- | -------------- | --- | --- |
|     |     | TEst   |                 |     |     |     | PID Controller |     |     |
|     |     | I K    |                 |     |     | A   |                |     | _   |
|     |     | D TEst |                 |     |     | DO  |                |     |     |
Observed
P
|     | Observed    |     |     |     | disturbance (in        |     |     |     | OE  |
| --- | ----------- | --- | --- | --- | ---------------------- | --- | --- | --- | --- |
|     | disturbance |     |     |     | units of acceleration) |     |     |     |     |
K
|     | (in units   |     | TEst |     |      |     |     |       |     |
| --- | ----------- | --- | ---- | --- | ---- | --- | --- | ----- | --- |
|     |             |     | J    |     | A    |     | V   |       | P   |
|     | of current) |     | TEst | +   | O Tz |     | O   | Tz    | O   |
|     |             |     |      |     | z-1  |     |     | z-``1 |     |
+
|     |     | V   |     |     | Motor Model |     | Sensor Model |     |     |
| --- | --- | --- | --- | --- | ----------- | --- | ------------ | --- | --- |
S z -1
T``z
Simple difference
|     |     | Figure 8-28. Observer-based disturbance decoupling in motion systems. |     |     |     |     |     |     |     |
| --- | --- | --------------------------------------------------------------------- | --- | --- | --- | --- | --- | --- | --- |
scaled first by the estimated torque constant,K ,to create units of torque and then
TEst
divided by the total (motor and load) estimated inertia, J , to form units of accel-
TEst
eration.These steps are consistent with the motion-based observers used throughout
this chapter.
The unique section of Figure 8-28 is the decoupling path from the observed dis-
turbance,A ,to the current command.This signal must be converted from units of
DO
acceleration to current.This is done by first multiplying by total inertia,J ,to create
TEst
observed torque and then dividing by the motor-estimated torque constant,K ,to
TEst
create current. This signal must also be scaled by the disturbance-decoupling para-
meter, K . If K is set to 0, disturbance decoupling is turned off; if it is set to 1,
|     | DD  | DD  |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
disturbances will be fully decoupled, within the ability of the system.
Recall  the  stability  problems  of observer-based  disturbance  decoupling  from
Chapter 5. If the observer-loop gain, here affected by J and K , is significantly
|     |     |     |     |     |     | TEst |     | TEst |     |
| --- | --- | --- | --- | --- | --- | ---- | --- | ---- | --- |
in error,instability can result.On most servo systems,the value of K is known with
T
reasonable precision. However, in many applications, the actual inertia varies con-
siderably during normal operation. Disturbance decoupling is normally difficult to
use in applications with varying inertia;however,if the value of J can be regularly
TEst
updated to follow the changes in actual inertia,the method can still be applied.This
normally requires that the changes in inertia are not too rapid and that they can be
accurately predicted.

8.3 USINGOBSERVERS TOIMPROVEDISTURBANCERESPONSE (cid:3) 205
8.3.1.1 Experiment 8E: Using Disturbance Decoupling in Motion Systems
Experiment 8E models the observer structure of Figure 8-28.To simplify the model,
a single term K /J is formed at the bottom center of the model (note that the
TEst TEst
J block is an Inverse Live Constant, indicating the output is the input divided by
TEst
the constant value).This term multiplies the current-loop output to convert that signal
from current to acceleration units. The term also divides the observed disturbance
to convert its units from acceleration to current. Also, notice that in Figure 8-28 an
explicit clamp has been added to the input of the current loop. The clamp function
is normally provided implicitly through the PI controller;however,since the PI output
is added to the disturbance signal, the output must be clamped again to ensure that
the maximum commanded current is always within the ability of the power stage.
Another difference between Experiment 8E and the idealized block diagram of
Figure 8-28 is that the experiment uses the observed velocity feedback to close
the loop in order to get maximum benefit from the observer. The Live Scope in
Figure 8-29 shows the system response to a torque disturbance (the command source
defaults to zero in this model).
The benefits of using disturbance decoupling can be seen by adjusting the para-
meter K to 1 (to fully enable decoupling) as compared to 0 (to disable decoupling).
DD
Recall also from Chapter 5 that when K is set to 1, the control-loop integral gain
DD
needs to be zeroed to avoid ringing in the command step response.The step response
Figure 8-29. Experiment 8E: Disturbance decoupling in a motion system.

206 (cid:2) CHAPTER 8 USING THE LUENBERGEROBSERVER IN MOTION CONTROL
T
D
V
F
(a) (b)
Figure 8-30. Response to a 5-nm step torque disturbance without and with disturbance decoupling.
(a) Disabled decoupling (K =0, K=850). (b) Full decoupling (K =1, K=0).
DD I DD I
to a disturbance torque is shown with K set to 0 and 1 (with K zeroed when
DD I
K =1) in Figure 8-30. Disturbance decoupling reduces the excursion in velocity by
DD
more than half.Note that the ideal response would be no variation in velocity.
The Bode plot of the disturbance response is shown in Figure 8-31.There are two
gain plots, the one above for the system without decoupling and the one below for
Disturbance response
without disturbance
decoupling (K = 0, K = 850)
DD I
Disturbance response
Decoupling provides
with full disturbance
more than 10 dB
decoupling (K = 1 , K = 0)
improvement at 2 Hz DD I
Figure 8-31. Bode plot of disturbance response with and without disturbance decoupling.

|     |     |     | 8.3 USINGOBSERVERS |     | TOIMPROVEDISTURBANCERESPONSE |     |     | (cid:3) 207 |
| --- | --- | --- | ------------------ | --- | ---------------------------- | --- | --- | ----------- |
the system with full decoupling. These plots are obtained using the Dist Dsa, which
is at the top center of the model, and setting K to both 0 and 1 (and zeroing K
|     |     |     |     | DD  |     |     | I   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
when K =1).Notice that the system with disturbance decoupling provides more than
DD
10dB (10¥) enhancement at 2Hz.This is a substantial improvement,especially taking
into  account  that  the  velocity-loop  gains  were  already  tuned  to  high  values
(K P =4.2 and K I =850) in Section 8.2.1.2.
8.3.2 Observer-Based Acceleration Feedback
Acceleration feedback works by slowing the motor in response to measured acceler-
ation [9,12–14,21,25,27,32,38].The acceleration of the motor is measured,scaled
by K ,and then used to reduce the acceleration (current) command.The larger the
AFB
actual acceleration,the more the current command is reduced.K AFB has a similar effect
to increasing inertia; this is why acceleration feedback is sometimes called electronic
inertia or electronic flywheel [25, 26]. The idealized structure is shown in Figure 8-32
[12].
The effect of acceleration feedback is easily seen by calculating the transfer func-
tion of Figure 8-32. Start by assuming current loop dynamics are ideal: G PC (s)=1.
Applying the G/(1+GH) rule to Figure 8-32 produces the transfer function
|     | P (s)      |     | K J    |      | 1   |     |       |     |
| --- | ---------- | --- | ------ | ---- | --- | --- | ----- | --- |
|     | M =        |     | T      | T    | ¥   |     | (8.7) |     |
|     | I (s) 1+(K |     | J )¥(J | K )K | s2  |     |       |     |
|     | C          | T   | T      | T T  | AFB |     |       |     |
which reduces to
|     |     | P (s) | K J | 1   |     |     |       |     |
| --- | --- | ----- | --- | --- | --- | --- | ----- | --- |
|     |     | M     | T   | T   | .   |     |       |     |
|     |     |       | =   | ¥   |     |     | (8.8) |     |
|     |     | I (s) | 1+K | s2  |     |     |       |     |
C AFB
It is clear upon inspection of Equation 8.8 that any value of K >0 will have the
AFB
same effect as increasing the total inertia, J , by the factor of 1+K . Hence, K
|     |     |     | T   |     |     | AFB | AFB |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
can be thought of as electronic inertia.
| I + |     |     |     | I K | A 1 | V   | 1 P |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C   |     |     |     | F   | M   | M   | M   |     |
|     |     | G   | (s) |     | T   |     |     |     |
| _   |     | PC  |     | J   | s   |     | s   |     |
T
Current loop
J
|     | K   |     |     | T   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     | AFB |     | K   |     |     |     |     |     |
T
This signal reduces
|     |     | A , in units  |     |     |     |     |     |     |
| --- | --- | ------------- | --- | --- | --- | --- | --- | --- |
M
| commanded current |     | of current |     |     |     |     |     |     |
| ----------------- | --- | ---------- | --- | --- | --- | --- | --- | --- |
in proportion to
measured acceleration
|     | Figure 8-32. | Idealized acceleration feedback. |     |     |     |     |     |     |
| --- | ------------ | -------------------------------- | --- | --- | --- | --- | --- | --- |

208 (cid:2) CHAPTER 8 USING THE LUENBERGEROBSERVER IN MOTION CONTROL
The primary effect of feeding back acceleration is to increase the effective inertia.
However, this alone produces little benefit. The increase in effective inertia actually
reduces loop gain, reducing system response rates. The benefits of acceleration feed-
back are realized when control-loop gains are scaled up by the amount that the inertia
increases, that is, by the ratio of 1+K . This is shown in Figure 8-33. Here, as
AFB
K AFB increases, the effective inertia increases, and the loop gain is fixed so that the
stability margins and command response are unchanged.
Using the G/(1+GH) rule and allowing the 1+K terms to cancel,the command
AFB
| response for the system of |     | Figure 8-33 is |     |     |     |     |     |     |     |
| -------------------------- | --- | -------------- | --- | --- | --- | --- | --- | --- | --- |
s2)
|     |     | V (s) | G (s)¥G   | (s)¥K |       | (J     |     |       |     |
| --- | --- | ----- | --------- | ----- | ----- | ------ | --- | ----- | --- |
|     |     | M =   | C         | PC    | T     | T      |     | (8.9) |     |
|     |     | V (s) | 1+G (s)¥G |       | (s)¥K | (J s2) |     |       |     |
|     |     | C     | C         | PC    |       | T T    |     |       |     |
or
|     |     | V (s) | G (s)¥G |     | (s)¥K | J   |     |        |     |
| --- | --- | ----- | ------- | --- | ----- | --- | --- | ------ | --- |
|     |     | M     | C       | PC  |       | T T | .   | (8.10) |     |
=
|     |     | V (s) | s2+G | (s)¥G | (s)¥K | J   |     |     |     |
| --- | --- | ----- | ---- | ----- | ----- | --- | --- | --- | --- |
|     |     | C     |      | C     | PC    | T T |     |     |     |
Notice that the command response is unaffected by the value of K AFB .This is because
the loop gain increases in proportion to the inertia,producing no net effect.
The  disturbance  response  of Figure  8-33, unlike  the  command  response, is
improved by acceleration feedback.Again,using the G/(1+GH) rule,the disturbance
response is:
|     |     | V (s) | K   | [(1+K | )J  | ]   |     |        |     |
| --- | --- | ----- | --- | ----- | --- | --- | --- | ------ | --- |
|     |     | M     |     | T     | AFB | T   | .   | (8.11) |     |
=
|     |     | T (s) | s2+G | (s)¥G | (s)¥K | J   |     |     |     |
| --- | --- | ----- | ---- | ----- | ----- | --- | --- | --- | --- |
|     |     | D     |      | C     | PC    | T T |     |     |     |
For the idealized case of Equation 8.11,the disturbance response is improved through
the entire frequency range in proportion to the term 1+K .For example,if K is
|     |     |     |     |     |     | AFB |     |     | AFB |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
set to 10, the disturbance response improves by a factor of 11 across the frequency
range. Unfortunately, such a result is impractical. First, the improvement cannot be
realized significantly above the bandwidth of the power converter (current loop).This
Scale the PI output up by the same
amount effective inertia increases.
T
| V   |     | I   | I   |     | D   |     | A   | V   | P   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C   |     | C   | F   |     |     |     | M   | M   | M   |
+
|     |               |                                                               |     |     |     |       | 1      | 1   | 1   |
| --- | ------------- | ------------------------------------------------------------- | --- | --- | --- | ----- | ------ | --- | --- |
|     | G (s)         | 1+ K G                                                        | (s) | K   |     |       |        |     |     |
|     | C             | AFB                                                           | PC  | T   |     | (1+ K | ) J    | s   | s   |
| _   |               |                                                               |     |     | +   |       |        |     |     |
| +   |               |                                                               |     |     |     |       | AFB  T |     |     |
|     | PI Controller |                                                               |     |     |     | Motor |        |     |     |
|     | Figure 8-33.  | Velocity controller based on idealized acceleration feedback. |     |     |     |       |        |     |     |

|     |     |     | 8.3 USINGOBSERVERS | TOIMPROVEDISTURBANCERESPONSE |     | (cid:3) 209 |
| --- | --- | --- | ------------------ | ---------------------------- | --- | ----------- |
is clear upon inspection as the acceleration feedback signal cannot improve the system
at frequencies where the current loop cannot inject current.The second limitation on
acceleration feedback is the difficulty in measuring acceleration.While there are accel-
eration sensors that are used in industry,few applications can afford either the increase
in cost or the reduction in reliability brought by an addition sensor and its associated
wiring. One solution to this problem is to use observed acceleration rather than
measured.Of course,the acceleration can be observed only within the capabilities of
the observer configuration;this limits the frequency range over which the ideal results
of Equation 8.11 can be realized.
| 8.3.2.1 Using Observed Acceleration |     |     |     |     |     |     |
| ----------------------------------- | --- | --- | --- | --- | --- | --- |
Observed acceleration is a suitable alternative for acceleration feedback in many
systems where using a separate acceleration sensor is impractical. Such a system is
shown in Figure 8-34. The observed acceleration, A , is scaled to current units and
O
deducted from the current command.The term 1+K scales the control-law output
AFB
as it did in Figure 8-33.
| 8.3.2.2 Experiment 8F: Using Observed Acceleration Feedback |     |     |     |     |     |     |
| ----------------------------------------------------------- | --- | --- | --- | --- | --- | --- |
Experiment  8F  models  the  acceleration-feedback  system  of Figure  8-34  (see
Figure 8-35); the structure is quite similar to the disturbance-decoupling system
of Figure 8-29. The velocity loop uses the observed velocity feedback to close the
V
T
| C     |      | I   | I       | D   |         |     |
| ----- | ---- | --- | ------- | --- | ------- | --- |
|       |      |     |         | V   | P =P    |     |
|       |      | C   | F       |     |         |     |
| +     |      | +   |         | + 1 | M 1 M F |     |
| G (s) |      |     |         |     |         |     |
|       | 1+ K |     | G (s) K |     |         |     |
| _ C   | AFB  | _   | PC T    | J s | s       |     |
+ T
Control
|     |     |     |     | Motor | Sensor |     |
| --- | --- | --- | --- | ----- | ------ | --- |
V
| F law |     | K   |     |       |     |     |
| ----- | --- | --- | --- | ----- | --- | --- |
|       |     | AFB |     |       | P + |     |
|       |     |     |     | G (s) | OE  |     |
CO
|     |     |     |     | A   | _   |     |
| --- | --- | --- | --- | --- | --- | --- |
|     |     |     | K   | DO  |     |     |
TEst
J
Observed
TEst
acceleration
|     | (in units   |     | +   | A V    | P     |     |
| --- | ----------- | --- | --- | ------ | ----- | --- |
|     |             |     |     | O Tz O | Tz O  |     |
|     | of current) |     |     | z-1    | z-``1 |     |
|     |             | J   | +   |        |       |     |
Est
|        |     | K    |              | Motor | Sensor |     |
| ------ | --- | ---- | ------------ | ----- | ------ | --- |
|        |     | TEst | Observed     |       |        |     |
| V      |     |      |              | Model | Model  |     |
| S z -1 |     |      | acceleration |       |        |     |
T``z
Figure 8-34. Observer-based acceleration feedback in motion systems.

210 (cid:2) CHAPTER 8 USING THE LUENBERGEROBSERVER IN MOTION CONTROL
Figure 8-35. Experiment 8F: Using observed acceleration feedback.
loop. Again, a single term, K /J , is formed at the bottom center of the model
TEst TEst
to convert the current-loop output to acceleration units and to convert the
observed acceleration to current units. Unlike Figure 8-29, the term 1+K is
AFB
formed using a summing block (at bottom center) and used to scale the control-law
output, consistent with Figure 8-33. As in Figure 8-29, an explicit clamp is used
to ensure that the maximum commanded current is always within the ability of the
power stage. The Live Scope in Figure 8-29 shows the system response to a torque
disturbance.
The improvement of acceleration feedback is evident in the step response, as
shown in Figure 8-36. As was the case with disturbance decoupling, recall that
without acceleration feedback, the control-law gains were set as high as was practi-
cal; the non-acceleration-feedback system took full advantage of the reduced phase
lag of the observed velocity signal.Still,acceleration feedback produces a substantial
benefit.
The Bode plot of the system with and without acceleration feedback is shown in
Figure 8-37. The acceleration feedback system provides benefits at all frequencies
below about 400Hz. Figure 8-37 shows two levels of acceleration feedback:
K =1.0 and K =10.0. This demonstrates that as the K increases, disturbance
AFB AFB AFB
response improves, especially in the lower frequencies where the idealized model of
Figure 8-32 is accurate. Note that acceleration feedback tests the stability limits of
the observer. Using the observer as configured in Experiment 8F, K cannot be
AFB
raised above 1.2 without generating instability in the observer. The problem is cured
by reducing the sample time of the observer through changing the Live Constant

|     | 8.3 USINGOBSERVERS | TOIMPROVEDISTURBANCERESPONSE |     | (cid:3) 211 |
| --- | ------------------ | ---------------------------- | --- | ----------- |
T
D
V
F
| (a) | (b) |     | (c) |     |
| --- | --- | --- | --- | --- |
Figure 8-36. Response to a 5-nm step disturbance without and with acceleration feedback.
(a) Without acceleration feedback (K =0.0), (b) with minimal acceleration feedback (K =1.0),
| AFB |     |     | AFB |     |
| --- | --- | --- | --- | --- |
(c) with more acceleration feedback (K =10.0).
AFB
named T to 0.0001. This allows K to be raised to at least 20 without
| SAMPLE | AFB |     |     |     |
| ------ | --- | --- | --- | --- |
generating instability. It should be pointed out that changing the sample time of a
model is easy but may be quite difficult in a working system. See Exercise 8-5 for
more discussion of this topic.
Without
acceleration
feedback
(K
AFB  = 0)
With With acceleration
| acceleration |     | feedback        |     |     |
| ------------ | --- | --------------- | --- | --- |
| feedback     |     | (K AFB  = 10.0, |     |     |
| (K  = 1.0)   |     | T  = 0.0001)    |     |     |
| AFB          |     | SAMPLE          |     |     |
Figure 8-37. Bode plot of velocity loop disturbance response without (K =0) and with (K =1.0, 10.0)
|     |     | AFB | AFB |     |
| --- | --- | --- | --- | --- |
acceleration feedback.

212 (cid:2) CHAPTER 8 USING THE LUENBERGEROBSERVER IN MOTION CONTROL
8.4 Exercises
1. Verify that at the first phase crossover (200Hz),the gain margin ofthe observer
in Experiment 8B is set almost entirely by the value of the integral gain, K .
IO
Hint: Take the open-loop plot gain with K =0 and compare to open-loop plot
IO
with default K at and around 200Hz.
IO
2. Use Experiment 8A to compare the disturbance response of observer- and non-
observer-based systems with identical control-law gains. Compile and run the
model. Change the input from command to disturbance as follows. Double-
click on Command Wave Gen and set the amplitude to 0.0001 (this is set low
enough to be insignificant but high enough to continue to trigger the Live
Scopes).Similarly,set the amplitude of the DisturbanceWave Gen to 2.0.The
Live Scopesare now showing the velocity signals in response to a disturbance.
A. Compare the three velocity signals.Notice that the three Live Scopesat the
bottom compare the three velocity signals to the actual motor velocity.
B. Predict which signals will give the best disturbance response with the
default set of control-loop gains.
C. Using Dist DSA,measure and compare the disturbance response based on
each of the three signals.
3. Using the Live Scope displays at the bottom of Experiment 8A, compare the
noise sensitivity ofthe three velocity signals.Enable resolution by double click-
ing on the Live Constant Use Res? at top right and select Yes. Compare the
results here to Exercise 8-2.
4. Use Experiments 8A and 8C to evaluate the robustness of an observer-based
system in the presence of fluctuations of total inertia (J ).
T
A. Find the PM of the encoder system of Experiment 8A with nominal para-
meters,using V and V as feedback.
O OMod
B. Repeat with the total inertia reduced from 0.002 to 0.0014.
C. Which system appears more robust, the one dependent on V or the one
O
dependent on V ?
OMod
D. Repeat part A for the resolver-based system of Experiment 8C.
E. Repeat part B for the resolver-based system of Experiment 8C.
F. Repeat part C for the resolver-based system of Experiment 8C.
5. Use Experiment 8F to study the relationship between acceleration feedback
and system sample time. Use the Live Scope display to see instability caused
by excessive values of K .
AFB
A. Make a table that shows the relationship between the maximum allowable
K with the system–observer sample time (T ) set at 0.00025,
AFB SAMPLE
0.0002,and 0.00015.
B. Compare the improvement in low-frequency disturbance response (say,
10Hz) for each of the three settings to the baseline system (K =0).(Set
AFB
TSampleto 0.0001s for this part;this improves the readings from the DSA
without requiring you to change the FFT sample time.)
C. Compare the results in part B to the ideal improvement gained by using
acceleration feedback.

References
1. D.H.Sheingold,Ed.,Analog-Digital Conversion Handbook,3rd Edition,Analog Devices,
Prentice Hall,Englewood Cliffs,NJ,1994.
2. A.Antoniou,Digital Filters Analysis,Design,and Applications,2ndEd.McGraw-Hill,New
York,1993.
3. B.Armstrong-Helouvry,Control of Machines with Friction,Kluwer Academic Publishers,
New York,1991.
4. G. Biernson, Principles of Feedback Controls, Vol. 1. John Wiley and Sons, New York,
1988.
5. G. Biernson, Principles of Feedback Controls, Vol. 2. John Wiley and Sons, New York,
1988.
6. J.Burke,“Extraction ofHigh Resolution Position Information from Sinusoidal Encoders,”
Proc.PCIM-Europe,Nuremberg,(1999):217–222.
7. J.D’Azzo and C.Houpis,Linear Control System Analysis and Design 3rdEdition,McGraw
Hill,New York,1988.
8. Data Devices Corp.,Manual for 19220 RDC (19220sds.pdf).Available at
www.ddc-web.com (use product search for “19220”).
9. J. Deur, “A Comparative Study of Servosystems with Acceleration Feedback,” Proc of
IEEE IAS,Rome,(2000).
10. R.Dorf,Modern Control Systems (6thEd.),Addison-Wesley,Boston,1992.
11. G.Ellis,Control System Design Guide (2ndEd.),Academic Press,Boston,2000.
12. G.Ellis and R.D.Lorenz,“Resonant Load Control Methods for Industrial Servo Drives,”
Proc.of IEEE IAS,Rome,(2000).
13. G.Ellis,“Cures for Mechanical Resonance in Industrial Servo Systems,”PCIM Proceed-
ings,Nuremberg,(2001):187–192.(Copied in Appendix A.)
14. G. Ellis and J.O. Krah, “Observer-Based Resolver Conversion in Industrial Servo
Systems,”PCIM Proceedings,Nuremberg,(2001):311–316.(Copied in Appendix B.)
15. J.Fassnacht,“Benefits and Limits of Using an Acceleration Sensor in Actively Damping
High Frequency Mechanical Oscillations,” Conf. Rec. of the IEEE IAS, (2001): 2337–
2344.
213

214 (cid:2) REFERENCES
16. G.F.Franklin et al.,Digital Control ofDynamic Systems,3rdEd.,Addison-Wesley,Boston,
1998.
17. G.F. Franklin et al., Feedback Control of Dynamic Systems, 3rd Ed., Addison-Wesley,
Boston,1994.
18. B.K.Ghosh et al.,Control in Robotics and Automation,Academic Press,Boston,1999.
19. M.Gopal,Modern Control System Theory,John Wiley and Sons,New York,1993.
20. Y.Hori et al.,“Slow Resonance Ratio Control for Vibration Suppression and Disturbance
Rejection in Torsional System,”IEEE Trans.Ind.Elec.46(Feb.1999):162–168.
21. J.K. Kang and S.K. Sul, “Vertical-Vibration Control of Elevator Using Estimated Car
Acceleration Feedback Compensation,” IEEE Trans. on Ind. Elec. 47 (February 2000):
91–99.
22. J.O.Krah,“Software Resolver-to-Digital Converter for High Performance Servo Drives,”
Proc.PCIM-Europe,Nuremberg,(1999):301–308.
23. H.S. Lee and M. Tomizuka, “Robust Motion Controller Design for High Accuracy
Positioning Systems,”IEEE Trans.Ind.Elec.43(February 1996):48–55.
24. Y.M. Lee et al., “Acceleration Feedback Control Strategy for Improving Riding Quality
of Elevator System,”Proc.of IEEE IAS,Phoenix,(1999):1375–1379.
25. R.D. Lorenz, “New Drive Control Algorithms (Stae Control, Observers, Self-Sensing,
Fuzzy Logic,and Neural Nets),”Proc.PCIM Conf.,Las Vegas,(September 1996).
26. R.D. Lorenz, “Modern Control of Drives,” COBEP’97, Belo Horizonte, MG, Brazil,
(December 1997):45–54.
27. R.D. Lorenz, “ME-746. Dynamics of Controlled Systems: A Physical Systems-Based
Methodology for Non-Linear,Multivariable,Control System Design,”Video Class,Uni-
versity of Wisconsin-Madison,1998.
28. S.J. Mason, “Feedback Theory: Some Properties of Signal Flow Graphs,”Proc. IRE 41
(July 1953):1144–1156.
29. S.J.Mason,“Feedback Theory:Further Properties of Signal Flow Graphs,”Proc.IRE44
(July 1956):920–926.
30. S.McClellan “Electromagnetic Compatibility for SERVOSTAR®S and CD.”Available at
www.motionvillage.com/training/handbook/cabling/shielding.html.
31. D.B.Miron,Design of Feedback Control Systems,Harcourt,San Diego,1989.
32. M.H.Moatemri et al.,“Implementation of a DSP-Based,Acceleration Feedback Robot
Controller:Practical Issues and Design Limits,”Conf.Rec.IEEE IAS Annual Mtg,(1999):
1425–1430.
33. F. Nekoogar and G. Moriarty, Digital Control using Digital Signal Processing, Prentice-
Hall,Englewood Cliffs,NJ,1999.
34. W.Palm,Modeling,Analysis and Control ofDynamic Systems,John Wiley and Sons,New
York,1983.
35. J.W. Park et al., “High Performance Speed Control of Permanent Magnet Synchronous
Motor with Eccentric Load,”Conf.Rec.IEEE IAS Annual Mtg,(2001):815–820.
36. C.L. Phillips and R.D. Harbor, Feedback Control Systems, 2nd Edition, Prentice-Hall,
Englewood Cliffs,NJ,1991.
37. O.Rubin,The Design ofAutomatic Control Systems,Artech House,Norwood,MA,1986.
38. P.B. Schmidt and R.D. Lorenz, “Design Principles and Implementation of Acceleration
Feedback to Improve Performance of DC Drives,”IEEE Trans.on Ind.Appl,(May/June
1992):594–599.
39. Y.S.Suh and T.W.Chun,“Speed Control of a PMSM Motor Based on the New Distur-
bance Observer,”Conf Rec.of IEEE IAS Annual Mtg.,(2001):1319–1326.

REFERENCES (cid:3) 215
40. S.M. Yang and S.J. Ke, “Performance Evaluation of a Velocity Observer for Accurate
Velocity Estimation of Servo Motor Drives,”ConfRec.ofIEEE IAS Annual Mtg.,(1998):
1697.
41. J.Yoshitsugu et al.,“Fuzzy Auto-Tuning Scheme based on a-Parameter Ultimate Sensi-
tivity Method for AC Speed Servo System,”Conf Rec.of IEEE IAS Annual Mtg.,(1998):
1625.
42. G.W. Younkin et al., “Considerations for Low-Inertia AC Drives in Machine Tool Axis
Servo Applications,”IEEE Trans.on Ind.Appl.27(March/April 1991):262–268.

Appendix A
Observer-Based Resolver
Conversion in Industrial
Servo Systems1
George Ellis
Kollmorgen,A Danaher Motion Company
Jens Ohno Krah
Kollmorgen Seidel,Germany
Resolvers are commonly used in industrial servo systems.The conversion of resolver
signals to measure position is usually accomplished using a tracking loop which causes
phase lag between the actual and the measured positions.This phase lag causes insta-
bility in the control loop and ultimately reduces performance of the servo system.
Observers are well known to reduce phase lag caused by sensors.Observers in servo
systems use a combination of the position signal and the torque producing current
to observe the motor speed. Resolver-to-digital converters (RDCs) have a structure
similar to observers so that RDCs can be modified to behave like observers. This
provides several advantages including providing position and velocity feedback with
little or no phase lag and providing estimations of motor acceleration and torque
disturbance.Acceleration feedback can be used to reduce problems with mechanical
resonance.Torque disturbance feedback can be used to improve the dynamic stiffness
of the control system.
1Presented at PCIM 2001 Conference,Nuremberg,Germany,June 19–21,2001.
Copyright ZM Communications.Reprinted by permission.
217

Appendix B
Cures for Mechanical
Resonance in Industrial
Servo Systems1
George Ellis
Kollmorgen,A Danaher Motion Company
Mechanical resonance is a pervasive problem in servo systems.Most problems of res-
onance are caused by the compliance of power transmission components. Standard
servo control laws are structured for rigidly coupled loads. However, in practical
machines some compliance is always present;this compliance often reduces stability
margins,forcing servo gains down and reducing machine performance.
Mechanical resonance falls into two categories:low frequency and high frequency.
High-frequency resonance causes instability at the natural frequency of the mechan-
ical system, typically between 500 and 1200Hz. Low-frequency resonance occurs at
the first phase crossover, typically 200 to 400Hz. Low-frequency resonance occurs
more often in general industrial machines.This distinction,rarely made in the litera-
ture,is crucial in determining the most effective means of correction.This paper will
present several methods for dealing with low-frequency resonance, all of which are
compared with laboratory data.
Introduction
It is well known that servo performance is enhanced when control-law gains are high.
However, instability results when a high-gain control law is applied to a compliantly
coupled motor and load. Machine designers specify transmission components, such
as couplings and gearboxes, to be rigid in an effort to minimize mechanical compli-
1Presented at PCIM 2001 Conference,Nuremberg,Germany,June 19–21,2001.
Copyright ZM Communications.Reprinted by permission.
227

228 (cid:2) APPENDIXBCURES FORMECHANICALRESONANCE ININDUSTRIAL SERVOSYSTEMS
T M
|     |     | J   | K   |     | J   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
|     |     | M   | S   |     | L   |     |     |
Figure 1. Simple compliantly coupled motor and load.
ance.However,some compliance is unavoidable.In addition,marketplace limitations,
such as cost and weight, force designers to choose lighter weight components than
would otherwise be desirable. Often, the resulting rigidity of the transmission is so
low that instability results when servo gains are raised to levels necessary to achieve
desired performance.
The well-known lumped-parameter model for a compliantly coupled motor and
load is shown in Figure 1 and a block diagram is shown in Figure 2 [1]. The load
and motor are two independent inertias connected by nonrigid components. The
equivalent spring constant of the entire transmission is K ; also, a viscous damping
S
term, b , is shown in Figure 2, which produces torque in proportion to the velocity
S
difference of motor and load.
Two-Part Transfer Function
The transfer function from drive current, I ,to motor velocity, V ,is
|     |       |        | F             |        |       | M   |     |
| --- | ----- | ------ | ------------- | ------ | ----- | --- | --- |
| V   | (s) Ê | K 1ˆÊ  | J s2+b        | s+K    |       | ˆ   |     |
| M   | =     | T      | L             | S      | S     | .   | (1) |
|     | ËJ    | s¯Ë(J  |               | ))s2+b |       | ¯   |     |
| I F | (s)   | M +J L | L J M (J L +J | M      | S s+K | S   |     |
Equation (1) has two terms. The term on the left is a rigidly coupled motor and
load and the term on the right is the effect of the compliant coupling. Note that
Equation (1) represents the plant in the case where the feedback sensor is on the
motor (as oppose to the load),as is common in industry.
T
D
V
|     | +   | + 1 | 1   | M   | 1   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
| I K |     |     |     |     |     |     | P   |
| F   | T _ | _ J | s   |     | s   |     | M   |
|     |     | M   |     |     |     |     |     |
|     |     |     | b   | +   |     |     |     |
|     |     |     | S   | _   |     |     |     |
|     |     |     |     |     |     | +   |     |
K
|     |     |     | S   |     |     | _   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |

|     | +   | + 1 | 1   |     | 1   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
P
|     |     | J   | s   |     | s   |     | L   |
| --- | --- | --- | --- | --- | --- | --- | --- |
V
|     |     | L   |     | L   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
Figure 2. Block diagram of compliantly coupled load.

LOW-FREQUENCYRESONANCE (cid:3) 229
Key problem for low-
frequency resonance:
|       | Compliantly-coupled | decoupling of load raises   |     |     |
| ----- | ------------------- | --------------------------- | --- | --- |
| 40 dB | motor and load      | effective loop gain above F |     | .   |
R
F
R
20 dB
F AR
0 dB
Rigidly-coupled
| 20  | 100 |     | 1000 |     |
| --- | --- | --- | ---- | --- |
motor and load
| Hz Gain | Hz  |     |  Hz |     |
| ------- | --- | --- | --- | --- |
Phase
0∞
-180∞
Figure 3. Plot of motor–load plant with 5:1 load-to-motor inertia ratio.
The ideal plant for traditional control laws is a scaled integrator.The term on the
left of Equation (1) is such a plant. However, that ideal plant is corrupted by the
compliance term (right side of Equation (1)).Figure 3 shows a Bode plot of Equation (1)
where the load has about five times more inertia than the motor.The compliance term
has a gain peak at the resonant frequency, F , and a gain minimum at the antireso-
R
nant frequency,F ,as shown in (2).The corrupting effect of compliance can be seen
AR
in Figure 3.Were the load rigidly coupled,the plant would be the ideal integrator (the
left side of Equation (1)) which is shown as a dashed line.However,compliance causes
attenuation at and around F and amplification at, around, and above F .
|     | AR       |          |     | R   |
| --- | -------- | -------- | --- | --- |
|     | 1 K SHz, | 1 K SHz. |     |     |
|     | F =      | F =      |     | (2) |
|     | R 2p J   | AR 2p J  |     |     |
|     | P        | L        |     |     |
Low-Frequency Resonance
The key problem in low-frequency resonance is the increase in gain at frequencies
above F [1].As shown in Figure 3,below F the transfer function acts like a simple
| R   |     | AR  |     |     |
| --- | --- | --- | --- | --- |
integrator.The gain falls at 20dB/decade and the phase is approximately -90°.It also
behaves like an integrator above F ,but with a gain substantially increased compared
R
to the gain well below F . Above F , the load is effectively disconnected from the
|     | AR R |     |     |     |
| --- | ---- | --- | --- | --- |
motor so that the gain of the plant is the inertia of the motor.In Figure 3,which has
a 5:1 load-to-inertia ratio, the effective inertia falls by a factor of 6dB. This raises
the loop gain by 16dB at high frequencies,reducing margins of stability.

230 (cid:2) APPENDIXBCURES FORMECHANICALRESONANCE ININDUSTRIAL SERVOSYSTEMS
V C V E PI + I C I F Motor P M
Current
Control Filters K and Enc. P
_ _ controller T F
+ laws load
A
MO
G Observer
V VD
F
Difference
Figure 4. Velocity control system.
Velocity Control Law
Figure 4 shows a velocity control system. The velocity error (V ) is processed by a
E
control law and filters. The current command, I , is connected to the current con-
C
troller, which produces current, I , in the motor. The motor–load plant is connected
F
to an encoder. An observer, fed by the feedback current and position, produces an
observed acceleration,A .The observer will be discussed in detail later.With excep-
MO
tion to the observer,Figure 4 represents a velocity control loop as is commonly used
in industry.
The problem caused by the compliant (right) term in Equation (1) is seen in the
open-loop Bode plot of the velocity controller of Figure 4. The open-loop transfer
function,V (s)/V (s),is well known to predict stability problems using two measures:
F E
phase margin (PM) and gain margin (GM). PM is the difference of -180° and the
phase of the open loop at the frequency where the gain is 0dB. GM is the negative
of the gain of the open loop at the frequency where the phase crosses through -180°.
The open-loop plot for a rigidly coupled load demonstrating low-frequency
resonance is shown in Figure 5. The harmful effects of compliance are seen in the
GM.As marked in Figure 5,when the resonant frequency is well below the first phase
crossover (270Hz) the effect of the compliant load is to reduce the GM approximately
by the amount (J +J )/J .If J /J (the inertia mismatch) is 5,the reduction of GM
M L M L M
will be 6 or about 16dB. Assuming no other remedy were available, the gain of the
compliantly coupled system would have to be reduced by 16dB, compared to the
rigid system, assuming both would maintain the same GM. Such a large reduction
in gain would translate to a system with much poorer command and disturbance
response.
High-frequency resonance is different; it occurs in lightly damped mechanisms
when the natural frequency of the mechanical system (F ) is well above the first phase
R
crossover. Here, the gain near F forms a strong peak. The gain caused by a lightly
R
damped right-hand term in Equation (1) can exceed 40dB. While both types of
resonance are caused by compliance, the relationship of the F and the first phase
R
crossover changes the remedy substantially; cures of high-frequency resonance can
exacerbate problems with low-frequency resonance. The mechanical structures that
cause high-frequency resonance (stiff transmission components and low damping) are

METHODSOFCORRECTIONAPPLIEDTO LOW-FREQUENCYRESONANCE (cid:3) 231
Open loop gain with The effective gain
compliant coupling increase that results
from the compliant
load reduces the GM.
Open loop gain with
Here the GM is just
0 dB ideal (rigid) coupling
over 10 dB. With the
ideal system, the GM
-20 dB would have been
about 30 dB.
20 Hz 100 Hz 500 Hz
0∞
First phase
crossover
-180∞
~270 Hz
Figure 5. Open loop with low-frequency resonance.
typical of high-end servo machines such as machine tools. Smaller and more cost-
sensitive general-purpose machines in such industries as packaging,textiles,plotting,
and medical typically have less rigid transmissions and higher damping so that low-
frequency resonance is more common.
Methods of Correction Applied to Low-Frequency Resonance
Numerous methods have been used to remedy resonance [1–5].The most common in
industry is the low-pass filter. Another method suggested by numerous authors is
acceleration feedback, where the acceleration is provided by an observer. This paper
will not discuss the notch filter,which is effective with high-frequency resonance,but
not with low-frequency resonance, a problem that appears over a broad frequency
range.
Test Unit
The test unit,shown in Figure 6,is a motor and load connected by plastic tubing that
has been slit to increase compliance.The motor inertia is 1.8¥10-5kg–m2and the load
is 6.3¥10-5kg–m2(both include the coupling to the tubing).The coupling has a com-
pliance of 30Nm/rad.This ratio produced a resonant frequency of about 230Hz and
an antiresonant frequency of about 110Hz. These figures are consistent with
machines used in industry. The drive used was a 3 Amp Kollmorgen ServoStar 600

232 (cid:2) APPENDIXBCURES FORMECHANICALRESONANCE ININDUSTRIAL SERVOSYSTEMS
Other couplings used in testing
MT1502 Motor
J=1.8x10-5 kg-m2
Load
(includes coupling)
J=6.3x10-5 kg-m2 Coupling
K =30 Nm/rad
S
Figure 6. Test-unit mechanism is a scaled model of machines commonly used in industry.
amplifier executing the velocity loop at 16kHz.This drive is equipped with low-pass
and biquadratic filters,an observer, and acceleration feedback.
Baseline System
The baseline system had no filters and did not use acceleration feedback.The PI con-
troller was tuned to maximize performance.The proportional gain was raised as high
as possible without generating large oscillations (G =2.5). The integral gain was
V
then raised until a step command generated 25% overshoot (G =10ms). The step
VTN
response is shown in Figure 7. Settling time was about 60ms. The -3-dB bandwidth
was measured as 23Hz.
Low-Pass Filter
A single-pole low-pass filter was used. The frequency was adjusted to 50Hz. Servo
gains could be raised to G =5 and G =17ms. The settling time improved to
V VTN
35ms.The bandwidth was 35Hz.
V
C
V
F
Figure 7. Step response of baseline system.

METHODSOFCORRECTIONAPPLIEDTO LOW-FREQUENCYRESONANCE (cid:3) 233
Biquadratic Filter
A biquadradic filter was applied to the system.A biquad filter has two poles and two
zeros; it can be thought of as a high-pass filter in series with a low-pass filter. For
these tests, the best case adjustment found experimentally was to set the high-pass
filter at 250Hz and the low-pass filter at 100Hz.The gains were raised again,this time
to G =8 and G =10ms. Performance improved further. Settling time was reduced
V VTN
to 22ms. The bandwidth was measured as 56Hz.
Acceleration Feedback
Acceleration feedback was applied [6–15]. Acceleration was observed using a Luen-
berger observer, as shown in Figure 8. The observer takes input from the motor
current and the encoder.It adds the two and feeds the sum to a model of the motor.
That model produces the observed position, which is compared to the actual posi-
tion.The PID observer compensator drives out most error up to the observer band-
width, which is usually between 200 and 500Hz. One by-product of the observer
is an acceleration signal, which represents acceleration much better than double-
differentiating the position feedback signal. A more complete discussion of the
observer can be found in [6,9–11].
Acceleration feedback was applied to the biquad system. The gain G was set to
VD
15, which is approximately 2.5 in the SI units shown in Figure 8. This reduced the
effects of resonance and the PI gains were raised (G =22 and G =12).The results
V VTN
were a dramatic improvement over the other systems. Settling time was reduced to
just 12ms and the bandwidth was measured as 77Hz. The step response is shown in
Figure 9.
Comparison of All Methods
All three methods (low pass, biquad, and acceleration feedback–biquad) are
compared in the frequency domain with the closed-loop Bode plot (V (s)/V (s)) of
F C
Figure 10. This plot is generated by the ServoStar 600 Drive on the test mechanism
+ I I Physical system
From C Current F
Motor/Load Enc. P
PI _ Loops F
G x J + + +
VD PID Observer compensator
K _
T
K T Model motor
A
MEst
Js2
Observer
Figure 8. Luenberger observer provides observed acceleration (A ).
MEst

234 (cid:2) APPENDIXBCURES FORMECHANICALRESONANCE ININDUSTRIAL SERVOSYSTEMS
V
C
V
F
Figure 9. Step response of system with acceleration feedback.
of Figure 6. The results show the dramatic improvement offered by acceleration
feedback. Notice that the bandwidth (the frequency where the gain falls to -3dB) is
greatly increased. In addition, stability margins are maintained. Peaking, the unde-
sirable phenomenon where gain rises above 0dB at high frequency in the closed-loop
response,is a reliable measure of stability.As shown in Figure 10,the peaking of all
four configurations is about the same, with the baseline system displaying the most
peaking. This indicates that the cures for resonance allow higher gain while main-
taining equivalent margins of stability.
Base line
peaking: 8 dB
Bi-quad filter Acc fb BW: Peaking at first
BW: 56 Hz 77 Hz phase crossover
(230 Hz) indicates
instability with
-3dB low-frequency res.
Baseline system
has the most
Base line
peaking; the other
BW: 23 Hz
three are roughly
One low-pass
equivalent.
BW: 35 Hz 100 Hz 200 Hz
0∞
-180∞
Figure 10. Comparison of closed-loop responses of baseline and when using three antiresonance methods.

REFERENCES (cid:3) 235
Conclusion
Low-frequency resonance is common in industry.It differs from the less common,but
more often studied problem of high-frequency resonance. Low-frequency resonance
causes oscillations at the first phase crossover ofthe open-loop system;high-frequency
resonance causes oscillations at the natural mechanical frequency of the mechanism.
Low-frequency resonance can be addressed by several methods including low pass,
biquadratic filters, and acceleration feedback. Acceleration feedback is a practical
method for curing low-frequency resonance.It has been implemented in an industrial
motor controller.
Acceleration feedback in combination with the biquad filter provides dramatic
improvement for systems suffering from low-frequency resonance. This was demon-
strated on laboratory hardware.Compared to the traditional solution of a single-pole
low-pass filter, the combination of acceleration feedback and the biquad filter allow
the settling time to be cut by a factor of three (from 35 to 12ms) and the bandwidth
to be raised by that same factor (23 to 77Hz). At the same time, acceleration feed-
back maintained stability margins, indicating that the increased gain of the servo
system will be useful in practical applications.
Acknowledgments
The author thanks Dr. Jens Krah for his contributions to this paper, which include
implementing the observer and acceleration feedback in the ServoStar 600 and pro-
viding numerous helpful insights.
References
1. G.Ellis,“Control System Design Guide”(2nd ed.),Academic Press,Boston,2000.
2. P. Schmidt and T. Rehm, Notch filter tuning for resonant frequency reduction in dual
inertia systems,in“Proc.of IEEE IAS,Phoenix,Oct.3–7,1999,”pp.1730–1734.
3. S. Vukosavic and M. Stojic, Suppression of torsional oscillations in a high-performance
speed servo drive,IEEE Trans.Ind.Elec.45(1998),108–117.
4. H.Wertz and F.Schütte,Self-tuning speed control for servo drives with imperfect mechan-
ical load,in“Proc of IEEE IAS,Rome,”2000.
5. R.Dhaouadi,K.Kubo,and M.Tobise,Analysis and compensation ofspeed drive systems
with torsional loads,IEEE Trans.Ind.Appl.30(1994),760–766.
6. G.Ellis and J.O.Krah,Observer-based resolver conversion in industrial servo systems,in
“PCIM-Europe,2001.”
7. Y.Hori,H.Sawada,and Y.Chun,Slow resonance ratio control for vibration suppression
and disturbance rejection in torsional system,IEEE Trans.Ind.Elec.46(1999),162–168.
8. J.Deur,A comparative study ofservosystems with acceleration feedback,in“Proc ofIEEE
IAS,Rome,2000.”
9. G. Ellis and R.D. Lorenz, Resonant load control methods for industrial servo drives, in
“Proc.of IEEE IAS,Rome,2000.”

236 (cid:2) APPENDIXBCURES FORMECHANICALRESONANCE ININDUSTRIAL SERVOSYSTEMS
10. P.B. Schmidt and R.D. Lorenz, Design principles and implementation of acceleration
feedback to improve performance of DC drives,IEEE Trans.Ind.Appl.(May/June 1992),
594–599.
11. M.H. Moatemri, P.B. Schmidt, and R.D. Lorenz, Implementation of a DSP-based,
acceleration feedback robot controller: Practical issues and design limits, in “IEEE-IAS
Conf.Rec.,1991,”pp.1425–1430.
12. Y.M.Lee,J.K.Kang,and S.K.Sul,Acceleration feedback control strategy for improving
riding quality of elevator system,in“Proc.of IEEE IAS,Phoenix,1999,”pp.1375–1379.
13. J.K. Kang and S.K. Sul, Vertical-vibration control of elevator using estimated car
acceleration feedback compensation,IEEE Trans.Ind.Elec.47(2000),91–99.
14. R.H. Welch, “Mechanical Resonance in a Closed-Loop Servo System: Problems and
Solutions,”Tutorial from Welch Enterprises,Oakdale,MN.
15. G.W. Younkin, W.D. McGlasson, and R.D. Lorenz, Considerations for low-inertia AC
drives in machine tool axis servo applications,IEEE Trans.Ind.Appl.27(1991),262–268.

Appendix C
European Symbols for
Block Diagrams
This appendix lists the symbols for the most common function blocks in formats typ-
ically used in North America and in Europe. Block diagram symbols in most North
American papers,articles,and product documentation rely on text.Most linear func-
tions are described by their s-domain or z-domain transfer functions;nonlinear func-
tions are described by their names (frictionand sin).On the other hand,block diagram
symbols in European literature are generally based on graphical symbols.Linear func-
tions are represented by the step response.There are exceptions in both cases.In North
American documentation,saturation and hysteresis are typically shown symbolically,
whereas European literature uses text for transcendental functions.
Part I: Linear Functions
237

| 238 (cid:2) | APPENDIXCEUROPEAN | SYMBOLSFOR BLOCKDIAGRAMS |
| ----------- | ----------------- | ------------------------ |
Part II: Nonlinear Functions

PARTII:NONLINEARFUNCTIONS (cid:3) 239

Appendix D
Development of the
Bilinear Transformation
Bilinear Transformation
The bilinear transformation is so named because it approximates zwith a ratio of two
linear functions in s.Begin with the definition of z:
esT2
z∫esT = (D.1)
e-sT2
The Taylor series for esT is
(sT)2 (sT)3
z=1+sT+ + +◊◊◊ (D.2)
2! 3!
Using the first two terms of the Taylor series for both the numerator and denomina-
tor of Equation D.1 produces
1+sT 2
z@ (D.3)
1-sT 2
Some algebra rearranges the equation to
2 Êz-1ˆ
z@ (D.4)
T Ëz+1¯
As an alternative to Table 3-2, Equation D.4 can be used to provide a transfer
function in zthat approximates any function of s.
241

| 242 (cid:2) | APPENDIXDDEVELOPMENT | OFTHE BILINEAR | TRANSFORMATION |     |     |
| ----------- | -------------------- | -------------- | -------------- | --- | --- |
Prewarping
Prewarping the bilinear transformation causes the phase and gain of the s-domain
and z-domain functions to be identical at the prewarping frequency. This is useful
where exact equivalence is desired at a particular frequency, such as when using a
notch filter.Prewarping modifies the approximation of Equation D.4 to:
|     |     |     | w   | Êz-1ˆ |     |
| --- | --- | --- | --- | ----- | --- |
sª 0 (D.5)
2)Ëz+1¯
tan(wT
0
where w is the prewarping frequency, the frequency at which exact equivalence is
0
desired.Recalling Euler’s formulas for sine and cosine:
|     |     |         | ejx+e-jx | ejx -e-jx |     |
| --- | --- | ------- | -------- | --------- | --- |
|     |     | cos(x)= |          | , sin(x)= |     |
(D.6)
|     |     |     | 2   | 2j  |     |
| --- | --- | --- | --- | --- | --- |
and recalling that tan(x)=sin(x)/cos(x), Equation D.5 can be rewritten as
|     |     |     | 2j  | ejw0T2+e-jw0T2 | Êz-1ˆ |
| --- | --- | --- | --- | -------------- | ----- |
s=w
|     |     | 0 ◊    |          | ◊   |       |
| --- | --- | ------ | -------- | --- | ----- |
|     |     | ejw0T2 | -e-jw0T2 | 2   | Ëz+1¯ |
ejw0T2+e-jw0T2
Êz-1ˆ
= jw ◊
|     |     | 0 ejw0T2        | -e-jw0T2 | Ëz+1¯     |     |
| --- | --- | --------------- | -------- | --------- | --- |
|     |     | Êejw0T2+e-jw0T2 |          | ˆÊesT -1ˆ |     |
jw (D.7)
= 0Ëejw0T2
-e-jjw0T2¯ËesT+1¯
Our interest here is in steady-state response so that s=jw:
|     |     |     | Êejw0T2+e-jw0T2 | ˆÊesT -1ˆ         |       |
| --- | --- | --- | --------------- | ----------------- | ----- |
|     |     | s=  | jw              |                   | (D.8) |
|     |     |     | 0Ëejw0T2        | -e-jw0T2¯ËesT +1¯ |       |
Now,if ejwT/2is divided out of both the numerator and the denominator (on the right
side),the result is
|     |     |     | Êejw0T2+e-jw0T2 | ˆÊejwT2 -e-jwT2 | ˆ   |
| --- | --- | --- | --------------- | --------------- | --- |
s= jw (D.9)
0Ëejw0T2
-e-jw0T2¯ËejwT2+e-jwT2¯
So when w=w ,most of the factors cancel out, leaving the exact value for s:
0
s=jw
which means that when the transfer function is evaluated at the prewarping frequency,
the approximation is exactly correct.

PHASE ADVANCING (cid:3) 243
Factoring Polynomials
Most methods of approximating functions of s with functions of z require that
the polynomials, at least the denominator, be factored. The bilinear transformation
does not have this requirement,though the factored form usually requires less algebra,
as this example shows. Compare this function factored (D.10) and unfactored
(D.11):
1
T(s)= (D.10)
(s+1)4
1
T(s)= (D.11)
s4+4s3+6s2+4s+1
The factored form can be converted to zalmost directly:
[T ¥(z+1)]4 [T (T+2)]4(z+1)4
= (D.12)
[T(z-1)+T(z+1)]4 [z+(T -2) (T+2)]4
However, the unfactored form would require a considerable amount of algebra to
convert.
Phase Advancing
The approximation, z+1(cid:2)2–wT/2, can be used to advance the phase of the z func-
tion when the sfunction has fewer zeros than poles.
To begin:
z+1=ejwT+1 (D.13)
Dividing ejwT/2out of the right side yields
z+1=ejwT 2(ejwT 2+ejwT 2) (D.14)
Recalling Euler’s formula, 2cos(x)=ejx+e-jx,produces
ÊwTˆ
z+1=2ejwT 2cos (D.15)
Ë 2 ¯
Finally,when wT/2 is small,cos(wT/2)(cid:2)1 so that

244 (cid:2) APPENDIXDDEVELOPMENT OFTHE BILINEAR TRANSFORMATION
ÊwTˆ
z+1ª2ejwT 2 =2– (D.16)
Ë 2 ¯
This approximation is accurate enough for most applications since it is usually not
important that the gain of the sand zfunctions match at high frequencies.

Appendix E
Solutions to Exercises
Chapter 2
2-1A. Compile, click run, and double-click on the block K to bring into view an
P
adjustment box.Click on bold >> button to raise value.K =2 induces ringing
P
and overshoot; K =5 causes instability. Conclusion: Higher control-loop
P
gains reduce stability margins.
2-1B. Double-click on Wave Gen block to bring the Wave Gen control panel into
view. Use combo box at left to change waveform type. Conclusion: Gentler
excitation makes marginal stability more difficult to recognize.
2-1C. Overshoot is gone with zero integral gain;overshoot increases with greater K.
I
Conclusion:Higher integral gain causes overshoot and instability.
2-2A. 176Hz.
2-2B. -11.4dB.
2-2C. Lower control-loop gains reduce command response at higher frequencies.
2-3A. 0.002 to 0.0002s.
2-3B. More stable,but only over a range.Below 0.0002s,little improvement can be
seen.This is because the phase lag of the power converter and feedback filter
are large enough to make insignificant the phase lag associated with sampling.
2-3C. The two are almost the same (notice all model parameters are identical).
Conclusion: A digital PI system with sufficiently fast sample time behaves
approximately like an analog PI system.
Chapter 3
3-1A. K (cid:2)0.5,K (cid:2)42.GM=13dB,PM=60°.
P I
3-1B. K (cid:2)0.85,K (cid:2)70.GM=12dB,PM=58°.
P I
3-1C. K (cid:2)1.0,K (cid:2)85.GM=12.5dB,PM=59°.
P I
245

246 (cid:2) APPENDIXESOLUTIONSTOEXERCISES
(cid:2)1.4,K (cid:2)120.GM=12.8dB,
3-1D. K PM=59.5°
P I
3-1E. No overshoot with K and 10% with K gives 12–13dB GM and 58°–60°PM.
P I
3-1F. Allow some overshoot with K and/or more than 10% with K.
P I
3-2A. 76,140,157,and 214Hz.
3-2B. If tuning criteria are held constant,more phase lag from filters will reduce the
|     | ultimate responsiveness of | a control system. |
| --- | -------------------------- | ----------------- |
3-3A. Procedure (determined by trial-and-error):Allow about 5% overshoot with K
P
and about 25% overshoot with K.
I
(cid:2)0.7,K (cid:2)70.GM=10.3dB,
|     | K   | PM=49°. |
| --- | --- | ------- |
P I
| 3-3B. | K (cid:2)1.0,K (cid:2)120.GM=10.3dB, | PM=49°. |
| ----- | ------------------------------------ | ------- |
P I
(cid:2)1.4,K (cid:2)140.GM=9.5dB,
| 3-3C. | K P I | PM=48°. |
| ----- | ----- | ------- |
(cid:2)2.0,K (cid:2)200.GM=9.5dB,
| 3-3D. | K   | PM=49° |
| ----- | --- | ------ |
P I
3-4A. 124,180,255,and 363Hz.
3-4B. The bandwidths in 3-4A are about 50% higher than those in 3-2A. More
aggressive tuning leads to higher frequency command response.
Chapter 4
| 4-1A. | K =0.6,K =10.0. |     |
| ----- | --------------- | --- |
P I
4-1B. Approximately 0.25s.
| 4-1C. | K =1.7,K =30.0.Settles in approximately 0.1s. |     |
| ----- | --------------------------------------------- | --- |
P I
4-1D. Luenberger observer removes phase lag.This allows higher control-law gains
which provide faster settling time.
| 4-2A. | K =0.05,K =17,K | =2000. |
| ----- | --------------- | ------ |
|       | DO PO           | IO     |
4-2B. 108Hz.
4-2C. No significant difference. Tuning values do not depend on observer band-
width,at least when the observer models are very accurate.
4-3A. Yes,nearly identical.
4-3B. No. Phase lag can cause instability in the loop, even when the amount lag is
so small it is difficult to see comparing signals by eye.
4-4A. 50.
4-4B. That the procedure finds the correct K if the estimated sensor dynamics are
Est
just reasonably close to representing the actual sensor.
Chapter 5
| 5-1A. | K =0.06,K =25,K | =1400. |
| ----- | --------------- | ------ |
|       | DO PO           | IO     |
| 5-1B. | K =0.04,K =14,K | =700.  |
|       | DO PO           | IO     |

CHAPTER6 (cid:3) 247
5-2A. 50.
5-2B. 50.
5-3A. Increased phase lead at and around 50Hz.
5-3B. Increased phase lag at and around 50Hz.
5-3C. When FGs is lower than nominal, this condition causes phase lag. This
can be verified by monitoring the step response shown in the Live Scope of
Experiment 5D when changing sensor bandwidth.
5-4A. 49°PM and 14dB GM.
| 5-4B. K | Gain C/O | PM Phase C/O | GM   |
| ------- | -------- | ------------ | ---- |
|         | (Hz)     | (deg) (Hz)   | (dB) |
| 20      | 6.4      | 42 89        | 30   |
| 50      | 12       | 49 46        | 14   |
| 100     | 24       | 36 43.5      | 5.8  |
| 5-4C. K | Gain C/O | PM Phase C/O | GM   |
|         | (Hz)     | (deg) (Hz)   | (dB) |
| 20      | 2.5      | 41 21        | 24   |
| 50      | 5        | 47 21        | 17   |
| 100     | 9        | 39 21        | 11   |
5-4D. Nominal margins of stability are approximately the same for both the tradi-
tional and the observer-based systems.The observer system is more sensitive
to increase in plant gain (K) as shown by the loss of 13°PM and 8dB of GM
for Khigh;compare this to the traditional system,whith a loss of only 6°PM
and 6dB GM.Increased loss of stability in the observer-based system is easily
seen in the step response for high K.
Chapter 6
6-1A. 154Hz.
6-1B. 144Hz.
6-1C. 103 (for observed disturbance) and 102Hz.
6-1D. 72 (for observed disturbance) and 71Hz.
6-1E. They are nearly the same when the estimated plant and sensor are accurate
representations of the actual plant and sensor.Under these conditions,Equa-
tions 6.4 and 4.6 are identical. Note: The small difference between 6-1A and
6-1B is caused by variation in the setup of the DSAs (via the “gear” buttons)
in Experiments 5A and 6A.
6-1F. The response of observed disturbance is different from the observer response;
Equation 6.4 is not a good approximation when the sensor and plant models
vary substantially from the actual sensor and plant.

248 (cid:2) APPENDIXESOLUTIONSTOEXERCISES
6-2A. 0.022.
6-2B. 0.05,0.02,0.01.
6-2C. It is inversely proportional.
6-3A. Should be similar to Figure 6-17 for the second two cases.
6-3B. 4.5,-8.3,and -25dB.
6-3C. 12.8dB or 4.4 times.
6-3D. 16.7dB or 6.8 times.
6-3E. 1.76,0.404,and 0.06.
6-3F. 1.76/0.404 or 4.35
6-3G. 0.404/0.06 or 6.3.
6-3H. Both measures produce essentially the same measurements.
6-4A. K =1.5,K =25 (50Hz);
P I
K =3.0,K =50 (100Hz);
P I
K =6.0,K =100 (200Hz).
P I
6-4B. 1.2 (50Hz),0.6 (100Hz),and 0.4 (200Hz).
6-4C. 0.5 (50Hz), 0.3 (100Hz),and 0.2 (200Hz).
6-4D. No. The majority of disturbance response comes from the decoupling path
and the control-law gains have little effect.
Chapter 7
7-1A. 144,80,52Hz.
7-1B. 14 (high),8 (medium),0dB (low).
7-1C. Yes. K .
DO
7-2A. About 0.2 divisions or 0.04.
7-2B. About 1 division or 0.2.
7-2C. About 2 divisions or 0.4.
7-2D. At 200Hz, part A (default parameters) -28dB; part B, -14dB; part C,
-8dB. Comparison: Part A is 14dB (5 times) lower than part B, which is
6dB (2 times) lower than part C. This is consistent with the time-domain
measurements.
7-3A. About 1.2.
7-3B. About 0.5.
7-3C. Yes,both in the Live Scope Cand in the Noise DSA.
7-3D. 8.5Hz.
7-3E. Both the noise response and the disturbance response of the systems of parts
A and D are equivalent.

CHAPTER8 (cid:3) 249
Chapter 8
8-1. First phase crossover disappears when K =0; without the additional 90°
IO
phase lag contributed by K ,there is no crossover at (or near) 200Hz.
IO
8-2A. V is highly inaccurate. The other two signals are accurate.
OMod
8-2B. V disturbance response will probably be poor because the velocity per-
OMod
turbations caused by the disturbance are so poorly represented by the signal.
8-2C. V O provides the best response. V S provides similar response except for strong
peaking at 400Hz caused by the too high control-law gains for the phase lag of
the sensed signal.V provides the poorest response as discussed in Part B.
OMod
8-3. The noise sensitivities V O and V S are similar. The noise sensitivity V OMod is
lower, due to the filtering effect of the modified Luenberger observer (see
Section 7.5). Compare to Exercise 8-2: The implicit filtering of the modified
observer  provides  advantages  (lower  noise  sensitivity)  and  disadvan-
tages (poorer disturbance response) equivalent to an observer with a lower
bandwidth.
8-4A. 48°in both cases.
| 8-4B. 24° for V       | and 28°for V | .    |
| --------------------- | ------------ | ---- |
|                       | O            | OMod |
| 8-4C. The one using V | .            |      |
OMod
8-4D. 51°in both cases.
| 8-4E. 40°for V        | and 36°for V         | .                      |
| --------------------- | -------------------- | ---------------------- |
|                       | O                    | OMod                   |
| 8-4F. The one using V | O .                  |                        |
| 8-5A. T               | Maximum K            |                        |
| SAMPLE                |                      | AFB                    |
| 0.00025               |                      | 1.2                    |
| 0.0002                |                      | 2.5                    |
| 0.00015               |                      | 6.0                    |
| 8-5B. K               | Disturbance response | Improvement offered by |
DD
|                           | at 10Hz      | acceleration feedback |
| ------------------------- | ------------ | --------------------- |
|                           | (dB)         | (dB)                  |
| 0                         | -15          | (reference)           |
| 1                         | -21          | 6 (2¥)                |
| 2.5                       | -26          | 10 (3.1¥)             |
| 6                         | -32          | 17 (7¥)               |
| 8-5C. Ideal result is 1+K | improvement. |                       |
AFB
| Case 1: | 1+1=2.     |     |
| ------- | ---------- | --- |
| Case 2: | 1+2.5=3.5. |     |
| Case 3: | 1+6=7.     |     |
The results in part B are similar to the ideal results.

Index
Note: Page numbers followed by f or t refer to the figure or table on that page,
respectively.
| A                                     |         |     | Block diagrams,44               |     |     |
| ------------------------------------- | ------- | --- | ------------------------------- | --- | --- |
| Acceleration                          |         |     | European symbols,233–235        |     |     |
| feed forward,175                      |         |     | Bode plot                       |     |     |
| observed,                             | 220     |     | bandwidth,                      | 51  |     |
| Acceleration feedback,207,229         |         |     | closed-loop,                    | 60f |     |
| and gain reduction,208                |         |     | disturbance,actual vs.observed, |     |     |
| Accelerometer,                        | 209,219 |     | 119f                            |     |     |
| Accumulation,                         | 55      |     | disturbance decoupling,132f     |     |     |
| Aliasing,142                          |         |     | and frequency domain,           |     | 33  |
| Analog control systems,54             |         |     | graphical phasor display,49     |     |     |
| Analog-to-digital converter (ADC),58, |         |     | measuring response,             |     | 51  |
| 142                                   |         |     | open-loop,69f                   |     |     |
Analysis vs.experimentation, 100,113 open-loop plot of PI controller,
65f
| B                                 |        |     | peaking,                  | 52f           |     |
| --------------------------------- | ------ | --- | ------------------------- | ------------- | --- |
| Bandwidth                         |        |     | position vs.              | velocity,194f |     |
| and closed-loop responsiveness,51 |        |     | saturation,               | 37            |     |
| definition,15                     |        |     | vs. scope,53f             |               |     |
| observer,                         | 103    |     | signal-to-noise,          | 37            |     |
| resolver-to-digital converter,    |        | 181 | and unstable systems,200  |               |     |
| velocity loop,176                 |        |     | Visual ModelQ analysis,35 |               |     |
| Bilinear transform,               | 56,237 |     | z-domain,                 | 57            |     |
| prewarping,                       | 57,238 |     | Brushless motors,175      |               |     |
251

252 (cid:2) INDEX
| C                                 |                     |            |     | Coupling,mechanical,                 |     |       | 224          |
| --------------------------------- | ------------------- | ---------- | --- | ------------------------------------ | --- | ----- | ------------ |
| Calculation noise,144             |                     |            |     | Crossover frequency,                 |     |       | 61           |
| Capacitance variation,100         |                     |            |     | Cyclic error,10,                     |     | 11    |              |
| Characterizing components,        |                     |            | 99  |                                      |     |       |              |
| Classical vs.state space,         |                     | 82         |     | D                                    |     |       |              |
| Closed loop,59                    |                     |            |     | Decoupling,129                       |     |       |              |
| Bode plot,60f                     |                     |            |     | Delay,43                             |     |       |              |
| Coasting,182                      |                     |            |     | Derivative gain (D-gain),            |     |       | 89           |
| Colored noise,142                 |                     |            |     | Design process                       |     |       |              |
| Coloring filter,142               |                     |            |     | for Luenberger observer,             |     |       | 82–86        |
| Command,6                         |                     |            |     | for observers,                       |     | 2     |              |
| Command filtering,7               |                     |            |     | Differences,                         | 55  |       |              |
| Command noise,143                 |                     |            |     | Differentiation,digital,             |     |       | 55           |
| Command response,15,              |                     | 50–51,176, |     | Digital control,7                    |     |       |              |
| 185                               |                     |            |     | Digital control system               |     |       |              |
| Commutation,175                   |                     |            |     | data processing,                     |     | 54    |              |
| Compensators,digital,55           |                     |            |     | modeling with VisualQ,               |     |       | 37–38        |
| Compliance,mechanical,            |                     | 223        |     | and phase lag,38                     |     |       |              |
| Compliant load,transfer function, |                     |            | 224 | Digital filters,                     |     | 84    |              |
| Computational resources,183       |                     |            |     | Digital signal processor,            |     |       | 75           |
| Continuous systems,               |                     | 54         |     | Digital-to-analog converter (DAC),58 |     |       |              |
| Control law,6                     |                     |            |     | Disturbance                          |     |       |              |
| Control law gains and noise,156   |                     |            |     | and control laws,                    |     | 6     |              |
| Control loop,6f                   |                     |            |     | in Luenberger observer,115–116       |     |       |              |
| Control systems                   |                     |            |     | measuring,12–13                      |     |       |              |
| command response,15               |                     |            |     | and model error detection,           |     |       | 113          |
| cost,13                           |                     |            |     | observed,203                         |     |       |              |
| disturbance rejection,15–16       |                     |            |     | observer,116–117                     |     |       |              |
| ease of use,17                    |                     |            |     | and observer compensator design,89   |     |       |              |
| frequency domain analysis,33–37   |                     |            |     | and observers,                       |     | 77–78 |              |
| goals,13–17                       |                     |            |     | observing,13,129                     |     |       |              |
| modeling with VisualQ,26–32       |                     |            |     | rejection,12,                        |     | 15    |              |
| noise response,16                 |                     |            |     | response and power-converter         |     |       |              |
| observer-based vs.traditional,    |                     |            | 2   | bandwidth,                           |     | 162   |              |
| reliability,14                    |                     |            |     | sensing,                             | 129 |       |              |
| robustness,16–17                  |                     |            |     | types,11–12                          |     |       |              |
| stability,14–15                   |                     |            |     | Disturbance decoupling,12,           |     |       | 129, 221     |
| structures,5–13                   |                     |            |     | and integral gain,132                |     |       |              |
| traditional.see                   | Traditional control |            |     | motion systems,203                   |     |       |              |
| system                            |                     |            |     | and noise,156                        |     |       |              |
| Cost                              |                     |            |     | and observer bandwidth,136           |     |       |              |
| of control systems,13             |                     |            |     | Disturbance response,3,              |     |       | 123–124,185, |
| reduction,3                       |                     |            |     | 192                                  |     |       |              |
| Coulomb friction,98               |                     |            |     | and gains,127                        |     |       |              |

INDEX (cid:3) 253
| improving,124,129              |     |     |     | improved measurement of           |     |     | plant gain, |
| ------------------------------ | --- | --- | --- | --------------------------------- | --- | --- | ----------- |
| and integral gain,136          |     |     |     | 104f                              |     |     |             |
| and low observer bandwidth,127 |     |     |     | measuring performance,            |     |     | 49,50f      |
| in observer-based systems,125  |     |     |     | measuring plant gain,             |     |     | 86–88       |
| and observers,202              |     |     |     | modified observer compensator,168 |     |     |             |
and power converter bandwidth,138 noise and disturbance decoupling,
| transfer functions,124–125 |     |     |     | 159–160                      |     |     |     |
| -------------------------- | --- | --- | --- | ---------------------------- | --- | --- | --- |
| Disturbance torque,186     |     |     |     | observed disturbance,118–120 |     |     |     |
| Drift,70                   |     |     |     | observer-based control,      |     |     | 75  |
Dynamic signal analyzer (DSA),34–37 observer-based disturbance
|                     |     |     |     | decoupling,                   | 131 |     |       |
| ------------------- | --- | --- | --- | ----------------------------- | --- | --- | ----- |
| E                   |     |     |     | observer-based reduction of   |     |     | phase |
| Ease of use,17      |     |     |     | lag,76–77                     |     |     |       |
| Electrical plants,9 |     |     |     | observer for encoder systems, |     |     | 193   |
Electromagnetic interference. seeEMI observer for resolver systems, 202
| Electromagnetic torque,186 |         |     |     | phase lag and simple differences, |     |     |     |
| -------------------------- | ------- | --- | --- | --------------------------------- | --- | --- | --- |
| Electronic flywheel,207    |         |     |     | 188                               |     |     |     |
| Electronic inertia,207     |         |     |     | phase lag from resolver systems,  |     |     |     |
| EMI,70,144,184             |         |     |     | 198                               |     |     |     |
| Encoder,                   | 178,184 |     |     | power converter and disturbance   |     |     |     |
| Encoder resolution,        |         | 188 |     | response,137                      |     |     |     |
Encoder system observer,193 sensor noise and actual state,152–
| Errata, 4                         |     |                   |     | 155                                 |     |       |         |
| --------------------------------- | --- | ----------------- | --- | ----------------------------------- | --- | ----- | ------- |
| Error                             |     |                   |     | sensor noise and observed state,    |     |       |         |
| cyclical,11                       |     |                   |     | 150–152                             |     |       |         |
| feedback signal,10                |     |                   |     | simple control system,26–32         |     |       |         |
| plant gain,101                    |     |                   |     | tuning an observer,                 |     | 91f,  | 103f    |
| sensor model,                     |     | 102,110           |     | tuning observer with DSA,           |     |       | 94f     |
| Error signal,                     | 6   |                   |     | variation and observer performance, |     |       |         |
| Estimated parameters,68           |     |                   |     | 105–107                             |     |       |         |
| Excitation,6                      |     |                   |     | variation and system stability,     |     |       | 108–    |
| Experimentation vs.               |     | analysis, 100,113 |     | 109                                 |     |       |         |
| Experiments,                      | 4   |                   |     |                                     |     |       |         |
| acceleration feedback in motion   |     |                   |     | F                                   |     |       |         |
| systems,210                       |     |                   |     | Fast Fourier transform (FFT),       |     |       | 37, 194 |
| control system with DSA,34–37     |     |                   |     | Feed-forward,                       | 175 |       |         |
| digital control system,37–38      |     |                   |     | Feedback filtering                  |     |       |         |
| disturbance decoupling in motion  |     |                   |     | intrinsic,                          | 10  |       |         |
| systems,205                       |     |                   |     | and stability,11                    |     |       |         |
| disturbance response and gain,128 |     |                   |     | Feedback sensors,                   |     | 10–11 |         |
filtering observed disturbance,163 Filter-form observer, 78–82,101,118,
| I-gain in observer compensator, |     |     | 122– | 146                       |     |     |     |
| ------------------------------- | --- | --- | ---- | ------------------------- | --- | --- | --- |
| 123                             |     |     |      | disadvantages,            | 82  |     |     |
| idealized feedback,74           |     |     |      | Filtering, and stability, |     | 11  |     |

254 (cid:2) INDEX
| Filtering derivative signals,      | 6   | Inaccuracy                 |               |     |         |          |
| ---------------------------------- | --- | -------------------------- | ------------- | --- | ------- | -------- |
| Filtering effects,86               |     | effects,                   | 100–102       |     |         |          |
| Filtering noise,16                 |     | sources,98                 |               |     |         |          |
| Filtering observed disturbance,169 |     | vs. variation,             |               | 102 |         |          |
| Filters                            |     | Inductance variation,      |               |     | 85      |          |
| biquadratic,229                    |     | Inertia mismatch,226       |               |     |         |          |
| command,7                          |     | Inertia,                   | variation,204 |     |         |          |
| digital,55                         |     | Instability,               | in observers, |     | 90      |          |
| notch,7                            |     | Integral gain (I-gain),89, |               |     | 122–123 |          |
| phase-advancing,7                  |     | zeroing,                   | 63            |     |         |          |
| transfer functions,43              |     | Integrating plants,8,      |               |     | 10,135, | 153, 166 |
| types,7                            |     | Integration,digital,       |               |     | 55      |          |
z-domain,55
| Flow and force,10               |     | L                    |     |     |     |     |
| ------------------------------- | --- | -------------------- | --- | --- | --- | --- |
| Fluid dynamics,9t               |     | Laplace operator,    |     | 42  |     |     |
| Fluid mechanics,9t              |     | Laplace transform,42 |     |     |     |     |
| Following error,175             |     | Lead compensator,43  |     |     |     |     |
| Force,and flow,10               |     | Lead networks,       |     | 7   |     |     |
| Frequency,and responsiveness,51 |     | Limit cycles,        | 58  |     |     |     |
Frequency domain,42.see also s- Linear,time invariant (LTI) systems,43
| domain;z-domain                 |     | Linearity,42            |     |     |     |     |
| ------------------------------- | --- | ----------------------- | --- | --- | --- | --- |
| Frequency domain analysis,33–37 |     | Load disturbance,       |     | 115 |     |     |
| Friction,98                     |     | Luenberger observer,72f |     |     |     |     |
construction,68–72
| G                                |     | definition,67–68     |     |     |      |     |
| -------------------------------- | --- | -------------------- | --- | --- | ---- | --- |
| G/(1 +GH) rule,44,57             |     | design process,82–90 |     |     |      |     |
| Gain,47–48                       |     | with disturbances,   |     |     | 116f |     |
| determining experimentally,86–88 |     | filter form,78–81    |     |     |      |     |
| and noise,156                    |     | modified,            | 189 |     |      |     |
reduction with acceleration feedback, in motion systems, 173–174, 184–185
| 208–209                     |     | noise,                            | 141–142 |     |        |     |
| --------------------------- | --- | --------------------------------- | ------- | --- | ------ | --- |
| Gain crossover frequency,61 |     | predictor-corrector form,         |         |     | 77–78  |     |
| Gain margin,59,62           |     | and sensor noise,145              |         |     |        |     |
| calculation,61f             |     | using disturbance decoupling,221f |         |     |        |     |
| Gear box,224                |     | Lumped-parameter models,          |         |     | 99,224 |     |
Ground loops,144
M
| H              |     | Marginal stability,           |                 | 15, | 52  |       |
| -------------- | --- | ----------------------------- | --------------- | --- | --- | ----- |
| Heat flow,9t   |     | Margins of                    | stability,16,62 |     |     |       |
| Homogeneity,42 |     | analysis by open-loop method, |                 |     |     | 59–62 |
Mason’s signal flow graphs
| I                            |     | Luenberger observer,117f |     |     |     |     |
| ---------------------------- | --- | ------------------------ | --- | --- | --- | --- |
| Idealized control system,74f |     | s-domain,45–47           |     |     |     |     |
| Implementing observers,      | 2   | z-domain,                | 57  |     |     |     |

INDEX (cid:3) 255
| Measures of                  | performance,62 |     | sensor, 11,144             |     |     |     |     |
| ---------------------------- | -------------- | --- | -------------------------- | --- | --- | --- | --- |
| Measuring performance,49,50f |                |     | and sensor attenuation,150 |     |     |     |     |
Measuring sensor parameters,84 in traditional and observer systems,
| Mechanical compliance,     |     | 223 | 148–150                           |     |     |     |     |
| -------------------------- | --- | --- | --------------------------------- | --- | --- | --- | --- |
| Mechanical resonance,223   |     |     | white vs.colored,142              |     |     |     |     |
| Mechanics,9t               |     |     | Noise analysis,144                |     |     |     |     |
| Microprocessor,            | 75  |     | Noise entry,143                   |     |     |     |     |
| Model inaccuracy           |     |     | Noise sensitivity,145             |     |     |     |     |
| effects,100–102            |     |     | Noise susceptibility and observer |     |     |     |     |
| sources,98                 |     |     | bandwidth,                        | 146 |     |     |     |
| ModelQ,4                   |     |     | Non-linear effects,               |     | 98  |     |     |
| simulation environment,17  |     |     | Notch filters,7                   |     |     |     |     |
| Models,lumped-parameter,99 |     |     | Nyquist frequency,142             |     |     |     |     |
Modified Luenberger observer,189
| Modified observed state,165 |     |     | O   |     |     |     |     |
| --------------------------- | --- | --- | --- | --- | --- | --- | --- |
Modified observer compensator,164– Observed acceleration,209, 220, 229
| 166                          |     |     | Observed disturbance,     |     | 82, | 116–117, | 203, |
| ---------------------------- | --- | --- | ------------------------- | --- | --- | -------- | ---- |
| experimental evaluation,168  |     |     | 221                       |     |     |          |      |
| gradual implementation,170   |     |     | DC error,120              |     |     |          |      |
| and observed disturbance,169 |     |     | filtering, 169            |     |     |          |      |
| Motion-control systems       |     |     | and integral gain,122–123 |     |     |          |      |
| applications,173–174         |     |     | and model inaccuracy,120  |     |     |          |      |
disturbance decoupling,203–204 and modified observer compensator,
| Motion sensors,177 |     |     | 169 |     |     |     |     |
| ------------------ | --- | --- | --- | --- | --- | --- | --- |
noise analysis,157
| N                                  |                   |         | transfer function,117             |         |            |     |     |
| ---------------------------------- | ----------------- | ------- | --------------------------------- | ------- | ---------- | --- | --- |
| Noise                              |                   |         | Observed RD conversion,           |         |            | 218 |     |
| and the actual state,              |                   | 152–153 | Observed signals,68               |         |            |     |     |
| analysis of                        | observers,146     |         | Observed state                    |         |            |     |     |
| calculation,144                    |                   |         | modified,                         | 165     |            |     |     |
| command,143                        |                   |         | and noise,150–152                 |         |            |     |     |
| and control law gains,156          |                   |         | Observed torque disturbance,      |         |            | 221 |     |
| and derivative control,6           |                   |         | Observer bandwidth,               |         | and noise, |     | 161 |
| from feedback sensors,10           |                   |         | Observer compensator              |         |            |     |     |
| and observed disturbance,157       |                   |         | D-gain,89                         |         |            |     |     |
| and the observed state,151         |                   |         | design,88–90                      |         |            |     |     |
| observer,                          | 89,95             |         | I-gain,89                         |         |            |     |     |
| and observer bandwidth,161         |                   |         | modified,                         | 164–166 |            |     |     |
| and observer model,156             |                   |         | need for I-gain,219               |         |            |     |     |
| and the power converter,153,160    |                   |         | saturation,                       | 89      |            |     |     |
| reduction with filters,            |                   | 7       | second D-gain,198                 |         |            |     |     |
| in resolver-to-digital conversion, |                   |         | tuning,90–95                      |         |            |     |     |
| 181                                |                   |         | Observer computational resources, |         |            |     |     |
| response of                        | control system,16 |         | 75                                |         |            |     |     |

256 (cid:2) INDEX
| Observer tuning,103–104,192–195 |     |     | P                           |     |     |     |
| ------------------------------- | --- | --- | --------------------------- | --- | --- | --- |
| analytically,93                 |     |     | Parameter variation,104–105 |     |     |     |
| configuration,91                |     |     | Peaking,36,52               |     |     |     |
| in R-D-based system,201–202     |     |     | in observer,                | 94  |     |     |
and resolver-to-digital converter, 201 Performance enhancement, 3, 183
Observers.see alsoLuenberger observer Performance measures, 62
| advantages,13     |     |     | experiment 3A, |     | 49, 50f |     |
| ----------------- | --- | --- | -------------- | --- | ------- | --- |
| bandwidth,103,116 |     |     | Phase, 47–48   |     |         |     |
bandwidth and noise susceptibility, Phase-crossover frequency,62
| 146                                    |     |     | multiple,196                  |             |     |     |
| -------------------------------------- | --- | --- | ----------------------------- | ----------- | --- | --- |
| bandwidth,low,127                      |     |     | Phase lag,                    | 124,156     |     |     |
| closed-loop response,93                |     |     | and control loop stability,11 |             |     |     |
| computationally efficient filter form, |     |     | and digital systems,38        |             |     |     |
| 81                                     |     |     | elimination,                  | 62,75,76–77 |     |     |
| and control system reliability,        |     | 14  | experiments,                  | 72–75       |     |     |
| design process,82–86                   |     |     | in motion control sensors,184 |             |     |     |
| and digital control,7–8                |     |     | in motion control systems,    |             |     | 184 |
| and disturbance response,202           |     |     | and performance,74            |             |     |     |
| feed-forward path,92                   |     |     | RD conversion,                |             | 217 |     |
| filter-form,78–82,101,118,146          |     |     | reduction with observers,15,  |             |     |     |
| including RD conversion,197            |     |     | 185–187                       |             |     |     |
| instability,90                         |     |     | from resolvers,197            |             |     |     |
| low gains for scaling measurement,     |     | 88  | and sensor noise,16           |             |     |     |
| noise sensitivity,145–150              |     |     | from sensors,                 | 69          |     |     |
| noise susceptibility,90,               | 95  |     | from sine encoders,           |             | 197 |     |
| overview,2–3                           |     |     | and stability,127             |             |     |     |
| peaking,94                             |     |     | z-domain,                     | 57          |     |     |
| predictor-corrector form,77–78         |     |     | and zone tuning,64            |             |     |     |
| role in control system,                | 3f  |     | Phase margin,59,              |             | 62  |     |
| sample-hold,123                        |     |     | calculation,                  | 61f         |     |     |
| sample time,103                        |     |     | Phasors                       |             |     |     |
| saturation,194                         |     |     | s-domain,48                   |             |     |     |
| shortcomings,2,3                       |     |     | z-domain,                     | 56–57       |     |     |
| stability,89                           |     |     | PID control,6,6f,43           |             |     |     |
state-space and classical form,82 observer compensator, 88–90
| Offset,83                         |     |     | specifying gain margin and phase |              |     |     |
| --------------------------------- | --- | --- | -------------------------------- | ------------ | --- | --- |
| Open loop,174                     |     |     | margin,                          | 62           |     |     |
| multiple phase crossover,         |     | 196 | tuning,65                        |              |     |     |
| Open-loop method,59–62            |     |     | PID position loop,177            |              |     |     |
| Bode plot,60f                     |     |     | Plant,6,8–10                     |              |     |     |
| Operation-dependent variation,100 |     |     | gain errors,                     | 101          |     |     |
| Optical encoder,178               |     |     | integrating,10                   |              |     |     |
| Overshoot,52,62,65                |     |     | order of                         | integration, | 86  |     |
| Overshoot and settling,50         |     |     | transfer functions,9t            |              |     |     |

INDEX (cid:3) 257
Plant dynamic parameter,86 Resolver-to-digital converter (RDC),
| Plant estimator,84                  |         |        |     |     | 179                       |     |     |     |
| ----------------------------------- | ------- | ------ | --- | --- | ------------------------- | --- | --- | --- |
| Plant scaling,85                    |         |        |     |     | bandwidth vs.system,200   |     |     |     |
| experimental determination,86–      |         |        |     |     | signal processing,        |     | 215 |     |
| 88                                  |         |        |     |     | transfer function,180,198 |     |     |     |
| Plant variation,                    |         | 85,102 |     |     | Resolvers,184,214         |     |     |     |
| Position loop,174                   |         |        |     |     | frameless,                | 214 |     |     |
| Position sensor,178                 |         |        |     |     | Resonance,7,              | 223 |     |     |
| high resolution,184                 |         |        |     |     | high-frequency,226        |     |     |     |
| phase lag,                          | 184     |        |     |     | low-frequency,225         |     |     |     |
| Power, 6                            |         |        |     |     | Response,6,50–51          |     |     |     |
| Power conversion,8                  |         |        |     |     | and control-law gains,50  |     |     |     |
| Power converter,6,                  |         | 64     |     |     | Ringing,36,52             |     |     |     |
| bandwidth and disturbance response, |         |        |     |     | Robustness,16–17          |     |     |     |
| 162                                 |         |        |     |     | Root locus method,        |     | 59  |     |
| and noise,                          | 153,160 |        |     |     | Rotational mechanics,     |     |     | 9t  |
Predictor-corrector,67,77–78
| structure,116                           |                |     |     |       | S                               |                       |       |       |
| --------------------------------------- | -------------- | --- | --- | ----- | ------------------------------- | --------------------- | ----- | ----- |
| Prewarping,                             | 238            |     |     |       | s-domain,42                     |                       |       |       |
| Profile generator,175                   |                |     |     |       | block diagrams,44–47            |                       |       |       |
| Proportional-integral-differential (PI) |                |     |     |       | Bode plots,49                   |                       |       |       |
| control.                                | seePID control |     |     |       | linearity and frequency domain, |                       |       |       |
| Proportional-integral (PI) control,     |                |     |     | 6,8f, | 42–43                           |                       |       |       |
| 43                                      |                |     |     |       | measuring performance,          |                       |       | 49–54 |
| digital,55                              |                |     |     |       | phase and gain,                 |                       | 47–48 |       |
| specifying gain margin and phase        |                |     |     |       | transfer function,43–44         |                       |       |       |
| margin,                                 | 62             |     |     |       | transfer functions,43–44        |                       |       |       |
| tuning,32,                              | 64             |     |     |       | s,Laplace operator,             |                       | 42    |       |
| Proportional (P) control,               |                |     | 6   |       | Sample-and-hold (S/H),          |                       |       | 57–58 |
|                                         |                |     |     |       | Sample-data systems,            |                       | 54    |       |
| Q                                       |                |     |     |       | Sample time,38                  |                       |       |       |
| Quadrature encoder,188                  |                |     |     |       | Sampling,                       | in digital systems,54 |       |       |
| Quantization,58,70                      |                |     |     |       | Saturation,37,42,               |                       | 85    |       |
| and analog sensors,                     |                |     | 142 |       | observer,194                    |                       |       |       |
| Quantization noise,                     |                | 142 |     |       | observer compensator,           |                       |       | 89    |
| Qxdesign,                               | 4,18           |     |     |       | Scope,vs.                       | Bode plot,53f         |       |       |
|                                         |                |     |     |       | Sensor model errors,            |                       | 110   |       |
| R                                       |                |     |     |       | Sensor error,                   | detecting,112–113     |       |       |
| Random excitation,37                    |                |     |     |       | Sensor estimator,83             |                       |       |       |
| Random noise,142                        |                |     |     |       | Sensor filtering,               |                       | 83    |       |
| Reliability,                            | 14             |     |     |       | Sensor gain error,99            |                       |       |       |
| Resolution,16,                          |                | 58  |     |       | Sensor model                    |                       |       |       |
| Resolver,178–179                        |                |     |     |       | errors,102                      |                       |       |       |
| phase lag,197                           |                |     |     |       | variation,102                   |                       |       |       |

258 (cid:2) INDEX
| Sensor noise,10,11,            | 144 |     | Stribeck effect, | 98  |     |     |     |
| ------------------------------ | --- | --- | ---------------- | --- | --- | --- | --- |
| analysis,144                   |     |     | Superposition,   | 43  |     |     |     |
| and disturbance observation,13 |     |     | Sync function,   | 58  |     |     |     |
effect on actual state,152–155
| Sensor offset,83             |     |     | T                              |     |     |          |     |
| ---------------------------- | --- | --- | ------------------------------ | --- | --- | -------- | --- |
| Sensor offset error,99       |     |     | Tachometer,177–178             |     |     |          |     |
| Sensor problems,1,69         |     |     | Temperature variation,         |     |     | 100      |     |
| Sensor scaling,83            |     |     | Tension control,182            |     |     |          |     |
| Sensors                      |     |     | Thermal disturbance,           |     | 115 |          |     |
| alternative options,14       |     |     | Time invariance,43             |     |     |          |     |
| bandwidth variation,107      |     |     | Torque, 186                    |     |     |          |     |
| dynamic characteristics,83   |     |     | Torque disturbance,115,221     |     |     |          |     |
| ideal,69                     |     |     | Torque transducer,182          |     |     |          |     |
| measuring parameters,84      |     |     | Tracking converter,179         |     |     |          |     |
| motion,177                   |     |     | Traditional control system,    |     |     | 68, 69f, | 73f |
| types,10                     |     |     | Trajectory generator,          |     | 175 |          |     |
| Servo systems,174            |     |     | Transfer function              |     |     |          |     |
| Settling time,50             |     |     | analysis and modified observer |     |     |          |     |
| Signals,sensed and observed, |     | 2   | compensator,167                |     |     |          |     |
Simple difference process, 15,182,185 of controller elements, 43t
| Sine encoder,181–182,184                |       |          | DC response,                           | 42                    |                 |           |     |
| --------------------------------------- | ----- | -------- | -------------------------------------- | --------------------- | --------------- | --------- | --- |
| phase lag,197                           |       |          | of disturbance response,124–125        |                       |                 |           |     |
| Sliding friction,98                     |       |          | position vs.                           | velocity,195          |                 |           |     |
| Software experiments,                   | 4,17. | see also | s-domain,42,                           | 43–44                 |                 |           |     |
| experiments                             |       |          | z-domain,                              | 54–55                 |                 |           |     |
| default model,18–26                     |       |          | Transfer functions of                  |                       | plant elements, |           | 9t  |
| Software,resolver-to-digital converter, |       |          | Transform pair,42                      |                       |                 |           |     |
| 181                                     |       |          | Translational mechanics,               |                       |                 | 9t        |     |
| Stability,52–54,69                      |       |          | Transmission components,               |                       |                 | 224       |     |
| analysis by open-loop method,           |       | 59–      | Tuning,32                              |                       |                 |           |     |
| 62                                      |       |          | observer,103–104,                      |                       | 192             |           |     |
| enhancing with observer,72–77           |       |          | observer compensator,                  |                       |                 | 90–95     |     |
| and filtering,11                        |       |          | observers,                             | varying sensor model, |                 |           |     |
| of observers,89,92                      |       |          | 110                                    |                       |                 |           |     |
| and variation,108                       |       |          | observers with RD converter,           |                       |                 | 201       |     |
| Stability margins,16                    |       |          | proportional-integral-differential     |                       |                 |           |     |
| State-space,82                          |       |          | (PID) controller,                      |                       | 65              |           |     |
| Step response,50                        |       |          | proportional-integral (PI) controller, |                       |                 |           |     |
| of sluggish and responsive systems,     |       |          | 64                                     |                       |                 |           |     |
| 53f                                     |       |          | zone-based method,                     |                       |                 | 62–65, 92 |     |
Stepper motors,174
| Stiction,98   |     |     | U                             |     |     |     |     |
| ------------- | --- | --- | ----------------------------- | --- | --- | --- | --- |
| Stiffness,124 |     |     | Unit-to-unit variation,99–100 |     |     |     |     |

INDEX (cid:3) 259
| V                             |         |     | live scope,                          | 20,25–26, 32 |     |
| ----------------------------- | ------- | --- | ------------------------------------ | ------------ | --- |
| Variable frequency AC (VFAC), |         | 174 | multipliers,22,                      | 29           |     |
| Variation,100                 |         |     | phase lag experiments,               | 72–77        |     |
| vs. inaccuracy,102            |         |     | scale-by live constants,             | 30           |     |
| sensor bandwidth,107          |         |     | scope,19, 24–25                      |              |     |
| and system stability,108      |         |     | simple constants,31–32               |              |     |
| Velocity                      |         |     | simulation environment,              | 17           |     |
| feed forward,                 | 175     |     | solver,19,20                         |              |     |
| sensing,182                   |         |     | string constants,30                  |              |     |
| Velocity control system,226   |         |     | variables, 34                        |              |     |
| Velocity loop,                | 174,176 |     | waveform generation,37               |              |     |
| Viscous damping,86,           | 98      |     | waveform generator,                  | 19, 21–22    |     |
| Visual ModelQ,4               |         |     | Voltage-controlled oscillator (VCO), |              | 180 |
| analog switch,                | 30      |     |                                      |              |     |
| Bode plot,                    | 35      |     | W                                    |              |     |
| constants,27–28               |         |     | Web-handling,182                     |              |     |
| default model,18–26           |         |     | Web site, qxdesign,                  | 4            |     |
| digital models,37             |         |     | White noise,142                      |              |     |
| digital values,21             |         |     | Wind-up, 89                          |              |     |
| documentation nodes,20        |         |     | Wiring, 16                           |              |     |
DSA,34–37
| DSA autofind,37           |     |     | Z                        |       |     |
| ------------------------- | --- | --- | ------------------------ | ----- | --- |
| DSA controls,36–37        |     |     | z-domain                 |       |     |
| DSA excitation,37         |     |     | bilinear transform,      | 56    |     |
| fly-over help,20          |     |     | Bode plot,57             |       |     |
| hot connection,32         |     |     | definition,54            |       |     |
| inspector,                | 30  |     | phasors,56–57            |       |     |
| installation,             | 18  |     | sample-and-hold (S/H),   | 57–58 |     |
| inverse live constants,29 |     |     | transfer functions,54–55 |       |     |
| live constants,           | 28  |     | Zone-based tuning,       | 62–65 |     |