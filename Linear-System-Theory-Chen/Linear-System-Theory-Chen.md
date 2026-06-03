LINEAR SYSTEM
THEORY AND DESIGN
Third Edition
Chi -Tsang Chen
State University of New York at Stony Brook
New York Oxford
OXFORD UNIVERSITY PRESS
1999

THE OXFORD SERIES IN ELECTRICAL AND COMPUTER ENGINEERING
Adel S. Sedra, Series Editor, Electrical Engineering
Michael R. Lightner, Series Editor, Computer Engineering
Allen and Holberg, CMOS Analog Circuit Design
Bobrow, Elementary Linear Circuit Analysis. 2rr,'d Ed.
Bobrow, Fundamentals of Electrical Engineering. 2nd Ed.
Campbell, The Science and Engineering of Microelectroinic Fabrication
Chen, Analog and Digital Control System Design
Chen, Linear System Theory and Design. 3rd Ed.
Chen, System and Signal Analysis. 2nd Ed.
Comer. Digital Logic and State Machine Design. 3rd Ed.
Cooper and McGillem, Probabilistic Methods of Signal and System Analysis. 3rd Ed.
Fortney, Principles of Electronics: Analog & Digital
Franco, Electric Circuits Fundamentals
Granzow, Digital Transmission Lines
Guru and Hiziroglu, Electric Machinery & Transformers. 2nd Ed.
Hoole and Hoole, A Modern Short Course in Engineering Electromagnetics
Jones, Introduction to Optical Fiber Communication Systems
Krein, Elements of Power Electronics
Kuo, Digital Control Systems. 3rd Ed.
Lathi, Modern Digital and Analog Communications Systems. 3rd Ed.
McGiliem and Cooper, Continuous and Discrete Signal and System Analysis. 3rd Ed.
Miner, Lines and Electromagnetic Fields for Engineers
Roberts and Sedra, SPICE. 2nd Ed.
Roulston, An Introduction to the Physics of Semiconductor Devices
Sadiku, Elements of Electromagnetics. 2nd Ed.
San tina. Stubberud, and Hostetter, Digital Control System Design. 2nd Ed.
Schwarz, Electromagnetics for Engineers
Schwarz and Oldham, Electrical Engineering: An Introduction. 2nd Ed.
Sedra and Smith, Microelectronic Circuits. 4th Ed.
Stefani, Savant, Shahian, and Hostetter, Design of Feedback Control Systems. 3rd Ed.
Van Valkenburg, Analog Filter Design
Warner and Grung, Semiconductor Device Electronics
Wolovich, Automatic Control Systems
Yariv, Optical Electronics in Modern Communications. 5th Ed.

OXFORD UNIVERSITY PRESS
|            |                 |               | Oxford         | New York   |               |            |           |
| ---------- | --------------- | ------------- | -------------- | ---------- | ------------- | ---------- | --------- |
|            | Athens          | Auckland      | Bangkok        | Bogota     | Buenos Aires  |            | Calcutta  |
| Cape Town  | Chennai         |               | Dar es Salaam  | Delhi      | Aorence       | Hong Kong  | Istanbul  |
|            | Karachi         | Kuala Lumpur  | Madrid         | Melbourne  | Mexico City   |            | Mumbai    |
|            | Nairobi  Paris  | Sao Paulo     | Singapore      | Taipei     | Tokyo         | Toronto    | Warsaw    |
and associated companies in
|     |     |     | Berlin  | Ibadan  |     |     |     |
| --- | --- | --- | ------- | ------- | --- | --- | --- |
Copyright © 1999 by Oxford University Press, Inc,
Published by Oxford University Pre,s s. Inc,
198 Madison Avenue. New York. New York 10016
Oxford is a registered trademark of Oxford University Press
All rights reserved, No part of this publication may be
reproduced. stored in a retrieval system. or transmitted.
in any fonn or by any means, electronic, mechanical,
photocopying. recording. or otherwise. without the prior
permission of Oxford University Press.
Library of Congress Cataloging-in-Publication Data
Chen. Chi-Tsong
|     | Linear system theory and design I by Chi-Tsang Chen. - |                                                             |     |     |     |     | 3rd ed.  |
| --- | ------------------------------------------------------ | ----------------------------------------------------------- | --- | --- | --- | --- | -------- |
|     | p.  cm. -                                              | (The Oxford series in electrical and computer engineering)  |     |     |     |     |          |
Includes bibliographical references and index.
ISBN (}'19-511777-S (cloth).
|     | 1. Linear systems.  |       | 2. System design.  |     | I. Title.  | II. Series.  |           |
| --- | ------------------- | ----- | ------------------ | --- | ---------- | ------------ | --------- |
|     | QA402.C44           | 1998  |                    |     |            |              |           |
|     | 629.8'32-<1c21      |       |                    |     |            |              | 97-35535  |
CIP
|     |     | Printing (last digit): 9 8 7 6 5 4  |     |     |     | 3 2  1  |     |
| --- | --- | ----------------------------------- | --- | --- | --- | ------- | --- |
Printed in the United States of America
on acid-free paper

To
BIH-JAU

Contents
Preface xi
Chapter 1: Introduction 1
1.1 Introduction
1.2 Overview 2
Chapter 2: Mathematical Descriptions of Systems 5
2.1 Introduction 5
2.1.1 Causaliity and Lumpedness 6
2.2 Linear Systems 7
2.3 Linear Time-Invariant (LTI) Systems 11
2.3.1 Op-Amp Circuit Implementation 16
2.4 Linearization 17
2.5 Examples 18
2.5.1 RLC Networks 26
2.6 Discrete-Time Systems 31
2.7 Concluding Remarks 37
Problems 38
Chapter 3: Linear Algebra 44
3.1 Introduction 44
3.2 Basis, Representation, and Orthonormalization 45
3.3 Linear Algebraic Equations 48
3.4 Similarity Transformation 53
3.5 Diagonal Form and Jordan Form 55
3.6 Functions of a Square Matrix 61
3.7 Lyapunov Equation 70
3.8 Some Useful Formulas 71
3.9 Quadratic Form and Positive Definiteness 73
3.10 Singular-Value Decomposition 76
3.11 Norms of Matrices 78
Problems 78
vii

viii  CONTENTS
Chapter 4: State-Space Solutions and Realizations  86
| 4.1  Introduction  |     | 86  |
| ------------------ | --- | --- |
4.2  Solution of LTI State Equations  81
| 4.2.1 Discretization  |     | 90  |
| --------------------- | --- | --- |
4.2.2 Solution of Discrete-Time Equations  92
4.3  Equivalent State Equations  93
| 4.3.1 Canonical Forms  |     | 97  |
| ---------------------- | --- | --- |
4.3.2 Magnitude Scoling in Op-Amp Circuits  98
| 4.4  Realizations  | 700  |     |
| ------------------ | ---- | --- |
4.5  Solution of Linear Time-Varying (LTV) Equations  706
| 4.5.1 Discrete-Time Case  |     | 710  |
| ------------------------- | --- | ---- |
4.6  Equivalent Time-Varying Equations  717
4. 7  Time-Varying Realizations  17 5
| Problems  | 77 1  | I   |
| --------- | ----- | --- |
•
Chapter 5: Stability  727
| 5.1  Introduction  |     | 727  |
| ------------------ | --- | ---- |
Input-Output Stability of LTI Systems  721
5.2
| 5.2.1 Discrete-Time Case       |      | 126  |
| ------------------------------ | ---- | ---- |
| 5.3  Internal Stability        |      | 129  |
| 5.3.1 Discrete-Time Case       |      | 131  |
| 5.4  Lyapunov Theorem          |      | 132  |
| 5.4. 1 Discrete-Time Case      |      | 135  |
| 5.5  Stability of LTV Systems  |      | 131  |
| Problems                       | 140  |      |
Chapter 6: Controllability and ObseNability  743
| 6.1  Introduction             |     | 143  |
| ----------------------------- | --- | ---- |
| 6.2  Controllability          |     | 144  |
| 6.2.1 Controllablity Indices  |     | 150  |
| 6.3  Observability            |     | 153  |
| 6.3.1 Observability Indices   |     | 157  |
6.4  Canonical Decomposition  158
6.5  Conditions in Jordan-Form Equations  164
6.6  Discrete-Time State Equations  169
6.6.1 Controllability to the Origin and Reachability  177
6.7  Controllability After Sampling  112
| 6.8  LTV State Equations  |      | 716  |
| ------------------------- | ---- | ---- |
| Problems                  | 180  |      |
Chapter 7: Minimal Realizations and Coprime Fractions  784
| 7. 1  Introduction  |     | 184  |
| ------------------- | --- | ---- |
7.2  Implications of Coprimeness  185
| 7.2.1 Minimal Realizations  |     | 189  |
| --------------------------- | --- | ---- |

ix
Contents
7.3  Computing Coprime Fractions  192
| 7.3.1 QR Decomposition                    | 195  |     |
| ----------------------------------------- | ---- | --- |
| 7.4  Balanced Realization                 | 197  |     |
| 7.5  Realizations from Markov Parameters  | 200  |     |
7.6  Degree of Transfer Matrices  205
7.7  Minimal Realizations-Matrix Case  207
| 7.8  Matrix Polynomial Fractions  | 209  |     |
| --------------------------------- | ---- | --- |
7.8.1 Column and Row Reducedness  212
| 7.8.2 Computing Matrix Coprime Fractions         | 214  |      |
| ------------------------------------------------ | ---- | ---- |
| 7.9  Realizations from Matrix Coprime Fractions  |      | 220  |
| 7.10 Realizations from Matrix Markov Parameters  |      | 225  |
| 7.11 Concluding Remarks                          | 227  |      |
Problems  228
Chapter 8: State Feedback and State Estimators  231
| 8.1  Introduction  231  |      |     |
| ----------------------- | ---- | --- |
| 8.2  State Feedback     | 232  |     |
8.2.1 Solving the Lyapunov Equation  239
| 8.3  Regulation and Tracking                     | 242  |      |
| ------------------------------------------------ | ---- | ---- |
| 8.3.1 Robust Tracking and Disturbance Rejection  |      | 243  |
| 8.3.2 Stabilization  247                         |      |      |
| 8.4  State Estimator  247                        |      |      |
| 8.4.1 Reduced-Dimensional State Estimotor        | 251  |      |
8.5  Feedback from Estimated States  253
| 8.6  State Feedback-Multivariable Case  | 255  |     |
| --------------------------------------- | ---- | --- |
| 8.6.1 Cyclic Design                     | 256  |     |
8.6.2 Lyapunov-Equation Method  259
| 8.6.3 Canonical-Form Method  | 260  |     |
| ---------------------------- | ---- | --- |
8.6.4 Effect on Transfer Matrices  262
| 8.7  State estimators-Multivariable Case  | 263  |     |
| ----------------------------------------- | ---- | --- |
8.8  Feedback from Estimated States-Multivariable Case  265
Problems  266
Chapter 9: Pole Placement and Model Matching  269
| 9.1  Introduction  269                            |                  |      |
| ------------------------------------------------- | ---------------- | ---- |
| 9.1.1 Compensator Equations. ..C                  | lassical Method  | 271  |
| 9.2  Unity-Feedback Configuration-Pole Placement  |                  | 273  |
| 9.2.1 Regulation and Tracking                     | 275              |      |
| 9.2.2 Robust Tracking and Disturbance Rejection   |                  | 277  |
9.2.3 Embedding Internal Models
280
9.3  Implementable Transfer Functions  283
| 9.3.1 Model Matching. ..T                           | wo-Parameter Configuration  | 286  |
| --------------------------------------------------- | --------------------------- | ---- |
| 9.3.2 Implementation of Two-Parameter Compensators  |                             | 291  |
| 9.4  Multivariable Unity-Feedback Systems           | 292                         |      |
| 9.4.1 Regulation and Tracking                       | 302                         |      |
| 9.4.2 Robust Tracking and Disturbance Rejection     |                             | 303  |
9.5  Multivariable Model Matching-Two-Parameter
| Configuration  | 306  |     |
| -------------- | ---- | --- |

x
CONTENTS
9.5.1 Decoupling 311
9.6 Concluding Remarks 314
Problems 315
References 379
Answers to Selected Problems 327
Index 337
I
r

Preface
This text is intended for use in senior/first-year graduate courses on linear systems and
multi variable system design in electrical, mechanical, chemical, and aeronautical departments.
It may also be useful to practicing engineers because it contains many design procedures. The
mathematical background assumed is a working knowledge of linear algebra and the Laplace
transform and an elementary knowledge of differential equations.
Linear system theory is a vast field. In this text, we limit our discussion to the conventional
approaches of state-space equations and the polynomial fraction method of transfer matrices.
The geometric approach, the abstract algebraic approach, rational fractions, and optimization
are not discussed.
We aim to achieve two objectives with this text. The first objective is to use simple
and efficient methods to develop results and design procedures. Thus the presentation is
not exhaustive. For example, in introducing polynomial fractions, some polynomial theory
such as the Smith-McMillan form and Bezout identities are not discussed. The second
objective of this text is to enable the reader to employ the results to carry out design.
Thus most results are discussed with an eye toward numerical computation. All design
procedures in the text can be carried out using any software package that includes singular
value decomposition, QR decomposition, and the solution of linear algebraic equations and
the Lyapunov equation. We give examples using MATLAB®, as the package' seems to be the
most widely available.
This edition is a complete rewriting of the book Linear System Theory and Design, which
was the expanded edition of Introduction to Linear System Theory published in 1970. Aside
from, hopefully, a clearer presentation and a more logical development, this edition differs
from the book in many ways:
• The order of Chapters 2 and 3 is reversed. In this edition, we develop mathematical
descriptions of systems before reviewing linear algebra. The chapter on stability is moved
earlier.
• This edition deals only with real numbers and foregoes the concept of fields. Thus it is
mathematically less abstract than the original book. However, all results are still stated as
theorems for easy reference.
• In Chapters 4 through 6, we discuss first the time-invariant case and then extend it to the
time-varying case. instead of the other way around.
I. MATLAB is a regiSlered ,rademark of the MathWorks. Inc .• 24 Prime Park Way. Natick. MA 01760·1500. Phone:
508·64 7·7000. fax: 508-().l7 -700 I. E-mail: info@mathworks.com. http://www.mathworks.com.
xi

xii PREFACE
• The discussion of discrete-time systems is expanded.
• In state-space design, Lyapunov equations are employed extensively and multi variable
canonical forms are downplayed. This approach is not only easier for classroom presentation
but also provides an attractive method for numerical computation.
• The presentation of the polynomial fraction method is streamlined. The method is equated
with solving linear algebraic equations. We then discuss pole placement using a one-degree
of-freedom configuration, and model matching using a two-degree-of-freedom configura
tion.
• Examples using MATLAB are given throughout this new edition.
This edition is geared more for classroom ust< and engineering applications; therefore, many
topics in the original book are deleted, includi~g strict system equivalence, deterministic iden
tification, computational issues, some multi variable canonical forms, and decoupling by state
feedback. The polynomial fraction design in the input/output feedback (controller/estimator)
configuration is deleted. Instead we discuss design in the two-parameter configuration. This
configuration seems to be more suitable for practical application. The eight appendices in the
original book are either incorporated into the text or deleted.
The logical sequence of all chapters is as foll{ows:
I
Chap. 8
Chap. 1-5 Chap. 6 Chap. 7
=:} =:}
Sec. 7.1-7.3 Sec. 9.1-9.3
=:}
Sec. 7.6-7.8 Sec. 9.4-9.5
=:} =:}
In addition, the material in Section 7.9 is needed to study Section 8.6.4. However, Section 8.6.4
may be skipped without loss of continuity. Furthermore, the concepts of controllability and
observability in Chapter 6 are useful, but not essential for the material in Chapter 7. All minimal
realizations in Chapter 7 can be checked using the concept of degrees, instead of checking
controllability and observability. Therefore Chapters 6 and 7 are essentially independent.
This text provides more than enough material for a one-semester course. A one-semester
course at Stony Brook covers Chapters I through 6, Sections 8.1-8.5, 7.1-7.2, and 9.1-9.3.
Time-varying systems are not covered. Clearly, other arrangements are also possible for a
one-semester course. A solutions manual is available from the publisher.
I am indebted to many people in revising this text. Professor lmin Kao and Mr. Juan
Ochoa helped me with MATLAB. Professor Zongli Lin and Mr. T. Anantakrishnan read
the whole manuscript and made many valuable suggestions. I am grateful to Dean Yacov
Shamash. College of Engineering and Applied Sciences. SUNY at Stony Brook. for his
encouragement. The revised manuscript was reviewed by Professor Harold Broberg, EET
Department, Indiana Purdue University; Professor Peyman Givi. Department of Mechanical
and Aerospace Engineering. State University of New York at Buffalo; Professor Mustafa
Khammash. Department of Electrical and Computer Engineering. Iowa State University; and
Professor B. Ross Barmish. Department of Electrical and Computer Engineering. University
of Wisconsin. Their detailed and critical comments prompted me to restructure some sections
and to include a number of mechanical vibration problems. I thank them all.

Preface xiii
I am indebted to Mr. Bill Zobrist of Oxford University Press who persuaded me to
undertake this revision. The people at Oxford University Press, including Krysia Bebick,
Jasmine Urrneneta, Terri O'Prey, and Kristina Della Bartolomea were most helpful in this
undertaking. Finally, I thank my wife, Bih-Jau, for her support during this revision.
Chi-Tsong Chen

I
!

LINEAR SYSTEM
THEORY AND DESIGN

Chapter
Introduction
1.1 Introduction
The study and design of physical systems can be carried out using empirical methods. We can
apply various signals to a physical system and measure its responses. If the performance is not
satisfactory, we can adjust some of its parameters or connect to it a compensator to improve
its performance. This approach relies heavily on past experience and is carried out by trial and
error and has succeeded in designing many physical systems.
Empirical methods may become unworkable if physical systems are complex or too
expensive or too dangerous to be experimented on. In these cases, analytical methods become
indispensable. The analytical study of physical systems consists of four parts: modeling,
development of mathematical descriptions, analysis, and design. We briefly introduce each
of these tasks.
The distinction between physical systems and models is basic in engineering. Forexample,
circuits or control systems studied in any textbook are models of physical systems. A resistor
with a constant resistance is a model: it will bum out if the applied voltage is over a limit.
This power limitation is often disregarded in its analytical study. An inductor with a constant
inductance is again a model; in reality, the inductance may vary with the amount of current
flowing through it. Modeling is a very important problem, for the success of the design depends
on whether the physical system is modeled properly.
A physical system may have different models depending on the questions asked. It may
also be modeled differently in different operational ranges. For example, an electronic amplifier
is modeled differently at high and low frequencies. A spaceship can be modeled as a particle
in investigating its trajectory; however, it must be modeled as a rigid body in maneuvering.
A spaceship may even be modeled as a flexible body when it is connected to a space station.
In order to develop a suitable model for a physical system. a thorough understanding of the
physical system and its operational range is essential. In this text, we will call a model of a
physical system simply a system. Thus a physical system is a device or a collection of devices
existing in the real world; a system is a model of a physical system.
Once a system (or model) is selected for a physical system, the next step is to apply
various physical laws to develop mathematical equations to describe the system. For ex
ample, we apply Kirchhoff's voltage and current laws to electrical systems and Newton's
law to mechanical systems. The equations that describe systems may assume many forms;

2 INTRODUCTION
they may be linear equations, nonlinear equations, integral equations, difference equations,
differential equations, or others. Depending on the problem under study, one form of equation
may be preferable to another in describing the same system. In conclusion, a system may
have different mathematical-equation descriptions just as a physical system may have many
different models.
After a mathematical description is obtained, we then carry out analyses-quantitative
and/or qualitative. In quantitative analysis, we are interested in the responses of systems
excited by certain inputs. In qualitative analysis, we are interested in the general properties
of systems, such as stability, controllability, and observability. Qualitative analysis is very
important, because design techniques may often evolve from this study.
If the response t)f a system is unsatisfactory, the system must be modified. In some
cases, this can be achieved by adjusting some parameters of the system; in other cases,
compensators must be introduced. Note thq! the design is carried out on the model of the
physical system. If the model is properly chosen, then the performance of the physical system
should be improved by introducing the required adjustments or compensators. If the model is
poor, then the performance of the physical system may not improve and the design is useless.
Selecting a model that is close enough to a physical system and yet simple enough to be studied
analytically is the most difficult and important problem in system design.
1,20veNiew
The study of systems consists of four parts: modeling, setting up mathematical equations,
analysis, and design. Developing models for physical systems requires knowledge of the
particular field and some measuring devices. For example, to develop models for transistors
requires a knowledge of quantum physics and some laboratory setup. Developing models
for automobile suspension systems requires actual testing and measurements; it cannot be
achieved by use of pencil and paper. Computer simulation certainly helps but cannot replace
actual measurements. Thus the modeling problem should be studied in connection with the
specific field and cannot be properly covered in this text. In this text, we shall assume that
models of physical systems are available to us.
The systems to be studied in this text are limited to linear systems. Using the concept of
linearity, we develop in Chapter 2 that every linear system can be described by
l'
yet) = G(t. r)u(r)dr (1.1)
'0
This equation describes the relationship between the input U and output y and is called the
input-outplll or external description. If a linear system is lumped as well, then it can also be
described by
xU) = A(t)x(t) +B(1)u(l) ( 1.2)
+
y(l) = C(t)x(t) D(t)u(t) ( 1.3)
Equation (1.2) is a set of first-order differential equations and Equation (1.3) is a set of algebraic
equations. They are called the internal description of linear systems. Because the vector x is
called the state, the set of two equations is called the state-space or. simply, the state equation.

1.2 Overview 3
If a linear system has, in addition, the property of time invariance, then Equations ( 1.1)
through (1.3) reduce to
l'
y(t) = G(t - r)u(r)dr ( 14)
and
+
x(t) = Ax(t) Bu(t) 11.5)
+
y(t) = Cx(t) Du(t) ( 1.6)
For this class of linear time-invariant systems, the Laplace transfom1 is an important tool in
analysis and design. Applying the Laplace transform to (1.4) yields
yes)
= (;(5)6.(5) ( 1.7)
where a variable with a circumflex denotes the Laplace transform of the variable. The fun-:rion
(;(5) is called the trallsfer matrix. Both (1.4) and (1.7) are input-output or external descriprions.
The former is said to be in the time domain and the latter in the frequency domian.
Equations (l.l) through (1.6) are called continuous-time equations because their time
variable t is a continuum defined at every time instant in (-(~J. :xl). If the time is defined
only at discrete instants. then the corresponding equations are called discrete-time equations.
This text is devoted to the analysis and design centered around (1.1) through ( 1.7) and their
discrete-time counterparts.
We briefly discuss the contents of each chapter. In Chapter 2. after introducing the
aforementioned equations from the concepts of lumpedness, linearity, and time invariance.
we show how these equations can be developed to describe systems. Chapter 3 reviews linear
algebraic equations, the Lyapunov equation, and other pertinent topics that are essential for
this text. We also introduce the Jordan form because it will be used to establish a number of
results. We study in Chapter 4 solutions of the state-space equations in (1.2) and (1.5). Different
analyses may lead to different state equations tliat describe the same system. Thus we introduce
the concept of equivalent state equations. The basic relationship between state-space equations
and transfer matrices is also established. Chapter 5 introduces the concepts of bounded-input
bounded-output (BIBO) stability, marginal stability, and asymptotic stability. Every system
must be designed to be stable; otherwise, it may bum out or disintegrate. Therefore stability
is a basic system concept. We also introduce the Lyapunov theorem to check asymptotic
stability.
Chapter 6 introduces the concepts of controllability and observability. They are essential
in studying the internal structure of systems. A fundamental result is that the transfer matrix
describes only the controllable and observable part of a state equation. Chapter 7 studies
minimal realizations and introduces coprime polynomial fractions. We show how to obtain
coprime fractions by solving sets of linear algebraic equations. The equivalence of controllable
and observable state equations and coprime polynomial fractions is established.
The last two chapters discuss the design of time-invariant systems. We use controllable
and observable state equations to carry out design in Chapter 8 and use coprime polynomial
fractions in Chapter 9. We show that, under the controllability condition. all eigem'alues
of a system can be arbitrarily assigned by introducing state feedback. If a state equation
is observable, full-dimensional and reduced-dimensional state estimators. with any desired

4 INTRODUCTION
eigenvalues, can be constructed to generate estimates of the state. We also establish the
separation property. In Chapter 9, we discuss pole placement, model matching, and their
applications in tracking, disturbance rejection, and decoupling. We use the unity-feedback
configuration in pole placement and the two-parameter configuration in model matching. In our
design, no control performances such as rise time, settling time, and overshoot are considered:
neither are constraints on control signals and on the degree of compensators. Therefore this
is not a control text per se. However, all results are basic and useful in designing linear time
invariant control systems.
,,
\
I

Chapter
,f~,'
•
I  , .,. " ~
)
'",",,",  -j
;~~iDJI
Mathematical
| Descriptions  |     | of Systems  |     |     |
| ------------- | --- | ----------- | --- | --- |
2.1  Introduction
The class of systems studied in this text is assumed to have some input tenninals and output
terminals as shown in Fig. 2.1. We assume that if an excitation or input is applied to the input
tenninals, a unique response or output signal can be measured at the output terminals. This
unique relationship between the excitation and response, input and output, or cause and effect
is essential in defining a system. A system with only one input terminal and only one output
terminal is  called a single-variable system or a single-input single-output (SISO) system,
A system with two or more input terminals and/or two or more output terminals is called
a multi variable system. More specifically, we can call a system a multi-input multi-output
(MIMO) system if it has two or more input terminals and output terminals, a single-input
multi-output (SIMO) system if it has one input terminal and two or more output terminals.
| "it)  |     |     | y(r)  |     |
| ----- | --- | --- | ----- | --- |
0
| 0   | u (()  | yet)  |     |     |
| --- | ------ | ----- | --- | --- |
Black
box
| !I[kJ                | !I[k)  | y[k)  | y[k)     |             |
| -------------------- | ------ | ----- | -------- | ----------- |
| 0                    | k      |       | 0  I  2  | 3  4  5  k  |
| Figure 2.1  System.  |        |       |          |             |
5

,
6 MATHEMATICAL DESCRIPTIONS OF SYSTEMS
A system is called a continuous-time system if it accepts continuous-time signals as
its input and generates continuous-time signals as its output. The input will be denoted by
lowercase italic 11ft) for single input or by boldface u(t) for multiple inputs. If the system has
p input terminals, then uCt) is a p x 1 vector or u == [II) U2 .. , up]', where the prime denotes
the transpose. Similarly, the output will be denoted by y(t) or yet). The time t is assumed to
range from -00 to DC.
A system is called a discrete-time system if it accepts discrete-time signals as its input
and generates discrete-time signals as its output. All discrete-time signals in a system will
be assumed to have the same sampling period T. The input and output will be denoted by
u[k] :== u(kT) and y[k] :== y(kT), where k denotes discrete-time instant and is an integer
ranging from -00 to 00. They become boldface for mUltiple inputs and multiple outputs.
I
!
2.1.1 Causality and Lumpedness
A system is called a memoryless system if its output y(to) depends only on the input applied
at to; it is independent of the input applied before or after to. This will be stated succinctly as
follows: current output of a memoryless system depends only on current input; it is independent
of past and future inputs. A network that consists of only resistors is a memory less system.
Most systems, however, have memory. By this we mean that the output at to depends on
uCt) for t < to, t == to, and t > to. That is. current output of a system with memory may depend
on past, current, and future inputs.
A system is called a causal or nonanticipatory system if its current output depends on
past and current inputs but not on future input. If a system is not causal, then its current output
will depend on future input. In other words, a noncausal system can predict or anticipate what
will be applied in the future. No physical system has such capability. Therefore every physical
system is causal and causality is a necessary condition for a system to be built or implemented
in the real world. This text studies only causal systems.
Current output of a causal system is affected by past input. How far back in time will the
past input affect the current output? Generally, the time should go all the way back to minus
infinity. In other words. the input from -00 to time t has an effect on yet)· Tracking u(t)
from t == -00 is. if not impossible, very inconvenient. The concept of state can deal with this
problem.
Defillition 2.1 The state x(to) of a system at time to is the infonnation at to that, together
with the inpllt u(t), for t :::: to, determines uniquely the output yet) for all t :::: to.
By definition. ifwe know the state at to. there is no more need to know the input u(t) applied
before to in determining the output y(t) after to. Thus in some sense, the state summarizes the
effect of past input on future output. For the network shown in Fig. 2.2, if we know the voltages
x) (to) and X2 (to) across the two capacitors and the current X3 (to) passing through the inductor,
then for any input applied on and after to, we can determine uniquely the output for t :::: [0.
Thus the state of the network at time is
[0

2.2 Linear Systems 7
Figure 2.2 Network with 3 state variables.
Xl(tO)]
X(tO) = X2 (to)
[
X3 (to)
It is a 3 x I vector. The entries of x are called state variables. Thus, in general, we may consider
the initial state simply as a set of initial conditions.
Using the state at to, we can express the input and output of a system as
x(to) }
(2.1 )
u(t), t ::: to --- y(t), t::: to
It means that the output is partly excited by the initial state at to and partly by the input applied
at and after to. In using (2.1), there is no more need to know the input applied before to all the
way back to -00. Thus (2.1) is easier to track and will be called a state-input-output pair.
A system is said to be lumped if its number of state variables is finite or its state is a
finite vector. The network in Fig. 2.2 is clearly a lumped system; its state consists of three
numbers. A system is called a distributed system if its state has infinitely many state variables.
The transmission line is the most well known distributed system. We give one more example.
EXAMPLE 2.1 Consider the unit-time delay system defined by
=
yet) u(t - 1)
The output is simply the input delayed by one second. In order to determine (y(t), t ::: to}
from {u(t), t ::: to}, we need the information (u(t), to -I ::::: t < to}. Therefore the initial state
of the system is (u(t). to - 1 ::::: t < to}. There are infinitely many points in {to - 1 ::::: t < to}.
Thus the unit-time delay system is a distributed system.
2.2 Linear Systems
A system is called a linear system if for every to and any two state-input-Dutput pairs
xJto) }
> --- Yi(t). t ::: to
Ui ( t), t _ to
for i = 1, 2, we have

8  MATHEMATICAL DESCRIPTIONS OF SYSTEMS
+
| XI (to)  | Xl (to)          | }         |         |          |               |     |
| -------- | ---------------- | --------- | ------- | -------- | ------------- | --- |
| +        |                  |           | +       |          |               |     |
| Ut(t)    | U2(t),  t::: to  | -+ Yt(l)  | Y2(t),  | t::: to  | (additivity)  |     |
and
| aXt (to)  |          | }            |          |                |     |     |
| --------- | -------- | ------------ | -------- | -------------- | --- | --- |
|           |          | -+ aYt (I),  | t::: to  | (homogeneity)  |     |     |
| aUt (t),  | t::: to  |              |          |                |     |     |
for any real constant a, The first property is called the additivity property, the second, the
homogeneity property, These two properties can be combined as
+
| atXt (to)          | a2X2(tO)  | }            |     |           |     | t:::  |
| ------------------ | --------- | ------------ | --- | --------- | --- | ----- |
|                    |           | -+ atYt (t)  |     | +         |     |       |
|                    |           |              |     | a2Y2(t),  |     | to    |
| atut(tl +alU2(t),  |           | t::: to      |     |           |     |       |
for any real constants at and a2, and is call~d the superposition property. A system is called
a nonlinear system if the superposition property does not hold.
If the input u(t) is identically zero for t ::: to, then the output will be excited exclusively
by the initial state x(to). This output is called the zero-input response and will be denoted by
Y:i or
|     | X(to)  | }            |     | t:::  |     |     |
| --- | ------ | ------------ | --- | ----- | --- | --- |
|     |        | -+ Y:i (t),  |     |       | to  |     |
u(t) == 0,
t ::: to
If the initial state x(to) is zero, then the output will be excited exclusively by the input. This
output is called the zero-state response and will be denoted by Yos or
|     | X(to) = 0  | }           |     |          |     |     |
| --- | ---------- | ----------- | --- | -------- | --- | --- |
|     |            | -+ Yzs(t),  |     | t::: to  |     |     |
|     | u(t),      | t ::: to    |     |          |     |     |
The additivity property implies
|                | x(to)    |                  |     | x(to)          |     |       |
| -------------- | -------- | ---------------- | --- | -------------- | --- | ----- |
| Output due to  |          | - output due to  |     |                |     |       |
|                | {  t:::  |                  |     | {  u(t) == 0,  |     | t:::  |
|                | u(t),    | to               |     |                |     | to    |
x(to) = 0
+
output due to
{
u(t), t ::: to
or
+
| Response  | =  zero-input response  |     |     | zero-state response  |     |     |
| --------- | ----------------------- | --- | --- | -------------------- | --- | --- |
Thus the response of every linear system can be decomposed into the zero-state response and
the zero-input response. Furthermore, the two responses can be studied separately and their
sum yields the complete response. For nonlinear systems, the complete response can be very
different from the sum of the zero-input response and zero-state response. Therefore we cannot
separate the zero-input and zero-state responses in studying nonlinear systems.
If a system is linear, then the additivity and homogeneity properties apply to zero-state
responses. To be more specific, if x(to)  =  0, then the output will be excited exclusively by
the input and the state-input-output equation can be simplified as lUi  -+ Yi}. If the system is
|     | +   | +   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
linear, then we have {u t  U2  -+ Yt   Y2}  and {aui  -+ aYi} for all a  and all Ui. A similar
remark applies to zero-input responses of any linear system.
i,
Input-ilutput description  We develop a mathematical equation to describe the zero-state
I
response of linear systems. In this study, the initial state is assumed implicitly to be zero and the  I

2.2 Linear Systems 9
output is excited exclusively by the input. We consider first SISO linear systems. Let 8" (I -Id
be the pulse shown in Fig. 2.3. It has width L:,. and height 1/ L:,. and is located at time I,. Then
every input U{I) can be approximated by a sequence of pulses as shown in Fig. 2.4. The pulse
in Fig. 2.3 has height 1/ c,; thus 8,,(1 - ti)C, has height I and the left-most pulse in Fig. 2.4
with height U{ti) can be expressed as u{ti)8,,(t - tdC,. Consequently. the input u{t) can be
expressed symbolically as
U(/) "" Lu(t,)8,,{t - t;)L:,.
Let gt;(t, t;) be the output at time t excited by the pulse u(t) = 80(1 - til applied at time Ii.
Then we have
8" (t - Ii) ~ g u (t. ti)
8,,(1 -li)U(ti)C, ~ gu(t, l;)u(t;)L:,. (homogeneity)
L8,,(I -li)U(ti)L:,. ~ Lgt;(I, li)U(li)C, (additivity)
i
Thus the output y{t) excited by the input u{t) can be approximated by
y(t) "" Lgu(t, t,)U(ti)C, (2.2)
Figure 2.3 Pulse at I,.
1
I, I, + A
I '
I :
I
I,
Figure 2.4 Approximation of input signal.

10 MATHEMATICAL DESCRIPTIONS OF SYSTEMS
Now if t. approaches zero, the pulse 8~ (t -Ii) becomes an impulse at Ii, denoted by <5 (t -ti), and
the corresponding output will be denoted by g (t, Ii). As t. approaches zero, the approximation
in (2.2) becomes an equality, the summation becomes an integration, the discrete ti becomes
i:
a continuum and can be replaced by r, and t. can be written as dr. Thus (2.2) becomes
y(t) = g(l, r)u(,) dr (2.3)
Note that g(I, r) is a function of two variables. The second variable denotes the time at which
the impulse input is applied; the first variable denotes the time at which the output is observed.
Because g(t, T) is the response excited by an impulse, it is called the impulse response.
If a system is causal. the output will not appear before an input is applied. Thus we have
Causal <==> g~I, r) = 0 for t < T
A system is said to be relaxed at 10 if its initial state at to is O. In this case, the output y(t),
for I ::: 10, is excited exclusively by the input U(I) for 1 ::: to. Thus the lower limit of the
integration in (2.3) can be replaced by 10. If the system is causal as well, then g(l, r) = 0 for
I < r. Thus the upper limit of the integration in (2.3) can be replaced by I. In conclusion,
every linear system that is causal and relaxed at 10 can be described by
l'
yet) = g(t, ,)u(r) dT (2.4)
'0
In this derivation, the condition of lumpedness is not used. Therefore any lumped or distributed
linear system has such an input-output description. This description is developed using only
the additivity and homogeneity properties; therefore every linear system, be it an electrical
system, a mechanical system, a chemical process, or any other system, has such a description.
If a linear system has p input terminals and q output terminals, then (2.4) can be
extended to
l'
yet) = GU, r)u(r)dT (2.5)
'0
where
gllU, r) gl2Cl,r) glp(t, T)
g21(t, r) gnU, ,) g2p(t, T)
GU, r) =
and gij (t, T) is the response at time I at the i th output terminal due to an impulse applied at
time, at the jth input terminal, the inputs at other terminals being identically zero. That is,
gij(l, ,) is the impulse response between the jth input terminal and the ith output terminal.
Thus G is called the impulse response malrix of the system. We stress once again that if a
system is described by (2.5), the system is linear, relaxed at 10, and causal.
State-space description Every linear lumped system can be described by a set of equations
of the form

2.3 Linear Time-Invariant (LTI) Systems 11
= +
x(t) A(t)x(t) B(t)u(t) (2.6)
+
yet) = C(t)x(t) D(t)u{t) (2.7)
x
where := dx/dt. ' For a p-input q-output system, u is a p x I vector and y is a q x I vector.
If the system has n state variables, then x is an n x I vector. In order for the matrices in (2.6)
and (2.7) to be compatible, A, B, C, and D must be n x n, n x p, q x n, and q x p matrices.
The four matrices are all functions of time or time-varying matrices. Equation (2.6) actually
consists of a set of n first-order differential equations. Equation (2.7) consists of q algebraic
equations. The set of two equations will be called an n-dimensional state-space equation or,
simply, state equation. For distributed systems, the dimension is infinity and the two equations
in (2.6) and (2.7) are not used.
The input-output description in (2.5) was developed from the linearity condition. The
development of the state-space equation from the linearity condition. however, is not as simple
and will not be attempred. We will simply accepr it as a facL
2,3 Linear Time-Invariant (LTI) Systems
A system is said to be time invariant if for every state-input-output pair
x(to) }
~ yet), t 2: to
U ( t), 1 2: 10
and any T, we have
+
x u ( ( t t o - T T ) ) . t 2: to + T } ~ y(t - T), 1 2: to + T (time shifting)
It means that if the initial state is shifted to time to + T and the same input waveform is applied
from to + T instead of irom to, then the output waveform will be the same except thar it starts
to appear from time to + T. In other words, if the initial state and the input are the same, no
matter at what time they are applied, the output waveform will always be the same. Therefore,
. for time-invariant systems, we can always assume, without loss of generality, that to = O. If a
system is not time invariant. it is said to be time varying.
Time invariance is defined for systems, not for signals. Signals are mostly time varying.
If a signal is time invariant such as u (t) = I for all I, then it is a very simple or a tri vial signal.
The characteristics of time-invariant systems must be independent of time. For example, the
network in Fig. 2.2 is time invariant if R" Cr, and L, are constants.
Some physical systems must be modeled as time-varying systems. For example, a burning
rocket is a time-varying system. because its mass decreases rapidly with time. Although the
performance of an automobile or a TV set may deteriorate over a long period of rime, irs
characteristics do not change appreciable in the first couple of years. Thus a large number of
physical systems can be modeled as time-invariant systems over a limited time period.
L We use A := B to denOle that A. by definition. equals B. We use A = : B to denote that B. by definition, equals A.

12  MATHEMATICAL DESCRIPTIONS OF SYSTEMS
Input-output description  The zero-state response of a linear system can be described by
(2.4). Now if the system is time invariant as well. then we have'
|     |     |          | =   | +          | +   | =         |        | =     |     |     |
| --- | --- | -------- | --- | ---------- | --- | --------- | ------ | ----- | --- | --- |
|     |     | g(t. r)  |     | g(1  T. r  |     | T)  g(t - | r. 0)  | g(t - | r)  |     |
for any T. Thus (2.4) reduces to
|     |     |     |     | l'  |     |     | l'  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     | =   |     |     | =   |     |     |     |     |
(2.8)
|     |     | y(t)  |     | g(1 - | r)u(r)dr  |     | g(r)u(t - | r)dr  |     |     |
| --- | --- | ----- | --- | ----- | --------- | --- | --------- | ----- | --- | --- |
where we have replaced 10 by O. The second equality can easily be verified by changing the
variable. The integration in (2.8) is called a convolution integral. Unlike the time-varying case
where g is a function of two variables. g is a function of a single variable in the time-invariant
=
case. By definition g(l)  g(t - 0) is the output at time I due to an impulse input applied at
time O. The condition for a linear time-inv.iui.ant system to be causal is g(t) = 0 for I  < O.
EXAMPLE 2.2  The unit-time delay system studied in Example 2.1 is a device whose output
equals the input delayed by I second. If we apply the impulse 8(1) at the input terminal. the
output is .5 (t - I). Thus the impulse response of the system is 8 (I - I).
EXAMPLE 2.3  Consider the  unity-feedback system shown in Fig.  2.5(a).  It consists of a
multiplier with gain a and a unit-time delay element. It is a 5150 system. Let r(t) be the
input of the feedback system. If r(l) =  a(t). then the output is the impulse response of the
feedback system and equals
x
|     |     | =   |     |     |     |     |     | + ... =  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | -------- | --- | --- |
gl(t)  a8(r - I) +a 2 8(t - 2) +a 3 8(r - 3)  2::>i8(1 - i)  (2.9)
;=1
Let r(r) be any input with r(t)  == 0 for I  < 0; then the output is given by
|     |         |     | ,      |             |     |       | l'    |      |           |     |
| --- | ------- | --- | ------ | ----------- | --- | ----- | ----- | ---- | --------- | --- |
|     |         |     | 1      |             |     | 2:>i  |       |      |           |     |
|     | y(r) =  |     | gl(l - | r)r(r)dr =  |     | X     | 8(t - | r  - | i)r(r)dr  |     |
",
-4
|     |     |     | o   |     |     | i=1  | 0   |     |     |     |
| --- | --- | --- | --- | --- | --- | ---- | --- | --- | --- | --- |
j
J
x
=Lair(l-i)
|     |     |     | ;=1  | r=t-;  | i=l  |     |     |     |     |     |
| --- | --- | --- | ---- | ------ | ---- | --- | --- | --- | --- | --- |
Because the unit-time delay system is distributed. so is the feedback system.
| +     |     |     | L'nit-time  |          |       | rtf)  +  |     |     | UniHime  | yIT )  |
| ----- | --- | --- | ----------- | -------- | ----- | -------- | --- | --- | -------- | ------ |
| TIt)  |     |     |             |          | y(t}  |          |     |     |          |        |
|       |     |     | delay       | I---r".  |       |          |     |     | delay    |        |
|       |     |     | element     |          |       |          |     |     | element  |        |
(b)
(a)
Figure 2.5  Positive and negative feedback systems.
2. ~ote that g(t. r) and g(t - r) are two different functions. However. for convenience. the same symbol g is used.

13
|     |     | 2.3  | Linear Time-Invariant (LTI) Systems  |     |
| --- | --- | ---- | ------------------------------------ | --- |
Transfer-function matrix  The Laplace transform is an important tool in the: study of linear
time-invariant (LTI) systems. Let .v(s) be the Laplace transform of y(t), that is .
1
x
|     | .v(s) =  | y(t)e-stdl  |     |     |
| --- | -------- | ----------- | --- | --- |
Throughout this text, we use a variable with a circumflex to denote the Laplace transform of
the variable. For causal systems, we have g(t)  =  0 for I  < 0 or g(1 - =  0 for r  > I. Thus
r)
the upper integration limit in (2.8) can be replaced by 00. Substituting (2.8) and interchanging
the order of integrations, we obtain
(I X
fOO
yes)
| =    |           | g(t - rjlt(r) dr) e-s(t-r)e-srdl  |     |     |
| ---- | --------- | --------------------------------- | --- | --- |
| I""  | 1=0  r=O  |                                   |     |     |
(f X
| =   |     | g(1 - r)e-s(t-r) dl) u(r)e-sr dr  |     |     |
| --- | --- | --------------------------------- | --- | --- |
r::=:O  1=0
which becomes. after introducing the new variable v = I  - r,
|          | l~o (l~-r  |           |            | sr  |
| -------- | ---------- | --------- | ---------- | --- |
| yes)  =  |            | g(v)e- st | dV) u(r)e- | dr  |
'
Again using the causality condition to replace the lower integration limit inside the parentheses
from v  =  -r to v  =  O. the integration becomes independent of r and the double integrations
become
or
=
(2.10)
|     | yes)  | g(s)u(s)  |     |     |
| --- | ----- | --------- | --- | --- |
where
1
x
|     | 8(5) =  | g(t)e-udl  |     |     |
| --- | ------- | ---------- | --- | --- |
is called the transfer function of the system. Thus the transfer function is the Laplace transform
of the impulse response and. conversely, the impulse response is the inverse Laplace transform
of the transfer function. We see that the Laplace transform transforms the convolution integral
in (2.8) into the algebraic equation in (2.10). In analysis and design. it is simpler to use algebraic
equations than to use convolutions. Thus the convolution in (2.8) will rarely be used in the
remainder of this text.
For a p-input q-output system, (2.10) can be extended as
| .VI(S)   | gll(s)  | gI2(S)  | glp(S)  | UI(S)   |
| -------- | ------- | ------- | ------- | ------- |
| '\·,(5)  | 821(5)  | g22(S)  | 82p(S)  | 112(5)  |
or
yes)
= G(s)n(s)
(2.11 )

,
,
i
14
MATHEMATICAL DESCRIPTIONS OF SYSTEMS
is the transfer function from the jth input to the ith output. The q x
,:,here gij(S)  p matrix
G(s) is called the transfer-function matrix or, simply, transfer marrix of the system.
EXAMPLE  2.4  Consider the  unit-time  delay  system studied in Example  2.2.  Its  impulse
| response is i5(t - | I). Therefore its transfer function is  |     |     |     |     |
| ------------------ | --------------------------------------- | --- | --- | --- | --- |
1'X)
|     | g(s) =  L[i5(t - | I)J =  | 8(t - l)e-" | dt =  e-'t!t=l =  | e-'  |
| --- | ---------------- | ------ | ----------- | ----------------- | ---- |
This transfer function is an irrational function of s.
EXAMPLE 2.5  Consider the feedback system shown in Fig. 2.S(a). The transfer function of
the unit-time delay element is e-'. The transfer function from r to y can be computed directly
| from the block diagram as  |     |     | }   |     |     |
| -------------------------- | --- | --- | --- | --- | --- |
(2.12)
This can also be obtained by taking the Laplace transform of the impulse response, which was
computed in (2.9) as
Io>c
i
=
|     |     | gl(t)  | i5(t - | i)  |     |
| --- | --- | ------ | ------ | --- | --- |
;=1
| Because L[i5{t - | ill = e-i ' , the Laplace transform of g/ |             |          | {t) is            |     |
| ---------------- | ----------------------------------------- | ----------- | -------- | ----------------- | --- |
|                  |                                           |             | ""       | 00                |     |
|                  | g/(s)  =                                  | L[g/(tl] =  | La'e-i,  | =  ae-' L(ae-')i  |     |
|                  |                                           |             | ;=1      | ;=0               |     |
I
00.
'\'r' =
|     |     | L...  | 1-  | r   |     |
| --- | --- | ----- | --- | --- | --- |
;=0
| for Ir  I <  I. we can express the infinite series in closed form as  |     |     |     |     |     |
| --------------------------------------------------------------------- | --- | --- | --- | --- | --- |
which is the same as (2.12).
The transfer function in (2.12) is an irrational function of s. This is so because the feedback
system is a distributed system. If a linear time-invariant system is lumped, then its transfer
function will be a rational function of of. We study mostly lumped systems; thus the transfer
functions we will encounter are mostly rational functions of s.
Every rational transfer function can be expressed as g(s) =  N(s)/ D(s), where N(s) and
D(s) are polynomials of s. Let us use deg to denote the degree of a polynomial. Then g(s) can
be classified as follows:  Ii
~
| ",) prop" <> de. D (,) e de. N (,) <> it |     |     |                             |     |     |
| ---------------------------------------- | --- | --- | --------------------------- | --- | --- |
| •                                        |     |     | 0 0)  "'0 o,"oo,"ro CO"""'  |     |     |

2.3 Linear Time-Invariant (LTI) Systems 15
• g(s) strictly proper ¢> deg D(s) > degN(s) ¢> g(oo) = O.
=
• g(s) biproper ¢> deg D(s) deg N(s) ¢> g(oo) = nonzero constant.
• g(s) improper ¢> deg D(s) < deg N(s) ¢> Ig(x)1 = 00.
Improper rational transfer functions will amplify high-frequency noise, which often exists in
the real world; therefore improper rational transfer functions rarely arise in practice.
A real or complex number).. is called a pole of the proper transfer function g (s) =
N(s)/D(s) if Ig()..)1 = 00; a zero if gO.) = O. If N(s) and D(s) are coprime, that is, have
g
no common factors of degree I or higher, then all roots of N (s) are the zeros of (s), and all
roots of D(s) are the poles of g(s). In terms of poles and zeros, the transfer function can be
expressed as
=
g(s) k (s - ::I)(S - :2)· ·· (s - Zm)
(s - piles - P2) · .. (s - POI)
This is called the ::era-pole-gain f0rm. In MATLAB, this form can be obtained from the transfer
function by calling [z, p, kJ = tf2zp (num, den).
, ,
A rational matrix G(s) is said to be proper if its every entry is proper or if G(oo) ~s a zero
or nonzero constant matrix: it is strictly proper ifits every entry is strictly proper or ifG(oo) is
G
a zero matrix. If a rational matrix G(s) is square and if both G(s) and -I (s) are proper. then
G(s) is said to be biproper. We call A a pole of G(s) if it is a pole of some entry of G(s). Thus
every pole of every entry of G(s) is a pole of G(s). There are a number of ways of defining
zeros for G(s). We call)" a blocking zera if it is a zero of every nonzero entry of G(s). A more
useful definition is the transmission zero, which will be introduced in Chapter 9.
State-space equation Every linear time-invariant lumped system can be described by a set
of equations of the form
+
x(t) = Ax(t) Bu(t)
(2.13 )
+
y(t) = Cx(t) Du(t)
For a system with p inputs, q outputs, and Il state variables, A, B, C, and D are, respectively,
n x n. n X p, q x n. and q x p constant matrices. Applying the Laplace transform to (2.13)
yields
+
sx(s) - x(O) = Ax(s) Bu(s)
5'(s) = Cx(s) + Du(s)
which implies
+
xes) = (sl - A)-lx(O) (sl - A)-IBu(s) (2.14 )
+ +
Yes) = C(sl - A)-IX(D) C(sI - A)-IBu(s) Du(s) (2.15)
They are algebraic equations. Given xeD) and u(s), xes) and Yes) can be computed algebraically
from (2.14) and (2.15). Their inverse Laplace transforms yield the time responses xU) and
y(t). The equations also reveal the fact that the response of a linear system can be decomposed

16  MATHEMATICAL DESCRIPTIONS OF SYSTEMS
as the zero-state response and the zero-input response. If the initial state xeD)  is zero. then
(2.15) reduces to
|     |       | == [C(sI - | A)-'B  +  |          |     |     |
| --- | ----- | ---------- | --------- | -------- | --- | --- |
|     | Yes)  |            |           | D]ii(s)  |     |     |
Comparing this with (2.11) yields
A)-'B + D
|     |     | G(s) == CCsI - |     |     |     | (2.16)  |
| --- | --- | -------------- | --- | --- | --- | ------- |
This relates the input-output (or transfer matrix) and state-space descriptions.
The functions tf2ss and 552 tf in MATLAB compute one description from the other.
They compute only the SISO and SIMO cases. For example, (num, den J = ss2 tf (a, b, c,
d, 1) computes the transfer matrix from the first input to all outputs or, equivalently. the first
column of G(s). If the last argument I -in $,   s 2 t f ( a , b, c, d, 1) is replaced by 3. then the
function generates the third column of G(s).
To conclude this section. we mention that the Laplace transform is not used in studying
linear time-varying systems. The Laplace transform of get, r) is a function of two variables
and i[A(t)x(t)] f. i[A(t)]i[x(r)]; thus the Laplace transform does not offer any advantage
and is not used in studying time-varying systems.
2.3.1  Op-Amp Circuit Implementation
Every linear time-invariant (LTI) state-space equation can be implemented using an operational
amplifier (op-amp) circuit. Figure 2.6 shows two standard op-amp circuit elements. All inputs
are connected.  through resistors, to  the  inverting  terminal.  Not shown are  the  grounded
noninverting terminal and power supply. If the feedback branch is a resistor as shown in Fig.
2.6(a), then the output of the element is -(ax, +bX2 +CX3). If the feedback branch is a capactor
with capacitance C and RC ==  I as shown in Fig. 2.6(b), and if the output is assigned as x, then
| +   | +   |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
.~  ==  -(av,  bt'2  CV3)' We call the first element an adder; the second element, an integrator.
Actually, the adder functions also as multipliers and the integrator functions also as multipliers
and adder. If we use only one input, say, x"  in Fig. 2.6(a). then the output equals -ax,. and
the element can be used as an inverter with gain a. Now we use an example to show that every
LTI state-space equation can be implemented using the two types of elements in Fig. 2.6.
Consider the state equation
|     |     | -0.3]  |     | [-2]  |     |     |
| --- | --- | ------ | --- | ----- | --- | --- |
[x,(t)]
|         |     |     |        | +  u(t)  |     | (2.17)  |
| ------- | --- | --- | ------ | -------- | --- | ------- |
|         |     | -8  | X2(t)  | 0        |     |         |
| Ria  R  |     |     | Ria    | C        |     |         |
| XI      |     |     |        |          | =,  |         |
1'1
| Rib  |     |     | Rib  |     | RC  |     |
| ---- | --- | --- | ---- | --- | --- | --- |
x:!
l'~
| Ric   |                 |       | Ric  |       | x         |       |
| ----- | --------------- | ----- | ---- | ----- | --------- | ----- |
| .1:]  |                 | l']   |      |       |           |       |
|       | -(ax! + bx:! +  |       |      | -i =  | +         | +     |
|       |                 | CX~)  |      |       | aVI  bV2  | eLl3  |
| (a)   |                 |       |      | (b)   |           |       |
Figure 2.6  Two op-amp circuit elements.
l

|     |     |     |     |     | 2.4  Linearization  | 17  |
| --- | --- | --- | --- | --- | ------------------- | --- |
(2.18)
It  has dimension 2 and we need two integrators to implement it.  We  have the freedom in
choosing the output of each integrator as +Xi or -Xi. Suppose we assign the output of the
left-hand-side (LHS) integrator as XI  and the output of the right-hand-side (RHS) integrator
as -X2 as shown in Fig. 2.7. Then the input of the LHS integrator should be, from the first
+  +
equation of (2.17), -XI  =  -2xl  O.3xz  211  and is connected as shown. The input of the
RHS integrator should be .i2 = XI - 8X2 and is connected as shown. If the output of the adder
=
is chosen as y, then its input should equal - y  2xI - 511, and is connected as shown.
3X2 -
Thus the state equation in (2.17) and (2.18) can be implemented as shown in Fig. 2.7. Note that
there are many ways to implement the same equation. For example. if we assign the outputs
of the two integrators in Fig. 2.7 as XI  and X2, instead of Xl  and -X2, then we will obtain a
different implementation.
In actual operational amplifier circuits, the range of signals is limited, usually I or 2 volts
below the supplied voltage. If any signal grows outside the range, the circuit will saturate or
bum out and the circuit will not behave as the equation dictates. There is. however, a way to
deal with this problem. as we will discuss in Section 4.3.1.
2.4  Linearization
Most physical systems are nonlinear and time varying. Some of them can be described by the
nonlinear differential equation of the form
R
~
v~
|     |     | - x,  /  R  |     |     |     |     |
| --- | --- | ----------- | --- | --- | --- | --- |
'" .A
|     | R ?   | C   |     | C   |         |     |
| --- | ----- | --- | --- | --- | ------- | --- |
|     | I -   |     |     |     | RJ2  R  |     |
|     |       | I/  |     | IL  |         |     |
A
|     |      | "   |     | "         | vv~  |     |
| --- | ---- | --- | --- | --------- | ---- | --- |
|     | R/2  | "'- |     |           | RJ3  |     |
|     |      |     | R   | ~  -.\"2  |      |     |
|     | .    | Xi  |     |           | »-~  |     |
| u   |      | /'  | vv  |           |      | \"  |
V
R/5
|     | RjO.3  |     | RI8  |     |     |     |
| --- | ------ | --- | ---- | --- | --- | --- |
vAvAv
I~ A  V
|     | vv~  | R     |     |     |         |     |
| --- | ---- | ----- | --- | --- | ------- | --- |
|     |      | v .A  |     |     | RC = I  |     |
/
x:
'" .A
R
R
~
R  ~
-II
.AA  V
| Figure 2.7  | Op-amp implementation of (2.17) and (2.18).  |     |     |     |     |     |
| ----------- | -------------------------------------------- | --- | --- | --- | --- | --- |

r
18 MATHEMATICAL DESCRIPTIONS OF SYSTEMS
x(r) == h(x(r), u(r), r) (2.19)
yet) == f(x(r), u(r), r)
where hand f are nonlinear functions. The behavior of such equations can be very complicated
and its study is beyond the scope of this text.
Some nonlinear equations, however, can be approximated by linear equations under
certain conditions. Suppose for some input function Uo (t) and some initial state, Xo (r) is the
solution of (2.19); that is,
(2.20)
+
Now suppose the input is perturbed slightly to become Uo (r) u(r) and the initial state is also
perturbed only slightly. For some nonlinear equations, the corresponding solution may differ
+
from xo(t) only slightly. In this case, the s'olution can be expressed as xo(r) x(r) with x(n
small for all I.) Under this assumption, we can expand (2.19) as
xo(r) + x(t) == h(xo(t) + x(t), uo(t) + ii(r), t)
ah ah_
== h(xo(t), uo(t) , t) + ax x + au u + ... (2.21 )
where, forh == [hi h2 hJl', x == [XI X2 xJ)', and u == [UI uz)',
They are called lacobians. Because A and B are computed along the two time functions xo(t)
x
and uo(r), they are, in general, functions of r. Using (2.20) and neglecting higher powers of
and ii. we can reduce (2.21) to
x(r) == A(r)x(t) + B(r)ii(t)
This is a linear state-space equation. The equation yet) == f(x(t), u(t), r) can be similarly
linearized. This linearization technique is often used in practice to obtain linear equations.
2.5 Examples
In this section we use examples to illustrate how to develop transfer functions and state-space
equations for physical systems.
EXAMPLE 2.6 Consider the mechanical system shown in Fig. 2.8. It consists of a block with
mass m connected to a wall through a spring. We consider the applied force u to be the input
3. This is not true in general. For some nonlinear equations, a very small difference in initial stales will generate
completely different solutions, yielding the phenomenon of chaos.

2.S Examples 19
and displacement y from the equilibrium to be the output. The friction between the floor and the
block generally consists of three distinct parts: static friction, Coulomb friction, and viscous
=
friction as shown in Fig. 2.9. Note that the horizontal coordinate is velocity j. dy/dt. The
friction is clearly not a linear function of the velocity. To simplify analysis, we disregard
the static and Coulomb frictions and consider only the viscous friction. Then the friction
becomes linear and can be expressed as k,5·(t), where k, is the viscous friction coefficient. The
characteristics of the spring are shown in Fig. 2.10: it is not linear. However, if the displacement
is limited to (y" Y2) as shown, then the spring can be considered to be linear and the spring
force equals k y, where k2 is the spring constant. Thus the mechanical system can be modeled
2
as a linear system under linearization and simplification.
.'. =0
Figure 2.8 Mechanical system.
p
h
f"
J. u
i.Lr-.'"V''V"'L.-.l m
Force Force
Viscous friction
Static
\
Velocity -----:,tL----.... Velocity
o
Coulomb
(al (b)
Figure 2.9 Mechanical system.(a) Static and Coulomb frictions. (b) Viscous friction.
Figure 2.10 Characteristic of spring. Force
Break
----,}-
Displacemenl

20 MATHEMATICAL DESCRIPTIONS OF SYSTEMS
We apply Newton's law to develop an equation to describe the system. The applied force
u must overcome the friction and the spring force. The remainder is used to accelerate the
block. Thus we have
(2.22)
where y == d2y(t)/dt2 and.y == dy(t)/dt. Applying the Laplace transform and assuming zero
initial conditions, we obtain
which implies
, 1 ,
+ +
yes) == k k u(s)
ms,.-?
IS 2
This is the input-{)utput description of the system. Its transfer function is 1/(ms2 + kls + k 2).
If m == I, kl == 3, k2 == 2, then the impulse response of the system is
get) == rl [ 1 ] == £-1 [_1_ __1 _] == e-r _ e-2r
s2 + 3s + 2 s + 1 s + 2
and the convolution description of the system is
yet) == for get - r)u(r) dr == for (e-U- r ) - e-2(r-r)u(r) dr
Next we develop a state-space equation to describe the system. Let us select the displace
y.
ment and velocity of the block as state variables; that is, XI == y, X2 == Then we have, using
(2.22),
They can be expressed in matrix form as
y(t) ==[I 01[XI(t)]
X2(t)
This state-space equation describes the system.
EXAMPLE 2.7 Consider the system shown in Fig. 2.11. It consists of two blocks, with masses
m I and m2. connected by three springs with spring constants k;. i == I, 2. 3. To simplify the
discussion, we assume that there is no friction between the blocks and the floor. The applied
~ y, ~ y, r Figure 2.11 Spring·mass system .
~m, ~m'
.
777777777)7777777777
i

|     |     |     |     |     |     |     |     |     | 2.5  Examples  | 21  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | -------------- | --- |
force  U  I must overcome the spring forces and the remainder is used to accelerate the block,
thus we have
or
=
|     |     |     |       | +   | +             |           |     |     |     | (2.23)  |
| --- | --- | --- | ----- | --- | ------------- | --------- | --- | --- | --- | ------- |
|     |     |     | mlYI  |     | (kl  k 2 )YI  | - k Z Y2  | UI  |     |     |         |
For the second block. we have
=
|     |     |     | m2Yc - |     | k2YI  +  (kl  | +  k2)Y2  | lI2  |     |     | (2.24)  |
| --- | --- | --- | ------ | --- | ------------- | --------- | ---- | --- | --- | ------- |
They can be combined as
|     |     | m l  | m0, ][Y.IJ+[kl+k2  |     |      | - k2    | ][YI]=[lIl]  |     |      |     |
| --- | --- | ---- | ------------------ | --- | ---- | ------- | ------------ | --- | ---- | --- |
|     | [   | o    |                    |     |      | +       |              |     |      |     |
|     |     |      |                    | Y2  | -k2  | kl  k2  | Y2           |     | liZ  |     |
This is a standard equation in studying vibration and is said to be in normal form. Se~ Reference
[18]. Let us define
.~i
oj
Then we can readily obtain
0
|            |     | 0   |     |     | 0    | 0       |     |     | 0   |     |
| ---------- | --- | --- | --- | --- | ---- | ------- | --- | --- | --- | --- |
| m -(kl + k |     |     | 2)  |     | k2   |         |     | I   |     |     |
|            |     |     |     | 0   |      | 0  [~}  |     |     | 0   |     |
|            |     | ml  |     |     | nil  |         |     | ml  |     |     |
-
[  III ]
|     |     | 0   |     | 0   | 0   | 1   |     | 0   | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
U2
|     |     | k,  |     |     | -(kl + k |     |     |     |     |     |
| --- | --- | --- | --- | --- | -------- | --- | --- | --- | --- | --- |
|     |     |     |     |     | 2)       |     |     |     | 1   |     |
|     |     |     |     | 0   |          | 0   |     | 0   |     |     |
|     |     |     |     |     | nil      |     |     |     | m2  |     |
m2
0  0
|     | [~~]  |     | [~  |       | 0o ] x  |     |     |     |     |     |
| --- | ----- | --- | --- | ----- | ------- | --- | --- | --- | --- | --- |
|     | y :=  | =   |     | 0  1  |         |     |     |     |     |     |
This two-input two-output state equation describes the system in Fig. 2.11.
To develop its input-output description. we apply the Laplace transform to (2.23) and
(2.24) and assume zero initial conditions to yield
|     |     |                |     | +        | +                |                      |     |     |     |     |
| --- | --- | -------------- | --- | -------- | ---------------- | -------------------- | --- | --- | --- | --- |
|     |     | In Is2.VI (s)  |     | (k       | l  k2),I'1 (s) - | k 2 Y2(S) = III (s)  |     |     |     |     |
|     |     |                |     |          | +                | +                    |     |     |     |     |
|     |     | m2s2.Hs) -     |     | k2YI(s)  | (kl              | k2),V2(S) = 112(S)   |     |     |     |     |
From these two equations. we can readily obtain
[1Il,S2 :(:)1
|     | .VI  | (5)]  | =   |     | +  k2  |     |     |     |     |     |
| --- | ---- | ----- | --- | --- | ------ | --- | --- | --- | --- | --- |
[
|     | Y2(S)  |     |     | kz  |     |     |     |     |     |     |
| --- | ------ | --- | --- | --- | --- | --- | --- | --- | --- | --- |
drs)
where
This is the transfer-matrix description of the system. Thus what we will discuss in this text can
be applied directly to study vibration.

,
,
22  MATHEMATICAL DESCRIPTIONS OF SYSTEMS  ;
EXAMPLE 2.8  Consider a cart with an inverted pendulum hinged on top of it as shown in Fig.
2.12. For simplicity, the cart and the pendulum are assumed to move in only one plane, and the
friction, the mass of the stick, and the gust of wind are disregarded. The problem is to maintain
the pendulum at the vertical position. For example, if the inverted pendulum is falling in the
direction shown, the cart moves to the right and exerts a force, through the hinge, to push the
pendulum back to the vertical position. This simple mechanism can be used as a model of a
space vehicle on takeoff.
Let H and V be, respectively, the horizontal and vertical forces exerted by the cart on the
pendulum as shown. The application of Newton's law to the linear movements yields
2y
d
| M-  | =u-H  |     |     |     |
| --- | ----- | --- | --- | --- |
dl2
d2
|                                   |     | .  I  | •• ..      | . ,  .  |
| --------------------------------- | --- | ----- | ---------- | ------- |
| H = m-(y + IsmB) = my + mlOcosO - |     |       | ml(Ot smO  |         |
2
dl
d2
|         | =             | =           | .•  .  • ,  |     |
| ------- | ------------- | ----------- | ----------- | --- |
| mg - V  | m-, (l cosO)  | ml[-O smO - | (0)- cosO]  |     |
dl-
The application of Newton's law to the rotational movement of the pendulum around the hinge
yields
|     |             | =        | +           |     |
| --- | ----------- | -------- | ----------- | --- |
|     | mgl sin 61  | mle . I  | my I cos 0  |     |
They are nonlinear equations. Because the design objective is to maintain the pendulum
e
at the vertical position, it is reasonable to assume 0 and  to be small. Under this assumption,
we can use the approximation sin 0 = 61 and cos 61  =  I. By retaining only the linear terms in 61
e  oe,
and  or, equivalently, dropping the terms with 612 , (0)2, 00, and  we obtain V = mg and
|     | M.r = u - | my - | mle  |     |
| --- | --------- | ---- | ---- | --- |
+
g61  = Ie  y
which imply
My = u -mg61  (2.25)
+  (2.26)
|     | Mle =        | (M                           | m)g61 - u  |     |
| --- | ------------ | ---------------------------- | ---------- | --- |
|     | Figure 2.12  | Cart with invened pendulum.  |            |     |
,
,I
I

|     |     |     |     |     |     |     |     | 2.S  Examples  | 23  |
| --- | --- | --- | --- | --- | --- | --- | --- | -------------- | --- |
Using  these  linearized equations. we  now  can develop  the  input-{)utput and state-space
descriptions. Applying the Laplace transfonn to (2.25) and (2.26) and assuming zero initial
conditions. we obtain
|     |     | Ms 2y"e s) = u" (s) - |     |     | mgB" (s)  |       |     |     |     |
| --- | --- | --------------------- | --- | --- | --------- | ----- | --- | --- | --- |
|     |     |                       | 2'  | =   | +         | •     |     |     |     |
|     |     | Mis B(s)              |     | (M  | m)gB(s) - | u(s)  |     |     |     |
From these equations. we can readily compute the transfer function  g  yu (s) from u to y and the
transfer function gou (s) from u to B as
g
|     |     | •           |     |                                | S2 _  |       |     |     |     |
| --- | --- | ----------- | --- | ------------------------------ | ----- | ----- | --- | --- | --- |
|     |     | g yu (s) =  |     | ~:-:-:;---:-:-,==-+--- -:---:  |       |       |     |     |     |
|     |     |             |     | s2[Ms2 -                       | (M    | m)g]  |     |     |     |
|     |     | •           |     |                                | -1    |       |     |     |     |
=
|     |     | gou(s)  |     | M     | (M  | )     |     |     |     |
| --- | --- | ------- | --- | ----- | --- | ----- | --- | --- | --- |
|     |     |         |     | s  2  | -   | +m g  |     |     |     |
=
To develop a state-space equation. we select state variables as  =  y.  = y.  B.
|     |     |     |     |     |     |     |     | XI  X2  | X3  |
| --- | --- | --- | --- | --- | --- | --- | --- | ------- | --- |
= e.
and  Then from this selection. (2.25). and (2.26) we can readily obtain
X4
0
| ;~]  | [~~  |     | -m~/M  |     | ~]  |     |     |     |     |
| ---- | ---- | --- | ------ | --- | --- | --- | --- | --- | --- |
[
|     |     |       |     |     |     |       | + [  | M        |     |
| --- | --- | ----- | --- | --- | --- | ----- | ---- | -------- | --- |
|     | =   |       |     |     |     | [;:]  |      | 11 ]  U  |     |
|     |     | 0  0  |     | 0   |     | 1     |      | 0        |     |
| X3  |     |       |     |     |     | X3    |      |          |     |
X4
|     |          | 0  0       | (M +m)gI |     | MI  0  | X4  |     | -IIMI  |         |
| --- | -------- | ---------- | -------- | --- | ------ | --- | --- | ------ | ------- |
|     | Y =  [I  | 0  0  O]x  |          |     |        |     |     |        | (2.27)  |
e
This state equation has dimension 4 and describes the system when Band  are very small.
A communication satellite of mass m orbiting around the earth is shown in
EXAMPLE 2.9
Fig. 2.13. The altitude of the satellite is specified by r (t).  B( t). and </I (t) as shown. The orbit
can be controlled by three orthogonal thrusts ur(t).  uo(t). and u</>(t). The state. input. and
output of the system are chosen as
r(t)
f(t)
B(t)
|         |     |     |       | = [U | r ( t  | ) ]       | =   | [  re t )   ]  |     |
| ------- | --- | --- | ----- | ---- | ------ | --------- | --- | -------------- | --- |
| x(t) =  |     |     | u(t)  |      | U g (t | )   yet)  |     | B ( t )        |     |
e(t)
</I (t)
u</> (t)
</I(t)
</I (t)
Then the system can be shown to be described by
r
|     |     | r02 cos2 </I + rei} - |     |     |     | +          |     |     |     |
| --- | --- | --------------------- | --- | --- | --- | ---------- | --- | --- | --- |
|     |     |                       |     |     |     | kl r2  url | m   |     |     |
o
x
| =   | hex. u) =  |     |      |        |                      |     |                 |     | (2.28)  |
| --- | ---------- | --- | ---- | ------ | -------------------- | --- | --------------- | --- | ------- |
|     |            |     | I r  | + 2e¢  | sin </I I cos </I +  |     | uol mr cos </I  |     |         |
-2fO
¢
+
|     |     | _0  | 2 cos </I sin 4> - |     | 2r¢l | r  u</>I mr  |     |     |     |
| --- | --- | --- | ------------------ | --- | ---- | ------------ | --- | --- | --- |

24  MATHEMATICAL DESCRIPTIONS OF SYSTEMS
-
-
u,
I  Satellite (mass m)
I
Earth
|     |     | e/.. " - | ---_ -- |     | I  '"  |     |     |     |
| --- | --- | -------- | ------- | --- | ------ | --- | --- | --- |
1,/
'"
|     | ---- | ________ ::::.J,..  |     |     |     |     |     |     |
| --- | ---- | ------------------- | --- | --- | --- | --- | --- | --- |
Figure 2.13  Satellite in orbit.
One solution, which corresponds to a circular equatorial orbit, is given by
Uo  == 0
r; w;
with  = k, a known physical constant. Once the satellite reaches the orbit. it will remain
in the orbit as long as there are no disturbances. If the satellite deviates from the orbit, thrusts
must be applied to push it back to the orbit. Define
|       | =      | +     |     |               | +      |            |     | +     |
| ----- | ------ | ----- | --- | ------------- | ------ | ---------- | --- | ----- |
| x(t)  | Xo(t)  | x(t)  |     | u(t) = uo(t)  | ii(t)  | y(t) = Yo  |     | y(t)  |
If the perturbation is very small, then (2.28) can be linearized as
|     |     |      |     |     | o   | o   | o   |     |
| --- | --- | ---- | --- | --- | --- | --- | --- | --- |
|     |     | 0    |     | 0   |     |     |     |     |
|     |     | 3w2  |     |     |     | o   | o   |     |
|     |     |      | 0   | 0   |     |     |     |     |
0
o  o
|      |     | 0   | 0    | 0   |     |     |     |       |
| ---- | --- | --- | ---- | --- | --- | --- | --- | ----- |
|      | =   |     | 2w   |     |     |     |     |       |
| xU)  |     |     | - o  |     | o   | o   | o   | x(t)  |
|      |     | 0   |      | 0   |     |     |     |       |
ro
|     |     | 0   | 0   | 0   | 0   | 0   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
,
|     |     | 0   | 0   | 0   | 0   |     | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
-w~
|     |     | 0   | 0   |     | 0   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
I
|     |     |     | 0   |     | 0   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
m
|     |     | 0   | 0   |     | 0      |     |     |     |
| --- | --- | --- | --- | --- | ------ | --- | --- | --- |
|     | +   |     | I   |     | ii(t)  |     |     |     |
|     |     | 0   |     |     | 0      |     |     |     |
mro
|     |     | 0   | 0   |     | 0   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
I
|     |     | 0   | 0   |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
mro

|     |     |     |     |     |     | 2.5  Examples  | 25  |
| --- | --- | --- | --- | --- | --- | -------------- | --- |
|     | 0   | 0   | 0   | 0   | 0   |                |     |
I
|        | 0  0  |     | 0   | 0   | 0   |        |         |
| ------ | ----- | --- | --- | --- | --- | ------ | ------- |
| y(t)=  |       |     |     |     |     | x(t )  | (2.29)  |
|        | 0  0  | 0   | 0   |     | 0   |        |         |
This six-dimensional state equation describes the system. In this equation. A, B. and C happen
to be constant. lf the orbit is an elliptic one. then they will be time varying. We note that the
three matrices are all block diagonal. Thus the equation can be decomposed into two uncoupled
e,
parts. one involving rand  the other 4>. Studying these two parts independently can simplify
analysis and design.
EXAMPLE 2.10  In chemical plants, it is often necessary to maintain the levels of liquids. A
simplified model of a connection of two tanks is shown in Fig. 2.14. It is assumed that under
normal operation. the inflows and outflows of both tanks all equal Q and their liquid levels
equal HI and H2. Let 1I  be inflow perturbation of the first tank, which will cause variations
in liquid level XI  and outflow YI  as shown. These variations will cause level variation X2 and
outflow variation Y in the second tank. It is assumed that
|     |     | XI  | -X2  |            | Xo  |     |     |
| --- | --- | --- | ---- | ---------- | --- | --- | --- |
|     |     |     |      | and  Y =-  |     |     |     |
YI  =
R2
where R are the flow resistances and depend on the normal height HI and H2. They can also
j
be controlled by the valves. Changes of liquid levels are governed by
| AI dXI =  | (u - | yd dt  | and  | A2 dX2 =  |     | y) dt  |     |
| --------- | ---- | ------ | ---- | --------- | --- | ------ | --- |
(YI -
where Aj are the cross sections of the tanks. From these equations. we can readily obtain
|     |     |     | U   | XI - X2  |     |     |     |
| --- | --- | --- | --- | -------- | --- | --- | --- |
-
XI
|     |     |     | Al       | AIRI  |     |     |     |
| --- | --- | --- | -------- | ----- | --- | --- | --- |
|     |     | Xl  | XI  -X1  | X2    |     |     |     |
|     |     | =   |          | - --  |     |     |     |
|     |     |     | A2RI     | A2R2  |     |     |     |
Thus the state-space description of the system is given by
[::~]  [~~~~~~2
=
Y = [0
I/R21x
--
Figure 2.14  Hydraulic
tanks.  Q +11
- - T
|     |     | -------- ---- | .-  |     |     |     |     |
| --- | --- | ------------- | --- | --- | --- | --- | --- |
--
HI +XI
Al
Q +)"1

26 MATHEMATICAL DESCRIPTIONS OF SYSTEMS
Its transfer function can be computed as
. I
g(s) == ,
+ + + +
AIA2RIR2S- (AIRI AIR2 A2R2)s I
2.5.1 RLC networks
In RLC networks, capacitors and inductors can store energy and are associated with state
variables. If a capacitor voltage is assigned as a state variable x, then its current is C X, where
C is its capacitance. If an inductor current is assigned as a state variable x, then its voltage is
Lx, where L is its inductance. Note that resistors are memoryless elements, and their currents
or voltages should not be assigned as state variables. For most simple RLC networks, once
state variables are assigned, their state eq~ations can be developed by applying Kirchhoff's
current and voltage laws, as the next example illustrates.
EXAMPLE 2.11 Consider the network shown in Fig. 2.15. We assign the Ci-capacitor voltages
as Xi, i == 1,2 and the inductor current as X3. It is important to specify their polarities. Then
their currents and voltage are, respectively, CIXIo C2X2, and LX3 with the polarities shown.
f' From the figure, we see that the voltage across the resistor is u - XI with the polarity shown.
Thus its current is (u - xdl R. Applying Kirchhoff's current law at node A yields C2X2 == X3;
at node B it yields
i
~
I
Thus we have
X . I == -- XI - - - X3 + -U- I
RCI C
I
RCI
I
I
X2 == -X3 I
C
2
Appling Kirchhoff's voltage law to the right-hand-side loop yields LX3 == XI - X2 or I
~
The output y is given by
y == LX3 == XI - X2
Figure 2.15 Network.
R + B
+
XI

2.5 Examples 27
They can be combined in matrix form as
o
-I/C,] [IIRCI]
o I/C2 x + 0 u
-IlL o 0
+ o·
y = [I - I O]x u
This three-dimensional state equation describes the network shown in Fig. 2.15.
The procedure used in the preceding example can be employed to develop state equations
to describe simple RLC networks. The procedure is fairly simple: assign state variables and
then use branch characteristics and Kirchhoff's laws to develop state equations. The procedure
can be stated more systematically by using graph concepts, as we will introduce next. The
procedure and subsequent Example 2.12, however, can be skipped without loss of continuity.
First we introduce briefly the concepts of tree, link, and cutset of a network. We consider
only connected networks. Every capacitor, inductor, 'resistor, voltage source, and current source
will be considered as a branch. Branches are connected at· nodes. Thus a network can be
considered to consist of only branches and nodes. A 'loop is a connection of branches starting
from one point and coming back to the same point without passing any point twice. The
algebraic sum of all voltages along every loop is zero (Kirchhoff's voltage law). The set of all
branches connect to a node is called a cutset. More generally, a cutset of a connected network
is any minimal set of branches so that the removal of 't he set causes the remaining network
to be unconnected. For example, removing all branches connected to a node leaves the node
unconnected to the remaining network. The algebraic sum of all branch currents in every
cutset is zero (Kirchhoff's current law).
A tree of a network is defined as any connection of branches connecting all the nodes but
containing no loops. A branch is called a tree branch if it is in the tree, a link if it is not. With
respect to a chosen tree, every link has a unique loop, called the fundamental loop, in which
the remaining loop branches are all tree branches. Every tree branch has a unique cutset, called
the fundamental cutset, in which the remaining cutset branches are all links. In other words, a
fundamental loop contains only one link and a fundamental cutset contains only one tree branch.
~ Procedure for developing state-space equations'
1. Consider an RLC network. We first choose a normal tree. The branches of the normal
tree are chosen in the order of voltage sources, capacitors, resistors, inductors, and current
sources.
2. Assign the capacitor voltages in the normal tree and the inductor currents in the links as
state variables. Capacitor voltages in the links and inductor currents in the normal tree are
not assigned.
3. Express the voltage and current of every branch in terms of the state variables and,
if necessary, the inputs by applying Kirchhoff's voltage law to fundamental loops and
Kirchhoff's current law to fundamental cutsets.
4. The reader may skip this procedure and go directly to Example 2.13,

28 MATHEMATICAL DESCRIPTIONS OF SYSTEMS
4. Apply Kirchhoff's voltage or current law to the fundamental loop or cutset of every branch
that is assigned as a state variable.
EXAMPLE 2.12 Consider the network shown in Fig. 2.16. The normal tree is chosen as shown
with heavy lines; it consists of the voltage source, two capacitors, and the I-Q resistor. The
capacitor voltages in the normal tree and the inductor current in the link will be assigned as
state variables. If the voltage across the 3-F capacitor is assigned as XI, then its current is 3.tl.
The voltage across the I-F capacitor is assigned as X2 and its current is X2. The current through
the 2-H inductor is assigned as X3 and its voltage is 2X3. Because the 2-Q resistor is a link. we
use its fundamental loop to find its voltage as UI - XI. Thus its current is (UI - xI)/2. The
\-Q resistor is a tree branch. We use its fundamental cutset to find its current as X3. Thus its
=
voltage is I . X3 X3. This completes Stel? 3.
The 3-F capacitor is a tree branch and its fundamental cutset is as shown. The algebraic
sum of the cutset currents is 0 or
which implies
. = I. I + I + I
XI -;;.\1 - )X3 ;;UI ,)uz
The I-F capacitor is a tree branch, and from its fundamental cutset we have X2 - X3 = 0 or
The 2-H inductor is a link. The voltage along its fundamental loop is 2X3 + X3 - XI + X2 = 0
or
Fundamental
cutset of @
Fundamental
cutset of Q)
(UI - '<1)/2 I /
Y2 I
,-_ .... / //J / +
211 ,
,
-1+. ...
2H
a / J ,. :.." o .x · i , : - -1 Y'I -
Fundamenr~
(volta_ge I cutset of ~
source) L..--__. ...;:::...IL.. ___. .J....., __ " 'A"-..._ ..; X _ 3 ___- -'_
~l,~~
- 1+
Figure 2.16 Network with two inputs.

|     |     |     |     |     |     |     |     |     |     |     |     | 2.5  Examples  | 29  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | -------------- | --- |
They can be expressed in matrix form as
°
|     |     |     |     |     |     | °   |     |     |     |     |     |     | (2.30)  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------- |
2-n
If we consider the voltage across the 2-H inductor and the current through the  resistor as
the outputs. then we have
|     |     |     |     | y, =  | 2X3 = X, - |     | X2 - | X3  =  | [I  - | 1  - | l)x  |     |     |
| --- | --- | --- | --- | ----- | ---------- | --- | ---- | ------ | ----- | ---- | ---- | --- | --- |
and
°
|     |     |     |     | Y2  = 0.5(u, - |     | xi! := [-0.5  |     |     | O]x + [0.5  |     | O)u  |     |     |
| --- | --- | --- | --- | -------------- | --- | ------------- | --- | --- | ----------- | --- | ---- | --- | --- |
They can be written in matrix form as
-I  °
|     |     |     |     |        | -~.5  |     | -I]  |     | [00]  |     |     |     | (2.31 )  |
| --- | --- | --- | --- | ------ | ----- | --- | ---- | --- | ----- | --- | --- | --- | -------- |
|     |     |     |     | y:= [  |       | o   |      |     | +     |     |     |     |          |
|     |     |     |     |        |       |     |      | x   | 0.5   | 0   | u   |     |          |
Equations (2.30) and (2.31) are the state-space description of the network.
The transfer matrix of the network can be computed directly from the network or using
the formula in (2.16):
We will use MATLAB to compute this equation. We type
1
|      | a=[-1/        | 5   | 0        |               | 0  1;0.5       | -0.5  | -:  | .S];b= | [1/ | 6   | 0;0  |       |     |
| ---- | ------------- | --- | -------- | ------------- | -------------- | ----- | --- | ------ | --- | --- | ---- | ----- | --- |
|      |               |     | -1/      | 3;0           |                |       |     |        |     | 1/  | 3;G  | 0; ;  |     |
| .'~  | c=[l          | -1  | -1;-0.5  | 0             | O];d=[O 0;0.5  |       |     | 0];    |     |     |      |       |     |
| ,    | [N:,dl]=ss2tf |     |          | (a, b,c,d,1)  |                |       |     |        |     |     |      |       |     |
,";I
·1
: ~
.~   which yields
i
~.~
N-
| .~   | ~=  |     |     |         |     |         |          |     |          |     |     |     |     |
| ---- | --- | --- | --- | ------- | --- | ------- | -------- | --- | -------- | --- | --- | --- | --- |
| .1I  |     |     |     | 0.0000  |     | 0.1667  | -0.0000  |     | -0.0000  |     |     |     |     |
1
|     |     |     |     | 0.5000  |     | 0.2500  |     | 0.3333  | -0.0000  |     |     |     |     |
| --- | --- | --- | --- | ------- | --- | ------- | --- | ------- | -------- | --- | --- | --- | --- |
"~
.j
j
-"' ;'
|     |     |     |     |     | 1.0000  | 0.6667  |     | 0.7500  | 0.0833  |     |     |     |     |
| --- | --- | --- | --- | --- | ------- | ------- | --- | ------- | ------- | --- | --- | --- | --- |
This is the first column of the transfer matrix. We repeat the computation for the second input.
| Thus the transfer matrix of the network is  |     |     |     |     |     |     |     |     |     |     |     |     | 1   |
| ------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
0.1667s2
0.3333s"
|     |          |     |        |                  |           |          |        |            | +            |     | +                 | + 0.0833  |     |
| --- | -------- | --- | ------ | ---------------- | --------- | -------- | ------ | ---------- | ------------ | --- | ----------------- | --------- | --- |
|     | (;(s):=  |     | s3  +  | 0.~667s" \0.75s  |           | + 0.083  |        | s3         | 0.6667s'     |     | 0.75s             |           |     |
|     |          |     |        | +                |           | +        |        | -0.1667s2  |              |     |                   |           |     |
|     |          | [   | 0.5s   |                  | 0.25s     | 0.3333s  |        |            |              | -   | 0.0833s -         | 0.0833    |     |
|     |          |     | S3  +  | 0.6667s'         | +  0.75s  | +        | 0.083  | s3         | +  0.6667s'  |     | + 0.75s + 0.0833  |           |     |

1
30  MATHEMATICAL DESCRIPTIONS OF SYSTEMS
I
I
EXAMPLE 2.13  Consider the network shown in Fig. 2.l7(a), where T is a tunnel diode with
i
the characteristics shown in Fig. 2.l7(b). Let Xl be the voltage across the capacitor and X2 be
i
the current through the inductor. Then we have u = Xl
and
|     |        | =  +          | =                |     |     |     |
| --- | ------ | ------------- | ---------------- | --- | --- | --- |
|     | X2(t)  | CXI(t)  i(t)  | CXI(t) +h(xl(t»  |     |     |     |
=
|     | LX 2(t)  | E - RX2(t) - | XI (I)  |     |     |     |
| --- | -------- | ------------ | ------- | --- | --- | --- |
They can be arranged as
~
t
.  -h(xi (I)) +X2c(t)
=
|     |     | XI(t)  C  |     |     |     |     |
| --- | --- | --------- | --- | --- | --- | --- |
(2.32)
|     |     | .  -XI(t) - | RX2(t)  | E   |     |     |
| --- | --- | ----------- | ------- | --- | --- | --- |
|     |     | xo(l) =     |         | + - |     |     |
|     |     | - ILL       |         |     |     |     |
I
This set of nonlinear equations describes the network. Now if XI (t) is known to lie only inside
=
the range (a, b) shown in Fig. 2.l7(b), then h(XI(I»  can be approximated by h(xI(t»
XI (1)/ RI. In this case, the network can be reduced to the one in  Fig. 2.17(c) and can be
described by
|     |     | l/C   | ]     | [0] E  |     |     |
| --- | --- | ----- | ----- | ------ | --- | --- |
|     |     |       | [XI]  | +      |     |     |
|     |     | -R/L  |       | l/L    |     |     |
X2
-,
Fl-
Lx!
-IIR,
|     | L  x,  |     |     | i = h(v)  |     |     |
| --- | ------ | --- | --- | --------- | --- | --- |
-T
+
RX'R
F
~
|     | x,  | v  T  |     |     |     |     |
| --- | --- | ----- | --- | --- | --- | --- |
- V
|         | L    |     |     |     | c   |     |
| ------- | ---- | --- | --- | --- | --- | --- |
| E -=..  | Cx,  |     |     |     | Vo  | d   |
L
(0)
(a)
|     | L  x,  |     |     | L   |     |     |
| --- | ------ | --- | --- | --- | --- | --- |
|     |        | r   |     |     | X2  |     |
y  yy
1+
R~
| R   |     |     | :   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
K
t+
|     | x,  |        |     |     | X,  C;:r:  | -R'!,  |
| --- | --- | ------ | --- | --- | ---------- | ------ |
|     |     | v  R,  | fE  |     |            | t'     |
t
| E-=..  | L   |     |     |     |     |     |
| ------ | --- | --- | --- | --- | --- | --- |
L
|     | (c)  |     |     |     | (d)  |     |
| --- | ---- | --- | --- | --- | ---- | --- |
Figure 2.17
Network with a tunnel diode.

2.6 Discrete-Time Systems 31
This is an LTI state-space equation. Now if XI (I) is known to lie only inside the range (c, d)
shown in Fig. 2.l7(b). we may intro X d I uce the variables Xl (t) = XI (t) - v o, andx2(t) = X2 (I) -i o
and approximate h(XI (t» as io - (tl/ R2. Substituting these into (2.32) yields
[I/C I/C] [0]-
.rI] [XI]
[
R2
X2 = -I/L -R/L X2 + I/L E
, .~
'j where E = E - Va - Rio. This equation is obtained by shifting the operating point from (0. 0)
J
"".. to (vo, io) and by linearization_at (vo, io)' Because the two linearized equations are identical
if - Rz is replaced by RI and E by E, we can readily obtain its equivalent network shown in
Fig. 2.17(d). Note that it is not obvious how to obtain the equivalent network from the original
network without first developing the state equation.
2.6 Discrete-Time Systems
This section develops the discrete counterpart of continuous-time systems. Because most
concepts in continuous-time systems can be applied directly to the discrete-time systems,
the discussion will be brief.
The input and output of every discrete-time system will be assumed to have the same
sampling period T and will be denoted by u[k] := u(kT), y[k]:= y(kT), where k is an integer
ranging from to +Xl. A discrete-time system is causal if current output depends on current
-()C
and past inputs. The state at time ko, denoted by x[ko], is the infonnation at time instant ko,
which together with u[k]. k :::: ko, detennines uniquely the output y[kJ, k :::: ko. The entries of
x are called state variables. If the number of state variables is finite, the discrete-time system
is lumped; otherwise. it is distributed. Every continuous-time system involving time delay,
as the ones in Examples 2.1 and 2.3, is a distributed system. In a discrete-time system, if the
time delay is an integer multiple of the sampling period T, then the discrete-time system is a
lumped system.
A discrete-time system is linear if the additivity and homogeneity properties hold. The
response of every linear discrete-time system can be decomposed as
Response = zero-state response + ~ero-input response
and the zero-state responses satisfy the superposition property. So do the zero-input responses.
Input~utput description Let a[k] be the impulse sequence defined as
ifk = m
a[k - mJ = { ~
if k f= m
where both k and III are integers. denoting sampling instants. It is the discrete counterpart of
a a
the impulse (t - til· The impulse (I - II) has zero width and infinite height and cannot be
generated in practice: whereas the impulse sequence o[k - m] can easily be generated. Let
u[kJ be any input sequence. Then it can be expressed as
L00
u[k] = u[m]8[k - ml
m=-oo
Let g[k, IIll be the output at time instant k excited by the impulse sequence applied at time
instant Then we have
Ill.

32  MATHEMATICAL DESCRIPTIONS OF SYSTEMS
o[k - mJ -4 g[k. mJ
| o[k -  | mJu[m] -4 g[k. mJu[m]  | (homogeneity)  |     |     |
| ------ | ---------------------- | -------------- | --- | --- |
| I)(k - | mJu[mJ-4 Lg[k. m]u[m]  | (additivity)   |     |     |
m
m
Thus the output y[k] excited by the input u[kJ equals
00
|     | y[k] =  L  | g[k. mJu[mJ  |     | (2.33)  |
| --- | ---------- | ------------ | --- | ------- |
m=-:JQ
This is the discrete counterpart of (2.3) and its derivation is considerably simpler. The sequence
g[k. mJ is called the impulse respo/lSe sequence.
If a discrete-time system is causal, no output will appear before an input is applied. Thus
we have
Causal ~ g[k. mJ = 0,
for k < m
If a system is rela'led at ko and causal, then (2.33) can be reduced to
k
|     | y[kJ =  L  | g[k, mJu[m]  |     | (2.34)  |
| --- | ---------- | ------------ | --- | ------- |
m=ko
as in (2.4).
If a linear discrete-time system is time invariant as well, then the time shifting property
=
holds. In this case. the initial time instant can always be chosen as ko  0 and (2.34) becomes
|     | k   | k   |     |     |
| --- | --- | --- | --- | --- |
=
| y[kJ  | L  g[k - mJu[ml =  | L  g[mJu[k - | mJ  | (2.35)  |
| ----- | ------------------ | ------------ | --- | ------- |
|       | m=O                | m=O          |     |         |
This is the discrete counterpart of (2.8) and is called a discrete convolution.
The z-transform is an important tool in the study of LTI discrete-time systems. Let .v(z)
be the z-transform of y[kJ defined as
oc
(2.36)
y(z) := Z[y[kJJ := Ly[klz-k
k~O
We first replace the upper limit of the integration in (2.35) to oo.s and then substitute it into
(2.36) to yield
f (t
| Hz) =  | g[k - | mlll[m z-<k-m1z -m  |     |     |
| ------ | ----- | ------------------- | --- | --- |
J)
k~O \;~o
t (tg[k -
=
mJz-<k-':'l) u[mJz-m
| m~O  | k=O  |     |     |     |
| ---- | ---- | --- | --- | --- |
| (f   |      | (f  |     |     |
1
| =   | g[lJZ- | u[mlz-m) =: g(z)u(z)  |     |     |
| --- | ------ | --------------------- | --- | --- |
)
|     | I~O  | m~O  |     |     |
| --- | ---- | ---- | --- | --- |
5. This is permitted under the causality assumption.

2.6 Discrete-Time Systems 33
where we have interchanged the order of summations. introduced the new variable I = k - Ill,
and then used the fact that g[l] = 0 for I < 0 to make the inner summation independent of 11l.
The equation
.v(z) = g(~)il(z) (2.37)
is the discrete counterpart of(2.1O). The function g(z) is the z-transfonn of the impulse response
sequence g[k] and is called the discrete transfer function. Both the discrete convolution and
transfer function describe only zero-state responses.
EXAMPLE 2.14 Consider the unit-sampling-time delay system defined by
y[k] = u[k - I]
The output equals the input delayed by one sampling period. Its impulse response sequence is
=
g[k] 8[k - I] and its discrete transfer function is
g(z) = Z[8[k - III = Z-I = ~
It is a rational function of ;:. Note that every continuous-time system involving time delay is a
distributed system. This is not so in discrete-time systems.
EXAMPLE 2.15 Consider the discrete-time feedback system shown in Fig. 2.18(a). It is the
discrete counterpart of Fig. 2.5(a). If the unit-sampling-time delay element is replaced by its
:-1.
transfer function then the block diagram becomes the one in Fig. 2.l8(b) and the transfer
function from r to ." can be computed as
a"-I a
g(z) = I - -1-
- az Z - a
z
This is a rational function of and is similar to (2.12). The transfer function ~an also be
obtained by applying the ~-transform to the impulse response sequence of the feedback system.
As in (2.9). the impulse response sequence is
:x;
gf[k] = a8[k - I] + a 2 8[k - 2] + ... = I:>m8[k - m]
m=l
The z-transform of S[k - III] is z-m. Thus the transfer function of the feedback system is
":x;c
= az - 1 L -I)," =
a~
which yields the same result.
The discrete transfer functions in the preceding two examples are all rational functions
of z. This may not be so in general. For example, if
for m ~ 0
=
for k 1,2 ... ,

34
MATHEMATICAL DESCRIPTIONS OF SYSTEMS
|       | +   |     |     |     | y[kJ  |       | +   |     |      |
| ----- | --- | --- | --- | --- | ----- | ----- | --- | --- | ---- |
| r[k)  |     |     |     |     |       | r[~J  |     |     | HzJ  |
Unit-time  _-1
delay
|              |                                 | (a)  |     |     |     |     |     | (b)  |     |
| ------------ | ------------------------------- | ---- | --- | --- | --- | --- | --- | ---- | --- |
| Figure 2.18  | Discrete-time feedback system.  |      |     |     |     |     |     |      |     |
Then we have
|     |     |         |       |     | I                   |     |        |          | I   |
| --- | --- | ------- | ----- | --- | ------------------- | --- | ------ | -------- | --- |
|     |     | A (  )  | -1 +  |     |  + ; -3 + ... =     |     | I  (1  |          |     |
|     |     | g   Z   | =  Z  | 2 1 | :   Z  -, - 3 1  Z  |     | - n    | - z- 1)  |     |
z.
It is an irrational function of  Such a system is a distributed system. We study in this text only  1
t
lumped discrete-time systems and their discrete transfer functions are all rational functions
| of z.  |     |     |     |     |     |     |     |     | r   |
| ------ | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Discrete rational transfer functions can be proper or improper. If a transfer function is
=
| improper such as g(z)  |     |     | + 2z - |     | 1)/(z - 0.5), then  |     |     |     |     |
| ---------------------- | --- | --- | ------ | --- | ------------------- | --- | --- | --- | --- |
(Z2
|     |     |     |     |       | Hz)  +  |      |     |     |     |
| --- | --- | --- | --- | ----- | ------- | ---- | --- | --- | --- |
|     |     |     |     |       | ;:2     | 2z - | 1   |     |     |
|     |     |     |     | u(z)  | Z -     | 0.5  |     |     |     |
which implies
|     |     | +    |      |          | =  +  | +   | +          |       |     |
| --- | --- | ---- | ---- | -------- | ----- | --- | ---------- | ----- | --- |
|     |     | y[k  | 1] - | 0.5y[k]  | u[k   | 2]  | 2u[k  1] - | u[k]  |     |
or
|     |     | + 1]  | =   |          | +  + 2] +  |     | + 1] - |       |     |
| --- | --- | ----- | --- | -------- | ---------- | --- | ------ | ----- | --- |
|     |     | y[k   |     | 0.5y[k]  | u[k        |     | 2u[k   | u[k]  |     |
|     |     |       |     |          | +          |     |        | +     |     |
It means that the output at time instant k  I depends on the input at time ins!ant k  2,
a future input. Thus a discrete-time system described by an  improper transfer function is
not causal. We study only causal systems. Thus all discrete rational transfer functions will
be proper. We mentioned earlier that we also study only proper rational transfer functions
of s in the continuous-time case. The reason, however, is different. Consider g(s)  =  s or
y(t) = du(t)/dt. It is a pure differentiator. If we define the differenliation as
+
|     |     |     |     | du(t)  | .                         | u(t  | 6) - u(t)  |     |     |
| --- | --- | --- | --- | ------ | ------------------------- | ---- | ---------- | --- | --- |
|     |     |     |     | = --   | =  hm ~--..:.-...:....:.  |      |            |     |     |
v(t)
|     |     |     | •   | dt  |     |     | 6   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
t>~O
+
where 6> 0, then the output yet) depends on future input u(t  6) and the differentiator is
not causal. However, if we define the differentiation as
|     |     |     |          | du(t)  | .                    | u(t) - | u(t - 6)  |     |     |
| --- | --- | --- | -------- | ------ | -------------------- | ------ | --------- | --- | --- |
|     |     |     | v (t) =  |        | =                    |        |           |     |     |
|     |     |     |          | --     | hm -'--'----''----'- |        |           |     |     |
|     |     |     | .        | dt     |                      |        | 6         |     |     |
t>~O
then the output yet) does not depend on future input and the differentiator is causal. Therefore
in continuous-time systems, it is open to argument whether an improper transfer function
represents a noncausal system. However, improper transfer functions of s will amplify high-

|     |     |     |     |     |     | 2.6  Discrete-Time Systems  |     | 35  |
| --- | --- | --- | --- | --- | --- | --------------------------- | --- | --- |
frequency noise, which often exists in the real world. Therefore improper transfer functions
are avoided in practice.
State-space equations  Every linear lumped discrete-time system can be described by
|     |     |      | +              |     | +         |     |     |     |
| --- | --- | ---- | -------------- | --- | --------- | --- | --- | --- |
|     |     | x[k  | I] = A[k]x[k]  |     | B[k]u[k]  |     |     |     |
(2.38)
+
|     |     |     | y[k] =  | C[k]x[k]  | D[k]u[k]  |     |     |     |
| --- | --- | --- | ------- | --------- | --------- | --- | --- | --- |
e,
where A, B,  and D are functions of k. If the system is time invariant as well, then (2.38)
becomes
|     |     | x[k +  | 1] = Ax[k] + Bu[k]  |     |     |     |     |     |
| --- | --- | ------ | ------------------- | --- | --- | --- | --- | --- |
(2.39)
=
|     |     |     | y[k]  | ex[k]  | +  Du[k]  |     |     |     |
| --- | --- | --- | ----- | ------ | --------- | --- | --- | --- |
where A, B. e, and D are constant matrices. Let x(.:) be the z-transform of x[k] or
Loc
|     |     | x(z) =  | Z[x[k]] :=  |     | x[k]Z-k  |     |     |     |
| --- | --- | ------- | ----------- | --- | -------- | --- | --- | --- |
k=O
Then we have
|        |        | L   |                 |     | Loc   |            |     |     |
| ------ | ------ | --- | --------------- | --- | ----- | ---------- | --- | --- |
|        | +      |     | +               |     |       | +          |     |     |
| Z[x[k  | I]] =  |     | x[k  I]z-k = z  |     | x[k   | I]Z-(k+l)  |     |     |
[f
|     |     | =   |          | +      |        |            |        |     |
| --- | --- | --- | -------- | ------ | ------ | ---------- | ------ | --- |
|     |     | z   | x[l]z-I  | x[O] - | X[O]]  | = z(x(z) - | x[O])  |     |
i=l
Applying the z-transform to (2.39) yields
|     |     | zx(z) - | zx[O] = Ax(z)    |     | +  Bil(.:)  |     |     |     |
| --- | --- | ------- | ---------------- | --- | ----------- | --- | --- | --- |
|     |     |         | Yez) = ex(.:) +  |     | Dil(z)      |     |     |     |
which implies
=
|     | x(.:)  (zl - | A)-IZX[O]  |     | +  (d - | A)-IBil(z)  |     |     | (2.40)  |
| --- | ------------ | ---------- | --- | ------- | ----------- | --- | --- | ------- |
y(z) =  e(zI - A)-IZX[O] + C(zl - A)-IBil(z) + Dil(z)  (2.41 )
They are the discrete counterparts of (2.14) and (2.15). Note that there is an extra.: in front of
x[O]. Ifx[O] =  0, then (2.41) reduces to
|     |     | y(z)  | =  [C(zl - | A)-IB  | +  D]il(.:)  |     |     | (2.42)  |
| --- | --- | ----- | ---------- | ------ | ------------ | --- | --- | ------- |
Comparing this with the MIMO case of (2.37) yields
=
|     |     | G(.:)  | C(zl - | A)-IB  | +   | D   |     | (2.43)  |
| --- | --- | ------ | ------ | ------ | --- | --- | --- | ------- |
This is the discrete counterpart of (2.16). If the Laplace transform variable s is replaced by the
z-transform variable z, then the two equations are identical.

36  MATHEMATICAL DESCRIPTIONS OF SYSTEMS
EXAMPLE 2.16  Consider a money market account in a brokerage finn. If the interest rate
depends on the amount of money in the account. it is a nonlinear system. If the interest rate is
the same no matter how much money is in the account, then it is a linear system. The account
is a time-varying system if the interest rate changes with time: a time-invariant system if the
interest rate is fixed. We consider here only the LTI case with interest rate r = 0.OI5'!c per day
and compounded daily. The input u [k] is the amount of money deposited into the account on
the kth day and the output y[k] is the total amount of money in the account at the end of the
kth day. If we withdraw money, then lI[k] is negative.
If we deposit one dollar on the  first day (that is,  II[OJ  =  I) and nothing thereafter
| =   | =   |     |     |     |     |     |     | =   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
(u[k]  O.  k  I.  2. ... ). then y(01  =  u[OJ  =  I andv[l] =  1+ 0.00015  1.00015.
Because the muney is compounded daily, we have
|     | y[2] = y[IJ +  |     | y[I]· 0.00015 = .1[1]· 1.00015 =  |     |     |     | (100015)~  |     |     |
| --- | -------------- | --- | --------------------------------- | --- | --- | --- | ---------- | --- | --- |
I
and, in general,
=
|     |     |     |     | y[k]  | (I.OOO15l  |     |     |     |     |
| --- | --- | --- | --- | ----- | ---------- | --- | --- | --- | --- |
Because the input {I, O.  0, ... J is an impulse sequence, the output is. by definition, the impulse
response sequence or
|     |     |     |     | g[kJ =  | (1.00015/  |     |     |     |     |
| --- | --- | --- | --- | ------- | ---------- | --- | --- | --- | --- |
and the inpuH'lutput description of the account is
|     |         |     | k        |           |              | k   |          |     |         |
| --- | ------- | --- | -------- | --------- | ------------ | --- | -------- | --- | ------- |
|     | y[k] =  |     | L  g[k - | m]u[m] =  | L(1.00015l-m |     | ll[lIl]  |     | (2.44)  |
|     |         |     | m=O      |           | m=O          |     |          |     |         |
The discrete transfer function is the z-transfonn of the impulse response sequence or
|     | g(z)  | =           | =  L        | (100015/z-k  |              | =           |     | l   |          |
| --- | ----- | ----------- | ----------- | ------------ | ------------ | ----------- | --- | --- | -------- |
|     |       | Z[g(kll     |             |              |              | L(I·OOOI5z- |     | )k  |          |
|     |       |             | k=O         |              |              | k=O         |     |     |          |
|     |       | =           |             |              |              |             |     |     | (2.45 )  |
|     |       | ----~----7- |             |              | ----~~~      |             |     |     |          |
|     |       | 1 -         | 1.00015z-1  |              | Z - 1.00015  |             |     |     |          |
Whenever we use (2.44) or (2.45), the initial state must be zero, or there is initially no money
in the account.
Next we develop a state-space equation to describe the account. Suppose y[kJ is the tot:.!1
amount of money at the end of the kth day. Then we have
|      | +          |     | + 0.00015y[k] +  |     | +     |                    |     | +  +      |          |
| ---- | ---------- | --- | ---------------- | --- | ----- | ------------------ | --- | --------- | -------- |
| y[k  | I] = y[k]  |     |                  |     | lI[k  | I] =  l.oool5y[kJ  |     | lI[k  IJ  | (2.46 )  |
If we define the state variable as x[k] := v[kJ, then
|     |     |     | +        | =           |     | +  +  |     |     |     |
| --- | --- | --- | -------- | ----------- | --- | ----- | --- | --- | --- |
|     |     |     | x[k  I]  | lOOOI5x[k]  |     | lI[k  | I]  |     |     |
(2.4 7)
=
|     |     |     | y[kJ  | x[kJ  |     |     |     |     |     |
| --- | --- | --- | ----- | ----- | --- | --- | --- | --- | --- |
+
Because of lI[k  I], (2.47)  is  not in the standard form of (2.39). Thus we cannot select
x[k] := y[kJ as a state variable. Next we select a different state variable as

Concluding Remarks
2.7  37
|     |     |     | x[k] := y[k] - | u[k]  |     |
| --- | --- | --- | -------------- | ----- | --- |
|     | ,+  | =   |                | =     |     |
Substituting y[k  I]  x[k +  I] + !I[k +  I] and y[k]  x[k] + II[k] into (2.46) yields
~.
|     |     | +          |              | +            |     |
| --- | --- | ---------- | ------------ | ------------ | --- |
|     |     | x[k  I] =  | 1.00015x[k]  | I.OOOI5u[k]  |     |
(2.48)
| •.  |     | y[k] = x[k]  | +  u[k]  |     |     |
| --- | --- | ------------ | -------- | --- | --- |
;
This is in the standard form and describes the money market account.
The linearization discussed for the continuous-time case can also be applied to the discrete
time case with only slight modification. Therefore its discussion will not be repeated.
2.7  Concluding Remarks
We introduced in this chapter the concepts of causality, lumpedness. linearity. and time invari
ance. Mathematical equations were then developed to describe causal systems. as summarized
in the following.
|     | System type  | Internal description  |     | External description  |     |
| --- | ------------ | --------------------- | --- | --------------------- | --- |
J'
=
|     | Distributed. linear  |     |     | y(t)  G(t. r)u(r) dr  |     |
| --- | -------------------- | --- | --- | --------------------- | --- |
'"
|     | Lumped. linear  | x = A(t)x + B(t)u  |     |                       |     |
| --- | --------------- | ------------------ | --- | --------------------- | --- |
|     |                 |                    |     | y(t)= J: Gu.r)U(r)dr  |     |
|     |                 | y = C(t)x          | +   |                       |     |
D(t)u
1,'
|     | Distributed. linear.  |     |     | =           | r)u(r) dr  |
| --- | --------------------- | --- | --- | ----------- | ---------- |
|     |                       |     |     | yet)  G(t - |            |
|     | time-invariant        |     |     | ()          |            |
y(s)  =  {;(s)u(s). (;(s) irrational
l'
|     |                  | x        |     | =           |            |
| --- | ---------------- | -------- | --- | ----------- | ---------- |
|     | Lumped. linear.  | = Ax+Bu  |     | y(t)  G(t - | r)u(r) dr  |
time-invariant
=
|     |     | y = Cx +Du  |     | Yes)  {;(S)U(S). {;(s) rational  |     |
| --- | --- | ----------- | --- | -------------------------------- | --- |
Distributed systems cannot be described by finite-dimensional state-space equations. External
description describes only zero-state responses; thus whenever we use the description. systems
are implicitly assumed to be relaxed or their initial conditions are assumed to be zero.
We  study in  this text  mainly lumped linear time-invariant systems. For this class of
systems. we use mostly the time-domain description (A. B. C. D) in the internal description
and the frequency-domain  (Laplace-domain) description G(s) in  the external description.
Furthermore. we will express every rational transfer matrix as a fraction of two polynomial
matrices, as we will develop in the text. By so doing, all designs in the SISO case can be
extended to the multi variable case.

r
38 MATHEMATICAL DESCRIPTIONS OF SYSTEMS
The class of lumped linear time-invariant systems constitutes only a very small part of
nonlinear and linear systems. For this small class of systems, we are able to give a complete
treatment of analyses and syntheses. This study will form a foundation for studying more
general systems.
2.1 Consider the memoryless systems with characteristics shown in Fig. 2.19, in which u
denotes the input and y the output. Which of them is a linear system? Is it possible to
introduce a new output so that the system in Fig. 2.l9(b) is linear?
y y y
t
r Yo
-----,,j.<::=-----,,
o --~"-+o- ---_u ----.,jL- o - ----+ll
(a) (b) (c)
Figure 2.19
2.2 The impulse response of an ideallowpass filter is given by
ge sin 2w(t - to)
t) - 2w---'-------"-
2w(t - to)
for all t, where wand to are constants. Is the ideallowpass filter causal? Is it possible to
build the filter in the real world?
2.3 Consider a system whose input u and output yare related by
y(t) = (Pau)(t) := {u(t) for t ~ a
o
fort> a
where a is a fixed constant. The system is called a truncation operator, which chops off
the input after time a. Is the system linear? Is it time-invariant? Is it causa]?
2.4 The input and output of an initially relaxed system can be denoted by Y = H where
11,
H is some mathematical operator. Show that if the system is causal, then
PaY = PaHu = PaHPau
where Pa is the truncation operator defined in Problem 2.3. Is it true Pa H u = H Pa u?
2.5 Consider a system with input u and output y. Three experiments are performed on the
system using the inputs u, (t), U2(t), and U3(t) for t :::: O. In each case, the initial state
x(O) at time t = 0 is the same. The corresponding outputs are denoted by y" Y2, and Y3.
Which of the following statements are correct if x(O) ,p O?

Problems  39
| 1.  1fu) =  | UI +U2, then Y3        | =  YI  +  Y2·  |     |
| ----------- | ---------------------- | -------------- | --- |
|             | =  +                   | =  +           |     |
| 2. If u)    | 0.5(u I  U2), then Y)  | 0.5(YI  Y2).   |     |
| 3.  1fu) =  | UI  - 1/2, then YJ     | =  YI  - Y2.   |     |
Which are correct if x(O) = O?
2.6  Consider a system whose input and output are related by
ifu(t - 1) i' 0
|     | yet) =  | { ~2(t)IU(t - 1)  |     |
| --- | ------- | ----------------- | --- |
if u(t - I) = 0
for all t. Show that the system satisfies the homogeneity property but not the additivity
property.
2.7  Show that if the additivity property holds, then the homogeneity property holds for all
rational numbers ex. Thus if a system has some "continuity" property,  then additivity
implies homogeneity.
2.8  Let g(t. r) = g(t +ex, ,+ex) for alII". and ex. Show that g(t, , ) depends only on t - r.
|                | x  + ,           | ,)Iox                |         |
| -------------- | ---------------- | -------------------- | ------- |
| [Hint: Define  | =  I  and y = t  | and show that ag(t.  | =  0.]  |
- ,
2.9  Consider a system with impulse response as shown in Fig. 2.20(a). What is the zero-state
response excited by the input U(I) shown in Fig. 2.20(b).
u(t)
g(f)
o  o
|     | 2  J  | 4   | 2   |
| --- | ----- | --- | --- |
(a)
-I
(b)
Figure 2.20
2.10  Consider a system described by
y+2y-3y=Li-u
What are the transfer function and the impulse response of the system?
2.11  Let y(l) be the unit-step response of a linear time-invariant system. Show that the impulse
response of the system equals dy(t lid!.
2.12  Consider a two-input and two-output system described by

40  MATHEMATICAL DESCRIPTIONS OF SYSTEMS
where N and DI}  are polynomials of p  := d/dt. What is the transfer matrix of the
ij
system?
2.13  Consider the feedback systems shown in Fig. 2.5. Show that the unit-step responses of
=
the positive-feedback system are as shown in Fig. 2.2l(a) for a
I and in Fig. 2.21(b)
for a = 0.5. Show also that the unit·step responses of the negative-feedback system are
as shown in Figs. 2.2l(c) and 2.2l(d). respectively. for a  =  I and a  =  0.5.
| y(t)  |     |     | -"It)  |     |     |
| ----- | --- | --- | ------ | --- | --- |
6
5
| 4      |          |          | 1       |          |          |
| ------ | -------- | -------- | ------- | -------- | -------- |
| 3      |          | 0=1      | 0.75    |          | a = 0.5  |
| 2      |          |          | 0.5     |          |          |
| 0      | 2  3  4  | 5  6  7  | 0       | 2  3  4  | 5  6  7  |
|        | (al      |          |         | (b)      |          |
| y(t )  |          |          | \'(1 )  |          |          |
0.5
0.25
o
|     | 2345678  |     | 01234567  |     |     |
| --- | -------- | --- | --------- | --- | --- |
- I
|     | (e)  |     |     | \d)  |     |
| --- | ---- | --- | --- | ---- | --- |
Figure 2.21
2.14  Draw an op-amp circuit diagram for
]
|     |     | x = [~2  ~]  | ~4  |     |     |
| --- | --- | ------------ | --- | --- | --- |
x + [
II
|     |     | Y = [3  lO]x - 211  |     |     |     |
| --- | --- | ------------------- | --- | --- | --- |
2.15  Find state equations to describe the pendulum systems in Fig. 2.22. The systems are
|     |     |     |     | e. e\.  | e2  |
| --- | --- | --- | --- | ------- | --- |
useful to model one- or two-link robotic manipulators. If  and  are very small,
can you consider the two systems as linear"
2.16  Consider the simplified model of an aircraft shown in Fig. 2.23. It is assumed that the
|     |     |     | eo.  | elevator angle 110, altitude ho.  |     |
| --- | --- | --- | ---- | --------------------------------- | --- |
aircraft is in an equilibrium state at the pitched angle
|     |     | It  |     | e  and u from  | eo  |
| --- | --- | --- | --- | -------------- | --- |
and cruising speed 1:0.  is assumed that small deviations of  and 110
|     | 11  =  | e  and h  =  |     |     |     |
| --- | ------ | ------------ | --- | --- | --- |
generate forces  k\  k2L1  as shown in the figure. Let m be the mass of
the aircraft. I the moment of inertia about the center of gravity P, be the aerodynamic
damping. and h the deviation of the altitude from 11 0. Find a state equation to describe
the system. Show also that the transfer function from u to h. by neglecting the effect of
I, is
,:
•
i
i

Problems 41
(OJ
figure 2.22
h
"
I,
1----1, ---1.111
figure 2.23
2.17 The soft landing phase of a lunar module descending on the moon can be modeled as
In.
shown in Fig. 2.24. The thrust generated is assumed to be proportional to where m is
=
the mass of the module. Then the system can be described by lIl.i' -klll - mg. where
g is the gravity constant on the lunar surface. Define state variables of the system as
x,
= = .\'. = =
y, X2 X3 m. and II m, Find a state-space equation to describe the system.
2.18 Find the transfer functions from II to )" and from .1', to y of the hydraulic tank system
shown in Fig. 2,25. Does the transfer function from II to y equal the product of the twO
transfer functions? Is this also true for the system shown in Fig. 2.147 [rlnm-er: No.
because of the loading problem in the two tanks in Fig, 2.14, The loading problem is an
important issue in developing mathematical equations to describe composite systems.
See Reference [7],1

I
42 MATHEMATICAL DESCRIPTIONS OF SYSTEMS
I
Figure 2.24
I
I
I
I
t
Thrust = km
•
Lunar surface I
-
!
Q+u
Figure 2.25
--T
---- . -
-._-----
--
- - T
---- - -
-------- --
Q+ y
2.19 Find a state equation to describe the network shown in Fig. 2.26. Find also its trans
fer function.
1 F Figure 2.26
r
-In In
u y
t
(current J-
source)
IH
2.20 Find a state equation to describe the network shown in Fig. 2.2. Compute also its transfer
matrix.
2.21 Consider the mechanical system shown in Fig. 2.27. Let I denote the moment of inertia
of the bar and block about the hinge. It is assumed that the angular displacement () is
very small. An external force u is applied to the bar as shown. Let y be the displacement

Problems 43
of the block, with mass m 2, from equilibrium. Find a state-space equation to describe
the system. Find also the transfer function from u to y.
Figure 2.27 I, //////
I
I
.L
k,
~
e r f"
~ _J
;l
m,
~ ~
~ . kl ~
?
~
t,
I I
I
I m,

Chapter
/
Linear Algebra
3.1 Introduction
This chapter re\'iews a number of concepts and results in linear algebra that are essential in the
study of this text. The topics are carefully selected. and only those that will be used subsequently
are introduced. Most results are developed intuitively in order for the reader to better grasp
the ideas. They are stated as theorems for easy reference in later chapters. However. no formal
proofs are gi ven.
As we saw in the preceding chapter. all parameters that arise in the real world are real
numbers. Therefore we deal only with real numbers. unless stated otherwise. throughout this
text. Let A, B. C. and D be, respectively. n x m. III x r.l x n. and r x p real matrices. Let a,
be the ith column of A, and b the jth row of B. Then we have
j
b
l
b
2
(3.1)
(3.2)
and
BD= (3.3)
.
I
44
1

3.2 Basis, Representation, and Orthonormalization 4S
These identities can easily be verified. Note that a, b i is an 11 x r matrix; it is the product of an
11 x I colunm vector and a I x r row vector. The product bi ai is not defined unless n = r; it
becomes a scalar if 11 = r.
3.2 Basis, Representation, and Orthonormalization
Consider an II-dimensional real linear space. denoted by 'R n. Every vector in 'R" is an II-tuple
of real numbers such as .
X=
To save space, we write it as x = [XI X2 ..• x,,],. where the'prime denotes the transpose.
The set of vectors (XI. X2 ..... xm) in 'R" is said to be lillearly depelldent if there exist
real numbers al. a2 . .... am. not all zero. such that
(3.4)
= = =
If the only set of ai for which (3.4) holds is al O. a2 O. .... am O. then the set of
vectors (XI. X2 •.. .. xm) is said to be linearly independent.
If the set of vectors in (3.4) is linearly dependent. then there exists at least one Cti. say.
a I. that is different from zero. Then (3.4) implies
I
XI == --[Q'~X2 + Ct3X3 + ... + ctmxm]
C¥I
=: fhx2 + fhx 3 + '" + f3m x m
where f3i = -C¥i /a I· Such an expression is called a linear combination.
The dimensioll of a linear space can be defined as the maximum number of linearly
independent vectors in the space. Thus in 'R n. we can find at most 11 linearly independent
vectors.
Basis and representation A set of linearly independent vectors in 'R" is called a basis if
every vector in 'R n can be expressed as a unique linear combination of the set. In 'R". any set
of n linearly independent vectors can be used as a basis. Let {ql. q2 ....• q,,} be such a set.
Then every vector X can be expressed uniquely as
(3j)
Define the n x 11 square matrix
Q := [ql ql ... q,,) (3.6)
Then (3.5) can be written as

46  LINEAR ALGEBRA
r
al
I
a2
|     |     |     |     |     | x =Q  |     | =: Qx  |     |     |     | (3.7)  |
| --- | --- | --- | --- | --- | ----- | --- | ------ | --- | --- | --- | ------ |
I
We call  x  =  [al  an]' the representation of the vector x with respect to the basis
a2  '"
(ql. q2.· ... qn).
| We will associate with every 'R  |     |     |     |     | n the following orthonormal basis:  |     |     |     |     |     |     |
| -------------------------------- | --- | --- | --- | --- | ----------------------------------- | --- | --- | --- | --- | --- | --- |
|                                  |     |     | I   |     | 0                                   |     |     |     | 0   | 0   |     |
0
|     |     |      | 0   |       | I   |     |     |     | 0   |     |        |
| --- | --- | ---- | --- | ----- | --- | --- | --- | --- | --- | --- | ------ |
|     |     |      | 0   |       | 0   |     |     |     | 0   | 0   |        |
|     |     | i =  |     | i2 =  |     |     | i   | =   |     | in  | (3.8)  |
|     |     | l    |     |       |     |     | n-  | l   |     | =   |        |
|     |     |      | o   |       | o   |     |     |     |     |     |        |
|     |     |      |     |       |     |     |     |     | I   | 0   |        |
|     |     |      | o   |       | o   |     |     |     |     |     |        |
0
With respect to this basis. we have
|     |     |     |     | X2  |               |     |            |     |     | X2  |     |
| --- | --- | --- | --- | --- | ------------- | --- | ---------- | --- | --- | --- | --- |
|     |     |     |     |     | =             |     |            |     | =   |     |     |
|     |     |     | X'- |     | xIiI +X2i2 +  |     | ... +xnin  |     | In  |     |     |
where In is the n x n unit matrix. In other words, the representation of any vector x with respect
to the orthonormal basis in (3.8) equals itself.
Consider the vector x = [1
EXAMPLE 3.1  3]' in 'R2 as shown in Fig. 3.1, The two vectors
| =   |     |     | =   |     |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
ql  [3  I]' and q2  [2  2]' are clearly linearly independent and can be used as a basis. If we
draw from x two lines in parallel with q2 and ql, they intersect at -ql and 2q2 as shown. Thus
the representation of x with respect to {ql, q2l is [-I 2]'. This can also be verified from
To find the representation of x with respect to the basis [q2, i 2}. we draw from x two lines
in parallel with i2 and q2. They intersect at 0.Sq2 and 2h. Thus the representation of x with
| respect to {q2, izl is [0.5  |     |     | 2]'. (Verify.)  |     |     |     |     |     |     |     |     |
| ---------------------------- | --- | --- | --------------- | --- | --- | --- | --- | --- | --- | --- | --- |
Norms of vectors  The concept of norm is a generalization of length or magnitude. Any
real-valued function of x. denoted by Ilxll. can be defined as a norm if it has the following
properties:
|                 |                          |     |     |     | =                   |     |     | =   |     |     |     |
| --------------- | ------------------------ | --- | --- | --- | ------------------- | --- | --- | --- | --- | --- | --- |
| 1.  Ilxll ::::  | 0 for every x and Ilxll  |     |     |     | 0 if and only if x  |     |     | O.  |     |     |     |
=  lalllxli. for any real a.
2.  Ilaxll
| 3.  Ilxl  | +  x211  | CS  IIxlll  | +  IIx211  | for every XI  |     | andx2.  |     |     |     |     |     |
| --------- | -------- | ----------- | ---------- | ------------- | --- | ------- | --- | --- | --- | --- | --- |

3.2 Basis, Representation, and Orthonormalization 47
Figure 3.1 Different representations of
vector x.
x
The last inequality is called the triangular inequality.
Let x = [Xt X2 ..• xn]'. Then the norm of x can be chosen as anyone of the following:
n
IlxIII:= LIXil
;=1
(t
Ilxlb := .Jx'x = I X d2 ) 1(2
Ilxll"" := maXi Ixd
They are called. respectively. I-norm. 2- or Euclidean norm. and infinite-norm. The 2-norm
is the length of the vector from the origin. We use exclusively. unless stated otherwise, the
Euclidean norm and the subscript 2 will be dropped.
In MATLAB. the norms just introduced can be obtained by using the functions
nOl'm(x, 1). norrr: (x, 2) =Dorm(x), andnorm(x, inf).
Orthonormalization A vector x is said to be normalized if its Euclidean nonn is I or x'x = I.
Note that x'x is scalar and xx' is n x n. Two vectors Xl and X2 are said to be orthogonal if
x;
Xl = X;Xt = O. A set of vectors Xi, i = I, 2 .... , m, is said to be orthonomtal if
, { 0 if i f. j
Xi Xj = I =
if i j
Given a set of linearly independent vectors eI, e2, .... em, we can obtain an orthonormal
set using the procedure that follows:

48  LINEAR ALGEBRA
|     | UI := el  |                    |     | ql :=  ul/llulll  |     |     |
| --- | --------- | ------------------ | --- | ----------------- | --- | --- |
|     | U2        | := e2 - (q; e2)ql  |     | q2  := u2/11u211  |     |     |
I II  I I
|     | Um :=  | em - " L m ..k; - 1 I   (q k, em)qk  |     | qm := Um |   Um |     |
| --- | ------ | ------------------------------------ | --- | -------- | ---- | --- |
The first equation normalizes the vector el to have norm I. The vector (q; e2)ql is the projection
of the vector e2 along ql. Its subtraction from ez yields the vertical pan U2. It is then normalized
to 1 as shown in Fig. 3.2. Using this procedure, we can obtain an orthononnal set. This is called
the Schmidt orthonormalization procedure.
Let A  =  [al  a2  ...  am]  be an n  x  m  matrix with m  n. If all columns of A or
<
(ai, i =  1,2 ..... m I Me orthonormal, then
|     |     | a;  |     | 0   | 0   |     |
| --- | --- | --- | --- | --- | --- | --- |
I
a'
|     |      | 2        |      | 0   | 0   |     |
| --- | ---- | -------- | ---- | --- | --- | --- |
|     | =    |          | =    |     |     | =   |
|     | A'A  | [al  a2  | am]  |     |     | 1m  |
0  0
a~
where 1m  is the unit matrix of order m. Note that, in general, AA' '" In. See Problem 3.4.
3.3  Linear Algebraic Equations
Consider the set of linear algebraic equations
Ax =Y  (3.9)
where A and yare. respectively, m x nand m x  1 real matrices and x is an n x  I vector. The
matrices A and yare given and x is the unknown to be solved. Thus the set actually consists of
m equations and n unknowns. The number of equations can be larger than. equal to. or smaller
than the number of unknowns.
We discuss the existence condition and general form of solutions of (3.9). The range
space of A is defined as all possible linear combinations of all columns of A. The rank of A is
| U"_ _  _     | _  _  _  _  _  _  | _  _  _  _  _  e 2  |     |       |     |     |
| ------------ | ----------------- | ------------------- | --- | ----- | --- | --- |
|              |                   |                     |     | u,  - |     |     |
| 1<:.... __+  | _----_+ _         | L  .                |     |       |     |     |
| O~q;e,       | ~                 |                     |     |       |     |     |
I
Figure 3.2  Schmidt orthonormization procedure.

3.3 Linear Algebraic Equations 49
defined as the dimension of the range space or, equivalently, the number oflinearly independent
columns in A. A vector x is called a null vector of A if Ax = O. The null space of A consists
of all its null vectors. The nullity is defined as the maximum number of linearly independent
null vectors of A and is related to the rank by
=
Nullity (A) number of columns of A - rank (A) (3.\0)
EXAMPLE 3.2 Consider the matrix
(3.11)
where ai denotes the ith column of A. Clearly a, and a2 are linearly independent. The third
column is the sum of the first two columns or a, + a2 - a3 = O. The last column is twice the
second column. or 2a2 - aJ = O. Thus A has two linearly independent columns and has rank
2. The set (a,. a2l can be used as a basis of the range space of A.
Equation (3.10) implies that the nullity of A is 2. It can readily be verified that the two
vectors
(3.12)
=
meet the condition Ani O. Because the two vectors are linearly independent, they form a
basis of the null space.
The rank of A is defined as the number of linearly independent columns. It also equals
the number of linearly independent rows. Because of this fact, if A is m x n. then
rank(A) :5 min(m, n)
In MATLAB. the range space. null space, and rank can be obtained by calling the functions
orth, nul l. and rank. For example, for the matrix in (3.11). we type
a=[O 112;12 3 4;2020j;
rank(ai
which yields 2. Note that MATLAB computes ranks by using singular-value decomposition
(svd). which will be introduced later. The svd algorithm also yields the range and null spaces
of the matrix. The MATLAB function R=orth (a ) yields'
Ans R=
0.3782 - 0.3084
0.8877 -0.1468 (3.13 )
0.2627 0.9399
1. This is obtained using MATLAB Version 5. Earlier versions may yield different results.

I
50 LINEAR ALGEBRA
I
The two columns of R fonn an orthononnal basis of the range space. To check the orthonor
mality, we type R' * R, which yields the unity matrix of order 2. The two columns in R are not I ,
,
obtained from the basis {al. a2} in (3.11) by using the Schmidt orthononnalization procedure;
I
they are a by-product of svd. However, the two bases should span the same range space. This , , I I
can be verified by typing
!
rank ([al a2 RJ)
which yields 2. This confinns that {ai, a2} span the same space as the two vectors of R. We
mention that the rank of a matrix can be very sensitive to roundoff errors and imprecise data.
For example, if we use the five-digit display of R in (3.13), the rank of [al a2 R J is 3. The
rank is 2 if we use the R stored in MATLAB, which uses 16 digits plus exponent.
The null space of (3.11) can be obtained by typing null (a) , which yields
I
Ans N~
,
0.3434 -0.5802 ,
I
0.8384 0.3395
(3.14)
-0.3434 0.5802
-0.2475 -0.4598
The two columns are an orthononnal basis of the null space spanned by the two vectors {1I1. lIl1
in (3.12). All discussion for the range space applies here. That is, rank ( [nl n2 NJ)
yields 3 if we use the five-digit display in (3.14). The rank is 2 if we use the N stored in
MATLAB.
With this background, we are ready to discuss solutions of (3.9). We use p to denote the
rank of a matrix.
>
Theorem 3. I
1. Given an m x n matrix A and an m x I vector y, an n x I solution x exists in Ax = y if and only
if y lies in the range space of A or. equivalently.
=
peA) p ([A y])
+
where [A y] is an m x (n I) matrix with y appended to A as an additional column.
=
2. Given A. a solution x exists in Ax y for every y. if and only if A has rank In (full row rank).
The first statement follows directly from the definition of the range space. If A has full
row rank, then the rank condition in (I) is always satisfied for every y. This establishes the
second statement.
>-
Theorem 3.2 (Parameterization of all solutions)
Given an m x n matrix A and an m x I vector y.let xp be a solution of Ax = y and let k := n - p (A)
be the nullity of A. If A has rank n (full column rank) or k = O. then the solution xp is unique. If k > O.
=
then for every real (Xi, i I, 2, .... k. the vector

3.3 Linear Algebraic Equations 51
x == xp +aIOI + ... +akok (3.15)
is a solution of Ax == y. where {ni ..... ok! is a basis of Ihe null space of A.
Substituting (3.15) into Ax == y yields
k
Axp + LO!jAn; == Axp +0 == Y
;=1
Thus. for every a;. (3.15) is a solution. Let x be a solution or Ax == y. Subtracting this from
Axp == y yields
A(x - x p) == 0
x -
which implies that xp is in the null space. Thus x can be expressed as in (3.15). This
establishes Theorem 3.2.
EXAMPLE 3.3 Consider the equation
I
2 3 (3.16)
o
2
This y clearly lies in the range space of A and xp == [0 - 4 0 0]' is a solution. A basis of the
null space of A was shown in (3.12). Thus the general solution of (3.16) can be expressed as
(3.17)
for any real O! I and 0!2.
In application, we will also encounter xA == y. where the m x n matrix A and the I x n
vector yare given. and the I x m vector x is to be solved. Applying Theorems 3.1 and 3.2 to
the transpose of the equation. we can readily obtain the following result.
>
Corollary 3.2
1. Given an m x 11 matrix A. a solution x exists in xA == y. for any y. if and only if A has full column
rank.
2. Given an In X n matrix A and an I x n vector y. let xp be a solution ofxA == y and let k == m - p (A).
If k == O. the solution xp is unique. If k > O. then for any O!j. i == 1.2 ..... k. the vector
x == xp + O!tni + ... + O!knk
is a solution of xA == y. where ojA == 0 and the set {ni .. ... nk! is linearly independent.
In MATLAB, the solution of Ax == y can be obtained by typing A \y. Note the use of
backslash. which denotes matrix left division. For example. for the equation in (3.16). typing

f
52 LINEAR ALGEBRA
I
!
a=[ O 1 12;12 34;2 02 O) ;y= [-4; -8;O] ;
1
a\y
=
yields [0 - 4 0 0 J '. The solution of xA y can be obtained by typing y / A. Here we use
slash, which denotes matrix right division.
Determinant and inverse of square matrices The rank of a matrix is defined as the number
of linearly independent columns or rows. It can also be defined using the detenninant. The
detenninant of a I x I matrix is defined as itself. For n = 2.3, .... the detenninant of n x n
square matrix A = [aij) is defined recursively as. for any chosen j ,
n
L
det A = aijCij (3.18)
f
f
where aij denotes the entry at the ith row and jth column of A. Equation (3.1S) is called
the Laplace expansion. The number cij is the cofactor corresponding to a,} and equals
(-I y+ j det Mi}. where Mij is the (n - I) x (n - I) submatrix of A by deleting its ith row
and jth column. If A is diagonal or triangular. then det A equals the product of all diagonal
entries.
The determinant of any r x r submatrix of A is called a minor of order r. Then the rank
can be defined as the largest order of all nonzero minors of A. In other words. if A has rank r,
then there is at least one nonzero minor of order r, and every minor of order larger than r is
zero. A square matrix is said to be nonsingular if its detenninant is nonzero. Thus a nonsingular
square matrix has full rank and all its columns (rows) are linearly independent.
The inverse of a nonsingular square matrix A = [aij) is denoted by A -I. The inverse has
the property AA -I = A -\ A = I and can be computed as
_I Adj A I ,
A = detA = detA [cij) (3.19)
where Cij is the cofactor. If a matrix is singular. its inverse does not exist. If A is :2 x 2. then
we have
A-1:=[all
(3.20)
a21
Thus the inverse of a 2 x 2 matrix is very simple: interchanging diagonJ.! entries and changing
the sign of off-diagonal entries (without changing position) and di\'idin~ the resulting matrix
b~' the detenninant of A. In general. using (3.19) to compute the inwrse is complicated. If A is
triangular. it is simpler to compute its inverse by solving AA -I = I. :\"te that the inverse of a
triangular matrix is again triangular. The MATLAB function :':-s computes the inverse of A.
Theorem 3.3
Consider Ax = y with A square.
1. If A is nonsingular, then the equation has a unique solution for every y and L'le Solulion equals A - I y.
In particular. the only solution of Ax = 0 is x = O.
i
I
l

3.4 Similarity Transiormation 53
2. The homogeneous equation Ax = 0 has nonzero solutions if and only if A is singular. The number
of linearly independent solutions equals the nullity of A.
3,4 Similarity Transformation
Consider an n x n matrix A. It maps 'R n into itself. If we associate with 'R n the orthonormal
basis {ii, i 2 •...• in} in (3.8), then the ith column of A is the representation of Ai; with reo
spect to the orthonormal basis. Now if we select a different set of basis {q I. q2. .... qn}. then
A. A
the matrix A has a different representation It turns out that the i til column of is the represelltatioll
of Aq; .. ,-iti! respect to the basis {qt. q2, .... qn}· This is illustrated by the example that follows.
EXAMPLE 3.4 Consider the matrix
(3.21)
Let b = [00 I]'. Then we have
[-il
[~:l
2
Ab= A b=A(Ab)=
It can be verified that the following relation holds:
(3.22)
Because the three vectors b, Ab, and A 2b are linearly independent, they can be used as a basis.
We now compute the representation of A with respect to the basis. It is clear that
[:J
2
A(b)=[b Ab A bl
2
A(Ab) = [b Ab A bl [:]
-:n
2 2
A(A b) = [b Ab A b] [
where the last equation is obtained from (3.22). Thus the representation of A with respect to
the basis {b. Ab, A 2b} is
(3.23)

54  LINEAR ALGEBRA
The preceding discussion can be extended to the general case. Let A be an n x n matrix. If
n
| there exists an n x I vector b such that the n vectors b. Ab •...• A |     |     |     |     |     |     | I   |     |
| -------------------------------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
- b are linearly independent
and if
|     |     | An =  |       | +      | + ... +  |           |     |     |
| --- | --- | ----- | ----- | ------ | -------- | --------- | --- | --- |
|     |     |       | .8lb  | .82Ab  |          | .8nAn-lb  |     |     |
then the representation of A with respect to the basis {b.  Ab ..... An-Ib) is
|     |     |     |     | o   | o   |      |     |     |
| --- | --- | --- | --- | --- | --- | ---- | --- | --- |
|     |     |     |     | 0   |     | .81  |     |     |
| ,   |     |     |     | o   | o   | .82  |     |     |
| .-  |     |     |     | o   | o   |      |     |     |
.83 (3.24)
A=
p
|     |     |     |     | o   | 0   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
.8n-1
o
|     |     |     |     | !O  | l.8n  |     |     |     |
| --- | --- | --- | --- | --- | ----- | --- | --- | --- |
This matrix is said to be in a companion form.
Consider the equation
|     |     |     |     | Ax=y  |     |     |     | (3.25)  |
| --- | --- | --- | --- | ----- | --- | --- | --- | ------- |
The square matrix A maps x in 'Rn into y in 'Rn . With respect to the basis {q I.  q2. .... qn).
the equation becomes
(3.26)
where x and y are the representations ofx and y with respect to the basis {ql.  q2 ..... qn).
As discussed in (3.7), they are related by
x =
|     |     |     |     | Qx  | y=Qy  |     |     |     |
| --- | --- | --- | --- | --- | ----- | --- | --- | --- |
with
|     |     |     | Q =  | [ql  q2  | ...  | qnl  |     | (3.27)  |
| --- | --- | --- | ---- | -------- | ---- | ---- | --- | ------- |
an n x n nonsingular matrix. Substituting these into (3.25) yields
|     |     | AQx =  |     | Qy  or  | Q-IAQx =  |     | y   | (3.28)  |
| --- | --- | ------ | --- | ------- | --------- | --- | --- | ------- |
Comparing this with (3.26) yields
|     |     | A =  | Q-IAQ  |     | or  A =  | QAQ-I  |     | (3.29)  |
| --- | --- | ---- | ------ | --- | -------- | ------ | --- | ------- |
This is called the similarity transformation and A and A are said to be similar. We write
(3.29) as
AQ=QA
or
|     | A(ql  q2  ...  | qnl =  | [Aql  | Aq2  | ...  | Aqnl =  | (ql  q2  ...  qnlA  |     |
| --- | -------------- | ------ | ----- | ---- | ---- | ------- | ------------------- | --- |

3.5 Diagonal Form and Jordan Form 55
A
This shows that the ith column of is indeed the representation of Aqj with respect to the
basis {ql, q2, ... , qn}.
3.5 Diagonal Form and Jordan Form
A square matrix A has different representations with respect to different sets of basis. In this
section, we introduce a set of basis so that the representation will be diagonal or block diagonal.
A real or complex number A is called an eigenvalue of the n x n real matrix A if there
exists a nonzero vector x such that Ax = AX. Any nonzero vector x satisfying Ax = AX is
called a (right) eigenvector of A associated with eigenvalue A. In order to find the eigenvalue
= =
of A, we write Ax AX Hx as
(A - AI)x = 0 (3.30)
where I is the unit matrix of order n. This is a homogeneous equation. If the matrix (A - AI) is
nonsingular, then the only solution of (3.30) is x = 0 (Theorem 3.3). Thus in order for (3.30)
to have a nonzero solution x, the matrix (A - AI) must be singular or have determinant O.
We define
t.(A) = det(H - A)
It is a monic polynomial of degree n with real coefficients and is called the characteristic
polynomial of A. A polynomial is called monic if its leading coefficient is I. If A is a root of
the characteristic polynomial, then the determinant of (A - AI) is 0 and (3.30) has at least one
nonzero solution. Thus every root of t.(A) is an eigenvalue of A. Because t.(A) has degree n,
the n x n matrix A has n eigenvalues (not necessarily all distinct).
We mention that the matrices
-0'3 Tl
o o
o
1
o
and their transposes
o
I
o
I
o o
all have the following characteristic polynomial:
These matrices can easily be formed from the coefficients of t.(A) and are called companion
form matrices. The companion-form matrices will arise repeatedly later. The matrix in (3.24)
is in such a form.

56  LINEAR ALGEBRA
Eigenvalues of A are all distinct  Let Ai. i  =  I.  2. .. . , n, be the eigenvalues of A and
be all distinct. Let qi be an eigenvector of A associated with Ai; that is, Aq,  =  Aiqi. Then
the set of eigenvectors (q I.  ql .. .. ,  q,,) is linearly independent and can be used as a basis.
Let  A  be the representation of A with respect to this basis. Then the first column of  A  is the
| representation of Aql =  | Alql with respect to (ql,  |     |     | q2,  | ... , qn). From  |     |
| ------------------------ | -------------------------- | --- | --- | ---- | ---------------- | --- |
o
|     |     | Aql =  Alql  | =  [ql  | q2  ...  | qn]  0  |     |
| --- | --- | ------------ | ------- | -------- | ------- | --- |
o
A
we conclude that the first column of  :is [AI  0  ...  OJ'.  The second column of A is the
representation of Aq2  =  A2q2  with respect to {ql,  q2,  qn},  that is, (0)" 0  ...  0]'.
Proceeding forward, we can establish
|     |     |     | AI     | 0  0  | 0   |          |
| --- | --- | --- | ------ | ----- | --- | -------- |
|     |     |     | 0  A2  | 0     | 0   |          |
|     |     |     | 0      | 0     | 0   |          |
|     |     | A=  |        | ;"3   |     | (3.31 )  |
0
|     |     |     | 0   | 0   | An  |     |
| --- | --- | --- | --- | --- | --- | --- |
This is a diagonal matrix. Thus we conclude that every matrix with distinct eigenvalues has
a diagonal matrix representation by using its eigenvectors as a basis. Different orderings of
eigenvectors will yield different diagonal matrices for the same A.
If we define
(332)
| then the matrix  A  | equals  |     |     |     |     |     |
| ------------------- | ------- | --- | --- | --- | --- | --- |
(3.33)
as derived in (3.29). Computing (3.33) by hand is not simple because of the need to compute
A.
the inverse of Q. However, if we know  then we can verify (3.33) by checking Q .. \ =  AQ.
| EXAMPLE 3.5  Consider the matrix  |     |     |     |     |     |     |
| --------------------------------- | --- | --- | --- | --- | --- | --- |
I  Its characteristic polynomial is
j
| I   |         |          |       |        | o       |     |
| --- | ------- | -------- | ----- | ------ | ------- | --- |
|     |         |          |       | ~I     | o  ]    |     |
|     | 6(A) =  | det(AI - | A) =  | del [  | A  -")  |     |
,1
-1  A-I
I
| J   |     | = A[A(;" - |      | =        | +           |     |
| --- | --- | ---------- | ---- | -------- | ----------- | --- |
|     |     |            | I) - | 2]  (A - | 2)(A  I);"  |     |

|     |     |     |     |     |     | 3.5  | Diagonal Form and Jordan Form  | 57.  |
| --- | --- | --- | --- | --- | --- | ---- | ------------------------------ | ---- |
~.  Thus A has eigenvalues 2. -1, and O. The eignevector associated with A =  2 is any nonzero
~  solution of
|     |     |     |     |     | _I  | o   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
~
|     |     |      | 2I)ql =  |     |     | -2  |          | 0   |
| --- | --- | ---- | -------- | --- | --- | --- | -------- | --- |
|     |     | (A - |          |     | ~   |     | ]  ql =  |     |
[
-I
Thus ql =  [0  1  I]' is an eigenvector associated with A =  2. Note that the eigenvector is not
unique. [0  a]' for any nonzero real a can also be chosen as an eigenvector. The eigenvector
a
| associated with A  | =   | -I is any nonzero solution of  |     |     |     |     |     |     |
| ------------------ | --- | ------------------------------ | --- | --- | --- | --- | --- | --- |
[i
|     |     |     | (A - (-I)I)q2 =  |     |     |     |     |     |
| --- | --- | --- | ---------------- | --- | --- | --- | --- | --- |
which yields q2  =  [0  - 2  I]'. Similarly. the eigenvector associated with A  = 0 can be
computed as q3 =  [2  I  - I]'. Thus the representation of A with respect to {q I, q2. q3} is
|     |     |     |     |     | 2   | 0   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
(3.34)
|     |     |     |     | A =  | ~   | ~I  |     |     |
| --- | --- | --- | --- | ---- | --- | --- | --- | --- |
| ,   |     |     |     |      | [   |     |     |     |
.'
It is a diagonal matrix with eigenvalues on the diagonal. This matrix can also be obtained by
computing
with
o
-2  (3.35 )
However, it is simpler to verify QA = AQ or
,
o
| '.  [:  |     | 0   |        |     |     |     |           |     |
| ------- | --- | --- | ------ | --- | --- | --- | --------- | --- |
|         |     |     | ~] [~  | ~l  | ~]- | [~  | ~  ~] [~  |     |
| ;       | -2  |     |        |     |     |     |           | -2  |
1
j
|     |     | -I  | 0   | 0   | 0   | 0   | I  I  | I   |
| --- | --- | --- | --- | --- | --- | --- | ----- | --- |
.'C\
The result in this example can easily be obtained using MATLAB. Typing
|     | a=[O  |     | 0  0;1  | 0  2;0  | 1   | 1];  | [q,d]=eig(a)  |     |
| --- | ----- | --- | ------- | ------- | --- | ---- | ------------- | --- |
yields
n
o
0.8186]
|     | [0.707~  |     |         |     |         |     |     | [~  ~I  |
| --- | -------- | --- | ------- | --- | ------- | --- | --- | ------- |
|     |          |     | 0.8944  |     | 0.4082  |     |     |         |
q =
d =
|     |     | 0.7071  | -0.4472  |     | -0.4082  |     |     |     |
| --- | --- | ------- | -------- | --- | -------- | --- | --- | --- |
where d is the diagonal matrix in (3.34). The matrix q is different from the Q in (3.35); but their
corresponding columns differ only by a constant. This is due to nonuniqueness of eigenvectors
and every column of q is normalized to have norm I in MATLAB. If we type eig (a) without
the left-hand-side argument. then MATLAB generates only the three eigenvalues 2,  -1,  O.

I
58 LINEAR ALGEBRA
I
We mention that eigenvalues in MATLAB are not computed from the characteristic polynomial.
Computing the characteristic polynomial using the Laplace expansion and then computing its
!
roots are not numerically reliable, especially when there are repeated roots. Eigenvalues are
computed in MATLAB directly from the matrix by using similarity transformations. Once
n
all eigenvalues are computed, the characteristic polynomial equals (A - Ai). In MATLAB,
typing r=e ig (a) ; poly (r) yields the characteristic polynomial.
EXAMPLE 3.6 Consider the matrix
A
[~l ~ -~3]
=
Its characteristic polynomial is (A + I)(A 2 -f4A+ 13). Thus A has eigenvalues -I, 2±3j. Note
'" that complex conjugate eigenvalues must appear in pairs because A has only real coefficients.
Theeigenvectorsassociatedwith-Iand2+3jare,respectively,[1 0 Ol'and[j -3+2j j]'.
=
The eigenvector associated with A 2 - 3 j is [-j - 3 - 2j - j]', the complex conjugate
of the eigenvector associated with A = 2 + 3j. Thus we have
o
I j -I
-j ]
Q = 0 -3 +2j -3 7 2j and A = ~ 2 + 3j (3.36)
[ o [ o
j
The MATLAB function [q, d] =eig (a) yields
I 0.2582j -0.2582j ]
q = 0 -0.7746 + 0.5164j -0.7746 - 0.5164j
[ o
0.2582j -0.2582j
; and
o
-I
2 + 3j
d= ~
[ o
All discussion in the preceding example applies here.
Complex eigenvalues Even though the data we encounter in practice are all real numbers.
complex numbers may arise when we compute eigenvalues and eigenvectors. To deal with this
problem, we must extend real linear spaces into complex linear spaces and permit all scalars
such as in (3.4) to assume complex numbers. To see the reason, we consider
Cti
=
Av [I I +2 j ] v = 0 (3.37)
I-j
If we restrict v to real vectors. then (3.37) has no nonzero solution and the two columns of
A are linearly independent. However, if v is permitted to assume complex numbers, then
v = [-2 1 - jl' is a nonzero solution of (3.37). Thus the two columns of A are linearly
dependent and A has rank 1. This is the rank obtained in MATLAB. Therefore. whenever
complex eigenvalues arise. we consider complex linear spaces and complex scalars and

3.6 Functions of a Square Matrix 59
transpose is replaced by complex-conjugate transpose. By so doing. all concepts and results
developed for real vectors and matrices can be applied to complex vectors and matrices.
Incidentally, the diagonal matrix with complex eigenvalues in (3.36) can be transformed into
a very useful real matrix as we will discuss in Section 4.3.1.
Eigenvalues of A are not all distinct An eigenvalue with mUltiplicity 2 or higher is called a
repeated eigenvalue. In contrast, an eigenvalue with multiplicity I is called a simple eigenvalue.
If A has only simple eigenValues, it always has a diagonal-form representation. If A has repeated
eigenvalues, then it may not have a diagonal form representation. However, it has a block
diagonal and triangular-form representation as we will discuss next.
Consider an n X n matrix A with eigenvalue A and multiplicity n. In other words, A has
=
only one distinct eigenvalue. To simplify the discussion, we assume n 4. Suppose the matrix
=
(A - AI) has rank n - 1 3 or, equivalently, nullity I; then the equation
(A - AI)q = 0
has only one independent solution. Thus A has only one eigenvector associated with A. We
need n - 1 = 3 more linearly independent vectors to form a basis for 'R 4 The three vectors
q2, q3, q4 will be chosen to have the properties (A - A1fq" = 0, (A - AI)3q3 = 0, and
=
(A - A1)4q4 O.
A vector v is called a generalized eigenvector of grade n if
(A - AI)"v = 0
and
(A - AI)n-'v 'I 0
If n = I, they reduce to (A - AI)v = 0 and v '10 and v is an ordinary eigenvector. For n = 4,
we define
V3 := (A - AI)V4 = (A - AI)v
V2 := (A - AI)V3 = (A - A1)2v
v, := (A - A1)v" = (A - AI)3v
They are called a chain of generalized eigenvectors of length n = 4 and have the properties
(A - AI)v, = 0, (A - AI)2v2 = 0, (A - AI)3V3 = O. and (A - A1)4v4 = O. These vectors,
as generated. are automatically linearly independent and can be used as a basis. From these
equations, we can readily obtain
Av, = AV,
= +
AV2 v, AV2
AV3 = V2 + AV3
= +
AV4 V3 AV.j

60  LINEAR ALGEBRA
Then the representation of A with respect to the basis {VI,  V2, V3,  v41 is
A 1 0 0]
o
A  1  0
|     | J:= [0  |     |     | (3.38)  |     |
| --- | ------- | --- | --- | ------- | --- |
0  A  I
o
0  0  A
We verify this for the first and last columns. The first column of J  is the representation of
AVI  =  AVI  with respect to {VI. V2, V3, v41. which is [A  0  0  OJ'. The last column of J  is the
+
representation of AV4  =  V3  AV4 with respect to {VI, V2, V3, V4}, which is [0  0  1 A]'. This
verifies the representation in (3.38). The matrix J has eigenvalues on the diagonal and 1 on the
superdiagonal. If we reverse the order of the basis. then the l's will appear on the subdiagonal.
The matrix is called a Jordan block of order n =  4.
If (A - AI) has rank n - 2 or. equivfently, nullity 2. then the equation
(A - AI)q = 0
has two linearly independent solutions. Thus A has two linearly independent eigenvectors and
we need (n - 2) generalized eigenvectors. In this case. there exist two chains of generalized
eigenvectors IVI. V2, ... , vkl and lUI, U2, ...• ulI with k  + [
|     |     | =  n. If VI  | and UI  are linearly  |     |     |
| --- | --- | ------------ | --------------------- | --- | --- |
independent, then the set of n vectors {VI, ... , Vb UI, ... , ud is linearly independent and can
be used as a basis. With respect to this basis, the representation of A is a block diagonal matrix
of form
A=diagIJI. J21
where J I and h are, respectively. Jordan blocks of order k and [.
Now we discuss a specific example. Consider a 5 x 5 matrix A with repeated eigenvalue AI
with multiplicity 4 and simple eigenvalue A2. Then there exists a nonsingular matrix Q such that
assumes one of the following forms
0
| AI     | 0  0  0   | AI  0     | 0      |     |     |
| ------ | --------- | --------- | ------ | --- | --- |
| 0  AI  | 0  0      | 0  AI     | 0  0   |     |     |
| 0      | 0  0      | 0  0      | 0  0   |     |     |
| AI =   | AI        | AI        |        |     |     |
| 0  0   | 0  AI  0  | 0  0  0   | AI  0  |     |     |
| 0  0   | 0  0  A2  | 0  0  0   | 0  A2  |     |     |
| AI     | 0  0  0   | AI  0     | 0  0   |     |     |
| 0  AI  | 0  0  0   | 0  AI  0  | 0  0   |     |     |
| 0  0   | 0         | 0  0      | 0  0   |     |     |
| A3=    | AI        | AI        |        |     |     |
| 0  0   | 0  AI  0  | 0  0  0   | AI  0  |     |     |
| 0  0   | 0  0      | 0  0  0   | 0      |     |     |
A2  )...2
AI  0  0  0  0
0  AI  0  0  0
0  0
| As=  | AI  0  0  |     |     | (3.39)  |     |
| ---- | --------- | --- | --- | ------- | --- |
0  0  0  AI  0
| 0  0  | 0  0  |     |     |     | I   |
| ----- | ----- | --- | --- | --- | --- |
).,2
f
l

3.6 Functions of a Square Matrix 61
The first matrix occurs when the nullity of (A - )"i I) is I. If the nullity is 2, then A has two
Jordan blocks associated with AI ; it may assume the form in Az or in A 3. If (A - AI I) has nullity
3, then A has three Jordan blocks associated with Al as shown in A.;. Certainly, the positions
of the Jordan blocks can be changed by changing the order of the basis. If the nullity is 4, then
A is a diagonal matrix as shown in A 5. All these matrices are triangular and block diagonal
with Jordan blocks on the diagonal; they are said to be in Jordan form. A diagonal matrix is a
degenerated Jordan form: its Jordan blocks all have order I. If A can be diagonalized, we can
use [q, d J = e i g ( a) to generate Q and A as shown in Examples 3.5 and 3.6. If A cannot be
diagonized, A is said to be defective and [q, d 1 = e i g (a) will yield an incorrect solution. In
this case, we may use the MATLAB function [q, d 1 = jordan (a) . However, j orca:". will
yield a correct result only if A has integers or ratios of small integers as its entries.
Jordan-form matrices are triangular and block diagonal and can be used to establish
many general properties of matrices. For example, because det(CD) = det C det D and
det Qdet Q-I = det I = I, from A = QAQ-I, we have
detA = detQdetAdetQ-I = detA
The determinant of A is the product of all diagonal entries or. equi valently, all eigenvalues of
A. Thus we have
det A = product of all eigenvalues of A
which implies that A is Ilollsingular if and only if it has no zero eigenvalue.
We discuss a useful property of Jordan blocks to conclude this section. Consider the
Jordan block in (3.38) with order 4. Then we have
(3.40)
=
and (J - U)k 0 for J,: ::: 4. This is called nilpotent.
3.6 Functions of a Square Matrix
This section studies functions of a square matrix. We use Jordan form extensively because
many properties of functions can almost be visualized in terms of Jordan form. We study first
polynomials and then general functions of a square matrix.
Polynomials of a square matrix Let A be a square matrix. If k is a positive integer. we
define
Ak := AA··· A (J,: terms)

62
LINEAR ALGEBRA
| =   |     |     |     |     | =   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
and AD  I. Let I(A) be a polynomial such as I(A)  A3 +  2A2 - 6 or (A  +  2)(4A - 3). Then
I(A) is defined as
|     |       | =  A3 +  |           |     |       | =  +         |      |     |
| --- | ----- | -------- | --------- | --- | ----- | ------------ | ---- | --- |
|     | I(A)  |          | 2A2 - 61  | or  | I(A)  | (A  2I)(4A - | 31)  |     |
If A is block diagonal, such as
|     |     |     | A =  | [AI  | 0]  |     |     |     |
| --- | --- | --- | ---- | ---- | --- | --- | --- | --- |
o
A2
where A I and Az are square matrices of any order, then it is straightforward to verify
|     |     | = [A~  |     |      | =     |          |       |         |
| --- | --- | ------ | --- | ---- | ----- | -------- | ----- | ------- |
|     |     | Ak     | 0]  | and  | I(A)  | [/(OAI)  | 0  ]  | (3.41)  |
|     |     |        | o   |      |       |          | . I(A |         |
|     |     |        | A~  |      |       |          | )     |         |
l
=
Consider the similarity transformatiJn A = Q-I AQ or A  QAQ-I. Because
|     |     | Ak =  (QAQ-I)(QAQ-I) ... (QAQ-I) = QAkQ_1  |     |     |     |     |     |     |
| --- | --- | ------------------------------------------ | --- | --- | --- | --- | --- | --- |
we have
|     |     |       | =         |     |           | =          |     |         |
| --- | --- | ----- | --------- | --- | --------- | ---------- | --- | ------- |
|     |     | I(A)  | Q/(A)Q-I  |     | or  I(A)  | Q-I I(A)Q  |     | (3.42)  |
A monic polynomial is a  polynomial with 1 as  its leading coefficient. The minimal
=
polynomial of A is defined as the monic polynomial 1/ICA) ofleast degree such that 1/1 (A)  O.
Note that the 0 is a zero matrix of the same order as A. A direct consequence of (3.42) is
| =   |     |     | (A) = o.  |     |     | A   |     |     |
| --- | --- | --- | --------- | --- | --- | --- | --- | --- |
that I(A)  0 if and only if I  Thus A and  or, more general, all similar matrices
have the same minimal polynomial. Computing the minimal polynomial directly from A is not
simple (see Problem 3.25); however, if the Jordan-form representation of A is available, the
minimal polynomial can be read out by inspection.
Let Ai be an eigenvalue of A with multiplicity ni. That is, the characteristic polynomial
of A is
n
|     |     |     | ~(A) = det(J...I- |     | A) =  | (A - Ai)"'  |     |     |
| --- | --- | --- | ----------------- | --- | ----- | ----------- | --- | --- |
Suppose the Jordan form of A is known. Associated with each eigenvalue, there may be one or
more Jordan blocks. The index of  denoted by ii is defined as the largest order of all Jordan
|     |     |     | Aj,  |     | j,  |     |     |     |
| --- | --- | --- | ---- | --- | --- | --- | --- | --- |
blocks associated with Ai. Clearly we have ii ::: nj. For example, the multiplicities of AI in all
j
five matrices in (3.39) are 4; their indices are, respectively, 4, 3, 2, 2, and 1. The multiplicities
and indices of A2 in all five matrices in (3.39) are all  I. Using the indices of all eigenvalues,
the minimal polynomial can be expressed as
|     | = L  | L   |     |     |     |     |     |     |
| --- | ---- | --- | --- | --- | --- | --- | --- | --- |
with degree ii  iij :::  nj = n = dimension of A. For example, the minimal polynomials
of the five matrices in (3.39) are
|     |     | 1/11  = (A - | AI)4(A - | A2)  | 1/12  =  | (A - AI)3(A - | A2)  |     |
| --- | --- | ------------ | -------- | ---- | -------- | ------------- | ---- | --- |
|     |     | 1/13  = (A - | AI)2(A - | A2)  | 1/1. =   | (A - AI)2(A - | A2)  |     |
|     |     | 1/15  = (A - | AI)(A -  | A2)  |          |               |      |     |

|     |     |     | 3.6  Functions of a Square Matrix  |     | 63  |
| --- | --- | --- | ---------------------------------- | --- | --- |
Their characteristic polynomials, however, all equal
We see that the minimal polynomial is a factor of the characteristic polynomial and has a degree
less than or equal to the degree of the characteristic polynomial. Clearly, if all eigenvalues of
A are distinct, then the minimal polynomial equals the characteristic polynomial.
Using the nilpotent property in (3.40), we can show that
1fr(A) == 0
and that no polynomial of lesser degree meets the condition. Thus 1fr (A)  as defined is  the
minimal polynomial.
.:"  Theorem 3.4 (Cayley-Hamilton theorem)
Let
be the characteristic polynomial of A. Then
|              | +    | 1 + ... +  | +      |            |          |
| ------------ | ---- | ---------- | ------ | ---------- | -------- |
| D.(A) == An  | a1An |            | an-1A  | a'll == 0  | (3.43 )  |
-
In  words,  a matrix satisfies its own characteristic polynomial. Because ni  >  iii, the
characteristic polynomial contains the minimal polynomial as a factor or D.(i,) ==
1fr(A)h(A)
for some polynomial heAl. Because 1fr(A) == 0, we have D.(A) == 1fr(A)h(A) == O· heAl == O.
This establishes the theorem. The Cayley-Hamilton theorem implies that An can be written as
a linear combination of {I.  A,  ... , An-I}. Multiplying (3.43) by A yields
| +            | + ... +  |         | +          |         |     |
| ------------ | -------- | ------- | ---------- | ------- | --- |
| A,,+I  alAn  |          | an_IA2  | anA == o·  | A == 0  |     |
which implies that A"-I-I can be written as a linear combination of {A,  A2 ...• A"}. which,
,
in turn, can be written as a linear combination of {I.  A ..... An-I}. Proceeding forward, we
conclude that. for any polynomial I CAl. no matter how large its degree is. I (A) can always
be expressed as
(3.44)
for some f3i. In other words. every polynomial of an n x n matrix A can be expressed as a linear
combination of {I, A ..... An-I}. If the minimal polynomial of A with degree ii is available,
then every polynomial of A can be expressed as a linear combination of {I. A ..... A"-I}. This
is a better result. However. because ii may not be available, we discuss in the following only
(3.44) with the understanding that all discussion applies to ii.
One way to compute (3.44) is to use long division to express I(A) as
|     | I(A) == q(A)D.(A)  |     | +  heAl  |     | (3.45)  |
| --- | ------------------ | --- | -------- | --- | ------- |
where q(A) is the quotient and heAl is the remainder with degree less than n. Then we have
| I(A) == q(A)D.(A)  |     | +              | +             |     |     |
| ------------------ | --- | -------------- | ------------- | --- | --- |
|                    |     | heAl == q(A)O  | heAl == heAl  |     |     |

64  LINEAR ALGEBRA
Long division is not convenient to carry out if the degree of f (A) is much larger than the degree
of 6(A). In this case, we may solve heAl directly from (3.45). Let
n
|     |     |     | heAl := f30  | +     | + ... +  |        | 1   |
| --- | --- | --- | ------------ | ----- | -------- | ------ | --- |
|     |     |     |              | f3IA  |          | f3n_IA | -   |
where the n unknowns f3j  are to be solved. If all n eigenvalues of A are distinct. these f3j can
be solved from the n equations
for i =  I. 2 . ... , n. If A has repeated eigenvalues, then (3.45) must be differentiated to yield
additional equations. This is stated as a theorem.
>.
Theorem 3.5
We are given f(A) and an n X n matrix A with characteristi~ polynomial
n
m
|     |     |     | 6(A) =  |     | (A - | A,)"'  |     |
| --- | --- | --- | ------- | --- | ---- | ------ | --- |
;=1
=
| where n  | L~=I nj. Define  |     |     |     |     |     |     |
| -------- | ---------------- | --- | --- | --- | --- | --- | --- |
It is a polynomial of degree n - I with n unknown coefficients. These n unknowns are to be solved
from the following set of n equations:
|     | f(/l(Aj) = h(I)(Aj)  |     | for 1= 0,  | I. ... , nj - |     | I  and  | i =  I,  2 .... , m  |
| --- | -------------------- | --- | ---------- | ------------- | --- | ------- | -------------------- |
where
and h(/l(Aj) is similariy defined. Then we have
=
|     |     |     |     | f(A)  | heAl  |     |     |
| --- | --- | --- | --- | ----- | ----- | --- | --- |
and heAl is said to equal f(A) on the spectrum of A.
EXAMPLE 3.7 Compute AIOO with
A
|                        |     |       |         | =  [~I     | ~2]                                          |     |     |
| ---------------------- | --- | ----- | ------- | ---------- | -------------------------------------------- | --- | --- |
|                        |     | f(A)  | =  AIOO |            | f(A). The characteristic polynomial of A is  |     |     |
| In other words. given  |     |       |         | • compute  |                                              |     |     |
MA) =  2 +  +  I = (A  +  1)2 Let heAl =  +  f3IA. On the spectrum of A. we have
|     | A  2A  |     |     |     | f30  |     |     |
| --- | ------ | --- | --- | --- | ---- | --- | --- |
.
.~
|     |     | f(-I) = he-I):  |     |     | (_1)100 =    |     | f30  - f31  |
| --- | --- | --------------- | --- | --- | ------------ | --- | ----------- |
| j   |     |                 |     |     |              |     | =           |
| .   |     | /'(-1)          | =   |     | 100· (_1)99  |     | f31         |
h'(-I):
+
Thus we have f31  =  -100, f30  =  I  f31  =  -99, heAl =  -99 - lOOA. and

3.6  Functions of a Square Matrix  65
IOO
|     | A = 1301  | +  13IA =  | -991 - | iOOA  |     |          |               |     |
| --- | --------- | ---------- | ------ | ----- | --- | -------- | ------------- | --- |
|     |           |            |        |       |     | I  ]. =  | [-199  -100]  |     |
=_99[1  0] -IOO[ 0
|     |     | o   | I   | -I  | -2  |     | 100  101  |     |
| --- | --- | --- | --- | --- | --- | --- | --------- | --- |
Clearly A  can also be obtained by multiplying A 100 times. However. it is simpler to use
100
Theorem 3.5.
Functions of a square matrix  Let f(A) be any function, not necessarily a polynomial. One
way to define f (A) is to use Theorem 3.5. Let h (A) be a polynomial of degree n - I. where n
is the order of A. We solve the coefficients of heAl by equating f (Al = heAl on the spectrum
of A. Then f(A) is defined as heAl.
| EXAMPLE 3.8  | Let  |     |        |     | -?]  |     |     |     |
| ------------ | ---- | --- | ------ | --- | ---- | --- | --- | --- |
|              |      |     |        | 0   | 0    |     |     |     |
|              |      |     | AI  =  | 0   | I    | 0   |     |     |
[
103
Compute eAI'. Or, equivalently. if f().) =
e;·I. what is f(AJl?
+  13IA +-
The characteristic polynomial of AI  is (A - I)~(A - 2). Let h(A)  =  130  13~A2
Then
|     |     |                  |     | el   |        | +     | +       |     |
| --- | --- | ---------------- | --- | ---- | ------ | ----- | ------- | --- |
|     |     | f(l) = h(l) :    |     |      | = 130  | 131   | 132     |     |
|     |     | J'(l) = h'(1) :  |     |      | = 131  | +     |         |     |
|     |     |                  |     | leI  |        | 2132  |         |     |
|     |     |                  |     | 21   |        | +     | + 413~  |     |
|     |     | f(2) = h(2) :    |     | e    | = 130  | 2131  |         |     |
Note that, in the second equation, the differentiation is with respect to A, not I. Solving these
equations yields 130 =  -2fe'  +  e21 , 131  = 3re +  2e' - 2e21 , and fh = e21  el  reI. Thus we
|     |     |     |     | '   |     |     |     | - - |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
have
|     |                       |     | +  e21)I  | +      | +     |       | 21           |     |
| --- | --------------------- | --- | --------- | ------ | ----- | ----- | ------------ | --- |
|     | eA11 = heAd = (-2rel  |     |           | (3re'  |       | 2e' - | 2e )AI       |     |
|     |                       |     |           |        |       |       | 21           | 21  |
|     |                       |     |           |        | 2e' - | e     | 0  2e' -0 2e |     |
]
+  21
|     |     | (e  | - el  re')A~ =  |     |     | 0   | el  |     |
| --- | --- | --- | --------------- | --- | --- | --- | --- | --- |
-
[
|     |     |     |     |     | e21  | el  | 0  2e21  | el  |
| --- | --- | --- | --- | --- | ---- | --- | -------- | --- |
|     |     |     |     |     |      | -   |          | -   |
EXAMPLE 3.9 Let
.
i"  Compute eA'I. The characteristic polynomial of A2 is (A - I)~(A - 2), which is the same as
for AI. Hence we have the same heAl as in Example 3.8. Consequently, we have
|     |     |     |       | 21  |      | l         | 21  |     |
| --- | --- | --- | ----- | --- | ---- | --------- | --- | --- |
|     |     |     | 2e' - | e   | 21 e | 2e' -0 2e |     |     |
]
|     |     | 1 =    | =   |     |     |     |     |     |
| --- | --- | ------ | --- | --- | --- | --- | --- | --- |
|     | eA  | h(Az)  |     | 0   | el  |     |     |     |
:
[
|     |     |     | e2l  | e'  | -tel  |     | 2e~t - e[  |     |
| --- | --- | --- | ---- | --- | ----- | --- | ---------- | --- |
_

66  LINEAR ALGEBRA
.,,
EXAMPLE 3,10 Consider the Jordan block of order 4:
At  1
,OAt
A=  (3.46)
o
0
[
o
0
Its characteristic polynomial is (A _A[)4. Although we can select h (A) as /30 + /31 A+ fhA+ fhA3
,
it is computationally simpler to select h (A) as
,
This selection is permitted because heAl has degree (n  =  =
| ,   |     |     |     |     |     |     |     |     | -   | 1)  3 and n  | 4 independent  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------------ | -------------- |
;,
| unknowns. The condition f(A) = heAl on the spectrum of  |     |     |     |     |     |     |     |     |     | A   |     |
| ------------------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
y ields immediately
,,:
:
. i
I"  (Atl
fh =
|     |     |     |     |     |     |     |     |     | 2'  | .   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Thus we have
|     |       | =   |           | f';~tl (A _  |     |         |     | I";~tl  |     | f(3~;Ad (A - |        |
| --- | ----- | --- | --------- | ------------ | --- | ------- | --- | ------- | --- | ------------ | ------ |
|     | f(A)  |     | f(At)I +  |              |     | AtI) +  |     | (,.\ _  |     | AII)2 +      | AtI)3  |
Using the special forms of  (A - Atl)k as discussed in (3.40). we can readily obtain
|     |     |     |         |     | f(Ad  | f'(Atl/l!  |     | I"(Atl/2'  |     | f(3)(At}/3!]  |     |
| --- | --- | --- | ------- | --- | ----- | ---------- | --- | ---------- | --- | ------------- | --- |
|     |     |     | f(A) =  |     | 00    | f(A,)      |     | f'(Atl/l!  |     | I"(At}/2!     |     |
(3.47)
o
|     |     |     |     |     |     |     |     | f(Atl  |     | f'(At)/l'  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ------ | --- | ---------- | --- |
[
o
|     |               |     |       |     |     |     | 0   |     | 0   | f(l.·t)  |     |
| --- | ------------- | --- | ----- | --- | --- | --- | --- | --- | --- | -------- | --- |
|     | If f(A) = eAI |     | then  |     |     |     |     |     |     |          |     |
,
|     |     |     |     |     | [?" teA.I'  |     |     | AII/2!  | N"/"]  |     |     |
| --- | --- | --- | --- | --- | ----------- | --- | --- | ------- | ------ | --- | --- |
(2e
|     |     |     |     |     |     |     |        | AII  |     | AII/2!  |     |
| --- | --- | --- | --- | --- | --- | --- | ------ | ---- | --- | ------- | --- |
|     |     |     |     |     |     | 0   | eA.!t  | (e   | (2e |         |     |
e AI  (3.48)
=
|     |     |     |     |     |     | 0   | 0   | e}ql  |     | (e AII  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ----- | --- | ------- | --- |
|     |     |     |     |     |     | 0   | 0   | 0     |     | eA1t    |     |
Because functions of A are defined through polynomials of A, Equations (3.41) and (3.42)
are applicable to functions.
| I  EXAMPLE 3.11  |     |     | Consider  |     |     |     |     |     |     |     |     |
| ---------------- | --- | --- | --------- | --- | --- | --- | --- | --- | --- | --- | --- |
,
,
|     |     |     |     |     |     | AI  |     | 0   | 0  0  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ----- | --- | --- |
1
|     |     |     |     |     |     | 0   |     |     | 0  0  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ----- | --- | --- |
AI
I
|     |     |     |     |     | A=  | 0   | 0   | AI     | 0  0  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ------ | ----- | --- | --- |
|     |     |     |     |     |     | 0   | 0   | 0  A2  |       |     |     |
|     |     |     |     |     |     |     |     | 0      | 0     |     |     |
|     |     |     |     |     |     | 0   | 0   |        | A2    |     |     |

|     |     |     |     |     |     |     |     | 3.6  Functions of a Square Matrix  |     | 67  |
| --- | --- | --- | --- | --- | --- | --- | --- | ---------------------------------- | --- | --- |
It is block diagonal and contains two Jordan blocks. If f(A)  =  eAt, then (3.41) and (3.48)
imply
eA1(
|     |     |     |     |     | teAJt  | tZeAlt /2!  |     | 0   | 0   |     |
| --- | --- | --- | --- | --- | ------ | ----------- | --- | --- | --- | --- |
|     |     |     |     | 0   | eA1    | teAl1       |     | 0   | 0   |     |
!
|     |     |     | =    | 0   |     |     |       |       |         |     |
| --- | --- | --- | ---- | --- | --- | --- | ----- | ----- | ------- | --- |
|     |     |     | eAt  |     | 0   |     | eAJt  | 0     | 0       |     |
|     |     |     |      | 0   | 0   |     | 0     | eA2t  | teA2'!  |     |
|     |     |     |      | 0   | 0   |     | 0     | 0     |         |     |
e)\."!1
| If f(A) =  | (s - | A)-I, then (3.41) and (3.47) imply  |     |     |     |     |     |     |     |     |
| ---------- | ---- | ----------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
I
|     |     |     |      |      |            |     |      |       | 0   | 0   |
| --- | --- | --- | ---- | ---- | ---------- | --- | ---- | ----- | --- | --- |
|     |     |     | (s - | AI)  | (s - All"  |     | (s - | AIl3  |     |     |
I
I
|     |     |     |     | 0   |      |      |      |       | 0   | 0   |
| --- | --- | --- | --- | --- | ---- | ---- | ---- | ----- | --- | --- |
|     |     |     |     |     | (s - | All  | (s - | AI)2  |     |     |
I
|     | (sI-A)-1 =  |     |     | 0   | 0   |     |      |      | 0   | 0  (3.49)  |
| --- | ----------- | --- | --- | --- | --- | --- | ---- | ---- | --- | ---------- |
|     |             |     |     |     |     |     | (s - | All  |     |            |
I
|     |     |     |     | 0   | 0   |     | 0   |     |           |            |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --------- | ---------- |
|     |     |     |     |     |     |     |     |     | (s - A2)  | (s - A2)2  |
I
|     |     |     |     | 0   | 0   |     | 0   |     | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
(s - A2)
Using power series  The function of A was defined using a polynomial of finite degree. We
now give an altematiw definition by using an infinite power series. Suppose f (A) can be
expressed as the power series
ex;
L>'V
i
f(A) =
i=O
with the radius of convergence p. If all eigenvalues of A have magnitudes less than p. then
f (A) can be defined as
L00:
IMi
f(A) =  (3.50)
i=O
Instead of proving the equivalence of this definition and the definition based on Theorem 3.5.
we use (3.50) to derive (3.47).
A
| EXAMPLE 3.12  |     | Consider the Jordan-form matrix  |        |            |     |      | in (3.46). Let  |     |          |     |
| ------------- | --- | -------------------------------- | ------ | ---------- | --- | ---- | --------------- | --- | -------- | --- |
|               |     |                                  |        | +          |     |      | +               |     | 2 + ...  |     |
|               |     | f(A) =                           | frAIl  | f'(AIl(A - |     | All  | r(AIl (A -      |     | AIl      |     |
2!
then

68 LINEAR ALGEBRA
(A -
Because Al I)' = 0 for k ::: n = 4 as discussed in (3.40). the infinite series reduces
immediately to (3.47). Thus the two definitions lead to the same function of a matrix.
The most important function of A is the exponential function eAr. Because the Taylor
series
. l~t~ ~nln
+ + -- + ... + - - + ...
eAr = I At
2! n'
converges for all finite t. and t. we have
(3.51)
,
This series involves only multiplications and additions and may converge rapidly: there
fore it is suitable for computer computation. We list in the following the program in MATLAB
that computes (3.51) for t = I:
~~nction E=exp~2(A)
;
E=zeros(size (~j)
c=eye (size 1.'1.) i ;
k=::";
~~ile norm(E+F-S,l» O
E=E+F;
F=A*F/k;
k=k+l ;
In the program, E denotes the partial sum and F is the next term to be added to E. The first line
defines the function. The next two lines initialize E and F. Let Ck denote the kth term of (3.51)
*
with t = I. Then we have Ck~1 = (Aj k)Ck for k = 1,2 ..... Thus we have F = A F jk. The
computation stops if the I-norm of E + F - E, denoted by norm(E -+- F - E. I). is rounded
to 0 in computers. Because the algorithm compares F and E. not F and O. the algorithm uses
+
norm(E F - E. I) instead of normIEI). Note that norm(a.l) is the I-norm discussed in
Section 3.2 and will be discussed again in Section 3.9. We see that the series can indeed be
programmed easily. To improve the computed result. the techniques of scaling and squaring can
be used. In MATLAB. the function ex;:>m2 uses (3.51). The function ex;:", or ex;;ml. however.
uses the so-called Pade approximation. It yields comparable results as eX;l!112 but requires only
about half the computing time. Thus ex;:>m is preferred to exprr2. The function expm3 uses
Jordan form, but it will yield an incorrect solution if a matrix is not diagonalizable. If a c1osed
form solution of eAr is needed. we must use Theorem 3.5 or Jordan form to compute e·\r.
We derive some important properties of eAr to conclude this section. Using (3.51). we
CJn readily verify the next two equalities
(3 52)
(3.53 )
(3.54) l

69
3.6  Functions of a Square Matrix
To show (3.54), we set 12  ==  -II' Then (3.53) and (3.52) imply
which implies (3.54). Thus the inverse of eAt can be obtained by simply changing the sign of
I. Differentiating term by term of (3.51) yields
| d   |     | I   |     |
| --- | --- | --- | --- |
x
|       | == ""'     |       | k   |
| ----- | ---------- | ----- | --- |
| _eAt  |            | Ik-IA |     |
| dl    | L..(k-I)I  |       |     |
k=1
Thus we have
(3.55)
This is an important equation. We mention that
(3.56)
==
The equality holds only if A and B commute or AB  BA. This can be verified by direct
substitution of (3.51).
The Laplace transform of a function! (t) is defined as
1
x
|     | 1<s):== .£[f(t)] ==  |     | !(t)e-"dt  |
| --- | -------------------- | --- | ---------- |
It can be shown that
.£ [:] ==
S-(k+l)
Taking the Laplace transform of (3.51) yields
|     | x   |     | '"  |
| --- | --- | --- | --- |
.£[eAt ==  ~s-(k+I)Ak == s-I ~(s-IA)k
]
|     | k=O  |     | k=O  |
| --- | ---- | --- | ---- |
Because the infinite series
")C
| " " ' (   -I | ,) k _l+  | -I·   +  - 2.2 | +  - ("I            |
| ------------ | --------- | -------------- | ------------------- |
| L . . S      | A   -     | S  A   S A     |   "' - -S -1A.) -1  |
k=O
converges for Is-I AI  <  1. we have
:x;
| S-I L (s-IA)k==S-II+s- |     | 2 A+s-JA | 2 +  ...  |
| ---------------------- | --- | -------- | --------- |
k=O
(3.57)
and

70  LINEAR ALGEBRA
(3.58)
Although in the derivation of (3.57) we require s to be sufficiently large so that all eigenvalues
of s- I A have magnirudes less than 1, Equation (3.58) acrually holds for all s except at the
eigenvalues of A. Equation (3.58) can also be established from (3.55). Because L[df(t)/dt 1 ==
sL[J(/»)- f(O), applying the Laplace transform to (3.55) yields
|     |     | sL[eA1 | eO ==  | AL[eA1 |     |     |
| --- | --- | ------ | ------ | ------ | --- | --- |
|     |     |        | )-     |        | )   |     |
or
|     |     | (sl - | A)L[eA1 | = eO = I  |     |     |
| --- | --- | ----- | ------- | --------- | --- | --- |
)
I
which implies (3.58).  !
3.7  Lyapunov Equation
Consider the equation
AM+MB=C  (3.59)
where A and B are, respectively, n x nand m x m constant matrices. In order for the equation
to be meaningful, the matrices M and C must be of order n x m. The equation is called the
Lyapullov equation.
The equation can be written as a set of standard linear algebraic equatio)1s. To see this,
= 3 and m = 2 and write (3.59) explicitly as
we assume II
al2
| [all  | a\3 ]  | [mil  | ml2] + [mil  |      | ml2] [b | ll  l2  |
| ----- | ------ | ----- | ------------ | ---- | ------- | ------- |
| a21   | a2l    |       |              | m21  |         | b ]     |
|       | a2l    | mZl   | mZ2          |      | mZ2  b  |         |
21  b22
| all    | a)2  all  | mll  | m)2  | mJI  | mX2  |     |
| ------ | --------- | ---- | ---- | ---- | ---- | --- |
| [ CII  | el2 ]     |      |      |      |      |     |
| -      | en        |      |      |      |      |     |
e21
|     | ell  Cl2  |     |     |     |     |     |
| --- | --------- | --- | --- | --- | --- | --- |
MUltiplying them out and then equating the corresponding entries on both sides of the equality,
we obtain
| all + bll  |        |     |      | b21  | 0    | 0   |
| ---------- | ------ | --- | ---- | ---- | ---- | --- |
|            | all    |     | a\3  |      |      |     |
|            | + bll  |     |      | 0    |      | 0   |
| a21        | an     |     | a2l  |      | bZI  |     |
0
| all  | al2  | all + bll  |      | 0      |           | b21         |
| ---- | ---- | ---------- | ---- | ------ | --------- | ----------- |
|      | 0    |            | 0    | all +  | an        |             |
| bIZ  |      |            |      | bZ2    |           | a\3         |
| 0    |      |            | 0    |        | +         |             |
|      | b\2  |            |      | aZI    | a22  b22  | a2l         |
| 0    | 0    |            | bl2  | all    | aJ2       | all +  b22  |

|       |      |     |     | 3.8  | Some Useful Formulas  | 71      |
| ----- | ---- | --- | --- | ---- | --------------------- | ------- |
| mil   | CII  |     |     |      |                       |         |
| mZI   | Cli  |     |     |      |                       |         |
| mJI   | C31  |     |     |      |                       |         |
| x     | -    |     |     |      |                       | (3.60)  |
| ml2   | CI2  |     |     |      |                       |         |
| m22   | CZ2  |     |     |      |                       |         |
| 1n32  | C32  |     |     |      |                       |         |
This is indeed a standard linear algebraic equation. The matrix on the preceding page is a
square matrix of order n x m = 3 x 2 = 6.
Let us define 5t(M)  := AM  +  MB. Then the Lyapunov equation can be written as .
A(M)  =  C.  It maps an nm-dimensional linear space into itself.  A scalar IJ  is called an
eigenvalue of A  if there exists a nonzero M such that
A(M) =  I/M
Because 5t can be considered as a square matrix of order nm, it has nl11 eigenvalues '/b for
k =  1,  2,  ... , nm. It turns out
|           | +            | =     |     |       |                |     |
| --------- | ------------ | ----- | --- | ----- | -------------- | --- |
| IJk = Ai  | f.J.j  fori  | 1,2.  | n;  | j  =  | 1,  2.  "', m  |     |
where Ai, i =  I,  2 .... ,  n, and f.J.j,  j  =  I,  2,  m, are, respectively. the eigenvalues of
A and B. In other words, the eigenvalues of A are all possible sums of the eigenvalues of A
andB.
We show intuitively why this is the case. Let u be an n x I right eigenvector of A associated
with Ai; that is, Au = Ai u. Let Y be a I x m left eigenvector of B associated with f.J. j: that is,
yB = Yf.J.j. Applying 5t to the n x m matrix uv yields
|           | Auy + uvB =  |       | +        |         | +         |     |
| --------- | ------------ | ----- | -------- | ------- | --------- | --- |
| 5t(UY) =  |              | AiUY  | UVf.J.j  | =  (A!  | f.J.j)UY  |     |
Because both U and v are nonzero. so is the matrix UY. Thus (Ai  +  f.J.j) is an eigenvalue of A.
The determinant of a square matrix is the product of all its eigenvalues. Thus a matrix
is  nonsingular if and only if it has no zero eigenvalue.  If there  are no  i  and j  such that
+  =
Ai  0, then the square matrix in (3.60) is nonsingular and. for every C, there exists a
f.J. j
unique M satisfying the equation. In this case, the Lyapunov equation is said to be nonsingular.
+
If Al  f.J.j  = 0 for some i and j. then for a given C, solutions mayor may not exist. If C lies
in the range space of ~"l. then solutions exist and are not unique. See Problem 3.32.
The MATLAB function m= lyap (a, b, -c)  computes the  solution of the Lyapunov
equation in (3.59).
3.8  Some Useful Formulas
This section discusses some formulas that will be needed later. Let A and B be m  x nand
x p constant matrices. Then we have
n
|     | p(AB) :::: min(p(A), p(B»  |     |     |     |     | (3.61 )  |
| --- | -------------------------- | --- | --- | --- | --- | -------- |
where p  denotes the rank. This can be  argued as follows.  Let p(B)  _  Then B has
|     |     |     |     |     | 01.  | 01  |
| --- | --- | --- | --- | --- | ---- | --- |
linearly independent rows. In AB, A operates on the rows of B. Thus the rows of AB are

72 LINEAR ALGEBRA
linear combinations of the rows of B. Thus AB has at most a linearly independent rows. In
AB, B operates on the columns of A. Thus if A has f3 linearly independent columns, then
AB has at most f3 linearly independent columns. This establishes (3.61). Consequently, if
A = BIBzB J ···, then the rank of A is equal to or smaller than the smallest rank ofB i.
LeI A be III x n and let C and D be any n x n and III x III nonsingular matrices. Then we
have
p(AC) = peA) = p(DA) (3.62)
In words, the rank of a matrix will not change after pre- or poslmultiplying by a nonsingular
matrix. To show (3.62), we define
P:=AC (3.63)
i
Because peA) ::: minim, n) and piC) = n', we have peA) ::: piC). Thus (3.61) implies
pep) ::: min(p(A), piC»~ ::: piA)
:-.lext we write (3.63) as A = PC-I. Using the same argument, we have peA) ::: pep). Thus we
conclude pCP) = piA). A consequence of (3.62) is that the rank of a marrix will not change
by elementary operations. Elementary operations are (l) multiplying a row or a column by a
nonzero number, (2) interchanging two rows or two columns, and (3) adding the producI of
one row (colUmn) and a number to another row (column). These operalions are the same as
multiplying nonsingular matrices. See Reference [6, p. 542].
Let A be III x nand B be n x Ill. Then we have
detiI + AB) = det(I" + BA) (3.64)
m
where 1m is the unit matrix of order 111. To show (3.64), let us define
-A]
1m
~] Q=
[ -B
I"
We compute
1m + AB 0 ]
NP=
[ B In
and
-A ]
+
I" BA
Because Nand Q are block triangular. their determinants equal the products of the delerminant
of their block-diagonal matrices or
det N = det 1m . det I" = I = del Q
Likewise, we have
det(NP) = det(I,. + AB) det(QP) = det(I" + BA)
Because

|     |     | 3.9  Quadratic Form and Positive Definiteness  |     |     | 73  |
| --- | --- | ---------------------------------------------- | --- | --- | --- |
det(NP) = det N det P = det P
and
det(QP) = det Q det P = det P
|                     | +             | +     |     |     |     |
| ------------------- | ------------- | ----- | --- | --- | --- |
| we conclude det(lm  | AB) = det(l"  | BA).  |     |     |     |
In N. Q. and P. if In. I",. and B are replaced. respectively. by JSln. )5111/. and -B. then
we can readily obtain
|                         | sn det(sl", -                          | AB) = sll/ det(sl" - |     | BA)  | 0 .65)  |
| ----------------------- | -------------------------------------- | -------------------- | --- | ---- | ------- |
| which implies. for n =  | or for n x n square matrices A and B.  |                      |     |      |         |
III
|     | det(sI | AB) = det(sl" - |     | BA)  | (366)  |
| --- | ------ | --------------- | --- | ---- | ------ |
n  -
They are useful formulas.
3.9  Quadratic Form and Positive Definiteness
An n x n real matrix M is said to be symmelric if its transpose equals itself. The scalar function
x'Mx. where x is an n x  I real vector and i\[' = M. is called a qlladralicjorm. We show that
all eigenvalues of symmetric M are real.
The eigenvalues and eigenvectors of real matrices can be cOillplex as shown in Example
3.6. Therefore we must allow x to assume complex numbers for the time being and consider the
scalar function x*Mx. where x' is the complex conjugate transpose of x. Taking the complex
conjugate transpose of x'~Ix yields
|     | (x*Mx)* =  | x'M'x = x'i\I'x == x'Mx  |     |     |     |
| --- | ---------- | ------------------------ | --- | --- | --- |
where we have used the fact that the complex conjugate transpose of a real M  reduces to
simply the transpose. Thus x'Mx is real for any complex x. This assertion is not true if M
is not symmetric. Let A be an eigenvalue of M and v be its eigenvector; that is. Mv =  ;. v.
Because
v'Mv =  V'AV =
A(\'V)
and because both v'Mv and v'v are real. the eigenvalue A must be real. This shows that all
eigenvalues of symmetric :\1 are real. After establishing this fact. we can return our study to
exclusively real vector x.
We claim that every symmetric matrix can be diagonalized using a similarity transfor
mation even it has repeated eigenvalue A. To show this. we show that there is no generalized
eigenvector of grade 2 or higher. Suppose x is a generalized eigenvector of grade 2 or
|     |     | (M - Al)c | = 0  |     | (367)  |
| --- | --- | --------- | ---- | --- | ------ |
X
|     |     | AI)x i= 0  |     |     | (368 )  |
| --- | --- | ---------- | --- | --- | ------- |
(M -
Consider

74 LINEAR ALGEBRA
I(M - ).I)x]'(M - ,u)x = x'(M' - AI')(M - ,u)X = x'(M - A1)2x
which is nonzero according to (3.68) but is zero according to (3.67). This is a contradiction.
Therefore the Jordan form of M has no Jordan block of order 2. Similarly, we can show that
the Jordan form of 1\1 has no Jordan block of order 3 or higher. Thus we conclude that there
exists a nonsingular Q such that
M=QDQ-I (3.69)
where D is a diagonal matrix with real eigenvalues of M on the diagonal.
A square matrix A is called an orthogonal matrix if all columns of A are orthonormal.
Clearly A is nonsingular and we have
A' A = Ii and A -I = At
r
which imply AA' = AA -I = I = A'A. Thus the inverse of an orthogonal matrix equals its
transpose. Consider (3.69). Because D' = D and M' = M, (3.69) equals its own transpose or
= =
which implies Q-I Q' and Q'Q QQ' = I. Thus Q is an orthogonal matrix; its columns
are orthonormalized eigenvectors of M. This is summarized as a theorem.
»
Theorem 3.6
For every real symmetric matrix M. there exists an orthogonal matrix Q such that
= =
M QDQ' or D Q'MQ
where D is a diagonal matrix with the eigenvalues of M. which are all real. on the diagonal.
A symmetric matrix M is said to be positive definite, denoted by M > O,jfx'Mx > 0 for
every nonzero x. It is positive semidefinite, denoted by M ~ 0, if x'Mx ~ 0 for every nonzero
x. If M > 0, then x'~1x = 0 if and only if X = O. If M is positive semidefinite. then there
exists a nonzero x such that x'Mx = O. This property will be used repeatedly later.
':> Theorem 3.7
A symmetric n x n matrix M is positive definite (positive semidefinite) if and only if anyone of the
following conditions holds.
1. Every eigenvalue of iV( is positive (zero or positive).
2. All the leading principal minors ofM are positive (all the principal minors of M are zero or positive).
3. There exists an n x n nonsingular matrix N (an n x n singular matrix N or an m x n matrix N with
m < n) such that 1\1 = N'N.
Condition (I) can readily be proved by using Theorem 3.6. Next we consider Conditon (3). If
M = N'N. then
x'Mx = x'N'Nx = (Nx)'(Nx) = IINxll~ ~ 0

3.9 Quadratic Form and Positive Definiteness 75
for any x. If N is nonsingular. the only x to make Nx = 0 is x = O. Thus M is positive definite. If N
is singular. there exists a nonzero X to make Nx = O. Thus M is positive semidefinite. For a proof of
Condition (2). see Reference [\0].
We use an example to illustrate the principal minors and leading principal minors. Consider
[:~: :~~ :~~]
M =
m31 m32 m33
Its principal minors are m II • m 22, m 33.
IIlII
det
[
m21
and det M. Thus the principal minors are the determinants of all submatrices of l\il whose diagonals
coincide with the diagonal of M. The leading principal minors of !'vi are
and detM
Thus the leading principal minors ofM are the determinants ofrhe submarrices ofM obrained by delering
=
the last k columns and lasr k rows for k 2, 1, O.
.. Theorem 3.8
1. An m X n matrix H. with m ~ n, has rank n. if and only if the n x n matrix H'H has rank n or
det(H'H) f= O.
2. An m x n matrix H. with m :::: n. has rank m. if and only if the m x m matrix HH' has rank m or
det(HH') f= O.
The symmetric matrix H'H is always positive semidefinite. It becomes positive definite if H'H is
nonsingular. We give a proof of this theorem. The argument in the proof will be used to establish the
main results in Chapter 6: therefore the proof is spelled out in detail.
Proof' Necessity: The condition p(H'H) = n implies p(H) = n. We show this by
contradiction. Suppose p(H'H) = n but p(H) < n. Then there exists a nonzero vector
= =
v such that Hv = O. which implies H'Hv O. This contradicts p(H'H) n. Thus
=
p(H'H) = n implies pm) n.
=
Sufficiency: The condition p(H) n implies p(H'H) = n. Suppose not, or
p(H'H) < n; then there exists a nonzero vector v such that H'Hv = O. which implies
v'H'Hv = 0 or
=
0= v'H'Hv (Hv)'(Hv) = IIHvll~
= =
Thus we have H,· O. This contradicts the hypotheses that v f= 0 and p(H) n. Thus
p(H) = implies p(H'H) = n. This establishes the first part of Theorem 3.8. The second
part can be established similarly. Q.E.D.
We discuss the relationship between the eigenvalues of H'H and those of HH'. Because both H'H
and HH' are symmetric and positive semidefinite, their eigenvalues are real and nonnegative (zero or

76  LINEAR ALGEBRA
positive). If H is m  X n. then H'H has n eigenvalues and HH' has m eigenvalues. Let A  =  Hand
B =  H'. Then (3.65) becomes
|     | det(sI | HH') =  | s",-n det(sI |     | H'H)  |         |     |
| --- | ------ | ------- | ------------ | --- | ----- | ------- | --- |
|     | m      | -       |              | n   | -     | (3.70)  |     |
This  implies  that the  characteristic  polynomials of HH' and H'H differ only  by  sm-n. Thus  we
conclude that HH' and H'H have the same nonzero eigenvalues but may have different numbers of
zero eigenvalues. Furthermore. they have at most ii := min (m, n) number of nonzero eigenvalues.
3,10  Singular-Value Decomposition
Let H be an nz  x n real matrix. Define M := H'H. Clearly M is n x n, symmetric. and semidefinite.
Thus all eigenvalues at M are real and nonnegative (zero or positive). Let r be the number of its positive
eigenvalues. Then the eigenvalues of M =  H'~ can be arranged as
| A'I  )::: A'::!  ::: ... A";  1>  |     |     |  0 =  | =   | ... =  An  |     |     |
| --------------------------------- | --- | --- | ----- | --- | ---------- | --- | --- |
Ar+ I
Let ii := min(m, n). Then the set
is called the singular values of H. The singular values are usually arranged in descending order in
magnitude.
EXAMPLE 3.13  Consider the 2 x 3 matrix
|     |     |     | -4  -1  |     |     |     |     |
| --- | --- | --- | ------- | --- | --- | --- | --- |
H=
|     |     |     | [ 2  0.5  |     |     |     |     |
| --- | --- | --- | --------- | --- | --- | --- | --- |
We compute
1
5
-10
-2.5
|     | M=H'H=  |     |     | 1.25  |     |     |     |
| --- | ------- | --- | --- | ----- | --- | --- | --- |
|     |         |     |     | -2.5  | 5   |     |     |
and compute its characteristic polynomial as
|         |       | A3  |           | 2          |         |     |     |
| ------- | ----- | --- | --------- | ---------- | ------- | --- | --- |
| det(H - | M) =  |     | - 26.25A  | =  A2 (A - | 26.25)  |     |     |
Thus the eigenvalues of H'H are 26.25, 0, and 0, and the singular values of Hare J26.25 =
5.1235 and O. Note that the number of singular values equals min (n, ml .
In view of (3.70), we can also compute the singUlar values of H from the eigenvalues of
.j
HH'. Indeed. we have
|     | _            |     | [  71  | -10.5]  |     |     |     |
| --- | ------------ | --- | ------ | ------- | --- | --- | --- |
|     | IYI:= HH' =  |     | -      |         |     |     |     |
|     |              |     | -10.5  | 5.25    |     |     |     |
and
|         |     | M)  A2 - | 26.25A =  | A(A - | 26.25)  |     | ;   |
| ------- | --- | -------- | --------- | ----- | ------- | --- | --- |
| det(H - |     | =        |           |       |         |     | i   |
,
Thus the eigenvalues of HH' are 26.25 and 0 and the singular values of H' are 5.1235 and
I
O. We see that the eigenvalues of HIH differ from those of HH' only in the number of zero
eigenvalues and the singular values of H equal the singular values of HI.
I

3.11  Norms oi Matrices  77
For :\1 =  H'H. there exists. following Theorem 3.6, an orthogonal matrix Q such that
Q'H'HQ = D =: S'S  (3.71 )
A;
where D is an n x n diagonal matrix with  on the diagonal. The matrix S is  x n with the
111
singular values i'i on the diagonal. Manipulation on (3.71) will lead eventially to the theorem
that follows,
Theorem 3,9 (Singular-value decomposition)
Every m x n matrix H can be transformed into the form
H= RSQ'
|     | =  =  |     | =   |     |     |
| --- | ----- | --- | --- | --- | --- |
with R'R  RR'  1m. Q'Q = QQ'  I", and S being 111  x 11  with the singular values of H on the
diagonal.
The columns of Q are  orthonormalized eigenvectors of H'H  and  the columns of R
are orthonormalized eigenvectors of HH'. Once R, S. and Q are computed. the rank of H
equals the number of nonzero singular values. If the rank of H  is r. the first r columns of
R are an orthonormal basis of the range space of H. The last (11  r) columns of Q are an
-
orthonormal basis of the null space ofH. Although computing singular-value decomposition is
time consuming. it is very reliable and gi"es a quantitative measure of the rank. Thus it is used in
MATLAB to compute the rank. range space. and null space. In MATLAB. the singular values
of H can be obtained by typing s~svd (H). Typing  [R, S, QJ  ~svd (H)  yields the three
matrices in the theorem. Typing or t h (H)  and :1u 11 (H)  yields. respectively. orthonormal
bases of the range space and null space of H. The function nul l  will be used repeatedly in
Chapter 7.
| EXAMPLE 3.14  | Consider the matrix in (3.11). We type  |              |             |     |     |
| ------------- | --------------------------------------- | ------------ | ----------- | --- | --- |
| a===  ~ 0     | 1  1  2; 1                              | 2  3  ~ ; :  | 0  2  0: ;  |     |     |
[r , s , q I =s 'ld (a)
which yield
-0.3034  n
8  0  0
|     | [0.3782  |     | 0.8729]  |     |     |
| --- | -------- | --- | -------- | --- | --- |
=
| r=  | 0.8877  | -0.1468  | -0.-1364  | s  [6'r | 2.4686  0  |
| --- | ------- | -------- | --------- | ------- | ---------- |
|     | 0.2627  | 0.9399   | 0.2182    |         | 0  0       |
-05802]
|     | [022"      | 0.7020   | 0.3434   |          |     |
| --- | ---------- | -------- | -------- | -------- | --- |
|     | 0.3498     | -0.2439  | 0.8384   | 0.3395   |     |
| q   | =  0.5793  |          |          |          |     |
|     |            | 0.4581   | -0.3434  | 0.5802   |     |
|     | 0.6996     | -0.4877  | -0.2475  | -0.4598  |     |
Thus the singular values of the matrix A in (3.11) are 6.1568. 2.4686. and O. The matrix has
two nonzero singular values. thus irs rank is 2 and. consequently. its nullity is 4 - p(A) = 2.
The first two columns of r are the orthonormal basis in (3.13) and the last two columns of q
are the orthonormal basis in (3.14).

78 LINEAR ALGEBRA
3,11 Norms of Matrices
The concept of norms for vectors can be extended to matrices. This concept is needed iJ
Chapter 5. Let A be an m X n matrix. The norm of A can be defined as
= IIAxl1 =
IIAII sup -- sup IIAxl1 (3.72
x"O Ilxll Ilxll=1
where sup stands for supremum or the least upper bound. This norm is defined through thl
norm ofx and is therefore called an induced nann. For different Ilxll, we have different IIAII
For example, if the I-norm IIxlll is used, then
mlx/~Iaijl)
IIAII] = = largest column absolute sum
where aij is the ijth element of A. If the Euclidean norm IIxl12 is used, then
IIAII2 = largest singular value of A
=
(largest eigenvalue of A' A) 1/2
If the infinite-norm Ilxll"" is used, then
(t
II A II"" = mrx laij I) = largest row absolute sum
)=1
These norms are all different for the same A. For example, if
A=[~I ~]
then IIAlb = 3 + I - II = 4, IIAII2 = 3.7, and IIAllco = 3 + 2 = 5, as shown in Fig.
3.3. TheMATLAB functions norm (a, 1), norm(a, 2) =norm(a) ,andnorm(a, inf)
compute the three norms.
The norm of matrices has the following properties:
IIAxll :::: IIAllllxll
+ +
IIA BII :::: IIAII IIBII
IIABII :::: IIAIIIIBIl
The reader should try first to solve all problems involving numerical numbers by hand and
then verify the results using MATLAB or any software.
3,} Consider Fig. 3.1. What is the representation of the vector x with respect to the basis
{ql, izJ? What is the representation of q] with respect to {i 2, q2P
3.2 What are the I-norm. 2-norm. and infinite-norm of the vectors

Problems 7'
x,
Xz
n
2 IIxll, = 1
) ,
~-- 2 3 4 3 4
, x,
,
x
- - _0 Ax
-2 IIxll~ = 1 -2
This magnitudt: gi yes
The sum of these two the nonn of A.
magnitudes gives the
norm of A.
(a) (b)
x,
2-~
IIxll"" = I
I -
/x
.., - -------- - -
-
-, --.l ...... --L - - - -- , , x,
-4 -3 - 2 -0 I 2 3 - 4 _ 5'
- - - - - - --. Ax
-2
This magnitude gi ves
the norm of A.
(c)
Figure 3.3 Different nonns of A.
3.3 Find two onhononnal vectors that span the same space as the two vectors in Problem
3.2.
3.4 Consider an n x m matrix A with n ::: m. If all columns of A are onhononnal. then
A' A = 1m. What can you say about AA'?
3.5 Find the ranks and nullities of the following matrices:

80 LINEAR ALGEBRA
2 3
-1 -2
o o
3.6 Find bases of the range spaces and null spaces of the matrices in Problem 3.5.
3.7 Consider the linear algebraic equation
It has three equations and two unknowns. Does a solution x exist in the equation') Is the
solution unique? Does a solution exis't if y = [I 1 1j '?
3.8 Find the general solution of
2 3
-I -2
o o
How many parameters do you have?
3.9 Find the solution in Example 3.3 that has the smallest Euclidean norm.
3.10 Find the solution in Problem 3.8 that has the smallest Euclidean norm.
3.11 Consider the equation
x[n] = An x[O] + An-1bu[O] + A n -2bu[IJ + ... + Abu[n - 2] + burn - I]
where A is an n x n matrix and b is an n x I column vector. Under what conditions on
A and b will there exist u[O], u[I] ... . , u[n - I] to meet the equation for any x[n] and
x[O]? [Hint: Write the equation in the form
urn - I]
urn - 2]
x[n1 - Anx[O] = [b Ab ... An-1b]
u[O]
3.12 Given
what are the representations of A with respect to the basis {b, Ab. A2b. A3b} and the
basis (b. Ab, A2b, AJb), respectively? (Note that the representations are the same!)
3.13 Find Jordan-form representations of the following matrices:

Problems  81
4
~O]
|      | [~  |       | [-~  | -IJ  |
| ---- | --- | ----- | ---- | ---- |
| AI=  | 2   | Az =  |      | 0    |
|      | 0   |       |      | -4   |
-n
3]
|     | 0   |     |     | 4   |
| --- | --- | --- | --- | --- |
[~
| AJ=  | I   | A4 =  |     | 20  16  |
| ---- | --- | ----- | --- | ------- |
[:
-25
|     | 0   |     |     | -20  |
| --- | --- | --- | --- | ---- |
Note that all except A. can be diagonalized.
3.14  Consider the companion-form matrix
|     |     | -(Xl  | -a3  | Tl  |
| --- | --- | ----- | ---- | --- |
[~~'
|     |     | 0   | 0   |     |
| --- | --- | --- | --- | --- |
A=
|     | .   | 0     |     |     |
| --- | --- | ----- | --- | --- |
|     |     | I     | 0   |     |
|     |     | 0  0  | I   |     |
Show that its characteristic polynomial is given by
|     |              | +  3 +    | +    | +   |
| --- | ------------ | --------- | ---- | --- |
|     | 6().) =  A4  | alA a2A2  | a3A  | a.  |
Show also that if Ai is an eigenvalue of A or a solution of MA) = 0, then [A;  A;  Ai  I J'
is an eigenvector of A associated with Ai.
3.15  Show that the Valldenllollde determinant
['
3  .3
AI  A A3
2
|     |     | A2   A2     |   A2•1     |     |
| --- | --- | ----------- | ---------- | --- |
|     |     | I   A~  3   |   "        |     |
|     |     | AI  A2  A3  | A4         |     |
|     |     | I           | I          |     |
equals fLsi<jS.(Aj - i.,). Thus we conclude that the matrix is nonsingular or. equiva
lently, the eigenvectors are linearly independent if all eigenvalues are distinct.
3.16  Show that the companion-form matrix in Problem 3.14 is nonsingular if and only if
i= O. Under this assumption. show that its inverse equals
iY4
o
o
3.17  Consider
AT
[~
A
A =
o
with A i= 0 and T > O. Show that [0  0  11' is a generalized eigenvector of grade 3 and
the three columns of

82 LINEAR ALGEBRA
0]
AT2
AT 0
o
I
constitute a chain of generalized eigenvectors of length 3. Verify
[ 1 0]
~
Q-IAQ= A I
o 0 A
3.18 Find the char:l.cteristic polynomials and the minimal polynomials of the following
matrices:
0 I 0
n n
~J [1
Al Al
0 Al 0 Al
0 0 0 0
0 0 0
n
[1
AI 0 [~ Al 0
0 Al J.l 0 Al
0 0 0 0
3.19 Show that if A is an eigenvalue of A with eigenvector x, then f(A) is an eigenvalue of
f (A) with the same eigenvector x.
=
3.20 Show that an n x n matrix has the property Ak 0 for k ~ m if and only if A has
eigenvalues 0 with multiplicity n and index m or less. Such a matrix is called a nilpotent
matrix.
3.21 Given
n
1
[~
0
A=
0
find A 10, A 103, and eAt.
3.22 Use two different methods to compute eAt for AI and A4 in Problem 3.13.
3.23 Show that functions of the same matrix commute; that is,
=
f(A)g(A) g(A)f(A)
C~msequently we have AeAt = eAt A.
3.24 . Let

Problems  83
| Find a matrix B such that eB = C. Show that if Ai  |     |     |     | =   |     |     |     |
| -------------------------------------------------- | --- | --- | --- | --- | --- | --- | --- |
0 for some i, then B does not exist.
Let
|     |     |      | A I    | 0]  |     |     |     |
| --- | --- | ---- | ------ | --- | --- | --- | --- |
|     |     | C =  | [0  A  | 0   |     |     |     |
o
0  A
Find a B such that eB = C. Is it true that, for any nonsingular C, there exists a matrix B
such that eB = C?
3.25  Let
I
|     | (sl - | A)-I =  | -Adj (sl - |     | A)  |     |     |
| --- | ----- | ------- | ---------- | --- | --- | --- | --- |
L\(s)
and let m (s) be the monic greatest common divisor of all entries of Adj (s I - A). Verify
for the matrix A3 in Problem 3.13 thatthe minimal polynominal of A equals L\(s)/m(s).
3.26  Define
where
and Ri are constant matrices. This definition is valid because the degree in s of the adjoint
| of (s I - A) is at most n - | I. Verify  |     |     |     |     |     |     |
| --------------------------- | ---------- | --- | --- | --- | --- | --- | --- |
Ro =1
tr(ARd
a.., =-
| -   | 2   |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
tr(AR 2)
3
|     |     | R    | = AR  | +          | I = A"-I +  |     | A"-2  |
| --- | --- | ---- | ----- | ---------- | ----------- | --- | ----- |
|     |     | "-I  |       | n-2  an-I  |             |     | 0'1   |
n
where tr stands for the trace of a matrix and is defined as the sum of all its diagonal
entries. This process of computing O'i and Ri is called the Leverrier algorithm.
3.27  Use Problem 3.26 to prove the Cayley-Hamilton theorem.
3.28  Use Problem 3.26 to show
I
|               |           | +   | +         | 2 +  | +          | +      | 3   |
| ------------- | --------- | --- | --------- | ---- | ---------- | ------ | --- |
| (sl - A)-I =  | -- [An-I  |     | (s  O'dAn |      | (s2  O'IS  | 0'2)An |     |
|               |           |     |           | -    |            |        | -   |
L\(s)

84  LINEAR ALGEBRA
3.29  Let all eigenvalues of A be distinct and let qi be a right eigenvector of A associated with
|                   |     | =               |     | =             |                 |     |
| ----------------- | --- | --------------- | --- | ------------- | --------------- | --- |
| Ai; that is. Aql  |     | Aiqi. Define Q  |     | [ql  q2  ...  | qnl and define  |     |
PI
P2
|     |     |     | P   | '- Q-I_ .  |     |     |
| --- | --- | --- | --- | ---------- | --- | --- |
|     |     |     |     | . - -.     |     |     |
PM
where Pi is the ith row of P. Show that Pi is a left eigenvector of A associated with Ai;
that is, PiA = AiPi.
3.30  Show that if all eigenvalues of A are distinct. then (sl - A)-I can be expressed as
|     |     |     | (sl-A)-I  | = L""- -qI  | iPi  |     |
| --- | --- | --- | --------- | ----------- | ---- | --- |
s - Ai
where qi and PI are right and left eigenvectors of A associated with Ai·
3.31  Find the M to meet the Lyapunov equation in (3.59) with
|     |     | A-[  | 0   | I]  |     |     |
| --- | --- | ---- | --- | --- | --- | --- |
|     |     | -    | -2  | -2  |     |     |
What are the eigenvalues of the Lyapunov equation? Is the Lyapunov equation singular?
Is the solution unique?
3.32  Repeat Problem 3.31 for
|     | A-[  | 0   | 1]  |     |     |     |
| --- | ---- | --- | --- | --- | --- | --- |
B=I
|     |     | -1  -2  |     |     |     |     |
| --- | --- | ------- | --- | --- | --- | --- |
with two different C.
3.33  Check to see if the following matrices are positive definite or semidefinite:
,
n
0  J
|     |     | ~   | [-:  |      | [alai  | ala~  al (/)  |
| --- | --- | --- | ---- | ---- | ------ | ------------- |
|     |     | I   |      | 0    | a2al   |               |
|     | [:  |     |      | -iJ  |        | Q'].Q2  ala)  |
|     |     | 0   |      | 0    | a)al   | a)a2  a3{/3   |
3.34  Compute the singular values of the following matrices:
o
~]
-1
3.35  If A is symmetric, what is the relationship between its eigenvalues and singular values?
I
i

Problems 85
3.36 Show
n
det In + [bl b2 ... bIll = 1 + Lambm
m=l
3.37 Show (3.65).
3.38 Consider Ax = y, where A is m x n and has rank m. Is (A' A)-I A'y a solution? If not.
under what condition will it be a solution? Is A'(AA')-Iy a solution?

Chapter
State-Space Solutions
and Realizations
4.1 Introduction
We showed in Chapter 2 that linear systems can be described by convolutions and, if lumped,
by state-space equations. This chapter discusses how to find their solutions. First we discuss
briefly how to compute solutions of the input-output description. There is no simple analytical
way of computing the convolution
= l~to
y(t) gU, r)u(r)dr
The easiest way is to compute it numerically on a digital computer. Before doing so, the
equation must be discretized. One way is to discretize it as
Lk
=
y(kA) g(kA, mA)u(mA)A (4.1)
m=ko
where A is called the integration step size. This is basically the discrete convolution discussed
in (2.34). This discretization is the easiest but yields the least accurate result for the same
integration step size. For other integration methods. see. for example. Reference [17].
=
For the linear time-invariant (LTI) case, we can also use y(s) g(s)u(s) to compute
the solution. If a system is distributed, g(s) will not be a rational function of s. Except for
some special cases, it is simpler to compute the solution directly in the time domain as in
(4.1). If the system is lumped, g(s) will be a rational function of s. In this case, if the Laplace
transform of u (t) is also a rational function of s , then the solution can be obtained by taking the
inverse Laplace transform of g(s)u(s). This method requires computing poles. carrying out
86

4.2 Solution of LTI State Equations 87
partial fraction expansion, and then using a Laplace transform table. These can be carried out
using the MATLAB functions roots and res idue. However, when there are repeated poles.
the computation may become very sensitive to small changes in the data, including roundoff
errors; therefore computing solutions using the Laplace transform is not a viable method on
digital computers. A better method is to transform transfer functions into state-space equations
and then compute the solutions. This chapter discusses solutions of state equations, how to
transform transfer functions into state equations, and other related topics. We discuss first the
time-invariant case and then the time-varying case.
4.2 Solution of LTI State Equations
Consider the linear time-invariant (LTI) state-space equation
x(t) = AX(I) + Bu(t) (4.2)
y(t) = Cx(t) + Du(t) (4.3)
where A, B, C, and D are, respectively, n x n, n x p, q x n, and q x p constant matrices.
The problem is to find the solution excited by the initial state x(O) and the input u(t). The
solution hinges on the exponential function of A studied in Section 3.6. In particular, we need
the property in (3.55) or
d
_eAt = AeAr = eAt A
dt
to develop the solution. Premultiplying e- Ar on both sides of (4.2) yields
e-Atic(t) _ e-A'Ax(t) = e-AtBu(t)
which implies
Its integration from 0 to t yields
l'
e-Arx("r)I:=o = e-ArBu(r)dr
Thus we have
l'
=
e-A'x(t) - eOx(O) e-ArBu(r)dr (4.4)
Because the inverse of e-A , is eA ' and eO = I as discussed in (3.54) and (3.52), (4.4) implies
l'
x(t) = eA'x(O) + eA(,-r)Bu(r)dr (4.5)
This is the solution of (4.2).
It is instructive to verify that (4.5) is the solution of (4.2). To verify this. we must show
=
that (4.5) satisfies (4.2) and the initial condition x(t) = x(O) at t = O. Indeed, at t 0, (4.5)
reduces to

88
STATE-SPACE SOLUTIONS AND REALIZATIONS
|     |     | x(O)  | == eAOx(O) == eOx(O) == Ix(O) == x(O)  |     |     |     |     |     |
| --- | --- | ----- | -------------------------------------- | --- | --- | --- | --- | --- |
Thus (4.5) satisfies the initial condition. We need the equation
!..11 f(t, T)dr == 11 (!.. f(t, T») dr  + f(t, T)lr=1  (4.6)
|     |     | at  |     | at  |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     | 10  |     | 10  |     |     |     |     |
to show that (4.5) satisfies (4.2). Differentiating (4.5) and using (4.6), we obtain
:t
|     |     | ==  [eAlx(o)  |     | +  11 eA(t-r)Bu(r) dr ]  |     |     |     |     |
| --- | --- | ------------- | --- | ------------------------ | --- | --- | --- | --- |
x(!)
|     |     | == AeAlx(O)  | + ['  |                   |     | +                |     |     |
| --- | --- | ------------ | ----- | ----------------- | --- | ---------------- | --- | --- |
|     |     |              |       | AeA11-r)Bu(T) dr  |     | eAU-riBu(r)!r=1  |     |     |
Jo
i
|     |     | == A (eArx(O)  | +   |                      |     | +   |           |     |
| --- | --- | -------------- | --- | -------------------- | --- | --- | --------- | --- |
|     |     |                |     | 11'eA,I-rlBu(T) dr)  |     |     | eAOBu(t)  |     |
which becomes, after substituting (4.5),
x(t) == Ax(t) + Bu(t)
Thus (4.5) meets (4.2) and the initial condition x(O) and is the solution of (4.2).
Substituting (4.5) into (4.3) yields the solution of (4.3) as
|     |     | yet) == CeAlx(O)  |     | +                     |     |     | +      |        |
| --- | --- | ----------------- | --- | --------------------- | --- | --- | ------ | ------ |
|     |     |                   |     | C 11 eA(I-rlBu(T) dr  |     |     | Du(t)  | (4.7)  |
This solution and (4.5) are computed directly in the time domain. We can also compute the
solutions by using the Laplace transform. Applying the Laplace transform to (4.2) and (4.3)
yields, as deri ved in (2.14) and (2.15),
|     |     |       | ==     | A)-'[x(O)  +  |         |     |        |     |
| --- | --- | ----- | ------ | ------------- | ------- | --- | ------ | --- |
|     |     | xes)  | (sl -  |               | Bu(s)]  |     |        |     |
|     |     |       | ==     |               | +       | +   |        |     |
|     |     | yes)  | C(sl - | A)-'[x(O)     | Bu(s)]  |     | Du(s)  |     |
Once xes)  and Yes)  are computed algebraically, their inverse Laplace transforms yield the
time-domain solutions.
AI
We now give some remarks concerning the computation of e . We discussed in Section
3.6 three methods of computing functions of a matrix. They can all be used to compute eAI
:
1.  Using Theorem 3.5: First, compute the eigenvalues of A; next. find a polynomial h (A) of
| degree n - | 1 that equals eAI on the spectrum of A: then eAr  |     |     |     |     |     | == heAl.  |     |
| ---------- | ------------------------------------------------- | --- | --- | --- | --- | --- | --------- | --- |
2.  Using lord~n form of A:  Let A ==  QAQ-'; then eAI  ==  QeAIQ- I, where A is in Jordan
form and eAr can readily be obtained by using (3.48).
3.  Using the infinite power series in (3.5 I): Although the series will not. in general, yield a
closed-form solution, it is suitable for computer computation. as discussed following (3.51).
In addition, we can use (3.58) to compute eAI, that is.
|     |     |     |     | == ,[-, (sl _  | A)-'  |     |     |        |
| --- | --- | --- | --- | -------------- | ----- | --- | --- | ------ |
|     |     |     |     | eAI            |       |     |     | (4.8)  |

4.2  Solution of LTI State Equations  89
The inverse of (s I - A) is a function of A; therefore. again. we have many methods to compute
it:
| 1.  Taking the inverse of (sl - |     |     | A).  |     |     |     |     |
| ------------------------------- | --- | --- | ---- | --- | --- | --- | --- |
2.  Using Theorem 3.5.
| 3.  Using (sl - | A)-I = Q(sl - |     | A)-IQ-I and (3.49).  |     |     |     |     |
| --------------- | ------------- | --- | -------------------- | --- | --- | --- | --- |
4.  Using the infinite power series in (3.57).
5.  Using the Leverrier algorithm discussed in Problem 3.26.
| EXA~IPLE 4.1  | We use Methods 1 and 2 to compute (sl - |     |     |       |        |     | A)-I. where  |
| ------------- | --------------------------------------- | --- | --- | ----- | ------ | --- | ------------ |
|               |                                         |     |     | A=[O  | -I]    |     |              |
|               |                                         |     |     |       | 1  -2  |     |              |
MeThod 1: We use (3.20) to compute
|     |     | -I  |     | ]-1  |     |     |     |
| --- | --- | --- | --- | ---- | --- | --- | --- |
|     |     |     | [s  |      |     |     | [s  |
+ 2
|     | I     |     |     | 1     |     | I   |       |
| --- | ----- | --- | --- | ----- | --- | --- | ----- |
|     |       | =   |     | +     | =   | +   | +     |
|     | (s  - | A)  | -1  | s  2  | S2  | 2s  | 1  1  |
;)2]
|     |     |     | [(s + 2)/(s +?  |     | -1/(s +  |     |     |
| --- | --- | --- | --------------- | --- | -------- | --- | --- |
|     |     | =   |                 |     | 1)2      |     |     |
1/(s +
|     |     |     |     | 1)- |     | S/(5+)- |     |
| --- | --- | --- | --- | --- | --- | ------- | --- |
+
MeThod 2: The eigenvalues of A are -1. -1. Let h()")  =  /30  /3IA. If heAl equals fCA)  :=
(5 - )..)-1 on the spectrum of A, then
|     |     | fe-I) = h(-I):  |     |     | +   | 1 = /30 - |      |
| --- | --- | --------------- | --- | --- | --- | --------- | ---- |
|     |     |                 |     |     | (s  | 1)-       | /31  |
+
|     |     | /,(-1) = h'(-I):  |     |     | (s  | 1)-2 =  | /31  |
| --- | --- | ----------------- | --- | --- | --- | ------- | ---- |
Thus we have
and
|     | (sl - | A)-I = heAl =  |        | [(s  +  1)-1 + (s + 1)-2JI +  |               |     | (s + I)-2A  |
| --- | ----- | -------------- | ------ | ----------------------------- | ------------- | --- | ----------- |
|     |       |                | [(s +  | 2)/(s +,1)2                   | -1/(s + ;)2]  |     |             |
=
+
|               |                        |     |          | I/(s  1)"        |     | s/(s+)- |     |
| ------------- | ---------------------- | --- | -------- | ---------------- | --- | ------- | --- |
| EXA~IPLE 4.2  | Consider the equation  |     |          |                  |     |         |     |
|               |                        |     | X(T)=[~  | =~]X(r)+[~]U(t)  |     |         |     |
Its solution is
+
|     |     | xU) = eA1x(O)  |     |     | 11 eArI-nBu(r)dr  |     |     |
| --- | --- | -------------- | --- | --- | ----------------- | --- | --- |
The matrix function eAI is the inverse Laplace transform of (s I - A) - I , which was computed
in the preceding example. Thus we have

1
90  STATE-SPACE SOLUTIONS AND REALIZATIONS
1
[(I
|     |     |     |     | +-I   | =   | +     | t    |     |
| --- | --- | --- | --- | ----- | --- | ----- | ---- | --- |
|     |     |     | (s  | 1 )2  |     |       | I)e- |     |
|     |     |     |     | s     |     | le-t  |      |     |
(S+)2
and
[(I
| =     |       |      | t    |          |     | Je'    |                        |     |
| ----- | ----- | ---- | ---- | -------- | --- | ------ | ---------------------- | --- |
|       | +  t  | -te- |      | ]        | [-  |        | (t - r)e-(t-o)u(r) dr  | ]   |
| x(t)  | I)e-  |      |      |          | +   |        |                        |     |
|       |       |      |      | t  x(O)  |     | t  0   |                        |     |
|       | te-t  | (I - | t)e- |          | Jo  | [1 -   | (t - r)]e-(t-o)u(r)dr  |     |
We discuss a general property of the zero-input response eAtx(O). Consider the second
matrix in (3.39). Then we have
|     |     | eAt'  |     | Alt  2 | eAlt /2  | 0   | 0   |     |
| --- | --- | ----- | --- | ------ | -------- | --- | --- | --- |
|     |     |       | le  | 1      |          |     |     |     |
t
|     |         |     |       |     | Alt   |       | 0     |     |
| --- | ------- | --- | ----- | --- | ----- | ----- | ----- | --- |
|     |         | 0   | eA\t  |     | le    | 0     |       |     |
|     | =       |     |       |     |       |       | Q-I   |     |
|     | eAt  Q  | 0   | 0     |     | eA1(  | 0     | 0     |     |
|     |         | 0   | 0     |     | 0     | eA\t  | 0     |     |
|     |         | 0   | 0     |     | 0     | 0     | eA2t  |     |
Every entry of eAt and, consequently, of the zero-input response is a linear combination of terms
2 Alt
{eAlt teAlt e ,  eA2t }. These terms are dictated by the eigenvalues and their indices. In
,  ,  t
n
general, if A has eigenvalue AI  with index  I, then every entry of eAt is a linear combination of
Every such term is analytic in the sense that it is infinitely differentiable and can be expanded
in a Taylor series at every t. This is a nice property and will be used in Chapter 6.
If every eigenvalue, simple or repeated, of A has a negative real part, then every zero
input response will approach zero as t ......  00. If A has an eigenvalue, simple or repeated, with
a positive reai pan, then most zero-input responses will grow unbounded as I ......  00. If A has
some eigenvalues with zero real pan and all with index I and the remaining eigenvalues all
have negative real pans, then no zero-input response will grow unbounded. However, if the
index is 2 or higher, then some zero-input response may become unbounded. For example, if
A has eigenvalue 0 with index 2, then eAt contains the terms (I,  I). If a zero-input response
contains the term t, then it will grow unbounded.
4.2.1  Discretization
Consider the continuous-time state equation
|     |     |     |       | =      | +      |     |     |         |
| --- | --- | --- | ----- | ------ | ------ | --- | --- | ------- |
|     |     |     | x(t)  | Ax(t)  | Bu(t)  |     |     | (4.9)   |
|     |     |     |       | =      | +      |     |     |         |
|     |     |     | y(t)  | Cx(t)  | Du(t)  |     |     | (4.10)  |
If the set of equations is to be computed on a digital computer, it must be discretized. Because
|     |     | .   |     | .  x(t  | +   | x(r)  |     |     |
| --- | --- | --- | --- | ------- | --- | ----- | --- | --- |
T) -
|     |     | x(t) =  | 11m  |     | T   |     |     |     |
| --- | --- | ------- | ---- | --- | --- | --- | --- | --- |
r-o

|     |     |     |     |     | 4.2  Solution of LTI State Equations  | 91  |
| --- | --- | --- | --- | --- | ------------------------------------- | --- |
we can approximate (4.9) as
|     |     | +              |     | +       | +       |          |
| --- | --- | -------------- | --- | ------- | ------- | -------- |
|     |     | x(r  T) = xU)  |     | Ax(t)T  | Bu(t)T  | (4.11 )  |
=  =
If we compute xU) and y(t) only aU  kT for k  0,  I,  ... , then (4.11) and (4.10) become
|     |     | +               | +   |           | +        |     |
| --- | --- | --------------- | --- | --------- | -------- | --- |
|     |     | x«k  1)T) = (I  |     | TA)x(kT)  | TBu(kT)  |     |
=  +
|     |     | y(kT)  | Cx(kT)  |     | DU(kT)  |     |
| --- | --- | ------ | ------- | --- | ------- | --- |
This is a discrete-time state-space equation and can easily be computed on a digital computer.
This discretization is the easiest to carry out but yields the least accurate results for the same
T. We discuss next a different discretization.
If an  input u(1)  is  generated by  a digital computer followed  by  a  digital-to-analog
converter, then u(t) will be piecewise constant. This situation often arises in computer control
of control systems. Let
+
|     | u(t) = u(kT) =: u[k]  |     |     | forkT:5 t  | < (k  I)T  | (4.12)  |
| --- | --------------------- | --- | --- | ---------- | ---------- | ------- |
for k  =  O.  I.  2.  . ... This input changes values only at discrete-time instants. For this input,
the solution of (4.9) still equals (4.5). Computing (4.5) at t  =  kT and t  =  (k + l)T yields
tT
AkT  +
|     | x[k] := x(kT) = e |     | x(O)  | 10  | eA(kT-r)Bu(-r) dr  | (4.13)  |
| --- | ----------------- | --- | ----- | --- | ------------------ | ------- |
and
tH1)T
| +   |     | +  =  |     | +   |     |     |
| --- | --- | ----- | --- | --- | --- | --- |
x[k  I] := x«k  I)T)  eA(Hl)T xeD)  10  eA«k+l)T-r)Bu(r) dr  (4.14)
Equation (4.14) can be written as
|     |      | +  =  AkT  |                    | +                     |     |     |
| --- | ---- | ---------- | ------------------ | --------------------- | --- | --- |
|     | x[k  | I]  eAT [e | xeD)               | lkT eA(kT-r)BU(r)dr]  |     |     |
|     |      | l (k+llT   |                    |                       |     |     |
|     |      | +          | eA(kT+T-r)Bu(r)dr  |                       |     |     |
kT
which becomes, after substituting (4.12) and (4.13) and introducing the new variable Ct  :=
+
kT  T - r,
(IT
|     |     | x[k  +  I] = eAT x[k]  |     | +   | eACtdCt) Bu[k]  |     |
| --- | --- | ---------------------- | --- | --- | --------------- | --- |
Thus, if an input changes value only at discrete-time instants kT and if we compute only the
responses at t  =  kT, then (4.9) and (4.10) become
|     |     | +    | =                   |     | +       |         |
| --- | --- | ---- | ------------------- | --- | ------- | ------- |
|     |     | x[k  | I]  AdX(k]          |     | BdU[k]  | (4.15)  |
|     |     |      | =  Cdx[k] + Ddu[k]  |     |         | (4.16)  |
y[k]

92 STATE-SPACE SOLUTIONS AND REALIZATIONS
with
(foT
Bd = eATdr) B ( 4.17)
This is a discrete-time state-space equation. Note that there is no approximation involved in
this derivation and (4.15) yields the exact solution of (4.9) at t = kT if the input is piecewise
constant.
We discuss the computation of B d. Using (3.51), we have
{T ( 2r2)
10 I+Ar+A !+,,· dr
2
T2 T3 T4
= TI + -A + _A2 + _A3 +".
2! , 3! 4!
j
This power series can be computed recursively as in computing (3.51). If A is nonsingular,
then the series can be wrilten as, using (3.51),
Thus we have
(if A is nonsingular) (4.18)
Using this formula, we can avoid computing an infinite series.
The MATLAB function [ad, bd 1 = c 2 d (a, b, T) transforms the continuous-time state
equation in (4.9) into the discrete-time state equation in (4.15).
4.2.2 Solution of Discrete-Time Equations
Consider the discrete-time state-space equation
+ +
x[k I] = Ax[k] BU[k]
(4.19)
= +
y(k] Cx[k] Du(k]
where the subscript d has been dropped. It is understood that if the equation is obtained from
a continuous-time equation, then the four matrices must be computed from (4.17). The two
equations in (4.19) are algebraic equations. Once x[O] and u[k], k = O. I, ... , are given. the
response can be computed recursively from the equations.
The MATLAB function ds t ep computes unit-step responses of discrete-time state-space
equations. It also computes unit-step responses of discrete transfer functions; internally. it first
transforms the transfer function into a discrete-time state-space equation by calling t f 2 s s.
which will be discussed later. and then uses ds tep. The function dl s im, an acronym for
discrete linear simulation, computes responses excited by any input. The function step
computes unit-step responses of continuous-time state-space equations. Internally, it first uses
the function c2d to transform a continuous-time state equation into a discrete-time equation I
and then carries out the computation. If the function step is applied to a continuous-time I
transfer function, then it first uses t f 2 s s to transform the transfer function into a continuous
I
time state equation and then discretizes it by using c2d and then uses ds tep to compute the

|     |     |     | 4.3  | Equivalent State Equations  |     | 93  |
| --- | --- | --- | ---- | --------------------------- | --- | --- |
response. Similar remarks apply to 1 s im, which computes responses of continuous-time state
equations or transfer functions excited by any input.
In order to discuss the general behavior of discrete-time state equations. we will develop
a general form of solutions. We compute
|       | =      | +         |               |     |        |     |
| ----- | ------ | --------- | ------------- | --- | ------ | --- |
| x[l]  | Ax[O]  | Bu[O]     |               |     |        |     |
|       | =      | +         | 2 +           |     | +      |     |
| x[2]  | Ax[l]  | Bu[l] = A | x[0]  ABu[O]  |     | Bu[l]  |     |
Proceeding forward, we can readily obtain, for k > 0,
k- I
+
|     | x[k] = Akx[O]  | LAk-l-mBu[m]  |     |     |     | (4.20)  |
| --- | -------------- | ------------- | --- | --- | --- | ------- |
m=O
k-I
L
|     |                 | +   |               | +   |        |          |
| --- | --------------- | --- | ------------- | --- | ------ | -------- |
|     | y[k] = CAkx[O]  |     | CAk-l-mBu[m]  |     | Du[k]  | (4.21 )  |
111=0
They are the discrete counterparts of (4.5) and (·t 7). Their derivations are considerably simpler
than the continuous-time case.
We discuss a general property of the zero-input response A'x[O]. Suppose A has eigen
value AI with multiplicity 4 and eigenvalue A2 with multiplicity I and suppose its Jordan form
"2
is as shown in the second matrix in (3.39). In other words, AI  has index 3 and  has index I.
Then we have
|         | "k   | k·   k -I  | k(k - I)A7-2/2  | 0   |      |     |
| ------- | ---- | ---------- | --------------- | --- | ---- | --- |
|         | I    | A I        |                 |     | 0    |     |
|         |      | "k         | uk-I            |     |      |     |
|         | 0    | I          | I               | 0   | 0    |     |
|         |      |            | "k              |     | Q-I  |     |
| Ak = Q  | 0    | 0          |                 | 0   | 0    |     |
I
Ak
|     | 0   | 0   | 0   | I   | 0   |     |
| --- | --- | --- | --- | --- | --- | --- |
Ak
|     | 0   | 0   | 0   | 0   |     |     |
| --- | --- | --- | --- | --- | --- | --- |
2
7-
which implies that every entry of the zero-input response is a linear combination of i"~ . U  1
,
"7-
k2 2 A;}. These terms are dictated by the eigenvalues and their indices.
•
If every eigenvalue. simple or repeated. of A has magnitude less than I. then every zero
input response will approach zero as k -> 00. If A has an eigenvalue, simple or repeated. with
magnitude larger than I, then most zero-input responses will grow unbounded as k -> 00. If A
has some eigenvalues with magnitude I and all with index I and the remaining eigenvalues all
have magnitudes less than I. then no zero-input response will grow unbounded. However. if
the index is 2 or higher. then some zero-state response may become unbounded. For example.
if A has eigenvalue I with index 2, then A k contains the terms (I.  k). If a zero-input response
contains the term k. then it will grow unbounded as k -> cc.
4.3  Equivalent State Equations
The example that follows provides a motivation for studying equivalent state equations.
EXAMPLE 4.3  Consider the  network shown in  Fig. 4.1.  It consists of one capacitor. one
inductor, one resistor. and one voltage source. First we select the inductor current XI  and

94  STATE-SPACE SOLUTIONS AND REALIZATIONS
capacilOr voltage  X2  as state variables as shown. The voltage across the inductor is XI  and
the current through the capacitor is X2. The voltage across the resistor is  X2;  thus its current is
| =   |     | =   |     |     |     |
| --- | --- | --- | --- | --- | --- |
|     |     | +   | +   |     |     |
x2JI  X2. Clearly we have XI  X2  Xz and XI  X2 - U  = O. Thus the network is described
by the following state equation:
|     |     | y = [0  | IJx  |     | (4.22)  |
| --- | --- | ------- | ---- | --- | ------- |
If, instead, the loop currents XI  and X2 are chosen as state variables as shown, then the voltage
x
across the inductor is  and the voltage across the resistor is (XI - X2) . I. From the left-hand
I
side loop, we have
|     | =   |                |     | =        |        |
| --- | --- | -------------- | --- | -------- | ------ |
|     |     | +              | or  |          | +  +   |
|     | U   | XI  XI  - X21  |     | XI  -XI  | X2  U  |
t
The voltage across the capacitor is the same as the one across the resistor. which is XI  - X2.
x
X2,
| Thus the current through the capacitor is  |     |     | I - | which equals X2 or  |     |
| ------------------------------------------ | --- | --- | --- | ------------------- | --- |
Thus the network is also described by the state equation
(4.23)
|     |     | y = [I  | IJx  |     |     |
| --- | --- | ------- | ---- | --- | --- |
-
The state equations in (4.22) and (4.23) describe the same network; therefore they must be
closely related. In fact, they are equivalent as will be established shortly.
Consider the n-dimensional state equation
|     |     | xCt) = AxCt)  | +   | Bu(t)  |     |
| --- | --- | ------------- | --- | ------ | --- |
(4.24)
|     |     | yCt) = Cx(t)  | +   | Du(t)  |     |
| --- | --- | ------------- | --- | ------ | --- |
where A is an n x n constant matrix mapping an n-dimensional real space 'R" into itself. The
state x is a vector in 'R" for all t; thus the real space is also called the state space. The state
equation in (4.24) can be considered to be associated with the orthonormal basis in (3.8). Now
we study the effect on the equation by choosing a different basis.
----..l/
| /I- ,,.:,+--x,  |     |     |                             | Figure 4.1  | Network with two different  |
| --------------- | --- | --- | --------------------------- | ----------- | --------------------------- |
| x,              |     |     | r sets of state variables.  |             |                             |
I H  +r
~IF
1
|     |     | .:Y  .=-L  |     |     |     |
| --- | --- | ---------- | --- | --- | --- |
X2
| L-______  | ____  |     |     |     |     |
| --------- | ----- | --- | --- | --- | --- |
| ~~        |       | ~   |     |     |     |

|     |     |     |     |     |     |     |     | 4.3  Equivalent State Equations  |     |     | 95  |
| --- | --- | --- | --- | --- | --- | --- | --- | -------------------------------- | --- | --- | --- |
Definition 4.1 Let P be an n x n real nonsingular matrix and let  x  = Px. Then the stute
equation,
+
|     |     |     |     |     | x(t) = Ax(t)  |     | Bu(t)  |     |     |     |     |
| --- | --- | --- | --- | --- | ------------- | --- | ------ | --- | --- | --- | --- |
(4.25)
|     |     |     |     |     | =     |        | +      |     |     |     |     |
| --- | --- | --- | --- | --- | ----- | ------ | ------ | --- | --- | --- | --- |
|     |     |     |     |     | yet)  | Cx(t)  | Du(t)  |     |     |     |     |
where
|     |     |     | A = PAP-I  |     |     |     | C   | =  cp-I  |     |     | (4.26)  |
| --- | --- | --- | ---------- | --- | --- | --- | --- | -------- | --- | --- | ------- |
x
is said to be (algebraically) equivalent to (4.24) and  =  Px is called an equivalence
transformation.
Equation (4.26) is obtained from  (4.24) by substituting x(t)  =  p-Ix(t) and x(t)  =
P- Ix(t). In this substitution, we have changed, as in Equation (3.7), the basis vectors of the
state space from the orthonormal basis to the columns ofP- 1 =: Q. Clearly A and A are similar
=  I =
andA is simply a different representation ofA. Tobeprecise,letQ  p- [ql  q2  ...  qnl.
A
Then the ith column of  is, as discussed in Section 3.4, the representation of Aqi with respect
|                    |     |      |         | qn}· From the equation 13 =  |     |     |     |          | =  p-I 13 =  |         |            |
| ------------------ | --- | ---- | ------- | ---------------------------- | --- | --- | --- | -------- | ------------ | ------- | ---------- |
| to the basis {ql,  |     | q2.  | . .. ,  |                              |     |     |     | PB or B  |              | [ql ql  | ... qnlB,  |
we see that the ith column of 13 is the representation of the ith column of B with respect to the
I
basis {q I,  q2,  "', qn}. The matrix C is to be computed from Cp- , The matrix D, called the
direct transmission part between the input and output, has nothing to do with the state space
and is not affected by the equivalence transformation,
We show that (4.14) and (4.25) have the same set of eigenvalues and the same transfer
=
| matrix. Indeed, we have. using det(P) det(p-I)  |         |     |                 |     |               |     | I,       |     |            |          |     |
| ----------------------------------------------- | ------- | --- | --------------- | --- | ------------- | --- | -------- | --- | ---------- | -------- | --- |
|                                                 |         | =   |                 |     | =             |     |          | =   |            |          |     |
|                                                 | ~().,)  |     | det(AI -        | A)  | det().,pp-I - |     | PAP-I)   |     | det[P('u - | AlP- II  |     |
|                                                 |         | =   |                 |     |               |     | =        |     | =          |          |     |
|                                                 |         |     | det(P) det('u - |     | A) det(p-I)   |     | det('u - |     | A)  6      | ().,)    |     |
and
|     |          |     |            |        | + D        |             |     |            |        | + D       |     |
| --- | -------- | --- | ---------- | ------ | ---------- | ----------- | --- | ---------- | ------ | --------- | --- |
|     | (;(s) =  |     | C(sI -     | A)-IB  | =          | CP-I[P(sI - |     | AlP-lrlpS  |        |           |     |
|     |          | =   |            |        |            | +           | =   |            | +      | =         |     |
|     |          |     | CP-Ip(sl - |        | A)-lp-lpB  |             | D   | C(sI -     | A)-IB  | D  (;(s)  |     |
Thus equivalent state equations have the same characteristic polynomial and, consequently, the
same set of eigenvalues and same transfer matrix. In fact, all properties of (4.24) are preserved
or invariant under any equivalence transformation.
Consider again the network shown in Fig. 4.1. which can be described by (4.12) and (4.23).
We show that the two equations are equivalent. From Fig. 4.1. we have XI  = .rl. Because the
voltage across the resistor is xz, its current is xl/I and equals Xl  - Xl. Thus we have
|     |     |     |     |     |     | [1  | 0]  |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
['~l]
XI] =
[
|     |     |     |     |     |     | I   | -1  |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     |     | Xl  |     |     | Xz  |     |     |     |
or
|     |     |     | l   | [1  |           |     |     | [1      |     |     |         |
| --- | --- | --- | --- | --- | --------- | --- | --- | ------- | --- | --- | ------- |
|     |     |     |     | ]   | O]-I[XI]  |     |     |         |     |     |         |
|     |     |     | .r  |     |           |     |     | O][XI]  |     |     |         |
|     |     |     | [   |     |           |     |     |         |     |     | (4.27)  |
|     |     |     | Xl  | -   | 1  -I     | Xl  | -   | 1  -I   | X2  |     |         |

96  STATE-SPACE SOLUTIONS AND REALIZATIONS
Note that. for this P, its inverse happens to equal itself. It is straightforward to verify that (4.22)
and (4.23) are related by the equivalence transformation in (4.26).
The MAT LAB function  [ab, bb, cb, db 1 ;55255 (a, b, c, d, p) carries out equiv
alence transformations.
Two state equations are said to be ~ero-state equivalent if they have the same transfer
matrix or
This becomes, after substituting (3.57).
0+ CBS-I + CABs-2 + CA~Bs-J + ...  D + CEs-1 + CABs-2 + CA~Es-3 + ...
=
Thus we have the theOiem that follows.
>-
Theorem 4.1
(A.  E,  C, D)
Two linear time-invariant state equations (A.  B.  C.  D) and  are zero-state equivalent
= D
or have the same transfer matrix if and only if 0  and
|     |     |     | m = 0,  | I, 2,  ...  |     |     |
| --- | --- | --- | ------- | ----------- | --- | --- |
It is clear that (algebraic) equivalence implies zero-state equivalence. In order for two
state equations to be equivalent, they must have the same dimension. This is. however, not the
case for zero-state equivalence, as the next example shows.
EXAMPLE 4.4  Consider the two networks shown in Fig. 4.2. The capacitor is assumed to have
capacitance -I F. Such a negative capacitance can be realized using an op-amp circuit. For the
|     |     | =   | =   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
circuit in Fig. 4.2(a), we have y(t)  0.5· u(t) or yes)  0.5u(s). Thus its transfer function is
0.5. To compute the transfer function of the network in Fig. 4.2(b), we may assume the initial
voltage across the capacitor to be zero. Because of the symmetry of the four resistors. half of
=
the current will go through each resistor or itt)  0.5u(t), where itt) denotes the right upper
|     |     | =   | =   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
resistor's curren!. Consequently, y(t)  i(t)· I  0.511(t) and the transfer function also equals
0.5. Thus the two networks, or more precisely their state equations, are zero-state equivalent.
This fact can also be verified by using Theorem 4.1. The network in Fig. 4.2(a) is described
|     |     |     | =   | =  =  | =   | =   |
| --- | --- | --- | --- | ----- | --- | --- |
by the zero-dimensional state equation y(t)  0.511(t) or A  B  C  0 and 0  0.5. To
ir
|     |     |     |     | Figure 4.2  | Two zero-state  |     |
| --- | --- | --- | --- | ----------- | --------------- | --- |
--+-+
equivalent networks.
|     |     | u - | i   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
I
|     | )'  | In  | In  Y  |     |     |     |
| --- | --- | --- | ------ | --- | --- | --- |
a.5r1
|     | ~   |     | x  ~  |     |     |     |
| --- | --- | --- | ----- | --- | --- | --- |
t
| u   | u  t  |     |     |     |     |     |
| --- | ----- | --- | --- | --- | --- | --- |
x
|        |     |      | - IF           |     |     |     |
| ------ | --- | ---- | -------------- | --- | --- | --- |
| a.5r1  |     | In   | In             |     |     |     |
|        |     | u -  | i +.(  i - ,(  |     |     |     |
| (a)    |     | (bl  |                |     |     |     |

|     |     |     |     |     |     |     | 4.3  | Equivalent State Equations  |     | 97  |
| --- | --- | --- | --- | --- | --- | --- | ---- | --------------------------- | --- | --- |
l  develop a state equation for the network in Fig. 4.2(b), we assign the capacitor voltage as state
| 'j  |     |     |     |     |     | x   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
variable x with polarity shown. Its current is  flowing from the negative to positive polarity
~,
because of the negative capacitance. If we assign the right upper resistor's current as ; (tl. then
x,
..J  the right lower resistor's current is ; - the left upper resistor's current is u - ;, and the left
| I   |     |     |     | +   |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
i   lower resistor's current is II  - ;  X. The total voltage around the upper right-hand loop is 0:
1
+
|     |     |     | i-x - |     | (u -;) = 0  | or  | ; = O.S(x  | u)  |     |     |
| --- | --- | --- | ----- | --- | ----------- | --- | ---------- | --- | --- | --- |
.i
which implies
1
1
|     |     |     |     |     | =         | =  =      | +   |     |     |     |
| --- | --- | --- | --- | --- | --------- | --------- | --- | --- | --- | --- |
| ,   |     |     |     |     | y  I . ;  | i  0.5(x  |     | u)  |     |     |
!
j
The total voltage around the lower right-hand loop is 0:
i
]
|     |     |     |     |     | +         |       | +        |     |     |     |
| --- | --- | --- | --- | --- | --------- | ----- | -------- | --- | --- | --- |
|     |     |     |     | x   | (i - x) - | (II - | i  x) =  | 0   |     |     |
;j  which implies
|       |     |     |     | 2.r = 2; +  |     | +       | +   |         |     |     |
| ----- | --- | --- | --- | ----------- | --- | ------- | --- | ------- | --- | --- |
| ~     |     |     |     |             | x - | = X     |     | u = 2x  |     |     |
| .,j   |     |     |     |             |     | II  II  | X   | -       |     |     |
j
Thus the network in Fig. -I.2(b) is described by the one-dimensional state equation
J
| •   |     |     |     |     | .i·(t) = x(l)  |     |     |     |     |     |
| --- | --- | --- | --- | --- | -------------- | --- | --- | --- | --- | --- |
j
|     |     |     |     |     | y(t) = O.Sx(t)  | +   |     |     |     |     |
| --- | --- | --- | --- | --- | --------------- | --- | --- | --- | --- | --- |
0.5u(l)
|       | A =  | B =  | C =  |           | D =  |                     |     | = D =  |               | =   |
| ----- | ---- | ---- | ---- | --------- | ---- | ------------------- | --- | ------ | ------------- | --- |
| with  |      | I,   | 0,   | 0.5, and  |      | 0.5. We see that D  |     |        | 0.5 and CAmB  |     |
CAmB
= 0 for m = 0,  l. .... Thus the two equations are zero-state equivalent.
| 4.3.1  | Canonical Forms  |     |     |     |     |     |     |     |     |     |
| ------ | ---------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
MATLAB contains the function  lab, bb, cb, db, P] =canon (a , b, c , d ,  ' t ype ' ). If
type=companion, the function will generate an equivalent state equation with A in the
|     |     |     |     |     |     |     |     |     | An 1bd is  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ---------- | --- |
companion form  in  (3.2-1).  This  function  works only if Q  :=  [bl  Abl  ...  -
nonsingular, where bl is the first column ofB. This condition is the same as {A,  bl} controllable,
as we will discuss in Chapter 6. The P that the function c anor, generates equals Q
|     |     |     |     |     |     |     |     |     | - 1. See the  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ------------- | --- |
discussion in Section 3.4.
We discuss a different canonical form.  Suppose A  has two real eigenvalues and two
complex eigenvalues. Because A has only real coefficients, the two complex eigenvalues must
be complex conjugate. Let AI, A2, Ct  + if], and a  - if] be the eigenvalues and ql, Q2, q). and
q~ be the corresponding eigenvectors. where II.!, A2, Ct, f], ql, and qz are all real and q~ equals
the complex conjugate of q). Define Q = [ql
qz  q3 q~l. Then we have
o
|     |     |     |     | AI  |     | 0   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
.Ll
o
J .- 0
.- 0
|     |     |     |     |     | o   | + if3  |     |     |     |     |
| --- | --- | --- | --- | --- | --- | ------ | --- | --- | --- | --- |
a
[
|     |     |     |     | o   | o   | o   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Note that Q and J can be obtained from  [q, j ] =e ig (a) in MATLAB as shown in Examples
3.5 and 3.6. This form is useless in practice but can be transformed into a real matrix by the
following similarity transformation

98  STATE-SPACE SOLUTIONS AND REALIZATIONS
o
.L]
o
+
|     |     |     |     |     |     |     | Ct  jfJ  |     |     |
| --- | --- | --- | --- | --- | --- | --- | -------- | --- | --- |
o
o
~  ~]
-
Ct  fJ  =: A
-fJ  Ct
We  see that this transformation transforms the complex eigenvalues on the diagonal  into
a block with the real  part of the eigenvalues on the diagonal and the imaginary part on
the off-diagonal. This new A-matrix is sllid to be  in modal form. The MATLAB function
(ab,bb,cb,db,Pl=canon(a,b,c,td ,  'modal')  or canon(a,b,c,d)
with  no
A
type specified will yield an equivalent state equation with  in modal form. Note that there is
no need to transform A into a diagonal form and then to a modal form. The two transformations
can be combined into one as
|     |     |     |     |     |     | ['  | 0  0  |     |     |
| --- | --- | --- | --- | --- | --- | --- | ----- | --- | --- |
0
|     |     | I          | -   |      |             |     | 0  I    | -:Sj]  |     |
| --- | --- | ---------- | --- | ---- | ----------- | --- | ------- | ------ | --- |
|     |     | P- = QQ =  |     | [ql  | q2  q3 q4]  |     | ~       |        |     |
|     |     |            |     |      |             |     | 0  0.5  |        |     |
|     |     |            |     |      |             |     | 0  0.5  | O.Sj   |     |
=  [ql q2 Re(q3) [m(q3)]
where Re and 1m stand, respectively, for the real part and imaginary part and we have used in
the last equality the fact that q4 is the complex conjugate of q3. We give one more example. The
modal form of a matrix with real eigenvalue A I  and two pairs of distinct complex conjugate
| eigenvalues Cti  | ± jfJi, for i =  |     |     | J, 2, is  |     |     |       |     |     |
| ---------------- | ---------------- | --- | --- | --------- | --- | --- | ----- | --- | --- |
|                  |                  |     |     |           | 0   | 0   | 0  0  |     |     |
AI
|     |     |     |     |     |       |      | 0  0  |     |         |
| --- | --- | --- | --- | --- | ----- | ---- | ----- | --- | ------- |
|     |     |     |     | 0   | Ctl   | fJl  |       |     |         |
|     |     |     | A=  | 0   | -fJl  | Ctl  | 0  0  |     | (4.28)  |
0  0
|     |     |     |     | 0   |     |     | Ct2  fJ2   |     |     |
| --- | --- | --- | --- | --- | --- | --- | ---------- | --- | --- |
|     |     |     |     | 0   | 0   | 0   | -f32  0'2  |     |     |
It is block diagonal and can be obtained by the similarity transformation
where ql. qz. and q4 are. respecti vely, eigenvectors associated with A1 -0' I  +  j fJl, and Ctz  +  j fJz.
This form is useful in state-space design.
4.3.2  Magnitude Scaling in Op-Amp Circuits
As discussed in Section 2.3.1. every LTI state equation can be implemented using an op-amp
circuit.! In actual op-amp circuits, all signals are limited by power supplies. If we use ± IS-volt
I. This subsection may be skipped without loss of continuity.

4.3 Equivalent State Equations 99
power supplies, then all signals are roughly limited to ± 13 volts. If any signal goes outside
the range, the circuit will saturate and will not behave as the state equation dictates. Therefore
saturation is an important issue in actual op-amp circuit implementation.
Consider an LTI state equation and suppose all signals must be limited to ±M. For linear
systems, if the input magnitude increases by a, so do the magnitudes of all state variables
and the output. Thus there must be a limit on input magnitude. Clearly it is desirable to have
the admissible input magnitude as large as possible. One way to achieve this is to use an
equivalence transformation so that
for all i and for all t. The equivalence transformation, however, will not alter the relationship
between the input and output; therefore we can use the original state equation to find the input
range to achieve ly(t)1 ::: M. In addition, we can use the same transformation to amplify some
state variables to increase visibility or accuracy. This is illustrated in the next example.
EXAMPLE 4.5 Consider the state equation
X=[-0°. 12]X+[IO]U
-I 0.1
y=[O.1 -1]x
Suppose the input is a step function of various magnitude and the equation is to be implemented
using an op-amp circuit in which all signals must be limited to ± I 0. First we use MATLAB
to find its unit-step response. We type
a~[-O.l 2;0 -lJ;b~[10;O.ll;c~[0.2 -lJ;d~O;
[y,x,tl~step(a,b,c,d) ;
plot(t,y,t,x)
which yields the plot in Fig. 4.3(a). We see that IXllmax = 100 > IYlmax = 20 and
IX21 « Iylmax, The state variable X2 is hardly visible and its largest magnitude is found
to be 0.1 by plotting it separately (not shown). From the plot, we see that if lu(l)1 ::: 0.5, then
the output will not saturate but Xl (t) will.
Let us introduce new state variables as
20 _ 20
Xl = -Xl = 0.2Xl xo = -x' = 200x,
100 " 0.1 - -
With this transformation. the maximum magnitudes of Xl (t) and .1'2 (t) will equally Imax. Thus
if yet) does not saturate. neither will all the state variables .ii' The transformation can be
x =
expressed as Px with
[5 0 ]
0.2
P= 2~] p-1 _
[ o
o 0.005
Then its equivalent state equation can readily be computed from (4.26) as
[-0.\
X ~ = 0.002]_x + [2] It
° -\ 20
Y = [\ - 0.005]x

100  STATE-SPACE SOLUTIONS AND REALIZATIONS
.t~
| 100  |     | 10   |     |
| ---- | --- | ---- | --- |
| 80   |     | 8  i | V   |
l
| 60  |     | 6   |     |
| --- | --- | --- | --- |
| 40  |     | 4   |     |
Y
| 20  |     | 2   |     |
| --- | --- | --- | --- |
0
40
| 10  20  | 30  40  | 0  10  | 20  30  |
| ------- | ------- | ------ | ------- |
|         | (al     |        | Ib)     |
Figure -13  Time responses.
Its step responses due to u(t) = 0.5 are plotted in Fig. 4.3(b). We see that all signals lie inside
the range ± 10 and occupy the full scale. Thus the equivalence state equation is better for
op-amp circuit implementation or simulation.
The magnitude scaling is important in using op-amp circuits to implement or simulate
continuous-time systems. Although we discuss only step inputs, the idea is applicable to any
input. We mention that analog computers are essentially op-amp circuits. Before the advent of
digital computers, magnitude scaling in analog computer simulation was carried out by trial
and error. With the help of digital computer simulation, the magnitude scaling can now be
carried out easily.
4.4  Realizations
Every linear time-invariant (LTI) system can be described by the input-outputdescription
yes) =
(;(5)6(5)
and. if the system is lumped as well, by the state-space equation description
+
|     | xU) = Ax(t)  | Bu(t)  |     |
| --- | ------------ | ------ | --- |
(4.29)
|     | yet) =  +  |     |     |
| --- | ---------- | --- | --- |
CX(IJ  Du(t)
=
If the state equation is known. the transfer matrix can be computed as (;(5)  Cis I -A)-I B+D.
The computed transfer matrix is unique. Now we study the converse problem, that is. to find a
state-space equation from a given transfer matrix. This is called the reali:ation problem. This
terminology is justitied by the fact that, by using the state equation. we can build an op-amp
circuit for the transfer matrix.
A transfer matrix (;(05)  is said to be reali:ahle if there exists a finite-dimensional state
equation (4.29) or. simply. IA. B. C, Dl such that
+ D
|     | (;(5) = C(sI - A)- | IB  |     |
| --- | ------------------ | --- | --- |

|     |     |     |     |     |     | 4.4  Realizations  | 101  |
| --- | --- | --- | --- | --- | --- | ------------------ | ---- |
and {A, B, C, OJ is called a realization of G(s), An LTI distributed system can be described
by a transfer matrix, but not by a finite-dimensional state equation, Thus not every C(s) is
realizable, If C(s) is realizable, then it has infinitely many realizations, not necessarily of
the same dimension, Thus the realization problem is fairly complex, We study here only the
realizability condition. The other issues will be studied in later chapters.
Theorem 4.2
:~~
A transfer matrix C(s) is realizable if and only if C(s) is a proper rational matrix.
We use (3.19) to write
| -                |     |     |          |          | I           |       |         |
| ---------------- | --- | --- | -------- | -------- | ----------- | ----- | ------- |
| Gsp(s) := C(sl - |     |     | A)-IB =  |          | C[Adj (51 - | A)]B  | (4.30)  |
|                  |     |     |          | det(sl - | A)          |       |         |
If A is n x Il, then det (51 - A) has degree n. Every entry of Adj (51 - A) is the determinant
of an (n - I) x (n - I) submatrix of (51 - A): thus it has at most degree (Il - I). Their linear
combinations again have at most degree (11  - I). Thus we conclude that C(sl - A)-IB is a
+
strictly proper rational matrix. If 0 is a nonzero matrix, then C(sl - A)-I B  0  is proper. This
shows that if C(s) is realizable, then it is a proper rational matrix. Note that we have
= 0
C(ee)
Next we show the converse; that is, if G(s) is a q x p proper rational matrix, then there
exists a realization. First we decompose C(s) as
|     |     | G(s) = G(ee)  A  |     | A  + A  | Gsp(s)  |     | (4.31)  |
| --- | --- | ---------------- | --- | ------- | ------- | --- | ------- |
where Csp is the strictly proper part of C(s). Let
|     |            |     | +    | I + ... +  | +          |     |         |
| --- | ---------- | --- | ---- | ---------- | ---------- | --- | ------- |
|     | des) = sr  |     | alsr |            | ar_ls  ar  |     | (4.32)  |
-
be the least common denominator of all entries of Gsp(s). Here we require des) to be monic;
that is, its leading coefficient is 1. Then Csp(s) can be expressed as
(433)
where Ni  are q x  p constant matrices. Now we claim that the set of equations
|     | -all  | -a,1  |     | -ar_ll | -arlp  | Ip  |     |
| --- | ----- | ----- | --- | ------ | ------ | --- | --- |
|     | p     | -     | p   |        | p      |     |     |
Ip
|     |     | 0   |     | 0   | 0   | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
| x=  | 0   | Ip  |     | 0   | 0   | 0   |     |
x+  u
(4.34)
|     | 0   | 0   |     |     | 0   | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
Ip
| =   |          | .. ·Nr_ | Nr] x + C(oo)u  |     |     |     |     |
| --- | -------- | ------- | --------------- | --- | --- | --- | --- |
| Y   | [NI  N2  |         | 1               |     |     |     |     |

1
102 STATE-SPACE SOLUTIONS AND REALIZATIONS
is a realization of G(s). The matrix Ip is the p x p unit matrix and every 0 is a p x p zero matrix.
The A-matrix is said to be in block companion form; it consists of r rows and r columns of
p x p matrices; thus the A-matrix has order rp x rp. The B-matrix has order rp x p. Because
the C-matrix consists of r number ofN;, each of order q x p, the C-matrix has order q x rp.
The realization has dimension r p and is said to be in controllable canonical form.
We show that (4.34) is a realization of G(s) in (4.31) and (4.33). Let us define
Zt
Zz
Z:= (4.35)
Zr
where Z; is p x p and Z is rp x p. Thell,i the transfer matrix of (4.34) equals
t • •
C(sl - A)- B + G(oo) = N\Zt + N Z + .. . + NrZr + G(oo) (4.36)
2 2
We write (4.35) as (sl - A)Z = B or
sZ = AZ+B (4.37)
Using the shifting property of the companion form of A, from the second to the last block of
equations in (4.37), we can readily obtain
which implies
Substituting these into the first block of equations in (4.37) yields
or, using (4.32),
Thus we have
S,-2
=
Zo --I
• des) p'
Substituting these into (4.36) yields
. I .
C(sl - A)-tB + G(oo) = _[Nts r - t + Nzsr - 2 + ... + Nrl + G(oo)
des)
This equals G(s) in (4.31) and (4.33). This shows that (4.34) is a realization ofG(s).

|     |     |     |     |     |     |     |     | 4.4  Real izations  | 103  |
| --- | --- | --- | --- | --- | --- | --- | --- | ------------------- | ---- |
EXAMPLE 4.6  Consider the proper rational matrix
|     |     |     |     | 10  |     | 3]  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
4s -
|     | G(s) =  |     |     | 2stl  |     | ~!~  |     |     |     |
| --- | ------- | --- | --- | ----- | --- | ---- | --- | --- | --- |
[
|     |     |     |      | +  +  |         | +    |     |     |     |
| --- | --- | --- | ---- | ----- | ------- | ---- | --- | --- | --- |
|     |     |     | (2s  | l)(s  | 2)  (s  | 2)"  |     |     |     |
(4.38)
-12
|     |     | =[~  |     | ~]+  |     |     |     |     |     |
| --- | --- | ---- | --- | ---- | --- | --- | --- | --- | --- |
2stl
[
|     |     |     |     | (2s +  |     | +   |     |     |     |
| --- | --- | --- | --- | ------ | --- | --- | --- | --- | --- |
l)(s  2)
where we have decomposed G(s) into the sum of a constant matrix and a strictly proper rational
+  +
matrix Gsp(s). The monic least common denominator of Gsp(s) is des) =  (s  0.5)(s  2)" =
+  4.5s2 +  +
s3  6s  2. Thus we have
[-6(S
| •         |     |     |        | 1      |        | +  2)2  | 3(s  | +  2)(s  +  0.5)]  |     |
| --------- | --- | --- | ------ | ------ | ------ | ------- | ---- | ------------------ | --- |
|           |     | +   |        | +  +   |        | +       |      | +  +               |     |
| Gsp(s) =  |     | s3  | 4.552  | 6s  2  | 0.5(s  | 2)      | (s   | l)(s  0.5)         |     |
3
05])
|     |     | d~S)  | ~6  | ~]  | [~~54  | ~:~]  |     | [-~4  |     |
| --- | --- | ----- | --- | --- | ------ | ----- | --- | ----- | --- |
|     |     |       |     | +   |        |       |     | +     |     |
|     | =   |       | ([  | s2  |        |       | s   |       |     |
,.
and a realization of (4.38) is
| -4.5  |     | 0   |     | -6  0  |     | -2  | 0   |     |     |
| ----- | --- | --- | --- | ------ | --- | --- | --- | --- | --- |
0
"
|     | 0  -4.5  |     |     | 0  -6  |     | 0   | -2  | 0   |     |
| --- | -------- | --- | --- | ------ | --- | --- | --- | --- | --- |
[:J
0  0
|     |     | 0   |     | 0  0  |     | 0   | 0   |     |     |
| --- | --- | --- | --- | ----- | --- | --- | --- | --- | --- |
| X=  |     |     |     |       |     |     |     | x+  |     |
0  0
|     | 0   |     |     | 0  0  |     | 0   | 0   |     |     |
| --- | --- | --- | --- | ----- | --- | --- | --- | --- | --- |
0
0
|     | 0   | 0   |     | 0   |     | 0   | 0   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
0  0
|       | 0   | 0    |      | 0  1  |         | 0   | 0   |       |         |
| ----- | --- | ---- | ---- | ----- | ------- | --- | --- | ----- | ------- |
|       | 3   | -24  | 7.5  | -24   |         |     |     | [::]  |         |
| [ -6  |     |      |      |       |         |     | [~  | ~]    | (4.39)  |
| Y=    |     |      |      |       | 03J x+  |     |     |       |         |
| 0     |     | 0.5  |      | 1.5   |         |     |     |       |         |
This is a six-dimensional realization.
We discuss a special case of (4.31) and (4.34) in which p =  l. To save space. we assume
=  =
r  4 and q  2. However. the discussion applies to any positive integers rand q. Consider
the 2 x  1 proper rational matrix
]+
|     |     | G(S)=[dl |                    |          |        | 1     |        |         |         |
| --- | --- | -------- | ------------------ | -------- | ------ | ----- | ------ | ------- | ------- |
|     |     |          |                    | S4 + als | 3 +    |       | +      | +       |         |
|     |     |          | d                  | 2        |        | a2s2  | a      | 3s  a4  |         |
|     |     |          |                    | +  s2 +  |        | S +   |        |         |         |
|     |     |          | /3lls3             | /312     | /3I3   |       | /314]  |         | (4.40)  |
|     |     |          | [ /321S3 + /322s2  |          | +      | +     |        |         |         |
|     |     |          | .                  |          | /3"3S  |       | fiN    |         |         |

104  STATE-SPACE SOLUTIONS AND REALIZATIONS  f
Then its realization can be obtained directly from (4.34) as
|     |     |     | [_a  |       | -;']  |     | [:]  |     |
| --- | --- | --- | ---- | ----- | ----- | --- | ---- | --- |
|     |     |     |      | -a2   | -a3   |     |      |     |
|     |     | .   |      | I  0  | 0     |     |      |     |
o
|     |     | x=  |     |       |     | x   | +   | 0  u  |
| --- | --- | --- | --- | ----- | --- | --- | --- | ----- |
|     |     |     |     | 0  I  | 0   |     |     |       |
o  (4.41 )
|     |     |      |       | 0  0             |           |     |        | 0   |
| --- | --- | ---- | ----- | ---------------- | --------- | --- | ------ | --- |
|     |     |      |       | 11  .81 !  .813  |           |     |        |     |
|     |     |      |       |                  | .81J] X+  |  [  | l      |     |
|     |     | Y =  | [.8   |                  |           | d   | ]  !I  |     |
|     |     |      | .8!1  |                  | .82.      | d2  |        |     |
|     |     |      |       | .8!"  fh3        |           |     |        |     |
This controllable-canonical-form realization can be read out from the coefficients of G(s) in
(4"+0).
There are  many  ways to realize a proper transfer matrix.  For example. Problem 4.9
gi\es a different realization of (4.33) with dimension rq. Let Gei(s)  be the ith column of
G(5) and let !Ii  be the ith component of the input vector u. Then Yes)  =  G(S)U(5) can be
ex pressed as
|     | Yes) = Gel (S)IJ 1(5)  |     |     | +           | + ...  | =:  YcI  |      | + Yc21s) + ...  |
| --- | ---------------------- | --- | --- | ----------- | ------ | -------- | ---- | --------------- |
|     |                        |     |     | GdS)LI2(S)  |        |          | (5)  |                 |
as shown in Fig. 4.4(a). Thus we can realize each column of G(s) and then combine them to
yield a realization of G(s). Let  G (5) be the ith row of G(s) and let Yi  be the ith component
ri
=
of the output vector y. Then yes)  G(s)u(s) can be expressed as
,\-i(S) = Gn(S)ti(s)
as shown in Fig. 4.4(b). Thus we can realize each row ofG(s) and then combine them to obtain
a realization of G(s). Clearly we can also realize each entry of G(s) and then combine them
to obtain a realization of G(s). See Reference [6. pp. 158-160].
The MATLAB function  [a, b, C , d 1 = t f 2 s s (num, den) generates the controllable
canonical-form realization shown in (4.41) for any single-input multiple-output transfer matrix
GCs). In its employment, there is no need to decompose G(s) as in (4.31). But we must compute
its least common denominator, not necessarily monic. The next example will apply t f2ss to
each column of G(s) in (4.38) and then combine them to form a realization of G(s).
|     |     |     |     |     |     | Figure 4A  |     | Realizalions of G(s) by  |
| --- | --- | --- | --- | --- | --- | ---------- | --- | ------------------------ |
y"
| G .. ,ls)  r--~  |     |     |     | G"  |     | columns and by rows.  |     |     |
| ---------------- | --- | --- | --- | --- | --- | --------------------- | --- | --- |
Is)
|     | y   | u   |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Ib)

|     |     |     |     |     |     |     | 4.4  Realizations  | lOS  |
| --- | --- | --- | --- | --- | --- | --- | ------------------ | ---- |
EXAMPLE 4.7  Consider thte p roper rational matrix in (4.38). Its first column is
~,
| •   |     |     |     | 1   |     | 1   |     | 1   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
20
|     |        |     | ~5  I~  |     | (~5 ~ \~)(~  | 2~)   | [~:2 ~ J5~   |     |
| --- | ------ | --- | ------- | --- | ------------ | ----- | ------------ | --- |
| i   | Gel    |     |         |     |              |       |              | 2   |
|     | (5) =  | [   |         | =   | [            | :  =  |              |     |
-1
,J
I
|     |     | (25 + 1)(5 + 2)  |     |     | 2s' + 55 + 2  |     | 2s2 + 55 + 2  |     |
| --- | --- | ---------------- | --- | --- | ------------- | --- | ------------- | --- |
;
!  Typing
|     | 01=[4  | -2  -20;0 | 0  1];d:=[2  |     | 5  2];          |     |            |     |
| --- | ------ | --------- | ------------ | --- | --------------- | --- | ---------- | --- |
|     |        |           |              |     | :a,c,c,::>tf2~s |     | (n: , d1i  |     |
yields the following realization for the first column of G(.,):
,
·
| 1   |     |     |     |     |     | [2]  |     |     |
| --- | --- | --- | --- | --- | --- | ---- | --- | --- |
.:'
|     |     |     |     |     |     | -12]  +  |       |     |
| --- | --- | --- | --- | --- | --- | -------- | ----- | --- |
|     |     |     |     |     |     | 0.5  0   |       |     |
|     |     |     |     |     |     | XI       | II I  |     |
,  Si~ilarly, the function t f2 s s can generate the following realization for the second column
'j
of G(5):
:~,
| ·',1   |     |     |     |     | -4  |     |     |     |
| ------ | --- | --- | --- | --- | --- | --- | --- | --- |
, +
|      |     | )(0 |   = A ox | b1-1-11  | =    |     |     |     |
| ---- | --- | --- | -------- | -------- | ---- | --- | --- | --- |
| · i  |     |     | - -      | -        | [ I  |     |     |     |
";
| .!,   |     |     |     |     |     |     |     | (443)  |
| ----- | --- | --- | --- | --- | --- | --- | --- | ------ |
·
.1,
'1
.
.~
1
These two realizations can be combined as
i
'1,
!
:
or
[T
-I  0
~l+[~
|     |     | x   | -   | 0   | 0   |      |     |     |
| --- | --- | --- | --- | --- | --- | ---- | --- | --- |
|     |     | .   |  -  |     |     | ll"  |     |     |
0  -4
(4.44 )
0
|     |     |     |       | -12  | 3       |      |     |     |
| --- | --- | --- | ----- | ---- | ------- | ---- | --- | --- |
|     |     |     | [ -6  |      | ~]x+[~  | ~]u  |     |     |
Y=
0  05
This is a different realization of the G(s) in (4.38). This realization has dimension 4, two less
than the one in (4.39).
The two state equations in (4.39) and (4.44) are zero-state equivalent because they have
the same transfer matrix. They are. however, not algebraically equivalent. More will be said

106  STATE-SPACE SOLUTIONS AND REALIZATIONS
in Chapter 7 regarding realizations. We mention that all discussion in this section, including
t f 2 5 5, applies without any modification to the discrete-time case
4.5  Solution of Linear Time-Varying (LTV) Equations
Consider the linear time-varying (LTV) state equation
|     |     |     |     | =     |           | +         |     |     |     |         |
| --- | --- | --- | --- | ----- | --------- | --------- | --- | --- | --- | ------- |
|     |     |     |     | x(I)  | A(t)x(t)  | B(t)u(t)  |     |     |     | (4.45)  |
+
|     |     |     |     | y(t) = C(t)x(t)  |     | D(t)u(t)  |     |     |     | (4.46)  |
| --- | --- | --- | --- | ---------------- | --- | --------- | --- | --- | --- | ------- |
It is assumed that, for every initial state f(to) and any input u(t), the state equation has a
unique solution. A sufficient condition forfsuch an assumption is that every entry of A(t) is a
continuous function of I. Before considering the general case, we first discuss the solutions of
x(t) = A(t)x(t) and the reasons why the approach taken in the time-invariant case cannot be
used here.
The solution of the time-invariant equation  x =  Ax can be extended from the scalar
equation i  =  ax. The solution of.i =  ax is x(t) =  ea,x(O) with d(ea')/dl =  aea =  ea'a.
'
|                             |     |     | x =         |       | =             |      |      |     |     |     |
| --------------------------- | --- | --- | ----------- | ----- | ------------- | ---- | ---- | --- | --- | --- |
| Similarly, the solution of  |     |     | Ax is x(t)  |       | eA'x(O) with  |      |      |     |     |     |
|                             |     |     |             | ~eAt  | = AeA         | = eA |      |     |     |     |
|                             |     |     |             |       |               | '    | ' A  |     |     |     |
dt
where the commutative property is crucial. Note that, in general. we have AB  i=  BA and
i=
| e{A+B),  | eA' eR'.  |     |     |     |     |     |     |     |     |     |
| -------- | --------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
The solution of the scalar time-varying equation i  = a(t)x due to x(O) is
|     |     |     |     |                | f' a(r)dr  |     | (0)  |     |     |     |
| --- | --- | --- | --- | -------------- | ---------- | --- | ---- | --- | --- | --- |
|     |     |     |     | X ( t ) = eJo  |            | x   |      |     |     |     |
with
|     |     |     | d   f'  a(ndr =  |     | (t)  f '  a(r)dr  |      | fo '  a(ndr a  | (t)  |     |     |
| --- | --- | --- | ---------------- | --- | ----------------- | ---- | -------------- | ---- | --- | --- |
|     |     | -   | e Jo             |     | a  eJ o           | = eJ | (              |      |     |     |
dt
Extending this to the matrix case becomes
f ' A l r)dr x (0)
|     |     |     |     | X ( t ) = eJ | o   | '   |     |     |     | (4.47)  |
| --- | --- | --- | --- | ------------ | --- | --- | --- | --- | --- | ------- |
with, using (3.51),
|     |     |     | 10'  |     | (10'  |     | (10'  |     |     |     |
| --- | --- | --- | ---- | --- | ----- | --- | ----- | --- | --- | --- |
I;
|     |     | =   | 1+  | A(r)dr +  | ~   | A(r)dr)  |     | A(S)dS) + ...  |     |     |
| --- | --- | --- | --- | --------- | --- | -------- | --- | -------------- | --- | --- |
e A{ndr
This extension, however, is not valid because
|     |                     |            |     | (1'     |            | )   | (1'    |         | )           |     |
| --- | ------------------- | ---------- | --- | ------- | ---------- | --- | ------ | ------- | ----------- | --- |
|     | d    eJfo'  A(rJdr  | =  A(/) +  |     | I       |            |     | +  1   | A(r)dr  | A(/) + ...  |     |
|     | d t                 |            |     | Z A(/)  | 0  A(s)ds  |     | Z   0  |         |             |     |
i= A(t)eI; A(r)dr
(4.48)
Thus, in general, (4.47) is not a solution of i  =  A(t)x. In conclusion, we cannot extend the

|     |     | 4.5  | Solution of Linear Time-Varying (LTV) Equations  |     |     |     |     |     | 107  |
| --- | --- | ---- | ------------------------------------------------ | --- | --- | --- | --- | --- | ---- |
solution of scalar time-varying equations to the matrix case and must use a different approach
to develop the solution.
Consider
x
|     |     |     | = A(t)x  |     |     |     |     |     | (4.49)  |
| --- | --- | --- | -------- | --- | --- | --- | --- | --- | ------- |
where A is n x n with continuous functions of t as its entries. Then for every initial state Xi (to).
there exists a unique solution Xi (t), for i =  1.  2,  "', n. We can arrange these n solutions as
X =  xn], a square matrix of order n. Because every Xi satisfies (4.49), we have
[XI  X2
|     |     |     | X(t) = A(t)X(t)  |     |     |     |     |     | (4.50)  |
| --- | --- | --- | ---------------- | --- | --- | --- | --- | --- | ------- |
If X(to) is nonsingular or the n  initial states are linearly independent, then X(t) is called a
fundamental matrix of (4.49). Because the initial states can arbitrarily be chosen, as long as
they are linearly independent. the fundamental matrix is not unique.
EXAMPLE 4_8  Consider the homogeneous equation
|     |     | .       | [0  | 0]    |       |     |     |     |          |
| --- | --- | ------- | --- | ----- | ----- | --- | --- | --- | -------- |
|     |     | x(t) =  |     | t  0  | x(t)  |     |     |     | (4.51 )  |
or
=
|     |     | XI(t)  | 0   |     |     |     |     |     |     |
| --- | --- | ------ | --- | --- | --- | --- | --- | --- | --- |
| =   |     | =      | =   |     |     |     |     | =   | =   |
The solution of XI (t)  0 for to  0 is XI (t)  XI (0); the solution of X2(t)  tXI (t)  (XI (0)
is
L
|          |     |             | +            |     |     | Z        | +      |     |     |
| -------- | --- | ----------- | ------------ | --- | --- | -------- | ------ | --- | --- |
| Xz(t) =  |     | r XI (O)dr  | X2(0) = 0.5t |     |     | X I (0)  | xz(O)  |     |     |
Thus we have
•
|       | =   |          | = [    |      |       | = [  |        |     |     |
| ----- | --- | -------- | ------ | ---- | ----- | ---- | ------ | --- | --- |
| x(O)  |     | X I  ( 0 | )   ]  | I ]  | x(t)  |      | I      | ]   |     |
|       |     | [        |        | =}   |       |      | 2      |     |     |
|       |     | X 2 ( 0  | )      | 0    |       |      | 0.5 t  |     |     |
and
|     |     |     | [I]  |     |     | [   | I ] |     |     |
| --- | --- | --- | ---- | --- | --- | --- | --- | --- | --- |
XI(O)] =
|       | =   |        |     |     | =     |        | +   |     |     |
| ----- | --- | ------ | --- | --- | ----- | ------ | --- | --- | --- |
| x(O)  | [   | X2(0)  | 2   | =}  | x(t)  | 0.5t2  |     | 2   |     |
The two initial states are linearly independent: thus
~
|     |     |       | = [   |       |      |     |     |     | (4.52)  |
| --- | --- | ----- | ----- | ----- | ---- | --- | --- | --- | ------- |
|     |     | X(t)  | I,    |       | + 2  | ]   |     |     |         |
|     |     |       | 0.5t- | 0.5t- |      |     |     |     |         |
is a fundamental matrix.
A very important property of the fundamental matrix is that X(t) is nonsingular for all t.
For example, X(t) in (4.52) has determinant 0.5t2 +  0.5t2 = 2; thus it is nonsingular for
2 -
all t. We argue intuitively why this is the case. IfX(t) is singular at some tl, then there exists
a nonzero vector v such that x(ti! := X(tdv = 0, which, in tum, implies x(t) := X(t)v == 0
for all t, in particular, at = to. This is a contradiction. Thus X(t) is nonsingular for all t.

| 108  STATE-SPACE SOLUTIONS AND REALIZATIONS  |                                                           |     |     |     |     |     |              |     |     |
| -------------------------------------------- | --------------------------------------------------------- | --- | --- | --- | --- | --- | ------------ | --- | --- |
|                                              | Definition 4.2 Let X(t) be allY fundamental matrix a/x =  |     |     |     |     |     | A(t)x. Then  |     |     |
1
|     |     |     |     | <1>((, to) :=  | X(t)X- | (to)  |     |     |     |
| --- | --- | --- | --- | -------------- | ------ | ----- | --- | --- | --- |
is called the state transition matrix a/x =
A(t)x. The state transition matrix is also Ihe
unique Sollllion of
a
|     |     |     |     | -<I>(t, to) =  |     | A(t)<I>(I, to)  |     |     | (4.53 )  |
| --- | --- | --- | --- | -------------- | --- | --------------- | --- | --- | -------- |
al
with the inilial condition <1>(10. 10) = I.
Because X(t) is nonsingular for alII, its inverse is well defined. Equation (4.53) follows
directly from (4.50). From the definition. ,w  e have the following important properties of the
|     | state transition matrix:  |                |              |     | '   |         |       |             |         |
| --- | ------------------------- | -------------- | ------------ | --- | --- | ------- | ----- | ----------- | ------- |
|     |                           | <1>(1, t) = I  |              |     |     |         |       |             | (4.54)  |
|     |                           |                | =            |     |     | I =     |       | =           |         |
|     |                           | <I>-I(t, 10)   | [X(t)X-I(loW |     |     | X(to)X- | I(t)  | <1>(10. t)  | (4.55)  |
=
|     |                            | <1>(1, to)  | <1>(1. l!l<l>(tl. 101  |     |     |     |     |     | (4.56)  |
| --- | -------------------------- | ----------- | ---------------------- | --- | --- | --- | --- | --- | ------- |
|     | for every I,  10, and II.  |             |                        |     |     |     |     |     |         |
EXAMPLE 4.9  Consider the homogeneous equation in Example 4.8. Its fundamental matrix
was computed as
|     |     |     |     |     | I   | I]  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
[
|     |     |     | X(I) =  |     | ,     | ,           |     |     |     |
| --- | --- | --- | ------- | --- | ----- | ----------- | --- | --- | --- |
|     |     |     |         |     | 0.51- | 0.5t- +  2  |     |     |     |
",  Its inverse is, using (3.20),
-0.5]
2 +
|     |     |     |     |        | [0.25t  | I  0.5  |     |     |     |
| --- | --- | --- | --- | ------ | ------- | ------- | --- | --- | --- |
|     |     |     |     | _I  =  |         |         |     |     |     |
| •   |     |     | X   | (I)    | -0 ')5  | 2       |     |     |     |
._  t
Thus the state transition matrix is given by
|     |     |     |     | I   | I]  |     | I   | -0.5]  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ------ | --- |
g
|     |     |     | [   |     |     |     | +   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
[0.25t
|     | .l  | <I>(I,tO) | =   | 2   | '  + 2  |         | ,   |      |     |
| --- | --- | --------- | --- | --- | ------- | ------- | --- | ---- | --- |
|     |     |           |     |     | 0.5 1-  | -0.2510 | '   | 0.5  |     |
0.5t
[0.5() -
~]
=
IJ)
It  is  straightforward to  verify  that this transition  matrix  satisfies  (4.53) and has the three
properties listed in (4.54) through (4.56).
Now we claim that the solution of (4.45) excited by the initial state x(to) =
Xo and the
input U(I) is given by
l'
=
|     |     | X(I)  | <I>(t.lo)Xo     |     | +  <I>(t, r)B(r)u(r)dr  |                         |     |     | (4.57)  |
| --- | --- | ----- | --------------- | --- | ----------------------- | ----------------------- | --- | --- | ------- |
|     |     |       |                 |     | 1L0                     |                         |     |     |         |
|     |     |       | =               |     | +                       |                         |     |     |         |
|     |     |       | <1>(1, to) [xo  |     |                         | <I>(to. r)B(r)u(r) dr]  |     |     | (4.58)  |

|     |     |     | 4.5 Solution of Linear Time-Varying (LTV) Equations  |     |     |     |     |     | 109  |
| --- | --- | --- | ---------------------------------------------------- | --- | --- | --- | --- | --- | ---- |
x
where cI>(t. r) is the state transition matrix of  = A(t)x. Equation (4.58) follows from (4.57)
by using cI>(l. r) =  cI>(t . (0)cI> (10. r). We show that (4.57) satisfies the initial condition and the
state equaion. At I =
10. we have
1 '0
|     | x(to) = cI>(lo. IO)XO  |     | +   | cI>(1. r)B(r)u(r) dr = Ixn  |     |     |     | +   |     |
| --- | ---------------------- | --- | --- | --------------------------- | --- | --- | --- | --- | --- |
0 = Xo
to
Thus (4.57) satisfies the initial condition. Using (-1.53) and (4.6). we have
l'
a
| -dx (1)  | =   | a             | + - |                      |     |     |     |     |     |
| -------- | --- | ------------- | --- | -------------------- | --- | --- | --- | --- | --- |
|          | -   | cI >(t.lo)Xo  |     | cI>(t. r)B(r)u(r)dr  |     |     |     |     |     |
al
| dl  |     |     | al  | to  |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
1t
(~cI>(l.
|     | A(l)cI>(r.lolxo  |     | +   |     | r)B(r») dr  |     |     | +  cI>(t.I)BU)ult)  |     |
| --- | ---------------- | --- | --- | --- | ----------- | --- | --- | ------------------- | --- |
|     | =                |     |     | al  |             |     |     |                     |     |
to
l'
|     |                    |     | +   |                          |     |     |     | +         |     |
| --- | ------------------ | --- | --- | ------------------------ | --- | --- | --- | --------- | --- |
|     | = A(t)cI>(I.IO)XO  |     |     | A(t)cI>(t. rlB(r)u(r)dr  |     |     |     | B(t)u(t)  |     |
'0i '
|     | =  ACt) [cI>(t, lolxo  |     | +         | cI>(t. r)B(r)u(rl dr]  |     |     |     | +  B(t)u(l)  |     |
| --- | ---------------------- | --- | --------- | ---------------------- | --- | --- | --- | ------------ | --- |
|     | =                      |     | +         |                        |     |     |     |              |     |
|     | A(t)x(I)               |     | B(I)u(l)  |                        |     |     |     |              |     |
Thus (4.57) is the solution. Substituting (4.57) into (4.46) yields
1t
|     |     |     | +   |     |     |     |     | +   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
y(t) =  C(t)cI>(I.IO)XO  cel)  cI>(l. r)B(r)u(r)dr  D(I)u(t)  (4.59)
tn
If the input is identically zero, then Equation (4.57) reduces to
|     |     |     | X(t) =  | cI>(T.lo)Xo  |     |     |     |     |     |
| --- | --- | --- | ------- | ------------ | --- | --- | --- | --- | --- |
This is the zero-input response. Thus the state transition matrix governs the unforced propa
gation of the state vector. If the initial state is zero. then (4.59) reduces to
1t
|     | y(t) =  | Cit)  | cI>(t. r)B(r)u(r) dr  |     |     | +   | D(I)u(l)  |     |     |
| --- | ------- | ----- | --------------------- | --- | --- | --- | --------- | --- | --- |
to
1t
+
|     |     | =   | [C(t)cI>(l. r)B(T)  |     | DO(t - |     | r)] u(r) dr  |     | (4.60)  |
| --- | --- | --- | ------------------- | --- | ------ | --- | ------------ | --- | ------- |
'0
This is the zero-state response. As discussed in (2.5). the zero-state response can be described by
l'
|     |     |     | y(t) =  | GU. r)u(r) dr  |     |     |     |     | (4.61 )  |
| --- | --- | --- | ------- | -------------- | --- | --- | --- | --- | -------- |
'II
where G(t. r) is the impulse response matrix and is the output at time I excited by an impulse
input applied at time r. Comparing (4.6.0) and (4.61) yields
|     |     | G(t. r) =  | C(t)cI>(l. r)B(r)     |     | +  D(t)8(t - |           | r)  |     |        |
| --- | --- | ---------- | --------------------- | --- | ------------ | --------- | --- | --- | ------ |
|     |     |            | = C(I)X(t)X-I(r)B(r)  |     |              | +         |     |     |        |
|     |     |            |                       |     |              | D(t)8(t - |     | r)  | (462)  |
This relates the input-output and state-space descriptions.

110  STATE-SPACE SOLUTIONS AND REALIZATIONS
The solutions in (4.57) and (4.59) hinge on solving (4.49) or (4.53). If A(t) is triangular
such as
0]
|     | XI(t)]   |     | [all(t)  |     | [XI(t)]  |     |     |
| --- | -------- | --- | -------- | --- | -------- | --- | --- |
|     | [ X2(t)  | ==  | a21 (t)  |     | X2(t)    |     |     |
an(t)
we can solve the scalar equation Xl (t) == all (t)XI (t) and then substitute it into
Because Xl (I) has been solved. the preceding scalar equation can be solved for X2(t). This is
what we did in Example 4.8. If A(t). such as A(t) diagonal or constant, has the commutative
property
|     | (L  |     |     | (L  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
I
|     |     |     | dr)  |     | dr)  |     |     |
| --- | --- | --- | ---- | --- | ---- | --- | --- |
A(~)
| A(t)  |     |     | ==  | A(r)  |     | A(t)  |     |
| ----- | --- | --- | --- | ----- | --- | ----- | --- |
for all to and t, then the solution of (4.53) can be shown to be
(1'
I
)k
|             |     | )r,'  A(r)dr  |       | I   |         |     |         |
| ----------- | --- | ------------- | ----- | --- | ------- | --- | ------- |
| <I>(r,to)=e |     | 'O            | =0L0  | ,   | A(r)dr  |     | (4.63)  |
hO k.
'0
I
For A(t) constant, (4.63) reduces to
=
|     | <I>(r, r)  |     | eA(r-r) == <I>(t - |     | r)  |     |     |
| --- | ---------- | --- | ------------------ | --- | --- | --- | --- |
!
and X(t) == eA Other than the preceding special cases, computing state transition matrices is  :
'.
I
generally difficult.
!
4.5. 1 Discrete-Time Case
Consider the discrete-time state equation
|     |      | +   | =         | +         |     |     |         |
| --- | ---- | --- | --------- | --------- | --- | --- | ------- |
|     | x[k  | I]  | A[k]x[k]  | B[k]u[k]  |     |     | (4.64)  |
=
|     |     | y[k]  | C[k]x[k]  | +  D[k]u[k]  |     |     | (4.65)  |
| --- | --- | ----- | --------- | ------------ | --- | --- | ------- |
The set consists of algebraic equations and their solutions can be computed recursively once
the initial state x[ko] and the input u[kl, for k  ::::  ko, are given. The situation here is much
simpler than the continuous-time case.
As in the continuous-time case. we can define the discrete state transition matrix as the
solution of
| <I>[k  +  | I, kol == A[kl<l>[k, ko]  |     |     | with <I>[ko, ko] = I  |     |     |     |
| --------- | ------------------------- | --- | --- | --------------------- | --- | --- | --- |
=  +
for k  ko,  ko  I,  ... . This is the discrete counterpart of (4.53) and its solution can be
obtained directly as
|     | <I>[k, ko] == A[k - |     | I]A[k - |     | 21· .. A[kol  |     | (4.66)  |
| --- | ------------------- | --- | ------- | --- | ------------- | --- | ------- |
for k > ko and <I>[ko, kol  =  I. We discuss a significant difference between the continuous- and
discrete-time cases. Because the fundamental matrix in the continuous-time case is nonsingular

|     |     |     |     |     |     | 4.6  Equivalent Time-Varying Equations  |     |     | III  |
| --- | --- | --- | --- | --- | --- | --------------------------------------- | --- | --- | ---- |
for all t, the state transition matrix 4>(t, to) is defined for t ::: to and t < to and can govern the
propagation of the state vector in the positive-time and negative-time directions. In the discrete
time case. the A-matrix can be singular; thus the inverse of 4>[k. ko] may not be defined. Thus
4>[k. ko] is defined only for k ::: ko and governs the propagation of the state vector in only the
positive-time direction. Therefore the discrete counterpart of (4.56) or
|     |     |     | 4>[k. kol =  |     | 4>[k. kIl4>[k |     | • kol  |     |     |
| --- | --- | --- | ------------ | --- | ------------- | --- | ------ | --- | --- |
l
holds only for k ::: kl ::: ko·
Using the discrete state transition matrix. we can express the solutions of (4.64) and (4.65)
as. for k > ko.
k-I
I:
|     |         |              | +   |          |     | +           |     |     |     |
| --- | ------- | ------------ | --- | -------- | --- | ----------- | --- | --- | --- |
|     | x[k] =  | 4>[k. ko]xo  |     | 4>[k. m  |     | I]B[m]u[m]  |     |     |     |
m=ko
(4.67)
k-I
I:
y[k] =  C[k]4>[k, kolxo  +  C[kl  4>[k, m  +  I]B[m]u[m]  +  D[k]u[k]
m=ko
Their derivations are similar to those of (4.20) and (4.21) and will not be repeated.
If the initial state is zero, Equation (4.67) reduces to
k-I
I:
|     |     |              |     |          |     | +           |     | +         |          |
| --- | --- | ------------ | --- | -------- | --- | ----------- | --- | --------- | -------- |
|     |     | y[k] = C[k]  |     | 4>[k. m  |     | I]B[mlu[ml  |     | D[k]u[k]  | ( 4.68)  |
m=ko
for k  >  ko. This describes the zero-state response of (4.65). If we define 4>[k, m] =  0 for
k < m, then (4.68) can be written as
k
I:
|     |     | y[k] =  |               |     | +   | +       |           |           |     |
| --- | --- | ------- | ------------- | --- | --- | ------- | --------- | --------- | --- |
|     |     |         | (C[k]4>[k, m  |     |     | IlB[m]  | D[m]8[k - | m]) u[m]  |     |
m=ko
'I
where the impulse sequence 8[k - m] equals I if k = m and 0 if k  m. Comparing this with
the multivariable version of (2.34). we have
C[k]4>[k, m + I]B[m] + D[m]8[k -
|     |     | G[k, m] =  |     |     |     |     |     | m]  |     |
| --- | --- | ---------- | --- | --- | --- | --- | --- | --- | --- |
for k ::: m. This relates the impulse response sequence and the state equation and is the discrete
counterpart of (4.62).
4.6  Equivalent Time-Varying Equations
This section extends the equivalent state equations discussed in Section 4.3 to the time-varying
case. Consider the n-dimensional linear time-varying state equation
|        |     |     |     | x          | = A(t)x  | +  B(t)u  |     |     |         |
| ------ | --- | --- | --- | ---------- | -------- | --------- | --- | --- | ------- |
| ,      |     |     |     |            |          |           |     |     | (4.69)  |
| • •    |     |     |     | y = C(t)x  |          | +  D(t)u  |     |     |         |
I

112  STATE-SPACE SOLUTIONS AND REALIZATIONS
x n matrix. It is assumed that P(I) is nonsingu\ar and both P(I) and P(I) are
Let Plt) be an  /I
continuous for all I. Let x = P(t )x. Then the state equation
x
+
|     |     | = AU)x  | B(I)u  |     |
| --- | --- | ------- | ------ | --- |
(4.70)
|     |     | -   | -   |     |
| --- | --- | --- | --- | --- |
+
|     |     | y =  C(t)x  | D(I)u  |     |
| --- | --- | ----------- | ------ | --- |
where
|     | =     |            | +             |     |
| --- | ----- | ---------- | ------------- | --- |
|     | A(I)  | [P(I)A(I)  | p(t)]p-I (I)  |     |
B(I) = P(I)B(I)
CU) =
C(r)p-I(I)
=
|     | O(t)  | DII)  |     |     |
| --- | ----- | ----- | --- | --- |
is said to be (algebraically) equivalent to (4.69) and P(I) is called an (a/gebraic) equil'G/ellce
transfonnation.
x
P(t)x + P(t)X.
Equation (4.70) is obtained from (4.69) by substituting x =  P(t)x and  =
Let X be a fundamental matrix of (4.69). Then we claim that
XU) := P(I)X(t)  (4.71)
is a fundamental matrix of (4.70). By definition. X(t) =  A(I )X(t) and XU) is nonsingular for
aliI. Because the rank of a matrix will not change by multiplying a nonsingular matrix, the
matrix P(tlX(I) is also nonsingular for aliI. Now we show that P(t)X(I) satisfies the equation
x
=  A(t)x. Indeed. we have
| d                | .         | .           | ,         |               |
| ---------------- | --------- | ----------- | --------- | ------------- |
|                  |           | +           |           | +             |
| dt [P(t)X(I)] =  | P(t)X(I)  | P(t)X(t) =  | P(t)X(t)  | P(t)A(t)X(I)  |
+
=  [P(I)  P(t)A(t)][P-I(r)P(t)]X(t) = A(I)[P(I)X(I)]
Thus Plt )X(t) is a fundamental matrix of x(t)= A(t)x(t).
Theorem 4.3
Let Ao be an arbitrary c_onstant matrix. Then there exists an equivalence transformation that tr3nsfomls
(4.69) into (4.70) with A(I) =  Ao.
x =
Proof'  Let XU) be a fundamental matrix of  A(t)x. The differentiation of X- I (I)
XU) = I yields
x-t
+
|     |     | (I)XlI)  X- | IX(t) = 0  |     |
| --- | --- | ----------- | ---------- | --- |
which implies
(4.72)
| =   |     |     | =   |     |
| --- | --- | --- | --- | --- |
Because A(I)  Ao  is  a constant  matrix.  X(I)  eAQ1  is  a  fundamental  matrix  of
x
= A(l)x = Aox. Following (4.7 I). we define
(4.73)

|     |     |     |     |     |     | 4.6  | Equivalent Time-Varying Equations  |     |     | 113  |
| --- | --- | --- | --- | --- | --- | ---- | ---------------------------------- | --- | --- | ---- |
and compute
|     | AU) =  | [P(rlA(r) +         |     | p(r)]p-I(t)  |               |     |        |     |              |     |
| --- | ------ | ------------------- | --- | ------------ | ------------- | --- | ------ | --- | ------------ | --- |
|     |        |                     |     |              | +             |     | +      |     |              |     |
|     |        | =  [eAv'X-I{t)A(t)  |     |              | AoeAO'X-I(t)  |     | eAo'X- |     | I(I)]X(t)e-A | .'  |
whic,b becomes. after substituting (4.72),
|                                |     |     | A(r)  | =  AoeA"'X-1 (t)X(t)e- |     |     | Ao  | '  = Ao  |     |     |
| ------------------------------ | --- | --- | ----- | ---------------------- | --- | --- | --- | -------- | --- | --- |
| This establishes the theorem.  |     |     |       | Q.E.D.                 |     |     |     |          |     |     |
X-1{t) and (4.70) reduces to
If Ao is chosen as a zero matrix, then P{t) =
A(r) = 0  ihr) =  X-I (r)B(t)  C(l) = C(t)X(t)  D(t) = D(l)  (4.74)
The block diagrams of (4.69) with A(t) i- 0 and A(t) =  0 are plotted in Fig. 4.5. The block
diagram with A(t) = 0 has no feedback and is considerably simpler. Every time-varying state
equation can be transfonned into such a block diagram. However, in order to do so. we must
know its fundamental matrix.
The impulse response matrix of (4.69) is given in (4.62). The impulse response matrix of
(4.70) is, using (4.71) and (4.72),
|     | - .      | = C -  | -    | -- I   | -    | +  -       |     |     |     |     |
| --- | -------- | ------ | ---- | ------ | ---- | ---------- | --- | --- | --- | --- |
|     | G (t, r) |   (r)X | (t)X |   (r)B | (r)  | D (t)o(t - | r)  |     |     |     |
'"
D
,
| u-     |     |     |            |          |     |     |      |     | v          |   y '"   |
| ------ | --- | --- | ---------- | -------- | --- | --- | ---- | --- | ---------- | -------- |
|        |     |     | ->. ro . . |   X  '"  | f   |     | '"   |     | ... > ..'  |          |
| ~,  B  |     |     | + ) :      |          |     |     | ,    | C   |            | J        |
|        |     |     |            |          |     |     |      |     | " 7   + [  |          |
7'
-
L
A
(aj
ii
|      |           |     |     |     |     | •   |     |       | +     |     |
| ---- | --------- | --- | --- | --- | --- | --- | --- | ----- | ----- | --- |
| - u  |           |     |     | it  |     |     |     | -,-'  | ~  y  |     |
|      | L....>.,  |     |     |     | f   |     | c   |       |       |     |
B
"'
...)----/
+
(bj
Figure 4.5  Block daigrams with feedback and without feedback.

~,
,
114  STATE-SPACE SOLUTIONS AND REALIZATIONS
;
| =                                       |     |     |           |     | +         |      |
| --------------------------------------- | --- | --- | --------- | --- | --------- | ---- |
| C(t)p-l(t)p(t)X(t)X-1(r)p-1(r)P(r)B(r)  |     |     |           |     | D(t)o(t - | r )  |
| =  C(t)X(t)X-I(r)B(r) +                 |     |     |           | =   |           |      |
|                                         |     |     | D(t)8(t - | r)  | G(t. r)   |      |
Thus the impulse response matrix is invariant under any equivalence transformation. The
property of the A-matrix. however, may not be preserved in equivalence transformations. For
example, every A-matrix can be transformed. as shown in Theorem 4.3. into a constant or a
zero matrix. Clearly the zero matrix does not have any property of A(t). In the time-invariant
case, equivalence transformations will preserve all properties of the original state equation.
Thus the equivalence transformation in the time-invariant case is not a special case of the
time-varying case.
Definition 4.3 A matrix P(t) is called q Lyapunov transformation ifP(t) is nonsingular,
pet) and P(t) are continuous, and P(t) bndp-I (t) are boundedforall t. Equations (4.69)
and (4.70) are said to be Lyapunov equivalent ifP(t) is a Lyapunov transformation.
It is clear that if P(t) = P is a constant matrix, then it is a Lyapunov transformation. Thus
the (algebraic) transformation in the time-invariant case is a special case of the Lyapunov
transformation. If pet) is required to be a Lyapunov transformation, then Theorem 4.3 does
not hold in general. In other words. not every time-varying state equation can be Lyapunov
equivalent to a state equation with a constant A-matrix. However, this is true if A(t) is periodic.
Periodic state equations  Consider the linear time-varying state equation in (4.69).  It is
assumed that
+ n =
|     |     | A(t  | A(t)  |     |     |     |
| --- | --- | ---- | ----- | --- | --- | --- |
for all t and for some positive constant T. That is. A(t) is periodic with period T. Let X(t) be
a fundamental matrix ofi =  A(t)x or X(t) = A(I)X(t) with X(O) nonsingular. Then we have
| X(t +  |     | =  +       | +   | =        | +   |     |
| ------ | --- | ---------- | --- | -------- | --- | --- |
|        | T)  | A(t  nX(t  | T)  | A(I)X(I  | T)  |     |
+ n
Thus X(t  is also a fundamental matrix. Furthermore, it can be expressed as
+ n
|     | X(I  | = X(t)X-1( O)X(T)  |     |     |     | (4.75)  |
| --- | ---- | ------------------ | --- | --- | --- | ------- |
This can be verified by direct substitution. Let us define Q =  X-I (O)X(T). It is a constant
nonsingular matrix. For this Q there exists a constant matrix  A  such that /,.T  =  Q (Problem
3.24). Thus (4.75) can be written as
|     |     | + n =  |       | AT  |     |         |
| --- | --- | ------ | ----- | --- | --- | ------- |
|     |     | X(t    | X(t)e |     |     | (4.76)  |
Define
P(t):= eArX-I(I)
(4.77)
We show that P(t) is periodic with period T:
+ n =
| +    | =                |     |     |               |        |     |
| ---- | ---------------- | --- | --- | ------------- | ------ | --- |
| P(t  | T)  eA(r+nX-I(t  |     |     | eAreAT[e-ATX- | I(t)]  |     |
=
|     | eArX-I(t) =  |     | pet)  |     |     |     |
| --- | ------------ | --- | ----- | --- | --- | --- |

4.7 Time-Varying Realizations 115
~ Theorem 4.4
+
Consider (4.69) with A{t) = A{t T) for all t and some T > O. Let X{t) be a fundamental matrix
= =
of X A(t)x. Let A be the constant matrix computed from eAT X- I (O)X{T). Then (4.69) is
Lyapunov equivalent to
+
x(t) = AX(r) P(t)B(t)u(t)
= +
y(r) C(t)p-I (t)x(t) D{t)u(t)
where Pet) = eA1X-1 (t).
The matrix pet) in (4.77) satisfies all conditions in Definition 4.3; thus it is a Lyapunov
transformation. The rest of the theorem follows directly from Theorem 4.3. The homogeneous
= + =
part of Theorem 4.4 is the theory of Floquet. It states that if x A{t)x and if AU T) A(t)
A1
for all t. then its fundamental matrix is of the form p-I(r)e , where p-I(t) is a periodic
function. Furthermore, x = A(t)x is Lyapunov equivalent to x = Ax.
4.7 Time-Varying Realizations
We studied in Section 4.4 the realization problem for linear time-invariant systems. In this
section, we study the corresponding problem for linear time-varying systems. The Laplace
transform cannot be used here; therefore we study the problem directly in the time domain.
Every linear time-varying system can be described by the input-output description
y(t) = 11 G{t, r)u{r) dr
'0
and, if the system is lumped as well, by the state equation
x(r) = A(t)x{t) + B(t)u{t)
(4.78)
+
y(r) = C(t)x(t) D{t)u(t)
If the state equation is available, the impulse response matrix can be computed from
G(t, r) = C(t)X{t)X-1 (r)B(r) + D(t)o(t - r) for t ::: r (4.79)
where X(t) is a fundamental matrix of x = A{l)x. The converse problem is to find a state
equation from a given impulse response matrix. An impulse response matrix G(t, r) is said to
be realizable if there exists (AU), B(t), C(t), D(t)l to meet (4.79).
~ Theorem 4.5
A q x p impulse response matrix G(t, r) is realizable if and only if G(t, r) can be decomposed as
+
G(t, r) = M(t)N(r) D(t)o{t - r) (4.80)
for all t ::: r. where M. N. and D are, respectively. q x n. n X p. and q x p matrices for some
integer n.

t: '0
.
-,
~
~ ~ ~
N '.
~~~
< -
9
i
.-.~ ,
~
•
~
~
!
,
g
•
, .. "•
1 '
~ •, 1 ~
~ ~
.o. " '.
~ '-----'
+
-.•. E
.~
l .~
" .A ,!+'8<t'.«
•

Problems  119
Show that its observable canonical form realization can be reduced from Problem 4.9 as  [-a.
0 0]
[P"
|      |       | oJ     |     | p" ]        |
| ---- | ----- | ------ | --- | ----------- |
|      | -a,   | lOx +  |     | f321  f322  |
| X =  | •     |        |     |             |
o  u
|     | -a3  | 0   | I   | f331  Ih2  |
| --- | ---- | --- | --- | ---------- |
o
|      | -a4       | 0        | 0     | f341  f342  |
| ---- | --------- | -------- | ----- | ----------- |
| Y =  | [I  0  0  | O)x + [d | dz)u  |             |
l
4.11  Find a realization for the proper rational matrix
|     |           | ~      | +2~)~S ~  |       |
| --- | --------- | ------ | --------- | ----- |
|     | G(s)  [s  |        | (s        |       |
|     | =         | I      |           | 2) ]  |
|     |           | s - 2  |           | s     |
|     |           | --     |           | --    |
|     |           | s+1    |           | s+2   |
4.12  Find a realization for each column of G(s) in Problem 4.11  and then connect them.
as shown in Fig. 4.4(a). to obtain a realization of (;(s). What is the dimension of this
realization? Compare this dimension with the one in Problem 4.11.
4.13  Find a realization for each row of (;(s) in Problem 4.11 and then connect them, as shown
in Fig. 4.4(b), to obtain a realization of (;(s). What is the dimension of this realization?
Compare this dimension with the ones in Problems 4.11 and 4.12.
4.14  Find a realization for
|     | =   | [-(12S + 6)  |     | 22s + 23]  |
| --- | --- | ------------ | --- | ---------- |
(;(s)
|     |     | + 34  |     | 3s + 34  |
| --- | --- | ----- | --- | -------- |
3s
4.15  Consider the n-dimensional state equation
x
|     | = Ax+ bu  |     |     | y = ex  |
| --- | --------- | --- | --- | ------- |
Let g(s)  be  its  transfer function.  Show that g(s)  has m  zews or, equivalently,  the
numerator of g(s) has degree m if and only if
=
|     |     | for i  | 0, I, 2, ... , n - | m - 2  |
| --- | --- | ------ | ------------------ | ------ |
and eA  b f. O. Or, equivalently, the difference between the degrees of the denom
n-m-I
inator and numerator of g(s) is a = n - m if and only if
=
|     | eAa-1b f. 0  |     | and  | eAib  0  |
| --- | ------------ | --- | ---- | -------- |
=
for i  0, 1,2, .... a - 2.
4.16  Find fundamental matrices and state transition matrices for

120  STATE-SPACE SOLUTIONS AND REALIZATIONS
and
.  [-I
elf]
x
X=  o
-I
a
| 4-17  Show  | <1>(10. o /at =  | -<I>(to. t)A(t).  |     |     |
| ----------- | ---------------- | ----------------- | --- | --- |
4_18  Given
show
4.19  Let
=
|     |     | <I>(t. to)  | [<I>II(t. to)  | <l>dt, to)]  |
| --- | --- | ----------- | -------------- | ------------ |
|     |     |             | <1>21 (t, to)  | <l>dt, to)   |
be the state transition matrix of
|     |     | x(t) =  | [AIOI(t)  A12(t)]x(t)  |     |
| --- | --- | ------- | ---------------------- | --- |
A
22(t)
=  =
Show that <1>21(1. to)  0 for all t and to  and that (J/Jt)<I>u(l, to)  A;; <I>;;(t. to). for
| i =  | 1,2.  |     |     |     |
| ---- | ----- | --- | --- | --- |
4.20  Find the state transition matrix of
|                                |     |     | .  [- sin t         |     |
| ------------------------------ | --- | --- | ------------------- | --- |
|                                |     |     | X=  o               |     |
| 4.21  Verify that X(t) = eA1Ce |     | B1  | is the solution of  |     |
=
X(O)  C
=
| 4.22  Show that if A(t)  |     | AIA(t) - | A(t)A l• then  |     |
| ------------------------ | --- | -------- | -------------- | --- |
AU) = eA1f A(O)e~Alt
Show also that the eigenvalues of A (t) are independent of t.
4.23  Find an equivalent time-invariant state equation of the equation in Problem 4.20.
Transform a time-invariant (A, B. C) into (0. IHt). CUJJ by a time-varying equivalence
4.24
transformation.
4.25  Find a time-varying realization and a time-invariant realization of the impulse response
Af
| g(t) = tle | .   |     |     |     |
| ---------- | --- | --- | --- | --- |
4.26  Find a realization of gU, r) = sin t(e~(t~r)  cos To Is it possible to find a time-invariant
state equation realization')

~l
118  STATE-SPACE SOLUTIONS AND REALIZATIONS
|     | A-  | I  0  0  0  | 0   | b   |     |     |
| --- | --- | ----------- | --- | --- | --- | --- |
l
|     |     | 0  0  | 0   | b2  |     |     |
| --- | --- | ----- | --- | --- | --- | --- |
|     | 0   | A- I  |     |     |     |     |
b)
|     | 0   | 0  A- 0  0  | 0   |     |     |     |
| --- | --- | ----------- | --- | --- | --- | --- |
|     |     |             | x+  |     | u   |     |
|     | x=  |             |     | b   |     |     |
|     | 0   | 0  0  A- I  | 0   |     |     |     |
l
b2
|     | 0   | 0  0  0  A- |     |     |     |     |
| --- | --- | ----------- | --- | --- | --- | --- |
b)
|     | 0   | 0  0  0  0  | A-  |     |     |     |
| --- | --- | ----------- | --- | --- | --- | --- |
C)]x
|     | y =  [cl  C2  | c)  <:1  <:2  |     |     |     |     |
| --- | ------------- | ------------- | --- | --- | --- | --- |
can be transfonned into
| [:  |     | iJ'tm·  |     |     |     |     |
| --- | --- | ------- | --- | --- | --- | --- |
12
;~
|     | A   |     | y =  | [CI  | C2  c)]i  |     |
| --- | --- | --- | ---- | ---- | --------- | --- |
0
where  A. b.  and Ci  are defined in Problem 4.6 and 12 is the unit matrix of order 2. [Hint:
Change the order of the state variables from  [XI  x61' to [Xl
|     |     |     |     | X2  X)  X4  | Xs  | X4  X2  Xs  |
| --- | --- | --- | --- | ----------- | --- | ----------- |
x61' and then apply the equivalence transfonnation x  =  Qi with Q  =  diag(QI.
X)
Q2. Q).]
4.8  Are the two sets of state equations
;Hi}
,~U ~
y = [1 -1 O]x
and
y=[I-IO]x
equivalent? Are they zero-state equivalent?
4.9  Verify that the transfer matrix in (4.33) has the following realization:
|     |         | 0      | 0   |       |     |     |
| --- | ------- | ------ | --- | ----- | --- | --- |
|     | -all q  | Iq     |     | NI    |     |     |
|     | -a2lq   | 0  Iq  | 0   | N2    |     |     |
| X=  |         |        |     | x+    | u   |     |
|     |         | 0  0   | Iq  | Nr-I  |     |     |
-ar-Ilq
|     |        |       | 0   | Nr  |     |     |
| --- | ------ | ----- | --- | --- | --- | --- |
|     | -arlq  | 0  0  |     |     |     |     |
...
O]x
y=[lqOO
This is called the observable canonical/onn realization and has dimension rq. It is dual
to (4.34).
4.10  Consider the 1 x 2 proper rational matrix
1
G(s) = [d A  d +
| l   | 2]  -:+- -~-+- -:,+. ---+- ­ |              |       |      |     |     |
| --- | ---------------------------- | ------------ | ----- | ---- | --- | --- |
|     | S4                           | als)  CV2s2  | CV)S  | CV4  |     |     |

Chapter
Stability
5.1 Introduction
Systems are designed to perform some tasks or to process signals. If a system is not stable. the
system may bum out, disintegrate, or saturate when a signal, no matter how small, is applied.
Therefore an unstable system is useless in practice and stability is a basic requirement for all
systems. In addition to stability, systems must meet other requirements, such as to track desired
signals and to suppress noise, to be really useful in practice.
The response of linear systems can always be decomposed as the zero-state response
and the zero-input response. It is customary to study the stabilities of these two responses
separately. We will introduce the BIBO (bounded-input bounded-output) stability for the zero
state response and marginal and asymptotic stabilities for the zero-input response. We study
first the time-invariant case and then the time-varying case.
5.2 Input-Output Stability of LTI Systems
Consider a SISO linear time-invariant (LTI) system described by
l' l'
y(t) = g(t - r)u(r) dr = g(r)u(t - r) dr (51)
where g(t) is the impulse response or the output excited by an impulse input applied at t = O.
Recall that in order to be describable by (5.1), the system must be linear, time-invariant, and
causal. In addition, the system must be initially relaxed at t = O.
121

|     |     |     |     | 5.2  | Input-Output Stability of LTI Systems  | 123  |
| --- | --- | --- | --- | ---- | -------------------------------------- | ---- |
Figure 5.1  Function.
n
|     |     |     | 2  3  | 4  5  |     |     |
| --- | --- | --- | ----- | ----- | --- | --- |
z
| integration of the function equals L:::z(l/n |     |     |     | ) <  |     |     |
| -------------------------------------------- | --- | --- | --- | ---- | --- | --- |
00. This function is absolutely integrable
but is not bounded and does not approach zero as t ~ 00.
Theorem 5.2
~
If a system with impulse response g (t) is BIBO stable, then, as t ~ 00:
1. The output excited by u(t) = a, for t :=: 0, approaches g(O) . a.
=
| 2.  The output excited by u (t)  |     |     | sin wot,  | for t :=: 0, approaches  |     |     |
| -------------------------------- | --- | --- | --------- | ------------------------ | --- | --- |
!g(jWo)! sin(wot+ 1=.g(jwo))
where g(s) is the Laplace transform of g(t) or
1'X>
|            |                        |         | g(s) =                      |           | sr  |            |
| ---------- | ---------------------- | ------- | --------------------------- | --------- | --- | ---------- |
|            |                        |         |                             | g(,)e-    |     | d,  (5.2)  |
| •  Proof"  | If u (t)= a for all t  |         | :=: 0, then (5. I) becomes  |           |     |            |
|            |                        |         | l'                          |           |     | l'         |
|            |                        | y(t) =  | g(,)u(t -                   | old, = a  |     | g(,)d-r    |
which implies
1
00
~
|     |     | yet)  | a   | g(,)d, =ag(O)  |     | ast~oo  |
| --- | --- | ----- | --- | -------------- | --- | ------- |
where we have used (5.2) with s =  O. This establishes the first part of Theorem 5.2. If
u(t) = sinwot, then (5.1) becomes
L
=
|     | y(t)  | g(,) sin wo(t - |     | ,) d,  |     |     |
| --- | ----- | --------------- | --- | ------ | --- | --- |
l'
|     |     | =  g(,) [sinwotcoswo' - |     |     | coswotsinwo'] d,  |     |
| --- | --- | ----------------------- | --- | --- | ----------------- | --- |
|     |     |                         | l'  |     |                   | l'  |
=
|     |     | sinwot  | g(,) cosWo' d, - |     | coswot  | g(,) sin Wo' d,  |
| --- | --- | ------- | ---------------- | --- | ------- | ---------------- |

124 STABILITY
Thus we have, as t -> 00,
l
x
yet) -> sinwot l Xg(r)coswordr: -coswot g(r)sinw"rdr (5.3)
If g(t) is absolutely integrable, we can replace s by jw in (5.2) to yield
l
x
=
g(jw) g(r)[coswr - j sinwrldr
The impulse response g(t) is assumed implicitly to be real: thus we have
1~
Re[g(jw)] = g(r)coswrdr
and ,
'-10<)
Im[g(jw)] = g(r) sin wr dr
where Re and 1m denote, respecti vely, the real part and imaginary part. Substituting these
into (5.3) yields
+
yet) -> sinwot(Re[g(jwo)]) coswot(Im[g(jwo)])
= [g(jwo)[ sin(wot+ :r.g(jwo »)
This completes the proof of Theorem 5.2. Q.E.D.
Theorem 5.2 is a basic result; filtering of signals is based essentially on this theorem.
Next we state the BIBO stability condition in terms of proper rational transfer functions.
~... Theorem 5.3
A SISO system with proper rational transfer function g(s) is EIBO stable if and only if every pole of
g(s) has a negative real pan or. equivalently, lies inside the left-half s-plane.
If g(s) has pole Pi with multiplicity mi. then its partial fraction expansion contains the
factors
s-P, (S-Pi)2 '
Thus the inverse Laplace transform of g(s) or the impulse response contains the factors
It is straightforward to verify that every such term is absolutely integrable if and only if p, has
a negative real part. Using this fact, we can establish Theorem 5.3.
EXAMPLE 5.1 Considerthe positive feedback system shown in Fig. 2.5(a1. Its impulse response
was computed in (2.9) as
00
g(t) = La'J(t - i)
1=1

,
122 STABILITY
An input u(t) is said to be bOllnded if u(t) does not grow to positive or negative infinity
or, equivalently, there exists a constant such that
Urn
°
IU(I)I :::: Urn < 00 for all I ~
A system is said to be BIBO stable (bounded-input bounded-output stable) if every bounded
input excites a bounded output. This stability is defined for the zero-state response and is
applicable only if the system is initially relaxed.
~ Theorem 5.1
A S1S0 system described by (5.1) is BlEO stable if and only if g(t) is absolutely integrable in [0, (0), or
roo
I
10
Ig\t)ldt::::: M < 00
for some constant M.
31
Proof: First we show that if g(t) is absolutely integrable, then every bounded input excites
a bounded output. Let u(t) be an arbitrary input with !u(t)1 :::: Urn < 00 for all t ~ O. Then
l'
11'
ly(I)1 = g(r)lI(t - r)drl:::: Ig(r)llu(1 - ,)Idr
l
cc
Ig(r)ldr :::: M
:::: Urn urn
Thus the output is bounded. Next we show intuitively that if g(t) is not absolutely
integrable, then the system is not BIBO stable. If g (t) is not absolutely integrable, then
there exists a tl such that
['I
10
Ig(r)1 dr = 00
Let us choose
°
II(II-r)={_~ if g(r) ~
ifg(r)<0
Clearly u is bounded. However. the output excited by this input equals
I
1"
t
y(tJl = g\r)II(t1 - r) dr = ' Ig(r)1 dr = 00
which is not bounded. Thus the system is not BIBO stable. This completes the proof of
Theorem 5.1. Q.E.D.
A function that is absolutely integrable may not be bounded or may not approach zero as
I -+ 00. Indeed, consider the function defined by
n + (t - n)n4 for n - 1/ n3 :::: t :::: n
f(t-n)= { n - (t - n)n 4 for n < I :::: n + 1/ n3
= 2
for n 2, 3, .. , and plotted in Fig. 5.1. The area under each triangle is l/n . Thus the absolute

5.2 Input-Output Stability of LTI Systems 125
where the gain a can be positive or negative. The impulse is defined as the limit of the pulse
in Fig. 2.3 and can be considered to be positive. Thus we have
x
L
Ig(r)1 = lali8(r - i)
i=l
and
iflal:::!
iflai < I
Thus we conclude that the positive feedback system in Fig. 2.5(a) is BIBO stable if and only
if the gain a has a magnitude less than I.
The transfer function of the system was computed in (2.12) as
ae-S
g(s) = ---
! - ae-S
It is an irrational function of s and Theorem 5.3 is not applicable. In this case, it is simpler to
use Theorem 5.1 to check its stability.
For multi variable systems, we have the following results.
;--~ Theorem 5.M1
A multi variable system with impulse response matrix G(t) [gij(t)] is BIBO stable if and only if
every gij(r) is absolutely integrable in [0, 00).
}:. Theorem 5.M3
1
A multi variable system with proper rational transfer matrix G(s) = [gi} (s) is BIBO stable if and only
if every pole of every gij (.I) has a negative real part.
We now discuss the BIBO stability of state equations. Consider
x(t) = Ax(t) + Bu(t)
(5.4)
y(t) = Cx(t) + Du(t)
Its transfer matrix is
Thus Equation (5.4) or. to ,be more precise. the zero-state response of (5.4) is BIBO stable if
and, only if every pole of ~(s) has a negative real part. Recall that every pole of every entry
of G(s) is called a pole of G(s).
We discuss the relationship between the poles of G(s) and the eigenvalues of A. Because
of
, I
G(s) = C[Adj(sI - A)]B + D (5.5)
det(sI - A)

r
|     |     |     |     | 5.2  Input-Output Stability of LTI Systems  |     |     | 127  |
| --- | --- | --- | --- | ------------------------------------------- | --- | --- | ---- |
Its proof is similar to the proof of Theorem 5.1 and will not be repeated. We give a discrete
counterpart of Theorem 5.2 in the following.
Theorem 5.02
If a discrete-time system with impulse response sequence g[k] is BIBO stable. then. as k ~ 00:
1. The output excited by u[k] = a.  for k?: 0. approaches gO)' a.
=
| 2.  The output excited by u [k]  |     |     | sin wok,  for k ?: 0, approaches  |     |     |     |     |
| -------------------------------- | --- | --- | --------------------------------- | --- | --- | --- | --- |
jw
|     |     |     | Ig(ejw')1 sin(wok+ j:g(e |     | ,))  |     |     |
| --- | --- | --- | ------------------------ | --- | ---- | --- | --- |
where g(z) is the :-transform of g[k] or
L
=
|     |     |     | g(z)  | g[m]z-m  |     |     | (5.8)  |
| --- | --- | --- | ----- | -------- | --- | --- | ------ |
m=O
Proof  If u[k] = a for all k ?: 0, then (5.7) becomes
~
|     |     |         | Lk        |         | Lk   |       |     |
| --- | --- | ------- | --------- | ------- | ---- | ----- | --- |
|     |     | y[k] =  | g[m]u[k - | m] = a  |      | g[m]  |     |
Q
k;Q
which implies
L00
|     |     | y[k] ~ a  | g[m] = agO)  |     | as k -+ 00  |     |     |
| --- | --- | --------- | ------------ | --- | ----------- | --- | --- |
m:;:::Q
z =
where we have used (5.8) with  I. This establishes the first part of Theorem 5.D2. If
=
u[k]  sin wok, then (5.7) becomes
Lk
y[k] =
|     |     | g[m] sin work - |     | m]  |     |     |     |
| --- | --- | --------------- | --- | --- | --- | --- | --- |
m=O
Lk

|     | =   | g[m](sin wok coswom - |     | cos wok sinwom)  |     |     |     |
| --- | --- | --------------------- | --- | ---------------- | --- | --- | --- |
m:=::::Q
|     |            |     | Lk             |          |     | Lk            |     |
| --- | ---------- | --- | -------------- | -------- | --- | ------------- | --- |
|     | = sin wok  |     | g[m] cos wom - | cos wok  |     | g[m] sin wom  |     |
m==O
Thus we have. as k -+ 00.
|                 |     |     | L x            |          |     | L00           |     |
| --------------- | --- | --- | -------------- | -------- | --- | ------------- | --- |
| y[kJ ~ sin wok  |     |     | g[m] cos wom - | cos wok  |     | g[m] sin wom  |     |
(5.9)
m=O
If g[k] is absolutely summable, we can replace z by ejw
in (5.8) to yield
x
|     |     | L00   |         | L            |     |            |     |
| --- | --- | ----- | ------- | ------------ | --- | ---------- | --- |
|     | jW  | =     | jwm  =  |              |     |            |     |
|     | g(e | )     | g[m]e-  | g[m][coswm - |     | j sin wm]  |     |
|     |     | m=O   |         | m=O          |     |            |     |

128  STABILITY
Thus (5.9) becomes
| y[k] -> sin wok(Re[g(e |     | iwu ))) + cos uJok (Im[g (eiwo)j)  |     |     |
| ---------------------- | --- | ---------------------------------- | --- | --- |
iwo
| =                                          | Ig(ei""')i sin(wok+ j:g(e |         | »   |     |
| ------------------------------------------ | ------------------------- | ------- | --- | --- |
| This completes the proof of Theorem 5.02.  |                           | Q.E.D.  |     |     |
Theorem 5.02 is  a basic result in digital signal  processing. Next we state the  BIBO
stability in terms of discrete proper rational transfer functions.
Theorem 5.03
A discrete-time SISO system with proper rational transfer function g(z) is SlBO stable if and only if
0,.
every pole of g(Z) has a magnitude less than I  equivalently. lies inside the unit circle on the :-plane.
If g(z) has pole p,  with multiplicity m"  then its partial fraction expansion cOn!ains the
factors
Thus the inverse z-transform of g(z) or the impulse response sequence cOn!ains the factors
|     | k    | k  k  km,-Ipl  |     |     |
| --- | ---- | -------------- | --- | --- |
|     | Pi'  | Pi'  "',       |     |     |
j
It is straightforward to verify that every such term is absolutely summable if and only if Pi has
a magnitude less than I. Using this fact, we can establish Theorem 5.03.
In the continuous-time case, an absolutely integrable function  f  (r), as shown in Fig. 5.1.
may not be bounded and may not approach zero as t  -> oc. In the discrete-time case, if g[kl
is absolutely summable, then it must be bounded and approach zero as k -> ::xl. However. the
com'erse is not true as the next example shows.
EXA~IPLE 5.3  Consider a discrete-time LTI system with impulse response sequence g[k] =
.,
| II k. for k =  1,2. "' , and g[O] = O. We compute  |         |              |           |     |
| -------------------------------------------------- | ------- | ------------ | --------- | --- |
| oc                                                 | xl      | I  I         | I         |     |
| S := "Ig[kll =                                     | "  - =  | 1+ - +  - +  | - +  ...  |     |
| ~                                                  | ~ k     | 234          |           |     |
| 1=0                                                | k=1     |              |           |     |
|                                                    | G D G   |              | D G       |     |
~
| =  I +  +  | +  +  | +  ... +  | +  +  ... +  | 11 )  + ...  |
| ---------- | ----- | --------- | ------------ | ------------ |
6
±
There are two terms. each is  or larger. in the first pair of parentheses; therefore their sum
- is larger than  ~. There are four terms, each is  ~ or larger, in the second pair of parentheses;
,  1.
I  therefore their sum is larger than  Proceeding forward we conclude
I  I  I
S> I+-+-+-+ .. ·=oc
.,  222
.,
This impulse response sequence is bounded and approaches 0 as k --+ ::xl but is not absolutely
i  summable. Thus the discrete-time system is not BIBO stable according to Theorem 5.0 I. The
:1
,j  transfer function of the system can be shown to equal

126 STABILITY
every pole of (;(s) is an eigenvalue of A. Thus if every eigenvalue of A has a negative real
part. then every pole has a negative real part and (5.4) is BIBO stable. On the other hand,
because of possible cancellation in (5.5), not every eigenvalue is a pole. Thus, even if A has
some eigenvalues with zero or positive real part, (5.4) may still be BIBO stable. as the next
example shows.
EXAMPLE 5.2 Consider the network shown in Fig. 4.2(b). Its state equation was derived in
Example 4.4 as
itt) = x(t) + O· u(t) yet) = 0.5x(t) + 0.5u(t) (5.6)
The A-matrix is I and its eigenvalue is 1. It has a positive real part. The transfer function of
the equation is
I
g(s) = 0.5(; - 1)-1 ·0 + 0.5 = 0.5
The transfer function equals 0.5. It has no pole and no condition to meet. Thus (5.6) is BIBO
stable even though it has an eigenvalue with a positive real part. We mention that BIBO stability
does not say anything about the zero-input response, which will be discussed later.
5.2.1 Discrete-Time Case
Consider a discrete-time SISO system described by
k k
L L
y[k] = g[k - mJu[mJ = g[mJu[k - mJ (5.7)
m=O
where g[k J is the impulse response sequence or the output sequence excited by an impulse
sequence applied at k = O. Recall that in order to be describable by (5.7), the discrete-time
system must be linear, time-invariant, and causal. In addition, the system must be initially
relaxed at k = O.
An input sequence u [k J is said to be bounded if u [k 1d oes not grow to positive or negative
infinity or there exists a constant Urn such that
=
lu[k)l ~ Urn < 00 for k 0, 1,2, ...
A system is said to be BIBO stable (bounded-input bounded-output stable) if every bounded
input sequence excites a bounded-output sequence. This stability is defined for the zero-state
response and is applicable only if the system is initially relaxed.
~ Theorem 5.01
A discrete-time SISO system described by (5.7) is BIBO stable if and only if g [k J is absolutely summable
in [0, 00) or
L00
Ig[kll ~ M < 00
k=O
for some constant M.

5.3 Internal Stability 129
It is not a rational function of ~ and Theorem 5.D3 is not applicable.
For multi variable discrete-time systems, we have the following results .
.c - Theorem S.MD 1
=
A !VIIMO discrete-time system with impulse response sequence matrix G[k] [gU[k]] is BlBO stable
if and only if every gu [k] is absolutely summable.
,;- Theorem S.MD3
[gU( .::)]
A MIMO discrete-time system with discrete proper rational transfer matrix G(~) = is BlBO
stable if and only if every pole of every gij (z) has a magnitude less than I.
We now discuss the BIBO stability of discrete-time state equations. Consider
x[k + I] = Ax[k] + Bu[k]
(5.10)
+
y[k] = Cx[k] Du[kJ
Its discrete transfer matrix is
Thus Equation (5.10) or, to be more precise, the zero-state response of (5.10) is BIBO stable
if and only if every pole of G(e) has a magnitude less .than I.
We discuss the relationship between the poles of G(z) and the eigenvalues of A. Because
of
- I
G(~) = C[Adj(zI - A)]B + D
det(.::I - A)
every pole of G(~) is an eigenvalue of A. Thus if every eigenvalue of A has a negative real
part. then (5.10) is BIBO stable. On the other hand. even if A has some eigenvalues with zero
or positive real part. (5.10) may, as in the continuous-time case. still be BIBO stable.
5.3 Internal Stability
The BIBO stability is defined for the zero-state response. Now we study the stability of the
zero-input response or the response of
x(t) = Ax(t) (5.1I )
excited by nonzero initial state Xo' Clearly, the solution of (5.11) is
x(r) = eAtxo (5.12)

5.3 Internal Stability 131
[~ ~ ~]
x = x
o
0 -I
is not marginally stable, however, because its minimal polynomial is A2 (,l, + I) and A = 0 is
not a simple root of the minimal polynomial.
As discussed earlier. every pole of the transfer matrix
is an eigenvalue of A. Thus asymptotic stability implies BIBO stability. Note that asymptotic
stability is defined for the zero-input response, whereas BIBO stability is defined for the
zero-state response. The system in Example 5.2 has eigenvalue 1 and is not asymptoti
cally stable; however, it is BIBO stable. Thus BlBO stability. in general. does not im
ply asymptotic stability. We mention that marginal stability is useful only in the design
of oscillators. Other than oscillators, every physical system is designed to be asymptoti
cally stable or BIBO stable with some additional conditions, as we will discuss in Chap
ter 7.
5.3.1 Discrete-Time Case
This subsection studies the internal stability of discrete-time systems or the stability of
+
x[k I] = Ax[k] (5.13)
excited by nonzero initial state Xo. The solution of (5.13) is, as derived in (4.20).
x[k] = Akxo (5.14)
Equation (5.13) is said to be marginally stable or stable in the sense of Lyapunov if every
finite initial state Xo excites a bounded response. It is asymptotically stable if every finite
initial state excites a bounded response. which, in addition. approaches 0 as k --+ 00. These
definitions are identical to the continuous-time case.
~ Theorem 5.04
1. The equation x[k + I J = Ax[k] is marginally stable if and only if all eigenvalues of A have
magnitudes less than or equal to I and those equal to I are simple roots of the minimal polynomial of
A.
+ =
2. The equation x[k 1] Ax[k] is asymptotically stable if and only if all eigenvalues of A have
magnitudes less than I.
As in the continuous-time case. any (algebraic) equi valence transformation will not alter
the stability of a state equation. Thus we can use Jordan form to establish the theorem. The
proof is similar to the continuous-time case and will not be repeated. Asymptotic stability

132 STABILITY
implies BIBO stability but not the converse. We mention that marginal stability is useful only
in the design of discrete-time oscillators. Other than oscillators. every discrete-time physical
system is designed to be asymptotically stable or BIBO stable with some additional conditions.
as we will discuss in Chapter 7.
5.4 Lyapunov Theorem
x
This section introduces a different method of checking asymptotic stability of = Ax. For
convenience. we call A stable if every eigenvalue of A has a negative real part.
Theorem 5.5
I
All eigenvalues of A have negative real partS'if and only if for any given positive definite symmetric
matrix N. the LyapullO" equation
A'M +MA =-N (5.15)
has a unique symmetric solution 1\1 and ]\II is positive definite.
Corollary 5.5
~II eigenvalues of an 11 x 11 matrix A have negative real parts if and only if for any given m x 11 matrix
N with In < 1/ and with the property
N
NA
rank 0 := rank = 11 (full column rank) (5.16)
where 0 is an /1111 x 11 matrix. the Lyapunov equation
A'M + MA = -N'N =: -N (5.17)
has a unique symmetric solution M and]\ll is positive definite.
For any:';, the matrix N in (5.17) is positive semidefinite (Theorem 3.7). Theorem 5.5
and its corollary are valid for any given N: therefore we shall use the simplest possible N.
Even so. using them to check stability of A is not simple. It is much simpler to compute,
using MATL\B, the eigenvalues of A and then check their real parts. Thus the importance
of Theorem 5.5 and its corollary is not in checking the stability of A but rather in studying
the stability of nonlinear systems. They are essential in using the so-called second method of
Lyapunov. We mention that Corollary 5.5 can be used to prove the Routh-Hurwitz test. See
Reference [6. pp. 417-419].
~ Proof of Theorem 5.5 Necessitv: Equation (5.15) is a special case of 0.59) with A = A'
=
and B A. Because A and A' have the same set of eigenvalues. if A is stable, A has no
+ =
two eigenvalues such that Ai A O. Thus the Lyapunov equation is nonsingular and
J
has a unique solution M for any N. We claim that the solution can be expressed as

130 STABILITY
x =
Definition 5.1 The :ero·input response of (5.4) or the equation Ax is marginally
stable or stable in the sense of Lyapunov if every finite initial state Xo excites a bounded
respollse. It is asymptotically stable ifeveryfinite initial state excites a bounded response,
which. in addition, approaches 0 as t -+ 00.
We mention that this definition is applicable only to linear systems. The definition that
is applicable to both linear and nonlinear systems must be defined using the concept of
equivalence states and can be found. for example, in Reference [6, pp. 401--403]. This text
studies only linear systems: therefore we use the simplified Definition 5.1.
>
Theorem 5.4
x = if
1. The equation Ax is marginally stable and only if all eigenvalues of A have zero or negative
real parts and those with zero real parts are simple roots of the minimal polynomial of A.
x
2. The equation = Ax is asymptotically stable if and only if all eigenvalues of A have negative real
parts.
We first mention that any (algebraic) equivalence transformation will not alter the stability
of a state equation. Consider i = Px, where P is a nonsingular matrix. Then x = Ax is
equivalent to X = Ax = PAP-t i. Because P is nonsingular, if x is bounded, so is x; if x
approaches 0 as t -+ 00, so does x. Thus we may study the stability of A by using A. Note
A
that the eigenvalues of A and of are the same as discussed in Section 4.3.
x = Ax xU) =
The response of excited by X(O) equals eAtx(O). It is clear that the
response is bounded if and only if every entry of eAt is bounded for all t 2: O. If A is in Jordan
form, then eAt is of the form shown in (3.48). Using (3.48), we can show that if an eigenvalue
has a negative real part. then every entry of (3.48) is bounded and approaches 0 as I -+ 00.
If an eigenvalue has zero real part and has no Jordan block of order 2 or higher. then the
corresponding entry in (3.48) is a constant or is sinusoidal for all t ~nd is. therefore. bounded.
This establishes the sufficiency of the first part of Theorem 5.4. If A has an eigenvalue with a
A
positive real part. then every entry in (3.48) will grow without bound. If has an eigenvalue
with zero real part and its Jordan block has order 2 or higher. then (3.48) has at least one entry
that grows unbounded. This completes the proof of the first part. To be asymptotically stable,
every entry of (3,48) must approach zero as t -+ 00. Thus no eigenvalue with zero real part is
permitted. This establishes the second part of the theroem.
EXAMPLE 5.4 Consider
1
[~ ~ ~
x
= x
o
0 -I
Its characteristic polynomial is ~(}..) = }.."(}.. + I) and its mimimal polynomial is >/I(}..) -
}..(}.. +
I). The matrix has eigenvalues O. O. and -I. The eigenvlaue 0 is a simple root of the
J
..j minimal polynomial. Thus the equation is marginally stable. The equation

|     |     |     |     |     |     | 5.4  | Lyapunov Theorem  | 133  |
| --- | --- | --- | --- | --- | --- | ---- | ----------------- | ---- |
l
X
Af
|     |     |     | M =  | eA'fNe | dt  |     |     | (5.18)  |
| --- | --- | --- | ---- | ------ | --- | --- | --- | ------- |
Indeed, substituting (5.18) into (5.15) yields
|        |       | 1'"  |         |     |     | 1'"    |       |     |
| ------ | ----- | ---- | ------- | --- | --- | ------ | ----- | --- |
|        |       |      |         | Af  | +   |        | Af    |     |
| A'M T  | MA =  |      | A'eAfNe |     | dl  | eA'fNe | A dl  |     |
l
:1
x
(eA'fNe~f)
|     |     | =     |        |     | dt =  |       | Ar  |         |
| --- | --- | ----- | ------ | --- | ----- | ----- | --- | ------- |
|     |     |       |        |     |       | eArNe | [0  |         |
|     |     | = 0 - | N =-N  |     |       |       |     | (5.19)  |
where we have used the fact eAf  =  0 at I =  :x for stable A. This shows that the M in
(5.18) is the solution. It is clear that if:,,\ is symmetric. so is M. Let us decompose N as
N =  r'I'N, where N is nonsingular (Theorem 3.7) and consider
r<
(X
|       | = 10  |                  |     |     | = 10  |               |     |        |
| ----- | ----- | ---------------- | --- | --- | ----- | ------------- | --- | ------ |
| x'Mx  |       | x'eA'fN'~eAfxdl  |     |     |       | i:NeArxll~dl  |     | (520)  |
Because both N and e-~r are nonsingular, for any nonzero x, the integrand of (5.20) is
¥
positive for every I.  Thus x'Mx is  positive for any x  O.  This  shows the positive
definiteness of M.
Sufficiency: We show that ifN and;\1 are positive definite, then A is stable. Let iI. be an
eigenvalue of A and v ¥ 0 be a corresponding eigenvector: that is, Ay  =
;.Y. Even though
A is a real matrix, its eigenvalue and eigenvector can be complex, as shown in Example 3.6.
=  = i. ·V·. where
Taking the complex-conjugate transpose of Av = iI. v yields v* A *  Y' A'
the asterisk denotes complex-conjugate transpose, Premultiplying v* and postmultiplying
v to (5,15) yields
|     | -v*Nv  | =   | v* A'l\h  | +  v*MAv  |     |     |     |     |
| --- | ------ | --- | --------- | --------- | --- | --- | --- | --- |
+
|     |     | =   | (iI.*  | i.)v*Mv =  | 2Re(iI.)v*Mv  |     |     | (5.21 )  |
| --- | --- | --- | ------ | ---------- | ------------- | --- | --- | -------- |
Because v*Mv and v*Nv are. as discussed in Section 3.9. both real and positive, (5.21)
implies ReO,)  <  O.  This shows that every eigenvalue of A has a negative real  part.
Q.E.D.
The proof of Corollary 5.5 follows the proof of Theorem 5,5 with some modific~tion. We
discuss only where the proof of Theorem 5.5 is not applicable. Consider (5 .20). Now N is m x n
with m  <  nand N =  N'N is positive semidefinite. Even so. M in (5.18) can still be positive
definite if the integrand of (5.20) is not identically zero for aliI. Suppose the integrand of (5.20)
is identically zero or Ne""x ==  0, Then its derivative with respect to I yields ;\'AeArx =  O.
Proceeding forward, we can obtain
N
NA
eArx = 0
(5.22)
NAn-I
This equation implies that. because of (5.16) and the nonsingularity of eAr. the only x meeting

5.4 Lyapunov Theorem 135
This shows the uniqueness of M. Although the solution can be expressed as in (5.24), the
integration is not used in computing the solution. It is simpler to arrange the Lyapunov equation,
after some transformations, into a standard linear algebraic equation as in (3.60) and then solve
the equation. Note that even if A is not stable, a unique solution still exists if A has no two
+ =
eigenvalues such that Ai Aj O. The solution, however, cannot be expressed as in (5.24);
the integration will diverge and is meaningless. If A is singular or, equivalently, has at least
one zero eigenvalue, then the Lyapunov equation is always singular and solutions mayor may
not exist depending on whether or not N lies in the range space of the equation.
5.4.1 Discrete-Time Case
Before discussing the discrete counterpart of Theorems 5.5 and 5.6, we discuss the discrete
counterpart of the Lyapunov equation in (3.59). Consider
M-AMB=C
where A and B are, respectively, n x nand m x m matrices. and M and Care n x m matrices.
As (3.60), Equation (5.25) can be expressed as Ym = c, where Y is an nm x nm matrix; m and
care nm x I column vectors with the m columns of M and C stacked in order. Thus (5.25) is
essentially a set of linear algebraic equations. Let 7]k be an eigenvalue of Y or of (5.25). Then
we have
=
7]k I - Ai/.Lj for i = 1,2, ... , n; j = 1,2, ... , m
where Ai and J.Lj are, respectively, the eigenvalues of A and B. This can be established intuitively
as follows. Let us define A(M) := M - AMB. Then (5.25) can be written as A(M) = C. A
scalar 7] is an eigenvalue of A if there exists a nonzero M such that A(M) = 7]M. Let u be
=
an n x 1 right eigenvector of A associated with Ai; that is, Au Ai u. Let v be a 1 x III left
=
eigenvector of B associated with J.Lj: that is, vB vJ.Lj. Applying A to the n x III nonzero
matrix uv yields
A(uv) = uv - AuvB = (1 - A,J.Lj)UV
Thus the eigenvalues of (5.25) are I - Ai J.Lj' for all i and j. If there are no i and j such that
AiJ.Lj = I, then (5.25) is nonsingular and, for any C, a unique solution M exists in (5.25). If
AiJ.Lj = I for some i and j, then (5.25) is singular and, for a given C, solutions mayor may
not exist. The situation here is similar to what was discussed in Section 3.7.
'>
Theorem 5.05
All eigenvalues of an n x n matrix A have magnitudes less than I if and only if for any given positive
= N'N, N
definite symmetric matrix N or for N where is any given m x n matrix with m < 11 and
with the property in (5.16), the discrete Lyapunov equation
M-A'MA=N (5.26)
has a unique symmetric solution 1\'1 and M is positive definite.

136 STABiLITY
We sketch briefly its proof for N > O. If all eigenvalues of A and. consequently, of A'
1=
have magnitudes less than I, then we have IAi;"-;I < I for all i and j. Thus A,-A} I and
(5.:!6) is nonsingular. Therefore, for any N, a unique solution exists in (5.26). We claim that
the solution can be expressed as
x
L
M = (A')"'NA'" (5.27)
m=O
Because lA, I < I for all i. this infinite series conwrges and is well defined. Substituting (5.27)
into (5.26) yie Ids
t(A,)mNA'" - A' (:t(A,)mNAm) A
m=O 111=0
= N + L(A')"'NA'" - L(A')"'NA'" = N
111=1 1Il=!
Thus (5.27) is the solution. If N is symmetric. so is M. If N is positive definite. so is M. This
establishes the necessity. To show sufficiency. let A be an eigenvalue of A and v 1= 0 be a
corresponding eigenvector: that is. Av = AV. Then we have
v'Nv = v'Mv - v' A'l\lAy
= =
v'Mv - A' y·l\h;. (I - IAI1)v'Mv
Because both v'N,· and v'Mv are real and positi\·e. we conclude (I - IAI") > 0 or IAI1 < I.
This establishes the theorem for N > O. The case N ~ 0 can similarly be established.
Theorem 5.06
[I' all eigenvalues of A have magnitudes less than i. then the discrete Lyapunov equation
M -A'MA = N
has a unique solution for every N. and the solution CJn be e.<pressed as
x
M = L(A')"'NA'"
111=0
It is important to mention that even if A has one or more eigenvalues with magnitudes
1=
larger than I. a unique solution still exists in the discrete Lyapunov equation if )., Aj I for all
i and j. In this case. the solution cannot be expressed as in (5.27) but can be computed from
a set of linear algebraic equations.
Let us discuss the relationships between the continuous-time and discrete-time Lyapunov
equations. The stability condition for continuous-time systems is that all eigenvalues lie
inside the open left-half s-plane. The stability condition for discrete-time systems is that all
eigenvalues lie inside the unit circle on the :-plane. Thl!se conditions can be related by the
bilinear transformation
:-1 1+ s
s=-- (5.28)
:+1 I-s

T
STABILITY
134
(5.22) is O. Thus the integrand of (5.20) cannot be identically zero for any x =f. O. Thus M is
positive definite under the condition in (5.16). This shows the necessity of Corollary 5.5. Next
we consider (5.21) with N =  N'N orl
|     | 2Re(A)v*Mv =  |     | -v*N'Nv = -IINvll;  |     |     | (5.23)  |
| --- | ------------- | --- | ------------------- | --- | --- | ------- |
| Nv  |               |     | Av                  |     |     |         |
We show that  is nonzero under (5.16). Because of  =  AV, we have A 2V =  AAv =  A2 V,
... ,An-Iv =  An-Iv. Consider
|     | N   |     | Nv  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
Nv
NAv
|     | NA  |     |     | ANv  |     |     |
| --- | --- | --- | --- | ---- | --- | --- |
v=
|     | NAn-I  |     | ]ijAn-lv  | An-'Nv  |     |     |
| --- | ------ | --- | --------- | ------- | --- | --- |
| -   |        |     | !         |         |     |     |
If Nv =  0, the rightmost matrix is zero; the leftmost matrix, however, is nonzero under the
conditions of (5.16) and v =f. O. This is a contradiction. Thus  Nv  is nonzero and (5.23) implies
Re(A)< O. This completes the proof of Corollary 5.5.
In  the  proof of Theorem of 5.5, we have established the following  result. For easy
reference, we state it as a theorem.
Theorem 5.6
~
If all eigenvalues of A have negative real parts, then the Lyapunov equation
A'M+MA= -N
has a unique solution for every N, and the solution can be expressed as
1
00
|     |     | M =  | eA'tNeAtdt  |     |     | (5.24)  |
| --- | --- | ---- | ----------- | --- | --- | ------- |
Because of the importance of this theorem, we give a different proof of the uniqueness
of the solution. Suppose there are two solutions MI and M 2. Then we have
|     | A'(MI - | M2) + (MI - | M2)A = 0  |     |     |     |
| --- | ------- | ----------- | --------- | --- | --- | --- |
which implies
|              |      |       | At                      |     | At        |     |
| ------------ | ---- | ----- | ----------------------- | --- | --------- | --- |
| eA't[A'(MI - | M +  | (MI - | M )Aje =  :t [eA't(MI - |     | M2)e j =  | 0   |
|              | 2)   |       | 2                       |     |           |     |
Its integration from 0 to 00 yields
M2)eAtjl~ = 0
[eA't (MI -
or, using eAt  '""*  0 as t ~ 00,
|     |     | 0-  | (M, - M 2) = 0  |     |     |     |
| --- | --- | --- | --------------- | --- | --- | --- |
I. Note that if x is a complex vector, then the Euclidean norm defined in Section 3.2 must be modified as Ilxll~ = x'x,
where x'"  is the complex conjugate transpose of x.

5.5 Stability of LTV Systems 137
which maps the left-half s-plane into the interior of the unit circle on the :-plane and \'ice
versa. To differentiate the continuous-time and discrete-time cases, we write
A'M + :\IA = -:\ (5.29)
and
(5.30)
Following (5.28). these two equations can be related by
Substituting the right-hand-side equation into IS.3D) and performing a simple manipulation.
we find
Comparing this with (5.29) yields
+
A = (Ad I)- I(Ad - I) (531 )
These relate (5.29) and (5.3D).
The MATLAB function lyap computes the Lyapunov equation in (5.29) and dlyap
computes the discrete Lyapunov equation in (S.3D). The function dlyap transforms (S.3D)
=
into (5.29) by using (5.31) and then calls lyap. The result yields M Md.
5.5 Stability of LN Systems
Consider a SISO linear time-varying (LTV) system described by
i l
y(l) = glr. rju(r)dr (5.32)
10
The system is said to be BIBO stable if every bounded input excites a bounded output. The
condition for (5.32) to be BIBO stable is that there exists a finite constant M such that
i
Ig(t. r )1d r :-::: M < x (533)
l
I"
for all I and 10 with I ~ [0. The proof in the time-invariant case applies here \\'ith only minor
modification.
For the multivuriable case. (5.32) becomes
il
y(c) = GU. r)u(r)dr (5.3'+)
Ie,
The condition for (5.34) to be BIBO stable is that every entry of G(I. r ) meets the condition
in (5.33). For multivariable systems. we can also express the condition in terms of norms. Any
norm discussed in Section 3.11 can be used. However. the infinite-norm
Ilull", = max IUil IIGllx = largest row absolute sum
e

5.5 Stability of LTV Systems 139
(5.37) depend on to? What is the rate for the state transition matrix to approach 0 in (5.38)?
The interested reader is referred to References [4, 15].
x
A time-invariant equation = Ax is asymptotically stable if all eigenvalues of A have
negative real parts. Is this also true for the time-varying case? The answer is negative as the
next example shows.
EXAMPLE 5.5 Consider the linear time-varying equation
-1 2t
x = A(t)x = 0 e ] x (5.39)
[
-I
The characteristic polynomial of A(r) is
). +
I
det().} - A(t» = det [ 0
Thus A (t) has eigenvalues -I and -I for all r. It can be verified directly that
t t
e- 0.5(eet_-t e- )]
4>(t,O)= 0
[
meets (4.53) and is therefore the state transition matrix of (5.39). See also Problem 4.16.
Because the (l,2)th entry of 4> grows without bound, the equation is neither asymptotically
stable nor marginally stable. This example shows that even though the eigenvalues can be
defined for A(t) at every t, the concept of eigenvalues is not useful in the time-varying case.
All stability properties in the time-invariant case are invariant under any equivalence
transformation. In the time-varying case, this is so only for BIBO stability, because the
impulse response matrix is preserved. An equivalence transformation can transform, as shown
= x=
in Theorem 4.3, any i A(r)x into Aox, where Ao is any constant matrix; therefore, in the
time-varying case, marginal and asymptotic stabilities are not invariant under any equivalence
transformation.
.. Theorem 5.7
x
Marginal and asymptotic stabilities of = A(r)x are invariant under any Lyapunov transformation.
As discussed in Section 4.6, if per) and per) are continuous, and per) is nonsingular
x = I
for all t, then P(t)x is an algebraic transformation. If, in addition, P(tl and p- (rJ are
x =
bounded for all r, then P(t)x is a Lyapunov transformation. The fundamental matrix XU)
x
of x = A(t)x and the fundamental matrix X(r) of = A(r)x are related by, as derived in
(4.71),
X(t) = P(r)X(r)
which implies
=
"'(t, r) X(r)X-I(r) = P(t)X(r)X-I(r)p-l(r)
= P(t)4>(t, r)p-I(r) (5.40)

140 STABILITY
Because bOlh °pe r) and p- l(t) are bounded, if 11<1>(1, r)11 is bounded, so is 114>(1. r)ll; if
1I<I>(t, r)ll-+ as 1-> 00. so is 114>(t, r)ll. This establishes Theorem 5.7.
In the time-invariant case, asymptotic stability of zero-input responses always implies
BlBO stability of zero-state responses. This is not necessarily so in the time-varying case. A
time-varying equation is asymptotically stable if
°
1I<I>(t. lo)l! -> aSI-> 00 (5.41)
for all I, [0 with , ~ '0. It is BIBO stable if
'
l
iIC(r)<I>(t. r)B(I)lldr < 00 (5.42)
10
'a
for all ,. with [ ~ '0. A function that approaches 0, as [ -+ 00, may not be absolutely
integrable. Thus asymptotic stability may jlot imply BlBO stability in the time-varying case.
However. if 11<1>(1. I)II decreases to zero rapidly. in particular. exponentially, and if C(tJ and
B(!) are bounded for all [, then asymptotic stability does imply BlBO stability. See References
[4,6. 15].
5.1 Is the network shown in Fig. 5.2 BlBO stable? If not. find a bounded input that will
PROBLEMS
excite an unbounded output.
Figure 5.2
r
+
u IF
\'
1-
5.2 Consider a system with an irrational transfer function g(s). Show that a necessary
5:::
condition for the system to be BIBO stable is that Ig(sJI is finite for all Re O.
5.3 Is a system with impllise response g (r) = 1/ (t + I) BIBO stable? How about g (r) = Ie-I
o?
for [ ~
+
5.4 Is a system with transfer function g(s) = e-~' / (5 I) BlBO stable')
5.5 Show that the negative-feedback system shown in Fig. 2.5(b) is BIBO stable if and only
=
if the gain a has a magnitude less than I. For a 1. find a bounded input r(r) that will
excite an unbounded output.
+
5.6 Consider a system with transfer function g(s) = (5 - 2)/ (s I). What are the steady-state
responses excited by u(1) = 3, for [ ~ 0, and by u![) = sin 21, for t ~ o?
5.7 Consider
x=[-~ 1~]x+[~2]u
y=[-23Jx-2u

138  STABILITY
is probably the most convenient to use in stability study. For convenience, no subscript will
be attached to any norm. The necessary and sufficient condition for (5.34) to be BIBO stable
is that there exists a finite constant M such that
i
|     | t IIG(t, r)11 dr ::::  | M < 00  |     |     |
| --- | ---------------------- | ------- | --- | --- |
to
for alII and 10 with I =::  10.
The impUlse response matrix of
|     | x        | +      |     |     |
| --- | -------- | ------ | --- | --- |
|     | = A(t)x  | B(t)u  |     |     |
(5.35)
|     | =         | +      |     |     |
| --- | --------- | ------ | --- | --- |
|     | y  C(t)x  | D(t)u  |     |     |
IS
|          | =                  | +          |     |     |
| -------- | ------------------ | ---------- | --- | --- |
| G(t, r)  | C(I)<I>(I, r)B(r)  | D(t).5(t - | r)  |     |
and the zero-state response is
it
| y(l) =  | C(t)<I>(t, r)B(r)u(r)dr +D(t)u(t)  |     |     |     |
| ------- | ---------------------------------- | --- | --- | --- |
to
Thus (5.35) or, more precisely, the zero-state response of (5.35) is BIBO stable if and only if
there exist constants M 1 and M 2 such that
|     | IID(t)11 :::: MI  | < 00  |     |     |
| --- | ----------------- | ----- | --- | --- |
and
i
IIG(I, r)lldr:::: M2 < 00
t
to
for alII and to with t =::  to.
Next we study the stability of the zero-input response of (5.35). As in the time-invariant
x =
case, we define the zero-input response of (5.35) or the equation  A(t)x to be marginally
stable if every finite initial state excites a bounded response. Because the response is governed
by
|     | xU) =  | <1>(1, (0)X(to)  |     | (5.36)  |
| --- | ------ | ---------------- | --- | ------- |
we conclude that the response is marginally stable if and only if there exists a finite constant
M such that
|      | 1I<I>(t, to)11  | ::::  M < 00  |     | (5.37)  |
| ---- | --------------- | ------------- | --- | ------- |
| =::  | x               |               |     |         |
for all to and for all t  to. The equation  =  AU)x is asymptotically stable if the response
excited by every finite initial state is bounded and approaches zero as I ~ 00. The asymptotic
stability conditions are the boundedness condition in (5.37) and
| II<I>U, to)11  | ~ 0  | aSI-->-cc  |     | (5.38)  |
| -------------- | ---- | ---------- | --- | ------- |
A great deal can be said regarding these definitions and conditions. Does the constant M  in

Problems 141
Is it BIBO stable"
5.8 Consider a discrete-time system with impulse response sequence
°
g[k] = k(0.8)k
for k :::
Is the system BlBO stable')
5.9 Is the state equation in Problem 5.7 marginally stableO Asymptotically stableO
5.1 0 Is the homogeneous state equation
-I
x = ~
[
marginally stable') Asymptotically stableO
5.11 Is the homogeneous state equation
-I
x=
~
[
marginally stable" .-\symptotically stable"
5.12 Is the discrete-time homogeneous state equation
I]
0.9 °
°
+
x[!.: IJ = ~ I x[k]
[ °
I
marginally stable" Asymptotically stable')
5.13 Is the discrete-time homogeneous state equation
°
09
x[k+IJ= ~ ~
[
marginally stable" .-\symptotically stableO
5.14 Use Theorem 5.5 to show that all eigenvalues of
_:]
= [_o.~
A
have negative real pans.
5.15 Use Theorem 5.D5 to show that all eigenvalues of the A in Problem 5.14 have magnitudes
less than I.
a,.
5.16 For any distinct negative real Ai and any nonzero real show that the matrix

r
I
Chapter
Controllability
and Observability
6.1 Introduction
This chapter introduces the concepts of controllability and observability. Controllability
deals with whether or not the state of a state-space equation can be controlled from the input,
and observability deals with whether or not the initial state can be observed from the output.
These concepts can be illustrated using the network shown in Fig. 6.1. The network has two
state variables. Let be the voltage across the capacitor with capacitance C for i = 1. 2.
Xj j,
The input u is a current source and the output y is the voltage shown. From the network. we
see that, because of the open circuit across r. the input has no effect on X2 or cannot control
X2. The current passing through the 2-Q resistor always equals the current source u; therefore
the response excited by the initial state Xi will not appear in y. Thus the initial state Xi cannot
be observed from the output. Thus the equation describing the network cannot be controllable
and observable.
These concepts are essential in discussing the internal structure of linear systems. They
are also needed in studying control and filtering problems. We study first continuous-time
Figure 6.1 Network. 1>2
1I IF
(current
service)
143

144 CONTROLLABILITY AND OBSERVABILITY
linear time-invariant (LTI) state equations and then discrete-time LTI state equations. Finally,
we study the time-varying case.
6.2 Controllability
Consider the n-dimensional p-input state equation
x
= Ax +Bu (6.1)
where A and B are, respectively, n x nand n x p real constant matrices. Because the output
does not play any role in controllability, we will disregard the output equation in this study.
Definition 6.1 The state equation (6.1) 01' the pair (A, B) is said to be controllable iflor
any initial state x(O) = Xo and allY filial state XI. there exists all input that tram/ers Xo
to XI ill afinite time. Otherwise (6.1) or (A. B) is said to be uncontrollable.
This definition requires only that the input be capable of moving any state in the state
space to any other state in a finite time: what trajectory the state should take is not specified.
Furthermore. there is no constraint imposed on the input: its magnitude can be as large as
desired. We gi ve an example to illustrate the concept.
EXAMPLE 6_1 Consider the network shown in Fig. 6.2(a). Its state variable x is the voltage
=
across the capacitor. If x(O) == 0, then x(t) 0 for all t :::: 0 no matter what input is applied.
This is due to the symmetry of the network. and the input has no effect on the voltage across
the capacitor. Thus the system or, more precisely, the state equation that describes the system
is not controllable.
Next we consider the network shown in Fig. 6.2(b). It has two state variables XI and
X2 as shown. The input can transfer XI or X2 to any value; but it cannot transfer XI and Xl
to any values. For example. if XI (0) = X2(0) = O. then no maller what input is applied,
XI (I) always equals x2(1) for all t :::: O. Thus the equation that describes the network is not
controllable.
-r+
,. .;.t -=T
IfI In +
+ + x _I IF x, iF x:
...:..L ...:..L
II '"
1/ '"
1!1 In
In In
( ') (b)
Figure 6.2 Uncontrollable networks.

142  STABILITY
2
| a   | alaz  |     | ala3  |
| --- | ----- | --- | ----- |
I
| 2AI  | AI  +A2  |     | AI  + A3  |
| ---- | -------- | --- | --------- |
-0
| azal  | a   | z   | a2a3  |
| ----- | --- | --- | ----- |
M=
|     | 2A2  |     | AZ + A3  |
| --- | ---- | --- | -------- |
A2 +  AI
2
| a3al    | a3a2     |     | _a_3   |
| ------- | -------- | --- | ------ |
| A3 +AI  | A3 + A2  |     | 2A3    |
is positive definite. [Hint: Use Corollary 5.5 and A=diag(AI, A2, A3)']
5.17  A real matrix M (not necessarily symmetric) is defined to be positive definite if x'Mx > 0
for any nonzero x. Is it true that the matrix M is positive definite if all eigenvalues of
M are real and positive or if all its leading principal minors are positive? If not, how do
you check its positive definitene~s? [Hint: Try
| [~2f  | ~]  [1~9  | ~)1  |     |
| ----- | --------- | ---- | --- |
5.18  Show that all eigenvalues of A have real parts less than -JL < 0 if and only if, for any
given positive definite symmetric matrix N, the equation
A'M+MA+ 2JLM =-N
has a unique symmetric solution M and M is positive definite.
5.19  Show that all eigenvalues of A have magnitudes less than p if and only if, for any given
positive definite symmetric matrix N, the equation
has a unique symmetric solution M and M is positive definite.
e-21/
5.20  Is a system with impulse response gU, T)  =  I-1rl, for t  2::  T, BLBO stable? How
about gU, T)  = sin t(e-(/-r)) cos T?
5.21  Consider the time-varying equation
| =       | +   |     |     |
| ------- | --- | --- | --- |
| i  2tx  | u   |     |     |
Is the equation EIBO stable? Marginally stable? Asymptotically stable?
5.22  Show that the equation in Problem 5.21 can be transformed by using  x  =  P(t)x, with
P(t) = e-I into
' ,
I'
| ~  = 0 ·x-  | +  e- u  | y=X  |     |
| ----------- | -------- | ---- | --- |
X
Is the equation ELBO stable? Marginally stable? Asymptotically stable? Is the transfor
mation a Lyapunov transformation?
5.23  Is the homogeneous equation
-1
| x =  | -31  |     |     |
| ---- | ---- | --- | --- |
[ -e
for to  2::  0, marginally stable? Asymptotically stable?

|     |     |     |     |     | 6.2  Controllability  | 145  |
| --- | --- | --- | --- | --- | --------------------- | ---- |
Theorem 6.1
The following stalemen!, are equivalent.
1.  The n-dimensional pair (A, B) is controllable.
2.  The Il  X n matrix
|                           |           | l'                 |     | l'              |        |        |
| ------------------------- | --------- | ------------------ | --- | --------------- | ------ | ------ |
|                           | \Vc(r) =  | eAt BB' eA'r dr =  |     | eAU r  !BB' eA  | r) dr  |        |
|                           |           |                    |     | -               | ,,-    | (6.2)  |
| is nonsingular for any f  | > O.      |                    |     |                 |        |        |
3.  The fI  X  np cOlltrollabilitv matrix
(6.3)
has rank n (full row rank).
+
4.  The Il  x  p) matrix [A - AI  B J has full row rank at every eigenvalue. A. of A.I
(II
5.  If. in addition. all eigenvalues of A have negative real parts. then the unique solution of
+
|     |     | AWe  | WeA' =  | -BB'  |     | (6.4)  |
| --- | --- | ---- | ------- | ----- | --- | ------ |
is positive definite. The solution is called the controllabilitv Gramia/! and can be expressed as
l X.
=
|     |     | W e  | eArBB' eA'r dr  |     |     | (6.S)  |
| --- | --- | ---- | --------------- | --- | --- | ------ |
Proof:  (I)  - (2):  First we show the equivalence of the two  forms  in  (6.2).  Define
~
r
| :=  ( - r. Then we have  |     |     |     |     |     |     |
| ------------------------ | --- | --- | --- | --- | --- | --- |
'
f
|     |       | rlBB' eA'U-rl dr =  |     | ~o                  |     |     |
| --- | ----- | ------------------- | --- | ------------------- | --- | --- |
|     | eAtr- |                     |     | eAT BB' eA'i (-df)  |     |     |
Jt=,
r=u
r
It becomes the first  fonn of (6.2) after replacing  by r. Because of the  foml of the
integrand. Wert) is always positive semidefinite; it is positive definite if and only if it is
nonsingular. See Section 3.9.
First we show that if W c(t) is nonsingular. then (6.1) is controllable. The response
of (6.1) at time fl was derived in (4.5) as
1"
|     | x(til = e'\'lx(O)  |     | +   | eAfI,-rIBu(r)dr  |     | 16.6)  |
| --- | ------------------ | --- | --- | ---------------- | --- | ------ |
=
| We claim that for any x(O)  |     | Xo and any X(tl) =  |     | XI. the input  |     |     |
| --------------------------- | --- | ------------------- | --- | -------------- | --- | --- |
u(t) = -B'e·\'(',
|     |     |     | -I)W,~I(fl)[eA'lxo - |     | xd  | (6 7)  |
| --- | --- | --- | -------------------- | --- | --- | ------ |
will transfer Xo to XI  at time fl. Indeed. substituting (6.7) into (6.6) yields
!. If A j" compl~x. then we must use complex numbers :lS scalars in checking the rank. See the discussion regarding
13.37).

|     |     |     | 6.2  | Controllability  | 147  |
| --- | --- | --- | ---- | ---------------- | ---- |
This contradicts the hypothesis that C has full row rank. This shows the equivalence of
(2) and (3).
(3)  - (4): If C has full row rank, then the matrix [A - AI  B) has full row rank at
every eigenvalue of A. If not, there exists an eigenvalue AI and a 1 x n vector q t= 0 such
that
which implies qA = Alq and qB =  O. Thus q is a left eigenvector of A. We compute
2
|     | qA =  (qA)A =  | (Alq)A = Aiq  |     |     |     |
| --- | -------------- | ------------- | --- | --- | --- |
Proceeding forward, we have qAk = Atq. Thus we have
| q[B AB  ...  | An-IB) =  | [qB  AlqB  | ...  A~-lqB) = 0  |     |     |
| ------------ | --------- | ---------- | ----------------- | --- | --- |
This contradicts the hypothesis that C has full row rank.
In order to show that p (C) < n implies p ([A - AI  B]) < n at some eigenvalue ),
I
of A, we need Theorems 6.2 and 6.6, which will be established later. Theorem 6.2 states
that controllability is invaraint under any equivalence transformation. Therefore we may
AI B])  < n at some eigenvalue of A, where (A, B) is equivalent to (A, B).
show p([A -
=
Theorem 6.6 states that if the rank of C is less than n or p (C)  n - m, for some integer
m ~ I, then there exists a nonsingular matrix P such that
|        |         |       | - [Be]  |     |     |
| ------ | ------- | ----- | ------- | --- | --- |
| A =    | =  [Ae  |       |         |     |     |
| PAP-I  |         | ~12]  |         |     |     |
|        |         |       | B=PB=   | 0   |     |
|        | o       | Ai    |         |     |     |
where Ai is m  x m. Let AI  be an eigenvalue of Ae and ql be a corresponding I x m
nonzero left eigenvector or qlAi = Alql. Then we have ql (Ae - All) =  O. Now we form
the 1 x n vector q :=  [0  qd. We compute
Be]
| - -              |     | [Ae-AII  | Ap  |     |         |
| ---------------- | --- | -------- | --- | --- | ------- |
| q[A-AIIB)=[Oqz)  |     |          | -"  | =0  | (6.10)  |
o
Ac-AIIO
which implies p([A - AI B])  <  n  and, consequently, p([A - AI  B))  <  n  at some
eigenvalue of A. This establishes the equivalence of (3) and (4).
(2) _  (S): If A is stable, then the unique solution of (6.4) can be expressed as in (6.S)
(Theorem S.6). The Gramian We is always positive semidefinite. It is positive definite if
and only if We is nonsingular. This establishes the equivalence of (2) and (S).  Q.E.D.
EXAMPLE 6.2
Consider the inverted pendulum srudied in Example 2.8. Its state equation was
developed in (2.27). Suppose for a given pendulum, the equation becomes
|     | 0  1     | 0   |     |     |     |
| --- | -------- | --- | --- | --- | --- |
| x   | =  0  0  | -I  |     |     |     |
000
|     | [   |     |     |     | (6.11)  |
| --- | --- | --- | --- | --- | ------- |
o
|     | 0   | S   |     |     |     |
| --- | --- | --- | --- | --- | --- |
=
y  [1  0 0 O)x

148 CONTROLLABILITY AND OBSERVABILITY
;1 We compute
I 0
o 2 -!~l
-2 0
o
-10
e
This matrix can be shown to have rank 4; thus the system is controllable. Therefore. if X3 =
deviates from zero slightly, we can find a control u to push it back to zero. In fact, a control
exists to bring x, = y, X3, and their derivatives back to zero. This is consistent with our
experience of balancing a broom on our palm.
The MATLAB functions c trb and " ram will generate the controllability matrix and
controllability Gramian. Note that the contrbllability Gramian is not computed from (6.5); it is
obtained by solving a set of linear algebraic equations. Whether a state equation is controllable
can then be determined by computing the rank of the controllability matrix or Gramian by
using rank in MATLAB.
EXAMPLE 6.3 Consider the platform system shown in Fig. 6.3; it can be used to study
suspension systems of automobiles. The system consists of one platform; both ends of the
platform are supported on the ground by means of springs and dashpots, which provide
viscous friction. The mass of the platform is assumed to be zero; thus the movements of
the two spring systems are independent and half of the force is applied to each spring
system. The spring constants of both springs are assumed to be I and the viscous friction
coefficients are assumed to be 2 and 1 as shown. If the displacements of the two spring
systems from equilibrium are chosen as state variables x, and x~, then we have x, + 2.i:, = u
and .\'2 + X2 = II or
. [- 0.5 0] [0.5]
X= o X+ 1I ( 6.12)
- I I
This state equation describes the system.
Now if the initial displacements are different from zero, and if no force is applied, the
platform will return to zero exponentially. In theory. it will take an infinite time for x, to equal
o = = -\.
exactly. Now we pose the problem. If xdO) 10 and X2(0) can we apply a force
to bring the platform to equilibrium in 2 seconds: The answer does not seem to be obvious
because the same force is applied to the two spring systems.
l
Figure 6.3 Platfonn system.
2u
Damping Damping Spring
codtit:ient coefficient constant
I
2

T
146 CONTROLLABILITY AND OBSERVABILITY
l
X(I)) = eAtlxo - (fot eA(tI-tlBB'eA'(tl-r)dr) W;I(II)[eAtIXo - xd
= eAtlXo - W e (t))W; I (rd(eAtlxo - xIl = XI
This shows that if We is nonsingular, then the pair (A, B) is controllable. We show the
converse by contradiction. Suppose the pair is controllable but We(tl) is not positive
definite for some 11. Then there exists an n X I nonzero vector v such that
which implies
(6.8)
for all r in [0, Id. If (6.1) is controllable, there exists an input that transfers the initial state
Atl
x(O) = e- v to x(t]) = 0 and (6.6) becomes
0= v + fotl eA(tl-r)Bu(r) dr
Its pre multiplication by v' yields
0= v'v+ fo" v'eA(tl-r)Bu(r)dr = IIvl12 +0
which contradicts v t= O. This establishes the equivalence of (I) and (2).
(2) ++ (3): Because every entry of eAtB is, as discussed at the end of Section 4.2, an
analytical function of t, if We (t) is nonsingular for some f, then it is nonsingular for all t
in (-00, 00). See Reference [6, p. 554]. Because of the equivalence of the two forms in
(6.2), (6.8) implies that We(r) is nonsingular if and only if there exists no n x I nonzero
vector v such that
for all I (6.9)
Now we show that if We(t) is nonsingular. then the controllability matrix C has full row
rank. Suppose C does not have full row rank, then there exists an n X I nonzero vector v
such that v' C = 0 or
for k = 0, 1,2, .. . , n - I
Because eAtB can be expressed as a linear combination of {B. AB . ... , An-I B} (Theorem
3.5), we conclude v' eAtB = O. This contradicts the nonsingularity assumption of Wc(t).
Thus Condition (2) implies Condition (3). To show the converse, suppose C has full row
rank but W e(r) is singular. Then there exists a nonzero v such that (6.9) holds. Setting
t = 0, we have v'B = O. Differentiating (6.9) and then setting I = 0, we have v' AB = O.
Proceeding fOIWard yields v' A kB = 0 for k = O. I. 2 .. ... They can be arranged as
v'(B AB ... An- IB]=v'C=O

|     |     |     |     |     |     |     |     |     | &.2  | Controllability  | 149  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ---- | ---------------- | ---- |
For Equation (6.12), we compute
05
-0.25]
| .,  |     |     |     |     | p([B  AB]) =  | p   | I   |     | -~   |     |     |
| --- | --- | --- | --- | --- | ------------- | --- | --- | --- | ---- | --- | --- |
|     |     |     |     |     |               |     | [   | -I  | - -  |     |     |
Thus the equation is controllable and, for any x(O), there exists an input that transfers x(O) to
o  in 2 seconds or in any finite time. We compute (6.2) and (6.7) for this system at II  = 2:
|     |     |     |     |        |     | ° ] [0.5J  |     |     |         | 0])  |     |
| --- | --- | --- | --- | ------ | --- | ---------- | --- | --- | ------- | ---- | --- |
|     |     |     |     | [2 ([  | °   |            |     |     | [e-O;r  |      |     |
e-0.5r
|     |     |     |          | 10  |      |     |     | [0.5  | I]  °  |       |      |
| --- | --- | --- | -------- | --- | ---- | --- | --- | ----- | ------ | ----- | ---- |
|     |     |     | Wc(2) =  |     |      |     |     |       |        |       | dr:  |
|     |     |     |          |     | e-r  |     | I   |       |        | e- r  |      |
0.3167]
= [0.2162
|     |     |     |     |     | 0.3167  0.4908  |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --------------- | --- | --- | --- | --- | --- | --- |
and
|     |     |     |           | -[0.5  | e-0.°5C2 -t)  |     |     |     |     |     |     |
| --- | --- | --- | --------- | ------ | ------------- | --- | --- | --- | --- | --- | --- |
|     |     |     | llJ(t) =  |        | I]            |     |     |     |     |     |     |
| ;   |     |     |           |        | [             |     |     |     |     |     |     |
'',;
|     |     |     | =   | -58.82eOSt +  |     |     |     |     |     |     |     |
| --- | --- | --- | --- | ------------- | --- | --- | --- | --- | --- | --- | --- |
27.96et
for r in [0, 2J. This input force will transfer x(O) =  [10  - I]' to [0  0]' in 2 seconds as shown
in Fig. 6.4(a) in which the input is also plotted. It is obtained by using the MATLAB function
~.~.
"'. 1
"   1 s ~::'"  an acronym for linear simulation. The largest magnitude of the input is about 45.
Figure 6.4(b) plots the input fA2  that transfers x(O) =  [10  - 1], to 0 in 4 seconds. We see
that the smaller the time interval, the larger the input magnitude. If no restriction is imposed on
the input, we can transfer x(O) to zero in an arbitrarily small time interval; however, the input
magnitude may become very large. If some restriction is imposed on the input magnitude, then
we cannot achieve the transfer as fast as desired. For example, if we require lu(t)1 <  9. for
all r. in Example 6.3, then we cannot transfer x(O) to 0 in less than ~ seconds. We remark that
the input U(I) in (6.7) is called the minimal energy cOlllrol in the sense that for any other input
|     | ii(t) that achieves the same trantsl fer, we have  |     |     |     |     |     | ltl  |     |     |     |     |
| --- | -------------------------------------------------- | --- | --- | --- | --- | --- | ---- | --- | --- | --- | --- |
l
|     |     |     |     |     | u'(t)ii(t)dl:::  |     |     | u'(tJu(t)dl  |     |     |     |
| --- | --- | --- | --- | --- | ---------------- | --- | --- | ------------ | --- | --- | --- |
|     |     |     |     |     | 10               |     | '0  |              |     |     |     |
60,,----,----,-----,----,
10~--_r----r_--_r----,
I
|     | f. ----I  |     |     | I   | I   |     |     |     | ,   | ,   |     |
| --- | --------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
40
|     |     |       | L   - - - - | "   - - | - - "  - - - - |     | 5             |     | ____  L ____ L __ _  |     |     |
| --- | --- | ----- | ----------- | ------- | -------------- | --- | ------------- | --- | -------------------- | --- | --- |
|     | i   |       | I           | I       | I              |     |               |     |                      |     |     |
|     | r   |  ---- |             | ,       | ,   UI         |     |               |     | Xl  :                |     |     |
|     | i,  |       | ,           |         | '              |     |               |     |                      |     |     |
|     | 20  |       | r - - - -   | T - -   | - - 1 - - --   |     |               |     |                      |     |     |
|     | ,   | Xl    | I           | I       | I              |     | 0----:-----.  |     |                      |     |     |
|     | !   |       | r           | I       | I              |     |               |     |                      |     |     |
0 1
----
|     | rI  --   | X l | :         |       |        |     | - 5      | - - - --;:'r--;:;:~"":'r-"  |           |       |     |
| --- | -------- | --- | --------- | ----- | ------ | --- | -------- | --------------------------- | --------- | ----- | --- |
|     | -:::0    | - - | r  - -- - |       |        |     |          |                             |           |       |     |
|     | -40L-__  |     | ____      | ____  |        |     | -10L-__  |                             | ____  __  | ____  |     |
|     |          | ~   | ~         |       | ~~--~  |     |          | ~                           | ~ ~       |       | _J  |
o
|     |             | 0.5  |                  |      | 1.5  2                 |     | 0   |     | 2 3  |     | 4   |
| --- | ----------- | ---- | ---------------- | ---- | ---------------------- | --- | --- | --- | ---- | --- | --- |
|     |             |      |                  | (a)  |                        |     |     |     | (b)  |     |     |
|     | Figure 6.4  |      | Transfer x(O) =  |      | [10  - I]' to [0 OJ'.  |     |     |     |      |     |     |

|     |     |     | 6.2  Controllability  | 151  |
| --- | --- | --- | --------------------- | ---- |
is called the controllability index of (A. B). Or, equivalently, if (A, B) is controllable. the
controllability index JL is the least integer such that
| =       |                |           | =   |         |
| ------- | -------------- | --------- | --- | ------- |
| p(Cp.)  | p«(B  AB  ...  | AP.-1Bj)  | n   | (6.15)  |
=  = ... =
Now we give a range of JL. If JLl  JL2  JLp, then n/ p  :::  JL. If all JLm. except
=
one, equal!, then JL  n - (p - 1); this is the largest possible JL. Let ii be the degree of the
minimal polynomial of A. Then, by definition, there exist aj such that
| An = alA | n 1 +     | + ... +  |      |     |
| -------- | --------- | -------- | ---- | --- |
|          | - a2An-2  |          | anI  |     |
which implies that AnB can be written as a linear combination of (B, AB, ... , An-IB). Thus
we conclude
| n/ p ::: JL  | ::: min(ii. n - | p  + I)  |     | (6.16)  |
| ------------ | --------------- | -------- | --- | ------- |
=
where p(B)  p. Because of (6.16). in checking controllability, it is unnecessary to check
the n x np matrix C. It is sufficient to check a matrix of lesser columns. Because the degree
of the minimal polynomial is generally not available-whereas the rank of B can readily be
computed-we can use the following corollary to check controllability. The second part of the
corollary follows Theorem 3.8.
,.  Corollary 6.1
The n-dimensional pair CA. B) is controllable if and only if the matrix
| C n- | + := (B  AB  | '"  An-PBl  |     | (6.17)  |
| ---- | ------------ | ----------- | --- | ------- |
| p    | l            |             |     |         |
=
where pCB)  p. has rank n or the n x n matrix C p+l C~_p+l is nonsingular.
n-
EXAMPLE 6.5  Consider the satellite system studied in Fig. 2.13. Its linearized state equation
was developed in (2.29). From the equation. we can see that the control of the first four state
variables by the first two inputs and the control of the last two state variables by the last input
are decoupled; therefore we can consider only the following subequation of (2.29):
|     | 1  0]  | [0  | 0]  |     |
| --- | ------ | --- | --- | --- |
o  oo
|     | 2     | I   | 0     |     |
| --- | ----- | --- | ----- | --- |
|     | o  o  | X+  |       |     |
|     | 1     | 0   | 0  u  |     |
(6.18)
o
|       | -2  0   | 0   | 1   |     |
| ----- | ------- | --- | --- | --- |
| y=[~  | ~  ~]x  |     |     |     |
0
=  =
where we have assumed, for simplicity. Wo  = m  ro  1. The controllability matrix of (6.18)
is of order 4 x 8. If we use Corollary 6.1. then we can' check its controllability by using the
following 4 x 6 matrix:
1  0
J]
o
2
(6.19)
o  =i
1
-2  0

152  CONTROLLABILITY Ai'iD OBSERVABILITY
It has rank 4. Thus (6.18) is controllable. From (6.19), we can readily verify that the control
lability indices are 2 and 2, and the controllability index is 2.
Theorem 6,2
The controllability property is invariant under any equivalence transfonnation.
-7
Proof'  Consider the pair (A, B) with controllability matrix
C =
|     |     | [B  AB  ...  | An-IB]  |     |
| --- | --- | ------------ | ------- | --- |
and its equivalent pair  (A, E)  with  A  =  PAP- I  and  E  =  PB, where P is a nonsingular
matrix. The coatrollability matrix of  (A. E)  is
| C   | [E  AE  | . -,'  An-IE]  |     |     |
| --- | ------- | -------------- | --- | --- |
=
|     | =  [PB  PAP-IPB  | ...           | PAn-Ip-IpB]  |         |
| --- | ---------------- | ------------- | ------------ | ------- |
|     | =  [PB  PAB      | ...  PAn-IB]  |              |         |
|     | =                |               | =            |         |
|     | P[B  AB          | ...  An-IB]   | PC           | (6.20)  |
Because P is nonsingular, we have PIC) = PIC) (see Equation (3.62». This establishes
Theorem 6.2.  Q.E.D.
Theorem 6,3
The set of the controllability indices of (A, B) is invariant under any equivalence transfomlation and
any reordering of the columns of B.
-7
Proof'  Let us define
(6.21 )
Then we have, following the proof of Theorem 6.2,
|     |     | PIC) =  p(Cd  |     |     |
| --- | --- | ------------- | --- | --- |
=
for  k  0, I, 2, .... Thus  the  set  of controllability  indices  is  invariant  under  any
equivalence transformation.
The rearrangement of the columns of B can be achieved by
B = BM
where ,\1 is a p x p nonsingular permutation matrix. It is straightforward to verify
| -.       | - -      | k-I -    | .                      |     |
| -------- | -------- | -------- | ---------------------- | --- |
| C .= [B  | AB  ...  | A  B] =  | Ckdtag(M. M, ... , M)  |     |
k
=  =
Because diag (M, M ..... M) is nonsingular. we have PIG)  p(Cic) for k  0. l. ....
Thus the set of controllability indices is invariant under any reordering of the columns of
B.
Q.E.D.
Because the set of the controllability indices is invariant under any equivalence transfor
mation and any rearrangement of the inputs. it is an intrinsic property of the system that the

1
150 CONTROLLABILITY AND OBSERVABILITY
Its proof can be found in Reference [6, pp. 556-558].
EXAMPLE 6.4 Consider again the platform system shown in Fig. 6.3. We now assume that the
viscous friction coefficients and spring constants of both spring systems all equal I. Then the
state equation that describes the system becomes
Clearly we have
-1 ]
=1
-1
and the state equation is not controllable. If XI (0) 1= X2(0), no input can transfer x(O) to zero
in a finite time. I
6.2.1 Controllability Indices
Let A and B be n x n and n x p constant matrices. We assume that B has rank p or full column
rank. If B does not have full column rank, there is a redundancy in inputs. For example, if
the second column of B equals the first column of B, then the effect of the second input
on the system can be generated from the first input. Thus the second input is redundant. In
conclusion, deleting linearly dependent columns of B and the corresponding inputs will not
affect the control of the system. Thus it is reasonable to assume that B has full column rank.
If (A, B) is controllable, its controllability matrix C has rank n and, consequently, n
linearly independent columns. Note that there are np columns in C; therefore it is possible to
find many sets of n linearly independent columns in C. We discuss in the following the most
important way of searching these columns; the search also happens to be most natural. Let b
i
be the ith column of B. Then C can be written explicitly as ,"-
(6.13)
Let us search linearly independent columns of C from left to right. Because of the pattern of
C. if Aib depends on its left-hand-side (LHS) columns, then A i +1 b will also depend on its
m m
LHS columns. It means that once a column associated with b becomes linearly dependent,
m
then all columns associated with b thereafter are linearly dependent. Let J.Lm be the number
m
of the linearly independent columns associated with b in C. That is, the columns
m
are linearly independent in C and Al'm+ib are linearly dependent for i = 0, I ..... It is clear
m
that if C has rank n, then
J.LI + J.L2 + ... + J.Lp = n (6.14)
The set {J.LI. J.L2 •••. , J.Lp} is called the controllability indices and
=
J.L max (J.L I, J.L2. . .• , J.L p)

6.3 Observability 153
state equation describes. The physical significance of the controllability index is not transparent
here: but it becomes obvious in the discrete-time case. As we will discuss in later chapters. the
controllability index can also be computed from transfer matrices and dictates the minimum
degree required to achieve pole placement and model matching.
6.3 Observability
The concept of observability is dual to that of controllability. Roughly speaking. controllability
studies the possibility of steering the state from the input: observability studies the possibility
of estimating the state from the output. These two concepts are defined under the assumption
that the state equation or. equivalently. all A. B. C. and D are known. Thus the problem of
observability is different from the problem of realization or identification. which is to determine
or estimate A. B. C. and D from the information collected at the input and output terminals.
Consider the n-dimensional p-input q-output state equation
x +
= Ax Bu
(622)
+
y = Cx Du
where A. B. C. and D are. respectively. /I x n.n x p, q X n, and q x p constant matrices.
Definition 6,01 The swte equation (6.22) is said to be observable if for allY unknOlt'n
initial state x(O). there exists a finite tl > 0 such that the knowledge of the input u and
the output y over [0, til suffices to determine uniqueiv the initial state x(O). Otherwise.
the equation is said to be unobservable.
EXAMPLE 6,6 Consider the network shown in Fig. 6.5. If the input is zero, no matter what the
initial voltage across the capacitor is, the output is identically zero because of the symmetry
of the four resistors. We know the input and output (both are identically zero), but we cannot
determine uniquely the initial state. Thus the network or. more precisely, the state equation
that describes the network is not observable.
EXAMPLE 6.7 Consider the network shown in Fig. 6.6(a). The network has two state variables:
the current XI through the inductor and the voltage x, across the capacitor. The input u is a
Figure 6.5 Unobservable network. I
IQ IQ
IF
+
I
1/ 'I." + \'
x
IQ IQ

6.3 Observability 155
~ Theorem 6.4
The state equation (6.22) is observable if and only if the n x n matrix
l'
Wo(t) = eA'TC'CeArdr (6.25)
is nonsingular for any t > 0.
Proof: We pre multiply (6.24) by eA"e' and then integrate it over [0, tIl to yield
([I 1'1
eA"C'CeA'dt)X(O) = eA"C'y(t)dt
If Wo(tIl is nonsingular, then
1'1
x(O) = W;I(tI) eA"C'y(t)dt (6.26)
This yields a unique x(O). This shows that if Wo(t), for any t > 0, is nonsingular, then
(6.22) is observable. Next we show that if Wo(td is singular or, equivalently, positive
semidefinite for all tl, then (6.22) is not observable. If Wo(tl) is positive semidefinite,
there exists an n x I nonzero constant vector v such that
which implies
(6.27)
for all t in [0, td. If u == 0, then XI (0) = v f. 0 and X2 (0) = 0 both yield the same
=
y(t) = CeA'x;(O) 0
Two different initial states yield the same zero-input response; therefore we cannot
uniquely determine x(O). Thus (6.22) is not observable. This completes the proof of
Theorem 6.4. Q.E.D.
We see from this theorem that observability depends only on A and C. This can also be
deduced from Definition 6.01 by choosing u(t) == O. Thus observability is a property of the
pair (A, C) and is independent ofB and D. As in the controllability part, ifWo(t) is nonsingular
for some t, then it is nonsingular for every t and the initial state can be computed from (6.26)
by using any nonzero time interval.
~ Theorem 6.5 (Theorem of duality)
The pair (A, B) is controllable if and only if the pair (A', B') is observable.

156 CONTROLLABILITY A,'JD OBSERVABILITY
:7
Proof: The pair (A. B) is controllable if and only if
lo'
W c(t) = eArBB'eA'rdr
is nonsingular for any t, The pair (A'. B') is observable if and only if. by replacing A by
A' and C by B' in (6.25).
lo'
Ar
Wo(tl = eArBB'e ' dr
is nonsingular for any t. The two conditions are identical and the theorem follows.
Q.E.D.
We list in the following the observahllity counterpart of Theorem 6.1. It can be proved
either directly or by applying the theorem of duality.
'> Theorem 6.01
The following statements are equivalent.
1. The n-dimensional pair (A, C) is observable.
2. The n x n matrix
16.28)
is nonsingular for any I > O.
3. The nq x 11 observabiliry matrix
C
CA
0= ( 6.29)
has rank n (full column rank). This matrix can be generated by calling obsv in MATLAB.
+
4. The (11 q) x n matrix
has full column rank at every eigenvalue. A, of A.
5. If. in addition. all eigenvalues of A have negative real parts. then the unique solution of
is positive definite. The solution is called the obsen'abiliry Gramian and can be expressed as
loX
Wo = eA'rC'CeArdr (6.31)

1
154 CONTROLLABILITY AND OBSERVABILITY
IH
u
(a) (b)
Figure 6.6 Unobservable network.
I
t
I current source. If u = 0, the network reduces to the one shown in Fig.6.6(b). If Xl (0) = a i' 0
= = =
and X2 0, then the output is identically zero. Any x(O) [a 0)' and U (I) 0 yield the same
output yet) == O. Thus there is no way to determine the initial state [a 0)' uniquely and the
equation that describes the network is not observable.
The response of (6.22) excited by the initial state x(O) and the input U(I) was derived in
(4.7) as
fa'
= + +
yet) CeAtx(O) C eA(t-r)Bu(r) dr Du(t) (6.23)
In the study of observability, ihe output y and the input u are assumed to be known; the inital
state x(O) is the only unknown. Thus we can write (6.23) as
(6.24)
where
fa'
yet)
:= y(I) - C eA(t-r)Bu(r) dr - DU(I)
is a known function. Thus the observability problem reduces to solving x(O) from (6.24). If
u == 0, then y(t) reduces to the zero-input response CeAtx(O). Thus Definition 6.01 can be
modified as follows: Equation (6.22) is observable if and only if the initial state x(O) can be
determined uniquely from its zero-input response over a finite time interval.
At
Next we discuss how to solve x(O) from (6.24). For a fixed I, Ce is a q x n constant
matrix, and y(I) is a q x I constant vector. Thus (6.24) is a set of linear algebraic equations
with n unknowns. Because of the way it is developed, for every fixed I, y(I) is in the range
At
space of Ce and solutions always exist in (6.24). The only question is whether the solution
At
is unique. If q < n, as is the case in general, the q x n matrix Ce has rank at most q and,
consequently, has nullity n - q or larger. Thus solutions are not unique (Theorem 3.2). In
conclusion, we cannot find a unique x(O) from (6.24) at an isolated I. In order to determine
x(O) uniquely from (6.24), we must use the knowledge of u(t) and yet) over a nonzero time
interval as stated in the next theorem.

6.3 Observability 157
6.3.1 ObseNobility Indices
Let A and C be n x nand q x n constant matrices. We assume that C has rank q (full row rank).
If C does not have full row rank, then the output at some output terminal can be expressed
as a linear combination of other outputs. Thus the output does not offer any new information
regarding the system and the terminal can be eliminated. By deleting the corresponding row.
the reduced C will then have full row rank.
If (A, C) is observable, its observability matrix 0 has rank n and, consequently, n linearly
independent rows. Let Ci be the ith row of C. Let us search linearly independent rows of 0 in
order from top to bottom. Dual to the controllability part, if a row associated with Cm becomes
linearly dependent on its upper rows. then all rows associated with Cm thereafter will also be
dependent. Let 1.Im be the number of the linearly independent rows associated with Cm. It is
clear that if 0 has rank 11. then
1.11 + V2 + ... + Vq = n (6.32)
The set {VI. V2 • ...• 1.Iq} is called the observability indices and
(6.33)
is called the observabilit\' index of (A, C). If (A, C) is observable. it is the least integer
such that
=n
Dual to the controllability part. we have
n / q ~ V ~ min (ii, n - q + 1) (6.34)
where p(C) = q and ii is the degree of the minimal polynomial of A .
. - Corollary 6.0 I
The n-dimensional pair (A. C) is observable if and only if the matrix
C
CA
On-q+1 = (6.35)
where p(C) = q. has rank 11 or the n x n matrix O~_q+1 On-q+1 is nonsingular.
>-
Theorem 6.02
The observability property is invariant under any equivalence transformation.

6.4 Canonical Decomposition 159
x = Ax+Bu
(6.38)
y = Cx+Du
Let x = Px. where P is a nonsingular matrix. Then the state equation
x
= Ax+Bu
(6.39)
y = Cx+Du
with A = PAP-I. B = PS. C = Cp-I. and D = D is equivalent to (6.38). All properties of
(6.38), including stability, controllability, and observability, are preserved in (6.39). We also
have
>-
Theorem 6.6
Consider the n-dimensional state equation in (6.38) with
p(e) = p([B AB ... An-Is)) = nl < n
We form the n x n matrix
where the first n I columns are any n linearly independent columns of C. and the remaining columns
1
can arbitrarily be chosen as long as P is nonsingular. Then the equivalence transformation x = Px or
X = p-IX will transform (6.38) into
(6.-W)
- -
where Ae is n I x n I and Ai is (n - n d x (n - n d. and the n I-dimensional subequation of (6.40).
Xc = Aexc + Beu
(6 ... 1)
is controllable and has the same transfer matrix as (6.38).
= x
Proof' As discussed in Section 4.3, the transfonnation x p-I changes the basis
I
of the state space from the orthononnal basis in (3.8) to the columns of Q := p- or
{ql •... , qn, . .... qn}. The ith column of A is the representation of Aqi with respect
=
to {ql ....• qn, . .... qn}. Now the vector Aqi. for i I. 2, ... • nlo are linearly
dependent on the set {ql .... , qn,); they are linearly independent of {qn,+I ..... qn}.
A B
Thus the matrix has the fonn shown in (6.40). The columns of are the representation
of the columns of S with resp;:ctto (q I, ... , qn, • ...• Qn). Now the columns of S depend
only on {ql ..... qn,}: thus B has the fonn shown in (6.40). We mention that if the n x p

160  CONTROLLABILITY AND OBSERVI\BILITY
matrix B has rank p and if its columns are chosen as the first p columns of P-' . then the
B
upper pan of  is the unit matrix of order p.
C
Let  be the controllability matrix of (6.40). Then we have piC) =  piC) =  n,. It
is straightforward to verify
- nJ   -
|     |     |     | AcBe  |     | A   | e   B e  | -~~~'Be ]  |     |     |
| --- | --- | --- | ----- | --- | --- | -------- | ---------- | --- | --- |
C=  [~c
|     |     |     |     | 0   |     | 0   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
- nl -
A~~'Be ]
|     |     |     | [~e  Ac  | Be  |     |     |     |     |     |
| --- | --- | --- | -------- | --- | --- | --- | --- | --- | --- |
=
0
| -   |     |     |     |     | -   | -   |     |     | - k- |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ---- |
where  ( . is the controllability matrix of (Ac. Be). Because the columns ot' AcBe. for
C
k ~ n " are linearly dependent on the columns of  c, the condition p( C)  =  11,  implies
p( Cel = n " Thus the n ,-dimensional state equation in (6.41) is controllable.
Next we show that (6.41) has the same transfer matrix as (6.38). Because (6.38) and
(6.40) have the same transfer matrix. we need to show only that (6.40) and (6.41) have
the same transfer matrix. By direct verification. we can show
|     | SI-OA |     | -A,:]-'=[(SI-Acr'  |     |     |     |     | M  ]  |     |
| --- | ----- | --- | ------------------ | --- | --- | --- | --- | ----- | --- |
e
|     | [   |     |      |      |     |     |       |     | (6.42 )  |
| --- | --- | --- | ---- | ---- | --- | --- | ----- | --- | -------- |
|     |     |     | sl - | Ai'  |     | 0   | (sl - | A   |          |
c')-'
where
Thus the transfer matrix of (6.40) is
|     |     |     | [51 - | -A,:  |     | ]-' [Be]  |     | D   |     |
| --- | --- | --- | ----- | ----- | --- | --------- | --- | --- | --- |
|     | t   | t]  |       | Ae    |     |           |     |     |     |
[
|     |             | ceo  |        |        |       |       | +    |            |     |
| --- | ----------- | ---- | ------ | ------ | ----- | ----- | ---- | ---------- | --- |
|     |             |      |        | .1'1 - | Ai'   |       | 0    |            |     |
|     |             | [c   | Co]    | A      |       | lV~]  |      | [Be]  + D  |     |
|     | =           |      | [(51 - | e )-'  |       |       |      |            |     |
|     |             | e    | c      | 0      | (sl-A |       | )-'  | 0          |     |
|     |             |      |        | -,-    |       |       | c    |            |     |
|     |             | -    | -      |        |       |       |      |            |     |
|     | =Ce(sI-Ac)  |      |        | Be+ D  |       |       |      |            |     |
which is the transfer matrix of (6.41). This completes the proof of Theorem 6.6.  Q.E.D.
x
In the equivalence transformation  = Px, the n-dimensional state space is divided into
two subspaces. One is the n ,-dimensional subspace that consists of all vectors of the form
[x;.
0,],: the other is the (n - n, )-dimensional subspace that consists of all vectors ot' the form
x;,]'.
[0'  Because (6.41) is controllable, the input u can transfer Xc from any state to any other
state. However. the input u cannot control Xc because. as we can see from (6.401. u does not
affect Xc  directly. nor indirectly through the state Xc.  By dropping the uncontrollable state
vector, we obtain a controllable state equation of lesser dimension that is zero-state equivalent
to the original equation.
EXAMPLE 6.8  Consider the three-dimensional state equation
|     |     |     |     |     |     |     | y = [I  | I  Ilx  | (6.43 )  |
| --- | --- | --- | --- | --- | --- | --- | ------- | ------- | -------- |

,
,
158 CONTROLLABILITY AND OBSERVABILITY
,I
~ Theorem 6.03
The set of the observability indices of (A, C) is invariant under any equivalence transfonnation and any
reordering of the rows of C.
Before concluding this section. we discuss a different way of solving (6.24). Differenti
ating (6.24) repeatedly and setting t = 0, we can obtain
C yeO)
CA YeO)
=
x(O)
I
t
or
(6.36)
Y'
where yU)(t) is the ith derivative of y(t), and yeO) := W(O) (0) .,. (y(v-I))']'. Equation
(6.36) is a set of linear algebraic equations. Because of the way it is developed, yeO) must lie
in the range space of Ov, Thus a solution x(O) exists in (6.36). If (A, C) is observable, then
Ov has full column rank and, following Theorem 3.2, the solution is unique. Premultiplying
(6.36) by 0:, and then using Theorem 3.8, we can obtain the solution as
(6.37)
We mention that in order to obtain YeO), yeO), ... , we need knowledge of y(t) in the neigh
borhood of t = O. This is consistent with the earlier assertion that we need knowledge of y(t)
over a nonzero time interval in order to determine x(O) uniquely from (6.24). In conclusion,
the initial state can be computed. using (6.26) or (6.37).
The output yet) measured in practice is often corrupted by high-frequency noise. Because
• differentiation will amplify high-frequency noise and
• integration will suppress or smooth high-frequency noise,
the result obtained from (6.36) or (6.37) may differ greatly from the actual initial state. Thus
(6.26) is preferable to (6.36) in computing initial states.
The physical significance of the observability index can be seen from (6.36). It is the
smallest integer in order to determine x(O) uniquely from (6.36) or (6.37). It also dictates the
minimum degree required to achieve pole placement and model matching, as we will discuss
in Chapter 9.
6.4 Canonical Decomposition
This section discusses canonical decomposition of state equations. This fundamental result will
be used to establish the relationship between the state-space description and the transfer-matrix
description. Consider

161
6.4  Canonical DecompOsition
|     |     |     |     | = [B  AB I. instead of C = [B  |     |     |
| --- | --- | --- | --- | ------------------------------ | --- | --- |
The rank of B is 2; therefore we can use C~  AB  A 'Bl. to check
the controllability of (6"+3) (Corollary 6.1). Because
0  I
|     | p(C~)=p([B ABj)=p  |     |     | I    | 0   |     |
| --- | ------------------ | --- | --- | ---- | --- | --- |
|     |                    |     |     | [ o  |     |     |
I
the state equation in (6.-13) is not controllable. let us choose
The first two columns ofQ are the first two linearly independent columns of C,; the last column
x
| is chosen arbitrarily to make Q nonsingular. let  |     |     |     |     | = Px. W | e co m p ute  |
| ------------------------------------------------- | --- | --- | --- | --- | ------- | ------------- |
|                                                   |     |     |     |     | n       | [ ;    n      |
i -:l [i
~
I
A = PAP-
=  [:
|     |     | o   |     | 0   |     |     |
| --- | --- | --- | --- | --- | --- | --- |
o
o
0
n
n
I
-:l [;
|     | B  = PB= [:  | 0   |     |     | -   |     |
| --- | ------------ | --- | --- | --- | --- | --- |
[:
|     |     | 0   |     | n   |     |     |
| --- | --- | --- | --- | --- | --- | --- |
I
c
|     | = Cp- I  | =  [I  |           | 0   |        |           |
| --- | -------- | ------ | --------- | --- | ------ | --------- |
|     |          |        | I  II [;  |     | =  [I  | 2 :  I J  |
;.Iote that the  I x  2 submatrix A21  of A and  Be  are zero as expected. The 2 x  I submatrix
'.\12 happens to be zero; it could be nonzero. The upper part of  B  is a unit matrix because the
columns of B are the first two columns of Q. Thus (6.43) can be reduced to
|     | .   | [I   |     |         |     |     |
| --- | --- | ---- | --- | ------- | --- | --- |
|     |     | 0]_  |     | [I  0]  |     |     |
°
|     | XC =  |       | +   |     | y =  | [I  2Jxc  |
| --- | ----- | ----- | --- | --- | ---- | --------- |
|     |       | I  I  |     | 1   | u    |           |
Xc
This equation is controllable and has the same transfer matrix as (6.43).
The MATlAB function c trbf transforms (6.38) into (6.-10) except that the order of the
columns in p-I
is reversed. Thus the resulting equation has the form
Theorem 6.6 is established from the controllability matrix. In actual computation. it is unnec
essary to form the controllability matrix. The result can be obtained by carrying out a sequence

6.4 Canonical Decomposition 163
~ Theorem 6.7
Every state-space equation can be transformed, by an equivalence transformation, into the following
canonical form
(6.45)
Y = [Ceo 0 Ceo O]x + Du
where the vector xeo is controllable and observable. xc'; is controllable but not observable. x"o is
observable but not controllable. and xc'; is neither controllable nor observable. Furthermore. the state
equation is zero-state equivalent to the controllable and observable state equation
xeo = Acoxco + Beau
(6.-16)
and has the transfer matrix
_I -
A _ _ +
G(s) = CeD(sI - Aea) Bea D
This theorem can be illustrated symbolically as shown in Fig. 6.7. The equation is first
decomposed, using Theorem 6.6. into controllable and uncontrollable subequations. We then
decompose each subequation, using Theorem 6.06, into observable and unobservable pans.
From the figure, we see that only the controllable and observable part is connected to both
the input and output tenninals. Thus the transfer matrix describes only this part of the system.
This is the reason that the transfer-function description and the state-space description are not
Aco
necessarily equivalent. For example. if any A-matrix other than has an eigenvalue with a
Figure 6.7 Kalman decomposition.
co
r--
u Y
co
-
- -- - -
I I
I I
I CO I
I I
c
G

164 CO:-':TROLL,-\BILITY AND OBSERVABILITY
positi\e real pan, then some state variable may grow without bound and the system may bum
OLlt. This phenomenon, however. cannot be detected from the transfer matrix,
The MATLAB function mi:-.:-eal. an acronym for minimal reali:ation. can reduce any
stJte equation to (6.46). The reason for calling it minimal realization will be gi\'en in the next
chapter.
EXAMPLE 6.9 Considerthe network shown in Fig. 6.8(a). Because the input is a current source,
responses due to the initial conditions in C 1 and LI will not appear at the output. Thus the state
\'ariables associated with C and L are not observable: whether or not they are controllable
1 1
is immaterial ir. subsequent discussion. Similarly. the state variable associated with L2 is not
controllable. Because of the symmetry of the four I-Q resistors. the state variable associated
\\ith C: is neither controllable nor observable. By dropping the state variables that are either
uncontrollable or unobservable. the network in Fig. 6.S(a) can be reduced to the one in Fig.
6.S(b). The current in each branch is u!2: thus the output y equals 2 . (11/2) or y = u. Thus
the transfer function of the network in Fig. 6.8(a) is g(s) = I.
[I' we assign state variables as shown, then the network can be described by
[05]
-0.5 0
[: 0 0 o ]
x- ~I
. - 0
0 -0.5 + :
X u
0 0 0
y = [0 0 o I]x + II
Because the equation is already of the form shown in (6.·W). it can be reduced to the following
controllable state equation
x, = [~ -~.5 ] Xc + [0~5] u
,. = [0 Olx, +
II
The output is independent of x, : thus the equation can be further reduced to \. = 11. This is
what we will obtain by using the \IATLAB function m~:-:real.
6.5 Conditions in Jordan-Form Equations
Controllability and observability are invariant under any equivalence transformation. If a state
equation is transformed into Jordan form. then the controllability and observabilit), conditions
become \'ery simple and can often be checked by inspection. Consider the state equation
x = Jx + Bx
(647)
y = Cx

~l
162 CONTROLLABILITY AND OBSERVABILITY I
i
of similarity transformations to transform [B AJ into a Hessenberg form. See Reference [6,
pp. 220-222J. This procedure is efficient and numerically stable and should be used in actual
computation.
Dual to Theorem 6.6, we have the following theorem for unobservable state equations.
:> Theorem 6.06
Consider the n-dimensional state equation in (6.38) with
C
CA
=
p(O) p
I .
CAn-I
We form the n x n matrix
PI
=
p P
n2
pn
where the first n2 rows are any n2linearly independent rows of 0, and the remaining rows can be chosen
arbitrarily as long as P is nonsingular. Then the equivalence transformation x = Px will transform
(6.38) into
- [xo]
y = [Co OJ ~.; + Du (6.44)
Ao Ao
where is nz x nl and is (n - n2) x (n - lI2), and the n2-dimensional subequation of (6.44),
Xo = A,.xo + Bou
y = Coxo +Du
is observable and has the same transfer matrix as (6.38).
x =
In the equivalence transformation Px, the n-dimensional state space is divided
into two subspaces. One is the nl-dimensional subspace that consists of all vectors of the
form [x~ 0']'; the other is the (n - n2)-dimensional subspace consisting of all vectors of the
form [0' x~]'. The state Xo can be detected from the output. However, Xo cannot be detected
from the output because, as we can see from (6.44), it is not connected to the output either
xo.
directly, or indirectly through the state By dropping the unobservable state vector, we obtain
an observable state equation of lesser dimension that is zero-state equivalent to the original
equation. The MATLAB function obsvf is the counterpart of ctrbf. Combining Theorems
6.6 and 6.06, we have the following Kalman decomposition theorem.

6.5 Conditions in Jordan-Form Equations 165
C = 2
I R = 1
+
XI
+
Xz LI = 1 1" 1 " L, = 1 X,
+ X3 - 111 1"
t
\ t
u
C, = 2 u
1"
1 Q 1 Q lQ
(aJ
Figure 6.8 Networks.
where J is in Jordan form. To simplify discussion. we assume that J has only two distinct
eigenvalues AI and 1.2 and can be written as
,
where JI consists of all Jordan blocks associated with Al and J2 consists of all Jordan blocks
associated with ).2- Again to simplify discussion. we assume that J I has three Jordan blocks
and J2 has two Jordan blocks or
JI = diag (JII' J12. J\3)
The row of B corresponding to the last row of J'J is denoted by b l,], The column of C
corresponding to the first column of J'] is denoted by Cj,}'
Theorem 6.8
1. The state equation in (6.47) is controllable if and only if the three row vectors {bill. b ll2. b!l)} are
linearly independent and the two row vectors {b121 . b122} are linearly independent.
2. The state equation in (6.47) is observable if and only if the three column vectors {cill. Cj12. Cj\3}
are linearly independent and the two column vectors {C/21. e122} are linearly independent.
We discuss first the implications of this theorem. If a state equation is in Jordan form.
then the controllability of the state variables associated with one eigenvalue can be checked
independently from those associated with different eigenvalues. The controllability of the state
variables associated with the same eigenvalue depends oilly on the rows of B corresponding
to the last row of all Jordan blocks associated with the eigenvalue. All other rows of B play no
role in determining the controllability. Similar remarks apply to the observability part except
that the columns of C corresponding to the first column of all Jordan blocks determine the
observability. We use an example to illustrate the use of Theorem 6.8.

|     |     |     | 6.5  Conditions in Jordan-Form Equations  |     | 167  |
| --- | --- | --- | ----------------------------------------- | --- | ---- |
u
U
==;{bfll
u
| :=~~ bIZ!  | 1---1  | +}--t  |     |     |     |
| ---------- | ------ | ------ | --- | --- | --- |
S - AZ
5 - Al
| Figure 6.9  | Block diagram of (6.48).  |     |     |     |     |
| ----------- | ------------------------- | --- | --- | --- | --- |
x
-
5
| Figure 6.10  | Internal structure of I/(s - | Ad.  |     |     |     |
| ------------ | ---------------------------- | ---- | --- | --- | --- |
The Jordan-form matrix J has two distinct eigenvalues AI  and ,1.2. There are two Jordan
=
blocks associated with AI  and one associated with )'2. If S  AI. (6.49) becomes
|     | 0  -1  0  | 0  0  | 0  0  |     |     |
| --- | --------- | ----- | ----- | --- | --- |
bill
|     | 0  0  -1  | 0  0  | 0  0  | b   |     |
| --- | --------- | ----- | ----- | --- | --- |
211
0  0  0  0
|     | 0        |        | 0  0  | bill  |         |
| --- | -------- | ------ | ----- | ----- | ------- |
|     | 0  0  0  | 0  -1  | 0  0  |       | (6.50)  |
bill
|     | 0  0  0  | 0  0  | 0  0  |     |     |
| --- | -------- | ----- | ----- | --- | --- |
b/J2
|     | 0  0  0  | 0  0  | AI  - ,1.2  -1  | bl2l  |     |
| --- | -------- | ----- | --------------- | ----- | --- |
|     | 0  0  0  | 0  0  | 0               | b     |     |
|     |          |       | AI  - ,1.2      | l21   |     |

168  CONTROLLABILITY AND OBSERVABILITY
The rank ot the matrix will  not change by elementary column operations. We add the
product of the second column of (6.50) by bill to the last block column. Repeating the
process for the third and fifth columns. we can obtain
-I
| 0     | 0  0  0   | 0   | 0  0  |     |
| ----- | --------- | --- | ----- | --- |
| 0  0  | -I  0  0  | 0   | 0  0  |     |
| 0  0  |           | 0   | 0     |     |
|       | 0  0  0   |     | bill  |     |
| 0  0  | 0  0  -I  | 0   | 0  0  |     |
| 0  0  | 0  0  0   | 0   | 0     |     |
bll2
-1
| 0  0  | 0  0  0  | i' - A2  | bl:1  |     |
| ----- | -------- | -------- | ----- | --- |
l
| 0  0  | 0  0  0  | 0  Al -)..2  |     |     |
| ----- | -------- | ------------ | --- | --- |
bl21
Because i. and Ae  are distinct. A I  )j2 is nonzero. We add the product of the seventh
| 1   | -   |     |     |     |
| --- | --- | --- | --- | --- |
column and -blel ( (AI - A2) to the last tolumn and then use the sixth column to eliminate
its right-hand-,ide entries to .v ield
~
-I
| 0     | 0  0  0   | 0   | 0  0  |          |
| ----- | --------- | --- | ----- | -------- |
| 0  0  | -1  0  0  | 0   | 0  0  |          |
| 0  0  | 0  0      | 0   | 0     |          |
|       | 0         |     | bill  |          |
| 0  0  | 0  0  -I  | 0   | 0  0  | (6.51)   |
| 0  0  | 0  0  0   | 0   | 0     |          |
bil2
| 0  0  | 0  0  0  | - A2  | 0  0  |     |
| ----- | -------- | ----- | ----- | --- |
" I
| 0  0  | 0  0  0  | 0  Al  | - A2  0  |     |
| ----- | -------- | ------ | -------- | --- |
It is clear that the matrix in (6.51) has full row rank if and only if bill and bl12 are linearly
independent. Proceeding similarly for each eigenvalue, we can establish Theorem 6.S.
Q.E.D.
Consider an n-dimensional Jordan-form state equation with p inputs and q outputs. If
there are 111, with m >  P. Jordan blocks associated with the same eigenvalue. then 11/ number
of I x  p row vectors can never be linearly independent and the state equation can never be
controllable. Thus a necessary condition for the state equation to be controllable is 11/  p.
::::
Similarly. a necessary condition for the state equation to be observable is 111  ~ q. For the
single-input or smgle-output case. we then have the following corollaries.
Corollary 6.8
A singlc:-input Jordln-forrn state equation is controllable if and only if there is only one Jordan block
as>c'ciatcd with each distinct eigenvalue and every entry of B corresponding to the la,1 ro", of each Jordan
bloc'k is different from zero.
Corollary 6.08
A ,ingle-outpUI Jordan-foml state equation is observable if and only if Ihere is only one Jordan block
assodated with each distin,t eigenvalue and every entry of C mrresponding to the first column of each
Jordan block is different from zero.

166  CONTROLLABILITY AND OBSERVABILITY
EXAMPLE 6.10  Consider the Jordan-form state equation
|      | )'1  | 1   | 0   | 0  0  | 0  0  |     | 0   | 0  0  |       |     |
| ---- | ---- | --- | --- | ----- | ----- | --- | --- | ----- | ----- | --- |
|      | 0    | AI  | 0   | 0  0  | 0  0  |     | 1   | 0  0  |       |     |
|      | 0    | 0   | AI  | 0  0  | 0  0  |     | 0   | 0     |       |     |
| x==  | 0    | 0   | 0   | 0     | 0  0  | x+  |     |       | 1  u  |     |
AI
|     | 0   | 0   | 0   | 0   | 0   |     | 1   | 2  3  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ----- | --- | --- |
A2
(6.48)
0
|     | 0   | 0   | 0   | 0  0  | A2     |     | 0   |     |     |     |
| --- | --- | --- | --- | ----- | ------ | --- | --- | --- | --- | --- |
|     | 0   | 0   | 0   | 0  0  | 0  A2  |     |     |     |     |     |
[i
|     |     | I  2  | 0  0  | 2   |     |     |     |     |     |     |
| --- | --- | ----- | ----- | --- | --- | --- | --- | --- | --- | --- |
|     |     | 0     | 2  0  | I   |     |     |     |     |     |     |
Y ==
nX
|     |     | 0  2  | 3  0  | I"  |     |     |     |     |     |     |
| --- | --- | ----- | ----- | --- | --- | --- | --- | --- | --- | --- |
!-
The matrix J has two distinct eigenvalues AI  and Az. There are three Jordan blocks, with order
2, I. and I, associated with AI . The rows of B corresponding to the last row of the three Jordan
blocks are [1 0 OJ. [0 1 0], and [1  1 IJ. The three rows are linearly independent. There is only
one Jordan block. with order 3. associated with A2. The row ofB corresponding to the last row
of the Jordan block is [1  I IJ. which is nonzero and is therefore linearly independent. Thus we
conclude that the state equation in (6.48) is controllable.
The conditions for (6.48) to be observable are that the three columns [I I I]'. [2 1 2]"  and
[023], are linearly independent (they are) and the one column [000]' is linearly independent
(it is not). Therefore the state equation is not observable.
Before proving Theorm 6.8, we draw a block diagram to show how the conditions in the
theorem arise. The inverse of (sl - J) is of the form shown in (3.49), whose entries consist
of only lies - Ai)k. Using (3.49), we can draw a block diagram for (6.48) as shown in Fig.
6.9. Each chain of blocks corresponds to one Jordan block in the equation. Because (6.48) has
four Jordan blocks, the figure has four chains. The output of each block can be assigned as a
state variable as shown in Fig. 6.10. Let us consider the last chain in Fig. 6.9. Ifb == 0, the
l2l
state variable X/21  is not connected to the input and is not controllable no matter what values
bz21  and bm  assume. On the other hand. if bl2l  is nonzero, then all state variables in the
chain are controllable. If there are two or more chains associated with the same eigenvalue,
then we require the linear independence of the first gain vectors of those chains. The chains
associated with different eigenvalues can be checked separately. All discussion applies to the
observability part except that the column vector eji} plays the role of the row vector b li}.
a
Proof of Theorem 6.8  We prove the theorem by using the condition that the matrix
[A - sl BJ or [sl - A  BJ has full row rank at every eigenvalue of A. In order not to be
| overwhelmed by notation, we assume [sl - |      |     |     |         | J  BJ to be of the form  |     |     |     |       |         |
| ---------------------------------------- | ---- | --- | --- | ------- | ------------------------ | --- | --- | --- | ----- | ------- |
| s - AI                                   | -1   |     | 0   | 0       | 0                        |     | 0   | 0   | bill  |         |
| 0                                        |      | AI  | -I  | 0       | 0                        |     | 0   | 0   |       |         |
|                                          | S  - |     |     |         |                          |     |     |     | b2l1  |         |
| 0                                        | 0    |     | AI  | 0       | 0                        |     | 0   | 0   |       |         |
|                                          |      | S   | -   |         |                          |     |     |     | bill  |         |
| 0                                        | 0    |     | 0   | s - AI  | -I                       |     | 0   | 0   |       | (6.49)  |
bll2
| 0   |     |     |     | 0   |         |     | 0   | 0       |       |     |
| --- | --- | --- | --- | --- | ------- | --- | --- | ------- | ----- | --- |
|     | 0   |     | 0   |     | S - AI  |     |     |         | bll2  |     |
| 0   | 0   |     | 0   | 0   | 0       | s - | A2  | -I      | bl2l  |     |
| 0   | 0   |     | 0   | 0   | 0       |     | 0   | s - A2  | bl21  |     |

6.6 Discrete-Time State Equations 169
EX.-\;\IPLE 6.11 Consider the state equation
jJ [n
j
,~ [~ ~
+
( 6.52)
\=[I002Jx
There are two Jordan blo~ks. one with order 3 and associated with eigenvalue O. the other with
order 1 and associated with eigenvalue -2. The entry of B corresponding to the last row of
the first Jordan block is zero: thus the state equation is not controllable. The two entries of C
corresponding to the first column of both Jordan blocks are different from zero: thus the state
equation is obser'able.
6.6 Discrete-Time State Equations
Consider the n-dimensional p-input q-output state equation
+ +
x[k 1] = Ax[k] Bu[k]
(6.53)
y[k] = Cx[k]
where A_ B, and C are. respectively, 11 x 11.11 X p. and q x /1 real constant matrices.
Definition 6.DI The disCI't'rt'-time stare equalioll (6.53) or the pair (A. B) is said to be
controllable ifjorallY illirial state x(O) = Xo lIlld allvfillal Slalt' Xl. rhere exisrs (/11 illput
sequence oj fillile lellgrh Ihal rransjers Xo to Xl. OrherH'ise rhe equatioll or (A. B) is
said to he uncontrollable.
Theorem 6.01
The following statements ~re equivalent:
I. The l1-dimensional pair (A. B) is controllable,
2. The 11 x /1 malrix
11-1
W,icIll - 11 = :L.:>A)"'BB'(Af ' 16.5.J )
/11==0
is nonsingular.
3. Tht!' n x np cOl/troilt/hilir,\" 1I1<llri_\
16.551
has rank 11 (full row rank). The matrix can be generated by calling =tr;:, in MATLAB.
+
4. The /1 x (/1 p) matrix [A - AI B] has full row rank at every eigenvalue. A. of A.
5. If. in addition. all eigenvalues of A have magnitudes less than I. then the unique solution of

6.6 Discrete-Time State Equations 171
~ Theorem 6.001
The following statements are equivalent:
1. The n-dimensional pair (A, C) is observable.
2. The n x n matrix
.-1
= m
Wdo[n - I] L(A')mC'CA (6.59)
m=O
is nonsingular or, equivalently. positive definite.
3. The nq x n observability matrix
(6.60)
has rank n (full column rank). The matrix can be generated by calling obsv in MATLAB.
4. The (n + q) x n matrix
has full column rank at every eigenvalue, A, of A.
5. If, in addition. all eigenvalues of A have magnitudes less than I. then the unique solution of
=
Wdo - A'WdoA C'C (6.61)
is positive definite. The solution is called the discrete obser:abilitv Gramian and can be expressed as
oc
m
Wdo = L(A,)mC'CA (6.62)
m=O
This can be proved directly or indirectly using the duality theorem. We mention that all
other properties-such as controllability and observability indices, Kalman decomposition,
and Jordan-form controllability and observability conditions~iscussed for the continuous
time case apply to the discrete-time case without any modification. The controllability index
and observability index, however, have simple interpretations in the discrete-time case. The
controllability index is the shortest input sequence that can transfer any state to any other state.
The observability index is the shortest input and output sequences needed to determine the
initial state uniquely.
6.6.1 Controllability to the Origin and Reachability
In the literature. there are three different controllability definitions:
1. Transfer any state to any other state as adopted in Definition 6.0 I.
2. Transfer any state to the zero state, called controllability to the origin.

172 CONTROLLABILITY AND OBSERVABILITY
3. Transfer the zero state to any stat~. called controllability from the origin or. more often.
reachabiliry.
In the continuous-time case. because e·~1 is nonsingular. the three definitions are equiva
lent. In the discrete-time case. if A is nonsingular. the three definitions are again equivalent.
But if A is singular. then (1 ) and (3) are equivalent. but not (2) and (3). The equivalence of (I)
and (3) can easily be seen from (6.58). We use examples to discuss the difference between (2)
and (3 J. Consider
(6.63)
Its controllability matrix has rank 0 and the.equation is not controllable as defined in (I) or not
reachable as defined in (3). The matrix A has the fom1 shown in (3.40) and has the propeny
Ak = 0 for k :::: 3. Thus we have
x[3] = A 3 x[0] = 0
for any initial state x[O]. Thus every state propagates to the zero state whether or not an input
sequence is applied. Thus the equation is controllable to the origin. A different example follows.
Consider
(6.64)
Its controllability matrix
has rank I and the equation is not reachable. However. for any XI [0] = a and X2[Oj = fJ.
the input 1I [0] = 2a + fJ transfers x[O] to x[ I] = O. Thus the equation is controllable to the
origin. Note that the A-matrices in (6.63) and (6.64) are both singular. The definition adopted
in Definition 6.D 1 encompasses the other two definitions and makes the discussion simple.
For a thorough discussion of the three definitions. see Reference [4].
6.7 Controllability After Sampling
Consider a continuous-time state equation
xU) = Ax(r) + Bu(tl (6.65)
If the input is piecewise constant or
+
u[k] := u(kT) = 1I(t) for k T :::: t < (k I) T
then the equation can be described. as developed in (4.17). by
x[k + I] = Axfkj + BU[k] (6.66)

,
-
170 CONTROLLABILITY AND OBSERVABILITY
(6.56)
is positive definite. The solution is called the discrete controllability Gramian and can be obtained by
using the MATLAB function dgram. The discrete Gramian can be expressed as
00
W dc = LAmBBI(A')m (6.57)
m~O
The solution of (6.53) at k = n was derived in (4.20) as
"-I
+
x[n) = A"x[O) LA"-I-mBu[m)
I
which can be written as !
u[n - I)
u[n - 2)
=
x[nj- A"x[O] [B AB ... A"-IB] (6.58)
u[O]
It follows from Theorem 3.1 that for any x[O] and x[n], an input sequence exists if and only
if the controllability matrix has full row rank. This shows the equivalence of (I) and (3). The
matrix Wdc[n - I) can be written as
B'
= B'A' ]
Wdc[n - 1) [B AB '" A"-IB) .
[
B'(A")"-I
The equivalence of (2) and (3) then follows Theorem 3.8. Note that W dc[m) is always positive
semidefinite. If it is nonsingular or, equivalently, positive definite, then (6.53) is controllable.
The proof of the equivalence of (3) and (4) is identical to the continuous-time case. Condition
(5) follows Condition (2) and Theorem 5.D6. We see that establishing Theorem 6.DI is
considerably simpler than establishing Theorem 6.1.
There is one important difference between the continuous- and discrete-time cases. If a
continuous-time state equation is controllable, the input can transfer any state to any other
state in any nonzero time interval, no matter how small. If a discrete-time state equation is
controllable, an input sequence of length n can transfer any state to any other state. If we
compute the controllability index j.I. as defined in (6.15), then the transfer can be achieved
using an input sequence of length j.I.. If an input sequence is shorter than j.I., it is not possible
to transfer any state to any other state.
Definition 6.DZ The discrete-time state equation (6.53) or the pair (A, C) is said to be
observable iffo r any unknown initial state x[O), there exists afinite integer kl > 0 such
=
that the knowledge of the input sequence u[k) and output sequence y[k] from k 0 to
kl suffices to determine uniquely the initial state x[O]. Othenvise, the equation is said
to be unobservable.

|     |     |     |     | 6.7 Controllability After Sampling  |     |     | 173  |
| --- | --- | --- | --- | ----------------------------------- | --- | --- | ---- |
with
(I T
|     |     |     | B =  | eA'dt) B =: MB  |     |     | (667)  |
| --- | --- | --- | ---- | --------------- | --- | --- | ------ |
The question is: If (6.65) is controllable, will its sampled equation in (6.66) be controllable') This
problem is important in designing so-called dead-beat sampled-data systems and in computer
control of continuous-time systems. The answer to the question depends on the sampling period
T and the location of the eigenvalues of A. Let A,  and;', be. respectively. the eigenvalues of
A.
A and  We use Re and 1m to denote the real part and imaginary part. Then we haw the
following theorem.
Theorem 6.9
Suppose (6.65) is controllable. A sufficient condition for its discretized equation in (6.66). with sampling
period  T.  to  be  controllable  is  that  IIm[A,  - Ajll  cF  27fIll/T for  =  I. 2 ..... whene,"r
111
1 =
Re[A,  - A O. For the single-input case. the condition is necessary as well.
J
First we remark on the conditions. If A has only real eigenvalues. then the discretized
equation with any sampling period T  >  0 is always controllable. Suppose A has complex
=
j t3. If the sampling period T does not equal any integer multiple of
conjugate eigenvalues ex
f3. then the discretized state equatiQn is controllable. If T =  f3 for some integer Ill. then
IT /  III IT /
the discretized equation lila\" lIot be controllable. The reason is as follows. Because  A  = eAT. if
A,  is an eigenvalue of A. then;', := eA,T is an eigenvalue of  A  (Problem 3.19). If T =  '13.
1Il7f
|     |     | =   |     | =   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
the two distinct eigenvalues i'l  ex  +  j f3 and A2  ex - j f3 of A become a repeated eigemalue
A.
_eaT or eaT of  This \\ill cause the discretized equation to be uncontrollable. as we \\ill
see in the proof. We show Theorem 6.9 by assuming A to be in Jordan form. This is perl11ined
because controllability is in\ariant under any equivalence transformation.
-7
Proof of Theorem 6.9  To simplify the discussion. we assume A to be of the form
|                   |     |         |      | AI     | 0  0   | 0  0  |         |
| ----------------- | --- | ------- | ---- | ------ | ------ | ----- | ------- |
|                   |     |         |      | 0  Al  | 0      | 0  0  |         |
|                   |     |         |      | 0  0   | Al  0  | 0  0  |         |
| A = diagl..\ll. A |     | 12. A21 | ) =  |        |        |       | (6.681  |
|                   |     |         |      | 0  0   | 0      | 0  0  |         |
Al
|     |     |     |     | 0  0  | 0  0  |     |     |
| --- | --- | --- | --- | ----- | ----- | --- | --- |
"2
|     |     |     |     | 0   | 0  0  | 0   |     |
| --- | --- | --- | --- | --- | ----- | --- | --- |
|     |     |     |     | ()  |       | A2  |     |
In other words. A has t\\O distinct eigenvalues AI  and A2. There are two Jordan blocks.
one with order 3 and one with order I. associated with Al
and only one Jordan block of
order 2 associated \\ ith i.2. Using (3.48). we have
-
| -    | -      | -              |               |     |     |     |     |
| ---- | ------ | -------------- | ------------- | --- | --- | --- | --- |
| A =  | diaglA | II. A12. A2tl  |               |     |     |     |     |
|      | .• T   | Tei., T        | T 2 e;' T /2  | 0   | 0   |     |     |
|      | ~      |                |               |     |     | ()  |     |
Tei.,T
|     | 0   | e~-i T  |         | 0   | 0   | ()  |     |
| --- | --- | ------- | ------- | --- | --- | --- | --- |
|     | 0   | 0       | ei.[ T  | 0   | 0   | ()  |     |
(6.69)
|     | ()  | ()  | 0   | ell.[ T  | 0      | 0      |     |
| --- | --- | --- | --- | -------- | ------ | ------ | --- |
|     | 0   | 0   | ()  | 0        | eAJ.T  | Tei:T  |     |
|     | 0   | 0   | ()  | 0        | 0      | eA.~T  |     |

175
|     |     |     |     |     |     |     | 6.7  | Controllability After Sampling  |     |     |
| --- | --- | --- | --- | --- | --- | --- | ---- | ------------------------------- | --- | --- |
3
|     |     |     |     |     |     |     |     | x   | 2   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
T
s+2
| ~ u[kl ./  | ~   |     |     |     |     | "   |     |     |     |     |
| ---------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Hold
|     |     | (s +  | +     | + 2j)(s +  |     |      |     |         |     |     |
| --- | --- | ----- | ----- | ---------- | --- | ---- | --- | ------- | --- | --- |
|     |     |       | I)(s  | I          | I - | 2j)  | -3  | - " -I  |     |     |
I  2  3
-I
|     |     |     |     |     |     |     |     | x   | -2   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ---- | --- |
|     |     |     |     |     |     |     |     |     | - 3  |     |
Figure 6.11  System with piecewise constant input.
I Using (4.41), we can readily obtain the state equation
[i]
|     |     |     |     |     | [~3  | ~7  | ~5]  |     |     |     |
| --- | --- | --- | --- | --- | ---- | --- | ---- | --- | --- | --- |
x
|     |     |     |     | =   |     |     | x +  | u   |     |     |
| --- | --- | --- | --- | --- | --- | --- | ---- | --- | --- | --- |
(6,73)
|     |     |     |     | y = [0  | I  2Jx  |     |     |     |     |     |
| --- | --- | --- | --- | ------- | ------- | --- | --- | --- | --- | --- |
to describe the system, It is a controllable-form realization and is clearly controllable, The
eigenvalues of A are -I,  -1 ± j2 and are plotted in Fig, 6, II. The three eigenvalues have
the same real part; their differences in imaginary parts are :2 and 4. Thus the discretized state
equation is controllable if and only if
|     |     |     |         | 2rrm  | =     |      |          | 2rrm  |     |     |
| --- | --- | --- | ------- | ----- | ----- | ---- | -------- | ----- | --- | --- |
|     |     |     | T f. -- |       | rr m  | and  | T f. -4- |       |     |     |
= O,Srrm
2
=
for m  I,  2,  "., The second condition includes the first condition. Thus we conclude that
f. O,Smrr for any positive
the discretized equation of (6.73) is controllable if and only if T
integer m,
|     | We use MATLAB to check the result for m =  |           |             |     |                |     | I or T = O.Srr, Typing  |     |     |     |
| --- | ------------------------------------------ | --------- | ----------- | --- | -------------- | --- | ----------------------- | --- | --- | --- |
|     | a~ [-3                                     | -7  -5;1  | 0  0;01     |     | O];b=[l;O;OI;  |     |                         |     |     |     |
|     | [ad,bdl                                    | ~c2d      | (a,b,pi!2)  |     |                |     |                         |     |     |     |
yields the discretized state equation as
|     |          |     | -0,1039  |     | 0.2079   |          |          |         |            |               |
| --- | -------- | --- | -------- | --- | -------- | -------- | -------- | ------- | ---------- | ------------- |
|     |          |     |          |     |          |          | 0.5197]  |         | [-0,1039]  |               |
|     | x[k+IJ=  |     |          |     |          |          |          | x[kJ +  |            |               |
|     |          |     | -0,1390  |     | -0.4158  | -0.5197  |          |         | 0,1039     | u[kJ  (6,74)  |
[
|     |     |     | 0, 1039  |     | 0,2079  |     | 0,3118  |     | 0,1376  |     |
| --- | --- | --- | -------- | --- | ------- | --- | ------- | --- | ------- | --- |
Its controllability matrix can be obtained by typing c trb (ad, bd) . which yields
|     |     |     |     |     | -0.1039  | 0.1039  |     |     |     |     |
| --- | --- | --- | --- | --- | -------- | ------- | --- | --- | --- | --- |
-0,0045]
=
|     |     |     | Cd  |     | 0.1039  | -0,1039  |     | 0,0045  |     |     |
| --- | --- | --- | --- | --- | ------- | -------- | --- | ------- | --- | --- |
[
|     |     |     |     |     | 0.1376  | 0,0539  |     | 0,0059  |     |     |
| --- | --- | --- | --- | --- | ------- | ------- | --- | ------- | --- | --- |
Its  first  two  rows  are clearly  linearly  dependent,  Thus  Cd  does  not  have  full  row  rank
and (6.74)  is  not controllable as  predicted by Theorem 6,9,  We  mention that if we  type

176 CONTROLLABILITY AND OBSERVABILITY
ra!1k (ctrb (ad, bd)) .the result is 3 and (6.74) is controllable. This is incorrect and is due
to roundoff errors. We see once again that the rank is very sensitive to roundoff errors.
What has been discussed is also applicable to the observability part. In other words. under
the conditions in Theorem 6.9, if a continuous-time state equation is observable. its discretized
equation is also observable.
6.8 LTV State Equations
Consider the n-dimensional p-input q-output state equation
x +
= A(t)x B(t)u
(6.75)
y = C(t)x
The state equation is said to be controllable at 10. if there exists a finite tl > 10 such that for any
x(to) = Xo and any XI. there exists an input that transfers Xo to XI at time II. Othef\\bc the Slate
equation is uncontrollable at 10. In the time-invariant case. if a state equation is controllable,
then it is controllable at every 10 and for every II > 10: thus there is no need to specify 10 and
II· In the time-varying case, the specification of 10 and II is crucial.
Theorem 6.11
The n-dimensional pair (A(t). B(tl) is controllable at time 10 if and only if there exists a rinite II > to
such that the n X n matrix
[6.76)
where «1>(1. I) is the state transition matrix ofx = A(I)x. is nonsingular.
Proof: We first show that if Wc(to, ttl is nonsingular. then (6.75) is contwllJble. The
(,
response of (6.75) at II was computed in (4.57) as
1
x(td = «I>(II,IO)XO + «I>(tl , rlB(I)u(I)dI (6.77)
(0
We claim that the input
(678)
will transfer Xo at time 10 to XI at time II' Indeed, substituting (6.78) into (6. r I yields
I
. W;I (to, Itl[«I> (tl , (0)Xo - xtl
= =
«1>(11. 10)Xo - Wc(to. II )W;I (to, II )[«1>(11, (0)XO - XI] XI I

174 CONTROLLABILITY AND OBSERVABILITY
This is not in Jordan fonn. Because we will use Theorem 6.8, which is also applicable to
the discrete-time case without any modification, to prove Theorem 6.9, we must transform
A A
in (6.69) into Jordan fonn. It turns out that the Jordan fonn of equals the one in (6.68)
if Ai is replaced bY).i := e AjT (Problem 3.17). In other words, there exists a nonsingular
=
triangular matrix P such that the transfonnation i Pi will transfonn (6.66) into
ilk + IJ = PAP-'x[kJ + PMBu[kJ (6.70)
with PAP-' in the Jordan fonn in (6.68) with Ai replaced by ).i. Now we are ready to
establish Theorem 6.9.
First we show that M in (6.67) is nonsingular. If A is of the fonn shown in (6.68),
then M is block diagonal and triangular. Its diagonal entry is of fonn
.. '-!a
T ,p
mu .- rj, Aj'd T _ { (eA;T - I)/Ai if Ai 0 (6.71)
o . I. - T if Ai = 0
Let Ai = (Xi + jf3i. The only way for mii = 0 is (Xi = 0 and f3iT = 2rrm. In this case,
,p
- jfJi is also an eigenvalue and the theorem requires that 2f3i T 2rrm. Thus we conclude
,p
mii 0 and M is nonsingular and triangular.
If A is of the fonn shown in (6.68), then it is controllable if and only if the third
and fourth rows of B are linearly independent and the last row of B is nonzero (Theorem
6.8). Under the condition in Theorem 6.9, the two eigenvalues)., = e A1T and).2 = eA,T
A
of are distinct. Thus (6.70) is controllable if and only if the third and fouI1h rows of
PMB are linearly independent and the last row of PMB is nonzero. Because P and M
are both triangular and nonsingular, PMB and B have the same properties on the linear
independence of their rows. This shows the sufficiency of the theorem. If the condition
in Theorem 6.9 is not met, then)., = ).2. In this case, (6.70) is controllable if the third,
fourth, and last rows of PMB are linearly independent. This is still possible if B has three
or more columns. Thus the condition is not necessary. In the single-input case, if)., = ).2,
then (6.70) has two or more Jordan blocks associated with the same eigenvalue and (6.70)
is, following Corollary 6.8, not controllable. This establishes the theorem. Q.E.D.
In the proof of Theorem 6.9, we have essentially established the theorem that follows.
>
Theorem 6. '0
If a continuous-time linear time-invariant state equation is nO! controllable, then its discretized state
equation. with any sampling period. is no! controllable.
This theorem is intuitively obvious. If a state equation is not controllable using any input,
it is certainly not controllable using only piecewise constant input.
EXAMPLE 6.12 Consider the system shown in Fig. 6.11. Its input is sampled every T seconds
~
j and then kept constant using a hold circuit. The transfer function of the system is given as
_ s+2 s+2
= + + + + + + + (6.72)
g(s) s3 3s2 7s 5 - (s I)(s I j2)(s I - j2)

|     |     |     |     |     |     |     | 6.8  LTV State Equations  | 177  |
| --- | --- | --- | --- | --- | --- | --- | ------------------------- | ---- |
Thus the equation is controllable at 10. We show the converse by contradiction. Suppose
(6.75) is controllable at 10 but W,·(Io, t) is singular or, positi\e semidefinite, for all II  > 10.
| Then there exists an n x  |     |     | J  nonzero constant vector v such that  |     |     |     |     |     |
| ------------------------- | --- | --- | --------------------------------------- | --- | --- | --- | --- | --- |
which implies
|     |     |     | B'(r)4>'(II. r)v "" 0  |     | or  | v'4>(tI,r)B(r);: 0  |     | (679)  |
| --- | --- | --- | ---------------------- | --- | --- | ------------------- | --- | ------ |
for all r  in [10.  II]' If (6.75) is controllable. there exists an input that transfps the initial
| state Xo =  |     | 4>(10. II)\' at 10 to XUI) =  |                     | O. Then (6.77) becomes  |     |                      |     |        |
| ----------- | --- | ----------------------------- | ------------------- | ----------------------- | --- | -------------------- | --- | ------ |
|             |     |                               |                     |                         | 1   | '1                   |     |        |
|             |     |                               | 0= 4>(11. loJ4>(IO. | liJv +                  |     | 4>(11, r)B(r)uir)dr  |     | (680)  |
'0
Its premultiplication by y' yields"

I
|     |     |     | O=v'v+v'  | 4>(II.r)B(r)u(r)dr=llvll'+O  |     |     |     |     |
| --- | --- | --- | --------- | ---------------------------- | --- | --- | --- | --- |
10
This contradicts the hypothesis Y  i=  O. Thus if (ACI), B(1)  is controllable at 10. W,(to. II)
must be nonsingular for some finite II  >  10. This establishes Theorem 6.11.  Q.E.D.
In order to apply Theorem 6.11, we need knowledge of the state transition matrix. which.
however, may not be 3\·ailable. Therefore it is desirable to develop a controllability condition
without involving 4>(1. r). This is possible if we have additional conditions on A(t) and B(I).
Recall  that we have assumed A(t) and B(t) to be continuous. Now we require them to be
(n - I) times continuously differentiable. Define MO(I) = B(1). We then define recursively a
| sequence of 11  | x   | p matrices :\1", (I) as  |     |     |     |     |     |     |
| --------------- | --- | ------------------------ | --- | --- | --- | --- | --- | --- |
£I
|     |     |     | M",_I(t):=  | -A(I)M",(t) +  |     |     | -M",CI)  | (6.81)  |
| --- | --- | --- | ----------- | -------------- | --- | --- | -------- | ------- |
£II
| for 111  = O.  | I ..... 11  |     | - I. Clearly. we have  |     |                 |     |     |     |
| -------------- | ----------- | --- | ---------------------- | --- | --------------- | --- | --- | --- |
|                |             |     | 4>(12. IlB(t) =        |     | 4>(12. t)Mo(tl  |     |     |     |
for any fixed I,. Using
a
|              |                 |     | -4>(1). I) =  |     | -4>(1). I)A(r)  |     |     |     |
| ------------ | --------------- | --- | ------------- | --- | --------------- | --- | --- | --- |
|              |                 |     | 01            | -   |                 | -   |     |     |
| (Problem 4.  | 7). we compute  |     |               |     |                 |     |     |     |
J
a
d
(J
|     |     | ;-[4>(12. t)B(I)j =  |     | -[4>(l2.I)]B(I) +  |     |     | 4>(1)  I)-B(I)  |     |
| --- | --- | -------------------- | --- | ------------------ | --- | --- | --------------- | --- |
|     |     |                      |     | al                 |     |     | "I              |     |
rJI
£I
|     |     |     | 4>(1,. tl[ -A(t)MoU) +  |     | dt MuUl] =  |     |                  |     |
| --- | --- | --- | ----------------------- | --- | ----------- | --- | ---------------- | --- |
|     |     | =   |                         |     |             |     | 4>(12. I)MI (t)  |     |

6.8 LTV State Equations 179
The detenninant of the matrix
1
- t2t
t2 - 1
is (2 + 1, which is nonzero for all t. Thus the state equation in (6.86) is controllable at every t.
EXAMPLE 6.14 Consider
(6.87)
and
. [10]
[et
x = 0 2 x + e2t ] u (6.88)
Equation (6.87) is a time-invariant equation and is controllable according to Corollary 6.8.
Equation (6.88) is a time-varying equation; the two entries of its B-matrix are nonzero for all
t and one might be tempted to conclude that (6.88) is controllable. Let us check this by using
Theorem 6.11. Its state transition matrix is
= [et~r
4>(t, r) e (?-r)]
2
and
t r r t
= -
4>(t, r)B(r) [eo
e2(
0
t-r)
] [
e
e
2r
] -
-
[
e
e
2t
]
We compute
L
t
]
[:~t
Wc(to, t) = [e
_ [e2t
(t - to)
- e3t (t - to)
Its detenninant is identically zero for all to and (. Thus (6.88) is not controllable at any to. From
this example, we see that, in applying a theorem, every condition should be checked carefully;
othelWise, we might obtain an erroneous conclusion.
We now discuss the observability pan. The linear time-varying state equation in (6.75)
is observable at to if there exists a finite tl such that for any state x(to) = XQ, the knowledge
of the input and output over the time interval [to, til suffices to determine uniquely the initial
state Xo. OthelWise, the state equation is said to be unobservable at to.
>-
Theorem 6.011
The pair (A(t), C(t)) is observable at time to if and only if there exists a finite tl > to such that the
n x n matrix

180  CONTROLLABILITY AND OBSERVABILITY
"
1
=
| Wo(to. til  | <I>'("r. to)C'(r)C(r)<I>(r. to)dr  |     |     | (6.89)  |
| ----------- | ---------------------------------- | --- | --- | ------- |
'0
=
where <I>(t. r) is the state transition matrix of X  A(t)x. is nonsingular.
~  Theorem 6.012
Let A(t) and C(t) be n - 1 times continuously differentiable. Then the n-dimensional pair (ACt). C(t»
is observable at ro if there exists a finite II  > 10 such that
No (ttl
N I (ttl
|     |       | =n  |     | (6.90)  |
| --- | ----- | --- | --- | ------- |
|     | rank  | ,   |     |         |
I
|     | Nn- | I (til  |     |     |
| --- | --- | ------- | --- | --- |
where
m = 0.1. ...• n - I
with
=
|     | No  | C(t)  |     |     |
| --- | --- | ----- | --- | --- |
We mention that the duality theorem in Theorem 6.5 for time-invariant systems is not
applicable to time-varying systems. It must be modified. See Problems 6.22 and 6.23.
6.1  Is the state equation
|      | [~  ~       | ~]   | [~]  |     |
| ---- | ----------- | ---- | ---- | --- |
| =    |             | x +  |      |     |
| x    |             |      | u    |     |
|      | -I  -3      | -3   | 0    |     |
| y =  | [I  2  IJx  |      |      |     |
controllable? Observable~
6.2  Is the state equation
controllable? Observable?
6.3  Is it true that the rank of[B  AB  .. .  An-IB] equals the rank of [AB  A2B  ...  AnB]?
If not, under what conditon will it be true?
6.4  Show that the state equation

178  CONTROLLABILITY AND OBSERVABILITY
Proceeding forward, we have
(6.82)
0, 1,2, .... The following theorem is sufficient but not necessary for (6.75) to be
for m =
controllable.
..  Theorem 6.12
Let A(t) and B(t) be n - 1 times continuously differentiable. Then the n-dimensional pair (ACt), B(t))
| is controllable at to if there exists a finite t\ >  |     |     | to such that  |     |
| ---------------------------------------------------- | --- | --- | ------------- | --- |
(6.83)
!a
Proof:  We show that if (6.83) holds, then Wc Cto , t) is nonsingular for all t :': tl· Suppose
not, that is, W c(to, t) is singular or positive semidefinite for some t2  :':  tl' Then there
exists an n x 1 nonzero constant vector v such that
1t2
=
|     | v'Wc(to, tz)v  | V'~(t2' r)B(r)B'(r)~'(t2' r)vdr  |     |     |
| --- | -------------- | -------------------------------- | --- | --- |
.  to
|     |     | 1t2                  | 2   |     |
| --- | --- | -------------------- | --- | --- |
|     |     | =                    |     | =   |
|     |     | IIB/(r)~'Ct2' r)vll  | dr  | 0   |
to
which implies
=  (6.84)
|     | B'(r)~/Ctz, r)v  |     | 0  or  v/~Ct2' r)B(r) == 0  |     |
| --- | ---------------- | --- | --------------------------- | --- |
for all r in [to,  t21. Its differentiations with respect to r yield, as derived in (6.82).
v/~Ctz, r)Mm(r) == 0
for m = O. 1.2, ... , n - 1, and all r in [to. t21, in particular, at fl· They can be arranged as
(6.85)
Because ~(t2' tl) is nonsingular, v/~Ct2. tl) is nonzero. Thus (6.85) contradicts (6.83).
Therefore, under the condition in (6.83), WcCto, t2), for any tz  :': tl, is nonsingular and
| (A(t), B(t»   | is, following Theorem 6.11, controllable at to·  |     |     | Q.E.D.  |
| ------------- | ------------------------------------------------ | --- | --- | ------- |
| EXAMPLE 6.13  | Consider                                         |     |     |         |
(6.86)
We have Mo =
[0  1  1]' and compute
:t
[~t]
+  MO
MI =  -A(t)Mo  =
|     |     |     | ~MI  ~;  |     |
| --- | --- | --- | -------- | --- |
|     |     | =   | +  = [   | ]   |
M2  -A(t)MI
|     |     |     | dt  z  | 1   |
| --- | --- | --- | ------ | --- |
t  -

Problems  J 8 J
is controllable if and only if the pair (An. Azl) is controllable.
6.5  Find a state equation to describe the network shown in  Fig. 6.1, and then check its
controllability and observability.
6.6  Find the controllability index and observability index of the state equations in Problems
6.1 and 6.2.
6.7  What is the controllability index of the state equation
|     | x   | + Iu  |     |
| --- | --- | ----- | --- |
= Ax
where I is the unit matrix0
6.8
Reduce the state equation
|     |     | y = [1  | IJx  |
| --- | --- | ------- | ---- |
to a controllable one. Is the reduced equation observable?
6.9  Reduce the state equation in Problem 6.5 to a controllable and observable equation.
6.10  Reduce the state equation
| AI     | 0  0   | 0   | 0   |
| ------ | ------ | --- | --- |
| 0      | AI  0  | 0   |     |
| x=  0  | 0  0   | 0   | 0   |
|        | AI     | x+  | II  |
| 0      | 0  0   |     | 0   |
AZ  1
| 0   | 0  0  0  | A2  |     |
| --- | -------- | --- | --- |
o
| Y =  [0  | I  I  I  IJx  |     |     |
| -------- | ------------- | --- | --- |
to a controllable and observable equation.
6.11  Consider the n-dimensional state equation
x =  Ax+Bu
y=Cx+Du
The rank of its controllability matrix is assumed to be n I < n. Let Q I be an n x n I matrix
whose columns are any n I linearly independent columns of the controllability matrix.
Let PI  be an nl x n matrix such that PIQI =  In" where In,  is the unit matrix of order
n I. Show that the following n I-dimensional state equation
XI  =  PIAQlxl + PIBu
y  =  CQIXI +Du
is controllable and has the same transfer matrix as the original state equation.
6.12  In Problem 6.11. the reduction procedure reduces to solving for PI in PIQI  =  I. How
do you solve PI?

Problems 183
Figure 6.12
6.19 Consider the continuous-time state equation in Problem 4.2 and its discretized equa
=
tions in Problem 4.3 with sampling period T I and rr. Discuss controllability and
observability of the discretized equations.
6.20 Check controllability and observability of
y = [0 l]x
6.21 Check controllability and observability of
6.22 Show that (A(t), B(t» is controllable atto if and only if (-A' (t), B' (t» is observable at
to·
6.23 For time-invariant systems, show that (A, B) is controllable if and only if (-A, B) is
controllable. Is this true for time-varying systems?

Chapter
Minimal Realizations
and Coprime Fractions
7.1 Introduction
This chapter studies further the realization problem discussed in Section 4.4. Recall that a
transfer matrix G(s) is said to be realizable if there exists a state-space equation
x
= Ax + Bu
y = ex + Du
that has G(s) as its transfer matrix. This is an important problem for the following reasons. First.
many design methods and computational algorithms are developed for state equations. In order
to apply these methods and algorithms. transfer matrices must be realized into state equations.
As an example. computing the response of a transfer function in MATLAB is achieved by first
transforming the transfer function into a state equation. Second. once a transfer function is
realized into a state equation. the transfer function can be implemented using op-amp circuits.
as discussed in Section 2.3.1.
If a transfer function is realizable. then it has infinitely many realizations. not necessarily
of the same dimension. as shown in Examples 4.6 and 4.7. An important question is then raised:
What is the smallest possible dimension~ Realizations with the smallest possible dimension
are called minimal-dimensional or minimal realizations. If we use a minimal realization to
implement a transfer function. then the number of integrators used in an op-amp circuit will
be minimum. Thus minimal realizations are of practical importance.
In this chapter, we show how to obtain minimal rc:alizations. We will show that a realization
=
of g(s) N (s)/ O(s) is minimal if and only if it is controllable and observable. or if and only
184

182  CONTROLLABILITY AND OBSERVABILITY
6.13  Develop a similar statement as in Problem 6.11 for an unobservable state equation.
6.14  Is the Jordan-form state equation controllable and observable?
|     |     | 2   | 0   | 0  0  | 0  0  |     | 2   |     | 0   |
| --- | --- | --- | --- | ----- | ----- | --- | --- | --- | --- |
|     |     | 0   | 0   | 0  0  | 0  0  |     | 2   | 1   |     |
2
|     |     |     |       | 0   | 0  0  |     | 1   | 1   | 1   |
| --- | --- | --- | ----- | --- | ----- | --- | --- | --- | --- |
|     |     | 0   | 0  2  | 0   |       |     |     |     |     |
x+
|     | x=   |     |       |        |       |     | 3   | 2   | 1  u  |
| --- | ---- | --- | ----- | ------ | ----- | --- | --- | --- | ----- |
|     |      | 0   | 0  0  | 2  0   | 0  0  |     |     |     |       |
|     |      | 0   | 0  0  | 0  1   | 0     |     | -1  | 0   | 1     |
|     |      | 0   | 0  0  | 0  0   | 1  0  |     | 1   | 0   | 1     |
|     |      | 0   | 0  0  | 0  0   | 0     |     | 1   | 0   | 0     |
|     |      |     | 2  1  | 3  -1  | 1     |     |     |     |       |
|     | y=U  |     | 1     | 2  '0  | 0     | nX  |     |     |       |
I
|     |     |     | 1  1  |     | 1  1  |     |     |     |     |
| --- | --- | --- | ----- | --- | ----- | --- | --- | --- | --- |
Is it possible to find a set of bjj  and a set of Cjj such that the state equation
6.15
|     |     |     |       | 0     | 0   |     |            |     |     |
| --- | --- | --- | ----- | ----- | --- | --- | ---------- | --- | --- |
|     |     |     | 1  1  | 0     |     |     | b ll  biZ  |     |     |
|     |     |     | 0  1  | 0  0  | 0   |     | b21  b22   |     |     |
X+
x=
|     |     |     | 0  0  | 1  1  | 0   |     | b31  b32  | U   |     |
| --- | --- | --- | ----- | ----- | --- | --- | --------- | --- | --- |
|     |     |     | 0  0  | 0     | 0   |     | b41  b42  |     |     |
|     |     |     | 0  0  | 0  0  | I   |     | bS2       |     |     |
b51
|     |     |      | C12       | CI3  | CI4  |       |     |     |     |
| --- | --- | ---- | --------- | ---- | ---- | ----- | --- | --- | --- |
|     |     | = [  | CIl       |      |      | CIS]  |     |     |     |
|     |     | Y    |           |      | C24  | C25   |     |     |     |
|     |     |      | C2l  C22  | C23  |      |       |     |     |     |
C35
|     |     |     | C3l  C32  | C33  | C34  |     |     |     |     |
| --- | --- | --- | --------- | ---- | ---- | --- | --- | --- | --- |
is controllable? Observable?
6.16  Consider the state equation
|     |     |     | 0      | 0    | 0   | 0   |     |       |     |
| --- | --- | --- | ------ | ---- | --- | --- | --- | ----- | --- |
|     |     |     | AI     |      |     |     |     | bl    |     |
|     |     |     | 0  al  | f31  | 0   | 0   |     | b ll  |     |
X+
|     |     | x=  |          |     |     |     |     |       | u   |
| --- | --- | --- | -------- | --- | --- | --- | --- | ----- | --- |
|     |     |     | 0  -f31  |     | 0   | 0   |     | b l2  |     |
al
|     |     |     | 0  0  | 0   |       |      |     | bZI  |     |
| --- | --- | --- | ----- | --- | ----- | ---- | --- | ---- | --- |
|     |     |     |       |     | a2    | f32  |     |      |     |
|     |     |     | 0  0  | 0   | -fh.  |      |     |      |     |
|     |     |     |       |     |       | a2   |     | bn   |     |
=
|     |     | Y  [CI  | CII  | CI2  | C21  | C22]  |     |     |     |
| --- | --- | ------- | ---- | ---- | ---- | ----- | --- | --- | --- |
It is the modal form discussed in (4.28). It has one real eigenvalue and two pairs of
complex conjugate eigenvalues. It is assumed that they are distinct. Show that the state
|     |     |     |     |     | 1=  |     | 1=  |     | 1=  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
equation is controllable if and only if bl  0; bjl  0 or bi2  0 for i  =  1.2. It is
=
| observable if and only if CI  |     |     | 1= 0; Cj I  |     | 1= 0 or Cj2  | 1= 0 for i  |     | I. 2.  |     |
| ----------------------------- | --- | --- | ----------- | --- | ------------ | ----------- | --- | ------ | --- |
6.17  Find two- and three-dimensional state equations to describe the network shown in Fig.
6.12. Discuss their controllability and observability.
6.18  Check controllability and observability of the state equation obtained in Problem 2.19.
Can you give a physical interpretation directly from the network?

7.2 Implications of Coprimeness 185
if its dimension equals the degree of <~(s). The degree o(~(s) is defined as the degree of D(s) if
the two polynomials D(s) and N(s) are coprime or have no common factors. Thus the concept
of coprimeness is essential here. In fact. coprimeness in the fraction N (s)/ D(s) plays the same
role of controllability and observability in state-space equations.
This chapter studies only linear time-invariant systems. We study first SISO systems and
then MI",10 systems.
7.2 Implications of Coprimeness
Consider a system with proper transfer function gIS). We decompose it as
+
g(s) = g(::x;) gsp(s)
where g,p(s) is strictly proper and g(x) is a constant. The constant glee) yields the D-matrix
in every realization and will not play any role in what will be discussed. Therefore we consider
in this section only strictly proper rational functions. Consider
/3IS' /3.
+ +
•. N(s) -c- /32s~ /3,s
g is) = -- = -,------,,-----=-'--'---'--- (7.1 l
D(s) s· +als' +als2 +a)s +a4
To simplify the discussion, we have assumed that the denominator D(s) has degree 4 and is
monic (has I as its leading coefficient). In Section 4.4, we introduced for (7.1) the realization
in (4.41) without any discussion of its state variables. Now we will redevelop (4.41) by first
defining a set of state variables and then discussing the implications of the coprimeness of
D(s) and N(s).
Consider
.v(s) = N(~)D-I (s)ll(s) (7.2)
Let us introduce a new variable dl) defined by ~(s) = D-I (s)/i(s). Then we have
D(s)v(s) = II(S) (7.3)
\'(5) = N(s)v(s) (7.4 )
Define state variables as
U::'j(tl]
'~I(S)]
[
v(t) xes) .1'2 (5)
.- [ or = (7.5)
u(
r) .i)(s)
v(Il .i·. (s)
Then we have
0.6)
They are independent of (7.1) and follow directly from the definition in (7.5 J. In order to
develop an equation for .(1, we substitute (7.5) into (7.3) or

7.2 Implications of Coprimeness 187
Its detenninant is I for any aj. Thus the controllability matrix C has full row rank and the
state equation is always controllable. This is the reason that (7.9) is called a controllable
canonical form.
Next we check its observability. It turns out that it depends on whether or not N (s) and
D(s) are coprime. Two polynomials are said to be coprime if they have no common factor of
degree at least I. More specifically, a polynomial R(s) is called a common factor or a common
divisor of D(s) and N(s) if they can be expressed as D(s) = D(s) R(s) and N(s) = N (s)R(s),
where D(s) and N(s) are polynomials. A polynomial R(s) is called a greatest common divisor
(gcd) of D(s) and N(s) if (I) it is a common divisor of D(s) and N(s) and (2) it can be divided
without remainder by every other common divisor of D(s) and N(s). Note that if R(s) is a
gcd, so is aRCs) for any nonzero constant a. Thus greatest common divisors are not unique2
In tenns of the gcd, the polynomials D(s) and N (s) are coprime if their gcd R (s) is a nonzero
constant, a polynomial of degree 0; they are not coprime if their gcd has degree I or higher.
~ Theorem 7.1
The controllable canonical fonn in (7.9) is observable if and only if D(s) and N (s) in (7.1) are coprime.
Prool We first show that if (7.9) is observable, then D(s) and N(s) are coprime. We
show this by contradiction. If D(s) and N(s) are not coprime, then there exists a Al such
that
N(Ail = filA~ + thAi + fi3A] + fi4 = 0 (7.11 )
°
D(A]) = A~ +a]A; +a2AT +a3AI +a4 = (7.12)
Let us define v : = p. i AT A] I)'; it is a 4 x I nonzero vector. Then (7.11) can be written
=
as N(AIl = cv O. where c is defined in (7.9). Using (7.12) and the shifting property of
the companion fonn, we can readily verify
-~I
[
Av = (7.13)
o
o
= = =
Thus we have A1v A(Av) = AIAv ATv and AJv AjV. We compute, using cv = 0,
1
[A~:vl
o,· = [cCA:2 ] V = [ ccA:2vv = Aicv = 0
3 3
cA cA v A3cv
I
which implies that the observability matrix does not have full column rank. This contradicts
the hypothesis that (7.9) is observable. Thus if (7.9) is observable, then D(s) and N(s)
are coprime.
Next we show the converse; that is, if D(s) and N (s) are coprime, then (7.9) is
observable. We show this by contradiction. Suppose (7.9) is not observable, then Theorem
6.01 implies that there exists an eigenvalue A] of A and a nonzero vector v such that
2. If we rc:quire R(s) to be monic. then the gcd is unique.

188 MINIMAL REALIZATIONS AND COPRIME FRACTIONS
A - All]
v=O
[ c
or
Av = Al v and ev = 0
Thus v is an eigenvector of A associated with eigenvalue AI. From (7.13), we see that
Ai
v = [Ai AI I], is an eigenvector. Substituting this v into cv = 0 yields
Thus AI is a root of N(s). The eigenvalue of A is a root of its characteristic polynomial,
which, because of the companion fOITI} of A, equals D(s). Thus we also have D(}·I) = O.
and D(s) and N (s) have the same factor s - AI. This contradicts the hypothesis that D(s)
and N(s) are coprime. Thus if D(s) and N(s) are coprime, then (7.9) is observable. This
establishes the theorem. Q.E.D.
If (7.9) is a realization of g(s), then we have, by definition.
g(s) = c(sl - A)-Ib
Taking its transpose yields
= =
f(s) = g(s) [e(sl - A)-Ibj' b'(sl - A')-Ic'
Thus the state equation
-al
x• =AI x+eI u= -Ctz
-a) (7.14)
[
-a4
=
y = b'x [I 0 0 O]x
is a different realization of (7.1). This state equation is always observable and is called an
observable canonical form. Dual to Theorem 7.1. Equation (7.14) is controllable if and only
if D(s) and N(s) are coprime.
x
We mention that the equivalence transformation = Px with
il
[! : ;
~
(7.15)
p
will transform (7.9) into
o
1
o
o o

186 MINIMAL REALIZATIONS AND COPRIME FRACTIONS
to yield
which becomes, in the time domain,
XI(t)=[-al -az -aJ -a4]x(t)+I·u(t) (7.7)
Substituting (7.5) into (7.4) yields
Y<s) = (f3lsJ + {3zs2 + f3Js + f34)V(S)
= f3lxl (s) + f32X2(S) + f3JxJ(s) + f34X4(S)
I
= [f31 f32 f3J' f34]X(S)
which becomes, in the time domain,
yet) = [f34 f3J f32 f3tJx(t) (7.8)
Equations (7.6), (7.7), and (7.8) can be combined as
[-a,
-a2 -aJ
0 0 TJ'+m'
~
x=Ax+bu=
I 0
(7.9)
0 I
y = ex = [f31 f32 f33 f34]X
This is a realization of (7.1) and was developed in (4.41) by direct verification.
Before proceeding, we mention that if N(s) in (7.1) is I, then y(t) = vet) and the output
yet) and its derivatives can be chosen as state variables. However, if N(s) is a polynomial of
degree I or higher and if we choose the output and its derivatives as state variables, then its
realization will be of the form
X =Ax+bu
= u
y ex + du + diu + d 2 + ...
This equation requires differentiations of u and is not used. Therefore, in general, we cannot
select the output y and its derivatives as state variables. I We must define state variables by
using vet). Thus v(t) is called a pseudo state.
Now we check the controllability and observability of (7.9). Its controllability matrix can
readily be computed as
J
I -al -a~ + l 2
;a a - aJ
C = 0 I a l - az (7.10)
o
0 -al
[
o o
0 I
I. See also Example 2.16, in particular, (2.47).

7.2 Implications of Coprimeness 189
This is also called a controllable canonical form. Similarly, (7.15) will transform (7.14) into
0 0 0
x=
1 0 0
010
[
001
y = ex = [0 0 0 l]x
This is a different obserYable canonical form.
7.2.1 Minimal Realizations
We first define a degree for proper rational functions. We call N (s) / D(s) a polynomial fraction
or, simply. afraction. Bec:luse
• N(s) N(s)Q(s)
g(s) = D(s) = D(s)Q(s)
for any polynomial Q(s). fractions are not unique. Let R(s) be a greatest common divisor
= =
(gcd) of N(s) and D(s). That is. if we write N(s) N(s)R(s) and D(s) D(s)R(s),
then the polynomials N(s) and D(s) are coprime. Clearly every rational function g(s) can be
=
reduced to g (s) N (s) / D (s). Such an expression is called a coprime fraction. We call D(s)
a characteristic polynomial of g(s). The degree of the characteristic polynomial is defined as
the degree of g(s). Note that characteristic polynomials are not unique; they may differ by a
nonzero constant. If we require the polynomial to be monic, then it is unique.
Consider the rational function
Its numerator and denominator contain the common factor s - 1. Thus its coprime fraction is
=
g(s) (s + 1)/4(s2 +s + 1) and its characteristic polynomial is 4s2 +4s +4. Thus the rational
function has degree 2. Given a proper rational function, if its numerator and denominator are
coprime-as is often the case-then its denominator is a characteristic polynomial and the
degree of the denominator is the degree of the rational function.
~ Theorem 7.2
A state equation (A. b. e. dl is a minimal realization of a proper rational function g(s) if and only if
(A. b) is controllable and (A. e) is observable or if and only if
=
dim A deg g(s)
Proof: If (A. b) is not controllable or if (A, e) is not observable, then the state equation
can be reduced to a lesser dimensional state equation that has the same transfer function
(Theorems 6.6 and 6.06). Thus (A, b. e, d) is not a minimal realization. This shows the
necessi ty of the theorem.

7.2 Implications of Coprimeness 191
The realization in (7.9) is controllable and observable if and only if g(s) :
N(s)/ D(s) is a coprime fraction (Theorem 7.1). In this case. we have dim A : deg
D(s) : deg g(s). Because all minimal realizations are equivalent, as will be established
immediately. we conclude that every realization is minimal if and only if dim A : deg
g(s). This establishes the theorem. Q.E.D.
To complete the proof of Theorem 7.2. we need the following theorem.
~ Theorem 7.3
All minimal realizations of g(s) are equivalent.
Proof' Let (A. b, c, d) and (A. ii, c, d) be minimal realizations of g(s). Then we have
d : d and, following (7.22).
Oe
OC: (7.23)
Multiplying OAC out explicitly and then using (7.20). we can show
OAC: OAC (7.24)
Note that the controllability and observability matrices are all nonsingular square matrices.
Let us define
Then (7.23) implies
p: 0-10: eel and p-I = 0-10: Ce-I (7.25)
a-I
From (7.23), we have e : OC : Pc. The first columns on both side of the equality
yield ii : Pb. Again from (7.23), we have 0: OCe-1 : OP- I . The first rows on both
c : I
sides of the equality yield cP- . Equation (7.24) implies
A = ij-IOACe-1 : PAP-I
Thus (A, b, c d) and (A, ii, c. d) meet the conditions in (4.26) and, consequently, are
equivalent. This establishes the theorem. Q.E.D.
Theorem 7.2 has many important implications. Given a state equation, if we compute its
transfer function and degree. then the minimality of the state equation can readily be determined
without checking its controllability and observability. Thus the theorem provides an alternative
way of checking controllability and observability. Conversely, given a rational function. if we
compute first its common factors and reduce it to a coprime fraction. then the state equations
obtained by using its coefficients as shown in (7.9) and (7.14) will automatically be controllable
and observable.
=
Consider a proper rational function g(s) N(s)/ D(s). If the fraction is coprime. then
every root of D(s) is a pole of g(s) and vice versa. This is not true if N(s) and D(s) are not
coprime. Let (A. b.c.d) be a minimal realization of g(s) : N(s)/ D(s). Then we have

192 MINIMAL REALIZATIONS AND COPRIME FRACTIONS
N(s) I
- = c(sl - Arl b + d = c [Adj(sI - A)] b + d
D(s) det(sl - A)
If N(s) and D(s) are coprime. then deg D(s) = degg(s) = dimA. Thus we have
D(s) = k det(sI - A)
for some nonzero constant k. Note that k = I if D(s) is monic. This shows that if a state
equation is controllable and observable. then every eigenvalue of A is a pole of g(s) and every
pole of g(s) is an eigen\'alue of A. Thus we conclude that if (A, b. c. d) is controllable and
observable. then we have
Asymptotic stability BIBO stability
¢==}
I
More generally, control/able and observable state eqllations and coprime /ractiolU comain
essentially fhe same in/omUllion and eiTher descripTion can be IIsed 10 carry Ollt analysis and
desigll.
7.3 Computing Coprime Fractions
The importance of coprime fractions and degrees was demonstrated in the preceding section.
In this section. we discuss how to compute them. Consider a proper rational function
• N(s)
g(s) = D(s)
where N(s) and D(s) are polynomials. If we use the MATLAB function roots to compute
their roots and then to cancel their common factors, we will obtain a coprime fraction. The
MATLAB function mi,,:-ea~ can also be used to obtain coprime fractions. In this section.
we introduce a different method by solving a set of linear algebraic equations. The method
does not offer any advantages over the aforementioned methods for scalar rational functions.
However. it can readily be extended to the matrix case. More importantly, the method will be
used to carry out design in Chapter 9.
Consider N(s)/D(s). To simplify the discussion. we assume deg N(s) ::: deg DIS) =
n = 4. Let us write
N(s) N(s)
D(s) D(s)
which implies
D(s)(-N(s» + N(s)D(s) = 0
It is clear that D(s) and N(s) are not coprime if and only if there exist polynomials .Y(s)
and D(s) with deg N(s) ::: deg D(s) < n = 4 to meet (7.26). The condition deg Disl < n
is crucial: otherwise. (7.26) has infinitely many solutions N(s) = N(s)R(s) and Dis) =
D(s)R(s) for any polynomial R(s). Thus the coprimeness problem can be reduced to solving
the polynomial equation in (7.26).
Instead of solving 17.26) directly, we will change it into solving a set of linear algebraic
equations. We write

190 MINIMAL REALIZATIONS AND COPRIME FRACTIONS
To show the sufficiency, consider the n-dimensional controllable and observable state
equation
x +
= Ax bu
(7.16)
y = cx +du
Clearly its n x n controllability matrix
(7.17)
and its n x n observability matrix
c
cA
0= (7.18)
cAn 1
-
both have rank n. We show that (7.16) is a minimal realization by contradiction. Suppose
n
the n-dimensional state equation, with < n,
X= Ax +
iiu
(7.19)
y = cx+du
is a realization of g(5). Then Theorem 4.1 implies d = d and
=
for m 0, I, 2, .. , (7.20)
Let us consider the product
c
cA
1
cAn
-
cb cAb cA2b CA,,-lb
cAb cA2b cA3b cAnb
- cA2b cA3b cA 4 b cAn+1b (7.21 )
cA
Using (7.20), we can replace every cAmb by mii. Thus we have
oe = OnC" (7.22)
where On is defined as in (6.21) for the n-dimensional state equation in (7.19) and Cn is
defined similarly. Because (7.16) is controllable and observable, we have p(O) = nand
= = n
pee) n. Thus (3.62) implies p(Oe) n. Now On and Cn are, respectively, n x
and n x n; thus (3.61) implies that the matrix OnCn has rank at most n. This contradicts
p(OnCn) = p(Oe) = n. Thus CA, b, c, d) is minimal. This establishes the first part of
the theorem.

193
73 Computing Coprime Fractions
| N(s) =   | No  +  Nls  +  N"S" + NJs.1  | +  N.js-l  |         |
| -------- | ---------------------------- | ---------- | ------- |
| - =      | - - -                        | " - 3      |         |
|          | +  +  s                      | - +        |         |
| D iS)    | D o  D IS  D 2               | D Js       |         |
|          | No +  +                      | + i{lSJ    |         |
| F/(s) =  | Nls  N1S"                    |            | (7.17)  |
This is a homogeneous lin~ar algebraic equation. The first block column of S consists of two
columns formed from the coefficients of Dis) and N (s) arranged in ascending powers of s.
The second block column is the first block column shifted down one position. Repeating the
process until S is a square matrix of order 2n =  8. The square matrix S is called the SY"'esTer
resultant. If the Sylvester resultant is singular. nonzero solutions exist in (7.28) (Theorem 3.3).
This means that polynomials N (s) and D(s) of degree 3 or less exist to meet (7.26). Thus
0(5) and N(s) are not coprime. If the Sylvester resultant is nonsingular. no nonzero solutions
exist in (7.28) or. equivalently. no polynomials IV (s) and D(s) of degree 3 or less exist to meet
(7.26). Thus D(s) and Nts) are coprime. [n conclusion. 0(5) and N(s) are coprime ifand
ollly if the Svlvesrer resultanT is nOllsingulm:
If the Sylvester result:lnt is singular. then N(s)! 0(5) can be reduced to
|     | N(s)  N(s)  |     |     |
| --- | ----------- | --- | --- |
|     | D(s)  D(s)  |     |     |
where IV(S) and D(s) are coprime. We discuss how to obtain a coprime fraction directly from
(7.28). Let us search Jine:lrly independent columns of S in order from left to right. We call
columns formed from OJ D-columns and formed from N ,v-columns. Then every D-column
j
i=  O. the first
is linearly independent of its left-hand-side (LHS) columns. Indeed. because D.j
D-column is [inearly independent. The second D-column is also linearly independent of its
LHS columns because the LHS entries of D.j are all zero. Proceeding forward, we conclude
that all D-columns are line:lrly independent of their LHS columns. On the other hand. an N
column can be dependent or independent of its LHS columns. Because of the repetitive pattern

7.3 Computing Coprime Fractions 195
which yields
anszbo[42 -32 0 11'
DI - D21'.
This monic null vector equals [-No Do - NI N" Thus we have
N(s) = -4 + 3s + o· s" D(s) = 1 + 2s + s"
and
3s - 4
2s~ + 7s3 + 15s2 + 16s + 10 - S2 + 1s + 1
Because the null vector is computed from the first linearly dependent N-column, the computed
N(s) and D(s) have the smallest possible degrees to meet (7.26) and, therefore. are coprime.
This completes the reduction of N (s) I D (s) to a coprime fraction.
The preceding procedure can be summerized as a theorem.
~,. Theroem 7.4
Consider g(s) = N (s) I D(s). We use the coefficients of D(s) and N (s) to form the Syl vester resultant
S in (7.28) and search its linearly independent columns in order from left to right. Then we have
=
deg g(s) number of linearly independent N-columns =: tL
and the coefficients of a coprime fraction g(s) = N ( s) I D(s) or
D
[-No Do - NI I ··· - N{L D{L]'
equals the monic null vector of the submatrix that consists of the primary dependent N-column and all
its LHS linearly independent columns of S.
We mention that if D- and N-columns in S are arranged in descending powers of s. then
it is not true that all D-columns are linearly independent of their LHS columns and that the
degree of g(s) equals the number of linearly independent N-columns. See Problem 7.6. Thus
it is essential to arrange the D- and N-columns in ascending powers of s in S.
7.3.1 QR Decomposition
As discussed in the preceding section. a coprime fraction can be obtained by searching linearly
independent c·olumns of the Sylvester resultant in order from left to right. It turns out the widely
available QR decomposition can be used to achieve this searching.
Q
Consider an n x m matrix M. Then there exists an n x n orthogonal matrix such that
QM=R
Q
where R is an upper triangular matrix of the same dimensions as M. Because operates on the
rows of M. the linear independence of the columns of M is preserved in the columns of R. In
other words, if a column of R is linearly dependent on its left-hand-side (LHS) columns, so is

,
196 MINIMAL REALIZATIONS AND COPRIME FRACTIONS
i
the corresponding column of M. Now because R is in upper triangular form. its mth column is
linearly independent of its LHS columns if and only if its mth entry at the diagonal position is
nonzero. Thus using R. the linearly independent columns of M. in order from left to right, can
be obtained by inspection. Because Q is orthogonal, we have Q-I = Q' = : Q and QM = R
becomes M = QR. This is called QR decomposition. In MATLAB, Q and R can be obtained
by typing (q, r l =qr (~) .
Let us apply QR decomposition to the resultant in Example 7.1. We type
do[10 16 15 ~ , 2J ;n<-20 3 :. 5 ~ .. ,
~.
,
sold 0 0;n 0 0 0;0 d 0 C;O n G 0; .. .
~
0 0 d 0;0 0 n 0;0 0 0 c·n 0 0 nl ';
,~
[q,rJoqr (s)
Because Q is not needed, we show only R:
-25.1 3.7 -20.6 10.1 -11.6 11.0 -4.1 5.3
0 -20.7 -10.3 4.3 -7.2 2.1 -3.6 6.7
0 0 -10.2 -15.6 -20.3 0.8 -16.8 9.6
0 0 0 8.9 -3.5 -17.9 -11.2 7.3
r=
0 0 0 0 -5.0 0 -12.0 - 15.0
0 0 0 0 0 0 -2.0 0
0 0 0 0 0 0 -4.6 0
0 0 0 0 0 0 0 0
We see that the matrix is upper triangular. Because the sixth column has 0 as its sixth entry
(diagonal position), it is linearly dependent on its LHS columns. So is the last column. To
determine whether a column is linearly dependent, we need to know only whether the diagonal
entry is zero or not. Thus the matrix can be si mpli fied as
d x x x x x x x
0 n x x x x x x
0 0 d x x x x x
0 0 0 n x x x x
r=
0 0 0 0 d 0 x x
0 0 0 0 0 0 x 0
0 0 0 0 0 0 d 0
0 0 0 0 0 0 0 0
where d. n, and x denote nonzero entries and d also denotes D-column and n denotes N
column. We see that every D-column is linearly independent of its LHS columns and there are
only two linearly independent N-columns. Thus by employing QR decomposition. we obtain
immediately J.L and the primary dependent N-column. In scalar transfer functions. we can use
either rank or qr to find J.L. In the matrix case. using rank is very inconvenient; we will use
QR decomposition.

194 MINIMAL REALIZATIONS AND COPRIME FRACTIONS
of 5, if an N -column becomes linearly dependent on its LHS columns, then all subsequent
N-columns are linearly dependent of their LHS columns. Let jJ. denote the number of linearly
+
independent N-columns in 5. Then the (jJ. I)th N-column is the first N-column to become
linearly dependent on its LHS columns and will be called the primary dependent N-column.
Let us use 5 I to denote the submatrix of 5 that consists of the primary dependent N -column
and all its LHS columns. That is, 51 consists of /1 + I D-columns (all of them are linearly
+ +
independent) and /1 I N-columns (the last one is dependent). Thus 51 has 2(/1 I) columns
+
but rank 2/1 I. In other words, SI has nullity I and, consequently, has one independent null
vector. Note that if ii is a null vector, so is aii for any nonzero a. Although any null vector can
IV
b_e used, we will use exclusi vely the null vector with I as its last entry to develop (s) and
D(s). For convenience. we call such a null vector a monic null vector. If we use the MATLAB
function null to generate a null vector, then the null vector must be divided by its last entry
to yield a monic null vector. This is illustdted in the next example.
EXAMPLE 7.1 Consider
N(s)
(7.29)
D(s)
We have n = 4 and its Sylvester resultant S is 8 x 8. The fraction is coprime if and only if S
is nonsingular or has rank 8. We use MATLAB to check the rank of S. Because it is simpler to
key in the transpose of S, we type
d= ( 10 16 15 7 2 J ; n = ( -2 0 3 1 6 0 J ;
s=(d 0 0 O;n 0 0 0;0 d 0 0;0 n 0 0; ...
a a
ODd 0; 0 0 nO; 0 0 0 d; 0 nJ';
m=rank (s)
The answer is 6; thus D(s) and N(s) are not coprime. Because all four D-columns of 5 are
linearly independent, we conclude that S has only two linearly independent N-columns and
/1 = 2. The third N-column is the primary dependent N-column and all its LHS columns are
linearly independent. Let SI denote the first six columns of S, an 8 x 6 matrix. The submatrix
51 has three D-column (all linearly independent) and two linearly independent N -columns.
thus it has rank 5 and nullity I. Because all entries of the last row of SI are zero, they can be
skipped in forming 51. We type
51=(d 0 C;n 0 0;0 d 0;0 n 0;0 0 d;O 0 nJ';
z=nul1(51)
which yie Ids
,,
1
ans z= (0.6860 0.3430 -0.5145 0.3430 0.0000 0.1715 l'
1
I 'j This null vector does not have I as its last entry. We divide it by the last entry or the sixth entry
of 2 by typing
<.i zb=z/z(6)

7.4 Balanced Realization 197
7.4 Balanced Realization3
Every transfer function has infinitely many minimal realizations. Among these realizations, it
is of interest to see which realizations are more suitable for practical implementation. If we
use the controllable or observable canonical form, then the A-matrix and b- or c-vector have
many zero entries, and its implementation will use a small number of components. However,
either canonical form is very sensitive to parameter variations; therefore both forms should
be avoided if sensitivity is an important issue. If all eigenvalues of A are distinct, we can
transform A, using an equivalence transformation, into a diagonal form (if all eigenvalues are
real) or into the modal form discussed in Section 4.3.1 (if some eigenvalues are complex). The
diagonal or modal form has many zero entries in A and will use a small number of components
in its implementation. More importantly, the diagonal and modal forms are least sensitive
to parameter variations among all realizations; thus they are good candidates for practical
implementation.
We discuss next a different minimal realization, called a balanced realization. However.
the discussion is applicable only to stable A. Consider
x = Ax + bll
(7.30)
y = ex
It is assumed that A is stable or all its eigenvalues have negative real parts. Then the
controllability Gramian We and the observability Gramian Wo are, respectively, the unique
solutions of
(731 )
and
(7.32)
They are positive definite if (7.30) is controllable and observable.
Different minimal realizations of the same transfer function have different controllability
and observability Gramians. For example, the state equation, taken from Reference [23],
. [-I [I]
x= -4/0' ] x+
1I
40' -2 20'
y=[-12/O'Jx (7.33 )
for any nonzero a, has transfer function g ( 5) = (35 + 18)/ (52 + 35 + 18). and is controllable
and observable. Its controllability and observability Gramians can be computed as
0°.5
. [0.5
and Wo= (734)
We = [ °
We see that different a yields different minimal realization and different controllability and
observability Gramians. Even though the controllability and observability Gramians will
change, their product remains the same as diag (0.25, I) for all o'.
3. This section may be skipped without loss of continuity.

7.4 Balanced Real ization 199
which implies that We Wo and RWoR' have the same set of eigenvalues. Thus we conclude
that all eigenvalues of WeW o are real and positive. Q.E.D.
Let us define
(7.42)
where are positive square roots of the eigenvalues of WeW o. For convenience, we arrange
(Jj
them in descending order in magnitude or
These eigenvalues are called the Hankel singular values. The product WeW o of any minimal
realization is similar to 1:2 .
~ Theorem 7.6
For any n-dimensional minimal state equation (A, b. c), there exists an equivalence transformation
x = Px such that the controllability Gramian We and observability Gramian \Vo o f its equivalent state
equation have the property
(7.43)
This is called a balanced realization.
=
Proof' We first compute We R'R as in (7.40). We then apply Theorem 3.6 to the real
and symmetric matrix RWoR' to yield
where U is orthogonal or U'U = I. Let
p-l = R'U1:- 1 /2 or P = 1: 1 /2U'(R)-1
Then (7.38) and We = R'R imply
We = 1:1/2U'(R')-IWcR-IU1:1/2 = 1:
and (7.39) and RWoR' = U1:2U' imply
\Vo = 1:- I /2U'RWoR'U1:- 1 /2 = 1:
This establishes the theorem. Q.E.D.
By selecting a different P, it is possible to find an equivalent state equation with \Ve = I
and Wo = 1:2 Such a state equation is called the input-normal realization. Similarly. we
can have a state equation with We = 1:2 and \Vo = I, which is called the output-normal
realization. The balanced realization in Theorem 7.5 can be used in system reduction. More
specifically. suppose

200  MINllvlAL REALIZATIONS AND COPRI,\lE FRACTIONS
(7,4~)
is a balanced minimal realization of a stable .~(s) with
|     | w,  | =  Wo = diag(1: | I. 1: |     |
| --- | --- | --------------- | ----- | --- |
2)
where the A-. b-. and c-matrices are partitioned according to the order of 1:,. If the Hankel
singular values of 1:1  and 1:, are disjoin£. then the reduced state equation
|     |     | = Alixi  | +     |     |
| --- | --- | -------- | ----- | --- |
|     |     | XI       | bill  |     |
(7.45)
is balanced and A II  is stable. If the singular values of 1:2 are much smaller than those of 1: I.
then the transfer function of (7.45) will be close to ,~(s). See Reference [23].
The MATLAB function ;:,al real will transform (A. b. C) into a balanced state equation.
The reduced equation in (7.45) can be obtained by using ba 1 red. The results in this section are
based on the controllability and observability Gramians. Because the Gramians in the MIMO
case are square as in the SISO case: all results in this section apply to the MIMO case without
any modification.
7.5  Realizations from Markov Parameters·
Consider the strictly proper rational function
|           |                           | + "              | +             | +                                         |
| --------- | ------------------------- | ---------------- | ------------- | ----------------------------------------- |
|           | = --,-FR- !-S,- I_I--I; - | .,\.. .1.1_-2- - | +             | "   j3                                    |
| g (   s)  |                           | :... P::2        | ;- _. . ._ .  | , "  , - , " - _ - 1 c 5  . -- - = 1/ -_  |
(7.46)
|     | Sl,  +als | ll - 1  +a2Ss  | + ...  | +crn-IS +a"  |
| --- | --------- | -------------- | ------ | ------------ |
2
We expand it into an infinite power series as
(7.4 7)
=  =
If ,~!.n is strictly proper as assumed in (7.46). then hiD)  O. The coefficients h(III).
III
I.  2 ..... are called Marko\' parameters. Let g(t) be the inverse Laplace transform of ,~(s) or.
equivalently. the impulse response of the system. Then we have
I
d",-I
|     | II (111)  | =  --I f?(t)  |      |     |
| --- | --------- | ------------- | ---- | --- |
|     |           | dtllf         | 1=0  |     |
-'
for  III  =  I.  2.  3 ..... This method of computing Markov parameters is impractical because
it requires repetitive differentiations. and differentiations are susceptible to noise' Equating
(7,46) and 0.47) yidds
~. Thi~ section may be skipped without loss of continuity.
i
5. In tht! discrete-time cast', if we apply In impulse :,equenct' to a system. then the output ,e4uem:e directly yield~
I
i\brkov parame!ers. Thus Markov paramerers can easily be gener;:ued in discrete-lime syslems.

198 MINIMAL REALIZATIONS AND COPRIME FRACTIONS
~ Theorem 7.5
Let (A, b, c) and (A, b, c) be minimal and equivalent and let We Wo and WcWo be the products of their
controllability and observability Gramians. Then We Wo and We 'Vo are similar and their eigenvalues
are all real and positive.
:3 Proof' Let x = Px, where P is a nonsingular constant matrix. Then we have
(7.35)
The controllability Gramian We and observability Gramian Wo of (A, b, c) are, respec
tively, the unique solutions of
(7.36)
and
A'Wo + WoA = -C'c (7.37)
Substituting A = PAP-I and b = Pb into (7.36) yields
PAP-I We + We(P,)-IA'P' = -Pbb'P'
which implies
+ =
AP-IWe(pyl p-IWe(P')-IA' -bb'
Comparing this with (7.31) yields
We = p-IWe(p')-1 or We = PWeP' (7.38)
Similarly, we can show
Wo = P'WoP or Wo = (p')-IWop-1 (7.39)
Thus we have
WeWo = P-I,Ve(p,)-lp'Wop = p-IWeWoP
This shows that all We Wo are similar and. consequently, have the same set of eigenvalues.
Next we show that all eigenvalues of We Wo are real and positive. Note that both
We and Wo are symmetric, but their product may not be. Therefore Theorem 3.6 is not
directly applicable to We WOo Now we apply Theorem 3.6 to We:
(7.40)
where D is a diagonal matrix with the eigenvalues of We on the diagonal. Because We
is symmetric and positive definite, all its eigenvalues are real and positive. Thus we can
express D as DI/2DI/2, where DI/2 is diagonal with positive square roots of the diagonal
entries of D as its diagonal entries. Note that Q is orthogonal or Q-I = Q'. The matrix
R = DI/2Q is not orthogonal but is nonsingular.
Consider RWoR'; it is clearly symmetric and positive definite. Thus its eigenvalues
are all real and positive. Using (7.40) and (3.66), we have

1.5 Realizations irom Markov Parameters  201
{JIS,,-I + {J~s"-~ + ... + {J"
1
| =  (5" + 0'15,,-1 + O'lS"-~ + ... -+- |     |     | O',,)litll  | -+- it(2)s-1 + ...  |     | )   |
| ------------------------------------- | --- | --- | ----------- | ------------------- | --- | --- |
)5-
From this equation, we can obtain the Marko\ parameters recursively as
h(I)={J1
| h(~) =   | - O'lh(l) + fJl            |     |     |     |     |     |
| -------- | -------------------------- | --- | --- | --- | --- | --- |
| 11(3) =  | - 0'Ih(2) - 0'1h(1) + {3,  |     |     |     |     |     |
h(II) =  - O'lit(1I - I) - O'lhlll - 2) - .. - O',,_litl I) + fJ"  (7.-+8 )
| lI(m) =  | - 0'111(111  - I) - | O'lh(1II - | 2) - ... - | 0',,_111(111  | - II -'- | I)  |
| -------- | ------------------- | ---------- | ---------- | ------------- | -------- | --- |
-O'"h(m -II)
for 111  = II  +  I.  n + 2 .....
| Next we use the Markov parameters to form the  |     |     | x fJ  | matrix  |     |     |
| ---------------------------------------------- | --- | --- | ----- | ------- | --- | --- |
(f
|     | h I I )  11(2)  |     | hlY)  | 1I1{3)  |     |     |
| --- | --------------- | --- | ----- | ------- | --- | --- |
h(3)  11(4)
|              | h(2)          |     |           | itl{J+I)    |             |         |
| ------------ | ------------- | --- | --------- | ----------- | ----------- | ------- |
|              | h13)  17(4)   |     | it( 5)    | IIlfJ + 2)  |             |         |
| T(O'. {J) =  |               |     |           |             |             | (7.50)  |
|              | h(a)  lila +  | I)  | 11(0'+2)  |             | +  {J - I)  |         |
/1(0'
It is called a Hallkellllarrix. It is important to mention that even if It (0)  oF  O.  h (0) does not
appear in the Hankel matrix.
Theorem 7.7
g
A strictly proper rational funClion  (5) has degree II if and only if
pT(n. II) = pT(1I + k. 11  -r IJ = II  for ewry k.l =  I. 2 ....  (7.51 )
where p denotes the rank.
Proof:  We first show that if deg itiJ) = II. thenpT(II. 11)  =  pT(1I +  I. nJ  =  p T( x. II).
If deg ,~(s) =  II.  then (7.-+9)  holds. and II  is  the smallest integer having the property.
Becallse of(7.49). the (II +  l)th row of Till + 1. III C;in be written as a linear combination
of the first n ro"s. Thus we have pTII1. II) =  pT11I +  I. n). Again. because of 17.49). the
+  2)th row of Till + 2. 11) depends on its pre\ious  rows and. consequently. on the
(n  11
first 11  rows. Proceeding forward. we can establish pT(II.II) = pT(x. 11). Now we claim
pT(oo. n) = n. If not. there would be an integer II  < n having the property (7,49). This
contradicts the hypothesis that deg c~(.n = II. Thus we have pT(n.lI) =  pT(X.II) =
11.
Applying (7.49) to the columns of T yields (7.51 ).
then g(.n
Now  we  show  that  if (7.51)  holds.  =  h( I ).\-1  +  h(2)s-~ +  ... can
be  expressed  as  a strictly  proper  rational  function  of degree  n.  From  the  condition

|     |     |     |     |     |     |     | 7.5 Real izations from Markov Parameters  |     |     |     |     | 203  |
| --- | --- | --- | --- | --- | --- | --- | ----------------------------------------- | --- | --- | --- | --- | ---- |
=
|     |     |     |     |     | T(n, n)  |     | OAC  |     |     |     |     | (7.55)  |
| --- | --- | --- | --- | --- | -------- | --- | ---- | --- | --- | --- | --- | ------- |
Using (7.53) and (7.55), we can obtain many different realizations. We discuss here only a
companion-form and a balanced-form realization.
Companion form  There are many ways to decompose T(n, n) into OC. The simplest is
= I or C = I. If we select 0  = I, then (7.53) and (7.55) imply C  = T(n, n)
to select 0
= T(n, n)T-l(n, n).The state equation corresponding to  =  =
| and A  |     |     |     |     |     |     |     |     |     | 0  I, C  | T(n, n), and  |     |
| ------ | --- | --- | --- | --- | --- | --- | --- | --- | --- | -------- | ------------- | --- |
A = T(n, nlT-l (n, n) is
|     |         |      | 0         | 1   | 0    |     | 0     | 0    |     | h(l)  |     |         |
| --- | ------- | ---- | --------- | --- | ---- | --- | ----- | ---- | --- | ----- | --- | ------- |
|     |         |      | 0         | 0   |      |     | 0     | 0    |     | h(2)  |     |         |
|     | X=      |      |           |     |      |     |       |      | X+  |       | u   |         |
|     |         |      | 0         | 0   | 0    |     | 0     |      |     | hen - | 1)  |         |
|     |         | -an  |           |     | -a   |     |       | -al  |     | hen)  |     |         |
|     |         |      | -Q'n-l    |     | n-2  |     | -Q'2  |      |     |       |     |         |
|     | y = [1  |      | 0  0 ...  | 0   | O]x  |     |       |      |     |       |     | (7.56)  |
Indeed, the first row of 0 = I and the first column of C = T(n, n) yield the c and b in (7.56).
| Instead of showing A = T(n, n)T- |     |     |     |     | l  (n, n), we show  |     |             |     |     |     |     |         |
| -------------------------------- | --- | --- | --- | --- | ------------------- | --- | ----------- | --- | --- | --- | --- | ------- |
|                                  |     |     |     |     | AT(n, n)            |     | =  T(n, n)  |     |     |     |     | (7.57)  |
Using the shifting property of the companion-form matrix in (7.56), we can readily verify
|     |     | h(l)  |     | h(2)   |     |     | h(2)  |     |     | h(3)  |     |         |
| --- | --- | ----- | --- | ------ | --- | --- | ----- | --- | --- | ----- | --- | ------- |
|     |     | h(2)  |     | h (3)  |     |     | h(3)  |     |     | h(4)  |     |         |
|     | A   |       |     |        |     | A   |       |     | -   |       |     | (7.58)  |
=
|     |     |       |     | h(n +  | 1)  |     | hen +  |     | h(n + 2)  |     |     |     |
| --- | --- | ----- | --- | ------ | --- | --- | ------ | --- | --------- | --- | --- | --- |
|     |     | hen)  |     |        |     |     |        | 1)  |           |     |     |     |
We see that the Markov parameters of a column are shifted up one position if the column
is pre multiplied by A.  Using this property, we can readily establish (7.57). Thus  0  =  I,
C = T(n, n), and A = T(Il. n)T-l(n, n) generate the realization in (7.56). It is a companion
form realization. Now we use (7.52) to show that (7.56) is indeed a realization. Because of the
form of c, cAm b equals simply the top entry of Am b or
2
|     |     |     | cb = h(l),  |     | cAb = h(2),  |     |     | b = h(3),  |     |      |     |     |
| --- | --- | --- | ----------- | --- | ------------ | --- | --- | ---------- | --- | ---- | --- | --- |
|     |     |     |             |     |              |     |     | cA         |     | ...  |     |     |
Thus (7.56) is a realization of g(s). The state equation is always observable because 0  I
=
has full rank. It is controllable if C = Ten. n) has rank n.
| EXAMPLE 7.2  |     | Consider  |     |      |        |     |     |     |     |     |     |     |
| ------------ | --- | --------- | --- | ---- | ------ | --- | --- | --- | --- | --- | --- | --- |
|              |     |           |     | 4s2  | - 2s - | 6   |     |     |     |     |     |     |
|              |     | g(s) =    |     |      |        | ,   |     |     |     |     |     |     |
+ 2s3 + 2s· + 3s + 1
2S4
1
= 0 . 5- + 2s-2  - 3s-3  - 2s-4 + 2s-5 + 3.5s-6 + .. .  (7.59)
We form T(4, 4) and compute its rank. The rank is 3; thus g(s) in (7.59) has degree 3 and its

204  MINIMAL REALIZATIONS AND COPRIME FRACTIONS
numerator and denominator have a common factor of degree I. There is no need to cancel first
the common factor in the expansion in (7.59). From the preceding derivation. we have
|     |     |     |     |     | -3]  |     | [0  | I 0]  |     |
| --- | --- | --- | --- | --- | ---- | --- | --- | ----- | --- |
[
2
A
|     | [~3 ~~  | ~7]  | ~   |     |     | -I =  |     |     |     |
| --- | ------- | ---- | --- | --- | --- | ----- | --- | --- | --- |
(7.60)
|     | =   |        |     | -3  | -2  |     | 0     | 0  I   |     |
| --- | --- | ------ | --- | --- | --- | --- | ----- | ------ | --- |
|     | -2  | ~ 3.5  | -3  |     | 2   |     | -0.5  | -I  0  |     |
and
|     |     | b  =  | [0  2  | - 3]'  | c =  | [I  | 0  0]  |     |     |
| --- | --- | ----- | ------ | ------ | ---- | --- | ------ | --- | --- |
The triplet (A. b. c) is a minimal realization of g(s) in (7.59).
We  mention that the  matrix A in  (7.60) can be obtained without computing t(n, n)
T-1(n, n). Using (7.49) we can show
|     |     |     |     | 2   | -3  |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
~
|     |     |     |     | -3  | -2  |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
T(3, 4)a := [
|     |     |     | -3  | -2  | 2   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Thus a is a null vector of T(3, 4). The MATLAB function
| t=[O  | 2  -3  -2;2  | -3  -2  | 2;-3  -2  | 2   | 3.5];a=null(t)  |     |     |     |     |
| ----- | ------------ | ------- | --------- | --- | --------------- | --- | --- | --- | --- |
yields a=[ -0.3333  - 0.6667  0.0000  - 0.6667]'. We normalize the last entry of a to I by
typing a / a ( 4 ) , which yields [0.5  I  0  I]'. The first three entries, with sign reversed, are the
last row of A.
Balanced form  Next we discuss a different decomposition of T(n. n) - Oc. which will
yield a realization with the property
cc
=  0'0
First we use singular-value decomposition to express T(n. n)as
(7.61)
where K and L are orthogonal matrices and A 1.2 is diagonal with the singular values of T(n, n)
on the diagonal. Let us select
|     |     | 0= KAI!2  |     |      | C = A1 |     | 2L'  |     | (7.62)  |
| --- | --- | --------- | --- | ---- | ------ | --- | ---- | --- | ------- |
|     |     |           |     | and  |        |     | /    |     |         |
Then we have
|     |     |      | =         |      |     | C-I =  |          |     |         |
| --- | --- | ---- | --------- | ---- | --- | ------ | -------- | --- | ------- |
|     |     | 0-1  | A -1/2K'  | and  |     |        | LA -1/2  |     | (7.63)  |
For this selection of C and 0, the triplet
|     |     |     | A =  |     |     | I   |     |     | (7.64)  |
| --- | --- | --- | ---- | --- | --- | --- | --- | --- | ------- |
O-It(n, n)C
(7.65)
b = first column of C
(7.66)
c = first row of 0

1
202  MINIMAL REALIZATIONS AND COPRIME FRACTIONS
|       |        | =   |            |     | =                       |     |     |     |     | =                               |     |
| ----- | ------ | --- | ---------- | --- | ----------------------- | --- | --- | --- | --- | ------------------------------- | --- |
|       | +      |     |            |     | n, we can compute (ai,  |     |     |     |     | 1. 2, .. .• n) to meet (7.49).  |     |
| pT(n  | 1,00)  |     | pT(n, 00)  |     |                         |     |     |     | j   |                                 |     |
=
| We then use (7.48) to compute (fli'  |     |     |     |     |     |     | I, 2, ... , n). Hence we have  |     |     |     |     |
| ------------------------------------ | --- | --- | --- | --- | --- | --- | ------------------------------ | --- | --- | --- | --- |
j
|     |     |       | =   |          | +    |          | +        |              |         |      |     |
| --- | --- | ----- | --- | -------- | ---- | -------- | -------- | ------------ | ------- | ---- | --- |
|     |     | g(s)  |     | h(l)s-l  |      | h(2)s-2  |          | h(3)s-3 ...  |         |      |     |
|     |     |       |     |          | 1 +  |          | + ... +  |              |         | +    |     |
|     |     |       |     | fllSn-   |      |          |          |              | fln-IS  |      |     |
|     |     |       |     |          |      | fl2Sn-2  |          |              |         | fln  |     |
Because the n is the smallest integer having the property in (7.51). we have deg g(s) = n.
| This completes the proof of the theorem.  |     |     |     |     |     |     | Q.E.D.  |     |     |     |     |
| ----------------------------------------- | --- | --- | --- | --- | --- | --- | ------- | --- | --- | --- | --- |
With this preliminary, we are ready to discuss the realization problem. Consider a strictly
proper transfer function g(s) expressed as
+I
|     |     |     |                 |     |     |          |     | +        |     | + .,.  |     |
| --- | --- | --- | --------------- | --- | --- | -------- | --- | -------- | --- | ------ | --- |
|     |     |     | g(s) = h(l)s-l  |     |     | h(2)s-2  |     | h(3)s-3  |     |        |     |
If the triplet (A, b, c) is a realization of g(s), then
|     |     |     | g(s) = c(sl - |     |     | A)-lb = e[s(1 - |     |     | s-IA)]-lb  |     |     |
| --- | --- | --- | ------------- | --- | --- | --------------- | --- | --- | ---------- | --- | --- |
which becomes, using (3.57),
|     |     |     |     |     | l +  | eAbs-2 +  |     | eA2bs-3 + ...  |     |     |     |
| --- | --- | --- | --- | --- | ---- | --------- | --- | -------------- | --- | --- | --- |
g(s) = ebs-
Thus we conclude that (A, b, c) is a realization of g(s) if and only if
=
|     |     |     |       | =   |         |     | form  |     | I,  2,  | ...  | (7.52)  |
| --- | --- | --- | ----- | --- | ------- | --- | ----- | --- | ------- | ---- | ------- |
|     |     |     | hem)  |     | eAm-lb  |     |       |     |         |      |         |
Substituting (7.52) into the Hankel matrix T(n, n) yields
|     |     |     |     |     |     |       | eA2b  |     |     | cAn-lb  |     |
| --- | --- | --- | --- | --- | --- | ----- | ----- | --- | --- | ------- | --- |
|     |     |     |     | eb  |     | cAb   |       |     |     |         |     |
|     |     |     |     |     |     | eAlb  | cA3b  |     |     | eAnb    |     |
eAb
|     |     |     |     |       |     |       | eA4b  |     |     | eAn+1b  |     |
| --- | --- | --- | --- | ----- | --- | ----- | ----- | --- | --- | ------- | --- |
|     |     |     |     | eA2b  |     | cAlb  |       |     |     |         |     |
T(n, n) =
|     |     |     |     | eAn-lb  |     | eAnb  | cAn+1b  |     |     | cA2(n-l)b  |     |
| --- | --- | --- | --- | ------- | --- | ----- | ------- | --- | --- | ---------- | --- |
which implies, as shown in (7.21),
|     |     |     |     |     |     | T(n, n) =  |     | OC  |     |     | (7.53)  |
| --- | --- | --- | --- | --- | --- | ---------- | --- | --- | --- | --- | ------- |
where 0 and C are, respectively, the n xn observability and controllability matrices of (A, b. c).
Define
+  I)
|     |     |     | h(2)  |     | h(3)  |     | h(4)  |     |     | hen  |     |
| --- | --- | --- | ----- | --- | ----- | --- | ----- | --- | --- | ---- | --- |
+
|     |     |     |     |     | h(4)  |     | h(5)  |     |     | hen  2)  |     |
| --- | --- | --- | --- | --- | ----- | --- | ----- | --- | --- | -------- | --- |
h(3)
+
hen  3)
|     | T(n, n) =  |     | h(4)  |     | h(5)     |     | h(6)  |      |     |        | (7.54)  |
| --- | ---------- | --- | ----- | --- | -------- | --- | ----- | ---- | --- | ------ | ------- |
|     |            |     |       | +   |          | +   |       | +    |     | h(2n)  |         |
|     |            |     | hen   |     | I)  hen  |     | 2)    | hen  | 3)  |        |         |
|     |            |     | +     |     |          |     |       |      |     |        | +       |
It is the submatrix of T(n  I, n) by deleting the first row or the sub matrix of T(n, n  I) by
deleting the first column. Then as with (7.53), we can readily show

|     |     |     |     |     | 7.6  | Degree of Transfer Matrices  | 205  |
| --- | --- | --- | --- | --- | ---- | ---------------------------- | ---- |
is a minimal realization of g(s). For this realization. we have
|     |     |     |     | cc =           | =   |     |     |
| --- | --- | --- | --- | -------------- | --- | --- | --- |
|     |     |     |     | A I!!L'LA li2  |     | A   |     |
and
Thus it is called a balanced reali:ation. This balanced realization is different from the balanced
realization discussed in Section 7.4. It is not clear what the relationships between them are.
EXAMPLE 7.3  Consider the transfer function in Example 7.2. NO\\' we will find a balanced
realization from Hankel matrices. We type
| 2     | -3;2  | -3  -2;-3  |     | -2  2];tc=[2  | -3  -2;-3  | -22;-2  | 2      |
| ----- | ----- | ---------- | --- | ------------- | ---------- | ------- | ------ |
| t=~C  |       |            |     |               |            |         | 3.S~;  |
[k  S  1 ] -= s'Ie ( :.) ;
I  I
sl=sq~t (5);
O=k*sl ;C=s: *1';
a=i~v(O) *tt*i~v(C).
| b::;[C(l,l);C(2,:);C(J,1)],co:::[O(l,l\  |     |     |     |     | 0(1,2)  | 0(1,21J  |     |
| ---------------------------------------- | --- | --- | --- | --- | ------- | -------- | --- |
This yields the following balanced realization:
|     |     | 0.4003  |     | -1.0024  |           |           |     |
| --- | --- | ------- | --- | -------- | --------- | --------- | --- |
|     |     |         |     |          | -0.4805]  | [1.2883]  |     |
x =
|     |     | 1.0024  |     | -0.3121  | 0.3209  x +  | -0.7303  | 11  |
| --- | --- | ------- | --- | -------- | ------------ | -------- | --- |
[
|     |      | 0.4805   |         | 0.3209            | -0.0882  | 1.0614  |     |
| --- | ---- | -------- | ------- | ----------------- | -------- | ------- | --- |
|     | v =  | [1.2883  | 0.7303  | - 1.0614]x +0· u  |          |         |     |
To check the correctness of this result, we type  [:-:, ci 1 ~ s s 2 t f  ( a , b, C , 0 ) , which yields
|     |     |     |     | ,          | 2s - 3               |     |     |
| --- | --- | --- | --- | ---------- | -------------------- | --- | --- |
|     |     |     |     | g (.I)  =  | --;J+;- ---+-, :--=  |     |     |
|     |     |     |     |            | .I  s  0.5           |     |     |
This equals g(s) in (7.59) after canceling the common factor 2(.1  +
I).
7.6  Degree of Transfer Matrices
This section will extend the concept of degree for scalar rational functions to rational matrices.
Given a proper rational matrix G(s), it  is  assumed that every entry of G(s) is  a coprime
fraction: that is. its numerator and denominator have no common factors. This will be a standing
assumption throughout the remainder of this text.
Definition 7.1 The characteristic polynomial of a P!oper rational matrix G(s) is defined
as the least common denominator of all minors ofG(s). The degree of the characteristic
polynomial is defined as the McMillan degree or,  simply,  the degree of Gis) and is
denoted by 8G(s),

7.7 Minimal Realizations-Matrix Case 207
To conclude this section, we mention two important properties. Let (A, B. C. D) be a
controllable and observable realization of (;(s). Then we have the following;
• Monic least common denominator of all minors of G(s) == characteristic polynomial of A .
• Monic least common denominator of all entries of G(s) == minimal polynomial of A.
For their proofs. see Reference [4, pp. 302-304].
7.7 Minimal Realizations-Matrix Case
We introduced in Section 7.2.1 minimal realizations for scalar transfer functions. Now we
discuss the matrix case.
>-
Theorem 7.M2
A state equation (A. B. C. D) is a minimal realization of a proper rational matrix (;(s) if and only if
(A, B) is controllable and (A. C) is observable or if and only if
dim A == deg G(s)
Proof' The proof of the first part is similar to the proof of Theorem 7.2. If (A. B) is not
controllable or if (A. C) is not observable, then the state equation is zero-state equivalent
to a lesser-dimensional state equation and is not minimal. If (A. B. C, D) is of dimension
(A. B. C. D).
n and is controllable and observable, and if the n-dimensional state equation
with n < n. is a realization of (;(s). then Theorem 4.1 implies D == D and
form == 0,1,2. ' "
Thus. as in (7.22). we have
OC == O"Cn
Note that O. C. 0". and C" are. respectively. nq x n. n x 1lp. nq x n, and n x IIp matrices.
Using the Sylvester inequality
+
p(O) p(C) - n ::: p(OC) ::: min(p(O). p(C»
which is proved in Reference [6. p. 31];and p(O) == p(C) == 11. we have p(OC) == n.
Similarly, we have p(O"C,,) == n < n. This contradicts p(OC) == p(O"C,,). Thus every
controllable and observable state equation is a minimal realization.
To show that (A. B. C, D) is minimal if and only if dim A == deg (;(.~) is much more
complex and will be established in the remainder of this chapter. Q.E.D.
,»- Theorem 7. M3
All minimal realizations of (;(s) are equivalent.

208 MINI,VlAL REALIZATIONS AND COPRIME FRACTIONS
Proof: The proof follows closely the proof of Theorem 7.3. Let (A, B, C, 0) and (,.\.. B,
C. D)
be any two n-dimensional minimal realizations of a q x p proper rational matrix
(;(s). As in (7.23) and (7.24), we have
OC= OC 0·67)
and
OAC= OAC (768)
In the scalar case, 0, C. 0, and C are all n x n nonsingular matrices and their inverses are
0
well defined. Here 0 and are nq x n matrices of rank n; C and Care n x IIp matrices
of rank 11. They are nOt square and their inverses are not defined. Let us define the 11 x I1q
matrix
(769)
Because 0' is 11 X I1q and 0 is I1q x n, the matrix 0' 0 is 11 X 11 and is, following Theorem
3.8, nonsingular. Clearly, we have
Thus O· is called the pseudoil1verse or left inverse of O. Note that 00+ is nq X Ilq and
does not equal a unit matrix. Similarly, we define
(7.70)
It is an np X n matrix and has the property
CC+ = CC(CC)-I = I
Thus C· is called the pseudoinverse or right inverse of C. In the scalar case. the
equivalence transformation is defined in 0.25) as P =
0-10
= CC-
I
. Now we replace
inverses by pseudoinverses to yield
P:= 0+0 = (0'0)-10'0 (7.71 )
= CC+ = CC'(CC)-I 0.72)
This equality can be verified directly by premultiplying (0' 0) and post multiplying (ce)
and then using (7.67). The inverse of P in the scalar case is p- I = 0-1 0 = C C- I. In
the matrix case, it becomes
p-I := 0+0 = (0'0)-10'0 (773)
= CC'" = CC'(CC')-I (774)
This again can be verified using (7.67). From OC = Oc, we have
C = (O'O)-IO'OC = PC
0= I
OCC'(CCyl = Op-
Their first p columns and first q rows are B = PB and C - CP- I . The equation
OAC = OAC implies

l
206  MINIMAL REALIZATIONS AND COPRIME FRACTIONS
| EXAMPLE 7.4  |     | Consider the rational matrices  |     |     |     |     |     |     |     |     |     |     |
| ------------ | --- | ------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
+]
,+1
| The matrix GI(s) has 1/(s  |     |     |     | +  1), 1/(s  |     | +  I), 1/(s  | +   | 1). and 1/(s  |     | +   |     |     |
| -------------------------- | --- | --- | --- | ------------ | --- | ------------ | --- | ------------- | --- | --- | --- | --- |
1) as its minors of order I
I
and det GI (s)  == 0 as its minor of order 2. Thus the characteristic polynomial of G (s) is s +
1
(s) ==  G (s) has 2/(5  +  1). 1/(s  +  1). I/(s  +  I). and 1/(5  +
| and oG | I   | l. The matrix  |     |     | 2   |     |     |     |     |     |     | I) as its  |
| ------ | --- | -------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---------- |
G
minors of order I, and det  (s) =  1/(s  +  1)2 as its minor of order 2. Thus the characteristic
2
| polynomial of G |     | 2 (s) is (s  |     | +  1)2 and oG |     | 2 (s) = 2.  |     |     |     |     |     |     |
| --------------- | --- | ------------ | --- | ------------- | --- | ----------- | --- | --- | --- | --- | --- | --- |
From this example. we see that the characteristic polynomial of G(5) is.  in  general,
different from the denominator of the de~nninant of G(5) (if G(5) is square] and different
from the least common denominator of all entries of G(s).
| EXAMPLE 7.5  |     | Consider the 2 x 3 rational matrix  |          |     |     |     |            |     |     |     |     |     |
| ------------ | --- | ----------------------------------- | -------- | --- | --- | --- | ---------- | --- | --- | --- | --- | --- |
|              |     |                                     |          |     |     | ~   | +          | +   |     |     |     |     |
|              |     |                                     |          |     |     |     | (05  1)(5  | 2)  |     |     |     |     |
|              |     |                                     | G(5) ==  |     | [5  | 1   |            |     |     |     |     |     |
1
-1
|     |     |     |     |     |     |      | +         | +   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | ---- | --------- | --- | --- | --- | --- | --- |
|     |     |     |     |     |     | + 1  | (5  1)(5  | 2)  |     |     |     |     |
5
Its minors of order 1 are the six entries of G(s). The matrix has the following three minors of
order 2:
+
|     |       | 5,    |      |           |        | 1               |                        | s           | 1     |                   |           |     |
| --- | ----- | ----- | ---- | --------- | ------ | --------------- | ---------------------- | ----------- | ----- | ----------------- | --------- | --- |
|     |       |       |      | +         |        |                 | ==                     |             |       |                   |           |     |
|     |       | +     | +    |           | +      | +               | -:-+-- -,-:-::+-c -~ - |             |       | .,-+- --.,-+- -~  |           |     |
|     | (5    | IHs   | 2)   | (5        | 1)2(s  |                 | 2)  (5                 | 1)2(s       | 2)    | (s                | 1)(5  2)  |     |
|     |       | s  1  |      | 1         |        |                 | s+4                    |             |       |                   |           |     |
|     | --    | . -   | +    |           |        | - --:-:--:---:- |                        |             |       |                   |           |     |
|     | s+15  |       | (s   | +l)(s+3)  |        | (s+1)(5+3)      |                        |             |       |                   |           |     |
|     |       | 1     |      |           |        | I               |                        |             |       | 3                 |           |     |
|     |       |       |      |           |        |                 |                        | =  -------- |       |                   |           |     |
|     |       | +     | +    |           | +      | +               | +                      |             | +     | +  2)(s +         |           |     |
|     | (5    | 1)(5  | 2)s  | (s        | 1)(5   |                 | 2)(5  3)               | s(s         | I)(s  |                   | 3)        |     |
|     |       |       |      |           |        |                 |                        | +           | +     |                   | +         |     |
.,  The least common denominator of all these minors is S(5  l)(s  2)(s  3). Thus the degree
1  of G(s) is 4. Note that G(s) has no minors of order 3 or higher.
In computing the characteristic polynomial. every minor must be reduced to a coprime
fraction as we did in the preceding ex.ample; otherwise. we will obtain an erroneous result.
We discuss two special cases. If G(s) is  1 x  p or q x  I, then there are no minors of order
2 or higher. Thus the characteristic polynomial equals the least common denominator of all
entries of G(s). In particular. if G(s) is scalar. then the characteristic polynomial equals its
denominator. If every entry of q x p G(s) has poles that differ from those of all other entries,
such as
then its minors contain no poles with multiplicities higher than those of each entry. Thus the
characteristic polynomial equals the product of the denominators of all entries of G(s).

209
|     |     |     |     |     |     |     |     | 7.8  | Matrix Polynomial Fractions  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ---- | ---------------------------- | --- | --- |
This  shows  that all  minimal  realizations of the  same  transfer  matrix  are  equivalent.
Q.E.D.
We see from the proof of Theorem 7.M3 that the results in the scalar case can be extended
directly to the matrix case if inverses are replaced by pseudoinverses. In MATLAB, the function
pinv generates the pseudoinverse. We mention that minimal realization can be obtained from
nonminimal realizations by applying Theorems 6.6 and 6.06 or by calling the MATLAB
function minreaL as the next example illustrates.
------
| EXAMPLE 7.6  |     | Consider the transfer matrix in Example -+.6 or  |     |     |     |        |     |     |       |     |     |
| ------------ | --- | ------------------------------------------------ | --- | --- | --- | ------ | --- | --- | ----- | --- | --- |
|              |     |                                                  |     |     |     | ~s~\O  |     |     | S~2l  |     |     |
[
|     |     |     |     | (s) =  |     |     |     |     |     |     | (7.75 j  |
| --- | --- | --- | --- | ------ | --- | --- | --- | --- | --- | --- | -------- |
G
|     |     |     |     |     |      |     | l~(S  |     | ~    |     |     |
| --- | --- | --- | --- | --- | ---- | --- | ----- | --- | ---- | --- | --- |
|     |     |     |     |     |      | +   | +     |     |      |     |     |
|     |     |     |     |     | (25  |     | 2)    | (s  | 2)2  |     |     |
|     |     |     |     |     |      |     |       | +   | +    |     |     |
Its characteristic polynomial can be computed as (2s  l)(s  2)2. Thus the rational matrix has
degree 3. Its six-dimensional realization in (4.39) and four-dimensional realization in (4.-1-1)
are clearly not minimal realizations. They can be reduced to minimal realizations by calling
the MATLAB function m::'r:::-ea~.  For example, for the realization in (4.39) typing
a= [-4.5  0  -6  0  -2  : ;0  -4.5  0  -6  0  -2; c  0  0  0  0  0; ...
o
|     | 1        | 0  0  | 0  0;0  | :    | !  0  0  | 0;0  | 0  G  1  | 0  OJ | ;   |     |     |
| --- | -------- | ----- | ------- | ---- | -------- | ---- | -------- | ----- | --- | --- | --- |
| b=  | [l  0;0  | 1;0   | 0;0     | :;00 | ;0       | OJ;  |          |       |     |     |     |
c= [- 6 3  -24  7.5  -=~ 3; 0  1  0 .5  :. 5  1  0.5J;0=[2  0;0  OJ ;
| [am,b~, |     | cm, | ~~J =mi~~2al |     | (a,b, | c,d)  |     |     |     |     |     |
| ------- | --- | --- | ------------ | --- | ----- | ----- | --- | --- | --- | --- | --- |
yields
|     |     | [  -0.8625  |         | -4.0897  |         |          |     |          |          | -0.5305]  |     |
| --- | --- | ----------- | ------- | -------- | ------- | -------- | --- | -------- | -------- | --------- | --- |
|     |     |             |         |          |         | 3.2544]  |     | [0.3218  |          |           |     |
|     | x=  |             |         |          |         |          |     | +        |          |           |     |
|     |     |             | 0.2921  | -3.0508  |         | 1.2709   |     | x        | 0.0459   | -0.4983   | u   |
|     |     | -0.0944     |         |          | 0.3377  | -0.5867  |     |          | -0.1688  | 0.0840    |     |
- 00339
|     | =   |      |     |     | 35.5281] x  |     | [2    | ~]u  |     |     |     |
| --- | --- | ---- | --- | --- | ----------- | --- | ----- | ---- | --- | --- | --- |
|     | v   | [0   |     |     |             |     |       |      |     |     |     |
|     | .   | 0    |     |     | -0.5720     |     | +  0  |      |     |     |     |
-2.1031
Its dimension equals the degree of(;(s): thus it is controllable and observable and is a minimal
realization of (;(s) in (7.75).
7.8  Matrix Polynomial Fractions
The degree of the scalar transfer function
|     |     |     |         | •   | N(sj  |         |         |             |     |     |     |
| --- | --- | --- | ------- | --- | ----- | ------- | ------- | ----------- | --- | --- | --- |
|     |     |     | g(s) =  |     | -- =  | N (s)D- | '(s) =  | D-'(s)N(s)  |     |     |     |
D(s)
is defined as the degree of D(s) if N(s) and D(s) are coprime. It can also be defined as
the smallest possible denominator degree. In this section, we shall develop similar results for

7.8 ,\latrix Polynomial Fractions 211
which implies that if the determinant of M(s) is a nonzero constant, so is the determinant of
I
M- (s). Thus the inverse of a unimodular matrix .'\1(5) is a2ain a unimodular matrix.
Definitio1l 7.3 A square polynomial matrix R(s) is a greatest common right divisor
(gcrdJ ofO(s) and N(s) if(i) R(s) is a common right dil"isor ofO(s) a1ld N(s) and (iiJ
R(s) is a left multiple of every common right dil"isor ofO(s) and N(s). If a gcrd is a
unimodular matrix, then O(s) and N (s) are said to be right coprime.
Dual to this definition, a square polynomial matrix R(s) is a greatest common left divisor
(geld) of D(s) and !\I(s) if (i) R(s) is a common left divisor of D(s) and !\I(s) and (ii) R(s)
is a right multiple of every common left divisor oi 0(5) and !\Irs). If a geld is a unimodular
matrix, then D(s) and !\I(s) are said to be left coprime.
Definition 7.4 Consider a proper rational matrix G(s) jactored as
0-1
G(s) = N(S)O-I (s) = (5 15i(s)
where N(s) and 0(5) are right coprime, and :\15) and 0(5) are left coprime. Then the
characteristic polynomial of G(s) is defined as
det O(s) or det 0(5)
and the degree ofG(s) is defined as
deg G A (s) = deg det 0(5) = deg det 0 _ (5)
Consider
G(s) = N(s)O-I(S) = [N(SIR(s)][D(s)R(s)]-1 (7.78)
=
where N(s) and O(s) are right coprime. Define D:(s) = D(s)R(s) and NI(s) N(s)R(s).
Then we have
detOI(s) = det[O(s)R(s)] = detO(s) det R(s)
which implies
degdetOI(s) = degd~tDls) -:- degdetR(s)
Clearly we have degdetOI(s) ::: degdetO(s) and the equality holds if and only if R(s) is
unimodular or, equivalently, NI (5) anc DI (s) are right coprime. Thus we conclude that if
1
N (s )0- (s) is a coprime fraction, then O(s) has the smallest possible determinantal degree
and the degree is defined as the degree of the transfer matrix. Therefore a coprime fraction can
also be defined as a polynomial matrix fraction with the smallest denominator's determinantal
degree. From (7.78), we can see that coprime fractions are not unique: they can differ by
unimodular matrices.
We have introduced Definitions 7.1 and 7.4 to define the degree of rational matrices. Their

212 MINIMAL REALIZATIONS AND COPRIME FRACTIONS
equivalence can be established by using the Smith-McMillan form and will not be discussed
here. The interested reader is referred to. for example. Reference [3].
7.8.1 Column and Row Reducedness
In order to apply Definition 7.4 to determine the degree of G(s) = N(s)D-1(s). we must
compute the determinant of D(s). This can be avoided if the coprime fraction has some
additional property as we will discuss next.
The degree of a polynomial vector is defined as the highest power of s in all entries of
the vector. Consider a polynomial matrix M(s). We define
8ciM(S) = degree o,f ith column ofM(s)
I
8 ;M(s) = degree of ith row of M(s)
r
and ca1l8 the column degree and Or; the row degree. For example, the matrix
ci
= s + 1 53 - 2s + 5
M(s)
[s - 1
= = = = =
has Oel I, Oe2 3, 0c3 O. Orl 3, and Or2 2.
Definition 7.5 A nonsingular polynomial matrix M(s) is column reduced if
=
deg del M(s) sum of all column degrees
It is row reduced if
=
deg det M(s) sum of all row degrees
A matrix can be column reduced but not row reduced and vice versa. For example. the
matrix
+
3s2 2s
= ,
M(s) (7.79)
[
s-+s-3
+ +
has determinant s3 - 52 55 3. Its degree equals the sum of its column degrees 2 and I. Thus
M(s) in (7.79) is column reduced. The row degrees of M(s) are 2 and 2; their sum is larger
than 3. Thus M(s) is not row reduced. A diagonal polynomial matrix is always both column
and row reduced. If a square polynomial matrix is not column reduced. then the degree of its
determinant is less than the sum of its column degrees. Every nonsingular polynomial matrix
can be changed to a column- or row-reduced matrix by pre- or posunultiplying a unimodular
matrix. See Reference [6. p. 603].
= =
Let 0e;M(s) k" and define Hc(s) diag(skcl. skc' •... ). Then the polynomial matrix
M(s) can be expressed as
(7.80)
For example. the M(s) in (7.79) has column degrees 2 and I and can be expressed as

210  MINIMAL REALIZATIONS AND COPRIME FRACTIONS
transfer matrices. Because matrices are not commutative. their orders cannot be altered in our
discussion.
Every q x p proper rational matrix (;(s) can be expressed as
(;(s) = N(s)D-1 (s)
(7.76)
where N (s) and D(s) are q x p and p x p polynomial matrices. For example, the 2 x 3 rational
matrix in Example 7.5 can be expressed as  :
|     |     |     |     |     | o   | ]_1  |     |
| --- | --- | --- | --- | --- | --- | ---- | --- |
o
I
| •  = [  | s   |     |     | +   | +         |     |         |
| ------- | --- | --- | --- | --- | --------- | --- | ------- |
| G (s)   |     |     |     | (s  | 1)(s  2)  |     | (7.77)  |
|         | -1  |     |     |     |           | ~   |         |
|         | 1   |     |     |     | o         |     |         |
s(s  3)
The three diagonal entries of D(s) in (7.77) lare the least common denominators of the three
columns of (;(5). The fraction in (7.76) oi (7.77) is called a right polynomial fraction or,
simply, right fraction. Dual to (7.76), the expression
(;(s) = f>-I
(s)N(s)
and N( s) are q
where f>(s)  x q and q  x  p polynomial matrices, is called a left polynomial
fraction or, simply, left fraction.
Let R(s) be any p x p nonsingular polynomial matrix. Then we have
(;(s) = (N(s)R(s)][D(s)R(sWI
= N(s)R(s)R-1 (s)D-1 (s) = N(s)D-1( s)
Thus right fractions are not unique. The same holds for left fractions. We introduce in the
following right coprime fractions.
Consider A(s) = 8(s)C(s), where A(s), 8(s), and C(s) are polynomials of compatible
orders. We call C(s) a right divisor of A(s) and A(s) a left multiple of C(s). Similarly, we call
8(s) a left divisor of A(s) and A(s) a right multiple of 8(s).
Consider two polynomial matrices D(s) and N(s) with the same number of columns p.
A P x P square polynomial matrix R(s) is called a common right divisor of D(s) and N(s) if
there exist polynomial matrices D(s) and N (s) such that
|     |       | =         |      |       | =         |     |     |
| --- | ----- | --------- | ---- | ----- | --------- | --- | --- |
|     | D(s)  | D(s)R(s)  | and  | N(s)  | N(s)R(s)  |     |     |
Note that D(s) and N (s) can have different numbers of rows.
Definition 7.2 A square polynomial matrix !VI(s) is called a unimodular matrix if its
detemJinant is nonzero and independent of s.
The following polynomial matrices are all unimodular matric~s:
[-2
[s
| 2S  | S2+S+1]  |     | SIO+S+I]  |     |     | s+s  1]  |     |
| --- | -------- | --- | --------- | --- | --- | -------- | --- |
[
| 2   | s+1  | '   | 0   | 3   | 's-1  |     |     |
| --- | ---- | --- | --- | --- | ----- | --- | --- |
Products of unimodular matrices are clearly unimodular matrices. Consider
|                      |     |     | =                  |     | =      | =   |     |
| -------------------- | --- | --- | ------------------ | --- | ------ | --- | --- |
| det M(s)det M-1( s)  |     |     | det (M(s)M-1( s»)  |     | det I  | I   |     |

7.8 Matrix Polynomial Fractions 213
0]+[ 2s I]
2][S2
M(S)=[~
lOs s-3 0
The constant matrix Mhe is called the column-degree coefficient matrix; its ith column is the
coefficients of the ith column of M(s) associated with Sk". The polynomial matrix Mle(s)
contains the remaining terms and its ith column has degree less than kei. If M(s) is expressed
as in (7.80), then it can be verified that M(s) is column reduced if and only if its column-degree
coefficient matrix Mhc is nonsingular. Dual to (7.80), we can express M(s) as
+
M(s) = Hr(s)Mhr Mlr(s)
= =
where 8" M(s) kri and Hr (s) diag(sk,1 . Sk,2, ... ). The matrix Mhr is called the row-degree
coefficient matrix. Then M(s) is row reduced if and only if M hr is nonsingular.
Using the concept of reducedness, we now can state the degree of a proper rational matrix
as follows. Consider G(s) = N(s)D-1(s) = D-1(s)N(s), where N(s) and D(s) are right
coprime, N(s) and D(s) are left coprime, D(s) is column reduced, and D(s) is row reduced.
Then we have
deg G(s) = sum of column degrees of D(s)
- sum of row degrees of D(s)
1
We discuss another implication of reducedness. Consider G(s) = N(s)D- (s). If G(s)
is strictly proper, then 8eiN(s) < 8ciD(s), for i = 1,2, .... p; that is. the column degrees
of N(s) are less than the corresponding column degrees of D(s). If G(s) is proper, then
8eiN(s) S 8ciD(s), for i = 1,2, ...• p. The converse, however, is not necessarily true. For
example. consider
Although 8ci N (s) < 8ci D(s) for i = I, 2, N (s )0-1 (s) is not strictly proper. The reason is that
D(s) is not column reduced.
:> Theorem 7.8
Let N (s) and D(s) be q x p and p x p polynomial matrices, and let D(s) be column reduced. Then
1
the rational matrix N(s)D- (s) is proper (strictly proper) if and only if
fori = 1. 2 .... , p.
:a
Proal The necessity part of the theorem follows from the preceding example. We show
the sufficiency. Following (7.80), we express
D(s) = DhcHc(s) + Dlc(s) = [Dhc + Dlc(s)H;:-I(S)]Hc(s)
N(s) = NhcHc(S) + NicCs) = [Nhc + Nlc(s)H;:-I(S)]Hc(s)
Then we have

|     |                    |          |      |       | 7.8  Matrix Polynomial Fractions  | 215  |
| --- | ------------------ | -------- | ---- | ----- | --------------------------------- | ---- |
|     |                    | = Do +   |      | +     | +  +                              |      |
|     | D(s)               |          | DIs  | D2S2  | D3S3  D4S4                        |      |
|     | N(s) = No + Nls +  |          |      |       | z +  + N4s4                       |      |
|     |                    |          |      | N2s   | N3s3                              |      |
|     | D(s) = Do +        |          |      | +     | +                                 |      |
|     |                    |          | DIs  | DZS2  | D3S3                              |      |
|     |                    | =  No +  |      | +     | + N3S3                            |      |
|     | N(s)               |          | Nis  | N2S2  |                                   |      |
D N
where  i,  i, Di, and Ni are, respectively, q x q, q x p, p x p, and q x p constant matrice~.
The constant matrices Di and Ni are known, and Di and Ni are to be solved. Substituting these
=
into (7.S2) and equating to zero the constant matrices associated with sk, for k
0, 1, ... ,
we obtain
-No
Do  No
|     |     | 0   | 0   | 0   | 0  0  0  |     |
| --- | --- | --- | --- | --- | -------- | --- |
Do
| DI  | . I'll  | Do  | No  | 0   | 0  0  |     |
| --- | ------- | --- | --- | --- | ----- | --- |
0
| D2  | Nz  | DI  | NI  | Do  | No  0  0  | --'NI  |
| --- | --- | --- | --- | --- | --------- | ------ |
D]
|     |     |     |     | D]  | N]      |     |
| --- | --- | --- | --- | --- | ------- | --- |
| D3  | N3  | D2  | Nz  |     | Do  No  |     |
SM:=  =0  (7.83)
| D4  | N4  | D3  | N3  | Dz  | DI  N]  |      |
| --- | --- | --- | --- | --- | ------- | ---- |
|     |     |     |     |     | Nz      | -Nz  |
Dz
| 0   | 0   | D4  | N4  | D3  | N3  D2  Nz  |     |
| --- | --- | --- | --- | --- | ----------- | --- |
| 0   | 0   | 0   | 0   | D4  | N4  D3  N3  |     |
-N3
D3
| 0   | 0   | 0   | 0   | 0   | 0  D4  N4  |     |
| --- | --- | --- | --- | --- | ---------- | --- |
This equation is the matrix version of (7.28) and the matrix S will be called a generali~ed
resultant. Note that every V-block column has q V-columns and every N -block column has p
N- columns. The generalized resultant S as shown has four pairs of V- and N- block columns;
+
thus it has a total of 4(q  p) columns. It has eight block rows; each block rows has q rows.
Thus the resultant has Sq rows.
We now discuss some general properties of S under the assumption that linearly indepen
dent columns of S from left to right have been found. It turns out that every V-column in every
V-block column is linearly independent of its left-hand-side (LHS) columns. The situation for
N -columns, however, is different. Recal1 that there are p N -columns in each N -block column.
We use Ni-column to denote the ith N-column in each N-block column. It turns out that if
N  N
the  i -column in some  -block column is linearly dependent on its LHS columns, then all
subsequent Ni-columns, because of the repetitive structure ofS, will be linearly dependent on
N
its LHS columns. Let IIi, i =  1,2, ... , p, be the number of linearly independent  i-columns
in S. They are called the column indices of G(s). The first Ni-column that becomes linearly
dependent on its LHS columns is called the primary dependent N i -column. It is clear that the
+  I)th N
(IIi  j  -column is the primary dependent column.
Corresponding to each primary dependent Ni  -column, we compute the monic null vector
(its last entry equals 1) of the submatrix that consists of the primary dependent N
i  -column and
all its LHS linearly independent columns. There are totally p such monic null vectors. From
these monic null vectors, we can then obtain a right fraction. This fraction is right coprime
because we use the least possible IIi and the resulting D(s) has the smallest possible column

216  MINIMAL REALIZATIONS AND COPRIME FRACTIONS
degrees. In addition, D(s) automatically will be column reduced. The next example illustrates
the procedure.
EXAMPLE 7.7  Find a right coprime fraction of the transfer matrix in (7.75) or
|     |     |     |     |     | 45-t1 0  |     | 5!2]  |     |     |     |
| --- | --- | --- | --- | --- | -------- | --- | ----- | --- | --- | --- |
=
|     |     |     | G(s)  |     | 25  | I   | 5 + I  |     |     | (7.84)  |
| --- | --- | --- | ----- | --- | --- | --- | ------ | --- | --- | ------- |
[
|     |     |     |     | (25 + 1)(5 + 2)  |     |     | (5 + 2)2  |     |     |     |
| --- | --- | --- | --- | ---------------- | --- | --- | --------- | --- | --- | --- |
First we  must find  a left fraction.  not necessarily  left coprime.  Using the least common
denominator of each row, we can readily obtain
]-1
|     | '   |     | [(25 + 1)(5 +2):  |     |     |     | °  .  |     |     |     |
| --- | --- | --- | ----------------- | --- | --- | --- | ----- | --- | --- | --- |
G(5) =
|     |     |     |     | o   | (25 +  |     | +  2)-0  |     |     |     |
| --- | --- | --- | --- | --- | ------ | --- | -------- | --- | --- | --- |
1)(5
|     |     |     | (45-10)(5+2)  |      |     | 3(25+1)]          |     | D--1(  | N-       |     |
| --- | --- | --- | ------------- | ---- | --- | ----------------- | --- | ------ | -------- | --- |
|     |     | x   |               |      |     |                   |     | =:     |          |     |
|     |     |     |               |      |     |                   |     |        | 5)  (s)  |     |
|     |     |     | [             | + 2  |     | (s + 1) (2s + 1)  |     |        |          |     |
S
Thus we have
2
|     |     | -   | [25 | +5S+2  |     |     |     |     |     |     |
| --- | --- | --- | --- | ------ | --- | --- | --- | --- | --- | --- |
D(s) =
253 + 952°+ 125 + 4]
°
0]
|     |     |     |     |     |     |     | °       | °   |     |     |
| --- | --- | --- | --- | --- | --- | --- | ------- | --- | --- | --- |
|     |     |     |     |     | 0]  |     | [2  0]  | [0  | 3   |     |
|     |     |     |     |     |     | +   | 0       | +   | 2   |     |
|     |     |     |     |     | 12  | S   | 9  5 -  |     | 5   |     |
and
|     | -   |     | [4s2 - |     |     |     |     |     |     |     |
| --- | --- | --- | ------ | --- | --- | --- | --- | --- | --- | --- |
+
|     |       |     |          | 25 - 20  |      | 65        | 3  ]           |     |              |     |
| --- | ----- | --- | -------- | -------- | ---- | --------- | -------------- | --- | ------------ | --- |
|     | N(s)  | =   |          |          |      | )         |                |     |              |     |
|     |       |     |          | 5  + 2   | 2s-  | + 35 + 1  |                |     |              |     |
|     |       | =   | [-20     | 3]       | [-2  | 6]5       | [4  0]s,- + [0 |     |   0]   S'1   |     |
|     |       |     | 21+13+0  |          |      |           |                | °   |  °           |     |
2
We form the generalized resultant and then use the QR decomposition discussed in Section
7.3.1 to search its linearly independent columns in order from left to right. Because it is simpler
to key in the transpose of So we type
| dl = [2       |           |          |          | C J ; d2 = [0  |     |         |                   |             |     |     |
| ------------- | --------- | -------- | -------- | -------------- | --- | ------- | ----------------- | ----------- | --- | --- |
|               | 0         | "  0     | 2  0  0  |                | 4   | 0  1:'  | 0  9  0  2 J ;    |             |     |     |
| n 1 = [ -2 0  |           |          |          | O};:o2 = [2    |     |         |                   |             |     |     |
|               |           | 2  -2    | 1  ~     | :1  0          |     | 1       | 3  0  :'  0  0];  |             |     |     |
| s = [dl       | 0         | 0  0     | 0; d2    | 0  0  CO; n 1  | 0   | 0  0    | 0; n2  :J  0      | 0  0; .. .  |     |     |
|               | o  0  dl  | 0        | 0;0  0   |                |     |         |                   |             |     |     |
|               |           |          |          | d2  0  0;0     | 0   | nl  0   | 0;0  C  n2        | 0  0; .. .  |     |     |
|               | 000       | 0  dl;O  | 0        | 0  0  d2;O     | 0   | 0  0    | nl;O  COO         | n2J ';      |     |     |
[q,rJ=qrls)
We  need only r: therefore the matrix q  will not be shown. As discussed in Section 7.3.1.
we need to know whether or not entries of r  are zero in determining linear independence of
columns: therefore all nonzero entries are represented by x  di  and ni. The result is
|     |     |     |     |     |     |     | 0   | 0   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

214 MINIMAL REALIZATIONS AND COPRIME FRACTIONS
.--------.
1 + + I
G(s) := N(s)D- (s) = [Nhc N{c(s)H;I(s)J[Dhc Dlc(s)H;1 (sW
Because D{c(s)H,:-I(s) and N{c(s)H,:-I(s) both approach zero as s _ 00, we have
lim (;(s) = NhcD;;-}
s~oo
where Dhc is nonsingular by assumption. Now if ociN(s) =::: OciD(S), then Nhc is a nonzero
constant matrix. Thus (;(00) is a nonzero constant and (;(s) is proper. If Dei N(s) < OciD(S),
=
then Nhc is a zero matrix. Thus (;(00) 0 and (;(s) is strictly proper. This establishes
the theorem. Q.E.D.
We state the dual of Theorem 7.8 without proof.
~ Corollary 7.8
Let N(s) and pes) be_q x p and q x q polynomial matrices, and let D(s) be row reduced. Then
n-I
the rational matrix (s)N (s) is proper (strictly 'proper) if and only if
for i = I, 2, ... , q.
7.8.2 Computing Matrix Coprime Fractions
1
Given a right fraction N(s)D- (s), one way to reduce it to a right coprime fraction is to
compute its gcrd. This can be achieved by applying a sequence of el:mentary operations.
=
Once a gcrd R(s) is computed, we compute N(s) = N(s)R-I(s) and D(s) D(s)R-I(s).
Then N(s)D-1 (s) = N(s)D- 1 ( s) and N(S)O-I (s) is a right coprime fraction. If D(s) is not
column reduced, then additional manipulation is needed. This procedure will not be discussed
here. The interested reader is referred to Reference [6, pp. 590-591).
We now extend the method of computing scalar coprime fractions in Section 7.3 to the
matrix case. Consider a q x p proper rational matrix (;(s) expressed as
(7.81 )
In this section, we use variables with an overbar to denote left fractions, without an overbar to
denote right fractions. Clearly (7.8\) implies
N(s)D(s) = O(s)N(s)
and
O(s)( -N(s» + N'(s)D(s) = 0 (7.82)
0-1
We shall show that given a left fraction (s)N'(s). not necessarily left coprime, we can
obtain a right coprime fraction N(s)D-1 (s) by solving the polynomial matrix equation in
(7.82). Instead of solving (7.82) directly, we shall change it into solving sets of linear algebraic
equations. As in (7.27), we express the polynomial matrices as, assuming the highest degree
to be 4 to simplify writing,

7.8 Matrix Polynomial Fractions 217
dl 0 x x .r x x x x 0 x x
0 d2 x .r x x x x 0 .r x x
0 0 nl x .r x x .r x x x x
0 0 0 112 x .r x x x x x x
0 0 0 0 dl x x x x x x x
0 0 0 0 0 d2 x .r x .r x x
r=
0 0 0 0 0 0 n1 x x .r x x
0 0 0 0 0 0 0 0 x x x 0
0 0 0 0 0 0 0 0 dl x .r 0
0 0 0 0 0 0 0 0 0 d2 0 0
0 0 0 0 0 0 0 0 0 0 0 0
0 0 0 0 0 0 0 0 0 0 0 0
We see that al1 D-columns are linearly independent of their LHS columns. There are two
N
linearly independent I-columns and one linearly independent N2-column. Thus we have
= =
J.L I 2 and J.L2 I. The eighth column of S is the primary dependent N2-column. We
N.2
compute a nul1 vector of the submatrix that consists of the primary dependent -column and
all its LHS linearly independent columns as
=2=null ([:::1 0 0;d2 0 O;nl 0 C;n2 iJ 0;... )
o
0 d1;0 0 d2;0 0 n1;0 0 n2 l 'J;
and then nonnalize the last entry to I by typing
z2b=z2/ z2 (8)
which yields the first monic null vector as
z2b= [7 -1: 2 -402 II '
N
The eleventh column of S is the primary dependent I-column. We compute a null vector
N
of the submatrix that consists of the primary dependent I-column and all its LHS linearly
independent columns (that is. deleting the eighth column) as
:l~null ( [d: 0 0 0 O;d2 0 0 0 O;nl Q 0 C O;n2 0 0 ~ 0; .. .
o
0 d1 0 0;0 0 d2 0 0; 0 0 ~l 0 0; ...
G ':1 0 0 dl; 0 0 0 0 d2 ; Q O J 0 n2. ~ ' ) ;
and then nomlalize the last entry to I by typing
: lb=zl 2: (:'0)
which yields the second monic null vector as
zlb=[10 -0.5 1 0 1 0 2.5 -2 0 11'

7.8 Matrix Polynomial Fractions 219
In general. if the generalized resultant has f.l-i linearly independent lVi-columns, then
D(s) computed using the preceding procedure is column reduced with column degrees l1i.
Thus we have
L
deg (;(s) = deg det D(s) = 11,
= total number of linearly independent lV-columns in S
We next show that the order of column degrees is immaterial. In other words, the order of
the columns of N(s) and D(s) can be changed. For example, consider the permutation matrix
P=[; iJ
~
= =
and O(s) D(s)P and N(s) N(s)P. Then the first, second, and third columns of D(s) and
N(s) become the third, first. and second columns of O(s) and N(s). However. we have
(;(s) = N(S)O-I(S) = [N(s)P][D(s)prl = N(s)D-I(s)
This shows that the columns ofD(s) and N(s) can arbitrarily be permutated. This is the same as
permuting the order of the null vectors in (7.83). Thus the set of column degrees is an intrinsic
property of a system just as the set of controllability indices is (Theorem 6.3). What has been
discussed can be stated as a theorem. It is an extension of Theorem 7.4 to the matrix case.
~ Theorem 7.M4
Let (;(s)
= fi-I
(s)N(s) be a left fraction, not necessarily left coprime. We use the coefficient matrices
of fi(s) and N ( s) to form the generalized resultant S shown in (7.83) and search its linearly independent
columns from left to right. Let f.l-i, i = I, 2, .... p. be the number oflinearly independent lVi-columns.
Then we have
+ + ... +
deg G(s) = f.l-l 112 f.l-p (7.87)
and a right coprime fraction N(s)D-1 (s) can ~ obtained by computing p monic null vectors of the p
matrices formed from each primary dependent N i -column and all its LHS linearly independent columns.
The right coprime fraction obtained by solving the equation in (7.83) has one additional
important property. After permutation, the column-degree coefficient matrix Dnc can always
become a unit upper triangular matrix (an upper triangular matrix with I as its diagonal entries).
Such a D(s) is said to be in column echelon form. See References [6. pp. 610-612; 13. pp.
483-487]. For the D(s) in (7.86), its column-degree coefficient matrix is
= [~ ~]
Dhc
It is unit upper triangular; thus the D(s) is in colu~ echelon form. Although we need only
column reducedness in subsequent discussions, if D(s) is in column echelon form, then the
result in the next section will be nicer.
Dual to the preceding discussion, we can compute a left coprime fraction from a right
fraction N(s)D-1(s), which is not necessarily right coprime. Then similar to (7.83), we form

220 MINIMAL REALIZATIONS AND COPRIME FRACTIONS
(7.88)
with
Do DI D2 D3 D4 0 0 0
No NI N2 N3 N4 0 0 0
o
Do DI D2 D3 D4 0 0
o
No NI N2 N3 N4 0 0
T'- (7.89)
o
0 Do DI D2 D3 D4 0
o
0 No,' NI N2 N3 N4 0
o o o
Do DI D2 D3 D4
o o o
No NI N2 N) N4
We search linearly independent rows in order from top to bottom. Then all D-rows are linearly
independent. Let the Ni-row denote the ith N-row in each N block-row. If an Ni-row becomes
linearly dependent, then all Ni-rows in subsequent N block-rows are linearly dependent on
their preceding rows. The first Ni-row that becomes linearly dependent is called a primary
=
dependent Ni-row. Let Vj, i I. 2 ..... q, be the number of linearly independent Ni-rows.
They are called the row indices of (;(s). Then dual to Theorem 7.M4. we have the following
corollary.
::)0 Corollary 7.M4
=
Let G(s) N(s)D-1 (s) be a right fraction. not necessarily right coprime. We use the coefficient
matrices of D(s) and N(s) to fonn the generlized resultant T shown in (7.89) and search its linearly
independent rows in order from top to bottom. Let Vi. for i = 1.2, .... q. be the number of linearly
independent Ni-rows in T. Then we have
deg G(s) = VI + V2 + ... + Vq
and a left coprime fraction D-I (s)N (s) can be obtained by computing q monic left null vectors of the
q matrices formed from each primary dependent Ni-row and all its preceding linearly independent rows.
The polynomial matrix D(s) obtained in Corollary 7.M4 is row reduced with row degrees
{Vi. i = I. 2 .... , q}. In fact, it is in row echelon form; that is, its row-degree coefficient
matrix. after some row permutation. is a unit lower triangular matrix.
7.9 Realizations from Matrix Coprime Fractions
Not to be overwhelmed by notation. we discuss a realization of a 2 x 2 strictly proper rational
matrix G(s) expressed as
(7.90)

218  MINIMAL REALIZATIONS AND COPRIME FRACTIONS
Thus we have
10
-nb2
| r,  |     |     |     | -nbl  |     |     |     | 7   |     |
| --- | --- | --- | --- | ----- | --- | --- | --- | --- | --- |
_n
|     |     |     |     | 1   | 22  |     | -0.5  | -I  |     |
| --- | --- | --- | --- | --- | --- | --- | ----- | --- | --- |
-n5
0
|     |     | -No  |     | dll  | dl2  |     | I   | I   |     |
| --- | --- | ---- | --- | ---- | ---- | --- | --- | --- | --- |
|     |     |      |     | 0    | 0    |     |     |     |     |
|     |     |      |     | d21  | d22  |     |     |     |     |
|     |     |      |     |      |      |     | 0   | 2   |     |
|     |     |      |     | 0    | 0    |     |     |     |     |
Do
|     |     |      |     |       | _n1     | 2   | I   | -4  |     |
| --- | --- | ---- | --- | ----- | ------- | --- | --- | --- | --- |
|     |     |      |     | -n:1  | I       |     |     |     |     |
|     |     |      |     | _n2   | -ni0-0  |     |     |     |     |
|     |     | -NI  |     | 1     |         |     | 0   | 0   |     |
I
|     |     |     | -   |        |         | -   |      |     | (7.85)  |
| --- | --- | --- | --- | ------ | ------- | --- | ---- | --- | ------- |
|     |     |     |     | d l l  | l2      |     | 2.5  | 2   |         |
|     |     | DI  |     |        | .   d I |     |      |     |         |
|     |     |     |     | I      | '       |     |      |     |         |
|     |     |     |     | 21 I   | 2       | 2   |      |     |         |
|     |     |     |     | d      | d       |     |      |     |         |
|     |     |     |     | l      | I       |     |      |     |         |
-Nz
|     |     |     |     | _nil  |     |     | -2  |     |     |
| --- | --- | --- | --- | ----- | --- | --- | --- | --- | --- |
_n~2
2
-n?
|     |     | D2  |     | -n~1  |     |     | 0   |     |     |
| --- | --- | --- | --- | ----- | --- | --- | --- | --- | --- |
'dF
d~1
|     |     |     |     | d21  | d22  |     |     |     |     |
| --- | --- | --- | --- | ---- | ---- | --- | --- | --- | --- |
|     |     |     |     | 2    | 2    |     |     |     |     |
where we have written out N; and D; explicitly with the superscripts ij denoting the ijth entry
and the subscript denoting the degree. The two monic null vectors are arranged as shown. The
order of the two null vectors can be interchanged, as we will discuss shortly. The empty entries
are to be filled up with zeros. Note that the empty entry at the (8  x  I)th location is due to
in
deleting the second  linearly dependent column in computing the second null vector. By
equating the corresponding entries in (7.85), we can readily obtain
|     |     |            | I   | I  ]   | [2. 5   | 2 ]     | [  I  | 0 ]  2  |     |
| --- | --- | ---------- | --- | ------ | ------- | ------- | ----- | ------- | --- |
|     |     | D(s) = [ 0 |     | 2   +  | 0       | I  S +  | 0     | 0       |     |
S
=
[S2 + 2.55 +
|     |     |     |     |     | I   | 25 +  | I ]  |     |     |
| --- | --- | --- | --- | --- | --- | ----- | ---- | --- | --- |
o
5+2
•  and
|     |     | N   | [-10  | -7]  | [-I  |     |     |     |     |
| --- | --- | --- | ----- | ---- | ---- | --- | --- | --- | --- |
s  =
|     |     | ( )  | 0.5    | I    | +  0  |      |     |     |     |
| --- | --- | ---- | ------ | ---- | ----- | ---- | --- | --- | --- |
|     |     |      |        | 10   |       | 7]   |     |     |     |
|     |     | =    | [2S2 - | S -  | 4s -  |      |     |     |     |
|     |     |      |        | 0.5  |       | I    |     |     |     |
Thus G(s) in (7.84) has the following right coprime fraction
=
|     | (;s  | [(2S-5)(S+2)  |     | 4S-7] [(5+2)(5+0.5)  |     |     |     | 25+1]-1  |     |
| --- | ---- | ------------- | --- | -------------------- | --- | --- | --- | -------- | --- |
(7.86)
|     | ( )  |     | 0.5  |     | 1   |     | 0   | 5 + 2  |     |
| --- | ---- | --- | ---- | --- | --- | --- | --- | ------ | --- |
|     |      |     |      |     |     |     | =   | =      |     |
The D(s) in (7.86) is column reduced with column degrees Jl..1  2 and Jl..2  1. Thus we have
|     | = 2  | =   |     |     |     |     |     |     |     |
| --- | ---- | --- | --- | --- | --- | --- | --- | --- | --- |
deg det D(5)  +  I  3 and the degree of (;(5) in (7.84) is 3. The degree was computed in
Example 7.6 as 3 by using Definition 7. \.

|     | 7.9  Realizations from Matrix Coprime Fractions  |     | 221  |
| --- | ------------------------------------------------ | --- | ---- |
where N (s) and D(s) are right coprime and D(s) is in column echelon form.6 We further assume
=
that the column degrees ofD(s) are III  4 and 112  =  2. First we define
sl"
| H(s):=  | 0   |     | (7.91)  |
| ------- | --- | --- | ------- |
[
and
Sl',-I
|     | 0   | s3  |     |
| --- | --- | --- | --- |
0
s0·   0
|          | 0   | s  0  |         |
| -------- | --- | ----- | ------- |
| L(s) :=  |     | -     | (7.92)  |
J. .u-1
0  S  - 0
0  s
|     | 0   | 0   |     |
| --- | --- | --- | --- |
The procedure for developing a realization for
| yes) = G(s)u(s) =  |     | N(s)D-Iu(s)  |     |
| ------------------ | --- | ------------ | --- |
follows closely the scalar case from (7.3) through (7.9). First we introduce a new variable v(t)
=  I
defined by y(s)  D- (s)u(s). Note that yes), called a pseudo state, is a 2 x 1 column vector.
Then we have
D(s)y(s) = u(s)
(7.93)
|     | y(s) = N (s )y(s)  |     | (7.94)  |
| --- | ------------------ | --- | ------- |
Let us define state variables as
o
[ ~I(S)J
| xes) = L(s)Y(s) =  | o   |     |     |
| ------------------ | --- | --- | --- |
V2(S)
|           | 0           | 1   |     |
| --------- | ----------- | --- | --- |
| s3vI (s)  | X, (s)      |     |     |
| s"VI      | (s)  X2(S)  |     |     |
su,(s)
X3(S)
|     | -.  |     | (7.95)  |
| --- | --- | --- | ------- |
VI (s)
X4(S)
| SV l (s)  | X5(S)  |     |     |
| --------- | ------ | --- | --- |
| V2(S)     | X6(S)  |     |     |
or, in the time domain,
v,
XI (t)  =  x2(1) =
| vP)(t)  | (t)  |     |     |
| ------- | ---- | --- | --- |
=
| X5(t)  V2(t)  X6(t) =  | Vl(t)  |     |     |
| ---------------------- | ------ | --- | --- |
6. All discussion is still applicable if D(s) is column reduced but not in echelon form.

7.9  Realizations from Matrix Coprime Fractions  223
Substituting this into (7.94) and using  xes) = L(S)V(5), we have
| yes)  | [13111  | 13112  | 13113  | 13114  | 13121  | 13122]X(5)  |     |
| ----- | ------- | ------ | ------ | ------ | ------ | ----------- | --- |
=  (7.103)
|     | 13211  | 13212  | 13213  | 13214  | 13221  | 13222  |     |
| --- | ------ | ------ | ------ | ------ | ------ | ------ | --- |
Combining (7.96), (7.101), and (7.103) yields the following realization for G(5):
| -aliI  | -a112  | -al13  |     | -a114  |     | -Q'121  | -at:!:!  |
| ------ | ------ | ------ | --- | ------ | --- | ------- | -------- |
|        | 0      |        | 0   | 0      |     | 0       | 0        |
| 0      |        | 1      | 0   | 0      |     | 0       | 0        |
x=
x
| 0      | 0      |        | .I  | 0        |     |         |          |
| ------ | ------ | ------ | --- | -------- | --- | ------- | -------- |
|        |        |        |     |          |     | 0       | 0        |
| -a211  | -a212  | -a213  |     | - Ct214  |     | -0'221  | -an:!    |
| 0      | 0      |        | 0   | 0        |     |         | 0        |
| 1      | b      |        |     |          |     |         | (7.104)  |
12
| 0     | 0      |        |        |        |     |     |     |
| ----- | ------ | ------ | ------ | ------ | --- | --- | --- |
| 0     | 0      |        |        |        |     |     |     |
| +  0  | 0      | u      |        |        |     |     |     |
| 0     | 1      |        |        |        |     |     |     |
| 0     | 0      |        |        |        |     |     |     |
|       | 13112  | 13113  | 13114  | 13121  |     |     |     |
Y=  . [ 13111
13m] x
| 13211  | 13212  | /3213  | 13214  | /3221  | 13m  |     |     |
| ------ | ------ | ------ | ------ | ------ | ---- | --- | --- |
+
This is a (iJ.I  iJ.2)-dimensional state equation. TheA-matrix has two companion-form diagonal
|     | =   |     |     |     |     | =   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
blocks: one with order iJ.I  4 and the other with order iJ.2  2. The off-diagonal blocks are
zeros except their first rows. This state equation is a generalization of the state equation in
(7.9) to two-input two-output transfer matrices. We can easiiy show that (7.104) is always
controllable and is  called a controllable-form realization.  Furthermore, the controllability
indices are iJ.I  =  4 and iJ.2 =  2.  As in (7.9), the state equation in (7.104) is observable if
and only if D(s) and N(s) are right coprime. For its proof, see Reference [6, p. 282]. Because
I
we start with a coprime fraction N(s)D- , the realization in (7.104) is observable as well. In
conclusion, the realization in (7.104) is controllable and observable and its dimension equals
+
iJ.I  iJ.2 and. following Theorem 7.M4, the degree of G(s). This establishes the second part
of Theorem 7.M2, namely, a state equation is minimal or controllable and observable if and
only if its dimension equals the degree of its transfer matrix.
EXAMPLE 7.8  Consider the transfer matrix in Example 7.6. We gave there a minimal realiza
tion that is obtained by reducing the nonminimal realization in (4.39). Now we will develop
directly a minimal realization by using a coprime fraction. We first write the transfer matrix as

224 MINIMAL REALIZATIONS AND COPRIME FRACTIONS
10 3]
45 -
t !
G(s) = 2s I ~ ~ =; G(oo) + G,p(s)
[
+ + +
(2s I)(s 2) (s 2)~ !
I
[~ ~] ! ~ 7]
= + [ 2S 1
I
+ + +
(2s 1)(5 2) (5 2)~
As in Example 7.7. we can find a right coprime fraction for the strictly proper part of G(s) as
G s =[-65 -12 -9][S2+ 2 .5S + 1 25+1]-1
,p( ) 0.5 I; 0 s + 2
Note that its denominator matrix is the same as the one in (7.86). Clearly we have {ll = 2 and
{l~ = I. We define
[i
:J
0]
S2
H(s) = [ 0 s L(5) =
Then we have
1 2] [2.5 1 I]
[
= +
D(s) 0 1 H(s) 0 0 2 L (s)
and
-6 -12 -9]
N(s) = [ 0 0.5 I L(s)
We compute
and
[1 -2] [2.5 [2.5 -3]
=
D-1D 1 1 ] = I
he Ie 0 I 0 o 2 0 0 2
Thus a minimal realization of G(s) is
-']
-2.5 -I 3
0 0
x=
.+ [:
.:. u
(7.105)
0 0 -2
[ -6 -12 ~9]x+[~ ~]
Y=
u
0 0.5

,
.,
222  MINIMAL REALIZATIONS AND COPRIME FRACTIONS
+
This state vector has dimension iLl  iLz = 6. These definitions imply immediately
(7.96)
xs.
Next we use (7.93) to develop equations for XI  and  First we express D(s) as
=
|     |     | D(s)  | DhcH(S)  |     | + DlcL(s)  |     |     | (7.97)  |
| --- | --- | ----- | -------- | --- | ---------- | --- | --- | ------- |
where H(s) and L(s) are defined in (7.91) and (7.92). Note that Dhe  and Dlc are constant
matrices and the column-degree coefficient matrix  Dhc  is  a unit upper triangular matrix.
Substituting (7.97) into (7.93) yields
|     |     | [DheH(S)  | +   | DleL(S»)v(s) = u(s)  |     |     |     |     |
| --- | --- | --------- | --- | -------------------- | --- | --- | --- | --- |
or
|     | H(s)v(s)  |     | +  Di.":DleL(s)v(s) = DheIU(S)  |     |     |     |     |     |
| --- | --------- | --- | ------------------------------- | --- | --- | --- | --- | --- |
Thus we have, using (7.95)"
|     | H(s)v(s) = -DheIDleX(S)  |     |     |     | +   | Dh:u(s)  |     | (7.98)  |
| --- | ------------------------ | --- | --- | --- | --- | -------- | --- | ------- |
Let
|       |     |          | al12  | a1l3  | a1l4  | alZI  |     |         |
| ----- | --- | -------- | ----- | ----- | ----- | ----- | --- | ------- |
| D-ID  | _   | . [alii  |       |       |       |       |     | (7.99)  |
he  le-'
|     |     | aZll  | a21Z  | aZI3  | aZI4  | aZ21  |     |     |
| --- | --- | ----- | ----- | ----- | ----- | ----- | --- | --- |
and
b;z]
|     |     |     | l   | [~  |     |     |     | (7.100)  |
| --- | --- | --- | --- | --- | --- | --- | --- | -------- |
|     |     |     | Dhc | =:  |     |     |     |          |
Note that the inv.~rse ,of a unit' upper triangular matrix is again a unit upper triangular matrix.
vz
Substituting (7.99) and (7.100) into (7.98), and using SXI (s)  =  S'VI (s), and s_is(s)  =
S2 (s),
we find
|             |     |           | al12  | a1l3  | al14  | al2l  |          |     |
| ----------- | --- | --------- | ----- | ----- | ----- | ----- | -------- | --- |
| [S~I(S)] =  |     | _  [alii  |       |       |       |       | am]X(S)  |     |
| SX5(S)      |     |           |       | aZI3  | al14  | a2Z1  | a2lZ     |     |
|             |     | aZll      | aZIZ  |       |       |       |          |     |
b;z]
[~
|     |     | +   |     | u(s)  |     |     |     |     |
| --- | --- | --- | --- | ----- | --- | --- | --- | --- |
which becomes, in the time domain.
[I  b;z] u
|           |     | all2  | al13  | al14  | <XIZI  |         |     |          |
| --------- | --- | ----- | ----- | ----- | ------ | ------- | --- | -------- |
| [~I] = _  |     |       |       |       |        | am] x+  |     | (7.101)  |
[alii
|     |       |       | a2I3  |       | a 221  | aZ22  | 0   |     |
| --- | ----- | ----- | ----- | ----- | ------ | ----- | --- | --- |
| Xs  | aZll  | a212  |       | aZ14  |        |       |     |     |
I
1[(;(s) =  N(s)D- (s) is strictly proper, then the column degrees of N(s) are less than the
corresponding column degrees of D(s). Thus we can express N(s) as
N(s) =  [tilll  tim  till 3  til14  tim  ti122]L(S)  (7.102)
|     |     |        |        | ti213  |        | ti221  | ti222  |     |
| --- | --- | ------ | ------ | ------ | ------ | ------ | ------ | --- |
|     |     | ti211  | I3zIZ  |        | tiZI4  |        |        |     |

7.10 Realizations from Matrix ,\\arkov Parameters 225
This A-matrix has two companion-form diagonal blocks: one \Iith order 2 and the other
order I. This three-dimensional realization is a minimal realization and is in controllable
canonical foml.
Dual to the preceding minimal realization, if we use C(s) = 0-1 (s)N(s). where Den
and 1'11(5) are left coprime and 0(5) is in row echelon form with row degrees {v,. i =
1.2, .... q). then we can obtain an observable-form realization with observability indices
{v,. i = I. 2 ..... q). This wi II not be repeated.
We summarize the main results in the following. As in the SISO case. an n-dimensional
multivariable state equation is controllable and observable if its transfer matrix has degree 11. If
a proper transfer matrix is expressed as a right coprime fraction with column reducedness. then
the realization obtained by using the preceding procedure will automatically be controllable
and observable.
= =
Let (A. B. C. D) be a minimal realization of C(5) and let (;(5) D-I(s)N(s)
N(s)D-1 (s) be coprime fractions; D(s) is row reduced, and D(s) is column reduced. Then
we have
which implies
. I
---::------:-B[Adj(sl - A)]C + D = N(s)[Adj(D(s»]
det(sl - A) det D(s)
1 --
= _ [Adj(D(s))]N(s)
det D(s)
Because the three polynomials det (51 - A), det D(s), and det 0 (5) have the same degree.
they must denote the same polynomial except possibly different leading coefficients. Thus we
conclude the following:
= =
• deg (;(5) deg det D(s) deg det 0(5) = dim A.
=
• The characteristic polynomial of (;(s) kl det D(s) = k2 det D(s) = kJ det (5 I - A) fOI
some nonzero constant k,.
• The set of column degrees of D(s) equals the set of controllability indices of (A. B).
0(.»
• The set of row degrees of equals the set of observability indices of (A. C).
We see that coprime fractions and controllable and observable state equations contain essen
tially the same information. Thus either description can be used in analysis and design.
7,10 Realizations from Matrix Markov Parameters
Consider a q x p strictly proper rational matrix G(s). We expand it as
(;(s) = H( I )s- I + H(2)s-2 + H(3)s-J + ... (7106

228 MINIM"'L REALIZATIONS AND COPRL'v\E FRACTIONS
and observability conditions can also be expressed in terms of coprimeness conditions. See
References [4, 6, 13.20]. The objectives of this chapter are ro discuss a numerical merhod ro
compute coprime fracrions and to introduce just enough background to carry our designs in
Chapter 9.
In addition to polynomial fracrions, it is possible to express transfer functions as stable
rational function fractions. See References [9, 21]. Stable rational function fracrions can be
developed without discussing polynomial fractions; however, polynomial fractions can provide
an efficient way of computing rational fractions. Thus rhis chapter is also useful in studying
rational fractions.
7.1 Given
PROBLEMS
5 -1
g
(s) - -"------'0-
+
- (5' - I) (s 2)
find a three-dimensional controllable realization. Check its observability.
7.2 Find a three-dimensional observable realization for the transfer function in Problem 7.1.
Check its controllability.
7.3 Find an uncontrollable and unobservable realization for the transfer function in Problem
7.1. Find also a minimal realization.
7.4 Use the Sylvester resultant to find the degree of the transfer function in Problem 7.1.
7.5 Use the Sylvester resultant to reduce (2s - 1)/(45' - I) to a coprime fraction.
7.6 Form the Sylvester resultant of 8(5) = (s + 2)/(5 2 + 25) by arranging the coefficients of
N (5) and Dis) in descending powers of 5 and then search linearly independent columns
in order from left to right. Is it true that all D-columns are linearly independent of their
LHS columns? Is it true that the degree of g(s) equals the number oflinearly independent
N-columns?
7.7 Consider
{3IS+{3, !v(s)
8(5 ) = 5' ~ (tIS + Ct2 D(s)
and its realization
[I]
. [-Ctl
x = -Ct2] x + u y = [{31 ,8,]x
I 0 0
Show that the state equation is observable if and only if rhe Sylvester resultant of D(s)
and N (s) is nonsingular.
7.8 Repeat Problem 7.7 for a transfer function of degree 3 and its controllable-form realiza
rion.
= +
7.9 Verify Theorem 7.7 for 8(5) I/(s 1)2.

Chapter
···"~·· ·
C.'.
.•..
"11
.
;,
State Feedback
and State Estimators
8,1 Introduction
The concepts of controllability and observability were used in the preceding two chapters to
study the internal structure of systems and to establish the relationships between the internal
and external descriptions. Now we discuss their implications in the design of feedback control
systems.
Most control systems can be formulated as shown in Fig. 8.1, in which the plant and
the reference signal r(t) are given. The input u(t) of the plant is called the actuating signal
or control signal. The output y(t) of the plant is called the plant output or controlled signal.
The problem is to design an overall system so that the plant output will follow as closely as
possible the reference signal rtf)· There are two types of control. If the actuating signal u(t)
depends only on the reference signal and is independent of the plant output, the control is
called an open-loop control. If the actuating signal depends on both the reference signal and
the plant output. the control is called a closed-loop orfeedback control. The open-loop control
is, in general, not satisfactory if there are plant parameter variations and/or there are noise
and disturbance around the system. A properly designed feedback system. on the other hand,
-------------------,
Figure 8.1 Design of control systems.
~ ~
r 1
-I Plant
1
1
L _____ _
231

Problems 229
+
7.10 Use the Markov parameters of g(s) = I/(s I)" to find an irreducible companion-form
realization.
+
7.11 Use the Markov parameters of g(s) = I/(s I)" to find an irreducible balanced-form
realization.
7.12 Show that the two state equations
x=[~ :]x+[~]u y = [2 2]x
and
x=[
2 O]x+[I]u v= O]x
[2
-I -I 2
are realizations of (2s + 2)/(S2 - S - 2). Are they minimal realizations? Are they
algebraically equivalent?
7.13 Find the characteristic polynomials and degrees[ of tIhe f ollowing propIer rat]ional matrices
I
[~ S+3] + +
s ~ I (h(s) = (s ~ 1)2 (s I)? 2)
G1(s) =
s+3 s+1 s+2 (s+I)(s+2)
and
s+3
~ ~
'is]
s+2
G,C<) [ (, I)'
s+1
(s+3)" s+4
Note that each entry of G)(s) has different poles from other entries.
;r
7.14 Use the left fraction
[~s [~I]
G(s) =
to form a generalized resultant as in (7.83), and then search its linearly independent
columns in order from left to right. What is the number of linearly independent N
columns? What is the degree of GCs J? Find a right coprime fraction of G(s). Is the given
left fraction coprime0
7.15 Are all D-columns in the generalized resultant in Problem 7.14 linearly independent of
their LHS columns? Now in forming the generalized resultant, the coefficient matrices of
D(s) and N (s) are arranged in descending powers of s. instead of ascending powers of
s as in Problem 7.14. Is it true that all D-columns are linearly independent of their LHS
columns? Does the degree of G(s) equal the number of linearly independent N-columns?
Does Theorem 7.M4 hold?

230 MINIMAL REALIZATIONS AND COPRIME FRACTIONS
7.16 Use the right coprime fraction of G(s) obtained in Problem 7.14 to form a generalized
resultant as in (7.89), search its linearly independent rows in order from top to bottom,
and then find a left coprime fraction of G(s).
7.17 Find a right coprime fraction of
s2 + I
2s~1
• 3 S2
G(s) = s
s+2 2
[
s2 s
and then a minimal realization.
,
I

232 STATE FEEDBACK A,'.; 0 STATE ESTIMP,TORS
can reduce the effect of parameter variations and suppress noise and disturbance. Therefore
feedback control is more widely used in practice.
This chapter studies designs using state-space equations. Designs using coprime fractions
will be studied in the next chapter. We study Ii rst single-variable systems and then multi variable
systems. We study only linear time-invariant systems.
8.2 State Feedback
Consider the II-dimensional single-variable state equation
x +
= Ax bit
(81)
.
\" = cx
.
where we ha\·e assumed d = 0 to simplify discussion. [n state feedback. the input u is given by
L"
/I = r - kx = r - [k[ k2 ... k" Jx = r - k,Xi (8.2)
i=]
as shown in Fig. 8.2. Each feedback gain k, is a real constant. This is called the COllstallt gail1
Ilegatil·e state feedback or. simply. state feedback. Substituting (8.2) into (8.1) yields
x = (A - bk)x + br
(8.3)
\. = ex
Theorem 8.1
The pair !A - bk. b). for any I x 11 real constant vector k. is controllable if and only if (A. b) is
controllable.
-1
Proof· We show the theorem for 11 = 4. Define
C = [b Ab A~b A 3 b]
and
C = [b (A - bk)b (A - bk)Cb (A - bk)Jb]
f
They are the controllability matrices of 18.1) and (8.3). It is straightforward to verify
r- - --------------- I
+ Figure 8.2 State kedbacK.
III x x \
"}----j b ~
-'
A
L- I k

|     |     |     |     |     | 8.2  State Feedback  |     | 235  |
| --- | --- | --- | --- | --- | -------------------- | --- | ---- |
into the controllable canonical form
-;4]-
|     |     |     | -a  | -0!2  -C¥3  |      |     |     |
| --- | --- | --- | --- | ----------- | ---- | --- | --- |
|     |     |     |     | l           | [~]  |     |     |
o
|     | .             | - - | 1   | 0     |         |     |        |
| --- | ------------- | --- | --- | ----- | ------- | --- | ------ |
|     | x  = Ai+bu =  |     | ~   |       | o  x +  |     |        |
|     |               |     |     | 1  0  | 0       | u   |        |
|     |               |     | [   |       |         |     | (8.7)  |
|     |               |     |     | o     | o       |     |        |
0
|     |     | ex  [I'll  | tl2  tl3  tl41i  |     |     |     |     |
| --- | --- | ---------- | ---------------- | --- | --- | --- | --- |
y =  =
Furthermore. the transfer function of (8.1) with n = 4 equals
|     |     | • ( )  | I'll S3 + tl2s2 + tl3s + tl4  |     |     |     |     |
| --- | --- | ------ | ----------------------------- | --- | --- | --- | --- |
=
|     |     | gs  |     | 3 + a2s2 + a3S + a4  |     |     | (S.S)  |
| --- | --- | --- | --- | -------------------- | --- | --- | ------ |
S4 + als
EI  Proof:
Let C and C be the controllability matrices of (8.1) and (8.7). In the SISO case,
both C and C are square. If (8.1) is controllable or C is nonsingular, so is C. And they
are related by C = PC (Theorem 6.2 and Equation (6.20)). Thus we have
|     |     |      | I   |            | I  I   |     |     |
| --- | --- | ---- | --- | ---------- | ------ | --- | --- |
|     |     | P =  | CC- | or  Q:= p- | =  CC- |     |     |
The controllability matrix C of (8.7) was computed in (7.10). Its inverse turns out to be
|     |     |     |      | 1  al  |      |     |        |
| --- | --- | --- | ---- | ------ | ---- | --- | ------ |
|     |     |     |      | az     | a3]  |     |        |
|     |     |     |      | al     | a2   |     |        |
|     |     |     | C-I  | ~      |      |     |        |
|     |     |     | =    | 0      |      |     | (8.9)  |
al
[
|     |     |     |     | o  0  o  |     |     |     |
| --- | --- | --- | --- | -------- | --- | --- | --- |
1
This can be verified by multiplying (8.9) with (7.10) to yield a unit matrix. Note that the
constant term a4 of (8.5) does not appear in (8.9). Substituting (8.9) into Q =  I
|     |     |     |     |     |     | C C- | yields  |
| --- | --- | --- | --- | --- | --- | ---- | ------- |
(8.6). As shown in Section 7.2, the state equation in (8.7) is a realization of (8.8). Thus
the transfer function of (8.7) and, consequently, of (8.1) equals (8.8). This establishes the
| theorem.  | Q.E.D.  |     |     |     |     |     |     |
| --------- | ------- | --- | --- | --- | --- | --- | --- |
With this theorem, we are ready to discuss eigenvalue assignment by state feedback.
Theorem 8.3
~
=
If the n-dimensional state equation in (S.l) is controllable, then by state feedback u  r - kx. where
bk can arbitrarily be assigned provided that
k is a 1 x n real constant vector, the eigenvalues of A -
complex conjugate eigenvalues are assigned in pairs.
=
II  Proof:  We again prove the theorem for n  4. If (8.1) is controllable, it can be transformed
into the controllable canonical form in (8.7). Let A and b denote the matrices in (8.7).
| Then we have A =  |     | PAP-I and b =  |     |                   | x                              |     |     |
| ----------------- | --- | -------------- | --- | ----------------- | ------------------------------ | --- | --- |
|                   |     |                |     | Pb. Substituting  | =  Px into the state feedback  |     |     |
yields
kx
|     |     | u = r  | - kx = r - | kP-lx =: r - |     |     |     |
| --- | --- | ------ | ---------- | ------------ | --- | --- | --- |
|     | I   |        | bk         |              |     | bk  |     |
where  k  := kP- . Because  A - = P(A - bk)p-I, A - bk and  A - have the same
set of eigenvalues. From any set of desired eigenvalues, we can readily form

8.2 State Feedback 233
1
-kb -k(A - bk)h
.k( A - bk)'b
I -kb -k(A - bk)b
C, " C [; (84)
. 0
0 I -kb
0 0 0 I
Note that k is I x 11 and b is II X I. Thus kb is scalar: so is every entry in the rightlllost
matrix in (8.4). Because the rightmost matrix is nonsingular for any k. the rank of C]
equals the rank of C. Thus (8.3) is controllable if and only if 18.1) is controllable.
This theorem can also. be established directly from the definition of controllability.
Let Xo and XI be two arbitrary states. h(S.I) is controllable. there exists an input III that
transfers Xl) to XI in a finite time. Now if we choose rl = III + kx. then the input rl of the
state feedback system will transfer XI) to XI. Thus \\ e conclude that if (S.I) is controllable.
so is (8.3).
We see from Fig. 8.2 that the input r does not control the state x directly: it generates
to control x. Therefore. if II cannnot control x. neither can r. This establishes once again
1I
the theorem. Q.E.D.
Although the controllability property is invariant under any state feedback. the observ
ability property is not. This is demonstrated by the example that follows.
EXAMPLE 8.1 Consider the state equation
x=[~ ~]X+[~]II
r=[12Jx
The state equation can readily be shown to be controllable and observable. Now we introduce
the state feedback
lI=r-[311x
Then the state feedback equation becomes
x=[~ ~Jx+[~Jr
r=[12Jx
Its controllability matrix is
0 2]
[
r
C = I 0
which is nonsingular. Thus the state feedback equation is controllable. Its observability matri\ is
0- [I 2]
=
J I 2
which is singular. Thus the state feedback equation is not observable. The reason that the
observability property may not be preserved in state feedback will be given later.

234  STATE FEEDBACK AND STATE ESTIMATORS
We use an example to discuss what can be achieved by state feedback.
|     | EXAMPLE  8.2  | Consider a plant described by  |     |     |     |     |     |     |     |     |     |     |
| --- | ------------- | ------------------------------ | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
~~
|     |     |     |     |     | x=[~  | ~]X+[~]U  |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | ----- | --------- | --- | --- | --- | --- | --- | --- |
;'.1
"
~"  The A-matrix has characteristic polynomial
'"
|     |     |       | =   |      |       | =       |      | =       |       |        |     |     |
| --- | --- | ----- | --- | ---- | ----- | ------- | ---- | ------- | ----- | ------ | --- | --- |
| \"  |     | 6(S)  |     | (S - | 1)2 - | 9  S2 - | 2s - | 8  (S - | 4)(s  | +  2)  |     |     |
and,  consequently, eigenvalues 4 and  -2. It is  unstable.  Let us  introduce state feedback
~~.  =
|     | u  r - [k,  | kz]x. Then the state feedback system is described by  |     |     |     |     |     |     |     |     |     |     |
| --- | ----------- | ----------------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
t:
|     |     |     | x=([~  |     | ~j-[~  |     | ~])x+[~]r  |     |     |     |     |     |
| --- | --- | --- | ------ | --- | ------ | --- | ---------- | --- | --- | --- | --- | --- |
'"
;.'
| ~ .'"'    |     |     |     | =   | ~   | ~          | + [~J  |     |     |     |     |     |
| --------- | --- | --- | --- | --- | --- | ---------- | ------ | --- | --- | --- | --- | --- |
|           |     |     |     | [1  | k,  | 3  k2 ] X  |        | r   |     |     |     |     |
~~
:~
~ This new A-matrix has characteristic polynomial
.~
"
| "    |     |     |        | =   |      |           |     |       |      |     |     |     |
| ---- | --- | --- | ------ | --- | ---- | --------- | --- | ----- | ---- | --- | --- | --- |
| ,'.  |     |     |        |     |      | 1+ kd(s - |     | 3(3 - |      |     |     |     |
|      |     |     | 6/(S)  |     | (s - |           |     | I) -  | k2)  |     |     |     |
:'1
|     |     |     |     | = s2  | +   |       | +    |         |       | 8)  |     |     |
| --- | --- | --- | --- | ----- | --- | ----- | ---- | ------- | ----- | --- | --- | --- |
|     |     |     |     |       |     | (k, - | 2)s  | (3k 2 - | k,  - |     |     |     |
It is clear that the roots of 6/ (s)  or, equivalently,  the eigenvalues of the state feedback
system can be placed in any positions by selecting appropriate k,  and k 2. For example, if
the two eigenvalues are to be placed at -I ± )2, then the desired characteristic polynomial is
|     | +  +  | +   |     | +   | +   |     |     |     |     |     | =   |     |
| --- | ----- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
(s  I  )2)(s  I - )2) = s2  2s  5. Equating k, - 2 = 2 and 3k 2 - k, - 8  5 yields
= 4 and k2 =
k,  17/3. Thus the state feedback gain [4  17/3] will shift the eigenvalues from
4,-2to-l±)2.
This example shows that state feedback can be used to place eigenvalues in any positions.
Moreover the feedback gain can be computed by direct substitution. This approach, however,
will become very involved for three- or higher-dimensional state equations. More seriously.
the approach will not reveal how the controllability condition comes into the design. Therefore
a more systematic approach is desirable. Before proceeding, we need the following theorem.
We state the theorem for n = 4; the theorem. however. holds for every positive integer n.
>-
Theorem 8.2
Consider the state equation in (8.1) with n = 4 and the characteristic polynomial
|     |     |                  |     |     |     | =  4 +  | J    |  +       | +    | +   |     |        |
| --- | --- | ---------------- | --- | --- | --- | ------- | ---- | -------- | ---- | --- | --- | ------ |
|     |     | 6(s) = det (sl - |     |     | A)  | s       | atS' |   azs-0  | aJs  | a.  |     | (8.5)  |
x =
If (8.1) is controllable. then it can be transformed by the transformation  Px with
|     |     |     |     |     |     |     |     | la,  | a2  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ---- | --- | --- | --- | --- |
3
a,
aa2
|     |     | Q := P-'  |     | =   | [b Ab A2b  |     | A3b]  | 0   |     | ]   |     |        |
| --- | --- | --------- | --- | --- | ---------- | --- | ----- | --- | --- | --- | --- | ------ |
|     |     |           |     |     |            |     |       | o   |     |     |     | (8.6)  |
|     |     |           |     |     |            |     |       | 0   | 1   | a,  |     |        |
[
o
|     |     |     |     |     |     |     |     | 0   | 0   | 1   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

236  STATE FEEDBACK AND STATE ESTIMATORS
|     |     |     |               |     | 4 +  | - J +  | -       | +      | +    |         |
| --- | --- | --- | ------------- | --- | ---- | ------ | ------- | ------ | ---- | ------- |
|     |     |     | L'l.f(S) = S  |     |      | a ls   | a "s-1  | a- )s  | a-4  | (8.10)  |
If k is chosen as
|     |     |     | k =  | [al - | al  | a2-, a"  | a) - | a3  a. - | a4]  | (8.11 )  |
| --- | --- | --- | ---- | ----- | --- | -------- | ---- | -------- | ---- | -------- |
the state feedback equation becomes
-a
|     |     |     |     |     |     |     | -a"  | -a3  |     |     |
| --- | --- | --- | --- | --- | --- | --- | ---- | ---- | --- | --- |
l
|     |     |     |     |     |     |     | o   |     | T]i+[~l  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | -------- | --- |
0
|     | x   | (A - |       | + br  |     |     |     |     |     |         |
| --- | --- | ---- | ----- | ----- | --- | --- | --- | --- | --- | ------- |
|     | =   |      | bk)x  |       | =   | :   |     |     |     |         |
|     |     |      |       |       |     |     | 1   | 0   |     |         |
|     |     |      |       |       | [   |     |     |     |     | (8.12)  |
o
fh  fh
|     | y = [,81  |     |     | i'l.]x  |     |     |     |     |     |     |
| --- | --------- | --- | --- | ------- | --- | --- | --- | --- | --- | --- |
Because of the companion form, the characteristic polynomial of (A - bk) and, conse
quently, of (A - bk) equals (8.10). Thus the state feedback equation has the set of desired
eigenvalues. The feedback gain k can be computed from
|                    |     |      |                  |     |      | kP            | kcel  |        |         |         |
| ------------------ | --- | ---- | ---------------- | --- | ---- | ------------- | ----- | ------ | ------- | ------- |
|                    |     |      |                  |     | k =  |               | =     |        |         | (8.13)  |
|                    |     | C-I  |                  |     |      | =  [b Ab A2b  |       | A3b].  |         |         |
| with k in (8.11),  |     |      | in (8.9), and C  |     |      |               |       |        | Q.E.D.  |         |
We give an alternative derivation of the formula in (8.11). We compute
|     | L'l.f | (s) = det (sl - |     | A   | +  bk) = det  |     | (sl - | A)[I  | +  (sl - A)-Ibkl)  |     |
| --- | ----- | --------------- | --- | --- | ------------- | --- | ----- | ----- | ------------------ | --- |
+
|     |     | = det (sl - |     | A)det [I  |     | (sl - | A)-Ibk]  |     |     |     |
| --- | --- | ----------- | --- | --------- | --- | ----- | -------- | --- | --- | --- |
which becomes, using (8.5) and (3.64),
+
|     |     |     |     | L'l.f(s) =  | L'l.(s)[1  |     | k(sI - | A)-Ib]  |     |     |
| --- | --- | --- | --- | ----------- | ---------- | --- | ------ | ------- | --- | --- |
Thus we have
|     |     |     |     | =   |     |     |     | =   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
L'l.f(S) - L'l.(s)  L'l.(s)k(sI - AJ-Ib  L'l.(s)k(sl - A)-Ib  (8.14)
Let  z be the output of the feedback gain shown in Fig. 8.2 and let k =  [k k2  k3  k.J.  Because
l
the transfer function from u to y in Fig. 8.2 equals
|     |     |     |          |           |     |        | 3 +   | '    | R       |     |
| --- | --- | --- | -------- | --------- | --- | ------ | ----- | ---- | ------- | --- |
|     |     |     | (,(sl _  | A)-Ii) =  |     | i'lIS  | i'l:s | - +  | S +     |     |
|     |     |     |          |           |     |        |       | i'l3 | f -' 4  |     |
L'l.(s)
the transfer function from u to z should equal
|     |     |     |         |      |      | -                          | 3 + -., + - |      | + - |         |
| --- | --- | --- | ------- | ---- | ---- | -------------------------- | ----------- | ---- | --- | ------- |
|     |     |     | -       | -    | 1-   | kls                        | k,s-        | k3S  | k.  |         |
|     |     |     | k(s I - | A) - | b =  | -c-__- =-:---c--,----'--_  |             |      |     | (8.15)  |
L'l. (s)
Substituting (8.15), (8.5), and (8.10) into (8.14) yields
| -   |     | 3 +  | -   | ,+-  |     |     | +  - |     | -3 + -2 + - | + - |
| --- | --- | ---- | --- | ---- | --- | --- | ---- | --- | ----------- | --- |
(al - al)s  (a2 - (2)s- (a3 - aJ)s  (a. - (4) = kls  k2s  k3S  k4
This yields (8.11).

8.2 State Feedback 239
1m s 1m:
?')I Re s 1 I ~ I ') ~ ?A , Re::
c
"
(a) (b)
Figure 8.3 Desired eigenvalue location.
See Reference [I]. However, selecting Q and R requires trial and error. In conclusion. how to
select a set of desired eigenvalues is not a simple problem.
We mention that Theorems 8.1 through 8.3-in fact. all theorems to be introduced later
in this chapter-apply to the discrete-time case without any modification. The only difference
is that the region in Fig. 8.3(a) must be replaced by the one in Fig. 8.3(b). which is obtained
by the transformation: = eS
•
8.2.1 Solving the Lyopunov Equation
This subsection discusses a different method of computing state feedback gain for eigenvalue
assignment. The method. however, has the restriction that the selected eigenvalues cannot
contain any eigenvalues of A.
>
Procedure 8.1
Consider controllable (A. bl. where A is n x n and b is n x I. Find a I x n real k such that (A - bk)
has any set of desired eigenvalues that contains no eigenvalues of A.
1. Select an n X n matrix F that has the set of desired eigenvalues. The form of F can be chosen arbitrarily
and wi II be discussed later.
2. Select an arbitrary I x 11 vector k such that (F. k) is observable.
= hk.
3. Solve the unique T in the Lyapunov equation AT - TF
4. Compute the feedback gain k = kT-1 •
We justify first the procedure. 1fT is nonsingular, then k = kT and the Lyapunov equation
=
AT - TF bk implies
(A - bk)T = TF or A - bk = TFrl
Thus (A - bk) and T are similar and have the same set of eigenvalues. Thus the eigenvalues
of (A - bk) can be assigned arbitrarily except those of A. As discussed in Section 3.7, if A and

8.2 State Feedback  237
Feedback transfer function  Consider a plant described by tA. b. c). If (A. b) is controllable.
(A. b. c) can be transformed into the controllable form in (8.7) and its transfer function can
then be read out as. for n = 4.
3
|     |     |     | /3IS | + /32s~ +  | /335 + /3 ..  |     |
| --- | --- | --- | ---- | ---------- | ------------- | --- |
g(s) = c(sl _ A)-lb =
(816)
.
|     |     |     | s-l+als3 | +a2s~+a3s+a-l  |     |     |
| --- | --- | --- | -------- | -------------- | --- | --- |
After state feedback. the state equation becomes (A - bk. b. c) and is still of the controlbblc
canonical form as shown in (8.12). Thus the feedback transfer function from r  to y is
|     | ~  (s) = c(51 _ A + bk)-lb =  |     |     | /3IS' + fh~2 + /3ls + /3.  |     |     |
| --- | ----------------------------- | --- | --- | -------------------------- | --- | --- |
(8.17)
|     | gr  | .   | -l  | - 1   + a2S-, | -  a,s + a- |     |
| --- | --- | --- | --- | ------------- | ----------- | --- |
|     |     |     | 5   | + a lSO       | +           | .   |
We see that the numerators of (8.16) and (8.17) are the same. In other words. state feedback
does not affect the zeros of the plant transfer function. This is actually a general propeny of
feedback:feedhack can shift the poles of a plallt but has 170 effect on the :erus. This can be used
to explain hy a state feedback may alter the observability propeny of a state quation. If one or
more poles are shifted to coincide with zeros of g(s). then the numerator and denominator of
gj(s) in (8.17) are not coprime. Thus the state equation in (8.12) and. equivalently, (A - bk.  C)
are not observable (Theorem 7.1).
EXAMPLE 8.3  Consider the inverted pendulum studied in Example 6.2. Its state equation is.
;,   as derived in (6.11).
| l   |     |       | o      |     |     |     |
| --- | --- | ----- | ------ | --- | --- | --- |
| .~  |     | 0  I  | l]HUJ  |     |     |     |
-I
x =  ~  ~
o
[ (8.1 S)
|     |     | o  0  | 5   |     |     |     |
| --- | --- | ----- | --- | --- | --- | --- |
.\·=[IOOOlx
j  It is controllable; thus its ei~en\'alues can be assi~ned arbitrarilv. Because the A-matrix is block
j  triangular, its characteristi: polynomial can be ~btained by in~pection as
.,
..i
|     |        | .,  " )     | .J     | 3  -:,~,-, +O |        |     |
| --- | ------ | ----------- | ------ | ------------- | ------ | --- |
|     | 6(s)=s | -( r -5)=s  | + O·s  |               | 's +O  |     |
1
First we compute P that will transform (8.18) into the controllable canonical form. Using (8.61.
~
we have
o
|     |     | I   |     |        | -5       |      |
| --- | --- | --- | --- | ------ | -------- | ---- |
|     |     | 1   |     | 2] [\  | 0        |      |
|     |     | o   |     | o      | 0  I  o  | -~]  |
')
|     | p-l =  CC-l  =  | [   |     |     |     |     |
| --- | --------------- | --- | --- | --- | --- | --- |
o
|     |     | -2  |      | -\0  | 0  0  \  |     |
| --- | --- | --- | ---- | ---- | -------- | --- |
|     |     | o   |      |      | o        |     |
|     |     | -2  | -10  | 000  |          |     |
o
I  n
|     | [1,  o  |     |     |     |     |     |
| --- | ------- | --- | --- | --- | --- | --- |
-3
-2  o
o  o
.',
j  Its inverse is

238  STATE FEEDBACK AND STATE ESTIMATORS
| "     |     |     |     |     | o   | o   | o   | 1   |     |     |
| ----- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| :>~   |     |     |     |     |     |     |     | -2  |     |     |
| ,j    |     |     |     |     |     |     |     | o   |     |     |
| :'-1  |     |     |     |     | o   | o   | I   |     |     |     |
-2
p=
| .~'!  |     |     |     |     | o   | -5  |     |      |     |     |
| ----- | --- | --- | --- | --- | --- | --- | --- | ---- | --- | --- |
|       |     |     |     |     |     |     | 0   | 1    |     |     |
|       |     |     |     |     |     |     |     | -6   |     |     |
1
| 6~, 4   |     |     |     |     |     |     |     | o   |     |     |
| ------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|         |     |     |     |     | -~  | 0   | -~  |     |     |     |
~  Let the desired eigenvalues be -1.S ± O.S j  and -1 ± j. Then we have
;J
| #   |     |         | =     |       |            |                  |     |             |          |     |
| --- | --- | ------- | ----- | ----- | ---------- | ---------------- | --- | ----------- | -------- | --- |
|     |     | f>j(S)  | (s +  | 1.S - | O.Sj)(s +  | 1.5 + O.Sj)(s +  |     | 1 - j)(s +  | 1 +  j)  |     |
~
'.'
~
| ~   |     |     | =S4+Ss3+ 10.SS2+ Ils+S  |     |     |     |     |     |     |     |
| --- | --- | --- | ----------------------- | --- | --- | --- | --- | --- | --- | --- |
~
Thus we have, using (8.11),
~
| •~   |     |     |      | °             |     |     |           |           |         |     |
| ---- | --- | --- | ---- | ------------- | --- | --- | --------- | --------- | ------- | --- |
|      |     |     | k =  |               |     |     |           | =         |         |     |
|      |     |     | [5 - | 105 + 5/ II - |     |     | 0 5 - OJ  | [5  IS.S  | 11  SJ  |     |
~
d
•~   ~
| .,  |     |     |     | = kP  |       |     |        |     |     |         |
| --- | --- | --- | --- | ----- | ----- | --- | ------ | --- | --- | ------- |
|     |     |     |     | k     | =     |     | 11  -  | U]  |     |         |
| "   |     |     |     |       | [-~3  | -   | 103    | -   |     | (8.19)  |
| 4   |     |     |     |       |       |     | 3  12  | 3   |     |         |
| .~  |     |     |     |       |       |     |        |     | 0.  |         |
,;:~  This  state  feedback  gain  will  shift the  eigenvalues of the  plant from  10,  ±jv's} to
.<
.J  1-1.S±O.Sj.
-I±j}.
';.;J<
The MATLAB function place computes state feedback gains for eigenvalue placement
or assignment. For the example. we type
|     | a=[O 1'        | 0  0; | 0  0  | -1  0;0  | 0  0  1;0  | 0       | 5  0];b=[0;1;0;-2];  |     |     |     |
| --- | -------------- | ----- | ----- | -------- | ---------- | ------- | -------------------- | --- | --- | --- |
|     | p= [-1.5+0.Sj  |       | -1.   | S-0.Sj   | -l+j       | -l-j];  |                      |     |     |     |
k=p1ace(a,b,p)
which yields [-1.6667  - 3.6667  - 8.S833  - 4.3333]. This is the gain in (8.19).
One may wonder at this point how to select a set of desired eigenvalues. This depends
on the performance criteria, such as rise time, settling time. and overshoot. used in the design.
Because the response of a system depends not only on poles but also on zeros, the zeros of the
plant will also affect the selection. In addition. most physical systems will saturate or burn out if
the magnitude of the actuating signal is very large. This will again affect the selection of desired
poles. As a guide. we may place all eigenvalues inside the region denoted by C in Fig. 8.3(a).
The region is bounded on the right by a vertical line . The larger the distance of the vertical line
from the imaginary axis. the faster the response. The region is also bounded by two straight
lines emanating from the origin with angle (). The larger the angle. the larger the overshoot. See
Reference [7J. If we place all eigenvalues at one point or group them iii a very small region.
then usually the response will be slow and the actuating signal will be large. Therefore it is
better to place all eigenvalues evenly around a circle with radius r inside the sector as shown.
The larger the radius. the faster the response; however. the actuating signal will also be larger.
Furthermore. the bandwidth of the feedback system will be larger and the resulting system
will be more susceptible to noise. Therefore a final selection may involve compromises among
many conflicting requirements. One way to proceed is by computer simulation. Another way
is to find the state feedback gain k to minimize the quadratic performance index
1
00
|     |     |     |     | J =  |     |     | +  u'(t)Ru(t)] dt  |     |     |     |
| --- | --- | --- | --- | ---- | --- | --- | ------------------ | --- | --- | --- |
[x'(t)Qx(t)

240  STATE FEEDBACK AND STATE ESTlMI\TORS
F have no eigenvalues in common. then a solution T exists in AT - TF =  bk for any k and
is un~que. If A and F have common eigenvalues. a solution T mayor may not exist depending
on bk. To remove this uncertainty. we require A and F to have no eigenvalues in common.
What remains to be proved is the nonsingularity of T.
Theorem 8.4
If A and F have no eigenvalues in common. then the unique solution Tof AT - TF =  bk is nonsingular
k)
if and only if (A. b) is controllable and (F.  is observable .
....,  Proof;  We prove the theorem for n =  4. Let the characteristic polynomial of A be
|     | 6.(5) =  | + ctl~3 + ct2S2 + ct3S + ct4  |     |     | (8.20)  |
| --- | -------- | ----------------------------- | --- | --- | ------- |
,5'
Then we have
|     |       | 4   )  +ct2A1- +ct3A+ct4  |     | I  =0  |     |
| --- | ----- | ------------------------- | --- | ------ | --- |
|     | MA)=A |   +ctjA                   |     |        |     |
(Cayley-Hamilton theorem). Let us consider
|     | 6.(F) :=  | ~ + ctjF) + ct2F2 + ct)F + ct41  |     |     | (8.21)  |
| --- | --------- | -------------------------------- | --- | --- | ------- |
If).,i is an eigenvalue of F. then 6.().,;) is an eigenvalue of 6.(F) (Problem 3.19). Because
t=
A and F have no eigenvalues in common. we have 6.(),,;)  0 for all eigenvalues of F.
Because the determinant of a matrix equals the product of all its eigenvalues. we have
n
t=
|     |     | det 6.(F) =  | 6.(),,;)  0  |     |     |
| --- | --- | ------------ | ------------ | --- | --- |
Thus 6. (F) is nonsingular.
| Substituting AT" =  |        | TF + bk into A2T - | AF2 yields    |             |     |
| ------------------- | ------ | ------------------ | ------------- | ----------- | --- |
| A"T -               | TF" =  | A(TF + bk) -       | TF2 =  Ahk +  | (AT - TF)F  |     |
|                     |        | =  Abk+ bkF        |               |             |     |
Proceeding forward. we can obtain the following set of equations:
|     | IT -  | TI = 0            |     |     |     |
| --- | ----- | ----------------- | --- | --- | --- |
|     | AT -  | TF =  bk          |     |     |     |
|     | A"T - | TF2 =  Abk + bkF  |     |     |     |
AlT _ TFJ = A "bk + AbkF + bkF"
|     | A 4T - | TF4 =  Albk +  | A"bkF  +  AbkF" + bkF | J   |     |
| --- | ------ | -------------- | --------------------- | --- | --- |
We multiply the first equation by ct4. the second equation by ctl. the third equation by ctl.
the fourth equation by ct j. and the last equation by 1. and then sum them up. After some
manipulation. we finally obtain
|     | 6.(A)T - | T6.(F) =  -T6.(F)  |     |     |     |
| --- | -------- | ------------------ | --- | --- | --- |

8.3 Regulation and Tracking 243
(S) = yes) = ~ls3 + ~2s2 + fhs + ~4 (8.24)
gA l rA (s) P s 4 + £ - lIS 3 + £ - lzs1- + 0 - !3S + a- .
If (A, b) is controllable, all eigenvalues of (A - bk) or, equivalently, all poles of gl(s) can
be assigned arbitrarily, in particular, assigned to lie inside the sector in Fig. 8.3(a). Under this
assumption, if the reference input is a step function with magnitude a, then the output y(t)
will approach the constant gl(O) . a as t -+ 00 (Theorem 5.2). Thus in order for yet) to track
asymptotically any step reference input, we need
a4
= p~4
1= gl(O) or p = ~4 (8.25)
£l4
which requires ~4 f. O. From (8.16) and (8.17), we see that ~4 is the numerator constant term
of the plant transfer function. Thus ~4 f. 0 if and only if the plant transfer function g(s) has no
zero at s = O. In conclusion, if g(s) has one or more zeros at s = D, tracking is not possible.
If g(s) has no zero at s = D, we introduce a feedforward gain as in (8.25). Then the resulting
system will track asymptotically any step reference input.
We summarize the preceding discussion. Given (A, b, e); if (A, b) is controllable, we
may introduce state feedback to place the eigenvalues of (A - bk) in any desired positions and
the resulting system will achieve regulation. If (A, b) is controllable and if e(sI - A)-Ib has
no zero at s = 0, then after state feedback, we may introduce a feedforward gain as in (8.25).
Then the resulting system can track asymptotically any step reference input.
8.3.1 Robust Tracking and Disturbance Rejection'
The state equation and transfer function developed to describe a plant may change due to
change of load, environment, or aging. Thus plant parameter variations often occur in practice.
The equation used in the design is often called the nominal equation. The feedforward gain
p in (8.25), computed for the nominal plant transfer function, may not yield gl(O) = I for
nonnominal plant transfer functions. Then the output will not track asymptotically any step
reference input. Such a tracking is said to be.nonrobust.
In this subsection we discuss a different design that can achieve robust tracking and
disturbance rejection. Consider a plant described by (8.1). We now assume that a constant
disturbance w with unknown magnitude enters at the plant input as shown in Fig. 8A(a). Then
the state equation must be modified as
x
= Ax+ bu +bw
(8.26)
y = ex
The problem is to design an overall system so that the output y(t) will track asymptotically
any step reference input even with the presence of a disturbance w (t) and with plant parameter
variations. This is called robust tracking and disturbance rejection. In order to achieve this
design, in addition to introducing state feedback, we will introduce an integrator and a unity
feedback from the output as shown in Fig. 8A(a). Let the output of the integrator be denoted by
\. This section may be skipped without loss of continuity.

|     |     |     |     |     |     |     |     | 8,2  State Feedback  | 241  |
| --- | --- | --- | --- | --- | --- | --- | --- | -------------------- | ---- |
:][ :,]
|     |     |     |               |     |     | ["'  a2  | al    |     |        |
| --- | --- | --- | ------------- | --- | --- | -------- | ----- | --- | ------ |
|     |     |     |               |     | ,   | a,  al   | I     |     |        |
|     |     |     | =[bAbA2bA~bJ  |     |     | -        |       |     | (822)  |
|     |     |     |               |     |     |          | I  0  |     |        |
al
o
|     |     |     |     |     |     | I   | 0  0  | kP  |     |
| --- | --- | --- | --- | --- | --- | --- | ----- | --- | --- |
=
where we have used ~(A)  0, If (A. b) is controllable and (F. k) is observable. then all
three matrices after the last equality are nonsingular. Thus (8.22) and the non singularity of
t.(F) imply that Tis nonsingular. If (A. b) is uncontrollable and/or (F. k) is unobservable.
then the product of the three matrices is singular. Therefore T is singular. This establishes
|     | the theorem.  |     | Q.E,D,  |     |     |     |     |     |     |
| --- | ------------- | --- | ------- | --- | --- | --- | --- | --- | --- |
We now discuss the selection of F and k. Given a set of desired eigenvalues. there are
infinitely many F that ha\'e the set of eigenvalues. If we form a polynomial from the set. we
can use its coefficients to form a companion-form matrix F as shown in (7.14). For this F.
we can select k as [I  0  ...  0] and (F. k) is observable. If the desired eigenvalues are all
distinct, we can also use the modal form discussed in Section 4.3.1. For example. if II  =  5.
and if the five distinct desired eigenvalues are selected as A I. at ± j f31. and a2 ± if32. then we
can select F as
|     |     |     |     |     | AI  | 0  0     | 0  0  |     |     |
| --- | --- | --- | --- | --- | --- | -------- | ----- | --- | --- |
|     |     |     |     |     | 0   | al  f31  | 0  0  |     |     |
I
|     |     |     |     |     | -f31  |       | 0         |     | (8 23)  |
| --- | --- | --- | --- | --- | ----- | ----- | --------- | --- | ------- |
|     |     |     |     | F=  | 0     | al    | 0         |     |         |
|     |     |     |     |     | 0     | 0  0  | a2  f32   |     |         |
|     |     |     |     |     | 0     | 0  0  | -f32  a2  |     |         |
It is a block-diagonal matrix. For this F, if k has at least one nonzero entry associated with
eachdiagonalblocksuchask=[IIOIOJ,k=[IIOOlj,ork=[IIIII].then(F.k)is
observable (Problem 6.16), Thus the first two steps of Procedure 8.1 are very simple. Once F
and k are selected. we may llse the MATLAB function lyap to solve the Lyapunov equation
in Step 3. Thus Procedure 8,1 is easy to carry out as the next example illustrates.
.,
8.4  Consider the  inverted  pendulum studied  in  Example  8.3.  The  plant  state
.~  EXAMPLE
I ± i  and -1.5 ± 0,5 i.
equation is given in (8.18) and the desired eigenvalues were chosen as -
~
We select F in modal form as
o
-I
|     |     |     |     |     |     |     | o  0~5]  |     |     |
| --- | --- | --- | --- | --- | --- | --- | -------- | --- | --- |
|     |     |     |     |     | -I  | -I  |          |     |     |
',{
~  o
| .j  |     |     |     | F =  |     | -1.5  |     |     |     |
| --- | --- | --- | --- | ---- | --- | ----- | --- | --- | --- |
[
o
|     |     |     |     |     |     | -0.5  | -1.5  |     |     |
| --- | --- | --- | --- | --- | --- | ----- | ----- | --- | --- |
"
'1
| and k =  |     | [I 0 I OJ. We type  |     |     |     |     |     |     |     |
| -------- | --- | ------------------- | --- | --- | --- | --- | --- | --- | --- |
'J
!
<
|     | a= [O  | 1 0  0;0  | 0   | 0;0  | 0  0  1;00  | 5   | 0] ;b= [0;1;0; | -2;;  |     |
| --- | ------ | --------- | --- | ---- | ----------- | --- | -------------- | ----- | --- |
1  f=[- l  1  0  0;-1  -:  0  C;O 0  -1. 5  0.5;0  0  -0 .5  -1 .5; ;
| I   | kb<l  | 0  1  0]; c=:,'",p(a |     |     | , b, -b*kb) | ;   |     |     |     |
| --- | ----- | -------------------- | --- | --- | ----------- | --- | --- | --- | --- |
j
k=kb*inv(t)

~';.,
242 STATE FEEDBACK AND STATE ESTIMATORS
The answer is [-1.6667 - 3.6667 - 8.5833 - 4.3333], which is the same as the one obtained
~ k k.
by using function place. If we use a different = [I I I I). we will obtain the same Note
that the feedback gain is unique for the SISO case.
8.3 Regulation and Tracking
Consider the state feedback system shown in Fig. 8.2. Suppose the reference signal r is zero,
and the response of the system is caused by some nonzero initial conditions. The problem is
to find a state feedb'lck gain so that the response will die out at a desired rate. This is called a
regulator problem. This problem may arise when an aircraft is cruising at a fixed altitude H Q.
Now. because of turbulance or other factors, the aircraft may deviate from the desired altitude.
Bringing the deviation to zero is a regulat6r problem. This problem also arises in maintaining
the liquid level in Fig. 2.14 at equilibrium.
A closely related problem is the tracking problem. Suppose the reference signal r is a
constant or r(t) = a, for t ~ O. The problem is to design an overall system so that yet)
a
approaches r(l) = a as t approaches infinity. This is called asymptotic tracking of step
=
reference input. It is clear that if r(t) = a 0, then the tracking problem reduces to the
regulator problem. Why do we then study these two problems separately? Indeed, if the same
state equation is valid for all r, designing a system to track asymptotically a step reference input
will automatically achieve regulation. However. a linear state equation is often obtained by
shifting to an operating point and linearization, and the equation is valid only for r very small
or zero; thus the study of the regulator problem is needed. We mention that a step reference
input can be set by the position of a potentiometer and is therefore often referred to as set point.
Maintaining a chamber at a desired temperature is often said to be regulating the temperature; it
is actually tracking the desired temperature. Therefore no sharp distinction is made in practice
between regulation and tracking a step reference input. Tracking a nonconstant reference signal
is called a servomechanism problem and is a much more difficult problem.
Consider a plant described by (A. b, c). If all eigenvalues of A lie inside the sector shown
in Fig. 8.3, then the response caused by any initial conditions will decay rapidly to zero and
no state feedback is needed. If A is stable but some eigenvalues are outside the sector, then
the decay may be slow or too oscillatory. If A is unstable. then the response excited by any
nonzero initial conditions will grow unbounded. In these situations. we may introduce state
=
feedback to improve the behavior of the system. Let u r - kx. Then the state feedback
equation becomes (A - bk. b. c) and the response caused by x(O) is
yet) = ce(A-bk)/x(O)
If all eigenvalues of (A - bk) lie inside the sector in Fig. 8.3(a). then the output will decay
rapidly to zero. Thus regulation can easily be achieved by introducing state feedback.
The tracking problem is slightly more complex. In general. in addition to state feedback.
we need a feedforward gain p as
=
u(t) pr(t) - kx
Then the transfer function from r to y differs from the one in (8.17) only by the feedforward
gain p. Thus we have

244 STATE FEEDBACK AND STATE ESTIMATORS
x
r + I' >J c I .v
b~
+
l===l
A
(a)
y
g(s)
(b)
(c)
Figure 8.4 (a) State feedback with internal modeL (b) Interchange of two summers. (c) Transfer
function block diagram.
Xa(t). an augmented state variable. Then the system has the augmented state vector [x' xal'.
From Fig. 8.4(a), we have
Xa = r - y = r - ex (8.27)
[:J
u = [k ka] (8.28)
For convenience, the state is fed back positively to u as shown. Substituting these into (8.26)
yields
r
[:. ] = [A ~cbk b~a][:,] + [~] + [~ ] w
(8.29)
0][:']
y=[c
This describes the system in Fig. 8.4(a).
~ Theorem 8.5
If (A. b) is controllable and if g(s) = c(51 - A)-Ib has no zero at 5 = 0, then all eigenvalues of the
A-matrix in (8.29) can be assigned arbitrarily by selecting a feedback gain [k k a]·
a
=
Proof' We show the theorem for n 4. We assume that A, b, and c have been transformed
into the controllable canonical form in (8.7) and its transfer function equals (88). Then
the plant transfer function has no zero at 5 = 0 if and only if f34 of O. We now show that
the pair

|     |     |     |     | 8.4  State Estimator  | 247  |
| --- | --- | --- | --- | --------------------- | ---- |
We see that
| •         |     | ka1'I(O)       | kaN(O)     |       |         |
| --------- | --- | -------------- | ---------- | ----- | ------- |
|           |     | +              |            |       | (8.35)  |
| 8y,(0) =  | o.  | iJ(O)  kaN(O)  | =  kaN(O)  | =  1  |         |
Equation (8.35) holds even when there are parameter perturbations in the plant transfer function
and the gains. Thus asymptotic tracking of any step reference input is robust. Note that this
robust tracking holds even for very large parameter perturbations as long as the overall system
remains stable.
We see that the design is achieved by inserting an integrator as shown in Fig. 8.4. The
integrator is in fact a model of the step reference input and constant disturbance. Thus it is
called the internal model principle. This will be discussed further in the next chapter.
8.3.2  Stabilization
If a state equation is controllable, all eigenvalues can be assigned arbitrarily by introducing
state feedback. We now discuss the case when the state equation is not controllable. Every
uncontrollable state equation can be transformed into
|     | [::]=[~e  | ~I:][~:]+[~]u  |     |     |     |
| --- | --------- | -------------- | --- | --- | --- |
(8.36)
where (It, be) is controllable (Theorem 6.6). Because the A-matrix is block triangular, the
eigenvalues of the original A-matrix are the union of the eigenvalues of Ae and Ai"  If we
introduce the state feedback
|          |          | -        | - -     | [xe]  |     |
| -------- | -------- | -------- | ------- | ----- | --- |
| II = r - | kx = r - | kX = r - | [k k2J  | Xc    |     |
l
| where we have partitioned  | k  as in ;C, then (8.36) becomes  |     |     |     |     |
| -------------------------- | --------------------------------- | --- | --- | --- | --- |
k
|           | Ac -0b ck  | A   j}e | [~:  | ]  [~    |         |
| --------- | ---------- | ------- | ---- | -------- | ------- |
| [:: ]  =  | [          |         |      | +  ]  r  | (8.37)  |
|           |            | I  1 2  | 2 ]  |          |         |
We see that Ai' and, consequently, its eigenvalues are not affected by the state feedback. Thus
we conclude that the controllability condition of (A, b) in Theorem 8.3 is not only sufficient
but also necessary to assign all eigenvalues of (A - bk) to any desired positions.
Consider again the state equation in (8.36). If Ai' is stable, and if (Ae, bel is controllable,
then (8.36) is said to be stabilizable. We mention that the conirollability condition for tracking
and disturbance rejection can be replaced by the weaker condition of stabilizability. But in this
case, we do not have complete control of the rate of tracking and rejection. If the uncontrollable
stable eigenvalues have large imaginary parts or are close to the imaginary axis, then the
tracking and rejection may not be satisfactory.
8.4  State Estimator
We introduced in the preceding sections state feedback under the implicit assumption that all
state variables are available for feedback. This assumption may not hold in practice either

|     |     |      |     |      | 8.3  Regulation and Tracking  |     |     | 245  |
| --- | --- | ---- | --- | ---- | ----------------------------- | --- | --- | ---- |
|     |     | [~c  | ~]  | [~]  |                               |     |     |      |
(8.30)
is controllable if and only if f34  1= O. Note that we have assumed n = 4; thus the dimension
of (8.30) is five because of the additional augmented state variable  The controllability
Xa'
matrix of (8.30) is
| Ab  A2b  |     | Alb  | 4    |     |     |     |     |     |
| -------- | --- | ---- | ---- | --- | --- | --- | --- | --- |
| [~       |     |      | A b  | ]   |     |     |     |     |
-cAlb
| -cb  -cAb  | -cA"b  |       |           |       |               |     |      |     |
| ---------- | ------ | ----- | --------- | ----- | ------------- | --- | ---- | --- |
| I  -al     |        | a0 i- |           |       | +             | al  |      |     |
|            |        | a2    | -al (aT - |       | (,2 )  azal - |     | al5  |     |
| 0          | I      | -al   |           | Q'j - | 0'2           |     |      |     |
aZ5
| =10  | 0   | I   |     |     | -al  |     | al5  |     |
| ---- | --- | --- | --- | --- | ---- | --- | ---- | --- |
| 0    |     | 0   |     |     |      |     |      |     |
|      | 0   |     |     |     |      |     | a45  |     |
+
| 0  -f31  | f3lal -f32  |     | -f31 (aT - |     | (2)  f32al - | f3J  | a55  |     |
| -------- | ----------- | --- | ---------- | --- | ------------ | ---- | ---- | --- |
where the last column is not written out to save space. The rank of a matrix will not change
by elementary operations. Adding the second row multiplied by f31  to the last row. and
adding the third row multiplied by f32 to the last row, and adding the founh row mUltiplied
by f33  to the last row. we obtain
,
|         | a- -  |                 |     | +         |            |       |     |         |
| ------- | ----- | --------------- | --- | --------- | ---------- | ----- | --- | ------- |
| I  -al  |       | (x"   -al (aT - |     | ( 2 )     | a2al - al  | al5   |     |         |
|         | I     | -               |     | ,         |            |       |     |         |
| 0  I    | -0'1  |                 |     | 0'- - a,  |            | a25   |     |         |
|         |       |                 |     | I         | -          |       |     |         |
| 0  0    | I     |                 |     |           |            |       |     | (8.31)  |
|         |       |                 |     | -0'1      |            | a35   |     |         |
| 0  0    | 0     |                 |     | I         |            | a45   |     |         |
| 0  0    | 0     |                 |     | 0         |            | -f34  |     |         |
i=
Its detenninant is -f34. Thus the matrix is nons in gular if and only if f34  O. In conclusion,
if (A. b) is  controllable and if g(s) has no zero at s  =  O.  then the pair in (8.30) is
controllable. It follows from Theorem 8.3 that all eigenvalues of the A·matrix in (8.29)
can be assigned arbitrarily by selecting a feedback gain [k  kal.  Q.E.D.
We mention that the controllability of the pair in (8.30) can also be explained from pole
zero cancellations. If the plant transfer function has a zero at s = 0, then the tandem connection
of the integrator, which has transfer function  lis, and the plant will involve the pole-zero
cancellation of s and the state equation describing the connection will not be controllable. On
the other hand, if the plant transfer function has no zero at s =  0, then there is no pole-zero
cancellation and the connection will be controllable.
assume that a set of n +
Consider again (8.29).  We  I desired stable eigenvalues or,
+
equivalently, a desired polynomial t:J. f (s) of degree n  I has been selected and the feedback
ka 1h as been found such that
gain [k
|     |               | [SI-~-bk  |     |     | -~ka ]  |     |     |         |
| --- | ------------- | --------- | --- | --- | ------- | --- | --- | ------- |
|     | t:J.j(s)=det  |           |     |     |         |     |     | (8.32)  |
Now we show that the output y will track asymptotically and robustly any step reference input
ret)  =  a and reject any step disturbance with unknown magnitude. Instead of establishing
the assenion directly from (8.29), we will develop an equivalent block diagram of Fig. 8.4(a)
and then establish the assenion. First we interchange the two summers between v and U as

'1'
246  STATE FEEDBACK AND STATE ESTIMATORS
u
shown in Fig. 8.4(b). This is permitted because we have  = v + kx + w before and after the
interchange. The transfer function from Ii to y is
|     | o            | N(s)  |           |     |      | -I  |     | (8.33)  |
| --- | ------------ | ----- | --------- | --- | ---- | --- | --- | ------- |
|     | g(s) := -_-  |       | := c(sl - | A - | bk)  | b   |     |         |
D(s)
=  det (sl -
with D(s)  A - bk). Thus Fig. 8.4(a) can be redrawn as shown in Fig. 8.4(c). We
next establish the relationship between c,j(s) in (8.32) and g(s) in (833). It is straightforward
to verify the following equality:
|     |     | IO]  |     |     | A-  |     |     |     |
| --- | --- | ---- | --- | --- | --- | --- | --- | --- |
[Sl -
| r           |       |            |           |       | bk        | -bka | ]   |     |
| ----------- | ----- | ---------- | --------- | ----- | --------- | ---- | --- | --- |
| ... -c(sl - |       | A - bk)-I  | 1         |       | c         |      | s   |     |
| -_          | [Sl - | A° - bk    | I         | -bka  |           |      |     |     |
|             |       |            | +         |       |           |      | ]   |     |
|             |       |            | S  c(sl - | A -   | bk)-Ibka  |      |     |     |
Taking its determinants and using (8.32) and (8.33), we obtain
|     |     |              | _     | (       | N(S»)  |     |     |     |
| --- | --- | ------------ | ----- | ------- | ------ | --- | --- | --- |
|     |     | I· c,j(s) =  | D(s)  | s  + -- | -ka    |     |     |     |
D(s)
which implies
+
|     |     | c,j(s) = sD(s)  |     | kaN(s)  |     |     |     |     |
| --- | --- | --------------- | --- | ------- | --- | --- | --- | --- |
This is a key equation,
From Fig, 8.4(c), the transfer function from w to y can readily be computed as
N(s)
|     | _   | "liW    | _        |        |          |           |     |     |
| --- | --- | ------- | -------- | ------ | -------- | --------- | --- | --- |
|     |     |         |          | sN(s)  |          | _  sN(s)  |     |     |
|     |     | kaN(s)  | - sD(s)  | +      | kaN(s) - | c,j(s)    |     |     |
gyw -
1+--'----
sD(s)
If the disturbance is w(t) =  w for all t ::: 0, where w is an unknown constant, then w(s) = w / s
and the corresponding output is given by
|     |     | •   | sN(s) w  |     | wN(s)  |     |     |     |
| --- | --- | --- | -------- | --- | ------ | --- | --- | --- |
(8.34)
|     |     | Yw(s) =  | ---       | =-~  |         |     |     |     |
| --- | --- | -------- | --------- | ---- | ------- | --- | --- | --- |
|     |     |          | c,j(s) s  |      | c,j(s)  |     |     |     |
Because the pole sin (834) is canceled, all remaining poles ofYw (s) are stable poles. Therefore
the corresponding time response, for any W, will die out as t  -....
00. The only condition to
achieve the disturbance rejection is that  Yw  (s) has only stable poles. Thus the rejection still
. holds, even if there are plant parameter variations and variations in the feedforward gain ka
and feedback gain k, as long as the overall system remains stable. Thus the disturbance is
suppressed at the output both asymptotically and robustly.
The transfer function from r to y is
|     |     | ka  N(s)  |     |     |     |     |     |     |
| --- | --- | --------- | --- | --- | --- | --- | --- | --- |
D0
|         | =   | -;  | =   | _         |     | =   |         |     |
| ------- | --- | --- | --- | --------- | --- | --- | ------- | --- |
| gy,(s)  |     |     |     | kaN(s) _  |     |     | kaN(s)  |     |
+
| .   |     | ka  | N(s)  sD(s)  |     | kaN(s)  |     | c,j(s)  |     |
| --- | --- | --- | ------------ | --- | ------- | --- | ------- | --- |
1+----
s  D(s)

248 STATE FEEDBACK AND STATE ESTIMATORS
because the state variables are not accessible for direct connection or because sensing devices
or transducers are not available or very expensive. In this case. in order to apply state feedback.
we must design a device, called a state estilllator or state observer. so that the output of the
device will generate an estimate of the state. In this section, we introduce full-dimensional
state estimators which have the same dimension as the original state equation. We use the
x
circumflex over a variable to denote an estimate of the variable. For example, is an estimate
i x.
of x and is an estimate of
Consider the n-dimensional state equation
x = +
Ax btl
(838)
y = ex
where A, b, and e are given and the input tI(t) and the output y(t) are available to us. The
state x, however, is not available to us. The problem is to estimate x from tI and y with the
knowledge of A, b, and e. If we know A and b, we can duplicate the original system as
x = Ax + btl (839)
and as shown in Fig. 8.5. Note that the original system could be an electromechanical system
and the duplicated system could be an op-amp circuit. The duplication will be called an open
loop estimator. Now if (8.38) and (8.39) have the same initial state, then for any input. we have
x(t) = x(t) for all I ::: O. Therefore the remaining question is how to find the initial state of
(8.38) and then set the initial state of (8.39) to that state. If (8.38) is observable, its initial state
x(O) can be computed from II and y over any time interval, say, [0, Ill. We can then compute
the state at t~ and set X(tl) = X(t2). Then we have x(t) = X(I) for all t ::: I!. Thus if (8.38) is
observable, an open-loop estimator can be used to generate the state vector.
There are, however, two disadvantages in using an open-loop estimator. First. the initial
state must be computed and set each time we use the estimator. This is very inconvenient.
Second, and more seriously, if the matrix A has eigenvalues with positive real pans, then
even for a very small difference between x(to) and x(to) for some 10, which may be caused by
disturbance or imperfect estimation of the initial state, the difference between x(r) and x(t)
will grow with time. Therefore the open-loop estimator is, in general. not satisfactory.
We see from Fig. 8.5 that even though the input and output of (8.38) are available. we
x x y Figure 8.5 Open-loop state estimator.
'Ib~s
II I---~
A
--------------- 1
n ' • r.l I x
Ib~
A

8.4 State Estimator 251
4. Then the state equation
i::i: = Fz + Tbu + Iy (8.43)
= T-Iz (8.44)
generates an estimate of x.
We first justify the procedure. Let us define
e:= z - Tx
Then we have, replacing TA by FT + Ie,
e = :i: - TX = Fz + Tbu + lex - TAx - Tbu
+ + = =
= Fz lex - (FT ic)x F(z - Tx) Fe
IfF is stable, for any e(O), the error vector e(t) approaches zero as t _ 00. Thus z approaches
Tx or, equivalently, T-Iz is an estimate ofx. All discussion in Section 8.2.1 applies here and
will not be repeated.
8.4.1 Reduced-Dimensional State Estimator
Consider the state equation in (8.42). If it is observable, then it can be transformed, dual to
Theorem 8.2, into the observable canonical form in (7.14). We see that y equals XI, the first
state variable. Therefore it is sufficient to construct an (n - I)-dimensional state estimator to
estimate Xj for i = 2. 3, ... ,n. This estimator with the output equation can then be used to
estimate all n state variables. This estimator has a lesser dimension than (8.42) and is called a
reduced-dimensional estimator.
Reduced-dimensional estimators can be designed by transformations or by solving Lya
punoy equations. The latter approach is considerably simpler and will be discussed next. For
the former approach, the interested reader is referred to Reference [6, pp. 361-363].
~ Procedure 8.Rl
1. Select an arbitrary (n - I) x (n - I) stable matrix F that has no eigenvalues in common with those
ofA.
2. Select an arbitrary (n - 1) x 1 vector 1 such that (F, I) is controllable.
=
3. Solve the unique T in the Lyapunov equation TA - FT Ie. Note that T is an (n - I) x n matrix.
4. Then the (n - I )-dimensional state equation
i = Fz + Tbu + Iy (8.45)
i:=[~r[~]
(8.46)
is an estimate of x.
We first justify the procedure. We write (8.46) as

|     |     |     | 8.4 State Estimator  |     | 249  |
| --- | --- | --- | -------------------- | --- | ---- |
Figure 8.6  Closed-loop state estimator.
|     |     | .Ibl  |              |     | <I  v  |
| --- | --- | ----- | ------------ | --- | ------ |
|     | II  |       | ;~ISI-A)-ll  | ;~  |        |
- - --1
r-
11-:-
I
|     |     |     | +   |                  | x   |
| --- | --- | --- | --- | ---------------- | --- |
|     |     |     | x   | ;=::::±:::::=:»  |     |
b~s
+
'---------------
use only the input to drive the open-loop estimator. Now we shall modify the estimator in Fig.
8.5 to the one in Fig. 8.6, in which the output y(t)  =
cx(t) of (8.38) is compared with eX(t).
Their difference, passing through an n x  I constant gain vector I. is used as a correcting term.
If the difference is zero, no correction is needed. If the difference is nonzero and if the gain I
is properly designed. the difference will drive the estimated state to the actual state. Such an
estimator is called a closed-loop or an asymptotic estimator or, simply, an estimator.
The open-loop estimator in (8.39) is now modified as, following Fig. 8.6.
|          | +    | +          |     |     |     |
| -------- | ---- | ---------- | --- | --- | --- |
| x =  Ax  | btl  | I(y - eX)  |     |     |     |
which can be written as
| i  =  | Ic)x  | +  bu  +  II  |     |     | (8.40)  |
| ----- | ----- | ------------- | --- | --- | ------- |
(A -
x.
and is shown in Fig. 8.7. It has two inputs u and v and its output yields an estimated state
Let us define
| e(t) := xU) - |     | x(t)  |     |     |     |
| ------------- | --- | ----- | --- | --- | --- |
It is the error between the actual  state and the estimated state.  Differentiating e and then
substituting (8.38) and (8.40) into it, we obtain
I
Figure 8.7  Closed-loop state estimator.
|     |     | .1 b      | :~(II_AJ-li  | :~ c  |          |
| --- | --- | --------- | ------------ | ----- | -------- |
|     | II  |           |              |       | 1  ,  "  |
|     | X<  | :  r==:j  |              |       |          |
I
A-Ie
I
---------------

250 STATE FEEDBACK AND STATE ESTIMATORS
e = x - i = +
Ax bu - (A - Ie)x - bu - I(cx)
= (A -le)x - (A - Ic)x = (A - \c) (x - x)
or
e
= (A -le)e (8.41)
This equation governs the estimation error. If all eigenvalues of (A - Ie) can be assigned
arbitrarily, then we can control the rate for e(t) to approach zero or. equivalently, for the
estimated state to approach the actual state. For example, if all eigenvalues of (A - Ie) have
negative real parts smaller than then all entries of e will approach zero at rates faster
-(1,
than e-(1t. Therefore, even if there is a large error between x(to) and x(ro) at initial time to,
the estimated state will approach the actual iState rapidly. Thus there is no need to compute
t
the initial state of the original state equation. In conclusion, if all eigenvalues of (A - Ie) are
properly assigned, a c1osed-ioop estimator is much more desirable than an open-loop estimator.
As in the state feedback. what constitutes the best eigenvalues is not a simple problem.
Probably, they should be placed evenly along a circle inside the sector shown in Fig.8.3(a). If
an estimator is to be used in state feedback, then the estimator eigenvalues should be faster than
the desired eigenvalues of the state feedback. Again. saturation and noise problems will impose
constraints on the selection. One way to carry out the selection is by computer simulation.
~ Theorem 8.03
Consider the pair (A, c). All eigenvalues of (A - Ie) can be assigned arbitrarily by selecting a real
constant vector I if and only if (A. c) is observable.
This theorem can be established directly or indirectly by using the duality theorem. The
pair (A, c) is observable if and only if (A', e') is controllable. If (A', e') is controllable. all
eigenvalues of (A' - e'k) can be assigned arbitrarily by selecting a constant gain vector k. The
transpose of (A' - e'k) is (A - k'e). Thus we have 1= k'. In conclusion, the procedure for
computing state feedback gains can be used to compute the gain I in state estimators.
Solving the Lyapunov equation We discuss a different method of designing a state estimator
for the n-dimensional state equation
x
= Ax+ bu
(8.42)
y = ex
The method is dual to Procedure 8.1 in Section 8.2.1.
~ Procedure 8.01
1. Select an arbitrary n x n stable matrix F that has no eigenvalues in common with those of A.
2. Select an arbitrary n x I vector I such that (F. \) is controllable.
3. Solve the unique T in the Lyapunov equation TA - IT = Ie. This T is nonsingular following the
dual of Theorem 8.4.

252  STATE FEEDBACK AND STATE ESTIMATORS
|     |     |     | ~        | ~             |     |     |     |     |
| --- | --- | --- | -------- | ------------- | --- | --- | --- | --- |
|     |     |     | [  ]  =  | [  ] X =: Px  |     |     |     |     |
which implies y =  ex and z =  Tx. Clearly v is an estimate of ex. We now show that z is an
estimate of Tx. Define
|     |     |     | e = z - | Tx  |     |     |     |     |
| --- | --- | --- | ------- | --- | --- | --- | --- | --- |
Then we have
| e =  |      | =   | +        | +     |       |      | =   |     |
| ---- | ---- | --- | -------- | ----- | ----- | ---- | --- | --- |
|      | :i - | Tx  | Fz  Tbu  | lex - | TAx - | Tbu  | Fe  |     |
Clearly if F is stable, then e(t) -. 0 as t  -. 00. Thus z is an estimate of Tx.
Theorem 8.6
~
If A and F have no common eigenvalues, then the square matrix
[~J
p=
where T is the unique solution of TA - FT =  Ie. is nonsingular if and only if (A, e) is observable and
(F. I) is controllable.
=
~  Proof'  We prove the theorem for n  4. The first part of the proof follows closely the
proof of Theorem 8.4. Let
|                  |     |     |             |       | ,    | ,    |     |     |
| ---------------- | --- | --- | ----------- | ----- | ---- | ---- | --- | --- |
|                  |     |     | A) = s ~ +  |       | +    | +    | +   |     |
| 6(s) = det (sl - |     |     |             | als'  | a2s- | a3s  | a4  |     |
Then, dual to (8.22), we have
i][::,]
[a,
|     |           |                 |     |     | 0'2  al  |     |     |        |
| --- | --------- | --------------- | --- | --- | -------- | --- | --- | ------ |
|     |           |                 |     |     | al  1    |     |     |        |
| -   | T ~(F) =  | [I FI F21 F31)  |     | a:  |          |     |     | (847)  |
|     |           |                 |     | al  | I  0     |     |     |        |
o
|     |     |     |     |     | 0  0  |     | eA3  |     |
| --- | --- | --- | --- | --- | ----- | --- | ---- | --- |
I
and ~(F) is nonsingular if A and F have no common eigenvalues. Note that if A is 4 x 4,
then F is 3 x 3. The rightmost matrix in (8.47) is the observability matrix of (A. e) and will
be denoted by O. The first matrix after the equality is the controllability matrix of (F. I)
with one extra column and will be denoted by C. The middle matrix will be denoted by
A and is always nonsingular. Using these notations. we write T as - ~ - I (F) C~A 0 and P
becomes
~
|     |     | P = [  | ]  =              | [ - 6 - | I (;) CA 0 ]  |     |     |         |
| --- | --- | ------ | ----------------- | ------- | ------------- | --- | --- | ------- |
|     |     |        | [~  -6\F)][C~~0]  |         |               |     |     | (8.48)  |
=
Note that if n =  4, then P, 0, and A are 4 x 4: T and C are 3 x 4 and 6 (F) is 3 x 3.
4
If (F, I)  is not controllable, C has rank at most 2. Thus T has rank at most 2 and P is
4
singular. If (A, e) is not observable, then there exists a nonzero 4 x  1 vector r such that

8.6 State Feedback-Multivariable Case 255
The A-matrix in (8.55) is block triangular; therefore its eigenvalues are the union of those
of (A - bk) and (A - Ie). Thus inserting the state estimator does not affect the eigenvalues
of the original state feedback; nor are the eigenvalues of the state estimator affected by the
connection. Thus the design of state feedback and the design of state estimator can be carried
out independently. This is called the separation property.
The state equation in (8.55) is of the form shown in (6.40); thus (8.55) is not controllable
and the transfer function of (8.55) equals the transfer function of the reduced equation
x = (A - bk)x + br y = ex
or
+
gj(s) = e(sI - A bk)-'b
(Theorem 6.6). This is the transfer function of the original state feedback system without using
a state estimator. Therefore the estimator is completely canceled in the transfer function from
r to y. This has a simple explanation. In computing transfer functions. all initial states are
assumed to be zero. Consequently, we have x(O) = x(O) = 0, which implies x(t) = x(t)
for alIt. Thus, as far as the transfer function from r to y is concerned, there is no difference
whether a state estimator is employed or not.
8.6 State Feedback-Multivariable Case
This section extends state feedback to multi variable systems. Consider a plant described by
the n-dimensional p-input state equation
x = Ax + Bu
(8.56)
Y = Cx
In state feedback, the input u is given by
u=r-Kx (8.57)
where K is a p x n real constant matrix and r is a reference signal. Substituting (8.57) into
(8.56) yields
x = (A - BK)x + Br
(8.58)
Y= Cx
>-
Theorem 8.M!
The pair (A - BK. B). for any p x n real constant matrix K. is controllable if and only if CA. B) is
controllable.
The proof of this theorem follows closely the proof of Theorem 8.1. The only difference
is that we must modify (8.4) as

|     |     | 8.5  | Feedback from Estimated States  |     | 253  |
| --- | --- | ---- | ------------------------------- | --- | ---- |
Or = 0, which implies er = 0 and Pr = O. Thus P is singular. This shows the necessity
of the theorem.
Next we show the sufficiency by contradiction. Suppose P is singular. Then there
exists a nonzero vector r such that Pr = 0, which implies
|     | [C4~O]r= [C4~Or]  |     |     |     | (8.49)  |
| --- | ----------------- | --- | --- | --- | ------- |
=0
Define a := A Or = [al a2 a3 a4l' =: [a a4J'. where a represents the first three entries of
a. Expressing it explicitly yields
I] [
| all  |     | al  |     |     |     |
| ---- | --- | --- | --- | --- | --- |
[a3  a2
o
|     |          | 1   | c A r  | x         |     |
| --- | -------- | --- | ------ | --------- | --- |
| Q2  | 0'2  at  |     | c r ]  | [  x   ]  |     |
o
| [   |        | o   | cA2 - | x   |     |
| --- | ------ | --- | ----- | --- | --- |
| a3  | al  1  |     | r     |     |     |
o  o
| a4  | 1  0  |     | cA3r  | er  |     |
| --- | ----- | --- | ----- | --- | --- |
where x  denotes entries that are not needed in subsequent discussion. Thus we have
a4 = cr. Clearly (8.49) implies a4 = cr = O. Substituting a4  = 0 into the lower part of
(8.49) yields
|     | C AOr = C | 4 a = Ca = 0  |     |     | (8.50)  |
| --- | --------- | ------------- | --- | --- | ------- |
4
a
where C is 3 x 3 and is the controllability matrix of (F, I) and  is the first three entries
of a. If (F,I) is controllable, then Ca = 0 implies a = O. In conclusion, (8.49) and the
controllability of (F,I) imply a = O.
Consider A Or = a = O. The matrix A is always nonsingular. If (A, c) is observable,
then 0 is nonsingular and A Or = 0 implies r = O. This contradicts the hypothesis that r
is nonzero. Thus if (A, c) is observable and (F, I) is controllable, then P is nonsingular.
This establishes Theorem 8.6.  Q.E.D.
Designing state estimators by solving Lyapunov equations is convenient because the
same procedure can be used to design full-dimensional and reduced-dimensional estimators.
As we shall see in a later section, the same procedure can also be used to design estimators for
multi-input multi-output systems.
8.5  Feedback from Estimated States
Consider a plant described by the n-dimensional state equation
x
|     |     | = Ax  +  bu  |     |     |     |
| --- | --- | ------------ | --- | --- | --- |
(8.51)
y = ex
If (A, b) is controllable. state feedback u  =  r  - kx can place the eigenvalues of (A - bk)
in any desired positions. If the state variables are not available for feedback, we can design a
state estimator. If (A, c) is observable, a full- or reduced-dimensional estimator with arbitrary
eigenvalues can be constructed. We discuss here only full-dimensional estimators. Consider
the n-dimensional state estimator
|     |           | +     | +       |     |         |
| --- | --------- | ----- | ------- | --- | ------- |
|     | ~ =  (A - | ic)x  | bu  Iv  |     | (8.52)  |

-~1
254 STATE FEEDBACK AND STATE ESTIMATORS
The estimated state in (8.52) can approach the actual state in (8.51) with any rate by selecting
the vector I.
The state feedback is designed for the state in (8.51). If x is not available, it is natural to
apply the feedback gain to the estimated state as
u=r-Id (8.53)
as shown in Fig. 8.8. The connection is called the controller-estimator configuration. Three
questions may be raised in this connection: (I) The eigenvalues of (A - bk) are obtained from
u = r - kx. Do we still have the same set of eigenvalues in using u = r - kX? (2) Will
the eigenvalues of the estimator be affected by the connection? (3) What is the effect of the
estimator on the transfer function from r to y? To answer these questions, we must develop
a state equation to describe the overall system in Fig. 8.8. Substituting (8.53) into (8.51) and
I
(8.52) yields
x +
= Ax - bkx br
i = (A - Ie)x + b(r - kX) + lex
They can be combined as
[~ _~:~
[:] = + [:]
A bk][;] r
(8.54)
Ol[;]
y=[c
This 2n-dimensional state equation describes the feedback system in Fig. 8.8. It is not easy
to answer the posed questions from this equation. Let us introduce the following equivalence
transformation:
[: ] =[ x : x] =[ ; =:
~I][;]
p [;]
Computing P-', which happens to equal P, and then using (4.26), we can obtain the following
equivalent state equation:
[:]=[A~bk A~\][:]+[:]r
(8.55)
Ol[:]
y=[c
r + u v Figure 8.8 Controller-estimator configuration.
I--r-.
Estimator
L-__- -.Jt Y

256  STATE FEEDBACK AND STATE ESTIMATORS
|     |     |     | -K(A - | BK)B  | -K(A - | BK)'B]  |     |     |
| --- | --- | --- | ------ | ----- | ------ | ------- | --- | --- |
IP  -KB
|     |     |     | Ip  | -KB  | -K(A - | BK)B  |     |     |
| --- | --- | --- | --- | ---- | ------ | ----- | --- | --- |
Cf
|     | =   | C  :  | 0   | Ip  |     | -KB  |     |     |
| --- | --- | ----- | --- | --- | --- | ---- | --- | --- |
[
|     |     |     | 0   | 0   |     | Ip  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
=
where C and Care n x np conrro!lability matrices with n  4 and Ip is the unit matrix of
f
order p. Because the rightmost 4p x 4p matrix is nonsingular. C has rank n if and only if C
f
has rank n. Thus the controllability property is preserved in any state feedback. As in the SISO
case, the observability property, however. may not be preserved. Next we extend Theorem 8.3
to the matrix case
".  Theorem 8.M3
All eigenvalues of (A - BK) can be assigned arbitrarily (provided complex conjugate eigen\alues are
assigned in pairs) by selecting a real constant K if and only if (A, B) is controllable.
If (A. B) is not controllable, then (A. B) can be transformed into the form shown in (8.36)
Ac
and the eigenvalues of  will not be affected by any state feedback. This shows the necessity
of the theorem. The sufficiency will be established constructively in the next three subsections.
8.6.1  Cyclic Design
In this design, we change the multi-input problem inro a single-input problem and then apply
Theorem 8.3. A matrix A is called CYclic if its characteristic polynomial equals its minimal
polynomial. From the discussion in Section 3.6, we can conclude that A is cyclic if and only
if the Jordan form of A  has one and only one Jordan block associated with each distinct
eigenvalue.
Theorem 8.7
If the n-dimensional p-input pair (A, B) is controllable and if A is cyeiic, then for almost any p X
vector v. the single-input pair (A. Bv) is controllable.
We argue inruitively the validity of this theorem. Controllability is invariant under any
equivalence transformation; thus we may assume A to be in Jordan form. To see the basic idea,
we use the following example:
|     | 2  I  | 0   |     | 0     |     |     | l  rx  |     |
| --- | ----- | --- | --- | ----- | --- | --- | ------ | --- |
|     |       | 0   | 0   | I..,  |     |     |        |     |
|     | 0  2  | 0   | 0   | 0     |     |     |        |     |
1
|      |        |       |     |     |     | ~  ~     |     | ~   |
| ---- | ------ | ----- | --- | --- | --- | -------- | --- | --- |
| A =  | 10  0  | 2  0  |     |     |     |          | =   |     |
|      |        |       | 0   | B=  |     | B.  B [  |     | I   |
(8.59)
|     | 0  0  | 0  -I  |     | 4  1J  |     |     |     |     |
| --- | ----- | ------ | --- | ------ | --- | --- | --- | --- |
|     | 0  0  | 0  0   | -I  | I      |     |     |     |     |
There is only one Jordan block associated with each distinct eigenvalue; thus A is cydic. The

8.6 State Feedback-Mul tivariable Case  259
be assigned arbitrarily by selecting a k (Theorem 8.3). Combining the two state feedback
| =      | =          |             |               |     |      |     |
| ------ | ---------- | ----------- | ------------- | --- | ---- | --- |
| u  w - | K1x and w  | r - Klx as  |               |     |      |     |
|        |            |             | + K2)X =: r - |     | K"\  |     |
|        |            | u = r -     | (K1           |     |      |     |
we obtain a K := KI + K2 that achieves arbitrary eigenvalue assignment. This establishes
Theorem 8.M3.
8.6.2  Lyapunov-Equation Method
This section will extend the procedure of computing feedback gain in Section 8.2.1 to the
multivariable case. Consider an n-dimensional p-input pair CA. B). Find a p x n real constant
matrix K so that (A - BK) has any set of desired eigenvalues as long as the set does not contain
any eigenvalue of A.
1:>  Procedure 8.Ml
1.  Select an n x n matrix F with a set of desired eigenvalues that contains no eigenvalues of A.
| 2.  Select an arbitrary p x n marrix  |     | K  such that (F.  |     | K)  is observable.  |     |     |
| ------------------------------------- | --- | ----------------- | --- | ------------------- | --- | --- |
TF = Bit
3. Solve the unique T in the Lyapunov equation AT -
K
4.  If T  is singular.  select a different  and repeat the  process.  If T  is  nonsingular.  we compute
| K =  KT-I.  and (A -                                 |     | BK) has the set of desired eigenvalues.  |     |            |     |     |
| ---------------------------------------------------- | --- | ---------------------------------------- | --- | ---------- | --- | --- |
| If Tis nonsingular. the Lyapunov equation and KT= K  |     |                                          |     | imply      |     |     |
|                                                      |     | BK)T = TF                                |     | BK = TF'T- | 1   |     |
|                                                      |     | (A -                                     | or  | A -        |     |     |
Thus (A - BK) and F are similar and have the same set of eigenvalues. Unlike the SISO case
where T is always nonsingular. the T here may not be nonsingular even if (A. B) is controllable
and (F. K)
is observable. In other words. the two conditions are necessary but not sufficient
for T to be nonsingular.
i>  Theorem 8.M4
If A and F have no eigen\alues in comm_on. then the unique solution T of AT - TF = BK is nonsingular
only if (A. B) is controllable and (F. K) is observable.
~  Proof:  The proof of Theorem 8.4 applies here except that (8.22) must be modified as. for
n =4.
|     |     |     |     | Q'31  Q'lI  | Q' I I  i]  |     |
| --- | --- | --- | --- | ----------- | ----------- | --- |
[i:,]
|     |              |               |        | Q' I I  | I   |     |
| --- | ------------ | ------------- | ------ | ------- | --- | --- |
|     | - T D.(F) =  | [B  AB  A 2B  | A 3B]  | Q'll    |     |     |
o
I  I
[  Q'I
|     |     |     |     |       | o   | .    |
| --- | --- | --- | --- | ----- | --- | ---- |
|     |     |     |     | I  o  | o   | KF3  |
or

8.6  State Feedback-Multivariable Case  257
condition for (A, B) to be controllable is that the third and the last rows of B are nonzero
(Theorem 6.8).
The necessary and sufficient conditions for (A. Bv) to be controllable are a  i
0 and
| f3  | i  (8.59). Because a  | =  +  2V2 and f3  |     | =              | or f3  |                         |
| --- | --------------------- | ----------------- | --- | -------------- | ------ | ----------------------- |
|     | 0 in                  | VI                |     | VI. either Ct  |        | is zero if and only if  |
=  0 or VI/V2 =  -2/1. Thus any v other than VI  =  0 and l'1  =  -2V2 will make (A. Bv)
VI
controllable. The vector v can assume any value in the two-dimensional real space shown in
Fig. 8.9. The conditions t'l  =  0 and VI  =  -2V2 constitute two straight lines as shown. The
probability for an arbitrarily selected v to lie on either straight line is zero. This establishes
Theorem 8.6. The cyclicity assumption in this theorem is essential. for example, the pair
n
.,
~l
|     |     | A =  [:  |     | B =  [:  |     |     |
| --- | --- | -------- | --- | -------- | --- | --- |
o
is  controllable  (Theorem  6.8).  However.  there  is  no  v  such  that  (A. Bv)  is  controllable
(Corollary 6.8).
If all eigenvalues of A are distinct. then there is only one Jordan block associated with
each eigenvalue. Thus a sufficient condition for A to be cyclic is that all eigenvalues of A are
distinct.
Theorem 8.8
If (A. B) is controllable, then for almost any p x n real constant matrix K. the matrix (A - BK) has
only distinct eigenvalues and is. consequently. <:yclic.
We show intuitively the theorem for 11  = 4. Let the characteristic polynomial of A - BK be
|     |     | ... +  | 3 +  | ., +  | +   |     |
| --- | --- | ------ | ---- | ----- | --- | --- |
D.j(S) = 5
|     |     | GI5  | a2S- | a.15  | a~  |     |
| --- | --- | ---- | ---- | ----- | --- | --- |
where the a, are functions of the entries of K. The differentiation of D.j(s) with respect to 5
yields
|     |     | ,  4' + 3     |      | ' + .,  | +   |     |
| --- | --- | ------------- | ---- | ------- | --- | --- |
|     |     | D./(5) =  5'  | air  | _Cl25   | a3  |     |
D.j
If D.! (5) has repeated roots. then D./ (s) and  (5) are not coprime. The necessary and sufficient
condition for them to be not coprime is that their Sylvester resultant is singular or
| Figure 8.9  | Two-dimensi,)nal real space.  |     |     |     |     | l"~  |
| ----------- | ----------------------------- | --- | --- | --- | --- | ---- |
2
"  = 0
,.,  l'\
|     |     |     |     |     | -2  - | 1  0  |
| --- | --- | --- | --- | --- | ----- | ----- |

~
258  STATE FEEDBACK AND STATE ESTIMATORS
|     |           | a.  | a3  0    | 0    | 0   | 0    | 0   | 0   |     |     |
| --- | --------- | --- | -------- | ---- | --- | ---- | --- | --- | --- | --- |
|     |           | a3  | 2a2  a.  | a]   | 0   | 0    | 0   | 0   |     |     |
|     |           |     |          |      |     |      | 0   | 0   |     |     |
|     |           | a2  | 3a,  a3  | 2a~  | a.  | a3   |     |     |     |     |
|     |           |     | 4  a2    | 3a,  | a3  | 2az  | a4  | a3  |     |     |
|     | det I a,  |     |          |      |     |      |     | I   |     |     |
== b(kij) == 0
|     |     | 1   | 0  a,  | 4   | a2  | 3a,  | a3  | 2a2  |     |     |
| --- | --- | --- | ------ | --- | --- | ---- | --- | ---- | --- | --- |
|     |     | 0   | 0  I   | 0   | a,  | 4    | a2  | 3a,  |     |     |
|     |     | 0   | 0  0   | 0   | 1   | 0    | a,  | 4    |     |     |
|     |     | 0   | 0  0   | 0   | 0   | 0    |     | 0    |     |     |
See (7.28). It is clear that all possible solutions of b(k == 0 constitute a very small subset of
ij)
all real kij. Thus if we select an arbitrary K, the probability for its entries to meet b(kij) == 0
is. O. Thus all eigenvalues of (A - BK) wil,l be distinct. This establishes the theorem.
With these two theorems, we can noW find a K to place all eigenvalues of (A - BK) in
any desired positions. If A is not cyclic, we introduce u =  w - K, x, as shown in Fig. 8.10,
A
| such that  := A - |     | BK, in  |         |        |     |            |     |     |     |         |
| ----------------- | --- | ------- | ------- | ------ | --- | ---------- | --- | --- | --- | ------- |
|                   |     |         | x       |        |     | +          |     | +   |     |         |
|                   |     |         | == (A - | BK,)x  |     | Bw ==: Ax  |     | Bw  |     | (8.60)  |
is cyclic. Because (A, B) is controllable, so is (A, B). Thus there exists a p  x  1 real vector
v such that (A, Bv) is controllable.' Next we introduce another state feedback w =  r - Kzx
| with K2 =  vk, where k is a 1 x n real vector. Then C8.60) becomes  |     |      |      |     |         |     |      |            |     |     |
| ------------------------------------------------------------------- | --- | ---- | ---- | --- | ------- | --- | ---- | ---------- | --- | --- |
|                                                                     |     | x =  |      |     | +       | =   |      | +          |     |     |
|                                                                     |     |      | (A - | BK  | )x  Br  |     | (A - | Bvk)x  Br  |     |     |
2
Because the single-input pair CA, Bv)  is  controllable. the eigenvalues of (A  - Bvk)  can
K,
<:-
K,
v
| r  -,  w-   | u   |       | ~,ttx,  |     |     |     |      |     | y   |     |
| ----------- | --- | ----- | ------- | --- | --- | --- | ---- | --- | --- | --- |
| r           |     |       |         |     |     | f   | ~-~  |     |     |     |
| - ' - ~  ~  |     |       |         |     |     |     |      | C   |     |     |
| . +         |     | ,  B  | ..."    | ):  | ~   |     | I-   | ,   |     |     |
| + ~         |     |       |         |     |     |     |      |     |     | ~   |
+
'---
A  ~
| Figure 8,10  State feedback by cyclic design.  |     |     |     |     |     |     |     |     |     |     |
| ---------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
2. The choices of K, and v are nOI unique. They can be chosen arbitnuily and the probability is I (hal they will meet
the requirements. In Theorem 7.5 of Reference (5J. a prOl:l!dure is given (Q choose K, and V with no unc~naimy.
The computation. however, is complicated.

260  STATE FEEDBACK AND STATE ESTIMATORS
|     |     |     | - Tc.(F) =  |     | CLO  |     |     | (S.6\)  |
| --- | --- | --- | ----------- | --- | ---- | --- | --- | ------- |
where t.(F) is  nonsingular and  C.  , and 0  are. respectively. n  x  np. np x lip. and
L
np x II. If C or 0  has rank less than n, then T  is singular following (3.61). However.
the conditions that C and 0  have rank n do not imply the nonsingularity of T. Thus the
controllability of (A, B) and observability of (F. K) are only necessary conditions for T
| to be nonsingular. This establishes Theorem S.1vI4.  |     |     |     |     |     | Q.E.D.  |     |     |
| ---------------------------------------------------- | --- | --- | --- | --- | --- | ------- | --- | --- |
Given a controllable (A, B). it is possible to construct an observable (F. K) so that the
T in Theorem S.M4 is singular. Howe\'er. after selecting F. if  K  is selected randomly and if
(F. K) is observable. it is believed that the probability for T to be nonsingular is  I. Therefore
solving the Lyapunov equation is a viable method of computing a feedback gain matrix to
achieve arbitrary eigenvalue assignment,' As in the SISO case, we may choose F in companion
form or in modal form as shown in (S.23). If F is chosen as in (S.23), then we can select K as
|     |     |     |     |     | - [0  |     |     |     |
| --- | --- | --- | --- | --- | ----- | --- | --- | --- |
|     |     |     | o   |     |       | o   | o   |     |
I  I  0
|      |      |       | ~]  |     | K=  |       | ~]  |     |
| ---- | ---- | ----- | --- | --- | --- | ----- | --- | --- |
| K =  |      |       |     | or  |     | o  o  |     |     |
|      | [ 0  | 0  0  |     |     |     | I     |     |     |
(see Problem 6.\6). Once F and K are chosen, we can then use the MATLAB function l
yap
to solve the Lyapunov equation. Thus the procedure can easily be carried out.
8.6.3  Canonical-Form Method
We introduced in the preceding subsections two methods of computing a feedback gain matrix
to achieve arbitrary eigenvalue assignment. The methods are relatively simple: however, they
will not reveal the structure of the resulting feedback system. In this subsection. we discuss
a different design that will reveal the effect of state feedback on the transfer matrix. We also
give a transfer matrix interpretation of state feedback.
In  this design. we  must transform (A. B)  into a controllable canonical fomL  It is an
extension of Theorem S.2 to the multi variable case. Although the basic idea is the same, the
procedure can become very involved. Therefore we will skip the details and present the final
result. To simplify the discussion. we assume that (8.56) has dimension 6. two inputs. and two
outputs. We first search linearly independent columns of C =  [B  AB  ...  A5B] in order from
left to right. It is assumed that its controllability indices are J.lI  =  4 and J.l~  =  2. Then there
x
exists a nonsingular matrix P and  = Px will transform (8.56) into the controllable cJnonical
form
-Q'122
| -alii   | -Q'II~  | -0' II)  | - 0' II~  |     | -at:!1       |         |     |     |
| ------- | ------- | -------- | --------- | --- | ------------ | ------- | --- | --- |
|         | 0       | 0        | 0         |     | 0            | 0       |     |     |
| 0       |         | 0        | 0         |     | 0            | 0       |     |     |
| x=      |         |          |           |     |              |         | Ix  |     |
| 0       | 0       |          | 0         |     | 0            | 0       |     |     |
| -0'211  | -0'211  | -0']13   | -0'214    |     | -Cl'::!::!1  | -0'222  |     |     |
| o       | o       | o        | o         |     |              | o       |     |     |

8.7 State Estimators-Multivariable Case 263
[DheH(S) + (Die + K)L(s)] v(s) = res)
Substituting this into (S.69) yields
yes) = N(s) [DheH(S) + (Die + K)L(s)]-1 reS)
Thus the transfer matrix from r to y is
Gf(S) = N(s) [DheH(S) + (Die + K)L(sW I (8.71)
The state feedback changes the plant transfer matrix N(s)D-I (s) to the one in (S.72). We see
that the numerator matrix N(s) is not affected by the state feedback. Neither are the column
degree H(s) and the column-degree coefficient matrix Dhe affected by the state feedback.
However, all coefficients associated with L(s) can be assigned arbitrarily by selecting a K.
This is similar to the SISO case.
It is possible to extend the robust tracking and disturbance rejection discussed in Section
8.3 to the multi variable case. It is simpler, however, to do so by using coprime fractions:
therefore it will not be discussed here.
8.7 State Estimators-Multivariable Case
All discussion for state estimators in the single-variable case applies to the multi variable
case; therefore the discussion will be brief. Consider the n-dimensional p-input q-output state
equation
x
= Ax+Bu
(8.73)
y = Cx
The problem is to use available input u and output y to drive a system whose output gives an
estimate of the state x. We extend (8.40) to the multi variable case as
x = (A - LC)x + Bu + Ly (8.74)
This is a full-dimensional state estimator. Let us define the error vector as
e(l) := x(r) - x(t) (8.75)
Then we have, as in (S.4I).
e
= (A - LC)e (8.76)
If (A, C) is observable. then all eigenvalues of (A - LC) can be assigned arbitrarily by choosing
x
an L. Thus the convergence rate for the estimated state to approach the actual state x can be
as fast as desired. As in the SISO case, the three methods of computing state feedback gain K
in Sections 8.6.1 through 8.6.3 can be applied here to compute L.
Next we discuss reduced-dimensional state estimators. The next procedure is an extension
of Procedure S.RI to the multi variable case.

|        |       |       |        |       | 8.6  State Feedback-Multivariable Case  |     |     | 261    |
| ------ | ----- | ----- | ------ | ----- | --------------------------------------- | --- | --- | ------ |
| I      | b l2  |       |        |       |                                         |     |     |        |
| 0      | 0     |       |        |       |                                         |     |     |        |
| 0      | 0     |       |        |       |                                         |     |     |        |
| +1  0  | 0     | u     |        |       |                                         |     |     | (86~)  |
| 0      | I     |       |        |       |                                         |     |     |        |
| 0      | 0     |       |        |       |                                         |     |     |        |
| [~III  | ~112  | ~113  | ~IIJ,  | ~121  | ~122                                    |     |     |        |
| Y=     |       |       |        |       | ]  X                                    |     |     |        |
| ~211   | ~m    | ~213  | ~214   | ~221  |                                         |     |     |        |
f3222
Note that this form is identical to the one in (7.104).
We  now discuss how  to  find  a feedback  gain matrix to  achieve arbitrary eigenvalue
assignment. From a given set of six desired eigenvalues. we can form
|     |     | +   | 3 +  | 2 +  | +   | +   | +   |     |
| --- | --- | --- | ---- | ---- | --- | --- | --- | --- |
"'I(S) =  (5·  alllS al12S al13S  (114)(s2  a221S  (222)  (8.63 )
Let us select K as
|     |     |         | [~II1-etlll  |     |              | a     |      |     |
| --- | --- | ------- | ------------ | --- | ------------ | ----- | ---- | --- |
|     | [~  | bI2]-1  |              |     | alll - al12  | a113- | 113  |     |
K=
1
|     |     |     | et211  | - a211  | a'l11 - Ct212  | 0'213 - Ct213  |     |     |
| --- | --- | --- | ------ | ------- | -------------- | -------------- | --- | --- |
|     |     |     | all.-  | a I14   | -a121          | -aI"           | ]   |     |
(S.64)
|     |     |     | -       |        | -           |                   |     |     |
| --- | --- | --- | ------- | ------ | ----------- | ----------------- | --- | --- |
|     |     |     | C(~14 - | Ct214  | anI - a22l  | a22:::!  - Ct222  |     |     |
Then it is straightforward to verify the following
-a
|     |     |        |        |     |             | 0   | 0   |     |
| --- | --- | ------ | ------ | --- | ----------- | --- | --- | --- |
|     |     | -alii  | -a112  |     | 113  -all.  |     |     |     |
o
|     |     |     | 0   | 0   |     | 0   | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     | o   |     |     | o   |     |     |     |
|     |     |     |     | 0   |     | 0   | 0   |     |
(8.65)
| A.-BK=  |     | o      |         |         | o       |        |          |     |
| ------- | --- | ------ | ------- | ------- | ------- | ------ | -------- | --- |
|         |     |        | 0       |         |         | 0      | 0        |     |
|         |     | -alII  | -0'212  | -£¥213  | -Q'214  | -a221  | - CX222  |     |
|         |     | o      | O.      | 0       | 0       |        | 0        |     |
Because (A. - BK) is block triangular. for any alii, i =  1.2. 3, 4, its characteristic polynomial
equals the product of the characteristic polynomials of the two diagonal blocks of orders 4
and 2. Because the diagonal blocks are of companion form. we conclude that the characteristic
polynomialof(A.-BK)equa!stheonein(S.63).IfK =  KP.then(A.-BK) =  P(A-BK)P- l
Thus the feedback gain K =  KP will place the eigenvalues of (A - BK) in the desired locations.
This establishes once again Theorem 8.M3.
Unlike the single-input case. where the feedback gain is unique. the feedback gain matrix
in the multi-input case is not unique. For example. the K in (8.64) yields a lower block-triangular
matrix in (A.  - 13K). It is possible to select a different K to yield an upper block-triangular
matrix or a block-diagonal matrix. Furthermore, a different grouping of (8.63) will again yield
a different K.

,
262  STATE FEEDBACK AND STATE ESTIMATORS
8.6.4  Effect on Transfer Matrices'
In the single-variable case. state feedback can shift the poles of a plant transfer function g(s) to
any positions and yet has no effect on the zeros. Or, equivalently, state feedback can change the
denominator coefficients, except the leading coefficient I, to any values but has no effect on the
numerator coefficients. Although we can establish a similar result for the multi variable case
from (8.62) and (8.65), it is instructive to do so by using the result in Section 7.9. Following
| the notation in Section 7.9, we express (;(s) = C(sI - |     |     |     |     |     | A)-IB as  |     |     |     |
| ------------------------------------------------------ | --- | --- | --- | --- | --- | --------- | --- | --- | --- |
=
|     |     |     | (;(s)  | N(s)D-I (s)  |     |     |     |     | (8.66)  |
| --- | --- | --- | ------ | ------------ | --- | --- | --- | --- | ------- |
or
|     |     |     | yes)  | =   |     |     |     |     | (8.67)  |
| --- | --- | --- | ----- | --- | --- | --- | --- | --- | ------- |
N(~)D-I (s)u(s)
where N(s) and D(s) are right coprime and D(s) is column reduced. Define
|     |     |     |     |           | =      |     |     |     | (8.68)  |
| --- | --- | --- | --- | --------- | ------ | --- | --- | --- | ------- |
|     |     |     |     | D(s)v(s)  | fits)  |     |     |     |         |
as in (7.93). Then we have
|     |     |     |     | yes) = N(s)v(s)  |     |     |     |     | (8.69)  |
| --- | --- | --- | --- | ---------------- | --- | --- | --- | --- | ------- |
Let H(s) and L(s) be defined as in (7.91) and (7.92). Then the state vector in (8.62) is
=
|     |     |     |     | xes)  L(s)v(s)  |     |     |     |     |     |
| --- | --- | --- | --- | --------------- | --- | --- | --- | --- | --- |
Thus the state feedback becomes, in the Laplace-transform domain,
(8.70)
|     |     | fits) =  | res) - | Kx(s) =  | res) - | KL(s)v(s)  |     |     |     |
| --- | --- | -------- | ------ | -------- | ------ | ---------- | --- | --- | --- |
and can be represented as shown in Fig. 8.11.
Let us express D(s) as
|     |     |     | D(s) = Dh,·H(S)  |     | +   |     |     |     | (8.71)  |
| --- | --- | --- | ---------------- | --- | --- | --- | --- | --- | ------- |
DlcL(s)
Substituting (8.71) and (8.70) into (8.68) yields
+
|     |     | [DhcH(S)  | DlcL(s)] yes) =  |     | res) - |     | KL(s)v(s)  |     |     |
| --- | --- | --------- | ---------------- | --- | ------ | --- | ---------- | --- | --- |
which implies
|            | ..  |     |       |     |     |       | Figure 8.11  | Transfer matrix  |     |
| ---------- | --- | --- | ----- | --- | --- | ----- | ------------ | ---------------- | --- |
| +   oilS)  |     |     | VIS)  | ..  |     | y(S)  | ,            |                  |     |
r(s) ..
|     |     | D-l (5)  |     | N(s)  |     | ,   | interpretation of state feedback.  |     |     |
| --- | --- | -------- | --- | ----- | --- | --- | ---------------------------------- | --- | --- |
rI
..
~
~
i(s)
|     |     | ¢::  | ¢-    |     |     |     |     |     |     |
| --- | --- | ---- | ----- | --- | --- | --- | --- | --- | --- |
|     | K   |      | L(s)  |     |     |     |     |     |     |
3. This subsection may be skipped without loss of continuity. The material in Section 7.9 is needed to study this
subsection.

264 STATE FEEDBACK AND STATE ESTI,\MTORS
Procedure 8.MRI
e). e
Consider the /I·dimensional q·output observable pair (A. It is assumed that has rank q.
1. Select an arbitrary (/I - q) X (11 - q) stable matrix F that has no eigenvalues in common with those
of A.
2. Select an arbitrary (II - q) X q matrix L such that (F. L) is controllable.
3. Solve the unique (11 - q) x 11 matrix T in the Lyapunov equation TA - FT = LC.
-l. If the square matri.' of order II
[~J
p = (8.77)
is singular. go back to Step 2 and repeat the p~)cess. If Pis nonsingular. then the (11 - q )-dimensional
state equation .
z = Fz + TBu + Ly (8.78)
[~r [~J
x= (8.79)
generates an estimate of x.
We first justify the procedure. We write (8.79) as
[~J [~Jx
=
which implies y = ex and z = Tx. Clearly y is an estimate of Cx. We now show that z is an
estimate of Tx. Let us defi ne
e:= z - Tx
Then we have
e = z - Ti = Fz + TBu + Lex - TAx - TBu
= Fz + (Le - TA)x = F(z - Tx) = Fe
If F is stable. then e( T) ..... 0 as T ..... x. Thus z is an estimate of Tx.
Theorem 8.M6
If A and F have no common eigenvalues. then the square matrix
[~]
P:=
"here T is the unique solution of TA - FT = LC. is nonsingular only if (A. C) is observable and
(F. L) is controllable.
This theorem can be proved by combining the proofs of Theorems 8.1\,14 and 8.6. Unlike
Theorem 8.6, where the conditions are necessary and sufficient for P to be nonsingular. the

Problems  267
8.6  Consider a system with transfer function
+
|     | '( )    | (S  - I)(s                         | 2)        |
| --- | ------- | ---------------------------------- | --------- |
|     | g s  =  | -c----'-c:-c---'--'-.".,...--'--'- |           |
|     |         | +                                  | +         |
|     |         | (s  I)(s -                         | 2)(s  3)  |
Is it possible to change the transfer function to
|     |     | ,  I  |     |
| --- | --- | ----- | --- |
gj(s) =-
s+3
by state feedback? Is the resulting system BIEO stable? Asymptotically stable?
8.7  Consider the continuous-time state equation
|     | 1I  -2]  |     | [I]  |
| --- | -------- | --- | ---- |
[
x=
|     | ~   | ~  ~  x+  | ~   |
| --- | --- | --------- | --- |
It
|     | Y = [2  0  | O]x  |     |
| --- | ---------- | ---- | --- |
Let u = pr -
kx. Find the feedforward gain p and state feedback gain k so that the
resulting system has eigenvalues -2 and -I ± j 1 and will track asymptotically any step
reference input.
8.8  Consider the discrete-time state equation
|     | I   | 1   |     |
| --- | --- | --- | --- |
;2]
[~
+
| x[k  | I] =  0  | I  x[k]  | +  ]  u[k]  |
| ---- | -------- | -------- | ----------- |
[
o
0
[2  0
|     | y[k] =  | O]x[k]  |     |
| --- | ------- | ------- | --- |
Find the state feedback gain so that the resulting system has all eigenvalues at :  =  O.
Show that for any initial state, the zero-input response of the feedback system becomes
identically zero for k ?': 3.
8.9  Consider the discrete-time state equation in Problem 8.8. Let u[k]  =  pr[k] - kx[k],
where p is a feedforward gain. For the k in Problem 8.8. find a gain p so that the output
will track any step reference input. Show also that y[k] =  r[kJ for k ?':  3. Thus exact
tracking is achieved in a finite number of sampling periods instead of asymptotically.
This is possible if all poles of the resulting system are placed at : = O. This is called the
dead-beat design.
8.10  Consider the uncontrollable state equation
o  J]x{}
[~
o
x
|     | =  o  2  |     |     |
| --- | -------- | --- | --- |
|     | 0        | -I  |     |
|     | o  0     | o   |     |
=
Is it possible to find a gain k so that the equation with state feedback u  r - kx has
eigenvalues -2, -2. -I, -I? Is it possible to have eigenvalues -2, -2, -2, -I'? How
about -2, -2, -2, -2? Is the equation stabilizable?
I

|     |     | B.8  | Feedback irom Estimated States-Multi variable Case  |     |     |     |     |     | 265  |
| --- | --- | ---- | --------------------------------------------------- | --- | --- | --- | --- | --- | ---- |
conditions here are only necessary. Given (A. e ). it is possible to construct a controllable pair
(F. L) so that P is singular. However. after selecting F. if L is selected randomly and if (F. L)
is controllable. it is believed that the probability for P to be nonsingular is I.
8.8 Feedback from Estimated States-Multivariable Case
This section will extend the separation propeny discussed in Section 8.5 to the multi\ariable
case. We use the reduced-dimensional  state estimator: therefore  the development is more
complex.
Consider the n-dimensional state equation
|     |     |     | x = Ax  |     | +  Bu  |     |     |     |     |
| --- | --- | --- | ------- | --- | ------ | --- | --- | --- | --- |
(8.80)
y =  ex
and the (n - q)-dimensional state estimator in (8.78) and (8.79). First we compute the inverse
of Pin (8.77) and then partition itas [QI  Qcl. whereQI is 11  x q andQ2 iSIl x (11 -q): that is.
|     |     |     | Q~1[~]=QIC |     | +   | Q~T = I  |     |     |     |
| --- | --- | --- | ---------- | --- | --- | -------- | --- | --- | --- |
(8.81 )
[QI
Then the (n - q)-dimensional state estimator in (8.78) and (8.791 can be wrillen as
|     |     |     | z     | +       | +    |     |     |     |         |
| --- | --- | --- | ----- | ------- | ---- | --- | --- | --- | ------- |
|     |     |     | = Fz  | TBu     |      | Ly  |     |     | (882)   |
|     |     |     | x =   | QIY -t- | Qcz  |     |     |     | (8.83)  |
If the original state is not available for state feedback. we apply the feedback gain matrix to x
to yield
|     |     | u =  | r - Kx =  | r - | KQIY - | KQcz  |     |     | (8.8-1)  |
| --- | --- | ---- | --------- | --- | ------ | ----- | --- | --- | -------- |
Substituting this into (8.80) and (8.82) yields
|     | x  =  | Ax + B(r -     | KQ1ex - |          | KQczJ  |     |     |     |         |
| --- | ----- | -------------- | ------- | -------- | ------ | --- | --- | --- | ------- |
|     | =     | (A - BKQIC)x - |         | BKQ2Z +  |        | Br  |     |     | (8.85)  |
z
+ LCx
|     | =   | Fz + TB(r - | KQI ex - |     | KQ~z)  |     |     |     |     |
| --- | --- | ----------- | -------- | --- | ------ | --- | --- | --- | --- |
+
|     | =   | (LC - | TBKQIC)x  |     | (F - | TBKQ2)Z -'- | TBr  |     | (886)  |
| --- | --- | ----- | --------- | --- | ---- | ----------- | ---- | --- | ------ |
They can be combined as
x]
| [   | [A - |       | BKQ1C   |     | -BKQ~  |        |        |     |        |
| --- | ---- | ----- | ------- | --- | ------ | ------ | ------ | --- | ------ |
|     |      |       |         |     |        | ] [x]  | [B]    |     |        |
| i   | -    |       |         |     | TBKQ~  |        |        |     |        |
|     |      | Le -  | TBKQ1C  | F - |        | z      | +  TB  | r   |        |
|     |      | 1[:]  |         |     |        |        |        |     | (887)  |
y=[C 0
This On - q )-dimensional state equation describes the feedback system in Fig. 8.8. As in the
SISO case. let us carry out the following equivalence transformation

266  STATE FEEDBACK AND STATE ESTIMATORS
[z
|          | ~\x]  | [~~  | In~J  |      |
| -------- | ----- | ---- | ----- | ---- |
| [ :] ==  |       | ==   |       | [:]  |
==
After some manipulation and using TA - FT  LC and (8.81). we can finally obtain the
following equivalent state equation
| [:]==[A-OBK  |     | -B~Q2][:]+[:]r  |     |     |
| ------------ | --- | --------------- | --- | --- |
(8.88)
| ==  [C  | OJ [:]  |     |     |     |
| ------- | ------- | --- | --- | --- |
y
This equation is similar to (8.55) for the single-variable case. Therefore all discussion there
applies, without any modification, to thb multi variable case. In other words, the design of a
state feedback and the design of a state estimator can be carried out independently. This is
the separation property. Furthermore, all eigenvalues of F are not controllable from r and the
transfer matrix from r to y equals
A BK)-IB
==
|     |     | C(sI - +  |     |     |
| --- | --- | --------- | --- | --- |
Gf(s)
8.1  Given
==
| X==[~I  | :]x+[~]u  |     | y   | [I  IJx  |
| ------- | --------- | --- | --- | -------- |
find the state feedback gain k so that the state feedback system has -I and - 2 as its
eigenvalues. Compute k directly without using any equivalence transformation.
8.2  Repeat Problem 8.1 by using (8.13).
8.3  Repeat Problem 8.1 by solving a Lyapunov equation.
8.4  Find the state feedback gain for the state equation
~2]x+[~]1I
| X==[i  |     | :   |     |     |
| ------ | --- | --- | --- | --- |
so that the resulting system has eigenvalues - 2 and -I ± j I. Use the method you think
is the simplest by hand to carry out the design.
8.5  Consider a system with transfer function
| •   |     | (s-l)(s+2)  |     |     |
| --- | --- | ----------- | --- | --- |
==
|       |     | +            | +   |     |
| ----- | --- | ------------ | --- | --- |
| g(s)  | (s  | I)(s - 2)(5  | 3)  |     |
Is it possible to change the transfer function to
s -
I
==  -----
8f(s)
by state feedback? Is the resulting system smo stable? Asymptotically stable?

268  STATE FEEDBACK AND STATE ESTIMATORS
8.11  Design a full-dimensional and a reduced-dimensional state estimator for the state equa
tion in Problem 8.1. Select the eigenvalues of the estimators from {-3, -2 ± j21.
8.12  Consider the state equation in Problem 8.1. Compute the transfer function from r to y of
the state feedback system. Compute the transfer function from r to y if the feedback gain
is applied to the estimated state of the full-dimensional estimator designed in Problem
8.11. Compute the transfer function from r  to y if the feedback gain is applied to the
estimated state of the reduced-dimensional state estimator also designed in Problem 8.11.
Are the three overall transfer functions the same?
8.13  Let
| 0  I 0 0]  |     | [0  0]  |
| ---------- | --- | ------- |
| 0 \ 0      | B=  | 0 0     |
o
A=
| [   | :2  |       |
| --- | --- | ----- |
| -3  | 3   | 1  2  |
20002
Find two different constant mauices K such that (A - BK) has eigenvalues -4 ± 3 j
and -5 ±4j.

9.1 Introduction 271
The plants studied in this chapter will be limited to those describable by strictly proper
rational functions or matrices. We also assume that every transfer matrix has full rank in the
sen.:;e that if C(s) is q x p, then it has a q x q or p x p submatrix with a nonzero determinant.
If G(s) is square, then its determinant is nonzero or its inverse exists. This is equi valent to
the assumption that if (A. B, C) is a minimal realization of the transfer matrix. then B has full
column rank and C has full row rank.
The design to be introduced in this chapter is based on coprime polynomial fractions
of rational matrices. Thus the concept of coprimeness and the method of computing coprime
fractions introduced in Sections 7.1 through 7.3 and 7.6 through 7.8 are needed for studying
this chapter. The rest of Chapter 7 and the entire Chapter 8. however, are not needed here. In
this chapter, we will change the design problem into solving sets of linear algebraic equations.
Thus the method is called the linear algebraic method in Reference [7].
For convenience, we first introduce some terminology. Every transfer function g(s) =
N(s)j D(s) is assumed to be a coprime fraction. Then every root of D(s) is a pole and every
root of N (s) is a zero. A pole is called a stable pole if it has a negative real part; an unstable
pole if it has a zero or positive real part. We also define
• Minimum-phase zeros: zeros with negative real parts
• Nonminimum-phase zeros: zeros with zero or positive real parts
Although some texts call them stable and unstable zeros. they have nothing to do with stability.
A transfer function with only minimum-phase zeros has the smallest phase among all transfer
functions with the same amplitude characteristics. See Reference [7. pp. 284-285]. Thus we
use the aforementioned terminology. A polynomial is called a HUnI'it:; polynomial if all its
roots have negative real parts.
9.1.1 Compensator Equations-Classical Method
Consider the equation
.' . +
A(s)D(s) B(s)N(s) = F(s) (9.4)
where D(s). N(s). and F(s) are given polynomials and A(s) and B(s) are unknown poly
nomials to be solved. Mathematically speaking. this problem is equivalent to the problem of
+
solving integer solutions A and B in AD BN = F, where D. N. and F are given integers.
This is a very old mathematical problem and has been associated with mathematicians such
. as Diophantine. Bezout. and Aryabhatla.' To avoid controversy, we follow Reference [3J and
call it a compensator equation. All design problems in this chapter can be reduced to solving
compensator equations. Thus the equation is of paramount importance.
We first discuss the existence condition and general solutions of the equation. What will
be discussed, however. is not needed in subsequent sections and the reader may glance through
this subsection.
1. See Reference [21. last page of Preface I.

Chapter
Pole Placement and
Model Matching
9.1 Introduction
We first give reasons for introducing this chapter. Chapter 6 discusses state-space analysis
(controllability and observability) and Chapter 8 introduces state-space design (state feedback
and state estimators). In Chapter 7 coprime fractions were discussed. Therefore it is logical to
discuss in this chapter their applications in design.
One way to introduce coprime fraction design is to develop the Bezout identity and to
parameterize all stabilization compensators. See References [3. 6, 9, 13.20). This approach
is important in some optimization problems but is not necessarily convenient for all designs.
See Reference [8). We study in this chapter only designs of minimum-degree compensators
to achieve pole placement and model matching. We will change the problems into solving
linear algebraic equations. Using only Theorem 3.2 and its corollary. we can establish all
needed results. Therefore we can bypass the Bezout identity and some polynomial theorems
and simplify the discussion.
Most control systems can be fonnulated as shown in Fig. 8.1. That is. given a plant with
input and output y and a reference signal r. design an overall system so that the output v
II
will follow the reference signal r as closely as possible. The plant input II is also called the
actuating signal and the plant output v. the controlled signal. If the actuating signalll depends
only on the reference signal r as shown in Fig. 9.1(a). it is called an open-loop control. If 11
depends on rand v. then it is called a closed-loop or feedback control. The open-loop control
is. in general. not satisfactory if there are plant parameter variations due to changes of load.
environment. or aging. It is also very sensitive to noise and disturbance. which often exist in
the real world. Therefore open-loop control is used less often in practice.
269

,
,
270 POLE PLACEMENT AND MODEL MATCHING
There are many possible feedback configurations. The simplest is the unity-feedback
configuration shown in Fig. 9.I(b) in which the constant gain p and the compensator with
transfer function C(s) are to be designed. Clearly we have
u(s) = C(s)[pr(s) - yes)] (9./)
Because p is a constant. the reference signal r and the plant output y drive essentially the same
compensator to generate an acruating signal. Thus the configuration is said to have one degree
of freedom. Clearly the open-loop configuration also has one degree of freedom.
The connection of state feedback and state estimator in Fig. 8.8 can be redrawn as shown
in Fig. 9.I(c). Simple manipulation yields
_ I _ Cz(s)_
= + + (9.2)
u(s) 1 C (S/(5) - 1 C (s) yes)
t t
We see that rand y drive two independent compensators to generate au. Thus the configuration
is said to have two degrees of freedom.
A more natural two-degree-of-freedom configuration can be obtained by modifying
(9.1) as
u(s) = Ct(s)r(s) - Cz(s)y(s) (9.3)
and is plotted in Fig. 9.1 (d). This is the most general control signal because each of rand y
drives a compensator. which we have freedom in designing. Thus no configuration has three
degrees of freedom. There are many possible two-degree-of-freedom configurations; see. for
example. Reference [12]. We call the one in Fig. 9./(d) the two-parameter configuration;
the one in Fig. 9.1(c) the controller-estimator or plant-input-olltput-feedback configuration.
Because the two-parameter configuration seems to be more natural and more suitable for
practical application. we study only this configuration in this chapter. For designs using the
plant-input-output-feedback configuration. see Reference [6].
H
~ ~
Cis) 8(s)
( a)
(b)
r + u y " y
8(s) 8(5)
C,ls)
c, t-I. _-
~-,I (5)
(e) (d)
Figure 9.1 Control configurations.

272  POLE PLACEMENT AND MODEL MATCHING
Theorem 9.1
Given  polynomials  D(s) and  N(s).  polynomial  solutions  A(s) and  B(s)  exist in  (9.4)  for  any
polynomial F(s) ifandonly if D(s) and N(s) are coprime.
+
Suppose D(s) and N (.I) are not coprime and contain the same factors  a. Then the
+ a will appear in F(s). Thus if F(s) does not contain the factor. no solutions exist in
factors
(9.4). This shows the necessity of the theorem.
If D(s) and N(s) are coprime, there exist polynomials A(s) and B(s) such that
|     |     |     |     | -   | -   |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
+
|     |     |     |     | A(s)D(s)  | B (s)N(s) =  |     | I   |     |     | (9.5)  |
| --- | --- | --- | --- | --------- | ------------ | --- | --- | --- | --- | ------ |
Its matrix version is called the Be:ollt identity in Reference [13]. The polynomials A(s) and
B(s) can be obtained by the Euclidean algorithm and will not be discussed here. See Reference
|     |     |     |     |     | =   |     | =   |     | =   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
[6, pp. 578-580]. For example, if D(s)  .1 2  I and N(s)  s - 2, then A(s)  1/3 and
-
+
B(s)  =  -(.I  2)/3 meet (9,5). For any polynomial F(s), (9.5) implies
+
|     |     | F(s)A(s)D(s)  |     |     | F(s)B(s)N(s) =  |     | F(s)  |     |     | (9.6)  |
| --- | --- | ------------- | --- | --- | --------------- | --- | ----- | --- | --- | ------ |
| =   |     |               |     | =   |                 |     |       |     |     |        |
Thus A(s)  F(s)A(s) and B(s)  F(s)B(s) are solutions. This shows the sufficiency of the
theorem.
Next we discuss general solutions. For any D(s) and N(s), there exist two polynomials
A(s) and 8(5) such that
|     |     |     |     | ,   | ,                |     |     |     |     |        |
| --- | --- | --- | --- | --- | ---------------- | --- | --- | --- | --- | ------ |
|     |     |     |     |     | +  B(s)N(s) = 0  |     |     |     |     | (9.7)  |
A(s)D(s)
Obviously A(s)  =  -N(s) and 8(.1)  =  D(s) are such solutions. Then for any polynomial
Q(s),
|     |     | -   |     |     |     |     | -   |       |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ----- | --- | --- |
|     |     |     | +   |     | ,   | =   |     | +  ,  |     |     |
A(s) =  A (s)F(s)  Q(s)A (s)  B(s)  B (s)F(s)  Q(s)B (s)  (9.8)
are general solutions of (9.4). This can easily be verified by substituting (9.8) into (9.4) and
using (9.5) and (9.7).
|     |     |     | =   |     | =   |     | =   | +  2 +  | +   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ------- | --- | --- |
EXAMPLE 9.1  Given D(s)  .12  - 1. N(s)  .I - 2. and F(s)  .1.1  45 6.1  4. then
1
|     |       | =   | +     | 2 +  | +  +     |           | +   |     |     |     |
| --- | ----- | --- | ----- | ---- | -------- | --------- | --- | --- | --- | --- |
|     | A(s)  |     | (5.1  | 45   | 6.1  4)  | Q(s)( -5  |     | 2)  |     |     |
-1(.1
|     | B(s) =  |     |     | + 2)(.1 3  | 2  +6.1 +4) +  |     |        | 2  I)  |     | (9 9)  |
| --- | ------- | --- | --- | ---------- | -------------- | --- | ------ | ------ | --- | ------ |
|     |         |     |     |            | +4s            |     | Q(S)(5 | -      |     |        |
for any polynomial Q(s), are solutions of (9.4).
Although the classical method can yield general solutions, the solutions are not necessarily
convenient to use in design. For example, we may be interested in solving A(s) and B(5) with
least degrees to meet (9.4). For the polynomials in Example 9.1, after some manipulation, we
|                      |      | +   | +                             |     |     |     |     |     |     |     |
| -------------------- | ---- | --- | ----------------------------- | --- | --- | --- | --- | --- | --- | --- |
| tind that if Q(s) =  | (52  | 65  | 15)/3, then (9.9) reduces to  |     |     |     |     |     |     |     |
+
|     |     | A(s) = .I  |     | 34/3  | B(s) =  | (-225 - |     | 23)/3  |     | (910)  |
| --- | --- | ---------- | --- | ----- | ------- | ------- | --- | ------ | --- | ------ |

9.2 Unity-Feedback Configuration-Pole Placement 275
i=
number of rows increases by 2. Because Dn 0, the new D row is linearly independent of its
preceding rows. Thus the 2(n + I) x (2n + I) matrix Sn has rank (2n + I) (full column rank).
Repeating the argument. we conclude that if D(s) and N (s) are coprime and if m ::: n - 1.
then the matrix Sm in (9.14) has full column rank.
>
Theorem 9.2
Consider the unity-feedback system shown in Fig. 9.I(b). The plant is described by a strictly proper
= =
transferfunctiong(s) N(s)/D(s) with N(s) and D(s) coprimeanddeg N(s) < deg D(s) n.
+
Let m ::: n - I. Then for any polynomial F(s) of degree (n m), there exists a proper compensator
C (s) = B(s) / A (s) of degree m such that the overall transfer function equals
goes) = pN(s)B(s) = pN(s)B(s)
+
A(s)D(s) B(s)N(s)
Furthermore, the compensator can be obtained by solving the linear algebraic equation in (9.13).
As discussed earlier, the matrix Sm has full column rank for m ::: n - I: therefore, for
+ +
any (n m) desired poles or. equivalently, for any F(s) of degree (n m), solutions exist in
i=
(9.13). Next we show that B(s)/A(s) is proper or Am O. If N(s)/D(s) is strictly proper,
then N = 0 and the last equation of (9.13) reduces to
n
+
AmDn BmNn = DnAm = Fn+m
Because F(s) has degree (n + ml, we have Fn+m i= 0 and, consequently, Am i= O. This
establishes the theorem. If m = n - I, the compensator is unique: if m > n - I. compensators
are not unique and free parameters can be used to achieve other design objecti ves, as we will
discuss later.
9.2.1 Regulation and Tracking
Pole placement can be used to achieve the regulation and tracking discussed in Section 8.3. In
the regulator problem. we have r = 0 and the problem is to design a compensator C (s) so that
the response excited by any nonzero initial state will die out at a desired rate. For this problem,
if all poles of goes) are selected to have negative real parts, then for any gain p, in particular
p = I (no feedforward gain is needed). the overall system will achieve regulation.
We discuss next the tracking problem. Let the reference signal be a step function with
magnitude a. Then res) = a/s and the output .Yes) equals
yes) = go(s)r(s) = go(s)~
s
If galS) is BIBO stable, the output will approach the constant g,,(O)a (Theorem 5.2). This can
also be obtained by employing the final-value theorem of the Laplace transfonn as
lim y(t) = lim s)'(s) = go(O)a
f-X s-O
Thus in order to track asymptotically any step reference input. goes) must be BIBO stable and
go(O) = 1. The transferfunction from r to y in Fig. 9.I(b) is goes) = pN(s)B(s)/ F(s). Thus
we have

|     | 9.2  | Unity-Feedhack Configuration-Pole Placement  |     |     | 273  |
| --- | ---- | -------------------------------------------- | --- | --- | ---- |
They are the least-degree solutions of Example 9.1. In  this chapter,  instead of solving the
compensator equation directly as shown. we will change it into solving a set of linear algebraic
equations as in Section 7.3. By so doing. we can bypass some polynomial theorems.
9.2  Unity-Feedback Configuration-Pole Placement
Consider the unity-feedback system shown in Fig. 9.l(b). The plant transfer function g(s) is
assumed to be strictly proper and of degree  The problem is to design a proper compensator
fl.
+
C(s) ofleast possible degree m so that the resulting overall system has any set of n  III desired
poles. Because all transfer functions are required to have real coefficients, complex conjugate
poles must be assigned in pairs. This will be a standing assumption throughout this chapter.
Let g(s) =  N(s)/ D(s) and C(s) =  8(5)/ A(s). Then the overall transfer function from
r to y in Fig. 9.I(b) is
8(s) N(s)
|        | =            | =   |                 |     |     |
| ------ | ------------ | --- | --------------- | --- | --- |
| goes)  | pC(s)g(s)    |     | PA(;)"i5(;)     |     |     |
|        | 1+ C(s)g(s)  |     | 1-'- 8(5) N(s)  |     |     |
,  A(s) D(s)
p8(s)N(s)
(911 )
A(s)D(s) + 8(s)N(s)
In pole assignment, we are interested in assigning all poles of goes) or, equivalently. all roots
+
of A(s)D(s)  8(s)N(s). In  this design. nothing is said about the zeros of g"(s). As we
can see from (9.11), the design not only has no effect on the  plant zeros (roots of N (5»)
but also introduces new zeros (roots of 8(s»  into the overall transfer function. On the other
hand, the poles of the plant and compensator are shifted from D(s) and A(s) to the roots of
+
A(s)D(s)  8(s)N(s). Thusfeedback call shift poles bllt has no effect on :eros.
Given a set of desired poles, we can readily form a polynomial F(s) that has the desired
poles as its roots. Then the pole-placement problem becomes one of solving the polynomial
equation
|     | A(s)D(s) + 8(s)N(s) =  |     | F(s)  |     | (9.12)  |
| --- | ---------------------- | --- | ----- | --- | ------- |
Instead of solving (9.12) directly. we will transform it into solving a set of linear algebraic
|     | =   |     | ="  | =   |     |
| --- | --- | --- | --- | --- | --- |
equations. Let deg N (5)  < deg D(s)  nand deg 8(s)  deg A(s)  m. Then F(s) in (9.12)
+
has degree at most Il  m. Let us write
D(s) =  Do + DIs + Des: + ... + D"s"
D"  1= 0
No + Nls + Nes: + ... + N"s"
N(s) =
Ao + Als + A",: + ... + Amsm
A(s) =
|         | Bo + 8 s + 8:52 + ... + 8 |          |           |     |     |
| ------- | ------------------------- | -------- | --------- | --- | --- |
| 8(s) =  |                           |          | s"'       |     |     |
|         | 1                         |          | m         |     |     |
|         | Fo + Fis + F              | + ... +  |           |     |     |
| F(s) =  |                           | s:       | Fn+msn+m  |     |     |
2
where all coefficients are real constants. not necessarily nonzero. Substituting these into (9.12)
and matching the coefficients of like powers of s, we obtain

274  POLE PLACEMENT AND MODEL MATCHING
+
|     |     |     | AoDo  | BoNo =  Fa  |     |
| --- | --- | --- | ----- | ----------- | --- |
=
| AoDI  | +  BaNI  | +   | AIDo  | +  BINo  FI  |     |
| ----- | -------- | --- | ----- | ------------ | --- |
+
|     |     | AmDn  |     | BmNn =  Fn+m  |     |
| --- | --- | ----- | --- | ------------- | --- |
+  +
There are a total of (n  m  1) equations. They can be arranged in matrix form as
=
[Ao  Bo  AI  BI  '"  Am  BmlSm  [Fo  FI  F2  ...  Fn+ml  (9.13)
with
|     |         | ,  I ..  |     | 0      | 0   |
| --- | ------- | -------- | --- | ------ | --- |
|     | Do  DI  |          | Dn  |        |     |
|     | No  NI  |          | Nn  | 0      | 0   |
|     | 0  Do   |          | Dn- | I  D"  | 0   |
|     | 0  No   |          | Nn- | I  Nn  | 0   |
Sm:=  I  (9.14 )
|     | o  o  |     |     | o   |     |
| --- | ----- | --- | --- | --- | --- |
|     |       |     |     | Do  | Dn  |
|     | o  o  |     |     | o   |     |
|     |       |     |     | No  | N   |
n
If we take the transpose of (9.13), then it becomes the standard form studied in Theorems 3.1
and 3.2. We use the form in (9.13) because it can be extended directly to the matrix case. The
| +   |     | +  +  |     |     |     |
| --- | --- | ----- | --- | --- | --- |
matrix Sm  has 2(m  1) rows and (n  m  1) columns and is formed from the coefficients
of D(s) and N(s). The first two rows are simply the coefficients of D(s) and N(s) arranged
in ascending powers of s. The next two rows are the first two rows shifted to the right by one
position. We repeat the process until we have (m  +  1) sets of coefficients. The left-hand-side
row vector of (9.13) consists of the coefficients of the compensator C(s) to be solved. If C(s)
has degree m, then the row vector has 2(n!  +  I) entries. The right-hand-side row vector of
(9.13) consists of the coefficients of F(s). Now solving the compensator equation in (9.12)
becomes solving the linear algebraic equation in (9.13).
Applying Corollary 3.2, we conclude that (9.13) has a solution for any F(s) if and only
if Sm has full column rank. A necessary condition for Sm to have full column rank is that Sm
is square or has more rows than columns, that is.
|      | +       | +    | +   |                |      |
| ---- | ------- | ---- | --- | -------------- | ---- |
| 2(m  | 1) ~ n  | III  | I   | or  111  ~ 1/  | - I  |
If m < n - I. then Sm does not have full column rank and solutions may exist for some F(s),
but not for every F(s). Thus if the degree of the compensator is less than n - I. it is not possible
to achieve arbitrary pole placement.
=
Ifm  n-!.Sn_1 becornes a square matrix of order 2n. It is the transpose of the Sylves ter
resultant in (7.28) with n = 4. As discussed in Section 7.3, 5,,_1 is nonsingular if and only if
D(s) and N(s) are coprime. Thus if D(s) and N(s) are coprime, then Sn-I has rank 2n (full
column rank). Now if m increases by  !, the number of columns increases by  I but the the

276  POLE PLACEMENT AND MODEL MATCHING
|     |     |     |     |     | •       |     | N(O)B(O)  |        |          | BoNo  |     |     |     |
| --- | --- | --- | --- | --- | ------- | --- | --------- | ------ | -------- | ----- | --- | --- | --- |
|     |     |     |     |     |         |     | =         |        | =        |       |     |     |     |
|     |     |     |     |     | go (0)  |     | P         | F (0)  | P----r;- |       |     |     |     |
which implies
Fa
|     |     |     |     |     |     |     | P=-- |     |     |     |     |     | (9.15)  |
| --- | --- | --- | --- | --- | --- | --- | ---- | --- | --- | --- | --- | --- | ------- |
BoNo
Thus in order to track any step reference input, we require Bo f. 0 and No  f. O. The constant
Bo is a coefficient of the compensator and can be designed to be nonzero. The coefficient No
is the constant term of the plant numerator. Thus if the plant transfer function has one or more
|     | zeros at s  | =   |     |     |     |     |     |     |     |     |     |     |     |
| --- | ----------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
0, then No = 0 and the plant cannot be designed to track any step reference input.
This is consistent with the discussion in Section 8.3.
If the reference signal is a ramp function or r(t) =  0, then using a similar
|     |     |     |     |     |     |     |     |     |     | at, for t  | :::  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---------- | ---- | --- | --- |
argument, we can show that the overall trahsfer function goes) must be BlBO stable and has
the properties go(O)  =  I and g~(O) = 0 (Problems 9.13 and 9.14). This is summarized in the
following.
•  Regulation¢> goes) BIBO stable.
|     | •  Tracking step reference input¢> goes) BlBO stable and go(O) =  |     |     |     |     |     |     |     |     |     | 1.  |        |     |
| --- | ----------------------------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ | --- |
|     |                                                                   |     |     |     |     |     |     |     |     | =   |     | =  O.  |     |
•  Tracking ramp reference input¢> goes) BlBO stable, go(O)  I, and g~(O)
,
EXAMPLE 9.2  Given a plant with transfer function g(s)  = (s - 2)/(S2 - I). find a proper
'1
;i
compensator C(s) and a gain P in the unity-feedback configuration in Fig. 9.1(b) so that the
;!  output y will track asymptotically any step reference input.
The plant transfer function has degree n = 2. Thus if we choose m =  I, all three poles of
",
.~   the overall system can be assigned arbitrarily. Let the three poles be selected as -2. -I ± j 1;
,
,
,
they spread evenly in the sector shown in Fig. 8.3(a). Then we have
-j
|     |         |     |       |     |         |     |         |     |      | ,     |         | 3 +     |     |
| --- | ------- | --- | ----- | --- | ------- | --- | ------- | --- | ---- | ----- | ------- | ------- | --- |
|     | F(s) =  |     | +     | +   | +       | +   | j 1) =  |     | +    | +  +  | 2) = s  | 0  +    | +   |
|     |         | (s  | 2)(s  | I   | j l)(s  |     | I -     | (s  | 2)(s | - 2s  |         | 4s- 6s  | 4   |
j
|     |     |     |     |     |     |     | + O· s  | +   |     |     | +   | + O·  |     |
| --- | --- | --- | --- | --- | --- | --- | ------- | --- | --- | --- | --- | ----- | --- |
;:1  We use the coefficients of D(s) =  -I  1 . s2 and N(s) =  -2  1 . s  52 to form
d
]  (9.13) as
.~
|     |     |     |     |     |     | -I  | 0   | I   | 0   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
,~
| ,   |     |     |     |     |     | -2  |     | 0   | 0   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
I
|     |     |     |                |     |     |     |     |     |       |     | 6   | 1]  |     |
| --- | --- | --- | -------------- | --- | --- | --- | --- | --- | ----- | --- | --- | --- | --- |
| J   |     |     | [Ao Bo Al Btl  |     |     |     |     |     | 1=[4  |     | 4   |     |     |
(
| i   |     |     |     |     |     |     | 0  -1  | 0   | I   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | ------ | --- | --- | --- | --- | --- | --- |
j
| ,•   |     |     |     |     |     |     | 0  -2  |     | 0   |     |     |     |     |
| ---- | --- | --- | --- | --- | --- | --- | ------ | --- | --- | --- | --- | --- | --- |
!
1  Its solution is
j
.1  Al =  I  Ao =  34/3  BI  =  -22/3  Bo =  -23/3
1
1
This solution can easily be obtained using the MATLAB function / (slash), which denotes
;  matrix right division. Thus we have"
2. This is the solution obtained in (9.10), This process of solving Ihe polynomial equation in (9.13) is consid<rably
simpler than the procedure discussed in Section 9.1.1.

9.2  Unity-Feedback Configuration-Pole Placement  279
B(s)
|     |     |     | Cis) =  A(s)¢(s)  |     |     |     |
| --- | --- | --- | ----------------- | --- | --- | --- |
as shown in Fig. 9.2(a) will achieve the design. Let us compute the transfer function from
w to y:
N(s)1 D(s)
1+ (8(5)1 A(s)¢(s»)(N(s)1 D(s»
gyw(s) =
|     |     | N(s)A(s)¢(s)  |     |     | N(s)A(s)¢(s)  |     |
| --- | --- | ------------- | --- | --- | ------------- | --- |
+
|     | =  A(s)D(s)¢(s)  |     | B(s)N(s) =  |     |     | l' (s)  |
| --- | ---------------- | --- | ----------- | --- | --- | ------- |
Thus the output excited by wet) equals
=
|     | \'".(s) = g,w(s)w(s)  |     |     | N(s)A(s)¢(s) Nw(s)  |     |     |
| --- | --------------------- | --- | --- | ------------------- | --- | --- |
(9.21)
|     | '   | .   |     | F(s)  |     | Dw(s)  |
| --- | --- | --- | --- | ----- | --- | ------ |
Because all unstable roots of Dw(s) are canceled by ¢(s), all poles of ,vw(s) have negative
real parts. Thus we have y.,(t) -+ 0 as t -+ 00. In other words, the response excited by
w(t) is asymptotically suppressed at the output.
Next we compute the output Yr(s) excited by res):
| _      | _           | _ .  |               | 8(s)N(s)  |              | _   |
| ------ | ----------- | ---- | ------------- | --------- | ------------ | --- |
|        | =           |      | =             |           | +            |     |
| Yr(s)  | gyr(s)r(s)  |      | A(s)D(s)¢(s)  |           | B(s)N(S{(S)  |     |
Thus we have
Yr(s) =
|     | e(s) := res) - |     |     | (1 - | gyr(s»?(s)  |     |
| --- | -------------- | --- | --- | ---- | ----------- | --- |
A(s)D(s)¢(s) Nr(s)
=  (9.22)
|     |     |     | F(s)  | Dr(s)  |     |     |
| --- | --- | --- | ----- | ------ | --- | --- |
Again all unstable roots of Dr(s) are canceled by ¢(s) in  (9.22). Thus  we conclude
|     | -+ 00. Because of linearity, we have yet)  |     |     |     |     | =  +  |
| --- | ------------------------------------------ | --- | --- | --- | --- | ----- |
r(t) - Yr(t) -+ 0 as t  Yw(t)  Yr(t) and
yet) -+ 0 as I  -> 00. This shows asymptotic tracking and disturbance rejection.
r(t) -
From (9.21) and (9.22), we see that even if the parameters of D(s), N(s). A(s). and 8(s)
change, as long as the overall system remains BlBO stable and the unstable roots of Dr (5)
and Dw(s) are canceled by ¢(s), the system still achieve tracking and rejection. Thus the
design is robust:  Q.E.D.
This robust design consists of two steps. First find a model II ¢ (s) of the reference signal
and disturbance and then carry out pole-placement design. Inserting the model inside the loop
is referred to as the internal model principle. If the model II ¢ (5) is not located in the forward
path from w to Y and from r to e, then ¢(s) will appear in the numerators of gyw(s) and g,,(s)
(see Problem 9.7) and cancel the unstable poles of w(s) and 1'(5), as shown in (9.21) and
(9.22). Thus the design is achieved by unstable pole-zero cancellations of ¢(s). It is important
to mention that there are no unstable pole-zero cancellations in the pole-placement design and
the resulting unity-feedback system is totally stable, which will be defined in Section 9.3. Thus
the internal model principle can be used in practical design.
In classical control system design, if a plant transfer function or a compensator transfer
function is of type I (has one pole at s = 0), and the unity-feedback system is designed to be

|     |           |     |         | 9.2  Unity-Feedback Configuration-Pole Placement  |            |     |         |     |         |        | 277  |
| --- | --------- | --- | ------- | ------------------------------------------------- | ---------- | --- | ------- | --- | ------- | ------ | ---- |
| j   |           |     | + 34/3  |                                                   |            |     |         |     |         |        |      |
|     | A(s) = 5  |     |         | 8(5) =                                            | (-22/3)5 - |     | 23/3 =  |     | (-225 - | 23)/3  |      |
)
and the compensator
';l
| .. ,     |     |       |       |     | -(23 + 225)/3  |     |     |        |     |     |         |
| -------- | --- | ----- | ----- | --- | -------------- | --- | --- | ------ | --- | --- | ------- |
|          |     |       | 8(5)  |     |                |     |     | -22s - | 23  |     |         |
| ,,:.~,   |     |       | =     | =   |                | +   | =   |        | +   |     | (9.16)  |
|          |     | C(s)  | A(s)  |     | 34/3           | s   |     | 3s     | 34  |     |         |
..,!
will place the three poles of the overall system at -2 and -1 ± j 1. If the system is designed to
.,,
.  achieve regulation, we set p = 1 (no feedforward gain is needed) and the design is completed .
>:
To design tracking. we check whether or not No  t= O. This is the case; thus we can find a p
.:,.'  so that the overall system will track asymptotically any step reference input. We use (9.15) to
,":
compute p:
"'j
| :,1  |     |     |        | Fo    |              | 4   |     | 6   |     |     |         |
| ---- | --- | --- | ------ | ----- | ------------ | --- | --- | --- | --- | --- | ------- |
| i    |     |     | p=--=  |       |              |     |     | =-  |     |     | (9.17)  |
|      |     |     |        | BoNo  | (-23/3)(-2)  |     |     | 23  |     |     |         |
J
?  Thus the overall transfer function from r to y is
'<
|     |     |     |            | +          |     |     |         |     | +       |     |     |
| --- | --- | --- | ---------- | ---------- | --- | --- | ------- | --- | ------- | --- | --- |
| :   |     | •   | 6  [-(22s  | 23)/3](5 - |     | 2)  | -2(22s  |     | 23)(s - | 2)  |     |
. ~
(9,18)
|     |     | goes) =  | 23  (s3 + 4s3 + 6s  |     |     | +  4)  | =  23(53  | +   | 4s2 +  | 6s  +  4)  |     |
| --- | --- | -------- | ------------------- | --- | --- | ------ | --------- | --- | ------ | ---------- | --- |
..J,   Because goes) is BIBO stable and go(O) =  1. the overall system will track any step reference
input.
| 9,2,2  Robust Tracking and Disturbance Rejection  |     |     |     |     |     |     |     |     |     |     |     |
| ------------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Consider the design problem in Example 9.2. Suppose after the design is completed. the plant
transfer function g(s) changes. due to load variations, to g(s)'  =  (s - 2.1)/(s2 - 0.95). Then
the overall transfer function becomes
-22s -23 s -2.1
|     |     |                      | pC(5)g(S)  |     |     | 6   | 3s +   |     | s -      |     |     |
| --- | --- | -------------------- | ---------- | --- | --- | --- | ------ | --- | -------- | --- | --- |
|     |     |                      |            |     |     |     |        | 34  | 0.95     |     |     |
|     |     | goes) = 1 +C(s)g(s)  |            |     |     | 23  | -225 - | 23  | s - 2.1  |     |     |
1+-------
3s +
|     |     |     |     |     |     |     |     | 34  | s - 0.95  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --------- | --- | --- |
+
|     |     |     |     | -6(225  | 23)(s - | 2.1)  |     |     |     |     |     |
| --- | --- | --- | --- | ------- | ------- | ----- | --- | --- | --- | --- | --- |
(9.19)
|     |     |     | 23(3s3 +  | 12s2 + 20.35s  |     |     | +  16)  |     |     |     |     |
| --- | --- | --- | --------- | -------------- | --- | --- | ------- | --- | --- | --- | --- |
This goes)  is still BIBO stable, but ,teO) =  (6·23·2.1)/(23·16) =  0.7875  f=  L If the
reference input is a unit step function, the output will approach 0.7875 as t  ~ 00. There is
a tracking error of over 20%. Thus the overall system will no longer track any step reference
input after the plant parameter variations. and the design is said to be nonrobust.
In this subsection. we discuss a design that can achieve robust tracking and disturbance
rejection. Consider the system shown in Fig. 9.2, in  which a disturbance enters at the plant
input as shown. The problem is to design an overall system so that the plant output y will track
asymptotically a class of reference signal r even with the presence of the disturbance and with
plant parameter variations. This is called robust tracking and disturbance rejection.
Before proceeding. we discuss the nature of the reference signal r (t) and the disturbance
wet). If both r(t)  and  wet)  approach zero as  t  ->  00. then the  design is  automatically

278 POLE PLACEMENT AND MODEL MATCHING
r +j' . i • 1 g(s) y r+'l '.1 B(s) g(s) y
A(s)4>(s)
C(S)
(a) (b)
Figure 9.2 Robust tracking and disturbance rejection.
j
achieved if the overall system in Fig. 9.1 is designed to be SIBO stable. To exclude this
trivial case. we assume that r et) and wet) do not approach zero as t -+ 00. If we have
no knowledge whatsoever about the nature of ret) and w(t), it is not possible to achieve
asymptotic tracking and disturbance rejection. Therefore we need some information of r(t)
and wet) before carrying out the design. We assume that the Laplace transforms of rtf) and
w(t) are given by
N,(s) = =
= = w(s) L[w(t)] Nw(s) (9.20)
res) L[r(t)] Dr(s)
Dw(s)
where Dr(s) and Dw(s) are known polynomials; however, Nr(s) and Nw(s) are unknown
=
to us. For example, if r et) is a step function with unknown magnitude a, then res) a/so
Suppose the disturbance is wet) = b + c sin(wot + d); it consists of a constant biasing with
unknown magnitude b and a sinusoid with known frequency Wo but unknown amplitude c and
=
phase d. Then we have w(s) N (s)/s(s2 +w~). Let I/>(s) be the least common denominator
w
of the unstable poles of res) and w(s). The stable poles are excluded because they have no
effect on y as t -+ 00. Thus all roots of ¢(s) have zero or positive real parts. For the examples
just discussed. we have I/>(s) = S(S2 + w;).
~ Theorem 9.3
Consider the unity-feedback system shown in Fig. 9.2(a) with a strictly proper plant transfer function
g(s) = N(s)/ D(s). It is assumed that O(s) and N(s) are coprime. The reference signal ret) and
= =
disturbance wet) are modeled as res) Nr(s)/ Ores) and w(s) Nw(s)/ Dw(s). Let I/>(s) be the
least common denominator of the unstable poles of r(s) and w(s). If no root of <t> (s) is a zero of g (5).
then there exists a proper compensator such that the overall system will track r(c) and reject w(t), both
asymptotically and rObustly.
i3
Proof: If no root of I/>(s) is a zero of g(s) == N(s)/ D(s). then D(s)l/>(s) and N(s) are
coprime. Thus there exists a proper compensator B(s)/ A(s) such that the polynomial
F(s) in
+ =
A(s)D(s)<t>(s) B(s)N(s) F(s)
has any desired roots, in particular, has all roots lying inside the sector shown in Fig.
8.3(a). We claim that the compensator

280
POLE PLACE,'v\ENT AND MODEL MATCH I r-;C
BIBO stable, then the overall system will track asymptotically and robustly any step reference
input. This is a special case of the internal model principle.
EXAMPLE 9.3  Consider the plant in Example 9.2 or 8(s)  =  (s  - 2)/(s~ - 1). Design a
unity-feedback system with a set of desired poles to track robustly any step reference input.
First we introduce the internal model ¢(s) =  I/s. Then B(s)/ A(s) in Fig. 9.2(a) can be
solved from
|     |     |     |     |               | +   |           | =   |       |     |     |
| --- | --- | --- | --- | ------------- | --- | --------- | --- | ----- | --- | --- |
|     |     |     |     | A(s)D(s)¢(s)  |     | 8(s)N(s)  |     | F(s)  |     |     |
Because D(s) := D(s)dJ(s) has degree 3. we mav select A(s) and 8(s) to have degree 2. Then
|     |     |     |     | ...."'  |     |     |     |     |     | ....  |
| --- | --- | --- | --- | ------- | --- | --- | --- | --- | --- | ----- |
.
F (s) has degree 5. If we select five desired poles as - 2. -2 :::':: j I. and - I :::':: j 2. then we have
,
|     |     |     |       | =          | ..,!         |     | ,          |     |     |     |
| --- | --- | --- | ----- | ---------- | ------------ | --- | ---------- | --- | --- | --- |
|     |     |     | F(s)  | (s + 2)(s- | + 4s + 5)(s- |     | + 25 + 5)  |     |     |     |
3 +
|     |     |     |     | = s5 + 8s~ + 30s |     |     | 66s~ + 85s + 50  |     |     |     |
| --- | --- | --- | --- | ---------------- | --- | --- | ---------------- | --- | --- | --- |
=
Using the coefficients of D(s) =  (s~- I)s  0-s+0·s~+s3 and N(s) =  -2+5+0'S'+0'S3,
we form
|                         |             |         |      |          | 0                        |     | 0   |           |         |           |
| ----------------------- | ----------- | ------- | ---- | -------- | ------------------------ | --- | --- | --------- | ------- | --------- |
|                         |             |         |      | 0  -I    |                          | I   |     | 0         |         |           |
|                         |             |         |      | -2       | 0                        | 0   | 0   | 0         |         |           |
|                         |             |         |      | 0        | 0  -I                    | 0   | 1   |           |         |           |
|                         |             |         |      | 11       |                          |     |     | ~  = [50  | 85  66  | 30  8 11  |
|                         | [Ao Bo AI 8 | 1 A2 82 |      |          |                          |     |     | 1         |         |           |
|                         |             |         |      | 0  -2    |                          | 0   | 0   |           |         |           |
|                         |             |         |      | 0        | 0  0                     | -1  | 0   | I         |         |           |
|                         |             |         |      | 0        | 0  -2                    |     | 0   | 0         |         |           |
| Its solution is [127.3  |             |         | -25  | 0-118.7  | I  -96.31. Thus we have  |     |     |           |         |           |
25
|     |     |     |     | B(s)  | -96.3s~ - | 118.7s - |     |     |     |     |
| --- | --- | --- | --- | ----- | --------- | -------- | --- | --- | --- | --- |
|     |     |     |     | A(s)  | s2+127.3  |          |     |     |     |     |
and the compensator is
|     |     |     |         | 8(s)  | -96.3s2  |     | - 118.7s - | 25  |     |     |
| --- | --- | --- | ------- | ----- | -------- | --- | ---------- | --- | --- | --- |
|     |     |     | C(s) =  |       | =        |     |            |     |     |     |
+ 127.3)s
|     |     |     |     | A(s)¢(s)  |     | (s~  |     |     |     |     |
| --- | --- | --- | --- | --------- | --- | ---- | --- | --- | --- | --- |
l:sing this compensator of degree 3. the unity-feedback system in Fig. 9.2(a) will track robustly
any step reference input and has the set of desired poles.
9.2.3  Embedding Internal Models
The design in the preceding subsection was achieved by first introducing an internal model
I !<P(s) and then designing a proper 8(s)/ A (5). Thus the compensator 8(5)/ A (s)¢(.I) is always
strictly proper. In this subsection. we discuss a method of designing a biproper compensator
whose denominator will include the internal model as a factor as shown in Fig. 9.2\b). By so
doing, the degree of compensators can be reduced.

9.3 Implementable Transfer Functions 283
I Its solution is [I 4 2 4]. Thus the compensator is
8(s) 4s 2 + 2s + 4 4s 2 + 25 + 4
= = + =
C(s) -A(-s) I x (52 4) -"" 5 7 " " + "- 4 - :--
:1 This biproper compensator will place the poles of the unity-feedback system in the assigned
j positions. track any step reference input. and reject the disturbance a sin(2r + (1). both
asymptotically and robustly.
9.3 Implementable Transfer Functions
Consider again the design problem posed in Fig. 8.1 with a given plant transfer function
8(s). Now the problem is the following: given a desired overall transfer function 80(s). find
a feedback configuration and compensators so that the transfer function from r to y equals
80(5). This is called the model matching problem. This problem is clearly different from the
pole-placement problem. In pole placement, we specify only poles; its design will introduce
some zeros over which we have no control. In model matching. we specify not only poles but
also zeros. Thus model matching can be considered as pole-and-zero placement and should
yield a better design.
=
Given a proper plant transfer function 8(s), we claim that 80(5) I is the best possible
overall system we can design. Indeed, if 80(5) = I, then yet) = ret) for r :::: 0 and for any
ret). Thus the overall system can track immediately (not asymptotically) any reference input
no matter how erratic r(r) is. Note that although y(t) = r(t), the power levels at the reference
input and plant output may be different. The reference signal may be provided by turning a
knob by hand; the plant output may be the angular position of an antenna with weight over
several tons.
Although 80(s) = I is the best overall system, we may not be able to match it for a given
plant. The reason is that in matching or implementation, there are some physical constraints
that every overall system should meet. These constraints are listed in the following:
1. All compensators used have proper rational transfer functions.
2. The configuration selected has no plant leakage in the sense that all forward paths from r
to y pass through the plant.
3. The closed-loop transfer function of every possible input-output pair is proper and BlBO
stable.
Every compensator with a proper rational transfer function can be implemented using the
op-amp circuit elements shown in Fig. 2.6. If a compensator has an improper transfer function.
then its implementation requires the use of pure differentiators. which are not standard op
amp circuit elements. Thus compensators used in practice are often required to have proper
transfer functions. The second constraint requires that all power passes through the plant and
no compensator be introduced in parallel with the plant. All configurations in Fig. 9.1 meet
this constraint. In practice. noise and disturbance may exist in every component. For example.
noise may be generated in using potentiometers because of brush jumps and wire irregularity.
The load of an antenna may change because of gusting or air turbulence. These will be modeled
as exogenous inputs entering the input and outputterrninals of every block as shown in Fig. 9.3.

281
9.2  Unity-Feedback Configuration-Pole Placement
COllsid~r
|     |     |     |           |     | +         |     | =     |     |     |     |
| --- | --- | --- | --------- | --- | --------- | --- | ----- | --- | --- | --- |
|     |     |     | A(s)D(s)  |     | B(s)N(s)  |     | F(s)  |     |     |     |
| =   |     |     |           | =   |           |     |       |     |     |     |
If deg D (s)  n  and if deg A(s)  n  - I, then the solution Als) and B(s)  is unique. If
we increase the degree of A(5)  by one, then solutions are not unique. and there is one free
parameter we can select. Using the free parameter, we may be able  include an internal model
[Q
in the compensator. as the next example illustrates.
EX.UIPLE 9.4  Consider again the design problem in Example 9.2. The degree of D(s) is 2. If
A (.I) has degree I, then the solution is unique. Let us select A (s) to have degree 2. Then F (s)
must ha ve d~gree 4 and can be selected as
|         |     | (r ., +  | +   | +        | +             |     | .t +  | 1  +       | +  30.1 + 25  |     |
| ------- | --- | -------- | --- | -------- | ------------- | --- | ----- | ---------- | ------------- | --- |
| F(s) =  |     |          | 4s  | 5)(r '1  | 2.1  5) = .I  |     | 6s'   |   185-"'t  |               |     |
We form
|               |     |         |     | -I  | 0   | I   | 0   | 0    |                     |         |
| ------------- | --- | ------- | --- | --- | --- | --- | --- | ---- | ------------------- | ------- |
|               |     |         |     | -2  |     | 0   | 0   | 0    |                     |         |
|               |     |         |     | 0   | -I  | 0   | I   |      |                     |         |
|               |     |         |     | I   |     |     |     | ~ I  | [25  30  18  6  I)  | (9.23)  |
| [Ao Bo AI BI  |     | A2 B,)  |     |     |     |     |     | =    |                     |         |
|               |     |         |     | 0   | -2  |     | 0   |      |                     |         |
|               |     |         |     | o   | o   |     | o   |      |                     |         |
|               |     |         |     |     | -I  |     |     | I    |                     |         |
|               |     |         |     | o   | o   |     | o   |      |                     |         |
-2
In order for the proper compensator
+  +
|     |     |     |     |         | Bo  | Bls  | B,s2  |     |     |     |
| --- | --- | --- | --- | ------- | --- | ---- | ----- | --- | --- | --- |
|     |     |     |     | Cis) =  |     |      | -     |     |     |     |
+  +
|     |     |     |     |     | Ao  | Ais  | A2s2  |     |     |     |
| --- | --- | --- | --- | --- | --- | ---- | ----- | --- | --- | --- |
to have  lis as a factor. we require Ao =  O. There are five equ~tions and six unknowns in
= O. This is
(9.23). Thus one of the unknowns can be arbitrarily assigned. Let us select Ao
equivalent to deleting the first row of the 6 x 5 matrix in (9.23). The remaining 5 x 5 matrix
is nonsingular, and the remaining five unknowns can be solved uniquely. The solution is
|     | Bo  | AI  | BI  A2  | B2) = [0  | -   | 12.5  | 34.8  | - 38.7  | I  - 28.8)  |     |
| --- | --- | --- | ------- | --------- | --- | ----- | ----- | ------- | ----------- | --- |
[Ao
Thus the compensator is
|     |     |         |     | BIs)    | -28.852   | -   | 38.7s - | 12.5  |     |     |
| --- | --- | ------- | --- | ------- | --------- | --- | ------- | ----- | --- | --- |
|     |     | C(s) =  |     | - '- =  | ---,-~+-  |     | -::---  |       |     |     |
34.85
|     |     |     |     | A(.I')  |     | 52  |     |     |     |     |
| --- | --- | --- | --- | ------- | --- | --- | --- | --- | --- | --- |
This biproper compensator can achieve robust tracking. This compensator has degree 2. one
less than the one obtained in Example 9.3. Thus this is a better design.
In  the preceding example, we  mentioned that one of the unknowns in  (9.23) can be
arbitrarily assigned. This does not mean that any one of them can be arbitrarily assigned. For
example, if we assign A2 = 0 or, equivalently. delete the fifth row of the 6 x 5 matrix in (9.23).
then the remaining square matrix is singular and no solution may exist. In Example 9.4, if we

282
POLE PLACEMENT AND MODEL MATCHING
select Ao = 0 and if the remaining equation in (9.23) does not have a solution, then we must
increase the degree of the compensator and repeat the design. Another way to carry out the
design is to find the general solution of (9.23). Using Corollary 3.2, we can express the general
solution as
[Ao  Bo  Al  BI  A2  B21=[1  -13 34.3  -38.7  I  -28.31+a[2  -I  -100 II
|     |     |     |     | =   |     | =   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
with one free parameter a. If we select a  -0.5, then Ao  0 and we will obtain the same
compensator.
We give one more example and discuss a different method of embedding cjJ (s) in the
compensator.
=
EXAMPLE 9.5 Consider the unity-feedbackfystem in Fig. 9.2(b) with g(s)  I/s. Design a
proper compensator C(s) =  B(s)/ A(s) so that the system will track asymptotically any step
e)  e.
reference input and reject disturbance wet) = a sin(2t +  with unknown a and
In order to achieve the design, the polynomial A(s) must contain the disturbance model
(S2 + 4). Note that the reference model s is not needed because the plant already contains the
factor. Consider
=
+
|     |     |     | A(s)D(s)  |     | B(s)N(s)  | F(s)  |     |
| --- | --- | --- | --------- | --- | --------- | ----- | --- |
For this equation, we have deg D(s) =  n =  1. Thus if m =  n - I =  0, then the solution is
unique and we have no freedom in assigning A (s). If m = 2, then we have two free parameters
that can be used to assign A (s). Let
|     |       | =   |        | +   | B(s) =  | +        | +     |
| --- | ----- | --- | ------ | --- | ------- | -------- | ----- |
|     | A(s)  |     | Ao(s2  | 4)  |         | Bo  Bis  | B2S2  |
Define
|     |     |     | Do  |     |     | =   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
D(s) = D(s)(sz + 4) =  +  DIS +  Dzs2 +  D3S3  0 + 4s + 0 . S2 + s3
=
| We write A(s)D(s) +  |     | B(s)N(s)  |     | F(s) as  |     |     |     |
| -------------------- | --- | --------- | --- | -------- | --- | --- | --- |
=
+
|     |     |     | AoD(s)  |     | B(s)N(s)  | F(s)  |     |
| --- | --- | --- | ------- | --- | --------- | ----- | --- |
Equating its coefficients, we obtain
Do
|     |     |     |     | DI  | Dz  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
o
|     |                |     |     |         |     | D 3]    |         |
| --- | -------------- | --- | --- | ------- | --- | ------- | ------- |
|     |                |     |     | No  NI  |     | ~  =    |         |
|     | [Ao Bo BI B2l  |     |     |         |     | [Fo FI  | F2 F31  |
|     |                |     |     | 0       | No  |         |         |
|     |                |     | [   |         | NI  |         |         |
o
|     |     |     |     |     | 0  No  | NI  |     |
| --- | --- | --- | --- | --- | ------ | --- | --- |
For this example, if we select
|     |                                 |     |     | ,   |     | 3'              |     |
| --- | ------------------------------- | --- | --- | --- | --- | --------------- | --- |
|     | F(s) = (s + 2)(r + 2s + 2) = s  |     |     |     |     | + 4s" + 6s + 4  |     |
then the equation becomes
|     |     |     |     |     | 4  0  |     |     |
| --- | --- | --- | --- | --- | ----- | --- | --- |
|     |     |     |     | [0  |       | ~]  |     |
|     |     |     |     |     | 0  0  |     |     |
|     |     | "   |     |     | 1     |     |     |
= [4 64 11
|     |     | [Ao Bo BI B2)  |     |     | ~     |     |     |
| --- | --- | -------------- | --- | --- | ----- | --- | --- |
|     |     |                |     |     | I  0  |     |     |
0

284 POLE PLACEME>.:T AND MODEL MATCHING
Clearly we cannot disregard the effects of these exogenous inputs on the system. Although the
plant output is the signal we want to control, we should be concerned with all variables inside
the system. For example, suppose the closed-loop transfer function from r to u is not BIBO
stable: then any r will excite an unbounded u and the system will either saturate or bum out. If
the closed-loop transfer function from n 1 to u is improper, and if n 1 contains high-frequency
noise. then the noise will be greatly amplified at u and the amplified noise will drive the system
crazy. Thus the closed-loop transfer function of every possible input-output pair of the overall
system should be proper and BIBO stable. An overall system is said to be \I'e II posed if the
closed-loop transfer function of every possible input-output pair is proper; it is totally stable
if the closed-loop transfer function of every possible input-output pair is BIBO stable.
Total stability can readily be met in design. If the overall transfer function from r to y is
BIBO stable and if there is no unstable pole-zero cancellation in the system, then the overall
system is totally stable. For example. consider the system shown in Fig. 9.3(a). The overall
transfer function from r to y is
_ I
+
gv,(s) = s I
which is BIBO stable. However, the system is not totally stable because it involves an
unstable pole-zero cancellation of (s - 2). The closed-loop transfer function from n~ to y
+
is 5/(5 - 2)(s I), which is not BIBO stable. Thus the output will grow unbounded if noise
n2, e,'en very small, enters the system. Thus we require BIBO stability not only of 80(s) but
also of every possible closed-loop transfer function. Note that whether or not 8(5) and C(s)
are BIBO stable is immaterial.
The condition for the unity-feedback configuration in Fig. 9.3 to be well posed is
C(oclg(oo) f. -I (Problem 9.9). This can readily be established by using Mason's formula.
See Reference [7, pp. 200-201]. For example, for the unity-feedback system in Fig. 9.3(b),
= =
we have C(oc)g(oo) (-1/2) x 2 -I. Thus the system is not well posed. Indeed. the
closed-loop transfer function from r to y is
+ +
_ (-5 2)(2s 2)
+
goes) = s 3
which is improper. The condition for the two-parameter configuration in Fig. 9.1 (d) to be well
posed is g(oo)C2(00) f. -I. In the unity-feedback and two-parameter configurations. if g(s)
is strictly proper or g(oo) = 0, then g(oc)C(oo) = 0 f. -I for any proper C(s) and the overall
systems will automatically be well posed. In conclusion, total stability and well-posedness can
easily be met in design. Nevertheless. they do impose some restrictions on g,,(s).
s-2 2s + 2
s s-2 2s + I s-I
C(s) g(s) C(s) g(s)
<a) lb)
Figure 9.3 Feedback systems.

|     |     | 9.3  Implementable Transfer Functions  |     | 287  |
| --- | --- | -------------------------------------- | --- | ---- |
¥1  This compensator is proper. However. the tandem connection of C(s) and g(s) involves the
|     | 1) =  +  |     |     | +   |
| --- | -------- | --- | --- | --- |
pole-zero cancellation of (s! - (s  1) (5 - I), The cancellation of the stable pole s  I
;1
will not cause any serious problem in the overall system. However. the cancellation of the
'j
unstable pole s - I will make the overall system not totally stable. Thus the implementation
j  is not acceptable.
Model matching in general involves some pole-zero cancellations. The same situation
arises in state-feedback state-estimator design; all eigenvalues of the estimator are not con
trollable from the reference input and are canceled in the overall transfer function. However.
because we have complete freedom in selecting the eigenvalues of the estimator, if we select
them properly, the cancellation will not cause any problem in design. In using the unity
feedback configuration in model matching. as we saw in the preceding example. the canceled
poles are dictated by the plant transfer function. Thus. if a plant transfer function has poles with
positive real parts, the cancellation will involve unstable poles. Therefore the unity-feedback
configuration. in general. cannot be used in model matching,
The open-loop and the unity-feedback configurations in Figs, 9.1 (a) and 9, I(b) have one
degree of freedom and cannot be used to achieve every model matching. The configurations
in Figs. 9.I(c) and 9.I(d) both have two degrees of freedom. In using either configuration.
we have complete freedom in assigning canceled poles; therefore both can be used to achieve
every model matching. Because the two-parameter configuration in Fig. 9.1(d) seems to be
more natural and more suitable for practical implementation. we discuss only that configuration
here. For model matching using the configuration in Fig. 9.I(c), see Reference [6).
Consider the two-parameter configuration in Fig. 9.I(d). Let
|     | L(s)  | M(s)  |     |     |
| --- | ----- | ----- | --- | --- |
CI (5)  =
|     | Al (s)  | Cl(s) =  A!(s)  |     |     |
| --- | ------- | --------------- | --- | --- |
where L(s).  M(s),  AI(s). and Al(s) are polynomials. We call CI(s) thefeedfonmrd com
pensator and C (s) the feedback compensator. In general. Al (s) and Al(S) need not be the
2
same. It turns out that even if they are chosen to be the same, the configuration can still be used
to achieve any model matching, Furthermore, a simple design procedure can be developed.
Therefore we assume Al (s) =  Al(S) =  A(s) and the compensators become
|        | L(s)  | M(s)     |     |         |
| ------ | ----- | -------- | --- | ------- |
|        | =     | Cl(s) =  |     | (9.26)  |
| CI(s)  | A(s)  | A(s)     |     |         |
The transfer function from r to v in Fig. 9.1(d) then becomes
N(s)
| goes) = CI(s)  | Ag(S)      | =  L(s)  | D(s)       |     |
| -------------- | ---------- | -------- | ---------- | --- |
|                | 1+         |          | +          |     |
|                | g(s)C!(s)  | A(s) I   | N(s) M(s)  |     |
D(s)  A(s)
L(s)N(s)
(9,27)
+
| - A(s)D(s)  | M(s)N(s)  |     |     |     |
| ----------- | --------- | --- | --- | --- |
Thus in model matching, we search for proper L(s)/A(s) and M(s)/A(s) to meet
|         | = -- £(s)  = --=-...,----- | L(s)N(s)  |     |         |
| ------- | -------------------------- | --------- | --- | ------- |
| A       |                            |           |     | (9.28)  |
| g o(s)  |                            | +         |     |         |
|         | F(s)  A(s)D(s)             | M(s)N(s)  |     |         |

9.3 Implementable Transfer Functions 285
Definition 9.1 Given a plant with proper transfer function g(s), an overall transfer
fUllction goes) is said to be implementable if there exists a no-plant-leakage configuration
alld proper compensators so that the trallsfer functioll from r to y ill Fig. 8.1 equals
goes) alld the overall system is well posed alld totally stable.
If an overall transfer function goes) is not implementable. then no matter what configura
tion is used to implement it, the design will violate at least one of the aforementioned constraints.
Therefore, in model matching, the selected goes) must be implementable; otherwise, it is not
possible to implement it in practice.
Theorem 9.4
Consider a plant with proper transfer function g(s). Then goes) is implementable if and only if goes)
and
irs) := goes)
(9.24)
g(s)
are proper and SIBO stable.
>
Corollary 9.4
= =
Consider a plant with proper transfer function g(s) N(s)/ D(s). Then goes) £ (05)/ F(s) is
implemenrable if and only if
1. All roots of F(s) have negative real parts (F(s) is Hurwitz).
2. Deg F(s) - deg £(s) ::: deg D(s) - deg N(s) (pole-zero excess inequality).
3. All zeros of N (s) with zero or positive real parts are retained in £ (s) (retainmenr of non minimum
phase leros).
We first develop Corollary 9.4 from Theorem 9.4. If goes) = £(5)/ F(s) is BlBO stable.
then all roots of F(s) have negative real parts. This is condition (I). We write (9.24) as
irs) = goes) = E(s)D(s)
g(s) F(s)N(s)
The condition for i(s) to be proper is
+ +
deg F(s) deg N(s) ::: deg £(s) deg D(s)
which implies (2). In order for i(s) to be BlBO stable. all roots of N (s) with zero or positive real
parts must be canceled by the roots of £(5). Thus £(5) must contain the nonminimum-phase
zeros of N(s). This is condition (3). Thus Corollary 9.4 follows directly Theorem 9.4.
Now we show the necessity of Theorem 9.4. For any configuration that has no plant
leakage. if the closed-loop transfer function from r to y is goes), then we have
= =
yes) go(o5)r(s) g(s)u(s)

286 POLE PLACEMENT AND MODEL MATCHING
which implies
• = goes). '.
u(s) -.-r(s) = t(s)r(s)
g(s)
Thus the closed-loop transfer function from r to u is irs). Total stability requires every closed
loop transfer function to be Billa stable. Thus goes) and irs) must be BIBO stable. Well
posedness requires every closed-loop transfer function to be proper. Thus goes) and irs) must
be proper. This establishes the necessity of the theorem. The sufficiency of the theorem will
be established constructively in the next subsection. Note that if g(s) and irs) are proper. then
goes) = g(s)i(s) is proper. Thus the condition for 80(s) to be proper can be dropped from
Theorem 9.4.
In pole placement, the design will always introduce some zeros over which we have no
control. In model matching, other than retai¢ing nonminimum-phase zeros and meeting the
pole-zero excess inequality, we have complete freedom in selecting poles and zeros: any pole
inside the open left-half s-plane and any zero in the entire s-plane. Thus model matching
can be considered as pole-and-zero placement and should yield a better overall system than
pole-placement design.
Given a plant transfer function g(s), how to select an implementable model goes) is not
a simple problem. For a discussion of this problem, see Reference [7, Chapter 9].
9.3.1 Model Matching-Twa-Parameter Configuration
=
This section discusses the implementation of goes) = g(s)i(s). Clearly. if C(s) irs) in Fig.
9.1 (a), then the open-loop configuration has go (s) as its transfer function. This implementation
may involve unstable pole-zero cancellations and. consequently, may not be totally stable.
Even if it is totally stable, the configuration can be very sensitive to plant parameter variations.
Therefore the open-loop configuration should not be used. The unity-feedback configuration in
Fig. 9.I(b) can be used to achieve every pole placement; however it cannot be used to achieve
every model matching, as the next example shows.
~ EXAMPLE 9.6 Consider a plant with transfer function g(s) = (s - 2)/(s2 -I). We can readily
'j show that
:'·:·'.
~ _ . -(s - 2)
(9.25)
goes) = s2+2s+2
I
=
is implementable. Because go(O) 1. the plant output will track asymptotically any step
'~
reference input. Suppose we use the unity-feedback configuration with p = I to implement
goes). Then from
.'.
C(s)g(s)
=
F goes) 1+ C(s)g(s)
we can compute the compensator as
t: 80(S) _(52 - I)
C(s) = g(s)[1 - goes)] s(s + 3)

288  POLE PLACE,"'ENT AND MODEL MATCHI,NC
Note that the two-parameter configuration has no plant leakage. If the plant transfer function
g(s) is  strictly proper as  assumed and if C2(S)  =  M(s)/ A(s) is proper. then the overall
system is automatically well posed. The question of total stability will be discussed in the next
subsection.
Problem  Given  g(s)  =  N(s)/ D(s).  where  N(s)  and  D(s)  are  coprime  and deg
N(s)  <  degD(s)  =  n,  and given an implementable goes)  =  £(5)/ F(s). find proper
L(s)/ A(s) alld M(s)/ A(s) 10 meet (9.28).
Procedure 9,1
1.  Compute
|     |     | goes)  |           | £(5)  | £(5)  |     |         |
| --- | --- | ------ | --------- | ----- | ----- | --- | ------- |
|     |     | --=    |           |       |       |     | (9.29)  |
|     |     | N(s)   | F(s)N(5)  |       | F(s)  |     |         |
- -
where £(5) and F(s) are coprime. Since £(5) and F(s) are implicitly assumed to be coprime,
common factors may exist only between £(5) and N(s). Cancel all common factors be, ween them
anddenotetherestasE(s)andF(s).Notethatif£(s) =  N(s),thenFcs) =  = I.
F(s)andE(s)
l'sing (9,29), we rewrite (9.28) as
L(s)N(s)
|     | gn(s) =  | £ (s)N(s)  |     |     |     |     |     |
| --- | -------- | ---------- | --- | --- | --- | --- | --- |
(930)
+
|     |     | F   | (s)  | A(s)D(s)  |     | M (s)N(s)  |     |
| --- | --- | --- | ---- | --------- | --- | ---------- | --- |
From this equation, we may be tempted to set L(s)  =  £ (5) and solve for A(5) and M(5) from
+
F(s)  =  A(s)D(s)  M(s)N(s). However. no proper C,(s)  =  M(s)/ A(s) may exist in the
equation. See Problem 9.1. Thus we need some additional manipulation.
2,  Introduce an arbitrary Hurwitz polynomial F(s) such that 'he degree of F(s)F(s) is 211  - I or
higher. In other words. if deg F(s) =  p. then deg f:(s) ::':  211  - I - p. Because the polynomial
F(s) will be canceled in the design. its roots should be chosen to lie inside the sector shown in Fig.
S]!a).
J.  Rewrite (9.30) as
| _        |     | £(5)F(s)N(s)  |     |     | L(s)N(s)  |     |          |
| -------- | --- | ------------- | --- | --- | --------- | --- | -------- |
| 80(S) =  |     | _             | _   |     |           |     | (9.31)   |
+
|     |     | F(s)F(s)  |     | A(s)D(s)  |     | M(s)N(s)  |     |
| --- | --- | --------- | --- | --------- | --- | --------- | --- |
~ow we set
=
|     |     |     | L(s)  | £(s)F(s)  |     |     | (932)  |
| --- | --- | --- | ----- | --------- | --- | --- | ------ |
and solve A (5) and M (s) from
+
|     |     | A(s)D(s)  | M(s)N(s) =  |     | F(s)F(s)  |     | (9.33)  |
| --- | --- | --------- | ----------- | --- | --------- | --- | ------- |
lrwe write
|     |               |     | +    | +     | + ... +    |           |     |
| --- | ------------- | --- | ---- | ----- | ---------- | --------- | --- |
|     | A(s) =        | Ao  | A,s  | A~s~  |            | Ams'"     |     |
|     | M (s) = Mo +  |     |      | +     | ' + ... +  | ..        |     |
|     |               |     | B,s  | ,'vI  | r          | m " ,S m  |     |
2
|             |     |     | +    | +     | + ... +  |            |     |
| ----------- | --- | --- | ---- | ----- | -------- | ---------- | --- |
| Frs)F(s) =  |     | Fo  | F,s  | Fcs2  |          | Fn+",sn+m  |     |

|     |                                                      |     |     |     | 9.3  Implementable Transfer Functions  |     |     |     | 291  |
| --- | ---------------------------------------------------- | --- | --- | --- | -------------------------------------- | --- | --- | --- | ---- |
|     | 9.3.2  Implementation of Two-Parameter Compensators  |     |     |     |                                        |     |     |     |      |
Given a plant with transfer function g(s) and an implementable model go (s). we can implement
the model in the two-parameter configuration shown in Fig. 9.1 (d) and redrawn in Fig. 9A(a).
The compensators C, (s)
|     |     |     | =  L(s)/ A(s) and Cz(s)  |     | =  M(s)/ A(s) can be obtained by using  |     |     |     |     |
| --- | --- | --- | ------------------------ | --- | --------------------------------------- | --- | --- | --- | --- |
Procedure 9. I. To complete the design. the compensators must be built or implemented. This
is discussed in this subsection.
Consider the configuration in Fig. 9.4(a). The denominator A(s) of C, (s) is obtained by
solving the compensator equation in (9.33) and mayor may not be a Hurwitz polynomial. See
Problem 9.12. If it is not a Hurwitz polynomial and if we implement C I (5) as shown in Fig.
9.4(a). then the output of C, (5) will grow without bound and the overall system is not totally
stable. Therefore. in general. we should not implement the two compensators as shown in Fig.
9.4(a).lfwe move Cz(s) outside the loop as shown in Fig. 9A(b). then the design will involve
the cancellation of M(s). Because M(s) is also obtained by solving (9.33), we have no direct
control of M(s). Thus the design is  in general not acceptable. If we move C,(S) inside the
loop. then the configuration becomes the one shown in Fig. 9.4(c). We see that the connection
=
involves the pole-zero cancellation of L(s)  Fcs)£(s). We have freedom in selecting F(s).
The polynomial £(s) is part of £(5), which. other than the nonminimum-phase zeros of N(s),
we can also select. The nonminimum-phase zeros, however, are completely canceled in £
(s).
Thus L(s) can be Hurwitz3 and the implementation in Fig. 9A(c) can be totally stable and is
H
r
| r   | L(s)  | I   | .v  | r   | ~   |     |     |     | I},  |
| --- | ----- | --- | --- | --- | --- | --- | --- | --- | ---- |
I
|     |     | 8(5)  |     | I  U  | s)  | .H«)  |     | 8(5)  |     |
| --- | --- | ----- | --- | ----- | --- | ----- | --- | ----- | --- |
|     |     |       |     | M(s)  | _   | A(s)  |     |       |     |
r---
M(s)
04(5)
L--
(b)
(0)
r-
I
|      | r  U s )  |           | v   | r  I  | -: 0- |         |         |       |     |
| ---- | --------- | --------- | --- | ----- | ----- | ------- | ------- | ----- | --- |
|      | -         | 1/  g(s)  |     |       |       |         | I   1/  |       | \   |
| (~ - | .         |           |     | US)   |       | A-I(s)  |         | gls)  |     |
|      | . 4( s)   | -         |     |       |       |         | I       |       |     |
|      |           |           |     | I     | -     |         |         |       |     |
I
I
I
I
M(s)
,I
M(s)
Us)
I
L  --
L- ______________ _
|             | (e)                                     |     |     |     |     | (d)  |     |     |     |
| ----------- | --------------------------------------- | --- | --- | --- | --- | ---- | --- | --- | --- |
| Figure 9.4  | Two-degrees-of-freedom configurations.  |     |     |     |     |      |     |     |     |
3. This may not be true in the multi variable case.

|          |         |                                                   |     |     |                  |     | 9.3  Implementable Transfer Functions  |     |                 |     | 289  |
| -------- | ------- | ------------------------------------------------- | --- | --- | ---------------- | --- | -------------------------------------- | --- | --------------- | --- | ---- |
| with In  | ?  II - | 1. then A(s) and M(s) can be obtained by solving  |     |     |                  |     |                                        |     |                 |     |      |
|          |         | [Ao Mo AI MI                                      |     |     | ... Am MmlS", =  |     | [Fa FI                                 |     | F:  ... Fn+",l  |     |      |
(93~)
with
|     |     |     |     |     |     |          | Dn    | 0   |     | 0   |     |
| --- | --- | --- | --- | --- | --- | -------- | ----- | --- | --- | --- | --- |
|     |     |     |     | Do  | DI  |          |       |     |     |     |     |
|     |     |     |     |     |     |          |       | 0   |     | 0   |     |
|     |     |     |     | No  | NI  |          | ,V'I  |     |     |     |     |
|     |     |     |     | 0   |     |          |       |     |     | 0   |     |
|     |     |     |     |     | Do  | D',-l    |       | Dn  |     |     |     |
|     |     |     |     | 0   | No  | ,\',,-1  |       | Nn  |     | 0   |     |
Sm  :=
|     |     |     |     | o   |     |     | o   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     |     | 0   |     |     | Do  |     | Dn  |     |
|     |     |     |     | o   |     |     | o   |     |     |     |     |
|     |     |     |     |     | 0   |     |     |     |     | N   |     |
|     |     |     |     |     |     |     |     | No  |     | n   |     |
The compuled compensators L(s)/ A(s) and M (5)/ A(s) are proper.
We justify the procedure. By introducing Fcsl. the degree of F(s) Fcs) is 211 - I or higher
and. following Theorem 9.2, solu~ions,A(s) and M(s) with deg L'vf(s)  ::: deg A(s) =  and
111
m ?  n - I exist in (9.34) for any F(s)F(s). Thus the compensator M(s)/A(s) is proper. Note
that if we do not introduce F(s). proper compensator M(s)/ A(s) may not exist in (9.34).
Next we show deg L(s) ::: deg A(s). Applying the pole-zero excess inequality to (9.31)
and using (9.32), we have
|     | deg (F(s)F(s»  |     |     | - deg N(s) - |     | deg L(s) ?  |     | deg D(s) - |     | deg N(s)  |     |
| --- | -------------- | --- | --- | ------------ | --- | ----------- | --- | ---------- | --- | --------- | --- |
which implies
=
|     |     | deg L(s) ::: deg CFCs)Fcs»  |     |     |     |     | - deg D(s)  |     | deg A(s)  |     |     |
| --- | --- | --------------------------- | --- | --- | --- | --- | ----------- | --- | --------- | --- | --- |
Thus the compensator L(s)! A(s) is proper.
EXAMPLE 9.7  Consider the model matching problem studied in Example 9.6. That is. given
|     |     |     |     |     |     |     |     | 2 +  | +   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ---- | --- | --- | --- |
g(s)  =  (5  - 2)/ (s2  - I), match g,,(s) =  -(s - 2)/(5 25  2). We implement it in the
two-parameter configuration shown in Fig. 9.1 Cd). First we compute
|     |     | g,,(s)  |      |     |        |     |     |     |               | £(5)  |     |
| --- | --- | ------- | ---- | --- | ------ | --- | --- | --- | ------------- | ----- | --- |
|     |     |         |      | +   | +      |     |     | +   | +             |       |     |
|     |     |         | (s"  |     | 2)(s - | 2)  | ~   | 2s  | 2 =: -F(-s-)  |       |     |
|     |     | N(s)    |      | 25  |        |     | 52  |     |               |       |     |
Because the degree of F(s) is 2, we select arbitrarily  =  s +  4 so that the degree of
Fcs)
.1  F(s)Fcs) is 3 = 2n - l. Thus we have
|     |     |     |     |         |           |     | =    | +   |     |     |         |
| --- | --- | --- | --- | ------- | --------- | --- | ---- | --- | --- | --- | ------- |
|     |     |     |     | L(s) =  | E(s)Fcs)  |     | -(5  | 4)  |     |     | (9.35)  |
and A (5) and M (5) can be sol ved from
-,
|     |           |     | +   | M(s)N(s) =  |     | F(slFcs) =  |     | +    | +   | 2)(s +4)  |     |
| --- | --------- | --- | --- | ----------- | --- | ----------- | --- | ---- | --- | --------- | --- |
| '~  | A(s)D(s)  |     |     |             |     |             |     | (S2  | 2s  |           |     |
i
|        |     |     |     |     |       | +  6.12 +  |     | +    |     |     |     |
| ------ | --- | --- | --- | --- | ----- | ---------- | --- | ---- | --- | --- | --- |
| _.. z  |     |     |     |     | = s3  |            |     | 105  | 8   |     |     |

290 POLE PLACEMENT AND MODEL MATCHING
"~ or
J
I
1
; r-1 0 I 0
.", " : -2 0 0
-;" ... I
; [Ao Mo A, Md '.~ '= [8 10 6 I]
-1 0 I
0 -2 0
= = = +
The solution is Ao = 18. A, '= I. Mo -13. and M, -12. Thus we have A(s) 18 s
= -
and M (s) 13 - 12s and the compensators are
+ +
L(5) -(5 4) M(s) -(125 13)
= -- = = -- = --'----
C,(5) C,(5)
+ +
A (s) 5 18 j - A (5) S 18
r
This completes the design. Note that. because go(O) := I, the output of the feedback system
" will track any step reference input.
EXAMPLE 9.8 Given g(s) = (5 - 2)/(s2 - I). match
.'''':
, -(s - 2)(45 + 2) -4s 2 + 6s + 4
-~: = + + + = + + +
80(s) (s" 2s 2)(s 2) s3 4s" 6s 4
=
This goes) is BlBO stable and has the property go(O) I and g:(s) '= 0: thus the overall
system will track asymptotically not only any step reference input but also any ramp input.
See Problems 9.13 and 9.14. This goes) meets all three conditions in Corollary 9.4: thus it is
.. implementable. We use the two-parameter configuration. First we compute
~
+ +
goes) - (s - 2)(4s 2) -(4s 2) £(s)
N(s) = (s2 + 2s + 2)(s + 2)(s - 2) = S3 + 4s2 + 6s + 4 '=: F(s)
Because the degree of F(s) is 3, which equals 2n - I '= 3. there is no need to introduce F(s)
F
and we set (s) = l. Thus we have
L(s) = F(s)£(s) = -(4s + 2)
and A (s) and M (s) can be solved from
-I 0 I 0
-2 0 0
I ... I =
[Ao Ma A., Md [4 6 4 I]
0 -I 0 I
0 -2 0
i = = =
as Ao I, A, := 34/3. Mo -23/3. and M, -22/3. Thus the compensators are
\
!
i C, (s) = -(4s + 2) c!(s) '= -(22s + 23)
.l s + 34/3 3s +34
This completes the design. Note that this design does not involve any pole-zero cancellation
l
because Frs) = I.

292  POLE PLACEMENT AND MODEL MATCHING
acceptable. However. because the two compensators L (s) / A (s) and M (s) / L (s) have different
denominators, their implementations require a total of 2m integrators. We discuss next a better
implementation that requires only III integrators and involves only the cancellation of Frs).
Consider
|     | "      | =           |     |            | = L(s) •  |     | M(s) •  |     |     |
| --- | ------ | ----------- | --- | ---------- | --------- | --- | ------- | --- | --- |
|     | lI(s)  | Cl(s)r(s) - |     | Co(s)v(s)  | --res) -  |     | --yes)  |     |     |
|     |        |             |     | -.         | A(s)      |     | A(s)    |     |     |
res) ]
|     |     | =  A-I(s)[L(s)  |     | - M(s)]  | •   |     |     |     |     |
| --- | --- | --------------- | --- | -------- | --- | --- | --- | --- | --- |
[
yes)
This can be plotted as shown in Fig. 9.4(d). Thus we can consider the two compensators as a
single compensator with twa inputs and one output with transfer matrix
|     |     | C(s) =  [Cds)  | -   | C (s}J =  | A-I(s)[L(s)  |     | - M(s)]  |     | (9.36)  |
| --- | --- | -------------- | --- | --------- | ------------ | --- | -------- | --- | ------- |
2
If we find a minimal realization of (9.36), then its dimension is m and the two compensators
can be implemented using only III integrators. As we can see from (9.31), the design involves
only the cancellation of Frs). Thus the implementation in Fig. 9.4(d) is superior to the one in
Fig. 9.4(c). We see that the four configurations in Fig. 9.4 all have two degrees of freedom and
are mathematically equivalent. However, they can be different in actual implementation.
EXAMPLE 9.9  Implement the compensators in Example 9.8 using an op-amp circuit. We write
| •      |             | •   | •          | [-(4S+2)  |             | 7.33S+7.67] [r(S)]  |        |       |     |
| ------ | ----------- | --- | ---------- | --------- | ----------- | ------------------- | ------ | ----- | --- |
|        | =           |     |            | =         |             |                     |        | .     |     |
| lI(s)  | Cl(s)r(s) - | C   | 2 (s)V(s)  |           |             |                     |        |       |     |
|        |             |     |            |           | S +  11.33  | s +                 | 11.33  | y(s)  |     |
.
[r(S)]
|     |     |            |     | I "         |  _        |     | )     |     |     |
| --- | --- | ---------- | --- | ----------- | --------- | --- | ----- | --- | --- |
|     | =   | [-47.33]+  |     | [43 ..) .)  | -7:>.38]  |     | •     |     |     |
|     | (   |            | +   |             |           |     |       |     |     |
|     |     |            | s   | 11.33       |           |     | yes)  |     |     |
Its state-space realization is, using the formula in Problem 4.10 .
.t  =
|     |     | -11.33x + [43.33  |     |     | - 75.38] [:.]  |     |     |     |     |
| --- | --- | ----------------- | --- | --- | -------------- | --- | --- | --- | --- |
lI=X+[-47.33J[:,]
(See Problem 4.14.) This one-dimensional state equation can be realized as shown in Fig. 9.5.
This completes the implementation of the compensators.
9.4  Multivariable Unity-Feedback Systems
This section extends the pole placement discussed in Section 9.2 to the multi variable case.
Consider the unity-feedback system shown in Fig. 9.6. The plant has p inputs and q outputs
and is described by a q x p strictly proper rational matrix G(S). The compensator C(s) to be
designed must have q inputs and p outputs in order for the connection to be possible. Thus
CIs) is required to be a p x q proper rational matrix. The matrix P is a q x q constant gain
mat;ix. For the time being. we assume P = I Let the transfer matrix from r to y be denoted
q.
by G,,(s). a q  x q matrix. Then we have

|     |     |     |     | 9.4  Multivariable Unity-Feedback Systems  |     |     |     | 295  |
| --- | --- | --- | --- | ------------------------------------------ | --- | --- | --- | ---- |
where
|     |     | Do  | DI  | Dp  | 0   | 0   | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     | No  | NI  | Np  | 0   | 0   | 0   |     |
|     |     |     |     | D   | Dp  |     |     |     |
|     |     | 0   | Do  | _   |     | 0   | 0   |     |
p 1
|     |         | 0   |     | N      | Np  |     |     | (9.42)  |
| --- | ------- | --- | --- | ------ | --- | --- | --- | ------- |
|     | Sm  :=  |     | No  | p _ 1  |     | 0   | 0   |         |
|     |         | o   | o   | o      |     |     |     |         |
|     |         |     |     |        | Do  | DI  | Dp  |         |
|     |         | o   | o   | o      |     |     | Np  |         |
|     |         |     |     |        | No  | NI  |     |         |
+  1 block rows; each block row consists of p D-rows and q N-rows.
| The matrix Sm  | has m  |     |     |     |     |     |     |     |
| -------------- | ------ | --- | --- | --- | --- | --- | --- | --- |
+  +
Thus Sm has (m  l)(p  q) number of rows. Let us search linearly independent rows of Sm in
order from top to bottom. It turns out that if N (s )D- I  (s) is proper. then all D-rows are linearly
independent of their previous rows. An N -row can be linearly independent of its previous rows.
However, if an N -row becomes linearly dependent, then, because of the structure of Sm, the
same N-rows in subsequent N-block rows will be linearly dependent. Let Vi  be the number of
linearly independent ith N-rows and let
|     |     |     | v := max{vI, V2, ... , v |     | q}  |     |     |     |
| --- | --- | --- | ------------------------ | --- | --- | --- | --- | --- |
It is called the row index of (;(s). Then all q N-rows in the last N-block row of Sv are linearly
dependent on their previous rows. Thus Sv-I contains all linearly independent N-rows and its
total number equals, as discussed in Section 7.8.2, the degree of (;(s), that is.
|     |     |     | +       | + ... +  | = n  |     |     | (9.43)  |
| --- | --- | --- | ------- | -------- | ---- | --- | --- | ------- |
|     |     |     | VI  Vz  |          | Vq   |     |     |         |
Because all D-rows are linearly independent and there are a total of p v D-rows in Sv-I, we
|                           |     | +                              |     |     |     | +    |     |     |
| ------------------------- | --- | ------------------------------ | --- | --- | --- | ---- | --- | --- |
| conclude that Sv-I has n  |     | pv independent rows or rank n  |     |     |     | pv.  |     |     |
Let us consider
D
|     |     |     | Do  DI  |     | p _ 1  | D"J  |     |     |
| --- | --- | --- | ------- | --- | ------ | ---- | --- | --- |
=
|     |     | So  | [ No  |     | N    |      |     |     |
| --- | --- | --- | ----- | --- | ---- | ---- | --- | --- |
|     |     |     | NI    |     | _    |      |     |     |
|     |     |     |       |     | p 1  | NIL  |     |     |
+ I) number of columns; however, it has at least a total of L;=I (J.L
| It has p(J.L  |     |     |     |     |     |     | -   | J.L;)  zero  |
| ------------- | --- | --- | --- | --- | --- | --- | --- | ------------ |
columns. In the matrix SI, some new zero columns will appear in the rightmost block column.
However, some zero columns in So will not be zero columns in SI' Thus the number of zero
columns in SI remains as
p
+  + ... +
ex  := I)J.L - J.L;)  =  pJ.L - (J.LI  J.L2  J.Lp)  =  PJ.L - n  (9.44)
;=1

|                             |     |     |          |      | 9.4 Multivariable Unity-Feedback Systems  |     |      |     | 293  |
| --------------------------- | --- | --- | -------- | ---- | ----------------------------------------- | --- | ---- | --- | ---- |
| Figure 9.5  Op-amp circuit  |     |     |          |      |                                           |     |      |     |      |
|                             |     |     | R,-l3.3  | lie  |                                           |     |      |     |      |
| implementation.             |     |     | .A       |      |                                           | vv  | 'vv  |     |      |
|                             |     |     | 'v       | 1\   |                                           |     |      |     |      |
R
|     |     |     | ROS.4  | ~   |     |     | ~   |     |     |
| --- | --- | --- | ------ | --- | --- | --- | --- | --- | --- |
-x
|     |     |     |     | V   |     | .A  | V   | .  u  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ----- | --- |
r R'l1.3
R/7.3
'VV'v
'vv
~A
|     |     |     |     |     |     |     | /  R  |     |     |
| --- | --- | --- | --- | --- | --- | --- | ----- | --- | --- |
-y
|     |     |     |     |             |         |     | '"  'v      | "       |     |
| --- | --- | --- | --- | ----------- | ------- | --- | ----------- | ------- | --- |
|     |     |     |     | e(S)        |         |     | G(s)        |         |     |
|     |     |     |     | ----------- |         |     | ----------- |         |     |
|     |     | +   | •   |             |         |     |             |         |     |
|     |     |     |     |             |         |     | D -I (5)    |         | ~.  |
|     | ~P  |     |     | 8(s)        | A-I(s)  |     |             | !'its)  |     |
I
I
|     |     |     | L _____  |     |     | L   | _____  |     |     |
| --- | --- | --- | -------- | --- | --- | --- | ------ | --- | --- |
Multivariable unity feedback system with P = I
|     | Figure 9.6  |     |     |     |     |     | q.  |     |     |
| --- | ----------- | --- | --- | --- | --- | --- | --- | --- | --- |
+
|     |     |     |     | Go(s) =  [Iq  | G(s)C(sWIG(s)C(s)  |     |     |     |     |
| --- | --- | --- | --- | ------------- | ------------------ | --- | --- | --- | --- |
=
|     |     |     |     | G(s)C(s)[l |     | +  G(S)C(sWI  |     |     |     |
| --- | --- | --- | --- | ---------- | --- | ------------- | --- | --- | --- |
q
+
|     |     |     |     | = G(s)[lp  |     | C(s)G(sWIC(s)  |     |     | (9.37)  |
| --- | --- | --- | --- | ---------- | --- | -------------- | --- | --- | ------- |
The first  equality is  obtained from  yes)  =  G(s)C(s)[r(s) - y(s)]:  the  second one from
e(s) = res) - G(s)C(s)e(s): and the third one from lies) = C(s)[r(s) - G(s)li(s)]. They can
+
also be verified directly. For example. pre- and postmultiplying by [Iq  G(s)C(s)] in the first
two equations yield
|     |     |              |     | +                |     | +                  |     |     |     |
| --- | --- | ------------ | --- | ---------------- | --- | ------------------ | --- | --- | --- |
|     |     | G(s)C(s)[lq  |     | G(s)C(s)] = [Iq  |     | G(s)C(sl]G(s)C(s)  |     |     |     |
which is an identity. This establishes the second equality. The third equality can similarly be
establishaQ.
|     |     | =   |     |     |     |     |     | =   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Let G(s)  N(s)D-1( s) be a right coprime fraction and let C(s)  A - I (S)B(5) be a left
fraction to be designed. Then (9.37) implies
|     |                        |     |     | +                  |     | 1   |                    |     |     |
| --- | ---------------------- | --- | --- | ------------------ | --- | --- | ------------------ | --- | --- |
|     | Go(s) = N(S)o-l (s)[1  |     |     | A -I (s)B(s)N(s)D- |     |     | (SWI A - 1(s)B(s)  |     |     |
l
|     |     | = N(s)D-        | 1(s) lA-'(s)[A(s)D(S)  |                |     | + B(s)N(s)]D-1(s)r |     | A-1(s)B(s)  |        |
| --- | --- | --------------- | ---------------------- | -------------- | --- | ------------------ | --- | ----------- | ------ |
|     |     | =               |                        | +              |     |                    |     |             |        |
|     |     | N(s»)[A(s)D(s)  |                        | B(s)N(sW'B(s)  |     |                    |     |             |        |
|     |     | =               | 1                      |                |     |                    |     |             |        |
|     |     | N(s)F-          | (s)B(s)                |                |     |                    |     |             | (938)  |

294  POLE PLACEMENT AND MODEL MATCHING
where
|     |     |     | A(s)D(s)  | +  8(s)N(s) = F(s)  |     |     |     |     | (9.39)  |
| --- | --- | --- | --------- | ------------------- | --- | --- | --- | --- | ------- |
It is a polynomial matrix equation. Thus the design problem can be stated as follows: given
p x p D(s) and q x p N(s) and an arbitrary p x p F(s), find p x p A(s) and p x q 8(5) to
meet (9.39). This is the matrix version of the polynomial compensator equation in (9.12).
>
Theorem 9.Ml
Given polynomial matrices D(s) and N(s). polynomial matrix solutions A(s) and 8(5) exist in (9.39)
for any polynomial matrix F(s) if and only if D(s) and N (5) are right coprime.
Suppose D(s) and N(s) are not right coprime, then there exists a nonunimodular polyno
|     |     |     | =   |     |     | =   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
mial matrix R(s) such that D(s)  D(s)R(s) and N(s)  N(s)R(s). Then F(s) in (9.39) must
be of the form F(s)R(s), for some polynomial matrix F(s). Thus if F(s) cannot be expressed
in such a form, no solutions exist in (9.39). This shows the necessity of the theorem. If D(s)
and N(s) are right coprime, there exist polynomial matrices A(s) and 13(5) such that
+
|     |     |     | A(s)D(s)  | B(s)N(s) = I  |     |     |     |     |     |
| --- | --- | --- | --------- | ------------- | --- | --- | --- | --- | --- |
The polynomial matrices A(s) and B(s) can be obtained by a sequence of elementary oper
|     |     |     |     |     |     | =   |     | =   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
ations. See Reference [6, pp. 587-5951. Thus A(s)  F(s)A(s) and B(s)  F(s)B(s) are
solutions of (9.39) for any F(s). This establishes Theorem 9.MI. As  in the scalar case, it
is possible to develop general solutions for (9.39). However, the general solutions are not
convenient to use in our design. Thus they will not be discussed.
Next we will change solving (9.39)  into solving a set of linear algebraic equations.
=
Consider (;(5)  N(s)D-I(s), where D(s) and N(s) are right coprime and D(s) is column
reduced. Let JLi  be the degree of the ith column of D(s). Then we have, as discussed in
Section 7.8.2.
| deg(;(s) = degdet D(s) = JLI  |     |     |     |     | +   | + ... +  | =: n   |     | (9.40)  |
| ----------------------------- | --- | --- | --- | --- | --- | -------- | ------ | --- | ------- |
|                               |     |     |     |     |     | JLz      | f.l.p  |     |         |
Let f.I.  := max(f.l.I, JLz •...• JLp)' Then we can express D(s) and N(s) as
|     |            |     | +    | +  z  + ... +  |     |       |          |     |     |
| --- | ---------- | --- | ---- | -------------- | --- | ----- | -------- | --- | --- |
|     | D(s) = Do  |     | DIs  | D s            |     | D"s"  | D" 1= 0  |     |     |
1
|     |            |     | +    | +  I  + ... +  |                             |       |     |                   |     |
| --- | ---------- | --- | ---- | -------------- | --------------------------- | ----- | --- | ----------------- | --- |
|     | N(s) = No  |     | Nls  | Nzs            |                             | N"s"  |     |                   |     |
|     |            |     | =    | =  ... =       | f.l.p. Note also that N" =  |       |     | O. following the  |     |
Note that D" is singular unless f.l.1  f.l.z
strict properness assumption of (;(s). We also express A(s). 8(5), and F(s) as
|     |            |     | +   | +                          | + ... +  |        |     |     |     |
| --- | ---------- | --- | --- | -------------------------- | -------- | ------ | --- | --- | --- |
|     | A(s) = Ao  |     |     | Ais  Azs2                  |          | Ams"'  |     |     |     |
|     |            | =   | +   | +                          | + ... +  |        | sm  |     |     |
|     | 8(5)       |     | 8   | 8 15  Bzs2                 |          | 8      |     |     |     |
|     |            |     | 0   |                            |          | m      |     |     |     |
|     |            |     | +   | + F sZ + ... + F,,+ms,,+m  |          |        |     |     |     |
|     | F(s) = Fo  |     |     | Fis                        |          |        |     |     |     |
2
Substituting these into (9.39) and matching the coefficients of like powers of s, we obtain
| (Ao  | 8 AI  | 8   | Am   | 8m1Sm =  | [Fo  | FI  ...  | F,,+ml =: F  |     | (9.41)  |
| ---- | ----- | --- | ---- | -------- | ---- | -------- | ------------ | --- | ------- |
|      | 0     | 1   | ••.  |          |      |          |              |     |         |

L96  POLE PLACEMENT AND MODEL MATCHING
In fact, this is the number of zero columns in S""  =  2. 3 ..... Let S"_I be the matrix S,,_I
In
+  +
after deleting these zen:> columns. Because the number of columns in S'" is p(IL  I  Ill). the
number of columns in S"_I is
|     |       | f3:=  |        | +  I  +  | I) -   |         | pu +n  | (9-15)  |
| --- | ----- | ----- | ------ | -------- | ------ | ------- | ------ | ------- |
|     |       |       | p(J.L  | u -      | (PJ.L  | -11) =  |        |         |
|     | 5"-1  |       |        |          |        | +       | 5"_1   |         |
The rank of  clearly equals the rank of SI'_I or pu  n. Thus  h as full column rank.
Now if 111  increases by  I. the rank and the number of the columns of  S"  both increase by
| l' (because the  |     |     |     |     |     |     |     | 5"  |
| ---------------- | --- | --- | --- | --- | --- | --- | --- | --- |
p new D-rov,'s are all linearly independent of their previous rows): thus
still has full column rank. Proceeding forward, we conclude that S""  for III ::: /1  - I. has full
column rank.
Let us define
|     |     |     | H,(s) := diag(s" |     | l, 51"  | • ...• S"P)  |     | ( 9-16)  |
| --- | --- | --- | ---------------- | --- | ------- | ------------ | --- | -------- |
and
|     |     |     | H .. (05)  | = diag(s"'l . 5""  |     | . ... • 5"',0)  |     | (9.-17)  |
| --- | --- | --- | ---------- | ------------------ | --- | --------------- | --- | -------- |
Then we have the following matrix version of Theorem 9.2.
Theorem 9.M2
=  I
Consider the unity, feedback system shown in Fig. 9.6 with P  q. The plant is described by a q  x  p
=
slrictly proper rational matrix G(s)  Let G(s) be faclored as G(s)  N(s)D-1 (s). where D(s) and
= l. 2 ..... p. Let u
1'1(5) are right copri,:,e and D(s) is column reduced with column degrees J.Li.  i
=
be Ihe row index of G(s) and lei Ini  ::: u - I for i  1.2 . ... . p. Then for any p x  p polynominal
matrix F(s). such that
|     |     |     |     | lim H;I(S)F(s)H;I(S) = Fh  |     |     |     | (9-18)  |
| --- | --- | --- | --- | -------------------------- | --- | --- | --- | ------- |
s- x
is a nonsingular constant matri.\. there exists a p X  q proper compensator A -I (5 )B(s). whae A (s) is
row reduced with row degrees III I.  such thar the transfer matrix from r to y equals
|     |     |     |     | G,,(5) = N(s)F- | l (5)B(.I)  |     |     |     |
| --- | --- | --- | --- | --------------- | ----------- | --- | --- | --- |
Furthennore. the compensatl.lr can be obtained by soh'ing sets of linear algebraic equation, in 19..l1 1.
-?
| Proof"  | Let /II  | =  max (/III, /lie .....  |     | III p). Consider the constant matrix  |         |           |     |     |
| ------- | -------- | ------------------------- | --- | ------------------------------------- | ------- | --------- | --- | --- |
|         |          |                           | F   | := [Fo FI                             | F,  ."  | F"'.,-el  |     |     |
+  +
It is formed from the coefficient matrices of F(s) and has order p x (Ill  /1  I). Clearly
|     |     |     |     | +   |     | f   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
F(,»  has column degrees at most 111  J.Li. Thus  has at least a number of zero columns.
where a  is given in (9.-1·<).  Furthennore. the positions of these zero columns coincide
|     |     |     | F   |     |     | F   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
with those of S""  Let  be the constant matrix  after deleting these zero columns. Now
consider
-
-
|     |     |     | [Ao Bo AI BI ... Am BmIS", =  |     |     |     | F   | (9.-19)  |
| --- | --- | --- | ----------------------------- | --- | --- | --- | --- | -------- |

|     |     |     |     | 9.4 Multivariable Unity-Feedback Systems  |     |     |     |     | 299  |
| --- | --- | --- | --- | ----------------------------------------- | --- | --- | --- | --- | ---- |
I which yields. as in Example 7.7.
|     |     | dl  | 0   | 0      | 0  0  | 0   | 0  0  |     |     |
| --- | --- | --- | --- | ------ | ----- | --- | ----- | --- | --- |
|     |     | 0   | d2  | 0  0   | 0     | 0   | x  x  |     |     |
| I   |     | 0   | 0   | x      |       |     |       |     |     |
|     |     |     | nl  |        | 0     | 0   | 0  0  |     |     |
|     |     | 0   | 0   | 0  n2  | 0     | 0   | 0  0  |     |     |
r=1
|     |     | 0   | 0   | 0  0  | dl  | 0   | 0  0  |     |     |
| --- | --- | --- | --- | ----- | --- | --- | ----- | --- | --- |
d2
|     |     | 0   | 0   | 0  0  | 0   |     | 0  0  |     |     |
| --- | --- | --- | --- | ----- | --- | --- | ----- | --- | --- |
~
|     |     | 0   | 0   | 0  0  | 0   | 0   | nl  0  |     |     |
| --- | --- | --- | --- | ----- | --- | --- | ------ | --- | --- |
|     |     | 0   | 0   | 0  0  | 0   | 0   | 0  0   |     |     |
'~
I  The matrix q is not needed and is not typed. In the matrix r. we use x. di. and ni to denote
g
nonzero entries. The nonzero diagonal entries of r yield the linearly independent columns of S'I
or, equivalently. linearly independent rows ofSI. We see that there are two linearly independent
.~
~  NI-rows and one linearly independent N2-row. The degree of G(5) is 3 and we have found
,
three linearly independent N-rows. Therefore there is no need to search further and we have
~:'
VI  = 2 and V2  =  I. Thus the row index is V  = 2. We select ml =  m2  =  m =  v-I =  I. Thus
|     |     |     |     |     | +   | =   |     | +  =  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ----- | --- |
for any column-reduced F(5) of column degrees m  /11  3 and m  /12  2. we can find a
J  proper compensator such that the resulting unity-feedback system has F(s) as its denominator
matrix. Let us choose arbitrarily
~
(S2 + 45 + 5) (s + 3)
[
|     | F(s) =  |               |     | 0   |     |       | ~s    |     |         |
| --- | ------- | ------------- | --- | --- | --- | ----- | ----- | --- | ------- |
|     |         |               |     |     |     | s2 +  | + 5]  |     |         |
|     |         |               |     |     | 2   | 3     |       |     |         |
| ~   |         | =  [15+17S;75 |     |     |     |       |       |     |         |
|     |         |               |     |     | +5  |       | 2~    |     | (9.52)  |
~
|     |     |     |     |     |     | 5 +  | + 52 ]  |     |     |
| --- | --- | --- | --- | --- | --- | ---- | ------- | --- | --- |
,-
| ',::"  and form (9.41) with m =  |     | v - I =  | I:  |     |     |     |     |     |     |
| -------------------------------- | --- | -------- | --- | --- | --- | --- | --- | --- | --- |
.~
| ~~  |     | I   | 0   | 0   | 0   | I   | 0  0  | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | ----- | --- | --- |
| '~  |     | ~   |     |     |     |     |       |     |     |
|     |     |     | 0   | 0   |     | 0   | 0  0  | 0   |     |
.j'
|     |     | I   |     | 0   | 0   | 0   | 0  0  | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | ----- | --- | --- |
f
|     |     | 0   |     | 0   | 0   | 0   | 0  0  | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | ----- | --- | --- |
l
[Ao Bo Al BJl
<,
| ,   |     | 0   | 0   | 0   | 0   |     |       | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | ----- | --- | --- |
|     |     |     |     |     |     | 0   | 0  I  |     |     |
•
.i
| :1   |     | 0   | 0   | 0   | 0   | 0   | 0   | 0   |     |
| ---- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
,
| :~  |     | l   |     |     |     |     |       |     |     |
| --- | --- | --- | --- | --- | --- | --- | ----- | --- | --- |
|     |     |     | 0   | I   |     | 0   | 0  0  | 0   |     |
| "   |     | ~   |     |     |     |     |       |     |     |
| l   |     |     | 0   | 0   | I   | 0   | 0  I  | 0   |     |
•
"
| " d     |     |      |     | 0  17  | 0   | 7   | 0  I    |     |         |
| ------- | --- | ---- | --- | ------ | --- | --- | ------- | --- | ------- |
|         |     | [I~  |     |        |     |     | 0] =F-  |     | (9.53)  |
=
|     |     |     |     | 5  0  | 2   | 0   | I  0  0  |     |     |
| --- | --- | --- | --- | ----- | --- | --- | -------- | --- | --- |
F
The a in (9.44) is I for this problem. Thus SI  and  both have one zero column as we can
51
see in (9.53). After deleting the zero column, the remaining  has full column rank and. for
F.  51
any  solutions exist in (9.53). The matrix  has order 8 x 7 and solutions are not unique.

297
94 MuitivariabJe Unity-Feedback Systems
It is obtained from (9.41) by deleting a number of zero columns in S", and the con'espond
| -   |     | F.  |     | 8   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
in!! zero columns in  ~ow because  has full column rank if III >   \' - 1. we conclude
|     |     |     |     | m   |     |     | -   |
| --- | --- | --- | --- | --- | --- | --- | --- |
that for any F(s) of column degrees at most m +
Mi. solutions A, and B, exist in (949). Or.
equivalently. polynomial matrices A(s) and 8(5) of row degree III or less exist in (9.49).
8
Note that generally  has more rows than columns: therefore solutions of (9.-19) are not
m
unique.
Next we show that A -I (s)B(s) is proper. Note that 0" is. in general. singular and the
method of proving Theorem 9.2 cannot be used here. Using H,(s) and H,.(s). we write.
as in (7.80),
+
|     |     | 0(5) =  | [D h,  | Dlr(s)H: | I(s)]He(S)  |     |     |
| --- | --- | ------- | ------ | -------- | ----------- | --- | --- |
+
|     |     | N(s) =  | [N  | N,,(s)H: | I(s)]H,(s)  |     |     |
| --- | --- | ------- | --- | -------- | ----------- | --- | --- |
he
+
|     |     | A(s) = H,(s)[A |     | h,  | H; t(s)AI,(s)]  |     |     |
| --- | --- | -------------- | --- | --- | --------------- | --- | --- |
+
|     |     | 8(5) = H,(s)[8",  |     |     | H; I(s)8Ir(s)]  |     |     |
| --- | --- | ----------------- | --- | --- | --------------- | --- | --- |
+
|     |     | F(s) = H,(s)[Fh  |     | H;I(S)FI(sJH:I(s)]He(s)  |     |     |     |
| --- | --- | ---------------- | --- | ------------------------ | --- | --- | --- |
where Dds)H;:-1( 5). Nlc (5 )H;:-I (s), H; I (s )AI, (5). H,:-I (5) BI, (5). and H;-I (siFI (.I m ;-I\i)
are all strictly proper rational functions. Substituting the above into (9.39) yields. at s = x.
Ah,D", + BI"i'II'1(
= Fh
| which reduces to. because N'I<' =  |     |     |     | 0 following strict properness of G(s).  |     |     |     |
| ---------------------------------- | --- | --- | --- | --------------------------------------- | --- | --- | --- |
Ah,D'I( = Fh
Because D(s) is column reduced. Dhe is nonsingular. The constant matrix F" is nOl1singular
by assumption: thus A:"  =  F"D;;-c'  is nonsingular and A(5) is row reduced. Therefore
A - I (5)B(5) is proper (Corollary 7.8). This establishes the theorem.  Q.E.D.
A polynomial matrix F(s) meeting (9.-18) is said to be rOlf-colulIlIl reduced with W\\·
Ill,
|     |     |     |     | =   | = ... =  |     |     |
| --- | --- | --- | --- | --- | -------- | --- | --- |
degrees 111,  and column degrees fJ..i.  If /111  ffl"  =  111.  then the row-column
+  11,. In application.
reducedness is the same as column reducedness with column degrees III
we can select F(s) to be diagonal or triangular with polynomials with desired roots as  its
I
diagonal entries. Then F- (5) and. consequently. G,,(s) have the desired roots as their poles.
|     |     |     |     | +   |     | +   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
Consider again S,,- I' It is of o_rder (p  q)v x  (il  vip. It has ex  =  PM  - n number
|     |     |     |     |     |     | +   | +   |
| --- | --- | --- | --- | --- | --- | --- | --- |
of zero columns. Thus the matrix_S,,_1 is of order (p  q)v  X  [(II  l')p  - (I'll  - 1/)] or
+  q)v x (vp  +  1/). The matrix S,'_I contains pv linearly !ndependent D-rows but cOnlJins
(p
only VI  + ... +  v"  = 1/ linearly independent N-rows. Thus S,,_I contains
|     |     |     | := (I'  +  | q)v - | I'V -1/ =  |         |     |
| --- | --- | --- | ---------- | ----- | ---------- | ------- | --- |
|     |     |     | )I         |       |            | ql!-II  |     |
linearly dependent N -rows. Let 8,,_1 be the matrix 8,,_1 after deleting these linearly dependent
N-rows. Then the matrix 5,_1 is of order
|     |      | +      |              |       | +           | +             | +    |
| --- | ---- | ------ | ------------ | ----- | ----------- | ------------- | ---- |
|     | [(p  | q)l' - | (qv -II)] x  | (vI'  | 11) =  (vp  | 11)  X (I'{)  | /1)  |
Thus 5,'_1 is square and nonsingular.

298  POLE PLACEMENT AND MODEL MATCHING
=
|     | Consider (9.49) with m  |     |     |      |                  | v - I:  |     |     |               |     |     |     |
| --- | ----------------------- | --- | --- | ---- | ---------------- | ------- | --- | --- | ------------- | --- | --- | --- |
|     |                         |     |     | KSv_ | := (Ao Bo AI BI  |         |     | A   | Bv-dSv-1 = F  |     |     |     |
|     |                         |     |     |      | 1                |         |     |     | 1             |     |     |     |
V-
It actually consists of the following p sets of linear algebraic equations
|     |     |     |     |     |     | -   | -   |            |      |     |     |         |
| --- | --- | --- | --- | --- | --- | --- | --- | ---------- | ---- | --- | --- | ------- |
|     |     |     |     |     |     |     | =   | =          |      |     |     |         |
|     |     |     |     |     | kjS |     | fj  | i  I, 2 .. | . "  | p   |     | (9.50)  |
v_1
|     |     |     | f;  |     |     |     | F,  |     |     | 8   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
wher e   k; and  are the ith row ofK and  respectively. Because  v_1  has full column rank, for
r ..
|      | solutions k; exist in (9.50). Because  |     |     |     |     |     |     | 8                                             |     |     |     |     |
| ---- | -------------------------------------- | --- | --- | --- | --- | --- | --- | --------------------------------------------- | --- | --- | --- | --- |
| any  |                                        |     |     |     |     |     |     | v- has more y rows than columns, the general  |     |     |     |     |
1
solution of (9.50) contains y
free parameters (Corollary 3.2). If m in Sm increases by I from
| v - | I to v, then the number of rows of  |     |     |     |     |     | 8   |                  | +   |                     | 8   |            |
| --- | ----------------------------------- | --- | --- | --- | --- | --- | --- | ---------------- | --- | ------------------- | --- | ---------- |
|     |                                     |     |     |     |     |     | v   | increases by (p  |     | q) but the rank of  | v   | increases  |
+
only by p. In this case, the number of free phrarneters will increase from y to y  q. Thus in
the Mllv!O case, we have a great deal offreedom in carrying out the design.
We discuss a special case of (9.50). The matrix  8 has y linearly dependent N-rows. If
v-
1
we delete these linearly dependent N -rows from Sv-l and assign the corresponding columns
| in B; as zero, then (9.50) becomes  |     |     |     |     |      |     |           |             |     |     |     | .   |
| ----------------------------------- | --- | --- | --- | --- | ---- | --- | --------- | ----------- | --- | --- | --- | --- |
|                                     |     |     |     |     | (Ao  | Bo  | ... Av-I  | Bv-dSv-1 =  |     | F   |     |     |
5
where  is. as discussed earlier, square and nonsingular. Thus the solution is unique. This
v_ 1
is illustrated in the next example.
| EXAMPLE 9.10  |     |     | Consider a plant with the strict:ly] [pr oper trransfer matrix  |     |     |          |     |     |     |     |     |     |
| ------------- | --- | --- | --------------------------------------------------------------- | --- | --- | -------- | --- | --- | --- | --- | --- | --- |
| ·l~           |     |     |                                                                 |     |     | 1/5]=[1  |     |     |     |     |     |     |
l
| t·  |     |     |          | [1~2  |     |     |     | ~   | ~   |     |     |         |
| --- | --- | --- | -------- | ----- | --- | --- | --- | --- | --- | --- | --- | ------- |
|     |     |     | (;(5) =  |       |     |     |     |     |     |     |     | (9,51)  |
=: N(5)D-1 (5)
|     |     |     |     |     |     | lis  | 0   |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | ---- | --- | --- | --- | --- | --- | --- |
=
':1  The fraction is right coprime and D(s) is column reduced with column degrees III  2 and
=
| .~~  112  | I. We write  |     |     |     |     |     |     |     |     |     |     |     |
| --------- | ------------ | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
J
| .':~  |     |     |     |       | =   | 0   | 0 ] + [0 |   0 ]  | + [I |   0 ]  ,  |     |     |
| ----- | --- | --- | --- | ----- | --- | --- | -------- | ------ | ---- | --------- | --- | --- |
|       |     |     |     |       |     | 0   | 0        | 0  1   | 0    |   0   r   |     |     |
|       |     |     |     | D(s)  |     | [   |          | s      |      |           |     |     |
,~ .'
and
,j
|     |     |     |     | N(S)=[~  |     |     | :] + | [~  ~]s+[~  |     | ~]s2  |     |     |
| --- | --- | --- | --- | -------- | --- | --- | ---- | ----------- | --- | ----- | --- | --- |
, .,'~ ,I
~1
;:1  We use MATLAB to compute the row index. The QR decomposition discussed in Section 7.3.1
"  can reveal linearly independent columns. from left to right, of a matrix. Here we need linearly
~tl  independent rows. from top to bottom, of Sm; therefore we will apply QR decomposition to
the transpose of Sm. We type
|     | dl=       | (O  | 0  0  0  | 1  OJ             | ;d2=[O 0  |          | 0  1  | 0  OJ ;   |     |     |     |     |
| --- | --------- | --- | -------- | ----------------- | --------- | -------- | ----- | --------- | --- | --- | --- | --- |
|     | n 1 = [1  |     | 1  0  0  | 0  0 J ; n2 = [0  |           | 1        | 0  0  | 0  0 J ;  |     |     |     |     |
|     | sl=[dl    |     | 0  O;d2  | 0                 | O;nl      | 0  0;n2  | 0     | 0; ...    |     |     |     |     |
o
|     |     | 0   | dl; O 0  | d2; | 0  0  | nl ;O 0  | n2J | ;   |     |     |     |     |
| --- | --- | --- | -------- | --- | ----- | -------- | --- | --- | --- | --- | --- | --- |
[q,r]=qr(sl')

300  POLE PLACEMENT AND MODEL MATCHING
!:  In searching the row index. we knew that the last row of 51  is a linearly dependent row. If
we delete the row. then we must assign the second column of BI as 0 and the solution will be
unique. We type
|     | d1 = [0  | 0  0        | 0  0           | 1 J ; d2 = [ 0  | 0   | 0 10  | 0J;          |         |       |         |
| --- | -------- | ----------- | -------------- | --------------- | --- | ----- | ------------ | ------- | ----- | ------- |
|     | n1=      | [:  1  0    | 0  0           | OJ ;n2=[0       | 10  | 0     | 00J          | ;       |       |         |
|     | dl t     | =[ 0  0  0  | 0  1 J ; d2 t  | = [C            | 0   | 0 1   | OJ;nlt=[O 1  |         | 0  0  | 01 ;    |
|     | slt=[dl  | 0;d2        | O;nl           | 0;n2            | 0;  | 0  0  | d1t;0        | 0  d2t; | O  0  | nltJ ;  |
|     | flt      | =[lS  0     | 17  0          | '7  1J;         |     |       |              |         |       |         |
fl t/slt
~
,
L1
F.
,j  which yields [7  - 17  15  - 15  1 0  17]. Computing once again for the second row of  we
can finally obtain
·'1
0]
| '.'          |     |               |     |     |       | -17  | 15  | -15  | 1     | 0   |
| ------------ | --- | ------------- | --- | --- | ----- | ---- | --- | ---- | ----- | --- |
| y~           |     |               |     |     | = [~  |      |     |      |       | 17  |
| ,  .J.  ~    |     | [Ao Bo Al Bd  |     |     |       |      |     |      |       | o   |
| ; .- .       |     |               |     |     |       |      |     | o    | 5  0  | 0   |
2
.' ~
Note that MATLAB yieJds the first 7 columns; the last column 0 is assigned by us (due to
~~~
"  deleting the last row of SJ}. Thus we have
)
-;5]
|     |     | A(S)=[7~S  |     |     | -17 ]  |     | B(s) = [ 15 ~ 175  |     |     |     |
| --- | --- | ---------- | --- | --- | ------ | --- | ------------------ | --- | --- | --- |
| .,  |     |            |     |     | 2+5    |     |                    |     |     |     |
'.'
'.~  and the proper compensator
'l
| .,  |     |     | C(s  | =[5+7  |     | -17]-1[175+15  |     |     |     | -IS]  |
| --- | --- | --- | ---- | ------ | --- | -------------- | --- | --- | --- | ----- |
|     |     |     |      | )      | 0   | 5+2            |     |     | 0   | 5     |
will yield the overall transfer matrix
]-1
o
|     |     |        | = [~  | :][ (52 + 45 ~ 5)(5 +  |     |     |     |     |     |     |
| --- | --- | ------ | ----- | ---------------------- | --- | --- | --- | --- | --- | --- |
|     |     | Go(s)  |       |                        |     |     |     | 3)  |     |     |
+ 25 + 5
52
-;5]
| ~   |     |     |     | x[175;15  |     |     |     |     |     |     |
| --- | --- | --- | --- | --------- | --- | --- | --- | --- | --- | --- |
':l  (9.5.+)
This transfer matrix has the desired poles. This completes the design.
The design in Theorem 9.M2 is carried out by using a right coprime fraction of G(5). We
state next the result by using a left coprime fraction of G(s).
)- Corollary 9.M2
Consider the unity-feedback system shown in Fig. 9.7. The plant is described by a q x p strictly proper
rational matri:, G(s). Let G(s) be factored as G(5)  =  D-I(s)N(s). where 0(5) and N(5) are left
i =
coprime and D(s) is row reduced with row degrees v,.  I. 2 •... , q. Let I.l. be the column index of
G(s) and let mj ?: I.l. - I. Then for any q x q row-column reduced polynominal matrix F(s) such that
|     |     | ,                                       |     |     |     | )F-(s)dla' g (s -m,  |     |     |                 |               |
| --- | --- | --------------------------------------- | --- | --- | --- | -------------------- | --- | --- | --------------- | ------------- |
|     |     | 1. m d'J ag (s- "' , s -",. , .... s -v |     |     |     |                      |     |     | , s -m.·  , ... | . s -m ) = F- |
|     |     |                                         |     |     |     | q                    |     |     |                 | q  II         |
s-oc

1
9.4 Multivariable Unity-Feedback Systems  303
~,   This N(s) has rank 2 at every s: thus GI (s) has no transmission zero. Consider the 2 x 2 proper
rational matrix
'3
|         |        | S~2  |      |       |           | ][S+2  | 0]-1  |
| ------- | ------ | ---- | ---- | ----- | --------- | ------ | ----- |
| -~:. .  |        | [    |      | ]=[S  |           | o      |       |
|         | G      |      |      | 0     |           |        |       |
| ,       | (s) =  |      |      |       |           |        |       |
|         | 2      |      | -s + | 2     | 0  s + 2  |        |       |
| r.      |        | o    |      |       |           | 0      | s     |
s
":1  ;~
1
This N (s) has rank  I at s = 0 and s =  -2. Thus Gz (s) has two transmission zeros at 0 and
)
J  -2. Note that G(s) has poles also at 0 and -2.
From this example. we see that a transmission zero cannot be defined directly from G(s);
it must be defined from its coprime fraction. Either a right coprime or left coprime fraction
can be used and each yields the same set of transmission zeros. Note that if G(s) is square
| =   |     | I  = D-I  |     |     |     |     |     |
| --- | --- | --------- | --- | --- | --- | --- | --- |
and if G(s)  N(s)D- (s)  (s)N(s), where N(s) and D(s) are right coprime and D(s)
and N(s) are left coprime, then the transmission zeros of G(s) are the roocs of det N(s) or the
roots of det  N  (s). Transmission zeros can also be defined from a minimal realization of G(s).
~et (A, B, C, D) be any n-dimensional minimal realization of a q x  p proper rational matrix
G(s). Then the transmission zeros are those A such that
B]
|     |     |       | U-A  |     | +    |            |     |
| --- | --- | ----- | ---- | --- | ---- | ---------- | --- |
|     |     | rank  | -C   | D   | < n  | min(p, q)  |     |
[
This is used in the MATLAB function  tzero to compute transmission zeros. For a more
detailed discussion of transmission zeros, see Reference [6, pp. 623-635].
Now we are ready to discuss the conditions for achieving tracking or for meeting (9.59).
Note that N(s), F(s), and B(s) are q x p, p x p, and p x q. Because Iq has rank q. a necessary
condition for (9.59) to hold is that the q x  p matrix N(O) has rank q. Necessary conditions
| =   |     |     | =   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
for p(N(O»  q are p ~ q and s  0 is not a transmission zero of G(s). Thus we conclude
that in order for the unity-feedback configuration in Fig. 9.6 to achieve asymptotic tracking.
the plant must have the following two properties:
•  The plant has the same or a greater number of inputs than outputs .
•  The plant transfer function has no transmission zero at s = O.
Under these conditions. N(O) has rank q. Because we have freedom in selecting F(s). we can
| select it such that B(O) has rank q and the q x q constant matrix N(O)F- |     |     |     |     |     |     | I   |
| ------------------------------------------------------------------------ | --- | --- | --- | --- | --- | --- | --- |
(O)B(O) is nonsingular.
Under these conditions. the constant gain matrix P can be computed as
|     |     |     | =                  |     |     | I   |         |
| --- | --- | --- | ------------------ | --- | --- | --- | ------- |
|     |     |     | P  [N(O)F-I(O)B(OW |     |     |     | (9.60)  |
Then we have Go(O)  =  I q, and the unity-feedback system in Fig. 9.6 with P in (9.60) will
track asymptotically any step reference input.
9.4.2  Robust Tracking and Disturbance Rejection
As in the SISO case. the asymptotic tracking design in the preceding section is not robust. In
this section. we discuss a different design, To simplify the discussion. we study only plants with

|     |     | 9.4  tvlultivariable Unity-Feedback Systems  |     |     | 301  |
| --- | --- | -------------------------------------------- | --- | --- | ---- |
Cis)
| ----------- |     | ----------- | G(.<)  |     |     |
| ----------- | --- | ----------- | ------ | --- | --- |
,
'  ,
r  .i:.----
| , ~     |          | ~ N  |         |      | .   |
| ------- | -------- | ---- | ------- | ---- | --- |
| A-'(s)  | ~ ills)  |      | ~ b ..  | iu)  | ~   |
-,  (s)
~
|        |        | ,         |              | ,   |     |
| ------ | ------ | --------- | ------------ | --- | --- |
| I L"   |        | '         |              |     |     |
|   ____ | _ __ _ | __ __ I   |              |     |     |
|        |        |   L  ____ | __ ______ [  |     |     |
Unity feedback with G(5) = 0-)
Figure 9.7  (s)N(5).
i~ a nonsingular constant matrix. there exists a p x q proper compensator C(5) = B(5)A -) (5), where
A(s) is column reduced with column degrees m  to meet
I,
|     | O(s)A(s)  | +  N(5)8(5) =  | F(5)  |     |     |
| --- | --------- | -------------- | ----- | --- | --- |
(9.551
and the transfer matrix from r to y equals
|       | -         | - - -I     | -        |     |         |
| ----- | --------- | ---------- | -------- | --- | ------- |
|       | G,,(s) =  | 1 - A(s)F  | (5)015)  |     | (9.561  |
| - = - | -         | = -        | - -I     |     |         |
Substituting G(s)  O- IN(s) and C(s)  B(s)A  (s) into the first equation in (9.37)
yields
+ 0-1( s )N(5 )8(s)A -I (sW
| Go(s) =  [I  |     |     | 0-1 (5)1'; (s)BIs)A -I (5)  |     |     |
| ------------ | --- | --- | --------------------------- | --- | --- |
'
+
| = A(s)[O(s)A(s)  |     | N(s )B(sW I N(s)B(5)A - |     | I (5)  |     |
| ---------------- | --- | ----------------------- | --- | ------ | --- |
which becomes. after substituting (9.55),
| G,,(s) = A(s)F-1 (5)[F(s) - |        |             |     | I    |     |
| --------------------------- | ------ | ----------- | --- | ---- | --- |
|                             |        | 0(5)A(5)]A- |     | (5)  |     |
|                             | = 1 -  | I(5)0       |     |      |     |
|                             | A(s)F- | (s)         |     |      |     |
This establishes the transfer matrix from r to y in the theorem. The design in Corollary 9.1'.11
hinges on solving (9.55). Note that the transpose of (9.55) becomes (9.39): left coprime and
row reducedness become right coprime and column reducedness. Thus the linear algebraic
equation in  (9.41) can be used to solve the transpose of (9.55).  We  can also solve (9.55)
directly by forming
|     |     | o  o  |     | o  o  |     |
| --- | --- | ----- | --- | ----- | --- |
0 No
0
Bo
|     |          | 00  |     | o  o  |     |
| --- | -------- | --- | --- | ----- | --- |
|     | 0 ,  NI  | No  |     |       |     |
Ao
B,
| T",  I  A,  |          |           |     | o  o  |     |
| ----------- | -------- | --------- | --- | ----- | --- |
|             | Dn  N'l  | On-I  Nn- |     |       |     |
I
o  o
|     |     | 0"  N |     | 0 No  |     |
| --- | --- | ----- | --- | ----- | --- |
|     |     |       | n   | 0     |     |
Bm
Am
|     | o  o  | o  o  |     |     |     |
| --- | ----- | ----- | --- | --- | --- |
N"
On

302  POLE PLACEMENT AND MODEL MATCHING
Ba
Fa
Aa
F,
HI
|     |     |     | Al  | Fe  |     |     |         |
| --- | --- | --- | --- | --- | --- | --- | ------- |
|     |     | x   | I   |     |     |     | (9.57)  |
~m I
|     |     |     |     | LF Il+m  |     |     |     |
| --- | --- | --- | --- | -------- | --- | --- | --- |
Am
We search linearly independent columns of Tm in order from left to right. Let f1 be the column
index of G(s) or the least integer such that T,,_I contains n linearly independent AT-columns.
| Then the compensator can be solved from (9.57) with m = f1 - |     |     |     |     |     | J.  |     |
| ------------------------------------------------------------ | --- | --- | --- | --- | --- | --- | --- |
| 9.4.1  Regulation and Tracking                               |     |     |     |     |     |     |     |
As  in the  SISO case,  pole placement can be  used  to  achieve  regulation  and  tracking in
multi variable systems. In the regulator problem, we have r == 0 and if all poles of.the overall
system are assigned to have negative real parts, then the responses caused by any nonzero
initial state will decay to zero. Furthermore, the rate of decaying can be controlled by the
locations of the poles; the larger the negative real parts, the faster the decay.
Next we discuss tracking of any step reference input. In this design, we generally require
a feedforward constant gain matrix P. Suppose the compensator in Fig. 9.6 has been designed
by using Theorem 9.M2. Then the q x q transfer matrix from r to y is given by
I
|     |     |     | Go(s) = N(s)F- |     | (s)B(s)P  |     | (9.58)  |
| --- | --- | --- | -------------- | --- | --------- | --- | ------- |
If Go(s) is BIBO stable, then the steady-state response excited by r(t)  =  d. for t  >  O. or
I
res)  =  ds- , where d is an arbitrary q x  I constant vector, can be computed as, using the
final-value theorem of the Laplace transform,
|     |     | lim y(t) =  |     | lim sGo(s)ds-1 =  |     | Go(O)d  |     |
| --- | --- | ----------- | --- | ----------------- | --- | ------- | --- |
|     |     | (-+00       |     | 5--+0             |     |         |     |
Thus we conclude that in order for yet) to track asymptotically any step reference input, we
need, in addition to BIBO stabilitv,
|     |     |     | =      |                  |     | =   |         |
| --- | --- | --- | ------ | ---------------- | --- | --- | ------- |
|     |     |     | Go(O)  | N(O)F-I(O)B(O)P  |     | Iq  | (9.59)  |
Before discussing the conditions for meeting (9.59), we need the concept of transmission zeros.
Transmission zeros  Consider a q  x p proper rational matrix G(s) =  N(s)D- I  (5), where
N (s) and D(s) are right coprime. A number A, real or complex, is called a transmission ~ero
of G(s) if the rank of N(A) is smaller than min(p, q).
| '!  EXAMPLE 9.11  | Consider the 3 x 2 proper rational matrix  |     |     |     |     |     |     |
| ----------------- | ------------------------------------------ | --- | --- | --- | --- | --- | --- |
5
| J   |     |     | 0   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
j
| 1   |     | 5+2  | 5+  |     |     |     |     |
| --- | --- | ---- | --- | --- | --- | --- | --- |
][5+2
| J   |     |     |     |     |     | +o   |     |
| --- | --- | --- | --- | --- | --- | ---- | --- |
I  ~r
|     | G I (5) =  | 0   | ,     | - [  | 0s     |       |     |
| --- | ---------- | --- | ----- | ---- | ------ | ----- | --- |
|     |            |     |       |      | +   s  | I  0  |     |
|     |            | +   | s'    |      |        | s-    |     |
| J   |            | s   | 1  I  |      | s  1   | s     |     |
--
5
s+2

304  POLE PLACEMENT AND MODEL MATCHING
|     | r-------------------- |     |     |     | w   |     |     |     |
| --- | --------------------- | --- | --- | --- | --- | --- | --- | --- |
1
|          | I          |           |     |       | I                        |           |        |      |
| -------- | ---------- | --------- | --- | ----- | ------------------------ | --------- | ------ | ---- |
|          | •  I,      |           |     |       | I - >. ~ Y + ,           |           |        | Y,   |
| r  ~ - - | .          | > A-'(s)  | ~   |       |                          | -- - -"   |        |      |
|          | ep-'(s)lp  |           |     | H(s)  | ,   ;X   ; : : ;   N(s)  | fr'(s)    |        |      |
| ) l      |            |           | i " |       |                          | - - , I   | I-- -- | l    |
| -r       | I '        | I         |     |       |                          |           |        |      |
1+
|     | ~  I  |     |     |     |     |     |     |     |
| --- | ----- | --- | --- | --- | --- | --- | --- | --- |
L  ____________________
I
| figure 9.8  | Robust tracking and diqurbance rejection.  |     |     |     |     |     |     |     |
| ----------- | ------------------------------------------ | --- | --- | --- | --- | --- | --- | --- |
an equal number of input terminals and output \erminals or p  q. Consider the unity-feedback
:0
system shown in Fig. 9.8. The plant is described by a p  x  p strictly proper transfer matrix
fi-
factored in left coprime fraction as C(5)  ' (s)N(s). It is assumed that p x  I disturbance
:0
w(t) enters the plant input as shown. The problem is to design a compensator so that the output
y(t) will track asymptotically a class of p  x  1 reference signals r(t) even with the presence
of the disturbance w(t) and with plant parameter variations. This is called robust tracking alld
disturbance rejection.
As in the S1S0 case. we need some information on r(t) and w(t) before carrying out the
design. We assume that the Laplace transforms of ret) and w(t) are given by
r(s):o L[r(t)):o Nr(s)D;'(s)  W(s):o L[w(t)):o Nw(s)D~' (s)  (961 )
where Dr(s) and Dw(s) are known polynomials: however, Nr(s) and Nw(s) are unknown to
us. Let tP (5) be the least common denominator of the unstable poles of r(s) and w(s I. The
stable poles are excluded because they have no effect on yet) as t  -+ 00. We introduce the
internal model tP-'(s)Ip  as shown in Fig. 9.8. IfO(s) and N(s) are left coprime and ifno root
of tP(s) is a transmission zero of C(s) or, equivalently, tP(s) and det N(s) are coprime. then
it can be shown that O(s)tP(s) and N(s) are left coprime. See Reference [6. p. 4431. Then
- --I
Corollary 9.M2 implies that there exists a proper compensator C(s)  8(s)A  (s) such that
:0
+ N(s)B(s) =
|     |     |     |     | tP(s)O(s)A(s)  |     | F(s)  |     | (962)  |
| --- | --- | --- | --- | -------------- | --- | ----- | --- | ------ |
for any F(s) meeting the condition in Corollary 9.M2. Clearly F(s) can be chosen to be diagaonl
with the roots of its diagonal entries lying inside the sector shown in Fig. 8.3(a). The unity
feedback system in Fig. 9.8 so designed will track asymptotically and robustly the reference
signal r(t) and reject the disturbance w(t). This is stated as a theorem.
,..  Theorem 9.M3
Consider 'he unity·feedback system shown in Fig. 9.8 where the plant has a p X  P strictly proper transfer
|     |     | 0-'  |     |     |     |     | 0(5)  |     |
| --- | --- | ---- | --- | --- | --- | --- | ----- | --- |
matrix G(s) =  (s)N (s). It is assumed that O(s) and N(s) are left coprime and  is row reduced
with row degrees Vi. i  1. 2 ..... p. The reference signal r(r) and disturbance w(t) are modeled
:0
|     |     | =   |     |     | =   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
as res)  Nr(s)D;'(s) and w(s)  Nw(slD;;;'(s). Let </>(s)  be the least common denominator
of the unstable poles of res) and w(s). If no root of tP(s) is a transmission zero of C(s), then there
»-'
exists a proper compensator e(s)  :0  B(s )(A(s)</>(s  such that the overall system will robustly and
asymptotically track the reference signal r(l) and reject the disturbance w(t).

|     |     |     | 9.5  | Multivariable Model Matching  | 307  |
| --- | --- | --- | ---- | ----------------------------- | ---- |
+
y
| L (5)  |     | A-'(5)  | D-' (s)  | N(5)  |     |
| ------ | --- | ------- | -------- | ----- | --- |
M(s)
L ______________ _
Figure 9.9  Two-parameter configuration.
| o(s) = [I  | +   | A -I (s)M(s)N(s)D-1 (sJr |     | I   |     |
| ---------- | --- | ------------------------ | --- | --- | --- |
A -I (s)L(s)r(s)
+
|     | = D(s)[A(s)D(s)  |     | M(s)N(sWIL(s)r(s)  |     |     |
| --- | ---------------- | --- | ------------------ | --- | --- |
Thus we have
| yes) = N(s)D-I(s)u(s) = N(s)[A(s)D(s)  |     |     |     | +  M(s)N(s)rIL(s)r(s)  |     |
| -------------------------------------- | --- | --- | --- | ---------------------- | --- |
and the transfer matrix from r to y is
|     |                        |     | +        | I     |         |
| --- | ---------------------- | --- | -------- | ----- | ------- |
|     | Go(s) = N(s)[A(s)D(s)  |     | M(s)N(sW | L(s)  | (9.69)  |
Thus model matching becomes the problem of solving A(s), M(s) and L(s) in (9.69).
=  N(s)D-1 (s).
Problem Given a p  x p strictly proper rational matrix G(s)  where
N(s) and D(s) are right coprime and D(s) is column reduced with column degrees
/1-i.  i  =  1.2 ..... p.  and given any implementable Go(s). find proper compensators
A -I (s )L(s) and A -I (s )~[(s) in Fig. 9.9 to implement Go (s).
~  Procedure 9.M 1
I. Compute
|     |     | WI (s)Go(s)  | = F-       |     |         |
| --- | --- | ------------ | ---------- | --- | ------- |
|     |     |              | ' (s)£(s)  |     | (9.70)  |
where F(s) and £(s) are left coprime and F(s) is row reduced.
=
2.  Compute the row index v of(;(s)  N(s)D- 1 (s). This can be achieved by using QR decomposition.
3.  Select
|     | F(s) = diag(al (s). a2(s) ....• apes»~  |     |     |     | (9.71 )  |
| --- | --------------------------------------- | --- | --- | --- | -------- |
where ai (5) are arbitrary Hurwitz polynomials. such that F(s)F(s) is row-(;olumn reduced with
column degrees /1-i  and row degrees mi with
|     |     |     | I   |     | (9.72)  |
| --- | --- | --- | --- | --- | ------- |
mi ::: \! -
=
for i  I, 2 .... , p.

9.4 Multivariable Unity-Feedback Systems 305
a
Proof: First we show that the system will reject the disturbance at the output. Let us
assume r = 0 and compute the output Yu. (s) excited by w(s). Clearly we have
yw(s) = O-I(s)N(s)(w(s) - B(s) .. \. -I (S)<,b-I(s)yu'(s»)
which implies
1 1
Yw(s) = (I + 0- (s)N(s)B(s) .. \. -I (s)<,b -I (sW 10- (s)N(s)\r\'(s )
[0-
= 1 (s)(O(s)<,b(s)A(s) + N(s)B(s»)A -I (S)<,b-I (s)
x O-I(s)N(s)w(s)
= <,b(s)A(s)[O(s)<,b(s)A(s) + N(s)B(sWIN(s)w(s)
Thus we have, using (9.61) and (9.62).
Yw(s) = A(s)F-I(s)N(s)<,b(s)Nw(s)D,;;1 (s) (9.63)
Because all unstable roots of Du'(s) are canceled by <,b(s). all poles ofyu'(s) have negative
real parts. Thus we have yw(t) ~ 0 as t ~ 00 and the response excited by Wet) is
suppressed asymptotically at the output.
Next we compute the error errs) excited by the reference signal res):
errs) = res) - 0-1 (s)N(s)B(s)A -I (s)rl (s)er(s)
which implies
errs) = [1
+ 0-1
(s)N(s)B(s)A -I (s)<,b -I (s WI res)
+
= <,b(s)A(s)[O(s)<,b(s)A(s) N(s)B(sWIO(s)r(s)
= A(s)F-I(s)O(s)<P(s)Nr(s)D;I(s) (9.64)
Because all unstable roots of Dr(s) are canceled by <,b(s). the error vector errs) has only
stable poles. Thus its time response approaches zero as t ~ 00. Consequently, the output
y(t) will track asymptotically the reference signal r(t). The tracking and disturbance rejec
tion are accomplished by inserting the internal model <,b-I (s)Ip. If there is no perturbation
in the internal model. the tracking properry holds for any plant and compensator parameter
perturbations, even large ones, as long as the unity-feedback system remains BIBO stable.
Thus the design is robust. This establishes the theorem. Q.E.D.
In the robust design, because of the internal model, <p (s) becomes zeros of every nonzero
entry of the transfer matrices from w to y and from r to e. Such zeros are called blocking ~eros.
These blocking zeros cancel all unstable poles of w(s) and r(s); thus the responses due to these
unstable poles are completely blocked at the output. It is clear that every blocking zero is a
transmission zero. The converse, however, js not true. To conclude this section, we mention
that if we use a right coprime fraction for G(s), insert an internal model and stabilize it, we
can show only disturbance rejection. Because of the noncommutative property of matrices. we
are not able to establish robust tracking. However, it is believed that the system still achieves
robust tracking. The design discussed in Section 9.2.3 can also be extended to the multi variable
case; the design, however, will be more complex and will not be discussed.

306 POLE PLACEMENT AND MODEL MATCHING
9.5 Multivariable Model Matching-Two-Parameter Configuration
In this section. we extend the SISO model matching to the multi variable case. We study only
plants with square and nonsingular strictly proper transfer matrices. As in the SISO case,
given a plant transfer matrix G(s). a model Go(s) is said to be implementable if there exists a
no-plant-leakage configuration and proper compensators so that the resulting system has the
overall transfer matrix Go(s) and is totally stable and well posed. The next theorem extends
Theorem 9.4 to the matrix case.
'> Theorem 9.M4
Consider a plant with p x p strictly proper transfer matrix G(s). Then a p x p transfer matrix Go(s)
is implementable if and only if Go(s) and I
1'(s):= G-1(s)Go(s) (9.65)
are proper and BmO stable.'
For any no-plant-leakage configuration, the closed-loop transfer matrix from r to u is
i(s). Thus well posedness and total stability require Go(s) and 1'(s) to be proper and BmO
stable. This shows the necessity of Theorem 9.M4. Let us write (9.65) as
Go (s) = G(s )1'(s) (9.66)
Then (9.66) can be implemented in the open-loop configuration in Fig. 9.l(a) with C(s) = 1'(s).
This design, however, is not acceptable either because it is not totally stable or because it is very
sensitive to plant parameter variations. Ifwe implement it in the unity-feedback configuration,
we have no freedom in assigning canceled poles. Thus the configuration may not be acceptable.
In the unity-feedback configuration. we have
u(s) = C(S )[r(s) - Yes) )
Now we extend it to
=
u(s) C1(s)r(s) - C~(s)Yes) (9.67)
This is a two-degrees-of-freedom configuration. As in the SISO case, we may select C (s) and
I
Cl(s) to have the same denominator matrix as
CI(S) = A-1(s)L(s) Cl(s) = A-1(s)M(s) (9.68)
Then the two-parameter configuration can be plotted as shown in Fig. 9.9. From the figure,
we have
=
u(s) A-I (s)[L(s)r(s) - M(s)N(s)D-1 (s)u(s)]
which implies
4. If G(s) is not square, then Go(s) is implementable if and only if Go(s) is proper. is BIBO stable. and can be
expressed as Go(s) = G(s)T(s). where trs) is proper and BIBO stable. See Reference [6. pp. 517-523J.

308  POLE PLACEME,'iT AND MODEL MATCHING
4.  Set
|     |     |     |     | L(s) = F(s)E(s)  |     |     |     | (9.73)  |
| --- | --- | --- | --- | ---------------- | --- | --- | --- | ------- |
and solve A(s) and 1\1(s) from
A(s)D(s) + M(s)N(s) = F(s)F(s) =: F(5)
(9.74)
Then proper compensators A-1(s)L(s) and A-1(s)M(s) can be obtained to achieve the model
matching.
This procedure reduces to Procedure 9.1 if G(s) is scalar. We first justify the procedure.
Substituting (9.73) and (9.74) into (9.69) yields
|     |     | Go(s) =  | N(s)[F(s)F(sW1F(s)E(s) = N(S)y-I(S)E(s)  |     |     |     |     |     |
| --- | --- | -------- | ---------------------------------------- | --- | --- | --- | --- | --- |
This is (9.70). Thus the compensators implement Go (s). Define
m,
|     | Hc(s) = diag(s"', s"', .. |     |     | . , s"P)  | H r  (   )  | - d' l   ag  (sm  , . s  | , ...• s mp)  |     |
| --- | ------------------------- | --- | --- | --------- | ----------- | ------------------------ | ------------- | --- |
|     |                           |     |     |           | S           | -                        |               |     |
By assumption, the matrix
lim H;I (s)F(s)H;1 (s) =: Fh
S--+X
is a nonsingular constant matrix. Thus solutions A(s), having row degrees mi and being row
reduced. and 1\1(s), having row degrees mi or less, exist in (9.7.+)  (Theorem 9.M2). Thus
A-I (5)1\1(S) is proper. To show that A-I (s)L(s) is proper, we consider
T(s) = G-1(s)G
(s) = D(S)Wl(S)Go(s)
o
I
|     |     | = D(s)F- | 1  (s)E(s) = D(s)[F(s)F(sW |     |     | F(s)E(s)  |     |     |
| --- | --- | -------- | -------------------------- | --- | --- | --------- | --- | --- |
+
|     |     | = D(s)[A(s)D(s)  |     | M(s)N(sW1L(s)  |     |     |     |     |
| --- | --- | ---------------- | --- | -------------- | --- | --- | --- | --- |
r
1
+
|     |     | = D(s) IA(s)[1  |     | A -1(s)M(s)N(s)D-l(S)]D(s)  |     |     | L(s)  |     |
| --- | --- | --------------- | --- | --------------------------- | --- | --- | ----- | --- |
=
[I  +  A-I (s)M(s)G(SWI A -I (s)L(s)
=
which implies, because G(s)  N(s)D-1(s) is strictly proper and A - 1(s)M(s) is proper.
=
|     |     |     | lim T(s)  |     | lim A-I (s)L(s)  |     |     |     |
| --- | --- | --- | --------- | --- | ---------------- | --- | --- | --- |
|     |     |     | $-X       |     | S- ·?C           |     |     |     |
Because T(oo)  is  finite by assumption, we conclude that A -1(slL(s) is  proper. If G(s) is
strictly  proper and if all compensators are proper, then the two-parameter configuration is
automatically -well posed. The desi-gn involves the pole-zero cancdlation of F(s). which we
can select. If F(s) is selected as diagonal with Hurwitz polynomials as its entries. then pole-
zero cancellations involve only stable poles and the system is totally stable. This completes
the justification of the design procedure.
| l  EX.HIPLE 9.12  |     | Consider a plant with transfer matrix  |     |     |     |     |     |     |
| ----------------- | --- | -------------------------------------- | --- | --- | --- | --- | --- | --- |
.1  lis]  [I
I
|     |     |     | = [1~2  |     | =  :][s~  | ~r  |     |     |
| --- | --- | --- | ------- | --- | --------- | --- | --- | --- |
.1  G(s)  (975)
'.,
| ,J  |     |     |     | I/s  | 0   |     |     |     |
| --- | --- | --- | --- | ---- | --- | --- | --- | --- |

9.5 Multivariable Model Matching 311
=
Let us discuss a special case of model matching. Given G(s) N(S)O-l (s), let us select
1'(s) = O(s)ot (s), where 0f(s) has the same column degrees and the same column-degree
coefficient matrix as O(s). Then 1'(s) is proper and Go(s) = G(s)1'(s) = N(S)Ojl(S). This
is the feedback transfer matrix discussed in (8.72). Thus the state feedback design discussed
in Chapter 8 can also be carried out by using Procedure 9.MI.
9.5.1 Decoupling
Consider a p x p strictly proper rational matrix G(s) = N(S)O-l (s). We have assumed that
= l
G(s) is nonsingular. Thus G -I (s) O(s )N- (s) is well defined; however, it is in general
improper. Let us select 1'(s) as
l
1'(s) = G- (s)diag(djl (s), dil(s), ... , d;l(s» (9.83)
where dieS) are Hurwitz polynomials ofleast degrees to make 1'(s) proper. Define
I:(s) = diag(dl (s), d2(s), ... , dp(s» (9.8'+)
Then we can write T(s) as
= =
1'(s) O(s)Wl(s)I:-l(s) O(s)[I:(S)N(SWI (9.85)
If all transmission zeros of G(s) or, equivalently, all roots of det N(s) have negative real pans.
then 1'(s) is proper and BIBO stable. Thus the overall transfer matrix
Go(s) = G(s)1'(s) = N(S)O-I(S)O(S)[I:(s)N(s)]-1
= I = l
N(s)[I:(s)N(sW I:- (s) (9.86)
is implementable. This overall transfer matrix is a diagonal matrix and is said to be decoupled.
This is t~e design in Example 9.12.
If G(s) has nonminimum-phase transmission zeros or transmission zeros with zero or
positive real pans, then the preceding design cannot be employed. However, with some
modification, it is stilI possible to design a decoupled overall system. Consider again G(s) =
1
N (s )0- (s). We factor N (s) as
N(s) = NJ(s)N
2
(s)
with
=
Nl (s) diag(.Bll (s) . .BJ'''(s), ... , .Blp(S»
where .Bli (s) is the greatest common divisor of the ith row of N(s). Let us compute Ni' J( s),
and let .B2i (s) be the least common denominator of the unstable poles of the ith column of
Ni'l (s). Define
N~ := diag(.B2J(s), .Bds) , ... , .B2p(S»
Then the matrix
N- 2 (s) := Ni' J (s)N~(s)

|                                  |     |     |                                            |     |     | 9.5  | Multivariable Model Matching  |     |     | 309  |
| -------------------------------- | --- | --- | ------------------------------------------ | --- | --- | ---- | ----------------------------- | --- | --- | ---- |
| :;J  It has column degrees iJ.I  |     |     | = 2 and iJ.2= I. Let us select a model as  |     |     |      |                               |     |     |      |
'.;
| . ,!   |     |     | ~                  |     |     |     |     |     |     |         |
| ------ | --- | --- | ------------------ | --- | --- | --- | --- | --- | --- | ------- |
|        |     |     |                    |     |     |     | :   | 1   |     |         |
|        |     |     | G,{"  [ " + :' +,  |     |     |     |     |     |     | (9.76)  |
:,'  r:;
'oj
,~
!4  which is proper and BlBO stable. To check whether or not Go(s) is implementable, we 1com pute
~, 1
| ..             |      |        |     |      |           |     |         |     |         | 2   |
| -------------- | ---- | ------ | --- | ---- | --------- | --- | ------- | --- | ------- | --- |
| ~              |      |        |     |      |           |     | 2s2     |     | -2s     |     |
| ; , ." {       |      |        |     |      | G         |     | +       | +   | +       | +   |
| ~ . ~          | 1    |        | [~  | _ 52 | ]  (5) =  |     | s2  2s  | 2   | s2  2s  | 2   |
| ;   Tcs) := G- | (5)G | (S) =  |     |      |           |     |         |     |         |     |
| ~              |      | o      |     |      | o         |     |         |     |         |     |
|                |      |        |     | s    |           | [   | 0       |     | 25      |     |
.
| :.~  |     |     |     |     |     |     |     |     | +       | +   |
| ---- | --- | --- | --- | --- | --- | --- | --- | --- | ------- | --- |
|      |     |     |     |     |     |     |     |     | 52  25  | 2   |
.'
.,
t~  which is proper and BlBO stable. Thus Go(s) is implememable. We compute
:
1
|     | WI(S)Go(S) |     | =[~  | ~I]["+:<+l  |     |     |     |     |     |     |
| --- | ---------- | --- | ---- | ----------- | --- | --- | --- | --- | --- | --- |
)
|     |     |     |     |     |     |     | 1   | +    + 2  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --------- | --- | --- |
| "1  |     |     |     |     |     |     | s2  |   ~ 5     |     |     |
,'"
(:,
| , j    |     |     |     | J           |     | 5:  - | I    |     |     |     |
| ------ | --- | --- | --- | ----------- | --- | ----- | ---- | --- | --- | --- |
|        |     |     | =   | + ~ s + :2  |     | +  ~  | + 2  |     |     |     |
|        |     |     | s2  |             |     |       | s    |     |     |     |
,   }
[
+ 2s + 2
s-
| ·-'1  |     |     |     |     |     | ,0  |     |     | -2]  |     |
| ----- | --- | --- | --- | --- | --- | --- | --- | --- | ---- | --- |
]-1[2
:;
| J   |     |     | =[s2 | +2S+2  |     |           |     |     |     |     |
| --- | --- | --- | ---- | ------ | --- | --------- | --- | --- | --- | --- |
|     |     |     |      | o      |     | + 2s + 2  |     |     |     |     |
|     |     |     |      |        |     | s-        |     | 0   | 2   |     |
,',j
i
=: F-1(s)E(s)
.. '":
l
"i
>~  For this example, the degree of N-1(s)Go(s) can easily be computed as 4. The determinant
i  of F(s) has degree 4; thus the pair F(s) and E(s) are left coprime. It is clear that F(s) is row
•. j
,,,~
'~'l  reduced with row degrees TI  = T2  = 2. The row index ofG(s) was computed in Example 9.10
'
.. '~
;j  as v = 2. Let us select
·1
""
:1
.
|     |     |     | F(s) = diag«s  |     |     | +  2). I)  |     |     |     |     |
| --- | --- | --- | -------------- | --- | --- | ---------- | --- | --- | --- | --- |
'
. ~
d  Then we have
"j
|                 | .   | -   | [(S2 + 2s + |     |   2)(s +  |     |     |     |     |     |
| --------------- | --- | --- | ----------- | --- | --------- | --- | --- | --- | --- | --- |
| .;. ' ,  " :    |     |     |             |     |           | 2)  |     | 0   | ]   |     |
+ 2
| ' ., j     | F   | (s)F | (s) =  |     | 0   |     | s2  | s  ..,.. 2  |     |     |
| ---------- | --- | ---- | ------ | --- | --- | --- | --- | ----------- | --- | --- |
.
0,]
| .j   |     |     |     |     | 2   | 3   |     |     |     |     |
| ---- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
=[4+6S+4S
| ~1  |     |     |     |     | +5  |     |     |     |     | (9.77)  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------- |
o
| :1  |     |     |     |     |     | 2+2s+s- |     |     |     |     |
| --- | --- | --- | --- | --- | --- | ------- | --- | --- | --- | --- |
;~
It is row--{;olumn reduced with row degrees {m 1  =  ml =  I  =  v - II and column degrees
1
| =  =  |     |     |     |     |     | pes),  |     |     |     |     |
| ----- | --- | --- | --- | --- | --- | ------ | --- | --- | --- | --- |
{iJ.I  2, iJ.2  I}. Note that without introducing  proper compensators may not exist.
iJ'~
We set
,.
,
,:j
|     |     |     | •   | -   | [S+2  | 0][2  | ~2]  |     |     |     |
| --- | --- | --- | --- | --- | ----- | ----- | ---- | --- | --- | --- |
L(s) = F(s)E(s) =
|     |     |     |     |     | 0   | I   | 0   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
.~
~
-2(S2 +
|     |     |     | =  [2(S: 2)  |     |     | 2) ]  |     |     |     | (9.78)  |
| --- | --- | --- | ------------ | --- | --- | ----- | --- | --- | --- | ------- |
}:II

310  POLE PLACEMENT AND MODEL MATCHING
and solve A(s) and M(s) from
|     |     |           | +                            |     |     |     |     |     |     | (9.79)  |
| --- | --- | --------- | ---------------------------- | --- | --- | --- | --- | --- | --- | ------- |
|     |     | A(s)D(s)  | M(s)N(s) = F(s)F(s) =: F(s)  |     |     |     |     |     |     |         |
From the coefficient matrices of D(s) and N(s) and the coefficient matrices of (9.77), we can
readily form
|     |     |     |     |     |     | 0   | I  0  | 0   | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | ----- | --- | --- | --- |
|     |     |     | 0   | 0   | 0   |     |       |     |     |     |
I
c-
|     |     |     | O   | 0   | 0   |     | 0  0  | 0   | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | ----- | --- | --- | --- |
!
|     |      |              |     |     |     |     | 0     | 0   | 0   |     |
| --- | ---- | ------------ | --- | --- | --- | --- | ----- | --- | --- | --- |
|     |      |              | 1   |     | 0   | 0   | 0     |     |     |     |
|     |      |              | 0   |     | 0   | 0   | 0  0  | 0   | 0   |     |
|     | [Ao  | Mo  AI  MIl  |     |     |     |     |       |     |     |     |
0
|     |     |     | 0   | 0   | 0   | 0   | 0  0  | I   |     |     |
| --- | --- | --- | --- | --- | --- | --- | ----- | --- | --- | --- |
~
| J   |     |     | 0   | 0   | 0   | 0   | 0   | 0   | 0   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
itl
|     |     |     | 0   | 0   |     | I     | 0  0   | 0   | 0   |         |
| --- | --- | --- | --- | --- | --- | ----- | ------ | --- | --- | ------- |
|     |     |     | L   | 0   | 0   | I     | 40  0  | 0   | 0   |         |
| ~   |     |     | 0   |     |     |       |        |     |     |         |
|     |     |     |     |     | 0   | 6  0  | 0      |     |     |         |
|     |     |     |     | [~  |     |       |        | ~]  |     | (9.80)  |
|     |     |     |     | =   | 2   | 0  2  | 0  I   | 0   |     |         |
'~
| ~.  |     |     |     |     |     |     |     |     |     | 8   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
As discussed in Example 9.10, if we delete the last column of SI, then the remaining  1 has
full column rank and for any F(s), after deleting the last zero column, solutions exist in (9.80).
8
i  ,  Now if we delete the last N-row of  , which is linearly dependent on its previous row, the set
1
"
| of solutions is unique and can be obtained, using MATLAB, as  |     |     |     |     |     | 4 -4  |     |     |     |     |
| ------------------------------------------------------------- | --- | --- | --- | --- | --- | ----- | --- | --- | --- | --- |
[4
|     |     |     |     |     | -6  |     | I   | 0  6  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ----- | --- | --- |
~]
(981 )
|     |     | [Ao  Mo  AI  | MIl =  | 0   |     |       |     |       |     |     |
| --- | --- | ------------ | ------ | --- | --- | ----- | --- | ----- | --- | --- |
| 1   |     |              |        |     | 2   | 0  2  | 0   | I  0  |     |     |
t
~ote that the last zero column is by assignment because of the deletion of the last N-row in
SI' Thus we have
[4
>1
[4;
|     |     |         |     | -6  | ]   |         | +6s  | ~4]  |     | (9.82)  |
| --- | --- | ------- | --- | --- | --- | ------- | ---- | ---- | --- | ------- |
|     |     | A(s) =  | s   |     |     | M(s) =  | 0    |      |     |         |
2 +s
The two compensators A-I(slM(s) and A-I(s)L(s) are clearly proper. This completes the
J
design. As a check, we compute
| "j  |     |     |     |     |     |        |     | , : J  |     |     |
| --- | --- | --- | --- | --- | --- | ------ | --- | ------ | --- | --- |
| J   |     |     |     |     |     | +  2)  |     |        |     |     |
2(.1
|     |                            |     |     |     | +   |           | +   |     |     |     |
| --- | -------------------------- | --- | --- | --- | --- | --------- | --- | --- | --- | --- |
|     | Go(s) = N(s)F-1 (s)L(s) =  |     |     |     | s3  | 45'0+ 6s  | 4   |     |     |     |
[
';,.
1
|     |     | [>'+~+2  |     | ,:  |     |     |     |     |     |     |
| --- | --- | -------- | --- | --- | --- | --- | --- | --- | --- | --- |
=
-J- ')(' -+-?
C'-
+
This is the desired mode\. Note that the design involves the cancellation of (s  2), which we
can select. Thus the design is satisfactory.

312  POLE PLACEMENT AND MODEL MATCHING
has no unstable poles. Now we select T(s) as
|     |     |     |     |         | =      |         |     | I    |     |     |         |
| --- | --- | --- | --- | ------- | ------ | ------- | --- | ---- | --- | --- | ------- |
|     |     |     |     | TA (s)  | D(s)N- | 2(s)1:- |     | (s)  |     |     | (9.87)  |
with
|     |     |     | 1:(S) = diag(d |     |     | (s), d | (s), .... dp(s»  |     |     |     |     |
| --- | --- | --- | -------------- | --- | --- | ------ | ---------------- | --- | --- | --- | --- |
|     |     |     |                |     |     | l      | 2                |     |     |     |     |
where d i  (s) are Hurwitz polynomials of least degrees to make T (s) proper. Because:\;! (s) has
only stable poles, and dieS) are Hurwitz, T(s) is BIBO stable. Consider
|     |     | Go(s) = G(s)T(s) = NI (s)N |     |                 |     | (s)D-I (s)D(s)N |     |     |     | (s)1:- 1  (s)  |     |
| --- | --- | -------------------------- | --- | --------------- | --- | --------------- | --- | --- | --- | -------------- | --- |
|     |     |                            |     |                 |     | 2               |     |     | 2   |                |     |
|     |     |                            | = N |                 | I   | (s)             |     |     |     |                |     |
|     |     |                            |     | I(s)N 2d (S)1:- |     |                 |     |     |     |                |     |
(S»)
=  diag (fMS), /h(s), ... , f3p
(9.88)
|     |     |     |     | dl(s)  | d2(5)  |     | dp(s)  |     |     |     |     |
| --- | --- | --- | --- | ------ | ------ | --- | ------ | --- | --- | --- | --- |
where f3Js)  =  f3li(~)fh(s). It is proper because both T(5) and G(s) are proper. It is clearly
BIBO stable. Thus Go(s) is implementable and is a decoupled system.
I,
| EXAMPLE 9.13  |     | Consider  |     |     |     |     |     |     |     |     |     |
| ------------- | --- | --------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
'~  ~,
|       |     |                      |     |     | [s  |        |     | [53  |      | ]-1  |     |
| ----- | --- | -------------------- | --- | --- | --- | ------ | --- | ---- | ---- | ---- | --- |
| )::1  |     |                      |     |     |     |        |     |      | + I  |      |     |
| .,    |     | (s) = N(s)D-I (s) =  |     |     |     |        | 1   | ]    |      | I    |     |
|       |     | GA                   |     |     |     |        |     |      |      | ,    |     |
| jj    |     |                      |     |     |     | s - 1  | s - | I    | 0    | s-   |     |
.:1  ,.
We compute det N(s) =  (s  - 1)(s - 1) =  (s - 1)2 The plant has two nonminimum-phase
:~,
transmission zeros. We factor N(s) as
·1
: d
|     |     |     |     | N(s)N |     | [I  |     | 0 J[s  |     | I]  |     |
| --- | --- | --- | --- | ----- | --- | --- | --- | ------ | --- | --- | --- |
'oj
| "~  |     |     | N(s) =  |     | (5) =  |     |      |     |     |     |     |
| --- | --- | --- | ------- | --- | ------ | --- | ---- | --- | --- | --- | --- |
|     |     |     |         | 1   | 2      | o   |      |     |     |     |     |
|     |     |     |         |     |        |     | s-I  |     | I   | 1   |     |
.~,
| ~J,            |              |     |     | ».            |     |     |     |     |     |     |     |
| -------------- | ------------ | --- | --- | ------------- | --- | --- | --- | --- | --- | --- | --- |
| with ~ 1(5) =  | diag(l, (5 - |     | 1   | an d compute  |     |     |     |     |     |     |     |
J,,
.
| .   |     |     |     | N - |     | I   | [1  |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
~1
| 1      |     |     |     | I    | =     |     |     |     | ]   |     |     |
| ------ | --- | --- | --- | ---- | ----- | --- | --- | --- | --- | --- | --- |
| J .    |     |     |     | (s)  | (s _  | 1)  | _I  |     |     |     |     |
2
:~
> i   If we select
'j
i
| ,.   |     |     |     |      | =        |     |          |     |     |     |         |
| ---- | --- | --- | --- | ---- | -------- | --- | -------- | --- | --- | --- | ------- |
| ;    |     |     |     | N2d  | diag«s - |     | I). (s - | 1»  |     |     | (9.89)  |
'1
then the rational matrix
,j
|           |     |     |     | =        |            |     |      | I    | ~l  |     |     |
| --------- | --- | --- | --- | -------- | ---------- | --- | ---- | ---- | --- | --- | --- |
|           |     |     | N-  | N. 2- I  |            |     | = [  | _ I  | ]   |     |     |
| . J "     |     |     |     | 2(5)     | (5)N2d(S)  |     |      |      |     |     |     |
:'.:~
1
has no unstable poles. We compute
| i   |     |     |     |     |      |     | I, ] [I  |     | -1 ]  |     |     |
| --- | --- | --- | --- | --- | ---- | --- | -------- | --- | ----- | --- | --- |
|     |     |     |     | -   | [53  |     |          |     |       |     |     |
+  I
|     |     |     | D(s)N2(s) =  |     |     | 0   |     |     |     |     |     |
| --- | --- | --- | ------------ | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |              |     |     |     | s-  | -1  | s   |     |     |
:j
53,
+ s -
|     |     |     |     |     | =  [  | _s3  |     | I ]  |     |     |     |
| --- | --- | --- | --- | --- | ----- | ---- | --- | ---- | --- | --- | --- |
| 1   |     |     |     |     |       |      | 53  |      |     |     |     |
|     |     |     |     |     | -s-   |      | +   |      |     |     |     |
I
j
If we choose

Problems 315
Model matching generally involves pole-zero cancellations. One-degree-of-freedom
configura~s cannot be used here because we have no freedom in selecting canceled poles.
Any two-degree-of-freedom configuration can be used because we have freedom in selecting
canceled poles. This text discusses only the two-parameter configuration shown in Fig. 9.--1.
All designs in this chapter are achieved by solving sets of linear algebraic equations. The
basic idea and procedure are the same for both the SISO and MIMO cases. All discussion
in this chapter can be applied, without any modification, to discrete-time systems; the only
difference is that desired poles must be chosen to lie inside the region shown in Fig. 8.3(b)
instead of in Fig. 8.3(a).
This chapter studies only strictly proper G(s). IfG(s) is proper, the basic idea and
procedure are still applicable, but the degree of compensators must be increased to ensure
properness of compensators and well posedness of overall systems. See Reference [6J. The
model matching in Section 9.5 can also be extended to nonsquare plant transfer matrices. See
also Reference [6].
The comroller-estimatordesign in Chapter 8 can be carried out using polynomial fractions.
See References [6, pp. 506-514: 7. pp. 461-465]. Conversely, because of the equivalence of
controllable and observable state equations and coprime fractions, we should be able to use
state equations to carry out all designs in this chapter. The state-space design, however. will
be more complex and less intuitively transparent, as we may conclude from comparing the
designs in Sections 8.3.1 and 9.2.2.
The state-space approach first appeared in the 1960s, and by the 1980s the concepts of
controllability and observability and controller-estimator design were integrated into most
undergraduate control texts. The polynomial fraction approach was developed in the 1970s:
its underlying concept of coprimeness, however, is an ancient one. Even though the concepts
and design procedures of the coprime fraction approach are as simple as, if not simpler than,
the state-space approach. the approach appears to be less widely known. It is hoped that this
chapter has demonstrated its simplicity and usefulness and will help in its dissemination .
.t .s.if!~~:>1;;';!":" .~ 9.1 Consider
'P.ROBLEMS ::
;:iU~j:;-;; : ... " . + + +
.4(s)D(s) B(s)N(s) = s2 2s 2
where D(s) and N (s) are given in Example 9.1. Do solutions A (s) and B(s) exist in the
equation? Can you find solutions with deg B(s) :::: deg A(s) in the equation?
9.2 Given a plant with transfer function g(s) = (s '- 1)/(s2 - 4). find a compensator in
the unity-feedback configuration so that the overall system has desired poles at -2 and
-I ± j I. Also find a feedforward gain so that the resulting system will track any step
reference input.
=
9.3 Suppose the plant transfer function in Problem 9.2 changes to g(s) (s -0.9)/(s" ---1.1)
after the design is completed. Can the overall system still track asymptotically any step
reference input? If not. give two different designs. one with a compensator of degree 3
and another with degree 2. that will track asymptotically and robustly any step reference
input. Do you need additional desired poles? If yes, place them at -3.

o.j Multi\ ariable Model Matching 313
= + + + + + +
1:(5) diag«5~ 25 2)ls 21. (5: 25 2)(5 2))
then
-
, . -\
T(s) = DI51~2(51I: (s)
,-
-J is proper. Thus the overall transfer matrix
;
-j
, " ( S - 1 (5 - 1)2 )
,
1, Go(s) = G(5)T(s) = diag
~ (s~
+
25
+
21,,,-
+
2)
, ~
I.S-
,+-
2s
- +-
2)
-
(s
-+ -
2)
is implementable. This is a decoupled system. Thi< decoupled system will not track any step
reference input. Thus we modify i( as
i
i
(990)
.' , . ( -4(5 - 1) -+(5 - 1)2 )
"~. Go(s) = diag - . (5- , + 2s + 2)(s + 21 . - (5 - - -+: , 2s ~ +-- 2 - )( - 5 - +,- 2 - )
which has Go(O) = I and will track any step reference input.
(9.90) 9.:-''11.
l Next we implement in the two-parJJTleter .:onfiguration. We follow Procedure
.,;
To save space, we define des) ;= (52 + 25 + 2)(5 - 2), First we compute 1
j
~ -\ °
.~ L_ --+(5 - I)
N_ \' s1 iI] d°( 5)
(s)Go(s) = 5 - 4(5 + 1)2
.;.j [
. ,, 1
, des)
.1, -4(5 - I) °
[5 -
'1 I I -I dI°S)
- (s - 1)2 I - S 5 ] [ 4(s - 1)2
.j
des)
"j 1
'I [d~:) d~:) ° ]-\ [4 4]
.j = = [de°S)
• 4 -45 des) 4 4s
-
: !
des) des)
'.~ -
-.1 - \
=; F- (s)E(s)
1
.~ It is a left coprime fraction.
·l
;; From the plant transfer matrix. we haw
..,
I I] [0 0] [0 0], [I 0]
J [° ° ° ° ° ° °
1 1
\ 0(5) = + 5 + 1 S- + s-
"
i and
.\
:l °
[
I] [I 0] [0
°
°0] , [0
° °
0]
j N (5) = -I _ 1 + I I s + s- + 53
We use QR decomposition to compute the row index of G(s). We type
j
dl = [1 1 0 0 0 0 1 0 I ; d2 = [0 C O O 0 1 0 0 J ;
-c
nl=[O 1 1 0 0 G 0 Ol ;~2=[-1 1 1 0 0 0 0) ;

314  POLE PLACEMENT AND MODEL MATCHING
| s2=[dl  |     | 0  0   | 0  0;d2  | 0   | 0  0  O;nl  | 0      | 0  0  0;n2  | 0  0  0  0; .. .   |     |
| ------- | --- | ------ | -------- | --- | ----------- | ------ | ----------- | ------------------ | --- |
|         | o   | 0  dl  | 0  0;0   | 0   | d2  0  0;0  | 0  nl  | 0  0;0      | 0  n2  0  0; .. .  |     |
|         | o   | 0  0   | 0  dl;O  | 0   | 0  0  d2;0  | 0  0   | 0  nl;O     | 0  0  0  n2);      |     |
[q,r)=qr(s2')
From the matrix r  (not shown), we can see that there are three linearly independent Nl·rows
and two linearly independent N2-rows. Thus we have  = 3 and li2  = 2 and the row index
VI
equals v = 3. If we select
=
|     |     |     |     | F(s)  | diag (s  |     | + 3)2,  | (s  + 3»)  |     |
| --- | --- | --- | --- | ----- | -------- | --- | ------- | ---------- | --- |
then F(s)F(s) is row-<:olumn reduced with row degrees (2, 2} and column degrees (3, 2}. We
,
| ~  set  |     |     |     |     |     | j   |     |     |     |
| ------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
+
|     |     |     |                  |     |     | -4  | ( s   3   | ) 2   + W ]  |          |
| --- | --- | --- | ---------------- | --- | --- | --- | --------- | ------------ | -------- |
|     |     |     |                  |     |     | =   |           | - 4 ( s      |          |
|     |     |     | L(s) = F(s)E(s)  |     |     | 4   | (s   +  3 | )            | (9.91 )  |
|     |     |     |                  |     |     | [   |           | +            |          |
|     |     |     |                  |     |     |     |           | 4 s ( s  3)  |          |
and solve A(s) and M(s) from
~'  =
+
|     |     |     |     | A(s)D(s)  | M(s)N(s)  |     | F(s)F(s) := F(s)  |     |     |
| --- | --- | --- | --- | --------- | --------- | --- | ----------------- | --- | --- |
Using MATLAB, they can be solved as
_[S2+IOS+329
100  ]
|     |     |     |     |     |     | -46  |     |     | (9.92)  |
| --- | --- | --- | --- | --- | --- | ---- | --- | --- | ------- |
A(s) -
'i,  s2+7s+6
~  and
|     |     |     |        |     | -290s2 -   |        |     | 189s +     |         |
| --- | --- | --- | ------ | --- | ---------- | ------ | --- | ---------- | ------- |
|     |     |     |        |     |            | 114s - | 36  | 293]       |         |
|     |     |     | M(s) - |     |            |        |     |            | (9.93)  |
|     |     |     |        |     | [  46s2 +  |        | +   |            |         |
|     |     |     |        | -   |            | 34s    | 12  | -34s - 46  |         |
The compensators A -I (s)M(s) and A -I (s)L(s) are clearly proper. This completes the design.
The model matching discussed can be modified in several ways. For example. if stable
roots of det N2(s) are not inside the sector shown in Fig. 8.3(a), they can be included in th.
Go
Then they will be retained in  (s) and will not be canceled in the design. Instead of decoupling
the plant for each pair of input and output, we may decouple it for a group of inputs and a
group of outputs. In this case, the resulting overall transfer matrix is a block-diagonal matrix.
These modifications are straightforward and will not be discussed.
9.6  Concluding Remarks
In this chapter, we used coprime fractions to carry out designs to achieve pole placement or
model matching. For pole placement, the unity-feedback configuration shown in Fig. 9.I(a),
a one-degree-of-freedom configuration, can be used. If a plant has degree n, then any pole
placement can be achieved by using a compensator of degree n - 1 or larger. If the degree of
a compensator is larger than the minimum required, the extra degrees can be used to achieve
robust tracking, disturbance rejection, or other design objectives.

316 POLE PLACEMENT AND MODEL MATCHING
=
9.4 Repeat Problem 9.2 for a plant with transfer function g(s) (s - 1)/s(s - 2). Do
you need a feedforward gain to achieve tracking of any step reference input? Give your
reason.
9.5 Suppose the planttransferfunction in Problem 9.4 changes to g(s) = (s -0.9)/ s(s - 2.1)
after the design is completed. Can the overall system still track any step reference input?
Is the design robust'
g
9.6 Consider a plant with transfer function (s) = 1/ (s - I). Suppose a disturbance of form
w(r) = a sin(2r +e), with unknown amplitude a and phase e, enters the plant as shown
in Fig. 9.2. Design a biproper compensator of degree 3 in the feedback system so that
the output willlracl: asymptotically any step reference input and reject the disturbance.
Place the desired poles at -I ± j2 and -2 ± j 1.
9.7 Consider the unity feedback system shown in Fig. 9.10. The plant transfer function is
+
g(s) = 2/s(s 1). Can the output track robustly any step reference input? Can the
output reject any step disturbance w(r) = a? Why?
Figure 9.10
+
2 y
I.5
+
5(5 I)
9.8 Consider the unity-feedback system shown in Fig. 9.11(a). Is the transfer function from
r to y BIBO stable? Is the system totally stable? If not, find an input-<lutput pair whose
closed-loop transfer function is not BIBO stable.
5-2
CIs) g(s) y
5-2 T U 5 U I I ~
(a) (b)
Figure 9.11
9.9 Consider the unity-feedback system shown in Fig. 9.11 (b). (I) Show that the closed-loop
transfer function of every possible input-<lutput pair contains the factor (I +C(s)g(S
))-1 .
+
(2) Show that (I C(s)g(S»-1 is proper if and only if
I + C(oo)i(oo) oF 0
(3) Show that if C(s) and g(s) are proper, and if C(oo)i(oo) oF -I, then the system is
well posed.
+ + +
9.10 Given 8(S) = (s2 - 1)/(s) a,s2 a2S a), which of the following 8,,(S) are
implementable for any aj and b i.

References
We list only the references used in preparing this edition. The list does not indicate original sources of
the results presented. For more extensive lists of references. see References [2. 6. 13. 15].
I. Anderson. B. D. 0 .. and Moore. 1. B .. Optimal Control-Linear Quadratic Methods. Englewood
Cliffs. NJ: Prentice Hall. 1990.
2. Antsaklis. A. 1.. and Michel. A. N .. Linear Systems. New York: McGraw-Hill. 1997.
3. Callier. F. M .. and Desoer. C. A .• MlIltivariable Feedback Systems. New York: Springer-Verlag.
1982.
4. Callier. F. M .. and Desoer. C. A .. Linear System Theory. New York: Springer-Verlag. 1991.
5. Chen. C. T .• Inrroduction to Linear System Theory. New York: Holt, Rinehan & Winston. 1970.
6. Chen. C. T .. Linear System Theory and Design. New York: Oxford University Press. 1984.
7. Chen. C. T .. Analog and Digital Control System Design: Transfer Function. State-Space. and
Algebraic Methods. New York: Oxford University Press. 1993.
8. Chen. C. T.. and Liu. C. S .. "Design of Control Systems: A Comparative Study," IEEE Control
System Magazine. vol. 14. pp. 47-51. 1994.
9. Doyle. 1. c., Francis. B. A .. and Tannenbaum. A. R .• Feedback Control Theory. New York:
Macmillan, 1992.
10. Gantmacher, F. R .. The Theory of Matrices. vols. I and 2. New York: Chelsea, 1959.
I \. Golub. G. H .. and Van Loan, C. F., Matrix Computations 3rd ed., Baltimore: The Johns Hopkins
University Press. 1996.
12. Howze. J. W .. and Bhattacharyya. S. P. . "Robust tracking, error feedback. and lwo-degree-of-freedom
controllers." IEEE Trans. AlIIomatic Control. vol. 42, pp. 98~983. 1997.
13. Kailath. T.. Linear Svstems. Englewood Cliffs. NJ: Prentice Hall. 1990.
14. Kurcera. Y, Analysis and Design of Discrete Linear Control Systems. London: Prentice Hall. 1991.
w.,
15. Rugh, Linear Swem Theory. 2nd ed .. Upper Saddle River, NJ: Prentice Hall. 1996.
16. Strang, G .. Linear Algebra and Its Application. 3rd ed .. San Diego: Harcoun. Brace. lavanovich.
1988.
17. The Student Edition ofMATUB. Version 4. Englewood Cliffs. NJ: Prentice Hall. 1995.
18. Tongue. B. H .. Principles of Vibration. New York: Oxford University Press. 1996.
19. Tsui. C. C .. Robust COlltrol System Design. New York: Marcel Dekker. 1996.
20. Vardulakis. A. I. G .. Linear Multivariable Control. Chichester: John Wiley, 1991.
2 \. Vidyasagar. M .. Control Svstem Synrhesis: A Factorization Approach. Cambridge. ~A: MIT Press.
1985.
22. Wolovich. W. A .. Linear Multil'ariable Systems. New York: Springer-Verlag, 1974.
23. Zhou. K .. Doyle. J. C .. and Glover. K., Robust and Optimal COlllrol, Upper Saddle River. NJ:
Prentice Hall, 1995.
319

Problems  317
,
|     | s-I  | s + 1  |     | I   |     |
| --- | ---- | ------ | --- | --- | --- |
S- -
|     | (s +  | +         | +        |      |     |
| --- | ----- | --------- | -------- | ---- | --- |
|     | 1)2   | (s  2)(s  | 3)  (s - | 2)}  |     |
+
|     | (S2 - I)  | (s - I)(bos  | bl)     |     |                 |
| --- | --------- | ------------ | ------- | --- | --------------- |
|     | +         | +            | +  +    |     |                 |
|     | (S  2)2   | (s  2)2(s2   | 2s  2)  |     |                 |
| =   |           |              |         | =   | 1)/(s2 + 2s -'- |
9.11  Given g(s)  (s - I)/s(s - 2). implement the model goes)  -2(s - 2)
in the open-loop and the unity-feedback configurations. Are they totally stable? Can the
implementations be used in practice?
9.12  Implement Problem 9.11  in  the  two-parameter configuration.  Select the  poles to  be
canceled at s  =  -3. Is  A(s)  a  Hurwitz polynomial? Can you implement the  two
compensators as shown in Fig. 9.4(a)"' Implement the two compensators in Fig. 9.-+(d)
and draw its op-amp circuit.
9.13  Given a BIBO stable goes). show that the steady-state response .1',.,(1) :=  lim/_=-:  r(r)
excited by the ramp reference input ret) = at for t :::: 0 is given by
go(O)at +
|     | r,,(t) =  |     | g~(O)a  |     |     |
| --- | --------- | --- | ------- | --- | --- |
Thus if the output is to track asymptotically the ramp reference input we require go (0) =  I
=
and g~(O)  O.
9.14  Given a BIBO stable
m
|     | _        | bo+bls+···+bms     |         |     |     |
| --- | -------- | ------------------ | ------- | --- | --- |
|     | goes) =  |                    | __      |     |     |
|     |          | ~_~~               | --2.._  |     |     |
|     |          | ao +als + ... +anS |         | n   |     |
with n :::: m. show that go(O) =  0 if and only if aD = b o and al  = bl'
I and g~(O) =
|     |     |     | +   |     | +   |
| --- | --- | --- | --- | --- | --- |
9.15  Given a plant with transfer function g(s)  =  (s  3)(s - 2)/(S3  2s  - I). (I) find
conditions on bl. boo and a so that
|     |     | _  bls + bo  |     |     |     |
| --- | --- | ------------ | --- | --- | --- |
+ 2
|     |     | goes) =  2  |      |     |     |
| --- | --- | ----------- | ---- | --- | --- |
|     |     | s           | s+a  |     |     |
is implementable; and (2) determine if
+
|     | _   | (s - 2l\ | b s  bo)  |     |     |
| --- | --- | -------- | --------- | --- | --- |
|     |     | ==  ,    |  l        |     |     |
gats)
|     |     | (s  +  2)(5- | +  25  +  2)  |     |     |
| --- | --- | ------------ | ------------- | --- | --- |
is implementable. Find conditions on b and bo so that the overall transfer function will
l
track any ramp reference input.
9.16  Consider a plant with transfer matrix
1
+
|     |         | s         | 1   |     |     |
| --- | ------- | --------- | --- | --- | --- |
|     | G(s) =  | sis ~ I)  |     |     |     |
[
|     |     | s2 - | I   |     |     |
| --- | --- | ---- | --- | --- | --- |
Find a compensator in the unity-feedback configuration so that the poles of the overall
system are located at -2. -I ± j  and the rest at s ==  -3. Can you find a feed forward
gain so that the overall system will track asymptotically any step reference inpur'

318  POLE PLACEMENT AND MODEL MATCHING
9.17  Repeat Problem 9.16 for a plant with transfer matrix
|     | ,       | [  s+1  | I]    |
| --- | ------- | ------- | ----- |
|     | G(s) =  |         | -,--  |
|     |         | s(s-I)  | s--I  |
9.18  Repeat Problem 9.16 for a plant with transfer matrix
s -
2
s~ll
|     | G(s) _  | s2 - I  |     |
| --- | ------- | ------- | --- |
|     | -       | 1       |     |
[
|     |     | s   | s - 1  |
| --- | --- | --- | ------ |
1
9.19  Given a plant with the transfer matrix in Problem 9.18, is
|     |     | + IV  | 0   |
| --- | --- | ----- | --- |
4(s2 - 4s
| (;o(S) =  | +  +     | +         |     |
| --------- | -------- | --------- | --- |
|           | (S2  2s  | 2)(s  2)  |     |
+
4(S2 - 4s  1)
[  o
~,~~--~~+ ~
(s·+2s~ . 2)(s  2)
implementable? If yes, implement it.
r
9.20  Diagonalize a plant with transfer matrix
|     |     | ~][;  | ~   |
| --- | --- | ----- | --- |
= [ ~
|     | {;(s)  |     | S2  1  |
| --- | ------ | --- | ------ |
+  +
Set the denominator of each diagonal entry of the resulting overall system as s2  2s  2.

323
Answers to Selected Problems
x = [1  1] is a solution. Unique. No solution if y = [1  1 1]'.
3.7
O't  = 4/11.0'2 = 16/11. The solution
3.9
~~ ~~ ~116J
X= [:1
has the smallest 2-norm.
3.12
-']
|     |     |     | 0  0  |     |     |
| --- | --- | --- | ----- | --- | --- |
[~
|     |     | -   | 0  0  | 20  |     |
| --- | --- | --- | ----- | --- | --- |
A=
|     |     | 0   | 1  0  | -18  |     |
| --- | --- | --- | ----- | ---- | --- |
7  .
0  0
3.13  -1]
|     | [i  |     |     |     | 1 0 0]  |
| --- | --- | --- | --- | --- | ------- |
o
[
|     |     | 1  0  |     | AJ =  | 0  1  0  |
| --- | --- | ----- | --- | ----- | -------- |
QJ =
|     |     | o   |     |     | 002  |
| --- | --- | --- | --- | --- | ---- |
1
|     |     | 4 0]  |     |         | 0 I 0]  |
| --- | --- | ----- | --- | ------- | ------- |
|     |     | 20    | 1   | A4 =[0  | 0  1    |
Q4 =  [:
|     |     | -25  0  |     |     | 000  |
| --- | --- | ------- | --- | --- | ---- |
3.18
|          | =    |            |           |           | =        |
| -------- | ---- | ---------- | --------- | --------- | -------- |
| ~I()..)  | (A - | AI)l().. - | A2)       | Vtl()..)  | ~I()..)  |
| ~2(A) =  | (A - | AIl4       | Vt2(A) =  | (A -      | AIll     |
|          | =    |            |           | =         |          |
|          | (A - | All  4     | VtJ(A)    | (A -      | AI)  2   |
~J(A)
|     | =    |        |         | =    |      |
| --- | ---- | ------ | ------- | ---- | ---- |
|     | (A - | Ail 4  | Vt4(A)  | (A - | AI)  |
~4(A)
3.21
[i
1  n
| IO  |     |     |     | IOl  [1  | 1  1;2 ]  |
| --- | --- | --- | --- | -------- | --------- |
|     |     | 0   | A   | =        | 0  0      |
A =
o
|     |     | 0      |       |           | 0   |
| --- | --- | ------ | ----- | --------- | --- |
|     | l   | l      |       | l         |     |
|     |     | e - 1  | tel - | e +  1 ]  |     |
[ e
| =    | ~   | 1   | et  | 1   |     |
| ---- | --- | --- | --- | --- | --- |
| eAI  |     |     |     | -   |     |
et
0
3.22
[i
+
|     |      | 4t  | 2.5t"  |           |     |
| --- | ---- | --- | ------ | --------- | --- |
|     | e~1  |     |        | 3, + "']  |     |
+
|     |     |     | 1  20t  |     | 16t  |
| --- | --- | --- | ------- | --- | ---- |
=
|     |     |     | -25t  | 1 - | 20t  |
| --- | --- | --- | ----- | --- | ---- |

Answers to Selected Problems
CHAPTER 2
2.1  (a) Linear. (b) and (e) Nonlinear. In (b). shift the operating point to (0, Yo); then (u,  y)  is linear.
y  =
| where  |     | y - Yo.  |     |     |     |     |     |     |     |
| ------ | --- | -------- | --- | --- | --- | --- | --- | --- | --- |
2.3  Linear. time varying. causal.
2.5  No. yes. no for x(O)  f.  O. Yes. yes, yes for x(O) = O. The reason is that the superposition property
must also apply to the initial states.
| 2.9  y(t) = 0 for t  |     | < 0 and t > 4.  |     |              |     |     |                     |           |     |
| -------------------- | --- | --------------- | --- | ------------ | --- | --- | ------------------- | --------- | --- |
|                      |     |                 |     | I0 .5t2      |     |     | for 0               | < t  < 1  |     |
|                      |     |                 |     | -1.5t2 +4t - |     |     | 2  for 1::: t::: 2  |           |     |
Y(/) =
|             |       |           |     | -y(4 -           |     | t)  | for 2 < t ::: 4  |     |     |
| ----------- | ----- | --------- | --- | ---------------- | --- | --- | ---------------- | --- | --- |
|             | =     | +         | =   |                  |     |     |                  |     |     |
| 2,10  g(s)  | 1/(5  | 3), i(t)  |     | e-3t for t ~ O.  |     |     |                  |     |     |
2.12
]-1
[DJI
G(s) =
|     |     |      |       | (5)      | Dlz(s)  |     | [Nil (5)  | NI2(S)]  |     |
| --- | --- | ---- | ----- | -------- | ------- | --- | --------- | -------- | --- |
|     |     |      |       | D21 (5)  | D22(S)  |     | N21 (5)   | N22(S)   |     |
|     |     | = e  | = O.  |          |         | =   | =         |          |     |
2.15  (a) Define XI  andx2  Then XI  X2.X2  -(gll)sinxi - (ulml)cosxl. Ife is
small, then
|     |     |     | .    | [0  |     | I]  | [  0 ]  |     |     |
| --- | --- | --- | ---- | --- | --- | --- | ------- | --- | --- |
|     |     |     | x =  |     |     | x+  |         | u   |     |
0
|     |     |     |     | -gil  |     |     | -llmg  |     |     |
| --- | --- | --- | --- | ----- | --- | --- | ------ | --- | --- |
It is a linear state equation.
|                |     | =       | =      | =   |           |     | = O      |     |     |
| -------------- | --- | ------- | ------ | --- | --------- | --- | -------- | --- | --- |
| (b) Define XI  |     | el,x,   | 01.X3  |     | e2,andx4  |     | 2. Then  |     |     |
|                |     | XI  ==  |        |     |           |     |          |     |     |
X2
|     |     | X2  =  | - (gl lil sin XI          |     | +   | (m2glmll) COSX3 sin(x3 - |         |     | XI)  |
| --- | --- | ------ | ------------------------- | --- | --- | ------------------------ | ------- | --- | ---- |
|     |     |        | +  (llmll) sinx3 sin(x3 - |     |     |                          | XI)' u  |     |      |
Xl = x.
|     |     |       |                   |     | +   | I m212)(COS X3)U  |     |     |     |
| --- | --- | ----- | ----------------- | --- | --- | ----------------- | --- | --- | --- |
|     |     | X4 =  | - (g 112) sin Xl  |     |     | (I                |     |     |     |
This is a set of nonlinear equations. If Bi  "" 0 and BiB)  "" 0, then it can be linearized as
321

322  ANSWERS TO SELECTED PROBLEMS
|     |     |     |     |     |     | I   | 0   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
fJ'{JJ
;  ~  [ -gem, +;m')lm",
o
mzg/ml/l
|     |     |     |     |     |     | 0   | 0   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
0
|     |     |     |     |     |     | -g/ | Iz  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
2.16  From
|     |     |     |     | mh =       |     | h  =  |            | u   |     |     |
| --- | --- | --- | --- | ---------- | --- | ----- | ---------- | --- | --- | --- |
|     |     |     |     |            | f   | l -   | kif) -     | k2  |     |     |
|     |     |     |     | Ii} +bB =  |     | +/    | )12 -/lfl  |     |     |     |
|     |     |     |     |            |     | (/1   | 2          |     |     |     |
=
we can readily obtain a ;tate equation. Assuming I  0 and taking their Laplace transforms can
yield the transfer function.
I
|             | =            |     |     |      |      | I              |     |             |               |           |
| ----------- | ------------ | --- | --- | ---- | ---- | -------------- | --- | ----------- | ------------- | --------- |
| 2.18 81(s)  | 5'1(5)/U(5)  |     | =   | 1/(A | R 5  | +  I),  82(S)  | =   |             |               | +         |
|             |              |     |     |      | I I  |                |     | Y(S)/YI(S)  | =  i /(AzRzs  | I). Yes.  |
Y(5)/U(S) = 81 (5)82(S).
2.20
|     |     |     |     |     |     | 0   |     | I   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     |     |     |     | l/C | ]   |     |     |
|     |     | x=  | [   | 0   |     |     |     |     |     |     |
|     |     |     |     | 0   |     | 0   | I/  | C,  |     |     |
X
+
|     |     |     |     | -I/LI  | -I/LI  | -(RI  |     | R )/ LI  |     |     |
| --- | --- | --- | --- | ------ | ------ | ----- | --- | -------- | --- | --- |
2
[~~]
|     |     |     | + [  | 0   | -I;CI]  |     |     |     |     |     |
| --- | --- | --- | ---- | --- | ------- | --- | --- | --- | --- | --- |
0
|     |     |     |     | I/LI  | RI/ | LI  | -   |     |     |     |
| --- | --- | --- | --- | ----- | --- | --- | --- | --- | --- | --- |
=
+
|     |     | Y         | [-1   | - I  | - Rdx  | [I  | Rdu         |     |     |     |
| --- | --- | --------- | ----- | ---- | ------ | --- | ----------- | --- | --- | --- |
|     |     |           | yes)  |      |        |     | +           |     |     |     |
|     |     | 81 (s) =  |       | =    |        | s2  | (Rz/ LI )S  |     |     |     |
+
|     |     |          | UI (s)  |     | s 2 + (RI  | R2)        | s+  | ( -1 +-1) -I  |       |     |
| --- | --- | -------- | ------- | --- | ---------- | ---------- | --- | ------------- | ----- | --- |
|     |     |          |         |     |            | LI         |     | C             | C LI  |     |
|     |     |          |         |     |            |            |     | I             | 2     |     |
|     |     | 82(S) =  | yes) =  |     |            | +          |     | +  (Rz/Ld)    |       |     |
|     |     |          |         |     | (R15       | (l/CIl)(s  |     |               |       |     |
+
|     |     |     | U2(S)  |     | s 2 + (RI  | R2)  |     | ( -I +-I) -I  |     |     |
| --- | --- | --- | ------ | --- | ---------- | ---- | --- | ------------- | --- | --- |
s+
|     |     |                      |     |     |     | LI  |     | C I  | C 2  LI  |     |
| --- | --- | -------------------- | --- | --- | --- | --- | --- | ---- | -------- | --- |
|     |     | yes) = 81 (S)UI (s)  |     |     | +   |     |     |      |          |     |
82(S)U2(S)
CHAPTER 3
n,
U
| 3.1  | [-2  | 1.5]'.  |     |     |     |     |     |     |     |     |
| ---- | ---- | ------- | --- | --- | --- | --- | --- | --- | --- | --- |
3.3
2]
[
|     |     |     |       | I     | -3  |       |            |     |     |     |
| --- | --- | --- | ----- | ----- | --- | ----- | ---------- | --- | --- | --- |
|     |     |     | ql =  | 3.74  | I   | q2 =  | 1.;32 [:]  |     |     |     |
3.5  p(AI) = 2, nullity(AIl=I; 3, 0; 3, l.

324 ANSWERS TO SELECTED PROBLEMS
3.24
0
[lnAI In~AJ
B = 0 In 1.2
0 0
1/1.
['n A I~J
B = 0 In A
0 0
3.32 Eigenvalues: O. 0. No solution for CI. For any m I. [Ill I 3 - m I]' is a solution for C2·
3.34 )6. 1. 4.7. 1.7.
CHAPTER 4
4.2 \'(1) = 5e-t sin t for t ::: O.
4.3 For T = IT.
0] [
x[k + 1] = [ -0.~432 + 1.5648 ]
-0.0432 x[k] -l.0432 !I[k]
y[k] = [2 3]x[k]
4.5 ~!ATLAB yields Iylmax = 0.55.lxII""" = 0.5.lx2Im"", = l.05. and Ix) I",,,", = 0.51 for unit
step input. Define XI = XI . .\:' = 0.5x2. and.\:3 = Xl· Then
-2 0 0] [1]
[
i = 0.5 0 0.5 i + 0 it y = [1 - 2 O]i
o
-4 -2 I
The largest permissible a is 10/0.55 = 18.2.
4.8 They are not equivalent but are zero-state equivalent.
4.11 l'sing (434). we have
0 -2 0] [' : 0- l'
. [ - 0 3 -3 0 -") 0 I
~-
X=
1 0 0
>+ :
0 0
") 4
y = [ 2 -3] x+ [0 0] 11
-3 -2 -6 -2 I I
4.13
-3 I 0 0] [ 2
~3]
-2 0 0 0 4
x= [ o x+ It
0 -3 I -3 -2
o
0 -2 0 -6 -2

Answers to Selected Problems  327
CHAPTER 7
7.1
|     | -2  | 12 ]  |     | [I]  |     |     |
| --- | --- | ----- | --- | ---- | --- | --- |
[
x+
| x=  |     |          |     |       | y = [0  | 1  - IJx  |
| --- | --- | -------- | --- | ----- | ------- | --------- |
|     |     | ~  0  ~  |     | ~  u  |         |           |
Not observable.
7.3
|       | -2  | 1 2   |     | 1]  |     |     |
| ----- | --- | ----- | --- | --- | --- | --- |
|       |     | QI]   |     | [   |     |     |
| x. =  | 1   | 0  0  | x+  | 0   |     |     |
Q2
| [   |     |     |     | u   | y = [0  | 1  - 1 c41x  |
| --- | --- | --- | --- | --- | ------- | ------------ |
o
|     |     | 1  0  Q3  |     | 0   |     |     |
| --- | --- | --------- | --- | --- | --- | --- |
o
|     |     | 0  0  |     | 0   |     |     |
| --- | --- | ----- | --- | --- | --- | --- |
Q4
For any Qi and C4. it is an uncontrollable and unobservable realization.
|     |     | -3  -2]  |     | [I]  |     |     |
| --- | --- | -------- | --- | ---- | --- | --- |
[
x+
x=
|     |     | 1   | 0   | 0   | y = [0  | IJx  |
| --- | --- | --- | --- | --- | ------- | ---- |
II
A controllable and observable realization.
7.5
Solve the monic null vector of
|     |     | -1  | 0   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
[I
[-NO]
o ]
|     |     | 2   | -I  | -1  | Do  |     |
| --- | --- | --- | --- | --- | --- | --- |
=0
|     |     | 0   | 0   | 2   | -NI  |     |
| --- | --- | --- | --- | --- | ---- | --- |
°
|     |     | 0   | 4   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
DJ
°
| I]'. Thus 0.5/(0.5 +  |     |     |     | 1/(25 + 1).  |     |     |
| --------------------- | --- | --- | --- | ------------ | --- | --- |
as (-0.5 0.5  s) =
7.10
|     |     | °   | ]x+[o]u  |     |     |     |
| --- | --- | --- | -------- | --- | --- | --- |
x=[
y = (I  O]x
1
|     |     | -2  -I  |     | 1   |     |     |
| --- | --- | ------- | --- | --- | --- | --- |
7.13
|     | ~1(S)=5(s+l)(s+3)  |          |        |      | deg=3    |     |
| --- | ------------------ | -------- | ------ | ---- | -------- | --- |
|     |                    | =  (s +  |        | +    |          |     |
|     | ~2(S)              |          | 1)3(s  | 2)2  | deg = 5  |     |
7.17  Its right coprime fraction can be computed from any left fraction as
| •   | = [2.5  | S+0.5][  |     | 0.5s  | S2+0.5S]-1  |     |
| --- | ------- | -------- | --- | ----- | ----------- | --- |
G(s)
+ 2.5
|     |     | 2.5  s  |     | 5 - 0.5  | -0.5  |     |
| --- | --- | ------- | --- | -------- | ----- | --- |
or, by interchanging their two columns,

Answers to Selected Problems  325
|     | =[IOOOJX  |         |     | [OOJU  |     |
| --- | --------- | ------- | --- | ------ | --- |
|     | Y         | 000+11  |     |        |     |
BOlh have dimension 4.
4.16
de J
|     |          |     | J~  5  |     |     |
| --- | -------- | --- | ------ | --- | --- |
|     | X(t)=[~  |     | e0 ,:  |     |     |
eO.5,-
de]
J,'
|     |     | 1   | _eO.5,'  | e°.5,'  |     |
| --- | --- | --- | -------- | ------- | --- |
e /,o'-'J)
|     | 4>(t, to) =  | 0    |      |     |     |
| --- | ------------ | ---- | ---- | --- | --- |
|     |              | [    | 05   |     |     |
|     |              | e-'  | e']  |     |     |
[
|     | X(t) =       | 0         | 2e-'         |           |             |
| --- | ------------ | --------- | ------------ | --------- | ----------- |
|     |              | e-(t-to)  | 0.5(e' e'o - |           | e-' e''-']  |
|     | 4>(t, toJ =  | [         | 0            | e-(T-'oJ  |             |
4,20
eCos t -C05 '0
e-SiO~+Stn'o
|     | 4>(t, to) =  |     | 0   |     |     |
| --- | ------------ | --- | --- | --- | --- |
]
[
4.23  Let x(t)  =  P(f)x(t) with
|     |     | = [   |         | }O, ]  |     |
| --- | --- | ----- | ------- | ------ | --- |
|     |     | P(t)  | e-~osr  |        |     |
x
Then x(1) = 0 .  = O.
4.25
|             |     | t2e-A'    | ]    |       |         |
| ----------- | --- | --------- | ---- | ----- | ------- |
| X = O· x +  |     | -2re-I.'  | y =  | [eAT  | 2/.t)x  |
|             |     |           | II   |       | te!"  t |
|             |     | [  e-At   |      |       |         |
),3]
|     | 3),  | _3),2  |     | [I]   |              |
| --- | ---- | ------ | --- | ----- | ------------ |
|     | = [  |        | +   |       | =            |
| X   | ~    | 0  ~   | x   | ~  u  | y  [0 0 2)x  |
CHAPTER 5
|     | =   |     | =   |     |     |
| --- | --- | --- | --- | --- | --- |
5.1  The bounded input u (r)  sin t excites y(t)  0.5t sin t, which is not bounded. Thus the system
is nOl BIBO stable.
5,3  No. Yes.
5.6  If u(t)  =  3, then y(t) .....  -6. If u(t)  =  1.26 sin(2t  +  1.25).
sin 2t. then yet) .....
5.8  Yes.

326  ANSWERS TO SELECTED PROBLEMS
5.10 Not asymptotically stable. [ts minimal polynomial can be found from its Jordan fonn as t(;·) =
+
A(A  I). A =.0 is a simple eigenvalue. thus the equation is marginally stable.
teA) =
5.13  Not asymptotically stable. [ts minimal polynomial can be found from its Jordan fonn as
+
(A - 1)2(A  I). A =  1 is a repeated eigenvalue. thus the equation is not marginally stable.
5.15  If N = I. then
2.2 1.6J
[
M=
|     |     |     |     | 1.6  4.8  |     |     |     |
| --- | --- | --- | --- | --------- | --- | --- | --- |
It is positive definite; thus a\l eigenvalues have magnitudes less than I.
5.17 Because x'Mx = x' l O.S (M  +
M') ]x. the only way to check positive definiteness of nonsymmetric
+
M is to check positive definiteness of sym"1"tric O.S(M  M') .
•
5.20 Both are BlBO stable.
5.22  BlBO stable. marginally stable, not asymptotically stable. pet) is not a Lyapunov transfonnation.
CHAPTER 6
6.2  Controllable. observable.
6.5
J
|     | [~I  | ~I  | [~J  |     | y =  [0  | - I]x  | + 2u  |
| --- | ---- | --- | ---- | --- | -------- | ------ | ----- |
| x   |      |     | x +  |     |          |        |       |
|     | =    |     |      | u   |          |        |       |
Not controllable. not observable.
| =  1 for all i and IJ.  | =   |     |     |     |     |     |     |
| ----------------------- | --- | --- | --- | --- | --- | --- | --- |
6.7  lJ.i  I.
6.9  Y = 2u.
6.14 Controllable. not observable.
6.17  Using XI and X2 yields
| .    | [-2/11  | OJ  | [-2/IIJ  |       |      |      |        |
| ---- | ------- | --- | -------- | ----- | ---- | ---- | ------ |
|      |         |     | +        |       | y =  | [-1  | - I]x  |
| x =  |         |     | x        |       | u    |      |        |
|      | 3/22    | 0   |          | 3/22  |      |      |        |
This two-dimensional equation is not controllable but is observable.
Using XI, Xl. and X3 yields
-2/11
|     |     |     | 0]  | [-2/11]  |     |     |     |
| --- | --- | --- | --- | -------- | --- | --- | --- |
o
| x   | [     | o   | x +  | 3/22  |     | y = [0  | 0  I]x  |
| --- | ----- | --- | ---- | ----- | --- | ------- | ------- |
| =   | 3/22  |     | 0    |       | u   |         |         |
1/22
o
|     |     |     | 0   | 1/22  |     |     |     |
| --- | --- | --- | --- | ----- | --- | --- | --- |
This three-dimensional equation is not controllable and not observable.
=
6.19 For T  IT, not controllable and no! observable.
Not controllable at any t. Observable at every t.
6.21

328  ANSWERS TO SELECTED PROBLEMS
]-1
|     |     |       | =  [5 + 0.5  | 2.5] [52 + 0.55  |       |     |          |     |
| --- | --- | ----- | ------------ | ---------------- | ----- | --- | -------- | --- |
|     |     | G(5)  |              |                  |       |     | 0.55     |     |
|     |     |       |              | 5 + 2.5  2.5     | -0.5  |     | 5 - 0.5  |     |
esing the latter. we can obtain
|     |     | .   | [-0.5  | -0.25  | -0.25]  | [  I  | -~5]  |     |
| --- | --- | --- | ------ | ------ | ------- | ----- | ----- | --- |
|     |     |     | I      | 0      | 0  x+   | 0     |       | u   |
X=
o
|     |     |     |         | 0.5   | 0.5  | 0   |     |     |
| --- | --- | --- | ------- | ----- | ---- | --- | --- | --- |
|     |     |     | I  0.5  | 2.5]  |      |     |     |     |
Y =
|     |     |     | [       | x    |     |     |     |     |
| --- | --- | --- | ------- | ---- | --- | --- | --- | --- |
|     |     |     | I  2.5  | 2.5  |     |     |     |     |
CHAPTER 8
| 8.1  k =  | [4  1].  |     |     |     |     |     |     |     |
| --------- | -------- | --- | --- | --- | --- | --- | --- | --- |
8.3  For
|     |     |     | F [-I  |     | 0]   |     |     |     |
| --- | --- | --- | ------ | --- | ---- | --- | --- | --- |
|     |     |     |        | =   | k =  | [l  | I]  |     |
o
-2
we have
|     |     |     | T =  | [0  1/13]  | k  = krl =  |     | [4  IJ  |     |
| --- | --- | --- | ---- | ---------- | ----------- | --- | ------- | --- |
|     |     |     |      | 1  9/13    |             |     |         |     |
8.5  Yes. yes. yes.
| 8.7  u =  | pr - kxwithk = [1547  |     |     | - 8] andp =0.5.  |     |     |     |     |
| --------- | --------------------- | --- | --- | ---------------- | --- | --- | --- | --- |
2] and p = 0.5. The overall transfer function is
| 8.9  u[k] =  | pr[k] - | kx[k] with k =  |     | [l 5     |                    |     |     |     |
| ------------ | ------- | --------------- | --- | -------- | ------------------ | --- | --- | --- |
|              |         |                 |     | ,        | 0.5(2:' - 8: + 8)  |     |     |     |
|              |         |                 |     | gr(z) =  | -                  |     |     |     |
|              |         |                 |     | .        | ->                 |     |     |     |
and the output excited by r[k] =  a is )'[0] =  O. v[l] =  a. y[2) =  -3a. and )i[k] =  a for
k ::: 3.
8.11  Two-dimensional estimator:
|     |     |     | .  [-2  | 2]  |                     |     |     |     |
| --- | --- | --- | ------- | --- | ------------------- | --- | --- | --- |
|     |     |     | Z=      |     | Z+ [0.6282] u+ [I]  |     |     |     |
v
|     |     |     |          | -2  -2  | -0.3105  |     | 0   | .   |
| --- | --- | --- | -------- | ------- | -------- | --- | --- | --- |
|     |     |     | ,  [-12  | -27.5]  |          |     |     |     |
|     |     |     | x=       |         | Z        |     |     |     |
|     |     |     |          | 19      | 32       |     |     |     |
One-dimesnional estimator:
=  -3: +
|     |     |     |     | i:  | (\3/21)/1 +  |     |     |     |
| --- | --- | --- | --- | --- | ------------ | --- | --- | --- |
V
|     |     |     |     | [-4  | 21]     |      |     |     |
| --- | --- | --- | --- | ---- | ------- | ---- | --- | --- |
|     |     |     |     | x =  |         | [y]  |     |     |
|     |     |     |     |      | 5  -21  | z    |     |     |

Index
Actuating signal. 231 controller·estimator. 270. 287
Adder. 16 feedback. 267
Additivity. 8. 32 no-plant-leakage. 283
Adjoint. 52 one-degree-of-freedom. 270. 287
Asymptotic stability. 131. 138 open-loop. 269
Asymptotic tracking. 242. 302 plant-in put-output feedback. 270
of ramp input. 276 two-degree-of-freedom. 270. 287
of step input. 276 two-parameter. 270. 287. 291. 307
unity-feedback. 273. 284. 287
Balanced realization. 204. 227 Controllability. 144. 169. 176
Basis. 45 after sampling. 172
change of. 53
from the origin. 172
onhonormal, 46
Gramian. 145. 170
Bezout identity. 272
index. 151
BIBO stability. 122. 125. 138. 192
indices. 150. 225
Black box. 5
matrix, 145. 169
Blocking zero. 15.305
to the origin. 171
Convolution. integral. 12
Canonical-form. companion. 97. 203
discrete. 32
controllable, 102. 187.235
Coprimeness, 15. 187.21 I, 214
Jordan, 61. 164. 182
left, 211
modal. 98. 182.241
right, 211
observable. 188
Cyclic matrix. 256
Causality. 6. 10. 32
Cayley-Hamilton theorem. 63
Characteristic polynomial. 55, 225 Dead beat design. 267
of constant matrix. 55 Decoupling, 311
of rational function. 189 Degree of rational function, 189
of rational matrix. 205 McMi lIan. 205
Column degree. 212. 225 of rational matrix. 205, 211
Column-degree-coefficient matrix. 213. 219 Description of systems. 2
Column echelon form. 219 external,2
Column indices. 215 input-output. 2. 8. 12
Companion-form matrix. 54. 81 internal. 2
characteristic polynomial of. 55 state-space. 2. 10. 35
eigenvectors of. 81 Determinant. 52
Compensator. 273. 283 Discretization. 90
feedback. 287 Disturbance rejection. 243. 277
feedforward. 287 Divisor. common. 187,210
Compensator equation. 27 I greatest common. 187, 211
Configuration. See Control configuration left. 210
Control configuration. 270 right. 210
closed-loop. 267 Duality, theorem of. 155
331

,\nswers to Selected Problems 329
8.13 Sdect
1
-4 3
oo 00
F = -3 4
o 0 -5 4
[
o 0 -4 -5
If K = [1 0 1 0] h K = [62.5 147 20 515.5]
o t en o
0 0 0 0 0 0
[-606
J
If K = [1 0 0 0] then K = . 1 - -168 -14.2 -?
000 371.1 119.2 14.9 2.2
CHAPTER 9
9.2 C(s) = (lOs + 20)/(s - 6). p = -0.2.
9.4 C(s) = (22s - 4)/(s - 16). p = 1. There is no need for a feed forward gain because g(s)
Is.
contains 1
+ + + + 4».
9.6 C(s) = (7s3 14s~ 34s 25)/(s(s~
9.8 Yes. no. The transfer function from r to u is gu,(s) = sl(s + 1)(s - 2). which is not BIBO
stable.
9.10 Yes. no, no, no, yes. no (row-wise).
9.12 Cj(s) = -2(s+3)/(s-21).C2(s) = (28s-6)/(s-21).A(s) =s-21isnotHurwitz.lts
implementation in Fig. 9.4(a) will not be totally stable. A minimal realization of [C 1 (s) - C 2 (s)]
is
[:J
i=21x+[-48 -582J y = x + [-2 - 28] [: ]
from which an op-amp circuit can be drawn.
9.15 (I) a > 0 and bo = -2b j• (2) Yes. bo = -2. h = -4.
9.16 The I x 2 compensator
I
+
C(s) = 3 [3.5s 12 - 2J
s + .5
will place the closed-loop poles at -2. -1 ± j. -3. No.
9.18 If we select
+ + + + + +
F(s) = diag«s 2)(s" 2s 2)(s 3). (s2 2s 2»
then we cannot find a feedforward gain to achieve tracking. If
+ + + +
(s 2) (s2 2s 2)(s 3) 0 ]
F~)= •
[
I s-+2s+2
then the compensator

330  ANSWERS TO SELECTED PROBLEMS
]-1
|     |     |     | 5 - 4.7  | -53.7  |     | [-30.35 - | 29.7  | 4.25 - | 12]  |
| --- | --- | --- | -------- | ------ | --- | --------- | ----- | ------ | ---- |
1
| C(5) = A- | (5)B(5) =  |     | -3.3  |        |     |            |     |       |     |
| --------- | ---------- | --- | ----- | ------ | --- | ---------- | --- | ----- | --- |
|           |            |     | [     | 5-4.3  |     | -0.75-0.3  |     | 45-1  |     |
and the feedforward gain matrix
=
|     |     |     | p   | [0.92  | 0]  |     |     |     |     |
| --- | --- | --- | --- | ------ | --- | --- | --- | --- | --- |
|     |     |     |     | -4.28  | 1   |     |     |     |     |
will achieve the design.
9.20 The diagonal transfer matrix
|     |     |     |     | -2(5 - | 1)  |     |     |     |     |
| --- | --- | --- | --- | ------ | --- | --- | --- | --- | --- |
+
|     |     | Go(s) =  | 52  | 2s :- | 2   |              |     |     |     |
| --- | --- | -------- | --- | ----- | --- | ------------ | --- | --- | --- |
|     |     |          |     |       |     | _2(SO _  1)  | ]   |     |     |
o
[
|     |     |     |     |     | l'  | + 2s + 2  |     |     |     |
| --- | --- | --- | --- | --- | --- | --------- | --- | --- | --- |
s2
is impiememable. The proper compensators A -I (s)L(s) and A -I (s)M(s) with
|     | A(S)=[5+5  |      | -14]  |     | L(5) =  | [-2(S+3)  | 2(5+3)]  |     |     |
| --- | ---------- | ---- | ----- | --- | ------- | --------- | -------- | --- | --- |
|     |            | o    | +     |     |         |           |          |     |     |
|     |            |      | 5  4  |     |         | 2         | -25      |     |     |
|     |            | [-6  | 1]    |     |         |           |          |     |     |
135 +
M(s) =
2  -25
in the two-parameter configuration will achieve the design.

332 INDEX
Eigenvalue. 55 basis of. 45
assignment of. 23 ... 256 change of basis. 53
index of. 62 dimension. 45
multiplicity of. 59. 62 Linearity, 7
Eigenvector. 55 Linearization. 18. 30
generalized, 59 Link. 27
Equivalence, 95, 112. 191 Lyapunov equation. 70. 239
algebraic. 95, 112 discrete, 135
Lyapunov, 114 Lyapunov theorem. 132. 135
zero-state, 96 Lyapunov transfonnation. 114
Equivalence transfonnation, 95,112,152
Markov parameter. 200. 225
Floquet, theory of. 115 Matrix. M
Fraction, polynomial, 189 cofactor of. 52
coprime. 189. 192 cyclic. 256
matrix, 209, 210 function of. 65
Fundamental cutset. 27 fundamental, 107
Fundamental loop. 27 inverse of. 52
Fundamental matrix. 107, 108 left inverse of. 208
minor of. 52. 205
gcd. 187 nilpotent, 61
geld. 112 nons in gular. 52
gcrd,112 nonn of. 78
General solution, 50. 272, 282 oMogonal. 74
Generalized eigen vector, 59 principal minor. 75
chain of. 59 leading. 75
grade of, 59 pseudo inverse of. 208
Gramian, controllability, 145. 170 rank of. 49
observability. 156, 171 right inverse of. 208
singular value of. 76
Hankel matrix, 201, 226 state transition, 108
Hankel singular value. 199 symmetric. 73
Homogeneity, 8, 32 trace of. 83
Hurwitz polynomial. 271, 285 1v!inimal polynomial. 62
~Iinimal realization, 184. 191
Implementable transfer function, 285. 306 Minimum energy control, 149
Impulse response. 10 ~linor. 52. 205
matrix, 10 Modal fonn. 98, 182. 241
sequence, 32 Model matching. 283. 306
Impulse sequence. 31 Model reduction, 200
Integrator. 16 Monic polynomial. 62
Internal model principle, 247, 279 ~Iultiple, left, 210
Invener. 16 right. 210
~Iultiplier. 12
lacobian, 18
lordan block, 60 Nilpotent matrix. 61
lordan-fonn matrix. 60. 164 Nominal equation. 243
Nonn. of matrix, 78
Kalman decomposition theorem. 162 Euclidean. 47
induced, 78
Laplace expansion. 52 of vector, 46
Laplace transfonn. 13 N onnal tree, 27
Leverrier algorithm. 83 Null vector, 49
Linear algebraic equations. 48 monic. 194
Linear space. 45 Nullity, 49

INDEX 333
Observability, 153, 170, 179 strictly proper. 15
Gramian, 156, 171 ReachabIlity. 172
index, 157 Realization. 100
indices. 157, 225 balanced, 197.204.227
matrix. 156, 171 companion-form. 203
Observer. See State estimator controllable-form. 101. 10-1,223
Op-amp circuit. 16 input-normal. 199
magnitude scaling, 98 minimal. 189.207
Orthogonal matrix. 7-1 observable-form. II 8. 119
Orthogonality of vectors. 47 output-normal. 197
Orthonormal set, 47, 48 time-varying. liS
Reduced. column. 212
Parameterization, 50. 27], 282 row. 212
Periodic state system. 114 Regulator problem, 242, 302
Pole. 15 Relaxedness. 10
Pole placement. 273, 292 Response. 8. 3 I
Pole-zero cancellation, 287 impulse. 10
unstable. 287 zero-input. 8. 31
Pole-zero excess inequality, 285 zero-state. 8. 31
POlynomial matrix, 210 Resultant. generalized. 215
column degree, 212. 225 Sylvester, 193.274
column-degree-coefticient matrix. 213. 219 Robust design. 243. 30-1
column reduced, 212 Robust tracking, 243, 278
echelon form. 219. 220 Row degree. 212. 225
left di visor. 210 Row-degree-coefficient matrix. 21 J
left multiple, 210 Row echelon form. 220
right di visor. 210 Row indices, 220
right multiple, 210
row degree, 212. 225 Schmidt orthonormalization. 48
row-degree-coefficient matrix. 213 Separation property, 255. 266
row reduced, 212 Servomechanism. 242
unimodular, 210 Similar matrices. 54
Positive definite matrix. 74 Similarity transformation, 54
Positive semidefinite matrix. 74 Singular value. 76
Primary dependent column. 19-1. 215. ] 19 Singular value decomposition. 77. 204. 226
row. 220 Stability. asymptotic, 130, 138
Principal minor. 75 BIBO. 122. 125. 138
leading. 75 discrete, 126. 129
Pseudoinverse. 208 in the sense of Lyapunov. 130. 131
Pseudostate. 186. 221 marginal. 130. 131. 138
IOtal. 284
QR decomposition. 196 Stabilization. 2-17
Quadratic form. 73 State. 6
pseudo-, 186. 121
Range space. 49 variable, 7
Rank. of matrix, -19 State equation. 2. II. IS
of product of matrices, 72 discrete-time. 35.91. liD
Rational function. 14 discretization of. 91
biproper. 15 equi valent. 95
improper. IS. 3-1 periodic, 11-1
proper. 14 reduclion, 159. 162, 181
stricti y proper, I 5 solution of, 87. 93, 106
Rational matrix. 15 time-varying. 106. 110
biproper. 15 State estimator. 248. 263
proper. IS asymptotic. 249

334 INDEX
State estimator (continued) zero of, 15
closed-loop. 249 Transfer matrix. 14, 16
full-dimensional. 248. 263 blocking zero. 15. 305
open-loop. 248 pole of. 15
reduced-dimensional. 251. 264 transmission zero. 302, 311
State feedback. 232 Transmission zero, 302, 311
State-space equation. See State equation Tree. 27
State transition matrix, 108 branch. 27
Superposition property. 8 normal, 27
Sylvester resultant. 193, 274 Truncation operator, 38
Sylvester's inequality, 207
System. I Unimodular matrix. 210
causal, 6. to Unit-time-delay element, 7. 12. 14.33
continuous-time. 6
discrete-time. 6, 3 1 Vandermonde determinant. 81
i
distributed. 7 Vector, 45
I
linear, 7 Euclidean norm of, 47
lumped. 7 Infinite norm of, 47
memory less, 6 I-norm of, 47
MIMO,5 2-norm of, 47
multi variable, 5
nonlinear, 7 Well-posedness. 284
single-variable. 5
SISO,5 Zero. 15
time-invariant. 11 blocking. 15,305
time-varying, 11 minimum-phase zero, 311
nonminimum-phase zero. 311
Total stability, 284 transmission, 302. 311
Trace of matrix, 83 Zero-input response. 8. 31
Tracking. See Asymptotic tracking Zero-pole-gain form, 15
Transfer function, 13 Zero-state equivalence, 96
discrete. 33 Zero-state response, 8, 31
pole of. 15 ,-transform. 32