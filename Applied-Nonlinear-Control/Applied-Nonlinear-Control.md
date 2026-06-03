| Slotine • Li  | APPLIED  | NONLINEAR  | CONTROL |
| ------------- | -------- | ---------- | ------- |
!  i

APPLIED
NONLINEAR
CONTROL
Jean-Jacques E Slotine
Weiping Li

Applied
Nonlinear
Control
JEAN-JACQUES E. SLOTINE
Massachusetts Institute of Technology
WEIPING LI
Massachusetts Institute of Technology'
Prentice Hall
Englewood Cliffs, New Jersey 07632

Library of Congress Cataloging-in-Publication Data
Slotine, J.-J. E. (Jean-Jacques E.)
Applied nonlinear control / Jean-Jacques E. Slotine, Weiping Li
p. cm.
Includes bibliographical references.
ISBN 0-13-040890-5
1, Nonlinear control theory. I. Li, Weiping. II. Title.
QA402.35.S56 1991 90-33365
629.8'312-dc20 C1P
Editorial/production supervision and
interior design: JENNIFER WENZEL
Cover design: KAREN STEPHENS
Manufacturing Buyer: LORI BULWIN
= ^= © 1991 by Prentice-Hall, Inc.
^=&= A Division of Simon & Schuster
T k Englewood Cliffs, New Jersey 07632
All rights reserved. No part of this book may be
reproduced, in any form or by any means,
without permission in writing from the publisher.
Printed in the United States of America
20 19 18 17 16 15 14 13 12 1]
ISBN D-13-DHDfiTa-S
Prentice-Hall International (UK) Limited, London
Prentice-Hall of Australia Pty. Limited, Sydney
Prentice-Hall Canada Inc., Toronto
Prentice-Hail Hispanoamericana, S.A., Mexico
Prentice-Hall of India Private Limited, New Delhi
Prentice-Hall of Japan, Inc., Tokyo
Simon & Schuster Asia Pte. Ltd., Singapore
Editora Prentice-Hall do Brasil, Ltda., Rio de Janeiro

To Our Parents

Contents
Preface xi
1. Introduction 1
1.1 Why Nonlinear Control ? 1
1.2 Nonlinear System Behavior 4
1.3 An Overview of the Book 12
1.4 Notes and References 13
Part I: Nonlinear Systems Analysis 14
Introduction to Part I 14
2. Phase Plane Analysis 17
2.1 Concepts of Phase Plane Analysis 18
2.1.1 Phase Portraits 18
2.1.2 Singular Points 20
2.1.3 Symmetry in Phase Plane Portraits 22
2.2 Constructing Phase Portraits 23
2.3 Determining Time from Phase Portraits 29
2.4 Phase Plane Analysis of Linear Systems 30
2.5 Phase Plane Analysis of Nonlinear Systems 32
2.6 Existence of Limit Cycles 36
2.7 Summary 38
2.8 Notes and References 38
2.9 Exercises 38

VI11
3. Fundamentals of Lyapunov Theory 40
3.1 Nonlinear Systems and Equilibrium Points 41
3.2 Concepts of Stability 47
3.3 Linearization and Local Stability 53
3.4 Lyapunov's Direct Method 57
3.4.1 Positive Definite Functions and Lyapunov Functions 58
3.4.2 Equilibrium Point Theorems 61
3.4.3 Invariant Set Theorems 68
3.5 System Analysis Based on Lyapunov's Direct Method 76
3.5.1 Lyapunov Analysis of Linear Time-Invariant Systems 77
3.5.2 Krasovskii's Method 83
3.5.3 The Variable Gradient Method 86
3.5.4 Physically Motivated Lyapunov Functions 88
3.5.5 Performance Analysis 91
3.6 Control Design Based on Lyapunov's Direct Method 94
3.7 Summary 95
3.8 Notes and References 96
3.9 Exercises 97
4. Advanced Stability Theory 100
4.1 Concepts of Stability for Non-Autonomous Systems 101
4.2 Lyapunov Analysis of Non-Autonomous Systems 105
4.2.1 Lyapunov's Direct Method for Non-Autonomous Systems 105
4.2.2 Lyapunov Analysis of Linear Time-Varying Systems 114
4.2.3 The Linearization Method for Non-Autonomous Systems 116
4.3 * Instability Theorems 117
4.4 * Existence of Lyapunov Functions 120
4.5 Lyapunov-Like Analysis Using Barbalat's Lemma 122
4.5.1 Asymptotic Properties of Functions and Their Derivatives 122
4.5.2 Barbalat's Lemma 123
4.6 Positive Linear Systems 126
4.6.1 PR and SPR Transfer Functions 126
4.6.2 The Kalman-Yakubovich Lemma 130
4.6.3 Positive Real Transfer Matrices 131
4.7 The Passivity Formalism 132
4.7.1 Block Combinations 132
4.7.2 Passivity in Linear Systems 137

IX
4.8  * Absolute Stability  142
4.9  * Establishing Boundedness of Signals  147
4.10  * Existence and Unicity of Solutions  151
4.11  Summary  153
4.12  Notes and References  153
4.13  Exercises  154
5.  Describing Function Analysis  157
5.1  Describing Function Fundamentals  158
| 5.1.1  | An Example of Describing Function Analysis  | 158 |
| ------ | ------------------------------------------- | --- |
| 5.1.2  | Applications Domain                         | 162 |
| 5.1.3  | Basic Assumptions                           | 164 |
| 5.1.4  | Basic Definitions                           | 165 |
| 5.1.5  | Computing Describing Functions              | 167 |
5.2  Common Nonlinearities In Control Systems  169
5.3  Describing Functions of Common Nonlinearities  172
5.4  Describing Function Analysis of Nonlinear Systems  179
| 5.4.1  | The Nyquist Criterion and Its Extension      | 180 |
| ------ | -------------------------------------------- | --- |
| 5.4.2  | Existence of Limit Cycles                    | 182 |
| 5.4.3  | Stability of Limit Cycles                    | 184 |
| 5.4.4  | Reliability of Describing Function Analysis  | 186 |
5.5  Summary  187
5.6  Notes and References  188
5.7  Exercises  188
Part II: Nonlinear Control Systems Design  191
| Introduction  | to Part II  | 191 |
| ------------- | ----------- | --- |
6.  Feedback Linearization  207
6.1  Intuitive Concepts  208
6.1.1 Feedback Linearization And The Canonical Form  208
| 6.1.2  | Input-State Linearization   | 213 |
| ------ | --------------------------- | --- |
| 6.1.3  | Input-Output Linearization  | 216 |
6.2  Mathematical Tools  229
6.3  Input-State Linearization of SISO Systems  236

6.4 Input-Output Linearization of SISO Systems 246
6.5 * Multi-Input Systems 266
6.6 Summary 270
6.7 Notes and References 271
6.8 Exercises 271
7. Sliding Control 276
7.1 Sliding Surfaces 277
7.1.1 A Notational Simplification 278
7.1.2 * Filippov's Construction of the Equivalent Dynamics 283
7.1.3 Perfect Performance - At a Price 285
7.1.4 Direct Implementations of Switching Control Laws 289
7.2 Continuous Approximations of Switching Control Laws 290
7.3 The Modeling/Performance Trade-Offs 301
7.4 * Multi-Input Systems 303
7.5 Summary 306
7.6 Notes and References 307
7.7 Exercises 307
8. Adaptive Control 311
8.1 Basic Concepts in Adaptive Control 312
8.1.1 Why Adaptive Control ? 312
8.1.2 What Is Adaptive Control ? 315
8.1.3 How To Design Adaptive Controllers ? 323
8.2 Adaptive Control of First-Order Systems 326
8.3 Adaptive Control of Linear Systems With Full State Feedback 335
8.4 Adaptive Control of Linear Systems With Output Feedback 339
8.4.1 Linear Systems With Relative Degree One 340
8.4.2 Linear Systems With Higher Relative Degree 346
8.5 Adaptive Control of Nonlinear Systems 350
8.6 Robustness of Adaptive Control Systems 353
8.7 * On-Line Parameter Estimation 358
8.7.1 Linear Parametrization Model 359
8.7.2 Prediction-Error-Based Estimation Methods 364
8.7.3 The Gradient Estimator 364
8.7.4 The Standard Least-Squares Estimator 370

8.7.5 Least-Squares With Exponential Forgetting 374
8.7.6 Bounded-Gain Forgetting 376
8.7.7 Concluding Remarks and Implementation Issues 381
1.8 Composite Adaptation 382
1.9 Summary 388
1.10 Notes and References 389
1.11 Exercises 389
9. Control of Multi-Input Physical Systems 392
9.1 Robotics as a Prototype 393
9.1.1 Position Control 394
9.1.2 Trajectory Control 397
9.2 Adaptive Robot Trajectory Control 403
9.2.1 The Basic Algorithm 404
9.2.2 * Composite Adaptive Trajectory Control 411
9.3 Putting Physics in Control 416
9.3.1 High-Frequency Unmodeled Dynamics 416
9.3.2 Conservative and Dissipative Dynamics 418
9.3.3 Robotics as a Metaphor 419
9.4 Spacecraft Control 422
9.4.1 The Spacecraft Model 422
9.4.2 Attitude Control 425
9.5 Summary 432
9.6 Notes and References 433
9.7 Exercises 433
BIBLIOGRAPHY 437
INDEX 459

Preface
In recent years, the availability of powerful low-cost microprocessors has spurred
great advances in the theory and applications of nonlinear control. In terms of theory,
major strides have been made in the areas of feedback linearization, sliding control,
and nonlinear adaptation techniques. In terms of applications, many practical
nonlinear control systems have been developed, ranging from digital "fly-by-wire"
flight control systems for aircraft, to "drive-by-wire" automobiles, to advanced robotic
and space systems. As a result, the subject of nonlinear control is occupying an
increasingly important place in automatic control engineering, and has become a
necessary part of the fundamental background of control engineers.
This book, based on a course developed at MIT, is intended as a textbook for
senior and graduate students, and as a self-study book for practicing engineers. Its
objective is to present the fundamental results of modern nonlinear control while
keeping the mathematical complexity to a minimum, and to demonstrate their use and
implications in the design of practical nonlinear control systems. Although a major
motivation of this book is to detail the many recent developments in nonlinear control,
classical techniques such as phase plane analysis and the describing function method
are also treated, because of their continued practical importance.
In order to achieve our fundamental objective, we have tried to bring the
following features to this book:
• Readability: Particular attention is paid to the readability of the book by
carefully organizing the concepts, intuitively interpreting the major results, and
selectively using the mathematical tools. The readers are only assumed to have had
one introductory control course. No mathematical background beyond ordinary
differential equations and elementary matrix algebra is required. For each new
result, interpretation is emphasized rather than mathematics. For each major result,
we try to ask and answer the following key questions: What does the result
intuitively and physically mean? How can it be applied to practical problems?
What is its relationship to other theorems? All major concepts and results are
demonstrated by examples. We believe that learning and generalization from
examples are crucial for proficiency in applying any theoretical result.
• Practicality: The choice and emphasis of materials is guided by the basic
xiii

XIV
objective of making an engineer or student capable of dealing with practical control
problems in industry. Some results of mostly theoretical interest are not included.
The selected materials, in one way or another, are intended to allow readers to gain
insights into the solution of real problems.
• Comprehensiveness: The book contains both classical materials, such as
Lyapunov analysis and describing function techniques, and more modern topics
such as feedback linearization, adaptive control, and sliding control. To facilitate
digestion, asterisks are used to indicate sections which, given their relative
complexity, can be safely skipped in a first reading.
• Currentness: In the past few years, a number of major results have been
obtained in nonlinear control, particularly in nonlinear control system design and in
robotics. It is one of the objectives of this book to present these new and important
developments, and their implications, in a clear, easily understandable fashion.
The book can thus be used as a reference and a guide to the active literature in
these fields.
The book is divided into two major parts. Chapters 2-5 present the major
analytical tools that can be used to study a nonlinear system, while chapters 6-9 treat
the major nonlinear controller design techniques. Each chapter is supplied with
exercises, allowing the reader to further explore specific aspects of the material
discussed. A detailed index and a bibliography are provided at the end of the book.
The material included exceeds what can be taught in one semester or self-
learned in a short period. The book can be studied in many ways, according to the
particular interests of the reader or the instructor. We recommend that a first reading
include a detailed study of chapter 3 (basic Lyapunov theory), sections 4.5-4.7
(Barbalat's lemma and passivity tools), section 6.1 and parts of sections 6.2-6.4
(feedback linearization), chapter 7 (sliding control), sections 8.1-8.3 and 8.5 (adaptive
control of linear and nonlinear systems), and chapter 9 (control of multi-input physical
systems). Conversely, sections denoted with an asterisk can be skipped in a first
reading.
Many colleagues, students, and friends greatly contributed to this book through
stimulating discussions and judicious suggestions. Karl Hedrick provided us with
continued enthusiasm and encouragement, and with many valuable comments and
suggestions. Discussions with Karl Astrdm and Semyon Meerkov helped us better
define the tone of the book and its mathematical level. Harry Asada, Jo Bentsman,
Marika DiBenedetto, Olav Egeland, Neville Hogan, Marija Ilic, Lars Nielsen, Ken
Salisbury, Sajhendra Singh, Mark Spong, David Wormley, and Dana Yoerger
provided many useful suggestions and much moral support. Barbara Hove created

XV
most of the nicer drawings in the book; Giinter Niemeyer's expertise and energy was
invaluable in setting up the computing and word processing environments; Hyun Yang
greatly helped with the computer simulations; all three provided us with extensive
technical and editorial comments. The book also greatly benefited from the interest
and enthusiasm of many students who took the course at MIT.
Partial summer support for the first author towards the development of the book
was provided by Gordon Funds. Finally, the energy and professionalism of Tim Bozik
and Jennifer Wenzel at Prentice-Hall were very effective and highly appreciated.
Jean-Jacques E. Slotine
Weiping Li

Applied
Nonlinear
Control

Chapter 1
Introduction
The subject of nonlinear control deals with the analysis and the design of nonlinear
control systems, i.e., of control systems containing at least one nonlinear component.
In the analysis, a nonlinear closed-loop system is assumed to have been designed, and
we wish to determine the characteristics of the system's behavior. In the design, we
are given a nonlinear plant to be controlled and some specifications of closed-loop
system behavior, and our task is to construct a controller so that the closed loop
system meets the desired characteristics. In practice, of course, the issues of design
and analysis are intertwined, because the design of a nonlinear control system usually
involves an iterative process of analysis and design.
This introductory chapter provides the background for the specific analysis and
design methods to be discussed in the later chapters. Section 1.1 explains the
motivations for embarking on a study of nonlinear control. The unique and rich
behaviors exhibited by nonlinear systems are discussed in section 1.2. Finally, section
1.3 gives an overview of the organization of the book.
1.1 Why Nonlinear Control ?
Linear control is a mature subject with a variety of powerful methods and a long
history of successful industrial applications. Thus, it is natural for one to wonder why
so many researchers and designers, from such broad areas as aircraft and spacecraft
control, robotics, process control, and biomedical engineering, have recently showed
1

2 Introduction Chap. 1
an active interest in the development and applications of nonlinear control
methodologies. Many reasons can be cited for this interest:
• Improvement of existing control systems: Linear control methods rely on
the key assumption of small range operation for the linear model to be valid. When
the required operation range is large, a linear controller is likely to perform very
poorly or to be unstable, because the nonlinearities in the system cannot be properly
compensated for. Nonlinear controllers, on the other hand, may handle the
nonlinearities in large range operation directly. This point is easily demonstrated in
robot motion control problems. When a linear controller is used to control robot
motion, it neglects the nonlinear forces associated with the motion of the robot links.
The controller's accuracy thus quickly degrades as the speed of motion increases,
because many of the dynamic forces involved, such as Coriolis and centripetal forces,
vary as the square of the speed. Therefore, in order to achieve a pre-specified
accuracy in robot tasks such as pick-and-place, arc welding and laser cutting, the
speed of robot motion, and thus productivity, has to be kept low. On the other hand, a
conceptually simple nonlinear controller, commonly called computed torque
controller, can fully compensate the nonlinear forces in the robot motion and lead to
high accuracy control for a very large range of robot speeds and a large workspace.
• Analysis of hard nonlinearities: Another assumption of linear control is that
the system model is indeed linearizable. However, in control systems there are many
nonlinearities whose discontinuous nature does not allow linear approximation. These
so-called "hard nonlinearities" include Coulomb friction, saturation, dead-zones,
backlash, and hysteresis, and are often found in control engineering. Their effects
cannot be derived from linear methods, and nonlinear analysis techniques must be
developed to predict a system's performance in the presence of these inherent
nonlinearities. Because such nonlinearities frequently cause undesirable behavior of
the control systems, such as instabilities or spurious limit cycles, their effects must be
predicted and properly compensated for.
• Dealing with model uncertainties: In designing linear controllers, it is
usually necessary to assume that the parameters of the system model are reasonably
well known. However, many control problems involve uncertainties in the model
parameters. This may be due to a slow time variation of the parameters (e.g., of
ambient air pressure during an aircraft flight), or to an abrupt change in parameters
(e.g,, in the inertial parameters of a robot when a new object is grasped). A linear
controller based on inaccurate or obsolete values of the model parameters may exhibit
significant performance degradation or even instability. Nonlinearities can be
intentionally introduced into the controller part of a control system so that model

Sect. 1.1 Why Nonlinear Control? 3
uncertainties can be tolerated. Two classes of nonlinear controllers for this purpose
are robust controllers and adaptive controllers.
• Design Simplicity: Good nonlinear control designs may be simpler and more
intuitive than their linear counterparts. This a priori paradoxical result comes from the
fact that nonlinear controller designs are often deeply rooted in the physics of the
plants. To take a very simple example, consider a swinging pendulum attached to a
hinge, in the vertical plane. Starting from some arbitrary initial angle, the pendulum
will oscillate and progressively stop along the vertical. Although the pendulum's
behavior could be analyzed close to equilibrium by linearizing the system, physically
its stability has very little to do with the eigenvalues of some linearized system matrix:
it comes from the fact that the total mechanical energy of the system is progressively
dissipated by various friction forces (e.g., at the hinge), so that the pendulum comes to
rest at a position of minimal energy.
There may be other related or unrelated reasons to use nonlinear control
techniques, such as cost and performance optimality. In industrial settings, ad-hoc
extensions of linear techniques to control advanced machines with significant
nonlinearities may result in unduly costly and lengthy development periods, where the
control code comes with little stability or performance guarantees and is extremely
hard to transport to similar but different applications. Linear control may require high
quality actuators and sensors to produce linear behavior in the specified operation
range, while nonlinear control may permit the use of less expensive components with
nonlinear characteristics. As for performance optimality, we can cite bang-bang type
controllers, which can produce fast response, but are inherently nonlinear.
Thus, the subject of nonlinear control is an important area of automatic control.
Learning basic techniques of nonlinear control analysis and design can significantly
enhance the ability of a control engineer to deal with practical control problems
effectively. It also provides a sharper understanding of the real world, which is
inherently nonlinear. In the past, the application of nonlinear control methods had
been limited by the computational difficulty associated with nonlinear control design
and analysis. In recent years, however, advances in computer technology have greatly
relieved this problem. Therefore, there is currently considerable enthusiasm for the
research and application of nonlinear control methods. The topic of nonlinear control
design for large range operation has attracted particular attention because, on the one
hand, the advent of powerful microprocessors has made the implementation of
nonlinear controllers a relatively simple matter, and, on the other hand, modern
technology, such as high-speed high-accuracy robots or high-performance aircrafts, is
demanding control systems with much more stringent design specifications.
Nonlinear control occupies an increasingly conspicuous position in control

4 Introduction Chap. 1
engineering, as reflected by the ever-increasing number of papers and reports on
nonlinear control research and applications.
1.2 Nonlinear System Behavior
Physical systems are inherently nonlinear. Thus, all control systems are nonlinear to a
certain extent. Nonlinear control systems can be described by nonlinear differential
equations. However, if the operating range of a control system is small, and if the
involved nonlinearities are smooth, then the control system may be reasonably
approximated by a linearized system, whose dynamics is described by a set of linear
differential equations.
NONLINEARITIES
Nonlinearities can be classified as inherent (natural) and intentional (artificial).
Inherent nonlinearities are those which naturally come with the system's hardware and
motion. Examples of inherent nonlinearities include centripetal forces in rotational
motion, and Coulomb friction between contacting surfaces. Usually, such
nonlinearities have undesirable effects, and control systems have to properly
compensate for them. Intentional nonlinearities, on the other hand, are artificially
introduced by the designer. Nonlinear control laws, such as adaptive control laws and
bang-bang optimal control laws, are typical examples of intentional nonlinearities.
Nonlinearities can also be classified in terms of their mathematical properties,
as continuous and discontinuous. Because discontinuous nonlinearities cannot be
locally approximated by linear functions, they are also called "hard" nonlinearities.
Hard nonlinearities (such as, e.g., backlash, hysteresis, or stiction) are commonly
found in control systems, both in small range operation and large range operation.
Whether a system in small range operation should be regarded as nonlinear or linear
depends on the magnitude of the hard nonlinearities and on the extent of their effects
on the system performance. A detailed discussion of hard nonlinearities is provided in
section 5.2.
LINEAR SYSTEMS
Linear control theory has been predominantly concerned with the study of linear time-
invariant (LTI) control systems, of the form
x = Ax (1.1)
with x being a vector of states and A being the system matrix. LTI systems have quite
simple properties, such as

Sect. 1.2 Nonlinear System Behavior 5
• a linear system has a unique equilibrium point if A is nonsingular;
• the equilibrium point is stable if all eigenvalues of A have negative real
parts, regardless of initial conditions;
• the transient response of a linear system is composed of the natural modes
of the system, and the general solution can be solved analytically;
• in the presence of an external input u(t), i.e., with
x=Ax+Bu , (1.2)
the system response has a number of interesting properties. First, it satisfies
the principle of superposition. Second, the asymptotic stability of the system
(1.1) implies bounded-input bounded-output stability in the presence of u.
Third, a sinusoidal input leads to a sinusoidal output of the same frequency.
AN EXAMPLE OF NONLINEAR SYSTEM BEHAVIOR
The behavior of nonlinear systems, however, is much more complex. Due to the lack
of linearity and of the associated superposition property, nonlinear systems respond to
external inputs quite differently from linear systems, as the following example
illustrates.
Example 1.1: A simplified model of the motion of an underwater vehicle can be written
v + |v|v = « (1.3)
where v is the vehicle velocity and u is the control input (the thrust provided by a propeller). The
nonlinearity |v|v corresponds to a typical "square-law" drag.
Assume that we apply a unit step input in thrust u, followed 5 seconds later by a negative unit
step input. The system response is plotted in Figure 1.1. We see that the system settles much
faster in response to the positive unit step than it does in response to the subsequent negative unit
step. Intuitively, this can be interpreted as reflecting the fact that the "apparent damping"
coefficient |v| is larger at high speeds than at low speeds.
Assume now that we repeat the same experiment but with larger steps, of amplitude 10.
Predictably, the difference between the settling times in response to the positive and negative
steps is even more marked (Figure 1.2). Furthermore, the settling speed v in response to the first
s
step is not 10 times that obtained in response to the first unit step in the first experiment, as it
would be in a linear system. This can again be understood intuitively, by writing that

| Introduction |     |     | Chap. 1 |     |
| ------------ | --- | --- | ------- | --- |
3  1.0.
•5  0.8
0.6
0.4
0.2
0.0
| 5         | 10  |     | 10 15     | 20  |
| --------- | --- | --- | --------- | --- |
| time(sec) |     |     | time(sec) |     |
Figure 1.1: Response of system (1.3) to unit steps
| 10.0 |     | >  10.0 r |     |     |
| ---- | --- | --------- | --- | --- |
yti
8
| 8.0 - |     | 8.0 |     |     |
| ----- | --- | --- | --- | --- |
| 6.0   |     | 6.0 |     |     |
•
| 4.0 |     | 4.0 |     |     |
| --- | --- | --- | --- | --- |
-
| 2.0 |     | 2.0 |     |     |
| --- | --- | --- | --- | --- |
•
| 00  | t   | 0.0 |        |     |
| --- | --- | --- | ------ | --- |
|     | 10  |     | 10 15  | 20  |
time(sec)
time(sec)
Figure 1.2 : Response of system (1.3) to steps of amplitude 10
| « =1  =>  0 + |vs|vJ=l  | =>  | Vj=l |     |     |
| ----------------------- | --- | ---- | --- | --- |
| u =10  =>  0 + lvJv^lO  | =>  | v i  |     |     |
Carefully  understanding and effectively  controlling this nonlinear behavior is particularly
important if the vehicle is to move in a large dynamic range and change speeds continually, as is
typical of industrial remotely-operated underwater vehicles (R.O.V.'s).  D
SOME COMMON NONLINEAR SYSTEM BEHAVIORS
Let us now discuss some common nonlinear system properties, so as to familiarize
ourselves  with  the  complex  behavior  of  nonlinear  systems  and  provide  a  useful
background for our study in the rest of the book.

Sect. 1.2 Nonlinear System Behavior
Multiple Equilibrium Points
Nonlinear systems frequently have more than one equilibrium point (an equilibrium
point is a point where the system can stay forever without moving, as we shall
formalize later). This can be seen by the following simple example.
Example 1.2: A first-order system
Consider the first order system
(1.4)
with initial condition x(0) = x. Its linearization is
g
x = -x (1.5)
The solution of this linear equation is x(t) =xe~'. It is plotted in Figure 1.3(a) for various initial
o
conditions. The linearized system clearly has a unique equilibrium point at x = 0.
By contrast, integrating equation dx/(-x + x2) - dt, the actual response of the nonlinear
dynamics (1.4) can be found to be
x(t) = -
This response is plotted in Figure 1.3(b) for various initial conditions. The system has two
equilibrium points, x - 0 and x = 1 , and its qualitative behavior strongly depends on its initial
condition. CD
\x(t)
x(t)
(a) (b)
Figure 1.3 : Responses of the linearized system (a) and the nonlinear system (b)

8 Introduction Chap. 1
The issue of motion stability can also be discussed with the aid of the above
example. For the linearized system, stability is seen by noting that for any initial
condition, the motion always converges to the equilibrium point x = 0. However,
consider now the actual nonlinear system. While motions starting with x < 1 will
o
indeed converge to the equilibrium point x = 0, those starting with x> I will go to
o
infinity (actually in finite time, a phenomenon known as finite escape time). This
means that the stability of nonlinear systems may depend on initial conditions.
In the presence of a bounded external input, stability may also be dependent on
the input value. This input dependence is highlighted by the so-called bilinear system
X = XU
If the input u is chosen to be - 1, then the state x converges to 0. If « = 1, then | x \
tends to infinity.
Limit Cycles
Nonlinear systems can display oscillations of fixed amplitude and fixed period without
external excitation. These oscillations are called limit cycles, or self-excited
oscillations. This important phenomenon can be simply illustrated by a famous
oscillator dynamics, first studied in the 1920's by the Dutch electrical engineer
Balthasar Van der Pol.
Example 1.3: Van der Pol Equation
The second-order nonlinear differential equation
mx + 2c(x2-l)x + kx = 0 (1.6)
where m, c and k are positive constants, is the famous Van der Pol equation. It can be regarded as
describing a mass-spring-damper system with a position-dependent damping coefficient
2c(x2 - 1) (or, equivalently, an RLC electrical circuit with a nonlinear resistor). For large values
of jr, the damping coefficient is positive and the damper removes energy from the system. This
implies that the system motion has a convergent tendency. However, for small values of x, the
damping coefficient is negative and the damper adds energy into the system. This suggests that
the system motion has a divergent tendency. Therefore, because the nonlinear damping varies
with x, the system motion can neither grow unboundedly nor decay to zero. Instead, it displays a
sustained oscillation independent of initial conditions, as illustrated in Figure 1.4. This so-called
limit cycle is sustained by periodically releasing energy into and absorbing energy from the
environment, through the damping term. This is in contrast with the case of a conservative mass-
spring system, which does not exchange energy with its environment during its vibration. C3

Sect. 1.2 Nonlinear System Behavior 9
Figure 1.4 : Responses of the Van der Pol oscillator
Of course, sustained oscillations can also be found in linear systems, in the case
of marginally stable linear systems (such as a mass-spring system without damping) or
in the response to sinusoidal inputs. However, limit cycles in nonlinear systems are
different from linear oscillations in a number of fundamental aspects. First, the
amplitude of the self-sustained excitation is independent of the initial condition, as
seen in Figure 1.2, while the oscillation of a marginally stable linear system has its
amplitude determined by its initial conditions. Second, marginally stable linear
systems are very sensitive to changes in system parameters (with a slight change
capable of leading either to stable convergence or to instability), while limit cycles are
not easily affected by parameter changes.
Limit cycles represent an important phenomenon in nonlinear systems. They
can be found in many areas of enginering and nature. Aircraft wing fluttering, a limit
cycle caused by the interaction of aerodynamic forces and structural vibrations, is
frequently encountered and is sometimes dangerous. The hopping motion of a legged
robot is another instance of a limit cycle. Limit cycles also occur in electrical circuits,
e.g., in laboratory electronic oscillators. As one can see from these examples, limit
cycles can be undesirable in some cases, but desirable in other cases. An engineer has
to know how to eliminate them when they are undesirable, and conversely how to
generate or amplify them when they are desirable. To do this, however, requires an
understanding of the properties of limit cycles and a familiarity with the tools for
manipulating them.
Bifurcations
As the parameters of nonlinear dynamic systems are changed, the stability of the
equilibrium point can change (as it does in linear systems) and so can the number of
equilibrium points. Values of these parameters at which the qualitative nature of the

10 Introduction Chap. 1
system's motion changes are known as critical or bifurcation values. The
phenomenon of bifurcation, i.e., quantitative change of parameters leading to
qualitative change of system properties, is the topic of bifurcation theory.
For instance, the smoke rising from an incense stick (smokestacks and
cigarettes are old-fashioned) first accelerates upwards (because it is lighter than the
ambient air), but beyond some critical velocity breaks into swirls. More prosaically,
let us consider the system described by the so-called undamped Duffing equation
x + ax + x3 = 0
(the damped Duffing equation is x + ex + ax + px3 = 0 , which may represent a
mass-damper-spring system with a hardening spring). We can plot the equilibrium
points as a function of the parameter a. As a varies from positive to negative, one
equilibrium point splits into three points (x = 0, "Noc, - ~ia ), as shown in Figure
e
1.5(a). This represents a qualitative change in the dynamics and thus a = 0 is a critical
bifurcation value. This kind for bifurcation is known as a pitchfork, due to the shape
of the equilibrium point plot in Figure 1.5(a).
Another kind of bifurcation involves the emergence of limit cycles as
parameters are changed. In this case, a pair of complex conjugate eigenvalues
Pj = y + ja>, p = J-ju> cross from the left-half plane into the right-half plane, and
2
the response of the unstable system diverges to a limit cycle. Figure 1.5(b) depicts the
change of typical system state trajectories (states are x and x) as the parameter a is
varied. This type of bifurcation is called a Hopf bifurcation.
stable
stable unstable
stable
(a)
Figure 1.5 : (a) a pitchfork bifurcation; (b) a Hopf bifurcation

Sect. 1.2 Nonlinear System Behavior 11
Chaos
For stable linear systems, small differences in initial conditions can only cause small
differences in output. Nonlinear systems, however, can display a phenomenon called
chaos, by which we mean that the system output is extremely sensitive to initial
conditions. The essential feature of chaos is the unpredictability of the system output.
Even if we have an exact model of a nonlinear system and an extremely accurate
computer, the system's response in the long-run still cannot be well predicted.
Chaos must be distinguished from random motion. In random motion, the
system model or input contain uncertainty and, as a result, the time variation of the
output cannot be predicted exactly (only statistical measures are available). In chaotic
motion, on the other hand, the involved problem is deterministic, and there is little
uncertainty in system model, input, or initial conditions.
As an example of chaotic behavior, let us consider the simple nonlinear system
= 6 sinr
which may represent a lightly-damped, sinusoidally forced mechanical structure
undergoing large elastic deflections. Figure 1.6 shows the responses of the system
corresponding to two almost identical initial conditions, namely x(0) = 2, x(0) = 3
(thick line) and x(Q) = 2.01, x(0) = 3.01 (thin line). Due to the presence of the strong
nonlinearity in x5, the two responses are radically different after some time.
-3.0
10 20 25 30 35 40 45 50
timefsec")
Figure 1.6 : Chaotic behavior of a nonlinear system
Chaotic phenomena can be observed in many physical systems. The most
commonly seen physical problem is turbulence in fluid mechanics (such as the swirls
of our incense stick). Atmospheric dynamics also display clear chaotic behavior, thus

12 Introduction Chap. 1
making long-term weather prediction impossible. Some mechanical and electrical
systems known to exhibit chaotic vibrations include buckled elastic structures,
mechanical systems with play or backlash, systems with aeroelastic dynamics, wheel-
rail dynamics in railway systems, and, of course, feedback control devices.
Chaos occurs mostly in strongly nonlinear systems. This implies that, for a
given system, if the initial condition or the external input cause the system to operate
in a highly nonlinear region, it increases the possibility of generating chaos. Chaos
cannot occur in linear systems. Corresponding to a sinusoidal input of arbitrary
magnitude, the linear system response is always a sinusoid of the same frequency. By
contrast, the output of a given nonlinear system may display sinusoidal, periodic, or
chaotic behaviors, depending on the initial condition and the input magnitude.
In the context of feedback control, it is of course of interest to know when a
nonlinear system will get into a chaotic mode (so as to avoid it) and, in case it does,
how to recover from it. Such problems are the object of active research.
Other behaviors
Other interesting types of behavior, such as jump resonance, subharmonic generation,
asynchronous quenching, and frequency-amplitude dependence of free vibrations, can
also occur and become important in some system studies. However, the above
description should provide ample evidence that nonlinear systems can have
considerably richer and more complex behavior than linear systems.
1.3 An Overview of the Book
Because nonlinear systems can have much richer and more complex behaviors than
linear systems, their analysis is much more difficult. Mathematically, this is reflected
in two aspects. First, nonlinear equations, unlike linear ones, cannot in general be
solved analytically, and therefore a complete understanding of the behavior of a
nonlinear system is very difficult. Second, powerful mathematical tools like Laplace
and Fourier transforms do not apply to nonlinear systems.
As a result, there are no systematic tools for predicting the behavior of
nonlinear systems, nor are there systematic procedures for designing nonlinear control
systems. Instead, there is a rich inventory of powerful analysis and design tools, each
best applicable to particular classes of nonlinear control problems. It is the objective of
this book to present these various tools, with particular emphasis on their powers and
limitations, and on how they can be effectively combined.
This book is divided into two major parts. Part I (chapters 2-5) presents the

Sect. 1.4 Notes and References 13
major analytical tools that can be used to study a nonlinear system. Part II (chapters
6-9) discusses the major nonlinear controller design techniques. Each part starts with a
short introduction providing the background for the main issues and techniques to be
discussed.
In chapter 2, we further familiarize ourselves with some basic nonlinear system
behaviors, by studying second-order systems using the simple graphical tools provided
by so-called phase plane analysis. Chapter 3 introduces the most fundamental analysis
tool to be used in this book, namely the concept of a Lyapunov function and its use in
nonlinear stability analysis. Chapter 4 studies selected advanced topics in stability
analysis. Chapter 5 discusses an approximate nonlinear system analysis method, the
describing function method, which aims at extending to nonlinear systems some of the
desirable and intuitive properties of linear frequency response analysis.
The basic idea of chapter 6 is to study under what conditions the dynamics of a
nonlinear system can be algebraically transformed in that of a linear system, on which
linear control design techniques can in turn be applied. Chapters 7 and 8 then study
how to reduce or practically eliminate the effects of model uncertainties on the
stability and performance of feedback controllers for linear or nonlinear systems,
using so-called robust and adaptive approaches. Finally, chapter 9 extensively
discusses the use of known physical properties to simplify and enhance the design of
controllers for complex multi-input nonlinear systems.
The book concentrates on nonlinear systems represented in continuous-time
form. Even though most control systems are implemented digitally, nonlinear
physical systems are continuous in nature and are hard to meaningfully discretize,
while digital control systems may be treated as continuous-time systems in analysis
and design if high sampling rates are used. Given the availability of cheap
computation, the most common practical case when it may be advantageous to
consider sampling explicitly is when measurements are sparse, as e.g., in the case of
underwater vehicles using acoustic navigation. Some practical issues involved in the
digital implementation of controllers designed from continuous-time formulations are
discussed in the introduction to Part II.
1.4 Notes and References
Detailed discussions of bifurcations and chaos can be found, e.g., in [Guckenheimer and Holmes,
1983] and in [Thompson and Stewart, 1986], from which the example of Figure 1.6 is adapted.

Part I
Nonlinear Systems Analysis
The objective of this part is to present various tools available for analyzing nonlinear
control systems. The study of these nonlinear analysis techniques is important for a
number of reasons. First, theoretical analysis is usually the least expensive way of
exploring a system's characteristics. Second, simulation, though very important in
nonlinear control, has to be guided by theory. Blind simulation of nonlinear systems is
likely to produce few results or misleading results. This is especially true given the
great richness of behavior that nonlinear systems can exhibit, depending on initial
conditions and inputs. Third, the design of nonlinear controllers is always based on
analysis techniques. Since design methods are usually based on analysis methods, it is
almost impossible to master the design methods without first studying the analysis
tools. Furthermore, analysis tools also allow us to assess control designs after they
have been made, and, in case of inadequate performance, they may also suggest
directions of modifying the control designs.
It should not come as a surprise that no universal technique has been devised for
the analysis of all nonlinear control systems. In linear control, one can analyze a
system in the time domain or in the frequency domain. However, for nonlinear
control systems, none of these standard approaches can be used, since direct solution
of nonlinear differential equations is generally impossible, and frequency domain
transformations do not apply.
14

Parti Nonlinear Systems Analysis 15
While the analysis of nonlinear control systems is difficult, serious efforts have
been made to develop appropriate theoretical tools for it. Many methods of nonlinear
control system analysis have been proposed. Let us briefly describe some of these
methods before discussing their details in the following chapters.
Phase plane analysis
Phase plane analysis, discussed in chapter 2, is a graphical method of studying
second-order nonlinear systems. Its basic idea is to solve a second order differential
equation graphically, instead of seeking an analytical solution. The result is a family
of system motion trajectories on a two-dimensional plane, called the phase plane,
which allow us to visually observe the motion patterns of the system. While phase
plane analysis has a number of important advantages, it has the fundamental
disadvantage of being applicable only to systems which can be well approximated by
a second-order dynamics. Because of its graphical nature, it is frequently used to
provide intuitive insights about nonlinear effects.
Lyapunov theory
Basic Lyapunov theory comprises two methods introduced by Lyapunov, the
indirect method and the direct method. The indirect method, or linearization method,
states that the stability properties of a nonlinear system in the close vicinity of an
equilibrium point are essentially the same as those of its linearized approximation. The
method serves as the theoretical justification for using linear control for physical
systems, which are always inherently nonlinear. The direct method is a powerful tool
for nonlinear system analysis, and therefore the so-called Lyapunov analysis often
actually refers to the direct method. The direct method is a generalization of the
energy concepts associated with a mechanical system: the motion of a mechanical
system is stable if its total mechanical energy decreases all the time. In using the
direct method to analyze the stability of a nonlinear system, the idea is to construct a
scalar energy-like function (a Lyapunov function) for the system, and to see whether it
decreases. The power of this method comes from its generality: it is applicable to all
kinds of control systems, be they time-varying or time-invariant, finite dimensional or
infinite dimensional. Conversely, the limitation of the method lies in the fact that it is
often difficult to find a Lyapunov function for a given system.
Although Lyapunov's direct method is originally a method of stability analysis,
it can be used for other problems in nonlinear control. One important application is the
design of nonlinear controllers. The idea is to somehow formulate a scalar positive
function of the system states, and then choose a control law to make this function
decrease. A nonlinear control system thus designed will be guaranteed to be stable.
Such a design approach has been used to solve many complex design problems, e.g.,

16 Nonlinear Systems Analysis Part I
in robotics and adaptive control. The direct method can also be used to estimate the
performance of a control system and study its robustness. The important subject of
Lyapunov analysis is studied in chapters 3 and 4, with chapter 3 presenting the main
concepts and results in Lyapunov theory, and chapter 4 discussing some advanced
topics.
Describing functions
The describing function method is an approximate technique for studying
nonlinear systems. The basic idea of the method is to approximate the nonlinear
components in nonlinear control systems by linear "equivalents", and then use
frequency domain techniques to analyze the resulting systems. Unlike the phase plane
method, it is not restricted to second-order systems. Unlike Lyapunov methods,
whose applicability to a specific system hinges on the success of a trial-and-error
search for a Lyapunov function, its application is straightforward for nonlinear
systems satisfying some easy-to-check conditions.
The method is mainly used to predict limit cycles in nonlinear systems. Other
applications include the prediction of subharmonic generation and the determination
of system response to sinusoidal excitation. The method has a number of advantages.
First, it can deal with low order and high order systems with the same straightforward
procedure. Second, because of its similarity to frequency-domain analysis of linear
systems, it is conceptually simple and physically appealing, allowing users to exercise
their physical and engineering insights about the control system. Third, it can deal
with the "hard nonlinearities" frequently found in control systems without any
difficulty. As a result, it is an important tool for practical problems of nonlinear
control analysis and design. The disadvantages of the method are linked to its
approximate nature, and include the possibility of inaccurate predictions (false
predictions may be made if certain conditions are not satisfied) and restrictions on the
systems to which it applies (for example, it has difficulties in dealing with systems
with multiple nonlinearities).

Chapter 2
Phase Plane Analysis
Phase plane analysis is a graphical method for studying second-order systems, which
was introduced well before the turn of the century by mathematicians such as Henri
Poincare. The basic idea of the method is to generate, in the state space of a second-
order dynamic system (a two-dimensional plane called the phase plane), motion
trajectories corresponding to various initial conditions, and then to examine the
qualitative features of the trajectories. In such a way, information concerning stability
and other motion patterns of the system can be obtained. In this chapter, our objective
is to gain familiarity with nonlinear systems through this simple graphical method.
Phase plane analysis has a number of useful properties. First, as a graphical
method, it allows us to visualize what goes on in a nonlinear system starting from
various initial conditions, without having to solve the nonlinear equations analytically.
Second, it is not restricted to small or smooth nonlinearities, but applies equally well
to strong nonlinearities and to "hard" nonlinearities. Finally, some practical control
systems can indeed be adequately approximated as second-order systems, and the
phase plane method can be used easily for their analysis. Conversely, of course, the
fundamental disadvantage of the method is that it is restricted to second-order (or first-
order) systems, because the graphical study of higher-order systems is
computationally and geometrically complex.
17

18 Phase Plane Analysis Chap. 2
2.1 Concepts of Phase Plane Analysis
2.1.1 Phase Portraits
The phase plane method is concerned with the graphical study of second-order
autonomous systems described by
x =f ( ,x ) (2.1b)
2 2 Xl 2
where jq and x are the states of the system, and/, and/ are nonlinear functions of
2 2
the states. Geometrically, the state space of this system is a plane having x, and x as
2
coordinates. We will call this plane the phase plane.
Given a set of initial conditions x(0) = x, Equation (2.1) defines a solution
0
x(0- With time / varied from zero to infinity, the solution x(t) can be represented
geometrically as a curve in the phase plane. Such a curve is called a phase plane
trajectory. A family of phase plane trajectories corresponding to various initial
conditions is called a phase portrait of a system.
To illustrate the concept of phase portrait, let us consider the following simple
system.
Example 2.1: Phase portrait of a mass-spring system
The governing equation of the mass-spring system in Figure 2.1 (a) is the familiar linear second-
order differential equation
x+x = Q (2.2)
Assume that the mass is initially at rest, at length x . Then the solution of the equation is
o
x(l) = x cos t
o
x(t) = — A'sin(
o
Eliminating time / from the above equations, we obtain the equation of the trajectories
This represents a circle in the phase plane. Corresponding to different initial conditions, circles of
different radii can be obtained. Plotting these circles on the phase plane, we obtain a phase
portrait for the mass-spring system (Figure 2.1 .b). U

Sect. 2.1 Concepts of Phase Plane Analysis 19
k= 1 m=l
(a) (b)
Figure 2.1 : A mass-spring system and its phase portrait
The power of the phase portrait lies in the fact that once the phase portrait of a
system is obtained, the nature of the system response corresponding to various initial
conditions is directly displayed on the phase plane. In the above example, we easily
see that the system trajectories neither converge to the origin nor diverge to infinity.
They simply circle around the origin, indicating the marginal nature of the system's
stability.
A major class of second-order systems can be described by differential
equations of the form
x +f(x, x) = 0 (2.3)
In state space form, this dynamics can be represented as
k\=x2
with A| = x and JT = -*• Most second-order systems in practice, such as mass-damper-
2
spring systems in mechanics, or resistor-coil-capacitor systems in electrical
engineering, can be represented in or transformed into this form. For these systems,
the states are x and its derivative x. Traditionally, the phase plane method is
developed for the dynamics (2.3), and the phase plane is defined as the plane having x
and x as coordinates. But it causes no difficulty to extend the method to more general
dynamics of the form (2.1), with the (xj , xj) plane as the phase plane, as we do in this
chapter.

20 Phase Plane Analysis Chap. 2
2.1.2 Singular Points
An important concept in phase plane analysis is that of a singular point. A singular
point is an equilibrium point in the phase plane. Since an equilibrium point is defined
as a point where the system states can stay forever, this implies that x = 0, and using
(2.1),
/,(*,, JC) = 0 /(jr,jr) = 0 (2.4)
2 2 1 2
The values of the equilibrium states can be solved from (2.4).
For a linear system, there is usually only one singular point (although in some
cases there can be a continuous set of singular points, as in the system x + x = 0, for
which all points on the real axis are singular points). However, a nonlinear system
often has more than one isolated singular point, as the following example shows.
Example 2.2: A nonlinear second-order system
Consider the system
x + 0.6 x + 3 x + x1 = 0
whose phase portrait is plotted in Figure 2.2. The system has two singular points, one at (0, 0)
and the other at (-3, 0). The motion patterns of the system trajectories in the vicinity of the two
singular points have different natures. The trajectories move towards the point x = 0 while
moving away from the point x = — 3. D
One may wonder why an equilibrium point of a second-order system is called a
singular point. To answer this, let us examine the slope of the phase trajectories.
From (2.1), the slope of the phase trajectory passing through a point (X|,x) is
2
determined by
2 J2\ ! V
(2 5)
dx\ f\(x ,x )
x 2
With the functions /] and f assumed to be single valued, there is usually a definite
2
value for this slope at any given point in phase plane. This implies that the phase
trajectories will not intersect. At singular points, however, the value of the slope is
0/0, i.e., the slope is indeterminate. Many trajectories may intersect at such points, as
seen from Figure 2.2. This indeterminacy of the slope accounts for the adjective
"singular".
Singular points are very important features in the phase plane. Examination of
the singular points can reveal a great deal of information about the properties of a

Sect. 2.1 Concepts of Phase Plane Analysis 21
to infinity
Figure 2.2 : The phase portrait of a nonlinear system
system. In fact, the stability of linear systems is uniquely characterized by the nature
of their singular points. For nonlinear systems, besides singular points, there may be
more complex features, such as limit cycles. These issues will be discussed in detail
in sections 2.3 and 2.4.
Note that, although the phase plane method is developed primarily for second-
order systems, it can also be applied to the analysis of first-order systems of the form
x +f(x) = 0
The idea is still to plot x with respect to x in the phase plane. The difference now is
that the phase portrait is composed of a single trajectory.

22 Phase Plane Analysis Chap. 2
Example 2.3: A first-order system
Consider the system
There are three singular points, defined by - 4x + x3 = 0, namely, x = 0, -2, and 2. The phase-
portrait of the system consists of a single trajectory, and is shown in Figure 2.3. The arrows in
the figure denote the direction of motion, and whether they point toward the left or the right at a
particular point is determined by the sign of x at that point. It is seen from the phase portrait of
this system that the equilibrium point x = 0 is stable, while the other two are unstable. O
stable
unstable
Figure 2.3 : Phase trajectory of a first-
order system
2.1.3 Symmetry in Phase Plane Portraits
A phase portrait may have a priori known symmetry properties, which can simplify its
generation and study. If a phase portrait is symmetric with respect to the X\ or the x
2
axis, one only needs in practice to study half of it. If a phase portrait is symmetric
with respect to both the Xj and x axes, only one quarter of it has to be explicitly
2
considered.
Before generating a phase portrait itself, we can determine its symmetry
properties by examining the system equations. Let us consider the second-order
dynamics (2.3). The slope of trajectories in the phase plane is of the form
dx f{x\,x )
2 2
dx,
1
Since symmetry of the phase portraits also implies symmetry of the slopes (equal in
absolute value but opposite in sign), we can identify the following situations:
Symmetry about the x axis: The condition is
i

Sect. 2.2 Constructing Phase Portraits 23
f(x x ) = f(x,-x )
h 2 l 2
This implies that the function / should be even in x- The mass-spring system in
2
Example 2.1 satisfies this condition. Its phase portrait is seen to be symmetric about
axis.
Symmetry about the x axis: Similarly,
2
f(x\,x ) = -f(-x,x )
2 l 2
implies symmetry with respect to the x axis. The mass-spring system also satisfies
2
this condition.
Symmetry about the origin: When
f{x,x ) = -f(-x -x )
{ 2 h 2
the phase portrait of the system is symmetric about the origin.
2.2 Constructing Phase Portraits
Today, phase portraits are routinely computer-generated. In fact, it is largely the
advent of the computer in the early 1960's, and the associated ease of quickly
generating phase portraits, which spurred many advances in the study of complex
nonlinear dynamic behaviors such as chaos. However, of course (as e.g., in the case of
root locus for linear systems), it is still practically useful to learn how to roughly
sketch phase portraits or quickly verify the plausibility of computer outputs.
There are a number of methods for constructing phase plane trajectories for
linear or nonlinear systems, such as the so-called analytical method, the method of
isoclines, the delta method, Lienard's method, and Pell's method. We shall discuss
two of them in this section, namely, the analytical method and the method of isoclines.
These methods are chosen primarily because of their relative simplicity. The
analytical method involves the analytical solution of the differential equations
describing the systems. It is useful for some special nonlinear systems, particularly
piece-wise linear systems, whose phase portraits can be constructed by piecing
together the phase portraits of the related linear systems. The method of isoclines is a
graphical method which can conveniently be applied to construct phase portraits for
systems which cannot be solved analytically, which represent by far the most common
case.

24 Phase Plane Analysis Chap. 2
ANALYTICAL METHOD
There are two techniques for generating phase plane portraits analytically. Both
techniques lead to a functional relation between the two phase variables Xj and x in
2
the form
g(x x ,c) = 0 (2.6)
h 2
where the constant c represents the effects of initial conditions (and, possibly, of
external input signals). Plotting this relation in the phase plane for different initial
conditions yields a phase portrait.
The first technique involves solving equations (2.1) forx[ and x as functions of
2
time t, i.e.,
and then eliminating time t from these equations, leading to a functional relation in the
form of (2.6). This technique was already illustrated in Example 2.1.
The second technique, on the other hand, involves directly eliminating the time
variable, by noting that
and then solving this equation for a functional relation between Xj and x. Let us use
2
this technique to solve the mass-spring equation again.
Example 2.4: Mass-spring system
By noting that x = (dx/dx)(dx/dt), we can rewrite (2.2) as
-v — + x = 0
dx
Integration of this equation yields
i2+x2 =x2 •
o
One sees that the second technique is more straightforward in generating the equations
for the phase plane trajectories.
Most nonlinear systems cannot be easily solved by either of the above two
techniques. However, for piece-wise linear systems, an important class of nonlinear
systems, this method can be conveniently used, as the following example shows.
L

Sect. 2.2 Constructing Phase Portraits 25
Example 2.5: A satellite control system
Figure 2.4 shows the control system for a simple satellite model. The satellite, depicted in Figure
2.5(a), is simply a rotational unit inertia controlled by a pair of thrusters, which can provide either
a positive constant torque U (positive firing) or a negative torque — U (negative firing). The
purpose of the control system is to maintain the satellite antenna at a zero angle by appropriately
firing the thrusters. The mathematical model of the satellite is
where w is the torque provided by the thrusters and 8 is the satellite angle.
Jets Satellite
e d = o U'— i u 1 e i
-u p p
Figure 2.4 : Satellite control system
Let us examine on the phase plane the behavior of the control system when the thrusters are
fired according to the control law
u(t) = /- U if 9 > 0 (2.7)
w 1 u if e < o
which means that the thrusters push in the counterclockwise direction if G is positive, and vice
versa.
As the first step of the phase portrait generation, let us consider the phase portrait when the
thrusters provide a positive torque U. The dynamics of the system is
which implies that 6 dQ = U dQ. Therefore, the phase trajectories are a family of parabolas
defined by
where c is a constant. The corresponding phase portrait of the system is shown in Figure 2.5(b).
f
When the thrusters provide a negative torque - U, the phase trajectories are similarly found
to be

26 Phase Plane Analysis Chap. 2
u = -U
(a) (b) (c)
Figure 2.5 : Satellite control using on-off thrusters
with the corresponding phase portrait shown in Figure 2.5(c).
parabolic
trajectories
u = +U
switching line
Figure 2.6 : Complete phase portrait of the control system
The complete phase portrait of the closed-loop control system can be obtained simply by
connecting the trajectories on the left half of the phase plane in 2.5(b) with those on the right half
of the phase plane in 2.5(c), as shown in Figure 2.6. The vertical axis represents a switching line,
because the control input and thus the phase trajectories are switched on that line. It is interesting
to see that, starting from a nonzero initial angle, the satellite will oscillate in periodic motions
i

Sect. 2.2 Constructing Phase Portraits 27
under the action of the jets. One concludes from this phase portrait that the system is marginally
stable, similarly to the mass-spring system in Example 2.1. Convergence of the system to the
zero angle can be obtained by adding rate feedback (Exercise 2.4). [3
THE METHOD OF ISOCLINES
The basic idea in this method is that of isoclines. Consider the dynamics in (2.1). At a
point (JCJ , x ) in the phase plane, the slope of the tangent to the trajectory can be
2
determined by (2.5). An isocline is defined to be the locus of the points with a given
tangent slope. An isocline with slope a is thus defined to be
dx _f (x x ) _
2 2 h 2
dx f(x,x)
x l l 2
This is to say that points on the curve
all have the same tangent slope a.
In the method of isoclines, the phase portrait of a system is generated in two
steps. In the first step, a field of directions of tangents to the trajectories is obtained. In
the second step, phase plane trajectories are formed from the field of directions .
Let us explain the isocline method on the mass-spring system in (2.2). The
slope of the trajectories is easily seen to be
dx X\
2
dx\ x
2
Therefore, the isocline equation for a slope a is
X| + ax =0
2
i.e., a straight line. Along the line, we can draw a lot of short line segments with slope
a. By taking a to be different values, a set of isoclines can be drawn, and a field of
directions of tangents to trajectories are generated, as shown in Figure 2.7. To obtain
trajectories from the field of directions, we assume that the the tangent slopes are
locally constant. Therefore, a trajectory starting from any point in the plane can be
found by connecting a sequence of line segments.
Let us use the method of isoclines to study the Van der Pol equation, a
nonlinear equation.

28 Phase Plane Analysis Chap. 2
Figure 2.7 : Isoclines for the mass-spring
system
Example 2.6: The Van der Pol equation
For the Van der Pol equation
an isocline of slope a is defined by
dx_0.2(x2- \)x + x
Therefore, the points on the curve
0.2(x2- \)x + x + ax = 0
all have the same slope a.
By taking a of different values, different isoclines can be obtained, as plotted in Figure 2.8.
Short line segments are drawn on the isoclines to generate a field of tangent directions. The phase
portraits can then be obtained, as shown in the plot. It is interesting to note that there exists a
closed curve in the portrait, and the trajectories starting from both outside and inside converge to
this curve. This closed curve corresponds to a limit cycle, as will be discussed further in section
2.5. •
Note that the same scales should be used for the xj axis and Xj axis of the phase
plane, so that the derivative dx^dx-^ equals the geometric slope of the trajectories.
Also note that, since in the second step of phase portrait construction we essentially
assume that the slope of the phase plane trajectories is locally constant, more isoclines
should be plotted in regions where the slope varies quickly, to improve accuracy.

Sect. 2.3 Determining Time from Phase Portraits 29
a = -5
a=l
trajectory
isoclines
Figure 2.8 : Phase portrait of the Van der Pol equation
2.3 Determining Time from Phase Portraits
Note that time t does not explicitly appear in the phase plane having Xy and x as
2
coordinates. However, in some cases, we might be interested in the time information.
For example, one might want to know the time history of the system states starting
from a specific initial point. Another relevant situation is when one wants to know
how long it takes for the system to move from a point to another point in a phase plane
trajectory. We now describe two techniques for computing time history from phase
portraits. Both techniques involve a step-by step procedure for recovering time.
Obtaining time from At~Ax/x
In a short time At, the change of x is approximately
Ax ~ xAt (2.8)
where x is the velocity corresponding to the increment Ax. Note that for a Ax of finite
magnitude, the average value of velocity during a time increment should be used to
improve accuracy. From (2.8), the length of time corresponding to the increment Ax

30 Phase Plane Analysis Chap. 2
is
The above reasoning implies that, in order to obtain the time corresponding to the
motion from one point to another point along a trajectory, one should divide the
corresponding part of the trajectory into a number of small segments (not necessarily
equally spaced), find the time associated with each segment, and then add up the
results. To obtain the time history of states corresponding to a certain initial
condition, one simply computes the time t for each point on the phase trajectory, and
then plots x with respect to t and x with respect to t,
Obtaining time from t = f (1/i) dx
Since x = dx/dt, we can write dt - dx/x. Therefore,
where x corresponds to time t and x corresponds to time t . This equation implies
o 0
that, if we plot a phase plane portrait with new coordinates x and (1/i), then the area
under the resulting curve is the corresponding time interval.
2.4 Phase Plane Analysis of Linear Systems
In this section, we describe the phase plane analysis of linear systems. Besides
allowing us to visually observe the motion patterns of linear systems, this will also
help the development of nonlinear system analysis in the next section, because a
nonlinear systems behaves similarly to a linear system around each equilibrium point.
The general form of a linear second-order system is
x=ax+ bx (2.9a)
l r 2
k = cx+dx (2.9b)
2 i 2
To facilitate later discussions, let us transform this equation into a scalar second-order
differential equation. Note from (2.9a) and (2.9b) that
b k = b cx\ + d(x\ — axj)
2
Consequently, differentiation of (2.9a) and then substitution of (2.9b) leads to

Sect. 2.4 Phase Plane Analysis of Linear Systems 31
Xj = (a +d)X\ + (cb - ad)xi
Therefore, we will simply consider the second-order linear system described by
x + ax + bx = 0 (2.10)
To obtain the phase portrait of this linear system, we first solve for the time
history
x(t) = kexit + k el2> forX,*^ (2.11a)
l 2 2
x(t) = kexi' + k tehl for X = X^ (2.11b)
l 2 {
where the constants X\ and X are the solutions of the characteristic equation
2
s2 + as + b = (s - A,j) (s - Xj) =0
The roots A,j and ^> can be explicitly represented as
For linear systems described by (2.10), there is only one singular point (assuming
b & 0), namely the origin. However, the trajectories in the vicinity of this singularity
point can display quite different characteristics, depending on the values of a and b.
The following cases can occur
1. ^.j and Xj are both real and have the same sign (positive or negative)
2. X\ and Xj are both real and have opposite signs
3. A,j and X are complex conjugate with non-zero real parts
2
4. X{ and X are complex conjugates with real parts equal to zero
2
We now briefly discuss each of the above four cases.
STABLE OR UNSTABLE NODE
The first case corresponds to a node. A node can be stable or unstable. If the
eigenvalues are negative, the singularity point is called a stable node because both x(f)
and x(t) converge to zero exponentially, as shown in Figure 2.9(a). If both
eigenvalues are positive, the point is called an unstable node, because both x(t) and
x{t) diverge from zero exponentially, as shown in Figure 2.9(b). Since the eigenvalues
are real, there is no oscillation in the trajectories.

32 Phase Plane Analysis Chap. 2
SADDLE POINT
The second case (say X^ < 0 and A^ > 0) corresponds to a saddle point (Figure 2.9(c)).
The phase portrait of the system has the interesting "saddle" shape shown in Figure
2.9(c). Because of the unstable pole Xj , almost all of the system trajectories diverge
to infinity. In this figure, one also observes two straight lines passing through the
origin. The diverging line (with arrows pointing to infinity) corresponds to initial
conditions which make £ (i.e., the unstable component) equal zero. The converging
2
straight line corresponds to initial conditions which make k equal zero.
l
STABLE OR UNSTABLE FOCUS
The third case corresponds to a focus. A stable focus occurs when the real part of the
eigenvalues is negative, which implies that x(t) and x(t) both converge to zero. The
system trajectories in the vicinity of a stable focus are depicted in Figure 2.9(d). Note
that the trajectories encircle the origin one or more times before converging to it,
unlike the situation for a stable node. If the real part of the eigenvalues is positive,
then x(t) and x(t) both diverge to infinity, and the singularity point is called an
unstable focus. The trajectories corresponding to an unstable focus are sketched in
Figure 2.9(e).
CENTER POINT
The last case corresponds to a center point, as shown in Figure 2.9(f). The name
comes from the fact that all trajectories are ellipses and the singularity point is the
center of these ellipses. The phase portrait of the undamped mass-spring system
belongs to this category.
Note that the stability characteristics of linear systems are uniquely determined
by the nature of their singularity points. This, however, is not true for nonlinear
systems.
2.5 Phase Plane Analysis of Nonlinear Systems
In discussing the phase plane analysis of nonlinear systems, two points should be kept
in mind. Phase plane analysis of nonlinear systems is related to that of linear systems,
because the local behavior of a nonlinear system can be approximated by the behavior
of a linear system. Yet, nonlinear systems can display much more complicated
patterns in the phase plane, such as multiple equilibrium points and limit cycles. We
now discuss these points in more detail.

Sect. 2.5 Phase Plane Analysis of Nonlinear Systems 33
stable node 11
(a)
unstable node
X X- C7 77
(b)
saddle point
(c)
stable focus
(d)
unstable focus
x
(e)
center point
(0
Figure 2.9 : Phase-portraits of linear systems

34 Phase Plane Analysis Chap. 2
LOCAL BEHAVIOR OF NONLINEAR SYSTEMS
In the phase portrait of Figure 2.2, one notes that, in contrast to linear systems, there
are two singular points, (0,0) and (-3,0). However, we also note that the features of
the phase trajectories in the neighborhood of the two singular points look very much
like those of linear systems, with the first point corresponding to a stable focus and the
second to a saddle point. This similarity to a linear system in the local region of each
singular point can be formalized by linearizing the nonlinear system, as we now
discuss.
If the singular point of interest is not at the origin, by defining the difference
between the original state and the singular point as a new set of state variables, one
can always shift the singular point to the origin. Therefore, without loss of generality,
we may simply consider Equation (2.1) with a singular point at 0. Using Taylor
expansion, Equations (2.1a) and (2.1b) can be rewritten as
h = cxl + dx2 + 82^1'X 2>
where gj and g contain higher order terms.
2
In the vicinity of the origin, the higher order terms can be neglected, and
therefore, the nonlinear system trajectories essentially satisfy the linearized equation
JL'j = ax + bx
l 2
x = cx+dx
2 i 2
As a result, the local behavior of the nonlinear system can be approximated by the
patterns shown in Figure 2.9.
LIMIT CYCLES
m the phase portrait of the nonlinear Van der Pol equation, shown in Figure 2.8, one
observes that the system has an unstable node at the origin. Furthermore, there is a
closed curve in the phase portrait. Trajectories inside the curve and those outside the
curve all tend to this curve, while a motion started on this curve will stay on it forever,
circling periodically around the origin. This curve is an instance of the so-called
"limit cycle" phenomenon. Limit cycles are unique features of nonlinear systems.
In the phase plane, a limit cycle is defined as an isolated closed curve. The
trajectory has to be both closed, indicating the periodic nature of the motion, and
isolated, indicating the limiting nature of the cycle (with nearby trajectories

| Sect. 2.5 |     |     | Phase Plane Analysis of Nonlinear Systems  |     |     | 35  |
| --------- | --- | --- | ------------------------------------------ | --- | --- | --- |
converging or diverging from it).  Thus, while there are many closed curves in the
phase portraits of the mass-spring-damper  system in Example 2.1 or the satellite
system in Example 2.5, these are not considered limit cycles in this definition, because
they are not isolated.
Depending on the motion patterns of the trajectories in the vicinity of the limit
cycle, one can distinguish three kinds of limit cycles
1. Stable Limit Cycles: all trajectories in the vicinity of the limit cycle
converge to it as t —> °° (Figure 2.10(a));
2. Unstable Limit Cycles: all trajectories in the vicinity of the limit cycle
diverge from it as t -> °° (Figure 2.10(b));
3. Semi-Stable  Limit  Cycles: some of  the trajectories  in  the  vicinity
converge  to it,  while the others diverge  from  it  as r —» °°  (Figure
2  diverging
diverging
converging
|     | (a)  |     | (b)  | (c) |     |     |
| --- | ---- | --- | ---- | --- | --- | --- |
Figure 2.10 : Stable, unstable, and semi-stable limit cycles
As seen from the phase portrait of Figure 2.8, the limit cycle of the Van der Pol
equation  is  clearly  stable.  Let  us  consider  some  additional  examples  of  stable,
unstable, and semi-stable limit cycles.
Example 2.7: stable, unstable, and semi-stable limit cycles
Consider the following nonlinear systems
|     | (a) | =x -x (x |     |              |       |        |
| --- | --- | -------- | --- | ------------ | ----- | ------ |
|     |     | l 2 x    | l   | -x 2 (xf + x | 2 --  | (2.12) |
|     | (b) |          |     | +x (x,2  x   | 2- 1) | (2.13) |
|     |     | X,=J     |     | 2 +          | 2     |        |
(x,2
|     | (c) |     | -  I)2 | -x + x | 2- I)2 | (2.14) |
| --- | --- | --- | ------ | ------ | ------ | ------ |
|     |     |     |        | 2      | 2      |        |

36 Phase Plane Analysis Chap. 2
Let us study system (a) first. By introducing polar coordinates
/• = (x2 + x2)1/2 9 = tan-1(jc/x)
1 2 2 1
the dynamic equations (2.12) are transformed as
dr , , ,. d<d
T<=-r(r-l) Tr-X
When the state starts on the unit circle, the above equation shows that r(t) = 0. Therefore, the state
will circle around the origin with a period 1/2K. When r < 1, then r > 0. This implies that the state
tends to the circle from inside. When r > 1, then /• < 0. This implies that the state tends toward
the unit circle from outside. Therefore, the unit circle is a stable limit cycle. This can also be
concluded by examining the analytical solution of (2.12)
r(t) = 1 6(0 = Qn - 1
(l+ce-2')1/2
o
where
Similarly, one can find that the system (b) has an unstable limit cycle and system (c) has a semi-
stable limit cycle. Q
2.6 Existence of Limit Cycles
As mentioned in chapter 1, it is of great importance for control engineers to predict the
existence of limit cycles in control systems. In this section, we state three simple
classical theorems to that effect. These theorems are easy to understand and apply.
The first theorem to be presented reveals a simple relationship between the
existence of a limit cycle and the number of singular points it encloses. In the
statement of the theorem, we use N to represent the number of nodes, centers, and foci
enclosed by a limit cycle, and S to represent the number of enclosed saddle points.
Theorem 2.1 (Poincare) // a limit cycle exists in the second-order autonomous
system (2.1), then N = S + 1 .
This theorem is sometimes called the index theorem. Its proof is mathematically
involved (actually, a family of such proofs led to the development of algebraic
topology) and shall be omitted here. One simple inference from this theorem is that a
limit cycle must enclose at least one equilibrium point. The theorem's result can be

Sect. 2.6 Existence of Limit Cycles 37
verified easily on Figures 2.8 and 2.10.
The second theorem is concerned with the asymptotic properties of the
trajectories of second-order systems.
Theorem 2.2 (Poincare-Bendixson) If a trajectory of the second-order
autonomous system remains in a finite region Q, then one of the following is true:
(a) the trajectory goes to an equilibrium point
(b) the trajectory tends to an asymptotically stable limit cycle
(c) the trajectory is itself a limit cycle
While the proof of this theorem is also omitted here, its intuitive basis is easy to see,
and can be verified on the previous phase portraits.
The third theorem provides a sufficient condition for the non-existence of limit
cycles.
Theorem 2.3 (Bendixson) For the nonlinear system (2.1), no limit cycle can exist
in a region Q. of the phase plane in which 3/j /3xj + 3/ /3.X2 does not vanish and
2
does not change sign.
Proof: Let us prove this theorem by contradiction. First note that, from (2.5), the equation
0 (2.15)
is satisfied for any system trajectories, including a limit cycle. Thus, along the closed curve L of
a limit cycle, we have
f (/,rfjc-/rfx-> = 0 (2.16)
2 2 1
Using Stokes' Theorem in calculus, we have
where the integration on the right-hand side is carried out on the area enclosed by the limit cycle.
By Equation (2.16), the left-hand side must equal zero. This, however, contradicts the fact
that the right-hand side cannot equal zero because by hypothesis 3/j/3xj +3//3x2 does not
2
vanish and does not change sign. El
Let us illustrate the result on an example.

38 Phase Plane Analysis Chap. 2
Example 2.8: Consider the nonlinear system
x =
2
Since
which is always strictly positive (except at the origin), the system does not have any limit cycles
anywhere in the phase plane. . \3
The above three theorems represent very powerful results. It is important to
notice, however, that they have no equivalent in higher-order systems, where exotic
asymptotic behaviors other than equilibrium points and limit cycles can occur.
2.7 Summary
Phase plane analysis is a graphical method used to study second-order dynamic
systems. The major advantage of the method is that it allows visual examination of the
global behavior of systems. The major disadvantage is that it is mainly limited to
second-order systems (although extensions to third-order systems are often achieved
with the aid of computer graphics). The phenomena of multiple equilibrium points and
of limit cycles are clearly seen in phase plane analysis. A number of useful classical
theorems for the prediction of limit cycles in second-order systems are also presented.
2.8 Notes and References
Phase plane analysis is a very classical topic which has been addressed by numerous control texts.
An extensive treatment can be found in [Graham and McRuer, 1961]. Examples 2.2 and 2.3 are
adapted from [Ogata, 1970]. Examples 2.5 and 2.6 and section 2.6 are based on [Hsu and Meyer,
1968].
2.9 Exercises
2.1 Draw the phase portrait and discuss the properties of the linear, unity feedback control system
of open-loop transfer function
10

Sect. 2.9 Exercises 39
2.2 Draw the phase portraits of the following systems, using isoclines
(a) e + e + 0.5 e = o
(b) e + e + o.5 e = i
2.3 Consider the nonlinear system
x = y + x(x* + yl- 1) sin
y = - x + y (x2 + y2 - 1) sin
Without solving the above equations explicitly, show that the system has infinite number of limit
cycles. Determine the stability of these limit cycles. (Hint: Use polar coordinates.)
2.4 The system shown in Figure 2.10 represents a satellite control system with rate feedback
provided by a gyroscope. Draw the phase portrait of the system, and determine the system's
stability.
u
1
p + a -1 '
P1
Figure 2.10 : Satellite control system with rate feedback

Chapter 3
Fundamentals of Lyapunov Theory
Given a control system, the first and most important question about its various
properties is whether it is stable, because an unstable control system is typically
useless and potentially dangerous. Qualitatively, a system is described as stable if
starting the system somewhere near its desired operating point implies that it will stay
around the point ever after. The motions of a pendulum starting near its two
equilibrium points, namely, the vertical up and down positions, are frequently used to
illustrate unstable and stable behavior of a dynamic system. For aircraft control
systems, a typical stability problem is intuitively related to the following question:
will a trajectory perturbation due to a gust cause a significant deviation in the later
flight trajectory? Here, the desired operating point of the system is the flight
trajectory in the absence of disturbance. Every control system, whether linear or
nonlinear, involves a stability problem which should be carefully studied.
The most useful and general approach for studying the stability of nonlinear
control systems is the theory introduced in the late 19th century by the Russian
mathematician Alexandr Mikhailovich Lyapunov. Lyapunov's work, The General
Problem of Motion Stability, includes two methods for stability analysis (the so-called
linearization method and direct method) and was first published in 1892. The
linearization method draws conclusions about a nonlinear system's local stability
around an equilibrium point from the stability properties of its linear approximation.
The direct method is not restricted to local motion, and determines the stability
properties of a nonlinear system by constructing a scalar "energy-like" function for the
system and examining the function's time variation. For over half a century, however,
40

Sect. 3.1 Nonlinear Systems and Equilibrium Points 41
Lyapunov's pioneering work on stability received little attention outside Russia,
although it was translated into French in 1908 (at the instigation of Poincare), and
reprinted by Princeton University Press in 1947. The publication of the work of Lur'e
and a book by La Salle and Lefschetz brought Lyapunov's work to the attention of the
larger control engineering community in the early 1960's. Many refinements of
Lyapunov's methods have since been developed. Today, Lyapunov's linearization
method has come to represent the theoretical justification of linear control, while
Lyapunov's direct method has become the most important tool for nonlinear system
analysis and design. Together, the linearization method and the direct method
constitute the so-called Lyapunov stability theory.
The objective of this and the next chapter is to present Lyapunov stability
theory and illustrate its use in the analysis and the design of nonlinear systems. To
prevent mathematical complexity from obscuring the theoretical concepts, this chapter
presents the most basic results of Lyapunov theory in terms of autonomous {i.e., time-
invariant) systems, leaving more advanced topics to chapter 4. This chapter is
organized as follows. In section 3.1, we provide some background definitions
concerning nonlinear systems and equilibrium points. In section 3.2, various concepts
of stability are described to characterize different aspects of system behavior.
Lyapunov's linearization method is presented in section 3.3. The most useful theorems
in the direct method are studied in section 3.4. Section 3.5 is devoted to the question
of how to use these theorems to study the stability of particular classes of nonlinear
systems. Section 3.6 sketches how the direct method can be used as a powerful way
of designing controllers for nonlinear systems.
3.1 Nonlinear Systems and Equilibrium Points
Before addressing the main problems of defining and determining stability in the next
sections, let us discuss some relatively simple background issues.
NONLINEAR SYSTEMS
A nonlinear dynamic system can usually be represented by a set of nonlinear
differential equations in the form
x = f(x,r) (3.1)
where f is a «xl nonlinear vector function, and x is the nxl state vector. A particular
value of the state vector is also called a point because it corresponds to a point in the
state-space. The number of states n is called the order of the system. A solution x(0
of the equations (3.1) usually corresponds to a curve in state space as t varies from

I
42 Fundamentals ofLyapunov Theory Chap. 3
zero to infinity, as already seen in phase plane analysis for the case n = 2. This curve is
generally referred to as a state trajectory or a system trajectory.
It is important to note that although equation (3.1) does not explicitly contain
the control input as a variable, it is directly applicable to feedback control systems.
The reason is that equation (3.1) can represent the closed-loop dynamics of a feedback
control system, with the control input being a function of state x and time /, and
therefore disappearing in the closed-loop dynamics. Specifically, if the plant dynamics
x = f(x, u,0
and some control law has been selected
u = g(x, t)
then the closed-loop dynamics is
x = f[x,g(x,r),r]
which can be rewritten in the form (3.1). Of course, equation (3.1) can also represent
dynamic systems where no control signals are involved, such as a freely swinging
pendulum.
A special class of nonlinear systems are linear systems. The dynamics of linear
systems are of the form
i = A(f)x
where A(t) is an nxn matrix.
AUTONOMOUS AND NON-AUTONOMOUS SYSTEMS
Linear systems are classified as either time-varying or time-invariant, depending on
whether the system matrix A varies with time or not. In the more general context of
nonlinear systems, these adjectives are traditionally replaced by "autonomous" and
"non-autonomous".
Definition 3.1 The nonlinear system (3.1) is said to be autonomous if f does not
depend explicitly on time, i.e., if the system's state equation can be written
x = f (x) (3.2)
Otherwise, the system is called non-autonomous .
Obviously, linear time-invariant (LTI) systems are autonomous and linear time-

Sect. 3.1 Nonlinear Systems and Equilibrium Points 43
varying (LTV) systems are non-autonomous. The second-order systems studied in
chapter 2 are all autonomous.
Strictly speaking, all physical systems are non-autonomous, because none of
their dynamic characteristics is strictly time-invariant. The concept of an autonomous
system is an idealized notion, like the concept of a linear system. In practice,
however, system properties often change very slowly, and we can neglect their time
variation without causing any practically meaningful error.
It is important to note that for control systems, the above definition is made on
the closed-loop dynamics. Since a control system is composed of a controller and a
plant (including sensor and actuator dynamics), the non-autonomous nature of a
control system may be due to a time-variation either in the plant or in the control law.
Specifically, a time-invariant plant with dynamics
x = f (x, u)
may lead to a non-autonomous closed-loop system if a controller dependent on time t
is chosen, i.e., if u = g(x, f). For example, the closed-loop system of the simple plant
x = - x + u can be nonlinear and non-autonomous by choosing u to be nonlinear and
time-varying (e.g., u = -x2 sin t). In fact, adaptive controllers for linear time-invariant
plants usually make the closed-loop control systems nonlinear and non-autonomous.
The fundamental difference between autonomous and non-autonomous systems
lies in the fact that the state trajectory of an autonomous system is independent of the
initial time, while that of a non-autonomous system generally is not. As we will see in
the next chapter, this difference requires us to consider the initial time explicitly in
defining stability concepts for non-autonomous systems, and makes the analysis more
difficult than that of autonomous systems.
It is well known that the analysis of linear time-invariant systems is much easier
than that of linear time-varying systems. The same is true with nonlinear systems.
Generally speaking, autonomous systems have relatively simpler properties and their
analysis is much easier. For this reason, in the remainder of this chapter, we will
concentrate on the analysis of autonomous systems, represented by (3.2). Extensions
of the concepts and results to non-autonomous systems will be studied in chapter 4.
EQUILIBRIUM POINTS
It is possible for a system trajectory to correspond to only a single point. Such a point
is called an equilibrium point. As we shall see later, many stability problems are
naturally formulated with respect to equilibrium points.

44 Fundamentals ofLyapunov Theory Chap. 3
Definition 3.2 A state x* is an equilibrium state (or equilibrium point) of the system
if once x(t) is equal to x , it remains equal to x for all future time.
Mathematically, this means that the constant vector x* satisfies
0 = f(x*) (3.3)
Equilibrium points can be found by solving the nonlinear algebraic equations (3.3).
A linear time-invariant system
x = Ax (3.4)
has a single equilibrium point (the origin 0) if A is nonsingular. If A is singular, it has
an infinity of equilibrium points, which are contained in the null-space of the matrix
A, i.e., the subspace defined by Ax = 0. This implies that the equilibrium points are
not isolated, as reflected by the example x + x = 0 , for which all points on the x axis
of the phase plane are equilibrium points.
A nonlinear system can have several (or infinitely many) isolated equilibrium
points, as seen in Example 1.1. The following example involves a familiar physical
system.
Example 3.1: The Pendulum
Consider the pendulum of Figure 3.1, whose dynamics is given by the following nonlinear
autonomous equation
MR2 8 + b 6 + MgR sin 8 = 0 (3.5)
Figure 3.1 : The pendulum

Sect. 3.1 Nonlinear Systems and Equilibrium Points 45
where R is the pendulum's length, M its mass, b the friction coefficient at the hinge, and g the
gravity constant. Letting x^ = 8 , x = 0, the corresponding state-space equation is
2
x, = x (3.6a)
2
b s
x-y = x - — sinx, (3.6b)
9
MR1 R
Therefore, the equilibrium points are given by
x = 0 , sin X| = 0
2
which leads to the points (0 [2ji], 0) and (JI [27i], 0). Physically, these points correspond to the
pendulum resting exactly at the vertical up and down positions. Q
In linear system analysis and design, for notational and analytical simplicity, we
often transform the linear system equations in such a way that the equilibrium point is
the origin of the state-space. We can do the same thing for nonlinear systems (3.2),
about a specific equilibrium point. Let us say that the equilibrium point of interest is
x*. Then, by introducing a new variable
y = x-x*
and substituting x = y + x into equations (3.2), a new set of equations on the variable
y are obtained
y = f(y+x*) (3.7)
One can easily verify that there is a one-to-one correspondence between the solutions
of (3.2) and those of (3.7), and that in addition, y=0, the solution corresponding to
x = x*, is an equilibrium point of (3.7). Therefore, instead of studying the behavior of
the equation (3.2) in the neighborhood of x*, one can equivalently study the behavior
of the equations (3.7) in the neighborhood of the origin.
NOMINAL MOTION
In some practical problems, we are not concerned with stability around an equilibrium
point, but rather with the stability of a motion, i.e, whether a system will remain close
to its original motion trajectory if slightly perturbed away from it, as exemplified by
the aircraft trajectory control problem mentioned at the beginning of this chapter. We
can show that this kind of motion stability problem can be transformed into an
equivalent stability problem around an equilibrium point, although the equivalent
system is now non-autonomous.
Let \*(t) be the solution of equation (3.2), i.e., the nominal motion trajectory,
corresponding to initial condition x*(0) = x . Let us now perturb the initial condition
0

I
46 Fundamentals of Lyapunov Theory Chap. 3
to be x(0) = x + 8x and study the associated variation of the motion error
o 0
e(f) = x(r) - x*(0
as illustrated in Figure 3.2. Since both x*(t) and x(/) are solutions of (3.2), we have
Figure 3.2 : Nominal and Perturbed Motions
x* = f (x*) x(0) = x
0
x = f (x) x(0) = x
o
then e(?) satisfies the following non-autonomous differential equation
e = f (x* + e, t) - f(x*. t) = g(e, t) (3.8)
with initial condition e(0) = 8x . Since g(0, t) = 0, the new dynamic system, with e as
0
state and g in place of f, has an equilibrium point at the origin of the state space.
Therefore, instead of studying the deviation of x(0 from x (f) for the original system,
we may simply study the stability of the perturbation dynamics (3.8) with respect to
the equilibrium point 0. Note, however, that the perturbation dynamics is non-
autonomous, due to the presence of the nominal trajectory x*(r) on the right-hand side.
Each particular nominal motion of an autonomous system corresponds to an
equivalent non-autonomous system, whose study requires the non-autonomous system
analysis techniques to be presented in chapter 4.
Let us now illustrate this important transformation on a specific system.

Sect. 3.2 Concepts of Stability 47
Example 3.2: Consider the autonomous mass-spring system
3 = 0
which contains a nonlinear term reflecting the hardening effect of the spring. Let us study the
stability of the motion x*(t) which starts from initial position x.
0
Assume that we slightly perturb the initial position to be x(0) = x + 5x. The resulting system
o 0
trajectory is denoted as x(t). Proceeding as before, the equivalent differential equation governing
the motion error e is
me + k\ e + k I e3 + 3e2x*(t) + 3ex*2(t) ] = 0
2
Clearly, this is a non-autonomous system. •
Of course, one can also show that for non-autonomous nonlinear systems, the
stability problem around a nominal motion can also be transformed as a stability
problem around the origin for an equivalent non-autonomous system.
Finally, note that if the original system is autonomous and linear, in the form
(3.4), then the equivalent system is still autonomous, since it can be written
e = Ae
3.2 Concepts of Stability
In the beginning of this chapter, we introduced the intuitive notion of stability as a
kind of well-behavedness around a desired operating point. However, since nonlinear
systems may have much more complex and exotic behavior than linear systems, the
mere notion of stability is not enough to describe the essential features of their motion.
A number of more refined stability concepts, such as asymptotic stability, exponential
stability and global asymptotic stability, are needed. In this section, we define these
stability concepts formally, for autonomous systems, and explain their practical
meanings.
A few simplifying notations are defined at this point. Let B^ denote the
spherical region (or ball) defined by || x ]| < R in state-space, and S/j the sphere itself,
defined by || x || = R.

48 Fundamentals of Lyapunov Theory Chap. 3
STABILITY AND INSTABILITY
Let us first introduce the basic concepts of stability and instability.
Definition 3.3 The equilibrium state x = 0 is said to be stable if, for any R>0, there
exists r>0, such that if ||x(0)|| < r, then ||x(f)|| <R for all t>0 . Otherwise, the
equilibrium point is unstable.
Essentially, stability (also called stability in the sense of Lyapunov, or Lyapunov
stability) means that the system trajectory can be kept arbitrarily close to the origin by
starting sufficiently close to it. More formally, the definition states that the origin is
stable, if, given that we do not want the state trajectory x(f) to get out of a ball of
arbitrarily specified radius B^ , a value r(R) can be found such that starting the state
from within the ball B,. at time 0 guarantees that the state will stay within the ball B^
thereafter. The geometrical implication of stability is indicated by curve 2 in Figure
3.3. Chapter 2 provides examples of stable equilibrium points in the case of second-
order systems, such as the origin for the mass-spring system of Example 2.1, or stable
nodes or foci in the local linearization of a nonlinear system.
Throughout the book, we shall use the standard mathematical abbreviation
symbols:
V to mean "for any"
3 for "there exists"
e for "in the set"
=> for "implies that"
Of course, we shall say interchangeably that A implies B, or that A is a sufficient
condition of B, or that B is a necessary condition of A. If A => B and B => A ,
then A and B are equivalent, which we shall denote by A <=> B .
Using these symbols, Definition 3.3 can be written
VR>0,3r>0, || x(0) \\<r => V t > 0 , || x(f) || < R
or, equivalently
Vtf>0,3r>0, x(0) e B => V t > 0 , x(t) e B
r R
Conversely, an equilibrium point is unstable if there exists at least one ball B^,
such that for every r>0, no matter how small, it is always possible for the system
trajectory to start somewhere within the ball B and eventually leave the ball B
r R
(Figure 3.3). Unstable nodes or saddle points in second-order systems are examples of
unstable equilibria. Instability of an equilibrium point is typically undesirable, because

Sect. 3.2 Concepts of Stability 49
it often leads the system into limit cycles or results in damage to the involved
mechanical or electrical components.
curve 1 - asymptotically stable
curve 2 - marginally stable
curve 3 - unstable
Figure 3.3 : Concepts of stability
It is important to point out the qualitative difference between instability and the
intuitive notion of "blowing up" (all trajectories close to origin move further and
further away to infinity). In linear systems, instability is equivalent to blowing up,
because unstable poles always lead to exponential growth of the system states.
However, for nonlinear systems, blowing up is only one way of instability. The
following example illustrates this point.
Example 3.3: Instability of the Van der Pol Oscillator
The Van der Pol oscillator of Example 2.6 is described by
One easily shows that the system has an equilibrium point at the origin.
As pointed out in section 2.2 and seen in the phase portrait of Figure 2.8, system trajectories
starting from any non-zero initial states all asymptotically approach a limit cycle. This implies
that, if we choose R in Definition 3.3 to be small enough for the circle of radius R to fall
completely within the closed-curve of the limit cycle, then system trajectories starting near the
origin will eventually get out of this circle (Figure 3.4). This implies instability of the origin.
Thus, even though the state of the system does remain around the equilibrium point in a
certain sense, it cannot stay arbitrarily close to it. This is the fundamental distinction between
stability and instability. d

50 Fundamentals of Lyapunov Theory Chap. 3
trajectories
limit
cycle
Figure 3.4 : Unstable origin of the Van der Pol Oscillator
ASYMPTOTIC STABILITY AND EXPONENTIAL STABILITY
In many engineering applications, Lyapunov stability is not enough. For example,
when a satellite's attitude is disturbed from its nominal position, we not only want the
satellite to maintain its attitude in a range determined by the magnitude of the
disturbance, i.e., Lyapunov stability, but also require that the attitude gradually go
back to its original value. This type of engineering requirement is captured by the
concept of asymptotic stability.
Definition 3.4 An equilibrium point 0 is asymptotically stable if it is stable, and if in
addition there exists some r > 0 such that || x(0) || < r implies that \{t) —> 0 as t —> °°.
Asymptotic stability means that the equilibrium is stable, and that in addition,
states started close to 0 actually converge to 0 as time t goes to infinity. Figure 3.3
shows that system trajectories starting from within the ball B,. converge to the origin.
The ball B is called a domain of attraction of the equilibrium point (while the domain
r
of attraction of the equilibrium point refers to the largest such region, i.e., to the set of
all points such that trajectories initiated at these points eventually converge to the
origin). An equilibrium point which is Lyapunov stable but not asymptotically stable
is called marginally stable.
One may question the need for the explicit stability requirement in the
definition above, in view of the second condition of state convergence to the origin.
However, it it easy to build counter-examples that show that state convergence does
not necessarily imply stability. For instance, a simple system studied by Vinograd has
trajectories of the form shown in Figure 3.5. All the trajectories starting from non-zero

Sect. 3.2 Concepts of Stability 51
initial points within the unit disk first reach the curve C before converging to the
origin. Thus, the origin is unstable in the sense of Lyapunov, despite the state
convergence. Calling such a system unstable is quite reasonable, since a curve such as
C may be outside the region where the model is valid - for instance, the subsonic and
supersonic dynamics of a high-performance aircraft are radically different, while, with
the problem under study using subsonic dynamic models, C could be in the supersonic
range.
Figure 3.5 : State convergence does not imply stability
In many engineering applications, it is still not sufficient to know that a system
will converge to the equilibrium point after infinite time. There is a need to estimate
how fast the system trajectory approaches 0. The concept of exponential stability can
be used for this purpose.
Definition 3.5 An equilibrium point 0 is exponentially stable if there exist two
strictly positive numbers a and X such that
Vf>0, ||x(?)|| < a||x(O)||e-^' 0-9)
in some ball B around the origin.
r
In words, (3.9) means that the state vector of an exponentially stable system
converges to the origin faster than an exponential function. The positive number X is
often called the rate of exponential convergence. For instance, the system
x = -(1 + sin2*) x
is exponentially convergent to x = 0 with a rate X = 1 . Indeed, its solution is

52 Fundamentals ofLyapunov Theory Chap. 3
x(t) = x(0) exp(- ['[ 1 + sin2(jc(x))] dx)
and therefore
\x(0)\e-<
Note that exponential stability implies asymptotic stability. But asymptotic
stability does not guarantee exponential stability, as can be seen from the system
x = -x2, 40) =1 (3.10)
whose solution is x = 1/(1 + t), a function slower than any exponential function e~^f
(with X > 0).
The definition of exponential convergence provides an explicit bound on the
state at any time, as seen in (3.9). By writing the positive constant a as a = e^xo , it is
easy to see that, after a time of x + (l/X), the magnitude of the state vector decreases
o
to less than 35% ( ~ e~ ' ) of its original value, similarly to the notion of time-constant
in a linear system. After \ + (3/X.), the state magnitude ||x(r)|| will be less than
0
5% ( = e-3 )of
LOCAL AND GLOBAL STABILITY
The above definitions are formulated to characterize the local behavior of systems,
i.e., how the state evolves after starting near the equilibrium point. Local properties
tell little about how the system will behave when the initial state is some distance
away from the equilibrium, as seen for the nonlinear system in Example 1.1. Global
concepts are required for this purpose.
Definition 3.6 If asymptotic (or exponential) stability holds for any initial states, the
equilibrium point is said to be asymptotically (or exponentially) stable in the large. It
is also called globally asymptotically (or exponentially) stable.
For instance, in Example 1.2 the linearized system is globally asymptotically
stable, but the original system is not. The simple system in (3.10) is also globally
asymptotically stable, as can be seen from its solutions.
Linear time-invariant systems are either asymptotically stable, or marginally
stable, or unstable, as can be be seen from the modal decomposition of linear system
solutions; linear asymptotic stability is always global and exponential, and linear
instability always implies exponential blow-up. This explains why the refined notions
of stability introduced here were not previously encountered in the study of linear
1
systems. They are explicitly needed only for nonlinear systems.

Sect. 3.3 Linearization and Local Stability 53
3.3 Linearization and Local Stability
Lyapunov's linearization method is concerned with the local stability of a nonlinear
system. It is a formalization of the intuition that a nonlinear system should behave
similarly to its linearized approximation for small range motions. Because all physical
systems are inherently nonlinear, Lyapunov's linearization method serves as the
fundamental justification of using linear control techniques in practice, i.e., shows that
stable design by linear control guarantees the stability of the original physical system
locally.
Consider the autonomous system in (3.2), and assume that f(x) is continuously
differentiable. Then the system dynamics can be written as
where f stands for higher-order terms in x. Note that the above Taylor expansion
h 01
starts directly with the first-order term, due to the fact that f(0) = 0, since 0 is an
equilibrium point. Let us use the constant matrix A to denote the Jacobian matrix of f
with respect to x at x = 0 (an nx n matrix of elements 3/j- / dxj)
Then, the system
x = Ax (3.12)
is called the linearization (or linear approximation) of the original nonlinear system at
the equilibrium point 0.
Note that, similarly, starting with a non-autonomous nonlinear system with a control input u
x = f(x, u)
such that f(0, 0) = 0 , we can write
x = ( — ) x + ( — ) u + f (x, u)
h o t
V9x/(=0,u=0) V3u/(=0,u = 0)
x x
where f stands for higher-order terms in x and u. Letting A denote the Jacobian matrix of f with
h n t
respect to x at (x = 0, u = 0), and B denote the Jacobian matrix of f with respect to u at the same
point (annxm matrix of elements df I duj , where m is the number of inputs)
t

54  Fundamentals of Lyapunov Theory  Chap. 3
|     | '(x=O,u=O)  | vdu/( o,u=O) |
| --- | ----------- | ------------ |
x=
the system
x = Ax  + B u
is the linearization (or linear approximation) of the original nonlinear system at (x = 0, u = 0).
Furthermore, the choice of a control law of the form u = u(x) (with u(0) = 0 ) transforms the
original  non-autonomous  system  into an autonomous  closed-loop  system, having  x = 0 as an
equilibrium point. Linearly approximating the control law as
| ^   | x = Gx |     |
| --- | ------ | --- |
the closed-loop dynamics can be linearly approximated as
| x = f(x,u(x))  | « (A + BG)x |     |
| -------------- | ----------- | --- |
Of course, the same linear approximation can be obtained by directly considering the autonomous
closed-loop system
x = f(x, u(x)) = f,(x)
and linearizing the function f | with respect to x, at its equilibrium point x = 0.
In practice, finding a system's linearization is often most easily done simply by
neglecting any term of order higher than 1 in the dynamics, as we now illustrate.
Example 3.4: Consider the system
| x\  ~ X22 + x\          | cos;t2      |     |
| ----------------------- | ----------- | --- |
| x = x + (x + l)x+x  2 2 | { l l sin x | 2   |
Its linearized approximation about x = 0 is
i|  = 0 + Xj • 1 = Jtj
| X2 ~ X2 + 0 + x\  | +x\  X2 ~ X2 +  | x\  |
| ----------------- | --------------- | --- |
The linearized system can thus be written
1  0
| x =  | x   |     |
| ---- | --- | --- |
1  1

Sect. 3.3 Linearization and Local Stability 55
A similar procedure can be applied for a controlled system. Consider the system
x + 4xs + (x2 + 1) w = 0
The system can be linearly approximated about x = 0 as
i.e., the linearized system can be written
x = -u
Assume that the control law for the original nonlinear system has been selected to be
u = sinx + x3+xcos2x
then the linearized closed-loop dynamics is
The following result makes precise the relationship between the stability of the
linear system (3.12) and that of the original nonlinear system (3.2).
Theorem 3.1 (Lyapunov's linearization method)
• // the linearized system is strictly stable (i.e, if all eigenvalues of A are
strictly in the left-half complex plane), then the equilibrium point is
asymptotically stable (for the actual nonlinear system).
• If the linearized system is unstable (i.e, if at least one eigenvalue of A is
strictly in the right-half complex plane), then the equilibrium point is unstable
(for the nonlinear system).
• If the linearized system is marginally stable (i.e, all eigenvalues of A are in
the left-half complex plane, but at least one of them is on the /co axis), then
one cannot conclude anything from the linear approximation (the equilibrium
point may be stable, asymptotically stable, or unstable for the nonlinear
system).
While the proof of this theorem (which is actually based on Lyapunov's direct
method, see Exercise 3.12) shall not be detailed, let us remark that its results are
intuitive. A summary of the theorem is that it is true by continuity. If the linearized
system is strictly stable, or strictly unstable, then, since the approximation is valid "not
too far" from the equilibrium, the nonlinear system itself is locally stable, or locally
unstable. However, if the linearized system is marginally stable, the higher-order
terms in (3.11) can have a decisive effect on whether the nonlinear system is stable or

I
56 Fundamentals of Lyapunov Theory Chap. 3
unstable. As we shall see in the next section, simple nonlinear systems may be
globally asymptotically stable while their linear approximations are only marginally
stable: one simply cannot infer any stability property of a nonlinear system from its
marginally stable linear approximation.
Example 3.5: As expected, it can be shown easily that the equilibrium points (8 = n [2n] ,9 = 0)
of the pendulum of Example 3.1 are unstable. Consider for instance the equilibrium point
(9 = 7t, 6 = 0). Since, in a neighborhood of 6 = 7t, we can write
sin 6 = sin 7t + cos n (6 — n) + h.o.t. = (7t — 8) + h.o.t.
thus, letting 8 = 6 - TC , the system's linearization about the equilibrium point (9 = n , 8 = 0) is
H- b s _ £ § =o
MR2
Hence the linear approximation is unstable, and therefore so is the nonlinear system at this
equilibrium point. LJ
Example 3.6: Consider the first order system
The origin 0 is one of the two equilibrium points of this system. The linearization of this system
around the origin is
The application of Lyapunov's linearization method indicates the following stability properties of
the nonlinear system
• a < 0 : asymptotically stable;
• a > 0 : unstable;
• o = 0: cannot tell from linearization.
In the third case,, the nonlinear system is
x = bx5
The linearization method fails while, as we shall see, the direct method to be described can easily
solve this problem. CD

Sect. 3.4 Lyapunov's Direct Method 57
Lyapunov's linearization theorem shows that linear control design is a matter of
consistency: one must design a controller such that the system remain in its "linear
range". It also stresses major limitations of linear design: how large is the linear
range? What is the extent of stability (how large is r in Definition 3.3) ? These
questions motivate a deeper approach to the nonlinear control problem, Lyapunov's
direct method.
3.4 Lyapunov's Direct Method
The basic philosophy of Lyapunov's direct method is the mathematical extension of a
fundamental physical observation: if the total energy of a mechanical (or electrical)
system is continuously dissipated, then the system, whether linear or nonlinear, must
eventually settle down to an equilibrium point. Thus, we may conclude the stability of
a system by examining the variation of a single scalar function.
Specifically, let us consider the nonlinear mass-damper-spring system in Figure
3.6, whose dynamic equation is
= 0 (3.13)
with bx\x\ representing nonlinear dissipation or damping, and (k x +
o
representing a nonlinear spring term. Assume that the mass is pulled away from the
natural length of the spring by a large distance, and then released. Will the resulting
motion be stable? It is very difficult to answer this question using the definitions of
stability, because the general solution of this nonlinear equation is unavailable. The
linearization method cannot be used either because the motion starts outside the linear
range (and in any case the system's linear approximation is only marginally stable).
However, examination of the system energy can tell us a lot about the motion pattern.
nonlinear
spring and
p damper
x Figure 3.6 : A nonlinear mass-damper-
spring system
The total mechanical energy of the system is the sum of its kinetic energy and
its potential energy

58 Fundamentals ofLyapunov Theory Chap. 3
V(x) =- mx2 + \"(k x + kx3) dx = -m'x2 + -k x2+]-kxA (3.14)
o { 0 x
Z J o L 2. <\
Comparing the definitions of stability and mechanical energy, one can easily see some
relations between the mechanical energy and the stability concepfs described earlier:
• zero energy corresponds to the equilibrium point (x = 0, x = 0)
• asymptotic stability implies the convergence of mechanical energy to zero
• instability is related to the growth of mechanical energy
These relations indicate that the value of a scalar quantity, the mechanical energy,
indirectly reflects the magnitude of the state vector; and furthermore, that the stability
properties of the system can be characterized by the variation of the mechanical
energy of the system.
The rate of energy variation during the system's motion is obtained easily by
differentiating the first equality in (3.14) and using (3.13)
V(x) = mxx + (k x + k x3) x = x (-6x1x1) = -fclxl3 (3.15)
o x
Equation (3.15) implies that the energy of the system, starting from some initial value,
is continuously dissipated by the damper until the mass settles down, i.e., until x = 0.
Physically, it is easy to see that the mass must finally settle down at the natural length
of the spring, because it is subjected to a non-zero spring force at any position other
than the natural length.
The direct method of Lyapunov is based on a generalization of the concepts in
the above mass-spring-damper system to more complex systems. Faced with a set of
nonlinear differential equations, the basic procedure of Lyapunov's direct method is to
generate a scalar "energy-like" function for the dynamic system, and examine the time
variation of that scalar function. In this way, conclusions may be drawn on the
stability of the set of differential equations without using the difficult stability
definitions or requiring explicit knowledge of solutions.
3.4.1 Positive Definite Functions and Lyapunov Functions
The energy function in (3.14) has two properties. The first is a property of the function
itself: it is strictly positive unless both state variables x and x are zero. The second
property is a property associated with the dynamics (3.13): the function is
monotonically decreasing when the variables x and x vary according to (3.13). In
Lyapunov's direct method, the first property is formalized by the notion of positive
definite functions, and the second is formalized by the so-called Lyapunov functions.

Sect. 3.4 Lyapunov's Direct Method 59
Let us discuss positive definite functions first.
Definition 3.7 A scalar continuous function V(x) is said to be locally positive
definite ifV(0) = 0 and, in a ball B
R
x jt 0 => V(x) > 0
//V(0) = 0 and the above property holds over the whole state space, then V{\) is said
to be globally positive definite.
For instance, the function
V(x) = ~MR2x 2 + MRgil-cosx^
2
which is the mechanical energy of the pendulum of Example 3.1, is locally positive
definite. The mechanical energy (3.14) of the nonlinear mass-damper-spring system is
globally positive definite. Note that, for that system, the kinetic energy (1/2) m'x2 is
not positive definite by itself, because it can equal zero for non-zero values of X
The above definition implies that the function V has a unique minimum at the
origin 0. Actually, given any function having a unique minimum in a certain ball, we
can construct a locally positive definite function simply by adding a constant to that
function. For example, the function V(x) = x2 + x 2 - 1 is a lower bounded function
2
with a unique minimum at the origin, and the addition of the constant 1 to it makes it a
positive definite function. Of course, the function shifted by a constant has the same
time-derivative as the original function.
Let us describe the geometrical meaning of locally positive definite functions.
Consider a positive definite function V(x) of two state variables Xj and x . Plotted in a
2
3-dimensional space, V(x) typically corresponds to a surface looking like an upward
cup (Figure 3.7). The lowest point of the cup is located at the origin.
A second geometrical representation can be made as follows. Taking Xj and x
2
as Cartesian coordinates, the level curves V(x\,xj) = V typically represent a set of
a
ovals surrounding the origin, with each oval corresponding to a positive value of V .
a
These ovals, often called contour curves, may be thought as the sections of the cup by
horizontal planes, projected on the (xj, x ) plane (Figure 3.8). Note that the contour
2
curves do not intersect, because V(x, x ) is uniquely defined given (xj , x ).
t 2 2
A few related concepts can be defined similarly, in a local or global sense, i.e., a
function V(x) is negative definite if — V(x) is positive definite; V(x) is positive
semi-definite if V(0) = 0 and V(x) > 0 for x * 0; V(x) is negative semi-definite if - V(x)
is positive semi-definite. The prefix "semi" is used to reflect the possibility of V being

60 Fundamentals of Lyapunov Theory Chap. 3
v=vl
V2> \
Figure 3.7 : Typical shape of a positive definite function V(JCJ,
equal to zero for x ^ 0. These concepts can be given geometrical meanings similar to
the ones given for positive definite functions.
With x denoting the state of the system (3.2), a scalar function V(x) actually
represents an implicit function of time t. Assuming that V(x) is differentiable, its
derivative with respect to time can be found by the chain rule,
,-, dV(x) 3 V . 9 y,,
V = ^ = — x = — tf(x)
dt 33
x
33 x
V=
Figure 3.8 : Interpreting positive definite functions using contour curves

Sect. 3.4 Lyapunov's Direct Method 61
We see that, because x is required to satisfy the autonomous state equations (3.2),
V only depends on x. It is often referred to as "the derivative of V along the system
trajectory" - in particular, V = 0 at an equilibrium point. For the system (3.13), V^x)
is computed in (3.15) and found to be negative. Functions such as V in that example
are given a special name because of their importance in Lyapunov's direct method.
Definition 3.8 If, in a ball B , the function V(x) is positive definite and has
R
continuous partial derivatives, and if its time derivative along any state trajectory of
system (3.2) is negative semi-definite, i.e.,
V(x) < 0
then V(x) is said to be a Lyapunov function for the system (3.2).
Figure 3.9 : Illustrating Definition 3.8 for n = 2
A Lyapunov function can be given simple geometrical interpretations. In
Figure 3.9, the point denoting the value of V(xj,x ) is seen to always point down a
2
bowl. In Figure 3.10, the state point is seen to move across contour curves
corresponding to lower and lower values of V.
3.4.2 Equilibrium Point Theorems
The relations between Lyapunov functions and the stability of systems are made
precise in a number of theorems in Lyapunov's direct method. Such theorems usually
have local and global versions. The local versions are concerned with stability
properties in the neighborhood of equilibrium point and usually involve a locally
positive definite function.

62 Fundamentals of Lyapunov Theory Chap. 3
V = V
V = V
Figure 3.10 : Illustrating Definition 3.8 for n = 2 using contour curves
LYAPUNOV THEOREM FOR LOCAL STABILITY
Theorem 3.2 (Local Stability) //, in a ball h , there exists a scalar function V(x)
R
with continuous first partial derivatives such that
• V(x) is positive definite (locally in B )
R
• V(x) is negative semi-definite (locally in B )
R
then the equilibrium point 0 is stable. If, actually, the derivative V(x) is locally
negative definite in B^ , then the stability is asymptotic.
The proof of this fundamental result is conceptually simple, and is typical of
many proofs in Lyapunov theory.
Proof: Let us derive the result using the geometric interpretation of a Lyapunov function, as
illustrated in Figure 3.9 in the case n = 2. To show stability, we must show that given any strictly
positive number R, there exists a (smaller) strictly positive number r such that any trajectory
starting inside the ball B remains inside the ball B for all future time. Let m be the minimum of
r R
V on the sphere S . Since V is continuous and positive definite, m exists and is strictly positive.
R
Furthermore, since K(0) = 0, there exists a ball B around the origin such that V(x) < m for any x
r
inside the ball (Figure 3.1 la). Consider now a trajectory whose initial point x(0) is within the ball
B . Since V is non-increasing along system trajectories, V remains strictly smaller than m, and
r
therefore the trajectory cannot possibly cross the outside sphere S# . Thus, any trajectory starting
inside the ball B remains inside the ball B^ , and therefore Lyapunov stability is guaranteed.
r
Let us now assume that V is negative definite, and show asymptotic stability, by
contradiction. Consider a trajectory starting in some ball B as constructed above (e.g., the ball B
r r

Sect. 3.4 Lyapunov's Direct Method 63
(a) (b)
Figure 3.11: Illustrating the proof of Theorem 3.2 for n = 2
corresponding to R = R). Then the trajectory will remain in the ball B for all future time. Since
o s
V is lower bounded and decreases continually, V tends towards a limit L, such that
Vr>0, V(x(t))>L. Assume that this limit is not zero, i.e., that L>0. Then, since V is
continuous and V(0) = 0, there exists a ball B that the system trajectory never enters (Figure
r
3.1 lb). But then, since - V is also continuous and positive definite, and since B is bounded,
R
- V must remain larger than some strictly positive number L. This is a contradiction, because it
;
would imply that V(i) decreases from its initial value V to a value strictly smaller than L, in a
g
finite time smaller than [V - L)/L\. Hence, all trajectories starting in B asymptotically converge
g r
to the origin. Q
In applying the above theorem for analysis of a nonlinear system, one goes
through the two steps of choosing a positive definite function, and then determining its
derivative along the path of the nonlinear systems. The following example illustrates
this procedure.
Example 3.7: Local Stability
A simple pendulum with viscous damping is described by
e + e + sin e = o
Consider the following scalar function
V(x) = (l-

64 Fundamentals of Lyapunov Theory Chap. 3
One easily verifies that this function is locally positive definite. As a matter of fact, this function
represents the total energy of the pendulum, composed of the sum of the potential energy and the
kinetic energy. Its time-derivative is easily found to be
v(x) = esine + ee = -e2so
Therefore, by invoking the above theorem, one concludes that the origin is a stable equilibrium
point. In fact, using physical insight, one easily sees the reason why V(x) < 0, namely that the
damping term absorbs energy. Actually, V is precisely the power dissipated in the pendulum.
However, with this Lyapunov function, one cannot draw conclusions on the asymptotic stability
of the system, because V^x) is only negative semi-definite. Lj
The following example illustrates the asymptotic stability result.
Example 3.8: Asymptotic stability
Let us study the stability of the nonlinear system defined by
Jcj =jt| (xj2 + x2 2— 2) — Ax\X2 2
x = Ax^Xj + x (X[2 + x - 2)
2 2 2
around its equilibrium point at the origin. Given the positive definite function
V{x\,x)=x2+x2
2 l 2
its derivative V along any system trajectory is
Thus, V is locally negative definite in the 2-dimensional ball B, i.e., in the region defined by
2
jf]2 + x2 < 2. Therefore, the above theorem indicates that the origin is asymptotically stable. Ll
2
LYAPUNOV THEOREM FOR GLOBAL STABILITY
The above theorem applies to the local analysis of stability. In order to assert global
asymptotic stability of a system, one might naturally expect that the ball B^ in the
above local theorem has to be expanded to be the whole state-space. This is indeed
necessary, but it is not enough. An additional condition on the function V has to be
satisfied: V(x) must be radially unbounded, by which we mean that V(x) —> °° as
||x|| —> °° (in other words, as x tends to infinity in any direction). We then obtain the
following powerful result:

Sect. 3.4 Lyapuno v 's Direct Method 65
Theorem 3.3 (Global Stability) Assume that there exists a scalar function V of the
state x, with continuous first order derivatives such that
• V(x) is positive definite
• V(x) is negative definite
• V(x) -^oo as \\x\\ -> °°
then the equilibrium at the origin is globally asymptotically stable.
Proof: The proof is the same as in the local case, by noticing that the radial unboundedness of V,
combined with the negative defmiteness of V, implies that, given any initial condition x, the
o
trajectories remain in the bounded region defined by V(x) < V(\). O
g
The reason for the radial unboundedness condition is to assure that the contour
curves (or contour surfaces in the case of higher order systems) V(x) = V correspond
a
to closed curves. If the curves are not closed, it is possible for the state trajectories to
drift away from the equilibrium point, even though the state keeps going through
contours corresponding to smaller and smaller V>s- For example, for the positive
a
definite function V = [xj2/(l + Xj2)] + x 2, the curves V(x) = V for V > 1 are open
2 a a
curves. Figure 3.12 shows the divergence of the state while moving toward lower and
lower "energy" curves. Exercise 3.4 further illustrates this point on a specific system.
V(x) = K.
V(x) = K,
V(x) = V.
V > V > V
1 2 3
Figure 3.12 : Motivation of the radial unboundedness condition

66 Fundamentals of Lyapunov Theory Chap. 3
Example 3.9: A class of first-order systems
Consider the nonlinear system
x + c(x) = 0
where c is any continuous function of the same sign as its scalar argument x, i.e.,
xc(x) > 0 for
Intuitively, this condition indicates that - c(x) "pushes" the system back towards its rest position
x = 0, but is otherwise arbitrary. Since c is continuous, it also implies that c(0) = 0 (Figure 3.13).
Consider as the Lyapunov function candidate the square of the distance to the origin
The function V is radially unbounded, since it tends to infinity as \x\ —» °° . Its derivative is
Thus V < 0 as long as x * 0, so that x = 0 is a globally asymptotically stable equilibrium point.
c(x)
Figure 3.13 : The function c(x)
For instance, the system
is globally asymptotically convergent to x = 0, since for x * 0, sin2 x < (sin JC| -c (JC|. Similarly, the
system
is globally asymptotically convergent to x = 0. Notice that while this system's linear
approximation (x ~ 0) is inconclusive, even about local stability, the actual nonlinear system
enjoys a strong stability property (global asymptotic stability). O
1

Sect. 3.4 Lyapunov's Direct Method 67
Example 3.10: Consider the system
x\ =X2~X\(X\2 + X22)
The origin of the state-space is an equilibrium point for this system. Let V be the positive definite
function
V(x) = x2 + x2
The derivative of V along any system trajectory is
V(x) = 2x, x + 2xi = -2(x2 + x2)2
l 22 x 2
which is negative definite. Therefore, the origin is a globally asymptotically stable equilibrium
point. Note that the globalness of this stability result also implies that the origin is the only
equilibrium point of the system. f~1
REMARKS
Many Lyapunov functions may exist for the same system. For instance, if V is a
Lyapunov function for a given system, so is
V = pVa
x
where p is any strictly positive constant and a is any scalar (not necessarily an integer)
larger than 1. Indeed, the positive-definiteness of V implies that of Vj , the positive-
definiteness (or positive semi-definiteness) of - V implies that of —V\, and (the
radial unboundedness of V (if applicable) implies that of V .
x
More importantly, for a given system, specific choices of Lyapunov functions
may yield more precise results than others. Consider again the pendulum of Example
3.7. The function
V(x) = - 02 +1 (6 + 6)2 + 2( 1 - cosG)
is also a Lyapunov function for the system, because locally
i 2 < 0
However, it is interesting to note that V is actually locally negative definite, and
therefore, this modified choice of V, without obvious physica! meaning, allows the
asymptotic stability of the pendulum to be shown.

68 Fundamentals of Lyapunov Theory Chap. 3
Along the same lines, it is important to realize that the theorems in Lyapunov
analysis are all sufficiency theorems. If for a particular choice of Lyapunov function
candidate V, the conditions on V are not met, one cannot draw any conclusions on the
stability or instability of the system - the only conclusion one should draw is that a
different Lyapunov function candidate should be tried.
3.4.3 Invariant Set Theorems
Asymptotic stability of a control system is usually a very important property to be
determined. However, the equilibrium point theorems just described are often difficult
to apply in order to assert this property. The reason is that it often happens that V, the
derivative of the Lyapunov function candidate, is only negative semi-definite, as seen
in (3.15). In this kind of situation, fortunately, it is still possible to draw conclusions
on asymptotic stability, with the help of the powerful invariant set theorems, attributed
to La Salle. This section presents the local and global versions of the invariant set
theorems.
The central concept in these theorems is that of invariant set, a generalization of
the concept of equilibrium point.
Definition 3.9 A set G is an invariant set for a dynamic system if every system
trajectory which starts from a point in G remains in G for all future time.
For instance, any equilibrium point is an invariant set. The domain of attraction of an
equilibrium point is also an invariant set. A trivial invariant set is the whole state-
space. For an autonomous system, any of the trajectories in state-space is an invariant
set. Since limit cycles are special cases of system trajectories (closed curves in the
phase plane), they are also invariant sets.
Besides often yielding conclusions on asymptotic stability when V, the
derivative of the Lyapunov function candidate, is only negative semi-definite, the
invariant set theorems also allow us to extend the concept of Lyapunov function so as
to describe convergence to dynamic behaviors more general than equilibrium, e.g.,
convergence to a limit cycle.
Similarly to our earlier discussion of Lyapunov's direct method, we first discuss
the local version of the invariant set theorems, and then the global version.
LOCAL INVARIANT SET THEOREM
The invariant set theorems reflect the intuition that the decrease of a Lyapunov
I
function V has to gradually vanish (i.e., V has to converge to zero) because V is lower

Sect. 3.4 Lyapunov's Direct Method 69
bounded. A precise statement of this result is as follows.
Theorem 3.4 (Local Invariant Set Theorem) Consider an autonomous system of
the form (3.2), with f continuous, and let V(x) be a scalar function with continuous
first partial derivatives. Assume that
• for some I > 0, the region Qj defined by V(x) < I is bounded
• V(x) < 0 for all x in Q.
t
Let R be the set of all points within Q[ where V(x) = 0, and M be the largest
invariant set in R. Then, every solution x(t) originating in £2^ tends to M as t —» °°.
In the above theorem, the word "largest" is understood in the sense of set theory, i.e.,
M is the union of all invariant sets (e.g., equilibrium points or limit cycles) within R.
In particular, if the set R is itself invariant (i.e., if once V= 0, then V = 0 for all future
time), then M = R. Also note that V, although often still referred to as a Lyapunov
function, is not required to be positive definite.
The geometrical meaning of the theorem is illustrated in Figure 3.14, where a
trajectory starting from within the bounded region Q is seen to converge to the largest
;
invariant set M. Note that the set R is not necessarily connected, nor is the set M.
V=/
M
Figure 3.14 : Convergence to the largest invariant set M
The theorem can be proven in two steps, by first showing that V goes to zero,
and then showing that the state converges to the largest invariant set within the set
defined by V=0. We shall simply give a sketch of the proof, since the detailed proof
of the second part involves a number of concepts in topology and real analysis which
are not prerequisites of this text.

70 Fundamentals of Lyapunov Theory Chap. 3
Proof: The first part of the proof involves showing that V —> 0 for any trajectory starting from a
point in Qy, using a result in functional analysis known as Barbalat's lemma, which we shall
detail in section 4.3.
Specifically, consider a trajectory starting from an arbitrary point x in £ij. The trajectory
0
must stay in Q all the time, because V<0 implies that V[x(t)] < V[x(0)] < / for all t>0. In
;
addition, because V(x) is continuous in x (since it is differentiable with respect to x) over the
bounded region Q^, it is lower bounded in that region; therefore, since we just noticed that the
trajectory remains in Q, V[x(r)l remains lower bounded for all ( > 0. Furthermore, the facts that
;
f is continuous, V has continuous partial derivatives, and the region Q.j is bounded, imply that V is
uniformly continuous. Therefore, V[x(t)] satisfies the three conditions (V lower bounded; V < 0;
V uniformly continuous) of Barbalat's lemma. As a result, V[x(()] -• 0, which implies that all
system trajectories starting from within Qy converge to the set R.
The second part of the proof [see, e.g., Hahn, 1968] involves showing that the trajectories
cannot converge to just anywhere in the set R: they must converge to the largest invariant set M
within R. This can be proven by showing that any bounded trajectory of an autonomous system
converges to an invariant set (the so-called positive limit set of the trajectory), and then simply
noticing that this set is a subset of the largest invariant set M. D
Note that the asymptotic stability result in the local Lyapunov theorem can be
viewed a special case of the above invariant set theorem, where the set M consists
only of the origin.
Let us now illustrate applications of the invariant set theorem using some
examples. The first example shows how to conclude asymptotic stability for problems
which elude the local Lyapunov theorem. The second example shows how to
determine a domain of attraction, an issue which was not specifically addressed
before. The third example shows the convergence of system trajectories to a limit
cycle.
Example 3.11: Asymptotic stability of the mass-damper-spring system
For the system (3.13), one can only draw conclusion of marginal stability using the energy
function (3.14) in the local equilibrium point theorem, because V is only negative semi-definite
according to (3.15). Using the invariant set theorem, however, we can show that the system is
actually asymptotically stable. To do this, we only have to show that the set M contains only one
point.
The set R is defined by x = 0, i.e., the collection of states with zero velocity, or the whole
horizontal axis in the phase plane (x, x). Let us show that the largest invariant set M in this set R
contains only the origin. Assume that M contains a point with a nonzero position *,, then, the
acceleration at that point is ji" = - (klm)x- (k\/m)x^ *0. This implies that the trajectory will
o

| Sect. 3.4  |     |     | Lyapunov's Direct Method  | 71  |
| ---------- | --- | --- | ------------------------- | --- |
immediately  move  out of the set R and thus  also out of the set M,  a contradiction  to the
| definition.  |     |     |     | CD  |
| ------------ | --- | --- | --- | --- |
Example 3.12: Domain of Attraction
Consider  again  the  system  in  Example  3.8.  For  / = 2,  the  region  £i >  defined  by
2
V(x) = X|2 + x  2 < 2 , is bounded. The set R is simply the origin 0, which  is an invariant set
(since it is an equilibrium point). All the conditions of the local invariant set theorem are satisfied
and, therefore, any trajectory starting within the circle converges to the origin. Thus, a domain of
attraction is explicitly determined by the invariant set theorem.  CD
Example 3.13: Attractive Limit Cycle
Consider the system
|                                          | x  x = x  2 -               | x^  [xA  [ + 2x2-  2 | 10]                            |     |
| ---------------------------------------- | --------------------------- | -------------------- | ------------------------------ | --- |
|                                          | = -x,3                      | 3x5[x,4 + 2x2-       |                                |     |
|                                          | x  2                        | -  2                 | 2 10]                          |     |
| Notice first that the set defined by x4  |                             |                      | + 2x2 = 10 is invariant, since |     |
|                                          |                             | t                    | 2                              |     |
|                                          | -(x,4 + 2x2- 10) = -(4x,10  |                      | + 12x6)(x,4 + 2x2- 10)         |     |
|                                          |                             | 2                    | 2 2                            |     |
which is zero on the set. The motion on this invariant set is described (equivalently) by either of
the equations
x,  = x2
x2 =  -x,3
Therefore, we see that the invariant set actually represents a limit cycle, along which the state
vector moves clockwise.
Is this limit cycle actually attractive? Let us define as a Lyapunov function candidate
|     | l/=(x,4 + 2x2-  | I0)2 |     |     |
| --- | --------------- | ---- | --- | --- |
2
which represents a measure of the "distance" to the limit cycle. For any arbitrary positive number
/, the region Q/, which surrounds the limit cycle, is bounded.  Using our earlier calculation, we
immediately obtain
V = -8(xl0 + 3x6)(x,4 + 2x2- 10)2
|     | (   | 2   | 2   |     |
| --- | --- | --- | --- | --- |
Thus V is strictly negative, except if
|     | x,4 + 2x2=I0  | or  | x,l0 + 3x6  = 0 |     |
| --- | ------------- | --- | --------------- | --- |
|     | 2             |     | 2               |     |

I
72 Fundamentals ofLyapunov Theory Chap. 3
in which case V = 0. The first equation is simply that defining the limit cycle, while the second
equation is verified only at the origin. Since both the limit cycle and the origin are invariant sets,
the set M simply consists of their union. Thus, all system trajectories starting in Q; converge
either to the limit cycle, or to the origin (Figure 3.15).
Figure 3.15 : Convergence to a limit cycle
Moreover, the equilibrium point at the origin can actually be shown to be unstable. However,
this result cannot be obtained from linearization, since the linearized system (x'j = x , x = 0) is
2 2
only marginally stable. Instead, and more astutely, consider the region QJQO , and note that while
the origin 0 does not belong to Q , every other point in the region enclosed by the limit cycle is
100
in Q|QQ (in other words, the origin corresponds to a local maximum of V). Thus, while the
expression of V is the same as before, now the set M is just the limit cycle. Therefore,
reappUcation of the invariant set theorem shows that any state trajectory starting from the region
within the limit cycle, excluding the origin, actually converges to the limit cycle. In particular,
this implies that the equilibrium point at the origin is unstable. [D
Example 3.11 actually represents a very common application of the invariant set
theorem: conclude asymptotic stability of an equilibrium point for systems with
negative semi-definite V. The following corollary of the invariant set theorem is more
specifically tailored to such applications:
Corollary Consider the autonomous system (3.2), with f continuous, and let V(x) be
a scalar function with continuous partial derivatives. Assume that in a certain
neighborhood Q of the origin

Sect. 3.4 Lyapunov's Direct Method 73
• V(x) is locally positive definite
• V is negative semi-definite
• the set R defined by V(x) = 0 contains no trajectories of (3.2) other than
the trivial trajectory x = 0
Then, the equilibrium point 0 is asymptotically stable. Furthermore, the largest
connected region of the form £2^ (defined by V(x) < I) within £2 is a domain of
attraction of the equilibrium point.
Indeed, the largest invariant set M in R then contains only the equilibrium point 0.
Note that
• The above corollary replaces the negative definiteness condition on V in
Lyapunov's local asymptotic stability theorem by a negative
,sem/-definiteness condition on V, combined with a third condition on the
trajectories within R.
• The largest connected region of the form Q within £2 is a domain of
;
attraction of the equilibrium point, but not necessarily the whole domain of
attraction, because the function V is not unique.
• The set Q itself is not necessarily a domain of attraction. Actually, the
above theorem does not guarantee that £2 is invariant: some trajectories
starting in £2 but outside of the largest £2/ may actually end up outside £2.
GLOBAL INVARIANT SET THEOREMS
The above invariant set theorem and its corollary can be simply extended to a global
result, by requiring the radial unboundedness of the scalar function V rather than the
existence of a bounded £2;.
Theorem 3.5 (Global Invariant Set Theorem) Consider the autonomous system
(3.2), with f continuous, and let V(x) be a scalar function with continuous first partial
derivatives. Assume that
• V(x) -> °° as !|x|| -> oo
• V(x) < 0 over the whole state space
Let R be the set of all points where V(x) = 0, and M be the largest invariant set in R.
Then all solutions globally asymptotically converge toMas(->°°.
For instance, the above theorem shows that the limit cycle convergence in

74 Fundamentals ofLyapunov Theory Chap. 3
Example 3.13 is actually global: all system trajectories converge to the limit cycle
(unless they start exactly at the origin, which is an unstable equilibrium point).
Because of the importance of this theorem, let us present an additional (and
very useful) example.
Example 3.14: A class of second-order nonlinear systems
Consider a second-order system of the form
where b and c are continuous functions verifying the sign conditions
xb(x) > 0 for i*0
xc(x) > 0 for x&O
The dynamics of a mass-damper-spring system with nonlinear damper and spring can be
described by equations of this form, with the above sign conditions simply indicating that the
otherwise arbitrary functions b and c actually represent "damping" and "spring" effects. A
nonlinear R-L-C (resistor-inductor-capacitor) electrical circuit can also be represented by the
above dynamic equation (Figure 3.16). Note that if the functions b and c are actually linear
( b(x) = ot[ x , c(x) = <x x ), the above sign conditions are simply the necessary and sufficient
0
conditions for the system's stability (since they are equivalent to the conditions otj > 0, a > 0).
o
V = c(x) V — X V = b(x)
C R
+
^ —-
Figure 3.16 : A nonlinear R-L-C circuit
Together with the continuity assumptions, the sign conditions on the functions b and c imply
that b(0) = 0 and c(0) = 0 (Figure 3.17). A positive definite function for this system is
1
which can be thought of as the sum of the kinetic and potential energy of the system.

Sect. 3.4 Lyapunov's Direct Method 75
Differentiating V, we obtain
V = xx + c(x)x = -xb(x) -xc(x) + c(x)x = -xb{x) < 0
which can be thought of as representing the power dissipated in the system. Furthermore, by
hypothesis, x b(x) = 0 only if x = 0. Now x = 0 implies that
x = - c(x)
which is nonzero as long as x ^ 0. Thus the system cannot get "stuck" at an equilibrium value
other than x = 0 ; in other words, with R being the set defined by x = 0, the largest invariant set
M in R contains only one point, namely [x = 0, x = 0]. Use of the local invariant set theorem
indicates that the origin is a locally asymptotically stable point.
b(x) c(x)
Figure 3.17 : The functions b(x) and c(x)
Furthermore, if the integral lxc(r)dr is unbounded as |x| —> °°, then V is a radially
unbounded function and the equilibrium point at the origin is globally asymptotically stable,
according to the global invariant set theorem.
For instance, the system
3 +x5 = x4 sin2x
is globally asymptotically convergent to x = 0 (while, again, its linear approximation would be
inconclusive, even about its local stability). D
The relaxation of the positive definiteness requirement on the function V, as
compared with Lyapunov's direct method, also allows one to use a single Lyapunov-
like function to describe systems with multiple equilibria.
Example 3.15: Multimodal Lyapunov Function
Consider the system

76 Fundamentals of Lyapunov Theory Chap. 3
! . KX
+x= sin—
For this system, we study, similarly to Example 3.14, the Lyapunov function
This function has two minima, atx = ± 1; x = 0, and a local maximum in x (a saddle point in the
state-space) at x = 0; x - 0. As in Example 3.14, the time-derivative of V is (without calculations)
V = - |x2-l|x4
i.e, the virtual power "dissipated" by the system. Now
V = 0 => i = 0 or i = il
Let us consider each of these cases:
x = 0 => 3c = sin — - x * 0 except if x = 0 or x = ± 1
x = + 1 => x = 0
Thus, the invariant set theorem indicates that the system converges globally to (x = 1; x = 0) or
(x = - 1; x = 0), or to (x = 0; x = 0). The first two of these equilibrium points are stable, since they
correspond to local mimina of V (note again that linearization is inconclusive about their
stability). By contrast, the equilibrium point (x = 0; x = 0) is unstable, as can be shown from
linearization (x = (it/2 - 1) x), or simply by noticing that because that point is a local maximum of
V along the x axis, any small deviation in the x direction will drive the trajectory away from it. ID
As noticed earlier, several Lyapunov functions may exist for a given system,
and therefore several associated invariant sets may be derived. The system then
converges to the (necessarily non-empty) intersection of the invariant sets M-, which
(
may give a more precise result than that obtained from any of the Lyapunov functions
taken separately. Equivalently, one can notice that the sum of two Lyapunov
functions for a given system is also a Lyapunov function, whose set R is the
intersection of the individual sets R,-.
3.5 System Analysis Based on Lyapunov's Direct Method
With so many theorems and so many examples presented in the last section, one may
feel confident enough to attack practical nonlinear control problems. However, the
theorems all make a basic assumption: an explicit Lyapunov function is somehow

Sect. 3.5 System Analysis Based on Lyapunov's Direct Method 77
known. The question is therefore how to find a Lyapunov function for a specific
problem. Yet, there is no general way of finding Lyapunov functions for nonlinear
systems. This is a fundamental drawback of the direct method. Therefore, faced with
specific systems, one has to use experience, intuition, and physical insights to search
for an appropriate Lyapunov function. In this section, we discuss a number of
techniques which can facilitate the otherwise blind search of Lyapunov functions.
We first show that, not surprisingly, Lyapunov functions can be systematically
found to describe stable linear systems. Next, we discuss two of many mathematical
methods that may be used to help finding a Lyapunov function for a given nonlinear
system. We then consider the use of physical insights, which, when applicable,
represents by far the most powerful and elegant way of approaching the problem, and
is closest in spirit to the original intuition underlying the direct method. Finally, we
discuss the use of Lyapunov functions in transient performance analysis.
3.5.1 Lyapunov Analysis of Linear Time-Invariant Systems
Stability analysis for linear time-invariant systems is well known. It is interesting,
however, to develop Lyapunov functions for such systems. First, this allows us to
describe both linear and nonlinear systems using a common language, allowing shared
insights between the two classes. Second, as we shall detail later on, Lyapunov
functions are "additive", like energy. In other words, Lyapunov functions for
combinations of subsystems may be derived by adding the Lyapunov functions of the
subsystems. Since nonlinear control systems may include linear components (whether
in plant or in controller), we should be able to describe linear systems in the Lyapunov
formalism.
We first review some basic results on matrix algebra, since the development of
Lyapunov functions for linear systems will make extensive use of quadratic forms.
SYMMETRIC, SKEW-SYMMETRIC, AND POSITIVE DEFINITE
MATRICES
Definition 3.10 A square matrix M is symmetric if M = MT (in other words, if
V/,y MJ: = Mji). A square matrix M is skew-symmetric if M = — M^ (i.e. if
Vi.y M^-Mji).
An interesting fact is that any square nxn matrix M can be represented as the
sum of a symmetric matrix and a skew-symmetric matrix. This can be shown by the
following decomposition

78 Fundamentals of Lyapunov Theory Chap. 3
.„ M + MT M - Mr
ivl = +
2 2
where the first term on the left side is symmetric and the second term is skew-
symmetric.
Another interesting fact is that the quadratic function associated with a skew-
symmetric matrix is always zero. Specifically, let M be a nxn skew-symmetric matrix
and x an arbitrary «xl vector. Then the definition of a skew-symmetric matrix implies
that
Since xrMrx is a scalar, the right-hand side of the above equation can be replaced by
its transpose. Therefore,
This shows that
Vx, xrMx = 0 (3.16)
In designing some tracking control systems for robots, for instance, this fact is very
useful because it can simplify the control law, as we shall see in chapter 9.
Actually, property (3.16) is a necessary and sufficient condition for a matrix M
to be skew-symmetric. This can be easily seen by applying (3.16) to the basis vectors
[ V i, erMe,- = 0 ] => [ V i, M = 0 ]
( s H
and
[ V (ij), (e,- + HjfM^i + e ) = 0 ] => [V ((,;), M + M + M + MJJ = 0 ]
y u tj fi
which, using the first result, implies that
In our later analysis of linear systems, we will often use quadratic functions of
the form x^Mx as Lyapunov function candidates. In view of the above, each quadratic
function of this form, whether M is symmetric or not, is always equal to a quadratic
function with a symmetric matrix. Thus, in considering quadratic functions of the form
x^Mx as Lyapunov function candidates, one can always assume, without loss of
generality, that M is symmetric.

Sect. 3.5 System Analysis Based on Lyapunov's Direct Method 79
We are now in a position to introduce the important concept of positive definite
matrices.
Definition 3.11 A square nxn matrix M is positive definite (p.d.) if
x*0 => xrMx>0
In other words, a matrix M is positive definite if the quadratic function x^Mx is a
positive definite function. This definition implies that to every positive definite matrix
is associated a positive definite function. Obviously, the converse is not true.
Geometrically, the definition of positive-definiteness can be interpreted as
simply saying that the angle between a vector x and its image Mx is always less than
90° (Figure 3.18).
Figure 3.18 : Geometric interpretation of
the positive-definiteness of a matrix M
A necessary condition for a square matrix M to be p.d. is that its diagonal
elements be strictly positive, as can be seen by applying the above definition to the
basis vectors. A famous matrix algebra result called Sylvester's theorem shows that,
assuming that M is symmetric, a necessary and sufficient condition for M to be p.d. is
that its principal minors (i.e., Mjj , M^M 2- M \ M > ••• > det M ) all be strictly
2 2 i2
positive; or, equivalently, that all its eigenvalues be strictly positive. In particular, a
symmetric p.d. matrix is always invertible, because the above implies that its
determinant is non-zero.
A positive definite matrix M can always be decomposed as
M = UrAU (3.17)
where U is a matrix of eigenvectors and satisfies UTU = I, and A is a diagonal matrix
containing the eigenvalues of the matrix M. Let X (M) denote the smallest
min
eigenvalue of M and A, (M) the largest. Then, it follows from (3.17) that
max
||2 < xTMx < X (M)\\xf
max

80 Fundamentals ofLyapunov Theory Chap. 3
This is due to the following three facts:
• xrMx = xrUrAUx = zrAz, where Ux = z
• X (M)l< A < U M )I
min
• zTz = ||x||2
The concepts of positive semi-definite, negative definite, and negative semi-
definite can be defined similarly. For instance, a square n x n matrix M is said to be
positive semi-definite (p.s.d.) if
V x , xT M x > 0
By continuity, necessary and sufficient conditions for positive semi-definiteness are
obtained by substituting "positive or zero" to "strictly positive" in the above conditions I
for positive definiteness. Similarly, a p.s.d. matrix is invertible only if it is actually I
p.d. Examples of p.s.d. matrices are n x n matrices of the form M = NrN where N is a :
m x n matrix. Indeed,
V x , xT NrN x = (Nx)r (Nx) > 0
A matrix inequality of the form
M,>M
2
(where Mj and M are square matrices of the same dimension) means that
2
M, - M > 0
2
i.e., that the matrix Mj - M is positive definite. Similar notations apply to the
2
concepts of positive semi-definiteness, negative definiteness, and negative semi-
definiteness.
A time-varying matrix M(f) is uniformly positive definite if
3 a > 0, V t > 0, M(0 > a I
A similar definition applies for uniform negative-definiteness of a time-varying
matrix.
LYAPUNOV FUNCTIONS FOR LINEAR TIME-INVARIANT SYSTEMS
Given a linear system of the form x = A x , let us consider a quadratic Lyapunov
function candidate
V = \T P x

Sect. 3.5 System Analysis Based on Lyapunov's Direct Method 81
where P is a given symmetric positive definite matrix. Differentiating the positive
definite function V along the system trajectory yields another quadratic form
V = (3.18)
where
ArP+PA=-Q (3.19)
The question, thus, is to determine whether the symmetric matrix Q defined by the so-
called Lyapunov equation (3.19) above, is itself p.d. If this is the case, then V satisfies
the conditions of the basic theorem of section 3.4, and the origin is globally
asymptotically stable. However, this "natural" approach may lead to inconclusive
result, i.e., Q may be not positive definite even for stable systems.
Example 3.17: Consider a second-order linear system whose A matrix is
4
A =
-12
If we take P = I, then
0 -4
-4 -24
The matrix Q is not positive definite. Therefore, no conclusion can be drawn from the Lyapunov
function on whether the system is stable or not. C]
A more useful way of studying a given linear system using scalar quadratic
functions is, instead, to derive a positive definite matrix P from a given positive
definite matrix Q, i.e.,
• choose a positive definite matrix Q
• solve for P from the Lyapunov equation (3.19)
• check whether P is p.d
If P is p.d., then x^Px is a Lyapunov function for the linear system and global
asymptotical stability is guaranteed. Unlike the previous approach of going from a
given P to a matrix Q, this technique of going from a given Q to a matrix P always
leads to conclusive results for stable linear systems, as seen from the following
theorem.

82 Fundamentals of Lyapunov Theory Chap. 3
Theorem 3.6 A necessary and sufficient condition for a LTl system x = A x to be
strictly stable is that, for any symmetric p.d. matrix Q, the unique matrix P solution of
the Lyapunov equation (3.19) be symmetric positive definite.
Proof: The above discussion shows that the condition is sufficient, thus we only need to show
that it is also necessary. We first show that given any symmetric p.d. matrix Q, there exists a
symmetric p.d. matrix P verifying (3.19). We then show that for a given Q, the matrix P is
actually unique.
Let Q be a given symmetric positive definite matrix, and let
P = f exp(Ar t) Q exp(A r) dt (3.20)
One can easily show that this integral exists if and only if A is strictly stable. Also note that the
matrix P thus defined is symmetric and positive definite, since Q is. Furthermore, we have
oo
= J [ Ar exp(Ar 0 Q exp(A t) + exp(Ar t) Q exp(A t)A]dt
= ArP + PA
where the first equality comes from the stability of A (which implies that exp (A°°) = 0), the
second from differentiating the exponentials explicitly, and the third from the fact that A is
constant and therefore can be taken out of the integrals.
The uniqueness of P can be verified similarly by noting that another solution Pj of the
Lyapunov equation would necessarily verify
oo
Pi = -] 4exp(Ar0P exp(A()]
1
oo
= - J exp(AT f) ( Ar P, + P, A ) exp(A I) ] dt
oo
= I exp(Ar t) Q exp(A t)dt = V
J0
An alternate proof of uniqueness is the elegant original proof given by Lyapunov, which
makes direct use of fundamental algebra results. The Lyapunov equation (3.19) can be
i

Sect. 3.5 System Analysis Based on Lyapunov's Direct Method 83
interpreted as defining a linear map from the n2 components of the matrix P to the n2 components
of the matrix Q, where P and Q are arbitrary (not necessarily symmetric p.d.) square matrices.
Since (3.20) actually shows the existence of a solution P for any square matrix Q, the range of
this linear map is full, and therefore its null-space is reduced to 0. Thus, for any Q, the solution P
is unique. D
The above theorem shows that any positive definite matrix Q can be used to
determine the stability of a linear system. A simple choice of Q is the identity matrix.
Example 3.18: Consider again the second-order system of Example 3.17. Let us take Q = I and
denote P by
Pll Pl2
P =
Pl\ P22
where, due to the symmetry of P, pi = Pu- Then the Lyapunov equation is
2
0 -8 - 1 0
Pll P\2
4 -12 0 -1
Pl2 P22
whose solution is
p=5/16, p =P2=
n l2 2
The corresponding matrix
5 1
16 1 1
is positive definite, and therefore the linear system is globally asymptotically stable. Note that we
have solved for P directly, without using the more cumbersome expression (3.20). CD
Even though the choice Q = I is motivated by computational simplicity, it has a
surprising property: the resulting Lyapunov analysis allows us to get the best estimate
of the state convergence rate, as we shall see in section 3.5.5.
3.5.2 Krasovskii's Method
Let us now come back to the problem of finding Lyapunov functions for general
nonlinear systems. Krasovskii's method suggests a simple form of Lyapunov function

84 Fundamentals ofLyapunov Theory Chap. 3
candidate for autonomous nonlinear systems of the form (3.2), namely, V = f^f. The
basic idea of the method is simply to check whether this particular choice indeed leads
to a Lyapunov function.
Theorem 3.7 (Krasovskii) Consider the autonomous system defined by (3.2), with
the equilibrium point of interest being the origin. Let A(x) denote, the Jacobian matrix
of the system, i.e.,
A(x) = —
d x
// the matrix F = A + \T is negative definite in a neighborhood Q., then the
equilibrium point at the origin is asymptotically stable. A Lyapunov function for this
system is
V(x) = f{x) f(x)
// Q. is the entire state space and, in addition, V(x) —> °° as \\x\\ -> °o, then the
equilibrium point is globally asymptotically stable.
Proof: First, let us prove that the negative definiteness of F implies that f(x) ^ 0 for x * 0.
Since the square matrix F(x) is negative definite for non-zero x, one can show that the
Jacobian matrix A(x) is invertible, by contradiction. Indeed, assume that A is singular. Then one
can find a non-zero vector y such that A(x)y = 0. Since
0 0
the singularity of A implies that y^A y = 0, which contradicts the assumed negative definiteness
o g
ofF.
The invertibility and continuity of A guarantee that the function f(x) can be uniquely
inverted. This implies that the dynamic system (3.2) has only one equilibrium point in £i
(otherwise different equilibrium points would correspond to the same value of f), i.e., that f(x) ^ 0
for x * 0.
We can now show the asymptotic stability of the origin. Given the above result, the scalar
function V(x) = f^(x) f(x) is positive definite. Using the fact that f = A f, the derivative of V can be
written
V(x) = frf + frf = frAf + frArf = frFf
The negative definiteness of F implies the negative definiteness of V. Therefore, according to
Lyapunov's direct method, the equilibrium state at the origin is asymptotically stable. The global

Sect. 3.5 System Analysis Based on Lyapunov's Direct Method 85
asymptotic stability of the system is guaranteed by the global version of Lyapunov's direct
method. D
Let us illustrate the use of Krasovskii's theorem on a simple example.
Example 3.19: Consider the nonlinear system
^2 = 2jtj — 6^2 — 2x2
We have
-6 -12 4
F = A + Ar =
2 -6-6* 2 4 -12-12*
•2
The matrix F is easily shown to be negative definite over the whole state space. Therefore, the
origin is asymptotically stable, and a Lyapunov function candidate is
V(x) = fr(x)f(x) = (-6*, + 2x)2 + (2x,-6x-2x3)2
2 2 2
Since V(x) -> °° as ||x|| —> °° , the equilibrium state at the origin is globally asymptotically
stable. •
While the use of the above theorem is very straightforward, its applicability is
limited in practice, because the Jacobians of many systems do not satisfy the negative
definiteness requirement. In addition, for systems of high order, it is difficult to check
the negative definiteness of the matrix F for all x.
An immediate generalization of Krasovskii's theorem is as follows:
Theorem 3.8 (Generalized Krasovskii Theorem) Consider the autonomous system
defined by (3.2), with the equilibrium point of interest being the origin, and let A(x)
denote the Jacobian matrix of the system. Then, a sufficient condition for the origin to
be asymptotically stable is that there exist two symmetric positive definite matrices P
and Q, such that Vx ^ 0, the matrix
F(x) = A7P+PA + Q
is negative semi-definite in some neighborhood Q of the origin. The function
V(x) = f^Pf is then a Lyapunov function for the system. If the region Q is the whole
state space, and if in addition, V(x) -^ °° as \\x\\ —> °°, then the system is globally
asymptotically stable.

86 Fundamentals of Lyapunov Theory Chap. 3
Proof: This theorem can be proven similarly. The positive definiteness of V(x) can be derived as
before. Furthermore, the derivative of V can be computed as
V = — f(x) = fTPA(x)f + frPAr(x)Pf = frFf-frQf
3x
Because F is negative semi-definite and Q is positive definite, V is negative definite and the
equilibrium point at the origin is asymptotically stable. If V(x) —> °° as ||x|| —> °° , the global
version of Lyapunov's direct method indicates the global asymptotic stability of the system. D
3.5.3 The Variable Gradient Method
The variable gradient method is a formal approach to constructing Lyapunov
functions. It involves assuming a certain form for the gradient of an unknown
Lyapunov function, and then finding the Lyapunov function itself by integrating the
assumed gradient. For low order systems, this approach sometimes leads to the
successful discovery of a Lyapunov function.
To start with, let us note that a scalar function V(x) is related to its gradient W
by the integral relation
V(x) = Cwdx
where W= {dV/dx^, ,3V/dx}T. In order to recover a unique scalar function V
n
from the gradient VV, the gradient function has to satisfy the so-called curl conditions
a v V: a v V:
^r^ = -~ (/,;= i,2,...,n)
a Xj 3 Xj
Note that the ith component VV,- is simply the directional derivative d V/3 x . For
i
instance, in the case n = 2, the above simply means that
dVVy d V V
2
The principle of the variable gradient method is to assume a specific form for
the gradient VV, instead of assuming a specific form for the Lyapunov function V
itself. A simple way is to assume that the gradient function is of the form
VV = j^a (3.21)
; ljXj

Sect. 3.5 System Analysis Based on Lyapunov's Direct Method 87
where the a,-.'s are coefficients to be determined. This leads to the following
procedure for seeking a Lyapunov function V :
• assume that VV is given by (3.21) (or another form)
• solve for the coefficients a: so as to satisfy the curl equations
t
• restrict the coefficients in (3.21) so that V is negative semi-definite (at
least locally)
• compute V from VV by integration;
• check whether V is positive definite
Since satisfaction of the curl conditions implies that the above integration result is
independent of the integration path, it is usually convenient to obtain V by integrating
along a path which is parallel to each axis in turn, i.e.,
V(x) = f' W^.O.-.-.O) dx + f2 VV(x,x,0,...,0)dx2 + ...
{ 2 l 2
o o
Example 3.20: Let us use the variable gradient method to find a Lyapunov function for the
nonlinear system
i>> = — 2*2
We assume that the gradient of the undetermined Lyapunov function has the following form
The curl equationis
dx
2
da 3a
l2 21
a l2 + *.2 3x 2 °21 X] 3*,

88 Fundamentals of Lyapunov Theory Chap. 3
If the coefficients are chosen to be
a =a =\,a = a =0
n 22 n 2l
which leads to
W,=x, W = x
2 2
then V can be computed as
V = VV k = - 2x,2 - 2x2( 1 -xx)
2 y 2
Thus, V is locally negative definite in the region (1 - xx) > 0 . The function V can be computed
x 2
as
-x. -x, x2 + x-?-
t
V(x)= f x,dx, + f xdx = (3.22)
2 2
This is indeed positive definite, and therefore the asymptotic stability is guaranteed.
Note that (3.22) is not the only Lyapunov function obtainable by the variable gradient
method. For example, by taking
a,, = l, a = x2
n 2
«21=3*22 • a22=3
we obtain the positive definite function
V = ^i- + L2 + x,x3 (3.23)
2 2
whose derivative is
V = - 2x,2 - 6x2 - 2x2 (x,x - 3x,2x2)
2 2 2 2
One easily verifies that V is a locally negative definite function (noting that the quadratic terms
are dominant near the origin), and therefore, (3.23) represents another Lyapunov function for the
system. uJ
3.5.4 Physically Motivated Lyapunov Functions
The Lyapunov functions in the above sections 3.5.1-3.5.3, and in a number of
examples earlier in section 3.4, have been obtained from a mathematical point of
view, i.e., we examined the mathematical features of the given differential equations

Sect. 3.5 System Analysis Based on Lyapunov's Direct Method 89
and searched for Lyapunov function candidates V that can make V negative. We did
not pay much attention to where the dynamic equations came from and what
properties the physical systems had. However, this purely mathematical approach,
though effective for simple systems, is often of little use for complicated dynamic
equations. On the other hand, if engineering insight and physical properties are
properly exploited, an elegant and powerful Lyapunov analysis may be possible for
very complex systems.
Example 3.21: Global asymptotic stability of a robot position controller
A fundamental task in robotic applications is for robot manipulators to transfer objects from one
point to another, the so-called robot position control problem. In the last decade, engineers had
been routinely using P.D. (proportional plus derivative) controllers to control robot arms.
However, there was no theoretical justification for the stability of such control systems, because
the dynamics of a robot is highly nonlinear.
A robot arm consists a number of links connected by rotational or translational joints, with
the last link equipped with some end-effector (Figure 3.19). The dynamics of an n-link robot arm
can be expressed by a set of n equations,
H(q) q + b(q, q) + g(q) = T (3.24)
where q is an ^-dimensional vector describing the joint positions of the robot, x is the vector of
input torques, g is the vector of gravitational torques, b represents the Coriolis and centripetal
forces caused by the motion of the links, and H the nxn inertia matrix of the robot arm. Consider
a controller simply composed of a P.D. term and a gravity compensation term
(3.25)
where K and K are constant positive definite nxn matrices. It is almost impossible to use
D p
trial-and error to search for a Lyapunov function for the closed loop dynamics defined by (3.24)
and (3.25), because (3.24) contains hundreds of terms for the 5-Hnk or 6-link robot arms
commonly found in industry. Therefore, it seems very difficult to show that q —> 0 and q —» 0.
With the aid of physical insights, however, a Lyapunov function can be successfully found
for such complex robotic systems. First, note that the inertia matrix H(q) is positive definite for
any q. Second, the P.D. control term can be interpreted as mimicking a combination of dampers
and springs. This suggests the following Lyapunov function candidate
V = I[qrHq+ qrK q]
p
where the first term represents the kinetic energy of the manipulator, and the second term denotes
the "artificial potential energy" associated with the virtual spring in the control law (3.25).

90 Fundamentals of Lyapunov Theory Chap. 3
joint 2
base(link 0)
Figure 3.19 : A robot manipulator
In computing the derivative of this function, one can use the energy theorem in mechanics,
which states that the rate of change of kinetic energy in a mechanical system is equal to the power
provided by the external forces. Therefore,
Substitution of the control law (3.25) in the above equation then leads to
Since the arm cannot get "stuck" at any position such that q # 0 (which can be easily shown by
noting that acceleration is non-zero in such situations), the robot arm must settle down at q = 0
and q = 0, according to the invariant set theorem. Thus, the system is actually globally
asymptotically stable. O
Two lessons can be learned from this practical example. The first is that one
should use as many physical properties as possible in analyzing the behavior of a
system. The second lesson is that physical concepts like energy may lead us to some
uniquely powerful choices of Lyapunov functions. Physics will play a major role in
the development of the multi-input nonlinear controllers of chapter 9.

Sect. 3.5 System Analysis Based on Lyapunov's Direct Method 91
3.5.5 Performance Analysis
In the preceding sections, we have been primarily concerned with using Lyapunov
functions for stability analysis. But sometimes Lyapunov functions can further provide
estimates of the transient performance of stable systems. In particular, they can allow
us to estimate the convergence rate of asymptotically stable linear or nonlinear
systems. In this section, we first derive a simple lemma on differential inequalities.
We then show how Lyapunov analysis may be used to determine the convergence
rates of linear and nonlinear systems.
A SIMPLE CONVERGENCE LEMMA
Lemma: If a real function W(t) satisfies the inequality
W(t) + aW(t) < 0 (3.26)
where a is a real number. Then
W(t)<W(0)e~at
Proof: Let us define a function Z(t) by
Z(t) = W + aW (3.27)
Equation (3.26) implies that Z(t) is non-positive. The solution of the first-order equation (3.27) is
W(t) = W(0)e~a'+i e~a(;"r)Z{t)dr
* o
Because the second term in the right-hand-side of the above equation is non-positive, one has
W(t)<W(0)e-at •
The above lemma implies that, if W is a non-negative function, the satisfaction
of (3.26) guarantees the exponential convergence of W to zero. In using Lyapunov's
direct method for stability analysis, it is sometimes possible to manipulate V into the
form of (3.26). In such a case, the exponential convergence of V and the convergence
rate can be inferred and, in turn, the exponential convergence rate of the state may
then be determined. In later chapters, we will provide examples of using this lemma
for estimating convergence rates of nonlinear or adaptive control systems.
ESTIMATING CONVERGENCE RATES FOR LINEAR SYSTEMS
Now let us evaluate the convergence rate of a stable linear system based on the
Lyapunov analysis described in section 3.5.1. Let us denote the largest eigenvalue of

92 Fundamentals ofLyapunov Theory Chap. 3
the matrix P by A, (P), the smallest eigenvalue of Q by A. (Q), and their ratio
max min
^•mitfQir^mwfP) by Y- The positive definiteness of P and Q implies that these scalars
are all strictly positive. Since matrix theory shows that
we have
r ;>
x Qx
This and (3.18) imply that
V<-yV
This, according to lemma, means that
This, together with the fact x^Px > X, (P)||x(f)ll2 , implies that the state x converges
mln
to the origin with a rate of at least y/2.
One might naturally wonder how this convergence rate estimate varies with the
choice of Q, and how it relates to the familiar notion of dominant pole in linear theory.
An interesting result is that the convergence rate estimate is largest for Q = I. Indeed,
let P be the solution of the Lyapunov equation corresponding to Q = I:
o
and let P be the solution corresponding to some other choice of Q
Without loss of generality, we can assume that ^ ,>,(Qi) = 1, since rescaling Qj will
m
rescale P by the same factor, and therefore will not affect the value of the
corresponding y. Subtracting the above two equations yields
Now since X. -(Qj) = 1 = X, (I), the matrix (Q[ -1) is positive semi-definite, and
mi n max
hence the above equation implies that (P - P) is positive semi-definite. Therefore
o
Since A, (Qj) = 1 = A, (I), the convergence rate estimate
m;n m;n

Sect. 3.5 System Analysis Based on Lyapunov's Direct Method 93
corresponding to Q = I is larger than (or equal to) that corresponding to Q = Qj.
If the stable matrix A is symmetric, then the meaning of this "optimal" value of
y, corresponding to the choice Q = I, can be interpreted easily. Indeed, all
eigenvalues of A are then real, and furthermore A is diagonalizable, i.e., there exists a
change of state coordinates such that in these coordinates A is diagonal. One
immediately verifies that, in these coordinates, the matrix P = - 1/2 A~ ' verifies the
Lyapunov equation for Q = I, and that therefore the corresponding y/2 is simply the
absolute value of the dominant pole of the linear system. Furthermore, y is obviously
independent of the choice of state coordinates.
ESTIMATING CONVERGENCE RATES FOR NONLINEAR SYSTEMS
The estimation of convergence rate for nonlinear systems also involves manipulating
the expression of V so as to obtain an explicit estimate of V. The difference lies in that,
for nonlinear systems, V and V are not necessarily quadratic functions of the states.
Example 3.22: Consider again the system in Example 3.8. Given the chosen Lyapunov function
candidate V= ||x||2, the derivative V, can be written
V=2V(V- 1)
that is,
dV
- = -2dt
V(l-V)
The solution of this equation is easily found to be
9 /
CLP~
V(x)= 1 a + e ae~2'
where
1 - V(0)
If ||x(0)||2 = V(0) < I, i.e., if the trajectory starts inside the unit circle, then a > 0, and
V(t)<ae~2'
This implies that the norm ||x(/)|| of the state vector converges to zero exponentially, with a rate
of 1.
However, if the trajectory starts outside the unit circle, i.e., if V(0) > I, then a<0, so that

94 Fundamentals of Lyapunov Theory Chap. 3
V(i) and therefore ||x|| tend to infinity in a finite time (the system is said to exhibit finite escape
time, or "explosion"). I—I
3.6 Control Design Based on Lyapunov's Direct Method
The previous sections have been concerned with using Lyapunov's direct method for
system analysis. In doing the analysis, we have implicitly presumed that certain
control laws have been chosen for the systems. However, in many control problems,
the task is to find an appropriate control law for a given plant. In the following, we
briefly discuss how to apply Lyapunov's direct method for designing stable control
systems. Many of the controller design methods we will describe in chapters 6-9 are
actually based on Lyapunov concepts.
There are basically two ways of using Lyapunov's direct method for control
design, and both have a trial and error flavor. The first technique involves
hypothesizing one form of control law and then finding a Lyapunov function to justify
the choice. The second technique, conversely, requires hypothesizing a Lyapunov
function candidate and then finding a control law to make this candidate a real
Lyapunov function.
We saw an application of the first technique in the robotic P.D. control
example in section 3.5.4, where a P.D. controller is chosen based on physical intuition,
and a Lyapunov function is found to show the global asymptotic convergence of the
resulting closed-loop system. The second technique can be illustrated on the
following simple example.
Example 3.23: Regulator Design
Consider the problem of stabilizing the system
i.e., to bring it to equilibrium at x = 0. Based on Example 3.14, it is sufficient to choose a
continuous control law u of the form
where
i(i3 + u (i))<0 for i
1
x(x2 - u(x)) > 0 for
2
The above inequalities also imply that globally stabilizing controllers can be designed even in

Sect. 3.7 Summary 95
the presence of some uncertainty on the dynamics. For instance, the system
where the constants o^ and a are unknown, but such that CC[ > - 2 and lo^l < 5, can be globally
2
stabilized using the control law
u = -2p-5x\x\ •
For some classes of nonlinear systems, systematic design procedures have been
developed based on these above two techniques, as can be seen in chapter 7 on the
sliding control design methodology, in chapter 8 on adaptive control, and in chapter 9
on physically-motivated designs.
Finally, it is important to notice that, just as a nonlinear system may be globally
asymptotically stable while its linear approximation is only marginally stable, a
nonlinear system may be controllable while its linear approximation is not. Consider
for instance the system
x + x5 - x2 u
This system can be made to converge asymptotically to zero simply by letting u = - x.
However, its linear approximation at x = 0 and u = 0 is x ~ 0 , and therefore is
uncontrollable!
3.7 Summary
Stability is a fundamental issue in control system analysis and design. Various
concepts of stability, such as Lyapunov stability, asymptotic stability, exponential
stability, and global asymptotic or exponential stability, must be defined in order to
accurately characterize the complex and rich stability behaviors exhibited by nonlinear
systems.
Since analytical solutions of nonlinear differential equations usually cannot be
obtained, the two methods of Lyapunov are of major importance in the determination
of nonlinear system stability.
The linearization method is concerned with the small motion of nonlinear
systems around equilibrium points. It is mainly of theoretical value, justifying the use
of linear control for the design and analysis of weakly nonlinear physical systems.
The direct method, based on so-called Lyapunov functions, is not restricted to
small motions. In principle, it is applicable to essentially all dynamic systems, whether
L

96 Fundamentals of Lyapunov Theory Chap. 3
linear or nonlinear, continuous-time or discrete-time , of finite or infinite order, and in
small or large motion. However, the method suffers from the common difficulty of
finding a Lyapunov function for a given system. Since there is no generally effective
approach for finding Lyapunov functions, one has to use trial-and-error, experience,
and intuition to search for appropriate Lyapunov functions. Physical properties (such
as energy conservation) and physical insights may be exploited in formulating
Lyapunov functions, and may lead to uniquely powerful choices. Simple mathematical
techniques, such as, e.g., Krasovskii's method or the variable gradient method, can
also be of help.
Generally, the application of Lyapunov theory to controller design is more
easily rewarding. This is because, in design, one often has the freedom to deliberately
modify the dynamics (by designing the controller) in such a way that a chosen scalar
function becomes a Lyapunov function for the closed-loop system. In the second part
of the book, we will see many applications of Lyapunov theory to the construction of
effective nonlinear control systems.
3.8 Notes and References
In Lyapunov's original work [Lyapunov, 1892], the linearization method (which, today, is
sometimes incorrectly referred to as the first method) is simply given as an example of application of
the direct (or second) method. The first method was the so-called method of exponents, which is
used today in the analysis of chaos.
Many references can be found on Lyapunov theory, e.g., [La Salle and Lefschetz, 1961] (on
which the invariant set theorems are based), [Kalman and Bertram, 1960; Hahn, 1967; Yoshizawa,
1966]. An inspiring discussion of the role of scalar summarizing functions in science, along with a
very readable introduction to elementary Lyapunov theory, can be found in [Luenberger, 1979],
Examples 3.1 and 3.13 are adapted from [Luenberger, 1979]. Examples 3.3 and 3.8 are
adapted from [Vidyasagar, 1978]. The counterexample in Figure 3.12 is from [Hahn, 1967].
Example 3.14 is adapted from [La Salle and Lefschetz, 1961; Vidyasagar, 1978]. The variable
gradient method in subsection 3.5.3 is adapted from [Ogata, 1970]. The robotic example of section
3.5.4 is based on [Takegaki and Arimoto, 1981]. The remark on the "optimal" choice of Q in section
3.5.5 is from [Vidyasagar, 1982]. A detailed study of Krasovskii's theorems can be found in
[Krasovskii, 1963].

Sect. 3.9 Exercises 97
3.9 Exercises
3.1 The norm used in the definitions of stability need not be the usual Euclidian norm. If the state-
space is of finite dimension n (i.e., the state vector has n components), stability and its type are
independent of the choice of norm (all norms are "equivalent"), although a particular choice of norm
may make analysis easier. For n = 2 , draw the unit balls corresponding to the following norms:
(i) ||x||2 = (x)2 + (jf)2 (Euclidian norm)
l 2
(ii) ||x||2 = (x,)2 + 5(x)2
2
(iii) 11x11 = 1*, |+ |*1
2
(iv) ||x|| = Sup(|*,|,|*|)
2
Recall that a ball B(x , R), of center x and radius /?, is the set of x such that || x - xj| < R , and that
o 0
the unit ball is B(0, 1).
3.2 For the following systems, find the equilibrium points and determine their stability. Indicate
whether the stability is asymptotic, and whether it is global.
(a) x = — x3 + sin *
(b) i = (5-x)5
(c) x + x5 + x1 =JC2 sin8xcos23x
(d) x + (x-l)4i7+x5=*3sin3x
(e) * + (*- l)2x7 + x = sin(itx/2)
3.3 For the Van der Pol oscillator of Example 3.3, demonstrate the existence of a limit cycle using
the linearization method.
3.4 This exercise, adapted from [Hahn, 1967], provides an example illustrating the motivation of
the radial unboundedness condition in Theorem 3.3. Consider the second-order system
2(*, +x)
2
with z = 1 +X|2. On the hyperbola x = 2/(xj — "^ 2 ), the system trajectory slope is
2

98 Fundamentals of Lyapunov Theory Chap. 3
x2 _i
while the slope of the hyperbola is
dx i -23l2x + x^/2
x l
Note that for x, > ~\j~2 , the first expression is larger than the second, implying that the trajectories
cannot cut the branch of the hyperbola which lies in the first quadrant, in the direction toward the
axes (since on the hyperbola we have i, > 0 if JCJ > ~NJ2 ). Thus, there are trajectories which do not
tend toward the origin, indicating the lack of global asymptotic stability. Use the scalar function
x 2
V(x) = -L + x2
2
to analyze the stability of the above system.
3.5 Determine regions of attraction of the pendulum, using as Lyapunov functions the pendulum's
total energy, and the modified Lyapunov function of page 67. Comment on the two results.
3.6 Show that given a constant matrix M and any time-varying vector x, the time-derivative of the
scalar xr M x can be written
-xrMx = xT(M + MT)x = xr(M + Mr) x
dt
and that, if M is symmetric, it can also be written
-xTMx= 2 xr M x = 2 xr M x
dt
3.7 Consider an n x n matrix M of the form M = NrN , where NisamXn matrix. Show that M is
p.d. if, and only if, m > n and N has full rank.
3.8 Show that if M is a symmetric matrix such that
Vx, xrMx = 0
then M = 0.
3.9 Show that if symmetric p.d. matrices P and Q exist such that
ATP + P A + 2X.P = -Q
then all the eigenvalues of A have a real part strictly less than - X. (Adapted from [Luenberger,
1

Sect. 3.9 Exercises 99
1979].)
3.10 Consider the system
A,y + Aj + Ay = 0
2 3
where the 2n x 1 vector x = [yT yT]T is the state, and the n x n matrices A.j ace all symmetric
positive definite. Show that the system is globally asymptotically stable, with 0 as a unique
equilibrium point.
3.11 Consider the system
x = A x y = c^x
Use the invariant set theorem to show that if the system is observable, and if there exists a symmetric
p.d. matrix P such that
ATP + l
then the system is asymptotically stable.
Can the result be derived using the direct method? (Adapted from [Luenberger, 1979].)
3.12 Use Krasovskii's theorem to justify Lyapunov's linearization method.
3.13 Consider the system
x = 4x2y-f(x)(x2
l
y = -2xi-f (y)(x2
2
where the continuous functions /j and / have the same sign as their argument. Show that the
2
system tends towards a limit cycle independent of the explicit expressions of/| and/ .
2
3.14 The second law of thermodynamics states that the entropy of an isolated system can only
increase with time. How does this relate to the notion of a Lyapunov function?

Chapter 4
Advanced Stability Theory
In the previous chapter, we studied Lyapunov analysis of autonomous systems. In
many practical problems, however, we encounter non-autonomous systems. For
instance, a rocket taking off is a non-autonomous system, because the parameters
involved in its dynamic equations, such as air temperature and pressure, vary with
time. Furthermore, as discussed earlier, determining the stability of a nominal motion
for an autonomous system requires the stability analysis of an equivalent non-
autonomous system around an equilibrium point. Therefore, stability analysis
techniques for non-autonomous systems must be developed. This constitutes the major
topic of this chapter.
After extending the concepts of stability and the Lyapunov stability theorems to
non-autonomous systems, in sections 4.1 and 4.2, we discuss a number of interesting
related topics in advanced stability theory. Some Lyapunov theorems for concluding
instability of nonlinear systems are provided in section 4.3. Section 4.4 discusses a
number of so-called converse theorems asserting the existence of Lyapunov functions.
Besides their theoretical interest, these existence theorems can be valuable in some
nonlinear system analysis and design problems. In section 4.5, we describe a very
simple mathematical result, known as Barbalat's lemma, which can be conveniently
used to solve some asymptotic stability problems beyond the treatment of Lyapunov
stability theorems, and which we shall use extensively in chapters 8 and 9. In section
4.6, we discuss the so-called positive real linear systems and their unique properties,
which shall be exploited later in the book, particularly in chapter 8. Section 4.7
describes passivity theory, a convenient way of interpreting, representing, and
100

Sect. 4.1 Concepts of Stability for Non-Autonomous Systems 101
combining Lyapunov or Lyapunov-like functions. Section 4.8 discusses a special class
of nonlinear systems which can be systematically treated by Lyapunov analysis.
Section 4.9 studies some non-Lyapunov techniques which can be used to establish
boundedness of signals in nonlinear systems. Finally, section 4.10 discusses
mathematical conditions for the existence and unicity of solutions of nonlinear
differential equations.
4.1 Concepts of Stability for Non-Autonomous Systems
The concepts of stability for non-autonomous systems are quite similar to those of
autonomous systems. However, due to the dependence of non-autonomous system
behavior on initial time t , the definitions of these stability concepts include t
o 0
explicitly. Furthermore, a new concept, uniformity, is necessary to characterize non-
autonomous systems whose behavior has a certain consistency for different values of
initial time t . In this section, we concisely extend the stability concepts for
0
autonomous systems to non-autonomous systems, and introduce the new concept of
uniformity.
EQUILIBRIUM POINTS AND INVARIANT SETS
For non-autonomous systems, of the form
x = f(x, t) (4.1)
equilibrium points x are defined by
f(x*,0 = 0 Vt>t (4.2)
o
Note that this equation must be satisfied V t> t , implying that the system should be
o
able to stay at the point x* all the time. For instance, one easily sees that the linear
time-varying system
x = A(r)x (4.3)
has a unique equilibrium point at the origin 0 unless A(?) is always singular.
Example 4.1: The system
k = -*££- (4.4)
l+x2
has an equilibrium point at x = 0. However, the system

102 Advanced Stability Theory Chap. 4
x = - HQl. + fc(r) (4.5)
1+x2
with b(t) ^ 0, does not have an equilibrium point. It can be regarded as a system under external
input or disturbance b(f). Since Lyapunov theory is mainly developed for the stability of nonlinear
systems with respect to initial conditions, such problems of forced motion analysis are more
appropriately treated by other methods, such as those in section 4.9. LJ
The definition of invariant set is the same for non-autonomous systems as for
autonomous systems. Note that, unlike in autonomous systems, a system trajectory is
generally not an invariant set for a non-autonomous system (Exercise 4.1).
EXTENSIONS OF THE PREVIOUS STABILITY CONCEPTS
Let us now extend the previously defined concepts of stability, instability, asymptotic
stability, and exponential stability to non-autonomous systems. The key in doing so is
to properly include the initial time t in the definitions.
0
Definition 4.1 The equilibrium point 0 is stable at t if for any R>0, there exists a
0
positive scalar r{R,t ) such that
0
\\x(t )\\<r => \\x(t)\\<R Vr>f (4.6)
o o
Otherwise, the equilibrium point 0 is unstable.
Again, the definition means that we can keep the state in a ball of arbitrarily small
radius R by starting the state trajectory in a ball of sufficiently small radius r.
Definition 4.1 differs from definition 3.3 in that the radius r of the initial ball may
depend on the initial time t .
0
The concept of asymptotic stability can also be defined for non-autonomous
systems.
Definition 4.2 The equilibrium point 0 is asymptotically stable at time t if
o
• it is stable
• 3 r(t ) > 0 such that \\ x(t ) \\ < r{t ) => || x(t) || -» 0 as t -> oo
0 0 o
Here, the asymptotic stability requires that there exists an attractive region for every
initial time t . The size of attractive region and the speed of trajectory convergence
0
may depend on the initial time t .
0
The definitions of exponential stability and global asymptotic stability are also
straightforward.
i

Sect. 4.1 Concepts of Stability for Non-Autonomous Systems 103
Definition 4.3 The equilibrium point 0 is exponentially stable if there exist two
positive numbers, a and X, such that for sufficiently small x(t ) ,
o
Definition 4.4 The equilibrium point 0 is globally asymptotically stable if\/ x(/ )
0
x(f) -> 0 as t —> °°
Example 4.2: A first-order linear time-varying system
Consider the first-order system
x(t) = -a(t)x(t)
Its solution is
x(0 = x(r)exp[-f a(r)dr]
o
Thus, the system is stable if a(t) > 0, V l > t . It is asymptotically stable if f°° a(r) dr = + °° . It
0
is exponentially stable if there exists a strictly positive number T such that V / > 0,
f'+ a(r) dr > y, with y being a positive constant.
For instance,
• The system x = -x/( 1 + t)2 is stable (but not asymptotically stable).
• The system x = - x/(l + t) is asymptotically stable.
• The system x = — tx is exponentially stable.
Another interesting example is the system
1 + sinxz
whose solution can be expressed as
' -1
40=x(r
o
)exp[f -=—
Ji 1 +sinxz(r)
Since
r
1 , . <->o
i I +sinx2(V) - dr > 2

104 Advanced Stability Theory Chap. 4
the system is exponentially convergent with rate 1/2 . d ||
UNIFORMITY IN STABILITY CONCEPTS
The previous concepts of Lyapunov stability and asymptotic stability for non-
autonomous systems both indicate the important effect of initial time. In practice, it is
usually desirable for the system to have a certain uniformity in its behavior regardless
of when the operation starts. This motivates us to consider the definitions of uniform
stability and uniform asymptotic stability. As we shall see in later chapters, non-
autonomous systems with uniform properties have some desirable ability to withstand
disturbances. It is also useful to point out that, because the behavior of autonomous
systems is independent of the initial time, all the stability properties of an autonomous
system are uniform.
Definition 4.5 The equilibrium point 0 is locally uniformly stable if the scalar r in
Definition 4.1 can be chosen independently oft , i.e., ifr = r(R).
o
The intuitive reason for introducing the concept of uniform stability is to rule
out systems which are "less and less stable" for larger values of t . Similarly, the
0
definition of uniform asymptotic stability also intends to restrict the effect of the initial
time t on the state convergence pattern.
0
Definition 4.6 The equilibrium point at the origin is locally uniformly
asymptotically stable if
• it is uniformly stable
• There exists a ball of attraction B , whose radius is independent of t ,
R 0
such that any system trajectory with initial states in B converges to 0
R
uniformly in t
0
By uniform convergence in terms of t , we mean that for all R\ and R satisfying
0 2
0 < R < /?! < R , 3 T{R R ) > 0, such that, V t > 0,
2 o b 2 g
\\«S )\\<R\ => Hx(0ll<K Vr>f + r(/?!,/? )
0 2 o 2
i.e., the state trajectory, starting from within a ball B , will converge into a smaller
R
ball B after a time period T which is independent of t .
R 0
By definition, uniform asymptotic stability always implies asymptotic stability.
The converse is generally not true, as illustrated by the following example.

Sect. 4.2 Lyapunov Analysis of Non-Autonomous Systems 105
Example 4.3: Consider the first-order system
x
x = —
1 +t
This system has the general solution
40 = - r^ X{t)
I +t n"
This solution asymptotically converges to zero. But the convergence is not uniform. Intuitively,
this is because a larger t requires a longer time to get close to the origin. D
o
Using Definition 4.3, one can easily prove that exponential stability always
implies uniform asymptotic stability.
The concept of globally uniformly asymptotic stability can be defined by
replacing the ball of attraction B^ by the whole state space.
4.2 Lyapunov Analysis of Non-Autonomous Systems
We now extend the Lyapunov analysis results of chapter 3 to the stability analysis of
non-autonomous systems. Although many of the ideas in chapter 3 can be similarly
applied to the non-autonomous case, the conditions required in the treatment of non-
autonomous systems are more complicated and more restrictive. We start with the
description of the direct method. We then apply the direct method to the stability
analysis of linear time-varying systems. Finally, we discuss the linearization method
for non-autonomous nonlinear systems.
4.2.1 Lyapunov's Direct Method for Non-Autonomous Systems
The basic idea of the direct method, i.e., concluding the stability of nonlinear systems
using scalar Lyapunov functions, can be similarly applied to non-autonomous systems.
Besides more mathematical complexity, a major difference in non-autonomous
systems is that the powerful La Salle's theorems do not apply. This drawback will
partially be compensated by a simple result in section 4.5 called Barbalat's lemma.
TIME-VARYING POSITIVE DEFINITE FUNCTIONS AND DECRESCENT
FUNCTIONS
When studying non-autonomous systems using Lyapunov's direct method, scalar
functions with explicit time-dependence V(t, x) may have to be used, while in

106 Advanced Stability Theory Chap. 4
autonomous system analysis time-invariant functions V(x) suffice. We now introduce
a simple definition of positive definiteness for such scalar functions.
Definition 4.7 A scalar time-varying function V(x, t) is locally positive definite if
V(0, 0 = 0 and there exists a time-invariant positive definite function V (x) such that
o
Vf>( , V(x,t)>V (x) (4.7)
0 o
Thus, a time-variant function is locally positive definite if it dominates a
time-invariant locally positive definite function. Globally positive definite functions
can be defined similarly.
Other related concepts can be defined in the same way, in a local or a global
sense. A function V(x, t) is negative definite if - V(x, t) is positive definite; V(x, t) is
positive semi-definite if V(x, t) dominates a time-invariant positive semi-definite
function; V(x, t) is negative semi-definite if - V(x, t) is positive semi-definite.
In Lyapunov analysis of non-autonomous systems, the concept of decrescent
functions is also necessary.
Definition 4.8 A scalar function V(x, t) is said to be decrescent if V(Q,t) = 0, and if
there exists a time-invariant positive definite function V j(x) such that
V t > 0 , V(x,t)< V(x)
{
In other words, a scalar function V(x, t) is decrescent if it is dominated by a time-
invariant positive definite function.
Example 4.4: A simple example of a time-varying positive definite function is
V(x, r) = (1 +sin2r)(x,2 + x2)
2
because it dominates the function V(\) -x 2 + x2. This function is also decrescent because it is
o l 2
dominated by the function V,(x) = 2(x,2 + x2)- D
2
Given a time-varying scalar function V(x, t), its derivative along a system
trajectory is
^ av av/. 3v av
= + = + /(M (48)
at dt dx dt 3x
LYAPUNOV THEOREM FOR NON-AUTONOMOUS SYSTEM STABILITY
The main Lyapunov stability results for non-autonomous systems can be summarized
by the following theorem.

Sect. 4.2 Lyapunov Analysis of Non-Autonomous Systems 107
Theorem 4.1 (Lyapunov theorem for non-autonomous systems)
Stability: If, in a ball B around the equilibrium point 0, there exists a scalar
R
function V(x, t) with continuous partial derivatives such that
1. V is positive definite
2. V is negative semi-definite
then the equilibrium point 0 is stable in the sense of Lyapunov.
Uniform stability and uniform asymptotic stability: If, furthermore,
3. V is decrescent
then the origin is uniformly stable. If condition 2 is strengthened by requiring that
V be negative definite, then the equilibrium point is uniformly asymptotically
stable.
Global uniform asymptotic stability: If the ball B is replaced by the whole state
R
space, and condition 1, the strengthened condition 2, condition 3, and the condition
4. V(x, 0 is radially unbounded
are all satisfied, then the equilibrium point at 0 is globally uniformly
asymptotically stable.
Similarly to the case of autonomous systems, if, in a certain neighborhood of
the equilibrium point, V is positive definite and V, its derivative along the system
trajectories, is negative semi-definite, then V is called a Lyapunov function for the
non-autonomous system.
The proof of this important theorem, which we now detail, is rather technical.
Hurried readers may skip it in a first reading, and go directly to Example 4.5.
In order to prove the above theorem, we first translate the definitions of positive definite
functions and decrescent functions in terms of the so-called class-K functions.
Definition 4.9 A continuous function a: R+ —> R+ is said to be of class K for to belong to class
K),if
• <x(0) = 0
• a(p) > 0 Vp > 0
• a is non-decreasing

108 Advanced Stability Theory Chap. 4
The following lemma indicates the relation of positive definite and decrescent functions to
class K functions.
Lemma 4.1: A function V(x, t) is locally (or globally) positive definite if, and only if, there exists a
function a of class K such that V(0,0 = 0 and
V(x, t) > a(||x||) (4.9)
V (> 0 and VxeBg (or the whole state space).
A function V(x, t) is locally (or globally) decrescent if and only if there exists a class K
function (3 such that V(0, () = 0 and
V(x, r) < p(l(x|{) (4.10)
V t > 0 and V x e B^ (or in the whole state space).
Proof: Let us prove the positive definite function part first. Sufficiency is obvious from the
definition, because a(||x||) itself is a scalar time-invariant positive definite function. We now
consider necessity, i.e., assume that there exists a time-invariant positive function V(x) such that
0
V(x, t) > V(x), and show that a function a of class K exists such that (4.9) holds. Let us define
o
a(p)= inf V(x) (4.11)
o
p £ IMI £ R
Then, oc(0) = 0, a is continuous and non-decreasing. Because V(x) is a continuous function and
0
non-zero except at 0, <x(p) > 0 for p > 0. Therefore, a is a class K function. Because of (4.11),
(4.9) is satisfied.
The second part of the lemma can be proven similarly, with the function P defined by
P(p) = sup V,(x) (4.12)
0 < ||x|| < p
where Vj(x) is the time-invariant positive function in Definition 4.8. D
Given the above lemma, we can now restate Theorem 4.1 as follows:
Theorem 4.1 Assume that, in a neighborhood of the equilibrium point 0, there exists a scalar
function V(x, () with continuous first order derivatives and a class-K function a such that, Vx ^t 0
2a. V(x, ()<0
then the origin 0 is Lyapunov stable. If, furthermore, there is a scalar class-K function P such that
J
3. Hx,r)<P(||x||)

| Sect. 4.2  | Lyapunov Analysis of Non-Autonomous Systems  |     | 109 |
| ---------- | -------------------------------------------- | --- | --- |
then 0 is uniformly stable. If conditions 1 and 3 are satisfied and condition 2a is replaced by
condition 2b
with y being another class-K function,  then 0 is uniformly asymptotically stable.  If conditions 1, 2b
and 3 are satisfied in the whole state space, and
lim  <x(||x|j)->°°
x-> °°
then 0 is globally uniformly asymptotically stable.
Proof: We derive the three parts of the theorem in sequence.
Lyapunov stability: To establish Lyapunov stability, we must show that given R > 0, there exists
| r > 0 such that (4.6) is satisfied.                                            | Because of conditions 1 and 2a, |          |        |
| ------------------------------------------------------------------------------ | ------------------------------- | -------- | ------ |
| <x(||x(0||) < V[x(f),'] * V[x(t), y                                            |                                 | Vt > t   | (4.13) |
|                                                                                | o                               | o        |        |
| Because V is continuous in terms of x and V(0, t) = 0, we can find r such that |                                 | o        |        |
\\x(t)\\<r  =>  V(x(t),t)<a(R)
o o o
This means that if ||x(/)|| < r, then a(||x(/)j|) < a(R), and, accordingly, ||x(0|| <R , Vt> t .
| 0   |     |     | o   |
| --- | --- | --- | --- |
Uniform stability and uniform asymptotic stability: From conditions 1 and 3,
<x(||xMII) < V(x(t), t) < P(||x(0||)
For any R > 0, there exists r(R) > 0 such that (}(r) < a(R) (Figure 4.1). Let the initial condition
| x(t) be chosen such that ||x(/)|| < r. Then 0 | 0   |     |     |
| --------------------------------------------- | --- | --- | --- |
a(R) > P(r) > V[x(t), t] > V[x(t), t] > a(||x(0ll)
o o
This implies that
Vt>tn,  \\x(t)\\<R
| Uniform stability is asserted because r is independent of t |     |  .  |     |
| ----------------------------------------------------------- | --- | --- | --- |
o
In establishing uniform asymptotic stability, the basic idea is that if x does not converge to
the origin, then it can be shown that there is a positive number a such that - V [x(t), t] > a > 0 .
This implies that
V[x(t), t] - V[x(t),  t]=\'vdt<-(t-t)a
|     | o o | 0   |     |
| --- | --- | --- | --- |

110 Advanced Stability Theory Chap. 4
p (llxll)
V(x,t)
a(llxll)
Figure 4.1 : A positive definite and
R llxll
decrescent function
and thus, that
0<V[x(t),t]<V[x(t ),t ]-(t-t )a
o o 0
which leads to a contradiction for large (. Let us now detail the proof.
Let ||x(g || < r, with r obtained as before. Let n be be any positive constant such that
0 <(i < || x(g ||. We can find another positive constant 8(|X) such that (5(8)< a(n.). Define e = 7(5)
and set
Then, if ||x(r)|| > |i for all t in the period t < t < t H t + T, we have
0 y 0
O'< a(u.) < V[x(r,),t!]< V[x(r,g- f'VllxWID* < V[x{t),t)} - f
o o o
< V[x(f ), g - (f[ - ge < P(r) - Te = 0
0
This is a contradiction, and so there must exist l 6 ['.'il s»cn that ||x(()|| < 5 . Thus, for all
2 o 2
t>,.
2
a(||x(0ll) < V[x((),(] < V[x(r),(] < P(8) < a(ji)
2 2
As a result,
||x(0i|<M- Vr>(+T>f
o 2
which shows uniform asymptotic stability.
Global uniform asymptotic stability: Since a() is radially unbounded, R can be found such that
P(r) < a(R) for any ;\ In addition, /• can be made arbitrarily large. Hence, the origin x = 0 is
globally uniformly asymptotically stable. O

Sect. 4.2 Lyapunov Analysis of Non-Autonomous Systems 111
Example 4.5: Global Asymptotic Stability
Consider the system defined by
i,M = -*,(»)-e-2'jc(0
2
x(t) = x(t)-x(t)
2 ] 2
To determine the stability of the equilibrium point at 0, let us choose the following scalar function
This function is positive definite, because it dominates the time-invariant positive function
X|2 + x2. I' 's a'so decrescent, because it is dominated by the time-invariant positive definite
2
function x 2 + 2x2. Furthermore,
i 2
This shows that
Thus, V is negative definite, and therefore, the point 0 is globally asymptotically stable. IH
Stability results for non-autonomous systems can be less intuitive than those for
autonomous systems, and therefore, particular care is required in applying the above
theorem, as we now illustrate with two simple examples.
For autonomous systems, the origin is guaranteeed to be asymptotically stable if
V is positive definite and V is negative definite. Therefore, one might be tempted to
conjecture that the same conditions are sufficient to guarantee the asymptotic stability
of the system. However, this intuitively appealing statement is incorrect, as
demonstrated by the following counter-example.
Example 4.6: Importance of the decrescence condition
Let g(t) be a continuously-differentiable function which coincides with the function e~'12 except
around some peaks where it reaches the value 1. Specifically, g2(t) is shown in Figure 4.2. There
is a peak for each integer value of (. The width of the peak corresponding to abcissa n is assumed
to be smaller than (1/2)". The infinite integral of g2 thus satisfies
f g\r)dr < I e~rdr + T — = 2
and therefore, the scalar function

| 112  Advanced Stability Theory |     | Chap. 4 |
| ------------------------------ | --- | ------- |
|                                | v2  | (4.14)  |
V(x, 0 = -
| gl(t)                             | Jo    |     |
| --------------------------------- | ----- | --- |
| is positive definite ( V(\, t) >  | x1).  |     |
| 01                                | g2(t) |     |
Figure 4.2: The function
Now consider the first-order differential equation
(4.15)
g{i)
If we choose V(x, t) in (4.14) as the Lyapunov function candidate, we easily find that
V = - X 2
| i.e., V is negative definite.                      | Yet, the general solution of (4.15) is |     |
| -------------------------------------------------- | -------------------------------------- | --- |
| and hence the origin is not asymptotically stable. |                                        | •   |
Since the positive definiteness of V and the negative semi-definiteness of V are
already sufficient to guarantee the Lyapunov stability of the origin, one may wonder
what additional property the negative definiteness of V does provide.  It can be shown
that, if V is negative definite, then an infinite sequence r,'s (/ = 1, 2,...) can be found
such that the corresponding state values \(tj) converge to zero as i —> °° (a result of
mostly theoretical interest).
Another illustration that care is required before jumping to conclusions involves
the following interesting second-order dynamics
| x + c{t)'x + k | x = 0 | (4.16) |
| -------------- | ----- | ------ |
o
which can represent a mass-spring-damper system (of mass 1), where  c(t) >0  is a
time-varying damping coefficient, and k  is a spring constant.  Physical intuition may
o
suggest that the equilibrium point (0,0) is asymptotically stable as long as the damping

Sect. 4.2 Lyapunov Analysis of Non-Autonomous Systems 113
c(t) remains larger than a strictly positive constant (implying constant dissipation of
energy), as is the case for autonomous nonlinear mass-spring-damper systems.
However, this is not necessarily true. Indeed, consider the system
x + (2+e')x + x = 0
One easily verifies that, for instance, with the initial condition JC(O) = 2, x(0) = -1, the
solution is x(t) - 1 + e~l, which tends to x = 1 instead! Here the damping increases so
fast that the system gets "stuck" at x = 1.
Let us study the asymptotic stability of systems of the form of (4.16), using a
Lyapunov analysis.
Example 4.7: Asymptotic stability with time-varying damping
Lyapunov stability of the system (although not its asymptotic stability) can be easily established
using the mechanical energy of the system as a Lyapunov function. Let us now use a different
Lyapunov function to determine sufficient conditions for the asymptotic stability of the origin for
the system (4.16). Consider the following positive definite function
,
K ( xo +x
where a is any positive constant smaller than -J k , and
o
Kcan be easily computed as
V=la-c(t)]i2 + ^{c(!)-2k }x2
o
Thus, if there exist positive numbers a and (5 such that
c(/)>a>0 c(f)<P<2/t
o
then V is negative definite. Assuming in addition that c(t) is upper bounded (guaranteeing the
decrescence of I7), the above conditions imply the asymptotic convergence of the system.
It can be shown [Rouche, et al., 1977] that, actually, the technical assumption that c(t) is
upper bounded is not necessary. Thus, for instance, the system
is asymptotically stable. [J

114 Advanced Stability Theory Chap. 4
4.2.2 Lyapunov Analysis of Linear Time-Varying Systems
None of the standard approaches for analyzing linear time-invariant systems (e.g.,
eigenvalue determination) applies to linear time-varying systems. Thus, it is of
interest to consider the application of Lyapunov's direct method for studying the
stability of linear time-varying systems. Indeed, a number of results are available in
this regard. In addition, in view of the relation between the stability of a non-
autonomous system and that of its (generally time-varying) linearization, to be
discussed in section 4.2.3, such results on linear time-varying systems can also be of
practical importance for local stability analysis of nonlinear non-autonomous systems.
Consider linear time-varying systems of the form
x = A(r) x (4.17)
Since LTI systems are asymptotically stable if their eigenvalues all have negative real
parts, one might be tempted to conjecture that system (4.17) will be stable if at any
time t > 0, the eigenvalues of A(t) all have negative real parts. If this were indeed the
case, it would make the analysis of linear time-varying systems very easy. However,
this conjecture is not true.
Consider for instance the system
-1 e2t~ x
x
= (4.18)
0 -1 x
2
The eigenvalues of the matrix A(/) are both equal to - 1 at all times. Yet, solving first
for x and then substituting in the x equation, one sees that the system verifies
2 x
x = x(0) e~< x+x= x(0) e'
2 2 x x 2
and therefore is unstable, since x\ can be viewed as the output of a first-order filter
whose input x (0) e' tends to infinity.
2
A simple result, however, is that the time-varying system (4.17) is
asymptotically stable if the eigenvalues of the symmetric matrix A(0 + AT(t) (all of
which are real) remain strictly in the left-half complex plane
3\>0,\/i,\/t>0, \j(A(t) + Ar(0) < - *- (4.19)
This can be readily shown using the Lyapunov function V = x^x, since

Sect. 4.2 Lyapunov Analysis of Non-Autonomous Systems 115
V = xTx + xTx = xr (A(f) + AT(t)) x<-XxTx = -lV
so that
V t > 0 , 0 < xrx = V(t) < V(0) e-Xt
and therefore x tends to zero exponentially.
Of course, the above result also applies in case the matrix A depends explicitly
on the state. It is also important to notice that the result provides a sufficient condition
for asymptotic stability (some asymptotically stable systems do not verify (4.19), see
Exercise 4.8).
A large number of more specialized theorems are available to determine the
stability of classes of linear time-varying systems. We now give two examples of such
results. The first result concerns "perturbed" linear systems, i.e., systems of the form
(4.17), where the matrix A(t) is a sum of a constant stable matrix and some "small"
time-varying matrix. The second result is a more technical property of systems such
that the matrix A(t) maintains all its eigenvalues in the left-half plane and satisfies
certain smoothness conditions .
Perturbed linear systems
Consider a linear time-varying system of the form
x = (A, + A (?)) x (4.20)
2
where the matrix Aj is constant and Hurwitz (i.e., has all its eigenvalues strictly in the
left-half plane), and the time-varying matrix A (?) is such that
2
A (0 -> 0 as t -> °°
2
and
oo
J II A (0 II dt < °° (i.e, the integral exists and is finite)
2
Then the system (4.20) is globally exponentially stable.
Example 4.8: Consider the system
X2 = ~ X2 + 4 X3 2
.v3 = - (2 + sin I) jr3

| 116  Advanced Stability Theory  |     |     |     | Chap. 4 |
| ------------------------------- | --- | --- | --- | ------- |
Since JC tends to zero exponentially, so does JC2, and therefore, so does x-  Applying the above
| 3   |     | 3   | 2   |     |
| --- | --- | --- | --- | --- |
result to the first equation, we conclude that the system is globally exponentially stable.  CD
Sufficient smoothness conditions on the A(0 matrix
Consider the linear system (4.17), and assume that at any time t > 0, the eigenvalues of
A(t) all have negative real parts
| 3a>0,Vi,Vr>0,yA(0]<-a  |     |     |     | (4.21) |
| ---------------------- | --- | --- | --- | ------ |
! If, in addition, the matrix A(?) remains bounded, and
oo
AT(t) A(t) dt < °°
| f   |     | (i.e, the integral exists and is finite) |     |     |
| --- | --- | ---------------------------------------- | --- | --- |
I
then the system is globally exponentially stable.
4.2.3  * The Linearization Method for Non-Autonomous Systems
I  Lyapunov's linearization method can also be developed for non-autonomous systems.
1  Let a non-autonomous system be described by (4.1) and 0 be an equilibrium point.
Assume that f is continuously differentiable with respect to x. Let us denote
I
(4.22)
Then for any fixed time t (i.e., regarding t as a parameter), a Taylor expansion of f
leads to
If f can be well approximated by A(t)x for any time t, i.e.,
| Urn  sup     | h-°J *'  | = 0  Vf>0  |     | (4.23) |
| ------------ | -------- | ---------- | --- | ------ |
| ||x||  -> 0  | ||X||    |            |     |        |
then the system
| x = A(r)x  |     |     |     | (4.24) |
| ---------- | --- | --- | --- | ------ |
is  said to be  the  linearization  (or  linear  approximation) of the  nonlinear  non-
autonomous system (4.1) around equilibrium point 0.
Note that
J

Sect. 4.3 * Instability Theorems 117
• The Jacobian matrix A thus obtained from a non-autonomous nonlinear
system is generally time-varying, contrary to what happens for autonomous
nonlinear systems. But in some cases A is constant. For example, the
nonlinear system x = -x + x2/t leads to the linearized system x = -x.
• Our later results require that the uniform convergence condition (4.23) be
satisfied. Some non-autonomous systems may not satisfy this condition, and
Lyapunov's linearization method cannot be used for such systems. For
example, (4.23) is not satisfied for the system x - -x + tx1.
Given a non-autonomous system satisfying condition (4.23), we can assert its
(local) stability if its linear approximation is uniformly asymptotically stable, as stated
in the following theorem:
Theorem 4.2 If the linearized system (with condition (4.23) satisfied) is uniformly
asymptotically stable, then the equilibrium point 0 of the original non-autonomous
system is also uniformly asymptotically stable.
Note that the linearized time-varying system must be uniformly asymptotically
stable in order to use this theorem. If the linearized system is only asymptotically
stable, no conclusion can be drawn about the stability of the original nonlinear system.
Counter-examples can easily verify this point.
Unlike Lyapunov's linearization method for autonomous systems, the above
theorem does not relate the instability of the linearized time-varying system to that of
the nonlinear system. There does exist a simple result which infers the instability of a
non-autonomous system from that of its linear approximation, but it is applicable only
to non-autonomous systems whose linear approximations are time-invariant.
Theorem 4.3 // the Jacobian matrix A(0 is constant, A(t) = A , and if (4.23) is
o
satisfied, then the instability of the linearized system implies that of the original non-
autonomous nonlinear system, i.e., (4.1) is unstable if one or more of the eigenvalues
of A has a positive real part.
o
*
4.3 Instability Theorems
The preceding study of Lyapunov's direct method is concerned with providing
sufficient conditions for stability of nonlinear systems. This section provides some
instability theorems based on Lyapunov's direct method.
Note that, for autonomous systems, one might think that the conclusive results
provided by Lyapunov's linearization method are sufficient for the study of instability.

| 118  | Advanced Stability Theory  |     | Chap. 4  | |J  |
| ---- | -------------------------- | --- | -------- | --- |
However, in some cases, instability theorems based on the direct method may be
advantageous.  Indeed, if the linearization method fails (i.e., if the linearized system is
marginally stable), these theorems may be used to determine the instability of the
nonlinear system.  Another advantage may be convenience, since the theorems do not
require linearization of the system equations.
We state the theorems directly in a non-autonomous setting. For autonomous
systems, the conditions simplify in a straightforward fashion.
Theorem 4.4 (First instability theorem)  If, in a certain neighborhood Q of the
origin, there exists a continuously differentiable, decrescent scalar function V(x, t)
such that
|     | • V(0, 0=0  V t > t |     |     |     |
| --- | ------------------- | --- | --- | --- |
0
• V(x, t 0 ) can assume strictly positive values arbitrarily close to the origin
• V(x, 0 is positive definite (locally in Q.)
| then the equilibrium point 0 at time t |     |  is unstable. |     |     |
| -------------------------------------- | --- | ------------- | --- | --- |
0
Note that the second condition is weaker than requiring the positive definiteness
V(x) = jti2 - x 2
of V.  For example, the function  is obviously not positive definite,
2
but it can assume positive values arbitrarily near the origin (V(x) = Xj2 along the line
Example 4.9: Consider the system
|     | x, = 2x+x,(x,2 + 2x4)  |     | (4.26) |     |
| --- | ---------------------- | --- | ------ | --- |
|     | 2                      | 2   |        |     |
x = -2x, + .v(x,2 + x4)
|                                                                                                | 2 2 | 2   | (4.27) |     |
| ---------------------------------------------------------------------------------------------- | --- | --- | ------ | --- |
| Linearization of this system yields Jt, = 2x and x = - 2xj. The eigenvalues of this system are |     | 2 2 |        |     |
+ 2) and  - 2y", indicating the inability of Lyapunov's  linearization  method for this system.
However, if we take
2  x\  X1
its derivative is
Because of the positive definiteness of V and V, the above theorem indicates the instability of the
system.

| Sect. 4.3  |     |     | Instability Theorems  | 119 |
| ---------- | --- | --- | --------------------- | --- |
Theorem 4.5 (Second instability theorem)  If, in a certain neighborhood Q. of the
origin, there exists a continuously differentiable, decrescent scalar function  V(x, t)
satisfying
• V(0, t ) = 0  and  V(x, t ) can assume strictly positive values arbitrarily
|     | 0   | 0   |     |     |
| --- | --- | --- | --- | --- |
close to the origin
|     | • V(x, t) - X V(x, t) > 0  | V t > t |   VxeQ |     |
| --- | -------------------------- | ------- | ------ | --- |
0
with X being a strictly positive constant, then the equilibrium point 0 at time t  is
0
unstable.
Example 4.10: Consider the system described by
|     | X] = X| + 3xsin2x  | + 5xjX2sin2X|      |     | (4.28) |
| --- | ------------------ | ------------------ | --- | ------ |
|     |                    | 2 2 2              |     |        |
|     | x  = 3xj sin2x     | + x  -  5x2xcos2x  |     | (4.29) |
|     | 2                  | 2 2 1 2            | 1   |        |
Let us consider the function  K(x) = (l/2)(Xj2 —x2) , which was shown earlier to assume
2
positive values arbitrarily near the origin. Its derivative is
|     | V = x,2-x2  | + 5x,2x2  = 2V  | + 5x,2x2 |     |
| --- | ----------- | --------------- | -------- | --- |
|     | 2           | 2               | 2        |     |
Thus, the second instability theorem shows that the equilibrium point at the origin is unstable. Of
course, in this particular case, the instability could be predicted more easily by the linearization
| method.  |     |     |     | CD  |
| -------- | --- | --- | --- | --- |
In order to apply the above two theorems, V is required to satisfy  certain
conditions at all points in the neighborhood £2.  The following theorem (Cetaev's
theorem) replaces theses conditions by a boundary condition on a subregion in O.
Theorem 4.6 (Third instability theorem)  Let Q. be a neighborhood of the origin.
If there exists a scalar function  V(x, 0  with continuous first partial derivatives,
decrescent in Q, and a region O/ in O, such that
• K(x, t) and V(\, t) are positive definite in Qj
• The origin is a boundary point ofQ./
• At the boundary points ofQ.] within Q, V(x, t) = Ofor all  t>t
0
| then the equilibrium point 0 at time t |     |  is unstable. |     |     |
| -------------------------------------- | --- | ------------- | --- | --- |
o
The geometrical meaning of this theorem can be seen from Figure 4.3. Let us
illustrate the use of this theorem on a simple example.

120 Advanced Stability Theory Chap. 4
n (V>o
1
V>0)
Figure 4.3 : Geometrical interpretation of
the third instability theorem
Example 4.11: Consider the system
The linearization of this system leads to a pole at the origin and a pole at - 1. Therefore,
Lyapunov's linearization method cannot be used to determine the stability of this nonlinear
system. Now let us take the function V = x, - x2/2. Its derivative is
2
Examining V and V and using Cetaev's theorem, one can show the instability of the origin. •
4.4 * Existence of Lyapunov Functions
In the previous Lyapunov theorems, the existence of Lyapunov functions is always
assumed, and the objective is to deduce the stability properties of the systems from the
properties of the Lyapunov functions. In view of the common difficulty in finding
Lyapunov functions, one may naturally wonder whether Lyapunov functions always
exist for stable systems. A number of interesting results concerning the existence of
Lyapunov functions, called converse Lyapunov theorems, have been obtained in this
regard. For many years, these theorems were thought to be of no practical "value
because, like the previously described theorems, they do not tell us how to generate
Lyapunov functions for a system to be analyzed, but only represent comforting
reassurances in the search for Lyapunov functions. In the past few years, however,
there has been a resurgence of interest in these results. The reason is that a subsystem
of a nonlinear system may be known to possess some stability properties, and the
converse theorems allow us to construct a Lyapunov function for the subsystem,
which may subsequently lead to the generation of a Lyapunov function for the whole
system. In particular, the converse theorems can be used in connection with stability

Sect. 4.4 * Existence of Lyapunov Functions 121
analysis of feedback linearizable systems and robustness analysis of adaptive control
systems.
THE CONVERSE THEOREMS
There exists a converse theorem for essentially every Lyapunov stability theorem
(stability, uniform stability, asymptotic stability, uniform asymptotic stability, global
uniform asymptotic stability and instability). We now present three of the converse
theorems.
Theorem 4.7 (stability) If the origin of (4.1) is stable, there exists a positive
definite function V(x, t) with a non-positive derivative.
This theorem indicates the existence of a Lyapunov function for every stable system.
Theorem 4.8 (uniform asymptotic stability) If the equilibrium point at the origin
is uniformly asymptotically stable, there exists a positive definite and decrescent
function V(x, t) with a negative definite derivative.
This theorem is theoretically important because it will later be useful in establishing
robustness of uniform asymptotic stability to persistent disturbance.
The next theorem on exponential stability has more practical value than the
second theorem, because its use may allow us to explicitly estimate convergence rates
in some nonlinear systems.
Theorem 4.9 (exponential stability) If the vector function f(x, t) in (4.1) has
continuous and bounded first partial derivatives with respect to x and t,for all x in a
ball B,. and for all t>0, then the equilibrium point at the origin is exponentially stable
if, and only if, there exists a function V(x, t) and strictly positive constants o.j, OLj, (Xj,
a such that V x e B,., V t > 0
4
cqIMI2 < V(x,t) < a ||x||2 (4.30)
2
V<-a ||x||2 (4.31)
3
ll^ll ^ oc ||x|| (4.32)
4
d x
The proofs of the converse theorems typically assume that the solution of the
system is available, and then construct a Lyapunov function based on the assumed
solution [Hahn, 1967]. Proof of Theorem 4.9 can be found in [Bodson, 1986; Sastry
andBodson, 1989].

122 Advanced Stability Theory Chap. 4
4.5 Lyapunov-Like Analysis Using Barbalat's Lemma
For autonomous systems, the invariant set theorems are powerful tools to study
stability, because they allow asymptotic stability conclusions to be drawn even when
V is only negative .se/Mj-definite. However, the invariant set theorems are not
applicable to non-autonomous systems. Therefore, asymptotic stability analysis of
non-autonomous systems is generally much harder than that of autonomous systems,
since it is usually very difficult .to find Lyapunov functions with a negative definite
derivative. An important and simple result which partially remedies this situation is
Barbalat's lemma. Barbalat's lemma is a purely mathematical result concerning the
asymptotic properties of functions and their derivatives. When properly used for
dynamic systems, particularly non-autonomous systems, it may lead to the satisfactory
solution of many asymptotic stability problems.
4.5.1 Asymptotic Properties of Functions and Their Derivatives
Before discussing Barbalat's lemma itself, let us clarify a few points concerning the
asymptotic properties of functions and their derivatives. Given a differentiable
function/of time t, the following three facts are important to keep in mind.
• /—> 0 ?t> /converges
The fact that/(0 —> 0 does not imply that/(f) has a limit as t —> °° .
Geometrically, a diminishing derivative means flatter and flatter slopes. 'i
However, it does not necessarily imply that the function approaches a limit.
Consider, for instance, the rather benign function/(0 = sin(log t). While
cos(loe t)
= —v B ' -> 0 n as t-*°°
t
the function/(0 keeps oscillating (slower and slower). The function fit)
may even be unbounded, as with/(f) = -\[7 sin(log f). Note that functions of
the form log t, sin t, e01, and combinations thereof, are quite easy to find in
dynamic system responses.
/converges &> /—»0
The fact that/(r) has a finite limit as t —> °° does not imply that/(f) -> 0.
For instance, while the function/(f) = e~' sin(e2') tends to zero, its derivative
/is unbounded. Note that this is not linked to the frequent sign changes of the
1

Sect. 4.5 Lyapunov-Like Analysis Using Barbalat's Lemma 123
function. Indeed, with/(?) = e~' sin2(e2') > 0 ,/ is still unbounded.
• If /is lower bounded and decreasing (/<0), then it converges to a
limit.
This is a standard result in calculus. However, it does not say whether the
slope of the curve will diminish or not.
4.5.2 Barbalat's Lemma
Now, given that a function tends towards a finite limit, what additional requirement
can guarantee that its derivative actually converges to zero? Barbalat's lemma
indicates that the derivative itself should have some smoothness. More precisely, we
have
Lemma 4.2 (Barbalat) If the differentiable function f{i) has a finite limit as
t —> °°, and if f is uniformly continuous, then f(t) —> 0 as t —> °° .
Before proving this result, let us define what we mean by uniform continuity.
Recall that a function g(t) is continuous on [0, °°) if
Vff>0, V R>0,3T)(R,t)>0, V?>0, U-r,l<T| => \g(t)-g(t)l<R
l t
A function g is said to be uniformly continuous on [0, °°) if
VR>0,3r\(R)>0;Vt>0,Vt>0, \t-t\<r\ => lg(0-g('i)l <R
l l
In other words, g is uniformly continuous if one can always find an T) which does not
depend on the specific point f j - and in particular, such that T| does not shrink as
?1 —¥ °°, as shall be important when proving the lemma. Note that t and fj play a
symmetric role in the definition of uniform continuity.
Uniform continuity of a function is often awkward to assert directly from the
above definition. A more convenient approach is to examine the function's derivative.
Indeed, a very simple sufficient condition for a differentiable function to be uniformly
continuous is that its derivative be bounded. This can be easily seen from the finite
difference theorem
Vf,Vf[, 3 t (between rand t^ such that g(t) - g(t^) = g(t) (t- t)
2 2 {
and therefore, if R>0 is an upper bound on the function l£l , one can always use
l
T| = R/R j independently of /j to verify the definition of uniform continuity.

124  Advanced Stability Theory  Chap. 4
Let us now prove Barbalat's lemma, by contradiction.
Proof of Barbalat's lemma: Assume that f(t)  does not approach zero as (-> °°.  Then
3 e > 0, V T > 0 , 3 t > T,  1/(0 I > e . Therefore, we can get an infinite sequence of /,'s (such
| 0                                                                                                    | o                     |     |
| ---------------------------------------------------------------------------------------------------- | --------------------- | --- |
| that (,- —> °° as ( —> °o) such that l/(f,-) I ^ R • Since/(0 is assumed to be uniformly continuous, |                       | o   |
| 3 r| > 0, such that for any / and (                                                                  | satisfying \t —t \<v\ |     |
\hn -/('")i <~
This implies that for any t within the ^-neighborhood of t (i.e., such that 1/ - (,1 < r\)
i
1/(0 I >y
Hence, for all r,
;
| iiffr   ',+y\  •   | r' ;+ T l  •      | eo  |
| ------------------ | ----------------- | --- |
| f ( t)dt\ = ff     |   '   1 / 1(0* ^  | ^   |
| '-n                | '-ri              | l   |
where the left equality comes from the fact that / keeps a constant sign over the integration
| interval, due to the continuity of/and the bound 1/(0 I > e/2 > 0 . |     | o   |
| ------------------------------------------------------------------- | --- | --- |
This result would contradict the known fact that the integral [ f(r)dr  has a limit (equal to
/(oo) _/(0)) as t -> oo .  •
Given the simple sufficient condition for uniform continuity mentioned earlier,
an immediate and practical corollary of Barbalat's lemma can be stated as follows: (/
the differentiable function f (t) has a finite limit as f-> °°, and is such that f exists
and is bounded, thenf{t) —> 0 as t —> °° .
The following  example  illustrates  how to assert the uniform  continuity of
signals in control systems.
Example 4.12: Consider a strictly stable linear system whose input is bounded. Then the system
output is uniformly continuous.
Indeed, write the system in the standard form
x = A x + B u
y =  Cx
Since u is bounded and the linear system is strictly stable, thus the state x is bounded. This in turn
implies from the first equation that x is bounded, and therefore from the second equation that

Sect. 4.5 Lyapunov-Like Analysis Using Barbalat's Lemma 125
y = C x is bounded. Thus the system output y is uniformly continuous. D
USING BARBALAT'S LEMMA FOR STABILITY ANALYSIS
To apply Barbalat's lemma to the analysis of dynamic systems, one typically uses the
following immediate corollary, which looks very much like an invariant set theorem in
Lyapunov analysis:
Lemma 4.3 ("Lyapunov-Like Lemma") If a scalar function V(x, t) satisfies the
following conditions
• V(x, t) is lower bounded
• V^x, t) is negative semi-definite
• V^x, t) is uniformly continuous in time
then V{x, t) -» 0 as t ->°«.
Indeed, V then approaches a finite limiting value VQO, such that Voo 2 V (x(0), 0) (this
does not require uniform continuity). The above lemma then follows from Barbalat's
lemma.
To illustrate this procedure, let us consider the asymptotic stability analysis of a
simple adaptive control system.
Example 4.13: As we shall detail in chapter 8, the closed-loop error dynamics of an adaptive
control system for a first-order plant with one unknown parameter is
e = -e + 6w(t)
Q = -ew(t)
where e and 8 are the two states of the closed-loop dynamics, representing tracking error and
parameter error, and w{t) is a bounded continuous function (in the general case, the dynamics has
a similar form but with e, 0, and w(t) replaced by vector quantities). Let us analyze the
asymptotic properties of this system.
Consider the lower bounded function
Its derivative is
This implies that V(t) < V(0), and therefore, that e and 9 are bounded. But the invariant set

126 Advanced Stability Theory Chap. 4
theorems cannot be used to conclude the convergence of e, because the dynamics is non-
autonomous.
To use Barbalat's lemma, let us check the uniform continuity of V. The derivative of V is
- 7
This shows that V is bounded, since w is bounded by hypothesis, and e and 0 were shown above ~
to be bounded. Hence, V is uniformly continuous. Application of Barbalat's lemma then
indicates that e —> 0 as t —> °°.
Note that, although e converges to zero, the system is not asymptotically stable, because 8 is
only guaranteed to be bounded. Q
The analysis in the above example is quite similar to a Lyapunov analysis based
on invariant set theorems. Such an analysis based on Barbalat's lemma shall be called
a Lyapunov-like analysis. It presents two subtle but important differences with
Lyapunov analysis, however. The first is that the function V can simply be a lower
bounded function of x and t instead of a positive definite function. The second
difference is that the derivative V must be shown to be uniformly continuous, in
addition to being negative or zero. This is typically done by proving that V is bounded.
Of course, in using the Lyapunov-like lemma for stability analysis, the primary
difficulty is still the proper choice of the scalar function V.
4.6 Positive Linear Systems
In the analysis and design of nonlinear systems, it is often possible and useful to
decompose the system into a linear subsystem and a nonlinear subsystem. If the
transfer function (or transfer matrix) of the linear subsystem is so-called positive real,
then it has important properties which may lead to the generation of a Lyapunov
function for the whole system. In this section, we study linear systems with positive
real transfer functions or transfer matrices, and their properties. Such systems, called
positive linear systems, play a central role in the analysis and design of many
nonlinear control problems, as will be seen later in the book.
4.6.1 PR and SPR Transfer Functions
We consider rational transfer functions of nth-order single-input single-output linear
systems, represented in the form
1

Sect. 4.6 Positive Linear Systems 127
,, , "bm In m +u bm -\" inm~l+ T ••+• T b "o
Kp) =
The coefficients of the numerator and denominator polynomials are assumed to be real
numbers and n>m. The difference n-m between the order of the denominator and
that of the numerator is called the relative degree of the system.
Definition 4.10 A transfer function h(p) is positive real if
Re[h(p)]>0 for all Re[p]>0 (433)
It is strictly positive real if h(p-e) is positive real for some £ > 0 .
Condition (4.33), called the positive real condition, means that h(p) always has a
positive (or zero) real part when p has positive (or zero) real part. Geometrically, it
means that the rational function h(p) maps every point in the closed right half (i.e.,
including the imaginary axis) of the complex plane into the closed right half of the
h(p) plane. The concept of positive real functions originally arose in the context of
circuit theory, where the transfer function of a passive network (passive in the sense
that no energy is generated in the network, e.g., a network consisting of only
inductors, resistors, and capacitors) is rational and positive real. In section 4.7, we
shall reconcile the PR concept with passivity.
Example 4.14: A strictly positive real function
Consider the rational function
I
h(p) =
p + X
which is the transfer function of a first-order system, with X > 0. Corresponding to the complex
variable/? =
Obviously, Re[/i(p)] > 0 if a > 0. Thus, h(p) is a positive real function. In fact, one can easily
see that h(p) is strictly positive real, for example by choosing e = X/2 in Definition 4.9. D
For higher-order transfer functions, it is often difficult to use the definition
directly in order to test the positive realness condition, because this involves checking
the positivity condition over the entire right-half of the complex plane. The following
theorem can simplify the algebraic complexity.

128 Advanced Stability Theory Chap. 4
Theorem 4.10 A transfer function h(p) is strictly positive real (SPR) if and only if
i) h(p) is a strictly stable transfer function
ii) the real part ofh(p) is strictly positive along thej(i> axis, i.e.,
V co > 0 Re[/j(/to)] > 0 (4.34)
The proof of this theorem is presented in the next section, in connection with the so-
called passive systems.
The above theorem implies simple necessary conditions for asserting whether a
given transfer function h(p) is SPR:
• h(p) is strictly stable
• The Nyquist plot of h(f<x>) lies entirely in the right half complex plane.
Equivalently, the phase shift of the system in response to sinusoidal inputs is
always less than 90°
• h(p) has relative degree 0 or 1
• h{p) is strictly minimum-phase {i.e., all its zeros are strictly in the left-
half plane)
The first and second conditions are immediate from the theorem. The last two
conditions can be derived from the second condition simply by recalling the procedure
for constructing Bode or Nyquist frequency response plots (systems with relative
degree larger than 1 and non-minimum phase systems have phase shifts larger than
90° at high frequencies, or, equivalently have parts of the Nyquist plot lying in the
left-half plane).
Example 4.15: SPR and non-SPR transfer functions
Consider the following systems
p + a p + b
h(p) =
2
p2-p+\
p1+ap+b
p2 + p + 1

| Sect. 4.6  |     |     | Positive Linear Systems  |     | 129 |
| ---------- | --- | --- | ------------------------ | --- | --- |
The transfer functions h^  h , and ft are not SPR, because h is non-minimum phase, h is
|                                                     |     | 2   | 3   | x   | 2   |
| --------------------------------------------------- | --- | --- | --- | --- | --- |
| unstable, and /i has relative degree larger than 1. | 3   |     |     |     |     |
Is the (strictly stable, minimum-phase, and of relative degree 1) function  h  actually SPR?
4
We have
|     | h (ico) =  | -/'t0+ '   [/<*>+ l][-(Q2-ya)+ 1] |     |     |     |
| --- | ---------- | --------------------------------- | --- | --- | --- |
  =
|     |     | -co2+yco+l  | [l-co2]2 + co2 |     |     |
| --- | --- | ----------- | -------------- | --- | --- |
(where the second equality is obtained by multiplying numerator and denominator by the complex
conjugate of the denominator) and thus
|     | „ . , . . ,,   | -tf>2+ 1 + co2  | 1                |     |     |
| --- | -------------- | --------------- | ---------------- | --- | --- |
|     | Re[ h (jm) ] = | [1-CO2]2 + CO2  | [1 -Cl)2]2 + CO2 |     |     |
4
which shows that  h  is SPR (since it is also strictly stable). Of course, condition (4.34) can also
4
| be checked directly on a computer.  |     |     |     |     | Q   |
| ----------------------------------- | --- | --- | --- | --- | --- |
The basic difference between PR and SPR transfer functions is that PR transfer
functions may tolerate poles on the jo) axis, while SPR functions cannot.
Example 4.16: Consider the transfer function of an integrator,
h(p) = -
P
Its value corresponding to p = a +j(£> is
One easily sees from Definition 4.9 that h(p)  is PR but not SPR.  •
More precisely, we have the following result, which complements Theorem
4.10.
Theorem 4.11  A transfer function h(p) is positive real if, and only if,
i) h(p) is a stable transfer function
(il) The poles of h(p) on the ja  axis are simple (i.e., distinct) and the
associated residues are real and non-negative
Hi) Re[h(j(i>)] > 0 for any co > 0 such that ;co is not a pole  ofh(p)

130 Advanced Stability Theory Chap. 4
4.6.2 The Kalman-Yakubovich Lemma
If a transfer function of a system is SPR, there is an important mathematical property
associated with its state-space representation, which is summarized in the celebrated
Kalman-Yakubovich (KY) lemma.
Lemma 4.4 (Kalman-Yakubovich) Consider a controllable linear time-invariant
system
x=Ax + bw
y = cTx
The transfer function
Mp) = cT (4.35)
is strictly positive real if, and only if, there exist positive definite matrices P and Q
such that
ArP = -Q (4.36a)
Pb = c (4.36b)
The proof of this lemma is presented in section 4.7 in connection with passivity in
linear systems. Beyond its mathematical statement, which shall be extensively used in
chapter 8 (Adaptive Control), the KY lemma has important physical interpretations
and uses in generating Lyapunov functions, as discussed in section 4.7.
The KY lemma can be easily extended to PR systems. For such systems, it can
be shown that there exist a positive definite matrix P and a positive sera-definite
matrix Q such that (4.36a) and (4.36b) are verified. The usefulness of this result is that
it is applicable to transfer functions containing a pure integrator ( l/p in the
frequency-domain), of which we shall see many in chapter 8 when we study adaptive
controller design. The Kalman-Yakubovich lemma is also referred to as the positive
real lemma.
In the KY lemma, the involved system is required to be asymptotically stable
and completely controllable. A modified version of the KY lemma, relaxing the
controllability condition, can be stated as follows:

Sect. 4.6 Positive Linear Systems 131
Lemma 4.5 (Meyer-Kalman-Yakubovich) Given a scalar y> 0, vectors b and c,
an asymptotically stable matrix A, and a symmetric positive definite matrix L, ;/ the
transfer function
//(p) = 1 + cT[pl-A]-lb
is SPR, then there exist a scalar e > 0, a vector q, and a symmetric positive definite
matrix P such that
ATP + PA = -qq7-eL
Pb = c [~
This lemma is different from Lemma 4.4 in two aspects. First, the involved
system now has the output equation
y = cTx + %u
Second, the system is only required to be stabilizable (but not necessarily
controllable).
4.6.3 Positive Real Transfer Matrices
The concept of positive real transfer function can be generalized to rational positive
real matrices. Such generalization is useful for the analysis and design of multi-input-
multi-output nonlinear control systems.
Definition 4.11 An mxm transfer matrix H(p) is called PR if
H(p) has elements which are analytic for Re(p) > 0;
H(p) + UT(p*) is positive semi-definite for Re(p) > 0.
where the asterisk * denotes the complex conjugate transpose. H(p) is SPR if
H(p - e) is PR for some e > 0.
The Kalman-Yakubovich lemma and the Meyer-Kalman-Yakubovich lemma can be
easily extended to positive real transfer matrices.

132 Advanced Stability Theory Chap. 4
4.7 The Passivity Formalism
As we saw earlier, Lyapunov functions are generalizations of the notion of energy in a
dynamic system. Thus, intuitively, we expect Lyapunov functions to be "additive",
i.e., Lyapunov functions for combinations of systems to be derived by simply adding
the Lyapunov functions describing the subsystems. Passivity theory formalizes this
intuition, and derives simple rules to describe combinations of subsystems or "blocks"
expressed in a Lyapunov-like formalism. It also represents an approach to
constructing Lyapunov functions or Lyapunov-like functions for feedback control
purposes.
As a motivation, recall first that the dynamics of state-determined physical
systems, whether linear or nonlinear, satisfy energy-conservation equations of the
form
— [Stored Energy] = [External Power Input] + [Internal Power Generation]
dt
These equations actually form the basis of modeling techniques such as bond-graphs.
The external power input term can be represented as the scalar product y^u of an input
("effort" or "flow") u, and a output ("flow" or "effort") y.
In the following, we shall more generally consider systems which verify
equations of the form
y Tu - {t) (4.37)
1 1 gl
where Vj(f) and gj(O are scalar functions of time, Uj is the system input, and y is its
t
output. Note that, from a mathematical point of view, the above form is quite general
(given an arbitrary system, of input U)(?) and output y\(t), we can let, for instance,
g](0 = 0 and V((r) = [' y^(r) Uj(r) dr). It is the physical or "Lyapunov-like"
properties that V\{t) and gj(f) may have, and how they are transmitted through
combinations with similar systems, that we shall be particularly interested in.
4.7.1 Block Combinations
Assume that we couple a system in the form (4.37), or power form, to one verifying
the similar equation
V (t) = yT u - g(t)
2 2 2 2
in a feedback configuration, namely u = yj and U[ = - y (Figure 4.4), assuming of
2 2
1

| Sect. 4.7  |     |     | The Passivity Formalism  | 133 |
| ---------- | --- | --- | ------------------------ | --- |
course that the vectors  u,- and y.• are all of the same dimension. We then have
|     | V(t) + V x 2 (t) ] =  | -   |     | (4.38) |
| --- | --------------------- | --- | --- | ------ |
dt
,, 8
|     | 2   |     | Figure 4.4  : Two blocks  | of  the  form |
| --- | --- | --- | ------------------------- | ------------- |
(4.37), in a feedback configuration
Let us assume that the function  V\ + V  is lower bounded (e.g., is positive). Then,
2
using the same reasoning as in section 4.5, we have
• If V t > 0 , g\(i) + g (t)  ^  0 , then the function Vj + V  is upper bounded,
|     |     | 2   | 2   |     |
| --- | --- | --- | --- | --- |
and
<  00
If  in  addition,  the  function  gj + g   is  uniformly  continuous,  then
2
|     | ->0  as  | t->°°. |     |     |
| --- | -------- | ------ | --- | --- |
•  In  particular,  if  gj(r)  and  g (t)  are  both  non-negative  and  uniformly
2
continuous, then they both tend to zero as t —> °°
Note that an explicit expression of V + V  is not needed in the above results.  More
l 2
generally, without any assumption on the sign of  Vj + V   or  g\ + g  , we can state
2 2
that
•  If  Vj + V 2  has  a  finite  limit  as  t —> °°  , and  if  gj + g 2   is  uniformly
| continuous, then  | [ gy(t) + g | 2 (t) ] —> 0 as  | t —> °°. |     |
| ----------------- | ----------- | ---------------- | -------- | --- |
A system verifying an equation of the form (4.37) with V\ lower bounded and
gj>0  is  said  to  be passive  (or  to  be  a passive  mapping  between  ii[  and  yj).
Furthermore, a passive system is said to be dissipative if
g (t)dt>0
|     |     | =>  | l   |     |
| --- | --- | --- | --- | --- |

134 Advanced Stability Theory Chap. 4
Example 4.17: The nonlinear mass-spring-damper system
m x + x^ x^ + x^ — F
represents a dissipative mapping from external force F to velocity i, since
i(I i2+I;t8) = xF - x2k*
m
Of course, here Vj is simply the total (kinetic plus potential) energy stored in the system, and |
gj is the dissipated power. Q
Example 4.18: Consider the system (Figure 4.5)
x + X(t) x=u (4.39)
h(x)i
(4.39)
FILTER
NONLINEARITY
Figure 4.5 : A passive single-input single-output system
where the function h is of the same sign as its argument, although not necessarily continuous, and
X(t) > 0. The mapping w —> y is passive, since
4 \Xh(\)a\ = h(x)x = yu- X(t) h(x)x
dtJ
o
with \xh(E,)dE, > 0 and X(t)h(x)x > 0 for all x. The mapping is actually dissipative if X(t) is
not identically zero.
Of course, the function X(t) may actually be of the form X[x{t)]. For instance, the system
y = x — sin2x
is a dissipative mapping from u to y.
1

| Sect. 4.7 |     | The Passivity Formalism  |     | 135 |
| --------- | --- | ------------------------ | --- | --- |
A particularly convenient aspect of formalizing the construction of Lyapunov-
like functions as above, is that parallel and feedback combinations of systems in the
power form are still in the power form. Indeed, it is straightforward to verify that, for
both the parallel combination and the feedback combination (Figure 4.6), one has
| yru  | ru  |     |     |     |
| ---- | --- | --- | --- | --- |
= y^u,  +  y
2 2
Namely, for the parallel combination
| yTu = (y, + y | )Tu=  y\Tu  | + yTu  = yir«i  | + y2r"2 |     |
| ------------- | ----------- | --------------- | ------- | --- |
|               | 2           | 2               |         |     |
and for the feedback combination
| yTu  | = y T(u +y )  = y,ru, | y Ty   | = u T  y |     |
| ---- | --------------------- | ------ | -------- | --- |
|      | 1 l 2                 | { 2    | 2 2      |     |
Incidentally, this result is a particular case of what is known in circuit theory as
Tellegen's power conservation theorem. Thus, we have, for the overall system
| V=V, |     | = 81+82 |     |     |
| ---- | --- | ------- | --- | --- |
By induction, any combination of feedback  and/or parallel combinations of
systems in  the power form  can also be described  in the power form,  with  the
corresponding V and g simply being equal to the sum of the individual Vj and  gj.
8 =
y=yi
" = yi 2
Figure 4.6 : Parallel and feedback combinations

136 Advanced Stability Theory Chap. 4
The power of this simple result is, of course, that it does not require that the
subsystems be linear.
Note that, assuming that V is lower bounded, the overall system can be passive
while some of its components may be "active" ( g,- < 0 ): for the system to be passive,
the sum of the g± has to be positive, i.e., there should be more overall "power
dissipation" in the system than there is "power generation". Also, note that the
passivity of a block is preserved if its input or its output is multiplied by a strictly
positive constant (an input gain or an output gain), since this simply multiplies the
associated V- and g by the same constant. Thus we have, more generally
( t
where a, is the product of the input gain and the output gain for block i.
Example 4.19: Consider again the adaptive control system of Example 4.13. The fact that
e2 = e'e - e 6 w(t) - e2
2 d;
can be interpreted as stating that the mapping 6 w(t) -4 c is dissipative. Furthermore, using the
parameter adaptation law
6 = - e w(t) (4.40)
then corresponds to inserting a passive feedback block between e and — 8 w(t), since
lie2 =-e>v(oe •
2 d(
Note that, for a passive system, we may always assume that g = 0 , simply by
adding [' g(r) dr to the original V. Hence, the definition of passivity is often written
as
3a>-t>oV(>0, [' yT(r) u(r) dr > a (4.41)
j
o
which simply says that there exists a lower bounded V such that g = 0 .
Also, note that the power form is expressed in terms of the dot-product y^u.
Therefore, if u and y are other choices of inputs and outputs for the system such that
a a
yT u = y^u at all times, then they satisfy the same passivity properties as u and y.
a a
For instance, if the mapping u —> y is passive, so is the mapping Au —» A~^y,
where the matrix A is any (perhaps time-varying) invertible matrix. In particular,
j

Sect. 4.7 The Passivity Formalism 137
passivity is conserved through orthogonal transformations ( A AT = I). Furthermore,
note that the dimension of the vectors u and y is not necessarily the same as that
a a
of the vectors u and y .
4.7.2 Passivity in Linear Systems
An important practical feature of the passivity formulation is that it is easy to
characterize passive linear systems. This allows linear blocks to be straightforwardly
incorporated or added in a nonlinear control problem formulated in terms of passive
mappings.
As we shall now show, a strictly stable linear SISO system is passive if, and
only if,
V co > 0 , Re[h(j(o)] > 0 (4.42)
where h is the transfer function of the system (which we shall assume to be rational)
and Re refers to the real part of a complex number. Geometrically, condition (4.42)
can also be written as (Figure 4.7)
V co > 0 , | Arg h(j(0) | < ^ (4.43)
Thus, we see that a strictly stable linear SISO system is passive if, and only if its
phase shift in response to a sinusoidal input is always less than (or equal to) 90°.
Re Figure 4.7 : Geometric interpretation of
the passivity condition for a linear SISO
system
Proof of condition (4.42): The proof is based on Parseval's theorem, which relates the time-
domain and frequency-domain expressions of a signal's squared norm or "energy", as well as
those of the correlation of two signals.
Consider a strictly stable linear SISO system, of transfer function y(p)/u(p) = h(p), initially
at rest (y = 0) at t = 0. Let us apply to this system an arbitrary control input between / = 0 and

| 138  Advanced Stability Theory |     |     | Chap. 4 |
| ------------------------------ | --- | --- | ------- |
some positive time (, and no input afterwards.  Recalling expression  (4.41) of passivity, we
compute
| I  y(r) u(r) dr  | =  \  y{r) u(r) dr  | = —  |  y(ja>) H*O'CO) da |     |
| ---------------- | ------------------- | ------------------------- | --- |
J
| o   | -Loo  | 271 -LOO |     |
| --- | ----- | -------- | --- |
where the first equality comes from the fact that u is zero after time / (and, of course, both u and y
are zero for negative time), and the second equality comes from Parseval's theorem, with the
superscript  referring to complex conjugation.  Since y(jin) ~ h(jfo) «(/co), we thus have
| ;                    | ,  oo                   |     |     |
| -------------------- | ----------------------- | --- | --- |
| |  y{r) u(r) dr = —  | [  h(j(i>) |«O'co)|2 da |     |     |
| J /,                 | 271 J _ no              |     |     |
Now  since h is the transfer  function  of  a real system, its coefficients  are real, and  thus
h(-j(H) = [h(ja)T  . Hence,
| f y(r)u(r)dr  | = -  f  ReWja))} \u{ja)\2 da |     | (4.44) |
| ------------- | ---------------------------- | --- | ------ |
Given  expression  (4.41)  of passivity,  equation  (4.44)  shows  that (4.42)  is a  sufficient
condition  for  the  system  to  be  passive.  Indeed,  taking  an  arbitrary  input  u,  the  integral
f y(r) u(r) dr does not depend on the values of u at times later than ( (so that our earlier
assumption that u is zero after time (is not restrictive).
Equation (4.44) also shows that (4.42) is a necessary condition for the system to be passive.
Indeed, if (4.44)  was not verified,  then there would be a finite  interval  in co over  which
Re[/i(yw)] < 0, because h is continuous in co. The integral could then be made arbitrarily negative
by choosing  |«(y'to)| large enough over this finite interval.  D
Note that we have assumed that h(p) is strictly stable, so as to guarantee the
existence of  the frequency-domain  integrals  in the above proof. Actually,  using
standard results in complex variable analysis, the proof can be extended easily to the
case where h(p) has perhaps some poles on the yd) axis, provided that these poles be
simple (i.e., distinct) and that the associated residues be non-negative. As discussed
earlier in section 4.6, systems belonging to this more general class and  verifying
condition (4.42) are called positive real (PR) systems. Thus, a linear single-input
system is passive if (and only if) it is positive real.
Condition (4.42) can also be formally stated as saying that the Nyquist plot of h
is in the right half-plane.  Similarly, if the Nyquist plot of a strictly stable (or PR)
linear system of transfer function h is strictly in the right half-plane (except perhaps
for co = °° ), i.e, if

Sect. 4.7 The Passivity Formalism 139
V co > 0 , Re[/*(/0))] > 0 (4.45)
then the system is actually dissipative. As discussed in section 4.6, strictly stable linear
systems verifying (4.45) are called strictly positive real (SPR) systems.
It can also be shown that, more generally, a strictly stable linear MIMO system
is passive if, and only if
V co > 0 , HO'co) + Hr(-;co) > 0
where H is the transfer matrix of the system. It is dissipative if
V co > 0 , H(yco) + Hr(-;co) > 0
THE KALMAN-YAKUBOVICH LEMMA
For linear systems, the closeness of the concepts of stability and passivity can be
understood easily by considering the Lyapunov equations associated with the systems,
as we now show. The discussion also provides a more intuitive perspective on the KY
lemma of section 4.6.2, in the light of the passivity formalism.
Recall from our discussion of Lyapunov functions for linear systems (section
3.5.1) that, for any strictly stable linear system of the form x = A x , one has
V Q symmetric p.d. , 3 P symmetric p.d. , such that AT P + P A = - Q (4.46)
an algebraic matrix equation which we referred to as the Lyapunov equation for the
linear system. Letting
= ~xTPx
yields
V=--xTQx
Consider now a linear system, strictly stable in open-loop, in the standard form
x = A x + B u y = Cx
The Lyapunov equation (4.46) is verified for this system, since it is only related to the
system's stability, as characterized by the matrix A, and is independent of the input
and output matrices B and C. Thus, with the same definition of V as above, V now
simply contains an extra term associated with the input u

140 Advanced Stability Theory Chap. 4
V = xr P (Ax + Bu) = xrPBu -1 xTQx (4.47)
Since y = Cx, we see that (4.47) defines a dissipative mapping between u and y,
provided that the matrices B and C be related by
I
This result, known as the Kalman-Yakubovich (KY) lemma, shows the closeness of the
passivity and stability concepts, given compatible choices of inputs and outputs. Since
the Lyapunov equation (4.46) can be satisfied for any arbitrary symmetric p.d. matrix
Q, the KY lemma states that given any open-loop strictly stable linear system, one can
construct an infinity of dissipative input-output maps simply by using compatible
choices of inputs and outputs. In particular, given the system's physical inputs and the
associated matrix B, one can choose an infinity of outputs from which the linear
system will look dissipative.
In the single-input case, and given our earlier discussion of frequency-domain
characterizations of the passivity of linear systems, the KY lemma can be equivalently
stated as Lemma 4.4. Note that the controllability condition in that frequency-domain
formulation simply ensures that the transfer function h(p) completely characterizes the
linear system defined by (A, b, c) (since P is symmetric positive definite and (A, b) is
controllable, thus (A, cT) = (A, b^P) is observable). Also, as noted earlier, the KY
lemma can be extended to PR systems, for which it can be shown that there exist a
positive definite matrix P and a positive .semi-definite matrix Q such that (4.36a) and
(4.36b) are verified. The main usefulness of this result is that it is applicable to
transfer functions containing a pure integrator, which are common in adaptive
controller design.
Example 4.20: The passivity of the adaptation law (4.40) of Example 4.19 can also be shown
directly by noticing that the integrator structure
9 = - e w(t)
implies that the mapping - e w{i) —» 9 is passive, and therefore that the mapping e —> - w(t) 8
is also passive (since 9 [- e w(t)} = [- w(t) 9] e ).
Furthermore, the passivity interpretation shows that the integrator in the above update law
can be replaced by any PR transfer function, while still guaranteeing that the tracking error e
tends to zero. Indeed, since the dissipation term #2 's simply zero using the original update law,
the KY lemma shows that, with the modified update law, there exists a symmetric positive
definite matrix P and a symmetric positive semi-definite matrix Q (which, in this simple first-
order case, are simply scalars P > 0 and Q > 0 ) such that
i

Sect. 4.7 The Passivity Formalism 141
V = e2 + PQ2+\ Q[&(r)]2dr
^ o
V = -2e2
The tracking convergence proof can then be completed as before using Barbalat's lemma.
Thus, the passivity interpretation can quickly suggest additional design flexibility. D
PASSIVITY INTERPRETATION OF SPR SYSTEMS
The passivity interpretation of SPR systems may allow one to quickly determine
whether a transfer function is SPR, using physical insights.
Consider for instance the transfer function
10/7
h (p) =
5 4p2 + 5p+
We can determine whether h is SPR using a procedure similar to that used for the
5
function /z in Example 4.15. We can also simply notice that h can be interpreted as
4 5
the transfer function of a mass-spring-damper system
A'x + 5'x + x = 10M
y='x
with force as input and velocity as output. Thus h is dissipative, and thus SPR (since
5
it is also strictly stable).
Finally, one can easily verify that
• If h(p) is SPR, so is l/h(p)
• If h\(p) and h (p) are SPR, so is
2
h(p) = a, h(p) + a h (p)
{ 2 2
provided that ocj > 0 and a > 0
2
• If h\{p) and h (p) are SPR, so is
2
h\(p)
\+h{p)h (p)
l 2
which is the overall transfer function of the negative feedback system having
h\(p) as the forward path transfer function and h (p) as the feedback path
2

142 Advanced Stability Theory Chap. 4
transfer function
While these results can be derived directly, they are simply versions specific to the
linear single-input case of more general properties of passive systems. The first result
simply reflects the fact that the input u and the output y play a symmetric role in the
definition of passivity. The last two results represent the linear single-input frequency-
domain interpretation of our earlier general discussion on the combination of passive
blocks. Actually, if either h(p) or h {p) is SPR, while the other is merely passive,
x 2
then h(p) is SPR. This allows us to easily construct new SPR transfer functions
simply by taking any stable transfer function having a phase shift smaller than 90° at
all frequencies, and putting it in feedback or in parallel configuration with any SPR
transfer function.
4.8 * Absolute Stability
The systems considered in this section have the interesting structure shown in Figure
4.8. The forward path is a linear time-invariant system, and the feedback part is a
memoryless nonlinearity, i.e., a nonlinear static mapping. The equations of such
systems can be written as
x = Ax- (4.48a)
(4.48b)
where (j> is some nonlinear function and G(p) = cT[pl- A] lb . Many systems of
practical interest can be represented in this structure.
e
G(p)
J *
•
y
Figure 4.8 : System structure in absolute
stability problems
THE ISSUE OF ABSOLUTE STABILITY
The nonlinear system in Figure 4.8 has a special structure. If the feedback path simply
contains a constant gain, i.e., if <j)(v) = a y, then the stability of the whole system, a
linear feedback system, can be simply determined by examining the eigenvalues of the
closed-loop system matrix A - ocbc^. However, the stability analysis of the whole
system with an arbitrary nonlinear feedback function <j) is much more difficult.

Sect. 4.8 ' Absolute Stability 143
In analyzing this kind of system using Lyapunov's direct method, we usually
require the nonlinearity to satisfy a so-called sector condition, whose definition is
given below.
Definition 4.12 A continuous function 0 is said to belong to the sector [ky, k-^, if
there exists two non-negative numbers k\ and £ such that
2
k ^f<_k
=> x 2 (4.49)
Geometrically, condition (4.49) implies that the nonlinear function always lies
between the two straight lines k^y and k y, as shown in Figure 4.9. Two properties are
2
implied by equation (4.49). First, it implies that (j)(0) = 0. Secondly, it implies that
yty(y) > 0, i.e, that the graph of ty(y) lies in the first and third quadrants. Note that in
many of later discussions, we will consider the special case of §(y) belonging to the
sector [0, it], i.e, 3 k > 0, such that
0 < <j>(y) < ky (4.50)
Slope
Figure 4.9 : The sector condition (4.49)
Assume that the nonlinearity §(y) is a function belonging to the sector [yfcj, £ ],
2
and that the A matrix of the linear subsystem in the forward path is stable (i.e.,
Hurwitz). What additional constraints are needed to guarantee the stability of the
whole system? In view of the fact that the nonlinearity in Figure 4.9 is bounded by the
two straight lines, which correspond to constant gain feedback, it may be plausible
that the stability of the nonlinear system should have some relation to the stability of
constant gain feedback systems. In 1949, the Soviet scientist M.A. Aizerman made
the following conjecture: // the matrix [A — bc^k] is stable for all values of k in
[&j, £ ]> then the nonlinear system is globally asymptotically stable.
2

144 Advanced Stability Theory Chap. 4
POPOV'S CRITERION
Aizerman's is a very interesting conjecture. If it were true, it would allow us to deduce
the stability of a nonlinear system by simply studying the stability of linear systems.
However, several counter-examples show that this conjecture is false. After
Aizerman, many researchers continued to seek conditions that guarantee the stability
of the nonlinear system in Figure 4.8. Popov's criterion imposes additional conditions
on the linear subsystem, leading to a sufficient condition for asymptotic stability
reminiscent of Nyquist's criterion (a necessary and sufficient condition) in linear
system analysis.
A number of versions have been developed for Popov's criterion. The following
basic version is fairly simple and useful.
Theorem 4.12 (Popov's Criterion) // the system described by (4.48) satisfies the
conditions
• the matrix A is Hurwitz (i.e., has all its eigenvalues strictly in the left half-
plane) and the pair [A, b] is controllable
• the nonlinearity <|> belongs to the sector [0, k]
• there exists a strictly positive number a such that
V©>0 Re[(l +ja(o) G(yco)] + - > e (4.51)
k
for an arbitrarily small e > 0, then the point 0 is globally asymptotically stable.
Inequality (4.51) is called Popov's inequality. The criterion can be proven
constructing a Lyapunov function candidate based on the KY lemma.
Let us note the main features of Popov's criterion:
• It only applies to autonomous systems.
• It is restricted to a single memoryless nonlinearity.
• The stability of the nonlinear system may be determined by examining the
frequency-response functions of a linear subsystem, without the need of
searching for explicit Lyapunov functions.
• It only gives a sufficient condition.
The criterion is most easy to apply by using its graphical interpretation. Let

Sect. 4.8 * Absolute Stability 145
Then expression (4.51) can be written
G (co)-aa»G (co) + - > e (4.52)
1 2
K
Now let us construct an associated transfer function W(y'co), with the same real part as
G(J co), but an imaginary part equal to co Im(G(y co)), i.e.,
W(/co) = x+jy= G^co) + ycoG (co)
2
Then (4.52) implies that the nonlinear system is guaranteed to be globally
asymptotically stable if, in the complex plane having x and y as coordinates, the polar
plot of W(j(o) is (uniformly) below the line x-ay + (l/k) = 0 (Figure 4.10). The
polar plot of W is called a Popov plot. One easily sees the similarity of this criterion
to the Nyquist criterion for linear systems. In the Nyquist criterion, the stability of a
linear feedback system is determined by examining the position of the polar plot of
GQ'co) relative to the point (0, - 1), while in the Popov criterion, the stability of a
nonlinear feedback system is determined by checking the position of the associated
transfer function W(j<$) with respect to a line.
Im
Figure 4.10 : The Popov plot
Example 4.21: Let us determine the stability of a nonlinear system of the form (4.48) where the
linear subsystem is defined by
p2 + 7p+ 10
and the nonlinearity satisfies condition (4.50).
First, the linear subsystem is strictly stable, because its poles are - 2 and - 5 . It is also
controllable, because there is no pole-zero cancellation. Let us now check the Popov inequality.
The frequency response function O(yto) is

146 Advanced Stability Theory Chap. 4
-«2+T '0)7+ 10
Therefore,
„ 4co2 + 3SO
o)4 + 29to2 + 100
„ -co(co2 + H)
2 (B4 + 29(fl2 + 100
Substituting the above into (4.52) leads to
4«2 + 30+occo2(co2+ll)+(I -e)((04 + 29a>2+ 100)>0
k
It is clear that this inequality can be satisfied by any strictly positive number a, and any strictly
positive number k, i.e., 0 < it < °°. Thus, the nonlinear system is globally asymptotically stable as
long as the nonlinearity belongs to the first and third quadrants. D
THE CIRCLE CRITERION
A more direct generalization of Nyquist's criterion to nonlinear systems is the circle
criterion, whose basic version can be stated as follows.
Theorem 4.13 (Circle Criterion) If the system (4.48) satisfies the conditions
• the matrix A has no eigenvalue on the ja> axis, and has p eigenvalues
strictly in the right half-plane;
• the nonlinearity (j) belongs to the sector [/cj ,k] >'
2
• one of the following is true
• 0 < k < k , the Nyquist plot of G(j(a) does not enter the disk
x 2
D(fej, kj) and encircles it p times counter-clockwise;
• 0 = &| < &2 , and the Nyquist plot ofG(j(a) stays in the half-plane
Rep>-l/k ;
2
• ky <0<k , and the Nyquist plot ofG(j(n) stays in the interior of
2
thediskT>(k,k ) ;
x 2
• ki<k <0 , the Nyquist plot of - G(j(i>) does not enter the disk
2
D(—k\,-k ) and encircles it p times counter-clockwise;
2
then the equilibrium point 0 of the system is globally asymptotically stable.
j

Sect. 4.9 * Establishing Boundedness of Signals 147
Im G(jo>)
ReG(jm)
Figure 4.11 : The circle criterion
Thus we see that, essentially, the critical point - l/k in Nyquist's criterion is
replaced in the circle criterion by the circle of Figure 4.11 (which tends towards the
point - l/£j as k tends to £j, i.e., as the conic sector gets thinner). Of course, the
2
circle criterion states sufficient but not necessary conditions.
The circle criterion can be extended to non-autonomous systems.
4.9 * Establishing Boundedness of Signals
In the stability analysis or convergence analysis of nonlinear systems, a frequently
encountered problem is that of establishing the boundedness of certain signals. For
instance, in order to use Barbalat's lemma, one has to show the uniform continuity of
/, which can be most conveniently shown by proving the boundedness of /. Similarly,
in studying the effects of disturbances, it is also desirable to prove the boundedness of
system signals in the presence of disturbances. In this section, we provide two useful
results for such purposes.
THE BELLMAN-GRONWALL LEMMA
In system analysis, one can often manipulate the signal relations into an integral
inequality of the form
y(t) < \' a{x)y(x)dT + b{t) (4.53)
where y(t), the variable of concern, appears on both sides of the inequality. The
problem is to gain an explicit bound on the magnitude of y from the above inequality.
The Bellman-Gronwall lemma can be used for this purpose.

| 148  Advanced Stability Theory  |     | Chap. 4 |
| ------------------------------- | --- | ------- |
Lemma 4.6 (Bellman-Gronwall)  Let a variable y(t) satisfy (4.53), with aft), bft)
being known real functions. Then
| y(t) < [' a(T)b(%) exp[\' a(r)dr]dx + b{t)  |     | (4.54) |
| ------------------------------------------- | --- | ------ |
| O                                           | JT  |        |
Ifb(t) is differentiable, then
| yit) < fe(O) exp[f'a(t)dx]+ \'b{x) exp[['a(r)dr)dx  |     | (4.55) |
| --------------------------------------------------- | --- | ------ |
JO  JO  JT
In particular, if bft) is a constant, we simply have
| y(t)<b(O)exptf'a(x)dx]  |     | (4.56) |
| ----------------------- | --- | ------ |
Proof: The proof is based on defining a new variable and transforming the integral inequality into
a differential equation, which can be easily solved. Let
| v(()=f  a(x)y(x)dx  |     | (4.57) |
| ------------------- | --- | ------ |
o
Then differentiation of v and use of (4.53) leads to
v = a(t)y(t) < a(t) v(r) + a(f) b{i)
Let
i(/) = a(t) y(t) - a(t) v(i)-a(t) b(t)
which is obviously a non-positive function. Then v(0 satisfies
v(0 - a{t) v(t) = a(t)b(t) + 5(0
Solving this equation with initial condition v(0) = 0, yields
| v(0= \'exp[\'a(r)dr]  | [a(x)b(x) + s(x)]dx  | (4.58) |
| --------------------- | -------------------- | ------ |
Since 5() is a non-positive function,
| v(0<|  r'  exp[J  r' a(r)dr] a(x) b(x)dx |     |     |
| ---------------------------------------- | --- | --- |
This, together with the definition of v and the inequality (4.53), leads to

Sect. 4.9 * Establishing Boundedness of Signals 149
y(t) < f'exp[['<*(/•)dr] a(x)b(x)dx + b(t)
O X
If /)(() is differentiable, we obtain, by partial integration
f exp[f a(r)dr]a(x)b(x)dx = - fc(t)exp[f a(r)dr] | IZ' + f'b(z)exp[('a(r)dr)di O
Jn Jt JT Ja JX
TOTAL STABILITY
Consider the nonlinear system
3x = d(t) (4.59)
which represents a non-linear mass-spring-damper system with a disturbance d(t)
(which may be due to unmodeled Coulomb friction, motor ripple, parameter
variations, etc). Is x bounded when the disturbance is bounded? This is the main
question addressed by the so-called total stability theory (or stability under persistent
disturbances).
In total stability, the systems concerned are described in the form
x = f(x, 0 + g(x, t) (4.60)
where g(x,/) is a perturbation term. Our objective is to derive a boundedness condition
for the perturbed equation (4.60) from the stability properties of the associated
unperturbed system
x = f(x, t) (4.61)
We assume that x = 0 is an equilibrium point for the unperturbed dynamics (4.61), i.e.,
f(0, t) = 0. But the origin is not necessarily an equilibrium point for the perturbed
dynamics (4.60). The concept of total stability characterizes the ability of a system to
withstand small persistent disturbances, and is defined as follows:
Definition 4.13 The equilibrium point x = 0 for the unperturbed system (4.61) is
said to be totally stable if for every e > 0, two numbers 8y and 82 exist such that
||x(/ )||<8j and ||g(x,r)|| < 5 imply that every solution x(t) of the perturbed system
o 2
(4.60) satisfies the condition \\x(t)\\ < £.
The above definition means that an equilibrium point is totally stable if the state
of the perturbed system can be kept arbitrarily close to zero by restricting the initial
state and the perturbation to be sufficiently small. Note that total stability is simply a
local version (with small input) of BIBO (bounded input bounded output) stability. It

150 Advanced Stability Theory Chap. 4
is also useful to remark that if the unperturbed system is linear, then total stability is
guaranteed by the asymptotic stability of the unperturbed system.
The following theorem is very useful to assert the total stability of a nonlinear
system.
Theorem 4.14 If the equilibrium point of (4.61) is uniformly asymptotically stable,
then it is totally stable.
This theorem can be proven by using the converse Lyapunov theorem 4.8. It means
that uniformly asymptotically stable systems can withstand small disturbances.
Because uniformly asymptotic stability can be asserted by the Lyapunov theorem 4.1,
total stability of a system may be similarly established by theorem 4.1. Note that
asymptotic stability is not sufficient to guarantee the total stability of a nonlinear
system as can be verified by counter-examples. We also point out that exponentially
stable systems are always totally stable because exponential stability implies uniform
asymptotic stability.
Example 4.22: Consider again the system (4.59). Let us analyze the stability of the unperturbed
system
x+ 2i3 + 3x = 0
first. Using the scalar function
and the invariant set theorem, one easily shows that the equilibrium point is globally
asymptotically stable. Because the system is autonomous, the stability is also uniform. Thus, the
above theorem shows that the system can withstand small disturbances d(t). D
Total stability guarantees boundedness to only small-disturbance, and requires
only local uniform asymptotic stability of the equilibrium point. One might wonder
whether the global uniform asymptotic stability can guarantee the boundedness of the
state in the presence of large (though still bounded) perturbations. The following
counter-example demonstrates that this is not true.
Example 4.23: The nonlinear equation
= w(t) (4.62)
can be regarded as representing mass-spring-damper system containing nonlinear damping fix)
and excitation force w(t), where / is a first and third quadrant continuous nonlinear function such
that

| Sect. 4.10 |     | ' Existence and Unicity of Solutions  |     |     | 151 |
| ---------- | --- | ------------------------------------- | --- | --- | --- |
\f(y) I < 1  _ oo < _y < oo
as illustrated in Figure 4.12.
fly)
|     |     |     | Figure  4.12  | :  A  nonlinear  | damping |
| --- | --- | --- | ------------- | ---------------- | ------- |
function
The system is totally stable, because the equilibrium point can be shown to be globally uniformly
asymptotically stable using the Lyapunov function V = (1/2)(x2 + x2).  Is the output bounded for
bounded input?
Let us consider the response of the system to the excitation force w(t) = A sin /,  A> S/n.  By
writing (4.62) as
x + x = Asint-f{x)
| and solving this linear equation with (A sin t -f(x))  |     |     | as input, we obtain |     |     |
| ------------------------------------------------------ | --- | --- | ------------------- | --- | --- |
rl
|     | A   | c*  | .  A  |     |     |
| --- | --- | --- | ----- | --- | --- |
x(t) = —(sint-tcost)-\  sin(t-x)f<Jc)d%  > — (s'mt-tcost)  -  I  \s'm(t-T)\dx
|     | 2   | J0  | 2   | J0  |     |
| --- | --- | --- | --- | --- | --- |
The integral on the right-hand side can be shown to be smaller than (2/;i)(l + e)t for any l> t ,
g
| and e > 0 and some t | o  . Att  n = (2« + l)7t, |     |     |     |     |
| -------------------- | ------------------------- | --- | --- | --- | --- |
x(t)>
n
| Therefore, if we'take A > 8/71 and e = 1/2, x(t) —> 0°. |     |     |     |     | •   |
| ------------------------------------------------------- | --- | --- | --- | --- | --- |
n
4.10  * Existence and Unicity of Solutions
This section discusses the mathematically important question of existence and unicity
of solutions of nonlinear differential equations. We first describe a simple and quite
general sufficient condition for a nonlinear differential equation to admit a solution,
and then simple but conservative conditions for this solution to be unique.

152 Advanced Stability Theory Chap. 4
Theorem 4.15 (Cauchy existence theorem) Consider the differential equation
x = f(x, t), with initial condition \(t ) = x . If the function f is continuous in the closed
0 0
region
\t-t \ < T, \\x-x \\ < R
o o
where T and R are strictly positive constants, then the equation has at least one
solution x(t) which satisfies the initial condition and is continuous over a finite time
period [t ,t] (where t > t).
o { x o
The above theorem indicates that the continuity of f is sufficient for the local
existence of solutions. However, it does not guarantee the uniqueness of the solution.
Example 4.24: An equation with multiple solutions
Consider the equation
with initial condition y(Q) = 0. Two of its solutions are y(t) = 0 and y = r3. [U
The following theorem gives a sufficient condition for the unique existence of a
solution.
Theorem 4.16 If the function f(x, t) is continuous in t, and if there exists a strictly
positive constant L such that
||f(x ,r)-f(x,,r)|| < L \\x -x \\ (4.63)
2 2 x
for all Xy and X2 in a finite neighborhood of the origin and all t in the interval
\t , t + T\ (with T being a strictly positive constant), then x — f(x, t) has a unique
0 o
solution x(t)for sufficiently small initial states and in a sufficiently short time interval.
Condition (4.63) is called a Lipschitz condition and L is known as a Lipschitz
constant. If (4.63) is verified, then f is said to be locally Lipschitz in x. If (4.63) is
verified for any time t, then f is said to be locally Lipschitz in x uniformly with respect
to t. Note that the satisfaction of a Lipschitz condition implies (locally) the continuity
of f in terms of x, as can be easily proven from the definition of continuity.
Conversely, if locally f has a continuous and bounded Jacobian with respect to x, then
f is locally Lipschitz. When (4.63) is satisfied for any x and x in the state space, f is
( 2
said to be globally Lipschitz. The above theorem can then be extended to guarantee
unique existence of a solution in a global sense (i.e., for any initial condition and any
time period).
While the condition for existence of solutions, as stated by Cauchy's theorem, is

Sect. 4.12 Notes and References 153
rather benign, the sufficient condition for unicity is quite strong, and, actually, overly
conservative. Most results on nonlinear dynamics simply assume that f is smooth
enough to guarantee existence and unicity of the solutions. Note that this is always the
case of good physical system models (at least in classical physics).
Actually, precise mathematical results exist about the relation between the
existence of a Lyapunov function for a given system and the existence and unicity of
solutions (see, e.g., [Yoshizawa, 1966, 1975]). From a practical point of view, these
results essentially mean that the existence of a Lyapunov function to describe a system
will guarantee the system's "good behavior" under some mild smoothness
assumptions on the dynamics.
4.11 Summary
Some advanced topics in nonlinear control theory are presented in this chapter.
Lyapunov theory for non-autonomous systems is discussed first. Its results are quite
similar to those for autonomous systems, although more involved conditions are
required. A major difference is that the powerful invariant-set theorem does not apply
to non-autonomous system, although Barbalat's lemma can often be a simple and
effective substitute. A number of instability theorems are also presented. Such
theorems are useful for non-autonomous systems, or for autonomous systems whose
linearizations are only marginally stable. Theorems on the existence of Lyapunov
functions may be of use in constructing Lyapunov functions for systems part of which
is known to have certain stability properties. The passivity formalism is also
introduced, as a notationally convenient and physically motivated interpretation of
Lyapunov or Lyapunov-like analysis. The chapter also includes some results for
establishing the boundedness of signals in nonlinear systems.
4.12 Notes and References
A comprehensive yet readable book on Lyapunov analysis of non-autonomous systems is [Hahn,
1967], on which most of the stability definitions in this chapter are based. The definitions and
results concerning positive definite and decrescent functions are based on [Hahn, 1967; Vidyasagar,
1978]. The statement and proof of Theorem 4.1 are adapted from [Kalman and Bertram, I960].
Example 4.5 is adapted from [Vidyasagar, 1978], Example 4.6 from [Massera, 1949], and Example
4.7 from [Rouche, el a/., 1977]. Figure 4.1 is adapted from A.S.M.E. Journal of Basic Engineering,
1960. In section 4.2.2, the result on perturbed linear systems is from [Vidyasagar, 1978], while the
result on sufficient smoothness conditions on the A(;) matrix is from [Middleton, 1988]. Sections
4.2.3 and 4.3 are largely adapted from [Vidyasagar, 1978], where proofs of the main results can be

154 Advanced Stability Theory Chap. 4
found. The statement of Theorem 4.9 follows that in [Bodson, 1986]. Lemma 4.2 and its proof are
from [Popov, 1973]. An extensive study of absolute stability problems from a frequency-domain
perspective is contained in [Narendra and Taylor, 1973], from which the definitions and theorems on
positive real functions are adapted. A more recent description of positive real functions and their
applications in adaptive control can be found in [Narendra and Annasswamy, 1989]. The Bellman-
Gronwall lemma and its proof are adapted from [Hsu and Meyer, 1968]. The definition and theorem
on total stability are based on [Hahn, 1965]. Example 4.23 is adapted from [Desoer, et al., 1965].
Passivity theory (see [Popov, 1973; Desoer and Vidyasagar, 1975]) is presented in a slightly
unconventional form. Passivity interpretations of adaptive control laws are discussed in [Landau,
1979]. The reader is referred to [Vidyasagar, 1978] for a detailed discussion of absolute stability.
The circle criterion and its extensions to non-autonomous systems were derived by [Narendra and
Goldwyn, 1964; Sandberg, 1964; Tsypkin, 1964; Zames, 1966],
Other important robustness analysis tools include singular perturbations (see, e.g.,
[Kokotovic, et al., 1986]) and averaging (see, e.g, [Hale, 1980; Meerkov, 1980]).
Relations between the existence of Lyapunov functions and the existence and unicity of
solutions of nonlinear differential equations are discussed in [Yoshizawa, 1966, 1975].
4.13 Exercises
4.1 Show that, for a non-autonomous system, a system trajectory is generally not an invariant set.
4.2 Analyze the stability of the dynamics (corresponding to a mass sinking in a viscous liquid)
v + 2a|v|v + bv = c a>0,b>0
4.3 Show that a function V(x, t) is radially unbounded if, and only if, there exists a class-K
function <j> such that
V(x,0><KIMI)
where the function (j) satisfies
Urn <KIM|) = oo
4.4 The performance of underwater vehicles control systems is often constrained by the
"unmodeled" dynamics of the thrusters. Assume that one decides to explicitly account for thruster
dynamics, based on the model
d) = -a, co|a)| + ax a!>0,a-,>0
2
u = ba> |oo| b>0

Sect. 4.13 Exercises 155
where x is the torque input to the propeller, co is the propeller's angular velocity, and » is the actual
thrust generated.
Show that, for a constant torque input x , the steady-state thrust is proportional to x (which is
0 g
consistent witht the fact that thruster dynamics is often treated as "unmodeled").
Assuming that the coefficients a,- and b in the above model are known with good accuracy,
design and discuss the use of a simple "open-loop" observer for u (given an arbitrary time-varying
torque input x) in the absence of measurements of (0. (Adapted from [Yoerger and Slotine, 1990].)
4.5 Discuss the similarity of the results of section 4.2.2 with Krasovskii's theorem of section 3.5.2.
4.6 Use the first instability theorem to show the instability of the vertical-up position of a
pendulum.
4.7 Show explicitly why the linear time-varying system defined by (4.18) does not satisfy the
sufficient condition (4.19).
4.8 Condition (4.19) on the eigenvalues of A(t) + AT(t) is only, of course, a sufficient condition.
For instance, show that the linear time-varying system associated with the matrix
-1 e"2
0 -1
is globally asymptotically stable.
4.9 Determine whether the following systems have a stable equilibrium. Indicate whether the
stability is asymptotic, and whether it is global.
- 10 e3'
(a)
0 -2
x\ -1 2sinr
(b)
0 -(/+!) X2
'-1 e2''
x\ x\
(c) = 0 -2
X2
4.10 If a differeniiable function/is lower bounded and decreasing (/< 0), then it converges to a
limit. However,/does not necessarily converge to zero. Derive a counter-example. (Hint: You may
L

156 Advanced Stability Theory Chap. 4
use for —/ a function that peaks periodically, but whose integral is finite.)
4.11 (a) Show that if a function/is bounded and uniformly continuous, and there exists a positive
definite function F(f, t) such that
J F(f(t), t) dt<oo
1
then f(t) tends to zero as f —> °°.
(b) For a given autonomous nonlinear system, consider a Lyapunov function Vina ball B^ ,
and let $ be a scalar, differentiable, strictly monotonously increasing function of its scalar argument.
Show that [<|>(V)-<|>(0)] is also a Lyapunov function for the system (distinguish the cases of
stability and of asymptotic stability). Suggest extensions to non-autonomous systems.
4.12 Consider a scalar, lower bounded, and twice continuously differentiable function V(t) such
that
V/>0, V(0<0
Show that, for any / > 0 ,
V(0 = 0 => V(t) = 0

Chapter 5
Describing Function Analysis
The frequency response method is a powerful tool for the analysis and design of linear
control systems. It is based on describing a linear system by a complex-valued
function, the frequency response, instead of a differential equation. The power of the
method comes from a number of sources. First, graphical representations can be used
to facilitate analysis and design. Second, physical insights can be used, because the
frequency response functions have clear physical meanings. Finally, the method's
complexity only increases mildly with system order. Frequency domain analysis,
however, cannot be directly applied to nonlinear systems because frequency response
functions cannot be defined for nonlinear systems.
Yet, for some nonlinear systems, an extended version of the frequency response
method, called the describing function method, can be used to approximately analyze
and predict nonlinear behavior. Even though it is only an approximation method, the
desirable properties it inherits from the frequency response method, and the shortage
of other systematic tools for nonlinear system analysis, make it an indispensable
component of the bag of tools of practicing control engineers. The main use of
describing function method is for the prediction of limit cycles in nonlinear systems,
although the method has a number of other applications such as predicting
subharmonics, jump phenomena, and the response of nonlinear systems to sinusoidal
inputs.
This chapter presents an introduction to the describing function analysis of
nonlinear systems. The basic ideas in the describing function method are presented in
157

158 Describing Function Analysis Chap. 5
section 5.1. Section 5.2 discusses typical "hard nonlinearities" in control engineering,
since describing functions are particularly useful for studying control systems
containing such nonlinearities. Section 5.3 evaluates the describing functions for
these hard nonlinearities. Section 5.4 is devoted to the description of how to use the
describing function method for the prediction of limit cycles.
5.1 Describing Function Fundamentals
In this section, we start by presenting describing function analysis using a simple
example, adapted from [Hsu and Meyer, 1968]. We then provide the formal definition
of describing functions and some techniques for evaluating the describing functions of
nonlinear elements.
5.1.1 An Example of Describing Function Analysis
The interesting and classical Van der Pol equation
x + a(x2-\)x + x = 0 (5.1)
(where a is a positive constant) has been treated by phase-plane analysis and
Lyapunov analysis in the previous chapters. Let us now study it using a different
technique, which shall lead us to the concept of a describing function. Specifically, let
us determine whether there exists a limit cycle in this system and, if so, calculate the
amplitude and frequency of the limit cycle (pretending that we have not seen the phase
portrait of the Van der Pol equation in Chapter 2). To this effect, we first assume the
existence of a limit cycle with undetermined amplitude and frequency, and then
determine whether the system equation can indeed sustain such a solution. This is
quite similar to the assumed-variable method in differential equation theory, where we
first assume a solution of certain form, substitute it into the differential equation, and
then attempt to determine the coefficients in the solution.
Before carrying out this procedure, let us represent the system dynamics in a
block diagram form, as shown in Figure 5.1. It is seen that the feedback system in 5.1
contains a linear block and a nonlinear block, where the linear block, although
unstable, has low-pass properties.
Now let us assume that there is a limit cycle in the system and the oscillation
signal x is in the form of
x(t) =/\sin(coO

| Sect. 5.1 |                    | Describing Function Fundamentals |                | 159 |
| --------- | ------------------ | -------------------------------- | -------------- | --- |
|           | Nonlinear Element  | ( - x x2)                        | Linear Element |     |
Figure 5.1 : Feedback interpretation of the Van der Pol oscillator
with A being the limit cycle amplitude and co being the frequency. Thus,
x(t) =Acocos(a>0
Therefore, the output of the nonlinear block is
w = -x2x  = -A2sin2((Of) Atocos(toz)
(l - cos(2coO ) cos(tor) = -d_^ (cos(a>0 - cos(3a>0 )
It is seen that w contains a third harmonic term.  Since the linear block has low-pass
properties, we can reasonably assume that this third harmonic term is  sufficiently
attenuated by the linear block and its effect is not present in the signal flow after the
| linear block. This means that we can approximate  |     |              | w by |     |
| ------------------------------------------------- | --- | ------------ | ---- | --- |
|                                                   | A3  | A2  A        |      |     |
| w = - — cocosccw =                                |     | [-Asin(cor)] |      |     |
|                                                   | 4   | 4  d!        |      |     |
so that the nonlinear block in Figure 5.1 can be approximated  by the equivalent
"quasi-linear" block in Figure 5.2.  The "transfer function" of the quasi-linear block
depends on the signal amplitude A, unlike a linear system transfer function (which is
independent of the input magnitude).
In the frequency domain, this corresponds to
| w = N(A, co) (-x) |     |     |     | (5.2) |
| ----------------- | --- | --- | --- | ----- |
where

160 Describing Function Analysis Chap. 5
QUASI-LINEAR
APPROXIMATION
1
,•=0 A2 w a X
— P P2- ap +1
4
1 |
Figure 5.2 : Quasi-linear approximation of the Van der Pol oscillator
N(A, co) = ^ (j
That is, the nonlinear block can be approximated by the frequency response function
N(A, co). Since the system is assumed to contain a sinusoidal oscillation, we have
x = A sin(cor) = G(j(n) w = G(jco) N(A, co) (-x)
where G(y'co) is the linear component transfer function. This implies that
A2(jco)
+ a = 0
4 C/co)2-a<jco) + l
Solving this equation, we obtain
A = 2 co= 1
Note that in terms of the Laplace variable p, the closed-loop characteristic equation of
this system is
1 +- •P a = 0 (5.3)
4 p2 - ap +
whose eigenvalues are
X,, = - ia(A2-4) ± |±a2(A2-4)2 - (5.4)
2
Corresponding to A = 2, we obtain the eigenvalues A,j2 = ±7- This indicates the
existence of a limit cycle of amplitude 2 and frequency 1. It is interesting to note
neither the amplitude nor the frequency obtained above depends on the parameter a in
J

Sect. 5.1 Describing Function Fundamentals 161
Equation 5.1.
In the phase plane, the above approximate analysis suggests that the limit cycle
is a circle of radius 2, regardless of the value of a. To verify the plausibility of this
result, the real limit cycles corresponding to the different values of a are plotted
(Figure 5.3). It is seen that the above approximation is reasonable for small value of
a, but that the inaccuracy grows as a increases. This is understandable because as a
grows the nonlinearity becomes more significant and the quasi-linear approximation
becomes less accurate.
limit cycle
Figure 5.3 : Real limit cycles on the phase plane
The stability of the limit cycle can also be studied using the above analysis. Let
us assume that the limit cycle's amplitude A is increased to a value larger than 2.
Then, equation (5.4) shows that the closed-loop poles now have a negative real part.
This indicates that the system becomes exponentially stable and thus the signal
magnitude will decrease. Similar conclusions are obtained assuming that the limit
cycle's amplitude A is decreased to a value less than 2. Thus, we conclude that the
limit cycle is stable with an amplitude of 2.
Note that, in the above approximate analysis, the critical step is to replace the
nonlinear block by the quasi-linear block which has the frequency response function
(A2/4) (j(0). Afterwards, the amplitude and frequency of the limit cycle can be
determined from 1 + G(ja>) N(A, co) = 0. The function N(A, co) is called the describing
function of the nonlinear element. The above approximate analysis can be extended to
predict limit cycles in other nonlinear systems which can be represented into the block
diagram similar to Figure 5.1, as we shall do in section 5.4.

162 Describing Function Analysis Chap. 5
5.1.2 Applications Domain
Before moving on to the formal treatment of the describing function method, let us
briefly discuss what kind of nonlinear systems it applies to, and what kind of
information it can provide about nonlinear system behavior.
THE SYSTEMS
Simply speaking, any system which can be transformed into the configuration in
Figure 5.4 can be studied using describing functions. There are at least two important
classes of systems in this category.
Nonlinear Element Linear Element
r(0 = 0 wft) y(0
w=f(x) G(p)
Figure 5.4 : A nonlinear system
The first important class consists of "almost" linear systems. By "almost" linear
systems, we refer to systems which contain hard nonlinearities in the control loop but
are otherwise linear. Such systems arise when a control system is designed using
linear control but its implementation involves hard nonlinearities, such as motor
saturation, actuator or sensor dead-zones, Coulomb friction, or hysteresis in the plant.
An example is shown in Figure 5.5, which involves hard nonlinearities in the actuator.
Example 5.1: A system containing only one nonlinearity
Consider the control system shown in Figure 5.5. The plant is linear and the controller is also
linear. However, the actuator involves a hard nonlinearity. This system can be rearranged into the
form of Figure 5.4 by regarding G as the linear component G, and the actuator
nonlinearity as the nonlinear element. D
"Almost" linear systems involving sensor or plant nonlinearities can be
similarly rearranged into the form of Figure 5.4.
The second class of systems consists of genuinely nonlinear systems whose
dynamic equations can actually be rearranged into the form of Figure 5.4. We saw an
example of such systems in the previous section.
i

Sect. 5.1 Describing Function Fundamentals 163
w(t) u(t) y(t)
G/P) G(p)
p
Figure 5.5 : A control system with hard nonlinearity
APPLICATIONS OF DESCRIBING FUNCTIONS
For systems such as the one in Figure 5.5, limit cycles can often occur due to the
nonlinearity. However, linear control cannot predict such problems. Describing
functions, on the other hand, can be conveniently used to discover the existence of
limit cycles and determine their stability, regardless of whether the nonlinearity is
"hard" or "soft." The applicability to limit cycle analysis is due to the fact that the
form of the signals in a limit-cycling system is usually approximately sinusoidal. This
can be conveniently explained on the system in Figure 5.4. Indeed, asssume that the
linear element in Figure 5.4 has low-pass properties (which is the case of most
physical systems). If there is a limit cycle in the system, then the system signals must
all be periodic. Since, as a periodic signal, the input to the linear element in Figure 5.4
can be expanded as the sum of many harmonics, and since the linear element, because
of its low-pass property, filters out higher frequency signals, the output y(t) must be
composed mostly of the lowest harmonics. Therefore, it is appropriate to assume that
the signals in the whole system are basically sinusoidal in form, thus allowing the
technique in subsection 5.1.1 to be applied.
Prediction of limit cycles is very important, because limit cycles can occur
frequently in physical nonlinear system. Sometimes, a limit cycle can be desirable.
This is the case of limit cycles in the electronic oscillators used in laboratories.
Another example is the so-called dither technique which can be used to minimize the
negative effects of Coulomb friction in mechanical systems. In most control systems,
however, limit cycles are undesirable. This may be due to a number of reasons:
1. limit cycle, as a way of instability, tends to cause poor control accuracy
2. the constant oscillation associated with the limit cycles can cause
increasing wear or even mechanical failure of the control system
hardware
3. limit cycling may also cause other undesirable effects, such as passenger

164 Describing Function Analysis Chap. 5
discomfort in an aircraft under autopilot
In general, although a precise knowledge of the waveform of a limit cycle is usually
not mandatory, the knowledge of the limit cycle's existence, as well as that of its
approximate amplitude and frequency, is critical. The describing function method can
be used for this purpose. It can also guide the design of compensators so as to avoid
limit cycles.
5.1.3 Basic Assumptions
Consider a nonlinear system in the general form of Figure 5.4. In order to develop the
basic version of the describing function method, the system has to satisfy the
following four conditions:
1. there is only a single nonlinear component
2. the nonlinear component is time-invariant
3. corresponding to a sinusoidal input x= sin(coO , only the fundamental
component Wj(f) in the output w(t) has to be considered
4. the nonlinearity is odd
The first assumption implies that if there are two or more nonlinear components
in a system, one either has to lump them together as a single nonlinearity (as can be
done with two nonlinearities in parallel), or retain only the primary nonlinearity and
neglect the others.
The second assumption implies that we consider only autonomous nonlinear
systems. It is satisfied by many nonlinearities in practice, such as saturation in
amplifiers, backlash in gears, Coulomb friction between surfaces, and hysteresis in
relays. The reason for this assumption is that the Nyquist criterion, on which the
describing function method is largely based, applies only to linear time-invariant
systems.
The third assumption is the fundamental assumption of the describing function
method. It represents an approximation, because the output of a nonlinear element
corresponding to a sinusoidal input usually contains higher harmonics besides the
fundamental. This assumption implies that the higher-frequency harmonics can all be
neglected in the analysis, as compared with the fundamental component. For this
assumption to be valid, it is important for the linear element following the nonlinearity
to have low-pass properties, i.e.,
|G(jco)| » | G(;«co) | for n = 2, 3,... (5.5)

Sect. 5.1 Describing Function Fundamentals 165
This implies that higher harmonics in the output will be filtered out significantly.
Thus, the third assumption is often referred to as the filtering hypothesis.
The fourth assumption means that the plot of the nonlinearity relation f(x)
between the input and output of the nonlinear element is symmetric about the origin.
This assumption is introduced for simplicity, i.e., so that the static term in the Fourier
expansion of the output can be neglected. Note that the common nonlinearities
discussed before all satisfy this assumption.
The relaxation of the above assumptions has been widely studied in literature,
leading to describing function approaches for general situations, such as multiple
nonlinearities, time-varying nonlinearities, or multiple-sinusoids. However, these
methods based on relaxed conditions are usually much more complicated than the
basic version, which corresponds to the above four assumptions. In this chapter, we
shall mostly concentrate on the basic version.
5.1.4 Basic Definitions
Let us now discuss how to represent a nonlinear component by a describing function.
Let us consider a sinusoidal input to the nonlinear element, of amplitude A and
frequency co, i.e., x(t) = Asin(au), as shown in Figure 5.6. The output of the nonlinear
component w{i) is often a periodic, though generally non-sinusoidal, function. Note
that this is always the case if the nonlinearity fix) is single-valued, because the output
is/[Asin(oo(/+2n:/GO))] =/[Asin(cor)]. Using Fourier series, the periodic function w(t)
can be expanded as
oo
w(0 = —+ ~^[a cos(n(i)t) + b sin(n(i)t)] (5.6)
n n
where the Fourier coefficients a's and bfs are generally functions of A and (0,
(
determined by
a = -\* w(t)d((M) (5.7a)
o
a = I f * w(t)cos (no)t)d(at) (5.7b)
KJ-
K
b = -\K w(t)sm(n(nt)d((tit) (5.7c)
n
ft -it

166 Describing Function Analysis Chap. 5
A sin(tt) t) w(t) A sin((0 t) M sin
N.L. N(A, w)
Figure 5.6 : A nonlinear element and its describing function representation
Due to the fourth assumption above, one has a = 0. Furthermore, the third
0
assumption implies that we only need to consider the fundamental component w(t),
x
namely
w(t) ~ wj(f) = aj cos(cof) + b sin(a>0 = Msin(co? + (()) (5.8)
x
where
M{A,co) = Ja^ + 6,2 and <j>(A,co) =
Expression (5.8) indicates that the fundamental component corresponding to a
sinusoidal input is a sinusoid at the same frequency. In complex representation, this
sinusoid can be written as wj = Mei(m + ^ = (b +ja\) eJmt.
{
Similarly to the concept of frequency response function, which is the frequency-
domain ratio of the sinusoidal input and the sinusoidal output of a system, we define
the describing function of the nonlinear element to be the complex ratio of the
fundamental component of the nonlinear element by the input sinusoid, i.e.,
(pi \x i
/V(A,co)=^ifl^ ^e^=Ub +ia ) (5.9)
{ x
With a describing function representing the nonlinear component, the nonlinear
element, in the presence of sinusoidal input, can be treated as if it were a linear
element with a frequency response function /V(A,co), as shown in Figure 5.6. The
concept of a describing function can thus be regarded as an extension of the notion of
frequency response. For a linear dynamic system with frequency response function
H(jw), the describing function is independent of the input gain, as can be easily
shown. However, the describing function of a nonlinear element differs from the
frequency response function of a linear element in that it depends on the input
amplitude A. Therefore, representing the nonlinear element as in Figure 5.6 is also
called quasi-linearization.
Generally, the describing function depends on the frequency and amplitude of
the input signal. There are, however, a number of special cases. When the
nonlinearity is single-valued, the describing function iV(A,co) is real and independent
of the input frequency co. The realness of N is due to the fact that a = 0, which is true
x

Sect. 5.1 Describing Function Fundamentals 167
because f[A sin(a>0] cos(cof), the integrand in the expression (5.7b) for <Z[, is an odd
function of cor, and the domain of integration is the symmetric interval [-71, TC]. The
frequency-independent nature is due to the fact that the integration of the single-
valued function f[A sin(cor)] sin(coO in expression (5.7c) is done for the variable cof,
which implies that co does not explicitly appear in the integration.
Although we have implicitly assumed the nonlinear element to be a scalar
nonlinear function, the definition of the describing function also applies to the case
when the nonlinear element contains dynamics {i.e., is described by differential
equations instead of a function). The derivation of describing functions for such
nonlinear elements is usually more complicated and may require experimental
evaluation.
5.1.5 Computing Describing Functions
A number of methods are available to determine the describing functions of nonlinear
elements in control systems, based on definition (5.9). We now briefly describe three
such methods: analytical calculation, experimental determination, and numerical
integration. Convenience and cost in each particular application determine which
method should be used. One thing to remember is that precision is not critical in
evaluating describing functions of nonlinear elements, because the describing function
method is itself an approximate method.
ANALYTICAL CALCULATION
When the nonlinear characteristics w =/(x) (where x is the input and w the output) of
the nonlinear element are described by an explicit function and the integration in (5.7)
can be easily carried out, then analytical evaluation of the describing function based
on (5.7) is desirable. The explicit function/(x) of the nonlinear element may be an
idealized representation of simple nonlinearities such as saturation and dead-zone, or it
may be the curve-fit of an input-output relationship for the element. However, for
nonlinear elements which evade convenient analytical expressions or contain
dynamics, the analytical technique is difficult.
NUMERICAL INTEGRATION
For nonlinearities whose input-output relationship w =f{x) is given by graphs or
tables, it is convenient to use numerical integration to evaluate the describing
functions. The idea is, of course, to approximate integrals in (5.7) by discrete sums
over small intervals. Various numerical integration schemes can be applied for this
purpose. It is obviously important that the numerical integration be easily

168 Describing Function Analysis Chap. 5
implementable by computer programs. The result is a plot representing the describing
function, which can be used to predict limit cycles based on the method to be
developed in section 5.4.
EXPERIMENTAL EVALUATION
The experimental method is particularly suitable for complex nonlinearities and
dynamic nonlinearities. When a system nonlinearity can be isolated and excited with
sinusoidal inputs of known amplitude and frequency, experimental determination of
the describing function can be obtained by using a harmonic analyzer on the output of
the nonlinear element. This is quite similar to the experimental determination of
frequency response functions for linear elements. The difference here is that not only
the frequencies, but also the amplitudes of the input sinusoidal should be varied. The
results of the experiments are a set of curves on complex planes representing the
describing function N(A, co), instead of analytical expressions. Specialized
instruments are available which automatically compute the describing functions of
nonlinear elements based on the measurement of nonlinear element response to
harmonic excitation.
Let us illustrate on a simple nonlinearity how to evaluate describing functions
using the analytical technique.
Example 5.2: Describing function of a hardening spring
The characteristics of a hardening spring are given by
w = x + x3/2
with x being the input and w being the output. Given an input x(t) = A sin(co(), the output
w(t) — A sin(cof) + A3 sin3(cof)/2 can be expanded as a Fourier series, with the fundamental being
W|(;) = tf| cos cor + foj sin co/
Because w(t) is an odd function, one has a^ = 0, according to (5.7). The coefficient ftj is
b,=-\ [Asin((Ot) + A3 sin3(mt)/2] sin((ot) d((Ot) = A +-A3
Therefore, the fundamental is
w, =(A + -A3)sin(cor)
8
and the describing function of this nonlinear component is
A

Sect. 5.2 Common Nonlinearities In Control Systems 169
= 1 +-A2
8
Note that due to the odd nature of this nonlinearity, the describing function is real, being a
function only of the amplitude of the sinusoidal input. •
5.2 Common Nonlinearities In Control Systems
In this section, we take a closer look at the nonlinearities found in control systems.
Consider the typical system block shown in Figure 5.7. It is composed of four parts: a
plant to be controlled, sensors for measurement, actuators for control action, and a
control law, usually implemented on a computer. Nonlinearities may occur in any part
of the system, and thus make it a nonlinear control system.
y(t)
controller actuators plant
Figure 5.7 : Block diagram of control systems
CONTINUOUS AND DISCONTINUOUS NONLINEARITIES
Nonlinearities can be classified as continuous and discontinuous. Because
discontinuous nonlinearities cannot be locally approximated by linear functions, they
are also called "hard" nonlinearities. Hard nonlinearities are commonly found in
control systems, both in small range operation and large range operation. Whether a
system in small range operation should be regarded as nonlinear or linear depends on
the magnitude of the hard nonlinearities and on the extent of their effects on the
system performance.
Because of the common occurence of hard nonlinearities, let us briefly discuss
the characteristics and effects of some important ones.
Saturation
When one increases the input to a physical device, the following phenomenon is often
observed: when the input is small, its increase leads to a corresponding (often
proportional) increase of output; but when the input reaches a certain level, its further
=«*_

170 Describing Function Analysis Chap. 5
increase does produces little or no increase of the output. The output simply stays
around its maximum value. The device is said to be in saturation when this happens.
Simple examples are transistor amplifiers and magnetic amplifiers. A saturation
nonlinearity is usually caused by limits on component size, properties of materials,
and available power. A typical saturation nonlinearity is represented in Figure 5.8,
where the thick line is the real nonlinearity and the thin line is an idealized saturation
nonlinearity.
w
/r1
Linear _j
y / 1 x
1
saturation
-* 1
1 saturation
1
Figure 5.8 : A saturation nonlinearity
Most actuators display saturation characteristics. For example, the output
torque of a two-phase servo motor cannot increase infinitely and tends to saturate, due
to the properties of the magnetic material. Similarly, valve-controlled hydraulic servo
motors are saturated by the maximum flow rate.
Saturation can have complicated effects on control system performance.
Roughly speaking, the occurence of saturation amounts to reducing the gain of the
device (e.g., the amplifier) as the input signals are increased. As a result, if a system is
unstable in its linear range, its divergent behavior may be suppressed into a self-
sustained oscillation, due to the inhibition created by the saturating component on the
system signals. On the other hand, in a linearly stable system, saturation tends to slow
down the response of the system, because it reduces the effective gain.
On-off nonlinearity
An extreme case of saturation is the on-off or relay nonlinearity. It occurs when the
linearity range is shrunken to zero and the slope in the linearity range becomes
vertical. Important examples of on-off nonlinearities include output torques of gas jets
for spacecraft control (as in example 2.5) and, of course, electrical relays. On-off
nonlinearities have effects similar to those of saturation nonlinearities. Furthermore
they can lead to "chattering" in physical systems due to their discontinuous nature.

Sect. 5.2 Common Nonlinearities In Control Systems 171
Dead-zone
In many physical devices, the output is zero until the magnitude of the input exceeds a
certain value. Such an input-output relation is called a dead-zone. Consider for
instance a d.c. motor. In an idealistic model, we assume that any voltage applied to
the armature windings will cause the armature to rotate, with small voltage causing
small motion. In reality, due to the static friction at the motor shaft, rotation will
occur only if the torque provided by the motor is sufficiently large. Similarly, when
transmitting motion by connected mechanical components, dead zones result from
manufacturing clearances. Similar dead-zone phenomena occur in valve-controlled
pneumatic actuators and in hydraulic components.
-8
dead zone
Figure 5.9 : A dead-zone nonlinearity
Dead-zones can have a number of possible effects on control systems. Their
most common effect is to decrease static output accuracy. They may also lead to limit
cycles or system instability because of the lack of response in the dead zone. In some
cases, however, they may actually stabilize a system or suppress self-oscillations. For
example, if a dead-zone is incorporated into an ideal relay, it may lead to the
avoidance of the oscillation at the contact point of the relay, thus eliminating sparks
and reducing wear at the contact point. In chapter 8, we describe a dead-zone
technique to improve the robustness of adaptive control systems with respect to
measurement noise.
Backlash and hysteresis
Backlash often occurs in transmission systems. It is caused by the small gaps which
exist in transmission mechanisms. In gear trains, there always exist small gaps
between a pair of mating gears, due to the unavoidable errors in manufacturing and
assembly. Figure 5.10 illustrates a typical situation. As a result of the gaps, when the
driving gear rotates a smaller angle than the gap b, the driven gear does not move at
all, which corresponds to the dead-zone (OA segment in Figure 5.10); after contact
has been established between the two gears, the driven gear follows the rotation of the
driving gear in a linear fashion (AB segment). When the driving gear rotates in the
reverse direction by a distance of 2b, the driven gear again does not move,

172 Describing Function Analysis Chap. 5
corresponding to the BC segment in Figure 5.10. After the contact between the two
gears is re-established, the driven gear follows the rotation of the driving gear in the
reverse direction (CD segment). Therefore, if the driving gear is in periodic motion,
the driven gear will move in the fashion represented by the closed path EBCD. Note
that the height of B, C, D, E in this figure depends on the amplitude of the input
sinusoidal.
driven , driving
;
gear I gear
output
angle
O A
b input
angle
Figure 5.10 : A backlash nonlinearity
A critical feature of backlash is its multi-valued nature. Corresponding to each
input, two output values are possible. Which one of the two occur depends on the
history of the input. We remark that a similar multi-valued nonlinearity is hysteresis,
which is frequently observed in relay components.
Multi-valued nonlinearities like backlash and hysteresis usually lead to energy
storage in the system. Energy storage is a frequent cause of instability and self-
sustained oscillation.
5.3 Describing Functions of Common Nonlinearities
In this section, we shall compute the describing functions for a few common
nonlinearities. This will not only allow us to familiarize ourselves with the frequency
domain properties of these common nonlinearities, but also will provide further
examples of how to derive describing functions for nonlinear elements.
SATURATION
The input-output relationship for a saturation nonlinearity is plotted in Figure 5.11,
with a and k denoting the range and slope of the linearity. Since this nonlinearity is
single-valued, we expect the describing function to be a real function of the inputi

Sect. 5.3 Describing Functions of Common Nonlinearities 173
unsaturated
w(t) output
saturation
saturated
output
sinusoidal
input
CO/
Figure 5.11 : Saturation nonlinearity and the corresponding input-output relationship
amplitude.
Consider the input x(t) = Asin(otf)- If A < a, then the input remains in the linear
range, and therefore, the output is w(t) = kAsin(a)f). Hence, the describing function is
simply a constant k.
Now consider the case A > a. The input and the output functions are plotted in
Figure 5.11. The output is seen to be symmetric over the four quarters of a period. In
the first quarter, it can be expressed as
kA sin(cor)
w(t) =
ka <OH<7l/2
where y= sin ' (a/A). The odd nature of w(t) implies that a\=Q and the symmetry

| 174  Describing Function Analysis |     |     | Chap. 5 |
| --------------------------------- | --- | --- | ------- |
over the four quarters of a period implies that
4  rKl2
| b 1 = -  I  | vv(f) sin(G)0 d(& t) |     |     |
| ----------- | -------------------- | --- | --- |
44rYY
|  r                         | ~   | A ft/2            |     |
| -------------------------- | --- | ----------------- | --- |
| = -  kAsinz{(Ot)d((at)+-\  |     | kasm(<£>t) d(($t) |     |
(5.10)
2kA
Therefore, the describing function is
| b\     | 2k   .  _i a       | a  \,  a2  , |        |
| ------ | ------------------ | ------------ | ------ |
| N(A)=  | =   f[sin  »_ + _  | 1-—]         | (5.11) |
|        | A                  | A-           |        |
The normalized  describing function  (N(A)/k) is plotted in Figure 5.12 as a
function of A/a . One can observe three features for this describing function:
1. N(A) = kif the input amplitude is in the linearity range
2. N(A) decreases as the input amplitude increases
3. there is no phase shift
The first feature is obvious, because for small signals the saturation is not displayed.
The second is intuitively reasonable, since saturation amounts to reduce the ratio of
the output to input. The third is also understandable because saturation does not cause
the delay of the response to input.
As a special case, one can obtain the describing function for the relay-type (on-
off) nonlinearity shown in Figure 5.13. This case corresponds to shrinking the linearity
range in the saturation function to zero, i.e., a —> 0, k —> °°, but ka = M.  Though b\
can be obtained from (5.10) by taking the limit, it is more easily obtained directly as
| 4  i.n/2  |                        | 4   |     |
| --------- | ---------------------- | --- | --- |
| b, = _ I  | Msin(cof) d((Ot) = - M |     |     |
| n Jo      |                        | ft  |     |
Therefore, the describing function of the relay nonlinearity is
| N{A)=™L  |     |     | (5.12) |
| -------- | --- | --- | ------ |
The normalized describing function (N/M) is plotted in Figure 5.13 as a function of
i

| Sect. 5.3 |     | Describing Functions of Common Nonlinearities  |     |     |     | 175 |
| --------- | --- | ---------------------------------------------- | --- | --- | --- | --- |
N(A) 1 k
s—  linearity range
1.0 --t
|     | 0.8 -- !\ |     |     |     |     |     |
| --- | --------- | --- | --- | --- | --- | --- |
i\
|     | 0.6 - • !   | V   |     |     |     |     |
| --- | ----------- | --- | --- | --- | --- | --- |
0.4-•
|     | !   | ^-  | —   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
0.2-•
|     | -4  | 1   | 1  ^ |     |     |     |
| --- | --- | --- | ---- | --- | --- | --- |
Figure 5.12 : Describing function of the
|     | 0  1. | 5.  | 10.  Ala |     |     |     |
| --- | ----- | --- | -------- | --- | --- | --- |
saturation nonlinearity
input amplitude. Although the describing function again has no phase shift, the flat
segment seen in Figure 5.12 is missing in this plot, due to the completely nonlinear
nature of the relay. The asymptic properties of the describing function curve in Figure
5.13 are particularly interesting. When the input is infinitely  small, the describing
function is infinitely large.  When the input is infinitely large, the describing function
is infinitely small.  One can gain an intuitive understanding of these properties by
considering the ratio of the output to input for the on-off nonlinearity.
|     | w   |     | N(A)1M |     |     |     |
| --- | --- | --- | ------ | --- | --- | --- |
on
1  to infinity
1.2-"
M \
1.0-
\  \
|     |     |     | 0.8-^-   V\ |     |     |     |
| --- | --- | --- | ----------- | --- | --- | --- |
0.6-
0
|     |     | X   | 0.4 - |     | to zero ^ |     |
| --- | --- | --- | ----- | --- | --------- | --- |
0.2-
-M
|     | \   |     |        |     | 1    | *-  |
| --- | --- | --- | ------ | --- | ---- | --- |
|     | off |     | 0  1.  | 5.  | 10.  | A   |
Figure 5.13 : Relay nonlinearity and its describing function
DEAD-ZONE
Consider the dead-zone characteristics shown in Figure 5.9, with the dead-zone width
being  25  and  its  slope  k.  The  response  corresponding  to  a  sinusoidal  input
x(t) = Asin(cor) into a dead-zone of width 28 and slope k, with  A >5, is plotted in
Figure 5.14.  Since the characteristics is an odd function, a = 0. The response is also
l
seen to be symmetric over the four quarters of a period.  In one quarter of a period,
i.e., when 0 < (at < n/2, one has

176 Describing Function Analysis Chap. 5 t
Figure 5.14 : Input and output functions for a dead-zone nonlinearity
0 O<co/<y
£(Asin(a>O-S) y<a>t< n/2
where y = sin ' (8/A). The coefficient bj can be computed as follows
4 ,rc/2 4 .71/2
b\ = - w(t) sin(au) d{u>t) = - i(Asin(co/) - 8) sin(cor) d((Ot)
KJ0 KJy
( (5.13) |
it 2
This leads to
A A
This describing function /V(A) is a /-ea/ function and, therefore, there is no phase shift

Sect. 5.3 Describing Functions of Common Nonlineariti.es 177
(reflecting the absence of time-delay). The normalized describing function is plotted in
Figure 5.15. It is seen that N(A)/k is zero when A/8 < 1, and increases up to 1 with
A/8. This increase indicates that the effect of the dead-zone gradually diminishes as
the amplitude of the input signal is increased, consistently with intuition.
Figure 5.15 : Describing function of the
dead-zone nonlinearity
BACKLASH
The evaluation of the describing functions for backlash nonlinearity is more tedious.
Figure 5.16 shows a backlash nonlinearity, with slope k and width 2b. If the input
amplitude is smaller than b, there is no output. In the following, let us consider the
input being x(t) = A sin(tt)f), A > b . The output w(t) of the nonlinearity is as shown in
the figure. In one cycle, the function w(t) can be represented as
w(t) = {A -b)k cor < 7t-y
w(t) = {A sin(co t) + b)k n- <a>t<2n
~~2~
3TC
w(t) = ~(A -b)k <oit<2n-y
T
5n
w(t) = (/4sin(cor) -b)k <
2
where y= sin'1 (1 - 2b/A).
Unlike the previous nonlinearities, the function w{t) here is neither odd nor even.
Therefore, «j and b\ are both nonzero. Using (5.7b) and (5.7c), we find through some
tedious integrations that

178  Describing Function Analysis Chap. 5
(0/
Figure 5.16 : Input and output functions for a backlash nonlinearity
| 4kb  ,b  ,, |       |      |
| ----------- | ----- | ---- |
| 1  jr.  2   | A  A  | i  A |
Therefore, the describing function of the backlash is given by
(5.14a)
(5.14b)
The amplitude of the describing function for backlash is plotted in Figure 5.17.
We note a few interesting points :

Sect. 5.4 Describing Function A nalysis of Nonlinear Systems 179
0 0.2 0.4 0.6 0.8 1.0 JL Figure 5.17 : Amplitude of describing
A
function for backlash
l.\N(A)\ = 0 ifA=b.
2. \N{A)\ increases, when b/A decreases.
3. |W(/4)|-> 1 as b/A-^ 0.
The phase angle of the describing function is plotted in Figure 5.18. Note that a phase
lag (up to 90°) is introduced, unlike the previous nonlinearities. This phase lag is the
reflection of the time delay of the backlash, which is due to the gap b. Of course, a
larger b leads to a larger phase lag, which may create stability problems in feedback
control systems.
IK
o
-20
-40
-60
-90
0 0.2 0.4 0.6 0.8 1.0 b_ Figure 5.18 : Phase angle of describing
A
function for backlash (degree)
5.4 Describing Function Analysis of Nonlinear Systems
For a nonlinear system containing a nonlinear element, we now know how to obtain a
decribing function for the nonlinear element. The next step is to formalize the
procedure in subsection 5.1.1 for the prediction of limit cycles, based on the

180 Describing Function Analysis Chap. 5
describing function representation of the nonlinearity. The basic approach to achieve
this is to apply an extended version of the famous Nyquist criterion in linear control to
the equivalent system. Let us begin with a short review of the Nyquist criterion and
its extension.
5.4.1 The Nyquist Criterion and Its Extension
Consider the linear system of Figure 5.19. The characteristic equation of this system is
8(p) = 1 + G(p) H(p) = 0
Note that 8(p), often called the loop transfer function, is a rational function of p, with
its zeros being the poles of the closed-loop system, and its poles being the poles of the
open-loop transfer function G(p) H(p). Let us rewrite the characteristic equation as
G(p) H(p) = -l
G(p)
H(p)
Figure 5.19 : Closed-loop linear system
Based on this equation, the famous Nyquist criterion can be derived straightforwardly
from the Cauchy theorem in complex analysis. The criterion can be summarized
(assuming that G(p) H(p) has no poles or zeros on the yco axis) in the following
procedure (Figure 5.20):
1. draw, in the p plane, a so-called Nyquist path enclosing the right-half
plane
2. map this path into another complex plane through G(p)H{p)
3. determine /V, the number of clockwise encirclements of the plot of
G{p)H{p) around the point (- 1,0)
4. compute Z, the number of zeros of the loop transfer function 5(p) in the
right-half p plane, by
Z = N + P , where P is the number of unstable poles of 5(p)
Then the value of Z is the number of unstable poles of the closed-loop system.
J

Sect. 5.4 Describing Function Analysis of Nonlinear Systems 181
p plane G(p)H(p)
+ 00 Nyquist path
co-> +co
-co
Figure 5.20 : The Nyquist criterion
A simple formal extension of the Nyquist criterion can be made to the case
when a constant gain K (possibly a complex number) is included in the forward path
in Figure 5.21. This modification will be useful in interpreting the stability analysis of
limit cycles using the describing function method. The loop transfer function becomes
8(p)=l+KG(p)H(p)
with the corresponding characteristic equation
G(p)H(p) = -
The same arguments as used in the derivation of Nyquist criterion suggest the same
procedure for determining unstable closed-loop poles, with the minor difference that
now Z represents the number of clockwise encirclements of the G(p) H(p) plot around
the point - l/K. Figure 5.21 shows the corresponding extended Nyquist plot.
Im
G(p) H(p)
0
—• K G(p) —
H(p)
Figure 5.21 : Extension of the Nyquist criterion

182 Describing Function Analysis Chap. 5
5.4.2 Existence of Limit Cycles
Let us now assume that there exists a self-sustained oscillation of amplitude A and
frequency co in the system of Figure 5.22. Then the variables in the loop must satisfy
the following relations:
x = -y
w = N(A,(o)x
Therefore, we have y = G(j(£>)N(A,(i))(-y). Because y * 0, this implies
GO'co) N(A,(0) +1=0 (5.15)
which can be written as
1
G0"«»=- (5.16)
N(A,(o)
Therefore, the amplitude A and frequency CO of the limit cycles in the system must
satisfy (5.16). If the above equation has no solutions, then the nonlinear system has no
limit cycles.
Expression (5.16) represents two nonlinear equations (the real part and
imaginary part each give one equation) in the two variables A and CO. There are
usually a finite number of solutions. It is generally very difficult to solve these
equations by analytical methods, particularly for high-order systems, and therefore, a
graphical approach is usually taken. The idea is to plot both sides of (5.16) in the
complex plane and find the intersection points of the two curves.
Describing
Function Linear Element
r(t) = 0 x(t) w(t) y(t)
N(A, CO) WCO)
r *
Figure 5.22 : A nonlinear system

Sect. 5.4 Describing Function Analysis of Nonlinear Systems 183
FREQUENCY-INDEPENDENT DESCRIBING FUNCTION
First, we consider the simpler case when the describing function N being a function of
the gain A only, i.e., N(A, co) = N(A). This includes all single-valued nonlinearities
and some important double-valued nonlinearities such as backlash. The equality
becomes
1
(5.17)
N(A)
We can plot both the frequency response function G(j(o) (varying co) and the negative
inverse describing function (- l/N(A)) (varying A) in the complex plane, as in Figure
5.23. If the two curves intersect, then there exist limit cycles, and the values of A and
co corresponding to the intersection point are the solutions of Equation (5.17). If the
curves intersect n times, then the system has n possible limit cycles. Which one is
actually reached depends on the initial conditions. In Figure 5.23, the two curves
intersect at one point K. This indicates that there is one limit cycle in the system. The
amplitude of the limit cycle is A^, the value of A corresponding to the point K on the
- l/N(A) curve. The frequency of the limit cycle is co^ , the value of co corresponding
to the point K on the G(jco) curve.
Figure 5.23 : Detection of limit cycles
Note that for single-valued nonlinearities, N is real and therefore the plot of
- l/N always lies on the real axis. It is also useful to point out that, as we shall
discuss later, the above procedure only gives a prediction of the existence of limit
cycles. The validity and accuracy of this prediction should be confirmed by computer
simulations.
We already saw in section 5.1.1 an example of the prediction of limit cycles, for
the Van der Pol equation.

184 Describing Function Analysis Chap. 5
FREQUENCY-DEPENDENT DESCRIBING FUNCTION
For the general case, where the describing function depends on both input amplitude
and frequency (N = N(A, co)), the method can be applied, but with more complexity.
Now the right-hand side of (5.15), - l/N(A, co) , corresponds to a family of curves on
the complex plane with A as the running parameter and co fixed for each curve, as
shown in Figure 5.24. There are generally an infinite number of intersection points
between the G(y'co) curve and the - 1/N(A, co) curves. Only the intersection points with
matched co indicate limit cycles.
Im
Figure 5.24 : Limit cycle detection for
frequency-dependent describing functions
To avoid the complexity of matching frequencies at intersection points, it may
be advantageous to consider the graphical solution of (5.16) directly, based on the
plots of G(ja>)N(A, co). With A fixed and co varying from 0 to °°, we obtain a curve
representing G(J(o)N{A,(o). Different values of A correspond to a family of curves, as
shown in Figure 5.25. A curve passing through the point (- 1,0) in the complex plane
indicates the existence of a limit cycle, with the value of A for the curve being the
amplitude of the limit cycle, and the value of co at the point (- 1,0) being the
frequency of the limit cycle. While this technique is much more straightforward than
the previous one, it requires repetitive computation of the G(/co) in generating the
family of curves, which may be handled easily by computer.
5.4.3 Stability of Limit Cycles
As pointed out in chapter 2, limit cycles can be stable or unstable. In the above, we
have discussed how to detect the existence of limit cycles. Let us now discuss how to
determine the stability of a limit cycle, based on the extended Nyquist criterion in
section 5.4.1.
Consider the plots of frequency response and inverse describing function in
Figure 5.26. There are two intersection points in the figure, predicting that the system

Sect. 5.4 Describing Function Analysis of Nonlinear Systems 185
Figure 5.25 Solving equation (5.15)
G(j(o)N(A,a>)
graphically
has two limit cycles. Note that the value of A corresponding to point L[ is smaller
than the value of A corresponding to L. For simplicity of discussion, we assume that
2
the linear transfer function G(p) has no unstable poles.
Im
Figure 5.26 : Limit Cycle Stability
Let us first discuss the stability of the limit cycle at point Lj. Assume that the
system initially operates at point Lj, with the limit cycle amplitude being A[, and its
frequency being 00|. Due to a slight disturbance, the amplitude of the input to the
nonlinear element is slightly increased, and the system operating point is moved from
Lj to L| . Since the new point L] is encircled by the curve of G(ju>), according to the
extended Nyquist criterion mentioned in section 5.4.1, the system at this operating
point is unstable, and the amplitudes of the system signals will increase. Therefore, the
operating point will continue to move along the curve - ]/N(A ) toward the other limit
cycle point L. On the other hand, if the system is disturbed so that the amplitude A as
2
decreased, with the operating point moved to the point Lj", then A will continue to
decrease and the operating point moving away from L in the other direction. This is
l

186 Describing Function Analysis Chap. 5
because L{ is not encircled by the curve G(yco) and thus the extended Nyquist plot
asserts the stability of the system. The above discussion indicates that a slight
disturbance can destroy the oscillation at point Lj and, therefore, that this limit cycle is
unstable. A similar analysis for the limit cycle at point L2 indicates that that limit
cycle is stable.
Summarizing the above discussion and the result in the previous subsection, we
obtain a criterion for existence and stability of limit cycles:
Limit Cycle Criterion: Each intersection point of the curve G(j(o) and the curve
- l/N(A) corresponds to a limit cycle. If points near the intersection and along the
increasing-A side of the curve - 1 /N(A) are not encircled by the curve G(jai) , then
the corresponding limit cycle is stable. Otherwise, the limit cycle is unstable.
5.4.4 Reliability of Describing Function Analysis
Empirical evidence over the last three decades, and later theoretical justification,
indicate that the describing function method can effectively solve a large number of
practical control problems involving limit cycles. However, due to the approximate
nature of the technique, it is not surprising that the analysis results are sometimes not
very accurate. Three kinds of inaccuracies are possible:
1. The amplitude and frequency of the predicted limit cycle are not
accurate
2. A predicted limit cycle does not actually exist
3. An existing limit cycle is not predicted
The first kind of inaccuracy is quite common. Generally, the predicted
amplitude and frequency of a limit cycle always deviate somewhat from the true
values. How much the predicted values differ from the true values depends on how
well the nonlinear system satisfies the assumptions of the describing function method.
In order to obtain accurate values of the predicted limit cycles, simulation of the
nonlinear system is necessary.
The occurrence of the other two kinds of inaccuracy is less frequent but has
more serious consequences. Usually, their occurrence can be detected by examining
the linear element frequency response and the relative positions of the G plot and
- l/.V plot.
\ 'iolation of filtering hypothesis: The validity of the describing function method relies
on the filtering hypothesis defined by (5.5). For some linear elements, this hypothesis

Sect. 5.5 Summary 187
is not satisfied and errors may result in the describing function analysis. Indeed, a
number of failed cases of describing function analysis occur in systems whose linear
element has resonant peaks in its frequency response G(/a>).
Graphical Conditions: If the G(yco) locus is tangent or almost tangent to the - l/N
locus, then the conclusions from a describing function analysis might be erroneous.
Such an example is shown in Figure 5.27(a). This is because the effects of neglected
higher harmonics or system model uncertainty may cause the change of the
intersection situations, particularly when filtering in the linear element is weak. As a
result, the second and third types of errors listed above may occur. A classic case of
this problem involves a second-order servo with backlash studied by Nychols. While
describing function analysis predicts two limit cycles (a stable one at high frequency
and an unstable one at low frequency), it can be shown that the low-frequency
unstable limit cycle does not exist.
Im Im
- 1 IN(A)
(a) (b)
Figure 5.27 : Reliability of limit cycle prediction
Conversely, if the - l/N locus intersects the G locus almost perpendicularly,
then the results of the describing function are usually good. An example of this
situation is shown in Figure 5.27(b).
5.5 Summary
The describing function method is an extension of the frequency response method of
linear control. It can be used to approximately analyze and predict the behavior of
important classes of nonlinear systems, including systems with hard nonlinearities.
The desirable properties it inherits from the frequency response method, such as its

188 Describing Function Analysis Chap. 5
graphical nature and the physically intuitive insights it can provide, make it an
important tool for practicing engineers. Applications of the describing function
method to the prediction of limit cycles were detailed. Other applications, such as
predicting subharmonics, jump phenomena, and responses to external sinusoidal
inputs, can be found in the literature.
5.6 Notes and References
An extensive and clear presentation of the describing function method can be found in [Gelb and
VanderVelde, 1968]. A more recent treatment is contained in [Hedrick, el al., 1982], which also
discusses specific applications to nonlinear physical systems. The describing function method was
developed and successfully used well before its mathematical justification was completely
formalized [Bergen and Franks, 1971]. Figures 5.14 and 5.16 are adapted from [Shinners, 1978]. The
Van der Pol oscillator example is adapted from [Hsu and Meyer, 1968].
5.7 Exercises
5.1 Determine whether the system in Figure 5.28 exhibits a self-sustained oscillation limit
cycle). If so, determine the stability, frequency, and amplitude of the oscillation.
+1'
H) K
p(p + >)(p+ 2)
-1
Figure 5.28 : A nonlinear system containing a relay
5.2 Determine whether the system in Figure 5.29 exhibits a self-sustained oscillation. If so,
determine the stability, frequency, and amplitude of the oscillation.
5.3 Consider the nonlinear system of Figure 5.30. Determine the largest K which preserves the
stability of the system. If K = 2K , find the amplitude and frequency of the self-sustained
max
oscillation.
5.4 Consider the system of Figure 5.31, which is composed of a high-pass filter, a saturation
function, and the inverse low-pass filter. Show that the system can be viewed as a nonlinear low-
A

Sect. 5.7 Exercises 189
Y = 0
p(p
Figure 5.29 : A nonlinear system
containing a dead-zone
pass filter, which attenuates high-frequency inputs without introducing a phase lag.
5.5 This exercise is based on a result of [Tsypkin, 1956].
Consider a nonlinear system whose output w(t) is related to the input u(t) by an odd function,
of the form
w(t) = F(u(t)) = - F( - u(t)) (5.18)
Derive the following very simple approximate formula for the describing function N(A)
N{A) = JL [ F(A) + F(AI2) ]
To this effect, you may want to use the fact that
fix)
-dx = -
6
where the remainder R verifies R = /6©/(2^6!) for some £€(-1,1). Show that
approximation (5.18) is quite precise (how precise?).
o 20
K
20 p(l+0.1p)(l+0.02p)
Figure 5.30 : A nonlinear system containing a saturation
*^

190 Describing Function Analysis Chap. S
+1
v
k- x p+l
2
+1
v
^ i » V+i
_/
a
Figure 5.31: A nonlinear low-pass filter
Invert (5.18) so as to obtain for the input-output relation a solution of the form
5.6 In this exercise, adapted form [Phillips and Harbor, 1988], let us consider the system of Figure 31
5.32, which is typical of the dynamics of electronic oscillators used in laboratories, with
-5p
G(p) =
+25
Use describing function analysis to predict whether the system exhibits a limit cycle, depending on jj
the value of the saturation level k. In such cases, determine the limit cycle's frequency and *
amplitude. %
Saturation Linear Element
w(t) y(')
G(p)
Figure 5.32 : Dynamics of an electronic oscillator
Interpret intuitively, by assuming that the system is started at some small initial state, and
noticing that y{t) can stay neither at small values (because of instability) nor at saturation values (by
applying the final value theorem of linear control).

Part II
Nonlinear Control Systems Design
In Part I, we studied how to analyze the behavior of a nonlinear control system,
assuming that the control system had been designed. Part II is devoted to the problem
of designing nonlinear control systems. In this introduction, we discuss some general
issues involved in nonlinear control system design, particularly emphasizing the
differences of nonlinear control design problems from linear ones. In the following
chapters, we will detail the specific control methods available to the designer.
As pointed out in chapter 1, the objective of control design can be stated as
follows: given a physical system to be controlled and the specifications of its desired
behavior, construct a feedback control law to make the closed-loop system display the
desired behavior. In accordance with this design objective, we consider a number of
key issues. First, two basic types of nonlinear control problems, nonlinear regulation
and nonlinear tracking, are defined. Next, the specifications of the desired behavior of
nonlinear control systems are discussed. Basic issues in constructing nonlinear
controllers are then outlined. Finally, the major methods available for designing
nonlinear controllers are briefly surveyed.
191

192 Nonlinear Control Systems Design Part II
II. 1 Nonlinear Control Problems
If the tasks of a control system involve large range and/or high speed motions,
nonlinear effects will be significant in the dynamics and nonlinear control may be
necessary to achieve the desired performance. Generally, the tasks of control systems
can be divided into two categories: stabilization (or regulation) and tracking (or
servo). In stabilization problems, a control system, called a stabilizer (or a regulator),
is to be designed so that the state of the closed-loop system will be stabilized around
an equilibrium point. Examples of stabilization tasks are temperature control of
refrigerators, altitude control of aircraft and position control of robot arms. In tracking
control problems, the design objective is to construct a controller, called a tracker, so
that the system output tracks a given time-varying trajectory. Problems such as
making an aircraft fly along a specified path or making a robot hand draw straight
lines or circles are typical tracking control tasks.
STABILIZATION PROBLEMS
In order to facilitate the analytic study of stabilization and tracking design in the later
chapters, let us provide some formal definitions of stabilization and tracking problems.
Asymptotic Stabilization Problem: Given a nonlinear dynamic system described by
x = f(x, u, t)
find a control law u such that, starting from anywhere in a region in Q., the state x
tends toQ as t —> °o .
If the control law depends on the measurement signals directly, it is said to be a
static control law. If it depends on the measurement through a differential equation,
the control law is said to be a dynamic control law, i.e., there is dynamics in the
control law. For example, in linear control, a proportional controller is a static
controller, while a lead-lag controller is a dynamic controller.
Note that, in the above definition, we allow the size of the region Q. to be large;
otherwise, the stabilization problem may be adequately solved using linear control.
Note also that if the objective of the control task is to drive the state to some non-zero
set-point x, we can simply transform the problem into a zero-point regulation
d
problem by taking x - \ as the state.
d

Nonlinear Control Problems 193
(a) (b)
Figure II.l : (a) a pendulum; (b) an inverted pendulum, with cart
Example II.l: Stabilization of a pendulum
Consider the pendulum in Figure II. 1 (a). Its dynamics is
T (II.l)
Assume that our task is to bring the pendulum from a large initial angle, say 6(0) = 60° , to the
vertical-up position. One choice of the stabilizer is
) — k 6 — mglsinQ (H.2)
with k and k denoting positive constants, This leads to the following globally stable closed-loop
d
dynamics
i.e., the controlled pendulum behaves as a stable mass-spring-damper system. Note that the
controller (II.2) is composed of a P.D. (proportional pius derivative) feedback part for stability
and a feedforward part for gravity compensation. Another interesting controller is
which leads to the stable closed-loop dynamics
This amounts to artificially reverting the gravity field and adding viscous damping.
This example illustrates the point that feedback and feedforward control actions amount to
modifying the dynamics of the plant into a desirable form. Lj
However, many nonlinear stabilization problems are not so easy to solve. One
such example is the inverted pendulum shown in Figure H.l(b) which can be easily
shown to have the following dynamics

194 Nonlinear Control Systems Design Part II
(M + m)x+mlcosQQ-mlsmQQ2 = u (II.4a)
m'x cosG + ml 8 - mgsinQ = 0 (II.4b)
(where the mass of the cart is not assumed to be negligible). A particularly interesting
task is to design a controller to bring the inverted pendulum from a vertical-down
position at the middle of the lateral track to a vertical-up position at the same lateral
point. This seeming simple nonlinear control problem is surprisingly difficult to solve
in a systematic fashion (see Exercise II.5). This problem arises because there are two
degrees of freedom and only one input.
TRACKING PROBLEMS
The task of asymptotic tracking can be defined similarly.
Asymptotic Tracking Problem: Given a nonlinear dynamics system described by
x = f(x, u, t)
y = h(x)
and a desired output trajectory y^, find a control law for the input u such that,
starting from any initial state in a region O, the tracking errors y(t) - y^f) go to zero,
while the whole state x remains bounded.
Note that, from a practical point of view, one may require that x actually remain
"reasonably" bounded, and, in particular, within the range of validity of the system
model. This may be verified either analytically, or in simulations.
When the closed-loop system is such that proper initial states imply zero
tracking error for all the time,
y(0 = y<fit) Vr>o
the control system is said to be capable of perfect tracking. Asymptotic tracking
implies that perfect tracking is asymptotically achieved. Exponential tracking
convergence can be defined similarly.
Throughout the rest of the book, unless otherwise specified, we shall make the
mild assumption that the desired trajectory y^ and its derivatives up to a sufficiently
high order (generally equal to the system's order) are continuous and bounded. We
also assume that yj(t) and its derivatives are available for on-line control computation.
This latter assumption is satisfied by control tasks where the desired output y {i) is
d
planned ahead of time. For example, in robot tracking tasks, the desired position
history is generally planned ahead of time and its derivatives can be easily obtained.
i

Nonlinear Control Problems 195
Actually, smooth time-histories are often generated themselves through a filtering
process, thereby automatically providing higher derivatives of the desired output. In
some tracking tasks, however, the assumption is not satisfied, and a so-called
reference model may be used to provide the required derivative signals. For example,
in designing a tracking control system for the antenna of a radar so that it will closely
point toward an aircraft at all times, we only have the position of the aircraft y {f)
a
available at a given time instant (assuming that it is too noisy to be numerically
differentiated). However, generally the tracking control law will also use the
derivatives of the signals to be tracked. To solve this problem, we can generate the
desired position, velocity and acceleration to be tracked by the antenna using the
following second-order dynamics
y'd+k\y<i+hyd = hyjfi (IL5>
where k and £ are chosen positive constants. Thus the problem of following the
l 2
aircraft is translated into the problem of tracking the output yjjt) of the reference
model. Note that the reference model serves the dual purpose of providing the desired
output of the tracking system in response to the aircraft position measurements, and
generating the derivatives of the desired output for tracker design. Of course, for the
approach to be effective, the filtering process described by (II.5) should be fast enough
for y^t) to closely approximate y{t).
a
For non-minimum phase systems (precise definitions of nonlinear non-
minimum phase systems will be provided in chapter 6), perfect tracking and
asymptotic tracking cannot be achieved, as seen in the following example.
Example II.2: Tracking control of a non-minimum phase linear system
Consider the linear system
y + 2y + 2y = — it + u
The system is non-minimum phase because it has a zero at p = 1. Assume that perfect tracking is
achieved, i.e., that y(l) = }></('). V ? > 0. Then, the input u satisfies
u-u = -(y+2y + 2y)
d d d
Since this represents an unstable dynamics, u diverges exponentially. Note that the above
dynamics has a pole which exactly coincides with the unstable zero of the original system, i.e.,
perfect tracking for non-minimum phase systems can be achieved only by infinite control inputs.
By writing u as
p2 + 2n + 2
" = " -\ yd
P

196 Nonlinear Control Systems Design Part II
we see that the perfect-tracking controller is actually inverting the plant dynamics. C]
The inability of perfect tracking for a non-minimum phase linear system has its
roots in its inherent tendency of "undershooting" in its step response. Thus, the control
design objective for non-minimum phase systems should not be perfect tracking or
asymptotic tracking. Instead, we should be satisfied with, for example, bounded-error
tracking, with small tracking error being achieved for desired trajectories of particular
interest.
RELATIONS BETWEEN STABILIZATION AND TRACKING PROBLEMS
Normally, tracking problems are more difficult to solve than stabilization
problems, because in tracking problems the controller should not only keep the whole
state stabilized but also drive the system output toward the desired output. However,
from a theoretical point of view, tracking design and stabilization design are often
related. For instance, if we are to design a tracker for the plant
y+f(y,y,u) = o
so that e(t) = y(t) — y^t) goes to zero, the problem is equivalent to the asymptotic
stabilization of the system
e+f(e,e,u,y ,y ,y ) = O (II.6)
d d d
whose state components are e and e. Clearly, the tracker design problem is solved if
we know how to design a stabilizer for the non-autonomous dynamics (II.6).
On the other hand, stabilization problems can often be regarded as a special
case of tracking problems, with the desired trajectory being a constant. In model
reference control, for instance, a set-point regulation problem is transformed into a
tracking problem by incorporating a reference model to filter the supplied set-point
value and generate a time-varying output as the ideal response for the tracking control
system.
II.2 Specifying the Desired Behavior
In linear control, the desired behavior of a control system can be systematically
specified, either in the time-domain (in terms of rise time, overshoot and settling time
corresponding to a step command) or in the frequency domain (in terms of regions in
which the loop transfer function must lie at low frequencies and at high frequencies).
In linear control design, one first lays down the quantitative specifications of the
closed-loop control system, and then synthesizes a controller which meets these
A

Specifying the Desired Behavior 197
specifications. However, systematic specification for nonlinear systems (except those
equivalent to linear systems) is much less obvious because the response of a nonlinear
system to one command does not reflect its response to another command, and
furthermore a frequency-domain description is not possible.
As a result, for nonlinear systems, one often looks instead for some qualitative
specifications of the desired behavior in the operating region of interest. Computer
simulation is an important complement to analytical tools in determining whether such
specifications are met. Regarding the desired behavior of nonlinear control systems, a
designer can consider the following characteristics:
Stability must be guaranteed for the nominal model (the model used for
design), either in a local sense or in a global sense. The region of stability and
convergence are also of interest.
Accuracy and speed of response may be considered for some "typical" motion
trajectories in the region of operation. For some classes of systems, appropriate
controller design can actually guarantee consistent tracking accuracy independently of
the desired trajectory, as discussed in chapter 7.
Robustness is the sensitivity to effects which are not considered in the design,
such as disturbances, measurement noise, unmodeled dynamics, etc. The system
should be able to withstand these neglected effects when performing the tasks of
interest.
Cost of a control system is determined mainly by the number and type of
actuators, sensors, and computers necessary to implement it. The actuators, sensors
and the controller complexity (affecting computing requirement) should be chosen
consistently and suit the particular application.
A couple of remarks can be made at this point. First, stability does not imply the
ability to withstand persistent disturbances of even small magnitude (as discussed in
section 4.9.2). The reason is that stability of a nonlinear system is defined with respect
to initial conditions, and only temporary disturbances may be translated as initial
conditions. For example, a stable control system may guarantee an aircraft's ability to
withstand gusts, while being inept at handling windshears even of small magnitude.
This situation is different from that of linear control, where stability always implies
ability to withstand bounded disturbances (assuming that the system does stay in its
linear range). The effects of persistent disturbance on nonlinear system behavior are
addressed by the concept of robustness. Secondly, the above qualities conflict to some
extent, and a good control system can be obtained only based on effective trade-offs in
terms of stability/robustness, stability/performance, cost/performance, and so on.

198 Nonlinear Control Systems Design Part II
II.3 Some Issues In Constructing Nonlinear Controllers
We now briefly describe a few aspects of controller design.
A Procedure for Control Design
Given a physical system to be controlled, one typically goes through the following
standard procedure, possibly with a few iterations:
1. specify the desired behavior, and select actuators and sensors;
2. model the physical plant by a set of differential equations;
3. design a control law for the system;
4. analyze and simulate the resulting control system;
5. implement the control system in hardware.
Experience, creativity, and engineering judgment are all important in this process. One
should consider integrating control design with plant design if possible, similarly to
the many advances in aircraft design which have been achieved using linear control
techniques. Sometimes the addition or relocation of actuators and sensors may make
an otherwise intractable nonlinear control problem easy.
Modeling Nonlinear Systems
Modeling is basically the process of constructing a mathematical description (usually
a set of differential equations) for the physical system to be controlled. Two points can
be made about modeling. First, one should use good understanding of the system
dynamics and the control tasks to obtain a tractable yet accurate model for control
design. Note that more accurate models are not always better, because they may
require unnecessarily complex control design and analysis and more demanding
computation. The key here is to keep "essential" effects and discard insignificant
effects in the system dynamics in the operating range of interest. Second, modeling is
more than obtaining a nominal model for the physical system: it should also provide
some characterization of the model uncertainties, which may be used for robust
design, adaptive design, or merely simulation.
Model uncertainties are the differences between the model and the real physical
system. Uncertainties in parameters are called parametric uncertainties while the
others are called non-parametric uncertainties. For example, for the model of a
controlled mass
m'x = u

Some Issues In Constructing Nonlinear Controllers 199
the uncertainty in m is parametric uncertainty, while the neglected motor dynamics,
measurement noise, sensor dynamics are non-parametric uncertainties. Parametric
uncertainties are often easy to characterize. For example, m may be known to lie
somewhere between 2 kg and 5 kg. The characterization of unmodeled dynamics for
nonlinear systems is often more difficult, unlike the linear control case where
frequency-domain characterizations can be systematically applied.
Feedback and Feedforward
In nonlinear control, the concept of feedback plays a fundamental role in controller
design, as it does in linear control. However, the importance of feedforward is much
more conspicuous than in linear control. Feedforward is used to cancel the effects of
known disturbances and provide anticipative actions in tracking tasks. Very often it is
impossible to control a nonlinear system stably without incorporating feedforward
action in the control law. Note that a model of the plant is always required for
feedforward compensation (although the model need not be very accurate).
Asymptotic tracking control always requires feedforward actions to provide the
forces necessary to make the required motion. It is interesting to note that many
tracking controllers can be written in the form
u = feedforward + feedback
or in a similar form. The feedforward part intends to provide the necessary input for
following the specified motion trajectory and canceling the effects of the known
disturbances. The feedback part then stabilizes the tracking error dynamics.
As an illustration of the use of feedforward, let us consider tracking controller
design in the familiar context of linear systems (as applicable to devices such as an x-y
plotter, for instance). The discussion is interesting in its own right, since tracking of
time-varying trajectories is not commonly emphasized in linear control texts.
Example H.3: Tracking control of linear systems
Consider a linear (controllable and observable) minimum-phase system in the form
A{p)y = B(p)u (II.7)
where
a + ap + .... + a_p"-i + p"
o l n l
The control objective is to make the output y(t) follow a time-varying desired trajectory yjit). We

200 Nonlinear Control Systems Design Part II
assume that only the output y(t) is measured, and that y^, y, ...,yj-r^ are known, with r being the
d
relative degree (the excess of poles over zeros) of the transfer function (thus, r=n-m).
The control design can be achieved in two steps. First, let us take the control law in the form
of
where v is a new input to be determined. Substitution of (II.8) into (II.7) leads to
A(p)e = B(p)v (II.9)
where e(t) = y(t) - yjf) is the tracking error. The feedforward signal (AIB) y can be computed as
d
A - (r)
where the a,- (i = 1,..., r) are constants obtained from dividing A by B, and w(t) is a filtered
version of yjj).
The second step is to construct input u so that the error dynamics is asymptotically stable.
Since e is known (by subtracting the known y from the measured y), while its derivatives are not,
d
one can stabilize e by using standard linear techniques, e.g., pole-placement together with a
Luenberger observer. A simpler way of deriving the control law is to let
(11.10)
D(p)
with C and D being polynomials of order (n-m). With this control law, the closed loop dynamics
is
If the coefficients of C and D are chosen properly, the poles of the closed-loop polynomial can be
placed anywhere in the complex plane (with the complex poles in conjugate pairs), as we shall
see in chapter 8. Therefore, the control law
" = 5^ + §< (IL11)
will guarantee that the tracking error e(t) remains at zero if initial conditions satisfy
yl'\0) = yJ-'XQ) (i = 1, ... ,;), and exponentially converges to zero if the initial conditions do not
satisfy these conditions.
The block diagram of the closed-loop system is depicted in Figure II.3. We can make the J
following comments about the control system:

Some Issues In Constructing Nonlinear Controllers 201
A
B
~1 C B y
D A
Figure II.2 : Linear Tracking Control system
• The feedforward part of the control law, computed by inverting the plant model, is
responsible for reducing and eliminating the tracking errors, while the feedback part
results in stability of the whole system. If some derivatives of the desired trajectories
yj,t) are not available, one can simply omit them from the feedforward, which will only
cause bounded error in tracking. Note that one may easily adapt the above controller for
model reference control, with y and its derivatives provided by the reference model.
d
• The control law (11.10) is equivalent to implementing a reduced-order Luenberger
observer. Higher order observers can also be used, possibly for the purpose of increasing
system robustness by exploiting the added flexibility.
• The above method cannot be directly used for tracking control of non-minimum phase
systems (with some of the roots of B(p) having positive real parts) since the inverse
model A/B is unstable. However, by feedforwarding low-frequency components of the
desired trajectories, good tracking in the low-frequency range (lower than the left-half
plane zeros of the plant) may still be achieved. For instance, by using (A/B) y as the
{ d
feedforward signal, the tracking error can be easily found to be
C B
e(t) =
AC+BDLB
If B| is close to B at low frequencies, the control system can track a slowly varying yj{i)
well. One particular choice of 6| is to eliminate the right half-plane zeros of B, which
will lead to good tracking for desired trajectories with frequencies lower than the right
half-plane zeroes. C]
Importance of Physical Properties
In linear control, it is common practice to generate a set of differential equations for a
physical system, and then forget where they came from. This presents no major
problem there, at least in a theoretical sense, because linear control theory provides

202 Nonlinear Control Systems Design Part II
powerful tools for analysis and design. However, such a procedure is typically
undesirable for nonlinear systems, because the number of tools available for attacking
nonlinear problems is comparatively limited. In nonlinear control design, exploitation
of the physical properties can sometimes make control design for complex nonlinear
plants a simple issue, or may easily solve an otherwise intractable design problem.
This point is forcibly demonstrated in the solution of the adaptive robot control
problem. Adaptive control of robot manipulators was long recognized to be far out of
the reach of conventional adaptive control theory, because a robot's dynamics is
strongly nonlinear and has multiple inputs. However, the use of two physical facts,
namely, the positive definiteness of the inertia matrix and the possibility of linearly
parametrizing robot dynamics, successfully led to an adaptive controller with the
desirable properties of global stability and tracking convergence, as shown in
chapter 9.
Discrete Implementations
As discussed in chapter 1, nonlinear physical systems are continuous in nature and are
hard to meaningfully discretize, while digital control systems may be treated as
continuous-time systems in analysis and design if high sampling rates are used
(specific quantifications are discussed, e.g., in section 7.3). Thus, we perform
nonlinear system analysis and controller design in continuous-time form. However, of
course, the control law is generally implemented digitally.
Numerical integration and differentiation are sometimes explicit parts of a
controller design. Numerical differentiation may avoid the complexity of constructing
the whole system state based on partial measurements (the nonlinear observer
problem), while numerical integration is a standard component of most adaptive
controller designs, and can also be needed more generally in dynamic controllers.
Numerical differentiation may be performed in many ways, all aimed at getting
a reasonable estimate of the time-derivative, while at the same time avoiding the
generation of large amounts of noise. One can use, for instance, a filtered
differentiation of the form
p+a p+a
where p is the Laplace variable and a » 1 . The discrete implementation of the
above equation, assuming e.g., a zero-order hold, is simply
where the constants a j and a are defined as
2
J

Available Methods of Nonlinear Control Design 203
a = e~aT a = \ - a
x 2 x
and T is the sampling period. Note that this approximate procedure can actually be
interpreted as building a reduced-order observer for the system. However, it does not
use an explicit model, so that the system can be nonlinear and its parameters unknown.
An alternative choice of filter structure is studied in Exercise II.6.
Numerical integration actually consists in simulating in real-time some
(generally nonlinear) dynamic subcomponent required by the controller. Many
methods can again be used. The simplest, which can work well at high sampling rates
or for low-dimensional systems, is the so-called Euler integration
xT
where T is the sampling period. A more sophisticated approach, which is very
effective in most cases but is more computationally involved than mere Euler
integration, is two-step Adams-Bashforth integration
x(t) - x(t-T) + (-x(t-T)--x(t-2T))T
More complex techniques may also be used, depending on the desired trade-off
between accuracy and on-line computational efficiency.
II.4 Available Methods of Nonlinear Control Design
As in the analysis of nonlinear control systems, there is no general method for
designing nonlinear controllers. What we have is a rich collection of alternative and
complementary techniques, each best applicable to particular classes of nonlinear
control problems.
Trial-and-error
Based on the analysis methods provided in Part I, one can use trial-and-error to
synthesize controllers, similarly to, e.g., linear lead-lag controller design based on
Bode plots. The idea is to use the analysis tools to guide the search for a controller
which can then be justified by analysis and simulations. The phase plane method, the
describing function method, and Lyapunov analysis can all be used for this purpose.
Experience and intuition are critical in this process. However, for complex systems
trial-and-error often fails.

204 Nonlinear Control Systems Design Part II
Feedback linearization
As discussed earlier, the first step in designing a control system for a given physical
plant is to derive a meaningful model of the plant, i.e., a model that captures the key
dynamics of the plant in the operational range of interest. Models of physical systems
come in various forms, depending on the modeling approach and assumptions. Some
forms, however, lend themselves more easily to controller design. Feedback
linearization deals with techniques for transforming original system models into
equivalent models of a simpler form.
Feedback linearization can be used as a nonlinear design methodology. The
basic idea is to first transform a nonlinear system into a (fully or partially) linear
system, and then use the well-known and powerful linear design techniques to
complete the control design. The approach has been used to solve a number of
practical nonlinear control problems. It applies to important classes of nonlinear
systems (so-called input-state linearizable or minimum-phase systems), and typically
requires full state measurement. However, it does not guarantee robustness in the face
of parameter uncertainty or disturbances.
Feedback linearization techniques can also be used as model-simplifying
devices for robust or adaptive controllers, to be discussed next.
Robust control
In pure model-based nonlinear control (such as the basic feedback linearization
control approach), the control law is designed based on a nominal model of the
physical system. How the control system will behave in the presence of model
uncertainties is not clear at the design stage. In robust nonlinear control (such as, e.g.,
sliding control), on the other hand, the controller is designed based on the
consideration of both the the nominal model and some characterization of the model
uncertainties (such as the knowledge that the load to be picked up and carried by a
robot is between 2 kg and 10 kg). Robust nonlinear control techniques have proven
very effective in a variety of practical control problems. They apply best to specific
classes of nonlinear systems, and generally require state measurements.
Adaptive control
Adaptive control is an approach to dealing with uncertain systems or time-varying
systems. Although the term "adaptive" can have broad meanings, current adaptive
control designs apply mainly to systems with known dynamic structure, but unknown
constant or slowly-varying parameters. Adaptive controllers, whether developed for
linear systems or for nonlinear systems, are inherently nonlinear.
A

Exercises 205
Systematic theories exist for the adaptive control of linear systems. Existing
adaptive control techniques can also treat important classes of nonlinear systems, with
measurable states and linearly parametrizable dynamics. For these nonlinear systems,
adaptive control can be viewed as an alternative and complementary approach to
robust nonlinear control techniques, with which it can be combined effectively.
Although most adaptive control results are for single-input single-output systems,
some important nonlinear physical systems with multiple-inputs have also been
studied successfully.
Gain-scheduling
Gain scheduling (see [Rugh, 1991] for a recent discussion, and references therein) is
an attempt to apply the well developed linear control methodology to the control of
nonlinear systems. It was originally developed for the trajectory control of aircraft.
The idea of gain-scheduling is to select a number of operating points which cover the
range of the system operation. Then, at each of these points, the designer makes a
linear time-invariant approximation to the plant dynamics and designs a linear
controller for each linearized plant. Between operating points, the parameters of the
compensators are then interpolated, or scheduled, thus resulting in a global
compensator. Gain scheduling is conceptually simple, and, indeed, practically
successful for a number of applications. The main problem with gain scheduling is
that has only limited theoretical guarantees of stability in nonlinear operation, but uses
some loose practical guidelines such as "the scheduling variables should change
slowly" and "the scheduling variables should capture the plant's nonlinearities".
Another problem is the computational burden involved in a gain-scheduling design,
due to the necessity of computing many linear controllers.
II.5 Exercises
II. 1 Why do linear systems with a right half-plane zero exhibit the so-called "undershooting"
phenomenon (the step response initially goes downward)? Is the inability of perfect tracking for non-
minimum phase systems related to the undershooting phenomenon?
Consider for instance the system
Sketch its step response and compare it with that of the system
p1 + 2p+2

206 Nonlinear Control Systems Design Part II
What are the differences in frequency responses?
What does the step response of a non-minimum phase linear system look like if it has two
right half-plane zeros? Interpret and comment.
11.2 Assume that you are given a pendulum and the task of designing a control system to track the
desired trajectory
6(/) = /4sinco» 0<A<9Q" 0<cc<10tfz
d
What hardware components do you need to implement the control system? What requirements does
the task impose on the the specifications of the components? Provide a detailed outline of your
control system design.
11.3 List the model uncertainties associated with the pendulum model (II. 1). Discuss how to
characterize them.
11.4 Carry out the tracking design for the linear plants
Simulate their responses to the desired trajectories
with (O being 0.5, 1.5, and 4. rad/sec.
11.5 Figure out an energy-based strategy to bring the inverted pendulum in Figure Il.l.b from the
vertical-down position to the vertical-up position. (Hint: You may want first to express the system's
kinetic energy in a modified coordinate system chosen such that rotation and translation are
uncoupled.)
What does your controller guarantee along the x direction? Does it reduce to the usual linear
inverted pendulum controller when linearized?
11.6 An alternative to the filtered differentiation (11.12) consists in simply passing an approximate
derivative through a zero-order hold discrete filter, e.g.,
c\xold
where c, = e~aT . Discuss the relative merits of the two approaches.
J

Chapter 6
Feedback Linearization
Feedback linearization is an approach to nonlinear control design which has attracted a
great deal of research interest in recent years. The central idea of the approach is to
algebraically transform a nonlinear system dynamics into a (fully or partly) linear one,
so that linear control techniques can be applied. This differs entirely from
conventional linearization (i.e., Jacobian linearization, as in section 3.3) in that
feedback linearization is achieved by exact state transformations and feedback, rather
than by linear approximations of the dynamics.
The idea of simplifying the form of a system's dynamics by choosing a different
state representation is not entirely unfamiliar. In mechanics, for instance, it is well
known that the form and complexity of a system model depend considerably on the
choice of reference frames or coordinate systems. Feedback linearization techniques
can be viewed as ways of transforming original system models into equivalent models
of a simpler form. Thus, they can also be used in the development of robust or
adaptive nonlinear controllers, as discussed in chapters 7 and 8.
Feedback linearization has been used successfully to address some practical
control problems. These include the control of helicopters, high performance aircraft,
industrial robots, and biomedical devices. More applications of the methodology are
being developed in industry. However, there are also a number of important
shortcomings and limitations associated with the feedback linearization approach.
Such problems are still very much topics of current research.
207

208 Feedback Linearization Chap. 6
This chapter provides a description of feedback linearization, including what it
is, how to use it for control design and what its limitations are. In section 6.1, the
basic concepts of feedback linearization are described intuitively and illustrated with
simple examples. Section 6.2 introduces mathematical tools from differential
geometry which are useful to generalize these concepts to a broad class of nonlinear
systems. Sections 6.3 and 6.4 describe feedback linearization theory for SISO systems,
and section 6.5 extends the methodology to MIMO systems.
6.1 Intuitive Concepts
This section describes the basic concepts of feedback linearization intuitively, using
simple examples. The following sections will formalize these concepts for more
general nonlinear systems.
6.1.1 Feedback Linearization And The Canonical Form
In its simplest form, feedback linearization amounts to canceling the nonlinearities in
a nonlinear system so that the closed-loop dynamics is in a linear form. This very
simple idea is demonstrated in the following example.
Example 6.1: Controlling the fluid level in a tank
Consider the control of the level h of fluid in a tank (Figure 6.1) to a specified level h. The
d
control input is the flow u into the tank, and the initial level is h.
o
output
flow
Figure 6.1 : Fluid level control in a tank
The dynamic model of the tank is
(6.1)

Sect. 6.1 Intuitive Concepts 209
where A(h) is the cross section of the tank and a is the cross section of the outlet pipe. If the
initial level h is quite different from the desired level h, the control of h involves a nonlinear
a d
regulation problem.
The dynamics (6.1) can be rewritten as
A(h)'h = u-a-\lgh
If «(/) is chosen as
u(t) = a^2gh +A(h)v (6.2)
with v being an "equivalent input" to be specified, the resulting dynamics is linear
A = v
Choosing v as
v = -ah (6.3)
with h = h(t) - h being the level error, and a being a strictly positive constant, the resulting
d
closed loop dynamics is
h + ah = 0 (6.4)
This implies that h(t) —> 0 as t —* °°. Based on (6.2) and (6.3), the actual input flow is
determined by the nonlinear control law
u(t) = a^2gh -A(h)ah (6.5)
Note that, in the control law (6.5), the first part on the right-hand side is used to provide the
output flow a~^2gh , while the second part is used to raise the fluid level according to the the
desired linear dynamics (6.4).
Similarly, if the desired level is a known time-varying function h(t), the equivalent input v
d
can be chosen as
v = h (t)-ah
d
so as to still yield H(t) -> 0 as / -» °° . •
The idea of feedback linearization, i.e., of canceling the nonlinearities and
imposing a desired linear dynamics, can be simply applied to a class of nonlinear
systems described by the so-called companion form, or controllability canonical form.
A system is said to be in companion form if its dynamics is represented by
xW =/(x) + b(x) u (6.6)

210 Feedback Linearization Chap. 6
where u is the scalar control input, x is the scalar output of interest,
x = [x,x, ... ,x(n~l}]T is the state vector, and /(x) and b(x) are nonlinear
functions of the states. This form is unique in the fact that, although derivatives of x
appear in this equation, no derivative of the input u is present. Note that, in state-space
representation, (6.6) can be written
x\ X2
d
df xn-\
f(x) + b(x)u
For systems which can be expressed in the controllability canonical form, using
the control input (assuming b to be non-zero)
u [v f]
=l -
(6.7)
we can cancel the nonlinearities and obtain the simple input-output relation (multiple-
integrator form)
(n) =
x v
Thus, the control law
with the k chosen so that the polynomial pn + k _\p"~l + .... + k has all its roots
i n 0
strictly in the left-half complex plane, leads to the exponentially stable dynamics
which implies that x(t) —> 0. For tasks involving the tracking of a desired output Xj(t),
the control law
v = x W - k e - k e - .... - k _ e^-V (6.8)
d o 2 n {
(where e{t) = x(t) - x {t) is the tracking error) leads to exponentially convergent
d
tracking. Note that similar results would be obtained if the scalar x was replaced by a
vector and the scalar b by an invertible square matrix.
One interesting application of the above control design idea is in robotics. The
following example studies control design for a two-link robot. Design for more
general robots is similar and will be discussed in chapter 9.

| Sect. 6.1 |     |     |     |     | Intuitive Concepts  | 211 |
| --------- | --- | --- | --- | --- | ------------------- | --- |
Example 6.2: Feedback linearization of a two-link robot
Figure 6.2 provides the physical model of a two-link robot, with each joint equipped with a motor
for  providing  input  torque, an encoder  for  measuring joint  position,  and  a tachometer  for
measuring joint velocity. The objective of the control design is to make the joint positions q and
 s
q follow desired position histories q^(t)  and q^t)  , which are specified by the motion planning
2
system of the robot.  Such tracking control problems arise when a robot hand is required to move
along a specified path, e.g., to draw circles.
Figure 6.2 : A two-link robot
Using the well-known Lagrangian equations in classical dynamics, one can easily show that
the dynamic equations of the robot is
|     |            |     | ~hq 2 -hq-hq | x 2 | S\  |       |
| --- | ---------- | --- | ------------ | --- | --- | ----- |
|     |            | 1   | _J_          | L   |     | (6.9) |
|     | "21 "22|52 |     | hq x         |     | 82  |       |
= [<7j q]T being the two joint angles, T = [lj  X]r being the joint inputs, and
|     | 2        |         |                  |                      | 2   |     |
| --- | -------- | ------- | ---------------- | -------------------- | --- | --- |
|     | H u =m   | x l  ,  | 2 + /            | 2 + 2/,/  coS<?2]+/2 |     |     |
|     | I = H2\  | = m2l\  | ' c ^^  + m2lc2  | + !2                 |     |     |
2

212 Feedback Linearization Chap. 6
Equation (6.9) can be compactly expressed as
H(q)q + C(q, q)q + g(q) = x
with H, C and g defined obviously. Thus, by multiplying both sides by H~' (the invertibility of
H is a physical property of the system, as discussed in Chapter 9), the above vector equation can
be put easily in the form of (6.6), with n = 2, although this dynamics now involves multiple inputs
and multiple outputs.
To achieve tracking control tasks, one can use the following control law
-hq -h
2
(6.10)
»2I»22»2
where
with v = [ v | i>2 ]r being the equivalent input, q = q — q ^ being the position tracking error and X
a positive number. The tracking error q then satisfies the equation
and therefore converges to zero exponentially. The control law (6.10) is commonly referred to as
"computed torque" control in robotics. It can be applied to robots with arbitrary numbers of joints,
as discussed in chapter 9. D
Note that in (6.6) we have assumed that the dynamics is linear in terms of the
control input u (although nonlinear in the states). However, the approach can be easily
extended to the case when u is replaced by an invertible function g(u). For example, in
systems involving flow control by a valve, the dynamics may be dependent on M4
rather than directly on u, with u being the valve opening diameter. Then, by defining
w = M4 , one can first design w similarly to the previous procedure and then compute
the input « by u = w1^4 . This means that the nonlinearity is simply undone in the
control computation.
When the nonlinear dynamics is not in a controllability canonical form, one
may have to use algebraic transformations to first put the dynamics into the
controllability form before using the above feedback linearization design, or to rely on
partial linearization of the original dynamics, instead of full linearization. These are

Sect. 6.1 Intuitive Concepts 213
the topics of the next subsections. Conceptually, such transformations are not totally
unfamiliar: even in the case of linear systems, pole placement is often most easily
achieved by first putting the system in the controllability canonical form.
6.1.2 Input-State Linearization
Consider the problem of designing the control input u for a single-input nonlinear
system of the form
x = f (x, u)
The technique of input-state linearization solves this problem in two steps. First, one
finds a state transformation z = z(x) and an input transformation u = u(x, v) so that
the nonlinear system dynamics is transformed into an equivalent linear time-invariant
dynamics, in the familiar form z = Az + bv. Second, one uses standard linear
techniques (such as pole placement) to design v.
Let us illustrate the approach on a simple second-order example. Consider the
system
i| = - 2x\ + <xx + sin x (6.11a)
2 x
x = -x cosx[ + M cos(2x() (6.11b)
2 2
Even though linear control design can stabilize the system in a small region around the
equilibrium point (0, 0), it is not obvious at all what controller can stabilize it in a
larger region. A specific difficulty is the nonlinearity in the first equation, which
cannot be directly canceled by the control input u.
However, if we consider the new set of state variables
z=x (6.12a)
x x
Z2 = ax2+ sinxj (6.12b)
then, the new state equations are
z =-2z +z (6.13a)
1 1 2
z = - 2zj cos Zj + coszj sinzj + au cos(2z[) (6.13b)
2
Note that the new state equations also have an equilibrium point at (0, 0). Now we see
that the nonlinearities can be canceled by the control law of the form

| 214  Feedback Linearization  |                                | Chap. 6 |
| ---------------------------- | ------------------------------ | ------- |
| u =                          | (v-coszj sin Zj + 2zj cos Zj)  | (6.14)  |
where v is an equivalent input to be designed (equivalent in the sense that determining
v amounts to determining «, and vice versa), leading to a linear input-state relation
| z=-2z l 1 +z | 2   | (6.15a) |
| ------------ | --- | ------- |
| z 2 =  v     |     | (6.15b) |
Thus, through the state transformation  (6.12) and input transformation  (6.14), the
problem of stabilizing the original nonlinear dynamics (6.11) using the original control
input u has been transformed into the problem of stabilizing the new dynamics (6.15)
using the new input v.
Since the new dynamics is linear and controllable, it is well known that the
linear state feedback control law
| v = -*jz,-fc | z   |     |
| ------------ | --- | --- |
2 2
can place the poles anywhere with proper choices of feedback gains. For example, we
may choose
| v = -2z   |     | (6.16) |
| --------- | --- | ------ |
2
resulting in the stable closed-loop dynamics
| z,=-2z | z   |     |
| ------ | --- | --- |
| 1+     | 2   |     |
and x > triis
whose poles are both placed at - 2. In terms of the original state x  l 2
control law corresponds to the original input
|          | ( - 2a.x - 2 sinxj - COSJCJ sinjtj + 2xj cos Xj )  | (6.17) |
| -------- | -------------------------------------------------- | ------ |
| cos {2x) | 2                                                  |        |
x
The original state x is given from z by
| x=z  |     | (6.18a) |
| ---- | --- | ------- |
l l
| jf  = (z -sinz | )/a  | (6.18b) |
| -------------- | ---- | ------- |
| 2 2            | 1    |         |
Since both zj and z  converge to zero, the original state x converges to zero.
2
The closed-loop system under the above control law is represented in the block
diagram in Figure 6.3. We can detect two loops in this control system, with the inner
J

Sect. 6.1 Intuitive Concepts 215
loop achieving the linearization of the input-state relation, and the outer loop
achieving the stabilization of the closed-loop dynamics. This is consistent with (6.14),
where the control input u is seen to be composed of a nonlinearity cancellation part
and a linear compensation part.
v = - k z u = u(\ , x = f(x, u)
linearization loop
pole-placement loop
z = z(x)
Figure 6.3 : Input-State Linearization
A number of remarks can be made about the above control law:
• The result, though valid in a large region of the state space, is not global.
The control law is not well defined when ;t[ = (JT/4 ± kn/2), k= 1,2,...
Obviously, when the initial state is at such singularity points, the controller
cannot bring the system to the equilibrium point.
• The input-state linearization is achieved by a combination of a state
transformation and an input transformation, with state feedback used in both.
Thus, it is a linearization by feedback, or feedback linearization. This is
fundamentally different from a Jacobian linearization for small range
operation, on which linear control is based.
• In order to implement the control law, the new state components (z, z )
( 2
must be available. If they are not physically meaningful or cannot be
measured directly, the original state x must be measured and used to compute
them from (6.12).
• Thus, in general, we rely on the system model both for the controller
design and for the computation of z. If there is uncertainty in the model, e.g.,
uncertainty on the parameter a, this uncertainty will cause error in the
computation of both the new state z and of the control input u, as seen in
(6.12) and (6.14).
• Tracking control can also be considered. However, the desired motion then
needs to be expressed in terms of the full new state vector. Complex

| 216  Feedback Linearization  |     | Chap. 6 |
| ---------------------------- | --- | ------- |
computations may be needed to translate the desired motion specification (in
terms of physical output variables) into specifications in terms of the new
states.
With the above successful design in mind, it is interesting to extend the input-
state linearization idea to general nonlinear systems. Two questions arise when one
speculates such generalizations:
• What classes of nonlinear systems can be transformed into linear systems?
• How to find the proper transformations for those which can?
These questions are systematically addressed in section 6.3.
6.1.3 Input-Output Linearization
Let us now consider a tracking control problem. Consider the system
| i = f(x,K)  |     | (6.19a) |
| ----------- | --- | ------- |
| y = h(x)    |     | (6.19b) |
and assume that our objective is to make the output y(t) track a desired trajectory y(i)
d   f
while keeping the whole state bounded, where yj{t)  and its time derivatives up to a  j
sufficiently high order are assumed to be known and bounded. An apparent difficulty  '
with this model is that the output y is only indirectly related to the input u, through the  ,
state variable x and the nonlinear state equations (6.19).  Therefore, it is not easy to  I
see how the input u can be designed to control the tracking behavior of the output y.
However, inspired by the results of section 6.1.1, one might guess that the difficulty of
the tracking control design can be reduced if we can find a direct and simple relation
between the system output y and the control input u.  Indeed, this idea constitutes the
intuitive  basis  for  the  so-called  input-output  linearization  approach  to  nonlinear
control design. Let us again use an example to demonstrate this approach.
| Consider the third-order system  |                       | J          |
| -------------------------------- | --------------------- | ---------- |
| i[ = sinjc                       | 2 +  (JC + 1) x 2 3   | (6.20a)  * |
| x = X[5 + x                      |                       | (6.20b)  • |
| 2                                | 3                     |            |
| i  = x2                          | + u                   | (6.20c)    |
3 x
| y = x  { |     | (6.20d) |
| -------- | --- | ------- |

| Sect. 6.1  |     |     |     | Intuitive Concepts  | 217 |
| ---------- | --- | --- | --- | ------------------- | --- |
To  generate a direct  relationship  between  the output y and the input u, let us
differentiate the output y
y = x = sin x + (x + 1) x
|     | x   | 2 2 | 3   |     |     |
| --- | --- | --- | --- | --- | --- |
Since y is still not directly related to the input u, let us differentiate  again. We now
obtain
|     | y = (x +l)  | u +/j(x)  |     |     | (6.21) |
| --- | ----------- | --------- | --- | --- | ------ |
2
| where f(x)  | is a function of the state defined by |     |     |     |     |
| ----------- | ------------------------------------- | --- | --- | --- | --- |
x
|     | f(x)  = (x5 + x) (x |  + cosx | ) + (x +l  | )x 2  | (6.22) |
| --- | ------------------- | ------- | ---------- | ----- | ------ |
|     | x                   | x 3 3   | 2 2        | x     |        |
Clearly, (6.21) represents an explicit relationship between y and u. If we choose the
control input to be in the form
1
|     |     | (v-/i)  |     |     | (6.23) |
| --- | --- | ------- | --- | --- | ------ |
x +
2
where v is a new input to be determined, the nonlinearity in (6.21) is canceled, and we
obtain a simple linear double-integrator relationship between the output and the new
input v,
The  design of a tracking  controller for this  double-integrator  relation  is simple,
because  of the availability  of linear  control  techniques.  For instance,  letting
e = y(t) ~ >^(0 be the tracking error, and choosing the new input v as
|     | v=y -k | e-k 'e  |     |     | (6.24) |
| --- | ------ | ------- | --- | --- | ------ |
|     | d      | x 2     |     |     |        |
with £j and k  being positive constants, the tracking error of the closed loop system is
2
given by
|     | e + ke  + ke  | = O  |     |     | (6.25) |
| --- | ------------- | ---- | --- | --- | ------ |
|     | 2             | l    |     |     |        |
which  represents an exponentially  stable  error  dynamics.  Therefore,  if initially
e(0) = e(0) = 0, then e{t) = 0,V t > 0 , i.e., prefect tracking is achieved; otherwise, e(t)
converges to zero exponentially.
Note that
• The control law is defined everywhere, except at the singularity points such
that x = - 1 .
2

218 Feedback Linearization Chap. 6
• Full state measurement is necessary in implementing the control law,
because the computations of both the derivative y and the input
transformation (6.23) require the value of x.
The above control design strategy of first generating a linear input-output
relation and then formulating a controller based on linear control is referred to as the
input-output linearization approach, and it can be applied to many systems, as will be
seen in section 6.4 for SISO systems and in section 6.5 for MIMO systems. If we
need to differentiate the output of a system r times to generate an explicit relationship
between the output y and input u, the system is said to have relative degree r. Thus,
the system in the above example has relative degree 2. As will be shown soon, this
terminology is consistent with the notion of relative degree in linear systems (excess
of poles over zeros). As we shall see later, it can also be shown formally that for any
controllable system of order n, it will take at most n differentiations of any output for
the control input to appear, i.e., r<n. This can be understood intuitively: if it took
more than n differentiations, the system would be of order higher than n; if the control
input never appeared, the system would not be controllable.
At this point, one might feel that the tracking control design problem posed at
the beginning has been elegantly solved with the control law (6.23) and (6.24).
However, one must remember that (6.25) only accounts for part of the closed-loop
dynamics, because it has only order 2, while the whole dynamics has order 3 (the
same as that of the plant, because the controller (6.23) introduces no extra dynamics).
Therefore, a part of the system dynamics (described by one state component) has been
rendered "unobservable" in the input-output linearization. This part of the dynamics
will be called the internal dynamics, because it cannot be seen from the external input-
output relationship (6.21). For the above example, the internal state can be chosen to
be x (because x , y , and y constitute a new set of states), and the internal dynamics is
3 3
represented by the equation
h = x\2 + ~l—r (Sd(O - k\e ~ k-ie +/i) (6-26)
X *
If this internal dynamics is stable (by which we actually mean that the states remain
bounded during tracking, i.e., stability in the BIBO sense), our tracking control design
problem has indeed been solved. Otherwise, the above tracking controller is
practically meaningless, because the instability of the internal dynamics would imply
undesirable phenomena such as the burning-up of fuses or the violent vibration of
mechanical members. Therefore, the effectiveness of the above control design, based
on the reduced-order model (6.21), hinges upon the stability of the internal dynamics.
Let us now use some simpler examples to show that internal dynamics are

Sect. 6.1 Intuitive Concepts 219
stable for some systems (implying that the previous design approach is applicable),
and unstable for others (implying the need for a different control design).
Example 6.3: Internal dynamics
Consider the nonlinear system
+ u
(6.27a)
u
y = x (6.27b)
x
Assume that the control objective is to make y track y{t). Differentiation of y simply leads to the
d
first state equation. Thus, choosing the control law
» = - *2 ~ e(t) + y(t) (6.28)
d
yields exponential convergence of e to zero
k + e = 0 (6.29)
The same control input is also applied to the second dynamic equation, leading to the internal
dynamics
x + x i=y -e (6.30)
2 2 d
which is, characteristically, non-autonomous and nonlinear. However, in view of the facts that e
is guaranteed to be bounded by (6.29) and y is assumed to be bounded, we have
d
\y (t)-e\ < D
d
where D is a positive constant. Thus, we can conclude from (6.30) that \x I <D1/3 (perhaps
2
after a transient), since x < 0 when x > D1'3 , and x > 0 when x < — D1'3 .
2 2 2 2
Therefore, (6.28) does represent a satisfactory tracking control law for the system (6.27),
given any trajectory y(t) whose derivative y(t) is bounded. D
d d
Conversely, one can easily show (Exercise 6.2) that if the second state equation
in (6.27) is replaced by Xj = — u, then the resulting internal dynamics is unstable.
Finally, let us remark that, although the input-output linearization is motivated
in the context of output tracking, it can also be applied to stabilization problems. For
example, if y^(t) = 0 is the desired trajectory for the above system, the two states y and
y of the closed-loop system will be driven to zero by the control law (6.28), implying
the stabilization of the whole system provided that the internal dynamics is stable. In

220 Feedback Linearization Chap. 6
addition, two useful remarks can be made about using input-output linearization for
stabilization design. First, in stabilization problems, there is no reason to restrict the
choice of output v = h{x) to be a physically meaningful quantity (while in tracking
problems the choice of output is determined by the physical task). Any function of x
may be used to serve as an artificial output (a designer output) to generate a linear
input-output relation for the purpose of stabilization design. Second, different choices
of output function leads to different internal dynamics. It is possible for one choice of
output to yield a stable internal dynamics (or no internal dynamics) while another
choice of output would lead to a unstable one. Therefore, one should choose, if
possible, the output function to be such that the associated internal dynamics is stable.
A special case occurs when the relative degree of a system is the same as its
order, i.e., when the output y has to be differentiated n times (with n being the system
order) to obtain a linear input-output relation. In this case, the variables y, y,...,
y(n-\) y b j f j variables for the system, and there is no
ma e usec as a new set o stae
internal dynamics associated with this input-output linearization. Thus, in this case,
input-output linearization leads to input-state linearization, and both state regulation
and output tracking (for the particular output) can be achieved easily.
THE INTERNAL DYNAMICS OF LINEAR SYSTEMS
We must admit that it is only due to the simplicity of the system that the internal
dynamics in Example 6.3 has been shown to be stable. In general, it is very difficult to
directly determine the stability of the internal dynamics because it is nonlinear, non-
autonomous, and coupled to the "external" closed-loop dynamics, as seen in (6.26).
Although a Lyapunov or Lyapunov-like analysis may be useful for some systems, its
general applicability is limited by the difficulty of finding a Lyapunov function, as
discussed in chapters 3 and 4. Therefore, we naturally want to seek simpler ways of
determining the stability of the internal dynamics. An examination of how the concept
of internal dynamics translates in the more familiar context of linear systems proves
helpful to this purpose.
Let us start by considering the internal dynamics of some simple linear systems.
Example 6.4: Internal dynamics in two linear systems
Consider the simple controllable and observable linear system
u
(6.31a)
X2 u
(6.31b)

Sect. 6.1 Intuitive Concepts 221
where y(t) is required to track a desired output y(t). With one differentiation of the output, we
d
simply obtain the first state equation
y = x + u
2
which explicitly contains «. Thus, the control law
u = -x + y -(y-y ) (6.32)
2 d d
yields the tracking error equation
(where e = y - y) and the internal dynamics
d
We see from these equations that while y(t) tends to y(t) (and y(i) tends to y(t)) , x remains
d d 2
bounded, and so does u. Therefore, (6.32) is a satisfactory tracking controller for system (6.31).
Let us now consider a slightly different system:
(6.33a)
X2
(6.33b)
The same control law as above yields the same tracking error dynamics, but now leads to the
internal dynamics
This implies that x , and accordingly u, both go to infinity as t —> °° . Therefore, (6.32) is not a
2
suitable tracking controller for system (6.33). CD
We are thus left wondering why the same tracking design method is applicable
to for system (6.31) but not to system (6.33). To understand this fundamental
difference between the two systems, let us consider their transfer functions, namely,
for system (6.31),
Wyip) = £±±-
P
and for system (6.33),

222 Feedback Linearization Chap. 6
We see that the two systems have the same poles but different zeros. Specifically,
system (6.31), for which the design has succeeded, has a left half-plane zero at - 1,
while system (6.33), for which the design has failed, has an right half-plane zero at 1.
The above observation (the internal dynamics is stable if the plant zeros are in
the left-half plane, i.e., if the plant is "minimum-phase") can actually be shown to be
true for all linear systems, as we do now. This is not surprising because, for non-
minimum phase systems, perfect tracking of arbitrary trajectories requires infinite
control effort, as seen in Example II.2.
To keep notations simple, let us consider a third-order linear system in state-
space form
z = Az+ b« (6.34)
and having one zero (and hence two more poles than zeros), although the procedure
can be straightforwardly extended to systems with arbitrary numbers of poles and
zeros. The system's input-output linearization can be facilitated if we first transform it
into the so-called companion form. To do this, we note from linear control that the
input/output behavior of this system can be expressed in the form *
b +b p
y = cT{pl-A)~xbu = - o x (6.35)
c
(where p is the Laplace variable). Thus, if we define
xi = o—r "
x = x
2 x
x = i
3 2
the system can be equivalently represented in the companion form
0 l (T x\
0 0 1 X2 + 0 (6.36a)
1
i

Sect. 6.1 Intuitive Concepts 223
y = lb o] (6.36b)
o
Let us now perform input-output linearization based on this form. The first
differentiation of the output leads to
and the second differentiation leads to
y = bo'x2 + b\h ~ V*3H a\x2 - a2xi (6.37)
It is seen that the input u appears in the second differentiation, which means that the
required number of differentiations (the relative degree) is indeed the same as the
excess of poles over zeros (of course, since the input-output relation of y to u is
independent of the choice of state variables, it would also take two differentiations for
u to appear if we used the original state-space equations (6.34)).
Thus, the control law
1
u = (a x —(-ke-ke + y ) (6.38)
o x l z d
where e = y - y^ , yields an exponentially stable tracking error
Since this is a second-order dynamics, the internal dynamics of our third-order system
can be described by only one state equation. Specifically, we can use JCJ to complete
the state vector, since one can easily show X|, y, and y are related to x, x , and x^
x 2
through a one-to-one transformation (and thus can serve as states for the system). We
then easily find from (6.36a) and (6.36b) that the internal dynamics is
xl = X2 = '~hox0
that is,
(6.39)
Since y is bounded (y = e + y), we see that the stability of the internal dynamics
d
depends on the location of the zero -b /bi of the transfer function in (6.35). If the
o

224 Feedback Linearization Chap. 6
system is minimum phase, then the zero is in the left-half plane, which implies that the
internal dynamics (6.39) is stable, independently of the initial conditions and of the
magnitudes of the desired y,..., yj^ (where r is the relative degree).
d
A classical example of the effect of a right half-plane zero is the problem of
controlling the altitude of an aircraft using an elevator.
Example 6.5: Aircraft altitude dynamics
horizontal
Figure 6.4 : Dynamic characteristics of an aircraft
A schematic diagram of the dynamics of an aircraft (in the longitudinal plane) is shown in Figure
6.4. The sum of the lift forces applied to the aircraft wings and body is equivalent to a single lift
force L , applied at the "center of lift" C . The center of lift does not necessarily coincide with
w E
the center of mass CQ (with a positive d meaning that the center of mass is ahead of the center of
lift). The mass of the aircraft is denoted by m and its moment of inertia about C is denoted by
G
/. We assume that all angles are small enough to justify linear approximations, and that the
forward velocity of the aircraft remains essentially constant.
The aircraft is initially cruising at a constant altitude h = h. To affect its vertical motion, the
o
elevator (a small surface located at the aircraft tail) is rotated by an angle E. This generates a
small aerodynamic force L on the elevator, and thus a torque about CQ . This torque creates a
E
rotation of the aircraft about CQ, measured by an angle a. The lift force L applied to the wings
w
is proportional to a , i.e., L = C o.. Similarly, L is proportional to the angle between the
w zw E
horizontal and the elevator, i.e., L = C (E-a) . Furthermore, various aerodynamic forces
E ZE
create friction torques proportional to d, of the form ba. In summary, a simplified model of the
aircraft vertical motion can be written
(C l+C d)a = C l E (6.40a)
ZE zw ZE
m'h = {C ^C )a-C E (6.40b)1
ZE m ZE
where the first equation represents the balance of moments and the second the balance of forces.

| Sect. 6.1  |     |     |     | Intuitive Concepts  | 225 |
| ---------- | --- | --- | --- | ------------------- | --- |
Remark that the open-loop stability of the first equation, which defines the dynamics of the
angle a, depends on the sign of the coefficient  (Cgl + C^d).  In particular, the equation is
Z
open-loop stable if d > 0 , i.e., if the center of mass is ahead of the center Of lift (this allows us to
understand the shape of a jumbo jet, or the fact that on small aircraft passengers are first seated on
the front rows).
To simplify notations, let now
|     | y = 1 =l  | b = 4  C =l  | C   = 5  1 = 3  | d = 0.2. |     |
| --- | --------- | ------------ | --------------- | -------- | --- |
|     |   m       | ZE           | m               |          |     |
The transfer functions describing the system can then be written
§4  T
|     | E(p) 2  |   (p + 2)    |                   |     |         |
| --- | ------- | ------------ | ----------------- | --- | ------- |
|     |   p     |  + 4p  + 4   |                   |     |         |
|     | h(p) _  | \4-4p-p2  _  | (6.24+/>)(2.24-p) |     |         |
|     | EYTA    | TT^y—~,  77  | T~,  XTo          |     | vo.tio; |
where p is the Laplace variable.
At time t = 0, a unit step input in elevator angle E is applied. From the initial and final value
theorems of linear control (or directly from the equations of motion), one can easily show that the
corresponding initial and final vertical accelerations are
|     | M7=0+) = - 1 < 0  |     | h(t= + °°)  = 3.5 > 0 |     |     |
| --- | ----------------- | --- | --------------------- | --- | --- |
The complete time responses in h and h are sketched in Figure 6.5. We see that the aircraft starts
in the wrong direction, then recovers. Such behavior is typical of systems with a right half-plane
zero. It can be easily understood physically, and is a direct reflection of the aircraft design itself.
The initial effect of the unit step in E is to create an instantaneous downward force  on the
elevator, thus creating an initial downward acceleration of the aircraft's center of mass. The unit
step in elevator angle also creates a torque about CQ , which builds up the angle a and thus
creates an increasing upward lift force on the wing and body. This lift force eventually takes over
the downward force on the elevator.  Of course, such non-minimum phase behavior is important
for the pilot to know, especially when flying at low altitudes.
Let us determine the associated internal dynamics. Defining the state as x = [ a  a  h  h]T,
the equations of motion can be written
|     | x,  = x  2           |     |     |     | (6.42a) |
| --- | -------------------- | --- | --- | --- | ------- |
|     | x  = — 4^2 — 4xj+3£  |     |     |     | (6.42b) |
2
|     | x = x  |     |     |     | (6.42c) |
| --- | ------ | --- | --- | --- | ------- |
3 4
|     | k  = 6x, - E  |     |     |     | (6.42d) |
| --- | ------------- | --- | --- | --- | ------- |
A

| 226  Feedback Linearization |     |     |     | Chap. 6 |
| --------------------------- | --- | --- | --- | ------- |
| Im                          | h   |     |     |         |
3.5
|     | Re  | time |     | time |
| --- | --- | ---- | --- | ---- |
-1
| (a)                                                      |     | (b)  | (c) |     |
| -------------------------------------------------------- | --- | ---- | --- | --- |
| Figure 6.5 : Pole-zero plot and step responses in h and  |     |      | h   |     |
The output of interest is the aircraft's altitude
y=xi
Differentiating y until the input E appears yields
y = * = x = 6x - E
| 3   | A l |     |     |     |
| --- | --- | --- | --- | --- |
consistent with the fact that the transfer function (6.41b) has relative degree 2.  Choose now a
pole-placement control law for E
where y = y - y . Then
d
| y + y + y = o |     |     |     | (6.43) |
| ------------- | --- | --- | --- | ------ |
The corresponding internal dynamics is
| x = -4JT-4-Kj + 3(6jf| |     | + y) |     |     |
| ---------------------- | --- | ---- | --- | --- |
2 2
that is
Jry + y)
| a + 4d- 14a  | = 'i{-y d |     |     | (6.44) |
| ------------ | --------- | --- | --- | ------ |
and therefore, is unstable. Specifically, the poles on the left-hand side of (6.44) are exactly the
| zeros of the transfer function (6.41b). |     |     |     | •   |
| --------------------------------------- | --- | --- | --- | --- |
THE ZERO-DYNAMICS
Since for linear systems the stability of the internal dynamics is simply determined by
the locations of the zeros, it is interesting to see whether this relation can be extended
to nonlinear systems. To do so requires first to extend the concept of zeros to
nonlinear systems, and then to determine the relation of the internal dynamics stability
J

Sect. 6.1 Intuitive Concepts 227
to this extended concept of zeros.
Extending the notion of zeros to nonlinear systems is not a trivial proposition.
Transfer functions, on which linear system zeros are based, cannot be defined for
nonlinear systems. Furthermore, zeros are intrinsic properties of a linear plant, while
for nonlinear systems the stability of the internal dynamics may depend on the specific
control input.
A way to approach these difficulties is to define a so-called zero-dynamics for a
nonlinear system. The zero-dynamics is defined to be the internal dynamics of the
system when the system output is kept at zero by the input. For instance, for the
system (6.27), the zero-dynamics is (from (6.30))
x +x 3 = 0 (6.45)
2 2
Noticing that the specification of maintaining the system output at zero uniquely
defines the required input (namely, here, u has to equal —x^ in order to keep Xj
always equal to zero), we see that the zero-dynamics is an intrinsic property of a
nonlinear system. The zero-dynamics (6.45) is easily seen to be asymptotically stable
(by using the Lyapunov function K = x 2).
2
Similarly, for the linear system (6.34), the zero-dynamics is (from (6.39))
xj +{b lb)x = 0
o x l
Thus, in this linear system, the poles of the zero-dynamics are exactly the zeros of the
system. This result is general for linear systems, and therefore, in linear systems,
having all zeros in the left-half complex plane guarantees the global asymptotic
stability of the zero-dynamics.
The reason for defining and studying the zero-dynamics is that we want to find
a simpler way of determining the stability of the internal dynamics. For linear
systems, the stability of the zero-dynamics implies the global stability of the internal
dynamics: the left-hand side of (6.39) completely determines its stability
characteristics, given that the right-hand side tends to zero or is bounded. In nonlinear
systems, however, the relation is not so clear. Section 6.4 investigates this question in
some detail. For stabilization problems, it can be shown that local asymptotic stability
of the zero-dynamics is enough to guarantee the local asymptotic stability of the
internal dynamics. Extensions can be drawn to the tracking problem. However, unlike
the linear case, no results on the global stability or even large range stability can be
drawn for internal dynamics of nonlinear systems, i.e., only local stability is
guaranteed for the internal dynamics even if the zero-dynamics is globally
exponentially stable.

228 Feedback Linearization Chap. 6
Similarly to the linear case, we will call a nonlinear system whose zero-
dynamics is asymptotically stable an asymptotically minimum phase system. The
concept of an exponentially minimum phase system can be defined in the same way.
Two useful remarks can be made about the zero-dynamics of nonlinear systems.
First, the zero-dynamics is an intrinsic feature of a nonlinear system, which does not
depend on the choice of control law or the desired trajectories. Second, examining the
stability of zero-dynamics is much easier than examining the stability of internal
dynamics, because the zero-dynamics only involves the internal states (while the
internal dynamics is coupled to the external dynamics and desired trajectories, as seen
in (6.26)).
Example 6.6: Aircraft zero-dynamics
Given (6.44), the zero-dynamics of the aircraft of Example 6.5 is
a + 4o- 14a = 0 (6.46)
This dynamics is unstable, confirming that the system is non-minimum phase. The poles of the
zero-dynamics are exactly the zeros of the transfer function (6.41 b).
Now model (6.40) is actually the linearization of a more general nonlinear model, applicable
at larger angles and angular rates. Since the zero-dynamics corresponding to the linearized model
simply is the linearization of the zero-dynamics corresponding to the nonlinear model, thus the
nonlinear system is also non-minimum phase, from Lyapunov's linearization method. D
To summarize, control design based on input-output linearization can be made
in three steps:
• differentiate the output y until the input u appears
• choose u to cancel the nonlinearities and guarantee tracking convergence
• study the stability of the internal dynamics
If the relative degree associated with the input-output linearization is the same as the
order of the system, the nonlinear system is fully linearized and this procedure indeed
leads to a satisfactory controller (assuming that the model is accurate). If the relative
degree is smaller than the system order, then the nonlinear system is only partly
linearized, and whether the controller can indeed be applied depends on the stability of
the internal dynamics. The study of the internal dynamics stability can be simplified
locally by studying that of the zero-dynamics instead. If the zero-dynamics is
unstable, different control strategies should be sought, only simplified by the fact that
the transformed dynamics is partly linear. 1

Sect. 6.2 Mathematical Tools 229
6.2 Mathematical Tools
The objective of the rest of this chapter is to formalize and generalize the previous
intuitive concepts for a broad class of nonlinear systems. To this effect, we first
introduce some mathematical tools from differential geometry and topology. To limit
the conceptual and notational complexity, we discuss these tools directly in the
context of nonlinear dynamic systems (instead of general topological spaces). Note
that this section and the remainder of this chapter represent by far the most
mathematically involved part of the book. Hurried practitioners may skip it in a. first
reading, and go directly to chapters 7-9.
In describing these mathematical tools, we shall call a vector function
f: R" —> R" a vector field in R", to be consistent with the terminology used in
differential geometry. The intuitive reason for this term is that to every vector function
f corresponds a field of vectors in an ^-dimensional space (one can think of a vector
f(x) emanating from every point x). In the following, we shall only be interested in
smooth vector fields. By smoothness of a vector field, we mean that the function f(x)
has continuous partial derivatives of any required order.
Given a smooth scalar function h(x) of the state x, the gradient of h is denoted
by Vh
The gradient is represented by a row-vector of elements (Vh): = dh I dx:. Similarly,
given a vector field f(x), the Jacobian of f is denoted by Vf
vf = i?
dx
It is represented by an n x n matrix of elements (Vf)- • = 3/j- I dx:.
(
LIE DERIVATIVES AND LIE BRACKETS
Given a scalar function h(x) and a vector field f(x), we define a new scalar function
Lfh, called the Lie derivative (or simply, the derivative) of h with respect to f.
Definition 6.1 Let h : R" —> R be a smooth scalar function, and f: R" —> R" be a
smooth vector field on R", then the Lie derivative of h with respect to f is a scalar
function defined by Lfh = Vh f.

230 Feedback Linearization Chap. 6
Thus, the Lie derivative Lfh is simply the directional derivative of h along the k
direction of the vector f.
Repeated Lie derivatives can be defined recursively
Lfh = h
L'h = L(L'-' h)= V(LM h) f for i= 1,2,
{ f f f
Similarly, if g is another vector field, then the scalar function Lg L h(x) is
f
g
One can easily see the relevance of Lie derivatives to dynamic systems by
considering the following single-output system
x = f(x)
y = h(x)
The derivatives of the output are
d h • . ,
y = — x = Lh
f
y =
dx
and so on. Similarly, if V is a Lyapunov function candidate for the system, its
derivative V can be written as Lf V.
Let us move on to another important mathematical operator on vector fields, the
Lie bracket.
Definition 6.2 Let f and g be two vector fields on R". The Lie bracket off and g is a
third vector field defined by
[f, g] = Vg f - Vf g
The Lie bracket [f, g] is commonly written as adf g (where ad stands for "adjoint").
Repeated Lie brackets can then be defined recursively by

| Sect. 6.2 |     |     |     |     | Mathematical Tools  |     | 231 |
| --------- | --- | --- | --- | --- | ------------------- | --- | --- |
adf g = g
adj g = [t, adf1'1 g]
for  /=1,2,
Example 6.7: The system (6.11) can be written in the form
with the two vector fields f and g defined by
|     | f = |     |     | g(x) = |     |     |     |
| --- | --- | --- | --- | ------ | --- | --- | --- |
COS(2A:|)
Their Lie bracket can be computed as
|     |     | 0   | 0 — 2xj + ax |  + nsxi | —2 + cosxj | a   | 0   |
| --- | --- | --- | ------------ | ------- | ---------- | --- | --- |
2 t
[f,g]=:
|     |     | -2sin(2x[) | 0   | —X2C0SXJ | x  sin Xj | — COSXj | cos(2x[) |
| --- | --- | ---------- | --- | -------- | --------- | ------- | -------- |
2
|     |     |                | acos(2xj)      |      |               |     | r   |
| --- | --- | -------------- | -------------- | ---- | ------------- | --- | --- |
|     |     | cosxjcos(2xj)- | 2sin(2x,)(-2x, | + ax | 2  + sinx ( ) |     |     |
The following lemma on Lie bracket manipulation will be useful later.
| Lemma 6.1  | Lie brackets have the following properties |     |     |     |     |     |     |
| ---------- | ------------------------------------------ | --- | --- | --- | --- | --- | --- |
(i) bilinearity:
|     | [f, c^g, + a | g ] = a [f, gj] + a |     | [f, g ] |     |     |     |
| --- | ------------ | ------------------- | --- | ------- | --- | --- | --- |
|     |              | 2 2                 | x   | 2 2     |     |     |     |
where f, f j , f  , g , g] and g  are smooth vector fields, and CC[ and a  are
|     |     | 2   | 2   |     |     |     | 2   |
| --- | --- | --- | --- | --- | --- | --- | --- |
constant scalars.
(it) skew-commutativity:
[f, g] = - [g, f]
(Hi) Jacobi identity:
|     | Ladgh  | =  LL | h-L Lh |     |     |     |     |
| --- | ------ | ----- | ------ | --- | --- | --- | --- |
|     |        | ( {   | g g f  |     |     |     |     |
where h(\) is a smooth scalar function of x.

| 232  Feedback Linearization |     |     |     | Chap. 6 |
| --------------------------- | --- | --- | --- | ------- |
Proof. The proofs of the first two properties are straightforward (Exercise 6.6). Let us derive the
third property, which can be rewritten as
The left-hand side of the above equation can be expanded as
while the right-hand side can be expanded as
| where 32/i / 3x2 is the Hessian of h, a symmetric matrix.  |     |     |     | D   |
| ---------------------------------------------------------- | --- | --- | --- | --- |
The Jacobi identity can be used recursively to obtain useful technical identities.
Using it twice yields
| Lad2g h  ~ Lad(adg) h  |     | ~ LfLadgh  | ~               |     |
| ---------------------- | --- | ---------- | --------------- | --- |
| (                      | f f |            | (               |     |
|                        |     | -  L       | Lh]  -  [LL   - |     |
|                        |     |            | g f f g         |     |
L2 h
|     | L  h - 2L L |     |  L h  | (6.47) |
| --- | ----------- | --- | ----- | ------ |
|     | g           | f   | g f f |        |
Similar identities can be obtained for higher-order Lie brackets.
DIFFEOMORPHISMS AND STATE TRANSFORMATIONS
The concept of diffeomorphism  can be viewed as a generalization of the familiar
concept of coordinate transformation. It is formally defined as follows:
Definition  6.3  A function  <|>: R" —> R",  defined in a  region Q,  is  called a
diffeomorphism if it is smooth, and if its inverse §~l exists and is smooth.
If  the  region  Q  is  the  whole  space  R",  then  <))(x) is  called  a global
diffeomorphism. Global diffeomorphisms are rare, and therefore one often looks for
local diffeomorphisms, i.e., for transformations defined only in a finite neighborhood
of a given point. Given a nonlinear function <(>(x), it is easy to check whether it is a
local diffeomorphism  by using the following  lemma,  which  is a  straightforward
consequence of the well-known implicit function theorem.
J

Sect. 6.2 Mathematical Tools 233
Lemma 6.2 Let (j>(xj be a smooth function defined in a region £1 in Rn. // the
Jacobian matrix V<(» is non-singular at a point \ = x of Q., then §(x) defines a local
0
diffeomorphism in a subregion ofCi.
A diffeomorphism can be used to transform a nonlinear system into another
nonlinear system in terms of a new set of states, similarly to what is commonly done
in the analysis of linear systems. Consider the dynamic system described by
y = h(\)
and let a new set of states be defined by
z = (|>(x)
Differentiation of z yields
z !* ! <«x)
6 x ox
One can easily write the new state-space representation as
i = f*(z) + g*(z)u
y = h*(z)
where x = (^'(z) has been used, and the functions f *, g* and h* are defined obviously.
Example 6.8; A non-global diffeomorphism
The nonlinear vector function
= <Kx) = (6.48)
3sinx-,
is well defined for all x and x. Its /acobian matrix is
t 2
10x,x
2
9x 0 3cosx
2
which has rank 2 at x = (0, 0). Therefore, Lemma 6.2 indicates that the function (6.48) defines a
local diffeomorphism around the origin. In fact, the diffeomorphism is valid in the region

234 Feedback Linearization Chap. 6
Q=((x,,x), |x|<rc/2)
2 2
because the inverse exists and is smooth for x in this region. However, outside this region, § does
not define a diffeomorphism, because the inverse does not uniquely exist. Q
THE FROBENIUS THEOREM
The Frobenius theorem is an important tool in the formal treatment of feedback
linearization for «tn-order nonlinear systems. It provides a necessary and sufficient
condition for the solvability of a special class of partial differential equations. Before
presenting the precise statement of the theorem, let us first gain a basic understanding
by discussing the case n = 3.
Consider the set of first-order partial differential equations
(6.49a)
>X2
djt dh dh
(6.49b)
8l +
dx. dx, 3*3
where and C| ,^2,^3) (/= 1,2,3) are known scalar functions of
xl>x2>x3> and h{x\,X2,x$ is an unknown function. Clearly, this set of partial
differential equations is uniquely defined by the two vectors
f = [/, f / ]T , g = [ g g g ]T. If a solution h(x ,x,x) exists for the above
2 3 x 2 3 x 2 3
partial differential equations, we shall say the set of vector fields {f , g} is completely
integrable.
The question now is to determine when these equations are solvable. This is not
obvious at all, a priori. The Frobenius theorem provides a relatively simple condition:
Equation (6.49) has a solution h(x\ ,^2,^3) if, and only if, there exists scalar functions
3) sucn mat
[f, g] = «! f + a g
2
i.e., if the Lie bracket of f and g can be expressed as a linear combination of f and g.
This condition is called the involutivity condition on the vector fields (f,g| •
Geometrically it means that the vector [f, g] is in the plane formed by the two vectors f
and g. Thus, the Frobenius theorem states that the set of vector fields {f,g| is
completely integrable if, and only if, it is involutive. Note that the involutivity
condition can be relatively easily checked, and therefore, the solvability of (6.49) can
be determined accordingly.
Let us now discuss the Frobenius theorem in the general case, after giving

| Sect. 6.2  |     |     | Mathematical Tools  | 235 |
| ---------- | --- | --- | ------------------- | --- |
formal definitions of complete integrability and involutivity.
Definition 6.4  A linearly independent set of vector fields {fj, f  ,...,  f }  on R" is
|     |     |     | 2 m |     |
| --- | --- | --- | --- | --- |
said to be completely integrable if, and only if, there exist n—m scalar functions
h^ix), h (\),....,  h _ {x) satisfying the system of partial differential equations
| 2   | n m          |     |     |        |
| --- | ------------ | --- | --- | ------ |
|     | Vh; fj  = 0  |     |     | (6.50) |
where 1 < / < n—m , 1 <j < m, and the gradients Vhj are linearly independent.
Note that with the number of vectors being m and the dimension of the associated
space being n, the number of unknown scalar functions  h involved is (n-m)  and the
v
number of partial differential equations is m(n-m).
Definition 6.5  A linearly independent set of vector fields {fj , f ,..., f  ) is said to
|     |     |     | 2 m |     |
| --- | --- | --- | --- | --- |
be involutive if, and only if, there are scalar functions a^  : R" —> R such that
|     | [f,-, f.](x) = $ W | x) f*(x)  V/,7  |     | (6.51) |
| --- | ------------------ | --------------- | --- | ------ |
Involutivity means that if one forms the Lie bracket of any pairs of vector fields from
the set {fj , f  ,..., f  ), then the resulting vector field can be expressed as a linear
2 m
combination of the original set of vector fields. Note that
• Constant vector fields are always involutive.  Indeed, the Lie bracket of
two constant  vectors is simply the zero  vector,  which can be trivially
expressed as linear combination of the vector fields.
• A set composed of a single vector f is involutive. Indeed,
[f,f] = (Vf)f-(Vf)f=O
• From Definition 6.5, checking whether a set of vector fields {fj ,...., f }
m
is involutive amounts to checking whether
|     | rank(f,(x)  .... f | (x)) = rank(f,(x) ... f | (x) [f,-, f ](x)) |     |
| --- | ------------------ | ----------------------- | ----------------- | --- |
|     |                    | m                       | M y               |     |
for all x and all i,j.
We can now state the Frobenius theorem formally.
Theorem 6.1 (Frobenius)  Let f [ , f  ,..., f  be a set of linearly independent vector
2 m
fields. The set is completely integrable if, and only if, it is involutive.
Example 6.9: Consider the set of partial differential equations

236  Feedback Linearization  Chap. 6
| 4,3!*-!*  | =o  |     |     |
| --------- | --- | --- | --- |
| 3 Xj      | 3 x |     |     |
2
| 3 h         | , 9 . 3 /i  | -  3ft  „   |     |
| ----------- | ----------- | ----------- | --- |
| - * , —+  ( | 2O_3 )      | + 2x-—  = 0 |     |
|             | X3 X2       | 3           |     |
| O Xy        | OX2         | 0JC3        |     |
The associated vector fields are jf, , f) with
2
(x2-3x)
| f, = [4*  3 | -1  Of  | f 2  = [-JC,  | 3 2 lx{f |
| ----------- | ------- | ------------- | -------- |
In order to determine whether this set of partial differential  equations is solvable (or whether
(fj f 2 ! is completely integrable), let us check the involutivity of the set of vector fields [f  l f). 2
One easily finds that
| [fl,f]  2 = [-12x3  | 3  Of |     |     |
| ------------------- | ----- | --- | --- |
Since [fj, f] = — 3 fj + 0f , this set of vector fields is involutive. Therefore, the two partial
| 2   | 2   |     |     |
| --- | --- | --- | --- |
differential equations are solvable.  D
6.3  Input-State Linearization of SISO Systems
In this section, we discuss input-state linearization for single-input nonlinear systems
represented by the state equations
i = f(x) + g(x)K  (6.52)
with f and g being  smooth vector fields.  We study when such systems can be
linearized by state and input transformations, how to find such transformations, and
how to design controllers based on such feedback linearizations.
Note that systems in the form (6.52) are said to be linear in control or affine. It
is useful to point out that if a nonlinear system has the form
x = f(x) + g(x) w[u + <|>(x)]
with w being an invertible scalar function and (|> being an arbitrary functional, a simple
variable substitution v = w[u + <|>(x)] puts the dynamics into the form of (6.52).  One
can  design  a  control  law  for  v  and  then  compute  u  by  inverting  w,  i.e.,
DEFINITION OF INPUT-STATE LINEARIZATION
In order  to proceed  with  a detailed  study  of  input-state  linearization,  a  formal
definition of this concept is necessary:

Sect. 6.3 Input-State Linearization o/SISO Systems 237
Definition 6.6 A single-input nonlinear system in the form (6.52), with f(x) and g(x)
being smooth vector fields on W, is said to be input-state linearizable if there exists a
region £2 in R", a diffeomorphism <|> : O —-> R", and a nonlinear feedback control law
u = a(x) + p(x)v (6.53)
such that the new state variables z = <{t(x) and the new input v satisfy a linear time-
invariant relation
z= Az+ bv (6.54)
where
"010 . . 0
0 0 1 .
A= b =
0 0 0 . . 1
0 0 0 . . 0
The new state z is called the linearizing state, and the control law (6.53) is called the
linearizing control law. To simplify notations, we will often use z to denote not only
the transformed state, but the diffeomorphism <|> itself, i.e. write
z = z(x)
This slight abuse of notations should not create any confusion.
Note that the transformed linear dynamics has its A matrix and b vector of a
special form, corresponding to a linear companion form. However, generality is not
lost by restricting ourselves to this special linear equivalent dynamics, because any
representation of a linear controllable system is equivalent to the companion form
(6.54) through a linear state transformation and pole placement. Therefore, if (6.53)
can be transformed into a linear system, it can be transformed into the form prescribed
by (6.54) by using additional linear transformations in state and input.
We easily see from the canonical form (6.54) that feedback linearization is a
special case of input-output linearization, where the output function leads to a relative
degree n. This means that if a system is input-output linearizable with relative degree
n, it must be input-state linearizable. On the other hand, if a system is input-state
linearizable, with the first new state Z\ representing the output, the system is input-
output linearizable with relative degree n. Therefore, we can summarize the

238 Feedback Linearization Chap. 6
relationship between input-output linearization and input-state linearization as follows:
Lemma 6.3 An nth-order nonlinear system is input-state linearizable if, and only if,
there exists a scalar function Zj(x) such that the system's input-output linearization
with Z[(x) as output function has relative degree n.
Note, however, that the above lemma provides no guidance about how to find the
desirable output function Z[(x).
CONDITIONS FOR INPUT-STATE LINEARIZATION
At this point, a natural question is: can all nonlinear state equations in the form of
(6.52) be input-state linearized? If not, when do such linearizations exist? The
following theorem provides a definitive answer to that question, and constitutes one of
the most fundamental results of feedback linearization theory.
Theorem 6.2 The nonlinear system (6.52), with ffxj and g(x) being smooth vector
fields, is input-state linearizable if, and only if, there exists a region Q such that the
following conditions hold:
• the vector fields {g, adf g ,...., adfn~^ g} are linearly independent in Q
• the set {g, adf g ,..., ad{"~^ g} is involutive in Q
Before proving this result, let us make a few remarks about the above conditions:
• The first condition can be interpreted as simply representing a
controllability condition for the nonlinear system (6.52). For linear systems,
the vector fields (g, adfg,...., adn~l g } become { b , Ab ,...., A""1 b ) ,
f
and therefore their independence is equivalent to the invertibility of the
familiar linear controllability matrix. It is also easy to show that if a system's
linear approximations in a closed connected region Q in R" are all
controllable, then, under some mild smoothness assumptions, the system can
be driven from any point in Q to any point in O. However, as mentioned in
chapter 3, a nonlinear system can be controllable while its linear
approximation is not. The first condition above can be shown to represent a
generalized controllability condition which also accounts for such cases.
• The involutivity condition is less intuitive. It is trivially satisfied for linear
systems (which have constant vector fields), but not generically satisfied in
the nonlinear case.
Let us now prove the above theorem. We first state a technical lemma. j

| Sect. 6.3  |     |     | Input-State Linearization ofSISO Systems  |     | 239 |
| ---------- | --- | --- | ----------------------------------------- | --- | --- |
Lemma 6.4  Let z(x) be a smooth function in a region il.  Then, in Q, the set of equations
|     | Lz  = LLz  | = ... = LLkz  |     | = O  | (6.55a) |
| --- | ---------- | ------------- | --- | ---- | ------- |
|     | g g        | f             | g { |      |         |
is equivalent to
|     | Li  = L | z  = ... = L | z     | = O  | (6.55b) |
| --- | ------- | ------------ | ----- | ---- | ------- |
|     | g adfg  |              | adfkg |      |         |
for any positive integer k.
Proof: Let us show that (6.55a) implies (6.55b).
When k = 0, the result is obvious. When k = 1, we have from Jacobi's identity (Lemma 6.1)
|     | Lad, z = LL | z-L   | Lz  | = 0-0  = 0 |     |
| --- | ----------- | ----- | --- | ---------- | --- |
|     | %           | f g g | f   |            |     |
When k = 2, we further have, using Jacobi's identity twice as in (6.47)
|     | L i z  = L2L | z-2LL | Lz    | + L L2z  = 0-0 + 0 = 0 |     |
| --- | ------------ | ----- | ----- | ---------------------- | --- |
|     | ad%          | f g   | t g f | g t                    |     |
Repeating this procedure, we can show by induction that (6.55a) implies (6.55b) for any k.
One proceeds similarly to show that (6.55b) implies (6.55a) (by using Jacobi's identity the
| other way around).  |     |     |     |     | D   |
| ------------------- | --- | --- | --- | --- | --- |
We are now ready for the proof of Theorem 6.2 itself.
Proof of Theorem 6.2: Let us first prove the necessity of the conditions. Assume that there exist
a state transformation z = z(x) and an input transformation u = a(x) + P(x) v such that z and v
satisfy (6.54). Expanding the first line of (6.54), we obtain
dz,
z
Proceeding similarly with the other components of z leads to a set of partial differential equations
3 z,  d z,
|     | —if+ -ig«  | = z | 2   |     |     |
| --- | ---------- | --- | --- | --- | --- |
3x  3x
d Zj  d z2
|     | -—f  + -—  | gi/ = z |     |     |     |
| --- | ---------- | ------- | --- | --- | --- |
|     | 9x  dx     |         | 3   |     |     |
dzn  dn
e
|     | f +  | g W = V |     |     |     |
| --- | ---- | ------- | --- | --- | --- |
d X  dx
Since Z| ,... , z are independent of u, while v is not, we conclude from the above equations that
n

240 Feedback Linearization Chap. 6
(6.56a) >l
' = 1.2,..., « (6.56b) ||
I
The above equations on the z,- can be compressed into a set of constraint equations on 2,
alone. Indeed, using Lemma 6.4, equation (6.56a) implies that
Vzadkg = 0 k = 0, 1,2,... ,n-2 (6.57a)
l (
Furthermore by proceeding as in the proof of Lemma 6.4, we can show
This implies that
Vzad"-lg * 0 (6.57b)
l (
The first property we can now infer from (6.57) is that the vector fields
g, adf g ,... , adf"~\ g must be linearly independent. Indeed, if for some number i (i < n-1), there
existed scalar functions <X|(x),..., ct^x) such that
/-I
we would have
n-2
adf" ' 8 = o. k ad { k g
This, together with (6.57a), would imply that
n-2
k=n-i-\
a contradiction to (6.57b).
The second property we can infer from (6.57) is that the vector fields are involutive. This
follows from the existence of a scalar function z satisfying the n- 1 partial differential equations
{
in (6.57a), and from the necessity part of the Frobenius theorem. Thus, we have completed the
necessity part of the proof of Theorem 6.2.
Let us now prove that the two conditions in Theorem 6.2 are also sufficient for the input-state
linearizability of the nonlinear system in (6.52), i.e., that we can find a state transformation and an
input transformation such that (6.54) is satisfied. The reasoning is as follows. Since the
involutivity condition is satisfied, from Frobenius theorem there exists a non-zero scalar function
z,(x) satisfying

| Sect. 6.3   |                  | Input-State Linearization ofSISO Systems  | 241    |
| ----------- | ---------------- | ----------------------------------------- | ------ |
| LS z\ = Lod |  H = - = Lod"-\  | z\ = °                                    | (6-58) |
fg t
From Lemma 6.4, the above equations can be written
| L z, = L Lz  | = ... = L L"-2  | z, = 0  | (6.59) |
| ------------ | --------------- | ------- | ------ |
g g t x g {
This means that if we use z = [ z  L Zj ... L"~'  zj ]T  as a new set of state variables, the first
|     | {   | f { |     |
| --- | --- | --- | --- |
n— 1 state equations verify
zk = zk+\  *=l,....n-l
while the last state equation is
| z = Lfz+L | Lf~xzu  |     | (6.60) |
| --------- | ------- | --- | ------ |
n x % x
Now  the question  is whether L L"~iz  can be equal  to zero.  Since  the vector  fields
|     |     | t l |     |
| --- | --- | --- | --- |
adf"~lg
{ g, adfg,...,  \ are linearly independent in £1, and noticing, as in the proof of Lemma
6.4, that (6.58) also leads to
we must have
| W-'gM*) * 0  |     | VxeQ  | (6.61) |
| ------------ | --- | ----- | ------ |
Otherwise, the non-zero vector Vz, would satisfy
| Vzl  tg  adi%  | -  ^""'g]  | = 0 |     |
| -------------- | ---------- | --- | --- |
f
and thus would be orthogonal to n linearly independent vectors, a contradiction.
Therefore, by taking the control law to be
u = (~L"z  +  v)/(L L"-iz)
|     | ( l | % t l |     |
| --- | --- | ----- | --- |
equation (6.60) simply becomes
'zn = v
which shows that the input-output linearization of the nonlinear system has been achieved.  d
HOW TO PERFORM INPUT-STATE LINEARIZATION
Based on the previous discussion, the input-state linearization of a nonlinear system
can be performed through the following steps:
• Construct the vector fields g, adf g,...., adfn~ 'g for the given system
• Check whether the controllability and involutivity conditions are satisfied

| 242  Feedback Linearization |     |     | Chap. 6 |
| --------------------------- | --- | --- | ------- |
• If both are satisfied, find the first state zy (the output function leading to
input-output linearization of relative degree n) from equations (6.58), i.e.,
|     | = 0 ; = 0,... ,n-2 |     | (6.62a) |
| --- | ------------------ | --- | ------- |
(6.62b)
|                                                 |     | ... Ln  *z y }T  |         |
| ----------------------------------------------- | --- | ---------------- | ------- |
| • Compute the state transformation z(x) = [ zj  |     | Lz\              | and the |
f f
input transformation (6.53), with
| a(x) = - |     |     | (6.63a) |
| -------- | --- | --- | ------- |
(6.63b)
Let us now demonstrate the above procedure on a simple physical example
[Marino and Spong, 1986; Spong and Vidyasagar, 1989].
Example 6.10: Consider the control of the mechanism in Figure 6.6, which represents a link
driven by a motor through a torsional spring (a single-link flexible-joint robot), in the vertical
plane. Its equations of motion can be easily derived as
|     | k(q-q ) = |     | (6.64a) |
| --- | --------- | --- | ------- |
l 2
| J'q 2 -k(q-q l | 2 )  = u |     | (6.64b) |
| -------------- | -------- | --- | ------- |
Figure 6.6 : A flexible-joint mechanism
Because nonlinearities (due to gravitational torques) appear in the first equation, while the control
input u enters only in the second equation, there is no obvious way of designing a large range
controller. Let us now consider whether input-state linearization is possible.
First, let us put the system's dynamics in a state-space representation. Choosing the state

| Sect. 6.3 |     |     | Input-State Linearization ofSISO  | Systems  243 |
| --------- | --- | --- | --------------------------------- | ------------ |
vector as
x=Ul  <?1 <72 <?2i
the corresponding vector fields f and g can be written
k
f =  [x2
sinx, --(X| -J
i]r
|     | g = [0  | o  o  |     |     |
| --- | ------- | ----- | --- | --- |
Second, let us check the controllability and involutivity conditions.  The controllability
matrix is obtained by simple computation
0  0  0  --1
77
|     | [g  ad%  | ad2fg  | ad3g] = |     |
| --- | -------- | ------ | ------- | --- |
|     | (        |        | f       |     |
It has rank 4 for k>0,IJ  <°°.  Furthermore, since the vector fields  ) g, ad g, ad2 g)  are
f {
constant, they form an involutive set. Therefore, the system in (6.64) is input-state linearizable.
Third,  let  us find out the  state  transformation  z = z(x)  and  the  input  transformation
u = <x(x) + j5(x) v so that input-state linearization is achieved.  From (6.62), and given the above
expression of the controllability matrix, the first component Z[ of the new state vector z should
satisfy
|     | = 0   |       | = 0 = 0 |     |
| --- | ----- | ----- | ------- | --- |
|     | 3 x-, | d x-. | d x     |     |
A
Thus, zj must be a function of jr only. The simplest solution to the above equations is
f
|     | z,  = JC. |     |     | (6.65a) |
| --- | --------- | --- | --- | ------- |
The other states can be obtained from z.
(6.65b)
|     | z = Vz f = - —i— smx - - (x, - x) 3 2 |     | x 3 | (6.65c) |
| --- | ------------------------------------- | --- | --- | ------- |

244 Feedback Linearization Chap. 6
z4 = Vz3 f = - x
2
cosx, - j ((x
2
- x
4
) (6.65d)
Accordingly, the input transformation is
u = (v-Vzf)/(Vzg)
4 4
which can be written explicitly as
(6.66)
where
* * MgL
a(\) = —f—sm (- ++ - + —f—
/
I J
As a result of the above state and input transformations, we end up with the following set of linear
equations
24=V
thus completing the input-state linearization.
Finally, note that
• The above input-state linearization is actually global, because the diffeomorphism z(x)
and the input transformation are well defined everywhere. Specifically, the inverse of the
state transformation (6.65) is
MgL
which is well defined and differentiable everywhere. The input transformation (6.66) is
also well defined everywhere, of course.
• In this particular example, the transformed variables have physical meanings. We see that

Sect. 6.3 Input-State Linearization of SISO Systems 245
Z] is the link position, z the link velocity, z the link acceleration, and z the link jerk. This
2 3 4
further illustrates our earlier remark that the complexity of a nonlinear physical model is
strongly dependent on the choice of state variables.
• In hindsight, of course, we also see that the same result could have been derived simply
by differentiating equation (6.64a) twice, i.e., from the input-output linearization
perspective of Lemma 6.3. D
Note that inequality (6.62b) can be replaced by the normalization equation
V ad"-lg = 1
Zl (
without affecting the input-state linearization. This equation and (6.62a) constitute a
total of n linear equations,
' 0 '
0
[adfg ad\g ...
0
dz/dx 1
l n
Given the independence condition on the vector fields, the partial derivatives
dz^/dxy , , dzy/dx,, can be computed uniquely from the above equations. The state
variable Zj can then be found, in principle, by sequentially integrating these partial
derivatives. Note that analytically solving this set of partial differential equations for
zj may be a nontrivial step (although numerical solutions may be relatively easy due
to the recursive nature of the equations).
CONTROLLER DESIGN BASED ON INPUT-STATE LINEARIZATION
With the state equation transformed into a linear form, one can easily design
controllers for either stabilization or tracking purposes. A stabilization example has
already been provided in the intuitive section 6.1, where v is designed to place the
poles of the equivalent linear dynamics, and the physical input u is then computed
using the corresponding input transformation. One can also design tracking
controllers based on the equivalent linear system, provided that the desired trajectory
can be expressed in terms of the first linearizing state component zj.
Consider again the flexible link example. Its equivalent linear dynamics can be
expressed as

246 Feedback Linearization Chap. 6
Assume that it is desired to have the link position Zj track a prespecified trajectory
). The control law
a 3 ~ ao
(where leads to the tracking error dynamics
The above dynamics is exponentially stable if the positive constants a- are chosen
(
properly. To find the physical input u, one then simply uses (6.66).
6.4 Input-Output Linearization of SISO Systems
In this section, we discuss input-output linearization of single-input nonlinear systems
described by the state space representation
(6.67a)
V = h(\) (6.67b)
where y is the system output. By input-output linearization we mean the generation of
a linear differential relation between the output y and a new input v (v here is similar
to the equivalent input v in input-state linearization). Specifically, we shall discuss the
following issues:
• How to generate a linear input-output relation for a nonlinear system?
• What are the internal dynamics and zero-dynamics associated with the
input-output linearization?
• How to design stable controllers based on input-output linearizations?
GENERATING A LINEAR INPUT-OUTPUT RELATION
As discussed in section 6.1.3, the basic approach of input-output linearization is
simply to differentiate the output function y repeatedly until the input u appears, and
then design u to cancel the nonlinearity. However, in some cases, the second part of
the approach may not be carried out, because the system's relative degree is
undefined.
The Case of Well Defined Relative Degree
Let us place ourselves in a region (an open connected set) £2 in the state space. Using
X

Sect. 6.4 Input-Output Linearization of SISO Systems 247
the notations of differential geometry, the process of repeated differentiation means
that we start with
y = Vh (f + g u) = L h(x) + L h(x) u
f g
If L h(x) * 0 for some x = x in Q , then, by continuity, that relation is
g 0 x
verified in a finite neighborhood £2 of x . In D, the input transformation
g
u = —!— (-Lfh + v)
Lgh
results in a linear relation between y and v, namely y = v.
If L h(x) = 0 for all x in £2 , we can differentiate y to obtain
g X
If L L /z(x) is again zero for a// x in Q , we shall differentiate again and again,
g f x
jW = L' h(x) + L L'- * /;(x)M
f g f
until for some integer r
L Lr~l h(x)*0
g {
for some x = x in il . Then, by continuity, the above relation is verified in a finite
0 x
neighborhood Q of x . In Q, the control law
o
u = ! (-Lrh + v) (6.68)
f
LgLf'""1/!
applied to
>>('•> = L' h(x) + L L'-! /i(x) M (6.69)
f g f
yields the simple linear relation
3-W = v (6.70)
As discussed in section 6.1.3, the number r of differentiations required for the
input u to appear is called the relative degree of the system, an extension of the usual
definition of relative degree for linear systems. As also noticed earlier, and as we
shall soon formalize, one necessarily has r < n (where n is the system order). If
r = n , then input-output linearization actually yields input-state linearization in O., as
stated in Lemma 6.3.

248 Feedback Linearization Chap. 6
Based on the above procedure, we can give the following formal definition.
Definition 6.7 The SISO system is said to have relative degree r in a region O if,
VXG Q
L L'/j(x) = 0 0<i<r-l (6.71a)
g f
LgLf'-'/iCx) * 0 (6.71b)
The Case of Undefined Relative Degree
It is often the case that one is a priori interested in the properties of the system about a
specific operating point x. The definition of the relative degree then requires
0
particular care.
As before, let us differentiate the output y until the input u appears (i.e., until the
coefficient of u is not identically zero in a neighborhood of x). Then, if the
0
coefficient of u is nonzero at x
0
this also implies, by continuity, that (6.71b) is verified over a finite neighborhood of
x . We shall then say that the system has relative degree r at the point x . |
0 0
However, it is possible that when the input appears, its coefficient •
Lg Lfr~' h(x) is zero at x , but nonzero at some points x arbitrarily close to x . |
o 0
The relative degree of the nonlinear system is then undefined at x . This case is
0
illustrated by the following simple example.
Example 6.1 IT Consider the system
x = p (x, x) + u
where p is some smooth nonlinear function of the state x = [ x x ]T. If
y = x
is defined as the output of interest, then the system is obviously in companion form, with relative
degree 2.
However, if instead one takes
as output, then
i

Sect. 6.4 Input-Output Linearization ofSISO Systems 249
y = 2 x'x
y = 2/J + 2x2 = 2jt(p+ «) + 2x2
In other words,
L Lh = 2x
g {
and therefore, at x = 0 and for this choice of output, the system has neither relative degree 1 nor
relative degree 2. E3
In some particular cases, as above, a simple change of output will allow one to
define an equivalent but easily solvable control problem. In general, however, input-
output linearization at a point cannot be straightforwardly achieved when the relative
degree is undefined. In the rest of this section, we consider only systems having a
well defined relative degree in a region Q (which shall often be a neighborhood of an
operating point of interest x ).
0
NORMAL FORMS
When the relative degree r is defined and r < n, the nonlinear system (6.67) can be
transformed, using y,y,..., y(r~V as part of the new state components, into a so-
called "normal form", which shall allow us to take a more formal look at the notions of
internal dynamics and zero-dynamics introduced in section 6.1.3. Let
|i = [n, H ... \i]T = [y y ... y(.r-»f (6.72)
2 r
In a neighborhood Q of a point x , the normal form of the system can be written as
o
V- = (6.73a)
a(\i,
(6.73b)
with the output defined as
(6.74)
The (i- and i|/- are referred to as normal coordinates or normal states in Q (or at x ).
( 0
Note that the companion form subsystem (6.73a) is simply another expression of
(6.69), while the subsystem (6.73b) does not contain the system input u.

| 250  Feedback Linearization  |     |     | Chap. 6 |
| ---------------------------- | --- | --- | ------- |
To show that the nonlinear system (6.67) can indeed be transformed into the
normal form (6.73), we have to show not only that such a coordinate transformation
exists, but also that it is a true state transformation. In other words, we need to show
that we can construct a (local) diffeomorphism
such  that  (6.73)  is verified.  According  to  Lemma  6.2, to  show  that  §  is a
diffeomorphism,  it suffices  to show that its Jacobian  is invertible, i.e., that the
gradients V|i- and V\|/• are all linearly independent.
In the following, we first show that the gradients V(j,- are linearly independent,
(
i.e., that the components of \i can serve as state variables. This result, of course, is not
overly surprising, since it simply says that the system output v and its first  r—l
derivatives can serve as state variables. We then show that  n—r other vector fields
v|/,- can be found to complete the new state vector, in other words, can be found such
that the gradients Vu.,- and Vy.- are all linearly independent.
Let us first show that the gradients V(i,- are linearly independent.
Lemma 6.5  If the relative degree of the system (6.67) is r in the region Q, then the
gradients V|Xj , V(i.2 , ;.... , V|i are linearly independent in £l.
r
Proof: Let us first remark that, in terms of (l, equations (6.71) can be written simply as
| Vu,- g = 0  | 1 < i < r  |     | (6.76a) |
| ----------- | ---------- | --- | ------- |
| V|i. g * o  |            |     | (6.76b) |
r
We present the proof for the case r = 3 (the general case can be shown in a similar fashion).
| Assume that there exist smooth functions  |            | a-(x) such that (everywhere in £2) ; |         |
| ----------------------------------------- | ---------- | ------------------------------------ | ------- |
|                                           | aV[i3 = 0  |                                      | (6.77a) |
3
Multiplying (6.77a) by g yields
| [c^Vu, +aVn + aV|i3]g  | 2 2 3 | = 0 |     |
| ---------------------- | ----- | --- | --- |
which, from (6.76), implies that 013 = 0 (everywhere in £2).
Replacing a 3 = 0 in (6.77a), in turn, implies that
| a,Vu, + aVu = 0  |     |     | (6.77b) |
| ---------------- | --- | --- | ------- |
|                  | 2 2 |     |         |
Multiplying (6.77b) by the Lie bracket adfg , and using Jacobi's identity and (6.71a), yields
0  = a\Lad V-\  + <:hLadgV2 =
%

| Sect. 6.4  |     | Input-Output Linearization of SISO Systems  |     |     | 251 |
| ---------- | --- | ------------------------------------------- | --- | --- | --- |
which, from (6.71b), implies that a = 0 (everywhere in Q).
2
| Replacing a? = "             | m (6.77b) implies that |                                          |     |     |         |
| ---------------------------- | ---------------------- | ---------------------------------------- | --- | --- | ------- |
|                              | a,VH[=O                |                                          |     |     | (6.77c) |
| Multiplying (6.77c) by ad2g  |                        | , and using (6.47) and (6.71a), leads to |     |     |         |
f
|     | 0 = o.L i\i  | = a, [L2 Lh -2LLLh  | + LL2  h] = a,LL2 h |     |     |
| --- | ------------ | ------------------- | ------------------- | --- | --- |
|     | x adg        | x ( g               | t g t g f           | g f |     |
which, from (6.71b), implies that CC] = 0 (everywhere in £1).
Thus, (6.77a) can only be verified if all the coefficients a- equal zero everywhere in Q.. This
(
| shows that the gradients V(i are linearly independent.  |     |     |     |     | •   |
| ------------------------------------------------------- | --- | --- | --- | --- | --- |
;
Note that an immediate implication of this result is that, consistently  with
intuition, the relative degree of an «m-order system is always smaller than n (because
there cannot be more than n linearly independent vectors in an ^-dimensional space).
Let us now show that there exist  n-r  more functions \\f: to complete the
coordinate transformation.
Proof: As noticed earlier, given Lemma 6.2, we simply need to show that gradients vectors V\|/-
can  be found  such  that the Vu, and V\|/- are all linearly  independent. The development  is
illustrated in Figure 6.7.
At x , equation (6.76a) indicates that the first r— 1 vectors V(i- (1 = 1, ...  , r— 1 ), which we
|     | o   |     | ;   |     |     |
| --- | --- | --- | --- | --- | --- |
have just shown to be linearly independent, are all within the hyperplane orthogonal to g. Since
the dimension of that hyperplane is n— 1 , one can find
n-r  =  (n-l)-(r-l)
vectors in that hyperplane that are linearly independent of the Vu.,- and linearly independent of
each other. Lei us call these vectors V\j/y (J = 1, ...  ,«-/). By definition, they verify
|     | Vvj/- g = 0  y | 1 <j<n~r  |     |     | (6.78) |
| --- | -------------- | --------- | --- | --- | ------ |
A subtle point at this stage is that gradient vector fields are not just any vector fields (they must
satisfy curl conditions, cf. also section 3.5.3).  Fortunately, Frobenius theorem (Theorem 6.1)
comes to the rescue, since its application  to the single vector field  g (which  is obviously
involutive) guarantees that there does exist n-\  linearly independent gradient  functions  Vh k
| which satisfy  | Vh  g = 0. |     |     |     |     |
| -------------- | ---------- | --- | --- | --- | --- |
k
Furthermore, from (6.76b), u is not in the hyperplane orthogonal to g. Thus the gradients
r
Vu (1 = 1, ...  ( , r) and Vy- (j = 1, ...  , n—r) are all linearly independent. Thus, the Jacobian
of the transformation (6.75) is invertible.

252 Feedback Linearization Chap. 6
Figure 6.7 : Illustrating the construction
of y
By continuity, the lacobian remains invertible in a neighborhood i2j of x . Redefining ii as
0
the intersection of Qj and £2, the transformation 4/ thus defines a diffeomorphism in Q. Hence, in
Q this transformation is a true state transformation, which puts the nonlinear system into the form
(6.73), with, in (6.73a)
a(n, y) = Lf'h(x) = Lrh[^~
(
while in (6.73b) the input u indeed does not appear, since from (6.78) the y.y verify
LMi(x) = 0 Vxe Q D
a :
From a practical point of view, explicitly finding a vector field y to complete
the transformation into a normal form requires the (often nontrivial) step of solving
the set (6.78) of partial differential equations in the \y-. The following example,
adapted from [Isidori, 1989], illustrates this procedure.
Example 6.12: Consider the nonlinear system
2x
e 2
2 A"| 2 + 1/2 (6.79)
0
> = h(\) = ,v
Since
y = 2 A'2 = 2 (2 Xj A'2 + sin x^) +

Sect. 6.4 Input-Output Linearization of SISO Systems 253
the system has relative degree 2, and
Lh(x) = 2x Lh{x) = O
f 2 g
LLh(x)=l
g t
In order to find the normal form, let us take
(i = L h(x) = 2x
2 f 2
The third function \|/(x) required to complete the transformation should satisfy
, 3 w -y 1 3\|/ „
x
L V = —ie2*2+ _Z = 0
s 3 *! 2dx
2
One solution of this equation is
\)/(x) = 1 + JCJ -e2jr2
V lr- Its Jacobian matrix is
Consider now the associated state transformation z = [ (LLj
0 0 l"
0 2 0
dx
1 -2e2jr2 0
which is non-singular for any x. The inverse transformation is given by
Thus, this state transformation is valid globally. With the above set of new coordinates, the
system dynamics is put into the normal form
D
THE ZERO-DYNAMICS
By means of input-output linearization, the dynamics of a nonlinear system is
decomposed into an external (input-output) part and an internal ("unobservable") part.
Since the external part consists of a linear relation between y and v (or equivalently,

254 Feedback Linearization Chap. 6
the controllability canonical form between y and u, as in (6.73a)), it is easy to design
the input v so that the output y behaves as desired. Then, the question is whether the
internal dynamics will also behave well, i.e., whether the internal states will remain
bounded. Since the control design must account for the whole dynamics (and therefore
cannot tolerate the instability of internal dynamics), the internal behavior has to be
addressed carefully.
The internal dynamics associated with the input-output linearization simply
corresponds to the last (n—r) equations \jf = w(|i, \|/) of the normal form. Generally,
this dynamics depends on the output states |i. However, as we now detail, we can
define an intrinsic property of the nonlinear system by considering the system's
internal dynamics when the control input is such that the output y is maintained at |j
zero. Studying this so-called zero-dynamics will allow us to make some conclusions
about the stability of the internal dynamics.
The constraint that the output y is identically zero implies that all of its time
derivatives are zero. Thus, the corresponding internal dynamics of the system, or zero-
dynamics, describes motion restricted to the (n-r)-dimensional smooth surface
(manifold) M defined by \i = 0 . In order for the system to operate in zero-dynamics,
o
i.e., for the state x to stay on the surface M , the initial state of the system x(0) must
o
be on the surface, and, furthermore, the input u must be such that y stays at zero, i.e.,
such that y^(t) = 0 . From (6.69), this means that u must equal
Corresponding to this input, and assuming that indeed the system's initial state is on
the surface, i.e., that ^.(0) = 0, the system dynamics can be simply written in normal
form as
|1 = 0 (6.80a)
V = w(0, \f) (6.80b)
By definition, (6.80b) is the zero-dynamics of the nonlinear system (6.67).
The evolution of the system state when operating in zero-dynamics is illustrated
in Figure 6.8. Note that, in normal coordinates, the control input u can be written as a
0
function only of the internal states \\i
y)

Sect. 6.4 Input-Output Linearization ofSISO Systems 255
Example 6.13: Zero-dynamics of a nonlinear system
Consider again the nonlinear system of Example 6.12. Its internal dynamics is represented by the
equation
Its zero-dynamics is obtained by letting \i = 0 and (l^ = 0
l
The input u = 0 maintains the output always equal to zero.
g
M
o
(a) (b)
Figure 6.8 : Evolution of the system state on the zero-dynamics manifold, for n = 3, r- 1.
(a) in original state coordinates, (b) in normal coordinates.
Note that computing a system's internal dynamics (or zero-dynamics) does not
necessarily require to first put the system explicitly in normal form, i.e. to solve the
p.d.e.'s defining y, which were carefully devised such that u does not appear in y.
Indeed, since u (or u ) is known as a function of the state x, it is often easier, given (i,
0
to simply find n—r vector fields p.- to complete the state transformation, and then
replace u (or u ) by its expression, as we did in section 6.1.3. One can verify that the
o
corresponding state transformation is one-to-one either directly, or by checking that
the Jacobian of the transformation is invertible.
Recall from section 6.1.3 that linear systems whose zero-dynamics are stable
are called minimum phase. For convenience of reference, we shall extend the
terminology to nonlinear systems.

256 Feedback Linearization Chap. 6
Definition 6.8 The nonlinear system (6.67) is said to be asymptotically minimum
phase if its zero-dynamics is asymptotically stable.
The concept of exponentially minimum phase can be defined similarly. If the
zero dynamics is asymptotically stable for any y(0), we shall say the system is
globally asymptotically minimum phase. Otherwise, we shall say the system is locally
minimum phase. For instance, the system (6.79) is globally asymptotically minimum
phase.
Let us now consider controller designs based on input-output linearization.
Essentially, the idea is to design a controller based on the linear input-output relation
and then check whether the internal dynamics is stable or not. In the following, we
first state a result for local stabilization, and then offer some discussions of global
stabilization and of tracking control.
LOCAL ASYMPTOTIC STABILIZATION
Consider again the nonlinear system (6.67). It is natural to wonder whether choosing
the artificial input v in (6.70) as a simple linear pole-placement controller provides
any guarantee about the stability of the overall system. In other words, assume that in
(6.70) we let
where the coefficients k are chosen such that the polynomial
[
pr + k_pr-x + + k + k (6.81)
r x lP 0
has all its roots strictly in the left-half plane. The actual control input u can then be
written, from (6.68)
u(x) = ^ - [ - L ^y - k_ y(>-V - ... - k y - k y] (6.82)
r x x o
LL> ly
g {
The following result indicates that, provided that the zero-dynamics is asymptotically
stable, this control law indeed stabilizes the whole system locally.
Theorem 6.3 Assume that the system (6.67) has relative degree r, and that its zero-
dynamics is locally asymptotically stable. Choose constants k such that the
t
polynomial (6.81) has all its roots strictly in the left-half plane. Then, the control law
(6.82) yields a locally asymptotically stable closed-loop system.
Proof: The result can be easily understood by writing the closed-loop dynamics in normal
coordinates, where by design

Sect. 6.4 Input-Output Linearization ofSISO Systems 257
0 1 0 .. 0"
o o o .. i K = Afl
h.o.t.
where h.o.t. denotes higher order terms in the Taylor expansion about x = 0 , and the matrices
o
A, A|, and A2 are defined obviously. The above equations can be written
d A O
+ h.o.t.
d7 V A, A 2
Now since the zero-dynamics is asymptotically stable, its linearization y = A y is either
2
asymptotically stable or marginally stable, according to Lyapunov's linearization theorem
(Theorem 3.1).
If A is asymptotically stable (i.e., has all its eigenvalues strictly in the left-half plane), then
2
the above linearized approximation of the whole dynamics is asymptotically stable, and therefore,
using again Lyapunov's linearization theorem, the nonlinear system is locally asymptotically
stable.
If A is only marginally stable, stability of the closed loop system can still be derived by
2
using the so-called center-manifold theory [Byrnes and Isidori, 1988]. E3
In view of the fact that local stabilization problems may also be solved by linear
control methods (through linearization and pole placement), one may wonder about
the usefulness of the above theorem. The answer to that question is that the above
stabilization method can treat systems whose linearizations contain uncontrollable but
marginally stable modes, while linear control methods requires the linearized system
to be strictly stabilizable.
For stabilization problems, where state convergence is the objective, one is
usually free to choose the output function y = h(x), and thus affect the zero-dynamics.
Therefore, it might be possible to choose an output function such that the
corresponding zero-dynamics is asymptotically stable. As a result, the controller
specified in the above theorem will be able to stabilize the nonlinear system.
Example 6.14: Consider the nonlinear system
=x, x (6.83a)

258 Feedback Linearization Chap. 6
X2 ~ ^ X2 + u (6.83b)
The system's linearization at x = 0 (where \ = [x x] ) is
l 2
i,=0
A"o = 3 JCT + M
and thus has an uncontrollable mode corresponding to a pure integrator.
Let us define the output function
(6.84)
Corresponding to this output, the relative degree of the system is 1, because
^ = -2i,-Jc, = -2x,2x,-3jt,-«
dt
The associated zero-dynamics (obtained by setting y — 0) is simply
and thus is asymptotically stable (cf. Example 3.9). Therefore, according to Theorem 6.3, the
control law
locally stabilizes the nonlinear system. •
GLOBAL ASYMPTOTIC STABILIZATION
As we saw earlier, the stability of the zero-dynamics only guarantees the local stability
of a control system based on input-output linearization (unless the relative degree
equals the system order, in which case there is no internal dynamics), while the
stability of the internal dynamics itself is generally untractable (except in very simple
cases, as in section 6.1.3). Thus, it is natural to wonder whether input-output
linearization ideas can be of any use in (often most practically important) global
stabilization problems. Similarly, one may wonder how to achieve system
stabilization using a given input-output linearization in case the zero-dynamics is
unstable.
An approach to global asymptotic stabilization based on partial feedback
linearization is to simply consider the control problem as a standard Lyapunov
controller design problem, but simplified by the fact that putting the system in normal
form makes part of the dynamics linear. As in most Lyapunov designs based on
mathematical rather than physical insights, the approach has a trial-and-error flavor,

Sect. 6.4 Input-Output Linearization ofSISO Systems 259
but may actually lead to satisfactory solutions. Let us study it on examples, where the
control law based on partial linearization has actually to be modified in order to
guarantee the global stability of the whole system.
The basic idea, after putting the system in normal form, is to view n as the
"input" to the internal dynamics, and \|/ as its "output". The first step is then to find a
"control law" \i = H (V) which stabilizes the internal dynamics, and an associated
o O
Lyapunov function V demonstrating that stabilizing property. This is generally
o
easier than finding a stabilizing control law for the original system, because the
internal dynamics is of lower order. The second step is then to get back to the original
global control problem, define a Lyapunov function candidate V appropriately as a
modified version of V , and choose the control input v so that V be a Lyapunov
o
function for the whole closed-loop dynamics.
Consider, for instance, the problem of stabilizing a nonlinear system whose
normal form is
y = v (6.85a)
z + 'z3+yz = 0 (6.85b)
where v is the control input and \|/ = [z z]T. Considering the internal dynamics
(6.85b), we see that if, we had, for instance, y = z2, then the internal dynamics would
be asymptotically stable (see Example 3.14). Moreover, this expression of y would
then also be compatible with the requirement that y tends to zero. This remark
suggests the following design.
Let V be a Lyapunov function indicating the stability of (6.85b) when y is
o
formally replaced by y = z2 . Based on Example 3.14, we can choose
0
V =!z2 + i-z4
° 2 4
Differentiating V using the actual dynamics (6.85) leads to
o
V = - z4- zz(y-z2)
o
Consider now the Lyapunov function candidate
V = V +-(y -z2)2
obtained by adding to V a quadratic "error" term in (y - y). We get
o 0
V = -z4 + (;y-z2)(v-3zz)

260 Feedback Linearization Chap. 6
This suggest the choice of control law
v = -y + z2 + 3zz
which yields
V = -z4 - (y-z2)2
Application of the invariant set theorem (Theorem 3.5) shows that this choice of v
brings the whole system state to zero.
Interestingly, the same procedure may also be applicable to non-minimum
phase systems. Consider, for instance, the problem of stabilizing a nonlinear system
whose normal form is
y = v (6.86a)
z + z3 - z5 + yz = 0 (6.86b)
where again v is the control input and y=[z z]T. Note that the system is non-
minimum phase, because its zero dynamics is unstable. Proceeding as before, and
noticing that the internal dynamics would be asymptotically stable if we had y = 2 z4,
we let
. 1 6
6
Differentiating V using the actual dynamics leads to
o
V = -z4 - zz(>>-2z4)
o
Considering now the Lyapunov function candidate
v= V +±(y
0
we get
V = -z4 + (j-2z4)(v-8z3z -z'z)
This suggest the choice of control law
v = ->> + 2z4 + 8z3z + zz
which yields
V = -z4 - (y-2z4)2

| Sect. 6.4  |     | Input-Output Linearization ofSISO Systems  |     |     | 261 |
| ---------- | --- | ------------------------------------------ | --- | --- | --- |
Application of the invariant set theorem shows that this choice of v brings the whole
system state to zero.
Another interesting feature of the method is that it can be applied recursively to
systems of increasing complexity, as the following example illustrates.
Example 6.15: Consider the system
y + y'i'-x  = 0
z + p -z5 +yz = 0
We first define, of course, a new input v such that
so that the system is in the simpler form
x — v
y + y^z2  = x
z + z3 -z5  +yz = 0
Consider now only the last two equations and view for a moment x as a control input. Then we
know from our earlier study of the system (6.86) that the "control law" x = x  where
0
x. = y-'z2 — y + 2z4 + 8z3z + zi
would  globally  asymptotically  stabilize the variables y and z, as can be shown  using the
Lyapunov function
|     | "  ~ 1Z  +6Z  | +  2^y |     |     |     |
| --- | ------------- | ------ | --- | --- | --- |
Consider now the Lyapunov function
2
We have
| V=V |  + (x-x            | )(k-x )  = V |   (x-x )(v-k | )   |     |
| --- | ------------------ | ------------ | ------------ | --- | --- |
|     | O o                | 0            | O + o        | o   |     |
|     | = -!4  - (y-2z4)2  | )(y-2z4      |              |     |     |
|     |                    | + (x-x o     | + v~k o      | )   |     |

262 Feedback Linearization Chap. 6
Define the control law v as
where x is computed formally from the system dynamics. This yields
g
V = -z4-(y-2z4)2-U-*)2
o
Application of the invariant set theorem then shows that this choice of v brings the whole system
state to zero. The original control input u can then be computed from v
TRACKING CONTROL
The simple pole-placement controller of Theorem 6.3 can be extended to asymptotic
tracking control tasks. Consider, for system (6.67), the problem of tracking a given
desired trajectory y^it). Let
and define the tracking error vector by
P(0 = |i(0 - \i (t) I
d
f
We then have the following result:
I
Theorem 6.4 Assume that the system (6.67) has relative degree r (defined and >
constant over the region of interest), that \i is smooth and bounded, and that the
d
solution \|/ of the equation
rf
exists, is bounded, and is uniformly asymptotically stable. Choose constants k such
t
that the polynomial (6.81) has all its roots strictly in the left-half plane. Then, by using
the control law
u = L— [ - v>i + y(r) - K-1 % - •••• - W (6-87)
d
the whole state remains bounded and the tracking error jl converges to zero
exponentially.
The proof of this theorem can be found in [Isidori, 1989]. Note that for tracking
control to be exact from time t = 0 on, using any control law, requires that

Sect. 6.4 Input-Output Linearization of SISO Systems 263
INVERSE DYNAMICS
In the following, we describe the concept of inverse dynamics, which provides an
interesting interpretation of the previous tracking control design based on feedback
linearization, and also yields insights about the tracking control of non-minimum
phase systems.
For systems described by (6.67), let us find out what the initial conditions x(0)
and control input u should be in order for the plant output to track a reference output
y(t) perfectly. To do this, let us assume that the system output y(t) is identical to the
r
reference output y(t), i.e., y(t)=y(t) , Vr>0. This implies that the time
r r
derivatives of all orders should be the same as those of the desired output, particularly,
y(k)() = y(k\) k = 0, 1,..., r-1 V t > 0 (6.88)
t t
In terms of normal coordinates, (6.88) can be written
H(0 = \i(t) = [ y(t) y(t) .... yW(t) ]T V t > 0
r r r
Thus, the control input u(t) must satisfy
y(-r\t) = a(]i V) + b{\i, \|/)«(r)
n r
that is,
J(r) - a(\i , I)/)
r
where \|f(?) is the solution of the differential equation
(6-90)
Given a reference trajectory ;y,.(0, we can obtain from (6.89) the required control input
for output y(t) to be identically equal to y{i). Note that this output depends on the
r
internal states \|/(0 and thus, in particular, on the initial y(0).
Normally, by the term "dynamics", we mean the mathematical equations for
computing the output y(t) of a system corresponding to a given input history u(f).
Equations (6.89) and (6.90), on the other hand, allow us to compute the input u{t)
corresponding to reference output history y(t). Therefore, (6.89) and (6.90) are often
r
called the inverse dynamics of the system (6.67). Formally, \|/ is the state of the
inverse dynamics, \i its input, and u its output.
r

264 Feedback Linearization Chap. 6
Note from (6.90) that a system's internal dynamics corresponds to inverting the
system for the reference output y such that
r
y/'-) = 3,/-)-£,._! 5K<-!)_ -k y
o
while its zero-dynamics corresponds to inverting the system for a zero reference
output.
TRACKING CONTROL FOR NON-MINIMUM PHASE SYSTEMS
The control law (6.87) cannot be applied to non-minimum phase nonlinear systems,
because they cannot be inverted. This is a generalization of the linear result that the
inverse of the transfer function of a non-minimum phase linear system is unstable.
Therefore, for such systems, we should not look for control laws which achieve
perfect or asymptotic convergent tracking errors. Instead, we should find controllers
which lead to small tracking errors for the desired trajectories of interest.
The control of non-minimum phase systems is a topic of active current research.
One interesting approach [Hedrick and Gopalswamy, 1989] is the output-redefinition
method, whose principle is to redefine the output function y = /ij(x) so that the
i
resulting zero-dynamics is stable. Provided that the new output function y\ is defined
in such a way that it is essentially the same as the original output function in the
frequency range of interest, exact tracking of the new output function y\ then also
implies good tracking of the original output y.
Example 6.16: Tracking control of a non-minimum phase system
To illustrate the idea of redefining the output, let us consider the tracking control of the linear
system
(6.91)
A(p)
where b is a strictly positive constant and the zeros of B(p) are all in the left-half plane (with p
o
being the Laplace variable). This system has a right half-plane zero at p = b and, therefore, perfect
tracking and exponentially convergent tracking of an arbitrary desired output yj^t) by y(t) is
impossible. To avoid the problem of unstable zero-dynamics associated with the output y, let us
consider the control of a "nominal output" y instead, with y^ defined by
i
'i
R t n\
(6.92)
with the desired output for y^ being simply yjj). Based on Theorem 6.4, one can easily find a
control input u that achieves convergent tracking of y^ .

Sect. 6.4 Input-Output Linearization of SISO Systems 265
With proper initial conditions, this control law leads to y^(J) =y{t). What is the tracking
d
error for the real output? Since one easily sees that the true output y(t) is
thus, the tracking error is proportional to the desired velocity y ,
d
and, in particular, is bounded as long as y is bounded. Interpreting the above in the frequency
d
domain, we also see that good tracking is achieved when the frequency content of y is well
d
below b.
An alternative choice of nominal output is
A(p)(\ + 9
b
wich is motivated by the approximation (1 -plb) ~ 1/(1 +p/b) for small \p\/b. With a
feedback linearization design and proper initial conditions, we have y^j) = yjj). This implies that
the true output is
Thus, the tracking error is proportional to the desired acceleration y,
d
As compared with the previous nominal output y^, this redefinition allows better tracking if
\y\ < b \y\ (or, in the frequency domain, if the frequency content of y is below b). D
d d d
Another practical approximation [Hauser, 1989] may be, when performing
input-output linearization using successive differentiations of the output, to simply
neglect the terms containing the input and keep differentiating the selected output a
number of times equal to the system order, so that there is "approximately" no zero-
dynamics. Of course, this approach can only be meaningful if the coefficients of u at
the intermediate steps are "small", i.e., if the systems are "weakly" non-minimum
phase. The approach is conceptually similar to neglecting "fast" right-half plane zeros
in linear systems (in the frequency domain, 1 — x p ~ 1/(1 + x p) if |xp| « 1 , i.e., if
the zero (1 /x) is much faster than the frequency range of interest).

266 Feedback Linearization Chap. 6
Finally, an approach to dealing with non-minimum phase systems is to modify
the plant itself. In linear systems, while poles can be placed using feedback, zeros are
intrinsic properties of the plant and the selected output, and can be changed only by
modifying the plant or the choice of output. Similarly, in nonlinear systems, the zero-
dynamics is a property of the plant, the output, and the desired trajectory. It can made
stable by changing the output, as discussed earlier. It can also, in principle, be
modified by changing the desired trajectory directly, although this is rarely practical if
the system is supposed to perform a variety of pre-specified tasks. Finally, it can be
made stable by changing the plant design itself. This may involve relocation or
addition of actuators and sensors, or modifying the physical construction of the plant
(e.g., the distribution of control surfaces on an aircraft, or the mass and stiffness
distributions in a flexible-link robot).
6.5 * Multi-Input Systems
The concepts used in the above sections for SISO systems, such as input-state
linearization, input-output linearization, zero-dynamics, and so on, can be extended to
MIMO systems.
In the MIMO case, we consider, in a neighborhood of a point x , square &
o
systems (i.e., systems with the same number of inputs and outputs) of the form *
I
x = f(x) + G(x)u y = h(x) (6.94) „
*
where x is «xl the state vector, u is the mxl control input vector (of components «,-),
y is the mxl vector of system outputs (of components >>,•), f and h are smooth vector
fields, and G is a nxtn matrix whose columns are smooth vector fields g.
(
FEEDBACK LINEARIZATION OF MIMO SYSTEMS
Input-output linearization of MIMO systems is obtained similarly to the SISO case, by
differentiating the outputs y until the inputs appear. Assume that ;,- is the smallest
i
integer such that at least one of the inputs appears in yfri\ then
with L Lf'/"1 h(x) * 0 for at least one j, in a neighborhood £2, of the point x .
g t 0
Performing the above procedure for each output >>- yields
(

Sect. 6.5 ' Multi-Input Systems 267
+ E(x)u (6.95)
Lrh (x)
f m
where the rrtxm matrix E(x) is defined obviously.
Define then Q as the intersection of the Q-. If, as assumed above, the partial
;
"relative degrees" r,- are all well defined, then Q is itself a finite neighborhood of x .
o
Furthermore, if E(x) is invertible over the region Q, then, similarly to the SISO case,
the input transformation
u = (6.96)
_ Jjmh
v
yields m equations of the simple form
(6.97)
= V:
Since the input v,- only affects the output y, (6.96) is called a decoupling control
i
law, and the invertible matrix matrix E(x) is called the decoupling matrix of the
system. The system (6.94) is then said to have relative degree (rj,...., r ) at x , and
m o
the scalar r = rj + ... + r is called the total relative degree of the system at x .
m 0
An interesting case corresponds to the total relative degree being n. In this case,
there is no internal dynamics. With the control law in the form of (6.96), we thus
obtain an input-state linearization of the original nonlinear system. With the
equivalent inputs v,- designed as in the SISO case, both stabilization and tracking can
then be achieved for the system without any worry about the stability of the internal
dynamics. Note that the necessary and sufficient conditions for input-state
linearization of multi-input nonlinear systems to be achievable are similar to and more
complex than those for single input systems [Su, et al., 1983].
The zero-dynamics of a MIMO system can be defined similarly to the SISO
case, by constraining the outputs to be zero. The notion of a minimum phase system
can also be similarly defined.

268 Feedback Linearization Chap. 6
EXTENSIONS OF THE BASIC MIMO LINEARIZATION
The above input-output linearization can be achieved only when the decoupling matrix
E is invertible in the region O. Given the straightforward procedure used to construct
E, this condition is rather restrictive (for instance, E may have a column of zeros). In
the following, we discuss two methods to generate input-output linearization when the
invertibility condition is violated, i.e., when E is singular. Both techniques have an
iterative nature, and formal conditions on the system (6.94) can be derived for them to
converge in a finite number of steps (see e.g., [Isidori, 1989], and references therein).
The first technique, called dynamic extension, involves choosing some new inputs as
the derivatives of some of the original system inputs, in a way that the corresponding
matrix E is invertible. The control system is designed based on the new set of inputs,
and the actual system inputs are then computed by integration. The second technique,
a MIMO form of system inversion, involves deriving new outputs so that the resulting
E matrix is invertible. In both cases, as in the basic version, the stability of the internal
dynamics (or, locally, of the zero-dynamics) has to be verified.
REDEFINING INPUTS: DYNAMIC EXTENSION
For notational simplicity, let us consider a system with 2 inputs and 2 outputs, and let
us assume that E(x) has rank one. This means that, without loss of generality, we can
redefine the input vector u (through linear transformations) so that E(x) has only one
non-zero column, ej = ej (x), i.e., so that equations (6.95) can be expressed in terms
of «! only,
(6.98)
y
2
(r
2
) W1 h2
Differentiating the above and replacing in the system dynamics then leads to an
equation of the form
(6.99)
If the matrix Ej is invertible, then the above equation is in the standard form of (6.95),
with «[ and uj regarded as control inputs, and Wj considered as an extra state. Input-
output linearization can then be used straightforwardly to design these inputs, i.e.,
A

Sect. 6.5 1 Multi-Input Systems 269
(6.100)
with the vector v chosen to place the poles of the resulting linear input-output
dynamics. However, the system input MJ must now be obtained from (6.100) by
integration. Thus the actual control law contains an integrator, yielding a "dynamic"
controller.
If, in (6.99), the matrix Ej is still singular, the procedure can be repeated,
amounting to adding more integrators.
REDEFINING OUTPUTS: SYSTEM INVERSION
Let us redefine the input as in the dynamic extension case, but now stop at (6.98).
Instead of going further to differentiate the left hand side, consider the variable
(where e^=[e^ e ]T)- Using (6.98) shows that the expression of z can be
x2
computed as a function of the state x only (and does not contain the input u), namely
z = e (x) L r\ h (x) - e (x) L/i h {x)
n f x x x 2
Hence, by differentiating z, we obtain an equation of the form
z = j (x)+y(x)u+j (x)u
o i l 2 2
If the matrix
«ll(x) 0
E (x) =
2
y,(x) y (x)
2
is invertible, we can regard>>] and z as outputs, u\ and u as inputs, and use the control
2
law
v~Lr\h
x x x
to achieve input-output linearization. This leads to

270 Feedback Linearization Chap. 6
The new inputs vj and v can be easily designed to regulate y and z. If the matrix E is
2 2
singular, we can repeat this procedure to create new outputs.
6.6 Summary
Feedback linearization is based on the idea of transforming nonlinear dynamics into a
linear form by using state feedback, with input-state linearization corresponding to
complete linearization and input-output linearization to partial linearization. The
method can be used for both stabilization and tracking control problems, single-input
and multiple-input systems, and has been successfully applied to a number of practical
nonlinear control problems, both as an system analysis tool and as a controller design
tool.
The method also has a number of important limitations:
1. it cannot be used for all nonlinear systems
2. the full state has to be measured
3. no robustness is guaranteed in the presence of parameter uncertainty or
unmodeled dynamics
The applicability of input-state linearization is quantified by a set of somewhat
stringent conditions, while input-output feedback linearization cannot be applied when
the relative degree is not defined and lacks systematic global results. Furthermore,
analytically solving the partial differential equations defining input-state linearizing
transformations is generally not systematic.
The second problem is due to the difficulty of finding convergent observers for
nonlinear systems and, when an observer can be found, the lack of a general
separation principle (analogous to that in linear systems) which guarantees that the
straightforward combination of a stable state feedback controller and a stable observer
will guarantee the stability of the closed-loop system.
The third problem is due to the fact that the exact model of the nonlinear system
is not available in performing feedback linearization. The sensitivity to modeling
errors may be particularly severe when the linearizing transformation is poorly
conditioned.

Sect. 6.8 Exercises 111
Active research is being performed to overcome the above drawbacks. For the
first problem, research is aimed at extending feedback linearization to non-minimum
phase or weakly non-minimum phase systems. For the second problem, many efforts
are being made to construct observers for nonlinear systems and to extend the
separation principle to nonlinear systems. For the third problem, robust and adaptive
control are being introduced to provide feedback linearizable systems with robustness
to parametric uncertainties. Chapters 7 and 8 provide some further discussions of
robust and adaptive techniques for feedback linearizable systems.
6.7 Notes and References
Extensive theoretical developments of the material in this chapter can be found in [Isidori, 1989],
from which Examples 6.12 and 6.14 are adapted, and in references therein. The writing of this
chapter was also influenced by the clear presentation in [Spong and Vidyasagar, 1989], and by the
clear and concise summary of input-output linearization in [Hauser, 1989]. The reader may also
consult the recent book [Nijmeijer and Van der Schaft, 1990], which contains many interesting
examples. A survey of aircraft control applications is contained in [Hedrick and Gopalswamy, 1989].
The discussion on global asymptotic stabilization of section 6.4 is inspired by the recent
works of [Kokotovic and Sussmann, 1989; Praly, et al., 1989]. See [Sastry and Kokotovic, 1988;
Sussmann, 1990] for further discussions of the relation between stability of the zero-dynamics and
overall system stability.
While nonlinear observer design is far from being a mature subject, a number of important
theoretical results have been derived [Hermann and Krener, 1977; Vidyasagar, 1980; Krener and
Respondek, 1985]. See, e.g., [Misawa and Hedrick, 1989] for a recent review.
The basic idea of "undoing" the nonlinear dynamics is quite old, and can be traced back at
least to the early robotics literature [Freund, 1973; Takase, 1975]. The basis of input-state
transformations was suggested by [Brockett, 1978] and fully derived in [Jacubczyk and Respondek,
1980; Hunt, et al., 1983]. Many results in input-output linearization are extensions of [Krener, et al.,
1983]. The basic principles of system inversion are due to [Hirschorn, 1981; Singh 1982], and extend
to nonlinear systems the classic linear control algorithm of [Silverman, 1969]. A detailed historical
perspective of the field can be found in [Isidori, 1989].
6.8 Exercises
6.1 Simulate the nonlinear controller design of section 6.1.1 for a spherical tank of radius 0.5
meter (m) and outlet opening radius 0.1 m. Let the initial height be 0.1 m and the desired final
height be 0.6 m.

272 Feedback Linearization Chap. 6
6.2 Show that the internal dynamics of the system
3
JC> + u
is unstable.
6.3 For the system
design a controller to track an arbitrary desired trajectory x (t) . Assume that the model is very
dl
accurate, that the state [x, x]T is measured, and that x (t), x (t), x (t) are all known. Write
2 dl dl dl
the full expression of the controller, as a function of the measured state [x, X]T • Check your
2
design in simple simulations.
6.4 Consider the system
where the variable x is to be controlled to zero. Note that the zero-dynamics is exponentially stable.
x
Show that, assuming that x(0) = 0, the stability of the internal dynamics depends on the initial
2
condition in X[ and on how fast u drives Xj to zero. In particular, if these are such that x > e ' ~ 2/'11,
i
then x > tan t and therefore tends to infinity in finite time.
2
6.5 K different interpretation can be given to the zero-dynamics of linear systems. Indeed, note the
frequency-domain equation (6.35) can be written
y Ab+b P }u
Thus, if we assume that the roots of the denominator polynomial are strictly in the left half-plane,
then there are certain control inputs which, after stable transients, do not affect the system output y.
These control inputs verify
J? u = 0 (6.101)
h
If the system is minimum-phase, these particular inputs tend to zero as / —> °° . But if the system is
non-minimum phase, then there are certain diverging control inputs which do not affect the system
output (after stable transients). This reflects a "helplessness" of the system input at certain

Sect. 6.8 Exercises 273
frequencies.
Show that equation (6.101) is of the same form as that defining the zero-dynamics of the
system.
For the aircraft of Example 6.5, find the control inputs which, after stable transients, do not
affect the output. Illustrate your result in simulation.
Can this interpretation of the zero-dynamics be extended to nonlinear systems?
6.6 Show the bilinearity and skew-commutativity of Lie brackets.
6.7 Check the input-state linearizability of the system
r
v
X2
2
d x
d7
xi
Can
23 =
serve as linearizing states? (Adapted from [Nijmeijer and Van der Schaft, 1990].)
6.8 Globally stabilize the nonlinear system
z + z3 -z7 + yz2 = 0
where u is the control input. Is the system minimum-phase?
6.9 Put in normal form the nonlinear system
5> + _yz2ln (z4 + 1) = u
z + z5 + z3 + yz2 = 5 u
where u is the control input. Can the system be locally/globally stabilized? Is the system minimum-
phase?
6.10 Consider the system of Figure 6.9, which represents a link driven by an electric motor
through a rigid mechanism, in the vertical plane. The (stable) motor electrical dynamics is assumed
to be slow, so that it cannot be neglected.
Using a procedure similar to that of Example 6.10, perform input-state linearization and

274 Feedback Linearization Chap. 6
Motor
Voltage input u
Figure 6.9 : A link driven by a slow motor
design a controller for this system in the following cases (where X is simply a scaling factor between
units):
• The motor dynamics is linear and first-order:
t + XjXx^Xu
• The motor dynamics is linear and second-order:
x + X l x + ^1,T = X«
• The motor dynamics is nonlinear and second-order:
What variables do you assume to be available for measurement?
In the above calculations, the back-emf of the motor has been neglected. It actually
introduces a damping torque / a q . Assuming that the motor dynamics is linear and first-order
0
(which is often a reasonable model, simply corresponding to an equivalent "RL" circuit), perform
input-state linearization and design a controller for the system. What variables do you assume to be
available for measurement?
6.11 Globally stabilize the nonlinear system
y + z_y4 = w5
z + (y-l)z2 + z5 = 0
where u is the control input. Is the system minimum-phase?
6.12 Consider the nonlinear system

Sect. 6.8 Exercises 275
y + z^ey'2 = u
z-(y + y3)('z4+ l) + z5+yz = 0
where u is the control input. Can the system be locally/globally stabilized?
6.13 Globally stabilize the nonlinear system
y+ y^e1 = M3
z - i4 + z5 = y u2z2
where u is the control input. Is the system minimum-phase?
6.14 Globally stabilize the nonlinear system
x + x2y = (x z2 + 4) u
y + y4eyz + x = 0
z + 'zi-z1 +yz2 = 0
where u is the control input. Is the system minimum-phase?
6.15 Discuss the stabilization of the MIMO system
x + xy2 = «j + 2«
2
y + x3 = 2 «| + 4«
2
using dynamic extension and inversion techniques.
Same question for the system
x + xe>' = Mj + 2 «
2
5> + y2 = 2 «[ + 4 «2
6.16 Consider again the system of Exercise 6.10 (including motor back-emf) but assume now that
the "link" actually consists of the three blades of an underwater propeller, so that the gravitational
torque - MgLsin q is replaced by the hydrodynamic torque
Xthrust = -/«, 4r |4-|
(where the notation T comes from the fact that the thrust generated by the propeller is
lhrml
proportional to i, , cf. Exercise 4.4). Assuming that the motor dynamics is linear and first-order,
hrusl
perform input-state linearization and design a controller for the system. Indicate what variables you
assume to be available for measurement.

Chapter 7
Sliding Control
In this chapter, we consider again the control of nonlinear systems of the general form
studied in chapter 6, but we now allow the models to be imprecise. Model
imprecision may come from actual uncertainty about the plant (e.g., unknown plant
parameters), or from the purposeful choice of a simplified representation of the
system's dynamics (e.g., modeling friction as linear, or neglecting structural modes in
a reasonably rigid mechanical system). From a control point of view, modeling
inaccuracies can be classified into two major kinds:
• structured (or parametric) uncertainties
• unstructured uncertainties (or unmodeled dynamics)
The first kind corresponds to inaccuracies on the terms actually included in the model,
while the second kind corresponds to inaccuracies on (i.e., underestimation of) the
system order.
As discussed earlier, modeling inaccuracies can have strong adverse effects on
nonlinear control systems. Therefore, any practical design must address them
explicitly. Two major and complementary approaches to dealing with model
uncertainty are robust control, which we discuss in this chapter, and adaptive control,
which is the subject of chapter 8. The typical structure of a robust controller is
composed of a nominal part, similar to a feedback linearizing or inverse control law,
and of additional terms aimed at dealing with model uncertainty. The structure of an
adaptive controller is similar, but in addition the model is actually updated during
276

Sect. 7.1 Sliding Surfaces 277
operation, based on the measured performance.
A simple approach to robust control, and the main topic of this chapter, is the
so-called sliding control methodology. Intuitively, it is based on the remark that it is
much easier to control lst-order systems (i.e., systems described by lst-order
differential equations), be they nonlinear or uncertain, than it is to control general
/ith-order systems (i.e., systems described by «th-order differential equations).
Accordingly, a notational simplification is introduced, which, in effect, allows
nth-order problems to be replaced by equivalent lst-order problems. It is then easy to
show that, for the transformed problems, "perfect" performance can in principle be
achieved in the presence of arbitrary parameter inaccuracies. Such performance,
however, is obtained at the price of extremely high control activity. This is typically at
odds with the other source of modeling uncertainty, namely the presence of neglected
dynamics, which the high control activity may excite. This leads us to a modification
of the control laws which, given the admissible control activity, is aimed at achieving
an effective trade-off between tracking performance and parametric uncertainty.
Furthermore, in some specific applications, particularly those involving the control of
electric motors, the unmodified control laws can be used directly.
For the class of systems to which it applies, sliding controller design provides a
systematic approach to the problem of maintaining stability and consistent
performance in the face of modeling imprecisions. Furthermore, by allowing the
trade-offs between modeling and performance to be quantified in a simple fashion, it
can illuminate the whole design process. Sliding control has been successfully applied
to robot manipulators, underwater vehicles, automotive transmissions and engines,
high-performance electric motors, and power systems.
The concepts are presented first for systems with a single control input, which
allows us to develop intuition about the basic aspects of nonlinear controller design.
Specifically, section 7.1 introduces the main concepts and notations of sliding control,
and illustrates the associated basic controller designs. Section 7.2 describes
modifications of the control laws aimed at eliminating excessive control activity.
Section 7.3 discusses the choice of controller design parameters. Section 7.4 then
studies generalizations to multi-input systems.
7.1 Sliding Surfaces
Consider the single-input dynamic system
x(") =/(x) + b(x) u (7.1)

278 Sliding Control Chap. 7
where the scalar x is the output of interest (for instance, the position of a mechanical
system), the scalar u is the control input (for instance, a motor torque), and
x = [JC Jc ... x(n~^]T is the state vector. In equation (7.1) the function/(x) (in
general nonlinear) is not exactly known, but the extent of the imprecision on /(x) is <
upper bounded by a known continuous function ofx ; similarly, the control gain b(x) is )
not exactly known, but is of known sign and is bounded by known, continuous
functions of x. For instance, typically, the inertia of a mechanical system is only -s
known to a certain accuracy, and friction models only describe part of the actual
friction forces. The control problem is to get the state x to track a specific time-
varying state x = [Xrf k • • • x^"^]^ in the presence of model imprecision on
rf d
f(x) and b(x).
For the tracking task to be achievable using a finite control u, the initial desired
state x^(0) must be such that
x (0) = x(0) (7.2)
d
In a second-order system, for instance, position or velocity cannot "jump", so that any
desired trajectory feasible from time t = 0 necessarily starts with the same position and
velocity as those of the plant. Otherwise, tracking can only be achieved after a
transient.
7.1.1 A Notational Simplification
Let x=x-x be the tracking error in the variablex, and let
d
be the tracking error vector. Furthermore, let us define a time-varying surface Sit) in
the state-space R(") by the scalar equation s(x\t) = 0 , where ?
'i
n-\
x (7.3) i
and A. is a strictly positive constant, whose choice we shall interpret later. For
instance, if n = 2 ,
s - x + Xx
i.e., s is simply a weighted sum of the position error and the velocity error; if n = 3 , £
I
s = x + 2Xx + X^x

Sect. 7.1 Sliding Surfaces 279
Given initial condition (7.2), the problem of tracking x = x is equivalent to that of
d
remaining on the surface S(t)for all t>0 ; indeed s = 0 represents a linear differential
equation whose unique solution is x = 0, given initial conditions (7.2). Thus, the
problem of tracking the n-dimensional vector x^ can be reduced to that of keeping the
scalar quantity s at zero.
More precisely, the problem of tracking the ^-dimensional vector x (i.e., the
d
original «th-order tracking problem in x) can in effect be replaced by a lst-order
stabilization problem in .y. Indeed, since from (7.3) the expression of s contains
J(«-1), we only need to differentiate s once for the input u to appear.
Furthermore, bounds on s can be directly translated into bounds on the tracking
error vector x, and therefore the scalar s represents a true measure of tracking
performance. Specifically, assuming that x(0) = 0 (the effect of non-zero initial
conditions in x can be added separately), we have
V t > 0 , | s(t) | < <t> => V t > 0, 13t«(r) | < (2X)' e (7.4)
i = 0,. .., n-\
1 1
P + X p + X p + X
n -1 blocks
Figure 7.1.a : Computing bounds on x
where e = O / X"~l . Indeed, by definition (7.3), the tracking error x is obtained from
s through a sequence of first-order lowpass filters (Figure 7.1.a, where p = (d/dt) is the
Laplace operator). Let y be the output of the first filter. We have
l
(t)= ['e-
y[
^ o
From \s\ <O we thus get
\y (t)\ < O
x
We can apply the same reasoning to the second filter, and so on, all the way to
J _j = x . We then get
n

280 Sliding Control Chap. 7
| x | < = e
Similarly, JC^ can be thought of as obtained through the sequence of Figure 7.1.b.
From the previous result, one has | Zj | < <E>A."~'~' , where z is the output of the
l
in - i - l)th filter. Furthermore, noting that
p _p + X-X_ j _ X
p+X p + X p + X
z
1 V -0)
P + x p+X p+X
J V.
n - i -1 blocks i blocks
Figure 7.1.b : Computing bounds on
one sees that the sequence of Figure 7.1.b implies that
i.e., bounds (7.4). Finally, in the case that x(0)^0, bounds (7.4) are obtained
asymptotically, i.e., within a short time-constant (n - 1)/A,.
Thus, we have in effect replaced an «th-order tracking problem by a lst-order
stabilization problem, and have quantified with (7.4) the corresponding
transformations of performance measures.
The simplified, lst-order problem of keeping the scalar s at zero can now be
achieved by choosing the control law u of (7.1) such that outside of Sit)
(7.5)
2 dt
where r\ is a strictly positive constant. Essentially, (7.5) states that the squared
"distance" to the surface, as measured by s2 , decreases along all system trajectories.
Thus, it constrains trajectories to point towards the surface 5(0, as illustrated in Figure
7.2. In particular, once on the surface, the system trajectories remain on the surface.
In other words, satisfying condition (7.5), or sliding condition, makes the surface an
invariant set. Furthermore, as we shall see, (7.5) also implies that some disturbances
or dynamic uncertainties can be tolerated while still keeping the surface an invariant
i

Sect. 7.1 Sliding Surfaces 281
set. Graphically, this corresponds to the fact that in Figure 7.2 the trajectories off the
surface can "move" while still pointing towards the surface. S(t) verifying (7.5) is
referred to as a sliding surface, and the system's behavior once on the surface is called
sliding regime or sliding mode.
Figure 7.2 : The sliding condition
The other interesting aspect of the invariant set 5(0 is that once on it, the system
trajectories are defined by the equation of the set itself, namely
n-\
x = 0
dt
In other words, the surface S(t) is both a place and a dynamics. This fact is simply the
geometric interpretation of our earlier remark that definition (7.3) allows us, in effect,
to replace an «th-order problem by a lst-order one.
Finally, satisfying (7.5) guarantees that if condition (7.2) is not exactly verified,
i.e., if x(r=0) is actually off x^t=0), the surface S(t) will nonetheless be reached in a
finite time smaller than \s(t=0)\/r\. Indeed, assume for instance that s(t=O) > 0, and let
'reach '3e tne ^me required to hit the surface s = 0. Integrating (7.5) between
/ = 0 and t = t leads to
reach
0-s(t=0) = s(t=t ) - v(f=O)<-Ti(/ -O)
Kach l reach

282 Sliding Control Chap. 7
which implies that
'reach < s(f=O)/T\
One would obtain a similar result starting with s{t=0) < 0 , and thus
r < |s(r=O)|/Ti *
reach
Furthermore, definition (7.3) implies that once on the surface, the tracking error tends
exponentially to zero, with a time constant (n - 1)A, (from the sequence of (n - 1)
filters of time constants equal to I/A,).
The typical system behavior implied by satisfying sliding condition (7.5) is ''
illustrated in Figure 7.3 for n = 2. The sliding surface is a line in the phase plane, of
slope - X and containing the (time-varying) point \ = [x x ]r. Starting from any .
d d rf
initial condition, the state trajectory reaches the time-varying surface in a finite time ijk
smaller than |s(?=0)|/r|, and then slides along the surface towards x exponentially,
d
with a time-constant equal to Ifk.
finite-time sliding mode
reaching phase exponential convergence
Figure 7.3 : Graphical interpretation of equations (7.3) and (7.5) (n = 2)
In summary, the idea behind equations (7.3) and (7.5) is to pick-up a well-
behaved function of the tracking error, s, according to (7.3), and then select the
feedback control law u in (7.1) such that s2 remains a Lyapunov-like function of the
closed-loop system, despite the presence of model imprecision and of disturbances.
The controller design procedure then consists of two steps. First, as will be illustrated
in section 7.1.3, a feedback control law u is selected so as to verify sliding condition
1
(7.5). However, in order to account for the presence of modeling imprecision and of

Sect. 7.1 Sliding Surfaces 283
disturbances, the control law has to be discontinuous across S(t). Since the
implementation of the associated control switchings is necessarily imperfect (for
instance, in practice switching is not instantaneous, and the value of s is not known
with infinite precision), this leads to chattering (Figure 7.4). Now (with a few
important exceptions that we shall discuss in section 7.1.4), chattering is undesirable
in practice, since it involves high control activity and further may excite high-
frequency dynamics neglected in the course of modeling (such as unmodeled
structural modes, neglected time-delays, and so on). Thus, in a second step detailed in
section 7.2, the discontinuous control law u is suitably smoothed to achieve an optimal
trade-off between control bandwidth and tracking precision: while the first step
accounts for parametric uncertainty, the second step achieves robustness to high-
frequency unmodeled dynamics.
chattering
Figure 7.4 : Chattering as a result of imperfect control switchings
7.1.2 * Filippov's Construction of the Equivalent Dynamics
The system's motion on the sliding surface can be given an interesting geometric
interpretation, as an "average" of the system's dynamics on both sides of the surface.
The dynamics while in sliding mode can be written as
5 = 0 (7.6)
By solving the above equation formally for the control input, we obtain an expression
for u called the equivalent control, u , , which can be interpreted as the continuous
e(

284 Sliding Control Chap. 7
control law that would maintain s = 0 if the dynamics were exactly known. For
instance, for a system of the form
x=f+ u
we have
and the system dynamics while in sliding mode is, of course,
Geometrically, the equivalent control can be constructed as
u = a u + (1 - a) u_ (7.7)
eq +
i.e., as a convex combination of the values of u on both sides of the surface S(t). The
value of a can again be obtained formally from (7.6), which corresponds to requiring
that the system trajectories be tangent to the surface. This intuitive construction is
summarized in Figure 7.5, where f = [ x f + u ]T , and similarly
+ +
f_ = [x f + u_]T and f = [x f + u ]. Its formal justification was derived in
eq eq
the early 1960's by the Russian mathematician A. F. Filippov.
s<0
s>0
Figure 7.5 : Filippov's construction of the equivalent dynamics in sliding mode
Recalling that the sliding motion on the surface corresponds to a limiting
behavior as control switchings occur infinitely fast, the formal solution a of (7.6) and
(7.7) can be interpreted as the average "residence time" of the trajectory on the side
s>0.
JL

Sect. 7.1 Sliding Surfaces 285
7.1.3 Perfect Performance - At a Price
Given the bounds on uncertainties on /(x) and b(x), constructing a control law to
verify the sliding condition (7.5) is straightforward, as we now illustrate.
A BASIC EXAMPLE
Consider the second-order system
x=f+u (7.8)
where u is the control input, x is the (scalar) output of interest, and the dynamics /
(possibly nonlinear or time-varying) is not exactly known, but estimated as/. The
estimation error on/is assumed to be bounded by some known function F — F(x,x):
\f~f\<F (7.9)
For instance, given the system
x + a(i) x2 cos 3x = u (7.10)
where a(t) is unknown but verifies
1 <a(t)<2
one has
/ = -1.5x2cos3x F = 0.5 x2 | cos 3x |
In order to have the system track x(t) s xj^t), we define a sliding surface s = 0
according to (7.3), namely:
s = (— + X)x = i + Xx (7.11)
\dt /
We then have:
s = x-x +Xx=f+u-x^ + Xx (7.12)
{/
The best approximation u of a continuous control law that would achieve s = 0 is thus
u = -f +x -l3c (7.13)
d
Note that in terms of the discussion of section 7.1.2, u can be interpreted as our best
estimate of the equivalent control. In order to satisfy sliding condition (7.5) despite
uncertainty on the dynamics /, we add to u a term discontinuous across the surface

286 Sliding Control Chap. 7
5 = 0:
u = u-k&gn(s) (7.14)
where sgn is the sign function:
sgn(s) = + 1 if i > 0
sgn(s) = - 1 if s < 0
By choosing k = k(x,x) in (7.14) to be large enough, we can now guarantee that (7.5)
is verified. Indeed, we have from (7.12)-(7.14)
s = (f-f)s - k\s\
dt
so that, letting
k = F + r\ (7.15)
we get from (7.9)
as desired. Note from (7.15) that the control discontinuity k across the surface s = 0
A
increases with the extent of parametric uncertainty. Also, note that/ and F need not
depend only on x or x . They may more generally be functions of any measured
variables external to system (7.8), and may also depend explicitly on time.
We can see on this basic example one of the main advantages of transforming
the original tracking control problem into a simple first-order stabilization problem in
s. Namely, the intuitive feedback control strategy "if the error is negative, push hard
enough in the positive direction (and conversely)" actually works for first-order
systems (recall also Example 3.9). It does not for higher-order systems.
INTEGRAL CONTROL
A similar result would be obtained by using integral control, i.e., formally letting
([' x(r) dr) be the variable of interest. The system (7.8) is now third-order relative to
this variable, and (7.3) gives:
We then obtain, instead of (7.13),

Sect. 7.1 Sliding Surfaces 287
u = —f + xj — 2 A, x — 7? x
with (7.14) and (7.15) formally unchanged. Note that f'xdr can be replaced by
f' x dr, i.e., the integral can be defined to within a constant. The constant can be
chosen to obtain s(t=0) = 0 regardless of x^(0), by letting
: = 2 + 2Xx + X2j'x dr - 3?(0)
GAIN MARGINS
Assume now that (7.8) is replaced by
x=f+bu (7.16)
where the (possibly time-varying or state-dependent) control gain b is unknown but of
known bounds (themselves possibly time-varying or state-dependent)
0 < b <b<b (7.17)
min max
Since the control input enters multiplicatively in the dynamics, it is natural to choose
A
our estimate b of gain b as the geometric mean of the above bounds:
b = (b b )l/2
mjn max
Bounds (7.17) can then be written in the form
A
P"'< £ <p (7.18)
b
where
Since the control law will be designed to be robust to the bounded multiplicative
uncertainty (7.18), we shall call (3 the gain margin of our design, by analogy to the
terminology used in linear control. Note that (3 may be time-varying or state-
dependent, and that we also have
Also note that the uncertainty on b may come directly in the form (7.18), e.g., if the
control action u itself is generated by a linear dynamic system.

| 288  | Sliding Control  |     |     | Chap. 7 |
| ---- | ---------------- | --- | --- | ------- |
With 5 and u defined as before, one can then easily show that the control law
u = b~l[u-ksgn(s)]
(7.19)
with
|     | k > P(F + iD + (p-l)|«|  |     |     | (7.20) |
| --- | ------------------------ | --- | --- | ------ |
satisfies the sliding condition.  Indeed, using (7.19) in the expression of s leads to
|     | s = (f- bb~l /) + (1 - btrx){-x |     | + Ai) - bb~lk sgn(s) |     |
| --- | ------------------------------- | --- | -------------------- | --- |
d
so that k must verify
|     | k > | bb-lf-f  | + (bb-{ - l)(-x |  + Xk) | + r^"1 |     |
| --- | -------------- | --------------- | --------------- | --- |
d
|                  | A  A           | A   |                              |     |
| ---------------- | -------------- | --- | ---------------------------- | --- |
| Since/=/ + (/-/  | ), where \f-f  |     | I < F, this in turn leads to |     |
k > bb~x F + r\bb~: + \bb~l -l\-\f-x  +
d
b
and thus to (7.20).  Note that the control discontinuity has been increased in order to
account for the uncertainty on the control gain b.
Example 7.1: A simplified model of the motion of an underwater vehicle can be written
|     | mx  + cx{x\  | = u  |     | (7.21) |
| --- | ------------ | ---- | --- | ------ |
where x defines position, w is the control input (the force provided by a propeller), m is the mass
of the vehicle (including the so-called added-mass, associated with motion in a fluid), and c is a
drag coefficient.  In practice, m and c are not known accurately, because they only describe
loosely the complex hydrodynamic effects that govern the vehicle's motion.
Defining s as s = x + Xx , computing i explicitly, and proceeding as before, a control law
satisfying the sliding condition can be derived as
|     | u = m( Xj -Xx)  | + cx\x\-k  | sgn i  | (7.22) |
| --- | --------------- | ---------- | ------ | ------ |
with
|     | k = (F+$r\) + m{$-l)\x |     | -lJc\  | (7.23) |
| --- | ---------------------- | --- | ------ | ------ |
d
Note that expression  (7.23) is "tighter" than the general  form  (7.20), reflecting the simpler
structure of parametric uncertainty:  intuitively, u can compensate for c x | x | directly, regardless
of the uncertainty on m. In general, for a given problem, it is a good idea to quickly rederive a
control law satisfying the sliding condition, rather than apply some pre-packed formula.  D
It is useful to pause at this point, and wonder whether a different control action, i

Sect. 7.1 Sliding Surfaces 289
obtained by some other method, could achieve the same task. The answer to this
question is that, given a feasible desired trajectory, there is a unique smooth control
time-function that tracks it exactly, namely
[x -f(x )] (7.24)
d d
Thus, whatever the method, the resulting control time-function will be the same, and
therefore using this particular approach simply provides a straightforward way of
arriving at that time-function. Because we require perfect tracking to be achieved even
in the presence of parametric uncertainty, this time-function is constructed through a
process of averaging infinitely fast discontinuous switchings, into what we called in
section 7.1.2 the equivalent control, which is precisely (7.24).
Control laws which satisfy sliding condition (7.5), and thus lead to "perfect"
tracking in the face of model uncertainty, are discontinuous across the surface S(t),
thus leading in practice to control chattering. In general, chattering is highly
undesirable, since it involves extremely high control activity, and furthermore may
excite high-frequency dynamics neglected in the course of modeling. In section 7.2,
we shall show how to modify the switching control laws derived above so as to
eliminate chattering.
In specific (if exceptional) applications, however, control chattering is
acceptable, and the pure switching control laws derived above can yield extremely
high performance. We now discuss such direct applications of the previous
development.
7.1.4 Direct Implementations of Switching Control Laws
The main direct applications of the above switching controllers include the control of
electric motors, and the use of artificial dither to reduce stiction effects.
SWITCHING CONTROL IN PLACE OF PULSE-WIDTH MODULATION
In pulse-width modulated electric motors, the control input u is an electrical voltage
rather than a mechanical force or acceleration. Control chattering may then be
acceptable provided it is beyond the frequency range of the relevant unmodeled
dynamics. Provided that the necessary computations (including both control law and
state estimation) can be handled on-line at a high enough rate, or implemented using
analog circuitry, pure sliding mode control using switched control laws can be a viable
and extremely high-performance option.

290 Sliding Control Chap. 7
SWITCHING CONTROL WITH LINEAR OBSERVER
The difficulty in obtaining meaningful state measurements at very high sampling rates
can be turned around by using state observers. For linear systems, the design of such
observers is well known and systematic. The principle of the approach to designing a
switching controller using an observer is then very simple. Instead of tracking the
surface 5 = 0, the system is made to track the surface s = 0, where s is obtained by
e e
replacing the state x by its estimate x in the expression of s. This can be achieved by
e
computing a dynamic compensation term u based on the available state estimates,
e
and using switching terms of the form - k(x) sgn(s), where k(x) is chosen large
e e e
enough to compensate both for parametric inaccuracies and for observer inaccuracies.
This yields s -> 0 (as t —> °°). Then, if the observer has been properly designed so
e
that it converges despite modeling uncertainties (which, again, is easy to achieve in
the linear case), we also have s —> s . Therefore, s —» 0, and the actual state
e
converges towards the desired state. Furthermore, sliding mode and its robust
properties are maintained on the surface s = 0, which tends towards the desired
e
sliding surface as the observer converges.
SWITCHING CONTROL IN PLACE OF DITHER
When uncertainty consists of effects small in magnitude but difficult to model, such as
stiction or actuator ripple, switching in s may be advantageously used in place of a
more standard "dither" signal. Ideally, the frequency of the switching should be
chosen well beyond that of significant structural vibration modes (in mechanical
systems), while remaining below the actuators' bandwidth. This assumes again that
meaningful state estimates can be provided at the selected switching frequency. Such
an approach can particularly improve the quality of low-speed behavior, which
otherwise is extremely sensitive to friction.
The examples above represent the few specific applications where chattering
can be tolerated and actually exploited. In the general case, however, the question is
how to derive control laws that maintain the system close to the surface 5 = 0 while
avoiding chattering altogether. This is the subject of the next section.
7.2 Continuous Approximations of Switching Control Laws
In general, chattering must be eliminated for the controller to perform properly. This
can be achieved by smoothing out the control discontinuity in a thin boundary layer
neighboring the switching surface
B{t) = (x, Kx;0l<<&) $>0 (7.25)
1

Sect. 7.2 Continuous Approximations of Switching Control Laws 291
s = 0
Figure 7.6.a : The boundary layer
where O is the boundary layer thickness, and e = <$>ftin~l is the boundary layer width,
as Figure 7.6.a illustrates for the case n = 2. In other words, outside of B(t), we choose
control law u as before {i.e., satisfying sliding condition (7.5)), which guarantees that
the boundary layer is attractive, hence invariant: all trajectories starting inside B(t=0)
remain inside B(t) for all r > 0 ; and we then interpolate u inside B(t) - for instance,
replacing in the expression of u the term sgn(j) by s/<3>, inside B(t), as illustrated in
Figure 7.6.b.
Given the results of section 7.1.1, this leads to tracking to within a guaranteed
precision e (rather than "perfect" tracking), and more generally guarantees that for all
trajectories starting inside B(t=0)
V t > 0 , | < (2X)' e i = 0, ... , n -l
Example 7.2: Consider again the system (7.10), and assume that the desired trajectory is
x= sin(;ir/2).
d
Figure 7.7 shows the tracking error and control law using the switched control law (with
A 20 01)
u = u~k sgn(.s)
= 1.5 x2 cos 3x + x - 20 1 - ( 0.5 x2 | cos 3x | + 0.1) sgn[ j + 20 x]
d

292 Sliding Control Chap. 7
Figure 7.6.b : Control interpolation in the boundary layer
at a sampling rate of 1 kHz. The actual value of a(t) used in the simulations is a(f) = |sinf| + 1
(which verifies the assumed bound on a(t)). We see that tracking performance is excellent, but is
obtained at the price of high control chattering.
Assume now that we interpolate the above control input in a thin boundary layer of thickness
0.1
u = u - k sat(s/<t>)
= 1.5 x2 cos 3x + x- 20 i - (0.5 x2 | cos 3x | + 0.1) sat[(j? + 20 x)/0.1 ]
d
As shown in Figure 7.8, the tracking perfomiance, while not as "perfect" as above, is still very
good, and is now achieved using a smooth control law. Note that the bounds on tracking error are
consistent with (7.25). D
6.0
4.0
2.0
0.0
-2.0
-4.0
0.0 1.0 2.0 3.0 4.0 3.0 4.0
time(sec) time(sec)
Figure 7.7 : Switched control input and resulting tracking performance
i

Sect. 7.2 Continuous Approximations of Switching Control Laws 293
6.0 4e-03
4.0
2.0
0.0
-2.0
-4.0 -4e-03
0.0 1.0 2.0 3.0 4.0 0.0 1.0 2.0 3.0 4.0
time(sec) time(sec)
Figure 7.8 : Smooth control input and resulting tracking performance
The intuitive understanding of the effect of control interpolation in a boundary
layer can be carried on further, and guide the selection of the design parameters A, and
<I>. As we now show, the smoothing of control discontinuity inside B(t) essentially
assigns a lowpass filter structure to the local dynamics of the variable s, thus
eliminating chattering. Recognizing this filter-like structure then allows us, in
essence, to tune up the control law so as to achieve a trade-off between tracking
precision and robustness to unmodeled dynamics. Boundary layer thickness <B can be
made time-varying, and can be monitored so as to well exploit the control "bandwidth"
available. The development is first detailed for the case p = 1 (no gain margin), and
then generalized.
A
Consider again the system (7.1) with b = b=l. In order to maintain
attractiveness of the boundary layer now that <P is allowed to vary with time, we must
actually modify condition (7.5). Indeed, we now need to guarantee that the distance to
the boundary layer always decreases
_d
=> _ [J- < -r\
df'
S<-<P => —\_S- {-<!>)[ > T\
dt
Thus, instead of simply requiring that (7.5) be satisfied outside the boundary layer, we
now require that (combining the above equations)
=> I£J2<(O- (7.26)
2 dt
The additional term O |$| in (7.26) reflects the fact that the boundary layer attraction
condition is more stringent during boundary layer contraction (O < 0) and less
stringent during boundary layer expansion (<t> > 0). In order to satisfy (7.26), the

294 Sliding Control Chap. 7
quantity -<D is added to control discontinuity gain fc(x) , i.e., in our smoothed
implementation the term k(\) sgn(s) obtained from switched control law u is actually
— f 1
replaced by k (x) sat(s/<t>), where
k (x) = fc(x) - <t> (7.27)
and sat is the saturation function, which can be formally defined as
sat(>>) = y if\y\<l
sat(y) = sgn(>>) otherwise
Accordingly, control law u becomes:
u - u - k (x) sat(s/<l>)
Let us now consider the system trajectories inside the boundary layer, where
they lie by construction: they can be expressed directly in terms of the variable s as
S = -F(x) ^ - A/(x) (7.28)
AA
where A/=/ -/. Now since k and A/are continuous in x, we can exploit (7.4) to
rewrite (7.28) in the form
s = - ~k(x ) ^ + ( - A/(x ) + O(e)) (7.29)
d d
We see from (7.29) that the variable s (which is a measure of the algebraic distance to
the surface S(t)) can be viewed as the output of a first-order filter, whose dynamics
only depends on the desired state xJJ), and whose inputs are, to the first order,
"perturbations," i.e., uncertainty A/(x^). Thus, chattering can indeed be eliminated, as
long as high-frequency unmodeled dynamics are not excited. Conceptually, the
structure of the closed-loop error dynamics can be summarized by Figure 7.9:
perturbations are filtered according to (7.29) to give s, which in turn provides tracking
error x by further lowpass filtering, according to definition (7.3). Control action u is a
function of x and x . Now, since X is the break-frequency of filter (7.3), it must be
d
chosen to be "small" with respect to high-frequency unmodeled dynamics (such as
unmodeled structural modes or neglected time delays). Furthermore, we can now tune
the boundary layer thickness <& so that (7.29) also represents a first-order filter of
1

Sect. 7.2 Continuous Approximations of Switching Control Laws 295
bandwidth L It suffices to let
(7.30)
which can be written from (7.27) as
<T> + A.O = k(x ) (7.31)
d
1 order filter 1
(7-29) (P+X)"-1
CHOICE OF <P DEFINITION OF s
Figure 7.9 : Structure of the closed-loop error dynamics
Equation (7.31) defines the desired time-history of boundary layer thickness <J>, and, in
the light of Figure 7.9, shall be referred to as the balance condition. Intuitively, it
amounts to tuning up the closed-loop system so that it mimics an «tn order critically
damped system. Furthermore, definition (7.27) can then be rewritten as
k (x) = k(x) - k(x ) + X® (7.32)
d
The s-trajectoiy, i.e., the variation of s with time, is a compact descriptor of the
closed-loop behavior: control activity directly depends on s, while by definition (7.3)
tracking error x is merely a filtered version of s. Furthermore, the s-trajectory
represents a time-varying measure of the validity of the assumptions on model
uncertainty. Similarly, the boundary layer thickness <J> describes the evolution of
dynamic model uncertainty with time. It is thus particularly informative to plot
s(t), ®(t), and - <t>(r) on a single diagram, as illustrated in Figure 7.10.
Example 7.3: Consider again the system described by (7.10). The complete control law is now
u = x-Xx + 1.5 x2 cos 3x - (0.5 x21 cos 3x | + r| - 4>) sat[(? + Xx)/<t>]
d
with 4> = - X$> + (0.5 x2 | cos 3x | +1|)
d d
and, assuming e.g., that xjifi) = 0 initially, 0(0) = r\/X . As in Example 7.2, we let T] = 0.1 and
X — 20. Typically, the arbitrary constant T| (which, formally, reflects the time to reach the
boundary layer starting from the outside) is chosen to be small as compared to the average value
of k(\), so as to fully exploit our knowledge of the structure of parametric uncertainty. The
d

| 296  Sliding Control |     |     | Chap. 7 |
| -------------------- | --- | --- | ------- |
Figure 7.10 : The ^-trajectories can convey much information on a single plot
value of X is selected based on the frequency range of unmodeled dynamics, as we shall discuss
later.
The tracking error, control input, and ^-trajectories are plotted in Figure 7.11 for the same
desired trajectory x = sin(7U/2) as in Example 7.2. We see that while the maximum value of the
d
time-varying boundary layer thickness <J> is the same as that originally chosen (purposefully) as
the constant value of O in Example 7.2, the tracking error is consistently better (up to 4 times
better) than that in Example 7.2, because varying the thickness of the boundary layer allows us to
make better use of the available bandwidth.  C\
| 1.0 2.0 | 3.0  4.0  | 1.0 2.0 | 3.0  4.0  |
| ------- | --------- | ------- | --------- |
|         | time(sec) |         | time(sec) |
Figure 7.11a : Control input and resulting tracking performance

Sect. 7.2 Continuous Approximations of Switching Control Laws 297
Figure 7.11b : ^-trajectories with time-varying boundary layers
In the case that p •£ 1, one can easily show that (7.31) and (7.32) become (with
=> (7.33)
(7.34)
=>
Pi
with initial condition 0(0) defined as:
(7.35)
Indeed, in order to satisfy (7.26) in the presence of uncertainty (3 on the control gain we let
6 => k~(x) = k(x) - O/p (7.36)
=> T(x) = *(x) - P 4> (7.37)
Furthermore, the balance condition can be written, instead of (7.30), as
(7.38)
that is,
k (x) =
d

298 Sliding Control Chap. 7 fj
Applying this relation to (7.36), (7.37) leads to the desired behavior of <I>:
=> ^
Vd
which we can combine with (7.36)-(7.37) and rewrite as (7.33)-(7.34). Finally, remark that if
(3 = (5^ , one has
k (x) = (k (x) - k (x )) + k (x) = k(x) - k(x)
rf d d
Note that the balance conditions (7.33) and (7.34) imply that <J> and thus x are
bounded for bounded x.
d
The balance conditions have a simple and intuitive physical interpretation:
neglecting time constants of order I/A., they imply that
that is
(bandwidth)" x (tracking precision)
= (parametric uncertainty measured along the desired trajectory)
Such trade-off is quite similar to the situation encountered in linear time-invariant
systems, but here applies to the more general nonlinear system structure (7.1), all
along the desired trajectory. In particular, it shows that, in essence, the balance
conditions specify the best tracking performance attainable, given the desired control
bandwidth and the extent of parameter uncertainty. Similarly, expression (7.20)
allows one to easily quantify the trade-off between accuracy and speed along a given
path, for instance.
Example 7.4: Let us consider again the underwater vehicle of Example 7.1, and smoothen the
control input using time-varying boundary layer, as described above. The a priori bounds on m
and c are
1 <m<5 0.5<c<1.5
and, accordingly,

Sect. 7.2 Continuous Approximations of Switching Control Laws  299
The actual values used in the simulation are
| 1.5sin(liU) | c= 1.2 + .2sin(lilr) |     |     |
| ----------- | -------------------- | --- | --- |
which are used as a metaphor of the complexity of the actual hydrodynamic effects. We let
i^=0.1  and X = 10.
The desired trajectory consists of a constant-acceleration phase at 2 m/s2 for two seconds, a
constant-velocity phase (at 4 m/s) for two seconds, and a constant-acceleration phase at - 2 m/s2
for two seconds. The corresponding tracking error, control input, and s-trajectories are plotted in
| Figure 7.12.  |     |     | •   |
| ------------- | --- | --- | --- |
§
0 -
-10
0.0  1.0  2.0  3.0  4.0  5.0  6.0 0.0 1.0  2.0  3.0  4.0  5.0  6.0
|     | time(sec) |     | time(sec) |
| --- | --------- | --- | --------- |
Figure 7.12a : Control input and resulting tracking performance
| 0.0 1.0 | 2.0 | 4.0 5.0  | 6.0 |
| ------- | --- | -------- | --- |
timefsecl
Figure 7.12b : ^-trajectories with time-varying boundary layers

300 Sliding Control Chap. 7
REMARKS
(i) The desired trajectory x must itself be chosen smooth enough not to excite
d
the high-frequency unmodeled dynamics.
(ii) An argument similar to that of the above discussion shows that the choice of
dynamics (7.3) used to define sliding surfaces is the "best-conditioned" among linear
dynamics, in the sense that it guarantees the best tracking performance given the
desired control bandwidth and the extent of parameter uncertainty.
(iii) If the model or its bounds are so imprecise that F can only be chosen as a
large constant, then <j> from (7.31) is constant and large, so that the term k sat(s/(j>)
simply equals X s/P in the boundary layer, and therefore acts as a simple P.D.: there is
no free lunch.
(iv) A well-designed controller should be capable of gracefully handling
exceptional disturbances, i.e., disturbances of intensity higher than the predicted
bounds which are used in the derivation of the control law. For instance, somebody
may walk into the laboratory and push violently on the system "to see how stiff it is";
an industrial robot may get jammed by the failure of some other machine; an actuator
may saturate as the result of the specification of an unfeasible desired trajectory. If
integral control is used in such cases, the integral term in the control action may
become unreasonably large, so that once the disturbance stops, the system goes
through large amplitude oscillations in order to return to the desired trajectory. This
phenomenon, known as integrator windup, is a potential cause of instability because
of saturation effects and physical limits on the motion. It can be simply avoided by
stopping integration (i.e. maintaining the integral term constant) as long as the system
is outside the boundary layer. Indeed, under normal circumstances the system does
remain in the boundary layer; on the other hand, when the conditions return to normal
after an exceptional disturbance, integration can resume as soon as the system is back
in the boundary layer, since the integral term is defined to within an arbitrary constant.
(v) In the case that X is time-varying (as further discussed in the next section),
the term
u =-Xx
should be added to the corresponding u, while augmenting gain k{\) accordingly by
the quantity | u |((3 - 1).
The degree of simplification in the system model may be varied according to
the on-line computing power available: in essence, the balance conditions quantify the

Sect. 7.3 The Modeling/Performance Trade-Offs 301
trade-off between model precision and tracking accuracy, as further detailed next.
Furthermore, the ^--trajectories provide a measure of the validity of the assumptions
on model uncertainty and of the adequacy of bound simplifications.
7.3 The Modeling/Performance Trade-Offs
The balance conditions (7.33)-(7.34) have practical implications in terms of
design/modeling/performance trade-offs. Neglecting time-constants of order I/A.,
conditions (7.33) and (7.34) imply that
(7.39)
as noticed in section 7.2. If we now consider the structure of control law (7.19), we
see that the effects of parameter uncertainty on / have been "dumped" in gain k.
Conversely, better knowledge of/reduces k by a comparable quantity. Thus (7.39) is
particularly useful in an incremental mode, i.e., to evaluate the effects of model
simplification (or conversely of increased model sophistication) on tracking
performance:
(7.40)
In particular, marginal gains in performance are critically dependent on control
bandwidth X: if large X's are available, poor dynamic models may lead to respectable
tracking performance, and conversely large modeling efforts produce only minor
absolute improvements in tracking accuracy.
It is of course not overly surprising that system performance be very sensitive to
control bandwidth A. : (7.1) only represents part of the system dynamics - e.g., its
rigid-body component - while X accounts for the unmodeled part. In the right-hand
side of (7.40), the effects of parametric uncertainty in (7.1) are reflected in the
numerator, while the presence of dynamics neglected in the model is reflected in the
denominator, since it both translates into the order n of the model, and imposes upper
bounds on the choice of X.
Thus, given model (7.1), a key question is to determine how large X can be
chosen. Although the tuning of this single scalar may in practice be done
experimentally, considerable insight on the overall design can be obtained by
explicitly analyzing the various factors limiting X. In mechanical systems, for
instance, given clean measurements, X is typically limited by three factors:
(i) structural resonant modes: X must be smaller than the frequency Vg of the
lowest unmodeled structural resonant mode; a reasonable interpretation of this

302 Sliding Control Chap. 7
constraint is, classically
- ^-R °* -jR V (7.41)
although in practice this bound may be modulated by engineering judgment, taking
notably into account the natural damping of the structural modes. Furthermore, it
may be worthwhile in certain cases to account for the fact that X may actually
R
vary with the task (e.g., given configuration or loads).
(ii) neglected time delays: along the same lines, we have a condition of the
form
J
(7.42)
when T^ is the largest unmodeled time-delay (for instance in the actuators).
(iii) sampling rate: with a full-period processing delay, one gets a condition of
the form
(7.43)
^sampling
where v is the sampling rate.
sam lin
The desired control bandwidth X is the minimum of the three bounds (7.41)-(7.43).
Bound (7.41) essentially depends on the system's mechanical properties, while (7.42)
reflects limitations on the actuators, and (7.43) accounts for the available computing
power. Ideally, the most effective design corresponds to matching these limitations,
i.e., having
«X ^X = X (7.44)
A S
Now (7.41) and (7.42) are "hard" limitations, in the sense that they represent
properties of the hardware itself, while (7.43) is "soft" as far as it reflects the
performance of the computer environment and the complexity of the control
algorithm. Assume for instance that bound (7.43) is the most stringent, which means
that the system's mechanical potentials are not fully exploited. This may typically
occur in modern high-performance robots (such as direct-drive arms) which feature
high mechanical stiffness and high resonant frequencies. It may be worthwhile, before
embarking in the development of dedicated computer architectures, to first consider
simplifying the dynamic model used in the control algorithm. This in turn allows one
to replace X = X \ by a larger X = A. which varies inversely proportionally to the
S OVJ fast

Sect. 7.4 * Multi-Input Systems 303
required computation time. From (7.40) and assuming that neither of bounds (7.41) or
(7.42) is hit in the process, this operation is beneficial as long as
_, .
(745)
Conversely, equality in (7.45) defines the threshold at which model simplification
starts degrading performance despite gains in sampling rate. This threshold is rarely
reached in practice: even assuming that marginal gains in model precision depend
linearly on the computation time involved, X~2 still varies as the square of the
required sampling period. Thus it is often advisable to reduce model complexity until
computation can be achieved at a rate fully compatible with the mechanical
capabilities of the arm, in other words until \$ is no longer the "active" limit on X.
The performance increase resulting from this simple operation may in turn be
adequate and avoid major development efforts on the computer hardware.
The trade-off between modeling inaccuracy and performance can be further
improved only by updating the model on-line. This can indeed be achieved when
some components of the model depend linearly on unknown but constant parameters,
allowing the corresponding uncertainties to be mapped in terms of a single unknown
constant vector. This is the topic of chapter 8, adaptive control.
7.4 * Multi-Input Systems
This section discusses extensions of the previous development to multi-input systems.
The point of view taken here is essentially mathematical. In chapter 9, we shall discuss
how the exploitation of known physical properties of the systems, such as
conservation of energy, may often make such multi-input extensions simpler and more
powerful.
Consider a nonlinear multi-input system of the form
m
xi{rti) = -//W + X bijW uj i=l, . . . ,m j = 1, .. ., m
i= i
where the vector u of components u-. is the control input vector, and the state x is
composed of the xfs and their first («- - 1) derivatives. As mentioned in chapter 6,
;
such systems are called square systems, since they have as many control inputs «.• as
outputs to be controlled Xj. We are interested again in the problem of having the state
x track a desired time-varying state x , in the presence of parametric uncertainties.
d

304 Sliding Control Chap. 7
We make two assumptions. First, we assume that the matching conditions
discussed in chapter 6 are verified, i.e., that parametric uncertainties are within the
range space of the input matrix B (of components bj). Since B is a square mxm
t
matrix, this simply means that B is invertible over the whole state-space, a
controllability-like assumption. Second, we assume that the estimated input matrix
A A
B is invertible, continuously dependent on parametric uncertainty, and such that B = B
in the absence of parametric uncertainty.
As in the single-input case, we shall write uncertainties on f in additive form,
and uncertainties on the input matrix B in multiplicative form
\}'i~fi\<Fi i=l, ...,m (7.46)
B = (I + A) B i=l, ...,m 7 = 1, ...,m (7.47)
where I is the n x n identity matrix. Note that the structure of expression (7.46) is
slightly different from that of (7.47), since the notion of a gain margin is mostly a
scalar concept, while (7.47) shall prove more convenient for the purpose of matrix
manipulation.
Let us define a vector s of components s by
t
n:-\
which, for notational compactness, we shall write
This defines a vector x/"~ ^ of components xfni ~ ^ , which can be computed from x
r
and x . As in the single-input case, the controller design can be translated in terms of
d
finding a control law for the vector u that verifies individual sliding conditions of the
form
1 d ,2 < _
i'1 ~ (7.48)
in the presence of parametric uncertainty. Letting k sgn(s) be the vector of
components k sgn(s), and choosing the control law to be of the form
v (
u = B" J (x/"-') - f - k sgn(s)) (7.49)
similarly to the single-input case, we can write

Sect. 7.4 * Multi-Input Systems 305
h = ft-fi + SAW"'--0-/,-)
- ]£ A,y £y sgn(.yy) - (I + A ) ^-sgn(^)
/7
j* •
Thus, the sliding conditions are verified if
> = 1 J• * i
/=1, ... ,«
and, in particular, if the vector k is chosen such that
(1 - D ) ki + J Dij kj = F + j^Dy | xf"i - I) - /,-1 + n,- (7.50)
u { r
y * l" y = 1
/= 1, ... ,n
Expression (7.50) represents a set of m equations in the m switching gains kj.
Do these equations have a solution k (then necessarily unique), and are the
components kj all positive (or zero)? The answer to both questions is yes, thanks to an
interesting result of matrix algebra, known as the Frobenius-Perron theorem.
Theorem (Frobenius-Perron) Consider a square matrix A with non-negative
elements. Then, the largest real eigenvalue p± of A of is non-negative. Furthermore,
consider the equation
(I - p-1 A) y = z
where all components of the vector z are non-negative. If p > pj , then the above
equation admits a unique solution y, whose components y are all non-negative.
t
Applying the Frobenius-Perron theorem to the matrix of components D,-., and noticing
that our second assumption on the system implies that Pi < 1, shows that equation
(7.50) uniquely defines a set of non-negative kj. Thus, the control law (7.49), with k
defined by (7.50), satisfies the sliding condition in the presence of parametric
uncertainties bounded by (7.46).
As in the single-input case, the switching control laws derived above can be
smoothly interpolated in boundary layers, so as to eliminate chattering, thus leading to
a trade-off between parametric uncertainty and performance. The reader is referred to
section 7.6 for details.
Note that the point of view taken in this section is essentially mathematical.

306 Sliding Control Chap. 7
Chapter 9 shall dvscuss how the exploitation of physical properties of the systems,
such as conservation of energy, often makes multi-input designs simpler and more
powerful. This will become particularly important in adaptive versions of the designs.
7.5 Summary
The aim of a sliding controller is to
(i) Design a control law to effectively account for
• parameter uncertainty, e.g., imprecision on the mass properties or
loads, inaccuracies on the torque constants of the actuators, friction,
and so on.
• the presence of unmodeled dynamics, such as structural resonant
modes, neglected time-delays (in the actuators, for instance), or finite
sampling rate.
(ii) Quantify the resulting modeling!performance trade-offs, and in
particular, the effect on tracking performance of discarding any particular
term in the dynamic model.
The methodology is based on a notational simplification, which amounts to
replacing an nth order tracking problem by a first order stabilization problem.
Although "perfect" performance can in principle be achieved in the presence of
arbitrary parameter inaccuracies, uncertainties in the model structure (i.e., unmodeled
dynamics) lead to a trade-off between tracking performance and parametric
uncertainty, given the available "bandwidth." In practice, this corresponds to replacing
a switching, chattering control law by its smooth approximation. In specific
applications where control chattering is acceptable, the pure switching control laws
can yield extremely high performance.
Sliding controller design provides a systematic approach to the problem of
maintaining stability in the face of modeling imprecisions. Furthermore, it quantifies
the modeling/performance trade-offs, and in that sense can illuminate the whole
design and testing process. Finally, it offers the potential of simplifying higher-level
programming, by accepting reduced information about both task and system.
J

Sect. 7.7 Exercises 307
7.6 Notes and References
The concept of a sliding surface originated in the Soviet literature [e.g., Aizerman and Gantmacher,
1957; Emelyanov, 1957; Filippov, 1960] (see also [Tsypkin, 1955; Flugge-Lotz, et al, 1958]),
mostly in the context of "variable-structure" regulation of linear systems, see [Utkin, 1977] for a
review (also [Young, 1978]). Classical sliding mode control, however, had important drawbacks
limiting its practical applicability, such as chattering and large control authority. The development of
sections 7.1-7.3 is based on [Slotine, 1984].
The combination of sliding controllers with state observers is discussed in [Bondarev, et al.,
1985] in the linear case, and [Hedrick and Ragavan, 1990] in the nonlinear case. Observers based on
sliding surfaces are discussed in [Drakunov, 1983; Slotine, et al, 1986, 1987; Walcott and Zak,
1987]. The development of section 7.4 is adapted from [Slotine, 1985; Hedrick and Gopalswamy,
1989]. The reader is referred to, e.g., [Luenberger, 1979] for a simple proof of the Frobenius-Perron
theorem. Some details on boundary layer interpolations in the multi-input case can be found in
[Slotine, 1985].
Practical implementations of sliding control are described, e.g., in [Yoerger, et al, 1986]
(underwater vehicles), [Hedrick, et al, 1988] (automotive applications), [Harashima, et al, 1988]
(robot manipulators). The literature in the field has been extremely active in the past few years.
Related approaches to robust control include, e.g., [Corless and Leitmann, 1981; Gutman and
Palmor, 1982; Ha and Gilbert, 1985].
7.7 Exercises
7.1 Consider the underwater vehicle of Example 7.4, and assume there is an unmodeled
"pendulum mode" of the vehicle at 2 Hz. Choose X accordingly, and simulate the vehicle's
performance on the same trajectory as in Example 7.4. What is the minimum sampling rate required
to implement your design?
Discuss the performance of the system on various trajectories, which you may want to
generate using a reference model, as in equation (II.5), with k = 2X,k = X2 .
i 2
Simulate the unmodeled 2 Hz mode by first passing the control law through a second-order
lowpass filter of unit d.c. gain before actually inputting it in the system. Tune X "experimentally"
around the value given by (7.41), for different values of the filter's damping.
7.2 For the system
Xj = sinx + ^ I + I Xj
2
x = a(()x4cosx + a.2(0 "
2 1 1 2

308 Sliding Control Chap. 7
design a controller to track an arbitrary desired trajectory x (t) . Assume that the state [jr, x]r
dt 2
is measured, that x (t) ,x^(t) ,x (t) are all known, and that aft) and a(f) are unknown time-
dl d dx 2
varying functions verifying the known bounds
V«>0, lotjCOl < 10 I<a(()<2
2
Write the full expression of the controller, as a function of the measured state [X\ x]T • Check
2
your design in simple simulations. (Hint: First feedback linearize the system by differentiating the
first equation.)
7.3 Consider again the system of Exercise 7.1, but define i so as to use integral control (as
discussed in section 7.1.3). Simulate the controller's performance and compare with the results of
Exercise 7.1, on various trajectories. Show that, besides allowing the system to always start at s = 0,
the integral control term keeps adjusting the control law as long as the effects of bounded
disturbances are not compensated.
7.4 Consider a system of the form (7.1), but where b is now constant and of known constant
positive bounds. Divide both sides of the equation by 6, and write the sliding condition as
where h = 1 Ib . By representing uncertainty on h additively, design a simple switching controller to
satisfy the above condition.
Smooth out the switching controller in boundary layers, and derive the corresponding balance
conditions.
Show that the accuracy of the approximate "bandwidth" analysis in the boundary layer
increases with X.
7.5 Consider a system of the form (7.1), and assume that not only x but also s can be measured
(e.g., that jtW can be measured). An additional term of the form -as (with a > 0 ) can then be
included in the control law.
Write the corresponding expression of s. Assuming for simplicity that the gain margin p is
constant, show that, given the bandwidth X and the parametric uncertainty, the effect of the
additional term in u is to reduce the maximum value of s by a factor ( 1 + a/p ). Show that this
implies that the tracking error x can in principle be made arbitrarily small simply by increasing a.
What are the limitations of this approach? In particular, assume that there is / % uncertainty
on the value of x^ . How small must / be to make the approach worthwhile? (Adapted from [Asada
andSlotine, 1986].)
1

Sect. 7.7 Exercises 309
7.6 Show that a condition similar to (7.68) can also be obtained by requiring that the system take
at least two sampling periods to cross the boundary layer.
Assume that sampling is the active limit on bandwidth, and that chattering is acceptable.
Based on the above result, how do the tracking performances of a switching controller and a smooth
sliding controller compare?
7.7 Design a switching controller for the system
x + <X|(/) |JC| Jc2 + a(t) x3 cos 2x = 5 ii + u
2
where (X[(/) and a(r) are unknown time-varying functions verifying the known bounds
2
Vi>0, |a,(f)|< 1 -1 <a(/)<5
2
(Hint: let v = 5 u + u . Discuss the effect of chattering in v .)
7.8 In the context of section 7.2, define
s = s - Osat(.s7<I>)
A
as a measure of distance to the boundary layer. Show that the time derivative of s^ is well defined
and continuous in time, and, specifically, that one can write
Show that equation (7.26) can be written
5S'A2*-W
(Adapted from [Slotine and Coetsee, 1986].)
7.9 In the context of tracking control, discuss alternate definitions of 5. For instance, consider
choices based on Butterworth filters rather than (7.3), and how they would modify bounds (7.4).
7.10 Design a sliding controller for the system
x'3) + (Xj(r) x- + a(t) i5 sin 4x = b(t) u
2
where a.\(t), a(t), and b(t) are unknown time-varying functions verifying the known bounds
2
Vr>0, |ct,(/)|<l |a(r)|<2 l<b(t)<4
2

310 Sliding Control Chap. 7
Assume that the state is measured, and that the slowest unmodeled dynamics is the actuator
dynamics, with a time-constant of about 1/50. Simulate the performance of the system on various
trajectories (which you may want to generate using a reference model).
J

Chapter 8
Adaptive Control
Many dynamic systems to be controlled have constant or slowly-varying uncertain
parameters. For instance, robot manipulators may carry large objects with unknown
inertial parameters. Power systems may be subjected to large variations in loading
conditions. Fire-fighting aircraft may experience considerable mass changes as they
load and unload large quantities of water. Adaptive control is a approach to the
control of such systems. The basic idea in adaptive control is to estimate the uncertain
plant parameters (or, equivalently, the corresponding controller parameters) on-line
based on the measured system signals, and use the estimated parameters in the control
input computation. An adaptive control system can thus be regarded as a control
system with on-line parameter estimation. Since adaptive control systems, whether
developed for linear plants or for nonlinear plants, are inherently nonlinear, their
analysis and design is intimately connected with the materials presented in this book,
and in particular with Lyapunov theory.
Research in adaptive control started in the early 1950's in connection with the
design of autopilots for high-performance aircraft, which operate at a wide range of
speeds and altitudes and thus experience large parameter variations. Adaptive control
was proposed as a way of automatically adjusting the controller parameters in the face
of changing aircraft dynamics. But interest in the subject soon diminished due to the
lack of insights and the crash of a test flight. It is only in the last decade that a
coherent theory of adaptive control has been developed, using various tools from
nonlinear control theory. These theoretical advances, together with the availability of
cheap computation, have lead to many practical applications, in areas such as robotic
311

312 Adaptive Control Chap. 8
: manipulation, aircraft and rocket control, chemical processes, power systems, ship
steering, and bioengineering.
The objective of this chapter is to describe the main techniques and results in
adaptive control. We shall start with intuitive concepts, and then study more
systematically adaptive controller design and analysis for linear and nonlinear
systems. The study in this chapter is mainly concerned with single-input systems.
Adaptive control designs for some complex multi-input physical systems are discussed
in chapter 9.
8.1 Basic Concepts in Adaptive Control
In this section, we address a few basic questions, namely, why we need adaptive
control, what the basic structures of adaptive control systems are, and how to go about
designing adaptive control systems.
8.1.1 Why Adaptive Control ?
In some control tasks, such as those in robot manipulation, the systems to be
controlled have parameter uncertainty at the beginning of the control operation. Unless
such parameter uncertainty is gradually reduced on-line by an adaptation or estimation
mechanism, it may cause inaccuracy or instability for the control systems. In many
other tasks, such as those in power systems, the system dynamics may have well
known dynamics at the beginning, but experience unpredictable parameter variations
as the control operation goes on. Without continuous "redesign" of the controller, the
initially appropriate controller design may not be able to control the changing plant
well. Generally, the basic objective of adaptive control is to maintain consistent
performance of a system in the presence of uncertainty or unknown variation in plant
parameters. Since such parameter uncertainty or variation occurs in many practical
problems, adaptive control is useful in many industrial contexts. These include:
• Robot manipulation: Robots have to manipulate loads of various sizes, weights,
and mass distributions (Figure 8.1). It is very restrictive to assume that the inertial
parameters of the loads are well known before a robot picks them up and moves
them away. If controllers with constant gains are used and the load parameters are
not accurately known, robot motion can be either inaccurate or unstable. Adaptive
control, on the other hand, allows robots to move loads of unknown parameters
with high speed and high accuracy.

Sect. 8.1 Basic Concepts in Adaptive Control 313
• Ship steering: On long courses, ships are usually put under automatic steering.
However, the dynamic characteristics of a ship strongly depend on many uncertain
parameters, such as water depth, ship loading, and wind and wave conditions
(Figure 8.2). Adaptive control can be used to achieve good control performance
under varying operating conditions, as well as to avoid energy loss due to excessive
rudder motion.
• Aircraft control: The dynamic behavior of an aircraft depends on its altitude,
speed, and configuration. The ratio of variations of some parameters can lie
between 10 to 50 in a given flight. As mentioned earlier, adaptive control was
originally developed to achieve consistent aircraft performance over a large flight
envelope.
• Process control: Models for metallurgical and chemical processes are usually
complex and also hard to obtain. The parameters characterizing the processes vary
from batch to batch. Furthermore, the working conditions are usually time-varying
{e.g., reactor characteristics vary during the reactor's life, the raw materials
entering the process are never exactly the same, atmospheric and climatic
conditions also tend to -change). In fact, process control is one of the most
important and active application areas of adaptive control.
obstacles
desired trajectory
•• unknown load
Figure 8.1 : A robot carrying a load of uncertain mass properties

314 Adaptive Control Chap. 8
Adaptive control has also been applied to other areas, such as power systems
and biomedical engineering. Most adaptive control applications are aimed at handling
inevitable parameter variation or parameter uncertainty. However, in some
applications, particularly in process control, where hundreds of control loops may be
present in a given system, adaptive control is also used to reduce the number of design
parameters to be manually tuned, thus yielding an increase in engineering efficiency
and practicality.
Figure 8.2 : A freight ship under various loadings and sea conditions
To gain insights about the behavior of the adaptive control systems and also to
avoid mathematical difficulties, we shall assume the unknown plant parameters are
constant in analyzing the adaptive control designs. In practice, the adaptive control
systems are often used to handle time-varying unknown parameters. In order for the
analysis results to be applicable to these practical cases, the time-varying plant
parameters must vary considerably slower than the parameter adaptation. Fortunately,
this is often satisfied in practice. Note that fast parameter variations may also indicate
that the modeling is inadequate and that the dynamics causing the parameter changes
should be additionally modeled.
Finally, let us note that robust control can also be used to deal with parameter
uncertainty, as seen in chapter 7. Thus, one may naturally wonder about the
differences and relations between the robust approach and the adaptive approach. In
principle, adaptive control is superior to robust control in dealing with uncertainties in
constant or slowly-varying parameters. The basic reason lies in the learning behavior
of adaptive control systems: an adaptive controller improves its performance as
adaptation goes on, while a robust controller simply attempts to keep consistent
performance. Another reason is that an adaptive controller requires little or no a
priori information about the unknown parameters, while a robust controller usually
requires reasonable a priori estimates of the parameter bounds. Conversely, robust
control has some desirable features which adaptive control does not have, such as its
ability to deal with disturbances, quickly varying parameters, and unmodeled
1

Sect. 8.1 Basic Concepts in Adaptive Control 315
dynamics. Such features actually may be combined with adaptive control, leading to
robust adaptive controllers in which uncertainties on constant or slowly-varying
parameters is reduced by parameter adaptation and other sources of uncertainty are
handled by robustification techniques. It is also important to point out that existing
adaptive techniques for nonlinear systems generally require a linear parametrization
of the plant dynamics, i.e., that parametric uncertainty be expressed linearly in terms
of a set of unknown parameters. In some cases, full linear parametrization and thus
adaptive control cannot be achieved, but robust control (or adaptive control with
robustifying terms) may be possible.
8.1.2 What Is Adaptive Control ?
An adaptive controller differs from an ordinary controller in that the controller
parameters are variable, and there is a mechanism for adjusting these parameters on-
line based on signals in the system. There are two main approaches for constructing
adaptive controllers. One is the so-called model-reference adaptive control method,
and the other is the so-called self-tuning method.
MODEL-REFERENCE ADAPTIVE CONTROL (MRAC)
Generally, a model-reference adaptive control system can be schematically
represented by Figure 8.3. It is composed of four parts: a plant containing unknown
parameters, a reference model for compactly specifying the desired output of the
control system, a feedback control law containing adjustable parameters, and an
adaptation mechanism for updating the adjustable parameters.
a — estimated parameters
Figure 8.3 : A model-reference adaptive control system

316 Adaptive Control Chap. 8
The plant is assumed to have a known structure, although the parameters are
unknown. For linear plants, this means that the number of poles and the number of
zeros are assumed to be known, but that the locations of these poles and zeros are not.
For nonlinear plants, this implies that the structure of the dynamic equations is known,
but that some parameters are not.
A reference model is used to specify the ideal response of the adaptive control
system to the external command. Intuitively, it provides the ideal plant response
which the adaptation mechanism should seek in adjusting the parameters. The choice
of the reference model is part of the adaptive control system design. This choice has to
satisfy two requirements. On the one hand, it should reflect the performance
specification in the control tasks, such as rise time, settling time, overshoot or
frequency domain characteristics. On the other hand, this ideal behavior should be
achievable for the adaptive control system, i.e., there are some inherent constraints on
the structure of the reference model (e.g., its order and relative degree) given the
assumed structure of the plant model.
The controller is usually parameterized by a number of adjustable parameters
(implying that one may obtain a family of controllers by assigning various values to
the adjustable parameters). The controller should have perfect tracking capacity in
order to allow the possibility of tracking convergence. That is, when the plant
parameters are exactly known, the corresponding controller parameters should make
the plant output identical to that of the reference model. When the plant parameters
are not known, the adaptation mechanism will adjust the controller parameters so that
perfect tracking is asymptotically achieved. If the control law is linear in terms of the
adjustable parameters, it is said to be linearly parameterized. Existing adaptive
control designs normally require linear parametrization of the controller in order to
obtain adaptation mechanisms with guaranteed stability and tracking convergence.
The adaptation mechanism is used to adjust the parameters in the control law.
In MRAC systems, the adaptation law searches for parameters such that the response
of the plant under adaptive control becomes the same as that of the reference model,
i.e., the objective of the adaptation is to make the tracking error converge to zero.
Clearly, the main difference from conventional control lies in the existence of this
mechanism. The main issue in adaptation design is to synthesize an adaptation
mechanism which will guarantee that the control system remains stable and the
tracking error converges to zero as the parameters are varied. Many formalisms in
nonlinear control can be used to this end, such as Lyapunov theory, hyperstability
theory, and passivity theory. Although the application of one formalism may be more
convenient than that of another, the results are often equivalent. In this chapter, we J
shall mostly use Lyapunov theory.

Sect. 8.1 Basic Concepts in Adaptive Control 317
As an illustration of MRAC control, let us describe a simple adaptive control
system for an unknown mass.
Example 8.1: MRAC control of an unknown mass
Consider the control of a mass on a frictionless surface by a motor force w, with the plant
dynamics being
mx = u (8.1)
Assume that a human operator provides the positioning command r(t) to the control system
(possibly through a joystick). A reasonable way of specifying the ideal response of the controlled
mass to the external command r(t) is to use the following reference model
with the positive constants X and "k^ chosen to reflect the performance specifications, and the
i
reference model output x being the ideal output of the control system (i.e., ideally, the mass
m
should go to the specified position r{t) like a well-damped mass-spring-damper system).
If the mass m is known exactly, we can use the following control law to achieve perfect
tracking
u = m(x — 2Xx — X2x)
m
with x = x(t) - x (t) representing the tracking error and X a strictly positive number. This control
m
law leads to the exponentially convergent tracking error dynamics
x + 2Xx + X2x = 0
Now let us assume that the mass is not known exactly. We may use the following control law
u = m(x -2Xic-X2x) (8.3)
m
which contains the adjustable parameter m. Substitution of this control law into the plant
dynamics leads to the closed-loop error dynamics
mv (8.4)
where s, a combined tracking error measure, is defined by
s = i + Xx (8.5)
the signal quantity v by
v = x -2Xx -X2x
m
and the parameter estimation error m by

318 Adaptive Control Chap. 8
fh = m-m
Equation (8.4) indicates that the combined tracking error s is related to the parameter error
tthhrroouugghh aa ssttaabbllee ffiilltteerr rreellaattiioonn.. One way of adjusting parameter m (for reasons to be seen later) is
to use the following update law
m = -yvs (8.6)
where y is a positive constant called the adaptation gain. One easily sees the nonlinear nature of
the adaptive control system, by noting that the parameter m is adjusted based on system signals,
and thus the controller (8.3) is nonlinear.
The stability and convergence of this adaptive control system can be analyzed using
Lyapunov theory. For the closed-loop dynamics (8.4) and (8.6), with s and m as states, we can
consider the following Lyapunov function candidate,
V = -[ms2+-m2] (8.7)
2 7
Its derivative can be easily shown to be
V = -Xms2 (8.8)
Using Barbalat's lemma in chapter 4, one can easily show that s converges to zero. Due to the
relation (8.5), the convergence of s to zero implies that of the position tracking error x and the
velocity tracking error x.
For illustration, simulations of this simple adaptive control system are provided in Figures
8.4 and 8.5. The true mass is assumed to be m=2. The initial value of m is chosen to be zero,
indicating no a priori parameter knowledge. The adaptation gain is chosen to be y = 0.5, and the
other design parameters are taken to be X^ = 10, Xj = 25, X. = 6. Figure 8.4 shows the results
when the commanded position is r(t) = 0, with initial conditions being x(0) = x (Q) — 0 and
m
x(0) = x (0) = 0.5. Figure 8.5 shows the results when the desired position is a sinusoidal signal,
m
r(i) = sin(4 t). It is clear that the position tracking errors in both cases converge to zero, while the
parameter error converge to zero only for the latter case. The reason for the non-convergence of
parameter error in the first case can be explained by the simplicity of the tracking task: the
asymptotic tracking of x (t) can be achieved by many possible values of the estimated parameter
m
m, besides the true parameter. Therefore, the parameter adaptation law does not bother to find out
the true parameter. On the other hand, the convergence of the parameter error in Figure 8.5 is
because of the complexity of the tracking task, i.e., tracking error convergence can be achieved
only when the true mass is used in the control law. One may examine Equation (8.4) to see the
mathematical evidence for these statements (also see Exercise 8.1). It is also helpful for the
readers to sketch the specific structure of this adaptive mass control system. A more detailed
discussion of parameter convergence is provided in section 8.2. D
1

| Sect. 8.1 |     | Basic Concepts in Adaptive Control  |     |     | 319 |
| --------- | --- | ----------------------------------- | --- | --- | --- |
| 0. 6      |     |                                     | 2.5 |     |     |
I 5
°-
UIIJ
2.0
| 0.4 |     |     | <u         |     |     |
| --- | --- | --- | ---------- | --- | --- |
| to  |     |     | retlemarap |     |     |
| 0-3 |     |     | 1.5        |     |     |
| 0.2 |     |     | 1.0        |     |     |
0.1
0.5
0.0
0.0
-0.1 0.0  0.5  1.0  1.5  2.0  2.5  3.0 0.0  0.5  1.0  1.5  2.0  2.5  3.0
|     | time(sec) |     |     | time(sec) |     |
| --- | --------- | --- | --- | --------- | --- |
Figure 8.4 : Tracking Performance and Parameter Estimation for an Unknown Mass,
0.8
0.6
0.4
0.2
0.0
-0.2
-0.4
-0.6
| -0.8    |                |          | 0.0      |           |         |
| ------- | -------------- | -------- | -------- | --------- | ------- |
| 0.0 0.5 | 1.0  1.5  2.0  | 2.5  3.0 | 0.0  0.5 | 1.5  2.0  | 2.5 3.0 |
|         | time(sec)      |          |          | time(sec) |         |
Figure 8.5 : Tracking Performance and Parameter Estimation for an Unknown Mass,
SELF-TUNING CONTROLLERS (STC)
In non-adaptive control design (e.g., pole placement), one computes the parameters of
the controllers from those of the plant. If the plant parameters are not known, it is
intuitively reasonable to replace them by their estimated values, as provided by a
parameter estimator.  A controller thus obtained by coupling a controller with an on-
line  (recursive)  parameter estimator  is called  a self-tuning  controller.  Figure  8.6
illustrates the schematic structure of such an adaptive controller. Thus, a self-tuning
controller is a controller which performs simultaneous identification of the unknown
plant.
The operation of a self-tuning controller is as follows: at each time instant, the
estimator sends to the controller a set of estimated plant parameters (a in Figure 8.6),

320 Adaptive Control Chap. 8
which is computed based on the past plant input u and output y; the computer finds the
corresponding controller parameters, and then computes a control input u based on the
controller parameters and measured signals; this control input u causes a new plant
output to be generated, and the whole cycle of parameter and input updates is
repeated. Note that the controller parameters are computed from the estimates of the
plant parameters as if they were the true plant parameters. This idea is often called the
certainty equivalence principle.
controller plant
estimator
S — estimated parameters
Figure 8.6 : A self-tuning controller
Parameter estimation can be understood simply as the process of finding a set of
parameters that fits the available input-output data from a plant. This is different from
parameter adaptation in MRAC systems, where the parameters are adjusted so that the
tracking errors converge to zero. For linear plants, many techniques are available to
estimate the unknown parameters of the plant. The most popular one is the least-
squares method and its extensions. There are also many control techniques for linear
plants, such as pole-placement, PID, LQR (linear quadratic control), minimum
variance control, or H°° designs. By coupling different control and estimation
schemes, one can obtain a variety of self-tuning regulators. The self-tuning method
can also be applied to some nonlinear systems without any conceptual difference.
In the basic approach to self-tuning control, one estimates the plant parameters
and then computes the controller parameters. Such a scheme is often called indirect
adaptive control, because of the need to translate the estimated parameters into
controller parameters. It is possible to eliminate this part of the computation. To do
this, one notes that the control law parameters and plant parameters are related to each
other for a specific control method. This implies that we may reparameterize the plant
model using controller parameters (which are also unknown, of course), and then use
standard estimation techniques on such a model. Since no translation is needed in this
scheme, it is called a direct adaptive control scheme. In MRAC systems, one can

Sect. 8.1 Basic Concepts in Adaptive Control 321
similarly consider direct and indirect ways of updating the controller parameters.
Example 8.2 : Self-tuning control of the unknown mass
Consider the self-tuning control of the mass of Example 8.1. Let us still use the pole-placement
(placing the poles of the tracking error dynamics) control law (8.3) for generating the control
input, but let us now generate the estimated mass parameter using an estimation law.
Assume, for simplicity, that the acceleration can be measured by an accelerometer. Since the
only unknown variable in Equation (8.1) is m, the simplest way of estimating it is to simply
divide the control input u{t) by the acceleration x , i.e.,
m(t) = ^ (8.9)
x
However, this is not a good method because there may be considerable noise in the measurement
x, and, furthermore, the acceleration may be close to zero. A better approach is to estimate the
parameter using a least-squares approach, i.e., choosing the estimate in such a way that the total
prediction error
J=!e2(r)dr (8.10)
is minimal, with the prediction error e defined as
e{t) = m(t)x(t)-u(f)
The prediction error is simply the error in fitting the known input u using the estimated parameter
mm.. TThhiiss ttoottaall eerrrroorr mmiinnii:mization can potentially average out the effects of measurement noise.
The resulting estimate is
wudr
•*o (8.11)
f w2dr
with w = 'x. If, actually, the unknown parameter m is slowly time-varying, the above estimate has
to be recalculated at every new time instant. To increase computational efficiency, it is desirable
to adopt a recursive formulation instead of repeatedly using (8.11). To do this, we define
P(t) = ~ (8.12)
f wzdr
* o
The function P(t) is called the estimation gain, and its update can be directly obtained by using

322 Adaptive Control Chap. 8
i[P-']=w2 (8.13)
at
Then, differentiation of Equation (8.11) (which can be written P~' m= f w u dr ) leads to
}o
m = -P(t)we (8.14)
In implementation, the parameter estimate m is obtained by numerically integrating equations
(8.13) and (8.14), instead of using (8.11). Note that a number of other estimation methods can be
used to provide the estimate of the mass. Such methods and their properties are discussed in more
detail in section 8.7, together with a technique for avoiding the use of acceleration measurement
x, using instead velocity or position measurements. Q
It is seen from this example that, in self-tuning control, estimator design and
controller design are separated. The estimation law (using y and u) is independent of
the choice of the control law, unlike in MRAC design where the parameter adaptation
law is affected by the choice of the control law (it is also interesting to note that, in
self-tuning control, saturation of the control input has no direct consequence on the
convergence of parameter estimation). While this implies flexibility in design and
simplicity in concept, the analysis of the convergence and stability of the self-tuning
control system is usually more complicated.
RELATIONS BETWEEN MRAC AND ST METHODS
As described above, MRAC control and ST control arise from different perspectives,
with the parameters in MRAC systems being updated so as to minimize the tracking
errors between the plant output and reference model output, and the parameters in ST
systems being updated so as to minimize the data-fitting error in input-output
measurements. However, there are strong relations between the two design
methodologies. Comparing Figures 8.3 and 8.6, we note that the two kinds of systems
both have an inner loop for control and an outer loop for parameter estimation. From
a theoretical point of view, it can actually be shown that MRAC and ST controllers
can be put under a unified framework.
The two methods can be quite different in terms of analysis and
implementation. Compared with MRAC controllers, ST controllers are more flexible
because of the possibility of coupling various controllers with various estimators (i.e.,
the separation of control and estimation). However, the stability and convergence of
self-tuning controllers are generally quite difficult to guarantee, often requiring the
signals in the system to be sufficiently rich so that the estimated parameters converge
to the true parameters. If the signals are not very rich (for example, if the reference
signal is zero or a constant), the estimated parameters may not be close to the true
pamareters, and the stability and convergence of the resulting control system may not
1

Sect. 8.1 Basic Concepts in Adaptive Control 323
be guaranteed. In this situation, one must either introduce perturbation signals in the
input, or somehow modify the control law. In MRAC systems, however, the stability
and tracking error convergence are usually guaranteed regardless of the richness of the
signals.
Historically, the MRAC method was developed from optimal control of
deterministic servomechanisms, while the ST method evolved from the study of
stochastic regulation problems. MRAC systems have usually been considered in
continuous-time form, and ST regulators in discrete time-form. In recent years,
discrete-time version of MRAC controllers and continuous versions of ST controllers
have also been developed. In this chapter, we shall mostly focus on MRAC systems in
continuous form. Methods for generating estimated parameters for self-tuning control
are discussed in section 8.7.
8.1.3 How To Design Adaptive Controllers ?
In conventional (non-adaptive) control design, a controller structure {e.g., pole
placement) is chosen first, and the parameters of the controller are then computed
based on the known parameters of the plant. In adaptive control, the major difference
is that the plant parameters are unknown, so that the controller parameters have to be
provided by an adaptation law. As a result, the adaptive control design is more
involved, with the additional needs of choosing an adaptation law and proving the
stability of the system with adaptation.
The design of an adaptive controller usually involves the following three steps:
• choose a control law containing variable parameters
• choose an adaptation law for adjusting those parameters
• analyze the convergence properties of the resulting control system
These steps are clearly seen in Example 8.1.
When one uses the self-tuning approach for linear systems, the first two steps
are quite straightforward, with inventories of control and adaptation (estimation) laws
available. The difficulty lies in the analysis. When one uses MRAC design, the
adaptive controller is usually found by trial and error. Sometimes, the three steps are
coordinated by the use of an appropriate Lyapunov function, or using some symbolic
construction tools such as the passivity formalism. For instance, in designing the
adaptive control system of Example 8.1, we actually start from guessing the Lyapunov
function V (as a representation of total error) in (8.7) and choose the control and

324 Adaptive Control Chap. 8 ||
adaptation laws so that V decreases. Generally, the choices of control and adaptation
laws in MRAC can be quite complicated, while the analysis of the convergence
properties are relatively simple.
Before moving on to the application of the above procedure to adaptive control
design for specific systems, let us derive a basic lemma which will be very useful in
guiding our choice of adaptation laws for MRAC systems.
Lemma 8.1: Consider two signals e and <|> related by the following dynamic equation
(8.15)
where e(t) is a scalar output signal, H(p) is a strictly positive real transfer function, k
is an unknown constant with known sign, §(t) is a mxl vector function of time, and
\(f) is a measurable mxl vector. If the vector § varies according to
<j>(0 = -sgn(£)yev(0 (8.16)
with y being a positive constant, then e(t) and §(t) are globally bounded. Furthermore,
if\ is bounded, then
e(t) -> 0 as t -> oo
Note that while (8.15) involves a mixture of time-domain and frequency-domain
notations (with p being the Laplace variable), its meaning is clear: e(t) is the response
of the linear system of SPR transfer function H(p) to the input [k$T(t)\(t)] (with
arbitrary initial conditions). Such hybrid notation is common in the adaptive control
literature, and later on it will save us the definition of intermediate variables.
In words, the above lemma means that if the input signal depends on the output
in the form (8.16), then the whole system is globally stable (i.e., all its states are
bounded). Note that this is a feedback system, shown in Figure 8.7, where the plant
dynamics, being SPR, have the unique properties discussed in section 4.6.1.
Proof: Let the state-space representation of (8.15) be
x = Ax+b[*<frrvl (8.17a)
e = crx (8.17b)
Since H(p) is SPR, it follows from the Kalman-Yakubovich lemma in chapter 4 that given a
symmetric positive definite matrix Q, there exists another symmetric positive definite matrix P
such that
ArP+PA = -Q
J

Sect. 8.1 Basic Concepts in Adaptive Control 325
SPR
- sgn(k) y (t)
V
Figure 8.7 : A system containing a SPR transfer function
Pb =
Let V be a positive definite function of the form
!A!<|>7> (8.18)
Its time derivative along the trajectories of the system defined by (8.17) and (8.16) is
V =
= -xrQx<0 (8.19)
Therefore, the system defined by (8.15) and (8.16) is globally stable. The equations (8.18) and
(8.19) also imply that e and (|> are globally bounded.
If the signal v(/) is bounded, x is also bounded, as seen from (8.17a). This implies the
uniform continuity of V, since its derivative
is then bounded. Application of Barbalat's lemma of chapter 4 then indicates the asymptotic
convergence of e(l) to zero. CI
It is useful to point out that the system defined by (8.15) and (8.16) not only
guarantees the boundedness of e and <j>, but also that of the whole state x, as seen from
(8.18). Note that the state-space realization in (8.17) can be non-minimal (implying
the possibility of unobservable or uncontrollable modes) provided that the
unobservable and uncontrollable modes be stable, according to the Meyer-Kalman-
Yakubovich lemma. Intuitively, this is reasonable because stable hidden modes are
not affected by the choice of $.
In our later MRAC designs, the tracking error between the plant output and

326 Adaptive Control Chap. 8
reference model output will often be related to the parameter estimation errors by an
equation of the form (8.15). Equation (8.16) thus provides a technique for adjusting
the controller parameters while guaranteeing system stability. Clearly, the tracking-
error dynamics in (8.4) satisfy the conditions of Lemma 8.1 and the adaptation law is
in the form of (8.16).
8.2 Adaptive Control of First-Order Systems
Let us now discuss the adaptive control of first-order plants using the MRAC method,
as an illustration of how to design and analyze an adaptive control system. The
development can also have practical value in itself, because a number of simple
systems of engineering interest may be represented by a first-order model. For
example, the braking of an automobile, the discharge of an electronic flash, or the
flow of fluid from a tank may be approximately represented by a first-order
differential equation
y = -a y + b u (8.20)
p p
where y is the plant output, u is its input, and a and b are constant plant parameters.
p p
PROBLEM SPECIFICATION
In the adaptive control problem, the plant parameters a and b are assumed to be
p p
unknown. Let the desired performance of the adaptive control system be specified by
a first-order reference model
where a and b are constant parameters, and r(t) is a bounded external reference
m m
signal. The parameter a is required to be strictly positive so that the reference model
m
is stable, and b is chosen strictly positive without loss of generality. The reference
m
model can be represented by its transfer function M
where
M =
with p being the Laplace variable. Note that M is a SPR function.
The objective of the adaptive control design is to formulate a control law, and
i

Sect. 8.2 Adaptive Control of First-Order Systems 327
an adaptation law, such that the resulting model following error y{t) - y
m
asymptotically converges to zero. In order to accomplish this, we have to assume the
sign of the parameter b to be known. This is a quite mild condition, which is often
satisfied in practice. For example, for the braking of a car, this assumption amounts to
the simple physical knowledge that braking slows down the car.
CHOICE OF CONTROL LAW
As the first step in the adaptive controller design, let us choose the control law to be
u= a(t)r + a(t)y (8.22)
r y
where a and a are variable feedback gains. With this control law, the closed-loop
r y
dynamics are
y = -(a -a b )y + ab r{t) (8.23)
p y p r p
The reason for the choice of control law in (8.22) is clear: it allows the
possibility of perfect model matching. Indeed, if the plant parameters were known, the
following values of control parameters
a =— a =^— (8.24)
r
b b
p p
would lead to the closed-loop dynamics
which is identical to the reference model dynamics, and yields zero tracking error. In
this case, the first term in (8.22) would result in the right d.c. gain, while the second
term in the control law (8.22) would achieve the dual objectives of canceling the term
(- ay) in (8.20) and imposing the desired pole —a y.
m
In our adaptive control problem, since a and b are unknown, the control input
p
will achieve these objectives adaptively, i.e., the adaptation law will continuously
search for the right gains, based on the tracking error y - y , so as to make y tend to
m
y asymptotically. The structure of the adaptive controller is illustrated in Figure 8.8.
m
CHOICE OF ADAPTATION LAW
Let us now choose the adaptation law for the parameters a and a. Let
r y
e=y-y
m
be the tracking error. The parameter errors are defined as the difference between the

| 328  Adaptive Control |     | Chap. 8 |
| --------------------- | --- | ------- |
Figure 8.8 : A MRAC system for the first-order plant
controller parameter provided by the adaptation law and the ideal parameters, i.e.,
|       | . "A  *" |        |
| ----- | -------- | ------ |
|       | a a -a   |        |
| 5(0 = | r r r    | (8.25) |
A  *
|     | a a -a |     |
| --- | ------ | --- |
|     | y y y  |     |
The dynamics of tracking error can be found by subtracting (8.23) from (8.21),
b a )y + (b a - b )r
r m
| = - a m | e + b p (ar + ay) r y | (8.26) |
| ------- | --------------------- | ------ |
This can be conveniently represented as
| b     |   ~  ~  1  ~       |        |
| ----- | ------------------ | ------ |
| e = D |                    | (8.27) |
| —i    | —(ar+ay)  =  —M(ar |        |
r y r
with p denoting the Laplace operator.
Relation (8.27) between the parameter errors and tracking error is in the familiar
form given by (8.15). Thus, Lemma 8.1 suggests the following adaptation law
| a = - sgn(b | ) yer | (8.28a) |
| ----------- | ----- | ------- |
| r           | p     |         |
| a  =-sgn(b  | )yey  | (8.28b) |
with y being a positive constant representing the adaptation gain.  From (8.28), it is
seen that  sgn(fe )  determines the direction of the search for the proper controller
parameters.

Sect. 8.2 Adaptive Control of First-Order Systems 329
TRACKING CONVERGENCE ANALYSIS
With the control law and adaptation law chosen above, we can now analyze the
system's stability and convergence behavior using Lyapunov theory, or equivalently
Lemma 8.1. Specifically, the Lyapunov function candidate
V(e, *) = I e2 + 1 \b \(a2 + a 2) (8.29)
p y
can be easily shown to have the following derivative along system trajectories
V=-a e2
Thus, the adaptive control system is globally stable, i.e., the signals e, a and a are
r
bounded. Furthermore, the global asymptotic convergence of the tracking error e{t) is
guaranteed by Barbalat's lemma, because the boundedness of e, a and a implies the
r y
boundedness of e (according to (8.26)) and therefore the uniform continuity of V.
It is interesting to wonder why the adaptation law (8.28) leads to tracking error
convergence. To understand this, let us see intuitively how the control parameters
should be changed. Consider, without loss of generality, the case of a positive
sgn(&A Assume that at a particular instant t the tracking error e is negative,
indicating that the plant output is too small. From (8.20), the control input u should be
increased in order to increase the plant output. From (8.22), an increase of the control
input u can be achieved by increasing a (assuming that r{t) is positive). Thus, the
r
adaptation law, with the variation rate of a depending on the product of sgn(£>), r and
r
e, is intuitively reasonable. A similar reasoning can be made about a .
y
The behavior of the adaptive controller is demonstrated in the following
simulation example.
Example 8.3: A first-order plant
Consider the control of the unstable plant
y = y + 3«
using the previously designed adaptive controller. The plant parameters a =-l,b =3 are
assumed to be unknown to the adaptive controller. The reference model is chosen to be
i.e., a = 4, b = 4. The adaptation gain y is chosen to be equal to 2. The initial values of both
m m
parameters of the controller are chosen to be 0, indicating no a priori knowledge. The initial
conditions of the plant and the model are both zero.

| 330  | Adaptive  Control |     |     |     | Chap. 8 |
| ---- | ----------------- | --- | --- | --- | ------- |
Two different reference signals are used in the simulation:
• lit) = 4. It is seen from Figure 8.9 that the tracking error converges to zero but the
parameter error does not.
•  r(t) - 4 sin(3 f).  It is seen  from  Figure 8.10  that  both the tracking error  and
|       | parameter error converge to zero.  |     |     |     | D   |
| ----- | ---------------------------------- | --- | --- | --- | --- |
| 5.0 r |                                    |     | 2.0 |     |     |
1.5
1.0
•g 3.5
| a. 3.0 |     |     | 0.5 |     |     |
| ------ | --- | --- | --- | --- | --- |
DO
| 2.5 |     |     | 0.0  |     |     |
| --- | --- | --- | ---- | --- | --- |
| 2.0 |     | g   | -0-5 |     |     |
1.5
°- -1.0
1.0
| 0.5 |          |               | -1.5         |      |           |
| --- | -------- | ------------- | ------------ | ---- | --------- |
| 0.0 |          |               | -2.0         |      |           |
| 0.0 | 1.0  2.0 | 3.0  4.0  5.0 | 0.0  1.0 2.0 | 3.0  | 4.0  5.0  |
|     |          | time(sec)     |              |      | time(sec) |
Figure 8.9 : Tracking performance and parameter estimation, r(t) = 4
2.0
1.5
1.0
0.5
0.0
-0.5
-1.0
-1.5
-2.0
|     | 2.0 4.0  | 6.0  8.0  10.0 | 0.0  2.0  4.0 | 6.0  | 8.0  10.0 |
| --- | -------- | -------------- | ------------- | ---- | --------- |
|     |          | time(sec)      |               |      | time(sec) |
Figure 8.10 : Tracking performance and parameter estimation, r(t) = 4 sin(31)
Note  that,  in the above  adaptive  control  design,  although  the stability  and
convergence of the adaptive controller is guaranteed for any positive j, a  and b   , the
m m
performance  of the adaptive controller will depend critically on y. If a small gain is
chosen,  the adaptation  will  be slow  and the transient  tracking  error  will  be  large.
Conversely,  the magnitude  of  the  gain  and, accordingly,  the performance  of the
adaptive control system, are limited by the excitation of unmodeled dynamics, because
too large an adaptation gain will lead to very oscillatory parameters.

Sect. 8.2 Adaptive Control of First-Order Systems 331
PARAMETER CONVERGENCE ANALYSIS
In order to gain insights about the behavior of adaptive control system, let us
understand the convergence of estimated parameters. From the simulation results of
Example 8.3, one notes that the estimated parameters converge to the exact parameter
values for one reference signal but not for the other. This prompts us to speculate a
relation between the features of the reference signals and parameter convergence, i.e.,
the estimated parameters will not converge to the ideal controller parameters unless
the reference signal r(t) satisfies certain conditions.
Indeed, such a relation between the features of reference signal and
convergence of estimated parameters can be intuitively understood. In MRAC
systems, the objective of the adaptation mechanism is to find out the parameters which
drive the tracking error y - y to zero. If the reference signal r(t) is very simple, such
m
as a zero or a constant, it is possible for many vectors of controller parameters, besides
the ideal parameter vector, to lead to tracking error convergence. Then, the adaptation
law will not bother to find out the ideal parameters. Let Q. denote the set composed of
all the parameter vectors which can guarantee tracking error convergence for a
particular reference signal history r(t). Then, depending on the initial conditions, the
vector of estimated parameters may converge to any point in the set or wonder around
in the set instead of converging to the true parameters. However, if the reference
signal r(t) is so complex that only the true parameter vector a* = \a* a*]T can lead
y
to tracking error convergence, then we shall have parameter convergence.
Let us now find out the exact conditions for parameter convergence. We shall
use simplified arguments to avoid tedious details. Note that the output of the stable
filter in (8.27) converges to zero and that its input is easily shown to be uniformly
continuous. Thus, ar + ay must converge to zero. From the adaptation law (8.28)
r y
and the tracking error convergence, the rate of the parameter estimates converges to
zero. Thus, when time t is large, a is almost constant, and
i.e.,
vT(t) 2 = 0 (8.30)
with
v = [r y]T a = [a,. af
y
Here we have one equation (with time-varying coefficients) and two variables. The
issue of parameter convergence is reduced to the question of what conditions the

332 Adaptive Control Chap. 8
vector [r(t) y(t)]T should satisfy in order for the equation to have a unique zero
solution.
If r(f) is a constant r , then for large t,
0
with a being the d.c. gain of the reference model. Thus,
[r y] = U «]r
0
Equation (8.30) becomes
a + aa = 0
r
Clearly, this implies that the estimated parameters, instead of converging to zero,
converge to a straight line in parameter space. For Example 8.3, with a = 1, the above
equation implies that the steady state errors of the two parameters should be of equal
magnitudes but opposite signs. This is obviously confirmed in Figure 8.9.
However, when r{t) is such that the corresponding signal vector v(t) satisfies the
so called "persistent excitation" condition, we can show that (8.28) will guarantee
parameter convergence. By persistent excitation of v, we mean that there exist strictly
positive constants ccj and T such that for any t > 0,
'+ ra l (8.31)
1
To show parameter convergence, we note that multiplying (8.30) by v(0 and
integrating the equation for a period of time T, leads to
Ct + T T ~
vvJdra = 0
Condition (8.31) implies that the only solution of this equation is a = 0, i.e., parameter
error being zero. Intuitively, the persistent excitation of v(f) implies that the vectors
v(f) corresponding to different times t cannot always be linearly dependent.
The only remaining question is the relation between r(t) and the persistent
excitation of \(t). One can easily show that, in the case of the first order plant, the
persistent excitation of v can be guaranteed, if r(t) contains at least one sinusoidal
component.

| Sect. 8.2  |     | Adaptive Control of First-Order Systems  | 333 |
| ---------- | --- | ---------------------------------------- | --- |
EXTENSION TO NONLINEAR PLANTS
The same method of adaptive control design can be used for the nonlinear first-order
plant described by the differential equation
|     | y = -a y-c | f(y)  + b u  | (8.32) |
| --- | ---------- | ------------ | ------ |
|     | p          | p p          |        |
where /  is any known nonlinear function.  The nonlinearity in these dynamics is
characterized by its linear parametrization in terms of the unknown constant c. Instead
of using the control law (8.22), we now use the control law
|     | u = a y y + af(y) + ar  | f r | (8.33) |
| --- | ----------------------- | --- | ------ |
where the second term is introduced with the intention of adaptively canceling the
nonlinear term.
Substituting  this control  law into the dynamics  (8.32) and subtracting the
resulting equation by (8.21), we obtain the error dynamics
1  ~
| e = —M( a | y + af(y) + ar) |     |     |
| --------- | --------------- | --- | --- |
|           | y               | f r |     |
k
r
where the parameter error 5yis defined as
|     | ~  A   | cp  |     |
| --- | ------ | --- | --- |
By choosing the adaptation law
A
|     | a  = -sgn(b | )yey  | (8.34a) |
| --- | ----------- | ----- | ------- |
|     | y           | p     |         |
|     | a=  ~sgn(b  | )yef  | (8.34b) |
|     | f           | p     |         |
|     | a -  -sgn(b | )yer  | (8.34c) |
|     | r           | p     |         |
one can similarly show that the tracking error e converges to zero, and the parameter
error remains bounded.
As for parameter convergence, similar arguments as before  can reveal the
convergence  behavior of the estimated  parameters.  For constant  reference  input
r = r , the estimated parameters converge to the line (with a still being the d.c. gain of
0
the reference model)
=0
which is a straight line in the three-dimensional parameter space.  In order for the

334 Adaptive Control Chap. 8
parameters to converge to the ideal values, the signal vector v = [r(t) y(t) f(y)]T
should be persistently exciting, i.e., there exists positive constants ocj and T such that
for any time f > 0,
,r+r \vTdr> a, I
Generally speaking, for linear systems, the convergent estimation of m
parameters require at least m/2 sinusoids in the reference signal r(t), as will be
discussed in more detail in sections 8.3 and 8.4. However, for this nonlinear case,
such simple relation may not be valid. Usually, the qualitative relation between r{t)
and v(0 is dependent on the particular nonlinear functions/(y). It is unclear how many
sinusoids in r(t) are necessary to guarantee the persistent excitation of v(t).
The following example illustrates the behavior of the adaptive system for a
nonlinear plant.
Example 8.4: simulation of a first-order nonlinear plant
Assume that a nonlinear plant is described by the equation
y- (8.35)
This differs from the unstable plant in Example 8.3 in that a quadratic term is introduced in the
plant dynamics.
Let us use the same reference model, initial parameters, and design parameters as in Example
8.3. For the reference signal r(r) = 4, the results are shown in Figure 8.11. It is seen that the
tracking error converges to zero, but the parameter errors are only bounded. For the reference
signal r(l) = 4sin(3(), the results are shown in Figure 8.12. It is noted that the tracking error and
the parameter errors for the three parameters all converge to zero. LJ
In this example, it is interesting to note two points. The first point is that a
single sinusoidal component in r(t) allows three parameters to be estimated. The
second point is that the various signals (including a and y) in this system are much
more oscillatory than those in Example 8.3. Let us understand why. The basic reason
is provided by the observation that nonlinearity usually generates more frequencies,
and thus v(t) may contain more sinusoids than r(t). Specifically, in the above example,
with /-(0 = 4sin(31), the signal vector v converges to
v(t) = [r(t) y (t) f (t)]
ss ss
where yjj) is the steady-state response and f (t) the corresponding function value,
s ss

Sect. 8.3  Adaptive Control of Linear Systems With Full State Feedback  335
| o 5.0 |     | 1.8 |     |     |
| ----- | --- | --- | --- | --- |
4.5
| K     |     | 1.6 |     |     |
| ----- | --- | --- | --- | --- |
| O 4.0 |     | 1.4 |     |     |
frepg
| 3.5 |     | 1.2 |     |     |
| --- | --- | --- | --- | --- |
| 3.0 |     | 1.0 |     |     |
a 2.5
0.8
kca 2.0
0.6
£3 1.5
0.4
1.0
0.2
0.5
| 0.0       |          | 0.0 >     |                |          |
| --------- | -------- | --------- | -------------- | -------- |
| 0.0  0.5  | 1.0  1.5 | 0.0  0.5  | 1.0  1.5  2.0  | 2.5  3.0 |
2.0  2.5  3.0
|     | time(sec) |     | time(sec) |     |
| --- | --------- | --- | --------- | --- |
| 0.2 |           | 0.4 |           |     |
o
| 0.0 |     | 0.2 |     |     |
| --- | --- | --- | --- | --- |
03
| e -0.2 |     | 0.0 |     |     |
| ------ | --- | --- | --- | --- |
w
| -0.4           |     | -0.2 |     |     |
| -------------- | --- | ---- | --- | --- |
| reteU1EJ1 -0.6 |     | -0.4 |     |     |
-0.6
| -L0  |     | -0.8 |     |     |
| ---- | --- | ---- | --- | --- |
| -1.2 |     | -1.0 |     |     |
-1.2
-1.4
| -1.6 |     | -1.4 |     |     |
| ---- | --- | ---- | --- | --- |
| -1.8 |     | -1.6 |     |     |
0.0  0.5  1.0  1.5 2.0  2.5  3.0 0.0  0.5  1.0  1.5 2.0  2.5  3.0
|     | time(sec) |     | time(sec) |     |
| --- | --------- | --- | --------- | --- |
Figure 8.11 : Adaptive control of a first-order nonlinear system, r(t) = 4
upper left: tracking performance
upper right: parameter a ; lower left: parameter a  ; lower right: parameter as
r
2  = 16A2sin2(3r + (J>) = 8 A2( 1 - cos(6? •
f (t)  = y
| ss  | ss  |     |     |     |
| --- | --- | --- | --- | --- |
where A and <|) are the magnitude and phase shift of the reference model at co = 3.
Thus, the signal vector v(t) contains two sinusoids, with/(jy) containing a sinusoid at
twice the original frequency. Intuitively, this component at double frequency  is the
reason for the convergent estimation of the three parameters and the more oscillatory
behavior of the estimated parameters.
Adaptive Control of Linear Systems With Full State
Feedback
Let us now move on to adaptive control design for more general systems.  In this
section, we shall study the adaptive control of linear systems when the full state is
measurable.  We  consider  the  adaptive  control  of  «th-order  linear  systems  in

| 336  Adaptive Control |     |     | Chap. 8 |
| --------------------- | --- | --- | ------- |
| 4.0                   |     | 1.8 |         |
1.6
1 3.0
1.4
2.0
1.2
1.0
1.0
0.0
0.8
| -1.0     |     | 0.6            |                |
| -------- | --- | -------------- | -------------- |
| -2.0     |     | 0.4            |                |
| -3.0     |     | 0.2            |                |
| -4.0     |     | 0.0            |                |
| 0.0  2.0 |     | 0.0  2.0  4.0  | 6.0  8.0  10.0 |
4.0  6.0  8.0  10.0
|     | time(sec) |     | time(sec) |
| --- | --------- | --- | --------- |
0.5
| B  -0.5 - |                | 0.0       |                    |
| --------- | -------------- | --------- | ------------------ |
| -1.0 -    |                | -0-5      |                    |
| -1.5 -    |                | -1.0      |                    |
| -2.0      |                | -1.5      |                    |
|           | 6.0  8.0  10.0 | 0.0  2.0  | 4.0 6.0  8.0  10.0 |
|           | time(sec)      |           | time(sec)          |
Figure 8.12 : Adaptive control of a first-order nonlinear system, r{t) = 4sin(3t)
upper left: tracking performance
upper right: parameter a ; lower left: parameter a  r ; lower right: parameter ay-
companion form:
(8.36)
••••+ a oy  =
where the state components  y,y,...  ,y(n~^  are measurable.  We assume that the
 ]T is unknown, but that the sign of a
| coefficient vector a = [ a |  ...  aj  a |     |  is assumed |
| -------------------------- | ----------- | --- | ----------- |
|                            | n o         |     | n           |
to be known.  An example of such systems is the dynamics of a mass-spring-damper
system
my + cy + ky = u
where we measure position and velocity (possibly with an optical encoder for position
measurement,  and a tachometer for velocity  measurement, or simply  numerically
differentiate the position signals).
The objective of the control system is to make y closely track the response of a
stable reference model

Sect. 8.3  Adaptive Control of Linear Systems With Full State Feedback  337
| <Wfl) + *n-\y | {n-l)  + ••••+ °w*  | = >it)  |     | (8.37) |
| ------------- | ------------------- | ------- | --- | ------ |
m
with r{t) being a bounded reference signal.
CHOICE OF CONTROL LAW
Let us define a signal z(t) as follows
with Pj,..., fi  being positive constants chosen such that pn  +  fi _ipn~l  + .... + P  is a
| n   |     |     | n   | o   |
| --- | --- | --- | --- | --- |
stable  (Hurwitz)  polynomial.  Adding  (- a n z(t))  to  both  sides  of  (8.36)  and
rearranging, we can rewrite the plant dynamics as
Let us choose the control law to be
|              | ^»-l'> + ....+a | = \r(t)a(t)  |     |        |
| ------------ | --------------- | ------------ | --- | ------ |
| «= a n z + a | n _ x           | o y          |     | (8.39) |
where \(t) = [z(t) y("~V  ....y  y]T and
| A,.  rAA  | AA  nT             |     |     |     |
| --------- | ------------------ | --- | --- | --- |
| a(t) = [a |  a _  .... a,  aj' |     |     |     |
| n         | n l                |     |     |     |
denotes the estimated parameter vector. This represents a pole-placement controller
which places the poles at positions specified by the coefficients P,-. The tracking error
e = y - y   then satisfies the closed-loop dynamics
m
| a [eW + p | _,O»-l) + .... + %e] = vT(t) a(r)  |     |     | (8.40) |
| --------- | ---------------------------------- | --- | --- | ------ |
| n         | n e                                |     |     |        |
where
~  A
a =a -a
CHOICE OF ADAPTATION LAW
Let us now choose the parameter adaptation law. To do this, let us rewrite the closed-
loop error dynamics (8.40) in state space form,
| k = Ax + b[(l/a | )vTa]  |     |     | (8.41a) |
| --------------- | ------ | --- | --- | ------- |
n
| e = cx  |     |     |     | (8.41b) |
| ------- | --- | --- | --- | ------- |
where

338  Adaptive Control Chap. 8
| 0 1 | 0 . .  0 | 0   |
| --- | -------- | --- |
| 0 0 | 1        | 0   |
b =
| 0 0 | 0 1 |     |
| --- | --- | --- |
0
"Po-Pi -P
|     | 2 • • -Pn-1 | 1   |
| --- | ----------- | --- |
c = [l  0 . .  0 0]
Consider the Lyapunov function candidate
where both F and P are symmetric positive definite constant matrices, and P satisfies
| PA + ATP = -Q  | Q = Qr>0 |     |
| -------------- | -------- | --- |
for a chosen Q. The derivative V can be computed easily as
V = - xrQx + 2aTvbTPx + 2 arr-lS
Therefore, the adaptation law
a = -TvbrPx  (8.42)
leads to
One can easily show the convergence of x using Barbalat's lemma.  Therefore, with
the adaptive controller defined by control law (8.39) and adaptation law (8.42), e and
its (n-1) derivatives converge to zero.  The parameter convergence condition can
again be shown to be the persistent excitation of the vector v.  Note that a similar
design can be made for nonlinear systems in the controllability canonical form, as
discussed in section 8.5.

Sect. 8.4 Adaptive Control of Linear Systems With Output Feedback 339
8.4 Adaptive Control of Linear Systems With Output
Feedback
In this section, we consider the adaptive control of linear systems in the presence of
only output measurement, rather than full state feedback. Design in this case is
considerably more complicated than when the full state is available. This partly arises
from the need to introduce dynamics in the controller structure, since the output only
provides partial information about the system state. To appreciate this need, one can
simply recall that in conventional design (no parameter uncertainty) a controller
obtained by multiplying the state with constant gains (pole placement) can stabilize
systems where all states are measured, while additional observer structures must be
used for systems where only outputs are measured.
A linear time-invariant system can be represented by the transfer function
where
... + a _pn~\ + pn
n x
where k is called the high-frequency gain. The reason for this term is that the plant
p
frequency response at high frequency verifies
\W(j<o)\ « —P-
i.e., the high frequency response is essentially determined by k . The relative degree r
p
of this system is r = n-m. In our adaptive control problem, the coefficients a-, b:
(
(i = 0, 1,..., n—\;j =0, 1, , m—l) and the high frequency gain k are all assumed to
p
be unknown.
The desired performance is assumed to be described by a reference model with
transfer function
W (p) = k Z-p- (8.44)
m m
Rm
where Z and R are monic Hurwitz polynomials of degrees n and m , and k is
m m m m m
positive. It is well known from linear system theory that the relative degree of the

340 Adaptive Control Chap. 8
reference model has to be larger than or equal to that of the plant in order to allow the
possibility of perfect tracking. Therefore, in our treatment, we will assume that
n -m >n-m.
m m
The objective of the design is to determine a control law, and an associated
adaptation law, so that the plant output y asymptotically approaches y . In
m
determining the control input, the output y is assumed to be measured, but no
differentiation of the output is allowed, so as to avoid the noise amplification
associated with numerical differentiation. In achieving this design, we assume the
following a priori knowledge about the plant:
• the plant order n is known
• the relative degree n- mis known
• the sign of k is known
p
• the plant is minimum-phase
Among the above assumptions, the first and the second imply that the model
structure of the plant is known. The third is required to provide the direction of
parameter adaptation, similarly to (8.28) in section 8.2. The fourth assumption is
somewhat restrictive. It is required because we want to achieve convergent tracking in
the adaptive control design. Adaptive control of non-minimum phase systems is still a
topic of active research and will not be treated in this chapter.
In section 8.4.1, we discuss output-feedback adaptive control design for linear
plants with relative degree one, i.e., plants having one more pole than zeros. Design
for these systems is relatively straightforward. In section 8.4.2, we discuss output-
feedback design for plants with higher relative degree. The design and
implementation of adaptive controllers in this case is more complicated because it is
not possible to use SPR functions as reference models.
8.4.1 Linear Systems With Relative Degree One
When the relative degree is 1, i.e., m = n— 1, the reference model can be chosen to be
SPR. This choice proves critical in the development of globally convergent adaptive
controllers.
CHOICE OF CONTROL LAW
To determine the appropriate control law for the adaptive controller, we must first
know what control law can achieve perfect tracking when the plant parameters are

Sect. 8.4 Adaptive Control of Linear Systems With Output Feedback 341
perfectly known. Many controller structures can be used for this purpose. The
following one, although somewhat peculiar, is particularly convenient for later
adaptation design.
Example 8.5: A controller for perfect tracking
Consider the plant described by
kJp + b )
n
(8.45)
and the reference model
(8.46)
2
P +amlP+am2
y (t)
m
w ( )
mP
r(t)
W (p)
p
Figure 8.13 : A model-reference control system for relative degree 1
Let the controller be chosen as shown in Figure 8.13, with the control law being
u = 0CiZ + y + kr (8.47)
P + bm
where z = u/(p + b ), i.e., z is the output of a first-order filter with input u, and CX| , p| ,p , k are
m 2
controller parameters. If we take these parameters to be
_am\-ap\
P| =

342 Adaptive Control Chap. 8
k
Kp
one can straightforwardly show that the transfer function from the reference input r to the plant
output y is
P
Therefore, perfect tracking is achieved with this control law, i.e., y(t) = y {t), V/ > 0.
m
It is interesting to see why the closed-loop transfer function can become exactly the same as
that of the reference model. To do this, we note that the control input in (8.47) is composed of
three parts. The first part in effect replaces the plant zero by the reference model zero, since the
transfer function from Mj to y (see Figure 8.13) is
The second part places the closed-loop poles at the locations of those of the reference model.
This is seen by noting that the transfer function from u to y is (Figure 8.13)
0
The third part of the control law (k /k)r obviously replaces k , the high frequency gain of the
m p p
plant, by k . As a result of the above three parts, the closed-loop system has the desired transfer
m
function. D
The controller structure shown in Figure 8.13 for second-order plants can be
extended to any plant with relative degree one. The resulting structure of the control
system is shown in Figure 8.14, where k* , 0j* ,02* and 0 * represents controller
O
parameters which lead to perfect tracking when the plant parameters are known.
The structure of this control system can be described as follows. The block for
generating the filter signal ci)[ represents an (« - l)tn order dynamics, which can be
described by
(»1 = Aooj + hu
where (Oj is an (n— l)xl state vector, A is an («- l)x(n-1) matrix, and h is a constant
vector such that (A, h) is controllable. The poles of the matrix A are chosen to be the

Sect. 8.4 Adaptive Control of Linear Systems With Output Feedback 343
r(t)
1 v-
Figure 8.14 : A control system with perfect tracking
same as the roots of the polynomial Z (p), i.e.,
m
dct[pl-A] =Z (p) (8.48)
m
The block for generating the («— l)xl vector oo has the same dynamics but with y as
2
input, i.e.,
d) = Aco + hy
2 2
It is straightforward to discuss the controller parameters in Figure 8.14. The scalar
gain k* is defined to be
and is intended to modulate the high-frequency gain of the control system. The vector
9j* contains (w-1) parameters which intend to cancel the zeros of the plant. The
vector 0 * contains (n-1) parameters which, together with the scalar gain 0 * can
2 O
move the poles of the closed-loop control system to the locations of the reference
model poles. Comparing Figure 8.13 and Figure 8.14 will help the reader become
familiar with this structure and the corresponding notations.
As before, the control input in this system is a linear combination of the
reference signal r(t), the vector signal (a obtained by filtering the control input u, the
l
signals 0) obtained by filtering the plant output y, and the output itself. The control
2
input u can thus be written, in terms of the adjustable parameters and the various

344 Adaptive Control Chap. 8
signals, as
u*{t) = k* r +8,*«)+e*a)+ Q*y (8.49)
1 2 2
Corresponding to this control law and any reference input r(t), the output of the plant
is
(8.50)
since these parameters result in perfect tracking. At this point, one easily sees the
reason for assuming the plant to be minimum-phase: this allows the plant zeros to be
canceled by the controller poles.
In the adaptive control problem, the plant parameters are unknown, and the
ideal control parameters described above are also unknown. Instead of (8.49), the
control law is chosen to be
u = k{t)r + 9 (0<» + 6 (0(»2 + QoW)1 (8-51)
1 1 2
where k(t), 0](O ,9 (0 and Q (t) are controller parameters to be provided by the
2 0
adaptation law.
CHOICE OF ADAPTATION LAW
For notational simplicity, let 8 be the 2/ixl vector containing all the controller
parameters, and oo be the 2« x 1 vector containing the corresponding signals, i.e.,
9(0 = WO 6i(f) 9 (0 %(t)]T
2
(o(t) = [r(t) oo,(O oo(O y(t)]T
2
Then the control law (8.51) can be compactly written as
u = QT(t)(o{t) (8.52)
Denoting the ideal value of 6 by 0* and the error between 9(0 and 9 by
<|>(0 = 9(f) - 9*, the estimated parameters 9(t) can be represented as
9(0 = 9* + (j)(0
Therefore, the control law (8.52) can also be written as
In order to choose an adaptation law so that the tracking error e converges to zero, we

Sect. 8.4 Adaptive Control of Linear Systems With Output Feedback 345
have to first find out how the tracking error is related to the parameter error. Let us use
a simple technique for this purpose.
With the control law given in (8.52), the control system with variable gains can
be equivalently represented as shown in Figure 8.15, with <^(t)(o/k* regarded as an
external signal. Since the ideal parameter vector 0* is such that the plant output in
Figure 8.15 is given by (8.50), the output here must be
y(0 = (8.53)
Figure 8.15 : An equivalent control system for time-varying gains
Since y (t) = W {p)r, the tracking error is seen to be related to the parameter error by
m m
the simple equation
e(t) = W (p) [§T(t)(o(t)/k*] (8.54)
m
Since this is the familiar equation seen in Lemma 8.1, the following adaptation law is
chosen
= -sgn(k )ye(t)(o(t) (8.55)
where y is a positive number representing the adaptation gain and we have used the
fact that the sign of k* is the same as that of k , due to the assumed positiveness of
"w •
Based on Lemma 8.1 and through a straightforward procedure for establishing
signal boundedness, one can show that the tracking error in the above adaptive control
system converges to zero asymptotically.

346 Adaptive Control Chap. 8
8.4.2 Linear Systems With Higher Relative Degree
The design of adaptive controller for plants with relative degree larger than 1 is both
similar to, and different from, that for plants with relative degree 1. Specifically, the
choice of control law is quite similar but the choice of adaptation law is very different.
This difference comes from the fact that the reference model now cannot be SPR.
CHOICE OF CONTROL LAW
We can show that the controller part of the system in Figure 8.15 is also applicable to
plants with relative degree larger than 1, leading to exact tracking when the plant
parameters are exactly known. Let us again start from a simple example.
Example 8.6: Consider the second order plant described by the transfer function
ku
p
y=-^—
and the reference model
k r
m
which are similar to those in Example 8.5, but now contain no zeros.
Let us consider the control structure shown in Figure 8.16 which is a slight modification of
the controller structure in Figure 8.13. Note that b in the filters in Figure 8.13 has been replaced
m
by a positive number X . Of course, the transfer functions W and W in Figure 8.16 now have
o m
relative degree 2.
The closed-loop transfer function from the reference signal r to the plant output y is
P + Kk
P
1 + -
p + X i + a p + a
o p pl p2
Therefore, if the controller parameters a , P, , $ > arK^ ^ are chosen such that
x 2
{p + X + a,) (p2 + a p + a ) + k($ + P) = {p + \,)(p2 +a p + a )
o pX p2 p ]P 2 ml m2
and

Sect. 8.4 Adaptive Control of Linear Systems With Output Feedback 347
m
w ( )
mP
r(t)
u y ' •.
k W p (p)
+ s
J
al
P + X 0
Pjp+P
2
P+X
o
Figure 8.16 : A model-reference control system for relative degree 2
then the closed loop transfer function W becomes identically the same as that of the reference
model. Clearly, such choice of parameters exists and is unique. D
For general plants of relative degree larger than 1, the same control structure as
given in Figure 8.14 is chosen. Note that the order of the filters in the control law is
still («- 1). However, since the model numerator polynomial Z (p) is of degree
m
smaller than (« - 1), it is no longer possible to choose the poles of the filters in the
controller so that det[pl - A] = Z (p) as in (8.48). Instead, we now choose
m
(8.57)
where X{p) = det[pl - A] and X^(p) is a Hurwitz polynomial of degree (n - 1 - m).
With this choice, the desired zeros of the reference model can be imposed.
Let us denote the transfer function of the feedforward part (M/MJ) of the
controller by X(p)/(k{p) + C(p)), and that of the feedback part by D(p)/X(p), where
the polynomial C(p) contains the parameters in the vector 0j, and the polynomial
D(p) contains 0 and the parameters in the vector 0 . Then, the closed-loop transfer
O 2
function is easily found to be
kk Z X{p)Z { )
p p x m P
W =— (8.58)
ry R

| 348  Adaptive Control  |     |     | Chap. 8 |
| ---------------------- | --- | --- | ------- |
The question now is whether in this general case there exist choice of values for
k, 6  , 0 ( and 9  such that the above transfer function becomes exactly the same as
0 2
W m (p), or equivalently
| R p (Up)+ C(p)) + k | p Z p D{p) = ^ZpRJp)  |     | (8.59) |
| ------------------- | --------------------- | --- | ------ |
The answer to this question can be obtained from the following lemma:
Lemma 8.2: Let A{p) and B(p) be polynomials of degree nj and W2» respectively. If
A(p) and B(p) are relatively prime, then there exist polynomials M(p) and N(p) such
that
| A(p)M(p)  + B(p)N(p)  | = A*(p)  |     | (8.60) |
| --------------------- | -------- | --- | ------ |
where A*(p) is an arbitrary polynomial.
This lemma can be used straightforwardly  to answer our question regarding
(8.59).  By regarding R  as A(p) in the lemma, k Z  as B(P) and X^(p)Z R   as
| p   |     | p   | p m |
| --- | --- | --- | --- |
A*{p), we conclude that there exist polynomials  (X(p) + C(p)) and D(p) such that
(8.59) is satisfied. This implies that a proper choice of the controller parameters
|                 |   el = 0l  | e2 = e2 |     |
| --------------- | ---------- | ------- | --- |
| k = k  6 O  = 0 | O          |         |     |
exists so that exact model-following is achieved.
CHOICE OF ADAPTATION LAW
When the plant parameters are unknown, we again use a control law of the form
(8.52), i.e.,
| u = QT(t)<o(t)  |     |     | (8.61) |
| --------------- | --- | --- | ------ |
with the 2n controller parameters in 8(0 provided by the adaptation law. Using a
similar reasoning as before, we can again obtain the output y in the form of (8.53) and
the tracking error in the form of (8.54), i.e.,
| e(t) = W (p)WTG>/k*}  |     |     | (8.62) |
| --------------------- | --- | --- | ------ |
m
However, the choice of adaptation law given by (8.55) cannot be used, because now
the reference model transfer function W (p) is no longer SPR. A famous technique
m
called error augmentation can be used to avoid the difficulty in finding an adaptation
law for (8.62). The basic idea of the technique is to consider a so-called augmented
error t(t) which correlates to the parameter error <|> in a more desirable way than the
tracking error eit).

Sect. 8.4 Adaptive Control of Linear Systems With Output Feedback  349
(o(t) e (t)  e (t)
Figure 8.17 : The augmented error
Specifically, let us define an auxiliary error x\(f) by
| = eT(t)W ( )[o)]  | - W (p)[QT(t)(0(t)] | (8.63) |
| ----------------- | ------------------- | ------ |
| m P               | m                   |        |
as shown in Figure 8.17.  It is useful to note two features about this error. First, r\(t)
can be computed on-line, since the estimated parameter vector. 0(f) and the signal
vector (o(t) are both available. Secondly, this error is caused by the time-varying
nature of the estimated parameters 8(f), in the sense that when 8(0 is replaced by the
true (constant) parameter vector 9*, we have
| Q*TW (p)[o>] - W | (p)[Q*Tw(t)] = 0 |     |
| ---------------- | ---------------- | --- |
| m                | m                |     |
This also implies that T| can be written
Now let us define an augmented error £(t), by combining the tracking error e(t)
with the auxiliary error r)(?) as
| = e{t) + <x(0 ri(0 |     | (8.64) |
| ------------------ | --- | ------ |
where a(t) is a time-varying parameter to be determined by adaptation. Note that oc(r)
is not a controller parameter, but only a parameter used in forming the new error e(0-
For convenience, let us write a(t) in the form
k
where (J) = a(t) -1.  Substituting (8.62) and (8.63) into (8.64), we obtain
a

350 Adaptive Control Chap. 8
lr (8.65)
where
(8.66)
This implies that the augmented error can be linearly parameterized by the parameter
errors (|>(0 and <j>. Equation (8.65) thus represents a form commonly seen in system
a
identification. A number of standard techniques to be discussed in section 8.7, such as
the gradient method or the least-squares method, can be used to update the parameters
for equations of this form. Using the gradient method with normalization, the
controller parameters 9(f) and the parameter oc(f) for forming the augmented error are
updated by
sgn(k )yt(o
9 = -
pn
~ (8.67a)
<x = - 7ETL (8.67b)
1 + ey" G>
With the control law (8.61) and adaptation law (8.67), global convergence of the
tracking error can be shown. The proof is mathematically involved and will be
omitted here.
Finally, note that there exist other techniques to get around the difficulty
associated with equation (8.62). In particular, it can be shown that an alternative
technique is to generate a different augmented error, which is related to the parameter
error 9 through a properly selected SPR transfer function.
8.5 Adaptive Control of Nonlinear Systems
There exists relatively little general theory for the adaptive control of nonlinear
systems. However, adaptive control has been successfully developed for some
important classes of nonlinear control problems. Such problems usually satisfy the
following conditions:
1. the nonlinear plant dynamics can be linearly parameterized
2. the full state is measurable
3. nonlinearities can be canceled stably (i.e., without unstable hidden
modes or dynamics) by the control input if the parameters are known

| Sect. 8.5  |     | Adaptive Control of Nonlinear Systems  |     | 351 |
| ---------- | --- | -------------------------------------- | --- | --- |
In this section, we describe one such class of SISO systems to suggest how to design
adaptive controllers for nonlinear systems (as an extension of the technique in section
8.3).  In chapter 9, we shall study in detail the adaptive control of special classes of
MIMO nonlinear physical systems.
PROBLEM STATEMENT
We consider «th-order nonlinear systems in companion form
n
|     | /"> + £  Of/Hx, f) = bu  |     |     | (8.68) |
| --- | ------------------------ | --- | --- | ------ |
where x = [y  y  ....  y(n~ ^]T is the state vector, the fj are known nonlinear functions
of the state and time, and the parameters oc- and b are unknown constants. We assume
(
that the state is measured, and that the sign of b is known. One example of such
dynamics is
|     | m'x + cf(x) + kf | (x)  = u  |     | (8.69) |
| --- | ---------------- | --------- | --- | ------ |
|     | x                | 2         |     |        |
which represents a mass-spring-damper system with nonlinear friction and nonlinear
damping.
The objective of the adaptive control design to make the output asymptotically
tracks a desired output yjj)  despite the parameter uncertainty.  To facilitate  the
adaptive controller derivation, let us rewrite equation (8.68) as
n
|     | hy(n) + X  aifi<x' ^  | =  u  |     | (8'7°) |
| --- | --------------------- | ----- | --- | ------ |
1=1
by dividing both sides by the unknown constant b, where h = lib and a,- =  ajb.
CHOICE OF CONTROL LAW
Similarly to the sliding control approach of chapter 7, let us define a combined error
(n~ » + \_2e("~2)
|     | s = | + -  +V V  | =   |     |
| --- | --- | ---------- | --- | --- |
 e
where e is the output tracking error and  A(p) =pn~l  + k -2P^"~^  +  + \  's  a
n
stable (Hurwitz) polynomial in the Laplace variable p.  Note that s can be rewritten as
j = _y(«-l)-_y (n-0
where >"/""'' is defined as
|     | ,(n-l)  («-l)_a, | (n-2)_  | -X    |     |
| --- | ---------------- | ------- | ----- | --- |
|     | v   = vyd        | / V2C e | ^ e e |     |
J

352 Adaptive Control Chap. 8 |j
Consider the control law
n
— h (ft) b 4- ^"" ft A (8 71 ^
i=\
where k is a constant of the same sign as h, and yW is the derivative of y^n'x\ i.e.,
r
Note that 31/") , the so-called "reference" value of /n), is obtained by modifying
yj-"^ according to the tracking errors.
If the parameters are all known, this choice leads to the tracking error dynamics
h's + ks = 0
and therefore gives exponential convergence of s, which, in turn, guarantees the
convergence of e.
CHOICE OF ADAPTATION LAW
For our adaptive control, the control law (8.71) is replaced by
n
where h and the a have been replaced by their estimated values. The tracking error
i
from this control law can be easily shown to be
1=1
This can be rewritten as
p + (Kin) ,_|
Since this represents an equation in the form of (8.15) with the transfer function
obviously being SPR, Lemma 8.1 suggests us to choose the following adaptation law
A
h = -
Specifically, using the Lyapunov function candidate
J

Sect. 8.6 Robustness of Adaptive Control Systems 353
V = j[ ^]
i
it is straightforward to verify that
V = -2\k\s2
and therefore the global tracking convergence of the adaptive control system can be
easily shown.
Note that the formulation used here is very similar to that in section 8.3.
However, due to the use of the compact tracking error measure s, the derivation and
notation here is much simpler. Also, one can easily show that global tracking
convergence is preserved if a different adaptation gain y is used for each unknown
(
parameter.
The sliding control ideas of chapter 7 can be used further to create controllers
that can adapt to constant unknown parameters while being robust to unknown but
bounded fast-varying coefficients or disturbances, as in systems of the form
1=1
where the /j- are known nonlinear functions of the state and time, h and the a, are
unknown constants, and the time-varying quantities a (t) are unknown but of known
iv
(possibly state-dependent or time-varying) bounds (Exercise 8.8).
8.6 Robustness of Adaptive Control Systems
The above tracking and parameter convergence analysis has provided us with
considerable insight into the behavior of the adaptive control system. The analysis has
been carried out assuming that no other uncertainties exist in the control system
besides parametric uncertainties. However, in practice, many types of non-parametric
uncertainties can be present. These include
• high-frequency unmodeled dynamics, such as actuator dynamics or
structural vibrations
• low-frequency unmodeled dynamics, such as Coulomb friction and stiction
• measurement noise
• computation roundoff error and sampling delay

354 Adaptive Control Chap. 8
Since adaptive controllers are designed to control real physical systems and such non-
parametric uncertainties are unavoidable, it is important to ask the following questions
concerning the non-parametric uncertainties:
• what effects can they have on adaptive control systems ?
• when are adaptive control systems sensitive to them ?
• how can adaptive control systems be made insensitive to them ?
While precise answers to such questions are difficult to obtain, because adaptive
control systems are nonlinear systems, some qualitative answers can improve our
understanding of adaptive control system behavior in practical applications. Let us
now briefly discuss these topics.
Non-parametric uncertainties usually lead to performance degradation, i.e., the
increase of model following error. Generally, small non-parametric uncertainties
cause small tracking error, while larger ones cause larger tracking error. Such
relations are universal in control systems and intuitively understandable. We can
naturally expect the adaptive control system to become unstable when the non-
parametric uncertainties become too large.
PARAMETER DRIFT
When the signal v is persistently exciting, both simulations and analysis
indicate that the adaptive control systems have some robustness with respect to non-
parametric uncertainties. However, when the signals are not persistently exciting,
even small uncertainties may lead to severe problems for adaptive controllers. The
following example illustrates this situation.
Example 8.7: Rohrs's Example
The sometimes destructive consequence of non-parametric uncertainties is clearly shown in the
well-known example by Rohrs, which consists of an adaptive first-order control system
containing unmodeled dynamics and measurement noise. In the adaptive control design, the plant
is assumed to have a the following nominal model
The reference model has the following SPR function
p + a p + 3
m

Sect. 8.6 Robustness of Adaptive Control Systems 355
The real plant, however, is assumed to have the transfer function relation
229
y =
P + 1 p2 + 30p + 229
This means that the real plant is of third order while the nominal plant is of only first order. The
unmodeled dynamics are thus seen to be 229/(p2 + 30p + 229), which are high-frequency but
lightly-damped poles at (- 15 +j) and (— 15 —j).
Besides the unmodeled dynamics, it is assumed that there is some measurement noise n(t) in
the adaptive system. The whole adaptive control system is shown in Figure 8.18. The
measurement noise is assumed to be n(t) = 0.5 sin(16.11).
reference y (t)
model
e(t)
nominal unmodeled n(t)
•
i 2 i 229 ;
: p + 1 \p2+30p+229 I
Figure 8.18 : Adaptive control with unmodeled dynamics and measurement noise
Corresponding to the reference input lit) = 2, the results of the adaptive control system are shown
in Figure 8.19. It is seen that the output y(t) initially converges to the vicinity of y = 2, then
operates with a small oscillatory error related to the measurement noise, and finally diverges to
infinity. C3
In view of the global tracking convergence proven in the absence of non-
parametric uncertainties and the small amount of non-parametric uncertainties present
in the above example, the observed instability can seem quite surprising. However,
one can gain some insight into what is going on in the adaptive control system by
examining the parameter estimates in Figure 8.19. It is seen that the parameters drift
slowly as time goes on, and suddenly diverge sharply. The simplest explanation of the
parameter drift problem is that the constant reference input contains insufficient
parameter information and the parameter adaptation mechanism has difficulty
distinguishing the parameter information from noise. As a result, the parameters drift
in a direction along which the tracking error remains small. Note that even though the

356 Adaptive Control
30 r-
20
10
0
-10
-20
0 10 20 30 40 50 60 70 80
time(sec)
sre
ma•iap
Chap. 8
20 p !
10
0
-10
-20
-30 -
-40
-50 -
-60
-70
-80
0 10 20 30 40 50 60 70 80
time(sec)
Figure 8.19 : Instability and parameter drift
tracking error stays at the same level when the parameters drift, the poles of the
closed-loop system continuously shift (since the parameters vary very slowly, the
adaptive control system may be regarded as a linear time-invariant system with three
poles). When the estimated parameters drift to the point where the closed-loop poles
enter the right-half complex plane, the whole system becomes unstable. The above
reasoning can be confirmed mathematically.
In general, the following points can be made about parameter drift. Parameter
drift occurs when the signals are not persistently exciting; it is mainly caused by
measurement noise; it does not affect tracking accuracy until instability occurs; it
leads to sudden failure of the adaptive control system (by exciting unmodeled
dynamics).
Parameter drift is a major problem associated with non-parametric uncertainties
(noise and disturbance). But there are possibly other problems. For example, when
the adaptation gain or the reference signal are very large, adaptation becomes fast and
the estimated parameters may be quite oscillatory. If the oscillations get into the
frequency range of unmodeled dynamics, the unmodeled dynamics may be excited
and the parameter adaptation may be based on meaningless signals, possibly leading
to instability of the control system. For parameter oscillation problems, techniques
such as normalization of signals (divide v by 1 + v^ v ) or the composite adaptation in
section 8.8 can be quite useful.
DEAD-ZONE
Even though the possibility of small disturbances leading to instability is quite
undesirable, it does not mean that adaptive control is impractical. A number of
techniques for modifying the adaptation law are available to avoid the parameter drift
problem. The simplest is called the "dead-zone" technique. Because of its simplicity J
and effectiveness, it is most frequently used.

Sect. 8.6 Robustness of Adaptive Control Systems 357
The dead-zone technique is based on the observation that small tracking errors
contain mostly noise and disturbance, therefore, one should shut the adaptation
mechanism off for small tracking errors. Specifically, we should replace an adaptation
law
A
a = - yve (8.75)
by
A \e\> A
a = (8.76)
\e\< A
where A is the size the dead-zone. As the following example shows, such a simple
modification can greatly reduce the effects of the disturbances.
Example 8.8: Use of Dead-Zone
Consider again the adaptive control system of Example 8.7, but modify the adaptation law by
incorporating a dead-zone of A = 0.7. The results are shown in Figure 8.20. It is seen that
tracking error stays around the ideal response of y = 2, with an oscillation due to the measurement
noise. The parameters now do not have any indication of drifting. It is interesting to point out
that the oscillation appears very fast because the time-scale in the figure is large and the noise
itself is of quite high frequency. CD
4.0 2.0
1.5
3.0
1.0
0.5
2.0
0.0
1.0 -0.5
-1.0
0.0 -1.5
10 20 30 40 50 60 70 80 0 10 20 30 40 50 60 70 80
time(sec) time(sec)
Figure 8.20 : Adaptive control with dead-zone
A number of other techniques also exist to relieve the problem of parameter
drift. One involves the so-called o-modification, which approximates the original
integrator in the adaptation law by a lowpass filter. Another is the "regressor
replacement" technique. By "regressor", we mean the vector v(f) in (8.75). Note that
\{t) is usually computed based on the plant measurement y and thus affected by
measurement noise n(t). Since the adaptation law (8.75) involves the multiplication of

358 Adaptive Control Chap. 8
\(t) by e(t), the update rate is related to the square of the measurement noise and
causes parameter drift. For example, in the presence of measurement noise n(t),
(8.28b) can be written
a = - sgn(6) Y (y + n - y ) (y, + n)
y x m
= - sgn(fc) y [{y - y ) y + n ( 2y, - yj + n2]
x m {
where y is the true plant output. It is noted that the first term truly contains parameter
l
information, the second term tends to average out, and the third term - sgn(fr) y rP- is
the reason for the drifting of a in Figure 8.19 (a drifts accordingly so that the
y r
tracking error remains small). As a result of this observation, one can relieve
parameter drift by replacing y in (8.28b) by y which is independent of n. It is
m
desirable to start this replacement after the tracking error has converged well.
8.7 * On-Line Parameter Estimation
When there is parameter uncertainty in a dynamic system (linear or nonlinear), one
way to reduce it is to use parameter estimation, i.e., inferring the values of the
parameters from the measurements of input and output signals of the system.
Parameter estimation can be done either on-line or off-line. Off-line estimation may
be preferable if the parameters are constant and there is sufficient time for estimation
before control. However, for parameters which vary (even though slowly) during
operation, on-line parameter estimation is necessary to keep track of the parameter
values. Since problems in the adaptive control context usually involve slowly time-
varying parameters, on-line estimation methods are thus more relevant.
In this section, we study a few basic methods of on-line estimation. Unlike
most discussions of parameter estimation, we use a continuous-time formulation rather
than a discrete-time formulation. This is motivated by the fact that nonlinear physical
systems are continuous in nature and are hard to meaningfully discretize.
Furthermore, digital control systems may be treated as continuous-time systems in
analysis and design if high sampling rates are used. The availability of cheap
computation generally allows high sampling rates and thus continuous-time models to
be used.
Note that, although the main purpose of the on-line estimators may be to
provide parameter estimates for self-tuning control, they can also be used for other
purposes, such as load monitoring or failure detection.

Sect. 8.7 * On-Line Parameter Estimation 359
8.7.1 Linear Parametrization Model
The essence of parameter estimation is to extract parameter information from
available data concerning the system. Therefore, we need an estimation model to
relate the available data to the unknown parameters, similarly to the familiar
experimental data fitting scenario, where we need to hypothesize the form of a curve
before finding specific coefficients describing it, based on the data. This estimation
model may or may not be the same as the model used for the control purpose. A quite
general model for parameter estimation applications is in the linear parametrization
form
y(0=W(/)a (8.77)
where the /z-dimensional vector y contains the "outputs" of the system, the
/w-dimensional vector a contains unknown parameters to be estimated, and the nxm
matrix W(f) is a signal matrix. Note that both y and W are required to be known from
the measurements of the system signals, and thus the only unknown quantities in
(8.77) are the parameters in a. This means that (8.77) is simply a linear equation in
terms of the unknown a. For every time instant t, there is such an equation. So if we
are given the continuous measurements of y(0 and W(0 throughout a time interval, we
have an infinite number of equations in the form of (8.77). If we are given the values
of y(f) and W(r) at k sampling instants, we have k sets of such equations instead. The
objective of parameter estimation is to simply solve these redundant equations for the
m unknown parameters. Clearly, in order to be able to estimate m parameters, we
need at least a total of m equations. However, in order to estimate the parameters a
well in the presence of inevitable noise and modeling error, more data points are
preferable.
In off-line estimation, one collects the data of y and W for a period of time, and
solves the equations once and for all. In on-line estimation, one solves the equation
recursively, implying that the estimated value of a is updated once a new set of data y
and W is available.
How well and how fast the parameters a are estimated depends on two aspects,
namely, the estimation method used and the information content (persistent excitation)
of the data y and W. Our primary objective in this section is to examine the properties
of some standard estimation methods. The generation of informative data is a
complex issue discussed extensively in the system identification literature. While we
shall not study this issue in detail, the relation between the signal properties and
estimation results will be discussed.
Model (8.77), although simple, is actually quite general. Any linear system can

| 360  Adaptive Control  |     | Chap. 8 |
| ---------------------- | --- | ------- |
be rewritten in this form after filtering both sides of the system dynamics equation
through an exponentially  stable filter of proper  order, as seen in the following
example.
Example 8.9: Filtering Linear Dynamics
Let us first consider the first-order dynamics
| y=-ay  + bu  |     | (8.78) |
| ------------ | --- | ------ |
| {            | x   |        |
Assume that a^ and foji n the model are unknown, and that only the output y and the input u are
available. The above model cannot be directly used for estimation, because the derivative of y
appears in the above equation (note that numerically differentiating y is usually  undesirable
because of noise considerations). To eliminate y in the above equation, let us filter (multiply) both
sides of the equation by l/(p + Xj) (where p is the Laplace operator and Xr is a known positive
constant). Rearranging, this leads to the form
| y(t) = y(Xa)  | + ub  | (8.79) |
| ------------- | ----- | ------ |
| f r           | x f x |        |
where
with the subscript / denoting filtered quantities.  Note that, as a result of the filtering operation,
the only unknown quantities in (8.79) are the parameters (Kj- a) and by x
Note that the above filtering introduces a d.c. gain of \[kf, i.e., the magnitudes of >y-and «y
are smaller than those of y and u by a factor of Xr at low frequencies. Since smaller signals may
lead to slower estimation, one may multiply both sides of (8.79) by a constant number, e.g., Xr.
Generally, for a linear single-input single-output system, its dynamics can be described by
| A(p)y = B(p)u  |     | (8.80) |
| -------------- | --- | ------ |
with
M)=  a  + ap + .... + a_,p"~1 + p"
| o   | { n  |     |
| --- | ---- | --- |
Let us divide both sides of (8.80) by a known monic polynomial of order n, leading to
| -W-«P\   | «ELu   | (8.81) |
| -------- | ------ | ------ |
| y        | +      |        |
| A O (P)  | A(p) o |        |
where

| Sect. 8.7  |                |                        | * On-Line Parameter Estimation  |     | 361 |
| ---------- | -------------- | ---------------------- | ------------------------------- | --- | --- |
|            | Ao = ao + a\P  | + •- + an-  \Pn~ ' +P" |                                 |     |     |
has known coefficients. In view of the fact that
|     | A (p)-A{p) = (a | -a ) + (a-a) |   +  ....+(a | _-a _)p"-] |     |
| --- | --------------- | ------------ | ------------ | ---------- | --- |
|     | 0               | o o          | l l P        | n l n l    |     |
we can write (8.81) in the basic form
y = 0rw(0
(8.82)
with 6 containing 2n unknown parameters, and w containing the filtered versions of the input and
output, defined by
b_)T
|     | 6 = l(a-a)  o | o (a,-*,)  ... (a_,-a_,)  | n n       | b  o ...  n { |     |
| --- | ------------- | ------------------------- | --------- | ------------- | --- |
|     | ,y            | py  pn~{y                 | u  pn~lu, |               |     |
T
|     | W-[A-   | T  -  -TT  | T  -  ^ TJ |     |     |
| --- | ------- | ---------- | ---------- | --- | --- |
|     | 0       | o          | o          |     |     |
Note that w can be computed on-line based on the available values of y and u.  d
The dynamics of many nonlinear systems can also be put into the form (8.77).
A simple example is the nonlinear mass-spring-damper system (8.69), for which the
input force  is obviously  linear in terms of mass, friction  coefficient,  and spring
coefficient.  For some more complicated  nonlinear dynamics, proper filtering  and
parameter transformation may be needed to put the dynamics into the form of (8.77),
as we now show.
Example 8.10: Linear parametrization of robot dynamics
Consider the nonlinear dynamics (6.9) of the two-link robot of Example 6.2. Clearly, the joint
torque vector q is nonlinear in terms of joint positions and velocities. It is also nonlinear in terms
of the physical parameters / c] , l c2 , and so on. However, it can be put into the form of (8.77) by a
proper reparametrization and a filtering operation.
Consider the reparametrization first. Let us define
ax = m2
a2 = m2  lc2
Then, one can show that each term on the left-hand  side of (6.9) is linear in terms of the
| equivalent inertia parameters a = [«!  |     | a  2 | a  3 a]T.  4 Specifically |     |     |
| -------------------------------------- | --- | ---- | ------------------------- | --- | --- |

362 Adaptive Control Chap. 8
= a
22 4
Note that /, and / are kinematic parameters, which are assumed to be known (they can be
2
similarly treated if not known). The above expressions indicate that the inertia torque terms are
linear in terms of a. It is easy to show that the other terms are also linear in a. Thus, we can write
T=Y(q,qq)a (8.83)
1 >
with the matrix V[ expressed (nonlinearly) as a function of only q, q and q; and a being a mxl
vector of equivalent parameters. This linear parametrization property actually applies to any
mechanical system, including multiple-link robots.
Relation (8.83) cannot be directly used for parameter estimation, because of the presence of
the unmeasurable joint acceleration q. To avoid the joint acceleration in this relation, we can use
the above filtering technique. Specifically, let w(i) be the impulse response of a stable, proper
filter (for example, for the first-order filter X/(p + X), the impulse response is e'"^). Then,
convolving both sides of (6.9) by w yields
fI t w{t-r)i(r)dr=\ .t w{t-r)[ Hq + Cq + G]dr (8.84)
o Jo
Using partial integration, the first term on the right-hand side of (8.84) can be rewritten as
= w(0)H(q)q - w(0)H[q(0)]q(0) - f [w(l-r)Hq- w(f-r)Hq]dr
o
This means that equation (8.84) can be rewritten as
y(/)=W(q,q)a (8.85)
where y is the fdtered torque and W is the filtered version of Y|. Thus, the matrix W can be
computed from available measurements of q and q. The filtered torque y can also be computed
(assuming no actuator dynamics) because the torque signals issued by the computer are known. [3
It is obvious at this point that the "output" y in model (8.77) does not have to be
the same as the output in a control problem. In the above robotic example, the
"output" y is actually the filtered version of the physical input to the robot. From a
parameter estimation point of view, what we want is just a linear relation between
known data and the unknown parameters. The following example further demonstrates

Sect. 8.7 * On-Line Parameter Estimation 363
this point.
Example 8.11: An alternative estimation model for robots
Consider again the above 2-link robot. Using the principle of energy conversation, one sees that
the rate of change of mechanical energy is equal to the power input from the joint motors, i.e.,
Trq = ^ ' (8.86)
at
where £(q, q) is the total mechanical energy of the robot. Since it is easy to show that the
mechanical energy can be linearly parameterized, i.e.,
£ = v(q, q)a
one can write the energy relation (8.86) as
dt
with v computable from the measurement of q and q. To eliminate the joint acceleration q in this
relation, we can again use filtering by a first-order filter l/(p + XA . This leads to
I Xv
f
[t] [ V ]a
This is in the form of (8.77), with
1
y = - [tTqJ
T
XrV _
W = V - -J— D
p + X
f
In the above example, note that the control model and the estimation model are
drastically different. Actually, while the control model (6.9) has two equations and
two outputs, the estimation model (8.86) has only one equation and one output
(actually, the scalar model (8.86) is applicable to robots with any number of links
because the energy relation is always scalar). With the energy relation (8.86), the
computation of w is greatly simplified compared with that of W in (8.85), because
there is no need to compute the complex centripetal and Coriolis forces (which may
contain hundreds of terms for multiple-DOF robots).

364 Adaptive Control Chap. 8
8.7.2 Prediction-Error-Based Estimation Methods
Before studying the various methods for parameter estimation, let us first discuss the
concept of prediction error. Assume that the parameter vector in (8.77) is unknown,
and is estimated to be a(f) at time t. One can predict the value of the output y{t) based
on the parameter estimate and the model (8.77),
y(0 = W(r)a(0 (8.87)
where y is called the predicted output at time t. The difference between the predicted
output and the measured output y is called the prediction error, denoted by e^ , i.e.,
y(0 (8-88)
The on-line estimation methods to be discussed in this section are all based on this
error, i.e., the parameter estimation law is driven by ej. The resulting estimators
belong to the so-called prediction-error based estimators, a major class of on-line
parameter estimators. The prediction error is related to the parameter estimation error,
as can be seen from
(8.89)
where a = a - a is the parameter estimation error.
In the following, we shall discuss the motivation, formulation and properties of
the following methods:
• Gradient estimation
• Standard least-squares estimation
• Least-squares with exponential forgetting
• A particular method of variable exponential forgetting
Note that in the convergence analysis of these estimators we shall assume that the true
parameters are constant, so that insights concerning the estimator's behavior can be
obtained. However, in the back of our mind, we will always be aware of the task of
handling time-varying parameters.
8.7.3 The Gradient Estimator
The simplest on-line estimator is the gradient estimator. Let us discuss its
formulation, convergence properties, and robustness properties.

Sect. 8.7 On-Line Parameter Estimation 365
FORMULATION AND CONVERGENCE
The basic idea in gradient estimation is that the parameters should be updated so that
the prediction error is reduced. This idea is implemented by updating the parameters in
the converse direction of the gradient of the squared prediction error with respect to
the parameters, i.e.,
3a
where p is a positive number called the estimator gain. In view of (8.88) and (8.87),
o
this can be written as
(8.90)
To see the properties of this estimator, we use (8.90) and (8.89) to obtain
Using the Lyapunov function candidate
V= ara
its derivative is easily found to be
V=-2p S.TWTWa<0
o
This implies that the gradient estimator is always stable. By noting that V is actually
the squared parameter error, we see that the magnitude of the parameter error is
always decreasing.
However, the convergence of the estimated parameters to the true parameters
depends on the excitation of the signals. To gain some insights on that point, let us
consider the estimation of a single parameter.
Example 8.12: Gradient estimation of a single parameter
Consider the estimation of one parameter from the model
y — wa
(with the mass estimation in Example 8.2 being such a case). The gradient estimation law is
a = -pwe
o x
This implies that

366 Adaptive Control Chap. 8
which can be solved as
2(() = 2(0)exp[-J pw2(r)dr]
o
This implies that the parameter error will converge to zero if the signal w is such that
Uimrn f w\r)dr =
oa'o
Note that a will exponentially converge to zero if w is persistently exciting, i.e., if there exist
positive constants T and <Xj such that for all t > 0 ,
In fact, the convergence rate is easily found to be pa.^fT.
o
Clearly, in this case, a constant non-zero w can guarantee the exponential convergence of a.
However, if the signal w decays too fast (e.g., w = e~'), one easily shows that the parameter error
does not converge to zero. LJ
The above convergence result concerning the one-parameter case can by
extended to the estimation of multiple parameters. Specifically, if the matrix W is
persistently exciting, i.e., there exist positive constants o^ and T such that VT > 0
j' + rWTWc/r > ajl (8.91)
then the parameter error a will converge exponentially, as shown in [Anderson, 1977;
Morgan and Narendra, 1977] through a fairly involved procedure. Such a condition for
parameter convergence is easily understandable, analogously to the case of model-
reference adaptive control. In the case of linear systems, as described by (8.80), it is
easy to verify that m sinusoids in the input signal u can guarantee the estimation of up
to 1m parameters. In the case of nonlinear systems, the relation between the number
of sinusoids and the number of parameters which can be estimated is not so clear. It is
possible to estimate more than 2m parameters with an input u containing m sinusoids,
as explained in section 8.2.
A slightly more general version of the gradient estimator is obtained by
replacing the scalar gain by a positive definite matrix gain P ,
o
J

Sect. 8.7 On-Line Parameter Estimation 367
A _ dreJe.l
a = -P
0 3 A
da
The global stability of the algorithm can be shown using the Lyapunov function
The convergence properties are very similar.
EFFECTS OF ESTIMATION GAIN
The choice of estimation gain p has a fundamental influence on the convergence
o
behavior of the estimator. For the single-parameter estimation case, one easily sees
that a larger p implies faster parameter convergence. In fact, the convergence rate is
0
linearly related to the estimation gain p. For the multiple-parameter case, however,
0
the relation between the magnitude of p and the convergence rate of the estimated
0
parameters is not as simple. Generally speaking, in a small range, increasing
estimation gain leads to faster parameter convergence. But beyond some point, further
increasing the estimation gain leads to more oscillatory and slower convergence, as
can be demonstrated with the estimation of the four load parameters in the robot
example 8.10. This phenomenon is caused by the gradient nature of the estimation,
similarly to what happens in the gradient search method in optimization: within a
small range, increase in step size in the gradient direction leads to faster convergence;
but beyond some point, larger size leads to more oscillatory and possibly slower
convergence.
Besides the effect on convergence speed, the choice of p also has implications
0
on the ability of the estimator to track time-varying parameters and withstand
disturbances, as will be discussed soon.
ROBUSTNESS PROPERTIES
The above analysis and simulations have been based on the assumed absence of
parameter variation and non-parametric uncertainties. In order for an estimator to
have practical value, however, it must have some robustness, i.e., maintain reasonably
good parameter estimation in the presence of parameter variation, measurement noise,
disturbances, etc.
The quality of the parameter estimates in a gradient estimator depends on a
number of factors, mainly,
• the level of persistent excitation of the signal W

368 Adaptive Control Chap. 8
• the rate of parameter variation and the level of non-parametric uncertainties
• the magnitude of the estimator gain p
0
The level of persistent excitation in W is decided by the control task or
experiment design. Persistent excitation is essential for the robustness of the estimator.
If the signals in the original design are not persistently exciting, parameters will not
converge even in the absence of non-parametric uncertainties. In the presence of non-
parametric uncertainties, the estimator may possibly become unstable, i.e., the
parameters may diverge. One may have to add some perturbation signals to the
control input to obtain good parameter estimation. The specific details in the data
generation may be complicated, but the bottom line is that one should produce as
much persist excitation as allowed by the involved constraints.
How fast the true parameters vary and how large the non-parametric
uncertainties also affect the quality of the parameter estimates. Obviously, if the true
parameters vary faster, it is harder for the parameter estimator to estimate accurately.
If a lot of noise and unmodeled disturbances and dynamics are present, the estimates
also become poor. To see this, let us consider the mass estimation problem, but now in
the presence of disturbance (unmodeled Coulomb friction or measurement noise) and
time-varying mass. The mass dynamics becomes
T(0 = m(t) w(t) + d(t)
where d(t) is the disturbance and w is the acceleration. The prediction error in this
case is
A ~
e-j = x — x= mw-d
By substituting this into (8.90), the parameter error is easily shown to satisfy
^ = -p w23-fl+p wd (8.92)
o o
This can be interpreted as a time-varying filter with "output" a and "input"
(-a + pwd). Clearly, larger parameter variation rate a and larger disturbance d(t)
o
leads to larger parameter error 5. If parameter a varies too fast or the non-parametric
uncertainties have too large values, one should consider using more accurate models,
i.e., modeling the dynamics of the parameter variation and also the disturbance.
The magnitude of the estimator gain also has a considerable influence on the
robustness of the estimator. If p is chosen to be large, the "bandwidth" of the filter
o
p vP- becomes large (so that higher-frequency noise can pass) and the input
0
component p wd to the filter becomes larger. This means that parameter estimation
o

| Sect. 8.7 |     | On-Line Parameter Estimation  |     | 369 |
| --------- | --- | ----------------------------- | --- | --- |
error due to disturbance will become larger. The increase of estimation gain has the
opposite effect on the estimator ability to estimate time-varying parameters. Consider
the case of w being a constant for example. The steady-state error of the estimated
parameter in (8.92) is m/(p w2), which shows that the parameter error is decreased by
o
the increase of the estimation gain.
The  following  simple  simulation  illustrates  the  behavior  of  the  gradient
estimator in the presence of measurement noise.
Example 8.13: Gradient estimation of a constant mass
Consider the problem of mass estimation for the dynamics
u = tn w(t) + d(t)
with w(t) = sin(/), and d(t) is interpreted as either disturbance or measurement noise.  The true
mass is assumed to be m = 2.  When the disturbance d{t) = 0, the estimation results are shown in
the left plot in Figure 8.21.  It is seen that larger gain corresponds to faster convergence, as
expected.  When the disturbance is d(i) = 0.5 sin(200, the estimation results are shown on the
right plot in Figure 8.21. It is seen that larger estimation gain leads to larger estimation error.
| 1.2 |     | ioit 1.2 |     |     |
| --- | --- | -------- | --- | --- |
o
| 1.0 |     | g 1.0  |     |     |
| --- | --- | ------ | --- | --- |
| 0.8 |     | (U 0.8 |     |     |
w
| B 0.6       |               | 0.6     |           |     |
| ----------- | ------------- | ------- | --------- | --- |
| 2           |               | a       |           |     |
| 0.4         |               | iap 0.4 |           |     |
| 0.2         |               | 0.2     |           |     |
| 0.0         |               | 0.0     |           |     |
| 0.0 1.0 2.0 | 3.0  4.0  5.0 | 0.0 2.0 | 3.0  4.0  | 5.0 |
|             | time(sec)     |         | time(sec) |     |
Figure 8.21 : gradient method, left: without noise, right: with noise
The  following  simple  simulation  illustrates  the  behavior  of  the  gradient
estimator in the presence of both parameter variation and measurement noise.
Example 8.14: Gradient estimation of a time-varying mass
Now suppose that the true parameter is slowly time-varying, with m(t) = 1 + O.5sin(O.5()- Let us
take p=  g 1.  The estimation results in the absence of disturbance is shown in the left plot in
Figure 8.22.  In the presence of the disturbance of the previous example, the parameter estimation
result is shown in the right plot.  It is seen that the gradient method works quite well in the
| presence of parameter variation and disturbance.  |     |     |     | D   |
| ------------------------------------------------- | --- | --- | --- | --- |

370 Adaptive Control Chap. 8
.6 .4
.2 .0
0.8
0.6
0.4
0.2
0.0
20 25 10 15 20 25
time(sec) time(sec)
Figure 8.22 : Time-varying gradient
8.7.4 The Standard Least-Squares Estimator
We all have some experience with least squares estimation (data fitting). In this
subsection, we shall formalize the technique and carefully study its properties.
FORMULATION
In the standard least-squares method, the estimate of the parameters is generated by
minimizing the total prediction error
/= f'|| y(r)-W(r)a(f) \\2dr (8.93)
o
with respect to a(t). Since this implies the fitting of all past data, this estimate
potentially has the advantage of averaging out the effects of measurement noise. The
estimated parameter a satisfies
' WTWdr] a(f) = j'WTydr (8.94)
Define
(8.95)
To achieve computational efficiency, it is desirable to compute P recursively, instead
of evaluating the integral at every time instant. This amounts to replacing the above
equation by the differential equation
(8.96)
at

Sect. 8.7 * On-Line Parameter Estimation 371
Differentiating (8.94) and using (8.95) and (8.96), we find that the parameter update
satisfies
a = -P(/)WTe, (8.97)
with P(f) being called the estimator gain matrix, similarly to the case of gradient
estimation. In the implementation of the estimator, it is desirable to update the gain P
directly, rather than using (8.96) and then inverting the matrix P~' . By using the
identity
[ p p] p p + p [ p] o
dt dt
we obtain
p = -PWrWP (8.98)
In using (8.97) and (8.98) for on-line estimation, we have to provide an initial
parameter value and an initial gain value. But there is a difficulty with this
initialization, because (8.97) and (8.98) imply that P should be infinity, while a is
initially undefined. To avoid this problem, we shall provide finite values to initialize P
and a. Clearly, one should use the best guess to initialize the a. The choice of the
initial gain P(0) should be chosen as high as allowed by the noise sensitivity. P(0) can
be chosen to be diagonal, for simplicity.
It is useful to remark that the above least-squares estimator can be interpreted in
a Kalman filter framework, with a being the state to be estimated and P being the
estimation covariance matrix. Based on this perspective, the initial gain P(0) should
be chosen to represent the covariance of the initial parameter estimates a(0).
PARAMETER CONVERGENCE
The convergence property of the estimator can be best understood by solving
the differential equations (8.96) and (8.97), assuming the absence of noise and
parameter variation. From (8.96), (8.97) and (8.98), one easily shows that
dr (8.99)
^[P
at
Thus,
a(0 = P(0P~'(0) 5(0) (8.100)

372 Adaptive Control Chap. 8
If W is such that
X {^'y/TWdr} -^oo _> oo (8.101)
min as f
where ^ [] denotes the smallest eigenvalue of its argument, then the gain matrix
min
converges to zero, and the estimated parameters asymptotically (but usually not
exponentially) converge to the true parameters. Note that the "infinite-integral"
condition (8.101) is a weaker condition than the persistent excitation (8.91). Indeed,
for any positive integer k,
f WTWdr = Yj\ WTWdr> ka l (8.102)
x
Thus, if W is persistently exciting, (8.102) is satisfied, P —» 0 and a —> 0.
The effects of the initial gain and initial parameter estimates can be easily seen
from (8.100) and (8.99). Obviously, a small initial parameter error 3(0) results in a
small parameter error all the time. A large initial gain P(0) also leads to a small
parameter error. This is particularly clear if we choose P(0) = pl, which leads to
o
3(0 = [I + p \'y/T(r)W()dr]-la(0)
o r
ROBUSTNESS
Roughly speaking, the least-squares method has good robustness with respect to noise
and disturbance, but poor ability in tracking time-varying parameters. The reason for
the good noise-rejection property is easy to understand: noise, particularly high-
frequency noise, is averaged out. The estimator's inability in tracking time-varying
parameters can also be understood intuitively, from two points of views. From a
mathematical point of view, P(0 converges to zero when W is persistently exciting,
i.e., the parameter update is essentially shut off after some time, and the changing
parameters cannot be estimated any more. From an information point of view, the
least-square estimate attempts to fit all the data up to the current time, while, in reality,
the old data is generated by old parameters.
The following example illustrates the behavior of the least-squares estimator in
the presence of measurement noise.
Example 8.15: Least-squares estimation of one parameter
Consider again the estimation of the mass system, now with a least-square method. The
parameter estimation results in the absence of disturbance, are shown in the left plot of Figure
8.23, with the two curves corresponding to the initial gain p = 2 and p = 10, respectively. It is
0 0
seen that the parameter converges faster with larger initial gain. Another feature is that least

Sect. 8.7 ' On-Line Parameter Estimation 373
square converge fast initially, but slowly afterward.
The parameter estimation results in the presence of disturbance are presented in the right plot
of Figure 8.23. The same initial gain values are used. It is seen that the estimated parameters are
much smoother than those from the gradient method. d
1-0
0.8
0.6
4
°-
0.2
0.0
2.0 3.0 4.0 5.0 0.0 1.0 2.0 3.0 4.0 5.0
time(sec) time(sec)
Figure 8.23 : Least-squares method; left: without noise ; right: with noise
The inability of the least-squares method to estimate time-varying parameters is
demonstrated in the following example.
Example 8.16: Least-squares estimation of time-varying parameter
Now the true parameter in = 1 is replaced by m{t)= 1 + 0.5sin(0.5/). The initial gain value is
chosen to be f(0) = 1. The true and estimated parameters in the absence of disturbance are shown
in the left plot of Figure 8.24. Those in the presence of disturbance are shown in the right plot. It
is seen that the estimated parameters cannot follow the true parameter variation, regardless of the
disturbance. O
1.8 o
1.6 re
1.4 ./' _A^ / \
1.2 \X / \
1.0 f
0.8 \ \ / / \ \ / /
0.6 \y \y
0.4
0.2
0.0 i i i i i
5 10 15 20 25
•)
time(sec)
mtis
arap
1.8
1.6
1.4 / \
1.2•i/\\ / \
1.0 ' \ ^^U^~T—-—
0.8 \ / \ / \ / \ /
0.6 \y
0.4
0.2
0 0 i i i
c 5 10 15 20 25
time(sec)
Figure 8.24 : Least-squares time-varying gradient

374 Adaptive Control Chap. 8
8.7.5 Least-Squares With Exponential Forgetting
Exponential forgetting of data is a very useful technique in dealing with time-varying
parameters. Its intuitive motivation is that past data are generated by past parameters
and thus should be discounted when being used for the estimation of the current
parameters. In this subsection, we describe the general formulation of least square
method with time-varying forgetting factor. In the next subsection, a desirable form of
forgetting factor variation will be discussed.
If exponential forgetting of data is incorporated into least-square estimation, one
minimizes
instead of (8.93), where X(t) > 0 is the time-varying forgetting factor. Note that the
exponential term in the integral represents the weighting for the data. One easily
shows that the parameter update law is still of the same form,
a = -P(f)Wre, (8.103)
but that the gain update law is now
[[PP-1]] M OP + W(f)W(0 (8.104)
at
In implementation, it is more efficient to use the following form of the gain update
tP] ^-(0PPW(0W(r)P (8.105)
tP]
dt
To understand the convergence properties of the estimator, let us again solve for
the gain and parameter errors explicitly. The estimator gain can be explicitly solved
from (8.104) to be
P~x(t) = P-1(O)exp[-f'x.('-)dr] + f'exp[-f'x.(v)rfv]Wr(/-)W(r)c/r (8.106)
O O V
To solve the explicit form of the parameter error, let us note that one can easily obtain
-[p-!a]= -^P-'a (8.107)
dt
Therefore,
1

Sect. 8.7 * On-Line Parameter Estimation 375
a(f) = exp[-\'X(r)dr]P(t)P-l(O)a(O) (8.108)
That is,
Comparing this and (8.100), and noting that
exp[fX(v)dv] > 1
o
one sees that exponential forgetting always improves parameter convergence over
standard least-squares. It also shows that the "infinite integral" condition (8.101) for
standard least-squares still guarantees the asymptotic convergence of the estimated
parameters. This also implies that persistent excitation of the signal W can guarantee
the convergence of the estimated parameters.
It is easy to see that exponential forgetting leads to exponential convergence of
the estimated parameters, provided that X{i) is chosen to be larger than or equal to a
positive constant and that signals are p.e. Specifically, assume that X(t) > X , with X
o o
being a positive constant. Then, we have from (8.104)
^ [P-i] = -A, P-' + WTW + (X(t) -X )P~l
0 o
p-l(t) = p-\0)e-K' + f'e-K('-r){WTXV
o
This guarantees from (8.92) that P~'(0 > e~K^a.\ I and, accordingly, that
a,
for t > 8. This and (8.108) show the exponential convergence of a(t) to zero with a rate
of at least X .
o
It is interesting to remark that, if the forgetting factor is constant, then the
exponential convergence rate of the estimated parameters is the same as the forgetting
factor. However, a constant forgetting factor may lead to diminishing magnitude in
certain directions of P~' (and accordingly, unbounded magnitude in certain directions
of P) in the absence of p.e., due to the exponential decaying components in (8.106).
Unboundedness (or even large magnitude) of the gain matrix is undesirable, since it
implies that the disturbance and noise in the prediction error may, through the update

376 Adaptive Control Chap. 8
law (8.103), lead to violent oscillations of the estimated parameters.
The following one-parameter example demonstrates the desirable and
undesirable properties for exponential forgetting with a constant forgetting factor.
Example 8.17 : Estimating one parameter with a constant forgetting factor
Consider the estimation of parameter a from the equation y = wa using the least-squares method
with a constant forgetting factor. The cost to be minimized is
/= fW'-'') [y(r)-w(r)a(0]2d''
The parameter update law is
a(t) = -P(t)w(t)e(t)
and the gain update law is
1[P-'] = -X P-l+ww
o
The gain update is easily solved to be
p-i(t) = P'l(0)e-K'+ f e-\M'^w2dr
o
and the parameter error is
2(0 = e~K' P(t)p-](0)a(0)
If the signal w is persistently exciting, P(t) will be upper bounded and a will converge to zero
exponentially with a rate X . If w is not persistently exciting (for example, for w = e~', P~l(t)
o
may converge to zero and thus P(t) to infinity). C3
Thus, we see that caution has to be exercised in choosing the forgetting factor.
A zero forgetting factor leads to vanishing gain (standard least-squares and thus
inability of tracking time-varying parameters) in the presence of persistent excitation,
while a constant positive factor leads to exploding gain in the absence of persistent
excitation. Since an estimator may encounter signals with different levels of persistent
excitation, an automatic tuning method for the forgetting factor is necessary.
8.7.6 Bounded-Gain Forgetting
To keep the benefits of data forgetting (parameter tracking ability) while avoiding the
possibility of gain unboundedness, it is desirable to tune the forgetting factor variation

Sect. 8.7 * On-Line Parameter Estimation 377
so that data forgetting is activated when w is persistently exciting, and suspended
when w is not. We now discuss such a tuning technique and the resulting estimator
convergence and robustness properties.
A FORGETTING FACTOR TUNING TECHNIQUE
Since the magnitude of the gain matrix P is an indicator of the excitation level of W, it
is reasonable to correlate the forgetting factor variation with ||P(OII- A specific
technique for achieving this purpose is to choose
WN^O-P)
(8-109)
ko
with X and k being positive constants representing the maximum forgetting rate and
o 0
prespecified bound for gain matrix magnitude, respectively. The forgetting factor in
(8.109) implies forgetting the data with a factor X if the norm of P is small (indicating
o
strong p.e.), reducing the forgetting speed if the norm of P becomes larger and
suspends forgetting if the norm reaches the specified upper bound. Since a larger
value of X means faster forgetting (which implies both stronger ability in following
o
parameter variations, but also more oscillations in the estimated parameters due to
shorter-time "averaging" of noisy data points), the choice of X represents a tradeoff
o
between the speed of parameter tracking and the level of estimated parameter
oscillation. The gain bound k affects the speed of parameter update and also the
0
effects of disturbance in the prediction error, thus involving a similar tradeoff. To be
consistent with our gain-bounding intention, we choose || P(0) |[ < k (hence
0
P(0)<£ I). We shall refer to the least-squares estimator with the forgetting factor
o
(8.109) as the bounded-gain-forgetting (BGF) estimator, because the norm of the gain
matrix can be shown to be upper bounded by the pre-specified constant k regardless
o
of persistent excitation.
CONVERGENCE PROPERTIES
We now show that the form (8.109) of forgetting factor variation guarantees that the
resulting gain matrix P(t) is upper bounded regardless of the persistent excitation of
W, unlike the case of constant forgetting factor. With the forgetting factor form
(8.109), the gain update equation (8.104) can be expressed as
V^ (8.110)
O
This leads to

| 378  Adaptive Control          |                  |                        | Chap. 8 |
| ------------------------------ | ---------------- | ---------------------- | ------- |
| P-!(0 =P-1(O)e"V+ \' e-KC-^l—  |                  | ||P||P-1 + WrW]dr      |         |
| > (P-1(0)-yt                   | -1I)e-^' + (l//t | )I+f'e-^('-'')W7"Wrfr  |         |
|                                | o                | o                      | (8.111) |
where we used the inequality ||P(r) ||P~ '(f) > I, obtained from the fact that
Note that ||P(0)||<£  guarantees the positive-definiteness  of (P~l(0)-k ~ll),  and
|     | o   |     | o   |
| --- | --- | --- | --- |
therefore for all t> 0 ,
K
so that P(r) < £ I. Note that this implies, from (8.109), that
O
X(t) > 0
Thus, we have shown the boundedness of P and the non-negative nature o
If W(t) is p.e. as defined by (8.91), we can further show that X(t) > \\>0, and,
thus, the estimated parameters are exponentially convergent.  To show this, note that,
from (8.111) and (8.91),
+  r^8oc]I
| P(0<  | °—.r-^I  |     | (8.H2) |
| ----- | -------- | --- | ------ |
| \+k   | ae~Kob   |     |        |
0 x
This, in turn, leads to the uniform lower boundedness of the forgetting factor by a
positive constant,
| X(t) = -g(* | -||P||)  >  ° °  | '  .  - = *-i  | (8.H3) |
| ----------- | ---------------- | -------------- | ------ |
o
| ko   |     | \+kk o a xKeKb |     |
| ---- | --- | -------------- | --- |
which in turn implies the exponential convergence of the estimated parameters.  Note
that, if W is strongly p.e., i.e., (X| is very large, \{t) ~ ~k .
0
Under p.e.,  one can also show that  P(0  is uniformly  lower bounded by a
constant  p.d.  matrix,  a property  which  is  desirable  for  estimating  time-varying
parameters. Indeed, from (8.106) and (8.113),
JL

Sect. 8.7 * On-Line Parameter Estimation 379
P" '(0 < P" '(0) + f'exp [-k, (t - T) ] WTWdr
* o
The second term on the right-hand side can be regarded as the output of the stable
filter
M + X M = WrW (8.114)
x
M is bounded if W is bounded. Thus, from (8.114) and (8.112), if W is p.e. and upper
bounded, P will be upper bounded and lower bounded uniformly, i.e.,
k l<P(t)<kl
2 {
where 0 < k < k < k .
2 x 0
The properties of the BGF estimator are summarized below:
Theorem 8.1 In the bounded-gain-forgetting estimator, the parameter errors and
the gain matrix are always upper bounded; If W is persistently exciting, then the
estimated parameters converge exponentially and P(t) is upper and lower bounded
uniformly by positive definite matrices.
The advantage of the BGF method over the gradient method is that the
estimated parameters are smooth. This implies, given the allowable level of estimated
parameter oscillation, that much larger gain bound can be used in BGF method. As a
result, faster parameter convergence can be achieved.
AN ALTERNATIVE TECHNIQUE OF DATA FORGETTING
It is interesting to note that the bounded-gain forgetting is not the only way to keep
data forgetting while avoiding gain explosion. In view of the fact that the problem
with the non-zero forgetting factor is the possibility of P"1 diminishing, we may, as
an alternative to variable-forgetting approach, use the following simple gain update
modification
-P"1 = -A.(0(P~I-K -1) + WrW (8.115)
o
where K is a symmetric p.d. matrix specifying the upper bound of the gain matrix P,
o
and X(t) is a constant or time-varying positive forgetting factor independent of P. X(t)
is chosen to satisfy X < X(t) < A,j with X and A,j denoting two positive constants. The
o o
parameter update law is still (8.103). One can easily show that this gain update leads
to similar properties as the bounded-gain forgetting.

380 Adaptive Control Chap. 8
ROBUSTNESS PROPERTIES
Let us now look at the behavior of the estimator in the presence of parameter
variations and disturbances. Consider again the single-parameter estimation problem
of Example 8.12. The gain update is
f(r)
df
One notes that the presence of noise and parameter variation does not affect the gain
value.
To see how the parameter error behaves, let us note that
~[P-la]+X(t)P-lZ = -P-la + wd (8.116)
dt
This describes a first-order filter of "bandwidth" ^.(0 with {-P~la + wd) as input and
f"1 a as output. We can easily draw some conclusions about the estimator behavior
based on this relation, assuming that the signal w is persistently exciting, the
disturbance d is bounded, and the rate of parameter variation is bounded. Since P~1
has been shown to be upper bounded, the input to the filter is bounded. Furthermore,
since the forgetting factor X(f) has been shown to be lower bounded, equation (8.116)
represents an exponentially stable filter and its output P~^a is guaranteed to be
bounded. The upper boundedness of P further indicates the boundedness of a. Note
that the bound of a will depend on the magnitude of the disturbance and the parameter
variation rate a. It also depends on the persistent excitation level of the signal w(t)
(which affects X(t)).
If the signal w is not persistently exciting, then the estimator can no longer
guarantee the boundedness of parameter errors in the presence of parameter variation
and disturbances. We can only say that P(t) (being independent to the additive
disturbances and parameter variations) is bounded and the parameter errors cannot
diverge too fast.
Example 8.18: BGF estimation of the single parameter
The BGF estimator is used to estimate the time-varying parameter. In the absence of
measurement noise, the estimated and true parameters are shown in the left plot of Figure 8.25. In
the presence of measurement noise, they are shown in the right-hand side plot of Figure 8.25. [j

Sect. 8.7 On-Line Parameter Estimation 381
10 15 20 25 10 15 20 25
time(sec) time(sec)
Figure 8.25 : BGF least-squares estimation; left: without noise; right: with noise
USE OF DEAD-ZONE
Similarly to the MRAC case, one should use a small dead-zone in estimating
parameters by the previous methods. It is particularly important when the signal W(t)
is not persistently exciting, leading to the avoidance of parameter drift. The dead-zone
should now be placed on the prediction error. The size of the dead-zone should be
chosen to be larger than the range of noise and disturbance in the prediction error.
The motivation is still that small error signals are dominated by noise and cannot be
used for reliable estimation.
8.7.7 Concluding Remarks and Implementation Issues
We have discussed a number of estimators in this section. Persistent excitation is
essential for good estimation. Most estimators do not have both fast convergence and
good robustness. The gradient estimator is simple but has slow convergence. The
standard least-squares estimator is robust to noise but cannot estimate time-varying
parameters. Least-squares estimation with exponential forgetting factor has the ability
to track time-varying parameters but there is a possibility of gain windup in the
absence of persistent excitation.
A particular technique of gain tuning, called bounded-gain-forgetting, is
developed to maintain the benefits of data forgetting while avoiding gain-windup. The
resulting estimator has both fast convergence and good noise sensitivity. The
computation and analysis of this estimator is reasonably simple.
In order to have good estimation performance, many implementation issues
have to be considered carefully, including
> choice of the bandwidth of the filter for generating (8.77)

382 Adaptive Control Chap. 8
• choice of initial parameter and initial gain matrix
• choice of forgetting rate and gain bound
• choice of excitation signals
Tradeoffs and judgement have to be used in making the above choices. The filter
bandwidth should be chosen to be larger than the plant bandwidth, so that the system
signals are able to pass through. But it should be smaller than frequency range (usually
high frequency) of the noise. Of course, the initial parameter estimates should be
chosen to be as accurate as possible. The initial gain matrix should be chosen to
obtain the proper convergence speed and noise robustness. The forgetting factor
should be chosen to be large enough so that parameter variation can be tracked
sufficiently accurately. However, it cannot be chosen too large lest the gain matrix is
too large or too oscillatory. The gain bound is chosen based on the knowledge of the
noise magnitude and the allowable level of estimated parameter oscillation, with larger
noise leading to smaller gain bound. The excitation signals should contain sufficient
spectrum lines to allow parameter convergence, and their frequencies should be within
the bandwidth of the plant so as to be able to excite the plant. Note that, although
unknown parameters can be time-varying, the speed of the variation should be much
smaller than the plant bandwidth, otherwise the parameter dynamics should be
modeled.
8.8 Composite Adaptation
In the MR AC controllers developed in sections 8.2-8.4, the adaptation laws extract
information about the parameters from the tracking errors e. However, the tracking
error is not the only source of parameter information. The prediction error e\ also
contains parameter information, as reflected in the parameter estimation schemes of
section 8.7. This section examines whether the different sources of parameter
information can be combined for parameter adaptation, and whether such a combined
use of information sources can indeed improve the performance of the adaptive
controller.
These questions are answered positively by a new adaptation method, called
composite adaptation, which drives the parameter adaptation using both tracking error
and prediction error. As we shall see, such an adaptation scheme not only maintains
the global stability of the adaptive control system, but also leads to fast parameter
convergence and smaller tracking errors. Indeed, the fundamental feature of
composite adaptation is its ability to achieve quick adaptation.

Sect. 8.8 Composite Adaptation 383
Composite
Adaptation
Figure 8.26 : Composite adaptation: e - tracking error e\ - prediction error
In the following, we first describe the concept of composite adaptation using the
simple mass control example, and then extend the results to more general linear and
nonlinear systems.
COMPOSITE ADAPTATION FOR A MASS
Although the benefits of composite adaptation are most obvious in adaptive control
problems involving multiple parameters, its mechanism is most easily explained first
on the simple example of controlling a mass. Consider the system m'x = u . A MRAC
controller has been designed in Example 8.1 for this system, with the control law
being
u = mv (8.117)
and the adaptation law being
m = -yvs (8.118)
If, instead, a prediction-error based estimator is used to estimate the parameter m, then
the parameter update law is
m = -ywe (8.119)
l
Note that while the adaptation law (8.118) is driven by the tracking error s, the
estimation law (8.119) is driven by e\.
In the so-called composite adaptive control, the control is the same as (8.117),
but the adaptation law is now a "combination" of the earlier adaptation law and the
prediction-error based estimation law
m = — P[vs + w£[]
Note that this adaptation law now is driven by both s and e . Also note that the gain
(
P{t) is provided by any of the gain update laws in section 8.7.
To show the stability of the resulting adaptive control system, let us still use the
Lyapunov function candidate

384 Adaptive Control Chap. 8
V = ~[ms2 + P~lm2]
This is essentially the same as the V in (8.7) except for the replacement of 7by P{t).
If P{t) is chosen to be a constant, the derivative of V is easily found to be
V = — Xms2- — w2m2
Note that the expression of V now contains a desirable additional quadratic (only
semi-negative) term in m. Using a similar reasoning as that in Example 8.1, one can
now show that both s —> 0 and e^ —> 0 as t —>°° .
If P is time-varying and generated as in BGF estimator, i.e., using equation
(8.104), we obtain
V = - Xms2 -1 w2m2 - - X(t)P~l m2
This can also be shown to lead to s —> 0 and e —» 0 as t ->°° . Furthermore, if w is
persistently exciting, one can easily show that both .s and m are exponentially
convergent to zero, i.e., the adaptive controller has exponential convergence.
COMPOSITE ADAPTIVE CONTROL OF FIRST-ORDER SYSTEMS
The advantages of composite adaptation are most clearly seen in systems with more
than one unknown parameters. In such cases, the composite adaptation law allows
high adaptation gain to be used without getting the oscillatory behavior and slow
convergence observed for the tracking-error-based adaptation laws (see section 8.2).
Let us use the first-order system in section 8.2 to illustrate the performance features of
composite adaptive controllers.
Tracking-Error Based Adaptive Control
Using the MRAC controller in section 8.2, the control law is of the form
w = vra (8.120)
The parameter adaptation law is
a = -sgnOt )Yve (8.121)
p
with
a = [a a]T v = [r y]T
r y

| Sect. 8.8  |     |     |     |     |     | Composite Adaptation  |     | 385 |
| ---------- | --- | --- | --- | --- | --- | --------------------- | --- | --- |
Prediction-Error Based Estimation
The estimation methods of section 8.7 can also be used to estimate a and a. But
|     |     |     |     |     |     |     | r   | y   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
before doing this we have to parameterize the plant in terms of these parameters.  By
| adding a | y to both sides of (8.20), we obtain |     |     |     |     |     |     |     |
| -------- | ------------------------------------ | --- | --- | --- | --- | --- | --- | --- |
m
|     | y + a | y = -(a | -a  | )y  | + b u |     |     |     |
| --- | ----- | ------- | --- | --- | ----- | --- | --- | --- |
|     |       | m       | p m |     | p     |     |     |     |
This leads to
|     |          | \  ,  | ,       |        | apam |     |     |     |
| --- | -------- | ----- | ------- | ------ | ---- | --- | --- | --- |
|     | u = —{p  |       | + a )y  | + -z-  | y    |     |     |     |
m
|     |     | b   p  |     |     | bup |     |     |     |
| --- | --- | ------ | --- | --- | --- | --- | --- | --- |
"
Since the ideal controller parameters and the plant parameters are related by (8.24), we
obtain
|     |        | (P +  | ajy |       |     |     |     |     |
| --- | ------ | ----- | --- | ----- | --- | --- | --- | --- |
|     | u = a  |       |     | +  ay |     |     |     |     |
r
bm
| Multiplying both sides by  |     |     | 1 /(p + a |     | ),  we then obtain |     |     |     |
| -------------------------- | --- | --- | --------- | --- | ------------------ | --- | --- | --- |
m
|     |       | u    |   _L  | +        | y   |     |     |     |
| --- | ----- | ---- | ----- | -------- | --- | --- | --- | --- |
|     |       |   =  | ar b  |  ayP + a |     |     |     |     |
|     | p + a |      |       |          |     |     |     |     |
|     |       | m    | m     |          | m   |     |     |     |
This can be compactly expressed in the linear parametrization form
M[ = wa
with
|     |       | u     |     | r        | ,7      | r y     | y  i    |     |
| --- | ----- | ----- | --- | -------- | ------- | ------- | ------- | --- |
|     | «1 =  |       |     | a = [ a  | r aY  y | w = [—  | —-—]    |     |
|     |       | p + a | m   |          | *       | b m     | p + a m |     |
Therefore, we can straightforwardly  use the estimation algorithms of section 8.7 to
obtain the following estimation laws
|     | a = -Pwe,  |     |     |     |     |     |     | (8.122) |
| --- | ---------- | --- | --- | --- | --- | --- | --- | ------- |
where e\ is the prediction error on«| .
Composite Adaptive Control
The composite adaptation laws can be easily constructed, from (8.121) and (8.122), as
|     | a = -P[sgn(6  |     | )\e  | + a{t)v/e]  | x   | •   |     | (8.123) |
| --- | ------------- | --- | ---- | ----------- | --- | --- | --- | ------- |

386 Adaptive Control Chap. 8
The controller is the same as in (8.120).
To analyze the stability and convergence of the composite adaptive controller,
one can still use the Lyapunov function in (8.29). If P is chosen to be constant, one has
One can easily show that e —> 0 and e) —> 0 as t —> °° .
If P is updated by the least-squares type algorithms, one can obtain similar
results. For example, if P is updated by (8.104), we can use the Lyapunov function
candidate
V = -[e2+aTP-lsi]
whose derivative is
From this, we can infer asymptotic and exponential convergence results, similarly to
the previous mass-control case.
Simulation Results
Simulations are used to illustrate the behavior of the composite adaptive controller.
Example 8.19: Composite adaptive control of first-order systems
The same first-order system as in section 8.2 is used for composite adaptive control. Everything is
as in section 8.2, except that now the prediction error term is incorporated into the adaptation law.
For the case of r(t) = 4, the tracking and estimation results are shown in Figure 8.27. The results
for r(() = 4 sin3( are shown in Figure 8.28. It is seen the parameter and tracking results are both
smooth. One can further increase the adaptation gain to obtain smaller tracking errors without
incurring much oscillation in the estimated parameters. LJ
The advantage of the composite adaptive controller essentially comes from the
smoothness of the results. This has significant implications on the adaptive control
performance. Due to the possibility of using high adaptation gain, we can obtain
smaller tracking error, faster parameter convergence without exciting high-frequency
unmodeled dynamics. In fact, simulations show that composite adaptive controllers
perform much better than standard adaptive controllers when unmodeled dynamics are
present.
i

| Sect. 8.8 |     |     | Composite Adaptation  |     | 387 |
| --------- | --- | --- | --------------------- | --- | --- |
-2.0
|     | 2.0 3.0  4.0  | 5.0 |     | 2.0 3.0  4.0  | 5.0 |
| --- | ------------- | --- | --- | ------------- | --- |
|     | time(sec)     |     |     | time(sec)     |     |
Figure 8.27 : Tracking performance and parameter estimation
r(t) = 4, composite adaptation
| 4.0     |               |     | 2.0     |               |     |
| ------- | ------------- | --- | ------- | ------------- | --- |
| 3.0     |               |     | 1.5     |               |     |
| 2.0     |               |     | 1.0     |               |     |
| 1.0     |               |     | 0.5     |               |     |
| 0.0     |               |     | 0.0     |               |     |
| -1.0    |               |     | -0.5    |               |     |
| -2.0    |               |     | -1.0    |               |     |
| -3.0    |               |     | -1.5    |               |     |
| -4.0    |               |     | -2.0    |               |     |
| 0.0 1.0 | 2.0 3.0  4.0  | 5.0 | 0.0 1.0 | 2.0 3.0  4.0  | 5.0 |
time(sec)
time(sec)
Figure 8.28 : Tracking performance and parameter estimation
r(t) = 4 sin 3?, composite adaptation
Interpretation of Composite Adaptation
To  gain  an  intuitive  interpretation  of  the  composite  adaptation  law,  let  us  for
simplicity choose P(f) = yl.  Using (8.123) and (8.89), the composite adaptation law
can be expressed as
a + ywrwa = -y vTe
(8.125)
Without the prediction term, we obtain the original MRAC adaptation law (8.28)
| i = -yyT |     |     |     |     | (8.126) |
| -------- | --- | --- | --- | --- | ------- |
e
Comparing (8.125) and (8.126), one notes that (8.126) represents an integrator while
(8.125) a time-varying  low-pass  filter.  Both tend  to attenuate the  high-frequency
components in <?, and thus parameters in both cases tend to be smoother than the
tracking errors. However, an integrator also attenuates low frequency components, as

388 Adaptive Control Chap. 8
: can be seen from its Bode plot. The stable filter in (8.125), on the other hand, has
i much less attenuation on the low frequency components in e (for example, if w is a
constant, (8.125) is a stable filter with a bandwidth of yw2). Therefore, the parameter
search in the composite adaptation goes along an "average" or "filtered" direction as
I specified by the low frequency components in the tracking error e. This explains the
smoothness of the parameter estimates in composite adaptive control.
i As shown in this section, the principle of composite adaptation is to combine a
I tracking-error based adaptation law and a prediction-error based parameter estimation
law. This idea can be straightforwardly extended to adaptive control in general. Note
that one must parameterize both the plant model and the controller using a common
I set of parameters in order to be able to combine the two types of errors for adaptation.
i In chapter 9, we shall discuss the application of this idea to the adaptive control of
robot manipulators, an important class of multi-input multi-output nonlinear systems.
8.9 Summary
Adaptive control is an appealing approach for controlling uncertain dynamic systems.
In principle, the systems can be uncertain in terms of its dynamic structure or its
parameters. So far, however, adaptive control can only deal with parameter-uncertain
systems. Furthermore, existing adaptation methods generally require linear
parametrization of the control law or the system dynamics.
Systematic theories exist on how to design adaptive controllers for general
linear systems. If the full state is available, adaptive control design and
implementation is quite simple. If only output feedback is available, however,
adaptive control design is much more involved because of the need to introduce
dynamics into the controller. Some classes of nonlinear systems can also be adaptively
controlled.
In MRAC systems, the adaptation law extracts parameter information from the
tracking errors. In self-tuning controllers, the parameter estimator extracts information
from prediction errors. In a new technique called composite adaptive control, the
adaptation law extracts parameter information from both sources. This new adaptation
method leads to faster adaptation without incurring significant oscillation in the
estimated parameters, thus yielding improved performance.

Sect. 8.11 Exercises 389
8.10 Notes and References
Analyses and discussions on the material of this chapter can be found, e.g., in the recent books
[Narendra and Annasswamy, 1989], which provides a systematic treatment of model-reference
adaptive control theory for linear systems, and [Astrb'm and Wittenmark, 1989], which includes
extensive studies of self-tuning algorithms as well as discussions of adaptive control implementation
issues. The basic formulation of a Lyapunov formalism for model-reference adaptive control is due
to [Parks, 1966]. Detailed discussions of discrete versions and self-tuning control can be found in
[Goodwin and Sin, 1984]. Passivity interpretations of model reference adaptive controllers are
discussed in [Landau, 1979]. Detailed studies of robustness can be found, e.g., in [Ioannou and
Kokotovic, 1983; Anderson, el al., 1986; Sastry and Bodson, 1989] and references therein.
The theoretical framework in section 8.4 is based on [Narendra and Annasswamy, 1989],
from which Lemmas 8.1 and 8.2 and Figures 8.14 and 8.17 are adapted. Example 8.7 and Figure
8.18 are based on [Rohrs, et al, 1985].
The development of section 8.5 is adapted from [Slotine and Coetsee, 1986], which also
details "robust" combinations with sliding control terms. Extensions and applications to specific
classes of nonlinear MIMO systems (robot manipulators) are developed in [Slotine and Li, 1986,
1987], and will be further detailed in chapter 9. [Taylor, et al, 1988, 1989] study extensions to
general MIMO systems under certain matching conditions, and most interestingly a singular
perturbation analysis of the effects of unmodeled dynamics. [Kanellakopoulos, et al, 1989] develop
adaptive nonlinear controllers under some less stringent, "extended" matching conditions. [Sastry
and Isidori, 1989] consider output tracking under the two assumptions of uniformly exponentially
stable zero-dynamics and of global Lipschitzness of the regressor. [Bastin and Campion, 1989;
Pomet and Praly, 1989] study indirect approaches to adaptive control of nonlinear systems.
Discrete-time parameter estimation is extensively studied in [Ljung, 1987]. The development
of section 8.7 is adapted from [Li and Slotine, 1987]. Related discussions can be found in
[Middleton, et al, 1988]. [Nicolo and Katende, 1982; Atkeson, et al, 1985; Khoshla and Kanade,
1985] detail linear parametrizations for robot dynamics.
Our discussion of section 8.8 is based on [Slotine and Li, 1987d, 1989] (see also chapter 9).
A closely related approach is presented in [Narendra and Duarte, 1988, 1989] using separate
controller and regressor parametrizations.
8.11 Exercises
8.1 Draw the block diagram for the adaptive mass control system in Example 8.1. Discuss the
intuitive reasonableness of the adaptation law.

| 390  Adaptive Control  |     | Chap. 8 |
| ---------------------- | --- | ------- |
8.2  Simulate the adaptive control system for the nonlinear first order plant in section 8.2, but with
the nonlinearity beingfiy) = siny.
8.3  Simulate the adaptive control system for the second order plant
| with a  = 0.1,   = -4,ft=2 |     |     |
| -------------------------- | --- | --- |
| pl  V                      | p   |     |
8.4  Consider a second-order linear system with a constant unknown disturbance d. Compare the
structure of a P.I.D. controller with that of a P.D. controller with adaptive compensation of d.
8.5  Carry out the detailed proof of tracking error convergence for general linear systems with
relative degree 1 (section 8.4.1).
8.6  Simulate the adaptive control system for the second order plant
| P2+a PlP+ap2 |     |     |
| ------------ | --- | --- |
with j|  = 0.1, a  2 = - 4,6  = 2 for two cases. In the first case, the output y and its derivative y are
assumed to be available. In the second case, only y is assumed to be available.
8.7  For the system
| x, = sinx +  | N t + 1 x |     |
| ------------ | --------- | --- |
2 2
design an adaptive controller to track an arbitrary desired trajectory  x dx (t).  Assume that the state
[Xj  x]T  is measured, that x (i)  ,'x (t),  i (t)  are all known, and that ot| and rx are unknown
| 2   | dx dx d{ | 2   |
| --- | -------- | --- |
constants.
Write the full expression of the controller, as a function of the measured state  [xj  x]  •
2
Check your design in simple simulations. {Hint: First feedback linearize the system by differentiating
the first equation.)
8.8  Consider systems of the form
where the state vector x= [y y .... ;y("~')]r is measured, the/) are known nonlinear functions of
the state and time,  h  and the a,  are unknown  constants (or very slowly  varying  "average"
coefficients), with h > 0 , and the time-varying quantities  a,-(f) are unknown but of known bounds v

Sect. 8.11 Exercises 391
(possibly state-dependent or time-varying)
Show that the ideas of chapter 7 and section 8.5 can be combined to yield a robust adaptive
controller. To do so, essentially replace s by s^ = s — <I>sat(.s/<I>) in the Lyapunov function of
section 8.5, i.e., use
n
V = hs 2 + [y~i~h2 + XY-'2,2]
A o
For simplicity, you may first choose <I> to be constant.
Show that, assuming that the noise level in the system is small, the boundary layer concept
leads to a natural choice of adaptation dead-zone (Hint: Choose the sliding control terms and the
boundary layer thickness <t> as if the constant parameters a were known, and note that s = 0 in the
t A
boundary layer).
Illustrate your design in simple simulations. (Adapted from [Slotine and Coetsee, 1986]).
8.9 For the nonlinear adaptive controller of section 8.5, show that if a priori bounds are known on
certain parameters, tracking convergence is preserved by temporarily stopping adaptation on a given
parameter estimate if the adaptation law would otherwise drive the estimate outside the known
bounds.
8.10 Discuss intuitively why parameter estimation can be easier on unstable systems than on
stable systems.
8.11 Derive a composite adaptive controller for the nonlinear first-order plant in section 8.2.
Simulate its behavior using different gains.

Chapter 9
Control of Multi-Input Physical Systems
As seen in the previous chapters, feedback control is well understood for large classes
of nonlinear systems with single inputs or uncoupled multiple inputs. For general
multi-input nonlinear systems, however, feedback control and especially robustness
issues are still research topics, the urgency of which has been rendered more acute by
the recent development of machines with challenging nonlinear dynamics, such as
robot manipulators, high-performance aircraft, or advanced underwater and space
vehicles.
In this chapter, we show that the new, richer control problems posed by
nonlinear systems may benefit from taking some distance from purely mathematical
approaches and having a closer look at the physics of the systems. The discussion
may be viewed as a renewed emphasis on the original motivation of Lyapunov theory,
which, as we saw in chapter 3, evolved from physical considerations.
In the following, we first motivate the approach by considering a specific
example, the trajectory control of robot manipulators. We then discuss generalizations
to other classes of controller design problems.
392

Sect. 9.1 Robotics as a Prototype 393
9.1 Robotics as a Prototype
Robot manipulators are familiar examples of trajectory-controllable mechanical
systems. However, their nonlinear dynamics present a challenging control problem,
since traditional linear control approaches do not easily apply. For a while, the
difficulty was mitigated by the fact that manipulators were highly geared, thereby
strongly reducing the interactive dynamic effects between links (it can be easily shown
that, in geared manipulators, the nonlinear or time-varying dynamic effects are divided
either by the transmission ratio r or by r2, with typical values of r being about 100).
However, in recent years, as the need for achieving greater accuracy in tracking and
force control made designs evolve towards "cleaner" approaches, such as gear-free
direct-drive arms (featuring reduced friction and avoiding backlash altogether) or low-
reduction cable-driven mechanisms, explicit account of the nonlinear dynamic effects
became critical in order to exploit the full dynamic potential of the new high-
performance manipulator arms.
Consider, for instance, a planar, two-link, articulated manipulator (Figure 9.1),
whose position can be described by a 2-vector q of joint angles, and whose actuator
inputs consist of a 2-vector T of torques applied at the manipulator joints. The
dynamics of this simple manipulator is strongly nonlinear, and can be written in the
general form
H(q)q + C(q,q)q + g(q) = T (9.1)
where H(q) is the 2x2 manipulator inertia matrix (which is symmetric positive
definite), C(q,q)q is a 2-vector of centripetal and Coriolis torques (with C(q,q) a 2x2
matrix), and g(q) is the 2-vector of gravitational torques. The feedback control
problem for such a system is to compute the required actuator inputs to perform
desired tasks (e.g., follow a desired trajectory), given the measured system state,
namely the vector q of joint angles, and the vector q of joint velocities.
Note that the inertia matrix H depends on the joint position q, consistently with
physical insight (for instance, as viewed from its "shoulder", a stretched arm has a
larger inertia than a folded arm). The centripetal torques vary with the square of
individual joint velocities, while the Coriolis torques vary with the products of
velocities at two different joints.
Also, note that the kinetic energy of the manipulator is (similarly to 1/2 m v2
for a one degree-of-freedom system)

394 Control of Multi-Input Physical Systems Chap. 9
unknown load
Figure 9.1: An articulated two-link manipulator
This expression accounts for the positive definiteness of the inertia matrix H(q).
Indeed, the kinetic energy must be strictly positive for any joint position q and any
non-zero joint velocity q. More precisely, in later developments, we shall use the fact
that H(q) is uniformly positive definite, i.e., that there exists a constant a > 0 such
that, for all positions q in the robot's workspace,
H(q) > al
where I is the identity matrix. This property can be seen by noticing that, if there did
not exist such an a > 0, then there would be a position q in the workspace where the
inertia matrix has a zero eigenvalue, because the workspace is a closed set; letting v
0
be the eigenvector associated with this zero eigenvalue, the robot arm could move
with a unit velocity (v /||v ||) but with zero kinetic energy, an impossibility. Thus,
o 0
H(q) is indeed uniformly positive definite.
9.1.1 Position Control
Let us assume that the manipulator of Figure 9.1 is in the horizontal plane (g(q) = 0),
and that the task is simply to move it to a given final position, as specified by a
constant vector q of desired joint angles. It is physically clear (as already mentioned
d
in chapter 3) that a joint proportional-derivative (P.D.) controller, namely a feedback
i

Sect. 9.1 Robotics as a Prototype 395
control law that selects each actuator input independently, based on the local
measurements of position errors q.- = q.- - q^ and joint velocities q.- (J = 1,2)
xj = -kPj4j-kDj<ij (9-2)
will achieve the desired position control task. Indeed, the control law (9.2), where kp:
and kpj are strictly positive constants, is simply mimicking the effect of equipping
each of the manipulator's joints with a passive mechanical device composed of a coil-
spring and a damper, and having the desired q : as its rest position. The resulting
d
passive physical system would simply exhibit damped oscillations towards the rest
position q^.
Yet, writing the system dynamics in the " f = m a " (i.e., Newtonian) form (9.1)
does not easily capture this simple fact. In order to formalize the above discussion, a
more appropriate approach is to rewrite the system's dynamics in terms of energy
transfers (i.e., in a Hamiltonian form). We can write conservation of energy in the
form
l^[qrHq] = f.t (9.3)
2 at
where the left-hand side is the derivative of the manipulator's kinetic energy, and the
right-hand side represents the power input from the actuators. Expression (9.3) does
not mean, of course, that the Coriolis and centripetal terms of (9.1) have disappeared,
but simply that they are now accounted for implicitly, since they stem from the time-
variation of the inertia matrix H. The stability and convergence proof for the P.D.
controller above can then be derived very simply. Let us actually take the control input
in a form slightly more general than (9.2), namely
T = - K q - K q (9.4)
P D
where Kp and K^ are constant symmetric positive definite matrices (the usual P.D.
controller (9.2) corresponds to having Kp and K diagonal), and let us consider the
D
total mechanical energy V that would be associated with the system if control law
(9.4) were implemented using physical springs and dampers, namely
V =i[q7'Hq + q7'Kpq] (9.5)
To analyze the closed-loop behavior of the controlled system, we shall use this virtual
mechanical energy V as our Lyapunov function, very similarly to what we chose for
the nonlinear mass-spring-damper systems of Chapter 3. The time-derivative of V can
be written, given (9.3), as

396 Control of Multi-Input Physical Systems Chap. 9
V'=qr(T+K q)
p
which, using control law (9.4), simplifies as
i> = -qTK q <0
D
Not surprisingly, we recognize V as the power dissipated by the virtual dampers. We
now only need to check that the system cannot get "stuck" at a stage where V equal 0
while q does not equal q , or, to put it more technically, invoke the invariant-set
d
theorem. Since V = 0 implies that q = 0 , which in turn implies that q = HHKpq ,
one has that V is identically 0 only if q equals 0. Therefore the system does converge
to the desired state, as the physical reasoning suggested.
Example 9.1 Let us illustrate the above result in a simple simulation. Consider the two-link
manipulator of Figure 9.1, whose dynamics can be written explicitly as
~hij -
2
»2l "22 §2 hq x
where
/|j = aj + 2133 cos q 2 + 2 <J 4 sin q^
j2 = #2j = ai + ai cos ^2 + a4 s'n Ql
H = a
22 2
h = a sin q -«cost
3 2 4 ?2
with
a x = <\ + m\
a 2 = 'ce2
a cos 8,,
3 =
a 4 = me >l 'ce sin 8 e
In the simulation, we use
= .12 = 0.5
The robot, initially at rest at (<7j =0, q- 0) , is commanded a step to
2
(<7<;i = ^°' ^d2 = 90°) • The corresponding transient position errors (translated in degrees, while
all control computations and gains use radians) and control torques are plotted in Figure 9.2, with
1

| Sect. 9.1 |     | Robotics as a Prototype  |     | 397 |
| --------- | --- | ------------------------ | --- | --- |
K D  = 100 I, K P   = 20 K D  . We see that indeed the P.D. controller achieves position control after
| a stable transient.  |     |     |     | C]  |
| -------------------- | --- | --- | --- | --- |
r
| 20  |     | 20  |     |     |
| --- | --- | --- | --- | --- |
f\ -
o
0
| 3 UOIJIS u |     | c   |     |     |
| ---------- | --- | --- | --- | --- |
o
-20
-20
| a r 7/ |     | o -40 |     |     |
| ------ | --- | ----- | --- | --- |
-40
| J   |     | -J60/ |     |     |
| --- | --- | ----- | --- | --- |
-60
| -80           |               | 100'      | I I I          | II  |
| ------------- | ------------- | --------- | -------------- | --- |
| 0.0 0.2  0.4  | 0.6  0.8  1.0 | 0.0  0.2  | 0.4  0.6  0.8  | 1.0 |
|               | time(sec)     |           | time(sec)      |     |
-
| 3e+O3r-      |     | 3e+03 |     |     |
| ------------ | --- | ----- | --- | --- |
| uqrotlortnoc |     | 1"    |     |     |
2e+03 U
1 2e+O3
ao
le+03
c le+03
o u
| 0e+00 |     | \   |     |     |
| ----- | --- | --- | --- | --- |
0e+00 \
-le+03
| -2e+03 |     | -le+03 |     |     |
| ------ | --- | ------ | --- | --- |
0.2  I I 0.4  I 0.6  II 0.8  1.0 0.0  0.2  I I 0.4  I 0.6  II 0.8  1.0
0.0
|     | time(sec) |     | time(sec) |     |
| --- | --------- | --- | --------- | --- |
Figure 9.2a : Position errors (in degrees) and control torques under P.D. control
9.1.2  Trajectory Control
We now consider the case when the manipulator is actually required to follow a
desired trajectory, rather than merely reach a desired position.  Note that a trajectory
control problem may arise even when the task is merely to move a load from its initial
position to a final desired position. This may be due to requirements on the maximum
time to complete the task, or may be necessary to avoid overshooting or otherwise
bumping into obstacles during the task.  These needs in turn specify  the required
"tracking" accuracy.
The simple P.D. controller above cannot be expected to handle the dynamic
demands of trajectory  tracking effectively.  We consider first  the use of  feedback
linearization. We then discuss the extension of the robustness results of Chapter 7 to
this multi-input case.  In section 9.2, we consider adaptive versions of the robust

398 Control of Multi-Input Physical Systems Chap. 9
controller. Note that the development is applicable to manipulators with an arbitrary
number of degrees of freedom, and having revolute or translational joints (or both).
FEEDBACK LINEARIZATION
Given the simple structure of Equation (9.1), the derivation of a feedback linearizing
transformation is straightforward. Taking T. of the form
T = H(q)v + C(q,q)q + g(q) (9.6)
where v is the new control input, leads to
Expression (9.6) is known as the "computed torque" in the robotics literature. Let us
define q = q - q^ as the tracking error. Letting
v = q - 2 X £[ - X2 q (X > 0)
d
then leads to the exponentially stable closed-loop dynamics
= 0
This assumes, of course, that the dynamic model, used in (9.6), is exact.
ROBUST CONTROL
Consider now the derivation of a robust trajectory controller. In the multi-input case,
many possibilities are available to specify the analog of sliding condition (7.5). One
may require sliding conditions of the form
to be verified individually along each degree of freedom i, with s- = q + X- cjj , as in
( i t
section 7.4. One may also interpret s2 in (7.5) as the squared norm of the distance to
the surface s = 0, and require in the multi-input case that
2dt
with, generalizing the single-input case (7.3), the vector s defined as,
s = q + Aq (9.7)
1
where A is a symmetric positive definite matrix, or more generally a matrix such that
- A is Hurwitz.

Sect. 9.1 Robotics as a Prototype 399
While both of these approaches are reasonable, it seems plausible, given the
results of the previous section, that the design may be simpler using in the sliding
condition the generalized squared norm s^Hs (obtained formally by replacing q by s
in the expression of the kinetic energy) rather than merely sT s. Indeed, in this second-
order system, we may interpret s of (9.7) as a "velocity error" term
q-q (9.8)
r
where
The "reference velocity" vector q, is formed by shifting the desired velocities q^
r
according to the position error q . It simply represents a notational manipulation which
allows one to translate energy-related properties (expressed in terms of the actual joint
velocity vector q ) into trajectory control properties (expressed in terms of the virtual
velocity error vector s). Similarly to the single-input case, the vector s conveys
information about boundedness and convergence of q and q , since the definition (9.8)
of s can also be viewed as a stable first-order differential equation in q , with s as an
input. Thus, assuming bounded initial conditions, showing the boundedness of s also
shows the boundedness of q and q, and therefore of q and q ; similarly, if s tends to 0
as t tends to infinity, so do the vectors q and q .
Our previous discussion of energy conservation also needs to be formalized a
step further. In the presence of external gravity torques g(q), energy conservation can
be written (generalizing (9.3)) as
l (9.9)
Differentiating the right-hand side explicitly
and expanding the term Hq using the system dynamics (9.1), we conclude, after
simplification of the input terms (x - g), that for all q
qr(H-2C)q = 0 (9.10)
This result suggests that the matrix (H - 2C) is skew-symmetric - this is not quite a
direct consequence of (9.10), since the matrix itself depends on q . Actually, while the
Coriolis and centripetal torque vector C q and the joint velocity vector q are uniquely
defined physical quantities, this does not define uniquely the matrix C. However, as

400 Control of Multi-Input Physical Systems Chap. 9
detailed below, with C defined component-wise by
1 "8//, i " dH dH
7 ik ik
the matrix (H - 2C) is indeed skew-symmetric, a fact which thus can be viewed as a
matrix expression of energy conservation.
Proof: Showing the above technical result (9.11) requires a more detailed look at the derivation
of the manipulator's dynamic equations. The total kinetic energy of the manipulator is
while the potential (gravitational) energy G associated with the robot links is a function only of
the manipulator position q ,
G = G(q)
Thus, the system's Lagragian is
L = 7--G = iqrH(q)q-G(q)
Lagrange's equations,
d dL _ dL _
df d q 3 q
then yield the dynamic equations of the manipulator, in the form
H q + b(q, q) + g(q) = T (9.12)
where the gravitational torque vector g(q) is simply
and the «xl vector b
is the vector of Coriolis and centripetal torques.
Let us examine the vector b(q, q) more closely. First, we note that each component of b is a
quadratic function of the joint velocity components q^. This can be seen by noting that the ith
component of b is

Sect. 9.1 Robotics as a Prototype 401
where the coefficients h^ are functions only of the joint positions, and verify
'Jk " 3ft 2 3 .
?|
We can write fo as the product of a lx« row-vector c-(q, q) and the velocity vector q
; (
i,. = c,q
Accordingly, the vector b(q, q) can be written as the product of a matrix C and the velocity
vector q,
b(q,q) = C(q,q)q (9.14)
where C is the matrix obtained by stacking up the row vectors c,-.
While the physical quantities b and q are uniquely defined, there are many choices of C
which can achieve the decomposition in (9.14). For example, a quadratic function
can correspond to either
cl=l<7l+<?2 Qi+hi
Now, by reindexing, we can rewrite bj in (9.13) as
and therefore, a particular choice of the matrix C is that given by (9.11)
The above expression can also be written
I . i " 3 Hjk d Hj

402 Control of Multi-Input Physical Systems Chap. 9
which shows that, with this particular definition of C, the matrix H-2C is indeed skew-
symmetric, n
Note that, since H, and therefore H, are symmetric matrices, the skew-
symmetry of the matrix H-2C can also be written
H = C + CT
In practice, for manipulators with only a few degrees of freedom, this equality may be
sufficient to derive the proper form of C without explicitly using (9.11).
With this further formalization of energy conservation, we are now ready to
address the robust trajectory control problem. Let us define
(9.15)
Differentiating
V(t) = sr(Hq-Hq) + I srHs
r
and substituting Hq from the system dynamics,
Hq = x-Cq-g= T-C(s + q)-g
r
yields
V(t) = sr(T-Hq-Cq,.-g) (9.16)
r
where the skew-symmetry of (H - 2C) has been used to eliminate the term 1/2 s^Hs .
Similarly to the single-input case, let us now define the control input to be of
the form
x = x - k sgn{s)
where k sgn(s) is defined as the vector of components kj sgn(Sj), and, similarly to the
term u in chapter 7, x is the control input vector which would make V equal 0 if the
dynamics were exactly known
We then have
V = sr[H(q)q, +C(q,q)q
r
J

| Sect. 9.2  |     | Adaptive Robot Trajectory Control |     | 403 |
| ---------- | --- | --------------------------------- | --- | --- |
Given bounds on modeling errors H , C ,and g , where
| H=H-H  | C=C-C  | g=g-g |     |     |
| ------ | ------ | ----- | --- | --- |
we see that choosing the components k of the vector k such that
t
k; > |[H(q)q,  +C(q,q)q
r
(where the constants  T|-  are strictly  positive)  allows  one to satisfy  the sliding
(
condition
V <-  XTI^-I
(= 1
As in the single-input case, the above sliding condition guarantees that the
surface s = 0 is reached in a finite time, and that once on the surface the trajectories
remain on the surface, and therefore tend to q/t)  exponentially. The control chattering
implied by the switching gains k can be eliminated by using smooth interpolations.
Example 9.2  Consider again the two-link manipulator of Example 9.1. The control law is now
A  ir
|     | "A          | -hq  - | k sat(j,/0.05) |     |
| --- | ----------- | ------ | -------------- | --- |
|     | "n  "12  ii | 2      | y              |     |
|     | A  A        |        | k sat(i/0.05)  |     |
2 2
H2\  H22\\clr2
The robot parameters  used in the simulation are the same as in Example 9.1. The controller
design assumes a maximum uncertainty of 25 % on the mass properties of the system.  The actual
parameter inaccuracy  used in the simulations is 20 % . We let A = 20 I, r\ = r| = 0.1 . The
x 2
ranges ^  = <t> = 0.05  2 of the interpolations are chosen so that the maximum value of each &,/<!>.
| is approximately equal to the diagonal values of K |     |  in Example 9.1. |     |     |
| -------------------------------------------------- | --- | ---------------- | --- | --- |
D
The robot, initially at rest at (<5>i = 0, q — 0) , is commanded a desired trajectory
2
| q dl | (t)  = 30" (I -cos (27t/)) |   qdl (t)  = 45°(1 -cos(27t/)) |     |     |
| ---- | -------------------------- | ------------------------------ | --- | --- |
The corresponding position errors and control torques are plotted in Figure 9.3.  O
| 9.2  Adaptive Robot Trajectory  |     | Control |     |     |
| ------------------------------- | --- | ------- | --- | --- |
In this section, we show that, as in the case of regulation using P.D. control, the
trajectory control problem can actually be addressed without any a priori knowledge of
the system's mass properties, by developing adaptive versions of the robust controller
discussed above.

404 Control of Multi-Input Physical Systems Chap. 9
0.2 1.5
0.1 1.0
0.0 0.5
-0.1 0.0
-0.2 •0.5
-0.3 -1.0
0.5 1.0 1.5 2.0 2.5 3.0 0.0 0.5 1.0 1.5 2.0 2.5 3.0
time(sec) time(sec)
200 100
2 100 50
-100 -50
-200 -100
0.0 0.5 1.0 1.5 2.0 2.5 3.0 0.0 0.5 1.0 1.5 2.0 2.5 3.0
time(sec) time(sec)
Figure 9.3 : Tracking errors and control torques under sliding control
9.2.1 The Basic Algorithm
Given the desired trajectory q^(0 (we shall assume that the desired position, velocity,
and acceleration are all bounded), and with some or all the manipulator parameters
being unknown, the adaptive controller design problem is to derive a control law for
the actuator torques, and an estimation law for the unknown parameters, such that the
manipulator output q(f) closely tracks the desired trajectory. To this effect let us
define a = a — a as the parameter estimation error, with a being a constant vector of
unknown parameters describing the manipulator's mass properties, and a its estimate.
We now consider, instead of (9.11), the Lyapunov function candidate
a] (9.17)
where V is a symmetric positive definite matrix. Differentiating, and using (9.16),
yields
V(t) =sr(T-Hq,.-Cq,-g)

Sect. 9.2 Adaptive Robot Trajectory Control 405
At this point, we exploit an additional physical property of the system, namely
that, given a proper definition of the unknown parameter vector a describing the
manipulator's mass properties, the terms H(q), C(q, q), and g(q), all depend linearly
on a. This property, already mentioned in chapter 8, can be immediately verified on
the dynamics of the two-link manipulator in Example 9.1, and is obtained in general
by referring all mass properties to the individual joint axes. Thus, we can define a
known matrix Y = Y(q,q,q,q,.) such that
r
)q +C(q,q)q,. + g(q) = Y(q,q,q.,q ) a
r ; r
Taking the control law to be
T = Ya-K s (9.18)
D
which includes a "feedforward" term Y a (which is the same as the term x of the
robust controller) in addition to a simple P.D. term K s , leads to
D
= srYa - srK D s a
Updating the parameter estimates a according to the correlation integrals
(9.19)
then yields
V(t) = -sTK s < 0 (9.20)
D
This implies (as intuition suggests, and as can be shown easily using Barbalat's lemma
of section 4.3.2, as detailed below), that the output error converges to the surface s = 0
, which, given the filter-like definition (9.8) of s, in turn shows that q and q tend to 0
as t tends to infinity. Therefore, both global stability of the system {i.e., boundedness
of the vectors q, q, and a), and convergence of the tracking error, are guaranteed by
the above adaptive controller.
Proof: Given the expression (9.20) of V, it suffices to show that V —> 0 as t —> °° in order to show
that s —> 0 as ; —> °°
V -> 0 => s -> 0
Furthermore, since V is positive, Barbalat's lemma indicates that V does tend to zero if it is
uniformly continuous, and in particular if V is bounded
V bounded => V -> 0 => s -> 0
Since, given (9.20), one has V = - 2 sT K s , this shows that
D

406 Control of Multi-Input Physical Systems Chap. 9
(s and s bounded) => V bounded => V —> 0 => s —> 0
Thus, we only have to show that s and s remain bounded.
Now since V>0 and V<0, V remains bounded. Given the expression (9.17) of V, this
implies that both s and a are bounded. Furthermore, this in turn implies that q, q, and a are all
bounded. Noticing that the closed-loop dynamics can be written in the simple form
Hs + (C + K )s = Ya (9.21)
D
this shows (since the uniform positive definiteness of H implies that H~' exists and is bounded)
that s is also bounded.
Thus, s —> 0 as t —> °° , which implies that both q and q tend to 0 as f tends to infinity. CD
Note that this approach does not necessarily estimate the unknown parameters
exactly, but simply generates values that allow the desired task to be achieved.
Similarly to the discussion of section 8.7, "sufficient richness" conditions on the
desired trajectory indicate how demanding the desired trajectory should be for
tracking convergence to necessarily require parameter convergence. Also, of course,
the tracking error does not merely tend "asymptotically" to zero, but for all practical
purposes, converges within finite time constants determined for a given trajectory by
the values of the gain matrices A , K , and F, themselves limited by the presence of
D
high-frequency unmodeled dynamics and measurement noise.
While it may seem somewhat superfluous to keep estimating the parameter
vector a in order to drive the very same manipulator, the practical relevance of the
above approach is that the possibly large unknown loads that the manipulator may
carry can also be directly accounted for, simply by considering the (securely) grasped
load as part of the last link. Actually, since the mass properties of the manipulator
itself do not change, one may adapt only on the mass properties of the load (which can
be described by at most 10 parameters, namely load mass, three parameters describing
the position of the center of mass, and six independent parameters describing the
symmetric load inertia matrix).
Furthermore, by combining this section's results with those of the previous
section, the approach can be easily extended to the case where only a few significant
parameters have to be adapted upon (in order to simplify the computations, for
instance), while the controller is robust to residual errors resulting from inaccuracies
on the a priori estimates of the other parameters (as well as, perhaps, to bounded time-
varying additive disturbances such as stiction).

Sect. 9.2 Adaptive Robot Trajectory Control 407
Example 9.3 Let us illustrate the basic properties of the adaptive controller on the two-link
manipulator of Examples 9.1 and 9.2.
With A = 20 I (as in Example 9.2) and K = 100 I (leading to the same P.D. gains as in
o
Example 9.1), the control law can be written
100 i,
"
A
H 2\ hq. 0 in 100 s 2
where h and the H-: are defined as before. Therefore, the components of the matrix Y can be
t
written explicitly as
Y\\ = in Yn = 'in Yn = 'in+'in
<?2 <7r2) sin<?2
1\ In
K = §
23 r
= 5 r i sin<72 i k r \
The adaptation law (9.19) uses the above expression of Y, with V = diag[.O3 .05 .1 .3].
The actual parameters used in the simulation are the same as in Examples 9.1 and 9.2, leading to
a = [a, a a af = [3.3 0.97 1.04 0.6]r
2 3 4
Assume again, as in Example 9.2, that the desired trajectory is
q (t) = 30° (1 - cos(2JI0) teW = 45° (1 - cos(2Kt))
dx
The corresponding tracking errors, control torques, and parameter estimates are plotted in Figure
9.4, starting without any a priori information ( a(0) = 0 ). The actual parameters used in the
simulations are the same as in the earlier examples. We see that tracking convergence to errors of
less than 0.5" occurs within the first half-second.
Note that, in this example, the number of equivalent parameters is 4 while the number of
original physical inertial parameters is 6 (three parameters for each link, i.e., mass, center of
mass, moment of inertia). This means that there are fewer equivalent parameters than physical
parameters, and therefore the physical parameters cannot be determined from the equivalent
parameters. This does not cause any problems in control, because in computing control inputs,
we actually use the equivalent parameters or their estimates.
For comparison. Figure 9.5 shows the tracking errors and control torques using the P.D.
control term — Kp s alone, on the same desired trajectory. Note that since a(0) = 0 , the adaptive

| 408  Control of Multi-Input Physical Systems |     |     |     |     | Chap. 9 |
| -------------------------------------------- | --- | --- | --- | --- | ------- |
-1.5
| 0.0  0.5 | 1.5  2.0  | 2.5  3.0 | 0.0  0.5  | 1.0  1.5 2.0  | 2.5  3.0 |
| -------- | --------- | -------- | --------- | ------------- | -------- |
|          | time(sec) |          |           | time(sec)     |          |
| 2"       |           | r        |           |               |          |
o
-100
| -200     |           |          | -100     |           |          |
| -------- | --------- | -------- | -------- | --------- | -------- |
| 0.0  0.5 | 1.5 2.0   | 2.5  3.0 | 0.0  0.5 | 1.5 2.0   | 2.5  3.0 |
|          | time(sec) |          |          | time(sec) |          |
Figure 9.4a : Tracking errors and control torques under adaptive control
control input and the P.D. control input are initially equal. •
AN ALTERNATIVE ADAPTIVE TRAJECTORY CONTROLLER
The above tracking convergence proof is unchanged if the gain matrix  Kp  is
chosen to be time-varying, provided that K   remains uniformly positive definite (so
D
that V -> 0 still implies that s —> 0 ) and of bounded time-derivative (so that  V still
is uniformly continuous). In the following, we show that an examination of the control
problem without uncertainty suggests a particular time-varying choice of  K  . We
D
then study how this choice translates in the adaptive case, and how to incorporate it in
a modified adaptive controller.
The case of no parameter uncertainty
When there is no parameter uncertainty, there is no need for adaptation. The control
law (9.18) can still be used, with the unknown parameters a replaced by the known
parameters a.  While the resulting controller is different from the computed torque
controller, it can also be shown to be exponentially convergent, and thus can be
viewed as an alternative to the computed torque controller.

Sect. 9.2 Adaptive Robot Trajectory Control 409
0.25 r
E 0.20 -
0.15 -
0.10
0.05
0.00 I
0.0 0.5 1.0 1.5 2.0 2.5 3.0 0.0 0.5 1.5 2.0 2.5 3.0
time(sec) time(sec)
M 2.0 r 2.0
I 1.5
1.0
0.5
0.0
0.0 0.5 1.0 1.5 2.0 2.5 3.0 0.0 0.5 1.0 1.5 2.0 2.5 3.0
time(sec) time(sec)
Figure 9.4b : Parameter estimates under adaptive control
Specifically, let us choose
where A is a strictly positive constant. This adjustment of K according to the
D
(positive definite) inertia matrix H is intuitively appealing, since it corresponds to
applying larger gains for joints of larger inertia. Let us consider the same function V
as before, i.e.,
Differentiation of V yields
This implies that V(t) = V{0)e~2^'. Furthermore, due to the uniform positive
definiteness of H,
3 a > 0, (a/2) ||s||2 < V(t) = V(0)e~2Xt

410 Control of Multi-Input Physical Systems Chap. 9
s o.o
-2.0
-4.0
-6.0
0.0 0.5 1.0 1.5 2.0 2.5 3.0 0.0 0.5 1.0 1.5 2.0 2.5 3.0
time(sec) time(sec)
2"
o
g
c
o
-100 -
-200 -100
0.0 0.5 1.0 1.5 2.0 2.5 3.0 0.0 0.5 1.0 1.5 2.0 2.5 3.0
time(sec) time(sec)
Figure 9.5 : Tracking errors and control torques under P.D. control
This shows that s is exponentially convergent to zero with a rate X. Letting A = XI
(where I is the identity matrix), this, in turn, implies the exponential convergence of
tracking errors q and q with the rate X.
It is interesting to note that, with this choice of K and A , the control law can
D
be rewritten as
T = H[qV2^q--^2q] + Cq +g
r
Thus, the control law is almost the same as a computed torque control law, except for
a minor difference in the second term. This control law is actually interesting in itself,
because it does not exactly cancel the robot dynamics, but it still guarantees
exponential tracking convergence at the same rate as an exact cancellation. This can
be attributed to the fact that it utilizes the inherent structure of the robot dynamics.
The adaptive case
Motivated by the choice of K used above in the absence of uncertainty, we might
D
be interested in using

Sect. 9.2 Adaptive Robot Trajectory Control 411
K = XHH (9.22)
D
in the adaptive case, when uncertainty is present. However, there is a problem with
this choice: the matrix H may not be always positive definite in the course of
parameter adaptation. We now show that this problem can be simply handled using a
modification of the adaptation law.
Considering again the Lyapunov-like function candidate (9.17), and choosing
K as in (9.22), we get
D
= sr[-A,Hs+ H(q,. - Xs) + Cq + g] + a^"1 3
r
Thus, if we let Y denote a modified Y matrix, defined by
m
H(q,. - Xs) + Cq + g = Y (q, q, q q) a (9.23)
r m r r
we obtain
V-= -XsTHs + aT\-T- 1 A ^Y s]
r~l an m
The adaptation law
A -—TYjs (9.24)
a =
then leads to
Since H, the actual manipulator inertia matrix, is always uniformly positive definite,
the above expression guarantees global stability and global tracking convergence of
the adaptive control system. Note that the control law can be simply written as
(9.25)
9.2.2 * Composite Adaptive Trajectory Control
In the previous section, the adaptation law extracts information about the parameters
from the joint tracking errors. However, the tracking errors are not the only source of
parameter information. As discussed in Example 8.10, prediction errors on the joint
torques also contain parameter information. Here we show that, as in section 8.8, the
different sources of parameter information be combined for parameter adaptation, and
can further improve the performance of the adaptive controller.

412 Control of Multi-Input Physical Systems Chap. 9
COMPOSITE ADAPTATION
The key to extracting information from both the tracking errors s and prediction errors
e is to create a parameter update law which is driven by both s and e. To this purpose,
while leaving the control law unchanged, we define, similarly to section 8.8, a
"composite adaptation law" of the form
a(0=-P(0[Yrs+WrR(f)e] (9.26)
where R(0 is a uniformly p.d. weighting matrix indicating how much attention the
adaptation law should pay to the parameter information in the prediction error, and the
adaptation gain P(t) is a uniformly p.d. gain matrix determined by the techniques to be
described below. The quantities Y, s are defined as before, while W and e are defined
in Example 8.10. In filtering the dynamics to avoid the joint acceleration (i.e., in
generating the matrix W), we can use a first-order filter, i.e.,
W(q,q) =-^[Y (q,q,q)] (9.27)
r 1
P + A
with Yj defined by (8.83). We thus obtain a new class of adaptive controllers. Note
that the earlier adaptive controller, which we shall refer to as a tracking-error-based
(TEB) adaptive controller, simply corresponds to
For simplicity, in the following we take R(f) in (9.26) to be the unity matrix. To
generate the gain matrix P in (9.26), we may use the gain update techniques of various
parameter estimators section 8.7.
Let us also point out some results on persistency of excitation relevant to our
later discussion. If tracking errors q and q converge to zero, then the persistent
excitation of W = W(q^ , q'j) implies the p.e. of W, as shown in chapter 8. Also, as
rf
explained in section 8.7, the p.e. of Wj is itself guaranteed by the p.e. and uniform
continuity of the matrix Y^, which is defined by
GLOBAL ASYMPTOTIC AND EXPONENTIAL CONVERGENCE
In the following, we show the global asymptotic and exponential convergence of the
tracking errors and parameter errors for the adaptive controllers based on the
composite adaptation law (9.26), using a Lyapunov-like analysis.
The convergence analysis for the composite adaptive controllers based on

Sect. 9.2 Adaptive Robot Trajectory Control 413
various gain-update techniques will all rely on the following scalar function
V(t) =hsTHs + arP "'a ] (9.28)
This is the same function as that used for the tracking-error-based (TEB) controller in
section 9.2.1, although we now allow P to be possibly time-varying. Specifically,
besides the case of a constant adaptation gain, we shall study the BGF exponentially
forgetting least-squares algorithm of section 8.7.5.
The Constant Gain (CG) Composite Adaptive Controller
The constant gain composite adaptive controller uses a constant (symmetric, p.d.)
matrix P(f) = P in the adaptation law (9.26). With the same Lyapunov-like function as
0
in the TEB derivation, the composite adaptation law simply adds an extra term in the
expression of V
V(t) =-srK s-arWrWa (9.29)
D
This implies that V(t) < V(0) and, therefore, that s and a are upper bounded from the
construction of V, since H is uniformly p.d. and P is p.d.. It is interesting to note that
o
the scalar function here is the same as that used in (9.28) for the tracking error-based
adaptive controller, while its derivative now contains an additional negative term
(-e^e), indicating that V(t) will decrease as long as either the tracking error or the
prediction error is not zero. More precisely,
If the manipulator's desired joint trajectories are bounded, then the tracking
errors q and q and the prediction errors e in the CG composite adaptive
controller all globally converge to zero, and the parameter error a remains
bounded. If, in addition, the trajectories are persistently exciting and uniformly
continuous, the estimated parameters asymptotically converge to the true
parameters.
Proof: The boundedness of s and a has already been pointed out. The boundedness of q and
q follows from the boundedness of s. We now prove the convergence of the tracking error
measure s and prediction error e by showing the convergence of V to zero for bounded desired
trajectories.
Let us first show the boundedness of V(t)
i> = -2srK s-2ere
D
since this in turn guarantees the uniform continuity of V(t). The boundedness of q, q, q, q and
d d
q implies that of q, q, q and <j. Examination of the terms in Y(q,q, q,., q,.) and C(q,q) reveals
d r r

414 Control of Multi-Input Physical Systems Chap. 9
that they are all bounded, reflecting the physical fact that, for a mechanical manipulator, bounded
motion quantities cannot correspond to unbounded forces. Given the closed-loop dynamics
(9.21),
(9.30)
D
and the upper boundedness of H "', s is bounded. This also implies that q is bounded.
From (9.28), we have
The second term in the right-hand side is bounded because W, Y, a and s are all bounded. Note
that the boundedness of q, q and q implies the boundedness of the torque t and that of the matrix
Yj. Based on the facts that the filter in (9.27) is exponentially stable and strictly proper, and that
Yj is bounded, one can easily show the boundedness of W. This in turn guarantees the
boundedness of e.
The boundedness of s, e, e and s implies the boundedness of V(t). Straightforward application
of Corollary 2.1 then leads to V(0->0 as t -> °° . Therefore, both the tracking error s and the
prediction error e asymptotically converge to zero. The convergence of s to zero in turn
guarantees the convergence of q and q to zero.
If W is persistently exciting, then W is also p.e.. The convergence of the estimated
rf
parameters to the true parameters can then be shown easily by noting that the adaptation law
PYrs (9.31)
0 0
represents an exponentially stable dynamics with convergent input YT s. CD
It is interesting to note that composite adaptive control guarantees the
convergence to zero of both tracking error and prediction error, while direct adaptive
control only guarantees that of the tracking error. This is a reflection of the fact that
composite adaptation explicitly pays attention to both tracking error and prediction
error.
As in section 8.8, the effect of the composite adaptation law can be given a
simple intuitive interpretation. Assume for simplicity that P(f) = yl. The TEB
adaptation law (with F = P(0) has a gradient-like nature, because it can be written as
This gradient nature accounts for the poor parameter convergence when large
adaptation gain is used. By contrast, using (9.28), one can rewrite the composite

Sect. 9.2 Adaptive Robot Trajectory Control 415
adaptation law as
This means that the parameters errors are now a filtered version of the gradient
direction, with the filter being time-varying. Thus, the parameter search in the
composite adaptation goes along a filtered, or averaged, direction. This indicates that
parameter and tracking error convergence in composite adaptive control can be
smoother and faster than in TEB adaptive control.
The Bounded-Gain-Forgetting (BGF) Composite Adaptive Controller
The composite adaptive controller with P in (9.26) determined by a BGF update is
called the BGF composite adaptive controller. Recall from chapter 8 that the BGF
update uses an exponentially forgetting least-squares gain update
p ( / ) ^ ) p + WW (9.32)
dt
with the following variable forgetting factor
X(t)=X {\-\\?\\lk ) (9.33)
0 o
where k and X are two positive constants specifying the upper bound of the gain
0 o
matrix norm and the maximum forgetting rate. This gain update guarantees that
V t > 0 , X(t) > 0, and P(r)< k \ for any signal W, and 3 X > 0 , V t > 0 , X(t) > X if
o { {
W isp.e..
For convenience of exponential convergence analysis, we shall use the
alternative adaptive trajectory controller described at the end of section 9.2.1
The BGF composite adaptive controller has globally convergent tracking errors
q and <| and prediction error e ;/ the desired trajectories are bounded.
Furthermore, if the desired trajectories are persistently exciting and uniformly
continuous, the parameter estimation errors and tracking errors are globally
exponentially convergent to zero.
Proof: For the BGF adaptive controller, defined by (9.24), (9.25), (9.32) (with Y defined by
m
(9.23)), one has
V(t) = - i,srHs - (K(t)l2) arP ~' a - aTWrWa < 0 (9.34)
The convergence of q, q and e can be shown as before. Note that, additionally, the convergence
of V(t) to zero leads to that of X(/)arP "'a .

416 Control of Multi-Input Physical Systems Chap. 9
As pointed out in section 8.7, ¥(f)<k\, and the persistent excitation of W^ (and
o
: consequently, that of W) guarantees that X(t) > X > 0. These imply
t
Mt)aTp-la> X^a/kg (9.35)
Therefore the convergence of A.(r)arP~'a to zero implies that of a. In fact, we can more
precisely show the exponential convergence of the tracking and estimation errors. Indeed, let y
o
be the strictly positive constant defined by •y = min(2AA,). In view of (9.31), we can write
o v 1
V(t) + l V(t) < 0
0
Therefore, V{t) < V(0) e~ \'. This, in turn, implies the exponential convergence of s and a to
zero. The exponential convergence of q and q to zero follows as a result of exponential
convergence of s. EH
As in section 8.8, the composite adaptive controller can be shown to allow the
adaptation gain to be increased much higher than in tracking-error-based adaptation,
yielding faster parameter convergence and better tracking accuracy , and to enjoy
enhanced robustness to unmodeled dynamics.
9.3 Putting Physics in Control
In this section, we consider extensions of the earlier discussion to larger classes of
systems and control problems.
9.3.1 High-Frequency Unmodeled Dynamics
As we saw in chapter 7, it is usually appropriate in control design to distinguish
between structured and unstructured modeling uncertainties. Structured uncertainties
correspond to inaccuracies in the parameters of the model (e.g., the effects of
unknown loads on the rigid-body dynamics of a manipulator), or to additive
disturbances (e.g., stiction), while unstructured uncertainties reflect errors on the
system order, i.e., unmodeled dynamics. If modeling is adequate, the unmodeled
dynamics (such as structural resonant modes, actuator dynamics, or sampling effects)
are of "high frequency". One can then define control "bandwidth" as the frequency
content of the control input, and design the control law so that its bandwidth is lower
than the frequency range of the unmodeled dynamics. Thus, setting the control
bandwidth can be thought of as a matter of consistency: while the role of feedback is
to reduce the effects of structured uncertainties on performance, it is limited by the
requirement that the frequency content of the control signal does not spill over into
that of the unstructured uncertainties.

Sect. 9.3 Putting Physics in Control 417
The discussion of the previous sections, however, which involves seeing some
components of our computer-generated control law as mimicking actual physical
systems, can be extended to improve performance beyond the classical bandwidth
limitation. This is achieved, in a sense, by putting some implicit structure in part of the
unmodeled dynamics. Consider again the earlier position control problem, but assume
now that the links present some structural flexibility (as real links do). The bandwidth
of the P.D. controller (i.e., the corresponding upper bounds on the gains k - and k :)
P D
should not be limited by the frequency range of the structural modes: were the links
very flexible and poorly damped, equipping each joint with a passive spring-damper
could not destabilize the system. Conversely, the control bandwidth is limited by how
well the P.D. control terms do succeed at mimicking the virtual spring-damper
systems, namely by the frequency ranges of actuator dynamics and sampling
limitations (whichever imposes the lowest bound), i.e., by the other unmodeled
dynamics. It is also limited by measurement noise, yet one can easily see that large
classes of measurement noise (in particular, for zero-mean noise uncorrelated with the
actual system state) do not modify the analysis - inputting white noise in a passive
system, for instance, does not affect stability. These effects can be easily verified
experimentally.
The above discussion can be generalized. Assume that the effective limit on
bandwidth (i.e., the lowest bound imposed by the unmodeled dynamics) is due to a
passive element of the actual system dynamics, such as e.g., structural resonant modes
or aero-elastic effects. Then components of the control law which, when combined
with that passive element, mimick new passive physical dynamics, can be tuned
separately from the rest of the controller by disregarding the limit on bandwidth
imposed by the passive element (see Exercise 9.6). Furthermore, the rest of the control
law may then be tuned less conservatively by exploiting the presumably better
behaved (e.g., better damped) behavior of the new "unmodeled dynamics" created by
the previous combination.
The implications in terms of numerical implementation are obvious. To avoid
that the limit on bandwidth be computational, the P.D.-like terms may be calculated at
a faster sampling rate, or may be implemented using analog circuitry. Accordingly,
the actual implementation may involve multiple time-scales, with the P.D.-like terms
computed the most often, the feedforward terms computed at a slower rate, and the
parameter update performed at a yet slower sampling rate.

418 Control of Multi-Input Physical Systems Chap. 9
9.3.2 Conservative and Dissipative Dynamics
In the robotic example, we dealt with a conservative physical system, subjected to
external inputs such as control torques, gravity, or disturbances. Dissipative terms,
such as friction, also represent additive inputs, and thus may be accounted for in a
fashion similar to the adaptive compensation of the gravity torque g . However, it is
potentially more effective to exploit the known dissipative character of these terms,
rather than treat them as simple perturbations. Assume, for instance, that a viscous
friction torque vector D q is present at the manipulator joints (with D a positive
definite matrix). Such a term, of course, does not affect the stability of position
control algorithms, since it only introduces additional damping. Let us now consider
trajectory control problems. Considering the friction term as an additive disturbance
Dq = Y^q) a , where a is a vector of possibly unknown friction coefficients, one
D D
can use the control law
x = Ya + Y (q) a - K s
D D D
and augment the adaptation law in a with one in a
D
leading to
as before. If instead we choose to explicitly account for the dissipative character of
friction, notice that Dq = Dq + Ds , and use the control law
r
x = Ya + Y (q)a - K s
D r D D
and, accordingly, the modified adaptation law in a
D
we now obtain
Thus, the second approach is equivalent to "increasing" K by the positive definite
D
matrix D. However, this is achieved using the desired velocity q^ rather than the
actual velocity q , and therefore insensitively to the measurement noise on the velocity
signals, so that one can typically tune the "effective" K at values higher than those
D
obtained by increasing K directly. Here again, the explicit account of the dissipative
D
nature of friction allows us in effect to increase the system's bandwidth beyond its

Sect. 9.3 Putting Physics in Control 419
classical limit.
A similar procedure can be used in the case of Coulomb friction. Assume that
we compensate for Coulomb friction D sgn[q] (where D. is a diagonal positive semi-
c c
definite matrix, and the sign function sgn is understood component-wise) using a term
D sgn[q,.] , rather than the obvious D sgn[q]. Similarly to the case of viscous
c c
friction, one can easily show that this procedure adds a negative semi-definite term to
V. Indeed, the extra term appearing in V can be written
n
- sT D ( sgn(q,.) - sgn(q) ) = -£•*; D ( sgn(<?-) - sgn(q ))
c ci ; ri
where the terms D > 0 are the diagonal elements of the Coulomb friction matrix D .
ci c
Noticing that sums of the form ( sgn(^-) - sgn(<jy-)) are either zero or of the same
( ;
sign as sgn(<jr- -<7 ) , i.e., as sgn(^), we see that, indeed, this Coulomb friction
( r;
compensation procedure adds a negative semi-definite term to V. Furthermore, using
sgn[q] rather than sgn[q] in the control and adaptation laws avoids the use of
r
velocity measurements for friction compensation, and thus alleviates problems of
inaccurate friction models at zero velocity.
This explicit distinction between dissipative and non-dissipative inputs is
particularly relevant in cases where major components of the dynamics are involved.
For instance, standard "square-law" models of hydrodynamic drag on a rigid body
involve force/torque vectors of the form D(q) q , with D(q) a symmetric positive
definite matrix, and therefore are similar in structure to the previous example, with
now the matrix D itself varying with the velocity vector q .
9.3.3 Robotics as a Metaphor
Assuming that the full system state can be measured or estimated, conceptual
extensions beyond mechanical systems can be derived: physical systems verify
energy conservation equations of the form
— [ Stored Energy ] = [ External Power Input ] + [ Internal Power Generation]
dt
of which (9.9) is a particular instance. The external power input term can be written
y^u, where u is the input vector ("effort" or "flow"in the vocabulary of physical
system modeling techniques, such as bond-graphs) and y is the output vector (flow or
effort). By properly defining which of the physical inputs are "internal", we can
always assume that the full vector u can be used for control purposes. Furthermore, we
are not necessarily limited to dissipative or passive systems (i.e., such that their

420 Control of Multi-Input Physical Systems Chap. 9
internal power generation be negative or zero), as long as the internal power generated
can be compensated for by the external power input, i.e., by a proper choice of u (as in
the case of gravitational forces in the robotic example). The major step is then to
design a feedback controller structure (equation (9.18) in the robotic example) that
translates the energy conservation equation in terms of a mapping between parametric
uncertainty and a vector s = y - y (rather than between u and y), such that s = 0
r
represent an exponentially stable differential equation in the tracking error - this
implies, predictably, that the number of components of s (and, accordingly, the
number of independent variables to be tracked) must be equal to (or smaller than) the
dimension of the control input vector u. Furthermore, while an explicit linear
parametrization of the dynamics is a key element in adaptive controller designs,
bounds on the parametric uncertainty (which, in the robotic example, would
correspond to bounds on the components of the vector Y a and on disturbances) may
be sufficient for simple robust designs, as seen in section 9.1.2.
Example 9.4: Passivity Interpretation of Adaptive Manipulator Control
The above discussion can be conveniently formalized in terms of the creation of passive
mappings by means of feedback loops and adaptation loops. Consider again the adaptive
manipulator controller of section 9.1.3. Conservation of energy
implies that the mapping T. - g —> q is passive. Taking the control law to be
T = Ya-Ks
o
transforms this open-loop passive mapping, between external input x — g and velocity q , into a
closed-loop dissipative mapping between parametric uncertainty Y a and the "reference velocity
error" vector s = q - q,.. Indeed, our choice of control law yields
Furthermore, using the adaptation law
then corresponds to inserting a passive feedback block between s and - Y a (Figure 9.6), since
I^-[5rr-'5] = -sr Y5
2 dt
The passivity of the adaptation law can also be shown directly by noticing that the integrator

Sect. 9.3 Putting Physics in Control 421
closed-loop manipulator dynamics
s
•A .
J *
Hs + (C + KD)s =
adaptation
- Ya
Figure 9.6 : Passivity interpretation of the adaptive robot controller
structure
implies that the mapping - Y7s —> a is passive, and therefore that the mapping s —> - Y a is also
passive. This also means that the integrator in the adaptation law can be replaced by any
operator which preserves the passivity of the mapping — Y^s —> a.
For instance, the integrator, lip in the frequency domain, can be replaced by any passive
transfer function of the form h(p)lp (note that the factor \/p has to be preserved explicitly,
because the convergence proof exploits the equality a = a ). It can be replaced by any passive
linear MIMO mapping between - Yrs and a. It can also be replaced by any passive nonlinear
mapping between - Yrs and a ; an example of performance enhancement using such a mapping
is the "composite" adaptive manipulator controller of section 9.2.2.
We thus see that the passivity interpretation can allow for considerable design flexibility, d
The adaptive manipulator control approach described above can be
straightforwardly extended to the rigid dynamics of spacecraft, as shown in the next
section. Similar concepts can apply to the nonlinear dynamics of high-performance
aircraft. Furthermore, besides basic forms of energy conservation, the scalar
summarizing property actually exploited for control system design may depend on the
problem considered. In underwater vehicle dynamics, for instance, conservative
effects such as added-mass can be directly accounted for by using the fluid's velocity
potential flow. In systems with implicit interaction ports, available energy (in the case
of interactions with quasi-ideal sources of temperature, pressure, or chemical
potential) may be most suitable.

422 Control of Multi-Input Physical Systems Chap. 9
9.4 Spacecraft Control
Robotic spacecraft potentially represent a safe and economical alternative or
complement to man in the construction, maintenance, and operation of the space
structures to be deployed in the next decade. They present, however, specific and
difficult control problems, largely due to their nonlinear dynamics. Furthermore,
while spacecraft can potentially be expected to easily handle objects of masses and
sizes comparable to or larger than their own (as, e.g., in releasing a payload from an
orbiter, retrieving a satellite, performing docking or construction operations, or
perhaps even throwing large loads accurately between robotic spacecraft), thanks to
weightlessness, such tasks involve by nature large dynamic uncertainties, and
therefore are likely to require effective adaptive capabilities. This section discusses
the accurate attitude tracking control of rigid spacecraft handling large loads of
unknown mass properties. The method is parallel to that of the robot manipulator case,
and presents similar advantages over techniques based on inverse dynamics, in terms
of simplicity, easier approach to robustness issues, and adaptive capabilities.
9.4.1 The Spacecraft Model
We consider the attitude control of a spacecraft driven by reaction wheels. In practice,
the spacecraft may also be equipped with gas-jet systems (used e.g., to control
translational motion of the system, to compensate for non-zero translational
momentum imparted by the loads, or to desaturate the reaction wheels), the control of
which shall be commented upon later.
The spacecraft is treated as a rigid body whose attitude can be described by two
sets of equations, namely, kinematic equations, which relate the time derivatives of the
angular position coordinates to the angular velocity vector, and dynamic equations,
which describe the evolution of the angular velocity vector. The development can be
directly applied to the case of a spacecraft having rigidly secured a (possibly) large
load of unknown mass properties. The results are also directly applicable to a
spacecraft having itself inadequately known mass properties, due to, e.g.,
reconfiguration, fuel variations in the gas-jet systems, thermal deformation, and so on.
DYNAMIC EQUATIONS
Let us first define the reference frames in which our attitude control problem shall be
described. We assume that the control torques are applied through a set of three
reaction wheels along orthogonal axes (Figure 9.7). Based on these axes, we define an
arbitrary orthonormal reference frame linked to the spacecraft, which we shall refer to
J

Sect. 9.4 Spacecraft Control 423
as the spacecraft frame. The origin of this frame is not necessarily the center of mass
of the system, nor are the axes necessarily the principal axes of the spacecraft. We also
assume that an arbitrary inertial frame has been defined, with respect to either fixed
stars or to a reference that can be considered inertial for the duration of the attitude
maneuver {e.g., a space station).
spacecraft frame
inertial frame
Figure 9.7 : Spacecraft attitude control using reaction wheels
Let to denote the angular velocity vector of the spacecraft, expressed in the
spacecraft frame. The equations describing the evolution of (0 in time may be written
as
Hd) = p xoo + T
The "inertia" matrix H is symmetric positive definite, and can be written
H = H° - HA
where H° is the total (spacecraft with reaction wheels) central inertia matrix, HA is the
(diagonal) matrix of axial wheels' inertias, and p is the total spacecraft angular
momentum, all expressed in spacecraft coordinates. Note that since T is the torque
vector applied to the spacecraft by the reaction wheels, - x is the vector of control
torques actually applied by the reaction wheels motors. The x operator denotes the
vector product operation. The notation [v x] will refer to the skew-symmetric matrix
defining the vector product by a vector v

424 Control of Multi-Input Physical Systems Chap. 9
0 -v
3
[vx] = v 0
3
KINEMATIC EQUATIONS
The angular position of the body may be described in various ways. For example, one
can consider the so-called Gibbs vector
£ = tan(p/2) e
which derives from a quaternion parametrization. The vector I; represents the result of
a virtual rotation of p radians about a virtual unit axis e, with reference to the inertial
reference frame. In that case, one can write
where
and I is the 3 x 3 identity matrix. This description is valid for —it < p < it. Using this
representation, the momentum p can be expressed as a function of \ by noting that
p = C(£)p7 (9.36)
where p' is the (constant) inertial angular momentum, and the matrix C(^) represents
the coordinate transformation from the inertial frame to the spacecraft frame:
Note that C"1© = CTQ = C(-1) .
Alternatively, the attitude of the body may be described using the classical
Euler angle representation, consisting of consecutive angular clockwise rotations of
angles (j), 6, and \\i (roll, pitch, and yaw), that would bring the inertial frame in
alignment with the spacecraft frame. In that case, one has
•y = M(Y) CO
where Y = (<|>,0,\|/)r, and

Sect. 9.4 Spacecraft Control 425
1 sin <j> tan 8 cos <|> tan 0
M(y) = 0 cos <j> — sin <f>
0 sin <j> sec 9 cos <j) sec 0
This description is valid in the region —JT/2 < 0 < n/2 (other representations use 4
"Euler parameters" to avoid such singularities). When using this second
representation, one can write for p an expression similar to (9.36), namely
P = R(7) P7
where R(y) represents the coordinate transformation matrix from the inertial frame to
spacecraft coordinates:
cos \]f cos 9 cos \f sin 0 sin $ - sin \j/ cos cos y sin 8 cos (j) + sin \f sin (
R(Y) = sin \y cos 9 sin \y sin 9 sin <j> + cos y cos sin y sin 8 cos (() — cos y sin <j
- sin \|/ cos Y sin 6
In summary, the equations describing the attitude of a spacecraft may be written
in the synthetic form
Hd) = p x co + x
(9.37)
x = J(x) co
where, depending on the representation used for the kinematic equations, the vector x
is either the attitude vector y, or the Gibbs vector ^ , with R(y) = C(£). Accordingly,
the matrix J represents either the matrix M or the matrix Z.
Note that control-moment-gyroscopes (CMGs) may be used in place of reaction
wheels while keeping a similar formalism. Instead of controlling angular momentum
by varying the angular speeds of rotors of constant orientation, as in the case of
reaction wheels, CMGs obtain the same effect by using simple or double gimbal
mechanisms to vary the orientation of constant-speed rotors. In this case, however, the
potential singularities of the gimbals have to be accounted for explicitly.
9.4.2 Attitude Control
CHOICE OF STATES
Consider the system described by (9.37), and choose as state-space coordinates the
components of the vectors x and x. This choice is well-defined, since the matrix J

426 Control of Multi-Input Physical Systems Chap. 9
remains invertible in the domain of validity of the kinematic representation. By
differentiating the expression of i, the equations of motion can be written as
H*(x)x+C*(x,x)x = F
with
J"1 (9.38)
C*(x,i) = - J"rH J-l jj-l - J-r[p x]J"! (9.39)
Note that it can be easily shown that one has the simple expression
JTkx) =2(1+ x^x)-1 [I - x x ] (9.40)
As in the robotic case, two properties of the above dynamics are exploited in the
adaptive controller design. First, the matrix (H* - 2C*) is skew-symmetric (a property
which can be interpreted as reflecting conservation of energy). Indeed, using
expressions (9.38) and (9.39), we have
H* - 2 C* = ^-(J-T) H J-l - J~T H ^(J-1) + 2 J-Tfo x]J-l
at at
which, given the skew-symmetry of the matrix [p x] , implies the skew-symmetry of
(H *• - 2 C*) . Second, the dynamics is linear in terms of a properly defined constant
parameter vector a. While many such parametrizations are possible, we choose a to
consist of the 6 independent components of the symmetric central inertia matrix H,
and of the 3 components of the constant inertial angular momentum p^. Given
expressions (9.38) and (9.39) and the relation (9.37), the matrices H*and C* are
indeed linear in the constant parameter vector a.
Based on the above dynamic formulation, it is now straightforward to derive,
for spacecraft control, results similar to those obtained in the case of robot
manipulators. This is not surprising, since we are dealing in both cases with
trajectory-controllable Hamiltonian systems. Specifically, we first show the
effectiveness of a simple proportional-derivative (P.D.) control for regulation
applications. We then derive a globally convergent adaptive controller for fast attitude
tracking applications, similar to the adaptive robot manipulator controller. We assume
that the system's state vector, namely x and x, is available (or computable) from
measurements.

Sect. 9.4 Spacecraft Control All
ATTITUDE REGULATION
We first show that a simple P.D.-like control law yields stable position control (i.e.,
given a constant x , has x converge to x ), using essentially the same proof as in the
d d
robot manipulator case.
Consider a simple P.D. control law in F, of the form
x =JrF = -iT[K x + K k] (9.41)
p D
Physically, this control law is actually mimicking the effect of a passive mechanical
system composed of springs and dampers. This remark can be formalized by taking as
a Lyapunov function candidate
V(t) =L[kTH*x + xTK x]
{ p
Intuitively, V\{t) can be interpreted as the sum of the pseudo "kinetic energy"
1/2 kT H* x and of the "potential energy" 1/2 x^KpX associated with the virtual spring
torques. Given the skew-symmetry of the matrix (H* - 2 C*), the time-derivative of
can be written as
which, using the P.D. control law (9.41), simplifies as
V (t) = -x.TK x < 0
l D
Not surprisingly, we recognize Vj (t) as the power dissipated by the virtual dampers.
We now only need to check that the system cannot get "stuck" at a stage where V\
equals 0 while x does not equal x , or, to put it more technically, invoke the invariant-
d
set theorem. Since Vj = 0 implies that x = 0, which in turn implies that
x = ( H* )-l Kp x, one has that V\ = 0 only if x = 0 (note that, given the Lyapunov
derivation, x is bounded as long as x^ is bounded, so that the singularity of the Gibbs-
vector kinematic representation is not reached, and therefore H* and H* ~' exist).
Thus, the system does converge to the desired state, as the physical reasoning
suggested.
Note that the position convergence of this very simple controller does not
require a priori knowledge of the system's mass properties, although, of course, for a
given set of gains, its transient performance does depend on the actual mass properties
of the spacecraft. Similarly, the proof extends to the case when the spacecraft is
equipped with flexible appendages (such as solar panels or large antennas) because
such structures are themselves mechanically passive systems, although the transient

428 Control of Multi-Input Physical Systems Chap. 9
performance depends on the natural damping of the appendages.
ADAPTIVE ATTITUDE TRACKING
The adaptive control problem applies to more demanding, fast attitude tracking
applications. It consists in generating a control law to be applied by the reaction
wheels, and a parameter vector estimation law, such that the tracking error
asymptotically converge to zero, i.e., such that the actual attitude vector \(t) "catch
up" with the desired attitude trajectory xjj). Although it yields a much higher
performance controller than the simple P.D. approach described above, the adaptive
controller also avoids any required a priori knowledge of the system's mass
properties.
We assume that the desired x, kj, and 'i are all bounded. Let a be the (time-
d d
varying) parameter vector estimate, a = a - a be the parameter estimation error, and
x = x - x be the tracking error. Consider the Lyapunov-like function
d
V(r)=-[sr
with the vector s, a measure of tracking error, defined as
s = X + Xx (9.42)
where A, is a strictly positive constant. We shall write (9.42) as
where
x = x -Xx (9.43)
r d
As in the robotic case, the "reference velocity" vector x is formed by shifting the
r
desired velocity k according to the position error x. Intuitively, the first term in the
d
Lyapunov function candidate V(t) is obtained by replacing the actual velocity x by the
"reference velocity error" s in the expression of the pseudo "kinetic energy"
1/2 xrH*x ; the second term in V(t) represents a quadratic measure of parameter
estimation error.
Differentiating V(t), and using the skew-symmetry of the matrix (H*-2C*),
leads to
V(t) = sr(F - H*x, - C*x.) + arr-' S
;
Taking the control law to be

| Sect. 9.4  |                             |     |     | Spacecraft Control  | 429    |
| ---------- | --------------------------- | --- | --- | ------------------- | ------ |
|            | F = H*(x)x,. + C*(x,x)x,.-K |     | s   |                     | (9.44) |
/)
where K  is a symmetric positive definite matrix, yields
o
|     | V(t) = sT( H % + C*x-K |     | s)  +  aTr-lk |     |     |
| --- | ---------------------- | --- | ------------- | --- | --- |
|     |                        | r   | D             |     |     |
where
|     | H* = H*- H*  | C* = C*- C* |     |     |     |
| --- | ------------ | ----------- | --- | --- | --- |
The linear parametrization of the dynamics  allows us to define  a known matrix
Y*(x,x,x., \ ) such that
|     | ; r                             |     |         |     |     |
| --- | ------------------------------- | --- | ------- | --- | --- |
|     | H *(x)x + C *(x,x)x = Y*(x,x,i  |     | , x ) a |     |     |
|     |                                 | r r | r r     |     |     |
so that
|     | V(t) = - srK | s + ar[ r~l S+Y* rs ] |     |     |     |
| --- | ------------ | --------------------- | --- | --- | --- |
D
Note that, given definition (9.24) of the reference velocity vector i r  , the computation
of the matrix Y*(x,x,i,x)  only requires x and x to be measured. Choosing the
r r
adaptation law as
yields
|     | V(t) = - srK | s < 0  |     |     | (9.45) |
| --- | ------------ | ------ | --- | --- | ------ |
D
This shows, using the uniform continuity of V as in the robotic case, that V —> 0 as
/ —> °°,  which in turn  implies that s —> 0, which  shows  that  x —> 0 and x —> 0.
Therefore, both global stability of the system and convergence of the tracking are
guaranteed by the above adaptive controller.
Note that one can show easily that adding a term (XxT  Kp x ) to the function V
still maintains V<0,  which shows directly that x is bounded, and therefore that the
singularity of the quaternion-based  (Gibbs vector) kinematic representation is not
reached as long as the rotation corresponding to the desired maneuver does not exceed
180 degrees. In the case that the desired maneuver does not correspond to this
requirement, one can simply decompose the control problem in subtasks, and change
reference frames between tasks.
The control law, expressed in terms of the applied reaction  wheels control
torques, can be written from (9.44) as
|     | T = Jr(H*x,. + C% - K | s ) = JT ( Y*a - K |     | s ) |     |
| --- | --------------------- | ------------------ | --- | --- | --- |
|     |                       | o                  |     | D   |     |

430 Control of Multi-Input Physical Systems Chap. 9
Note that while we are estimating the central inertia matrix H as part of the adaptation
process, the actual position of the center of mass of the system is not assumed to be
known. Also, note that the scheme does not necessarily estimate the unknown
parameters exactly, but simply generates values that allow the tracking error to
converge to zero (i.e., the actual trajectory to "catch up" with the desired trajectory).
As in the robotic case, "sufficient richness" conditions indicate how demanding the
desired trajectory should be for tracking convergence to necessarily require parameter
convergence. For a given trajectory, the speed of tracking convergence is determined
by the values of the gains X, K , and T, themselves limited by the presence of high-
D
frequency unmodeled dynamics and measurement noise. Composite adaptive versions
of the algorithm can also be developed.
As in the robotic case, the methodology can be easily extended to the case
where only a few significant parameters are adapted upon (in order to simplify the
computations, for instance), while the controller is robust to residual errors resulting
from inaccuracies on the a priori estimates of the other parameters, as well as to
bounded time-varying additive disturbances (e.g., such as those that may be created by
vibrations of flexible appendages). Also, as in section 9.3.1, the P.D. term — J-^K^s
in F can be replaced by any term of the form - iT [K x + Kx] (where the constant
D ?
matrices K and K are symmetric positive definite), and thus be tuned independently
D p
of X so as to be more robust to unmodeled structural vibrations.
Finally, note that we only assumed that the system's state (i.e., x and x) is
available from measurements. If the initial angular velocity £2(0) of the reaction
wheels about their axes can also be reliably measured, then, using the fact that
p' = R(- x(0)) [H°(o(0) + HAQ(0)] = R(- x(0)) HA [<o(0) + Q(0)] + R(- x(0)) H oo(0)
the above adaptive controller can be expressed (under the mild assumption that the
matrix HA of axial wheels inertias is known) in terms of only the 6 independent
components of the inertia matrix H. Of course, if p' itself is known (e.g., to be zero),
then again the adaptive controller need only estimate the 6 independent components of
the inertia matrix H .
Example 9.5 Let us illustrate the development with simple simulations. Assume that the
spacecraft, initially at x(0) = 0, is required to follow a hypothetical desired attitude trajectory
consisting of five parts, namely, a 1-second constant acceleration phase to
x/1) = [0.5 0.5 0.5]r , a 1 -second constant deceleration phase to x/2) = [ 1. 1. 1 .]T , a 3-second
constant attitude phase, and the reverse trajectory back to the original attitude. Assume that the
actual central inertia matrix H is

Sect. 9.4 Spacecraft Control 431
15 5 5
H = 5 10 7
5 7 20
and that the spacecraft has an inertial angular momentum p'= [1. -1. O.]T (imparted e.g., by the
original spinning of the load). The sampling rate used in the simulations is 100 Hz.
For comparison purposes, we first consider the performance of a simple P.D. controller in F,
with Kp — 200 I, KQ = 20 I. The corresponding tracking errors are given in Figure 9.8.
0.3
0.2
0.1
0.0
-0.1
-0.2
-0.3
-0.4
-0.5
CO 1.0 2.0 3.0 4.0 5.0 6.0 7.0 8.0 9.0 10.0
time(sec)
Figure 9.8 : Tracking errors, P.D. controller
Although the practical purpose of the adaptive controller is to achieve consistent performance
in the presence of large load variations, the strongest demonstration of the algorithm consists in
adapting to the mass properties of the whole spacecraft. That is, by setting a(0) = 0 , no initial
information is assumed about the inertia matrix or the angular momentum, and therefore, in this
example, the adaptive controller starts exactly as the P.D. The gains K and X are also chosen
D
such that the term K s (= K \+XK x) be exactly equal to the P.D. control law (namely,
D D D
with KQ as in the P.D. controller, and X = 10). The adaptation gain matrix is F=30I (a
conservative choice, as is indicated by the smoothness of the parameter estimates). The
corresponding tracking errors (Figure 9.9) show a five-time performance improvement over the
P.D. in the first leg, and a ten-time improvement in the second leg (where more initial information
is available from the first-leg adaptation process). The adaptive controller torques are similar in
magnitude and activity to those of the P.D. controller. Also, this controller performance is
obtained along a smooth and rather "unexciting" desired trajectory, which represents a challenge
to an adaptive controller. D
Advanced control algorithms present exceptional potential in the dynamically clean,
weightless environment of space. The above development can in principle be

432 Control of Multi-Input Physical Systems Chap. 9
0.10
0.05 *"\
~ 0.00
-0.05
-0.10
-0.15
1.0 2.0 3.0 4.0 5.0 6.0 7.0 8.0 9.0 10.0
timefseci
Figure 9.9 : Tracking errors, adaptive controller
extended easily to include translational control of the spacecraft using gas-jets, by
adding the system's mass and position of the center of mass to the list of components
of the unknown parameter vector a. Again, if we assume the reaction wheels' axial
angular velocities to be measured, and their axial inertias to be known, then only a
total of 10 parameters need to be estimated as part of the adaptation process. However,
the necessity of averaging on-off gas-jet action presents problems of its own.
In addition, the lightness requirements in space components may also present
difficulties linked to the presence of low-frequency structural modes. In particular,
while the previous discussion can be extended easily to control the rigid dynamics of
manipulators mounted on the spacecraft, practical implementation may require
flexibility issues to be explicitly addressed. In many space robotics applications,
however, distributed flexibility effects can be adequately modeled using simple
lumped approximations, which can in turn be easily handled using e.g., singularly
perturbed versions of the original rigid-model adaptive control results.
9.5 Summary
Simplicity and enhanced performance may be achieved by astutely exploiting the
known physical properties of the controlled systems. In the case of robot manipulators,
explicitly accounting for energy conservation allows us to study easily the stability of
basic control laws such as P.D.'s, and to derive simple robust controllers. The
additional property of linear parametrization, common to all mechanical systems, then
also allows us to construct globally tracking-convergent adaptive robot controllers.
Similar approaches can be taken in the contexts of, e.g., spacecraft control and process
control. Physical insights may also allow us to exploit dissipation terms (such as

Sect. 9.7 Exercises 433
friction in a mechanical system) rather than fight them, and they may also guide the
study of robustness to unmodeled dynamics.
9.6 Notes and References
The P.D. stability result of section 9.1.1 was first proved in a robotics context by [Takegafci and
Arimoto, 1981], and independently rederived by [De Jonckheere, 1981; Koditschek, 1984; Van der
Schaft, 1986], The slightly simpler proof used here is from [Slotine, 1988]. [Arimoto and Miyazaki,
1983] extended the result to P.I.D. control in the presence of gravitational torques. [Hogan, 1985]
provides a discussion of the closely related topic of impedance control. Details on robot kinematics
and dynamics can be found, e.g., in fAsada and Siotine, 1986].
The development of sections 9.1.2 and 9.2 is adapted from [Slotine and Li, 1986-1989].
Related results can be found, e.g, in [Craig, et al., 1986; Bastin and Campion, 1986; Middleton and
Goodwin, 1986; Bayard and Wen, 1987; Hsu, et al., 1987; Sadegh and Horowitz, 1987; Koditschek,
1987; Paden and Panja, 1988; Middleton, 1988; Ortega and Spong, 1988; Li and Slotine, 1989].
Passivity interpretations are discussed in [Kelly and Carelli, 1988; Landau and Horowitz, 1988;
Ortega and Spong, 1988]. Section 9.3 is adapted from [Slotine, 1988]. Computational aspects are
studied in [Walker, 1988; Niemeyer and Slotine, 1988, 1989]. The development is extensively
demonstrated experimentally in [Slotine and Li, 1987a, 1988] and in [Niemeyer and Slotine, 1988].
Extensions of the approach to process control are discussed in [Slotine and Yidstie, 1989, 1990],
Issues of persistency of excitation are discussed, e.g., in [Slotine and Li, 1987c].
Section 9.4 is based on [Slotine and Di Benedetto, 1988, 1990]. Related recent results can be
found, e.g., in [Baillieul and Levi, 1987; Wen, 1988; Koditschek, 1988; Dwyer and Kim, 1989;
Singh, 1989] and references therein.
9.7 Exercises
9.1 Consider a robot control law of the form
where x.":ax is the maximum torque that the /"• actuator can produce (and s/ = $, + A.g, )• Assuming
that control chattering is not an issue, what are the trajectories that can be tracked by this simple
controller?
Check your results in simulations on the manipulator of Example 9.2.
Assume now that the manipulator is in a vertical plane. How are the above results modified?

434 Control of Multi-Input Physical Systems Chap. 9
9.2 Show that the term - k sgn[s] in the sliding controller of section 9.1.2 can be replaced by a
term of the form — ks/||s|| while preserving global tracking convergence. What associated
inequality must k satisfy?
9.3 A mathematical result in input-output stability states that a (strictly) lowpass filtered version of
a square-integrable signal necessarily tends to zero. Show that this result allows to conclude
immediately from (9.17) and (9.20) that q -> 0 as / -> °° .
9.4 For the two-link manipulator of Example 9.3, check explicitly the uniform positive-
definiteness of the matrix H, and the skew-symmetry of the matrix (H — 2C).
9.5 Simulate the adaptive controller of Example 9.3 on various "typical" desired trajectories.
Discuss parameter convergence as a function of the trajectory excitation. Using (8.91), discuss
intuitively why
is reasonable measure of a trajectory's excitation (where Y = Y(q^,q,q ,q) and T is the time
d d rf d
length of the trajectory). Show that it is reasonable to pick T approximately proportional to the
average value of YTY on typical trajectories.
d d
9.6 Consider again the adaptive control of a manipulator, and assume for simplicity that A = X I.
Show that tracking convergence is preserved if, in the control law, an extra term of the form K^ q is
added to the term K s, where K is an arbitrary symmetric positive definite matrix. Specifically,
D P
show that adding 1/2 qT K.p q to the original Lyapunov-like function V then adds a negative (semi-
definite) term - X. qr Kp q to its derivative V.
From a practical point of view, the above result means that the P.D. control gains can be
tuned independently of X. Assuming that the presence of structural resonant modes is the active limit
on the magnitude of X, illustrate in simulations the advantages that such design flexibility provides,
on the two-link manipulator of Example 9.3.
9.7 Show that if the BGF update in the composite adaptive robot controller of section 9.2.2 is
replaced simply by an exponentially forgetting least-squares update with a constant forgetting factor,
then V converges to zero exponentially, regardless of excitation. Does this implies exponential
convergence of the tracking and of the parameters?
9.8 Given the results of Exercise 9.6, and using the BGF adaptive controller of section 9.2.2.,
suggest reasonable a priori choices of X, Kp, R, and the filter used to obtain W (including the filter's
d.c. gain), given a characterization of unmodeled dynamics as in section 7.3. Check your results in
simulations.

Sect. 9.7 Exercises 435
9.9 Show that a manipulator can be viewed as a passive mapping between joint torques and joint
velocities, even in the presence of gravitational torques. Does the manipulator necessarily have to be
rigid?
9.10 Discuss sliding and adaptive controllers for systems of the form
where the notation q("' refers to a vector of components q^"0 , q^-ni} , ... , with the state vector
being
x = [q,q, ... , <7,("i " '>, q , q, - . <?("2~ " • - f
l l 2 2 2
f being a nonlinear function of the state x, and H being a symmetric positive definite matrix function
of the state x and not depending explicitly on any of the qf"r ^ .
9.11 In the single-input case, extend the discussion of section 9.3.2 to the compensation of
monotonous increasing functions of q (or, more generally, of q("~l\ for nth-order dynamics rather
than second-order dynamics), such as e.g, a "square drag" q\q\ in an underwater vehicle.
Generalize in the multi-input case to the compensation of functions with positive semi-definite
Jacobians.
9.12 The manipulator control algorithms described in this chapter can be implemented directly in
cartesian space, i.e., using the end-point position (and orientation) x and velocity x as the new state,
in place of the joint positions and velocities. Two approaches are possible:
(a) Write the kinematic relation between q and x
x = Jq
where J = J(q) is the so-called manipulator Jacobian. Use that kinematic relation to compute
x from the robot dynamics. Show that this leads to writing the dynamics in the form [Khatib,
1983]
H*x + C*x + g* = F with x = JrF
Complete the adaptive controller design.
(b) With obvious notations, compute q according to
r
where we assume that the Jacobian remains invertible over the domain of operation, and
complete the design by using the usual joint-space adaptive controller.

436 Control of Multi-Input Physical Systems Chap. 9
Show that the two approaches actually lead to identical equations, except for the form of
K . Which is easier to implement computationally?
D
How do these results translate to spacecraft control? (Adapted from [Slotine and Li, 1986;
Niemeyer and Slotine, 1989].)

BIBLIOGRAPHY
Alexander, H. L., and Cannon, R. H., Experiments on the Control of a Satellite Manipulator,
Stanford University (1987).
Anderson, B. D. O., Exponential Stability of Linear Systems Arising From Adaptive Identification.
I.E.E.E. Trans, on Auto. Contr., 22-2 (1977).
Anderson, B. D. O., Bitmead, R. R., Johnson, C. R., Jr, Kokotovic, P. V., Kosut, R. L., Mareels,
I. M. Y., Praly, L., Riedle, B. D., Stability of Adaptive Systems: Passivity and Averaging Analysis,
M.I.T. Press (1986).
Anderson, B. D. O. and Johnson, C. R. Jr., Exponential Convergence of Adaptive Identification
and Control Algorithms, Automatica, 19, 1 (1982).
Arimoto, S., Learning Control Theory for Dynamic Systems - A Survey, I.E.E.E. Conf. Decision
and Control, Fort Lauderdale (1985).
Arimoto, S. and Miyazaki, F., Stability and Robustness of P.I.D. Feedback Control for Robot
Manipulators of Sensory Capability, 1st Int. Symp. Robotics Res. (1983).
Arnold, V. I., Ordinary Differential Equations, MIT Press (1973).
Asada, H., Studies In Prehension and Handling By Robot Hands With Elastic Fingers, Doctoral
Dissertation, Kyoto University (1979).
Asada, H. and Kanade, T., Design of Direct-Drive Arms, A.S.M.E. Journal of Vibration, Stress,
and Reliability In Design, 105, 3, July (1983).
Asada, H. and Slotine, J.-J. E., Robot Analysis and Control, John Wiley and Sons (1986).
Asakawa, K., Akiya, F. and Tabata, F., A Variable Compliance Device and Its Application for
Automatic Assembly, Fujitsu Laboratories, Kawasaki, Japan (1982).
Astrom, K. J., Analysis of Rohrs Counterexamples to Adaptive Control, Proc. 22nd I.E.E.E. Conf.
on Dec. and Contr., San Antonio, TX, p. 982 (1983a).
Astrom, K. J., Theory and Applications of Adaptive Control: A Survey, Automatica, 19, (5)
(1983b).
Astrom, K. J., Interactions Between Excitation and Unmodeled Dynamics in Adaptive Control,
437

438
Proc. 23rdI.E.E.E. Conf. on Dec. andContr., Las Vegas, NV, pp. 1276-1281 (1984).
Astrom, K. J. and Wittenmark, B., Computer Controlled Systems: Theory and Design,
Prentice-Hall (1984).
Astrom, K. J. and Wittenmark, B., Adaptive Control, Addison-Wesley (1989).
Atkeson, C. G., An, C. M. and Hollerbach, J. M., Estimation of Inertial Parameters of Manipulator
Loads and Links, Int. Symp. Robotics Res., Gouvieux (1985).
Aizerman, M. A. and Gantmakher, F. R., On Some Features of Switchings in Nonlinear Control
with a Piecewise-Smooth Response of the Nonlinear Element, Avlomatika i Telemekhanika, 18, 11
(1957).
Baillieul, J., Controllability and Observability of Polynomial Systems, Nonlin. Anal. 5, pp. 543-552
(1981).
Bailiieul, J. and Levi, M., Rotational Elastic Dynamics, Physica, Norht-Holland Physics Publishing
(1987).
Banks, S. P., A Note on Nonlinear Observers, Int. J. Contr., 34, 1, pp. 185-190 (1981).
Banks, S. P., Control Systems Engineering: Modelling and Simulation, Control Theory and
Microprocessor Implementation, Prentice-Hall (1986).
Barmish, B. R., Corless, M. J. and Leitmann, G., A New Class of Stabilizing Controllers for
Uncertain Dynamical Systems, S.I.A.M. J. Contr. Optimization, 21, 2, pp. 264-255 (1983).
Bastin, G. and Campion, G., Indirect Adaptive Control of Linearly Parameterized Nonlinear
Systems, 3rd I.F.A.C. ACASP, preprint (1989).
Bayard, D. S. and Wen, J. T., Simple Adaptive Control Laws for Robotic Manipulators, Proc. of
Fifth Yale Workshop on the Applications of Adaptive Systems Theory (1987).
Bergen, A. R. and Franks, R. L., Justification of the Describing Function Method, S.I.A.M.
J. Control, 9, pp. 568-589 (1971).
Bergmann, E. V., Walker, B. K., and Levy, D. R., Mass Property Estimation for Control of
Asymmetrical Satellites, A. I.A .A. Journal of Guidance, Control, and Dynamics, 10, 5 (1987).
Bobrow, J. E., Dubowsky, S., and Gibson, J. S., Time-Optimal Control of Robotic Manipulators
Along Specified Paths, Int. J. Robotics Research, 4, 3 (1985).
Bodson, M., Stability, Convergence, and Robustness of Adaptive Systems, Doctoral thesis. College
of Engineering, University of California, Berkeley (1986).
JL

439
Bondarev, A. G., Bondarev, S. A., Kostylyova, N. Y., and Utkin, V. I., Sliding Modes in Systems
with Asymptotic State Observers, Autom. Remote Contr., 6 (1985).
Book W. J., Recursive Lagrangian Dynamics of Flexible Manipulator Arms, 2nd Int. Sym. of
Robotics Research, Kyoto (1984).
Bottema, O. and Roth, B., Theoretical Kinematics, North Holland, Amsterdam (1979).
Brady, M. T., Hollerbach, M., Johnson, T. L., Lozano-Perez, T. and Mason, M. T., Robot
Motion, M.I.T. Press (19&2).
Brockett, R. W., Volterra Series and Geometric Control Theory, Automatica, 12, pp. 167-176
(1976).
Brockett, R. W., Feedback Invariants for Non-linear Systems, I.F.A.C. Congress, 6, pp. 1115-1120
(1978).
Brockett, R. W., Asymptoticstability and Feedback Stabilization, Differential Geometric Control
Theory, R. W. Brockett, R. S. Millman and H. Sussmann eds., Birkhauser, pp. 181-191 (1983).
Brunovsky, P., A Classification of Linear Controllable Systems, Kybernetika, 6, pp. 173-188
(1970).
Bryson, A. E., Control of Spacecraft and Aircraft, Department of Aeronautics and Astronautics
Report, Stanford University (1985).
Bryson, A. and Ho, Y., Applied Optimal Control, Hemisphere (1975).
Byrnes, C. I. and Isidori, A., A Frequency Domain Philosophy for Nonlinear Systems, l.E.E.E.
Conf. Dec. Contr., 23, pp. 1569-1573 (1984)
Byrnes, C. I., and Isidori, A., On the Attitude Stabilization of Rigid Spacecraft, preprint (1986).
Byrnes, C. I. and Isidori, A., Local Stabilization of Minimum-Phase Nonlinear Systems, Syst.
Contr. Lett., 11, pp. 9-17 (1988a).
Byrnes, C. I. and Isidori, A, Feedback Design from the Zero Dynamics Point of View, Boieman
Work. Comp. Contr. (1988b).
Byrnes, C. I. and Isidori, A., Analysis and Design of Nonlinear Feedback Systems, l.E.E.E. Trans.
Aut. Contr. (1989a).
Byrnes, C. I. and Isidori, A., Output Regulation of Nonlinear Systems, preprint (1989b).
Cannon, R. H. and Schmitz, E., Initial Experiments on the End-Point Control of a Flexible One-

440
Link Robot, Int. J. Robotics Research, 3, 3 (1984).
Canudas, C, Astrom, K. J. and Braun, K., Adaptive Friction Compensation in D.C. Motor Drives,
I.E.E.E. Int. Conf. Robotics and Automation, San Francisco (1986).
Cetaev, N. G., A Theorum on Instability (Russian), Dot Akad. Nauk. SSSR, 1, pp. 529-531 (1934).
Cetaev, N. G., On the Instability of Equilibrium in Some Cases Where the Force Function is Not
Maximum (Russian), Prikl. Mai. Meh., 16, pp. 89-93 (1952).
Cetaev, N. G., The Stability of Motion, Pergamon Press, New York (1961); translation of the
Russian edition, Moskow (1955).
Cho, D. and Hedrick, J. K., A Nonlinear Controller Design Method for Fuel-Injected Automotive
Engines, American Control Conf. (1988).
Chua, L. O. and Lin, G. N., Nonlinear Programming Without Computation, I.E.E.E. Trans.
Circuits and Systems, 31,2 (1984).
Corless, M. J. and Leitmann, G., Continuous State Feedback Guaranteeing Uniform Ultimate
Boundedness for Uncertain Dynamic Systems, I.E.E.E. Trans. Am. Conn., 26, 5, pp. 850-861
(1982).
Craig, J., Adaptive Control of Manipulators through Repeated Trials, American Control Conf., San
Diego (1984).
Craig, J. J., Hsu, P. and Sastry, S., Adaptive Control of Mechanical Manipulators, I.E.E.E. Int.
Conf. Robotics and Automation, San Francisco (1986).
Crouch, P., Spacecraft Attitude Control and Stabilization: Application of Geometric Control
Theory to Rigid Body Models, I.E.E.E. Trans. Autom. Control, 29, 4 (1984).
De Kleer, J., Qualitative and Quantitative Knowledge in Classical Mechanics, Artificial Intelligence
Laboratory, Massachusetts Institute of Technology, 352 (1975).
Denavit, J. and Hartenberg, R. S., A Kinematic Notation for Lower Pair Mechanisms Bases On
Matrices, J. Applied Mechanics 22 (1955).
Desa, S. and Roth, B., Synthesis of Control Systems for Manipulators Using Multivariabie Robust
Servomechanism Theory, Int. J. Robotics Research, 4, 3 (1985).
Desoer, C.A., Liu, R. and Auth, Jr., L.V., Linearity vs. Nonlinearity and Asymptotic Stability in
the Large. I.R.E. Transactions on Circuit Theory, vol. 12:117-118 (1965).
Desoer, C. A. and Vidyasagar, M., Feedback Systems: Input-Output Properties, Academic Press

441
(1975).
Di Benedetto, M. D., Grizzle, J. W., and Moog, C. H., Rank Invariants of Nonlinear Systems,
S.l.A.M. J. Contr. Optimii., to appear.
Di Benedetto, M. D. and Isidori, A., The Matching of Nonlinear Models via Dynamic State
Feedback, S.l.A.M. J. Contr. Optimiz. 24, pp. 1063-1075 (1986).
Drake, S. H., Using Compliance In Lieu of Sensory Feedback for Automatic Assembly, Doctoral
Dissertation, Department of Mechanical Engineering, Massachusetts Institute of Technology (1977).
Drakunov, S. V., An Adaptive Quasi-Optimal Filter with Discontinuous Parameters, Avtomatika i
Telemekhanika, 9, pp. 76-86 (1983).
Duarte, M. A. and Narendra, K. S., Combined Direct and Indirect Adaptive Control of Plants with
Relative Degree Greater than One, Technical Report No. 8715, Center for Systems Science, Yale
University, New Haven, CT (1987).
Duarte, M. A. and Narendra, K. S., Combined Direct and Indirect Adaptive Control of Plants with
Relative Degree Greater than One, Automatica, 25, 3 (1989).
Dubowsky, S. and DesForges, D. T., The Application of Model-Referenced Adaptive Control to
Robotic Manipulators, /. Dynamic Systems, Measurement, Control, 101 (1979).
Dwyer, T. A. W., Exact Nonlinear Control of Large Angle Rotational Maneuvers, I.E.E.E. Trans.
Autom. Control, 29 (1984)
Dwyer, T. A. W. and Batten, A. L., Exact Spacecraft Detumbling and Reorientation Maneuvers
with Gimbaled Thrusters and Reaction Wheels, A.A.S. J. of the Astronautical Sciences, 3 (1985).
Dwyer, T. A .W., Fadali, M. S. and Ning Chen, Single Step Optimization of Feedback -
Decoupled Spacecraft Attitude Maneuvers, I.E.E.E. 24th Conf. Dec. Control, Fort Lauderdale, FL
(1985).
Dwyer, T. A. W. and Kim, J., Bandwidth-Limited Robust Nonlinear Sliding Control of Pointing
and Tracking Maneuvers, American Control Conf. (1989).
Emelyanov, S. V., A Technique to Develop Complex Control Equations by Using Only the Error
Signal of Control Variable and Its First Derivative, Avtomatika i Telemekhanika, 18, 10, pp. 873-885
(1957).
Erdmann, M. A., Using Backprojections for Fine Motion Planning with Uncertainty, I.E.E.E. Int.
Conf. Robotics and Automation, St. Louis (1985).
Featherstone, R., The Calculation of Robot Dynamics Using Articulated-Body Inertias, Int.

442
J. Robotics Research, 2, 1 (1983a).
Featherstone, R., Position and Velocity Transformations Between Robot End Effector Coordinates
and Joint Angles, Int. J. Robotics Research, 2, 1 (1983b).
Fernandez, B. R. and Hedrick, J. K., Control of Multivariable Nonlinear Systems by the Sliding
Mode Method, Int. J. Contr., 46, 3, pp. 1019-1040 (1987).
Feynman, R. P., Leighton R. B. and Sands, M., The Feynman Lectures On Physics,
Addison-Wesley (1963).
Filippov, A. F., Differential equations with discontinuous right-hand sides, Mathematicheskii
Sbornik, 51, 1 (1960), in Russian. Translated in English, Am. Math. Soc. Trans., 62, 199 (1964).
Fliess, M., A Note on the Invertibility of Nonlinear Input-Output Differential Systems, Syst. Contr.
Lett. 8, pp. 147-151 (1986a).
Flugge-Lotz, I., Taylor, C. E. and Lindberg, H. E., Investigation of Nonlinear Control Systems,
NACA, ref. 1391 (1958).
Freund, E., Decoupling and Pole Assignment In Nonlinear Systems, Electronics Letter, 9, 16
(1973).
Freund, E., The Structure of Decoupled Nonlinear Systems, Int. J. Contr., 21, pp. 443-450 (1975).
Gelb, A. and Vander Velde, W. E,, Multiple-Input Describing Functions and Nonlinear System
Design, McGraw-Hill (1968).
Gilbert, E. G. and Ha, I. J., An Approach to Nonlinear Feedback Control With Applications to
Robotics, I.E.E.E. Conf. Decision and Control, San Antonio (1983).
Goldstein, H. Classical Mechanics, Addison-Wesley (1981).
Golla, D. F., Garg, S. C. and Hughes, P. C, Linear State-Feedback Control of Manipulators, Mech.
Machine Theory, 16(1981).
Goodwin, G. C, and Sin, K. S., Adaptive Filtering, Prediction, and Control, Prentice Hall (1984).
Graham, D. and D. McRuer, Analysis of Nonlinear Control Systems, John Wiley & Sons (1961).
Grizzle, J. W. and Isidori, A., Block Noninteracting Control with Stability via Static State
Feedback, Math. Contr. Sign. Syst. (1989).
Guckenheimer, J. and Holmes, P., Nonlinear Oscillations, Dynamical Systems, and Bifurcations of
Vector Fields, Springer-Verlag (1983).

443
Gutman, S., Uncertain Dynamical Systems - A Lyapunov Min-Max Approach, l.E.E.E. Trans.
Autom. Control, 24, pp. 437-443 (1979).
Gutman, S. and Palmor, Z. Properties of Min-Max Controller in Uncertain Dyanical Systems,
S.I.AM. J. Contr. Optimization, 20, 6, pp. 850-861 (1982).
Ha, I. J. and Gilbert, E. G., Robust Tracking in Nonlinear Systems and its Applications to
Robotics, l.E.E.E. Conf. Decision and Control, Fort Lauderdale (1985).
Ha, I. J. and Gilbert, E. G., A Complete Characterization of Decoupling Control Laws for a
General Class of Nonlinear Systems, l.E.E.E. Trans. Aut. Contr., 31, pp. 823-830 (1986).
Hahn, W., Theory and Application of Lyapunov's Direct Method, Prentice Hall (1963).
Hahn, W., Stability of Motion, Springer Verlag (1967).
Hale, J. K., Ordinary Differential Equations, Kreiger, Molaban, FL (1980); originally published,
Wiley (Interscience), New York (1969).
Hanafusa, H. and Asada, H., Mechanics of Gripping Form by Artificial Fingers, Trans. Society of
Instrument and Control Engineers, 12, 5 (1976).
Hanafusa, H. and Asada, H., A Robotic Hand With Elastic Fingers and its Application to
Assembly Process, I.F.A.C. Symp. Information and Control Problems in Manufacturing Technology,
Tokyo (1977a).
Hanafusa, H. and Asada, H., Stable Prehension of Objects by the Robot Hand with Elastic Fingers,
7th Int. Symp. Industrial Robots, Tokyo (1977b).
Hanafusa, H., Yoshikawa, T., and Nakamura, Y., Analysis and Control of Articulated Robot
Arms with Redundancy, Prep. 8th I.F.A.C. World Congress (1981).
Hauser, J. E., Approximate Tracking for Nonlinear Systems with Application to Flight Control,
Doctoral thesis. College of Engineering, University of California, Berkeley (1989).
Hedrick, J. K. and Gopalswamy, S., Nonlinear Flight Control Design via Sliding Methods, Dept.
of Mechanical Engineering, Univ. of California, Berkeley (1989).
Hermann, R. and Krener, A. J., Nonlinear Controllability and Observability, l.E.E.E. Trans. Aut.
Contr., 22, pp. 728-740 (1977).
Hilbert, D., and Cohn-Vossen, S., Geometry and The Imagination, Chelsea (1952).
Hirschorn, R. M., Invertibility of Multivariable Control Systems, l.E.E.E. Trans. Autom. Control,
24, pp. 855-865(1979).

444
Hirschorn, R. M., Output Tracking in Multivariabie Nonlinear Systems, l.E.E.E. Trans. Auiom.
Control, 26, pp. 593-595 (1981).
Hirschorn, R. M., Output Tracking for Nonlinear Systems with Singular Points, S.I A.M. J. Control
& Optimization, 25, pp. 547-557 (1987).
Ho, J. Y., Direct Path Method for Flexible Multibody Spacecraft Dynamics, A.I.A.A. J. Spacecraft
and Rockets, 14,2(1977).
Hogan, N., Impedance Control of a Robotic Manipulator, Winter Ann. Meeting of the A.SM.E.,
Washington, D.C. (1981).
Hogan, N., Impedance Control: An Approach to Manipulation, J. Dyn. Syst., Meas., and Control,
107, l,pp. 1-7 (1985a).
Hogan, N., Control Strategies for Computer Movements Derived from Physical Systems Theory,
Int. Symp. Synergetics, Bavaria (1985b).
Hollerbach, J. M., A Recursive Formulation of Lagrangian Manipulator Dynamics, l.E.E.E. Trans.
Systems, Man, Cybernetics, 10, 11 (1980).
Hollerbach, J. M., Wrist-Partitioned Inverse Kinematic Accelerations and Manipulator Dynamics,
Int. J. Robotics Res., 2, 4 (1983).
Horn, B. K. P., Robot Vision, McGraw Hill (1986).
Hsia, T. C, Adaptive Control of Robot Manipulators - A Review, l.E.E.E. Int. Conf. Robotics and
Automation, San Francisco (1986).
Hsu, J. C. and Meyer, A. U., Modern Control Principles and Applications, McGraw-Hill (1968).
Hsu, P., Sastry, S., Bodson, M. and Paden, B., Adaptive Identification and Control of
Manipulators Without Joint Acceleration Measurements, l.E.E.E. Int. Conf. Robotics and
Automation, Raleigh, NC (1987).
Hughes, P. C, Dynamics of a Flexible' Manipulator Arm for the Space Shuttle, Amer. Astronautical
Soc. and Amer. Inst. of Aeronautics and Astrodynamics Specialist Conf., Jackson Hole, Wyoming
(1977).
Hughes, P.C., Dynamics of a Chain of Flexible Bodies, J. Astronautical Sciences, 27,4 (1979).
Hunt, L. R., Su, R., and Meyer, G., Global Transformations of Nonlinear Systems, l.E.E.E. Trans.
Aut. Contr. 28, pp. 24-31 (1983b).
Inoue, H., Force Feedback in Precise Assembly Tasks, Artificial Intelligence Laboratory,

445
Massachusetts Institute of Technology, 308 (]977).
loannou, P. A. and Kokotovic, P. V., Instability Analysis and Improvement of Robustness of
Adaptive Control, Automatica, 20, 5, pp. 583-594 (1984).
loannou, P. A. and Kokotovic, P. V., Adaptive Systems with Reduced Models, Springer-Verlag,
1983
Isidori, A., Nonlinear Control Systems: An Introduction, Springer Verlag (1989).
Isidori, A., De Luca, A. and Nicolo, F., Control of Robot Arms with Elastic Joints via Nonlinear
Dynamic Feedback, l.E.E.E. Conf. Decision and Control, Fort Lauderdale (1985).
Isidori, A. and Grizzle, J. W., Fixed Modes and Nonlinear Noninteracting Control with Stability,
I.E.E.E. Trans. Am. Contr., 33, pp. 907-914 (1988).
Isidori, A., Krener, A. J., Giorgi, C. G. and Monaco, S., Nonlinear Decoupling via Feedback: A
Differential Geometric Approach, l.E.E.E. Trans. Aut. Contr. ,26, pp. 331-345 (1981).
Isidori, A., and Moog, C, On the Nonlinear Equivalent of the Notion of Transmission Zeros,
l.i.A.S.A. Conf. Modeling and Adaptive Control, Hungary (1986).
Isidori, A. and Moog, C, On the Nonlinear Equivalent of the Notion of Transmission Zeros,
Modelling and Adaptive Control, C. I. Byrnes and A. Kurzhanski eds., Springer Verlag: Lee. notes
Contr. Info. Scie., 105, pp. 445-471 (1988).
Isidori, A., and Ruberti, A., On the Synthesis of Linear Input-Output Responses for Nonlinear
Systems, Syst. Contr. Lett. 4, pp. 17-22 (1984).
Jakubczyk, B. and Respondek, W., On Linearization of Control Systems, Bull. Acad. Polonaise
Sci. Ser. Sci. Math., 28, pp. 517-522 (1980).
Jonckheere, E. A., Lagrangian Theory of Large Scale Systems, European Conf. Circuit Theory and
Design, The Hague, Netherlands (1981).
Junkins, J. L. and Turner, J, D., Optimal Spacecraft Rotational Maneuvers, Elsevier (1986).
Kane, T. R., and Levinson, D. A., The Use of Kane's Dynamic Equations in Robotics, Int.
J. Robotics Research, 2, 3 (1983).
Kanellakopoulos, I., Kokotovic, P. V. and Marino, R., Robustness of Adaptive Nonlinear Control
Under an Extended Matching Condition, I.F.A.C. NOLCOS preprint, pp. 192-197 (1989).
Kahn, M. E., The Near-Minimum-Time Control of Open-loop Articulated Kinematic Chains,
Artificial Intelligence Laboratory, Stanford University, 106 (1969).

446
Kahn, M. E. and Roth, B., The Near Minimum-Time Control of Open-Loop Articulated Kinematic
Chains, /. Dynamic Systems, Measurement, Control, 93 (1971).
Kalman, R. E. and Bertram, J. E., Control System Analysis and Design via the "Second Method"
of Lyapunov I: Continuous-Time Systems, Journal of Basic Engineering, pp. 394-400 (1960).
Kanade, T., Khosla, P. K. and Tanaka, N., Real-Time Control of CMU Direct-Drive Arm II Using
Customized Inverse Dynamics, I.E.E.E. Conf. On Decision and Control, Las Vegas (1984).
Kane, T. R., Dynamics of Nonholonomic Systems, J. Applied Mechanics, 28 (1961).
Kazerooni, H., A Robust Design Method for Impedance Control of Constrained Dynamic Systems,
Doctoral Dissertation, Massachusetts Institute ofTechnology (1985).
Kelly, R., and Carelli, R., Unified Approach to Adaptive Control of Robotic Manipulators, Proc.
27th Conf. on Dec. and Contr., pp. 1598-1603 (1988).
Khatib, O., Commande Dynamique dans L'Espace Operationnel des Robots Manipulateurs en
Presence D'obstacles, Docteur Ingenieur Thesis, Ecole Nationale Superieure de L'Aeronautique et
de L'Espace, Toulouse, France (1980).
Khatib, O., Dynamic Control of Manipulators in Operational Space, Sixth IFTOMM Congress on
Theory of Machines and Mechanisms, New-Delhi (1983).
Khorasani, K. and Spong, M. W., Invariant Manifolds and Their Application to Robot
Manipulators With Flexible Joints, I.E.E.E. Int. Conf. Robotics and Automation, St. Louis (1985).
Khosla, P. K. and Kanade, T., Parameter Identification of Robot Dynamics, I.E.E.E. Conf.
Decision and Control, Fort Lauderdale (1985).
Khosla, P. K., and Kanade, T., An Algorithm to Determine the Identifiable Parameters in the
Dynamic Robot Model, I.E.E.E. Int. Conf. Robotics and Automation, San Francisco (1986).
Koditschek, D. E., Natural Motion of Robot Arms. I.E.E.E. Conf. on Dec. and Contr., Las Vegas,
NV(1984).
Koditschek, D. E-, Adaptive Techniques for Mechanical Systems, Proc. of Fifth Yale Workshop on
the Applications of Adaptive Systems Theory (1987).
Koivo, A. J. and Guo, T. K., Control of Robotic Manipulator With Adaptive Control, I.E.E.E. Conf.
Decision and Control (1981).
Kokotovic, P. V., Applications of Singular Perturbation Techniques to Control Problems, S.I.A.M.
Rev., 26, pp. 501-550(1984).

447
Kokotovic, P. V., Control Theory in the 80's: Trends in Feedback Design, Automatica, 21, pp.
225-236(1985).
Kokotovic, P. V., Khalil, H. K. and O'Reilly, J., Singular Perturbation Methods in Control:
Analysis and Design, Academic Press (1986).
Kokotovic, P. V., Riedle, B. D. and Praly, L., On a Stability Criterion for Slow Adaptation,
Systems and Contr. Letters, 6, pp. 7-14 (1985).
Kokotovic, P. V. and Sussmann, H. J., Positive Real Lemma and the Global Stabilization of
Nonlinear Systems, Syst. and Contr. Lett., 13, pp. 125-133 (1989).
Krasovskii, N. N., The Inversion of the Theorems of Liapunov's Second Method and the Question
of Stability of Motion Using the First Approximation, Prikl. Mat. Meh., 20, pp. 255-265 (1956).
Krasovskii, N. N., Problems of the Theory of Stability of Motion, Stanford Univ. Press, Stanford,
CA (1963); translation of the Russian edition, Moskow (1959).
Krener, A. J. and Isidori, A., Linearization by Output Injection and Nonlinear Observers, Syst.
Contr. Lett., 3, pp. 47-52 (1983).
Krener, A. J., Isidori, A. and Respondek, W., Partial and Robust Linearization by Feedback,
l.E.E.E. Conf. Dec. Contr., 22, pp. 126-130 (1983).
Krener, A. J. and Respondek, W., Nonlinear Observers with Linearizable Error Dynamics S.I.A.M.
J. Contr. Optimiz., 23, pp. 197-216 (1985).
Landau, Y. D., Adaptive Control, Dekker (1979).
Landau, I. D., Adaptive Control Techniques for Robot Manipulators - The Status of the Art,
I.F.A.C. Symp. Robot Control, Barcelona (1985).
Landau, I., and Horowitz, R., Synthesis of Adaptive Controllers for Robot Manipulators Using a
Passive Feedback Systems Approach, l.E.E.E. Int. Conf. Robotics and Automation (1988).
La Salle, J. and Lefschetz, S., Stability by Liapunov's Direct Method, Academic Press (1961).
Lathrop, R.M., Parallelism In Manipulator Dynamics, l.E.E.E. Conf. On Robotics and Automation,
St. Louis (1985).
Lefschetz, S., Stability of Nonlinear Control Systems, Academic Press (1962).
Li, W., and Slotine, J.-J. E., Parameter Estimation Strategies for Robotic Applications., A.S.M.E.
Winter Annual Meeting (1987).

448
Li, W. and Slotine, J.-J. E., Indirect Adaptive Robot Control, System and Control Letters (1989).
Lions, J. L., Some Methods in the Mathematical Analysis of Systems and Their Control, Gordon
and Breach, New-York (1981).
Ljung, L., Systems Identification: Theory for the User, Prentice-Hall (1987).
Lozano-Perez, T., Robot Programming, I.E.E.E. Proceedings (1983).
Luenberger, D. G., Introduction to Dynamic Systems, /. Wiley & Sons, New York (1979).
Luh, J. Y. S., Walker, M. W. and Paul, R. P. C, On-Line Computational Scheme for Mechanical
Manipulators A.S.M.E.J. Dyn. Syst. Meas. Contr., 102 (1980a).
Luh, J. Y. S., Walker, M. H. and Paul, R. P. C, Resolved Acceleration Control of Mechanical
Manipulators, I.E.E.E. Trans. Automatic Control, 25, 3 (1980b).
Lyapunov, A. M., The General Problem of Motion Stability, (1892), in Russian. Translated in
French, Ann. Fac. Sci. Toulouse 9, pp. 203-474 (1907). Reprinted in Ann. Math. Study No. 17,
Princeton Univ. Press (1949).
Marino, R., High-gain Feedback in Nonlinear Control Systems, Int. J. Control, 42, pp. 1369-1385
(1985).
Marino, R., On the Largest Feedback Linearizable Subsystem, Syst. Contr. Lett., 7, pp. 345-351
(1986).
Marino, R. and Kokotovic, P. V., A Geometric Approach to Nonlinear Singularly Perturbed
Control Systems, Automatica, 24, pp. 31-41 (1988).
Marino, R. and Nicosia, S., On the Feedback Control of Industrial Robots with Elastic Joints: A
Singular Perturbation Approach, University of Rome, R-84.01 (1984).
Marino, R., and Spong, M. W., Nonlinear Control Techniques for Flexible Joint Manipulators: A
Single Link case Study, I.E.E.E. Conf. Rob. Autom. (1986).
Mason, M. T., Compliance and Force Control for Computer Controlled Manipulators, I.E.E.E.
Trans. Systems, Man and Cybernetics, 11, 6 (1981).
Mason, M. T., Manipulator Grasping and Pushing Operations, Doctoral Dissertation, Massachusetts
Institute of Technology (1982).
Mason, M. T. and Salisbury, J. K., Robot Hands and the Mechanics of Manipulation, M.IT. Press
(1985).

449
Massera, J. L., On Liapunov's Conditions of Stability, Ann. of Math., 50, pp. 705-721 (1949).
Massera, J. L., Contributions to Stability Theory, Ann. of Math., 64, pp. 182-206 (1956), Erratum
Ann. of Math., 68, p. 202 (1958).
Meerkov, S. M., Principle of Vibrational Control: Theory and Applications, I.E.E.E. Trans, on Aut.
Contr., 25, pp. 755-762 (1980).
Meyer, G. and Cicolani, L., Application of Nonlinear System Inverses to Automatic Flight Control
Design, Theory and Application of Optimal Control in Aerospace Systems, P. Kant ed., NATO
AGARD - AG251, pp. 10.1-10.29 (1980).
Middleton, R. H. and Goodwin, G. C, Adaptive Computed Torque Control for Rigid Link
Manipulators, I.E.E.E. Conf. on Dec. and Contr., Athens, Greece (1986).
Middleton, R. H., Hybrid Adaptive Control of Robot Manipulators, I.E.E.E. Conf. on Dec. and
Contr., Austin, TX (1988).
Misawa, E. A. and Hedrick, J. K., Nonlinear Observers: A State-of-the-art Survey, A.S.M.E.
J. Dyn. Syst. andMeas., 111, 3, pp. 344-352 (1989).
Monaco, S. and Stornelli, S., A Nonlinear Attitude Control Law for a Satellite with Flexible
Appendages, I.E.E.E. 24th Conf. Dec. Control, Fort Lauderdale, FL (1985).
Moog, C. H., Nonlinear Decoupling and Structure at Infinity, Mathematics of Control, Signals and
Systems, 1 pp. 257-268 (1988).
Morgan, A. P. and Narendra, K. S., On the Uniform Asymptotic Stability of Certain Linear
Nonautonomous Differential Equations, S.I.A.M. J. of Control and Optimization, 15 (1977).
Nakamura, Y. and Hanafusa, H., Task Priority Based Redundancy Control of Robot Manipulators,
Int. Symp. of Robotics Research, Kyoto (1984).
Nam, K. and Arapostathis, A., A Model-Reference Adaptive Control Scheme fo r Pure-Feedback
Nonlinear Systems, I.E.E.E. Trans. Aut. Contr., 33, pp. 1123-1131 (1989).
Narendra, K. S. and Annasswamy, A. M., Stable Adaptive Systems, Prentice Hall (1989).
Narendra, K. S. and Goldwyn, R. M., A Geometrical Criterion for the Stability of Certain
Nonlinear Nonautonomous Systems, I.E.E.E. Trans, of the Circuit Theory Group, CT-11 (3) (1964).
Narendra, Kumpati S. and Annaswamy, Anuradha M., Stable Adaptive Systems, Prentice Hall
(1989).
Narendra, K. S. and Taylor, J. H., Frequency Domain Criteria for Absolute Stability, Academic

450
Press (1973).
Nevins, J. L. and Whitney, D. E. Computer Controlled Assembly, Scientific American, 238, 2
(1978).
Nicosia, S., Nicolo, F. and Lentinit, D., Dynamical Control of Industrial Robots With Elastic and
Dissipative Joints, 8th Triennial I.F.A.C. World Congress, Kyoto, Japan (1981).
Niemeyer, G., and Slotine, J.-J. E., Performance in Adaptive Manipulator Control, Proc, 27th
I.E.E.E. Conf. Decision and Control, Austin, TX (1988).
Niemeyer, G., and Slotine, J.-J. E., Computational Algorithms for Adaptive Compliant Motion,
I.E.E.E. Int. Conf. Robotics and Automation (1989).
Nijmeijer, H., Controlled Invariance for Affine Control Systems, Intr. J. Contr., 2, pp. 824-833
(1981).
Nijmeijer, H., Controllability Distributions for Nonlinear Systems, Syst. Contr. Lett., 2, pp. 122-129
(1982).
Nijmeijer, H. and Schumacher, J. M., Zeros at Infinity for Affine Nonlinear Systems, l.E.E.E.
Trans. Aut. Contr., 30, pp. 566-573 (1986).
Nijmeijer, H. and Van der Schaft, A. J., Controlled Invariance for Nonlinear Systems, l.E.E.E.
Trans. Aut. Contr., 27, pp. 904-914 (1982).
Nijmeijer, H. and Van der Schaft, A.J., Nonlinear Dynamical Control Systems, Springer-Verlag
(1990).
Nilsson, N., Principles of Artificial Intelligence, Tioga Publishing, California (1980).
Ohwovoriole, M. S. and Roth, B., A Theory of Parts Mating for Assembly Automation, Ro. Man.
Sy. -81, Warsaw, Poland (1981).
Ogata, K., Modern Control Engineering, Prentice-Hall (1970).
Okada, T., Computer Control of Multi-Jointed Finger System, 6th Int. Joint Conf. on Artificial
Intelligence, Tokyo (1979).
Orin, D. E. and Schrader, W. W., Efficient Computation of the Jacobian for Robot Manipulators,
Int. J. Robotics Research (1984).
Ortega, R., and Spong, M., Adaptive Motion Control of Rigid Robots: A Tutorial, l.E.E.E. Int.
Conf. Decision and Control (1988).
Paden, B. and Riedle, B., A Positive-Real Modification of a Class of Nonlinear Controllers for

451
Robot Manipulators, Proc. American Control Conf. (1988).
Paden, B. and Panja, R., A Globally Asymptotically Stable 'PD+' Controller for Robot
Manipulators, Int. J. Contr., 47, 6 (1988).
Parks, P. D., Lyapunov Redesign of Model Reference Adaptive Control Systems, I.E.E.E. Trans, on
Am. Contr., 11, p. 362 ((966).
Paul, R. P. and Shimano, B., Compliance and Control, 1976 Joint Automatic Control Conf., San
Francisco (1976).
Phillips, C. L. and Harbor, R. D., Feedback Control Systems, Prentice-Hall (1988).
Pieper, D. L., The Kinematics of Manipulators Under Computer Control, Doctoral Dissertation,
Stanford University (1968).
Pieper, D. L. and Roth, B., The Kinematics of Manipulators Under Computer Control, 2nd Int.
Conf. Theory of Machines and Mechanisms, Warsaw (1969).
Pomet, J. B. and Praly, L., Adaptive Nonlinear Regulation: Equation Error from the Lyapunov
Equation, Proc. 28th I.E.E.E. CDC, pp. 1008-1013 (1989).
Popov, V. M., Absolute Stability of Nonlinear Control Systems of Automatic Control, Automation
and Remote Control, 22 (1962).
Popov, V. M., Hyperstability of Automatic Control Systems. Springer Verlag, New York (1973).
Praly, L., A Geometric Approach for the Local Analysis of a One Step Ahead Adaptive Controller,
Proc. 4th Yale Workshop on Applications of Adaptive Systems Theory, Yale University, CT (1985).
Praly, L., d'Andrea-Novel, B. and Coron, J. M., Lyapunov Design of Stabilizing Controllers,
Proc. I.E.E.E. Conf. Dec. and Contr. (1989).
Prigogine, I., Introduction to Thermodynamics of Irreversible Processes, 3rd Ed.,
Wiley-lnterScience, New York (1967).
Raibert, M. H., Analytical Equations vs. Table Look-Up for Manipulation: A Unifying Concept,
I.E.E.E. Conf. Decision and Control, New Orleans (1977).
Raibert, M. H., A Model for Sensory Motor Control and Learning, Biological Cybernetics, 29
(1978).
Raibert, M. H., Legged Robots that Balance, M.IT. Press (1986).
Raibert, M. H. and Craig J. J., Hybrid Position/Force Control of Manipulators, J. Dynamic

452
Systems, Measurement, Control, 102 (1981).
Raibert, M. H. and Horn, B. K. P., Manipulator Control Using the Configuration Space Method,
Industrial Robot, 5, 2 (1978).
Reboulet, C. and Champetier, C, A New Method for Linearizing Non-Linear Control Systems:
The Pseudolinearization, Int. J. Contr., 40,4, pp. 631-638 (1984).
Redding, D.C., and Adams, N.J., A.I.A.A. Journal of Guidance, Control, and Dynamics, 10, 1
(1987).
Riedle, B. D. and Kokotovic, Stability Analysis of an Adaptive System with Unmodeled Dynamics,
Int. J. Contr., 41, pp. 389-402 (1985a).
Riedle, B. D. and Kokotovic, P. V., A Stability-Instability Boundary for Disturbance-Free Slow
Adaptation and Unmodeled Dynamics, I.E.E.E. Trans, on Aut. Contr., 30, pp. 1027-1030 (1985b).
Rohrs, C. E., Valavani, L. S., Athans, M. and Stein, G., Robustness of Continuous-Time Adaptive
Control Algorithms in the Presence of Unmodeled Dynamics, I.E.E.E. Trans, on Aut. Contr., 30, pp.
881-889(1985).
Roth, B., Screws and Wrenches That Cannot Be Bought at a Hardware Store, Int. Symp. of Robotics
Research, Bretton Woods (1983).
Rouche, N., Habets, P. and Laloy, M., Stability Theory by Liapunov's Direct Method, Springer
Verlag(\911).
Rugh, W.J., Analytical Framework for Gain Scheduling, I.E.E.E. Control Systems Magazine, 11,1
(1991).
Sadegh, N., and Horowitz, R., Stability Analysis of an Adaptive Controller for Robotic
Manipulators, I.E.E.E. Int. Conf. Robotics and Automation, Raleigh, NC (1987).
Safonov, M. G. and Athans, M., Robustness and Computational Aspects of Nonlinear Stochastic
Estimators and Regulators, I.E.E.E. Trans. Aut. Contr., 26, 1, pp. 717-725 (1978).
Sahar, J. and Hollerbach, J., Planning of Minimum-Time Trajectories for Robot Arms, Artificial
Intelligence Laboratory, Massachusetts Institute of Technology, 804 (1984).
Salisbury, J. K., Active Stiffness Control of a Manipulator in Cartesian Coordinates, I.E.E.E. Conf.
Decision and Control, Albuquerque, New Mexico (1980).
Salisbury, J. K., Kinematic and Force Analysis of Articulated Hands, Doctoral Dissertation,
Stanford University (1982).

453
Salisbury, J. K., Design and Control of an Articulated Hand, Int. Symp. On Design and Systems,
Tokyo (1984).
Salisbury, J. K., and Craig, J. J., Articulated Hands: Force Control and Kinematic Issues, Int.
J. Robotics Research, 1, 1 (1982).
Sandberg, I. W., A Frequency-Domain Condition for the Stability of Feedback Systems Containing
a Single Time-Varying Nonlinear Element, Bell Syst. Tech. J., 43, pt. 2, p. 1601 (1964).
Sastry, S. and Bodson, M., Adaptive Control: Stability, Convergence, and Robustness,
Prentice-Hall (1989).
Sastry, S. S. and Isidori, A., Adaptive Control for Linearizable Systems, I.E.E.E. Trans. Aut. Contr.
(1989).
Scheinman V. C, Design of a Computer Controlled Manipulator, Stanford Artificial Intelligence
Laboratory, 92 (1969).
Schwartz, L., Cours d'Analyse, Hermann, Paris (1981).
Shimano, B., The Kinematic Design and Force Control of Computer Controlled Manipulators,
Artificial Intelligence Laboratory, Stanford University (1978).
Shinners, M. W., Modem Control System Theory and Application,
Addison-Wesley (1978).
Siljak, D. D., Large Scale Dynamic Systems, North-Holland (1978).
Silverman, L. M., Inversion of Multivariable Linear Systems, I.E.E.E. Trans. Aut. Contr., 14, pp.
270-276(1969).
Simon, H. A., The Sciences of the Artificial, 2nd Ed., M.I.T. Press (1981).
Singh, S. N., Decoupling of Invertible Nonlinear Systems with State Feedback and
Precompensation, I.E.E.E. Trans. Aut. Contr. 25, pp. 1237-1239 (1980).
Singh, S. N., A Modified Algorithm for Invertibility in Nonlinear Systems, I.E.E.E. Trans. Autom.
Control, 26, pp.595 - 598 (1981).
Singh, S. N., Generalized Functional Reproducibility Condition for Nonlinear Systems, I.E.E.E.
Trans. Autom. Control, 27, pp. 958-960 (1982).
Singh, S. N. and W. J. Rugh, Decoupling in a Class of Nonlinear Systems by State Variable
Feedback, J. Dynamic Systems, Measurement, Control (1972).
Slotine, J.-J. E., Tracking Control of Nonlinear Systems using Sliding Surfaces, Doctoral

454
Dissertation, Massachusetts Institute of Technology (1983).
Slotine, J.-J. E. Sliding Controller Design for Nonlinear Systems, Int. J. Control., 40, 2 (1984).
Slotine, J.-J. E. The Robust Control of Robot Manipulators, Int. J. Robotics Research, 4, 2 (1985).
Slotine, J.-J. E. and Coetsee, J. A., Adaptive Sliding Controller Synthesis for Nonlinear Systems,
Int. J. Control, 43, 6 (1986).
Slotine, J.-J. E. and Di Benedetto, M. D., Hamiltonian Adaptive Control of Spacecraft, M.I.T.-
N.S.L. Report 880105, Jan. (1988).
Slotine, J.-J. E. and Di Benedetto, M. D., Hamiltonian Adaptive Control of Spacecraft, I.E.E.E.
Trans, on Auto. Control, 35-7 (1990).
Slotine, J.-J. E., Hedrick, J. K. and Misawa, E. A., On Sliding Observers, A.S.M.E. J. Dyn. Syst.
andMeas., 109, 3, pp. 245-252 (1986).
Slotine, J.-J. E., and Li W., On The Adaptive Control of Robot Manipulators, in Robotics: Theory
and Applications (ed. F.W. Paul and K. Youcef-Toumi) from A.S.M.E. Winter Annual Meeting,
Anaheim, CA( 1986).
Slotine, J.-J. E., and Li W., Adaptive Robot Control, A Case Study, I.E.E.E. Int. Conf. Robotics
and Automation, Raleigh, NC (1987a).
Slotine, J.-J. E., and Li W., Adaptive Strategies in Constrained Manipulation, I.E.E.E. Int. Conf.
Robotics and Automation, Raleigh, NC (1987b).
Slotine, J. J. E. and Li W., Theoretical Issues in Adaptive Manipulator Control, Proc. of Fifth Yale
Workshop on Applications of Adaptive Systems Theory (1987c).
Slotine, J.-J. E. and Li W., Adaptive Robot Control - A New Perspective, I.E.E.E. Conf. Decision
and Control L.A., CA (1987d).
Slotine, J.-J. E., and Li W., On the Adaptive Control of Robot Manipulators, Int. J. Robotics Res.,
6, 3(1987e).
Slotine, J.-J. E., and Li W., Adaptive Manipulator Control: A Case Study, I.E.E.E. Trans, on Auto.
Control, 33-11 (1988).
Slotine, J.-J. E. and Li W., Composite Adaptive Control of Robot Manipulators, Automatica, 25, 4
(1989).
Slotine, J.-J. E. and Sastry S. S., Tracking Control of Nonlinear Systems Using Sliding Surfaces
With Applications to Robot Manipulators, Int. J. Control, 39, 2 (1983).

455
Slotine, J.-J. E. and Spong, M. W., Robust Robot Control with Bounded Input Torques, Int.
./. Robotics Systems, 2, 4 (1985).
Slotine, J.-J. E., and Yoerger, D. R., Inverse Kinematics Algorithm for Redundant Manipulators,
Int.]. Robotics and Automation, 1, 2 (1986).
Sontag, E. and Sussmann, H., Remarks on Continuous Feedback, I.E.E.E. Conf. Dec. Contr., 19,
pp.916-921 (1980).
Spong, M. W., and Vidyasagar M., Robust Nonlinear Control of Robot Manipulators, I.E.E.E.
Conf. Decision and Control, Fort Lauderdale (1985).
Spong, M. W., and Vidyasagar ML, Robot Dynamics and Control, John Wiley and Sons (1989).
Stepanenko, Y. and Vukobratovic, M., Dynamics of Articulated Open-Chained Active
Mechanisms, Mathematical Biosciences, 28 (1976).
Su, R., On the Linear Equivalents of Nonlinear Systems, Syst. Contr. Lett., 2, pp. 48-52 (1982).
Sussmann, H., Single Input Observability of Continuous Time Systems, Math. Syst. Theory, 12, pp.
371-393(1979).
Sussmann, H., Lie Brackets and Local Controllability, S.I.A.M. J. Contr. Optimiz., 21, pp. 686-713
(1983).
Sussmann, H., On a General Theorem on Local Controllability, S.I.A.M. J. Contr. Optimiz., 25, pp.
158-194(1987).
Sussmann, H. J., Limitations to the Stabilizability of Globally Minimum Phase Systems, I.E.E.E.
Trans. Aut. Contr., 35, 1 (1990).
Sweet, L. M. and Good, M. C, Redefinition of the Robot Control Problem: Effects of Plant
Dynamics, Drive System Constraints, and User Requirements, I.E.E.E. Conf. Decision and Control,
Las Vegas (1984).
Takegaki, M. and Arimoto, S., A New Feedback Method for Dynamic Control of Manipulators, J.
Dynamic Systems, Measurement, Control, 102 (1981).
Taylor, D. G., Kokotovic, P. V., Marino, R. and Kanellakopoulos, I., Adaptive Regulation of
Nonlinear Systems with Unmodeled Dynamics, I.E.E.E. Trans. Aut. Contr., 34, pp. 405-412 (1989).
Thau, F. E., Observing the State of Nonlinear Dynamic Systems, Int. J. Contr., 17, 3, pp. 471-479
(1973).

456
Thomson, W. and Tait, P., Treatise on Natural Philosophy, University of Cambridge Press (1886).
Tsypkin, J., Theory of Relay Systems in Automatic Control, Moscow (1955).
Tsypkin, J., Am. Remote Contr., 17(1956).
Uicker, J. J., On the Dynamic Analysis of Spatial Linkages Using 4 by 4 Matrices, Doctoral
Dissertation, Department of Mechanical Engineering and Astronautical Sciences, Northwestern
University (1965).
Uicker, J. J., Denavit, J. and Hartenberg, R. S., An Iterative Method for the Displacement
Analysis of Spatial Mechanisms, /. Applied Math., 31 (1964).
Utkin, V. I, Equations of Sliding Mode in Discontinuous Systems I, II, Automation and Remote
Control (1972).
Utkin, V. I., Variable Structure Systems With Sliding Mode: A Survey, l.E.E.E. Trans. Automatic
Control, 2 (1977).
Utkin, V.I., Sliding Modes and Their Application to Variable Structure Systems, MIR Publishers,
Moscow (1978).
Vafa, Z. and Dubowsky, S., On the Dynamics of the Manipulators in Space Using the Virtual
Manipulator Approach, Proc. of the 1987 l.E.E.E. Int. Conf. on Robotics and Automation, Raleigh,
NC(1987).
Van der Schaft, A. J., Observability and Controllability for Smooth Nonlinear Systems, S.I.A.M.
J. Contr. Optimiz., 20, pp. 338-354 (1982).
Van der Schaft, A. J., Stabilization of Hamiltonian Systems , Nonl. An. Theor. Meth. Appl., 10
(1986).
Van der Schaft, A. J., On Clamped Dynamics of Nonlinear Systems, Mem. n. 634, University of
Twente(1987).
Van der Schaft, A. J., On Clamped Dynamics of Nonlinear Systems, Analysis and Control of
Nonlinear Systems, C. I. Bymes, C. F. Martin and R. E. Saeks eds., North Holland, pp. 499-506
(1988).
Verghese, G., Fernandez, B. R. and Hedrick, J. K., Stable, Robust Tracking by Sliding Mode
Control, Systems and Contr. Lett. (1988).
Vidyasagar, M., Nonlinear System Analysis, Prentice-Hall, Englewood Cliffs, NJ (1978).
Vidyasagar, M., Decomposition Techniques for Large-Scale Systems with Nonadditive

457
Interactions: Stability and Stabilizability, i.E.E.E. Trans. Aut. Contr., 25, pp. 773-779 (1980a).
Vidyasagar, M., On the Stabilization of Nonlinear Systems Using State Detection, I.E.E.E. Trans.
Aut. Contr., 25, 3, pp. 504-509 (1980b).
Walcott, B. and Zak, S. H., State Observation of Nonlinear Uncertain Dynamical Systems, I.E.E.E.
Trans. Aut. Contr., 32, 2, pp. 166-169 (1987).
Walcott, B. and Zak, S. H., Combined Observer-Controller Synthesis for Uncertain Dynamical
Systems with Applications, I.E.E.E. Trans, on System, Man, and Cyber., 18, 1, pp. 88-104 (1988).
Walker, M. W. and Orin, D. E., Efficient Dynamic Computer Simulation of Robot Mechanisms,
A.S.M.E. J. Dynamic Systems, Measurement, Control, 104 (1982).
Walker, M.W., An Efficient Algorithm for the Adaptive Control of a Manipulator, Proc. 5th Int.
Conf. Robotics and Automation (1988).
Whitney, D. E., Resolved Motion Rate Control of Manipulators and Human Prostheses, I.E.E.E.
Trans. Man-Machine Systems, 10 (1969).
Whitney, D. E., Use of Resolved Rate to Generate Torque Histories for Arm Control, C. S. Draper
Laboratory, MAT-54 (1972a).
Whitney, D. E., The Mathematics of Coordinated Control of Prostheses and Manipulators, /.
Dynamics Systems, Measurement, Control (1972b).
Whitney, D. E., Historical Perspectives and State of the Art in Robot Force Control, I.E.E.E. Int.
Conf. Robotics and Automation, St. Louis (1985).
Wiener, N., Cybernetics, or Control and Communication in the Animal and the Machine, M.I.T.
Press (1961).
Winston, P. H., Artificial Intelligence, Addison-Wesley (1984).
Wolovich, W. A., Linear Multivariable Systems, Springer-Verlag, New York (1974).
Wonham, W. M., Linear Multivariable Control: A Geometric Approach, Springer Verlag (1979).
Yoerger, D. R., Newman, J. B. and Slotine, J.-J. E., Supervisory Control System for the JASON
ROV, I.E.E.E. J. Oceanic Eng., OE-11, 3 (1986).
Yoerger, D. R. and Slotine, J.-J. E., Robust Trajectory Control of Underwater Vehicles, I.E.E.E.
J. Oceanic Eng., 10,4(1985).
Yoerger, D. R. and Slotine, J.-J. E., Task-Resolved Motion Control of Vehicle Manipulator

458
Systems, Int. J. Robotics and Automation, 1, 2 (1986).
Yoshizawa, T., Stability Theory by Liapunov's Second Method, The Mathematical Society of Japan
(1966).
Yoshizawa, T., Stability Theory and the Existence of Periodic Solutions and Almost Periodic
Solutions, Springer Verlag (1975).
Young, K.-K. D., Controller Design for A Manipulator Using Theory of Variable Structure Systems,
I.E.E.E. Trans. Systems, Man, Cybernetics, 8, 2 (1978).
Young, K.-K. D., Kokotovic, P. K. and Utkin, V. I., A Singular Perturbation Analysis of High
Gain Feedback Systems, I.E.E.E. Trans. Automatic Control, 11 (1977).
Zames, G., On the Input-Output Stability of Time-Varying Nonlinear Feedback Systems, I.E.E.E.
Trans, on Am. Contr., Part I: 11,2, pp. 228-238, Part II: 11, 3, pp. 465-476 (1966).

INDEX
Absolute stability, 142 Duffing's equation, 10
Acceleration feedback, 309
Equilibrium point, 20, 43,101
Adams-Bashforth integration, 202
Equivalent control, 283
Adaptive control, 204, 303,310, 402
Euler angles, 423
Algorithm simplification, 276, 302
Existence of solutions in nonlinear
Artificial nonlinearities, 4
differential equations, 151
Autonomous systems, 42
Existence theorems in Lyapunov's
Averaging analysis, 154
direct method, 120
Balance conditions, 295, 297,308 Exponentially forgetting least-squares
Bandwidth, 277, 293, 298,301 algorithm, 363, 373, 375
Barbalat's lemma, 122
Feedback linearization, 204, 207
Bifurcations, 9
Flexible joint mechanism, 242
Boundary layer, 290, 390
Forgetting factor, 373,375
Certainty equivalence, 319 Friction, 2
Chaos, // adaptation to, 417
Circle criterion, 146 Frobenius Theorem, 235
Completely integrable vector fields, 234 Frobenius-Perron Theorem, 305
Composite adaptive control, 381, 410
(reared manipulators, 392
Computed torque, 211,397
Geometric theory, 230
Control interpolation, see Boundary layer
Gibbs vector, 423
Converse Lyapunov theorems, 120
Gradient estimation, 363
Critical damping, 295
Gradient method for Lyapunov function
Damping, 295, 417 generation, 86
Decrescent functions, 106
Hard nonlinearities, 2,4,171,174
Describing function, 757
High-frequency unmodeled dynamics, 276, 415
of backlash, 178
of a dead-zone, / 76 Impedance control, 432
of a saturation function, / 74 Indirect adaptive control, 319
Digital implementation, 202, 302 Industrial robot, see Robot control
Direct adaptive control, 319 Inertia Matrix, 89, 392
Direct-drive arms, 392 Input/output feedback linearization, 216, 246,
Dissipative system, 135, 417 267
Dither, 290 Input/state feedback linearization, 213, 236
459

460
Integral control, 286, 308, 389 Model-reference adaptive control, 314
Internal dynamics, 218, 258, Model simplification, 276,301,302
see also Zero-dynamics Model transformation, 204, 207
Invariant set, 68
Natural nonlinearities, 4
Invariant set theorems, 68
Non-autonomous systems, 42, 101,105,124
Inverse dynamics, 263,
Non-minimum-phase systems, 195, 223, 228,
see also Computed torque
255
Involutive vector fields, 235
Normal form, 249
Jacobian of a smooth vector field, 229
Parameter estimation, 310, 315,318,357
Kalman-Yakubovich lemma, 132,141 Parametric uncertainty, 198, 276,310
Kinetic energy, 74, 89,392 Passive mapping, 133
Krasovki's method for Lyapunov function Passive system, 133
generation, 83 Passivity, 132
Persistency of excitation, 331,365
Lagrangian dynamics formulation, 399
Popov criterion, 144
Least-squares estimation, 363, 369,373,375
Popov plot, 145
Lie brackets, 230
Positive definite function, 58,105
Lie derivatives, 230
Positive definite matrix, 78
Limit cycles, 28,36, 68,
Positive real lemma,
71, 182, 185
see Kalman-Yakubovich lemma
Linear approximation, 54, 116
Positive real system, 129
Linearization, 54,116,
Power form, 132
see also Feedback linearization
PR lemma,
Linear systems, 4
see Kalman-Yakubovich lemma
Lipschitz condition, 152
Process control, 432
Lyapunov equation, SO, 137
PR system, see positive real system
Lyapunov functions, 61,107
Pulse-width modulation, 289
Lyapunov's direct method, 57, 105
Lyapunov's linearization method, 53, 116 Quaternions, 423
Manipulator design, 392 Relative degree, 128, 218, 248, 267
Marginal Stability, 50,55 Robot control, 89, 210, 311, 392
Matching conditions on system Robustness, 204, 276, 310,352,391
uncertainties, 388
Self-excited oscillation, see Limit cycle
Matching of overall design, 302
Self-tuning control, 318, 357
Mathematical symbols ( V, 3, e, => ), 48
Sensitivity, see Robustness
Modeling errors, 2, 198, 276,301,310
Singular perturbations, 154,431
Modeling/performance trade-offs, 301,303, 310

461
Skew-symmetric matrix, 77
Zero-dynamics, 226, 253,
Sliding condition, 280,293, 397
see also Non-minimum-phase systems,
Sliding control, 276, 397 Internal dynamics
Sliding mode, 281
Sliding regime, see sliding mode
Sliding surface, 281, 397
Smooth vector field, 229
Spacecraft control, 421
SPR system,
see strictly positive real system
Square systems, 266
Stability, 47,101
asymptotic stability, 50,102
exponential stability, 51,103
global stability, 52,103
Lyapunov stability, 48,102
uniform stability, 104
Stabilization, 192
S-trajectory, 295
Strictly positive real system, 127
Switching control, 283, 285, 289
Symmetric matrix, 77
Tellegen's theorem, 135
Time-varying linear systems, 42,114
Time-varying nonlinear systems,
see Non-autonomous systems
Tracking, see Trajectory control
Trajectory control, 194, 216, 246,
262, 278, 396
Underwater vehicles, 5, 154, 277,
288, 298
Unicity of solution trajectories, 152
Uniform continuity, 123
Uniform stability, 104
Van der Pol equation, 8, 28,49, 97, 158
Vector field, 229