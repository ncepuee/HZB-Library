Wei Ren · Randal W. Beard
Distributed Consensus
in Multi-vehicle
Cooperative Control
Theory and Applications
123

Communications and Control Engineering

Series Editors
E.D. Sontag • M. Thoma • A. Isidori • J.H. van Schuppen
Published titles include:
Stability and Stabilization of Infinite Dimensional
Systems with Applications Robust Control (Second edition)
Zheng-Hua Luo, Bao-Zhu Guo and Omer Morgul Jürgen Ackermann
Nonsmooth Mechanics (Second edition) Flow Control by Feedback
Bernard Brogliato Ole Morten Aamo and Miroslav Krstić
Nonlinear Control Systems II Learning and Generalization (Second edition)
Alberto Isidori Mathukumalli Vidyasagar
L-Gain and Passivity Techniques in Nonlinear Constrained Control and Estimation
2
Control Graham C. Goodwin, María M. Seron and José A.
Arjan van der Schaft De Doná
Control of Linear Systems with Regulation and Randomized Algorithms for Analysis and Control
Input Constraints of Uncertain Systems
Ali Saberi, Anton A. Stoorvogel and Peddapullaiah Roberto Tempo, Giuseppe Calafiore and Fabrizio
Sannuti Dabbene
Robust and H∞ Control Switched Linear Systems
Ben M. Chen Zhendong Sun and Shuzhi S. Ge
Computer Controlled Systems Subspace Methods for System Identification
Efim N. Rosenwasser and Bernhard P. Lampe Tohru Katayama
Control of Complex and Uncertain Systems Digital Control Systems
Stanislav V. Emelyanov and Sergey K. Korovin Ioan D. Landau and Gianluca Zito
Robust Control Design Using H∞ Methods Multivariable Computer-controlled Systems
Ian R. Petersen, Valery A. Ugrinovski and Andrey Efim N. Rosenwasser and Bernhard P. Lampe
V. Savkin
Dissipative Systems Analysis and Control
Model Reduction for Control System Design (2nd Edition)
Goro Obinata and Brian D.O. Anderson Bernard Brogliato, Rogelio Lozano, Bernhard Maschke
and Olav Egeland
Control Theory for Linear Systems
Harry L. Trentelman, Anton Stoorvogel and Malo Algebraic Methods for Nonlinear Control Systems
Hautus Giuseppe Conte, Claude H. Moog and Anna M. Perdon
Functional Adaptive Control Polynomial and Rational Matrices
Simon G. Fabri and Visakan Kadirkamanathan Tadeusz Kaczorek
Positive 1D and 2D Systems Simulation-based Algorithms for Markov Decision
Tadeusz Kaczorek Processes
Hyeong Soo Chang, Michael C. Fu, Jiaqiao Hu and
Identification and Control Using Volterra Models Steven I. Marcus
Francis J. Doyle III, Ronald K. Pearson and
Bobatunde A. Ogunnaike Iterative Learning Control
Hyo-Sung Ahn, Kevin L. Moore and YangQuan Chen
Non-linear Control for Underactuated Mechanical
Systems
Isabelle Fantoni and Rogelio Lozano

Wei Ren and Randal W. Beard
Distributed
Consensus in
Multi-vehicle
Cooperative Control
Theory and Applications
123

Wei Ren, PhD Randal W. Beard, PhD
Department of Electrical and Computer Department of Electrical and Computer
Engineering Engineering
Utah State University Brigham Young University
Logan, UT 84322-4120 Provo, UT 84602
USA USA
ISBN 978-1-84800-014-8 e-ISBN 978-1-84800-015-5
DOI 10.1007/978-1-84800-015-5
Communications and Control Engineering Series ISSN 0178-5354
British Library Cataloguing in Publication Data
Ren, Wei
Distributed consensus in multi-vehicle cooperative control :
theory and applications. - (Communications and control engineering)
1. Digital control systems 2. Automatic control -
Mathematics 3. Algorithms
I. Title II. Beard, Randal W.
629.8'9'015181
ISBN-13: 9781848000148
Library of Congress Control Number: 2007934265
© 2008 Springer-Verlag London Limited
Apart from any fair dealing for the purposes of research or private study, or criticism or review, as
permitted under the Copyright, Designs and Patents Act 1988, this publication may only be reproduced,
stored or transmitted, in any form or by any means, with the prior permission in writing of the publishers,
or in the case of reprographic reproduction in accordance with the terms of licences issued by the
Copyright Licensing Agency. Enquiries concerning reproduction outside those terms should be sent to the
publishers.
The use of registered names, trademarks, etc. in this publication does not imply, even in the absence of a
specific statement, that such names are exempt from the relevant laws and regulations and therefore free
for general use.
The publisher makes no representation, express or implied, with regard to the accuracy of the information
contained in this book and cannot accept any legal responsibility or liability for any errors or omissions
that may be made.
Cover design: LE-TEX Jelonek, Schmidt & Vöckler GbR, Leipzig, Germany
Printed on acid-free paper
9 8 7 6 5 4 3 2 1
springer.com

|             | This       | work is dedicated | to      |
| ----------- | ---------- | ----------------- | ------- |
|             | My         | wife, Fei Cheng,  | and     |
| My parents, | Hongyi Ren | and Liying        | Wang    |
|             |            | -                 | Wei Ren |
|             |            | My wife,          | Andrea  |
|             |            | - Randal W.       | Beard   |

Preface
Recentadvances in miniaturizing ofcomputing,communication,sensing,and
actuation have made it feasible to envision large numbers of autonomous ve-
hicles (air, ground, and water) working cooperatively to accomplish an ob-
jective. Cooperative control of multiple vehicle systems has potential impact
in numerous civilian, homeland security, and military applications. Potential
civilian applications include monitoring forest fires, oil fields, pipelines, and
trackingwildlife. Potentialhomelandsecurity applicationsinclude borderpa-
trol and monitoring the perimeter of nuclear power plants. For the military,
applications include surveillance, reconnaissance, and battle damage assess-
ment. However, for all of these applications, communication bandwidth and
power constraints will preclude centralized command and control.
This book addresses the problem of information consensus, where a team
of vehicles must communicate with its neighbors to agree on key pieces of
information that enable them to work together in a coordinated fashion. The
problemisparticularlychallengingbecausecommunicationchannelshavelim-
ited range and experience fading and dropout. The study of information flow
and sharing among multiple vehicles in a group plays an important role in
understanding the coordinated movements of these vehicles. As a result, a
critical problem for cooperative control is to design appropriate distributed
algorithms such that the group of vehicles can reach consensus on the shared
information in the presence of limited and unreliable information exchange
and dynamically changing interaction topologies.
Our interest in distributed consensus algorithms and their applications
was motivated by our researchefforts in cooperative control of multiple vehi-
clesystemsand,inparticular,teamsofunmannedairvehicles.Airvehiclesare
constantly moving and consequently their ability to communicate is dynami-
cally changing.In addition,in currentmilitary scenariosinvolvingunmanned
air vehicles, large assets like the Predator may have two-way communica-
tion capabilities, but micro air vehicles may have only the ability to receive
commands. Therefore, we were motivated to study distributed coordination

viii Preface
problems where the communication network is noisy, limited, time-varying,
and possibly unidirectional.
Ofcourse,comingintoconsensus,oragreement,isnottheonlyissue.Each
member of the team must act to achieve the team objective using the best
available information. The interplay between communications/consensus and
control introduces significant challenges that are only beginning to be un-
derstood. In much of the current research on cooperative control, either the
consensus problem is studied in the absence of an application, or the coop-
erative control problem is studied under the assumption of full and reliable
communication.
Ourobjectiveinwritingthisresearchmonographistosummarizeourwork
incooperativecontrolusingdistributedconsensusalgorithms.Themonograph
isroughlydividedintotwoparts.Inthe firsthalfofthebook (Chapters1–7),
we describe theoreticalresults ondistributed consensus algorithms where the
dynamics of the information state evolve accordingto first- and second-order
dynamicsandaccordingtorigidbodyattitudedynamics.Theconsensusalgo-
rithms require only neighbor-to-neighborinteraction, which minimizes power
consumption,increasesstealth,andimprovesthescalabilityandrobustnessof
theteam.Thesecondhalfofthebook(Chapters8–14)describesourattempts
toapply the theoryto avarietyofapplicationsincooperativecontrol,includ-
ing formation keeping for wheeled mobile robots and spacecraft and cooper-
ative perimeter tracking and timing for a team of unmanned air vehicles. We
maintainawebsitehttp://www.engineering.usu.edu/ece/faculty/wren/
book/consensusat which can be found sample simulation and experimental
videos and other useful materials associated with the book.
The results in this book and particularly the results in Chapters 8–14
would not have been possible without the efforts and support of our col-
leaguesandstudents.Inparticular,weareindebtedtoProfessorTimMcLain
at Brigham Young University for his leadership in the area of cooperative
control for unmanned air vehicles and for countless discussions on consensus
andotherapplicationsofcooperativecontrol.We arealsoindebtedtoProfes-
sorEllaAtkins atthe UniversityofMichiganandProfessorsYangQuanChen
and Mac McKee at Utah State University for many fruitful discussions on
researchideas.We also acknowledgethe efforts of NathanSorensen, Yongcan
Cao,HaiyangChao,WilliamBourgeous,andLarryBallardatUtahStateUni-
versity,andDerek Kingston,JonathanLawton,BrettYoung, DavidCasbeer,
Ryan Holt, Derek Nelson, Blake Barber, Stephen Griffiths, David Johansen,
and Andrew Eldridge at Brigham Young University. We are thankful to our
editor Oliver Jackson for his interest in our project and his professionalism.
In addition, we acknowledge IEEE, John Wiley & Sons, Elsevier, AIAA, and
Taylor & Francis for granting us the permission to reuse materials from our
publications copyrightedby these publishers in this book. The last section of
eachchaptergivesadetailedlistofthereferencesusedinthechapter.Finally,
wegratefullyacknowledgethesupportofourresearchonconsensusalgorithms
and cooperative control by the Utah Water Research Laboratory and Com-

|     |     |     | Preface | ix  |
| --- | --- | --- | ------- | --- |
munity/UniversityResearchInitiativeaswellasNationalScienceFoundation
under Information Technology Research Grant CCR-0313056, NASA under
STTR Contract No. NNA04AA19C, Air Force Office of Scientific Research
under AwardNo. F49550-04-0209,F49620-01-1-0091,and F49620-02-C-0094,
and Defense Agency Research Projects Agency under Grant NBCH1020013.
| Utah State | University, Logan, | Utah       |           | Wei Ren  |
| ---------- | ------------------ | ---------- | --------- | -------- |
| Brigham    | Young University,  | Provo,Utah | Randal    | W. Beard |
|            |                    |            | September | 2007     |

Contents
Part I Overview of Consensus Algorithms in Cooperative Control
| 1 Overview |     | of Consensus |     | Algorithms | in  | Cooperative | Control | 3   |
| ---------- | --- | ------------ | --- | ---------- | --- | ----------- | ------- | --- |
1.1 Introduction ............................................ 3
1.2 Literature Review: Consensus Algorithms................... 6
|     | 1.2.1 | Fundamental |     | Consensus | Algorithms   | .................  |     | 7   |
| --- | ----- | ----------- | --- | --------- | ------------ | ------------------ | --- | --- |
|     | 1.2.2 | Convergence |     | Analysis  | of Consensus | Algorithms........ |     | 9   |
1.2.3 Synthesis and Extensions of Consensus Algorithms .... 15
|     | 1.2.4 | Design     | of  | Coordination                            | Strategies | via | Consensus |     |
| --- | ----- | ---------- | --- | --------------------------------------- | ---------- | --- | --------- | --- |
|     |       | Algorithms |     | ....................................... |            |     |           | 17  |
1.3 Monograph Overview .................................... 21
1.4 Notes .................................................. 22
| Part | II Consensus |     | Algorithms | for | Single-integrator |     | Dynamics |     |
| ---- | ------------ | --- | ---------- | --- | ----------------- | --- | -------- | --- |
2 Consensus Algorithms for Single-integrator Dynamics ..... 25
2.1 Fundamental Algorithms ................................. 25
2.2 Consensus Under Fixed Interaction Topologies .............. 28
|     | 2.2.1 | Consensus |     | Using a Continuous-time |     | Algorithm........ |     | 28  |
| --- | ----- | --------- | --- | ----------------------- | --- | ----------------- | --- | --- |
2.2.2 Consensus Using a Discrete-time Algorithm........... 38
2.3 ConsensusUnder Dynamically ChangingInteractionTopologies 42
|     | 2.3.1 | Consensus |     | Using a Continuous-time |     | Algorithm........ |     | 45  |
| --- | ----- | --------- | --- | ----------------------- | --- | ----------------- | --- | --- |
2.3.2 Consensus Using a Discrete-time Algorithm........... 49
|     | 2.3.3 | Simulation |     | Results | ................................ |     |     | 50  |
| --- | ----- | ---------- | --- | ------- | -------------------------------- | --- | --- | --- |
2.4 Notes .................................................. 52
3 Consensus Tracking with a Reference State................ 55
3.1 Problem Statement ...................................... 55
3.2 Constant Consensus Reference State ....................... 56
3.3 Time-varying Consensus Reference State ................... 58

xii Contents
|     | 3.3.1 | Fundamental |                                             | Consensus |           | Tracking | Algorithm.......... |         | 61  |
| --- | ----- | ----------- | ------------------------------------------- | --------- | --------- | -------- | ------------------- | ------- | --- |
|     | 3.3.2 | Consensus   |                                             | Tracking  | Algorithm |          | with Bounded        | Control |     |
|     |       | Inputs      | ........................................... |           |           |          |                     |         | 66  |
3.3.3 Information Feedback to the Consensus Reference State 68
3.4 Extension to Relative State Deviations ..................... 71
3.5 Notes .................................................. 73
| Part | III Consensus |     | Algorithms |     | for | Double-integrator |     | Dynamics |     |
| ---- | ------------- | --- | ---------- | --- | --- | ----------------- | --- | -------- | --- |
4 Consensus Algorithms for Double-integrator Dynamics .... 77
4.1 Consensus Algorithm .................................... 77
|     | 4.1.1 | Convergence                                        |     | Analysis |     | Under | Fixed Interaction     |     |     |
| --- | ----- | -------------------------------------------------- | --- | -------- | --- | ----- | --------------------- | --- | --- |
|     |       | Topologies........................................ |     |          |     |       |                       |     | 79  |
|     | 4.1.2 | Convergence                                        |     | Analysis |     | Under | Switching Interaction |     |     |
|     |       | Topologies........................................ |     |          |     |       |                       |     | 91  |
4.2 Consensus with Bounded Control Inputs ................... 96
4.3 Consensus Without Relative State Derivative Measurements ..100
4.4 Notes ..................................................103
5 Extensions to a Reference Model ..........................105
5.1 Problem Statement ......................................105
5.2 Consensus with a Reference for Information State Derivatives .106
|     | 5.2.1 | Consensus   |     | with    | Coupling    | Between | Neighbors’                 |     |     |
| --- | ----- | ----------- | --- | ------- | ----------- | ------- | -------------------------- | --- | --- |
|     |       | Information |     | State   | Derivatives |         | .......................106 |     |     |
|     | 5.2.2 | Consensus   |     | Without | Coupling    |         | Between Neighbors’         |     |     |
|     |       | Information |     | State   | Derivatives |         | .......................109 |     |     |
5.3 Consensus with References for Information States and Their
|     | Derivatives |     | .............................................111 |     |     |     |     |     |     |
| --- | ----------- | --- | ------------------------------------------------ | --- | --- | --- | --- | --- | --- |
5.3.1 Full Access to the Reference Model ..................112
5.3.2 Leader-following Strategy ..........................113
|     | 5.3.3 | General |     | Case .....................................114 |     |     |     |     |     |
| --- | ----- | ------- | --- | --------------------------------------------- | --- | --- | --- | --- | --- |
5.4 Notes ..................................................118
Part IV Consensus Algorithms for Rigid Body Attitude Dynamics
| 6 Consensus |     | Algorithms |     | for | Rigid | Body | Attitude | Dynamics | .123 |
| ----------- | --- | ---------- | --- | --- | ----- | ---- | -------- | -------- | ---- |
6.1 Problem Statement ......................................123
6.2 Attitude Consensus with Zero Final Angular Velocities.......124
| 6.3 | Attitude |     | Consensus | Without |     | Absolute | and Relative | Angular |     |
| --- | -------- | --- | --------- | ------- | --- | -------- | ------------ | ------- | --- |
Velocity Measurements...................................128
6.4 Attitude Consensus with Nonzero Final Angular Velocities....131
6.5 Simulation Results.......................................132
6.6 Notes ..................................................134

Contents xiii
7 Relative Attitude Maintenance and Reference Attitude
Tracking...................................................141
7.1 Relative Attitude Maintenance ............................141
7.1.1 Fixed Relative Attitudes with Zero Final Angular
Velocities.........................................141
7.1.2 Time-varying Relative Attitudes and Angular Velocities 142
7.2 Reference Attitude Tracking ..............................143
7.2.1 Reference Attitude Tracking with Attitudes
Represented by Euler Parameters....................143
7.2.2 Reference Attitude Tracking with Attitudes
Represented by Modified Rodriguez Parameters .......147
7.3 Simulation Results.......................................150
7.4 Notes ..................................................152
Part V Consensus-based Design Methodologies for Distributed
Multivehicle Cooperative Control
8 Consensus-based Design Methodologies for Distributed
Multivehicle Cooperative Control..........................159
8.1 Introduction ............................................159
8.2 Coupling in Cooperative Control Problems .................161
8.2.1 Objective Coupling ................................162
8.2.2 Local Coupling....................................162
8.2.3 Full Coupling .....................................162
8.2.4 Dynamic Coupling.................................163
8.3 Approach to Distributed Cooperative Control Problems with
an Optimization Objective................................163
8.3.1 Cooperation Constraints and Objectives..............164
8.3.2 Coordination Variables and Coordination Functions ...165
8.3.3 Centralized Cooperation Scheme ....................166
8.3.4 Consensus Building................................167
8.4 Approach to Distributed Cooperative Control Problems
Without an Optimization Objective........................169
8.4.1 Coordination Variable Constituted by a Group-level
Reference State ...................................170
8.4.2 Coordination Variable Constituted by Vehicle States...172
8.5 Literature Review .......................................174
8.5.1 Formation Control.................................174
8.5.2 Cooperation of Multiple UAVs ......................176
8.6 The Remainder of the Book ..............................178
8.7 Notes ..................................................178

xiv Contents
| Part         | VI Applications |     | to        | Multivehicle |     | Cooperative   |     | Control |
| ------------ | --------------- | --- | --------- | ------------ | --- | ------------- | --- | ------- |
| 9 Rendezvous |                 |     | and Axial | Alignment    |     | with Multiple |     | Wheeled |
Mobile Robots.............................................181
9.1 Experimental Platform...................................181
9.2 Experimental Implementation.............................182
9.3 Experimental Results ....................................184
9.3.1 Rendezvous.......................................185
|     | 9.3.2 | Axial   | Alignment                                     |     | ..................................188 |     |     |     |
| --- | ----- | ------- | --------------------------------------------- | --- | ------------------------------------- | --- | --- | --- |
|     | 9.3.3 | Lessons | Learned...................................188 |     |                                       |     |     |     |
9.4 Notes ..................................................189
| 10 Distributed |     |        | Formation | Control   | of                              | Multiple | Wheeled |     |
| -------------- | --- | ------ | --------- | --------- | ------------------------------- | -------- | ------- | --- |
| Mobile         |     | Robots | with      | a Virtual | Leader......................193 |          |         |     |
10.1 Distributed Formation Control Architecture ................193
10.2 Experimental Results on a Multirobot Platform .............197
10.2.1 Experimental Platform and Implementation ..........197
10.2.2 Formation Control with a Single Subgroup Leader.....199
10.2.3 Formation Control with Multiple Subgroup Leaders....200
|     | 10.2.4 | Formation |     | Control | with Dynamically |     | Changing    |               |
| --- | ------ | --------- | --- | ------- | ---------------- | --- | ----------- | ------------- |
|     |        | Subgroup  |     | Leaders | and Interrobot   |     | Interaction | Topologies201 |
10.3 Notes ..................................................202
| 11 Decentralized |     |           | Behavioral | Approach |                                   | to Wheeled |     | Mobile |
| ---------------- | --- | --------- | ---------- | -------- | --------------------------------- | ---------- | --- | ------ |
| Robot            |     | Formation | Maneuvers  |          | ..............................207 |            |     |        |
11.1 Problem Statement ......................................207
11.2 Formation Maneuvers....................................209
11.3 Formation Control.......................................211
|     | 11.3.1 | Coupled                   | Dynamics |     | Formation | Control | ...............211   |     |
| --- | ------ | ------------------------- | -------- | --- | --------- | ------- | -------------------- | --- |
|     | 11.3.2 | Coupled                   | Dynamics |     | Formation | Control | with                 |     |
|     |        | Passivity-basedInterrobot |          |     |           | Damping | .................214 |     |
11.3.3 Saturated Control .................................216
11.4 Hardware Results .......................................219
11.5 Notes ..................................................220
12 Deep Space Spacecraft Formation Flying ..................225
12.1 Problem Statement ......................................225
|     | 12.1.1 | Reference |     | Frames..................................226 |     |     |     |     |
| --- | ------ | --------- | --- | ------------------------------------------- | --- | --- | --- | --- |
12.1.2 Desired States for Each Spacecraft...................226
|     | 12.1.3 | Spacecraft |     | Dynamics...............................228 |     |     |     |     |
| --- | ------ | ---------- | --- | ------------------------------------------ | --- | --- | --- | --- |
12.2 Decentralized Architecture via the Virtual Structure Approach 228
12.2.1 Centralized Architecture ...........................228
12.2.2 Decentralized Architecture..........................229
12.3 Decentralized Formation Control Strategies .................232

Contents xv
12.3.1 Formation Control Strategies for Each Spacecraft......233
12.3.2 Formation Control Strategies for Each Virtual
Structure Instantiation.............................234
12.3.3 Convergence Analysis ..............................236
12.3.4 Discussion........................................239
12.4 Simulation Results.......................................241
12.5 Notes ..................................................245
13 Cooperative Fire Monitoring with Multiple UAVs .........247
13.1 Problem Statement ......................................247
13.2 Fire Perimeter Tracking for a Single UAV ..................250
13.3 Cooperative Team Tracking...............................251
13.3.1 Latency Minimization..............................251
13.3.2 Distributed Fire Monitoring Algorithm...............253
13.4 Simulation Results.......................................257
13.4.1 Fire Model .......................................257
13.4.2 Perimeter Tracking ................................257
13.4.3 Cooperative Tracking ..............................258
13.5 Notes ..................................................260
14 Cooperative Surveillance with Multiple UAVs .............265
14.1 Experimental Test Bed...................................265
14.2 Decentralized Cooperative Surveillance.....................268
14.2.1 Solution Methodology..............................269
14.2.2 Simulation Results ................................271
14.2.3 Flight Tests ......................................273
14.3 Notes ..................................................274
A Selected Notations and Abbreviations .....................279
B Graph Theory Notations ..................................281
C Matrix Theory Notations..................................285
D Rigid Body Attitude Dynamics ............................289
E Linear System Theory Background ........................293
F Nonlinear System Theory Background.....................295
References.....................................................299
Index..........................................................317

Part I
| Overview | of Consensus | Algorithms | in  |
| -------- | ------------ | ---------- | --- |
Cooperative Control

1
Overview of Consensus Algorithms in
Cooperative Control
This chapter overviewsconsensus algorithms in cooperativecontrol.The mo-
tivation for information consensus in cooperative control is given. A litera-
ture review on consensus algorithms is provided. Theoretical results regard-
ing consensus-seeking under both time-invariant and dynamically changing
communicationtopologiesaresummarized.Afewspecificapplicationsofcon-
sensus algorithms to multivehicle cooperative control are described. The or-
ganization of the monograph is also introduced.
1.1 Introduction
The abundance of embedded computational resources in autonomous vehi-
clesenablesenhancedoperationaleffectivenessthroughcooperativeteamwork
in civilian and military applications. Compared to autonomous vehicles that
perform solo missions, greater efficiency and operational capability can be
realized from teams of autonomous vehicles operating in a coordinated fash-
ion. Potential applications for multivehicle systems include space-based in-
terferometers; combat, surveillance, and reconnaissance systems; hazardous
material handling; and distributed reconfigurable sensor networks. To enable
these applications, various cooperative control capabilities need to be devel-
oped, including formation control, rendezvous, attitude alignment, flocking,
foraging,task and role assignment, payload transport, air traffic control, and
cooperative search.
Cooperativecontrolofmultipleautonomousvehiclesposessignificantthe-
oretical and practical challenges. First, the research objective is to develop a
systemofsubsystemsratherthanasinglesystem.Second,thecommunication
bandwidth and connectivity of the team are often limited, and the informa-
tion exchange among vehicles may be unreliable. It is also difficult to decide
what to communicate and when and with whom the communication takes
place. Third, arbitration between team goals and individual goals needs to

4 1 Overview of Consensus Algorithms in Cooperative Control
be negotiated.Fourth, the computationalresourcesof each individual vehicle
will always be limited.
Recent years have seen significant interest and research activity in the
area of coordinated and cooperative control of multiple autonomous vehicles
(e.g., [11,15,22,24,25,28,37,49,51,62–65,70,72,80,82,95,100–102,121,123,
133,142,151,153,189,200,203,225–228,234,244]).Much of this work assumes
the availability of global team knowledge, the ability to plan group actions
ina centralizedmanner,and/orperfectandunlimited communicationamong
the vehicles.
Acentralizedcoordinationschemereliesontheassumptionthateachmem-
ber of the team has the ability to communicate to a central location or share
informationviaafully connectednetwork.Asaresult,thecentralizedscheme
does not scale well with the number of vehicles. The centralized scheme may
result in a catastrophic failure of the overallsystem due to its single point of
failure. Also, real-world communication topologies are usually not fully con-
nected. In many cases, they depend on the relative positions of the vehicles
and on other environmental factors and are therefore dynamically changing
in time. In addition, wireless communication channels are subject to multi-
path, fading and drop-out. Therefore, cooperative control in the presence of
real-worldcommunication constraints becomes a significant challenge.
To understand the fundamental issues inherent in all cooperative control
problems, we offer the following, intuitively appealing, fundamental axiom:
Axiom 1.1 Shared information is a necessary condition for cooperation.
Informationnecessaryfor cooperationmaybe sharedinvariousways.For
example, relative position sensors may enable vehicles to construct state in-
formation for other vehicles [37], knowledge may be communicated among
vehicles using a wireless network [69], or joint knowledge might be pre-
programmed into the vehicles before a mission begins [16]. Under this ax-
iom, information exchange becomes a central issue in cooperative control. In
the following, we will refer to the information that is necessary for coopera-
tion as coordination information or coordination variable [139,193]. Suppose
that a particular cooperation strategy has been devised and shown to work
if the team has global access to the coordination information. Cooperation
will occur if each member in the team has access to consistent, accurate, and
completecoordinationinformation.However,inthepresenceofanunreliable,
dynamically changing communicationtopologyand dynamically changinglo-
calsituationalawarenessofeachvehicle,itisnotpossibleforallofthevehicles
to have access to consistent, accurate, or complete coordination information,
thatis,thevehiclesmayhavedifferentinstantiationsofthecoordinationvari-
able. Therefore, distributed algorithms need to be developed to ensure that
the team is converging to a consistent view of the coordination information.
As an example, consider a meet-for-dinner problem. In this problem, a
group of friends decides to meet for dinner at a particular restaurant but fail
tospecifyaprecisetimetomeet.Ontheafternoonofthedinnerappointment,

1.1 Introduction 5
all of the individuals realize that they are uncertain about the time that the
group will meet. A centralized solution to this problem is for the group to
have a conference call, to poll all individuals regarding their preferred time
for dinner, and to average the answers to arrive at a time when the group
will meet. However, this centralized solution requires that a conference line
be available and that the time of the conference call be known to the group.
Because whatever algorithm was used to convey the time of the conference
call to the group could also have been used to convey the time to meet for
dinner, the central problem remains.
The coordinationvariablein this example is the time when the groupwill
meetfordinner.Theparticulartimeisnotwhatisimportant,butratherthat
each individual in the group has a consistent understanding of that informa-
tion. A distributed solution to the problem would be for each individual to
call, one at a time, a subset of the group. Given his or her current estimate
ofthe meeting time, i.e., his orher instantiationofthe coordinationvariable,
the individual might update his or her estimate of the meeting time to be a
weighted average of his or her current meeting time and that of the person
with whom he or she is conversing. The question is to determine under what
conditionsthisstrategywillenabletheentireteamtoconvergetoaconsistent
meeting time.
Toillustratethemeet-for-dinnerexample,supposethatthereare10agents
who communicate with exactly one other individual, chosen randomly from
thegroup,forarandomlengthoftime.Afterthecommunicationhasexpired,
theprocessisrepeated.Figure1.1showstheevolutionofthedinnertimeswith
theabovementioneddistributedapproach,wheretheinitialstateisuniformly
assigned. Note that the entire team converges to a consistent meeting time
under switching communication topologies.
For cooperative control strategies to be effective, a team of vehicles must
be able to respondto unanticipated situations or changes in the environment
thataresensedasacooperativetaskiscarriedout.Forsomeapplications(e.g.,
cooperative observation on the same phenomenon or target), as the environ-
ment changes, the vehicles in the team must agree as to what changes took
place. For some other applications (e.g., accurate formation geometry main-
tenance), the vehicles need to maintain relative states between each other or
achieve different group behaviors. A direct consequence of Axiom 1.1 is that
cooperationrequiresthatthe groupofvehicles agreesonthe instantiations of
the coordinationvariableorthatdifferences betweenthe instantiationsofthe
coordination variable converge to prespecified values. A critical problem for
cooperative control is to determine algorithms so that a team of vehicles can
agreeonthe instantiationsofthe coordinationvariableorthatdifferencesbe-
tween the instantiations of the coordination variable converge to prespecified
values in the presence of (i) imperfect sensors, (ii) communication dropout,
(iii) sparse communication topologies, and (iv) noisy and unreliable commu-
nication links.

6 1 Overview of Consensus Algorithms in Cooperative Control
Meet−for−dinner example
7
6.8
6.6
6.4
6.2
6
5.8
5.6
5.4
5.2
5
0 5 10 15 20
Time (s)
emit
renniD
Fig. 1.1. Discrete-time meet-for-dinnersimulation
1.2 Literature Review: Consensus Algorithms
When multiple vehicles agree on the value of a variable of interest, they are
said to have reached consensus. Information consensus guarantees that vehi-
cles sharing information over a network topology have a consistent view of
information that is critical to the coordination task. To achieve consensus,
there must be a shared variable of interest, called the information state, as
wellasappropriatealgorithmicmethodsfornegotiatingtoreachconsensuson
the value of that variable, called the consensus algorithms. The information
staterepresentsaninstantiationofthecoordinationvariablefortheteam.Ex-
amples include a local representation of the center and shape of a formation,
the rendezvoustime,the lengthofaperimeterbeing monitored,the direction
of motion for a multivehicle swarm, and the probability that a military tar-
gethasbeendestroyed.Bynecessity,consensusalgorithmsaredesignedtobe
distributed,assumingonlyneighbor-to-neighborinteractionbetweenvehicles.
Vehicles update the value of their information states based on the informa-
tionstates of their neighbors.The goalis to designanupdate law so thatthe
information states of all of the vehicles in the network convergeto a common
value.
Consensus algorithms have a historical perspective in [32,41,55,81,
131,236], to name a few, and have recently been studied extensively in

|     |     |     | 1.2 Literature | Review: Consensus | Algorithms |     | 7   |
| --- | --- | --- | -------------- | ----------------- | ---------- | --- | --- |
the context of cooperative control of multiple autonomous vehicles [69,97,
126,145,158,190]. Some results in consensus algorithms can be understood
in the context of connective stability [215]. Consensus algorithms have ap-
plications in rendezvous [26,58,124,125,135,216,220,221], formation con-
trol[69,115,118,127,134,165,174],flocking [50,59,120,147,155,169,232,238],
attitudealignment[117,176,179,188],perimetermonitoring[38],decentralized
task assignment [6,143],and sensor networks [76,154,159,223,260].
| 1.2.1 Fundamental |     | Consensus | Algorithms |     |     |     |     |
| ----------------- | --- | --------- | ---------- | --- | --- | --- | --- |
The basic idea of a consensus algorithmis to impose similar dynamics onthe
information states of each vehicle. If the communication network among ve-
hicles allows continuous communication or if the communication bandwidth
is sufficiently large,then the informationstate update ofeachvehicle is mod-
eled using a differential equation. On the other hand, if the communication
data arrive in discrete packets, then the information state update is modeled
using a difference equation. This section overviews fundamental consensus
algorithms in which a scalar information state is updated by each vehicle us-
ing, respectively,a first-orderdifferential equationanda first-orderdifference
equation.
Suppose that there are n vehicles in the team. The team’s communica-
(cid:2)
tion topology can be represented by directed graph G = (V ,E ), where
|              |     |          |         |          | n n          | n           |     |
| ------------ | --- | -------- | ------- | -------- | ------------ | ----------- | --- |
| V ={1,...,n} |     |          | E       | ⊆V ×V    |              |             |     |
| n            | is  | the node | set and | n n n is | the edge set | (see Appen- |     |
dix B forgraphtheorynotations).For example,Fig.1.2showsthree different
communication topologies for three vehicles. The communication topology
may be time varying due to vehicle motion or communication dropouts. For
example, communication dropouts might occur when an unmanned air vehi-
cle (UAV) banks away from its neighbor or flies through an urban canyon.
The most common continuous-time consensus algorithm [69,97,126,158,190]
is given by
(cid:2)n
|     | x˙ (t)=− |     | a (t)[x (t)−x | (t)], i=1,...,n, |     |     | (1.1) |
| --- | -------- | --- | ------------- | ---------------- | --- | --- | ----- |
|     | i        |     | ij i          | j                |     |     |       |
j=1
A ∈ Rn×n
where a (t) is the (i,j) entry of adjacency matrix associated
| ij  |     |     |     |     | n   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
with G at time t and x is the information state of the ith vehicle. Setting
| n   |     | i   |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
a ij =0denotesthefactthatvehicleicannotreceiveinformationfromvehicle
j. A consequence of (1.1) is that the information state x (t) of vehicle i is
i
driventowardtheinformationstatesofitsneighbors.Thecriticalconvergence
question is, when do the information states of all of the vehicles converge to
| a common | value? |     |     |     |     |     |     |
| -------- | ------ | --- | --- | --- | --- | --- | --- |
Although (1.1) ensures that the information states of the team agree, it
doesnotdictateaspecifiedcommonvalue.Forexample,consideracooperative
rendezvousproblemwhereateamofvehiclesistaskedtoarrivesimultaneously

8 1 Overview of Consensus Algorithms in Cooperative Control
(cid:6)(cid:2)(cid:7)(cid:3)
1
(cid:8)(cid:4)(cid:9)(cid:5)(cid:2)(cid:2) (cid:2)(cid:6)(cid:3)(cid:7)
2
(cid:4)(cid:8)(cid:5)(cid:9)(cid:2)(cid:2) (cid:6)(cid:2)(cid:7)(cid:3)
3
(cid:8)(cid:4)(cid:9)(cid:5) (cid:6)(cid:2)(cid:7)(cid:3)
1
(cid:8)(cid:4)(cid:9)(cid:5)(cid:2)(cid:2) (cid:6)(cid:2)(cid:7)(cid:3)
2
(cid:8)(cid:4)(cid:9)(cid:5)(cid:4)(cid:4) (cid:3)(cid:3)(cid:2)(cid:6)(cid:3)(cid:7)
3
(cid:4)(cid:8)(cid:5)(cid:9) (cid:2)(cid:6)(cid:3)(cid:7)
1
(cid:4)(cid:8)(cid:5)(cid:9)(cid:2)(cid:2) (cid:6)(cid:2)(cid:7)(cid:3)
2
(cid:8)(cid:4)(cid:9)(cid:5)(cid:2)(cid:2) (cid:5)(cid:5)(cid:6)(cid:2)(cid:7)(cid:3)
3
(cid:8)(cid:4)(cid:9)(cid:5)
(a) (b) (c)
Fig. 1.2. Three different communication topologies for three vehicles. Subplot (c)
is strongly connected because there is a directed path between every pair of nodes.
However, (a) and (b) are not strongly connected.
at a specified location known to all vehicles. Because the rendezvous time is
not given and may need to be adjusted in response to pop-up threats or
other environmental disturbances, the team needs to reach consensus on the
rendezvous time. To do this, each vehicle first creates an information state
x that represents the ith vehicle’s understanding of the rendezvous time. To
i
initialize its information state, each vehicle determines a time at which it is
able to rendezvous with the team and sets x (0) to this value. Each team
i
member then communicates with its neighbors and negotiates a team arrival
timeusingconsensusalgorithm(1.1).Onboardcontrollersthenmaneuvereach
vehicle to rendezvous at the negotiated arrival time. When environmental
conditions change, individual vehicles may reset their information state and
thus cause the negotiation process to resume.
Note that (1.1) does not permit specifying a desired information state.
We show in Section 1.2.2 that if the communication topology is fixed and
the gains a are time invariant, then the common asymptotic value is a lin-
ij
ear combination of the initial information states. In general, it is possible to
guarantee only that the common value is a convex combination of the initial
information states.
Consensus algorithm (1.1) is written in matrix form as
x˙(t)=−L (t)x(t),
n
where x = [x ,...,x ]T is the information state and L (t)= [(cid:2) (t)] ∈Rn×n
1 n n ij
isthenonsymmetricalLaplacianmatrixassociatedwithG (seeAppendixB).
n
Consensus is achieved or reached by a team of vehicles if, for all x (0) and all
i
i,j =1,...,n, |x (t)−x (t)|→0, as t→∞.
i j
When communication among vehicles occurs at discrete instants, the in-
formation state is updated using a difference equation. The most common
discrete-time consensus algorithm has the form [97,145,190,236]
(cid:2)n
x [k+1]= d [k]x [k], i=1,...,n, (1.2)
i ij j
j=1
where k denotes a communication event; d [k] is the (i,j) entry of a row-
ij
stochastic matrix D = [d ] ∈ Rn×n (see Appendix C for matrix theory no-
ij
tations) at the discrete-time index k with the additional assumption that

|     |     |     |     | 1.2 Literature | Review: | Consensus | Algorithms |     | 9   |
| --- | --- | --- | --- | -------------- | ------- | --------- | ---------- | --- | --- |
(cid:6)=
d [k] > 0 for all i = 1,...,n and d [k] > 0 for all i j if information flows
| ii  |     |     |     |     | ij  |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
from vehicle j to vehicle i and d [k] = 0 otherwise. Intuitively, the informa-
ij
tion state of each vehicle is updated as the weighted average of its current
state and the current states of its neighbors. Note that a vehicle maintains
its current information state if it does not exchange information with other
vehicles at that instant. Discrete-time consensus algorithm(1.2) is written in
| matrix | form | as  |     |     |     |     |     |     |     |
| ------ | ---- | --- | --- | --- | --- | --- | --- | --- | --- |
x[k+1]=D[k]x[k].
Similartothe continuous-timecase,consensusisachieved orreachedif,forall
|             |             |          |           |                    | |x [k]−x     | [k]|→0,       | →∞. |     |     |
| ----------- | ----------- | -------- | --------- | ------------------ | ------------ | ------------- | --- | --- | --- |
| x i [0]     | and for     | all i,j  | =1,...,n, |                    | i j          | as k          |     |     |     |
| 1.2.2       | Convergence |          | Analysis  |                    | of Consensus | Algorithms    |     |     |     |
| Convergence |             | Analysis |           | for Time-invariant |              | Communication |     |     |     |
Topologies
In this section, we investigate conditions under which the information states
of consensus algorithm (1.1) converge when the communication topology is
time invariant and the gains a are constant, that is, the nonsymmetrical
ij
Laplacian matrix L is constant. As noted in Appendix B, zero is always
n
|     |     |     | −L  |     |     | −L  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
an eigenvalue of , and all nonzero eigenvalues of have negative real
|     |     |     | n   |     |     |     | n   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
parts. As also noted in Appendix B, the column vector 1 of ones is an
n
|     |     |     |     |     |     |     |     | span{1 | }   |
| --- | --- | --- | --- | --- | --- | --- | --- | ------ | --- |
eigenvector associatedwith the zero eigenvalue, which implies that n
is contained in the kernel of L . It follows that if zero is a simple eigenvalue
n
of L , then x(t) → x¯1 , where x¯ is a scalar constant, which implies that
| n        |      |     | n    |      |             |            |             |          |     |
| -------- | ---- | --- | ---- | ---- | ----------- | ---------- | ----------- | -------- | --- |
| |x (t)−x | (t)| | →0, |      | → ∞, |             |            |             |          |     |
| i        | j    |     | as t |      | for all i,j | = 1,...,n. | Convergence | analysis |     |
therefore focuses on conditions to ensure that zero is a simple eigenvalue of
L . Otherwise the kernel of L includes elements that are not in span{1 },
| n        |      |           |     | n                  |     |     |     |     | n   |
| -------- | ---- | --------- | --- | ------------------ | --- | --- | --- | --- | --- |
| in which | case | consensus |     | is not guaranteed. |     |     |     |     |     |
If the directed graph of L is strongly connected (see Appendix B), then
n
zeroisasimpleeigenvalueofL
|     |     |     |     | n   | [69,Proposition3].However,thisconditionis |     |     |     |     |
| --- | --- | --- | --- | --- | ----------------------------------------- | --- | --- | --- | --- |
not necessary. For example, consider the nonsymmetrical Laplacian matrices
|      | ⎡   |         | ⎤   |      | ⎡         | ⎤      | ⎡   |         | ⎤   |
| ---- | --- | ------- | --- | ---- | --------- | ------ | --- | ------- | --- |
|      |     | 1 −1    | 0   |      | 1 −1      | 0      | 1   | −1 0    |     |
| L    | ⎣   | 1.5−1.5 | ⎦   | L    | ⎣ 1.5−1.5 | ⎦ L    | ⎣   | 1.5−1.5 | ⎦   |
| 3(1) | =   | 0       | ,   | 3(2) | = 0       | , 3(3) | = 0 |         | ,   |
|      |     | 0 0     | 0   |      | 0 −2      | 2      | −2  | 0 2     |     |
(1.3)
of the directed graphs shown in Fig. 1.2. Although all of the nonsymmetrical
Laplacian matrices in (1.3) have simple zero eigenvalues, Figs. 1.2a and 1.2b
arenotstronglyconnected.Thecommonfeatureisthatthedirectedgraphsof
| L ,L |      | ,andL | allhavedirectedspanningtrees.Asshownin[115,127, |     |     |     |     |     |     |
| ---- | ---- | ----- | ----------------------------------------------- | --- | --- | --- | --- | --- | --- |
| 3(1) | 3(2) |       | 3(3)                                            |     |     |     |     |     |     |
193,255],zeroisasimpleeigenvalueofL ifandonlyiftheassociateddirected
n
graph has a directed spanning tree. This result implies that (1.1) achieves
consensus if and only if the directed communication topology has a directed
spanning tree or the undirected communication topology is connected.

10 1 Overview of Consensus Algorithms in Cooperative Control
For discrete-time consensus algorithm(1.2), TheoremC.1 implies that all
eigenvalues of D are either in the open unit disk or at1. As shownin [190],if
1isasimpleeigenvalueofD,thenlim k→∞ Dk →1 n νT,ask→∞,whereν is
ann×1nonnegativelefteigenvectorofDassociatedwiththeeigenvalue1and
satisfies νT1 = 1. As a result, x[k]= Dkx[0]→1 νTx[0], as k →∞, which
n n
impliesthat,foralli,x [k]→νTx[0],ask→∞,andthus|x [k]−x [k]|→0,
i i j
as k →∞.
TheoremC.5impliesthat1=ρ(A)isasimpleeigenvalueofrow-stochastic
matrix A if directed graph Γ(A) is strongly connected, or equivalently, if A
is irreducible. As in the continuous-time case, this condition is sufficient but
notnecessary.Furthermore,forrow-stochasticmatrixD,Γ(D)hasadirected
spanning tree if and only if λ=1 is a simple eigenvalue of D and is the only
eigenvalueofmodulusone[190].Asaresult,underatime-invariantcommuni-
cation topology with constant gains a , (1.2) achieves consensus if and only
ij
ifeither the directedcommunicationtopologyhas adirectedspanningtree or
the undirected communication topology is connected [190].
Equilibrium State under a Time-invariant Communication
Topology
We now investigate the consensus equilibrium for the special case in which
the communication topology is time invariant and the gains a are constant
ij
(i.e.,constantL ).Whenthedirectedcommunicationtopologyhasadirected
n
spanning tree, it follows from [193] that lim t→∞e−Lnt → 1
n
νT, where ν =
[ν
1
,...,ν
n
]T is an n×1 nonnegative left(cid:7)eigenvector of L
n
associated with
the simple zero eigenvalue and satisfies n ν = 1. As a result, for each
(cid:7) j=1 j
i=1,...,n,x (t)→ n ν x (0),ast→∞,thatis,theequilibriumstateis
i j=1 j j
a weighted average of the initial information states in the network. However,
someofthecomponentsofνmaybezero,implyingthattheinformationstates
of some vehicles do not contribute to the equilibrium.
To illustrate this phenomenon, consider the nonsymmetrical Laplacian
matrices given in (1.3). It can be verified that, for L , x(t) → x (0)1 ,
3(1) 3 3
for L , x(t) → [0.5714x (0) + 0.4286x (0)]1 , and, for L , x(t) →
3(2) 2 3 3 3(3)
[0.4615x (0)+0.3077x (0)+0.2308x (0)]1 . Note that with L , the ini-
1 2 3 3 3(1)
tial information states of vehicles 1 and 2 do not affect the equilibrium.
With L , the initial information state of vehicle 1 does not affect the equi-
3(2)
librium. However, with L , all of the vehicle’s initial information states
3(3)
affect the equilibrium. Observing the directed graphs shown in Fig. 1.2, we
can see that, for L , vehicle 3 is the only vehicle that can pass information
3(1)
to all of the other vehicles in the team, either directly or indirectly. Simi-
larly,forL ,bothvehicles2and3canpassinformationtothe entire team,
3(2)
whereas, for L , all vehicles can pass information to the entire team.
3(3)
Next, define the nonnegative matrix M = max (cid:2) I −L . Because ν is
i ii n n
the nonnegativelefteigenvectorofL correspondingtothe zeroeigenvalue,ν
n
is also the nonnegative left eigenvector of M corresponding to the eigenvalue

1.2 Literature Review: Consensus Algorithms 11
max (cid:2) of M. From Theorem C.1, it follows that ρ(M) = max (cid:2) . If the
i ii i ii
directed communication graphis strongly connected, so is the directed graph
of M, which also implies that M is irreducible (see Appendix C). By Theo-
rem C.5, if M is irreducible, then ν is positive. Therefore, when the directed
communication topology is strongly connected, all of the initial information
states contribute to the consensus equilibrium because ν (cid:6)= 0 for all i. Fur-
i
thermore, if ν = 1/n for all i, then the consensus equilibrium is the average
i
of the initial information states, a condition called average consensus [158].
If the directed communication topology is both strongly connected and bal-
anced, then 1 is a left eigenvector of L associated with the simple zero
n n
eigenvalue. Therefore, as shown in [158], averageconsensus is achievedif and
only if the directed communication topology is both strongly connected and
balanced. It can be shown that, in the case of undirected communication,
average consensus is achieved if and only if the topology is connected [158].
To illustrate these ideas, Fig. 1.3 shows time histories of the information
states for two different updates strategies.Figure 1.3a shows the information
states for x˙ = −L x, where L is given in (1.3). Because the directed
3(3) 3(3)
graphofL is stronglyconnected,allofthe vehicle’sinitialconditionscon-
3(3)
tribute to the equilibrium state. However, the equilibrium is not an average
consensus because the directed graph is not balanced. In contrast, Fig. 1.3b
shows the time histories of the information states for x˙ = −diag(w)L x,
3(3)
where w is the positive column left eigenvector of L corresponding to
3(3)
the zero eigenvalue satisfying wT1 = 1 and diag(w) is the diagonal matrix
3
wh(cid:8)ose diagonal(cid:9)entries are given by w. It can be shown that directed graph
Γ diag(w)L isstronglyconnectedandbalanced,resultinginaveragecon-
3(3)
sensus.
In contrast, when the directed communication topology has a directed
spanning tree, the consensus equilibrium is equal to the weighted average
of the initial conditions of those vehicles that have a directed path to all
other vehicles [193]. Requiring a directed spanning tree is less stringent than
requiringastronglyconnectedandbalancedgraph.However,asshownabove,
the consensus equilibrium is a function only of the initial information states
of those vehicles that have a directed path to all other vehicles.
Convergence Analysis for Dynamic Communication Topologies
Communication topologies are often dynamic. For example, communication
links among vehicles might be unreliable due to multipath effects and other
disturbances. Alternatively, if information is exchanged by means of line-of-
sight sensors, the neighbors visible to a vehicle might change over time, e.g.,
when a UAV banks away from its neighbor. Therefore, in this section, we
investigate conditions under which consensus algorithms convergeunder ran-
dom switching of the communication topologies.
One approach to analyzing switching topologies is to use algebraic graph
theory, which associates each graph topology with an algebraic structure of

| 12  | 1 Overview | of Consensus |     | Algorithms | in Cooperative | Control |     |
| --- | ---------- | ------------ | --- | ---------- | -------------- | ------- | --- |

0.8
x
| setats noitamrofnI |     |     |     |     |     | 1   |     |
| ------------------ | --- | --- | --- | --- | --- | --- | --- |
x
|     | 0.6 |     |     |     |     | 2   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
x
3
0.4
≠ average( 0.2, 0.4, 0.6)
|     | 0.2   |     |     |     |     |     |     |
| --- | ----- | --- | --- | --- | --- | --- | --- |
|     | 0     | 2   |     | 4   | 6   | 8   | 10  |
(a)  Time (s)
|                    | 0.8 |     |     |     |     |     |     |
| ------------------ | --- | --- | --- | --- | --- | --- | --- |
| setats noitamrofnI |     |     |     |     |     | x   |     |
1
x
|     | 0.6 |     |     |     |     | 2   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
x
3
0.4
= average( 0.2, 0.4, 0.6)
|     | 0.2   |     |     |     |     |     |     |
| --- | ----- | --- | --- | --- | --- | --- | --- |
|     | 0     | 2   |     | 4   | 6   | 8   | 10  |
(b)  Time (s)
x˙
Fig. 1.3. Consensus for three vehicles. Subplots (a) and (b) correspond to =
| −L   | x   | x˙ −diag(w)L |      | x,            |         | 0.4            |        |
| ---- | --- | ------------ | ---- | ------------- | ------- | -------------- | ------ |
| 3(3) | and | =            | 3(3) | respectively. | Because | is the average | of the |
initial states (0.2,0.4,0.6), average consensus is achieved in (b),where the directed
graph is strongly connected and balanced, butnot in (a), wherethedirected graph
| is only | strongly | connected. |     |     |     |     |     |
| ------- | -------- | ---------- | --- | --- | --- | --- | --- |
corresponding matrices. Because (1.1) is linear, its solution can be written
as x(t) = Φ(t,0)x(0), where Φ(t,0) is the transition matrix corresponding
−L
to n (t). Φ(t,0) is a row-stochastic matrix with positive diagonal entries
for all t ≥ 0 [192]. Consensus is achieved if lim t→∞Φ(t,0) → 1 μT, where
n
μ is a column vector. It is typical to assume that the communication topol-
ogy is piecewise constant over finite lengths of time, called dwell times, and
that dwell times are bounded below by a positive constant [97]. In this case,
| A   |     | L   |     |     |     |     | −t  |
| --- | --- | --- | --- | --- | --- | --- | --- |
n (t)andhence n (t)arepiecewiseconstantwithdwelltimesτ j =t j+1 j ,
where t ,t ,... are the switching instants, and thus consensus is achieved if
|     | 1 2 |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
lim j→∞e−Ln(tj)τje−Ln(tj−1)τj−1···e−Ln(t0)τ0 = 1 μT. Because e−Ln(tj)(t−tj)
n
is a row-stochastic matrix, convergence analysis involves the study of infinite
| products | of stochastic |     | matrices. |     |     |     |     |
| -------- | ------------- | --- | --------- | --- | --- | --- | --- |
A classical result given in [253] (see also [192]) demonstrates the con-
vergence property of infinite products of SIA matrices (see Appendix C).
Specifically, let S = {S ,S ,...,S } be a finite set of SIA matrices with
|     |     |     | 1 2 | k   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
···S
| the property |     | that every | finite | product | S S     | is SIA. | Then, for |
| ------------ | --- | ---------- | ------ | ------- | ------- | ------- | --------- |
|              |     |            |        |         | ij ij−1 | i1      |           |
each infinite sequence S ,S ,... there exists a column vector ν such that
|     |     |     | i1 i2 |     |     |     |     |
| --- | --- | --- | ----- | --- | --- | --- | --- |

|     |     | 1.2 | Literature | Review: | Consensus |     | Algorithms | 13  |
| --- | --- | --- | ---------- | ------- | --------- | --- | ---------- | --- |
···S
| lim j→∞S | S   | = 1νT. | Because | the | number | of  | potential communi- |     |
| -------- | --- | ------ | ------- | --- | ------ | --- | ------------------ | --- |
ij ij−1 i1
(cid:2)
cation topologies is finite, the set of matrices {S = e−Ln(tj)(tj+1−tj)}∞ is
|     |     |     |     |     | j   |     |     | j=1 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
−t
finite if the allowable dwell times τ j = t j+1 j are drawn from a finite set.
Reference [97]showsthat these matrices are SIA and uses this result to show
that the heading angles of a swarm of vehicles achieve consensus using the
nearestneighborrulesof[239].Thisisaspecialcaseofdiscrete-timeconsensus
algorithm (1.2), if there exists an infinite sequence of contiguous, uniformly
bounded time intervals, having one of a finite number of different lengths,
with the property that across each interval, the union (see Appendix B) of
the undirected communication topologies is connected. See [78,126,158,208]
for extensions.
Consider,on the other hand, the more realistic assumption that the dwell
times are drawn from an infinite but bounded set or A (t) is piecewise
n
continuous1 and its nonzero and hence positive entries are uniformly lower
and upper bounded. In this case, let S = {S ,S ,...} be an infinite set
1 2
×
of n n SIA matrices, let N t be the number of different types (see Ap-
pendix B) of all of(cid:7)the n×n SIA matrices, and define the matrix function
| χ(P)=1−min |       | min(p | ,p  | ).Then,lim | j→∞S | S   | ···S =1νT | if  |
| ---------- | ----- | ----- | --- | ---------- | ---- | --- | --------- | --- |
|            | i1,i2 |       | i1j | i2j        |      | ij  | ij−1 i1   |     |
j
|     |     | ∈   |     |     |     | (cid:2) | ···S |     |
| --- | --- | --- | --- | --- | --- | ------- | ---- | --- |
there exists a constant d [0,1) such that, for every W = S S ,
|     |     |     |     |     |     |     | k1 k2 | kNt+1 |
| --- | --- | --- | --- | --- | --- | --- | ----- | ----- |
it follows that χ(W) ≤ d [253]. It can be shown that this condition is sat-
isfied if there exists an infinite sequence of contiguous, uniformly bounded
time intervals, with the property that across each interval, the union of the
directed communication topologies has a directed spanning tree [190,192].
Reference [168] considers a similar problem by studying the products of row-
stochastic matrices with a lower triangular structure. In addition, a lower
bound on the convergence rate of consensus algorithm (1.2) under directed
| switching | communication | topologies   |     | is derived | in [36]. |     |     |     |
| --------- | ------------- | ------------ | --- | ---------- | -------- | --- | --- | --- |
| Lyapunov  | Analysis      | of Consensus |     | Algorithms |          |     |     |     |
Nonlinear analysis can also be used to study consensus algorithms [71,
128,145]. For discrete-time consensus algorithm (1.2), a set-valued Lya-
punov function V is defined as V(x ,...,x ) = (conv{x ,...,x })n, where
|     |     |     |     | 1   | n   |     | 1 n |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
(cid:2)
conv{x ,...,x } denotes the convex hull of {x ,...,x }, and Xn = X ×
| 1   | n   |     |     |     | 1   | n   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
···×X. It is shown in [145] that V(t ) ⊆ V(t ) for all t ≥ t , and that
|                                       |     |     |     | 2   | 1              |     | 2 1 |     |
| ------------------------------------- | --- | --- | --- | --- | -------------- | --- | --- | --- |
| x(t)approachesanelementofthesetspan{1 |     |     |     |     | },whichimplies |     |     |     |
thatconsensus
n
is reached. Using set-valued Lyapunov theory, [145] shows that discrete-time
consensus algorithm(1.2) is uniformly globally attractive with respect to the
collection of equilibrium solutions span{1 } if and only if there exists K ≥0
n
such that the union of the directed communication topologies has a directed
spanning tree across each interval of length Kh, where h is the sample time.
| 1            | L (t) |              |             |     |     |     |     |     |
| ------------ | ----- | ------------ | ----------- | --- | --- | --- | --- | --- |
| Accordingly, | n     | is piecewise | continuous. |     |     |     |     |     |

| 14  | 1 Overview | of  | Consensus | Algorithms | in  | Cooperative | Control |
| --- | ---------- | --- | --------- | ---------- | --- | ----------- | ------- |
For continuous-time consensus algorithm (1.1), [144] considers the Lya-
punov candidate V(x) = max{x ,...,x } − min{x ,...,x }. It is shown
|     |     |     |     | 1      | n   |     | 1 n |
| --- | --- | --- | --- | ------ | --- | --- | --- |
|     |     |     |     | span{1 | }   |     |     |
in [144] that the equilibrium set n is uniformly exponentially sta-
ble if there is an interval length T >0 such that, for all t, the directed graph
(cid:10)
| − t+T | L       |     |            |          |       |     |     |
| ----- | ------- | --- | ---------- | -------- | ----- | --- | --- |
| of    | n (s)ds | has | a directed | spanning | tree. |     |     |
t
Asanalternativeanalyticmethod,[219,246,247]appliesnonlinearcontrac-
tion theory to synchronization and schooling applications, which are related
to information consensus. In particular, (1.1) is analyzed under undirected
switching communication topologies, and a convergence result identical to
the result given in [97] is derived. In addition, [13] uses passivity as a design
tool for consensus algorithms over an undirected communication topology.
Information consensus is also studied from a stochastic point of view
in[87,88,256],whichconsiderarandomnetwork,wheretheexistenceofanin-
formationchannelbetween a pair ofvehicles at eachtime is probabilistic and
independentofotherchannels,resultinginatime-varyingundirectedcommu-
Rn×n
nication topology. For example, adjacency matrix A = [a ] ∈ for an
|     |     |     |     |     |     |     | n ij |
| --- | --- | --- | --- | --- | --- | --- | ---- |
undirected random graphis defined as a (p)=0, a (p)=1 with probability
|     |     |     |     |     | ii  |          | ij  |
| --- | --- | --- | --- | --- | --- | -------- | --- |
|     |     |     |     | 1−p |     | (cid:6)= |     |
p, and a = 0 with probability for all i j. In [88], consensus over an
ij
undirected randomnetwork is addressedby notions from stochastic stability.
| Communication |     | Delays |     | and Asynchronous |     | Consensus |     |
| ------------- | --- | ------ | --- | ---------------- | --- | --------- | --- |
Wheninformationisexchangedamongvehiclesthroughcommunication,time
delays from both message transmission and processing after receipt must be
considered.Letσ denotethe timedelayforinformationcommunicatedfrom
ij
vehicle j to reach vehicle i. In this case, (1.1) is modified as
(cid:2)n
|     |     | =−   |     | (t−σ         | )−x | (t−σ |        |
| --- | --- | ---- | --- | ------------ | --- | ---- | ------ |
|     |     | x˙ i |     | a ij (t)[x i | ij  | j    | ij )]. |
j=1
In the simplest case, where σ =σ and the communication topology is time-
ij
invariant, undirected, and connected, average consensus is achieved if and
| onlyif0≤σ |     | π   | [158],whereL |     |                                  |     |     |
| --------- | --- | --- | ------------ | --- | -------------------------------- | --- | --- |
|           | <   |     |              |     | n istheLaplacianmatrixoftheundi- |     |     |
2λmax(Ln)
rectedcommunicationtopology andλ (·) denotes the largesteigenvalue of
max
| a matrix. | See [30,119]for |     | extensions. |     |     |     |     |
| --------- | --------------- | --- | ----------- | --- | --- | --- | --- |
Alternatively, consider the case in which the time delay affects only the
information state that is being transmitted so that (1.1) is modified as
(cid:2)n
|     |     |     | =−  |            | (t)−x | (t−σ |        |
| --- | --- | --- | --- | ---------- | ----- | ---- | ------ |
|     |     | x˙  | i   | a ij (t)[x | i     | j    | ij )]. |
j=1
Whenσ =σ andthecommunicationtopologyisdirectedandswitching,the
ij
consensus result for switching topologies remains valid for an arbitrary time
delay σ [144].

|     |     | 1.2 | Literature | Review: | Consensus Algorithms | 15  |
| --- | --- | --- | ---------- | ------- | -------------------- | --- |
Fordiscrete-timeconsensusalgorithm(1.2),itisshownin[230]thatifcon-
sensus is reachedunder a time-invariantundirected communicationtopology,
thenthepresenceofcommunicationdelaysdoesnotaffectconsensus.Inaddi-
tion, the result in [145]is extended to take into accountbounded time delays
in [12]. Furthermore, [258] shows sufficient conditions for consensus under
dynamically changing communication topologies and bounded time-varying
| communication | delays. |     |     |     |     |     |
| ------------- | ------- | --- | --- | --- | --- | --- |
Moregenerally,inanasynchronousconsensusframework[31,35,67,68,140],
eachvehicleexchangesinformationasynchronouslyandupdatesitsstatewith
possibly outdated informationfrom its localneighbors.As a result, heteroge-
nous vehicles, time-varying communication delays, and packet dropout must
be taken into account in the same asynchronous consensus framework. Ref-
erence [68] categorizesseveralconsensus results in the literature according to
synchronism, connectivity, and direction of information flow.
| 1.2.3 Synthesis     | and | Extensions | of  | Consensus | Algorithms |     |
| ------------------- | --- | ---------- | --- | --------- | ---------- | --- |
| Consensus Synthesis |     |            |     |           |            |     |
In some applications, consensus algorithms must satisfy given requirements
or optimize performance criteria. For example, when a UAV or micro air
vehicle (MAV) swarm consists of hundreds or thousands of vehicles, it might
bedesirabletosolvethefastestdistributedlinearaveraging(FDLA)problem,
]∈Rn×nbesuchthatw
| whichisdefinedasfollows[259].LetW |     |     |     | =[w |     | =0if |
| --------------------------------- | --- | --- | --- | --- | --- | ---- |
|                                   |     |     |     | ij  |     | ij   |
informationisnotexchangedbetweenvehicleiandvehiclej.Givenx[k+1]=
| Wx[k], find W | to minimize |                   |         |                       |          |     |
| ------------- | ----------- | ----------------- | ------- | --------------------- | -------- | --- |
|               |             |                   |         | (cid:11)              | (cid:12) |     |
|               |             |                   |         | (cid:9)x[k]−x¯(cid:9) | 1/k      |     |
|               | r           | (W)=              | sup lim |                       | ,        |     |
|               | asym        | x[0](cid:5)=x¯k→∞ |         | (cid:9)x[0]−x¯(cid:9) |          |     |
subject to the condition that lim t→∞Wk = 11 1T , where x¯ = 11 1T x[0].
|     |     |     |     | n   | n n n | n n |
| --- | --- | --- | --- | --- | ----- | --- |
In otherwords,the FDLA problemis to find the weightmatrixW thatguar-
antees the fastest convergence to the average consensus value. In contrast to
discrete-time consensus algorithm (1.2), weights w can be negative [259].
ij
With the additional constraint w ij = w ji , the FDLA problem reduces to a
numerically solvable semidefinite program[259]. A related problem is consid-
eredin[106],whereaniterative,semidefinite-programming-basedapproachis
developed to maximize the algebraic connectivity of the Laplacian matrix of
undirected graphs (see Appendix B) with the motivation that the algebraic
connectivityoftheLaplacianmatrixcharacterizestheconvergencerateofthe
| consensus algorithm. |     |     |     |     |     |     |
| -------------------- | --- | --- | --- | --- | --- | --- |
Anotherproblemisconsideredin[202],whichfocusesondesigningconsen-
susalgorithmsinwhichtheinformationstateisupdatedaccordingtox˙ i =u i ,
and the information available to the ith vehicle is given by y = G x, where
i i
x=[x ,...,x ]T, y ∈Rmi, and G ∈Rmi×n. The information control input
| 1   | n i |     | i   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |

16 1 Overview of Consensus Algorithms in Cooperative Control
is designed in the form of u = k y +z , where k is a row vector with m
i i i i i i
components and z is a scalar.
i
Moregenerally,consideraninterconnectedne(cid:7)tworkofnvehicleswhosein-
formation states are updated according to x˙ = n A x +B w +B u ,
i j=1 ij j 1i i 2i i
i = 1,...,n, where x ∈ Rn denotes the information state, w ∈ Rm de-
i i
notes disturbances, and u ∈ Rr denotes the information control input with
i
i =1,...,n. Letting x, w, and u be column vectors with components x , w ,
i i
and u , respectively, the dynamics of x are denoted by x˙ =Ax+B w+B u.
i 1 2
Reference [52] focuses on synthesizing a decentralized state feedback control
lawthatguaranteesconsensusfortheclosed-loopsystemwithoutdisturbances
as wellas synthesizing a state-feedback controllerthat achievesnot only con-
sensus but optimal H performance for disturbance attenuation.
2
Extensions of Consensus Algorithms
Consensus algorithm (1.1) is extended in various ways in the literature. For
example, [17,47] generalize the consensus equilibrium to a weighted power
mean or arbitrary functions of the initial information states. In [104], quan-
tized consensus problems are studied, where the information state at each
node is an integer. In [224], an external input is incorporatedin (1.1) so that
the informationstate tracksa time-varyinginput. Consensus with a constant
reference state is addressed in [99,143], and consensus is addressed with a
time-varyingreferencestatein[90,180].In[229],necessaryandsufficientcon-
ditions are derived so that a collection of systems is controlled by a team
leader. An approach based on nonsmooth gradient flows is developed in [48]
to guarantee that average consensus is reached in finite time.
The single-integrator consensus algorithm given by (1.1) is also extended
to double-integrator dynamics in [89,186,261] to model more naturally the
evolution of physical phenomena, such as a coaxial rotorcraft MAV that can
be controlled through gentle maneuvers with a decoupled double-integrator
model. For double-integrator dynamics, the consensus algorithm is given by
(cid:2)n
x¨ =− a (t)[(x −x )+γ(x˙ −x˙ )],
i ij i j i j
j=1
where γ > 0 denotes the coupling strength between the information state
derivatives and both x and x˙ are transmitted between team members. It is
i i
shownin[186]thatboththecommunicationtopologyandcouplingstrengthγ
affect consensus-seekingin the generalcase of directedinformationexchange.
To achieve consensus, the directed communication topology must have a di-
rected spanning tree and γ must be sufficiently large.See [196]for extensions
to higher-order dynamics.
Relatedtoconsensusalgorithmsaresynchronizationphenomenaarisingin
systems of coupled nonlinear oscillators. The classical Kuramoto model [114]
consists of n coupled oscillators with dynamics given by

|     |     |     | 1.2 Literature | Review: | Consensus | Algorithms | 17  |
| --- | --- | --- | -------------- | ------- | --------- | ---------- | --- |
(cid:2)n
k
|     |     |     | θ˙ =ω + | sin(θ −θ | ),  |     | (1.4) |
| --- | --- | --- | ------- | -------- | --- | --- | ----- |
|     |     |     | i i     | j        | i   |     |       |
n
j=1
where θ i and ω i are, respectively, the phase and natural frequency of the
ith oscillator; and k is the coupling strength. Note that model (1.4) assumes
full connectivity of the network. Model (1.4) is generalized in [98] to nearest
| neighbor | information | exchange | as  |     |     |     |     |
| -------- | ----------- | -------- | --- | --- | --- | --- | --- |
(cid:2)n
k
|     |     | θ˙   |     |                 | −θ   |     |     |
| --- | --- | ---- | --- | --------------- | ---- | --- | --- |
|     |     | i =ω | i + | a ij (t)sin(θ j | i ). |     |     |
n
j=1
Connections between phase models of coupled oscillators and kinematic
models of self-propelledparticle groups are studied in [213].Analysis and de-
sign tools are developed to stabilize the collective motions. The stability of
thegeneralizedKuramotocouplednonlinearoscillatormodelisstudiedin[98],
whereitisproventhat,forcouplingsaboveacriticalvalue,alloscillatorssyn-
chronize given identical and uncertain natural frequencies. Extensions of [98]
to a tighter lower bound on the coupling strength are given in [46] for the
traditional Kuramoto model with full connectivity. The result in [98] is also
extended to account for heterogenous time delays and switching topologies
in [162].
Synchronization of coupled oscillators with other nonlinear dynamics is
alsostudiedinthe literature.Asanexample,consideranetworkofnvehicles
| with information |     | dynamics | given | by  |     |     |     |
| ---------------- | --- | -------- | ----- | --- | --- | --- | --- |
(cid:2)n
−x
|     |     | x˙ i | =f(x i ,t)+ | a ij (t)(x j | i ), |     | (1.5) |
| --- | --- | ---- | ----------- | ------------ | ---- | --- | ----- |
j=1
where x = [x ,...,x ]T. In [219], partial contraction theory is applied to
1 n
derive conditions under which consensus is reached for vehicles with dynam-
ics (1.5).As anotherexample,[166]studies a dynamic networkof n nonlinear
oscillators, where the state equation for each oscillator is given by
(cid:2)n
|     |     | x˙  | =f(x )+γ | a (t)(x | −x ), |     |     |
| --- | --- | --- | -------- | ------- | ----- | --- | --- |
|     |     | i   | i        | ij j    | i     |     |     |
j=1
∈ Rm
where x i and γ > 0 denotes the global coupling strength parameter.
It is shown in [166] that the algebraic connectivity of the network Laplacian
| matrix plays | a central | role | in synchronization. |     |     |     |     |
| ------------ | --------- | ---- | ------------------- | --- | --- | --- | --- |
1.2.4 Design of Coordination Strategies via Consensus Algorithms
In this section, we briefly describe a few applications of consensus algorithms
| to multivehicle | coordination |     | problems. |     |     |     |     |
| --------------- | ------------ | --- | --------- | --- | --- | --- | --- |

18 1 Overview of Consensus Algorithms in Cooperative Control
Rendezvous Problem
The rendezvous problem requires that a group of vehicles in a network ren-
dezvous at a time or a location determined through team negotiation. Con-
sensus algorithms can be used to perform the negotiation in a way that is
robust to environmental disturbances such as nonuniform wind for a team of
UAVs. The rendezvous problem for a group of mobile autonomous vehicles is
studied in [124,125], where synchronous and asynchronous cases are consid-
ered. In [124,125], vehicles execute a sequence of stop-and-go maneuvers to
rendezvous in a distributed manner without communication between neigh-
bors.A stop-and-gomaneuvertakesplace withina time intervalconsistingof
a sensing period during which neighbors’positions are determined, as well as
amaneuveringperiodduringwhichvehiclesmoveinresponsetothepositions
of their neighbors.
Figure 1.4 shows a simple coordination framework for multivehicle ren-
dezvous,whereaconsensusmanagerappliesdistributedconsensusalgorithms
to guarantee that all vehicles reachconsensus on a rendezvousobjective such
as a rendezvoustime or rendezvouslocation.Basedon the output ofthe con-
sensus manager,eachvehicle uses a localcontrollaw to drive itself to achieve
the rendezvous time and/or location. An application of Fig. 1.4 is described
in [110], where multiple UAVs are controlled to converge simultaneously on
the boundary of a radar detection area to maximize the element of surprise.
Teamwide consensus is reached on time-over-target,requiring each vehicle to
adjust its velocity to ensure synchronous arrival.
Consensus manager
Local … Local
control control
Fig. 1.4. A simple coordination framework for multivehicle rendezvous. The con-
sensusmanagerappliesdistributedconsensusalgorithmstoguaranteethattheteam
reaches consensus on arendezvousobjective. Based on theoutput of theconsensus
manager,eachvehicleapplieslocalcontrollawstoachievetherendezvousobjective.
Formation Stabilization
The formation stabilization problem requires that vehicles collectively main-
tain a prescribed geometric shape. This problem is relatively straightforward

|     |     |     | 1.2 | Literature | Review: | Consensus | Algorithms |     | 19  |
| --- | --- | --- | --- | ---------- | ------- | --------- | ---------- | --- | --- |
in the centralized case, where all team members know the desired shape and
location of the formation. On the other hand, in the decentralized formation
stabilizationproblem,eachvehicleknowsthedesiredformationshape,butthe
location of the formation needs to be negotiated among team members. The
information state for this problem includes the center of the formation. Each
vehicle initializes its information state by proposing a formation center that
does not require it to maneuver into formation. The consensus algorithm is
then employedby the teamof vehicles to negotiate a formationcenter known
| to all members | of  | the team. |     |     |     |     |     |     |     |
| -------------- | --- | --------- | --- | --- | --- | --- | --- | --- | --- |
In [69],an information flow filter is used to improve stability margins and
formation accuracy through propagation of the formation center to all vehi-
cles. Formation stabilization for multiple unicycles is studied in [127] using a
consensus algorithm to achieve point, line, and general formation patterns.
In addition, the simplified pursuit strategy for wheeled-vehicle formations
in [133] can be considered a special case of continuous-time consensus al-
gorithm (1.1), where the communication topology is a unidirectional ring.
Furthermore, feedback control laws are derived in [115] using relative infor-
mation between neighboring vehicles to stabilize vehicle formations.
| Formation | Maneuvering |     | and | Flocking |     |     |     |     |     |
| --------- | ----------- | --- | --- | -------- | --- | --- | --- | --- | --- |
Consensus algorithms can be applied to execute decentralized formation ma-
neuvers.Forexample,in[118],aclassofformationmaneuversisstudiedwhere
the desired position of each robot, hd(t), is either communicated to the team
i
by a centralized entity or is preprogrammed on each robot. The robots are
to maintain a prespecified formation shape even during transients and in re-
sponse to environmental disturbances. In other words, when one robot slows
down or maneuvers to avoid an obstacle, the other robots must maneuver
to maintain the formation shape. The intervehicle communication network is
limitedandrequiresadecentralizedapproachtomaintainthe formation.The
mobile robot dynamic model is feedback linearized as the double-integrator
systemh¨
i =u i ,whereh i denotesthe locationofapointontheithrobotthat
is not on the wheel axis and u denotes the control input. The decentralized
i
| formation | control | law   | is given | in [118] | as          |          |       |        |       |
| --------- | ------- | ----- | -------- | -------- | ----------- | -------- | ----- | ------ | ----- |
|           |         |       |          | (cid:2)n |             | (cid:2)n |       |        |       |
| u =−K     | h˜      | −D h˙ | −K       | a        | (h˜ −h˜ )−D |          | a (h˙ | −h˙ ), | (1.6) |
| i         | g i     | g     | i f      | ij       | i j         | f        | ij i  | j      |       |
|           |         |       |          | j=1      |             | j=1      |       |        |       |
where K and K are symmetrical positive-definite matrices, D and D
|     | g   | f   |     |     |     |     |     | g   | f   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
h˜ (cid:2)
are symmetrical positive-semidefinite matrices, and = h −hd. In control
|     |     |     |     |     |     | i   | i   | i   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
law (1.6), the first two terms guarantee that h approaches hd, whereas the
|                                       |     |     |     |     |     | i         |                     | i   |     |
| ------------------------------------- | --- | --- | --- | --- | --- | --------- | ------------------- | --- | --- |
| secondtwotermsguaranteethatthepairsh˜ |     |     |     |     | ,h˜ | andh˙ ,h˙ |                     |     |     |
|                                       |     |     |     |     | i   | j i       | j reachconsensus.If |     |     |
consensuscanbereachedforeachh˜ ,thepreservationofthedesiredformation
j
| shape is | guaranteed | during | maneuvers. |     |     |     |     |     |     |
| -------- | ---------- | ------ | ---------- | --- | --- | --- | --- | --- | --- |

| 20  | 1 Overview | of Consensus | Algorithms | in  | Cooperative | Control |     |     |
| --- | ---------- | ------------ | ---------- | --- | ----------- | ------- | --- | --- |
A similar approach can be applied to the rigid body attitude dynamics
|        |     |               | 1          | 1     |        | 1         |     |      |
| ------ | --- | ------------- | ---------- | ----- | ------ | --------- | --- | ---- |
|        |     | qˆ˙ =−        | ω ×qˆ +    | q¯ω , | q¯˙ =− | ω ·qˆ,    |     |      |
|        |     | i             | 2 i i      | 2 i i | i      | 2 i i     |     |      |
|        |     | J ω˙ =−ω      | ×(J ω )+T  | ,     |        |           |     |      |
|        |     | i i           | i i i      | i     |        |           |     |      |
|        |     |               | ∈          | R3,   | ∈ R,   | [qˆT,q¯]T |     | ∈ R4 |
| where, | for | the ith rigid | body, qˆ i | q¯ i  | and    | q i =     | i   | is   |
i
the unit quaternion,that is,the Euler parameters(see Appendix D), ω ∈R3
i
is the angular velocity, and J ∈ R3×3 and T ∈ R3 a(cid:14)re, respectively, the
|     |     |     | i   |     | i (cid:13) |     |     |     |
| --- | --- | --- | --- | --- | ---------- | --- | --- | --- |
[qˆ,q¯]T
inertiatensorandthecontroltorque.Definingvec =qˆastheoperator
that extracts the vector part of a quaternion, the control torque is given
by [117,176,188]
|     |     | (cid:13) (cid:14) | (cid:2)n |       | (cid:13) (cid:14) | (cid:2)n |       |          |
| --- | --- | ----------------- | -------- | ----- | ----------------- | -------- | ----- | -------- |
| T   | =−k | vec qd∗ q −D      | ω −k     | a vec | q ∗ q −D          | a        | (ω −ω | ), (1.7) |
| i   | G   | i i               | G i S    | ij    | j i               | S ij     | i     | j        |
|     |     |                   | j=1      |       |                   | j=1      |       |          |
≥
where k > 0 and k 0 are scalars, D is a symmetrical positive-definite
|     | G   | S   |     | G   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
matrix,D isasymmetricalpositive-semidefinitematrix,q∗ isthequaternion
S
conjugate,andqd
isthecentrallycommandedquaternion.Thefirsttwoterms
in (1.7) align the rigid body with the prespecified desired attitude qd. The
i
secondtwotermsin(1.7)areconsensustermsthatcausetheteamtomaintain
attitude alignment during the transients and in response to environmental
| disturbances |     | [176]. |     |     |     |     |     |     |
| ------------ | --- | ------ | --- | --- | --- | --- | --- | --- |
Using biologically observed motions of flocks of birds, [198] defines three
rules of flocking and applies them to generate realistic computer animations.
Thethreerulesofflockingarecollisionavoidance,velocitymatching,andflock
centering. Together these rules maintain the flock in close proximity without
collision. Reference [198] motivates the use of similar rules for multivehicle
robotic systems [155,232].As an example, consider the vehicle dynamics
|     |     |     | r˙ =v , | v˙ =u | ,   |     |     |     |
| --- | --- | --- | ------- | ----- | --- | --- | --- | --- |
|     |     |     | i i     | i     | i   |     |     |     |
where r and v are the position and velocity of vehicle i, respectively,and u
|     | i   | i   |     |     |     |     |     | i   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
denotes its input. In [155], the control input u i is defined as
(cid:2)n
∂V(r)
|     |     | =−  |     |            | −v )+fγ, |     |     |       |
| --- | --- | --- | --- | ---------- | -------- | --- | --- | ----- |
|     |     | u i | +   | a ij (r)(v | j i      |     |     | (1.8) |
|     |     |     | ∂r  |            |          | i   |     |       |
i
j=1
where the first term is the gradient of a collective potential function V(r),
the second term drives the system toward velocity consensus, and the third
term incorporates navigational feedback. In (1.8), the first term guarantees
flock centering and collision avoidance among the vehicles, the second term
guaranteesvelocitymatchingamongthevehicles,andthe thirdtermachieves
a group objective. Equation (1.8) has been validated for flocking with undi-
| rected | communication | topologies. |     |     |     |     |     |     |
| ------ | ------------- | ----------- | --- | --- | --- | --- | --- | --- |

1.3 Monograph Overview 21
1.3 Monograph Overview
The subject of this monograph is distributed coordination of multiple au-
tonomous vehicles. The objective of distributed coordination is to have mul-
tiple autonomousvehiclesworktogetherefficientlytoachievecollectivegroup
behavior via local interaction. This monograph introduces distributed con-
sensus algorithms and their applications in cooperative control of multiple
autonomous vehicles. The consensus algorithms require only neighbor-to-
neighbor information exchange, which minimizes the power consumption, in-
creases the stealth, and improves the scalability and robustness of the team.
In addition, the consensus algorithms allow the interaction topologies among
the vehicles to be dynamically changing,sparse,or intermittent. This feature
is particularly useful for real-world application scenarios where communica-
tiontopologiesareusuallynotfullyconnected,communicationlinksareoften
noisy and unreliable, and vehicles have only limited communication range
and bandwidth. This monograph includes both theoretical and experimen-
tal results in distributed coordination of multiple ground robots, spacecraft,
and UAVs. The theoretical results address distributed consensus algorithms
and their extensions for single-integrator, double-integrator, and rigid body
attitude dynamics and show convergence analysis results in the presence of
directed,limited, andunreliable informationexchangeamongvehicles.Those
results extend many existing results in the area of cooperative control. In
the application chapters of the book, we apply the distributed consensus al-
gorithms to several multivehicle cooperative control applications, including
formation keeping for wheeled mobile robots and spacecraft and cooperative
perimeter tracking and timing for a team of UAVs. The application results
demonstrate issues and challenges in multivehicle cooperative control.
This monograph consists of six parts and six appendices. The first part
overviewsconsensusalgorithmsincooperativecontrolofmultipleautonomous
vehicles (Chapter 1). The second part introduces consensus algorithms for
single-integrator dynamics (Chapter 2) and consensus algorithms with a ref-
erence state (Chapter 3). The third part introduces consensus algorithms for
double-integrator dynamics (Chapter 4) and their extensions to a reference
model (Chapter 5). The fourth part focuses on attitude consensus for rigid
body attitude dynamics (Chapter 6) and relative attitude maintenance and
reference attitude tracking (Chapter 7). The fifth part introduces consensus-
based design methodologies for distributed multivehicle cooperative control
(Chapter 8). The sixth part applies consensus algorithms to several multive-
hicle cooperative control applications: rendezvous and axial alignment with
multiple wheeled mobile robots (Chapter 9), distributed formation control of
multiplewheeledmobilerobotswithavirtualleader(Chapter10),adecentral-
izedbehavioralapproachtomultiplerobotformationmaneuvers(Chapter11),
deep space spacecraft formation flying (Chapter 12), cooperative fire moni-
toring with multiple UAVs (Chapter 13), and cooperative surveillance with
multiple UAVs (Chapter 14). In addition, Appendices A–F review, respec-

| 22 1 | Overview of Consensus | Algorithms | in Cooperative | Control |
| ---- | --------------------- | ---------- | -------------- | ------- |
tively, selected notations and abbreviations, graph theory notations, matrix
theory notations, rigid body attitude dynamics, linear system theory back-
| ground, | and nonlinear stability | theory background. |     |     |
| ------- | ----------------------- | ------------------ | --- | --- |
1.4 Notes
The results in this chapter are based mainly on [191]. For further literature
| review on      | consensus algorithms, | see [156]. |     |     |
| -------------- | --------------------- | ---------- | --- | --- |
| Acknowledgment | is given              | to         |     |     |
(cid:10)c2007 IEEE. Reprinted, with permission, from Wei Ren, Randal W.
Beard,andEllaM.Atkins,“Informationconsensusinmultivehiclecooperative
control: Collective group behavior through local interaction,” IEEE Control
| Systems | Magazine, vol. 27, | no. 2, pp. 71–82,April | 2007. |     |
| ------- | ------------------ | ---------------------- | ----- | --- |

Part II
| Consensus | Algorithms | for Single-integrator |
| --------- | ---------- | --------------------- |
Dynamics

2
Consensus Algorithms for Single-integrator
Dynamics
This chapter introduces consensus algorithms for single-integrator dynamics.
Both continuous-time and discrete-time consensus algorithms are analyzed
underbothfixedanddynamicallychanginginteractiontopologies.Thischap-
ter shows, respectively, that consensus under fixed interaction topologies can
beachievedasymptoticallyifandonlyifthedirectedinteractiontopologyhas
a directed spanning tree and consensus under dynamically changing interac-
tion topologies can be achieved asymptotically if there exist infinitely many
uniformly bounded, consecutive time intervals such that the union of the di-
rectedinteractiontopologiesacrosseachsuchintervalhasadirectedspanning
tree.
2.1 Fundamental Algorithms
(cid:2)
Suppose that there are n vehicles in a team. We use directed graph G =
n
(V ,E ), where V = {1,...,n} is the node set and E ⊆ V × V is
n n n n n n
the edge set, to model the interaction topology among the n vehicles. Let
A = [a ] ∈ Rn×n and L = [(cid:2) ] ∈ Rn×n be, respectively, the adjacency
n ij n ij
matrixandthenonsymmetricalLaplacianmatrixassociatedwithG (seeAp-
n
pendix B for graph theory notations). Note that an undirected graph can
be viewed as a special case of a directed graph. A directed graph takes into
accountthegeneralcasewhereinformationflowmaybeunidirectional.Unidi-
rectionalcommunicationlinksareusefulwhen,forexample,somevehiclesina
heterogeneousteamhavetransceivers,whereasotherlesscapablevehicleshave
only receivers. Furthermore, vehicles in a team may have nonuniform trans-
mission strength. In addition, in the case of information exchange through
local sensing,vehicles may be equipped with sensorsthat haveonly a limited
field of view, which may result in directed interaction topologies.
Consider information states with single-integrator dynamics given by
ξ˙ =u , i=1,...,n, (2.1)
i i

| 26     | 2 Consensus | Algorithms                |     | for Single-integrator |     |     | Dynamics                |     |
| ------ | ----------- | ------------------------- | --- | --------------------- | --- | --- | ----------------------- | --- |
|        | ∈Rm         |                           |     |                       |     | ∈Rm |                         |     |
| whereξ |             | istheinformationstateandu |     |                       |     |     | istheinformationcontrol |     |
|        | i           |                           |     |                       |     | i   |                         |     |
input of the ith vehicle. A continuous-time consensus algorithm is given by
(cid:2)n
|     |     | u   | =−  | a (t)(ξ | −ξ  | ), i=1,...,n, |     | (2.2) |
| --- | --- | --- | --- | ------- | --- | ------------- | --- | ----- |
|     |     | i   |     | ij      | i j |               |     |       |
j=1
where a (t) is the (i,j) entry of the adjacency matrix A (t)∈Rn×n at time
|     | ij  |     |     |     |     |     | n   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     | ∈   | E   |     |     |     |
t. Note that a (t) > 0 if (j,i) at time t and a (t) = 0 otherwise,
|     |     | ij  |     |     | n   |     | ij  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
∀j (cid:6)=i. Intuitively, the information state of each vehicle is driven toward the
information states of its neighbors. Equations (2.1) and (2.2) can be written
| in matrix | form | as  |     |        |       |     |     |       |
| --------- | ---- | --- | --- | ------ | ----- | --- | --- | ----- |
|           |      |     |     | ξ˙=−[L | (t)⊗I | ]ξ, |     | (2.3) |
|           |      |     |     |        | n     | m   |     |       |
Rn×n
where ξ = [ξT,...,ξT]T, L (t) ∈ is the nonsymmetrical Laplacian
|     |     | 1   | n   | n   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
matrixattime tand⊗denotesthe Kroneckerproduct.With(2.2),consensus
is achieved or reached by the team of vehicles if, for all ξ i (0) and all i,j =
| 1,...,n, | (cid:9)ξ (t)−ξ | (t)(cid:9)→0, |     | as t→∞. |     |     |     |     |
| -------- | -------------- | ------------- | --- | ------- | --- | --- | --- | --- |
i j
When interactionamong vehicles occurs atdiscrete instants,the informa-
tion state is updated using a difference equation. A discrete-time consensus
| algorithm | is given | by  |     |     |     |     |     |     |
| --------- | -------- | --- | --- | --- | --- | --- | --- | --- |
(cid:2)n
|     |     | ξ   | [k+1]= | d   | [k]ξ [k], | i=1,...,n, |     | (2.4) |
| --- | --- | --- | ------ | --- | --------- | ---------- | --- | ----- |
|     |     | i   |        |     | ij j      |            |     |       |
j=1
where k ∈ {0,1,...} is the discrete-time index; d [k] is the (i,j) entry of a
ij
|     |     |     | D   | ∈   | Rn×n |     |     |     |
| --- | --- | --- | --- | --- | ---- | --- | --- | --- |
row-stochastic matrix = [d ] (see Appendix C) at the discrete-
|     |     |     | n   | ij  |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
timeindexkwiththeadditionalassumptionthatd [k]>0foralli=1,...,n
ii
|     |     | ∀i (cid:6)= |     | ∈ E |     |     |     |     |
| --- | --- | ----------- | --- | --- | --- | --- | --- | --- |
and d ij [k]> 0, j, if (j,i) n and d ij [k] = 0 otherwise. Intuitively, the
information state of each vehicle is updated as the weighted average of its
current state and the current states of its neighbors. Equation (2.4) can be
| written | in matrix | form | as        |     |       |        |     |       |
| ------- | --------- | ---- | --------- | --- | ----- | ------ | --- | ----- |
|         |           |      | ξ[k+1]=(D |     | [k]⊗I | )ξ[k]. |     | (2.5) |
|         |           |      |           |     | n     | m      |     |       |
With (2.4), consensus is achieved or reached by the team of vehicles if, for all
|             |         |           | (cid:9)ξ | [k]−ξ | [k](cid:9)→0, |     | →∞.  |     |
| ----------- | ------- | --------- | -------- | ----- | ------------- | --- | ---- | --- |
| ξ i [0] and | all i,j | =1,...,n, |          | i     | j             |     | as k |     |
Notethatconsensusalgorithms(2.2)and(2.4)aredistributedinthesense
that each vehicle needs only information from its neighbors. Also note that
theinteractiontopologymaybechangingdynamicallyduetounreliabletrans-
missionoralimitedcommunication/sensingrange.We useG (t)andG [k]to
|     |     |     |     |     |     |     | n   | n   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
denotethedynamicallychanginginteractiontopologiescorrespondingto(2.2)
and (2.4), respectively. For a given interaction topology, the weights a (t)
ij
in (2.2) and d [k] in (2.4) may be time-varying to represent possibly the
ij
time-varying relative confidence of each vehicle’s information state or rela-
tivereliabilitiesofdifferentinteractionlinksamongvehicles.Asaresult,both
L (t) in (2.3) and D [k] in (2.5) may be dynamically changing over time.
| n   |     |     | n   |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |

2.1 FundamentalAlgorithms 27
Remark 2.1. The continuous-time update rule in [97] can be viewed as a spe-
cial case ofcontinuous-time consensus algorithm(2.2) by letting a (t)= 1 if
ij n
(j,i)∈E at time t and a (t)=0 otherwise, ∀j (cid:6)=i. The Vicsek model [239]
n ij
can be viewed as a special case of discrete-time consensus algorithm (2.4) by
letting d [k]= 1 if(j,i)∈E atthediscrete-timeindexk andd [k]=0
ij 1+|Ni| n ij
otherwise, ∀j (cid:6)= i, and d [k] = 1 , where |N | denotes the number of
ii 1+|Ni| i
neighbors of vehicle i, that is, each vehicle simply averages its own informa-
tionstatewiththosethatarecommunicatedtoit.ThesimplifiedVicsekmodel
used in [97] can be viewed as a special case of (2.4) by letting d [k] = 1 if
ij g
(j,i) ∈ E
n
at(cid:7)the discrete-time index k and d
ij
[k] = 0 otherwise, ∀j (cid:6)= i, and
d [k]=1− d [k], where g >n is a constant. (cid:13)(cid:14)
ii j(cid:5)=i ij
We have the following preliminary results:
Lemma 2.2.Continuous-time algorithm (2.2) achieves consensus asymptot-
ically if and only if
(cid:15) (cid:15) (cid:15)
t t σ1
Φ(t,0)=I + −L (σ )dσ + −L (σ ) −L (σ )dσ dσ
n n 1 1 n 1 n 2 2 1
0 0 0
+···→1 cT, (2.6)
n
as t→∞, where I is the n×n identity matrix, 1 denotes the n×1 column
n n
vector with all of the entries equal to 1, and c is an n vector of constant
coefficients.
Proof: Note that the team ofvehiclesreachesconsensusasymptoticallyif and
only if the set
S ={ξ ∈Rn :ξ =ξ =···=ξ },
1 2 n
is attractive and positively invariant.
Because ξ(t)=[Φ(t,0)⊗I ]ξ(0) (see Appendix E), (2.6) implies that
m
⎡ ⎤
(cT ⊗I )ξ(0)
m
lim ξ(t)=(1 cT ⊗I )ξ(0)= ⎢ ⎣ . . ⎥ ⎦,
n m .
t→∞
(cT ⊗I )ξ(0)
m
which implies that S is attractive and positively invariant.
Conversely,if S is attractive and positively invariant, then
lim ξ(t)= lim[Φ(t,0)⊗I ]ξ(0)=1 ⊗α,
m n
t→∞ t→∞
whereαis anm×1vectorofconstantcoefficients,whichinturnimplies that
lim Φ(t,0)=1 cT.
n
t→∞

| 28  | 2 Consensus | Algorithms |     | for Single-integrator |     |     | Dynamics |     |     |
| --- | ----------- | ---------- | --- | --------------------- | --- | --- | -------- | --- | --- |
Lemma 2.3.Discrete-timealgorithm (2.4)achievesconsensusasymptotically
| if and only | if  |        |           |     |      |      |       |     |       |
| ----------- | --- | ------ | --------- | --- | ---- | ---- | ----- | --- | ----- |
|             | D   | [k−1]D | [k−2]···D |     | [2]D | [1]D | [0]→1 | cT, |       |
|             |     | n      | n         |     | n    | n    | n n   |     | (2.7) |
→∞,
| as k | where | c is | an n vector | of  | constant | coefficients. |     |     |     |
| ---- | ----- | ---- | ----------- | --- | -------- | ------------- | --- | --- | --- |
Proof: Notethatξ[k]=(D [k−1]D [k−2]···D [1]D [0]⊗I )ξ[0].Theproof
|               |         |          | n    | n     |             | n   | n          | m   |     |
| ------------- | ------- | -------- | ---- | ----- | ----------- | --- | ---------- | --- | --- |
| is similar    | to that | of Lemma | 2.2. |       |             |     |            |     |     |
| 2.2 Consensus |         | Under    |      | Fixed | Interaction |     | Topologies |     |     |
In this section,we assume that the interactiontopology is time-invariantand
L
the weights a in (2.2) and d in (2.4) are constant, that is, in (2.3) and
|     | ij  |     | ij  |     |     |     |     | n   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
D in (2.5) are constant. We will derive necessary and sufficient conditions
n
for consensus of information using both continuous-time and discrete-time
| consensus       | algorithms. |       |                   |     |     |           |     |     |     |
| --------------- | ----------- | ----- | ----------------- | --- | --- | --------- | --- | --- | --- |
| 2.2.1 Consensus |             | Using | a Continuous-time |     |     | Algorithm |     |     |     |
In the following, we first consider the case where the information state is
inherently constant. We then consider the case where the information state
is dynamically evolving in time. This is the case, for example, in formation
controlproblemswheretheinformationstateisthedynamicstateofavirtual
leader.
Static Consensus
| We need | the following |     | lemma | to derive | our | main  | results. |     |     |
| ------- | ------------- | --- | ----- | --------- | --- | ----- | -------- | --- | --- |
|         |               |     |       |           | ∈   | Rn×n, |          | ≤   | ≥   |
Lemma 2.4(cid:7).Given a matrix A = [a ij ] where a ii 0, a ij 0,
∀i (cid:6)= j, and n a =0 for each i, then A has at least one zero eigenvalue
j=1 ij
1
with an associated eigenvector n , and all nonzero eigenvalues are in the open
left half plane. Furthermore, A has exactly one zero eigenvalue if and only if
the directed graph of A, denoted by Γ(A), has a directed spanning tree.
Proof: For the first statement, note that A has zero row sums, which implies
that A has at least one zero eigenvalue with an associated eigenvector 1 .
n
AlsonotethatAisdiagonallydominantandhasnonpositivediagonalentries.
ItfollowsfromTheoremC.1thatallnonzeroeigenvaluesofAareinthe open
left half plane.
The second statement of the lemma will be shown using an induction
argument.
(Sufficiency.) Step 1. The first step is to show that A has exactly one zero
| eigenvalue | if Γ(A) | is  | itself a directed |     | spanning | tree. |     |     |     |
| ---------- | ------- | --- | ----------------- | --- | -------- | ----- | --- | --- | --- |

2.2 Consensus UnderFixed Interaction Topologies 29
Noting that Γ(A) is itself a directed spanning tree, renumber the vehicles
consecutivelybydepthinthe directedspanningtree,withthe rootnumbered
as 1. In other words, children of 1 are numbered 2 to q , children of 2 to q
1 1
arelabeledq +1toq ,andsoon.NotethattheassociatedmatrixAislower
1 2
diagonal with only one diagonal entry equal to zero.
(cid:7) Step 2. Let Q = [q ij ] ∈ Rn×n, where q ii ≤ 0, q ij ≥ 0, ∀i (cid:6)= j, and
n q = 0 for each i. Let S = [s ] ∈ Rn×n satisfy the same properties as
j=1 ij ij
thoseofQ.AlsoletΓ(Q)andΓ(S)bedirectedgraphsofQandS,respectively.
We assume that s = q −k , s = q +k , and s = q otherwise,
(cid:7)(cid:7) (cid:7)(cid:7) (cid:7)m (cid:7)m (cid:7)m (cid:7)m ij ij
where k > 0 denotes the weight for the edge (m,(cid:2)), m (cid:6)= (cid:2), that is, Γ(S)
(cid:7)m
correspondsto a graphwhere one more edge from node m to node (cid:2) is added
(cid:2) (cid:2)
to Γ(Q), where m (cid:6)= (cid:2). Denote p (t) = det(tI −Q) and p (t) = det(tI −S)
Q S
(cid:2)
as the characteristic polynomial of Q and S, respectively. Let Q = tI −Q
t
(cid:2)
and S = tI −S. Given any matrix M, denote M([i,j]) as the submatrix of
t
M formed by deleting the ith row and jth column.
Next, we will show that if Q has exactly one zero eigenvalue,then so does
S. Without loss of generality,we assume that the new edge added to Γ(Q) is
from node m to node 1, where m (cid:6)= 1, for simplicity, because we can always
renumber node (cid:2) as node 1.
Obviously,S has atleastone zeroeigenvalue,andallother nonzeroeigen-
values are in the open left half plane following the first statement of this
lemma. Below, we will show that S has only one zero eigenvalue.
Assume that Q = [q ], and S = [s ], i,j = 1,...,n. Accordingly,
t tij t tij
it can be seen that s = t −s = t −q + k = q + k , s =
t11 11 11 1m t11 1m t1m
−s =−q −k =q −k , and s =q otherwise. Also note that
1m 1m 1m t1m 1m tij tij
detS ([1,j])=detQ ([1,j]), j =1,...,n. Then we know that
t t
(cid:2)n
detS = (−1)1+js detS ([1,j])
t t1j t
j=1
(cid:2)n
= (−1)1+jq detS ([1,j])
t1j t
j=1
+k detS ([1,1])−(−1)1+mk detS ([1,m])
1m t 1m t
=detQ +k {detS ([1,1])+(−1)mdetS ([1,m])}.
t 1m t t
Consider a matrix E = [e ], i,j = 1,...,n − 1, given by adding
ij
[s ,s ,...,s ]T to the (m −1)st column of S([1,1]). The matrix E can
21 31 n1
be denoted as ⎡ ⎤
s s ··· s +s ··· s
22 23 2m 21 2n
⎢ ⎢s 32 s 33 ··· s 3m +s 31 ··· s 3n ⎥ ⎥
E =⎢ ⎣ . .
.
. .
.
. .
.
... . .
.
. .
.
⎥ ⎦ .
s s ··· s +s ··· s
n2 n3 nm n1 nn

30 2 Consensus Algorithms for Single-integrator Dynamics
Thus e i(m⎡−1) = s (i+1)m + s (i+1)1 , ⎤ i = 1, ⎡ ...,n − 1. Given p ⎤ × p matri-
f ··· f +h ··· f f ··· f ··· f
11 1k 1k 1p 11 1k 1p
ces F¯ = ⎢ ⎣ . . . . . . . . . . ⎥ ⎦, F = ⎢ ⎣ . . . . . . . . . . ⎥ ⎦, and H =
. . . . . . . . . .
f ··· f +h ··· f f ··· f ··· f
⎡ p1 p⎤k pk pp p1 pk pp
f ··· h ··· f
11 1k 1p
⎢ ⎣ . . . . . . . . . . ⎥ ⎦, the properties of determinants imply that detF¯ =
. . . . .
f ··· h ··· f
p1 pk pp
detF +detH. Therefore, it can be verified that
det(tI−E)=detS ([1,1])+(−1)mdetS ([1,m]).
t t
Obviously, E has zero row sums and nonpositive diagonal entries and is di-
agonally dominant. The first statement of the lemma implies that E has at
least one zero eigenvalue and all nonzero eigenvalues are in the open left half
plane. As a result, the Routh stability criterion implies that the characteris-
tic polynomial of E denoted as det(tI −E) has a nonnegative coefficient in
the first power of t. We also know that Q has a positive coefficient for the
first power of t in its characteristic polynomial detQ because Q has exactly
t
one zero eigenvalue and all other eigenvalues are in the open left half plane.
Noting that detS = detQ +k det(tI −E), it is obvious that p (t) has a
t t 1m S
positivecoefficientforthefirstpoweroft.Therefore,S canonlyhaveonezero
eigenvalue.
Step 3. If Γ(A) is itself a directed spanning tree, we know from Step 1
thatAhasexactlyonezeroeigenvalue.Ifnot,graphΓ(A)canbeconstructed
by consecutively adding edges to the directed spanning tree. Step 2 implies
that adding one additional edge to the directed spanning tree results in an
associatedmatrixthatalsohasexactlyonezeroeigenvalue.Wecanrecursively
add additional edges, where Step 2 implies that the matrix associated with
each new graph has exactly one zero eigenvalue, until we obtain Γ(A). By
induction, we know that A has exactly one zero eigenvalue if Γ(A) has a
directed spanning tree.
(Necessity.) If Γ(A) does not have a directed spanning tree, then there
exists a vehicle that separates two subgroups that do not exchange informa-
tion or there exist at least two vehicles that do not receive any information
from their neighbors. For the first case, suppose that the first subgroup has
p vehicles and the second subgroup has q vehicles, where p+q = n−1. By
renumbering the vehicles by their subgroup, we assume that vehicles 1 to p
are in the first subgroup, vehicles p+2 to n are in the second subgroup, and
vehicle p+1 separates the two subgroups. Note that A can then be written
as ⎡ ⎤
A p 0 p×1 0 p×q
⎣ ⎦
A= a¯ a a¯ ,
p p+1,p+1 q
0 q×p 0 q×1 A q
where A ∈ Rp×p, a¯ = [a ,...,a ], a¯ = [a ,...,a ], and
p p p+1,1 p+1,p q p+1,p+2 p+1,n
A ∈ Rq×q. It is straightforward to see that both A and A have zero
q p q

2.2 Consensus UnderFixed Interaction Topologies 31
row sums and hence have at least one zero eigenvalue. It thus follows that
Rank(A ) ≤ p−1 and Rank(A ) ≤ q−1. Therefore, from the structure of
p q
A, we know that Rank(A) ≤ n−2, implying that A has at least two zero
eigenvalues. For the second case, A has at least two zero rows, which implies
that A has at least two zero eigenvalues.
Corollary 2.5.The nonsymmetrical Laplacian matrix L of a directed graph
n
has a simple zero eigenvalue with an associated eigenvector 1 and all of the
n
other eigenvalues are in the open right half plane if and only if the directed
graph has a directed spanning tree.
Proof: If we multiply the nonsymmetrical Laplacian matrix by −1, we get a
matrix satisfying the properties defined in Lemma 2.4.
Next, we will show that the team of vehicles reaches consensus asymp-
totically using continuous-time algorithm (2.2) if −L in (2.3) has exactly
n
one zero eigenvalue and all other eigenvalues are in the open left half plane.
The following result also computes the value of the information state that is
reached through the consensus process.
Lemma 2.6.IfL isthen×nnonsymmetricalLaplacian matrix,thene−Lnt,
n
∀t≥0, is a row-stochastic matrix with positive diagonal entries. In addition,
Rank(L )=n−1ifandonlyifL hasasimplezeroeigenvalue.Furthermore,
n n
if L has a simple zero eigenvalue and ν =[ν ,...,ν ]T ≥0 satisfy 1Tν =1
n 1 n n
and LTν =0,1 then e−Lnt →1 νT, as t→∞.
n n
Proof: For the first statement, given eigenvalues λ ∈ σ(−L ) with eigen-
i n
vectors z , i = 1,...,n, where σ(·) represents the spectrum of a matrix, we
i
know that eλit ∈ σ(e−Lnt) with the same eigenvectors as −L . Noting that
n
−L has at least one zero eigenvalue with an associated eigenvector 1 from
n n
Lemma2.4,itfollowsthate−Lnt hasatleastoneeigenvalueequaltoonewith
the same eigenvector 1 . Thus we know that e−Lnt1 = 1 , which implies
n n n
that e−Lnt always has row sums equal to 1. Define the nonnegative matrix
M =βI −L ,whereβ isthemaximumofthediagonalentriesofL .Wecan
n n n
see that e−Lnt = e−βteMt, which is obviously nonnegative and has positive
diagonal entries. As a result, e−Lnt, ∀t ≥ 0, is a row-stochastic matrix with
positivediagonalentries,whichimplies thatρ(e−Lnt)=1,where ρ(·)denotes
the spectral radius of a matrix.
For the second statement, if L has a simple zero eigenvalue, then
n
Nullity(L ) = 1, which in turn implies Rank(L ) = n−1. Next, we show
n n
that Rank(L ) = n−1 implies that L has a simple zero eigenvalue. Given
n n
the system x˙ = −L x, where x ∈Rn, the solution is x(t) =e−Lntx(0). Note
n
that e−Lnt is a row-stochastic matrix with positive d(cid:18)iagona(cid:18)l entries from the
first statement of the lemma. Then it follows that (cid:18) e−Lnt (cid:18) = 1, ∀t ≥ 0,
∞
which in turn implies that the system x˙ = −L x is marginally stable. Note
n
1 Thatis,ν isthen×1nonnegativelefteigenvectorofL associatedwiththezero
n
eigenvalue and satisfies 1Tν =1.
n

32 2 Consensus Algorithms for Single-integrator Dynamics
that the linear time-invariant (LTI) system x˙ = Fx, where F ∈ Rn×n, is
marginally stable if and only if all of the eigenvalues of F have nonpositive
real parts and every eigenvalue with zero real parts should have its geomet-
ric multiplicity equal to its algebraic multiplicity. Also note that −L has at
n
least one zero eigenvalue and all nonzero eigenvalues of −L have negative
n
real parts from Lemma 2.4. Because the system x˙ =−L x is marginally sta-
n
ble,thegeometricmultiplicityofthezeroeigenvalueofL equalsitsalgebraic
n
multiplicity. Note that Rank(L ) = n−1 implies that Nullity(L ) = 1, that
n n
is, the geometric multiplicity of the zero eigenvalue is one. It follows that the
algebraic multiplicity of the eigenvalue zero is also one, which in turn implies
that L has a simple zero eigenvalue.
n
For the third statement, note from Lemma 2.4 that all of the nonzero
eigenvaluesof−L areintheopenlefthalfplane.If−L hasexactlyonezero
n n
eigenvalue,thene−Lnt,∀t>0,hasexactlyoneeigenvalueequalto1andallof
the other eigenvalues have moduli less than 1. Let J =[j ], m,l = 1,...,n,
ml
be the Jordan matrix corresponding to −L ; then j = λ . Without loss
n mm m
of generality, assume that λ = 0 and λ is in the open left half plane,
n m
m=1,...,n−1.
Let −L =PJP−1, where P =[p ,...,p ] is an n×n matrix. Note that
n 1 n
p can correspond to an eigenvector associated with the eigenvalue λ = 0.
n n
Without loss of generality, choose p =1 as the eigenvector.
n n
We know that e−Lnt =PeJtP−1. It can be verified that
⎡ ⎤
00 ··· 0
eJt →
⎢ ⎢
⎢
. .
.
. .
.
... . .
.
⎥ ⎥
⎥,
⎣ 00 ··· 0 ⎦
00 ··· 1
ast→∞,fromthe propertyof−L .Aftersomemanipulation,weknowthat
n
e−Lnt →1 νT, as t→∞, where ν , i=1,...,n, corresponds to the last row
n i
of the matrix P−1. The result 1Tν = 1 comes from the fact that e−Lnt has
n
row sums equal to 1 for any t.
We also need to show that ν ≥ 0 and LTν = 0. Now consider the ma-
n
trix e−Lnk, k = 0,1,2,.... Obviously e−Lnk will approach 1 νT, as k → ∞.
n
From Lemma C.2, ν is an eigenvector of (e−Ln)T associated with the simple
eigenvalue1,whichinturnimplies thatν isaneigenvectorof−LT associated
n
with the simple eigenvalue 0. Equivalently, it follows that LTν = 0. From
n
Theorem C.4, (e−Ln)T has a nonnegative eigenvector x ≥ 0 associated with
the simp(cid:7)le eigenvalue 1. Thus it can be seen that ν = αx for some α (cid:6)= 0.
Because n ν = 1, it must be true that α > 0, which implies that ν ≥ 0.
i=1 i
Remark 2.7. Note that if we replace −L with −γL in (2.3), where γ > 0,
n n
we can increase consensus speed by increasing γ. The solution of (2.3) with
this new matrix is given by ξ = e−γLntξ(0), which converges faster than the
original solution, if we choose γ >1. (cid:13)(cid:14)

|     |     |     | 2.2 | Consensus | UnderFixed | Interaction | Topologies | 33  |
| --- | --- | --- | --- | --------- | ---------- | ----------- | ---------- | --- |
The following theorem shows a necessary and sufficient condition for con-
sensus with a time-invariant interaction topology and constant gains a .
ij
Theorem 2.8.SupposethatA isconstant.Algorithm (2.2)achieves consen-
n
ifan(cid:7)donlyifdirectedgraphG
| susasymptotically |     |     |     |     |     | hasadirectedspanningtree. |     |     |
| ----------------- | --- | --- | --- | --- | --- | ------------------------- | --- | --- |
n
In particular, ξ (t) → n ν ξ (0), as t → ∞, where ν = [ν ,...,ν ]T ≥ 0,
|     |     | i       |     | i=1 i i |     |     | 1   | n   |
| --- | --- | ------- | --- | ------- | --- | --- | --- | --- |
| 1Tν |     | andL Tν |     |         |     |     |     |     |
|     | =1, |         | =0. |         |     |     |     |     |
|     | n   | n       |     |         |     |     |     |     |
e−Lnt →
Proof: (Sufficiency.) From Lemma 2.2, we need to show that 1 cT,
n
where c is an n×1 vector. Obviously −L in (2.3) associated with G has
|     |     |     |     |     |     | n   |     | n   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
G
the same properties as A in Lemma 2.4. The fact that n has a directed
spanningtree impliesthatthe directedgraphof−L hasa directedspanning
n
tree. Therefore, we know from Lemma 2.4 that −L has exactly one zero
n
eigenvalue and all other eigenvalues are in the open left half plane. As a
result, we know that the continuous-time algorithm (2.2) achieves consensus
asymptotically according to Lemma 2.6. With (2.2), the solution of (2.1) is
by(cid:7)ξ(t)=(e−Lnt⊗I
| given |     |     |     | )ξ(0). | Therefore, | it follows from | Lemma | 2.6 that |
| ----- | --- | --- | --- | ------ | ---------- | --------------- | ----- | -------- |
m
| ξ   | (t)→ | n ν ξ (0), | i=1,...,n, |     | as t→∞. |     |     |     |
| --- | ---- | ---------- | ---------- | --- | ------- | --- | --- | --- |
| i   |      | i=1 i i    |            |     |         |     |     |     |
(Necessity.) Suppose that algorithm (2.2) achieves consensus asymptoti-
cally but that G does not have a directed spanning tree. Then there exist at
n
suchthatthereisnopathinG
| leasttwovehiclesiandj |     |     |     |     |     | n   | thatcontainsbothi |     |
| --------------------- | --- | --- | --- | --- | --- | --- | ----------------- | --- |
andj.Thereforeitisimpossibletobringdatabetweenthesetwovehiclesinto
consensus, which implies that consensus cannot be achieved asymptotically.
| Consensus |     | Equilibrium |     |     |     |     |     |     |
| --------- | --- | ----------- | --- | --- | --- | --- | --- | --- |
We haveshownthatalgorithm(2.2)achievesconsensus asymptoticallyif and
o(cid:7)nly if G has a directed span(cid:7)ning tree. In addition, ξ (t) will converge to
|     | n       |         |       |     |        |           | i               |     |
| --- | ------- | ------- | ----- | --- | ------ | --------- | --------------- | --- |
|     | n       | t→∞,    |       |     | n      | ≥0.       |                 |     |
|     | ν i ξ i | (0), as | where |     | ν i =1 | and ν i A | naturalquestion | is  |
|     | i=1     |         |       |     | i=1    |           |                 |     |
whethereachinitialconditionξ (0)willcontributetothefinalconsensusequi-
i
librium point. We assume in this subsection that G has a directed spanning
n
tree.
Observethatif there is a node k inG withoutanincoming edge (there is
n
G
at most one such node if n has a directed spanning tree), the linear update
ξ˙
law corresponding to this node is given by = 0 from (2.2), which implies
k
thatξ (t)=ξ (0)forallt.Therefore,theothernodesmustconvergetoξ (0),
|     | k   | k   |     |     |     |     |     | k   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
∀i(cid:6)=k.
| that | is, ν | =1 and | ν =0, |     |     |     |     |     |
| ---- | ----- | ------ | ----- | --- | --- | --- | --- | --- |
|      | k     |        | i     |     |     |     |     |     |
In general, the initial condition of a node contributes to the equilibrium
G
value if and only if the node has a directed path to all other nodes in n .
Thus ν (cid:6)=0 for every node that has a directed path to all other nodes in G
|     | i   |     |     |     |     |     |     | n   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
and ν = 0 otherwise. As a special case, the initial condition of each node in
i
a directed graph contributes to the final equilibrium point if and only if the
directed graph is strongly connected. The above argument can be explained
G
as follows. If there is no path from node j to node m in n , it is impossible

34 2 Consensus Algorithms for Single-integrator Dynamics
for ξ (t) tobe influencedbyξ (0).Onthe otherhand,if thereis a pathfrom
m j
node j to every other node in G , then ξ (t), ∀i (cid:6)= j, will be influenced by
n i
ξ (0).
j
Thefactthatν ≥0,i=1,...,n,canalsobeexplainedfromthefollowing
i
perspective. Assume that ν
(cid:7)
<0 for some (cid:2). Consider(cid:7)the case ξ
(cid:7)
(0)> 0 and
ξ (0)=0, ∀i(cid:6)=(cid:2). We know that ξ (t) will convergeto n ν ξ (0)=ν ξ (0),
i i i=1 i i (cid:7) (cid:7)
which is negative. Following continuous-time algorithm (2.2), ξ˙ (0) < 0 if
(cid:7)
there exists an incoming edge to node (cid:2) and ξ˙ (0) = 0 otherwise. In the first
(cid:7)
case, ξ (t) will decrease and ξ (t), ∀i (cid:6)= (cid:2) cannot decrease because ξ˙(0) ≥ 0,
(cid:7) i i
which implies that ξ (t) will be driven to a value c with 0≤c<ξ (0). In the
i (cid:7)
second case, ξ (t) will be driven to ξ (0). Both cases are contradictory to the
i (cid:7)
above result. Th(cid:7)erefore, ν
i
≥0, i=1,...,n.
Ifξ (t)→ 1 n ξ (0)(i.e.,ν = 1 foralliinTheorem2.8),thenthecon-
i n i=1 i i n
sensus equilibrium is the averageofthe initial informationstates,a condition
called average consensus.
Corollary 2.9. [158] Suppose that A is constant. Algorithm (2.2) achieves
n
average consensus asymptotically if and only if directed graph G is strongly
n
connected and balanced or undirected graph G is connected.
n
In summary of the subsections on static consensus and consensus equilib-
rium, we have the following two lemmas:
Lemma 2.10.Suppose that z = [zT,...,zT]T with z ∈ Rm and L ∈ Rp×p
1 p i p
satisfies the property (B.2). Then the following five conditions are equivalent.
(i) L has a simple zero eigenvalue with an associated eigenvector 1 and all
p p
other eigenvalues have positive real parts,
(ii) (L ⊗I )z =0 implies that z =···=z ,
p m 1 p
(iii) Consensus is reached asymptotically for the system z˙ =−(L ⊗I )z,
p m
(iv) The directed graph of L has a directed spanning tree,
p
(v) The rank of L is p−1.
p
Lemma 2.11.Suppose that z and L are defined in Lemma 2.10. Then the
p
following four conditions are equivalent.
(i) The directed graph of L has a directed spanning tree and vehicle k has no
p
incoming edges,2
(ii) The directed graph of L has a directed spanning tree and every entry of
p
the kth row of L is zero,
p
(iii) Consensus is reached asymptotically for the system z˙ = −(L ⊗I )z,
p m
where z (t)→z (0), i=1,...,p, as t→∞,
i k
(iv) Vehicle k is the only node that has a directed path to all other vehicles on
the team.
2 Atmost,onesuchvehiclecanexistwhenthedirectedgraphhasadirectedspan-
ning tree.

|          |                  | 2.2 | Consensus | UnderFixed | Interaction | Topologies | 35  |
| -------- | ---------------- | --- | --------- | ---------- | ----------- | ---------- | --- |
| Relative | State Deviations |     |           |            |             |            |     |
Notethat(2.2)representsthefundamentalformofconsensusalgorithms.The
algorithmcanbeextendedtoachievedifferentconvergenceresults.Forexam-
ple,(2.2)canbeextendedtoguaranteethatthedifferencesintheinformation
states convergeto desired values, i.e., ξ −ξ →Δ (t), where Δ (t) denotes
|     |     |     |     |     | i j ij | ij  |     |
| --- | --- | --- | --- | --- | ------ | --- | --- |
thedesired(time-varying)deviationbetweenξ andξ .Weapplythefollowing
|           |              |       |             |     | i   | j   |     |
| --------- | ------------ | ----- | ----------- | --- | --- | --- | --- |
| algorithm | for relative | state | deviations: |     |     |     |     |
(cid:2)n
|     | u =δ˙ | −   | a [(ξ | −ξ )−(δ | −δ )], | i=1,...,n, | (2.8) |
| --- | ----- | --- | ----- | ------- | ------ | ---------- | ----- |
|     | i     | i   | ij i  | j       | i j    |            |       |
j=1
(cid:2)
|     | −δ  | ∀i  | (cid:6)= |     |     |     |     |
| --- | --- | --- | -------- | --- | --- | --- | --- |
where Δ ij = δ i j , j, denotes the desired deviation between the in-
formation states. Note that by appropriately choosing δ , (cid:2) = 1,...,n, we
(cid:7)
can guarantee that the differences in the information states converge to de-
siredvalues.Algorithm(2.8)has applicationsin formationcontrol,where the
teamformsacertainformationshapebymaintainingrelativepositionsamong
vehicles. Also note that (2.2) corresponds to the case where Δ ≡0, ∀i(cid:6)=j.
ij
We have the following corollary for relative state deviations:
|     |     |     | A   |     |     | −   | →   |
| --- | --- | --- | --- | --- | --- | --- | --- |
Corollary 2.12.Suppose that n is constant. With (2.8), ξ i (t) ξ j (t)
Δ (t), as t → ∞, if and only if directed graph G has a directed spanning
| ij  |     |     |     |     | n   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
tree.
| Proof: With | (2.8), | (2.1) can | be written |     | as  |     |     |
| ----------- | ------ | --------- | ---------- | --- | --- | --- | --- |
(cid:2)n
ξˆ˙
|     |     | =−  | a   | (ξˆ −ξˆ), | i=1,...,n, |     |     |
| --- | --- | --- | --- | --------- | ---------- | --- | --- |
|     |     | i   | ij  | i         | j          |     |     |
j=1
whereξˆ (cid:2) −δ .FromTheorem2.8,weknowthatξˆ(t)→ξˆ(t),ast→∞,if
| i   | = ξ i i |     |     |     |     | i j |     |
| --- | ------- | --- | --- | --- | --- | --- | --- |
andonlyifG hasadirectedspanningtree.The restoftheproofthenfollows
n
the fact that ξˆ(t) →ξˆ(t), as t →∞, is equivalent to ξ (t)−ξ (t)→Δ (t),
|     | i   | j   |     |     |     | i j | ij  |
| --- | --- | --- | --- | --- | --- | --- | --- |
t→∞.
as
| Dynamic | Consensus |     |     |     |     |     |     |
| ------- | --------- | --- | --- | --- | --- | --- | --- |
Note that a perturbation term may exist in (2.2). The perturbation term
may represent an external signal or disturbance. As a result, consensus algo-
| rithm (2.2) | becomes |     |     |     |     |     |     |
| ----------- | ------- | --- | --- | --- | --- | --- | --- |
(cid:2)n
|     |     | =−  |         | −ξ      |                |     |       |
| --- | --- | --- | ------- | ------- | -------------- | --- | ----- |
|     | u   | i   | a ij (ξ | i j )+w | i , i=1,...,n, |     | (2.9) |
j=1
| where w | ∈Rm denotes | the | perturbation |     | term. |     |     |
| ------- | ----------- | --- | ------------ | --- | ----- | --- | --- |
i

36 2 Consensus Algorithms for Single-integrator Dynamics
In the special case where the information state of each vehicle is driven
by the same time-varying input wf(t)∈Rm, which might representan a pri-
ori known feedforward signal or an exogenous input signal, the associated
consensus algorithm is given by
(cid:2)n
u =− a (ξ −ξ )+wf, i=1,...,n. (2.10)
i ij i j
j=1
Equation (2.10) can also be written in matrix form as
ξ˙=−(L ⊗I )ξ+1 ⊗wf. (2.11)
n m n
We have the following theorem regarding consensus of the information
states ξ , i=1,...,n, using (2.10).
i
Theorem 2.13.Suppose that A is constant. Algorithm (2.10)achieves con-
n
sensus asymptotically if and o(cid:7)nly if directed gr(cid:10)aph G
n
has a directed spanning
tree. In particular, ξ (t) → n ν ξ (0) + t wf(τ)dτ, as t → ∞, where
i i=1 i i 0
ν =[ν ,...,ν ]T ≥0, 1Tν =1, and LTν =0.
1 n n n
Proof: (Suffi
(cid:10)
ciency.) The solution of (2.11) is given by ξ(t) = (e−Lnt ⊗
I )ξ(0) + t [e−Ln(t−τ) ⊗ I ][1 ⊗ wf(τ)]dτ (see Appendix E). Note from
m 0 m n
Lemma 2.6 that e−Lnt →1 νT and e−Ln(t−τ)1 =1 . This proves the suffi-
n n n
cient part.
(Necessity.) The necessary part follows directly from Theorem 2.8.
When w (cid:6)=w in (2.9), we have the following theorem:
i j
Theorem 2.14.Suppose that A is constant. Under the condition that di-
n
rected graph G has a directed spanning tree, if (cid:9)w −w (cid:9) is uniformly
n i j
bounded, so is (cid:9)ξ −ξ (cid:9), ∀i(cid:6)=j.
i j
Proof: Let ξ = (cid:2) ξ −ξ and w = (cid:2) w −w . Also let ξ˜= [ξT ,ξT ,...,ξT ]T
ij i j ij i j 12 13 1n
andw˜ =[wT ,wT ,...,wT ]T. Note thatξ =ξ −ξ .Using (2.9),(2.1)can
12 13 1n ij 1j 1i
be written in matrix form as
ξ˜˙ =(Q⊗I )ξ˜+w˜, (2.12)
m
where Q ∈ R(n−1)×(n−1) is constant. Note that Theorem 2.13 implies that
undertheconditionthatw =w ,∀i(cid:6)=j,andG containsadirectedspanning
i j n
tree, algorithm (2.9) achieves consensus asymptotically, which implies that
ξ˜(t) → 0, as t → ∞. It thus follows that (2.12) is asymptotically stable
under the same condition that w = w , ∀i (cid:6)= j, by noting that w = w ,
i j i j
∀i(cid:6)=j,implies w˜ =0.Because(2.12)isanLTIsystem,asymptoticalstability
implies bounded-inputbounded-state stability(see Appendix E),thatis,ifw˜
isuniformlybounded,soisξ˜.Equivalently,if(cid:9)w −w (cid:9)isuniformlybounded,
i j
so is (cid:9)ξ −ξ (cid:9), ∀i(cid:6)=j.
i j
Remark 2.15. Theorem 2.14 implies that using (2.9), (2.1) is input-to-state
stable (ISS) (see Appendix F) under the assumption of the theorem. (cid:13)(cid:14)

|              |         |     | 2.2 Consensus | UnderFixed |     | Interaction | Topologies | 37  |
| ------------ | ------- | --- | ------------- | ---------- | --- | ----------- | ---------- | --- |
| Illustrative | Example |     |               |            |     |             |            |     |
We consider a scenario where six vehicles are to rendezvous at a position
alongaparameterizedtrajectoryrepresentedby{r [τ(t)],r [s(t)]}.Figure2.1
|     |     |     |     |     |     | x   | y   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
showsthe correspondingcommunicationtopologyamongthesevehicles.Note
| the existence | of  | a directed | spanning | tree. |     |     |     |     |
| ------------- | --- | ---------- | -------- | ----- | --- | --- | --- | --- |
Itisassumedthateachvehicleknowstheparameterizedtrajectory.There-
fore, the parameters τ and s represent the minimum information needed to
achieve the coordination objective, i.e., τ and s are the information states.
We will instantiate τ and s on eachvehicle as τ and s , i=1,...,6. Here we
|     |     |     |     |     |     | i   | i   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
]T,
| let ξ i =[τ | i ,s i | i=1,...,6. |     |     |     |     |     |     |
| ----------- | ------ | ---------- | --- | --- | --- | --- | --- | --- |
(cid:6)(cid:6)
|     |     |     |                                                                  | (cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) (cid:8)(cid:8) | (cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) |                                                                  |     |     |
| --- | --- | --- | ---------------------------------------------------------------- | ------------------------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- | --- | --- |
|     |     |     |                                                                  | 1                                                                               | 2                                                                |                                                                  |     |     |
|     |     |     | (cid:7)(cid:7)                                                   |                                                                                 |                                                                  | (cid:9)(cid:9)                                                   |     |     |
|     |     |     | (cid:10)(cid:14)(cid:11)(cid:15)(cid:12)(cid:16)(cid:13)(cid:17) |                                                                                 |                                                                  | (cid:10)(cid:14)(cid:11)(cid:15)(cid:12)(cid:16)(cid:13)(cid:17) |     |     |
|     |     |     | 3                                                                |                                                                                 |                                                                  | 4                                                                |     |     |
|     |     |     | (cid:11)(cid:11)                                                 |                                                                                 |                                                                  | (cid:13)(cid:13)                                                 |     |     |
|     |     |     |                                                                  | (cid:9)(cid:9) (cid:10)(cid:10)                                                 |                                                                  |                                                                  |     |     |
|     |     |     |                                                                  | (cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13)                | (cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) |                                                                  |     |     |
|     |     |     |                                                                  | 5                                                                               | (cid:12)(cid:12) 6                                               |                                                                  |     |     |
|     |     |     | Fig. 2.1.                                                        | Communication                                                                   |                                                                  | topology                                                         |     |     |
Based on the communication topology shown in Fig. 2.1, the matrix −L
6
| is given by |     |     | ⎡       |         |       |          | ⎤    |     |
| ----------- | --- | --- | ------- | ------- | ----- | -------- | ---- | --- |
|             |     |     | −1.51.5 |         | 0 0   | 0        | 0    |     |
|             |     |     | ⎢       | 2 −2    | 0 0   | 0        | 0 ⎥  |     |
|             |     |     | ⎢       |         |       |          | ⎥    |     |
|             |     |     | ⎢       | −       |       |          | ⎥    |     |
|             |     |     | ⎢       | 0 .9 0  | 2.8 0 | 1 .9     | 0 ⎥  |     |
|             |     | −L  | =γ ⎢    |         |       |          | ⎥ ,  |     |
|             |     | 6   |         | 0 1 .2  | 0 −2  | .5 0     | 1 .3 |     |
|             |     |     | ⎢       |         |       |          | ⎥    |     |
|             |     |     | ⎣       |         |       | −3.2     | ⎦    |     |
|             |     |     |         | 0 0 1.4 | 1.8   |          | 0    |     |
|             |     |     |         | 0 0     | 0 0   | 0.7 −0.7 |      |     |
where γ >0 is a coefficient. The initial conditions for each instantiation of τ
(0)=0.2i−0.1
| and s are | given | by τ i |     | and | s i (0)=0.2i, |     | i=1,...,6. |     |
| --------- | ----- | ------ | --- | --- | ------------- | --- | ---------- | --- |
Figure 2.2 shows the consensus scenario using the continuous-time algo-
rithm (2.2) for γ =1 and γ =5, respectively.We can see that only the initial
conditions of vehicle 1 and vehicle 2 affect the equilibrium value, which is
consistent with the communication topology shown in Fig. 2.1, where it can
be seen that only vehicle 1 and vehicle 2 have a directed path to all other
vehicles. Figure 2.3 shows the same consensus scenario corresponding to the
communicationtopology formedby deleting the edge (2,1) in Fig. 2.1.It can
be seen that each instantiation of τ and s converges to τ 1 (0) and s 1 (0), re-
spectively. In both Figs. 2.2 and 2.3, consensus is reached faster for γ = 5
| than for γ | =1. |     |     |     |     |     |     |     |
| ---------- | --- | --- | --- | --- | --- | --- | --- | --- |

| 38  | 2   | Consensus | Algorithms |     | for Single-integrator |     | Dynamics |     |
| --- | --- | --------- | ---------- | --- | --------------------- | --- | -------- | --- |
|     |     |           | γ=1        |     |                       |     | γ=1      |     |
1.2
|     | 1.1 |     |     |     |     | 1   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
0.9
0.8
| τ   | i 0.7 |     |     |     |     | s i |     |     |
| --- | ----- | --- | --- | --- | --- | --- | --- | --- |
0.6
0.5
0.3
0.4
0.1
|     | 0   |     |          |     |     | 0.2 |          |       |
| --- | --- | --- | -------- | --- | --- | --- | -------- | ----- |
|     | 0   | 5   | 10       | 15  | 20  | 0   | 5 10     | 15 20 |
|     |     |     | Time (s) |     |     |     | Time (s) |       |
|     |     |     | γ=5      |     |     |     | γ=5      |       |
1.2
|     | 1.1 |     |     |     |     | 1   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     | 0.9 |     |     |     |     | 0.8 |     |     |
|     | 0.7 |     |     |     |     | i   |     |     |
| τ   | i   |     |     |     |     | s   |     |     |
0.6
0.5
|     | 0.3 |     |     |     |     | 0.4 |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
0.1
|     | 0   |     |          |     |     | 0.2 |          |       |
| --- | --- | --- | -------- | --- | --- | --- | -------- | ----- |
|     | 0   | 5   | 10       | 15  | 20  | 0   | 5 10     | 15 20 |
|     |     |     | Time (s) |     |     |     | Time (s) |       |
Fig. 2.2. Consensus of τ and s using continuous-timealgorithm (2.2)
|     |     |     |     | i   | i   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Figure2.4illustratesa dynamicconsensusscenariousing algorithm(2.10)
for γ = 1 and γ =5, respectively. The common predefined planning schemes
|     |       |       |       |         | 1|sin(t)| |      | 1|cos(t)|,    |       |
| --- | ----- | ----- | ----- | ------- | --------- | ---- | ------------- | ----- |
| for | τ and | s are | given | by τ˙ = | and       | s˙ = | respectively. | Here, |
|     |       |       |       |         | 5         |      | 4             |       |
we let wf(t)=[1|sin(t)|,1|cos(t)|]T in (2.10). It can be seen that consensus
|     |     |     | 5   | 4   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
is achieved asymptotically and that both τ i and s i follow their predefined
| planning |           | schemes.      |       |                 |           |           |          |     |
| -------- | --------- | ------------- | ----- | --------------- | --------- | --------- | -------- | --- |
| 2.2.2    | Consensus |               | Using | a Discrete-time |           | Algorithm |          |     |
| We       | need      | the following |       | lemmas          | to derive | our main  | results: |     |
Lemma 2.16.If a nonnegative matrix A = [a ] ∈ Rn×n has the same pos-
ij
itive constant row sums given by μ > 0, then μ is an eigenvalue of A with
an associated eigenvector 1 and ρ(A) = μ, where ρ(·) denotes the spectral
n
radius. In addition, the eigenvalue μ of A has algebraic multiplicity equal to
one, if and only if the directed graph of A, denoted by Γ(A), has a directed
spanning tree. Furthermore, if a > 0, i = 1,...,n, then |λ| < μ for every
ii
λ(cid:6)=μ.
eigenvalue Moreover, if Γ(A) has a directed spanning tree and a ii >0,
i=1,...,n, then μ is the unique eigenvalue of maximum modulus.

|     | 2.2 Consensus | UnderFixed | Interaction Topologies | 39  |
| --- | ------------- | ---------- | ---------------------- | --- |
|     | γ=1           |            | γ=1                    |     |
1.2
| 1.1 |     |     | 1   |     |
| --- | --- | --- | --- | --- |
0.9
0.8
| τ i 0.7 |     | s i |     |     |
| ------- | --- | --- | --- | --- |
0.6
0.5
0.3
0.4
0.1
| 0   |          | 0.2 |          |       |
| --- | -------- | --- | -------- | ----- |
| 0 5 | 10 15    | 20  | 0 5 10   | 15 20 |
|     | Time (s) |     | Time (s) |       |
|     | γ=5      |     | γ=5      |       |
1.2
1.1
1
0.9
0.8
| 0.7 |     | i   |     |     |
| --- | --- | --- | --- | --- |
| τ i |     | s   |     |     |
0.6
0.5
0.4
0.3
0.2
0.1
| 0   |          |     | 0        |       |
| --- | -------- | --- | -------- | ----- |
| 0 5 | 10 15    | 20  | 0 5 10   | 15 20 |
|     | Time (s) |     | Time (s) |       |
Fig. 2.3. Consensus of τ and s without edge (2,1) using continuous-time algo-
|     | i   | i   |     |     |
| --- | --- | --- | --- | --- |
rithm (2.2)
Proof: Forthefirststatement,notethatAhasthesamepositiveconstantrow
sums given by μ > 0, which implies that A1 n = μ1 n . Theorem C.1 implies
that all eigenvalues of A are located in the union of the n discs given by
|     | (cid:19)n  |     | (cid:2) |     |
| --- | ---------- | --- | ------- | --- |
|     | {z ∈C:|z−a | |≤  | |a |},  |     |
(2.13)
|     |     | ii  | ij  |     |
| --- | --- | --- | --- | --- |
j(cid:5)=i
i=1
where C is the set of complex numbers. It thus follows that ρ(A)=μ.
For the second statement, we need to show both necessary and sufficient
conditions.
(Sufficiency.) If Γ(A) has a directed spanning tree, then the directed
graph of B = A − μI also has a directed spanning tree. We know that
n
λ (A)=λ (B)+μ,wherei=1,...,n,andλ (·)representstheitheigenvalue.
| i i |     | i   |     |     |
| --- | --- | --- | --- | --- |
Noting that B satisfies the conditions in Lemma 2.4, we know that zero is an
eigenvalueof B with algebraicmultiplicity equalto one,whichimplies that μ
is an eigenvalue of A with algebraic multiplicity equal to one.

| 40  | 2 Consensus | Algorithms | for Single-integrator | Dynamics |     |
| --- | ----------- | ---------- | --------------------- | -------- | --- |
|     |             | γ=1        |                       | γ=1      |     |
|     | 3           |            | 4                     |          |     |
2.5
3
2
| τ   | i 1.5 |     | s i 2 |     |     |
| --- | ----- | --- | ----- | --- | --- |
1
1
0.5
|     | 0   |          | 0   |          |       |
| --- | --- | -------- | --- | -------- | ----- |
|     | 0 5 | 10 15    | 20  | 0 5 10   | 15 20 |
|     |     | Time (s) |     | Time (s) |       |
|     |     | γ=5      |     | γ=5      |       |
|     | 3   |          | 4   |          |       |
2.5
3
2
|     | 1.5 |     | i 2 |     |     |
| --- | --- | --- | --- | --- | --- |
| τ   | i   |     | s   |     |     |
1
1
0.5
|     | 0   |          | 0   |          |       |
| --- | --- | -------- | --- | -------- | ----- |
|     | 0 5 | 10 15    | 20  | 0 5 10   | 15 20 |
|     |     | Time (s) |     | Time (s) |       |
Fig. 2.4. Consensus and evolution of τ and s using algorithm (2.10)
|     |     |     | i   | i   |     |
| --- | --- | --- | --- | --- | --- |
(Necessity.)IfΓ(A)doesnothaveadirectedspanningtree,weknowfrom
Lemma 2.4 that B = A−μI has more than one zero eigenvalue, which in
n
| turn | implies that | A has more | than one eigenvalue | equal to μ. |     |
| ---- | ------------ | ---------- | ------------------- | ----------- | --- |
For the third statement, noting that a > 0, it is easy to see that
ii
|       |           |               |                 | {z ∈ C |z| | μ}        |
| ----- | --------- | ------------- | --------------- | ---------- | --------- |
| union | (2.13) is | included in a | circle given by | :          | = and the |
circularboundariesofthe unionofthendiscshaveonlyoneintersectionwith
the circle at z = μ. Thus we know that |λ| < μ for every eigenvalue of A
λ(cid:6)=μ.
satisfying
Combining the second and third statement, we know that μ is the unique
| eigenvalue | of maximum | modulus. |     |     |     |
| ---------- | ---------- | -------- | --- | --- | --- |
Remark 2.17. Theorem C.5 states that if a nonnegative matrix A is irre-
ducible,thatis,thedirectedgraphofAisstronglyconnected,thenthespectral
radius of A is a simple eigenvalue. We show that the irreducibility condition
is too stringent for nonnegative matrices with the same positive row sums.
Lemma 2.16 explicitly shows that for a nonnegative matrix A with identical
positive row sums, the spectral radius of A (the row sum in this case) is a
simple eigenvalue if and only if the directed graph of A has a directed span-
ning tree. In other words, A may be reducible but retains its spectral radius

|     |     | 2.2 | Consensus | UnderFixed |     | Interaction |     | Topologies | 41  |
| --- | --- | --- | --------- | ---------- | --- | ----------- | --- | ---------- | --- |
as a simple eigenvalue. Furthermore, if A has a directed spanning tree and
positive diagonalentries, we know that the spectral radius of A is the unique
(cid:13)(cid:14)
| eigenvalue | of maximum |     | modulus. |     |     |     |     |     |     |
| ---------- | ---------- | --- | -------- | --- | --- | --- | --- | --- | --- |
Corollary 2.18.A row-stochastic matrix A = [a ] ∈ Rn×n has algebraic
ij
multiplicity equal to one for its eigenvalue ρ(A)=1 if and only if Γ(A) has a
|λ|
directed spanning tree. Furthermore, if a > 0, i = 1,...,n, then < 1 for
ii
everyeigenvalue notequaltoone.Inaddition, ifΓ(A)has adirectedspanning
tree and a ii > 0, i = 1,...,n, then 1 is the unique eigenvalue of maximum
modulus.
Lemma 2.19.Let A = [a ] ∈ Rn×n be a row-stochastic matrix. If A has
ij
an eigenvalue λ = 1 with algebraic multiplicity equal to one and all other
eigenvalues satisfy |λ| < 1, then A is SIA. In particular, lim m→∞Am →
| νT, |     |     | ATν |     | 1Tν |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
1 n where ν satisfies =ν and =1. Furthermore, each element of
n
ν is nonnegative.
Proof: The first statement of the lemma follows Lemma C.2. For the second
statement, it is obviousthat AT is also nonnegative and has ρ(AT)=1 as an
eigenvaluewithalgebraicmultiplicityequaltoone.ThusTheoremC.4implies
thattheeigenspaceofAT
associatedwiththeeigenvalueλ=1isgivenbycx,
where c ∈ C, c (cid:6)= 0, and x is a nonnegative eigenvector. Because ν is also an
eigenvectorofAT associatedwith the eigenvalueλ=1 andsatisfies 1Tν =1,
n
| it follows | that each | element | of ν | must | be nonnegative. |     |     |     |     |
| ---------- | --------- | ------- | ---- | ---- | --------------- | --- | --- | --- | --- |
Next, we show a necessary and sufficient condition for consensus of infor-
| mation using | discrete-time |     | algorithm |     | (2.4). |     |     |     |     |
| ------------ | ------------- | --- | --------- | --- | ------ | --- | --- | --- | --- |
Theorem 2.20.Suppose that A is constant. Discrete-time algorithm (2.4)
n
achieves consensus asymptotically if and only if d(cid:7)irected graph G has a di-
n
|     |     |     |     |     |     | → n |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
rected spanning tree. In particular, ξ [k] ν ξ [0], where ν =
|             |       |           |         |        | i    | i=1  | i i |       |        |
| ----------- | ----- | --------- | ------- | ------ | ---- | ---- | --- | ----- | ------ |
| [ν ,...,ν   | ]T ≥0 | satisfies | DTν     | =ν and | 1Tν  | =1.  |     |       |        |
| 1           | n     |           | n       |        | n    |      |     |       |        |
|             |       |           |         |        |      | Dk   | →   | cT,   |        |
| Proof: From | Lemma | 2.3,      | we need | to     | show | that | 1 n | where | c is a |
n
| constant | column | vector. |     |     |     |     |     |     |     |
| -------- | ------ | ------- | --- | --- | --- | --- | --- | --- | --- |
(Sufficiency.)ObviouslyD isarow-stochasticmatrixwithpositivediago-
n
nalentries.ThefactthatG
hasadirectedspanningtreealsoimpliesthatthe
n
directed graphof D has a directed spanning tree. Combining Corollary2.18
n
|     |     |     |     |     | D k | → νT, |     |     |     |
| --- | --- | --- | --- | --- | --- | ----- | --- | --- | --- |
and Lemma 2.19, we know that lim k→∞ 1 n where ν satisfies the
n
| properties | defined | in the | lemma. |     |     |     |     |     |     |
| ---------- | ------- | ------ | ------ | --- | --- | --- | --- | --- | --- |
(Necessity.)If G does not have a directed spanning tree,neither does the
n
D
directed graph of , which implies, by Corollary 2.18, that the algebraic
n
multiplicity oftheeigenvalueρ(D )=1ofD isp>1.Therefore,theJordan
|                 |     |     |        | n   |          | n     |     |         |          |
| --------------- | --- | --- | ------ | --- | -------- | ----- | --- | ------- | -------- |
|                 |     | Dk  | formDk |     | =MJkM−1, |       |     |         |          |
| decompositionof |     | has | the    |     |          | where | M   | is full | rank and |
|                 |     | n   |        | n   |          |       |     |         |          |
Jk is lower triangular with p diagonal elements equal to one. Therefore, the
rank of lim D k is at least p > 1 which implies, by Lemma 2.3, that the
k→∞ n
| team of vehicles |     | cannot | reach consensus |     | asymptotically. |     |     |     |     |
| ---------------- | --- | ------ | --------------- | --- | --------------- | --- | --- | --- | --- |
Using discrete-time consensus algorithm (2.4), we have similar results for
| consensus | equilibrium | analysis |     | and dynamics |     | consensus. |     |     |     |
| --------- | ----------- | -------- | --- | ------------ | --- | ---------- | --- | --- | --- |

42 2 Consensus Algorithms for Single-integrator Dynamics
2.3 Consensus Under Dynamically Changing Interaction
Topologies
We need the following lemmas.
Lemma 2.21.Given n×n nonnegative matrices A and B, if A ≥ αB, for
some α>0, then Γ(B) is a subgraph of Γ(A).
Proof: Trivial.
.
Lemma 2.22.Given n×n nonnegative matrices P, Q, R, andS , if P ∼R
and Q∼S, then (P+Q)∼(R+S) and PQ∼RS, where ∼ denotes that two
nonnegative matrices are of the same type (see Appendix C for its definition).
Moreover, if an n×n time-varying nonnegative matrix M(t) with continuous
(cid:10)
entriesisofafixedtypefort∈[t ,t ],wheret <t ,thenM(t)∼ t2M(t)dt.
1 2 1 2 t1
Proof: Trivial.
Lemma 2.23.Let C(cid:7)(t) = [c
ij
(t)] ∈ Rn×n be piecewise continuous, where
c ≥0, ∀i(cid:6)=j, and c =0. Let Φ (t,t ) be the corresponding transition
ij j ij C 0
matrix.ThenΦ (t,t )isarow-stochasticmatrixwithpositivediagonalentries
C 0
for any t≥t .
0
Proof: Note that
(cid:15) (cid:15) (cid:15)
t t σ1
Φ (t,t )=I + C(σ )dσ + C(σ ) C(σ )dσ dσ +··· . (2.14)
C 0 n 1 1 1 2 2 1
t0 t0 t0
Noting that C(t)1 =0, we can verify that Φ (t,t )1 =1 .
n C 0 n n
Let B(t) = C(t) + μI n , where μ is a constant greater than max τ∈[t0,t]
max |c (τ)|. Note that B(t) is a nonnegative matrix with positive diagonal
i ii
entries. It is straightforwardto see that
d
Φ (t,t )=C(t)Φ (t,t )
C 0 C 0
dt
and
d
[Φ (t,t )e
−μ(t−t0)]
B 0
dt
=B(t)Φ (t,t )e
−μ(t−t0)−μΦ
(t,t )e
−μ(t−t0)
B 0 B 0
=(B(t)−μI )Φ (t,t )e −μ(t−t0)
n B 0
=C(t)Φ (t,t )e
−μ(t−t0),
B 0
and that Φ (t ,t ) = Φ (t ,t )e−μ(t0−t0) = I . Therefore, it follows that
C 0 0 B 0 0 n
Φ (t,t )=Φ (t,t )e−μ(t−t0).Using(2.14)tocomputeΦ (t,t ),itisstraight-
C 0 B 0 B 0
forwardto see that Φ (t,t ) is nonnegativeand haspositive diagonalentries.
B 0
Therefore, it follows that Φ (t,t ) is nonnegative and has positive diago-
C 0
nal entries. Combining these arguments, it follows that the transition matrix
Φ (t,t ) is a row-stochastic matrix with positive diagonal entries.
C 0

2.3 Consensus UnderDynamically Changing Interaction Topologies 43
|       |          |         |     | (t)]∈Rn×n |     | C˜  | (t)]∈Rn×n |            |     |
| ----- | -------- | ------- | --- | --------- | --- | --- | --------- | ---------- | --- |
| Lemma | 2.24.Let | C(t)=[c |     |           |     | and | =[c˜      | be contin- |     |
|       |          |         |     | ij        |     |     | ij        |            |     |
u(cid:7)ouson t∈[τ,(cid:7)s],wheres>τ, suchthat c (t)≥0and c˜ (t)≥0,∀i(cid:6)=j,and
|     |     |     |     |     |     | ij  | ij  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| n   |     | n   |     |     |     |     |     |     |     |
c ij (t)= c˜ ij (t)=0.LetΦ C (s,τ)andΦ C˜ (s,τ)bethecorresponding
| j=1 |     | j=1 |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
C˜(t)
transition matrices. Suppose that the directed graphs of C(t) and are the
same and fixed for t∈[τ,s]. Then the directed graph of C(t) is a subgraph of
| the directed | graph | of  | Φ (s,τ) | and | Φ (s,τ)∼Φ |     | (s,τ). |     |     |
| ------------ | ----- | --- | ------- | --- | --------- | --- | ------ | --- | --- |
|              |       |     | C       |     | C         | C˜  |        |     |     |
Proof: Let B(t) =C(t)+μI n , where μ is a constant greater than max τ∈[t0,t]
| max |c | (τ)|. | Following | Lemma |     | 2.23, | we  | know that | Φ (s,τ) | =   |
| ------ | ----- | --------- | ----- | --- | ----- | --- | --------- | ------- | --- |
| i ii   |       |           |       |     |       |     |           | C       |     |
Φ (s,τ)e−μ(s−τ). Note that the directed graphs of C(t) and B(t) are the
B
same, so are the directed graphs of Φ (s,τ) and Φ (s,τ). T(cid:10)herefore, us-
|     |     |     |     |     |     | C   | B   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
ing (2.(cid:10)14) to compute Φ (s,τ), we can see that Φ (s,τ) ≥ s B(σ )dσ ,
|       |         |       | B   |          |     |             | B         | τ        | 1 1   |
| ----- | ------- | ----- | --- | -------- | --- | ----------- | --------- | -------- | ----- |
|       | s       | ∼B(t) |     | t∈[τ,s], |     |             |           |          |       |
| where | B(σ )dσ |       | for |          |     | or in other | words,the | directed | graph |
|       | τ 1     | 1     |     |          |     |             |           |          |       |
ofB(t)fort∈[τ,s]isasubgraphofthedirectedgraphofΦ (s,τ).Therefore,
B
∈
the directed graph of C(t) for t [τ,s] is a subset of the directed graph of
Φ (s,τ).
C
Note thatΦ (s,τ)=Φ (s,τ)e−μ˜(s−τ),where C˜ =B˜−μ˜I .To showthat
|     |     | C˜  | B˜  |     |     |     |     | n   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Φ is of the same type as Φ C˜ , we need to show that Φ is of the same type
| C   |     |     |     |     |     |     | B   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
asΦ .Note thatB andB˜ areofthe sametype because theirdirectedgraphs
B˜
are the same. By writing Φ and Φ as in (2.14) and comparing each term,
|     |     |     |     | B   | B˜  |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Lemma 2.22 implies that eachcorresponding term is of the same type, which
in turn implies that Φ B (s,τ) and Φ B˜ (s˜,τ˜) are of the same type.
≥
Lemma 2.25. [97, Lemma 2] Let p 2 be a positive integer and let
P ,P ,...,P be n×n nonnegative matrices with positive diagonal entries,
| 1 2 | p   |     |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
then
|         |        | P            | P ···P | ≥γ(P | +P             | +···+P | ),  |     |     |
| ------- | ------ | ------------ | ------ | ---- | -------------- | ------ | --- | --- | --- |
|         |        |              | 1 2    | p    | 1              | 2      | p   |     |     |
| where γ | >0 can | be specified |        | from | P , i=1,...,p. |        |     |     |     |
i
Lemma 2.26.Let S ={A ,A ,...,A } be a set of row-stochastic matrices
|     |     | A   |     | 1 2 |     | (cid:7) |     |     |     |
| --- | --- | --- | --- | --- | --- | ------- | --- | --- | --- |
with positive diagonal entries. If the directed graph of A i has a directed span-
ningtree,thenA isSIA.Iftheunionofthedirectedgr(cid:20)aphsofA ,i=1,...,(cid:2),
|     |     | i   |     |     |     |     |     | i   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
has a directed spanning tree, then the matrix product (cid:7) A is SIA.
i
i=1
Proof: The first statement follows from Corollary 2.18 and Lemma 2.19. For
the secondstatement,notethatthe prod(cid:20)uctofrow-st(cid:7)ochasticmatricesisstill
|     |     |     |     |     |     | (cid:7) | ≥γ (cid:7) |     |     |
| --- | --- | --- | --- | --- | --- | ------- | ---------- | --- | --- |
a row-stochastic matrix. Also note that A i A i for some γ >0
|     |     |     |     |     |     | i=1 | i=1 |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
according to Lemma 2.25. Because the union of the directed graphs of the
matrices i(cid:7)n S has a directed spanning tree, it is obvious that the directed
A
(cid:7)
graph of A i has a directed spanning tree. Therefore, it can be seen
|     | i=1 |     | (cid:20) |     |     |     |     |     |     |
| --- | --- | --- | -------- | --- | --- | --- | --- | --- | --- |
that the directed graph of (cid:7) A has a directed spanning tree according to
i
i=1
Lemm(cid:20)a 2.21, which in turn implies, from the first statement of the lemma,
| that (cid:7) | A is | SIA. |     |     |     |     |     |     |     |
| ------------ | ---- | ---- | --- | --- | --- | --- | --- | --- | --- |
| i=1          | i    |      |     |     |     |     |     |     |     |
G
Lemma 2.27.Let n denote the set of all possible directed graphs for the n
|            |        |       |                |     |           | {G  | ),G ),...,G | )}, |       |
| ---------- | ------ | ----- | -------------- | --- | --------- | --- | ----------- | --- | ----- |
| vehicles.3 | If the | union | of directed    |     | graphs    | (t  | (t          | (t  | where |
|            |        |       |                |     |           | n 1 | n 2         | n p |       |
| 3          | G      |       |                |     |           |     |             |     |       |
| Note       | that n | has a | finitenumberof |     | elements. |     |             |     |       |

44 2 Consensus Algorithms for Single-integrator Dynamics
G (t ) ∈ G , has a directed spanning tree and L (t ) is the nonsymmetrical
n i n n i
Laplacian matrix associated with each directed graph G (t ), then the matrix
n i
product
e
−Ln(tp)Δtp···e −Ln(t2)Δt2e −Ln(t1)Δt1
is SIA, where Δt >0 are bounded below.
i
Proof: From (2.3), each matrix −L (t ) satisfies the properties defined in
n i
Lemma 2.4. Thus each −L (t ) can be written as the sum of a nonnegative
n i
matrix M and −η I , where η is the maximum of the diagonal entries
ti ti n ti
of L
n
(t
i
), i = 1,...,p. Note that e−Ln(ti)Δti = e−ηti ΔtieMti Δti ≥ α
i
M
ti
for
some α > 0. Since the union of directed graphs {G (t ),G (t ),...,G (t )}
i n 1 n 2 n p
has a directed spanning tree, we know that the union of the directed graphs
of M has a directed spanning tree, which in turn implies from Lemma 2.21
ti
that the union of the directed graphs of e−Ln(ti)Δti has a directed spanning
tr(cid:7)ee.FromLemma2.25,weknowthate−Ln(tp)Δtp···e−Ln(t2)Δt2e−Ln(t1)Δt1 ≥
γ p e−Ln(ti)Δti forsomeγ >0,whichimplies thatthe abovematrixprod-
i=1
uct also has a directed spanning tree.
From Lemma 2.6, each matrix e−Ln(ti)Δti is a row-stochasticmatrix with
positive diagonal entries, which implies that the above matrix product is
also a row-stochastic matrix with positive diagonal entries. Therefore, from
Lemma 2.26, we know that the above matrix product is SIA.
Lemma 2.28.Let C(t) = [c
ij
(t)] ∈ Rn×n be piecewise c(cid:7)ontinuous for t ∈
[τ,s], where s−τ > 0 is bounded, c ≥ 0, ∀i (cid:6)= j, and c = 0. If the
ij j ij
union of the directed graphs of C(t) for t∈[τ,s] has a directed spanning tree,
then the transition matrix Φ (s,τ) is SIA.
C
Proof: Note that Φ C (t (cid:7)+1 ,t 0 ) = Φ C (t (cid:7)+1 ,t (cid:7) )Φ C (t (cid:7) ,t (cid:7)−1 )···Φ C (t 1 ,t 0 ), where
(cid:2) (cid:2)
t = τ, t = s, and t , j =1,...,(cid:2), denotes the times when C(t) is discon-
0 (cid:7)+1 j
tinuous. FromLemma 2.24,we knowthat the directedgraphof C(t) for each
t∈[t i−1 ,t i ]isasubgraphofthedirectedgraphofΦ C (t i ,t i−1 ),i=1,...,(cid:2)+1.
In other words, if the union of the directed graphs of C(t) has a directed
spanning tree, so does the union of the directed graphs of the corresponding
transition matrices. Also note from Lemma 2.24 that each Φ C (t i ,t i−1 ) is a
row-stochastic matrix with positive diagonal entries. The proof then follows
from Lemma 2.26.
Lemma 2.29.If the union of a set of directed graphs {G [k ],G [k ],...,
n 1 n 2
G [k ]},whereG [k ]∈G ,hasadirectedspanningtree,thenthematrixprod-
n p n j n
uct D [k ]···D [k ]D [k ] is SIA, where D [k ] is the row-stochastic matrix
n p n 2 n 1 n j
in (2.5) associated with each directed graph G [k ].
n j
Pr(cid:7)oof: From Lemma 2.25, we know that D
n
[k
p
]···D
n
[k
2
]D
n
[k
1
] ≥
γ p D [k ]forsomeγ >0.Becausetheunionof{G [k ],G [k ],...,G [k ]}
j=1 n j n 1 n 2(cid:7) n p
hasadirectedspanningtree,weknowthatthedirectedgraphof p D [k ]
j=1 n j
has a directed spanning tree, which in turn implies that the directed graph

2.3 Consensus UnderDynamically Changing Interaction Topologies 45
|     |     |     | D   | ]···D | ]D  |     |     |     |     |
| --- | --- | --- | --- | ----- | --- | --- | --- | --- | --- |
of the matrix product [k [k [k ] has a directed spanning tree.
|     |     |     | n   | p   | n 2 | n 1 |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Also the matrix product D [k ]···D [k ]D [k ] is a row-stochastic matrix
|     |     |     |     | n p | n   | 2 n | 1   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
with positive diagonal entries because row-stochastic matrices with positive
diagonal entries are closed under matrix multiplication. From Lemma 2.26,
we know that the matrix product D [k ]D [k ]···D [k ] is SIA.
|     |     |     |     |     | n 1 | n 2 | n   | p   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     | S   | ={S |     | }   |     |     |     |
Lemma 2.30. [253] Let 1 ,S 2 ,...,S k be a finite set of SIA matrices
with the property that for each sequence S ,S ,...,S of positive length,
|     |     |     |     |     |     | i1  | i2  | ij  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
the matrix product S S ···S is SIA. Then for each infinite sequence
|                  |               |        | ij ij−1                       |     | i1       |      |      |       |        |
| ---------------- | ------------- | ------ | ----------------------------- | --- | -------- | ---- | ---- | ----- | ------ |
| S i1 ,S          | i2 ,... there | exists | a column                      |     | vector ν | such | that |       |        |
|                  |               |        | lim                           | S S | ···S     | =1   | νT.  |       | (2.15) |
|                  |               |        | j→∞                           | ij  | ij−1     | i1   | n    |       |        |
| Inaddition,whenS |               |        | isaninfiniteset,χ(W)<1,whereW |     |          |      |      | =S S  | ···S   |
|                  |               |        |                               |     |          |      |      | k1 k2 | kNt+1  |
n×n
and N t is the number of different types of all SIA matrices (see Ap-
pendix C for definitions). Furthermore, if there exists a constant 0 ≤ d < 1
| satisfying | χ(W)≤d,   |     | then  | (2.15)            | also holds. |     |           |     |     |
| ---------- | --------- | --- | ----- | ----------------- | ----------- | --- | --------- | --- | --- |
| 2.3.1      | Consensus |     | Using | a Continuous-time |             |     | Algorithm |     |     |
In this subsection, we will focus on demonstrating that under certain condi-
tions, the existence of a directed spanning tree jointly is sufficient for consen-
sus under dynamically changing interaction topologies using continuous-time
| algorithm | (2.2). |     |     |     |     |     |     |     |     |
| --------- | ------ | --- | --- | --- | --- | --- | --- | --- | --- |
Tomaketheproblemmathematicallytractable,weusethenotionofdwell
time introduced in [97,146].The idea is that there is a finite, lowerbound on
|     |     | A   |     |     |     |     |     |     | A   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
the time between (t) switches, and that between the switching times,
|     |     |     | n   |     |     |     |     |     | n   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
is constant. This implies that both A (t) and L (t) are piecewise constant.
|          |       |           |           |              | n      |      | n   |       |        |
| -------- | ----- | --------- | --------- | ------------ | ------ | ---- | --- | ----- | ------ |
| Equation | (2.3) | can       | therefore | be rewritten |        | as   |     |       |        |
|          |       | ξ˙(t)=−[L |           | )⊗I          |        | t∈[t |     |       |        |
|          |       |           |           | (t           | ]ξ(t), |      | ,t  | +τ ), | (2.16) |
|          |       |           |           | n i          | m      |      | i   | i i   |        |
where τ > 0 is the dwell time and t ,t ,t ,... is the infinite time sequence
|     | i   |     |     |     | 0 1 | 2   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
−t
| such that | t i+1 | i   | =τ i . |     |     |     |     |     |     |
| --------- | ----- | --- | ------ | --- | --- | --- | --- | --- | --- |
LetΘ¯
|     | beafinitesetofarbitrarypositivenumbers.LetΥ |     |     |     |     |     |     | beaninfinite | set |
| --- | ------------------------------------------- | --- | --- | --- | --- | --- | --- | ------------ | --- |
generated from the set Θ¯, which is closed under addition and multiplications
∈Υ,
by positive integers. We assume that τ i i=0,1,.... By choosing the set
Θ¯ properly, the dwell time can be chosen from an infinite set Υ.
Wehavethefollowingtheoremforalgorithm(2.2)underdirectedswitching
| interaction | topologies. |     |     |     |     |     |     |     |     |
| ----------- | ----------- | --- | --- | --- | --- | --- | --- | --- | --- |
Theorem 2.31.Let t ,t ,... be the infinite time sequence such that τ =
|     |     |     | 1 2 |     |     |     |     |     | i   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
t −t ∈Υ, i=0,1,.... Let G (t )∈G be the directed graph at time t=t
| i+1 | i   |     |     | n   | i n |     |     |     | i   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     | ∈   | Ψ¯, | Ψ¯  |     |     |     |     |     |     |
and a ij (t i ) where is a finite set of arbitrary nonnegative numbers.
Continuous-time algorithm (2.2) achieves consensus asymptotically if there
exists an infinite sequence of contiguous, nonempty, uniformly bounded, time

46 2 Consensus Algorithms for Single-integrator Dynamics
intervals [t ,t ),j =1,2,...,startingatt =t ,withthepropertythatthe
ij ij+1 i1 0
union of the directed graphs across each such interval has a directed spanning
tree. Furthermore, if the union of the directed graphs after some finite time
does not have a directed spanning tree, then consensus cannot be achieved
asymptotically.
Proof: Thesetofallpossiblematricese−Ln(ti)τi,where τ ∈Υ,underdynam-
i
ically changing interaction topologies and weights a (t), can be chosen or
ij
constructed by matrix multiplications from the set E¯ = {e−Ln(ti)τi,τ ∈ Θ¯}.
i
Clearly E¯ is finite because G , Ψ¯, and Θ¯ are finite.
n
Note that the union of the directed graphs across each time interval
[t ,t ) has a directed spanning tree. Let {L (t ),L (t ),...,
ij ij+1 n ij n ij+1
L n (t ij+1−1 )} be a set ofnonsymmetricalLaplacianmatricescorrespondingto
each directed graph in [t ,t ). Following Lemma 2.27, the matrix product
ij ij+1
Φ(t ,t ) = e −Ln(tij+1−1)τij+1−1···e −Ln(tij+1)τij+1e −Ln(tij )τij, j = 1,2,...,
ij+1 ij
is SIA. Because E¯ is finite and [t ,t ) is uniformly bounded, the set of all
ij ij+1
matrices Φ(t ,t ) is finite.
ij+1 ij
Note that the solution of (2.16) is given by
ξ(t)=[e −Ln(tik+1 )(t−tik+1 )Φ(t
ik+1
,t
ik
)···Φ(t
i2
,t
i1
)⊗I
m
]ξ(0),
where i is the largest nonnegative integer satisfying t ≤ t. It follows
k+1 ik+1
fromthefirststatementofLemma2.30thatΦ(t ,t )···Φ(t ,t )→1 νT,
ik+1 ik i2 i1 n
as k → ∞. It also follows from Lemma 2.6 that e −Ln(tik+1 )(t−tik+1 ) is a row-
stochastic matrix satisfying e −Ln(tik+1 )(t−tik+1 )1
n
νT = 1
n
νT. Therefore, we
concludethate −Ln(tik+1 )(t−tik+1 )Φ(t
ik+1
,t
ik
)···Φ(t
i2
,t
i1
)→1
n
νT,ast→∞,
under the assumption of the theorem,which provesthe first statement of the
theorem.
For the second statement, if the union of the directed graphs after some
finite time tˆdoes not have a directed spanning tree, then during the infinite
timeinterval[tˆ,∞),thereexistatleasttwovehiclessuchthatthereisnopath
in the union of the directed graphs that contains these two vehicles, which
implies that the information states of these vehicles cannot agree.
Corollary 2.32. [97] Let t ,t ,... be the infinite time sequence such that
1 2
t −t = τ , i = 0,1,..., where τ is a constant. Let G (t ) ∈ G be the
i+1 i D D n i n
undirected graph at time t = t . Suppose that a (t ) = 1 if (j,i) ∈ E and
i ij i n n
a (t )=0 otherwise, ∀j (cid:6)=i, at time t=t . Continuous-time algorithm (2.2)
ij i i
achieves consensus asymptotically if there exists an infinite sequence of con-
tiguous, nonempty, uniformly bounded, time intervals [t ,t ), j =1,2,...,
ij ij+1
starting at t =t , with the property that the union of the undirected graphs
i1 0
across each such interval is connected.
Consider,ontheotherhand,themorerealisticassumptionthatA (t)and
n
hence L (t) are piecewise continuous.
n

2.3 Consensus UnderDynamically Changing Interaction Topologies 47
|     |     |     | A   | ∈ Rn×n |     |
| --- | --- | --- | --- | ------ | --- |
Theorem 2.33.Suppose that (t) = [a (t)] in (2.3) is piecewise
|     |     |     | n   | ij  |     |
| --- | --- | --- | --- | --- | --- |
continuousanditsnonzeroandhencepositiveentriesarebothuniformlylower
∈[a,a¯],where0<a<a¯,if(j,i)∈E
| andupperbounded(i.e.,a |     | ij  |     |     | n anda ij =0 |
| ---------------------- | --- | --- | --- | --- | ------------ |
otherwise). Let t ,t ,... be the time sequence corresponding to the times at
0 1
whichA (t)switches,whereitisassumedthatt −t ≥t ,∀i=1,2,...with
|     | n   |     |     | i i−1 L |     |
| --- | --- | --- | --- | ------- | --- |
t a positive constant.4 Continuous-time algorithm (2.2) achieves consensus
L
asymptotically if there exists an infinite sequence of contiguous, nonempty,
uniformly bounded time-intervals [t ij ,t ij+1 ), j = 1,2,..., starting at t i1 =t 0 ,
with the property that the union of directed graphs G (t) across each such
n
| interval | has a directed | spanning | tree. |     |     |
| -------- | -------------- | -------- | ----- | --- | --- |
Proof: With t ,t ,... the switching time sequence, each interval [t ,t ) can
|     | 0 1 |     |     |     | i−1 i |
| --- | --- | --- | --- | --- | ----- |
be dividedintoafinite orinfinite numberofsubintervalssuchthatthe length
of each subinterval is greater than or equal to t but less than or equal to
L
G
t M =2t L , and on each subinterval the directed graph n (t) is time invariant
andthe weightsa (t)arecontinuous.Relabelthese subintervalsass ,s ,...,
|     | ij  |     |     |     | 0 1 |
| --- | --- | --- | --- | --- | --- |
where s =t . Note that for t∈[s ,s ], −L (t) is continuous and satisfies
| 0              | 0        |       | j−1 j | n   |     |
| -------------- | -------- | ----- | ----- | --- | --- |
| the assumption | of Lemma | 2.24. |       |     |     |
With (2.2), the solution of (2.1) can be denoted as ξ(t) = [Φ(t,t ) ⊗
0
I ]ξ(t ) = [Φ(t,s )Φ(s ,s )···Φ(s ,s )⊗I ]ξ(s ), where Φ is the transi-
| m 0 | j   | j j−1 | 1 0 | m 0 |     |
| --- | --- | ----- | --- | --- | --- |
−L
tion matrix corresponding to (t). Note that all nonzero and hence pos-
n
itive entries of A (t) are both uniformly lower and upper bounded. It fol-
n
|     |     | L   |     | G   |     |
| --- | --- | --- | --- | --- | --- |
lows that all entries of n (t) are within a compact set. If n (t) is switching
with time, there are a finite number of possible interaction topologies. For
each possible interaction topology, note that L (t) has the same structure in
n
the sense that positive, zero, and negative entries are in the same places for
t ∈[s ,s ]. From Lemma 2.24, each transition matrix Φ(s ,s ) is a row-
| j−1 | j   |     |       |     | j j−1 |
| --- | --- | --- | ----- | --- | ----- |
|     |     | ≤   | −s ≤t |     |       |
stochastic matrix, where t L s j j−1 M , and Φ(s j ,s j−1 ) is of constant
type over this interval for each possible interaction topology. Combining the
above arguments with the fact that Φ(s ,s ) is a continuous function of
|     |     |     | j   | j−1 |     |
| --- | --- | --- | --- | --- | --- |
∈
(cid:2) (t) for t [s j−1 ,s ], we see that each nonzero and hence positive entry
| ij  |     | j   |     |     |     |
| --- | --- | --- | --- | --- | --- |
of Φ(s ,s ) is uniformly lower bounded for each possible interaction topol-
j j−1
ogy. It is straightforward to see that there are only finitely many types for
Φ(s ,s j−1 ). We know that there exists a sequence of unions of the directed
j
graphs across some time intervals and each union is uniformly bounded and
Φ(k)
has a directed spanning tree. Thus the transition matrix for each union
is a product of finitely many matrices Φ(s ,s ). From Lemma 2.22, the
|     |     |     |     | ki ki−1 |     |
| --- | --- | --- | --- | ------- | --- |
Φ(k)
type of is uniquely decided by the order and type of each element in its
product. Also,fromLemma 2.28,we knowthat eachΦ(k) is SIA. In addition,
notingthatthedirectedgraphofeachΦ(k)
hasadirectedspanningtree,wesee
thatanyfinite numberofproductsofΦ(k) is alsoSIAaccordingto thesecond
statementofLemma2.26.NotingthatΦ(k) canhaveonlyfinitelymanytypes,
Φ(k),
we see that for each type of its nonzero and hence positive entries are
4 That is, it is assumed that the interaction topology and weights a (t) cannot
ij
| switch | infinitely fast. |     |     |     |     |
| ------ | ---------------- | --- | --- | --- | --- |

48 2 Consensus Algorithms for Single-integrator Dynamics
uniformlylowerbounded.LetW =Φ(j1)Φ(j2)···Φ(jNt+1).Fromthesecondar-
gument of Lemma 2.30,we know that χ(W)<1. Note that W canhave only
finite many types, denoted asW . To show that χ(W)≤d<1,it is sufficient
t
to show that for each type, there exists a 0 ≤ d < 1 such that χ(W) ≤ d .
i i
This can be verified by noting that the nonzero and hence positive entries of
W are uniformly lower bounded for each type. Let d=max{d ,d ,...,d }.
1 2 Wt
Itisobviousthatχ(W)≤d.FromthethirdstatementofLemma2.30,wecan
show that Φ(t,t ) → 1 νT, where ν is a column vector, under the condition
0 n
of the theorem. This proves the theorem.
Remark 2.34. The leader-followingscenariois a specialcaseofTheorem2.33.
If there is one vehicle in the team that does not have any incoming edge, but
theunionofthedirectedgraphshasadirectedspanningtree,thenthisvehicle
must be the root of the directed spanning tree, or in other words, the team
leader. Because consensus is guaranteed, the information states of the other
vehicles asymptotically converge to the information state of the team leader.
(cid:13)(cid:14)
Wehavethefollowingtheoremforalgorithm(2.9)underdirectedswitching
interaction topologies.
Theorem 2.35.Given consensus algorithm (2.9), under the assumption of
Theorem 2.33, if (cid:9)w −w (cid:9) is uniformly bounded, so is (cid:9)ξ −ξ (cid:9), ∀i(cid:6)=j.
i j i j
Proof: We assume that ξ ∈ R and w ∈ R for simplicity. However, the
i i
proof holds for ξ ∈ Rm and w ∈ Rm by introducing the Kronecker
i i
product. Let ξ = (cid:2) ξ − ξ , w = (cid:2) w − w , ξ˜ = [ξ ,ξ ,...,ξ ]T, and
ij i j ij i j 12 13 1n
w˜ =[w ,w ,...,w ]T. With (2.9), (2.1) can be written as
12 13 1n
ξ˜˙ =Q(t)ξ˜+w˜, (2.17)
where Q(t) ∈ R(n−1)×(n−1) is switching with time. Under the assumption of
Theorem 2.33, ξ˜(t) → 0 uniformly in t , as t → ∞, when w = 0. However,
0 i
unlike the proof of Theorem 2.14, for a linear time-varying system (LTV)
like (2.17), asymptotical stability does not necessarily imply bounded-input
bounded-state stability (see Appendix E). We will show that (2.17) is uni-
formly asymptoticallystableunderthe conditionthatw =0.With(2.2),the
i
solution of (2.1) is given by ξ(t) = Φ(t,0)ξ(0), t ≥ 0, where the transition
matrix Φ(t,0) ∈ Rn×n is a row-stoch(cid:7)astic matrix as shown in Lemma 2.23.
As a result, it follows that ξ (t) = n β (t)ξ (0), where β (t) ≥ 0 and
(cid:7) i j=1 ij j ij
n β (t) = 1. Therefore, it follows that max ξ (t) ≤ max ξ (0) and
j=1 ij j j j j
min ξ (t)≥min ξ (0), which in turn imply that
j j j j
max|ξ (t)|≤maxξ (0)−minξ (0). (2.18)
1j j j
j(cid:5)=1 j j
Let j =argmin ξ (0) and ¯j =argmax ξ (0). Note that
j j j j

2.3 Consensus UnderDynamically Changing Interaction Topologies 49
|     |     |               |            | (cid:21)         | (cid:21)              | (cid:21) | (cid:21)    |     |     |
| --- | --- | ------------- | ---------- | ---------------- | --------------------- | -------- | ----------- | --- | --- |
|     |     |               |            | (cid:21)         | (cid:21)              | (cid:21) | (cid:21)    |     |     |
|     |     | maxξ (0)−minξ |            | (0)=(cid:21)ξ¯jj | (0)(cid:21)=(cid:21)ξ | (0)−ξ    | (0)(cid:21) |     |     |
|     |     | j             |            | j                |                       | 1j       | 1¯j         |     |     |
|     |     | j(cid:21)     | (cid:21) j |                  |                       |          |             |     |     |
(cid:21) (cid:21)
|     |     | (cid:21)        | (cid:21) (cid:21) | (cid:21)≤2max|ξ |       |     |     |     |        |
| --- | --- | --------------- | ----------------- | --------------- | ----- | --- | --- | --- | ------ |
|     |     | ≤ (cid:21)ξ (0) | (cid:21)+ ξ (0)   |                 | (0)|. |     |     |     | (2.19) |
|     |     | 1j              | 1¯j               |                 | 1j    |     |     |     |        |
j(cid:5)=1
Combini(cid:18)ng (2(cid:18).18) and(cid:18)(2.19(cid:18)) gives max |ξ (t)| ≤ 2max |ξ (0)|, which
|         |                       |                          |          | j(cid:5)=1 | 1j   |          | j(cid:5)=1 | 1j     |     |
| ------- | --------------------- | ------------------------ | -------- | ---------- | ---- | -------- | ---------- | ------ | --- |
|         | (cid:18)              | (cid:18) (cid:18)        | (cid:18) |            |      |          |            |        |     |
|         | (cid:18)ξ˜(t)(cid:18) | ≤ 2(cid:18)ξ˜(0)(cid:18) |          | ∀t ≥       |      |          |            |        |     |
| implies |                       |                          |          | , 0,       | when | w i = 0. | Therefore, | (2.17) | is  |
|         |                       | ∞                        | ∞        |            |      |          |            |        |     |
uniformly stable when w = 0. Combining the above arguments, it follows
i
that (2.17) is uniformly asymptotically stable when w = 0, which in turn
i
implies that (2.17) is uniformly exponentially stable from Theorem E.3.(cid:18)A(cid:18)c-
(cid:18) (cid:18)
cording to Lemma E.6,it follows that if (cid:9)w˜(cid:9) is uniformly bounded, so is (cid:18)ξ˜(cid:18).
Equivalently,itfollowsthatif(cid:9)w −w (cid:9)isuniformlybounded,sois(cid:9)ξ −ξ (cid:9),
|     |     |     |     | i j |     |     |     | i   | j   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
∀i(cid:6)=j.
Remark 2.36. Theorem 2.35 implies that with (2.9), (2.1) is ISS under the
| assumption |           | of the theorem. | (cid:13)(cid:14) |     |           |     |     |     |     |
| ---------- | --------- | --------------- | ---------------- | --- | --------- | --- | --- | --- | --- |
| 2.3.2      | Consensus | Using           | a Discrete-time  |     | Algorithm |     |     |     |     |
Inthissubsection,wewillshowthatundercertainconditionsthe existenceof
a directed spanning tree jointly is sufficient for consensus under dynamically
changing interaction topologies using discrete-time algorithm (2.4).
Wehavethefollowingtheoremforalgorithm(2.4)underdirectedswitching
| interaction |     | topologies. |     |     |     |     |     |     |     |
| ----------- | --- | ----------- | --- | --- | --- | --- | --- | --- | --- |
Theorem 2.37.LetG [k]∈G bethedirectedgraphat discrete-timeindexk.
|     |     |         | n n |     |     |     |     |     |     |
| --- | --- | ------- | --- | --- | --- | --- | --- | --- | --- |
|     |     | [k]∈Ψ¯, | Ψ¯  |     |     |     |     |     |     |
Also let d ij where is a finite set of nonnegative numbers that are no
larger than one. Discrete-time algorithm (2.4) achieves consensus asymptot-
ically if there exists an infinite sequence of contiguous, nonempty, uniformly
bounded time intervals [k j ,k j+1 ), j = 1,2,..., starting at k 1 = 0, with the
property that the union of the directed graphs across each such interval has a
directed spanning tree. Furthermore, if the union of the directed graphs after
somefinitetimedoes nothave adirectedspanningtree,thenconsensuscannot
| be achieved |     | asymptotically. |     |     |     |     |     |     |     |
| ----------- | --- | --------------- | --- | --- | --- | --- | --- | --- | --- |
Proof:ThesetofallpossiblematricesD [k]underdynamicallychanginginter-
n
|                             |     |     |     | [k]isfinitebecausebothG |     |     | andΨ¯ |            |     |
| --------------------------- | --- | --- | --- | ----------------------- | --- | --- | ----- | ---------- | --- |
| actiontopologiesandweightsd |     |     |     |                         |     |     |       | arefinite. |     |
|                             |     |     |     | ij                      |     |     | n     |            |     |
Notethatthe unionofthedirectedgraphsacrosseachtimeinterval[k ,k )
|     |            |          |       |          |        |           |      | j    | j+1 |
| --- | ---------- | -------- | ----- | -------- | ------ | --------- | ---- | ---- | --- |
|     |            |          |       | {D       | ],D    | +1],...,D |      | −1]} |     |
| has | a directed | spanning | tree. | Let n [k | j n [k | j         | n [k | j+1  | be  |
the set of row-stochastic matrices corresponding to each directed graph in
| [k ,k | ).FollowingLemma2.29,thematrixproductD |     |     |     |     | [k  | −1]···D |     | [k + |
| ----- | -------------------------------------- | --- | --- | --- | --- | --- | ------- | --- | ---- |
| j     | j+1                                    |     |     |     |     | n   | j+1     |     | n j  |
1]D
[k ],j =1,2,...,isSIA.ThenbyfollowingaproofsimilartothatinThe-
n j
orem 2.31, the first statement of the theorem is demonstrated.
If the union of the directed graphs after some finite k does not have a
directedspanningtree,thenduringtheinfinitetimeinterval[k,∞),thereexist

| 50 2 | Consensus Algorithms | for Single-integrator |     | Dynamics |     |
| ---- | -------------------- | --------------------- | --- | -------- | --- |
at least two vehicles such that there is no path in the union of the directed
graphs that contains these two vehicles, which implies that the information
| states of | these vehicles | cannot agree. |     |     |     |
| --------- | -------------- | ------------- | --- | --- | --- |
G ∈ G
Corollary 2.38. [97] Let [k] be undirected graph at discrete-time
|     |     | n   | n   |     |     |
| --- | --- | --- | --- | --- | --- |
index k. Also let d [k] ∈ Ψ¯, where Ψ¯ is a finite set of nonnegative numbers
ij
that are no larger than one. Discrete-time algorithm (2.4) achieves consensus
asymptotically if there exists an infinite sequence of contiguous, nonempty,
uniformly bounded time intervals [k ,k ), j = 1,2,..., starting at k = 0,
|     |     |     | j j+1 |     | 1   |
| --- | --- | --- | ----- | --- | --- |
with the property that the union of the undirected graphs across each such
| interval | is connected. |     |     |     |     |
| -------- | ------------- | --- | --- | --- | --- |
Again, consider, on the other hand, the more realistic assumption that
D
| [k] is | piecewise constant. |     |     |     |     |
| ------ | ------------------- | --- | --- | --- | --- |
n
Theorem 2.39.Suppose that the row-stochastic matrix D [k] = d [k] ∈
n ij
Rn×n in (2.5) is piecewise constant and its nonzero and hence positive entries
∈[d,1],where0<d<1,
arebothuniformlylowerandupperbounded(i.e.,d
ii
and for all i (cid:6)= j, d ∈ [c,c¯], where 0 < c < c¯< 1 if (j,i) ∈ E and d = 0
|     | ij  |     |     |     | n ij |
| --- | --- | --- | --- | --- | ---- |
otherwise). Discrete-timealgorithm (2.4)achieves consensusasymptotically if
there exists an infinite sequence of contiguous, nonempty, uniformly bounded
time intervals [k ,k ), j = 1,2,..., starting at k = 0, with the property
|     | j j+1 |     |     | 1   |     |
| --- | ----- | --- | --- | --- | --- |
that the union of the directed graphs across each such interval has a directed
| spanning | tree. |     |     |     |     |
| -------- | ----- | --- | --- | --- | --- |
Proof: Note that D [k] is a row-stochastic matrix with positive diagonal en-
n
D
tries. In addition, for each possible interaction topology, n [k] is of the same
type and its nonzero and hence positive entries are uniformly lowerbounded.
We know that there exists a sequence of unions of the directed graphs across
some time intervals, and each union is uniformly bounded and has a directed
|     | D(i) |     | D   |     |     |
| --- | ---- | --- | --- | --- | --- |
spanning tree. Let n be the product of n [k] overthe ith union. Note that
each D(i) is SIA from Lemma 2.26. As a result, the proof follows the same
n
D(i)
reasoning as that of Theorem 2.33 with playing the role of Φ(k).
n
| 2.3.3 Simulation | Results |     |     |     |     |
| ---------------- | ------- | --- | --- | --- | --- |
In this subsection, we simulate information consensus for five vehicles un-
der dynamically changing interaction topologies using discrete-time algo-
rithm (2.4) and continuous-time algorithm (2.16), respectively.
For simplicity, we constrain the possible interaction topologies for these
|               |            | Gs {G | ,G ,G     | ,G ,G     | },          |
| ------------- | ---------- | ----- | --------- | --------- | ----------- |
| five vehicles | within the | set = |           |           | as shown in |
|               |            | 5     | 5(1) 5(2) | 5(3) 5(4) | 5(5)        |
Fig.2.5,whichisobviouslyasubsetofG .Fordiscrete-timealgorithm(2.4),we
5
assumethattheinteractiontopologyswitchesrandomlyinGsateachdiscrete-
5
time index k, where k = 0,1,2,... and the sample period is 0.5 seconds.
For the continuous-time algorithm, we assume that the interaction topology

2.3 Consensus UnderDynamically Changing Interaction Topologies 51
Gs
switches randomly in at each random time t = t , k = 0,1,2,.... The
|     |     |     | 5   |     |     | k   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
nonzero weights d in (2.4) and a in (2.16) are chosen arbitrarily a priori
|     |     | ij  |     | ij  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
Gs
for each directed graph in to satisfy the constraints of Theorems 2.37
5
| and 2.31, | respectively.                                                    |                  |                                                                  |                                                                  |                                                                  |                  |                                                                  |
| --------- | ---------------------------------------------------------------- | ---------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------- | ---------------------------------------------------------------- |
|           | G                                                                | 5(1)             | G 5(2)                                                           | G 5(3)                                                           | G 5(4)                                                           |                  | G 5(5)                                                           |
|           | (cid:10)(cid:14)(cid:11)(cid:15)(cid:12)(cid:16)(cid:13)(cid:17) |                  | (cid:10)(cid:14)(cid:11)(cid:15)(cid:12)(cid:16)(cid:13)(cid:17) | (cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) | (cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) |                  | (cid:10)(cid:14)(cid:11)(cid:15)(cid:12)(cid:16)(cid:13)(cid:17) |
|           |                                                                  | 3                | 1                                                                | 1                                                                | 3                                                                |                  | 4                                                                |
|           |                                                                  | (cid:14)(cid:14) | (cid:14)(cid:14)                                                 | (cid:14)(cid:14)                                                 | (cid:14)(cid:14)                                                 |                  | (cid:14)(cid:14)                                                 |
|           | (cid:10)(cid:14)(cid:11)(cid:15)(cid:12)(cid:16)(cid:13)(cid:17) |                  | (cid:10)(cid:14)(cid:11)(cid:15)(cid:12)(cid:16)(cid:13)(cid:17) | (cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) | (cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) |                  | (cid:10)(cid:14)(cid:11)(cid:15)(cid:12)(cid:16)(cid:13)(cid:17) |
|           |                                                                  | 1                | 2                                                                | 3                                                                | 4                                                                |                  | 5                                                                |
|           | Fig.                                                             | 2.5.             | Possible                                                         | interaction topologies                                           |                                                                  | for fivevehicles |                                                                  |
Note that each directed graph in Gs does not have a directed spanning
5
tree. However, as can be seen from Fig. 2.6, the union of these graphs has a
directedspanningtree.BecausetheswitchingamongthedirectedgraphsinGs
5
israndom,theconditionforconsensuswillbegenericallysatisfied.Simulation
results show that asymptotic consensus is achieved using both discrete-time
| algorithm | (2.4) | and continuous-time |     | algorithm | (2.16). |     |     |
| --------- | ----- | ------------------- | --- | --------- | ------- | --- | --- |
(cid:6)(cid:6)
|     |     | (cid:10)(cid:14)(cid:11)(cid:15)(cid:12)(cid:16)(cid:13)(cid:17)(cid:2)(cid:2) | (cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) | (cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) | (cid:15)(cid:15)(cid:10)(cid:14)(cid:11)(cid:15)(cid:12)(cid:16)(cid:13)(cid:17) | (cid:15)(cid:15)(cid:10)(cid:14)(cid:11)(cid:15)(cid:12)(cid:16)(cid:13)(cid:17) |     |
| --- | --- | ------------------------------------------------------------------------------ | ---------------------------------------------------------------- | ---------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | --- |
|     |     | 2                                                                              | 1                                                                | (cid:8)(cid:8) 3                                                 | 4                                                                                | 5                                                                                |     |
|     |     |                                                                                | Fig.                                                             | 2.6. Theunion                                                    | of G                                                                             | s                                                                                |     |
5
The initial information state is selected arbitrarily as 0.2∗i, i=1,...,5.
Figure2.7showstheconsensusresultsusingbothdiscrete-timealgorithm(2.4)
andcontinuous-timealgorithm(2.16).Note thatconsensusis reachedinboth
cases.
Considernowaleader-followingscenariowherethedirectedgraphswitches
| G(cid:7) (cid:2) | Gs \ | G    |           |          |         |      |                   |
| ---------------- | ---- | ---- | --------- | -------- | ------- | ---- | ----------------- |
| in =             |      | . As | a result, | there is | no edge | from | node 3 to node 1. |
| 5                | 5    | 5(1) |           |          |         |      |                   |
In this case, the union of the directed graphs still has a directed spanning
tree. However, unlike the previous case, there is no incoming edge to node 1.
Figure2.8showstheconsensusresultsusingbothdiscrete-timealgorithm(2.4)
and continuous-time algorithm (2.16). Note that ξ (t) (respectively, ξ [k]),
i i
i=2,...,5,convergesasymptoticallytoξ (0)(respectively,ξ [0])asexpected.
|     |     |     |     | 1   |     |     | 1   |
| --- | --- | --- | --- | --- | --- | --- | --- |

| 52  | 2 Consensus Algorithms | for Single-integrator | Dynamics |     |     |
| --- | ---------------------- | --------------------- | -------- | --- | --- |
Discrete−time update law
1
0.8
]k[ξ
i 0.6
0.4
0.2
| 0   | 5 10 | 15 20 25 | 30 35 | 40 45 | 50  |
| --- | ---- | -------- | ----- | ----- | --- |
Continuous−time update law
1
0.8
)t(ξ
i 0.6
0.4
0.2
| 0   | 5 10 | 15 20 25 | 30 35 | 40 45 | 50  |
| --- | ---- | -------- | ----- | ----- | --- |
Time (s)
Fig. 2.7. Consensus with G 5[k] and G 5(t ) randomly switching from G s
|     |     |     | k   |     | 5   |
| --- | --- | --- | --- | --- | --- |
2.4 Notes
The results in this chapter are based mainly on [187,190,192,193]. Variant
forms of continuous-time consensus algorithm (2.2) are proposed in [69,97,
126,158,190], and variant forms of discrete-time consensus algorithm (2.4)
are proposed in [97,145,190,236]. Lemma 2.25 is from [97]. Lemma 2.30 is
originally from Lemma 4 and the concluding remarks in [253], but its first
part is restated in [97]. Consensus over an undirected interaction topology is
addressedin [97].In particular,Corollaries2.32 and2.38 are from [97].Aver-
ageconsensusis consideredin[158].In particular,Corollary2.9is from[158].
For other theoretical results and extensions of algorithms (2.2) and (2.4), see
| the references | in Section | 1.2. |     |     |     |
| -------------- | ---------- | ---- | --- | --- | --- |
| Acknowledgment | is given   | to   |     |     |     |
(cid:10)c2005
|     | IEEE. Reprinted, | with permission, | from Wei | Ren and Randal | W.  |
| --- | ---------------- | ---------------- | -------- | -------------- | --- |
Beard,“Consensusseekinginmultiagentsystemsunderdynamicallychanging
interactiontopologies,”IEEETransactions onAutomaticControl,vol.50,no.
| 5, pp. | 655–661,May 2005. |     |     |     |     |
| ------ | ----------------- | --- | --- | --- | --- |
(cid:10)c2005 IEEE. Reprinted, with permission, from Wei Ren, Randal W.
Beard,and Derek B. Kingston,“Multi-agentKalman consensus with relative

2.4 Notes 53
1
0.8
0.6
0.4
0.2
0 5 10 15 20 25 30 35 40 45 50
]k[ξ
i
Discrete−time update law
1
0.8
0.6
0.4
0.2
0
0 5 10 15 20 25 30 35 40 45 50
Time (s)
)t(ξ
i
Continuous−time update law
Fig. 2.8. Consensus with G 5[k] and G 5(t k ) randomly switching from G 5 (cid:2)
uncertainty,”ProceedingsoftheAmericanControlConference,pp.1865–1870,
Portland, OR, 2005.
(cid:10)c2004 IEEE. Reprinted, with permission, from Wei Ren and Randal W.
Beard, “Consensus of information under dynamically changing interaction
topologies,”Proceedings of the American Control Conference, pp. 4939–4944,
Boston, MA, 2004.
(cid:10)c2005 Springer. Reprinted, with permission, from Wei Ren, Randal W.
Beard, and Timothy W. McLain, “Coordination variables and consensus
building in multiple vehicle systems” In V. Kumar, N. E. Leonard, and A.
S. Morse, editors, Cooperative Control, Lecture Notes in Control and Infor-
mation Sciences, vol. 390, pp. 171–188,Springer-Verlag,Berlin, 2005.

3
Consensus Tracking with a Reference State
This chapter studies consensus tracking algorithms for single-integrator dy-
namics, where the information states of all vehicles approach a constant or
time-varying consensus reference state. We first propose and analyze a con-
sensus trackingalgorithmwith a constantconsensus reference state.We then
propose consensus tracking algorithms with a time-varying consensus refer-
encestateandshowconditionsunderwhichconsensusisreachedonthetime-
varying consensus reference state in four cases, a directed fixed interaction
topology, a directed switching interaction topology, bounded control inputs,
and vehicle informationfeedback.The time-varyingconsensus reference state
may be an exogenous signal or evolve according to a nonlinear model. These
consensus tracking algorithms are also extended to achieve relative state de-
viations between vehicles.
3.1 Problem Statement
With algorithm (2.2), the consensus equilibrium is a weighted average of all
vehicles’initialinformationstatesandhenceconstant.Theconstantconsensus
equilibrium,whichdependsontheinteractiontopologyandweightsa ,might
ij
beapriori unknown.Theassumptionofconstantconsensusequilibriummight
not be appropriate when each vehicle’s information state evolves over time,
asoccurs informationcontrolproblems,wherethe formationevolvesin two-,
orthree-dimensionalspace.Inaddition,algorithm(2.2)ensures onlythatthe
information states convergeto a common value but does not allow specifying
a particular value. Although this paradigm is useful for applications such as
cooperative rendezvous where there is not a single correct value, there are
many applications where there is a desired, or reference, information state.
In this case, the convergence issues include both convergence to a common
value, as well as convergence of the common state to its reference value.
Suppose that the team consists of the same n vehicles as in Chapter 2,
together with an additional (virtual) vehicle labeled n+1, which acts as the

56 3 Consensus Tracking with a Reference State
unique (virtual) leader of the team. We call vehicle n+ 1 the team leader
and vehicles 1,...,n the followers. Vehicle n+1 has the information state
(cid:2)
ξ = ξr ∈ Rm, where ξr represents the consensus reference state. The
n+1
consensus reference state satisfies
ξ˙r =f(t,ξr), (3.1)
where f(·,·)is bounded, piecewise continuousint andlocally Lipschitz in ξr.
The main objective of this chapter is to propose and analyze consensus
algorithms to ensure that each vehicle in the team reaches consensus on a
constant or time-varying consensus reference state that evolves with time
or according to nonlinear dynamics when the consensus reference state is
available only to a subgroup of the followers, called subgroup leaders. The
consensustrackingproblemwithaconsensusreferencestateissolvedifξ (t)→
i
ξr(t), i=1,...,n, as t→∞.
(cid:2)
WeusedirectedgraphG =(V ,E )tomodeltheinteractiontopol-
n+1 n+1 n+1
ogy for the n+1 vehicles, where V = {1,...,n+1} is the node set and
n+1
E ⊆V ×V is the edge set. Let A =[a ]∈R(n+1)×(n+1) be the
n+1 n+1 n+1 n+1 ij
adjacency matrix associated with G , where a > 0 if (j,i) ∈ E and
n+1 ij n+1
a = 0 otherwise for all i = 1,...,n and j = 1,...,n+1, and a = 0
ij (n+1)j
for all j = 1,...,n+1. Also let L = [(cid:2) ] ∈ R(n+1)×(n+1) be the non-
n+1 ij
symmetrical Laplacian matrix associated with G , where (cid:2) =−a , i(cid:6)=j,
(cid:7) n+1 ij ij
(cid:2) = n+1 a , i,j =1,...,n+1.
ii j=1,j(cid:5)=i ij
Remark 3.1. Whenweneedtofocusonlyonvehicles1ton(i.e.,thefollowers),
(cid:2)
westilluseG =(V ,E )tomodeltheinteractiontopologyforthenfollowers,
n n n
asinChapter2.Inaddition,A ∈Rn×nandL ∈Rn×narestill,respectively,
n n
the adjacency matrix and the nonsymmetrical Laplacian matrix associated
with G , as in Chapter 2. (cid:13)(cid:14)
n
3.2 Constant Consensus Reference State
In this section, we consider the case where the consensus reference state ξ
r
is constant, that is, f(t,ξr) ≡ 0 in (3.1). For information states with single-
integrator dynamics (2.1), a consensus tracking algorithm with a constant
consensus reference state is given as
(cid:2)n
u =− a (ξ −ξ )−a (ξ −ξr), i=1,...,n, (3.2)
i ij i j i(n+1) i
j=1
whereξ ∈Rm istheithinformationstateanda ,i=1,...,n,j =1,...,n+
i ij
1, is the (i,j) entry of the adjacency matrix A ∈R(n+1)×(n+1). Note that
n+1
algorithm (3.2) corresponds to the leader-following case in Chapter 2 (see
Remark 2.34).

|     |     |     | 3.2 | Constant | Consensus | Reference | State 57 |
| --- | --- | --- | --- | -------- | --------- | --------- | -------- |
We have the following theorem for consensus tracking with a constant
| consensus | reference state. |     |     |     |     |     |     |
| --------- | ---------------- | --- | --- | --- | --- | --- | --- |
Theorem 3.2.Suppose that A is constant. The consensus tracking prob-
n+1
lem with a constant consensus reference state is solved with algorithm (3.2) if
| and only | if directed graph | G   | has | a directed | spanning | tree.1 |     |
| -------- | ----------------- | --- | --- | ---------- | -------- | ------ | --- |
n+1
Proof: Notingthatξr isconstantgivesξ˙r ≡0.With(3.2),(2.1)canbewritten
| in matrix | form as                |     |         |               |        |        |                |
| --------- | ---------------------- | --- | ------- | ------------- | ------ | ------ | -------------- |
|           |                        |     | ξ˙ =−(L |               | ⊗I )ξ, |        |                |
|           |                        |     |         | n+1           | m      |        |                |
|           | (cid:2) [ξT,...,ξT,ξrT |     | L       | ∈R(n+1)×(n+1) |        |        |                |
| where ξ   | =                      | ]T  | and     |               |        | is the | nonsymmetrical |
|           | 1 n                    |     |         | n+1           |        |        |                |
Laplacianmatrix.NotethatallentriesofthelastrowofL arezeroandthe
n+1
|     | L   |     |     |     |     |     | G   |
| --- | --- | --- | --- | --- | --- | --- | --- |
directed graph of n+1 has a directed spanning tree if and only if n+1 has a
directedspanningtree.Thenfromthestatements(ii)and(iii)ofLemma2.11
with L and ξ playing the roles of L and z, respectively, it follows that
| n+1   |                     |     |      | p    |             |     |                |
| ----- | ------------------- | --- | ---- | ---- | ----------- | --- | -------------- |
| →     |                     |     |      | → ∞, |             | G   |                |
| ξ (t) | ξr(0), i = 1,...,n, |     | as t |      | if and only | if  | has a directed |
| i     |                     |     |      |      |             | n+1 |                |
spanningtree.Equivalently,itfollowsthatξ (t)→ξr,i=1,...,n,ast→∞,
i
ξr
| because | is constant. |     |     |     |     |     |     |
| ------- | ------------ | --- | --- | --- | --- | --- | --- |
Example 3.3. Theorem 3.2 is illustrated by the following example. Consider
a team ofn = 4 vehicles together with the virtual team leader, vehicle 5.
ξr ≡
The virtual team leader has a constant consensus reference state 1.
Figures 3.1a–d show, respectively, the interaction topologies among the five
vehicles for Subcases (a)–(d), where node ξr denotes the virtual team leader.
∀j (cid:6)=
In Subcase (a), we let a 15 = 1 and a j5 = 0, 1, which corresponds
to the case where ξr is available to only vehicle 1. In Subcase (b), we let
a = 1, j = 1,...,4, which corresponds to the case where ξr is available to
j5
∀j ∈/ {3,4},
| all followers. | In Subcase | (c), | we let | a   | = a = 1 | and a = | 0,  |
| -------------- | ---------- | ---- | ------ | --- | ------- | ------- | --- |
|                |            |      |        | 35  | 45      | j5      |     |
which corresponds to the case where ξr is available only to vehicles 3 and 4.
∀j (cid:6)=4,
In Subcase (d), we let a 45 =1 and a j5 =0, which corresponds to the
| case where | ξr is available | only | to  | vehicle | 4.  |     |     |
| ---------- | --------------- | ---- | --- | ------- | --- | --- | --- |
Figures 3.2a–d show, respectively, the information states of all vehicles
using (3.2). Note that ξ converges to ξr in each subcase except Subcase (d).
i
Also note that node ξr has a directed path to all other nodes in Subcases
ξr
(a), (b), and (c). However, there does not exist a directed path from node
to all other nodes in Subcase (d). Note that in Subcase (c), neither 3 nor 4
has a directed path to all other followers. However, as shown above, ξ still
i
|            | ξr      |       | (cid:13)(cid:14) |     |     |     |     |
| ---------- | ------- | ----- | ---------------- | --- | --- | --- | --- |
| approaches | in this | case. |                  |     |     |     |     |
1 Note that vehicle n+1 has the state ξr and all entries of the last row of A n+1
arezero.FromLemma2.11,theconditionthatG hasadirectedspanningtree
n+1
is equivalent to the condition that vehicle n+1 is the only vehicle that has a
| directed | path to all | other vehicles |     | on theteam. |     |     |     |
| -------- | ----------- | -------------- | --- | ----------- | --- | --- | --- |

| 58 3 Consensus |     | Tracking with | a Reference | State |     |     |
| -------------- | --- | ------------- | ----------- | ----- | --- | --- |
(cid:5)(cid:5)
|     | (cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25) | (cid:15)(cid:15)(cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9)    | (cid:15)(cid:15)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5)     | (cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25) | (cid:15)(cid:15)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) (cid:15)(cid:15)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) |     |
| --- | ---------------------------------------------------------------- | --------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | --- |
|     | ξr                                                               | 1 (cid:18)(cid:18)(cid:4) (cid:4)                                           | 4                                                                            | ξr(cid:2)(cid:3) (cid:2)(cid:3) (cid:3)                          | 1 (cid:18)(cid:18)(cid:4) (cid:4) 4                                                                                                               |     |
|     |                                                                  |                                                                             | (cid:4)                                                                      | (cid:2)                                                          | (cid:3) (cid:3) (cid:4)                                                                                                                           |     |
|     |                                                                  |                                                                             | (cid:4) (cid:4)                                                              |                                                                  | (cid:2) (cid:3) (cid:3) (cid:4) (cid:4)                                                                                                           |     |
|     |                                                                  |                                                                             | (cid:4)                                                                      |                                                                  | (cid:2) (cid:2) (cid:3) (cid:3) (cid:4)                                                                                                           |     |
|     |                                                                  |                                                                             | (cid:4) (cid:4)                                                              |                                                                  | (cid:2) (cid:3) (cid:3) (cid:3) (cid:4) (cid:4)                                                                                                   |     |
|     |                                                                  | (cid:14)(cid:14)                                                            | (cid:4)                                                                      |                                                                  | (cid:2) (cid:2) (cid:14)(cid:14) (cid:3) (cid:3) (cid:4)                                                                                          |     |
|     |                                                                  |                                                                             | (cid:17)(cid:17)(cid:6)(cid:2)(cid:7)(cid:3)                                 |                                                                  | (cid:16)(cid:16) (cid:3) (cid:17)(cid:17)(cid:6)(cid:2)(cid:17)(cid:17)(cid:7)(cid:3)                                                             |     |
|     |                                                                  | (cid:2)(cid:6)(cid:3)(cid:7) (cid:4)(cid:8) (cid:5)(cid:9) (cid:19)(cid:19) | (cid:8)(cid:4)(cid:9)(cid:5)                                                 |                                                                  | (cid:6)(cid:2) (cid:7)(cid:3) (cid:8)(cid:4) (cid:9)(cid:5) (cid:19)(cid:19) (cid:8)(cid:4)(cid:9)(cid:5)                                         |     |
|     | (a):                                                             | 2                                                                           | 3                                                                            | (b):                                                             | 2 3                                                                                                                                               |     |
|     | (cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25) | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9)(cid:2)(cid:2)      | (cid:5)(cid:5)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5)       | (cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25) | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) (cid:5)(cid:5) (cid:15)(cid:15)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5)  |     |
|     | ξr(cid:3)(cid:3)(cid:3)(cid:3)(cid:3)(cid:3)(cid:3)              | 1 (cid:20)(cid:20) (cid:18)(cid:18)(cid:4)                                  | 4                                                                            | ξr                                                               | 1 (cid:18)(cid:18)(cid:4) 4                                                                                                                       |     |
|     |                                                                  | (cid:4)                                                                     | (cid:4)                                                                      |                                                                  | (cid:4) (cid:4)                                                                                                                                   |     |
|     |                                                                  |                                                                             | (cid:4)                                                                      |                                                                  | (cid:4)                                                                                                                                           |     |
|     |                                                                  | (cid:3) (cid:3)                                                             | (cid:4) (cid:4)                                                              |                                                                  | (cid:4) (cid:4)                                                                                                                                   |     |
|     |                                                                  | (cid:3) (cid:3)                                                             | (cid:4)                                                                      |                                                                  | (cid:4)                                                                                                                                           |     |
|     |                                                                  |                                                                             | (cid:3) (cid:3) (cid:4) (cid:4)                                              |                                                                  | (cid:4) (cid:4)                                                                                                                                   |     |
|     |                                                                  |                                                                             | (cid:3) (cid:3) (cid:17)(cid:17)(cid:6)(cid:2)(cid:17)(cid:17)(cid:7)(cid:3) |                                                                  | (cid:14)(cid:14) (cid:17)(cid:17)(cid:6)(cid:2)(cid:7)(cid:3)                                                                                     |     |
|     |                                                                  | (cid:2)(cid:6) (cid:3)(cid:7) (cid:4)(cid:8) (cid:5)(cid:9)                 | (cid:8)(cid:4)(cid:9)(cid:5)                                                 |                                                                  | (cid:6)(cid:2)(cid:7)(cid:3) (cid:8)(cid:4) (cid:9)(cid:5) (cid:8)(cid:4)(cid:9)(cid:5)                                                           |     |
|     | (c):                                                             | 2 (cid:19)(cid:19)                                                          | 3                                                                            | (d):                                                             | 2 (cid:19)(cid:19) 3                                                                                                                              |     |
Fig. 3.1. Interaction topologies among the five vehicles, where the constant con-
sensus reference state ξr may be available toone or more followers on the team
| 3.3 Time-varying |     | Consensus |     | Reference | State |     |
| ---------------- | --- | --------- | --- | --------- | ----- | --- |
Inthissection,weassumethatthe consensusreferencestatemightbeatime-
varying exogenous signal or evolves according to certain nonlinear dynamics.
|         |         (a) |           |     |         |         (b) |           |
| ------- | ----------- | --------- | --- | ------- | ----------- | --------- |
| 1.5     |             |           |     | 1.5     |             |           |
|         |             | Reference |     |         |             | Reference |
| 1       |             |           |     | 1       |             |           |
| ξ i 0.5 |             |           |     | ξ i 0.5 |             |           |
| 0       |             |           |     | 0       |             |           |
| −0.5    |             |           |     | −0.5    |             |           |
| 0       | 5           | 10 15     | 20  | 0       | 5 10        | 15 20     |
|         | Time (s)    |           |     |         | Time (s)    |           |
|         |         (c) |           |     |         |         (d) |           |
| 1.5     |             |           |     | 1.5     |             |           |
|         |             | Reference |     |         |             | Reference |
| 1       |             |           |     | 1       |             |           |
| ξ i 0.5 |             |           |     | ξ i 0.5 |             |           |
| 0       |             |           |     | 0       |             |           |
| −0.5    |             |           |     | −0.5    |             |           |
| 0       | 5           | 10 15     | 20  | 0       | 5 10        | 15 20     |
|         | Time (s)    |           |     |         | Time (s)    |           |
Fig. 3.2. Consensus tracking with a constant consensus reference state using (3.2)

3.3 Time-varying Consensus Reference State 59
Supposethatξr satisfiesthedynamicsgivenby(3.1).Wefirstshowthatalgo-
rithm(3.2)isnotsufficientforconsensustrackinginatime-varyingconsensus
reference state, as illustrated by the following example.
Example 3.4. Let ξr = cos(t) and consider the four subcases in Example 3.3.
As shown in Fig. 3.3, with algorithm (3.2), none of the subcases solves the
consensustrackingproblemwithatime-varyingconsensusreferencestate. (cid:13)(cid:14)
1.5
1
0.5
0
−0.5
−1
0 5 10 15 20
Time (s)
ξ i
(a)
1.5
Reference
1
0.5
0
−0.5
−1
0 5 10 15 20
Time (s)
ξ i
(b)
Reference
1.5
1
0.5
0
−0.5
−1
0 5 10 15 20
Time (s)
ξ i
(c)
1.5
Reference
1
0.5
0
−0.5
−1
0 5 10 15 20
Time (s)
ξ i
(d)
Reference
Fig. 3.3. Consensus tracking with a time-varying consensus reference state us-
ing (3.2)
We then consider the following algorithm:
(cid:2)n
u =a ξ˙r−a α (ξ −ξr)− a (ξ −ξ ), i=1,...,n, (3.3)
i i(n+1) i(n+1) i i ij i j
j=1
where α are positive constant scalars and a is the (i,j) entry of the ad-
i ij
jacency matrix A with the additional assumption that a = 1 if
n+1 i(n+1)
(n+1,i)∈E and a =0 otherwise.
n+1 i(n+1)

| 60  | 3   | Consensus | Tracking | with a | Reference | State |     |     |
| --- | --- | --------- | -------- | ------ | --------- | ----- | --- | --- |
Example 3.5. Algorithm(3.3)isillustratedbythefollowingexample.Letξr =
cos(t) and consider the four subcases in Example 3.3. As shown in Fig. 3.4,
withalgorithm(3.3),theconsensustrackingproblemissolvedonlyinSubcase
(b). (cid:13)(cid:14)
|     |      |     |         (a) |           |      |     |         (b) |           |
| --- | ---- | --- | ----------- | --------- | ---- | --- | ----------- | --------- |
|     | 1.5  |     |             |           | 1.5  |     |             |           |
|     |      |     |             | Reference |      |     |             | Reference |
|     | 1    |     |             |           |      | 1   |             |           |
|     | 0.5  |     |             |           | 0.5  |     |             |           |
| ξ   | i 0  |     |             |           | ξ i  | 0   |             |           |
|     | −0.5 |     |             |           | −0.5 |     |             |           |
|     | −1   |     |             |           | −1   |     |             |           |
|     | −1.5 |     |             |           | −1.5 |     |             |           |
|     | 0    | 5   | 10          | 15 20     |      | 0   | 5 10        | 15 20     |
|     |      |     | Time (s)    |           |      |     | Time (s)    |           |
|     |      |     |         (c) |           |      |     |         (d) |           |
|     | 1.5  |     |             |           | 1.5  |     |             |           |
|     |      |     |             | Reference |      |     |             | Reference |
|     | 1    |     |             |           |      | 1   |             |           |
|     | 0.5  |     |             |           | 0.5  |     |             |           |
| ξ   | i 0  |     |             |           | ξ i  | 0   |             |           |
|     | −0.5 |     |             |           | −0.5 |     |             |           |
|     | −1   |     |             |           | −1   |     |             |           |
|     | −1.5 |     |             |           | −1.5 |     |             |           |
|     | 0    | 5   | 10          | 15 20     |      | 0   | 5 10        | 15 20     |
|     |      |     | Time (s)    |           |      |     | Time (s)    |           |
Fig. 3.4. Consensus tracking with a time-varying consensus reference state us-
ing (3.3)
We have the following theorem for consensus tracking in a time-varying
| consensus |     | reference | state | using algorithm | (3.3): |     |     |     |
| --------- | --- | --------- | ----- | --------------- | ------ | --- | --- | --- |
Theorem 3.6.Suppose that A is constant. If a ≡ 1, i = 1,...,n,
|     |     |     |     | n+1 |     |     | i(n+1) |     |
| --- | --- | --- | --- | --- | --- | --- | ------ | --- |
then the consensus tracking problem with a time-varying consensus reference
| state  | is solved | with   | algorithm | (3.3).     |           |      |     |     |
| ------ | --------- | ------ | --------- | ---------- | --------- | ---- | --- | --- |
| Proof: | With      | (3.3), | (2.1) can | be written | in matrix | form | as  |     |
ξ˜˙
|     |     |     |     | =−[(L | +Q)⊗I | ]ξ˜, |     |     |
| --- | --- | --- | --- | ----- | ----- | ---- | --- | --- |
|     |     |     |     |       | n     | m    |     |     |
where Q = diag(α ,...,α )∈ Rn×n, L = [(cid:2) ] is then ×n nonsymmetrical
|     |     |     | 1   | n   | n   | ij  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
(cid:7) (cid:2)
Laplacian matrix (i.e., (cid:2) = −a , i (cid:6)= j, and (cid:2) = n a ), and ξ˜=
|     |     |     | ij  | ij  |     | ii  | j=1,j(cid:5)=i | ij  |
| --- | --- | --- | --- | --- | --- | --- | -------------- | --- |

|     |     |     |     |     | 3.3 Time-varying | Consensus | Reference | State | 61  |
| --- | --- | --- | --- | --- | ---------------- | --------- | --------- | ----- | --- |
(cid:2)
[ξ˜T,...,ξ˜T]T withξ˜ = ξ −ξr.Note thatL satisfiesthe property(B.2)with
|     | 1   | n   | i   | i   |     | n   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
p= n. From Theorem C.1, it is straightforward to see that all eigenvalues of
−(L +Q) have negative real parts. Therefore, it follows that ξ˜(t)→0, that
n
| is, | ξ (t)→ξr(t), |     | i=1,...,n, |     | as t→∞. |     |     |     |     |
| --- | ------------ | --- | ---------- | --- | ------- | --- | --- | --- | --- |
i
Remark 3.7. Note thatTheorem3.6doesnotrelyonthe interactiontopology
among the followers. Even if there is no information exchange among the
followers(i.e., A =0 ), algorithm(3.3)stillsolvesthe consensustracking
|     |     |     | n   | n×n |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
ξ˙r
problem with a time-varying consensus reference state, as long as ξr and
are available to all followers. However, this requirement is rather restricted.
(cid:13)(cid:14)
| 3.3.1 | Fundamental |     |     | Consensus | Tracking | Algorithm |     |     |     |
| ----- | ----------- | --- | --- | --------- | -------- | --------- | --- | --- | --- |
ξ˙r
In this subsection, we consider the case where ξr and are available only to
a subgroup of the followers. We propose a consensus tracking algorithm as
(cid:2)n
1
|     |     | u   | =     | a   | (t)[ξ˙ −γ(ξ | −ξ )] |     |     |     |
| --- | --- | --- | ----- | --- | ----------- | ----- | --- | --- | --- |
|     |     | i   | η (t) |     | ij j        | i j   |     |     |     |
i
j=1
1
|     |     |     | +   | a      | (t)[ξ˙r | −γ(ξ −ξr)], i=1,...,n, |     |     | (3.4) |
| --- | --- | --- | --- | ------ | ------- | ---------------------- | --- | --- | ----- |
|     |     |     |     | i(n+1) |         | i                      |     |     |       |
|     |     |     | η   | i (t)  |         |                        |     |     |       |
wherea (t),i=1,...,n,j =1,...,n+1,is the (i,j)entryofadjacencyma-
|     |     | ij  |     |     |     |     |     | (cid:7) |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ------- | --- |
(cid:2) n+1a
| trixA |     | (t)attimet,γ |     | isapositiveconstantscalar,andη |     |     | (t)= |     | (t). |
| ----- | --- | ------------ | --- | ------------------------------ | --- | --- | ---- | --- | ---- |
|       | n+1 |              |     |                                |     |     | i    | j=1 | ij   |
Note that eachvehicle’s informationcontrolinput depends onboth its neigh-
bors’information states and their derivatives2 because of the trackingnature
of (3.4). In practical implementation, the derivatives of the neighbors’ infor-
mation states can be calculated by numerical differentiation. For example,
ξ˙
in the simplest case, on the right side of (3.4) can be approximated by
j
ξj[k]−ξj[k−1],
where k is the discrete-time index and T is the sample period.
T
Next, we will show conditions under which a unique solution exists for
eachcontrolinput andconditions under whichconsensus trackingis achieved
over a directed fixed interaction topology and directed switching interaction
| topologies, |     | respectively. |     |     |     |     |     |     |     |
| ----------- | --- | ------------- | --- | --- | --- | --- | --- | --- | --- |
Wehavethefollowingtheoremforconsensustrackingoveradirectedfixed
| interaction |     | topology: |     |     |     |     |     |     |     |
| ----------- | --- | --------- | --- | --- | --- | --- | --- | --- | --- |
Theorem 3.8.Suppose that A is constant. With (3.4), a unique solution
n+1
for u i , i=1,...,n, exists and the consensus tracking problem is solved if and
| only | if directed |     | graph | G   | has a directed | spanning tree. |     |     |     |
| ---- | ----------- | --- | ----- | --- | -------------- | -------------- | --- | --- | --- |
n+1
2 Thederivativesoftheinformationstatesareequivalenttotheinformationcontrol
|     |          |        |      |       | ξ˙ =u  |     |     |     |     |
| --- | -------- | ------ | ---- | ----- | ------ | --- | --- | --- | --- |
|     | inputsby | noting | from | (2.1) | that j | j . |     |     |     |

62 3 Consensus Tracking with a Reference State
Proof: Noting that all entries of the last row of A are zero and G has
n+1 n+1
a directed spanning tree, it follows th(cid:7)at no other row of A
n+1
can have all
zero entries. It thus follows that η = n+1a (cid:6)= 0, i = 1,...,n. Thus (3.4)
i j=1 ij
is well defined.
Noting that ξ˙ =u , we rewrite (3.4) as
j j
n(cid:2)+1 (cid:2)n (cid:2)n
( a )u − a u −a ξ˙r =−γ[ a (ξ −ξ )+a (ξ −ξr)],
ij i ij j i(n+1) ij i j i(n+1) i
j=1 j=1 j=1
which can be written in matrix form as
[L n×(n+1) ⊗I m ]u=−γ[L n×(n+1) ⊗I m ]ξ, (3.5)
where u = (cid:2) [uT 1 ,...,uT n ,ξ˙rT ]T, ξ = (cid:2) [ξ 1 T,...,ξ n T,ξr (cid:7) T ]T, and L n×(n+1) = [(cid:2) ij ] ∈
Rn×(n+1) is defined as (cid:2) = −a , i (cid:6)= j, (cid:2) = n+1 a , i,j = 1,...,n,
ij ij ii j=1,j(cid:5)=i ij
and (cid:2)
i(n+1)
=−a
i(n+1)
, i(cid:22)=1,...,n(cid:23).
L
Note that L = n×(n+1) and the directed graph of L has a
n+1 0 1×(n+1) n+1
directed spanning tree if and only if G has a directed spanning tree. Also
n+1
note that L satisfies the property (B.2) with p=n+1. From statements
n+1
(iv)and(v)ofLemma2.10,itfollowsthatRank(L )=nifandonlyifG
n+1 n+1
has a directed spanning tree. This in turn implies that Rank(L n×(n+1) ) = n
if and only if G has a directed spanning tree because all of the entries in
n+1
the last row of L n+1 are zero. Rewrite L n×((cid:7)n+1) =[M|b], where M =[m ij ]∈
Rn×n is given as m = −a , i (cid:6)= j, m = n+1 a , and b ∈ Rn is given
ij ij ii j=1,j(cid:5)=i ij
as b = [−a 1(n+1) ,...,−a n(n+1) ]T. Noting that L n×(n+1) has n+1 columns
and each of its row sums is zero, it follows that the last column of L n×(n+1)
depends on its first n columns, where b=−M1 . As a result, it follows that
n
Rank(M) = Rank([M|b]) = n if and only if G has a directed spanning
n+1
tree.
Note that (3.5) can be written as
(M ⊗I )u+(b⊗I )ξ˙r =−γ[(M ⊗I )ξ+(b⊗I )ξr],
m m m m
where u = [uT,...,uT]T and ξ = [ξT,...,ξT]T. Because M has full rank
1 n 1 n
and therefore is invertible if and only if G has a directed spanning tree, it
n+1
followsthat u canbe solveduniquely under the same necessaryand sufficient
condition. The unique solution is given by
u=(M ⊗I ) −1[−γ(M ⊗I )ξ−γ(b⊗I )ξr −(b⊗I )ξ˙r],
m m m m
which can be further written as
u=−γξ+γ(1 ⊗ξr)+1 ⊗ξ˙r. (3.6)
n n

|           |        |     | 3.3 Time-varying |            | Consensus Reference | State | 63  |
| --------- | ------ | --- | ---------------- | ---------- | ------------------- | ----- | --- |
|           |        | −M1 |                  |            |                     | −M−1b |     |
| By noting | that b | =   | and M is         | invertible | implies that        |       | = 1 |
|           |        |     | n                |            |                     |       | n   |
underthesamenecessaryandsufficientcondition,and(M⊗I )−1(b⊗I )=
|     |     |     |     |     |     | m   | m   |
| --- | --- | --- | --- | --- | --- | --- | --- |
M−1b⊗I
| m             | from Lemma | C.8.       |              |      |            |            |      |
| ------------- | ---------- | ---------- | ------------ | ---- | ---------- | ---------- | ---- |
| Noting        | that ξ˙=u, | we rewrite | (3.6)        | as   |            |            |      |
|               |            | ξ˙−1       | ⊗ξ˙r =−γ(ξ−1 |      | ⊗ξr),      |            |      |
|               |            |            | n            |      | n          |            |      |
|               |            | →          | ⊗ξr(t)       | →    | ∞.         |            |      |
| which implies | that       | ξ(t)       | 1            | as t | Therefore, | it follows | that |
n
ξ (t) → ξr(t), i = 1,...,n, as t → ∞, if and only if G has a directed
| i              |     |     |     |     | n+1 |     |     |
| -------------- | --- | --- | --- | --- | --- | --- | --- |
| spanning tree. |     |     |     |     |     |     |     |
Remark 3.9. Notethatwehaveessentiallyuseddistributedalgorithm(3.4)to
achieve the same objective as centralized algorithm (3.6) can achieve. (cid:13)(cid:14)
Example 3.10. Theorem 3.8 is illustrated by the following example. Again,
consider n= 4 vehicles together with the virtual team leader, vehicle 5. Fig-
ure3.5showstheinteractiontopologyforthefivevehicles,wherea =a =
|     |     |     |     |     |     | 35  | 45  |
| --- | --- | --- | --- | --- | --- | --- | --- |
∀j ∈/ {3,4}.
1 and a j5 = 0, We consider two subcases using (3.4). In Sub-
case (a), let ξr = cos(t). In Subcase (b), assume that ξr satisfies (3.1) with
f(t,ξr)=sin(t)sin(2ξr),whereξr(0)=0.5.AsshowninFig.3.6,theinforma-
tion states of all followers converge to the exogenous signal cos(t) in Subcase
| (a) and to | the solution | of  | (3.1) in Subcase | (b). | (cid:13)(cid:14) |     |     |
| ---------- | ------------ | --- | ---------------- | ---- | ---------------- | --- | --- |
(cid:5)(cid:5)
|     |     |     | (cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25) ξr(cid:5)(cid:5)(cid:5)(cid:5)(cid:5)(cid:5) | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9)(cid:2)(cid:2) (cid:21)(cid:21)(cid:6) | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) |     |     |
| --- | --- | --- | ------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | -------------------------------------------------------- | --- | --- |
|     |     |     |                                                                                                               | 1 (cid:20)(cid:20) (cid:6)                                                                     | 4                                                        |     |     |
(cid:6)
|     |     |     |     | (cid:5) (cid:5) (cid:6) (cid:6) |     |     |     |
| --- | --- | --- | --- | ------------------------------- | --- | --- | --- |
|     |     |     |     | (cid:5) (cid:5) (cid:6)         |     |     |     |
(cid:5) (cid:5) (cid:6) (cid:5)(cid:6)
(cid:5) (cid:17)(cid:17)(cid:6)(cid:2)(cid:17)(cid:17)(cid:7)(cid:3)
|     |     |     |     | (cid:2)(cid:6) (cid:3)(cid:7) (cid:4)(cid:8) (cid:5)(cid:9) | (cid:8)(cid:4)(cid:9)(cid:5) |     |     |
| --- | --- | --- | --- | ----------------------------------------------------------- | ---------------------------- | --- | --- |
|     |     |     |     | 2(cid:19)(cid:19)                                           | 3                            |     |     |
Fig.3.5.Interactiontopologyamongthefivevehicles,wheretheconsensusreference
ξr
| state is available |     | to vehicles | 3 and 4 |     |     |     |     |
| ------------------ | --- | ----------- | ------- | --- | --- | --- | --- |
We have the following theorem for consensus tracking over a directed
| switching interaction |     | topology: |     |     |     |     |     |
| --------------------- | --- | --------- | --- | --- | --- | --- | --- |
Theorem 3.11.Suppose that A (t) is piecewise continuous and each
n+1
A
nonzero and hence positive entry of n+1 (t) is chosen from a compact set
[a,a¯], where a an a¯ are positive constants. Let t be the initial time. Also let
0
t ,t ,... be the switching times for A (t). With (3.4), a uniquesolution for
| 1 2 |     |     | n+1 |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
G
u , i = 1,...,n, exists if and only if directed switching graph (t) has a
| i   |     |     |     |     |     | n+1 |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
directed spanningtreeacross each interval [t ,t ), i=0,1,....Furthermore,
i i+1
G
the consensus tracking problem is solved if directed switching graph n+1 (t)
has a directed spanning tree across each interval [t ,t ), i=0,1,....
|     |     |     |     |     | i i+1 |     |     |
| --- | --- | --- | --- | --- | ----- | --- | --- |

| 64  | 3   | Consensus | Tracking | with | a Reference | State |     |     |
| --- | --- | --------- | -------- | ---- | ----------- | ----- | --- | --- |
        (a)
1.5
Reference
1
0.5
i 0
ξ
−0.5
−1
−1.5
|     | 0   | 2   | 4   | 6   | 8 10 | 12 14 | 16 18 | 20  |
| --- | --- | --- | --- | --- | ---- | ----- | ----- | --- |
Time (s)
        (b)
2
Reference
1.5
1
ξ i
0.5
0
−0.5
|     | 0   | 2   | 4   | 6   | 8 10 | 12 14 | 16 18 | 20  |
| --- | --- | --- | --- | --- | ---- | ----- | ----- | --- |
Time (s)
Fig. 3.6. Consensus tracking with a time-varying consensus reference state us-
ing (3.4). Subplot (a) corresponds to ξr = cos(t), and Subplot (b) corresponds to
| f(t,ξr)=sin(t)sin(2ξr) |     |     |     | in (3.1), | where ξr(0)=0.5. |     |     |     |
| ---------------------- | --- | --- | --- | --------- | ---------------- | --- | --- | --- |
(cid:6)=
Proof: Following the proof of Theorem 3.8, we can show that η (t) 0, i =
i
1,...,n, across each interval [t ,t ), i=0,1,... if directed switching graph
i i+1
G
n+1 (t) has a directed spanning tree across that interval. Thus (3.8) is well
| defined | under   | the        | condition | of         | the theorem.     |            |       |       |
| ------- | ------- | ---------- | --------- | ---------- | ---------------- | ---------- | ----- | ----- |
|         | Note    | that (3.5) | can       | be written | as               |            |       |       |
|         | [M(t)⊗I | ]u+[b(t)⊗I |           |            | ]ξ˙r =−γ{[M(t)⊗I | ]ξ+[b(t)⊗I | ]ξr}, | (3.7) |
|         |         | m          |           | m          |                  | m          | m     |       |
|         |         | (cid:2)    |           | (cid:2)    |                  |            |       |       |
where u=[uT,...,uT]T, ξ =[ξT,...,ξT]T, and M(t) and b(t) are defined as
|     |     | 1   | n   |     | 1 n |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
in the proof of Theorem 3.8 except that M(t) and b(t) are switching in (3.7).
Following the proof of Theorem 3.8, we can show that M(t) is invertible
across each interval [t ,t ), i=0,1,...if and only if G (t) has a directed
|          |     |             |      | i i+1     |     |     | n+1 |     |
| -------- | --- | ----------- | ---- | --------- | --- | --- | --- | --- |
| spanning |     | tree across | that | interval. |     |     |     |     |
M−1(t)
Next, we show that is bounded under the assumption of the the-
orem. Noting that each nonzero entry of A (t) is chosen from a compact
n+1
set, it follows that each nonzero entry of M(t) is also within a compact set.
Two matrices are said to have the same structure if their positive, zero, and
negative entries are in the same places. Under the assumption that G (t)
n+1

|     |     |     | 3.3 | Time-varying | Consensus | Reference | State 65 |
| --- | --- | --- | --- | ------------ | --------- | --------- | -------- |
is switching but has a directed spanning tree across each interval [t ,t ),
i i+1
the number of possible directed graphs for G (t) is finite. It then follows
n+1
A
that there are a finite number of possible structures for n+1 (t), which im-
plies that there are a finite number of possible structures for M(t). For each
possible structure ofM(t), M−1(t) exists acrosseachinterval[t ,t ), which
i i+1
|     |     | (cid:6)= |     |     |     | G   |     |
| --- | --- | -------- | --- | --- | --- | --- | --- |
implies that det[M(t)] 0 across each interval [t ,t ), if (t) has a di-
|     |     |     |     |     |     | i i+1 | n+1 |
| --- | --- | --- | --- | --- | --- | ----- | --- |
rected spanning tree across that interval. Thus for each possible structure of
M(t),det[M(t)]is withina compactsetthatdoes notinclude zero.Also note
that for each possible structure of M(t), all entries of its adjoint are within
a compact set. It thus follows that each entry of M−1(t) is within a compact
set. Therefore, it follows that u can be solved uniquely across each interval
| [t ,t ), | i=0,1,..., | and | the unique | solution | is  | given by |     |
| -------- | ---------- | --- | ---------- | -------- | --- | -------- | --- |
i i+1
| u=[M(t)⊗I |     | ] −1{−γ[M(t)⊗I |     | ]ξ−γ[b(t)⊗I |     | ]ξr −[b(t)⊗I | ]ξ˙r}. |
| --------- | --- | -------------- | --- | ----------- | --- | ------------ | ------ |
|           |     | m              |     | m           |     | m            | m      |
Noting that b(t) = −M(t)1 and M(t) is invertible across each interval
n
−M−1(t)b(t)=
[t i ,t i+1 ) under the assumptionofthe theorem,it followsthat
| 1 . Thus | the unique | solution | is  | given by |     |     |     |
| -------- | ---------- | -------- | --- | -------- | --- | --- | --- |
n
|     |     | u=−γξ+γ(1 |     | ⊗ξr)+1 |     | ⊗ξ˙r. |     |
| --- | --- | --------- | --- | ------ | --- | ----- | --- |
|     |     |           |     | n      |     | n     |     |
Therefore, it follows from the proof of Theorem 3.8 that ξ (t) → ξr(t),
i
i = 1,...,n, as t → ∞, if G (t) has a directed spanning tree across each
n+1
| interval [t | ,t ), | i=0,1,.... |     |     |     |     |     |
| ----------- | ----- | ---------- | --- | --- | --- | --- | --- |
i i+1
Remark 3.12. Note that the tracking nature of algorithm (3.4) requires more
stringentconditionsforconvergenceoverdirectedswitchinginteractiontopolo-
gies than those for algorithm(2.2), where the final consensus equilibrium is a
constant.Incontrastto algorithm(3.3), whichrequiresthatthe time-varying
consensus reference state be available to each follower for consensus track-
ing, algorithm (3.4) allows the time-varying consensus reference state to be
| available | only to | a subgroup | of  | the followers. |     | (cid:13)(cid:14) |     |
| --------- | ------- | ---------- | --- | -------------- | --- | ---------------- | --- |
Remark 3.13. In contrast to the leader-following strategy (e.g., [244]), where
the interaction topology is itself a directed spanning tree,3 algorithm (3.4)
takes into account the general case where information may flow among ve-
hicles. We have shown that with the time-varying consensus reference state,
complexity results from the information flow between neighbors. It is worth-
while to mention that the extension of consensus algorithms from a constant
reference to a time-varying reference is nontrivial. It is not straightforward
to apply the internal model principle of control to consensus tracking with a
time-varyingconsensusreferencestateformultivehiclesystemsinvolvingonly
| local information |     | exchange. | (cid:13)(cid:14) |     |     |     |     |
| ----------------- | --- | --------- | ---------------- | --- | --- | --- | --- |
3 The leader-following strategy requires an interaction topology that is itself a di-
rectedspanningtree.Notethattheconditionthatagraphhasadirectedspanning
tree is not equivalent to the condition that a graph is itself a directed spanning
tree. The latter condition is a special case of theformer one.

| 66  | 3   | Consensus | Tracking | with | a   | Reference State |     |     |     |
| --- | --- | --------- | -------- | ---- | --- | --------------- | --- | --- | --- |
Example 3.14. Theorem3.11 is illustrated by the following example. Suppose
that G (t) switches randomly from the set, {G ,...,G }, as shown in
|     | 5   |     |     |     |     |     | 5(1) | 5(4) |     |
| --- | --- | --- | --- | --- | --- | --- | ---- | ---- | --- |
Fig. 3.7, with a switching time around 0.25 seconds. We choose a ij (t) = 1 if
(j,i) ∈ E at time t and a (t) = 0 otherwise. Let f(t,ξr) = sin(t)sin(2ξr)
|     | n+1 |     |     | ij  |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
in(3.1)withξr(0)=1.Figure3.8showsthateachvehicletrackstheconsensus
(cid:13)(cid:14)
reference state with (3.4) under directed switching interactiontopologies.
|     |     | (cid:18)(cid:22)(cid:19)(cid:23) (cid:20)(cid:24)                | (cid:21)(cid:25)                | (cid:2)(cid:6) (cid:3)(cid:7) (cid:4)(cid:8) (cid:5)(cid:9) (cid:2)(cid:2)   | (cid:2) (cid:6) (cid:3) (cid:7) (cid:4) (cid:8)                          | (cid:5) (cid:9) (cid:18)(cid:22)(cid:19)(cid:23) (cid:20)(cid:24) (cid:21)(cid:25) | (cid:2) (cid:6) (cid:3) (cid:7) (cid:4) (cid:8) (cid:5) (cid:9)(cid:2)(cid:2)                   | (cid:15)(cid:15) (cid:6) (cid:2) (cid:7) (cid:3) (cid:8) (cid:4) (cid:9) (cid:5)         |     |
| --- | --- | ---------------------------------------------------------------- | ------------------------------- | ---------------------------------------------------------------------------- | ------------------------------------------------------------------------ | ---------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | --- |
|     |     | ξ r                                                              | (cid:7)(cid:8) (cid:8) (cid:8)  | 1 (cid:20)(cid:20) (cid:23)(cid:23)(cid:9) (cid:9)                           | 2 (cid:20)(cid:20)                                                       | ξ r (cid:7)                                                                        | 1                                                                                               | 2 (cid:20)(cid:20)                                                                       |     |
|     |     |                                                                  | (cid:7) (cid:7) (cid:8) (cid:8) | (cid:8) (cid:9)                                                              |                                                                          | (cid:7) (cid:7)                                                                    |                                                                                                 |                                                                                          |     |
|     |     |                                                                  | (cid:7) (cid:7)                 | (cid:8) (cid:8) (cid:9)                                                      | (cid:9)                                                                  | (cid:7)                                                                            | (cid:7)                                                                                         |                                                                                          |     |
|     |     |                                                                  | (cid:7)                         | (cid:8) (cid:8) (cid:8)                                                      | (cid:9)                                                                  |                                                                                    | (cid:7)                                                                                         |                                                                                          |     |
|     |     |                                                                  |                                 | (cid:7) (cid:7) (cid:8) (cid:8)                                              | (cid:8) (cid:9) (cid:9)                                                  |                                                                                    | (cid:7) (cid:7)                                                                                 |                                                                                          |     |
|     |     |                                                                  |                                 | (cid:7)                                                                      | (cid:8) (cid:8) (cid:8)(cid:9) (cid:14)(cid:14)                          |                                                                                    | (cid:7)                                                                                         | (cid:14)(cid:14)                                                                         |     |
|     |     |                                                                  |                                 | (cid:2)(cid:6) (cid:22)(cid:22) (cid:3)(cid:7) (cid:4)(cid:8) (cid:5)(cid:9) | (cid:2)(cid:3)(cid:3) (cid:6) (cid:3) (cid:7) (cid:4) (cid:8)            | (cid:5) (cid:9)                                                                    | (cid:2) (cid:6) (cid:22)(cid:22) (cid:3) (cid:7) (cid:4) (cid:8) (cid:5) (cid:9) (cid:2)(cid:2) | (cid:15)(cid:15) (cid:6) (cid:2) (cid:7) (cid:3) (cid:8) (cid:4) (cid:9) (cid:5)         |     |
|     |     |                                                                  |                                 | 4                                                                            | 3                                                                        |                                                                                    | 4                                                                                               | 3                                                                                        |     |
|     |     |                                                                  |                                 | G                                                                            |                                                                          |                                                                                    | G                                                                                               |                                                                                          |     |
|     |     |                                                                  |                                 | 5(1)                                                                         |                                                                          |                                                                                    | 5(2)                                                                                            |                                                                                          |     |
|     |     | (cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25) |                                 | (cid:15)(cid:15)(cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9)     | (cid:15)(cid:15)(cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) | (cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25)                   | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9)                                        | (cid:17)(cid:17)(cid:15)(cid:15)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) |     |
|     |     | ξr                                                               |                                 |                                                                              |                                                                          | ξr                                                                                 | 1(cid:9)(cid:23)(cid:23)                                                                        |                                                                                          |     |
|     |     |                                                                  |                                 | 1                                                                            | 2                                                                        |                                                                                    | (cid:9)                                                                                         | 2                                                                                        |     |
(cid:9) (cid:9)
(cid:9)
(cid:9) (cid:9)
(cid:9)
|     |     |     |      |                                                                        | (cid:14)(cid:14)                                         |                  | (cid:14)(cid:14)                                         | (cid:9)(cid:14)(cid:14)                                  |     |
| --- | --- | --- | ---- | ---------------------------------------------------------------------- | -------------------------------------------------------- | ---------------- | -------------------------------------------------------- | -------------------------------------------------------- | --- |
|     |     |     |      | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9)(cid:2)(cid:2) | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) |                  | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) |     |
|     |     |     |      | 4                                                                      | 3                                                        |                  | 4                                                        | 3                                                        |     |
|     |     |     |      | G                                                                      |                                                          |                  | G                                                        |                                                          |     |
|     |     |     |      | 5(3)                                                                   |                                                          |                  | 5(4)                                                     |                                                          |     |
|     |     |     | Fig. | 3.7. Directed                                                          |                                                          | switching graphs | for (3.4)                                                |                                                          |     |
3.3.2 Consensus Tracking Algorithm with Bounded Control Inputs
In this subsection, we consider a consensus tracking algorithm that explicitly
∈ Rm,
accounts for a bounded control effort. Given x = [x ,...,x ] define
1 m
tanh(x) =[tanh(x ),...,tanh(x )]T. We propose a consensus tracking algo-
|       |      |         | 1       |        | m   |     |     |     |     |
| ----- | ---- | ------- | ------- | ------ | --- | --- | --- | --- | --- |
| rithm | with | bounded | control | inputs |     | as  |     |     |     |
(cid:2)n
1
| u   | =   | [ a | ξ˙ +a |        | ξ˙r] |     |     |     |     |
| --- | --- | --- | ----- | ------ | ---- | --- | --- | --- | --- |
|     | i   |     | ij j  | i(n+1) |      |     |     |     |     |
η
i j=1
(cid:2)n
1
|     | −   | Λ tanh[ |     | a (ξ | −ξ )+a | (ξ       | −ξr)], i=1,...,n, |     | (3.8) |
| --- | --- | ------- | --- | ---- | ------ | -------- | ----------------- | --- | ----- |
|     |     | η i     |     | ij   | i j    | i(n+1) i |                   |     |       |
i
j=1
where a , i = 1,...,n, j = 1,...,n+1, is the (i,j) entry of the adjacency
|     | ij  |     | (cid:7) |     |     |     |     |     |     |
| --- | --- | --- | ------- | --- | --- | --- | --- | --- | --- |
(cid:2)
matrix A , η = n+1a , and Λ ∈ Rm×m is a symmetrical positive-
|     |     | n+1 | i   | j=1 ij |     | i   |     |     |     |
| --- | --- | --- | --- | ------ | --- | --- | --- | --- | --- |
definite matrix.

|     |     |     | 3.3 Time-varying |     | Consensus | Reference | State 67 |
| --- | --- | --- | ---------------- | --- | --------- | --------- | -------- |
6
Reference
i=1
i=2
i=3
i=4
4
2
ξ i 0
−2
−4
−6
|     | 0 1 2 | 3   | 4 5 | 6   | 7 8 | 9   | 10  |
| --- | ----- | --- | --- | --- | --- | --- | --- |
Time (s)
Fig.3.8.Consensustrackingwith(3.4)underdirectedswitchinginteractiontopolo-
| gies given | by Fig. 3.7 |     |     |     |     |     |     |
| ---------- | ----------- | --- | --- | --- | --- | --- | --- |
Next, we will show conditions under which a unique bounded solution
exists for each control input and conditions under which consensus tracking
| is achieved | over a | directed | fixed interaction |     | topology. |     |     |
| ----------- | ------ | -------- | ----------------- | --- | --------- | --- | --- |
Theorem 3.15.SupposethatA isconstant.With (3.8),auniquesolution
n+1
(cid:9)u (cid:9)
for u i , i = 1,...,n, exists, i ∞ is bounded and independent of the initial
conditions of the information states, and the consensus tracking problem is
solved if and only if directed graph G has a directed spanning tree.
n+1
Proof: Following the proof of Theorem 3.8, we rewrite (3.8) as
|     | ⊗I )u+(b⊗I |     | )ξ˙r =−Λtanh[(M |     | ⊗I  | )ξ+(b⊗I | )ξr], |
| --- | ---------- | --- | --------------- | --- | --- | ------- | ----- |
(M
|     | m       |     | m       |     | m   |         | m   |
| --- | ------- | --- | ------- | --- | --- | ------- | --- |
|     | (cid:2) |     | (cid:2) |     |     | (cid:2) |     |
where u = [uT,...,uT]T, ξ = [ξT,...,ξT]T, and Λ = diag(Λ ,...,Λ ). As
|     | 1   | n   | 1   | n   |     |     | 1 n |
| --- | --- | --- | --- | --- | --- | --- | --- |
shownintheproofofTheorem3.8,M hasfullrankandthereforeisinvertible
ifandonlyifG
|     | n+1 | hasadirectedspanningtree.Itfollowsthatucanbesolved |     |     |     |     |     |
| --- | --- | -------------------------------------------------- | --- | --- | --- | --- | --- |
uniquely under the same necessary and sufficient condition. In addition, it is
straightforward to see that (cid:9)u (cid:9) is bounded and independent of the initial
|     |     |     | i ∞ |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
conditions ofthe informationstates because ξ˙r is bounded and(cid:9)tanh(·)(cid:9) ≤
∞
1.

68 3 Consensus Tracking with a Reference State
(cid:7)
(cid:7) Consider a positive-definite function V = 1 2 n i=1 eT i Λ − i 1e i , where e i = (cid:2)
n a (ξ −ξ )+a (ξ −ξr).Notingthatwith(3.8),(2.1)canbewritten
j=1 ij i j i(n+1) i
(cid:7)as e˙
i
= −Λ
i
tanh(e
i
), it follows(cid:7)that the derivative of V is given by V˙ =
n eTΛ −1[−Λ tanh(e )] = − n eT tanh(e ), which is negative definite.
i=1 i i i i i=1 i i
Therefore,itfollowsfromTheoremF.1thate (t)→0,i=1,...,n,ast→∞.
i
Lettinge=[eT,...,eT]T,thene=(M⊗I )ξ+(b⊗I )ξr.Thuse (t)→0,
1 n m m i
i=1,...,n,ast→∞,impliesthat(M⊗I )ξ(t)+(b⊗I )ξr(t)→0ast→∞.
m m
Alsonotefromthepreviousargumentthat−M−1b=1 ifandonlyG has
n n+1
a directed spanning tree. It follows that ξ(t)→−(M ⊗I )−1(b⊗I )ξr(t)=
m m
−(M−1b⊗I )ξr(t)=1 ⊗ξr(t),whichimpliesthatξ (t)→ξr(t),i=1,...,n,
m n i
as t → ∞ if and only if the directed graph of G has a directed spanning
n+1
tree.
Notethat(3.8)explicitlyaccountsforboundedcontrolinputs,whereas(3.4)
does not. The following example compares (3.8) with (3.4) in simulation:
Example 3.16. Letf(t,ξr)=sin(t)sin(2ξr)in(3.1)withξr(0)=1.Figure3.9
shows directed graph G used in (3.8) and (3.4). Figures 3.10 and 3.11 show,
5
respectively,theconsensustrackingresultswith(3.8)and(3.4),whereSubplot
(a) shows ξ and ξr and Subplot (b) shows u . For initial conditions of the
i i
information states with larger differences, larger control efforts are needed
correspondinglywith(3.4).However,with(3.8),themaximumcontroleffortis
independentoftheinitialconditions.Ofcourse,the tradeoffisthatconsensus
tracking with (3.8) converges more slowly than with (3.4). (cid:13)(cid:14)
(cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25) (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9)(cid:2)(cid:2) (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5)
ξr(cid:10)(cid:5) (cid:10) (cid:5) (cid:10) (cid:5) (cid:10) (cid:10) (cid:5) (cid:10) (cid:5) (cid:10) (cid:5) (cid:10) (cid:2)(cid:6) (cid:5) (cid:24)(cid:24) (cid:3)(cid:7) 1 (cid:5) (cid:4)(cid:8) (cid:20)(cid:20) (cid:5)(cid:9) (cid:21)(cid:21)(cid:6) (cid:5) (cid:6) (cid:5) (cid:6) (cid:5) (cid:6) (cid:5) (cid:6) (cid:6) (cid:5) (cid:6) (cid:5)(cid:6) (cid:6)(cid:2)(cid:17)(cid:17)(cid:7)(cid:3) 2 (cid:8)(cid:4) (cid:14)(cid:14) (cid:20)(cid:20) (cid:9)(cid:5)
4 3
Fig. 3.9. Directed graph G 5 used in (3.8) and (3.4)
3.3.3 Information Feedback to the Consensus Reference State
Note that with consensus tracking algorithms (3.4) and (3.8), there is no
information feedback from the followers to the consensus reference state. If
a vehicle cannot track the consensus reference state due to disturbance or
temporalmalfunction,the consensusreferencestatewillevolveatitsnominal
speedwithoutcompensatingforvehicledisturbanceortemporalmalfunction.
We will propose consensus tracking algorithms that introduce feedback from
the followers to the consensus reference state.
One strategy is to update ξr as

|     |     |     |     | 3.3 Time-varying | Consensus Reference | State | 69  |
| --- | --- | --- | --- | ---------------- | ------------------- | ----- | --- |
(a)
|     | 6   |     |     |     |     |     | Reference |
| --- | --- | --- | --- | --- | --- | --- | --------- |
i=1
|     | 4   |     |     |     |     |     | i=2 |
| --- | --- | --- | --- | --- | --- | --- | --- |
i=3
2
i=4
i 0
ξ
−2
−4
−6
|     | 0   | 5   |     | 10 15 | 20 25 | 30  |     |
| --- | --- | --- | --- | ----- | ----- | --- | --- |
Time (s)
(b)
1.5
i=1
i=2
|     | 1   |     |     |     |     |     | i=3 |
| --- | --- | --- | --- | --- | --- | --- | --- |
i=4
0.5
u i
0
−0.5
−1
|     | 0   | 5   |     | 10 15 | 20 25 | 30  |     |
| --- | --- | --- | --- | ----- | ----- | --- | --- |
Time (s)
Fig. 3.10. Consensustrackingwithboundedcontrolinputsgivenby(3.8).Subplot
(a) shows the information states, and Subplot (b) shows the information control
inputs.
dξr
ds 1
|     |     |     |     | =f(s,ξr), | = ,    |     | (3.9) |
| --- | --- | --- | --- | --------- | ------ | --- | ----- |
|     |     |     | ds  |           | dt 1+z |     |       |
f
where f(·,·) is defined as in (3.1) and z denotes a nonnegative consen-
f
sus tracking performance function. The function z must satisfy the prop-
f
erty that z is small if consensus is achieved well and is large otherwise.
f
For example, (cid:7) we (cid:7) may choose a nonnegative function z f such that z f =
0 if k n a (cid:9)ξ −ξ (cid:9)2 is below a threshold and z grows as
|     | (cid:7) f (cid:7)i∈VL |     | j=1 ij | i j |     | f   |     |
| --- | --------------------- | --- | ------ | --- | --- | --- | --- |
k n a (cid:9)ξ −ξ (cid:9)2increasesabovethethreshold,wherek isapos-
| f   | i∈VL | j=1 | ij i | j   |     |     | f   |
| --- | ---- | --- | ---- | --- | --- | --- | --- |
V
itive constant and L denotes the subgroup leaders (i.e., the set of vehicles
to which ξr and ξ˙r are available). As a result, the consensus reference state
will evolve at its nominal speed if the consensus error is small and evolves
moreslowlyiftheconsensuserrorbecomeslarge.Notethatwiththefeedback
| strategy | (3.9),  | Theorems |     | 3.8, 3.11, and | 3.15 remain valid. |     |     |
| -------- | ------- | -------- | --- | -------------- | ------------------ | --- | --- |
|          | Another | strategy | is  | to define a    | in (3.4) and (3.8) | as  |     |
i(n+1)
a∗
i(n+1)
|     |     |     |     | a =    | ,   |     | (3.10) |
| --- | --- | --- | --- | ------ | --- | --- | ------ |
|     |     |     |     | i(n+1) | 1+z |     |        |
f

| 70  | 3 Consensus |     | Tracking | with a | Reference | State |     |     |     |
| --- | ----------- | --- | -------- | ------ | --------- | ----- | --- | --- | --- |
(a)
6
Reference
i=1
4
i=2
i=3
2
i=4
ξ i 0
−2
−4
−6
|     | 0   |     | 5   |     |     | 10  |     | 15  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Time (s)
(b)
8
i=1
i=2
6
i=3
| 4   |     |     |     |     |     |     |     |     | i=4 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
2
u i
0
−2
−4
−6
|     | 0   |     |     | 5   |     | 10  |     | 15  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Time (s)
Fig. 3.11. Consensus tracking without explicitly accounting for bounded control
inputswith (3.4).Subplot (a) shows theinformation states, and Subplot (b) shows
| theinformation |     | control | inputs. |     |     |     |     |     |     |
| -------------- | --- | ------- | ------- | --- | --- | --- | --- | --- | --- |
wherea∗
|     |        | denotesthenominalvaluefora |     |     |     |        | whenthereisnofeedback |     |     |
| --- | ------ | -------------------------- | --- | --- | --- | ------ | --------------------- | --- | --- |
|     | i(n+1) |                            |     |     |     | i(n+1) |                       |     |     |
mechanismandz is a nonnegativeconsensustrackingperformancefunction.
f
∈
The function z f must satisfy the properties that z f [0,z¯ f ], where z¯ f is an
upper bound for z , and z is small if consensus is achieved well and is large
|     |     | f   |     | f   |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
otherwise. With the feedback strategy (3.10), Theorem 3.11 remains valid
a∗
| because | a         | =0        | if     | =0 and    | a      | belongs | to a | compact | set when |
| ------- | --------- | --------- | ------ | --------- | ------ | ------- | ---- | ------- | -------- |
|         | i(n+1)    |           | i(n+1) |           | i(n+1) |         |      |         |          |
| a∗      | (cid:6)=0 | is chosen | from   | a compact | set.   |         |      |         |          |
i(n+1)
Example 3.17. The following example compares consensus tracking results
|     |     |     |     |     |     |     | G   |     | G   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
with and without information feedback. Suppose that is given by
|     |     |     |     |     |     |     |     | 5   | 5(2) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ---- |
in Fig. 3.7. Also suppose that vehicle 3 fails at t ∈ [5,7] seconds, where
|     | ≡   | ∈   |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
u 3 (t) 0 at t [5,7] seconds. We combine the information feedback strate-
gies (3.9), where z =50|ξ −ξ |, and (3.10), where a = 1 . Subplot (a)
|     |     | f   |     | 4 3 |     |     | 45  | 1+zf |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ---- | --- |
inFig.3.12showstheconsensustrackingresultwiththeinformationfeedback
strategies (3.9) and (3.10), and Subplot (b) in Fig. 3.12 shows the consensus
tracking result with (3.4) without information feedback. Note that during
∈
t [5,7] seconds, the information states of the vehicles stay closer and the

|     |     |     |     | 3.4 | Extension | to Relative | StateDeviations | 71  |
| --- | --- | --- | --- | --- | --------- | ----------- | --------------- | --- |
consensus reference state evolves more slowly in Subplot (a) than in Subplot
(b) due to the introduction of information feedback in Subplot (a). (cid:13)(cid:14)
(a)
2
Reference
i=1
|     | 1.5 |     |     |     |     |     | i=2 |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
i=3
i=4
1
i
ξ
0.5
0
−0.5
|     | 0   | 2   | 4   | 6 8 | 10  | 12 14 16 | 18 20 |     |
| --- | --- | --- | --- | --- | --- | -------- | ----- | --- |
Time (s)
(b)
2
Reference
i=1
|     | 1.5 |     |     |     |     |     | i=2 |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
i=3
i=4
1
ξ i
0.5
0
−0.5
|     | 0   | 2   | 4   | 6 8 | 10  | 12 14 16 | 18 20 |     |
| --- | --- | --- | --- | --- | --- | -------- | ----- | --- |
Time (s)
Fig. 3.12. Consensus tracking with information feedback versus without informa-
tion feedback. Subplot (a) corresponds to the case with information feedback, and
Subplot (b) corresponds to thecase without information feedback.
| 3.4 | Extension |     | to Relative |     | State | Deviations |     |     |
| --- | --------- | --- | ----------- | --- | ----- | ---------- | --- | --- |
We propose the following consensus algorithm for relative state deviations
| with | a time-varying |     | consensus |     | reference | state |     |     |
| ---- | -------------- | --- | --------- | --- | --------- | ----- | --- | --- |
(cid:2)n
1
|     |     |     | =δ˙ | {ξ˙  | −δ˙ | −γ[(ξ −ξ )−(δ | −δ )]} |     |
| --- | --- | --- | --- | ---- | --- | ------------- | ------ | --- |
|     |     | u i | i + | a ij | j j | i j           | i j    |     |
η
i j=1
|     |     |     | 1        | [ξ˙r−γ(ξ |     | −δ −ξr)], |     |        |
| --- | --- | --- | -------- | -------- | --- | --------- | --- | ------ |
|     |     |     | + a      |          |     |           |     | (3.11) |
|     |     |     | η i(n+1) |          | i   | i         |     |        |
i
(cid:2)
where Δ = δ − δ , ∀i (cid:6)= j, denotes the desired separation between the
|             |     | ij      | i j |     |     |     |     |     |
| ----------- | --- | ------- | --- | --- | --- | --- | --- | --- |
| information |     | states. |     |     |     |     |     |     |

| 72 3 Consensus | Tracking |     | with a Reference | State |     |     |     |
| -------------- | -------- | --- | ---------------- | ----- | --- | --- | --- |
A
Theorem 3.18.Suppose that is constant. With algorithm (3.11),
n+1
ξ (t) → ξr(t)+δ (t) and ξ (t)−ξ (t) → Δ (t), as t → ∞, if and only if
| i   | i   | i   | j   | ij  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
G
| directed graph | n+1     | has a directed | spanning | tree. |     |     |     |
| -------------- | ------- | -------------- | -------- | ----- | --- | --- | --- |
|                | (cid:2) |                | (cid:2)  |       |     | ξ˜˙ |     |
Proof: Define ξ˜ = ξ −δ and u˜ = u −δ˙ . Note that = u˜ . Also note
|     | i   | i i | i   | i i |     | i i |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
that (3.11) can be rewritten in the same form as (3.4) with ξ˜ and u˜ playing
|     |     |     |     |     |     | i i |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
ξ˜(t) →
the roles of ξ and u , respectively. As a result, from Theorem 3.8,
|     | i   | i   |     |     |     |     | i   |
| --- | --- | --- | --- | --- | --- | --- | --- |
ξr(t), i = 1,...,n, as t → ∞, which implies that ξ (t) → ξr(t)+δ (t) and
|             |         |      |     |     | i   |     | i   |
| ----------- | ------- | ---- | --- | --- | --- | --- | --- |
| (t)−ξ (t)→Δ |         | t→∞. |     |     |     |     |     |
| ξ i j       | ij (t), | as   |     |     |     |     |     |
Example 3.19. Theorem 3.18 is illustrated by the following example. As in
1−
Example 3.10, consider the two subcases using (3.11). We choose δ i =
i, i = 1,...,4. As shown in Fig. 3.13, ξ (t) → ξr(t), ξ (t) → ξr(t) − 1,
|              |      |                |     | 1    |       | 2                |     |
| ------------ | ---- | -------------- | --- | ---- | ----- | ---------------- | --- |
| (t)→ξr(t)−2, |      | (t)→ξr(t)−3,as |     | t→∞, |       | ξr               |     |
| ξ 3          | andξ | 4              |     |      | where | is the exogenous |     |
ξ˙r
signal cos(t) in Subcase (a) and is the solution of the nonlinear model =
| sin(t)sin(2ξr) | in Subcase | (b). | (cid:13)(cid:14) |     |     |     |     |
| -------------- | ---------- | ---- | ---------------- | --- | --- | --- | --- |
        (a)
2
Reference
1
0
i −1
ξ
−2
−3
−4
| 0   | 2 4 | 6   | 8   | 10 12 | 14  | 16 18 | 20  |
| --- | --- | --- | --- | ----- | --- | ----- | --- |
Time (s)
        (b)
2
Reference
1
0
ξ i
−1
−2
−3
| 0   | 2 4 | 6   | 8   | 10 12 | 14  | 16 18 | 20  |
| --- | --- | --- | --- | ----- | --- | ----- | --- |
Time (s)
Fig. 3.13. Consensus tracking with a time-varying consensus reference state us-
ing (3.11). Subplot (a) corresponds to ξr = cos(t), and Subplot (b) corresponds to
| f(t,ξr)=sin(t)sin(2ξr) |     |           | ξr(0)=0.5. |     |     |     |     |
| ---------------------- | --- | --------- | ---------- | --- | --- | --- | --- |
|                        |     | in (3.1), | where      |     |     |     |     |

3.5 Notes 73
3.5 Notes
The results in this chapter are based mainly on [173,175,180]. Variants of
algorithm(3.2)arealsoconsideredin[99,143]overadirectedfixedinteraction
topology.
Acknowledgment is given to
(cid:10)c2007Elsevier.Reprinted,withpermission,fromWeiRen,“Multi-vehicle
consensus with a time-varying reference state,” Systems and Control Letters,
vol. 56, no. 7–8, pp. 474–483,July 2007.
(cid:10)c2007IEEE.Reprinted,withpermission,fromWeiRen,“Consensusseek-
ing in multi-vehicle systems with a time-varyingreference state,” Proceedings
of the American Control Conference, pp. 717–722,New York City, 2007.
(cid:10)c2007 IEEE. Reprinted, with permission, from Wei Ren, “Consensus
trackingunder directed interactiontopologies:Algorithms andexperiments,”
IEEE Transactions on Control Systems Technology, 2007 (under review).

Part III
| Consensus | Algorithms | for Double-integrator |
| --------- | ---------- | --------------------- |
Dynamics

4
Consensus Algorithms for Double-integrator
Dynamics
This chapter introduces consensus algorithms for double-integratordynamics
that take into account motions of the information states and their deriva-
tives, extending the algorithms for single-integrator dynamics. We first pro-
pose a fundamental consensus algorithm and derive conditions under which
consensus is reached over directed fixed and switching interaction topologies,
respectively.Unlikethesingle-integratorcase,weshowthathavingadirected
spanning tree is a necessary rather than a sufficient condition for consensus-
seeking with double-integrator dynamics. We focus on a formal analysis of
interaction topologies that permit consensus for double-integrator dynamics.
Givenitsimportanceforthestabilityofthecoordinatedsystem,ananalysisof
the consensustermcontrolgainsis alsopresented,specificallythe strengthof
theinformationstatesrelativetotheirderivatives.Wethenproposetwoother
consensusalgorithmsthat,respectively,takeintoaccountboundedcontrolef-
fort and remove the requirement for measurements of relative information
state derivatives. We derive conditions under which consensus is reached for
these two algorithms over an undirected fixed interaction topology.
4.1 Consensus Algorithm
Chapters 2 and 3 focus on consensus algorithms that take the form of single-
integrator dynamics. Equations of motion of a broad class of vehicles require
a double-integratordynamic model. For example, some vehicle dynamics can
befeedbacklinearizedasdoubleintegrators,e.g.,mobilerobotdynamicmod-
els. In the case of consensus algorithms for single-integrator dynamics, the
consensus equilibrium is a constant. In contrast to the constant consensus
equilibrium, it might be proper to derive consensus algorithms for double-
integrator dynamics such that some information states converge to a con-
sistent value (e.g., position of the formation center) while others converge
to another consistent value (e.g., velocity of the formation center). Unfortu-

78 4 Consensus Algorithms for Double-integrator Dynamics
nately,the extensionofconsensusalgorithmsfromsingle-integratordynamics
to double-integrator dynamics is nontrivial.
Consider information states with double-integrator dynamics given by
ξ˙ =ζ , ζ˙ =u , i=1,...,n, (4.1)
i i i i
where ξ ∈ Rm is the information state, ζ ∈ Rm is the information state
i i
derivative, and u ∈ Rm is the information control input associated with the
i
ith vehicle.
Note that the interaction topologies for ξ and ζ among n vehicles are
i i
allowed to be different under some circumstances. We use directed graphs
(cid:2)
GA = (V ,EA), where V = {1,...,n} is the node set and EA ⊆ V ×V is
n n n n n n n
(cid:2)
the edge set, and GB = (V ,EB), where V is the same node set as above
n n n n
and EB ⊆ V ×V is the edge set, to model the interaction topologies for ξ
n n n i
and ζ , respectively, among the n vehicles. Let A = [a ] ∈ Rn×n and B =
i n ij n
[b
ij
]∈Rn×nbetheadjacencymatrixassociatedwithG
n
A andG
n
B,(cid:7)respectively.
Also let LA = [(cid:2) ] ∈ Rn×n (i.e., (cid:2) = −a , i (cid:6)= j, (cid:2) = n a )
n ij ij ij (cid:7)ii j=1,j(cid:5)=i ij
and LB = [(cid:2) ] ∈ Rn×n (i.e., (cid:2) = −b , i (cid:6)= j, (cid:2) = n b ) be the
n ij ij ij ii j=1,j(cid:5)=i ij
nonsymmetrical Laplacian matrix associated with GA and GB, respectively.
n n
When there is only one interaction topology associated with the n vehicles,1
(cid:2)
we simply use G = (V ,E ) to model the interaction topology among the n
n n n
vehicles,asinChapter2.Similarly,A andL are,respectively,theadjacency
n n
matrix and the nonsymmetrical Laplacian matrix associated with G .
n
We propose a consensus algorithm for (4.1) as
(cid:2)n
u =− a (t)[(ξ −ξ )+γ(t)(ζ −ζ )], i=1,...,n, (4.2)
i ij i j i j
j=1
where a (t) is the (i,j) entry of the adjacency matrix A (t) ∈ Rn×n associ-
ij n
ated with G 2 at time t and γ(t) is a positive scalar at time t. When ξ and
n i
ζ denote, respectively, the position and velocity of the ith vehicle, (4.2) rep-
i
resents the acceleration of that vehicle. With (4.2), consensus is achieved or
reachedbytheteamofvehiclesif,forallξ (0)andζ (0)andalli,j =1,...,n,
i i
(cid:9)ξ (t)−ξ (t)(cid:9)→0 and (cid:9)ζ −ζ (cid:9)→0, as t→∞.
i j i j
(cid:2) (cid:2)
Let ξ =[ξT,...,ξT]T and ζ =[ζT,...,ζT]T. By applying algorithm(4.2),
1 n 1 n
(4.1) can be written in matrix form as
(cid:22) (cid:23) (cid:22) (cid:23)
ξ˙ ξ
=(Θ(t)⊗I ) , (4.3)
ζ˙ m ζ
where
1 Forexample,theinteraction topologies for ξ andζ areidenticalorneedonly ξ
i i i
to beexchanged among vehicles.
2 In this case, theinteraction topologies for both ξ and ζ are identical.
i i

|     |     |     |     |          |           | 4.1 | Consensus | Algorithm | 79    |
| --- | --- | --- | --- | -------- | --------- | --- | --------- | --------- | ----- |
|     |     |     |     | (cid:22) |           |     | (cid:23)  |           |       |
|     |     |     |     |          | 0 n×n     | I n |           |           |       |
|     |     |     | Θ   | =        |           |     |           |           | (4.4) |
|     |     |     |     | −L       | (t)−γ(t)L |     | (t)       |           |       |
|     |     |     |     |          | n         |     | n         |           |       |
with L (t) ∈ Rn×n as the nonsymmetrical Laplacian matrix associated with
n
G
| at time | t.  |     |     |     |     |     |     |     |     |
| ------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
n
4.1.1 Convergence Analysis Under Fixed Interaction Topologies
In this subsection, we focus on analyzing consensus algorithm(4.2) when A
n
| and γ are | constant. |     | Given | a block | matrix   |          |     |     |     |
| --------- | --------- | --- | ----- | ------- | -------- | -------- | --- | --- | --- |
|           |           |     |       |         | (cid:22) | (cid:23) |     |     |     |
|           |           |     |       |         | A        | B        |     |     |     |
|           |           |     |       | M       | =        | ,        |     |     |     |
|           |           |     |       |         | C        | D        |     |     |     |
it is known that det(M)=det(AD−CB) if A and C commute, where det(·)
| denotes                                             | the determinant |     | of  | a matrix. |     |     |     |        |     |
| --------------------------------------------------- | --------------- | --- | --- | --------- | --- | --- | --- | ------ | --- |
| TofindtheeigenvaluesofΘ,wecansolvetheequationdet(λI |                 |     |     |           |     |     |     | −Θ)=0, |     |
2n
where det(λI −Θ) is the characteristic polynomial of Θ. Note that
2n
|     |     |        |     |         | (cid:11)(cid:22) |     |     | (cid:23)(cid:12) |     |
| --- | --- | ------ | --- | ------- | ---------------- | --- | --- | ---------------- | --- |
|     |     |        |     |         |                  | λI  | −I  |                  |     |
|     |     |        |     | −Θ)=det |                  | n   | n   |                  |     |
|     |     | det(λI | 2n  |         |                  | L   | +γL |                  |     |
λI
|           |      |     |     |     |          | n        | n   | n   |       |
| --------- | ---- | --- | --- | --- | -------- | -------- | --- | --- | ----- |
|           |      |     |     |     | =det[λ2I | +(1+γλ)L |     | ].  | (4.5) |
|           |      |     |     |     |          | n        |     | n   |       |
| Also note | that |     |     |     |          |          |     |     |       |
(cid:24)n
|     |     |     |        |     | +L   | (λ−μ |      |     |       |
| --- | --- | --- | ------ | --- | ---- | ---- | ---- | --- | ----- |
|     |     |     | det(λI | n   | n )= |      | i ), |     | (4.6) |
i=1
−L
| where μ      | is the | ith   | eigenvalue | of     | .      |      |     |     |     |
| ------------ | ------ | ----- | ---------- | ------ | ------ | ---- | --- | --- | --- |
|              | i      |       |            |        | n      |      |     |     |     |
| By comparing |        | (4.5) | and        | (4.6), | we see | that |     |     |     |
(cid:24)n
|     |     | (cid:8) |          |     | (cid:9) |             |     |     |     |
| --- | --- | ------- | -------- | --- | ------- | ----------- | --- | --- | --- |
|     |     | λ2I     | +(1+γλ)L |     |         | [λ2−(1+γλ)μ |     |     |     |
|     |     | det     |          |     | =       |             |     | ],  |     |
|     |     |         | n        |     | n       |             |     | i   |     |
i=1
which implies that the roots of (4.5) can be obtained by solving λ2 = (1+
γλ)μ . Therefore, it is straightforward to see that the eigenvalues of Θ are
i
| given by |     |     |     |     | (cid:25) |         |     |     |       |
| -------- | --- | --- | --- | --- | -------- | ------- | --- | --- | ----- |
|          |     |     |     | γμ  | ±        | γ2μ2+4μ |     |     |       |
|          |     |     | λ   | =   | i        | i       | i , |     | (4.7) |
i±
2
where λ and λ are called the eigenvalues of Θ that are associated with
|     | i+  | i−  |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
μ .
i
From (4.7), we can see that Θ has 2k zero eigenvalues if and only if −L
n
−L
has k zero eigenvalues. According to Lemma 2.4, n has at least one zero
eigenvalue with an associatedeigenvector1 , and allof the nonzero eigenval-
n
ues of −L have negative real parts. Therefore, we know that Θ has at least
n
two zero eigenvalues. Without loss of generality, we let λ 1+ =λ 1− =0.
Wehavethefollowinglemmaregardinganecessaryandsufficientcondition
| for an information |     | consensus |     | using | algorithm | (4.2): |     |     |     |
| ------------------ | --- | --------- | --- | ----- | --------- | ------ | --- | --- | --- |

| 80  | 4 Consensus |     | Algorithms | for | Double-integrator |     | Dynamics |     |     |
| --- | ----------- | --- | ---------- | --- | ----------------- | --- | -------- | --- | --- |
Lemma 4.1.Algorithm (4.2) achieves consensus asymptotically if and only
if Θ has exactly two zero eigenvalu(cid:7)es and all other(cid:7)eigenvalues have nega-
|     |     |     |     | (t)→ | n   |     | n   |     | (t)→ |
| --- | --- | --- | --- | ---- | --- | --- | --- | --- | ---- |
t(cid:7)ive real parts. Specifically, ξ i p i ξ i (0)+t p i ζ i (0) and ζ i
|     |     |     |     |     | i=1 |     | i=1 |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
n p ζ (0) for large t, where p=[p ,...,p ]T ≥0, 1Tp=1, andL Tp=0.
| i=1 | i i |     |     |     | 1   | n   | n   |     | n   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Proof: (Sufficiency.)WefirstshowthatthezeroeigenvalueofΘhasgeometric
multiplicity equal to one, when Θ has exactly two zero eigenvalues. Letting
q = [qT,qT]T, where q ,q ∈ Rn, is an eigenvector of Θ associated with the
|      | a b         |      | a b     |          |                  |          |                   |     |     |
| ---- | ----------- | ---- | ------- | -------- | ---------------- | -------- | ----------------- | --- | --- |
| zero | eigenvalue, | then | we know | that     |                  |          |                   |     |     |
|      |             |      |         | (cid:22) | (cid:23)(cid:22) | (cid:23) | (cid:22) (cid:23) |     |     |
|      |             |      |         | 0 n×n    | I n              | q a      | 0 n               |     |     |
|      |             |      | Θq =    |          |                  | =        | ,                 |     |     |
|      |             |      |         | −L       | −γL              | q        | 0                 |     |     |
|      |             |      |         | n        | n                | b        | n                 |     |     |
which implies that q = 0 and −L q = 0 , where 0 denotes the n×1
|     |     |     | b   | n   | n a | n   | n   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
−L
vector of all zeros, that is, q is an eigenvector of associated with the
|     |     |     |     | a   |     |     | n   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
zeroeigenvalueof−L .BecauseΘ hasexactlytwozeroeigenvalues,weknow
n
−L
from (4.7) that n has exactly one zero eigenvalue. Therefore, we see that
−L hasonlyonelinearlyindependenteigenvectorq associatedwiththezero
|     | n   |     |     |     |     |     | a   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
eigenvalue, which in turn implies that Θ has only one linearly independent
[qT,0T]T
eigenvector q = associated with the zero eigenvalue, that is, the
a n
zero eigenvalue of Θ has algebraic multiplicity equal to two but geometric
| multiplicity |           | equal to | one.       |     |        |           |      |     |     |
| ------------ | --------- | -------- | ---------- | --- | ------ | --------- | ---- | --- | --- |
|              | Note that | Θ can    | be written | in  | Jordan | canonical | form | as  |     |
|              | Θ =PJP    | −1       |            |     |        |           |      |     |     |
|              |           |          | ⎡          |     |        |           | ⎤⎡   | ⎤   |     |
νT
|     |     |      |      | 0   | 1   | 0   |               | 1        |       |
| --- | --- | ---- | ---- | --- | --- | --- | ------------- | -------- | ----- |
|     |     |      |      |     |     | 1   | × ( 2 n − 2 ) | ⎢ ⎥      |       |
|     |     | ,··· | ⎣    |     |     |     | ⎦             | ⎣ . . ⎦, |       |
|     | =[w | 1 ,w | 2n ] | 0   | 0   | 0 1 | × ( 2 n − 2 ) | .        | (4.8) |
J(cid:8)
|     |     |     |     | 0 (2n−2)×1 | 0 (2n−2)×1 |     |     | νT  |     |
| --- | --- | --- | --- | ---------- | ---------- | --- | --- | --- | --- |
2n
where w ∈R2n, j =1,··· ,2n, can be chosen to be the right eigenvectors or
j
generalized right eigenvectors of Θ, ν ∈ R2n, j = 1,··· ,2n, can be chosen
j
J(cid:8)
as the left eigenvectors or generalized left eigenvectors of Θ, and is the
Jordanupperdiagonalblockmatrixcorrespondingtothenonzeroeigenvalues
i=2,···
| λ i+ | and λ i−, |     | ,n. |     |     |     |     |     |     |
| ---- | --------- | --- | --- | --- | --- | --- | --- | --- | --- |
Without loss of generality,we choose w =[1T,0T]T and w =[0T,1T]T,
|     |     |     |     |     |     | 1   | n n | 2   | n n |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
whereitcanbeverifiedthatw andw arearighteigenvectorandgeneralized
|     |     |     |     | 1   | 2   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
righteigenvectorofΘassociatedwiththezeroeigenvalue,respectively.Noting
thatΘ hasexactlytwozeroeigenvalues,weknowthat−L has asimple zero
n
eigenvalue,whichinturnimpliesthatthereexistsann×1nonnegativevector
| psuchthatpTL |     | =0and1Tp=1,asshowninLemma2.6.Itcanbeverified |     |     |     |     |     |     |     |
| ------------ | --- | -------------------------------------------- | --- | --- | --- | --- | --- | --- | --- |
|              |     | n                                            |     | n   |     |     |     |     |     |
that ν = [pT,0T]T and ν = [0T,pT]T are a generalized left eigenvector
|     | 1   | n   |     | 2   | n   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
and left eigenvector of Θ associated with the zero eigenvalue, respectively,
where ν Tw = 1 and ν Tw = 1. Noting that the eigenvalues λ and λ i−,
|     | 1 1 |     | 2   | 2   |     |     |     |     | i+  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
i=2,···
|     | ,n, | have negative |     | real parts, | we see | that |     |     |     |
| --- | --- | ------------- | --- | ----------- | ------ | ---- | --- | --- | --- |

4.1 Consensus Algorithm 81
eΘt =PeJtP −1
⎡ ⎤
1 t 0 1×(2n−2)
=P ⎣ 0 1 0 1×(2n−2) ⎦ P −1,
0 (2n−2)×1 0 (2n−2)×1
eJ(cid:2)t
(cid:22) (cid:23)
1 pT t1 pT
which converges to n n for large t, where we have used the fact
0 n×n 1 n pT
that eJ(cid:2)t →0 (2n−2)×(2n−2) for large t.
Noting that for large t,
(cid:22) (cid:23) (cid:11)(cid:22) (cid:23) (cid:12)(cid:22) (cid:23)
ξ(t) 1 pT t1 pT ξ(0)
→ n n ⊗I ,
ζ(t) 0 n×n 1 n pT m ζ(0)
we see that ξ(t) → (1 pT ⊗ I )ξ(0) + t(1 pT ⊗ I )ζ(0) and ζ(t) →
n m n m
(1 pT ⊗I )ζ(0) for large t. As a result, we know that (cid:9)ξ (t)−ξ (t)(cid:9) → 0
n m i j
and(cid:9)ζ (t)−ζ (t)(cid:9)→0,ast→∞,thatis,consensusis achievedfor the team
i j
of vehicles.
(Necessity.) Suppose that the sufficient condition that Θ has exactly two
zero eigenvalues and all other eigenvalues have negative real parts does not
hold. Noting that Θ has at least two zero eigenvalues, the fact that the suf-
ficient condition does not hold implies that Θ has either more than two zero
eigenvalues or it has two zero eigenvalues and at least one eigenvalue with a
positive real part. Without loss of generality, assume that ς = ς = 0 and
1 2
Re(ς ) ≥ 0, where ς , k = 1,··· ,2n, denotes the kth eigenvalue of Θ and
3 k
Re(·) represents the real part of a number. Letting J = [j ] be the Jordan
k(cid:7)
canonical form of Θ, we know that j =ς , k =1,··· ,2n. Then we see that
kk k
ejkkt (cid:6)= 0, k = 1,2,3, for large t, which in turn implies that the first three
rows of eJt are linearly independent for large t. Therefore, we know that the
rank of eJt is at least three for large t, which implies that the rank of eΘt is
atleastthreef(cid:22)orlarg(cid:23)et.Notethatconsensusisreachedasymptoticallyifand
1 pT
onlyif eΘt → n forlarget,where pandq aren×1vectors.Asa result,
1 qT
n
the rank of eΘt cannot exceed two for larget. This results in a contradiction.
If all of the nonzero eigenvalues of −L are real and hence negative, it is
n
straightforward using (4.7) to verify that all nonzero eigenvalues of Θ have
negative real parts. We have the following lemma and corollary:
Lemma 4.2.If −L has a simple zero eigenvalue and all other eigenvalues
n
are real and hence negative, then algorithm (4.2) achieves consensus asymp-
totically for any γ >0.
Corollary 4.3.Suppose that G is undirected. Then algorithm (4.2) achieves
n
consensus asymptotically for any γ >0 if and only if G is connected.
n
In the generalcase, some nonzero eigenvalues of Θ may have positive real
parts even if all of the nonzero eigenvalues of −L have negative real parts,
n

82 4 Consensus Algorithms for Double-integrator Dynamics
as shown in the following five examples. In all five examples, we assume that
a = 1 if (j,i) ∈ E and γ = 1 in (4.2) unless stated otherwise. In addition,
ij n
we let ξ (0)=0.2(i−1) and ζ (0)=0.1(i−1), i=1,··· ,4.
i i
Example 4.4. When the interaction topology has separated subgroups, as
shown in Fig. 4.1, consensus cannot be achieved for the team of vehicles
because the information states and their derivatives from different separated
groupsdo notaffecteachother.We alsoknowthat−L has atleasttwozero
n
eigenvalues in this case from the necessity part of the proof of Lemma 2.4,
which in turn implies that Θ has at least four zero eigenvalues.
(cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) (cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13)
1 4
(cid:14)(cid:14) (cid:14)(cid:14)
(cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) (cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13)
2 3
Fig. 4.1. A directed graph with separated subgroups
Figure4.2showstheevolutionoftheinformationstatesξ andtheirderiv-
i
atives ζ , i = 1,··· ,4, using consensus algorithm (4.2) under the interaction
i
topology given by Fig. 4.1. Note that vehicles 1 and 2 reach consensus, and
vehicles 3 and 4 also reach consensus although the whole team cannot reach
consensus because the separate subgroups do not exchange information with
each other. (cid:13)(cid:14)
Example 4.5. When the interaction topology has multiple vehicles that have
only outgoing edges, as shown in Fig. 4.3, where both vehicle 1 and vehicle
4 have only outgoing edges, consensus cannot be achieved for the team of
vehicles because those vehicles’ information states and their derivatives are
notaffectedbyanyothervehicleintheteam.Notingthat−L hasatleasttwo
n
rowswithallzeroentriesinthiscase,weknowthat−L hasatleasttwozero
n
eigenvalues, which in turn implies that Θ has at least four zero eigenvalues.
Figure4.4showstheevolutionoftheinformationstatesξ andtheirderiv-
i
atives ζ , i = 1,··· ,4, using consensus algorithm (4.2) under the interaction
i
topology given by Fig. 4.3. Note that only vehicles 1 and 2 reach consensus.
(cid:13)(cid:14)
Example 4.6. When the interaction topology is undirected and connected, as
shown in Fig. 4.5, consensus is achieved asymptotically. Note that in the
case of undirected graphs, −L has a simple zero eigenvalue and all other
n
eigenvalues are negative if and only if the associated graph is connected.
Figure4.6showstheevolutionoftheinformationstatesξ andtheirderiv-
i
atives ζ , i = 1,··· ,4, using consensus algorithm (4.2) under the interaction
i
topologygivenbyFig.4.5.Note thatconsensusis reachedforallvehicles. (cid:13)(cid:14)

|     |     |     | 4.1 Consensus | Algorithm | 83  |
| --- | --- | --- | ------------- | --------- | --- |
4
i=1
i=2
3
i=3
i=4
2
ξ i
1
0
−1
| 0   | 1 2 | 3 4 5 | 6 7 | 8 9 | 10  |
| --- | --- | ----- | --- | --- | --- |
Time (s)
0.5
i=1
| 0.4 |     |     |     |     | i=2 |
| --- | --- | --- | --- | --- | --- |
i=3
| 0.3 |     |     |     |     | i=4 |
| --- | --- | --- | --- | --- | --- |
0.2
ζ i
0.1
0
−0.1
−0.2
| 0   | 1 2 | 3 4 5 | 6 7 | 8 9 | 10  |
| --- | --- | ----- | --- | --- | --- |
Time (s)
Fig. 4.2. Evolution of theinformation states andtheirderivativesundertheinter-
| action topology | given byFig. | 4.1                                                                                                                                               |                  |     |     |
| --------------- | ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------- | --- | --- |
|                 |              | (cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) (cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13)                 |                  |     |     |
|                 |              | 1                                                                                                                                                 | 4                |     |     |
|                 |              | (cid:14)(cid:14)                                                                                                                                  | (cid:14)(cid:14) |     |     |
|                 |              | (cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) (cid:15)(cid:15)(cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) |                  |     |     |
|                 |              | 2                                                                                                                                                 | 3                |     |     |
Fig. 4.3. A directed graph with multiplevehicles having only outgoing edges
Example 4.7. Whentheinteractiontopologyisitselfadirectedspanningtree,
as shown in Fig. 4.7, it is straightforward to see that −L can be written as
n
an upper diagonal matrix by permutation transformations. As a result, we
knowthatzeroisasimpleeigenvalueof−L andallothereigenvaluesof−L
|     |     |     | n   |     | n   |
| --- | --- | --- | --- | --- | --- |
are negative. Therefore, we know that consensus is achieved asymptotically
| in the case | of a directed | spanning tree. |     |     |     |
| ----------- | ------------- | -------------- | --- | --- | --- |
Figure4.8showstheevolutionoftheinformationstatesξ andtheirderiv-
i
1,···
atives ζ i , i = ,4, using consensus algorithm (4.2) under the interaction
topologygivenbyFig.4.7.Note thatconsensusis reachedforallvehicles. (cid:13)(cid:14)

| 84 4 Consensus | Algorithms | for Double-integrator | Dynamics |     |     |
| -------------- | ---------- | --------------------- | -------- | --- | --- |
4
i=1
i=2
3
i=3
i=4
2
ξ i
1
0
−1
| 0   | 1 2 | 3 4 5 | 6 7 | 8 9 | 10  |
| --- | --- | ----- | --- | --- | --- |
Time (s)
0.3
i=1
i=2
| 0.2 |     |     |     |     | i=3 |
| --- | --- | --- | --- | --- | --- |
i=4
0.1
ζ i
0
−0.1
−0.2
| 0   | 1 2 | 3 4 5 | 6 7 | 8 9 | 10  |
| --- | --- | ----- | --- | --- | --- |
Time (s)
Fig. 4.4. Evolution of theinformation states andtheirderivativesundertheinter-
| action topology | given byFig. | 4.3.                                                                                                                              |       |     |     |
| --------------- | ------------ | --------------------------------------------------------------------------------------------------------------------------------- | ----- | --- | --- |
|                 |              | (cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) (cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) |       |     |     |
|                 |              | 1                                                                                                                                 | 4     |     |     |
|                 |              | (cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) (cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) |       |     |     |
|                 |              | 2                                                                                                                                 | 3     |     |     |
|                 | Fig.         | 4.5. A connected undirected                                                                                                       | graph |     |     |
Example 4.8. Note that the undirected connected topology and the directed
spanning tree can be considered special cases of an interaction topology that
has a directed spanning tree. When the interaction topology has a directed
spanningtree,asshowninFig.4.9,consensusmaynotbeachieved,wherethe
consensus algorithm is given by (2.2). However, having a directed spanning
treeisanecessaryconditionforinformationconsensus,aswillbeshownbelow.
Figures 4.10 and 4.11 show the evolution of the information states ξ and
i
1,···
their derivatives ζ i , i = ,4, using consensus algorithm (4.2) under the
interaction topology given by Fig. 4.9 with γ = 1 and γ = 0.4, respectively.
Note that consensus is reached for γ = 1 but is not reached for γ = 0.4.

|     |     |     | 4.1 Consensus | Algorithm | 85  |
| --- | --- | --- | ------------- | --------- | --- |
2
i=1
i=2
| 1.5 |     |     |     |     | i=3 |
| --- | --- | --- | --- | --- | --- |
i=4
ξ i 1
0.5
0
| 0   | 1 2 | 3 4 5 | 6 7 | 8 9 | 10  |
| --- | --- | ----- | --- | --- | --- |
Time (s)
0.4
i=1
i=2
| 0.3 |     |     |     |     | i=3 |
| --- | --- | --- | --- | --- | --- |
i=4
0.2
ζ i
0.1
0
−0.1
| 0   | 1 2 | 3 4 5 | 6 7 | 8 9 | 10  |
| --- | --- | ----- | --- | --- | --- |
Time (s)
Fig. 4.6. Evolution of theinformation states andtheirderivativesundertheinter-
| action topology | given byFig. | 4.5                                                                                                                                               |     |     |     |
| --------------- | ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------- | --- | --- | --- |
|                 |              | (cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) (cid:15)(cid:15)(cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) |     |     |     |
|                 |              | 1                                                                                                                                                 | 4   |     |     |
(cid:14)(cid:14)
|     |      | (cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) (cid:15)(cid:15)(cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) |               |     |     |
| --- | ---- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------- | --- | --- |
|     |      | 2                                                                                                                                                 | 3             |     |     |
|     | Fig. | 4.7. A directed                                                                                                                                   | spanning tree |     |     |
Unlikethepreviouscaseswhereconvergencedoesnotdependonγ,consensus
may not generally be reached with small γ, given interaction topologies with
a directed spanning tree other than those from Examples 4.6 and 4.7.
By comparing Figs. 4.7 and 4.9, we see that more information exchange
is involved in Fig. 4.9 than in Fig. 4.7 in the sense that vehicle 3 sends infor-
mation to vehicle 1 in Fig. 4.9. However, although the consensus algorithm
convergesundertheinteractiontopologygivenbyFig.4.7foranyγ >0,con-
sensusalgorithm(4.2)doesnotconvergeundertheinteractiontopologygiven
by Fig. 4.9 if γ is too small. This is somewhat contradictory to our intuition

| 86  | 4   | Consensus | Algorithms |     | for Double-integrator | Dynamics |     |     |
| --- | --- | --------- | ---------- | --- | --------------------- | -------- | --- | --- |
0.8
i=1
i=2
0.6
i=3
i=4
0.4
ξ i
0.2
0
−0.2
|     | 0   | 1   | 2   | 3   | 4 5 | 6 7 | 8 9 | 10  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Time (s)
0.3
i=1
|     | 0.2 |     |     |     |     |     |     | i=2 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
i=3
|     | 0.1 |     |     |     |     |     |     | i=4 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
0
ζ i
−0.1
−0.2
−0.3
−0.4
|     | 0   | 1   | 2   | 3   | 4 5 | 6 7 | 8 9 | 10  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Time (s)
Fig. 4.8. Evolution of theinformation states andtheirderivativesundertheinter-
| action | topology | given | byFig. | 4.7 |                                                                                                                                                   |     |     |     |
| ------ | -------- | ----- | ------ | --- | ------------------------------------------------------------------------------------------------------------------------------------------------- | --- | --- | --- |
|        |          |       |        |     | (cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) (cid:15)(cid:15)(cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) |     |     |     |
|        |          |       |        |     | 1 (cid:25)(cid:25)(cid:11)                                                                                                                        | 4   |     |     |
(cid:11)
|     |     |     |     |     | (cid:11) (cid:11) |     |     |     |
| --- | --- | --- | --- | --- | ----------------- | --- | --- | --- |
(cid:11)
(cid:11) (cid:11)
(cid:11) (cid:11)
(cid:14)(cid:14)
|     |     |      |        |          | (cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) (cid:15)(cid:15)(cid:14)(cid:10)(cid:15)(cid:11)(cid:16)(cid:12)(cid:17)(cid:13) |                         |     |     |
| --- | --- | ---- | ------ | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------- | --- | --- |
|     |     |      |        |          | 2                                                                                                                                                 | 3                       |     |     |
|     |     | Fig. | 4.9. A | directed | graph with                                                                                                                                        | a directed spanningtree |     |     |
in the sense that more information exchange may lead to instability for the
| whole | team. | (cid:13)(cid:14) |     |     |     |     |     |     |
| ----- | ----- | ---------------- | --- | --- | --- | --- | --- | --- |
We have the following necessary condition for information consensus:
Theorem 4.9.If algorithm (4.2) achieves consensus asymptotically, then di-
| rected | graph | G   | has a directed |     | spanning tree.3 |     |     |     |
| ------ | ----- | --- | -------------- | --- | --------------- | --- | --- | --- |
n
3 In contrast, according to Theorem 2.8, the first-order consensus algorithm (2.2)
achieves consensus asymptotically if and only if the interaction topology has a
|     | directed | spanningtree. |     |     |     |     |     |     |
| --- | -------- | ------------- | --- | --- | --- | --- | --- | --- |

|     |     |     |     | 4.1 Consensus | Algorithm | 87  |
| --- | --- | --- | --- | ------------- | --------- | --- |
1.4
i=1
| 1.2 |     |     |     |     |     | i=2 |
| --- | --- | --- | --- | --- | --- | --- |
i=3
| 1   |     |     |     |     |     | i=4 |
| --- | --- | --- | --- | --- | --- | --- |
0.8
ξ i
0.6
0.4
0.2
0
| 0   | 1   | 2 3 | 4 5 | 6 7 | 8 9 | 10  |
| --- | --- | --- | --- | --- | --- | --- |
Time (s)
0.3
i=1
i=2
| 0.2 |     |     |     |     |     | i=3 |
| --- | --- | --- | --- | --- | --- | --- |
i=4
0.1
ζ i
0
−0.1
−0.2
| 0   | 1   | 2 3 | 4 5 | 6 7 | 8 9 | 10  |
| --- | --- | --- | --- | --- | --- | --- |
Time (s)
Fig. 4.10. Evolution of the information states and their derivatives under the in-
| teraction topology | given | byFig. | 4.9 with γ =1 |     |     |     |
| ------------------ | ----- | ------ | ------------- | --- | --- | --- |
Proof: If algorithm (4.2) achieves consensus asymptotically, following
Lemma 4.1, we know that Θ has exactly two zero eigenvalues. Therefore,
weseethatL hasasimplezeroeigenvalue.Corollary2.5impliesthatG has
|                     | n   |       |     |     |     | n   |
| ------------------- | --- | ----- | --- | --- | --- | --- |
| a directed spanning |     | tree. |     |     |     |     |
Before showing a sufficient condition for information consensus, we need
| the following  | lemma: |     |     |     |     |     |
| -------------- | ------ | --- | --- | --- | --- | --- |
| Lemma 4.10.Let |        |     |     |     |     |     |
(cid:25)
|     |     | γμ−α± | (γμ−α)2+4μ |     |     |     |
| --- | --- | ----- | ---------- | --- | --- | --- |
|     |     | ρ± =  |            | ,   |     |     |
2
| where ρ,μ∈C. | If α≥0, | Re(μ)<0, | Im(μ)>0, | and |     |     |
| ------------ | ------- | -------- | -------- | --- | --- | --- |
(cid:26)
(cid:27)
|     |     | (cid:27)    | 2            |           |     |       |
| --- | --- | ----------- | ------------ | --------- | --- | ----- |
|     |     | γ >(cid:28) | (cid:29)     | (cid:30), |     | (4.9) |
|     |     |             | |μ|cos tan−1 | Im(μ)     |     |       |
−Re(μ)
|     |     | Re(·) | Im(·) |     |     |     |
| --- | --- | ----- | ----- | --- | --- | --- |
then Re(ρ±) < 0, where and represent, respectively, the real and
| imaginary parts | of  | a number. |     |     |     |     |
| --------------- | --- | --------- | --- | --- | --- | --- |

88 4 Consensus Algorithms for Double-integrator Dynamics
1.4
1.2
1
0.8
0.6
0.4
0.2
0
0 1 2 3 4 5 6 7 8 9 10
Time (s)
ξ i
i=1
i=2
i=3
i=4
0.4
0.3
0.2
0.1
0
−0.1
−0.2
−0.3
0 1 2 3 4 5 6 7 8 9 10
Time (s)
ζ i
i=1
i=2
i=3
i=4
Fig. 4.11. Evolution of the information states and their derivatives under the in-
teraction topology given by Fig. 4.9 with γ =0.4. Consensus is not reached in this
case.
(cid:2)
Proof: 4 WeuseFig.4.12toshowthenotationsusedintheproof.Leta=γμ,
(cid:25)
(cid:2) (cid:2) (cid:2) (cid:2)
b = (γμ)2+4μ, and c = γμ − α. Also let s = (γμ)2, s = 4μ, and
1 2
(cid:2) (cid:2) (cid:2) (cid:2)
s = (γμ)2 +4μ. Furthermore, we let q = (γμ−α)2, q = 4μ, and q =
3 1 2 3
(γμ−α)2+4μ.
When α = 0, consider the triangle formed by vectors s , s , and s ,
1 2 3
where η is the inner angle of the triangle that faces the edge s . Accord-
i i
ing t(cid:31)o the law of cosines, |s
3
|2 = |s
1
|2+|s
2
|2−2|s
1
||s
2
|cosη
3
. Note that if
γ > 2 , then |s |2 > |s |2. Also note that η = tan−1 Im(μ) . There-
|μ|cosη3 1 3 3 −Re(μ)
fore, Inequality (4.9) guarantees that |s | > |s |, which in turn implies that
1 3
|a| > |b|. Noting that the phase angle of b is smaller than a, we know that
Re(ρ±)=Re(a±b)<0.
2
When α>0, note that Inequality (4.9) implies that |s |>|s | and hence
1 3
η > η . Represent a and c in polar coordinates as (r ,θ ) and (r ,θ ), re-
1 3 1 1 2 2
spectively, where θ ∈ (π,π), i = 1,2. Then s and q can be represented in
i 2 1 1
4 The proof is motivated by [203]. In particular, the proof for the case of α = 0
follows directly from Theorem 6 in [203].

|     |     |     | 4.1 | Consensus Algorithm | 89  |
| --- | --- | --- | --- | ------------------- | --- |
polarcoordinatesas(r2,2θ )and(r2,2θ ),respectively.Consideranothertri-
|     |     | 1 1 | 2 2 |     |     |
| --- | --- | --- | --- | --- | --- |
angle composed of vectorsq , q , and q with inner angles givenby φ , where
|     |     | 1 2 | 3   | i   |     |
| --- | --- | --- | --- | --- | --- |
φ i faces the edge q i . Noting that θ 2 > θ 1 , we know that 2θ 2 > 2θ 1 . We can
then show that φ > η and φ < η by noting that s = q and comparing
|     | 1   | 1 3 | 3   | 2 2 |     |
| --- | --- | --- | --- | --- | --- |
the triangles composed of q and s respectively, which implies that φ >φ .
|     |     | i   | i          | 1   | 3   |
| --- | --- | --- | ---------- | --- | --- |
|     |     |     | |q |>|q |. |     |     |
Using the law of cosines, we know that As a result, we know that
|          |              |             | 1 3             |          |     |
| -------- | ------------ | ----------- | --------------- | -------- | --- |
| Re(ρ±)<0 | by following | an argument | similar to that | for α=0. |     |
Fig. 4.12. Graphical view of notations used in theproof of Lemma 4.10
Theorem 4.11.Let μ , i = 1,··· ,n, denote the ith eigenvalue of −L . Al-
|     |     | i   |     |     | n   |
| --- | --- | --- | --- | --- | --- |
G
gorithm (4.2) achieves consensus asymptotically if directed graph has a
n
| directed | spanning tree | and |        |     |        |
| -------- | ------------- | --- | ------ | --- | ------ |
|          |               |     | γ >γ¯, |     | (4.10) |
(cid:2)
where γ¯ =0 if all of the n−1 nonzero eigenvalues of −L are negative and
n
(cid:26)
(cid:27)
|     |           |              | (cid:27) (cid:29) | 2 (cid:30)   |     |
| --- | --------- | ------------ | ----------------- | ------------ | --- |
|     | γ¯ =      | max          | (cid:28)          |              |     |
|     | ∀Re(μi)<0 | and Im(μi)>0 | |μ |cos           | tan−1 Im(μi) |     |
|     |           |              | i                 | −Re(μi)      |     |
otherwise.

| 90  | 4 Consensus | Algorithms |     | for Double-integrator |     | Dynamics |     |     |     |
| --- | ----------- | ---------- | --- | --------------------- | --- | -------- | --- | --- | --- |
|     | G           |            |     |                       |     |          |     |     | −L  |
Proof: If has a directed spanning tree, Corollary2.5 implies that has
|     |     | n   |     |     |     |     |     |     | n   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
a simple zero eigenvalue and all other eigenvalues have negative real parts.
2,···
Without loss of generality, we let μ 1 = 0 and Re(μ i ) < 0, i = ,n.
Then we know that Θ has exactly two zero eigenvalues. Note that if μ < 0,
i
then(4.7)impliesthatRe(λ i±)<0foranyγ >0,whereλ areeigenvaluesof
i±
Θ associatedwith μ . It is left to show that Inequality (4.10)guaranteesthat
i
alleigenvaluesofΘ associatedwithμ thatsatisfyRe(μ )<0andIm(μ )(cid:6)=0
|     |     |     |     | i   |     |     | i   |     | i   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
havenegativerealparts.Weneedonlytoconsiderμ i thatsatisfiesRe(μ i )<0
and Im(μ ) > 0 because any μ that satisfies Re(μ ) < 0 and Im(μ ) < 0 is
|     | i   |     |     | i   |     | i   |     |     | i   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
a complex conjugate of some μ that satisfies Re(μ ) < 0 and Im(μ ) > 0.
|     |     |     |     | i   |     | i   |     |     | i   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
ThisargumentthenfollowsfromLemma4.10.Asaresult,Lemma4.1implies
that consensus can be achieved asymptotically under the assumption of the
theorem.
We also have the following lemma regarding the consensus equilibrium.
Lemma 4.12.Suppose that Θ has exactly two zero eigenvalues and all other
→
e(cid:7)igenvalues have negative real parts. If ζ i (0) = 0, i = 1,...,n, then ξ i (t)
n
|     | p ξ (0)andζ | (t)→0,i=1,...,n,as |     |     | t→∞,where |     | p=[p | ,...,p | ]T ≥ |
| --- | ----------- | ------------------ | --- | --- | --------- | --- | ---- | ------ | ---- |
|     | i=1 i i     | i                  |     |     |           |     |      | 1      | n    |
0, 1Tp = 1, and LTp = 0. In addition, if ζ (0) = 0, i ∈ I , where I
|     | n   | n   |     |     |     | i   |     | L   | L   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
denotes(cid:7)the set of vehicles that have a directed path to all other vehicles, then
| ξ   | (t)→ | p ξ (0) | and ζ | (t)→0, i=1,...,n, |     | as t→∞. |     |     |     |
| --- | ---- | ------- | ----- | ----------------- | --- | ------- | --- | --- | --- |
| i   | i∈IL | i i     | i     |                   |     |         |     |     |     |
Proof: The first part of the lemma follows directly from Lemma 4.1. For
(cid:6)=
the second part of the lemma, we note that p i 0 if vehicle i has a di-
rected path to all other vehicles and p = 0 otherwise (see the subsec-
i
tion on(cid:7)consensus equilib(cid:7)rium in Section 2.2.1). As(cid:7)a result, we know that
|     | (t)→       |           |           |            |       | (t)→ |      |         | t→∞, |
| --- | ---------- | --------- | --------- | ---------- | ----- | ---- | ---- | ------- | ---- |
| ξ   |            | p ξ (0)+t |           | p ζ (0)    | and ζ |      |      | p ζ (0) | as   |
| i   | i∈IL       | i i       | i∈IL      | i i        | i     |      | i∈IL | i i     |      |
| and | the second | part of   | the lemma | is proved. |       |      |      |         |      |
Remark 4.13. Relevant to this subsection are [69] and [203], where forma-
tionstabilizationandalignmentproblemsareconsideredformultiple vehicles
modeled by double-integrator or more complicated linear dynamics. In [69],
informationexchangetechniquesarestudiedtoimprovestabilitymarginsand
the accuracy of vehicle formations. Reference [203] derives matrix theoreti-
cal conditions under which alignment can be achieved for multiple vehicles
with double-integrator dynamics in a general multi-observation setting. In
contrast, this subsection applies graph theoretical tools to explore explicit
graphicalconditions on the interactiontopologies under which consensus can
be achieved. As another comparison, this subsection focuses on analyzing
whether a given consensus algorithm converges, whereas [69] and [203] con-
siderwhetherafeedbackgainexiststoachieveformationstabilizationoralign-
ment. (cid:13)(cid:14)

4.1 Consensus Algorithm 91
4.1.2 Convergence Analysis Under Switching Interaction
Topologies
In the case of switching interaction topologies, the convergence analysis is
more involved than that for a fixed interaction topology. For first-order con-
sensus algorithm (2.2), we have shown in Theorem 2.33 that consensus can
be achievedasymptoticallyunder switchinginteractiontopologiesifthere ex-
ist infinitely many uniformly bounded, consecutive time intervals such that
the union of the directed graphs across each such interval has a directed
spanning tree. However, as shown in the following example, this condition is
generally not sufficient for information consensus for second-order consensus
algorithm (4.2).
Example 4.14. Let
⎡ ⎤ ⎡ ⎤ ⎡ ⎤
1−10 1 −1 0 00 0
L = ⎣ 0 0 0 ⎦ , L = ⎣ 0 1 −1 ⎦ , and L = ⎣ 01 −1 ⎦ .
3(1) 3(2) 3(3)
0 0 0 −2 0 2 00 0
Also let γ =γ =γ =1. Let Θ be defined as
1 2 3 i
(cid:22) (cid:23)
Θ = 0 3×3 I 3 ,
i −L −γ L
3(i) i 3(i)
where i = 1,2,3. Note that the directed graphs of L and L , denoted
3(1) 3(3)
Γ[L ]andΓ[L ]respectively,donothavedirectedspanningtreeswhereas
3(1) 3(3)
the directedgraphofL , denotedΓ[L ],does.Also note that Θ hasex-
3(2) 3(2) 2
actly two zero eigenvalues and all other nonzero eigenvalues have negative
real parts, whereas both Θ and Θ have exactly four zero eigenvalues and
1 3
all other nonzero eigenvalues have negative real parts. At each time interval
of 5 seconds, we let the interaction topology be Γ[L ] 90% of the time and
3(1)
be Γ[L ] the rest of the time. Note that at each time interval of 5 seconds,
3(2)
theunionoftheinteractiontopologiesΓ[L ]∪Γ[L ]hasadirectedspan-
3(1) 3(2)
ning tree. Using first-order algorithm (2.2), consensus is achieved, as shown
in Fig. 4.13. However, as shown in Fig. 4.14, consensus is not achieved us-
ing second-order algorithm (4.2). However, if we increase the gain γ to 10,
2
consensus is achieved asymptotically, as shown in Fig. 4.15. Alternatively, if
we reduce the length of each time interval to 1 second, consensus is achieved
asymptotically, as shown in Fig. 4.16. In addition, if we let the interaction
topology be Γ[L ] 50% of the time and be Γ[L ] the rest of the time,
3(1) 3(2)
consensus is achieved asymptotically, as shown in Fig. 4.17. Next, at each
time interval of 5 seconds, we let the interaction topology be Γ[L ] 90%
3(1)
of the time and be Γ[L ] the rest of the time. Note that at each time in-
3(3)
terval of 5 seconds,the union of the interactiontopologiesΓ[L ]∪Γ[L ]
3(1) 3(3)
has a directed spanning tree. Also note that Γ[L ] is only a subgraph of
3(3)
Γ[L ]. In contrast to Fig. 4.14, Fig. 4.18 shows that consensus is achieved
3(2)
asymptotically even if Γ[L ] has less information exchange than Γ[L ].
3(3) 3(2)
(cid:13)(cid:14)

| 92 4 Consensus | Algorithms | for Double-integrator | Dynamics |     |
| -------------- | ---------- | --------------------- | -------- | --- |
0.6
i=1
i=2
i=3
0.5
0.4
0.3
i
ξ
0.2
0.1
0
−0.1
| 0   |     | 5   | 10  | 15  |
| --- | --- | --- | --- | --- |
Time (s)
Fig.4.13.Consensusofinformationunderdirectedswitchinginteractiontopologies
using first-order algorithm (2.2) {Γ[L 3(1)] : 90%, Γ(L 3(2)) : 10%}. Consensus is
| achieved in this | case. |     |     |     |
| ---------------- | ----- | --- | --- | --- |
In the simple case where the interaction topology among vehicles is undi-
rected and is based on their physical proximity, that is, there is information
exchange between vehicle i and j if and only if the distance between them
is below a certain threshold, we have the following lemma for information
consensus:
4.15.Iftime-varyinggraphG
| Lemma              |                | n (t)isundirectedandconnectedateach |                 |     |
| ------------------ | -------------- | ----------------------------------- | --------------- | --- |
| instant, algorithm | (4.2) achieves | consensus                           | asymptotically. |     |
Proof: Let V = 1(cid:9)ξ −ξ (cid:9)2. The second equation in (4.1) can be rewritten
ij 2 i j
as
|     | (cid:2)n | (cid:2)n |     |     |
| --- | -------- | -------- | --- | --- |
∂V
|     | ζ˙ =− | a ij −γ | a (ζ −ζ ). | (4.11) |
| --- | ----- | ------- | ---------- | ------ |
|     | i     | ij ∂ξ   | ij i j     |        |
i
|     | j=1 | j=1 |     |     |
| --- | --- | --- | --- | --- |
G
Note that a ij =a ji because n (t) is undirected. Also note that (4.11) can be
writteninmatrixformasζ˙ =−[L (t)⊗I ]ξ−γ[L (t)⊗I ]ζ,whereL (t)is
|     |     | n m | n m | n   |
| --- | --- | --- | --- | --- |
G
the Laplacian matrix associated with undirected graph n at time t. Noting
that (4.11)has the same formas (4) in [231],we can follow a proof similar to
that ofTheoremVI.2 in [231]to showthat (cid:9)ζ (t)−ζ (t)(cid:9)→0 andζ˙(t)→0,
|     |     |     | i j | i   |
| --- | --- | --- | --- | --- |

|     |     |     |     |     | 4.1 | Consensus | Algorithm | 93  |
| --- | --- | --- | --- | --- | --- | --------- | --------- | --- |
15
i=1
i=2
10
i=3
5
ξ i
0
−5
−10
|     | 0   |     | 5   |     |     | 10  |     | 15  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Time (s)
5
i=1
i=2
|     | 0   |     |     |     |     |     |     | i=3 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
ζ i −5
−10
−15
|     | 0   |     | 5   |     |     | 10  |     | 15  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Time (s)
Fig. 4.14. Consensus of information under switching interaction topologies using
|     |     |     | {Γ[L |     | Γ[L | 10%}. |     |     |
| --- | --- | --- | ---- | --- | --- | ----- | --- | --- |
second-order algorithm (4.2) 3(1)] : 90%, 3(2)] : Consensus is not
| achieved                     | in this | case. |     |     |       |                      |     |      |
| ---------------------------- | ------- | ----- | --- | --- | ----- | -------------------- | --- | ---- |
| ast→∞.Asaresult,weknowthat[L |         |       |     |     | (t)⊗I | ]ξ(t)→0,whichimplies |     |      |
|                              |         |       |     | n   |       | m                    |     | that |
(cid:9)ξ (t)−ξ (t)(cid:9) → 0, as t → ∞, because undirected graph G (t) is connected
|     | i j |     |     |     |     |     | n   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
at each instant.
In the general case where the interaction topology among vehicles is di-
rected and is switching randomly with time, we assume that (4.3) can be
| written | as  |     | (cid:22) (cid:23) |     | (cid:22) | (cid:23) |     |     |
| ------- | --- | --- | ----------------- | --- | -------- | -------- | --- | --- |
ξ˙
⊗I ξ
|     |     |     | =(Θ |     | )   | ,   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     | ζ˙  | σ   | m ζ |     |     |     |
:[0,∞)→P
where σ is a piecewise constant switching signal with switching
times t ,t ,··· and P denotes a set indexing the class of all possible directed
|     | 0 1 |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
interaction topologies for the n vehicles that have directed spanning trees.
Here we assume that Θ(t) is piecewise constant and satisfies Θ(t) = Θ(t ),
i
| t∈[t | ,t ). |     |     |     |     |     |     |     |
| ---- | ----- | --- | --- | --- | --- | --- | --- | --- |
i i+1
|     | (cid:2) |     | (cid:2) |     |     |     |     |     |
| --- | ------- | --- | ------- | --- | --- | --- | --- | --- |
Let ξ = ξ −ξ and ζ = ζ −ζ be the consensus error variables. Note
|      | ij    | i j | ij i  | j   |          |               |       |        |
| ---- | ----- | --- | ----- | --- | -------- | ------------- | ----- | ------ |
|      |       | −ξ  |       | −ζ  |          |               |       |        |
| that | ξ = ξ | and | ζ = ζ | .   | Defining | the consensus | error | vector |
|      | ij 1j | 1i  | ij 1j | 1i  |          |               |       |        |
as ξ˜ = [ξT ,ξT ,...,ξT ]T and ζ˜ = [ζT ,ζT,...,ζT ]T, we get the following
|     | 12  | 13 1n |     | 12  | 13  | 1n  |     |     |
| --- | --- | ----- | --- | --- | --- | --- | --- | --- |
equation:

| 94  | 4   | Consensus | Algorithms |     | for | Double-integrator | Dynamics |     |     |
| --- | --- | --------- | ---------- | --- | --- | ----------------- | -------- | --- | --- |
2
i=1
|     | 1   |     |     |     |     |     |     |     | i=2 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
i=3
0
ξ i −1
−2
−3
−4
|     | 0   |     | 5   |     | 10  | 15  | 20  | 25  | 30  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Time (s)
0.3
i=1
|     | 0.2 |     |     |     |     |     |     |     | i=2 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
i=3
0.1
0
ζ i
−0.1
−0.2
−0.3
−0.4
|     | 0   |     | 5   |     | 10  | 15  | 20  | 25  | 30  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Time (s)
Fig.4.15.Consensusofinformationunderdirectedswitchinginteractiontopologies
using second-order algorithm (4.2) with increased γ {Γ[L 3(1)] : 90%, Γ[L 3(2)] :
2
10%}.
|     | Consensus |     | is achieved | in  | this | case.    |          |     |        |
| --- | --------- | --- | ----------- | --- | ---- | -------- | -------- | --- | ------ |
|     |           |     |             |     |   !  |          |          |     |        |
|     |           |     |             |     |      | (cid:22) | (cid:23) |     |        |
|     |           |     |             |     | ξ˜˙  | ξ˜       |          |     |        |
|     |           |     |             |     | =(Δ  | ⊗I )     | ,        |     | (4.12) |
|     |           |     |             |     | ζ˜˙  | σ m ζ˜   |          |     |        |
2(n−1)×2(n−1)
where Δ σ is a matrix that can b(cid:18)e der(cid:18)ivedfrom Θ σ . If Δ σ
(cid:18) (cid:18)≤e(aσ−χσt),t≥0.
| is  | stable,we | can | find | a ≥0 | and χ | >0 such that | eΔσt |     |     |
| --- | --------- | --- | ---- | ---- | ----- | ------------ | ---- | --- | --- |
|     |           |     |      | σ    |       | σ            |      |     |     |
Before stating the theorem for information consensus under directed
switching interaction topologies, we need the following lemma:
Lemma 4.16. [146, Lemma 2] Let {A : p ∈ P} be a closed, bounded set
p
of real, n×n matrices. Suppose that for each p ∈ P, A is stable, and let
p
a and(cid:18)χ be(cid:18) any finite, nonnegative and positive numbers, respectively, for
| p   | (cid:18) | p (cid:18) |     |     |     |     |     |     |     |
| --- | -------- | ---------- | --- | --- | --- | --- | --- | --- | --- |
which eApt ≤ e(ap−χpt), t ≥ 0. Suppose that τ is a number satisfying
0
|     |       | {ap}. |     |     |            |           |          | [0,∞) | → P  |
| --- | ----- | ----- | --- | --- | ---------- | --------- | -------- | ----- | ---- |
| τ 0 | > sup | p∈P   | For | any | admissible | switching | signal σ | :     | with |
χp
dwelltimenosmaller thanτ ,thetransitionmatrixofA satisfies(cid:9)Φ(t,μ)(cid:9)≤
|             |     |         |     |       | 0     |      | σ         |     |         |
| ----------- | --- | ------- | --- | ----- | ----- | ---- | --------- | --- | ------- |
| e(a−χ(t−μ), |     | ∀t≥μ≥0, |     |       |       | {a } |           | {χ  | − a p}. |
|             |     |         |     | where | a=sup | p∈P  | and χ=inf | p∈P |         |
|             |     |         |     |       |       | p    |           | p   | τ0      |
Theorem 4.17.Lett ,t ,··· bethetimeswhendirectedgraphG (t)switches.
|     |     |     |     | 0 1 |     |     |     | n   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Alsoletτ bethedwelltimesuchthatt −t ≥τ,∀i=0,1,···.IfG (t)has a
|     |     |     |     |     |     | i+1 i |     |     | n   |
| --- | --- | --- | --- | --- | --- | ----- | --- | --- | --- |

|     |     |     |     |     |     | 4.1 | Consensus | Algorithm | 95  |
| --- | --- | --- | --- | --- | --- | --- | --------- | --------- | --- |
1
i=1
i=2
i=3
0.5
ξ i
0
−0.5
|     | 0   | 2   | 4   | 6   | 8   | 10  | 12 14 | 16  | 18 20 |
| --- | --- | --- | --- | --- | --- | --- | ----- | --- | ----- |
Time (s)
0.3
i=1
|     | 0.2 |     |     |     |     |     |     |     | i=2 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
i=3
0.1
0
ζ i
−0.1
−0.2
−0.3
−0.4
|     | 0   | 2   | 4   | 6   | 8   | 10  | 12 14 | 16  | 18 20 |
| --- | --- | --- | --- | --- | --- | --- | ----- | --- | ----- |
Time (s)
Fig.4.16.Consensusofinformationunderdirectedswitchinginteractiontopologies
using second-order algorithm (4.2) with decreased interval length {Γ[L 3(1)] : 90%,
Γ[L 3(2)]:10%}.
|     |     | Consensus |     | is achieved | in  | this case. |     |     |     |
| --- | --- | --------- | --- | ----------- | --- | ---------- | --- | --- | --- |
t∈[t
directed spanning tree for each ,t ), γ is constant and satisfies (4.10)
|     |     |     |     |     | i   | i+1 |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
for each σ ∈ P, and the dwell time τ satisfies τ > sup {aσ}, then algo-
|     |     |     |     |     |     |     |     | σ∈P χσ |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ------ | --- |
rithm (4.2) achieves consensus asymptotically and is robust to perturbations
| under | directed | switching |     | interaction | topologies. |     |     |     |     |
| ----- | -------- | --------- | --- | ----------- | ----------- | --- | --- | --- | --- |
Proof: Givenacertainσ ∈P,notethatG (t)hasadirectedspanningtreefor
|     |     |     |     | (cid:7) |     | n   |     |     |     |
| --- | --- | --- | --- | ------- | --- | --- | --- | --- | --- |
∈
t [t ,t ) and γ satisfies (4.10). Then we know that consensus is achieved
(cid:7) (cid:7)+1
asymptotically if σ(t) ≡ σ , ∀t ≥ 0, from Theorem 4.11, that is, ξ → ξ
|     |     |     |          | (cid:7) |                   |     |         |      | i j   |
| --- | --- | --- | -------- | ------- | ----------------- | --- | ------- | ---- | ----- |
|     | →   | ∀i  | (cid:6)= |         | ≡                 |     |         | ξ˜   | →     |
| and | ζ   | ζ , | j, if    | σ(t)    | σ . Equivalently, |     | we know | that | 0 and |
|     | i   | j   |          |         | (cid:7)           |     |         |      |       |
ζ˜→0 asymptotically if σ(t)≡σ , which implies that switched system (4.12)
(cid:7)
|     |     |     | ∈   | P   |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
is stable for each σ under the conditions of the theorem. As a result,
switched system (4.12) is globally exponentially stable if dwell time τ sat-
{aσ},
isfies τ > sup σ∈P according to Lemma 4.16. The stability of switched
χσ
system (4.12) implies that consensus can be achievedasymptotically. The ro-
bustness of consensus algorithm (4.2) to perturbations comes from the fact
| that | (4.12) | is globally | exponentially |     | stable. |     |     |     |     |
| ---- | ------ | ----------- | ------------- | --- | ------- | --- | --- | --- | --- |

| 96  | 4   | Consensus | Algorithms |     | for Double-integrator |     | Dynamics |     |     |
| --- | --- | --------- | ---------- | --- | --------------------- | --- | -------- | --- | --- |
2
i=1
i=2
1
i=3
0
ξ i
−1
−2
−3
|     | 0   |     |     | 5   |     |     | 10  |     | 15  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Time (s)
0.4
i=1
|     | 0.2 |     |     |     |     |     |     |     | i=2 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
i=3
0
−0.2
ζ i
−0.4
−0.6
−0.8
−1
|     | 0   |     |     | 5   |     |     | 10  |     | 15  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Time (s)
Fig.4.17.Consensusofinformationunderdirectedswitchinginteractiontopologies
using second-order algorithm (4.2) {Γ[L 3(1)] : 50%, Γ[L 3(2)] : 50%}. Consensus is
| achieved | in        | this case. |      |         |     |         |        |     |     |
| -------- | --------- | ---------- | ---- | ------- | --- | ------- | ------ | --- | --- |
| 4.2      | Consensus |            | with | Bounded |     | Control | Inputs |     |     |
Notethat(4.2)doesnotexplicitlytakeintoaccountaboundedcontroleffort.
We propose a consensus algorithm for (4.1) with bounded control inputs as
(cid:2)n
u =− {a tanh[K (ξ −ξ )]+b tanh[K (ζ −ζ )]}, i=1,...,n, (4.13)
|     | i   | ij  |     | r i | j ij | v   | i j |     |     |
| --- | --- | --- | --- | --- | ---- | --- | --- | --- | --- |
j=1
|       |     | Rm×m |     |     | Rm×m |              |     |                   |        |
| ----- | --- | ---- | --- | --- | ---- | ------------ | --- | ----------------- | ------ |
| where | K   | ∈    | and | K   | ∈    | are constant |     | positive-definite | diago- |
|       | r   |      |     | v   |      |              |     |                   |        |
nal matrices, a and b are, respectively, the (i,j) entry of the adjacency
|        |     | ij     |     | ij  |        |            |      |        |         |
| ------ | --- | ------ | --- | --- | ------ | ---------- | ---- | ------ | ------- |
|        | A   | ∈ Rn×n |     | B   | ∈ Rn×n |            |      | GA GB5 |         |
| matrix |     |        | and |     |        | associated | with | and    | respec- |
|        |     | n      |     | n   |        |            |      | n n    |         |
tively, and tanh(·) is defined componentwise as in Section 3.3.2. Note that
i(cid:7)isboundedbecausetanh(·)isbounded.Inparticular,itfollows
with(4.13),u
n
that (cid:9)u (cid:9) ≤ (a +b ), which is independent of the initial conditions
|     | i ∞             |        | j=1    | ij ij   |                    |        |     |     |     |
| --- | --------------- | ------ | ------ | ------- | ------------------ | ------ | --- | --- | --- |
| of  | the information |        | states | and     | their derivatives. |        |     |     |     |
|     | Before          | moving | on,    | we need | the following      | lemma: |     |     |     |
| 5   |                 |        |        |         |                    | ξ      | ζ   |     |     |
In this case, theinteraction topologies for i and i are allowed to be different.

4.2 Consensus with Bounded Control Inputs 97
20
15
10
5
0
−5
0 5 10 15 20 25 30 35 40 45 50
Time (s)
ξ i
i=1
i=2
i=3
1.5
1
0.5
0
−0.5
0 5 10 15 20 25 30 35 40 45 50
Time (s)
ζ i
i=1
i=2
i=3
Fig.4.18.Consensusofinformationunderdirectedswitchinginteractiontopologies
using second-order algorithm (4.2) {Γ[L 3(1)] : 90%, Γ[L 3(3)] : 10%}. Consensus is
achieved in this case.
Lemma 4.18.Suppose that ς ∈ Rm, ϕ ∈ Rm, K ∈ Rm×m, andC = [c ] ∈
ij
Rn×n. If C is symmetrical, then
(cid:2)n (cid:2)n (cid:2)n (cid:2)n
1
c (ς −ς )T tanh[K(ϕ −ϕ )]= c ςT tanh[K(ϕ −ϕ )],
2 ij i j i j ij i i j
i=1j=1 i=1j=1
(4.14)
and
(cid:2)n (cid:2)n (cid:2)n (cid:2)n
1
c (ς −ς )T(ϕ −ϕ )= c ςT(ϕ −ϕ ). (4.15)
2 ij i j i j ij i i j
i=1j=1 i=1j=1
Proof: To show (4.14), note that

98 4 Consensus Algorithms for Double-integrator Dynamics
(cid:2)n (cid:2)n
1
c (ς −ς )T tanh[K(ϕ −ϕ )]
ij i j i j
2
i=1j=1
(cid:2)n (cid:2)n (cid:2)n (cid:2)n
1 1
= c ςT tanh[K(ϕ −ϕ )]− c ςT tanh[K(ϕ −ϕ )]
2 ij i i j 2 ij j i j
i=1j=1 i=1j=1
(4.16)
(cid:2)n (cid:2)n (cid:2)n (cid:2)n
1 1
= c ςT tanh[K(ϕ −ϕ )]+ c ςT tanh[K(ϕ −ϕ )]
2 ij i i j 2 ji j j i
i=1j=1 j=1i=1
(4.17)
(cid:2)n (cid:2)n
= c ςT tanh[K(ϕ −ϕ )],
ij i i j
i=1j=1
where we have used the fact that c = c and tanh[K(ϕ − ϕ )] =
ij ji j i
−tanh[K(ϕ −ϕ )],haveswitchedtheorderofthesummationsignsinthesec-
i j
ondtermin(4.16)to obtain(4.17),andhaveswitchedthe dummy variablesi
andj inthe secondtermin(4.17)toobtainthe lastequality.Equation(4.15)
can be shown by a similar argument.
Theorem 4.19.Suppose that A and B are constant. Algorithm (4.13)
n n
achieves consensus asymptotically if undirected graphs GA and GB are con-
n n
nected.
Proof: Note that with (4.13), (4.1) can be written as
(cid:2)n
ξ˙ =ζ −ζ , ζ˙ =− {a tanh(K ξ )+b tanh[K (ζ −ζ )]}, (4.18)
ij i j i ij r ij ij v i j
j=1
(cid:2)
where ξ =ξ −ξ . Consider the Lyapunov function candidate for (4.18) as
ij i j
(cid:2)n (cid:2)n (cid:2)n
1 1
V = a 1TK −1log[cosh(K ξ )]+ ζTζ , (4.19)
2 ij m r r ij 2 i i
i=1j=1 i=1
where cosh(·) and log(·) are defined componentwise. Note that V is positive
definiteandradiallyunboundedwithrespecttoξ ,∀i(cid:6)=j,andζ ifundirected
ij i
graph GA is connected. Differentiating V gives
n

4.2 Consensus with Bounded Control Inputs 99
(cid:2)n (cid:2)n
1
V˙ = a (ζ −ζ )T tanh(K ξ )
ij i j r ij
2
i=1j=1⎛ ⎞
(cid:2)n (cid:2)n
− ζT ⎝ {a tanh(K ξ )+b tanh[K (ζ −ζ )]}⎠
i ij r ij ij v i j
i=1 j=1
⎧ ⎫
(cid:2)n ⎨(cid:2)n ⎬
=− ζT b tanh[K (ζ −ζ )]
i ⎩ ij v i j ⎭
i=1 j=1
(cid:2)n (cid:2)n
1
=− b (ζ −ζ )T tanh[K (ζ −ζ )]≤0,
ij i j v i j
2
i=1j=1
where we have used the fact that dlog[cosh(x)] = x˙tanh(x) with x ∈ R and
dt
have used (4.18) to obtain the first equality, have used (4.14) in Lemma 4.18
to obtain the secondequality by noting thatξ =ξ −ξ , haveused (4.14)in
ij i j
Lemma 4.18againto obtain the third equality, and haveused the fact that x
and tanh(Kx) have the same sign componentwise, when x is a vector and K
is a positive-definite diagonal matrix, to obtain the last inequality.
Let S = {(ξ ,ζ )|V˙ = 0}. Note that V˙ ≡ 0 implies that ζ ≡ ζ , ∀i (cid:6)= j,
ij i i j
when undirected graph GB is connected, which in turn implies that ζ˙ ≡ ζ˙ ,
n i j
∀i (cid:6)= j. Therefore, it follows that ζ˙ ∈ span(1 ⊗η), where ζ˙ = [ζ˙T,...,ζ˙T]T
n 1 n
and η is some m ×1 real vector, when undirected graph GB is connected.
n
Because ζ ≡ζ , it follows from (4.18) that
i j
(cid:2)n
ζ˙ =− a tanh(K ξ ), i=1,...,n. (4.20)
i ij r ij
j=1
Note that (1 ⊗ η)Tζ˙ ≡ 0 from (4.20), where we have used the fact that
n
a = a and tanh(K ξ ) = −tanh(K ξ ). Thus it follows that ζ˙ is or-
ij ji r ij r ji
thogonal to 1
n
⊗ η. Theref(cid:7)ore, we conclude that ζ˙ ≡ 0, which in turn
implies from (4.20) that − n a tanh(K ξ ) ≡ 0. As a result, it fol-
(cid:7) (cid:7) j=1 ij r ij
lows that − n ξT[ n a tanh(K ξ )] ≡ 0, which in turn implies that
(cid:7) (cid:7) i=1 i j=1 ij r ij
−1 n n a ξT tanh(K ξ ) ≡ 0 from (4.14) in Lemma 4.18 by noting
2 i=1 j=1 ij ij r ij
that ξ = ξ −ξ . When undirected graph GA is connected, it follows that
ij i j n
ξ ≡ 0, i.e., ξ ≡ ξ , ∀i (cid:6)= j. By Theorem F.4, it follows that ξ (t) → ξ (t)
ij i j i j
and ζ (t)→ζ (t), ∀i(cid:6)=j, as t→∞.
i j
(cid:7)
Remark 4.20. Using the algorithm u = − n [a (ξ −ξ )+b (ζ −ζ )],
i j=1(cid:7)ij i(cid:7) j ij i j
i = 1,...,n, the Lyapunov function V = 1 n n a (cid:9)ξ −ξ (cid:9)2 +
(cid:7) 2 i=1 j=1 ij i j
1 n ζTζ can be used to show that the algorithm achieves consensus as-
2 i=1 i i
ymptoticallyundertheconditionsofTheorem4.19byfollowingaproofsimilar
to that of Theorem 4.19. (cid:13)(cid:14)

| 100                           | 4 Consensus |     | Algorithms |     | for Double-integrator |       | Dynamics |            |     |
| ----------------------------- | ----------- | --- | ---------- | --- | --------------------- | ----- | -------- | ---------- | --- |
|                               |             |     |            |     |                       | (t)→ξ | (t)→ζ    | (t),ast→∞. |     |
| Notethat(4.13)guaranteesthatξ |             |     |            |     |                       |       | (t)andζ  |            |     |
|                               |             |     |            |     |                       | i     | j i      | j          |     |
When it is desirable that ξ (t) → ξ (t) and ζ (t) → 0, as t → ∞, we propose
|     |     |     |     | i   | j   |     | i   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
a consensus algorithm for (4.1) with bounded control inputs as
(cid:2)n
|     | =−  |      |        |        | −ξ )]−tanh(K |     |                      |     |        |
| --- | --- | ---- | ------ | ------ | ------------ | --- | -------------------- | --- | ------ |
|     | u i | a ij | tanh[K | r (ξ i | j            |     | vi ζ i ), i=1,...,n, |     | (4.21) |
j=1
where K ∈ Rm×m and K ∈ Rm×m, i = 1,...,n, are positive-definite
|     | r   |     |     | vi  |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
diagonalmatrices.Notethatinthiscase,onlyξ i needtobeexchangedamong
vehicles.
Corollary 4.21.Suppose that A is constant. With (4.21), ξ (t)→ξ (t) and
|        |     |      |     |            | n     |     |                 | i   | j   |
| ------ | --- | ---- | --- | ---------- | ----- | --- | --------------- | --- | --- |
| (t)→0, |     | t→∞, |     |            |       | G   |                 |     |     |
| ζ i    |     | as   | if  | undirected | graph |     | n is connected. |     |     |
Proof: Following the proof of Theorem 4.19, consider the Lyapunov function
| candidate |     | given by | (4.19). | Differentiating |     |     | V, gives |     |     |
| --------- | --- | -------- | ------- | --------------- | --- | --- | -------- | --- | --- |
(cid:2)n
|     |     |     |     | V˙ =− | ζT  | tanh(K | ζ )≤0. |     |     |
| --- | --- | --- | --- | ----- | --- | ------ | ------ | --- | --- |
|     |     |     |     |       | i   |        | vi i   |     |     |
i=1
|     | {(ξ |      | )|V˙ | 0}.  |      | V˙  | ≡              |     | ≡        |
| --- | --- | ---- | ---- | ---- | ---- | --- | -------------- | --- | -------- |
| Let | S = | ,ζ   | =    | Note | that |     | 0 implies that | ζ   | 0, which |
|     |     | ij i |      |      |      |     |                | i   |          |
in(cid:7)turn implies that ζ˙ ≡ 0. It thus follows from (4.1) and (4.21) that
i
| −   | n      |        |     | −    | ≡   |            |             |         |         |
| --- | ------ | ------ | --- | ---- | --- | ---------- | ----------- | ------- | ------- |
|     | a      | tanh[K | (ξ  | ξ )] | 0.  | Therefore, | an argument | similar | to that |
|     | j=1 ij |        | r i | j    |     |            |             |         |         |
in the proof of Theorem 4.19 shows that ξ (t)→ξ (t) and ζ (t)→0, ∀i (cid:6)= j,
|      |           |               |         |       |          |            | i j              | i   |     |
| ---- | --------- | ------------- | ------- | ----- | -------- | ---------- | ---------------- | --- | --- |
| t→∞, |           |               |         |       | G        |            |                  |     |     |
| as   |           | if undirected |         | graph | n is     | connected. |                  |     |     |
| 4.3  | Consensus |               | Without |       | Relative |            | State Derivative |     |     |
Measurements
Note that (4.2) requires measurements of relative information state deriva-
tivesbetweenneighboringvehicles.Weproposeaconsensusalgorithmwithout
measurements of relative information state derivatives based on a passivity
| approach | as  |     |     |     |     |     |     |     |     |
| -------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
(cid:2)n
|     |     |     |     | xˆ˙  |     |     | −ξ    |     |         |
| --- | --- | --- | --- | ---- | --- | --- | ----- | --- | ------- |
|     |     |     |     | =Fxˆ | +   | a   | (ξ ), |     | (4.22a) |
|     |     |     |     | i    | i   | ij  | i j   |     |         |
j=1
(cid:2)n
|     |     |     |     | y =PFxˆ | +P  |     | a (ξ −ξ ), |     | (4.22b) |
| --- | --- | --- | --- | ------- | --- | --- | ---------- | --- | ------- |
|     |     |     |     | i       | i   |     | ij i j     |     |         |
j=1
(cid:2)n
|     |     |     | =−  |     | −ξ   | )−y |              |     |         |
| --- | --- | --- | --- | --- | ---- | --- | ------------ | --- | ------- |
|     |     |     | u   | a   | (ξ   |     | , i=1,...,n, |     | (4.22c) |
|     |     |     | i   |     | ij i | j   | i            |     |         |
j=1

4.3 Consensus Without RelativeState DerivativeMeasurements 101
|        | ∈Rm×m |             |     |     | isthe(i,j)entryoftheadjacencymatrixA |     |     |     |     |
| ------ | ----- | ----------- | --- | --- | ------------------------------------ | --- | --- | --- | --- |
| whereF |       | isHurwitz,a |     |     |                                      |     |     |     |     |
|        |       |             |     |     | ij                                   |     |     |     | n   |
associatedwith G ,6 andP ∈Rm×m isthesymmetricalpositive-definitesolu-
n
| tionoftheLyapunovequationFTP+PF |     |     |     |     |     | =−QwithQ∈Rm×msymmetrical |     |     |     |
| ------------------------------- | --- | --- | --- | --- | --- | ------------------------ | --- | --- | --- |
positive-definite.
Remark 4.22. Apassivityapproachisusedin[129,130,160,235]forcontrolling
a single vehicle. Algorithm (4.22) extends the passivity approach in these
referencestoachieveconsensusamongmultiplevehicleswithdouble-integrator
| dynamics. |     | (cid:13)(cid:14) |     |     |     |     |     |     |     |
| --------- | --- | ---------------- | --- | --- | --- | --- | --- | --- | --- |
A
Theorem 4.23.Suppose that n is constant. Algorithm (4.22)achieves con-
| sensus | asymptotically |     | if undirected |     | graph | G   | is connected. |     |     |
| ------ | -------------- | --- | ------------- | --- | ----- | --- | ------------- | --- | --- |
n
Proof: Let ξ = [ξT,...,ξT]T, ζ = [ζT,...,ζT]T, y = [yT,...,yT]T, xˆ =
|                 |     |     | 1   | n             |          | 1         | n      | 1      | n          |
| --------------- | --- | --- | --- | ------------- | -------- | --------- | ------ | ------ | ---------- |
| [xˆT,...,xˆT]T, |     |     |     | [uT,...,uT]T. |          |           |        |        |            |
|                 |     | and | u = |               |          | Algorithm | (4.22) | can be | written as |
| 1               | n   |     |     | 1             | n        |           |        |        |            |
|                 |     |     | xˆ˙ | =(I           | ⊗F)xˆ+(L |           | ⊗I )ξ, |        | (4.23a)    |
|                 |     |     |     | n             |          |           | n m    |        |            |
⊗P)xˆ˙,
|     |     |     |     |     | y =(I |     |     |     | (4.23b) |
| --- | --- | --- | --- | --- | ----- | --- | --- | --- | ------- |
n
|     |     |     |     | u=−(L |     | ⊗I )ξ−y, |     |     |         |
| --- | --- | --- | --- | ----- | --- | -------- | --- | --- | ------- |
|     |     |     |     |       | n   | m        |     |     | (4.23c) |
where L ∈ Rn×n is the Laplacian matrix associated with undirected graph
n
G
n .
| Note | that | with | (4.22),  | (4.1) | can be  | written  | as        |     |         |
| ---- | ---- | ---- | -------- | ----- | ------- | -------- | --------- | --- | ------- |
|      |      |      |          |       | ξ˙ =ζ   | ,        |           |     | (4.24a) |
|      |      |      |          |       | ij      | ij       |           |     |         |
|      |      |      | (cid:2)n |       |         | (cid:2)n |           |     |         |
|      |      | ζ˙   | =−       | a     | ξ −Pxˆ˙ | +        | a ξ +Pxˆ˙ | ,   | (4.24b) |
|      |      | ij   |          | ij    | ij      | i        | jk jk     | j   |         |
|      |      |      | j=1      |       |         | k=1      |           |     |         |
(cid:2)n
x¨ˆ =Fxˆ˙
|     |     |     |     |     | +   | a   | ζ ,   |     | (4.24c) |
| --- | --- | --- | --- | --- | --- | --- | ----- | --- | ------- |
|     |     |     |     | i   | i   |     | ij ij |     |         |
j=1
|     | (cid:2) |     |     | (cid:2) |     |     |     |     |     |
| --- | ------- | --- | --- | ------- | --- | --- | --- | --- | --- |
whereξ =ξ −ξ andζ =ζ −ζ .ConsidertheLyapunovfunctioncandidate
|            | ij  | i j    | ij  | i    | j    |     |            |         |     |
| ---------- | --- | ------ | --- | ---- | ---- | --- | ---------- | ------- | --- |
| for (4.24) | as  |        |     |      |      |     |            |         |     |
|            |     | 1      |     |      | 1    |     | 1          |         |     |
|            | V   | = ξT(L | ⊗I  | )2ξ+ | ζT(L | ⊗I  | )ζ+ xˆ˙T(I | ⊗P)xˆ˙. |     |
|            |     |        | n   | m    |      | n   | m          | n       |     |
|            |     | 2      |     |      | 2    |     | 2          |         |     |
Note that from the property of the symmetrical Laplacian matrix L , V is
n
positive definite and radially unbounded with respect to ξ , ζ , ∀i (cid:6)= j, and
ij ij
xˆ˙ when undirected graph G is connected. Differentiating V gives
| i   |            |      |        | n              |     |       |           |     |     |
| --- | ---------- | ---- | ------ | -------------- | --- | ----- | --------- | --- | --- |
| 6   |            |      | ξ      |                |     |       |           |     |     |
| In  | this case, | only | i need | to beexchanged |     | among | vehicles. |     |     |

102 4 Consensus Algorithms for Double-integrator Dynamics
1 1
V˙ =ζT(L ⊗I )2ξ+ζT(L ⊗I )u+ x¨ˆT(I ⊗P)xˆ˙ + xˆ˙T(I ⊗P)x¨ˆ
n m n m n n
2 2
=ζT[(L ⊗I )2ξ+(L ⊗I )u]
n m n m
1 1
+ xˆ˙T(I ⊗FT)(I ⊗P)xˆ˙ + ζT(LT ⊗I )(I ⊗P)xˆ˙
2 n n 2 n m n
1 1
+ xˆ˙T(I ⊗P)(I ⊗F)xˆ˙ + xˆ˙T(I ⊗P)(L ⊗I )ζ
n n n n m
2 2
1
=ζT[(L ⊗I )2ξ+(L ⊗I )u]− xˆ˙T(I ⊗Q)xˆ˙
n m n m n
2
+ζT(L ⊗I )(I ⊗P)xˆ˙
n m n
1
=− xˆ˙T(I ⊗Q)xˆ˙ ≤0,
n
2
wherewehaveused(4.23),thefactthatL =LT whengraphG isundirected,
n n n
and Lemma C.8.
Let S ={(ξ ,ζ ,xˆ˙ )|V˙ = 0}. Note that V˙ ≡0 implies that xˆ˙ ≡0, which
ij ij i
in turn implies that x¨ˆ ≡ 0, (L ⊗I )ζ ≡ 0 by differentiating (4.23a), and
n m
y ≡0from(4.23b).Because(L ⊗I )ζ ≡0,itfollowsfromLemma2.10that
n m
ζ ≡ ζ , i.e., ζ ≡ 0, ∀i (cid:6)= j, when undirected graph G is connected. It also
i j ij n
follows that ζ˙ ≡ ζ˙ , which implies that ζ˙ ∈ span(1 ⊗η), where η is some
i j n
m×1 real vector, when undirected graph G is connected. Because y ≡ 0,
n
from (4.1) and (4.23c), it follows that
ζ˙ ≡−(L ⊗I )ξ. (4.25)
n m
Note that (1 ⊗ η)Tζ˙ ≡ −(1 ⊗ η)T(L ⊗ I )ξ ≡ −(1TL ⊗ ηTI ) ≡ 0
n n n m n n m
because 1TL = 0 when graph G is undirected. Thus ζ˙ is orthogonal to
n n n
1 ⊗η. We then conclude that ζ˙ ≡0, which in turn implies from (4.25) that
n
(L ⊗I )ξ ≡0. If undirected graph G is connected, (L ⊗I )ξ ≡0 implies
n m n n m
thatξ ≡ξ ,i.e.,ξ ≡0,∀i(cid:6)=j.ByTheoremF.4,itfollowsthatξ (t)→ξ (t)
i j ij i j
and ζ (t)→ζ (t), ∀i(cid:6)=j, as t→∞.
i j
When it is desirable that ξ (t) → ξ (t) and ζ (t) → 0, as t → ∞, we
i j i
propose an algorithm as
xˆ˙ =Fxˆ +ξ , (4.26a)
i i i
y =PFxˆ +Pξ , (4.26b)
i i i
(cid:2)n
u =− a (ξ −ξ )−y , i=1,...,n, (4.26c)
i ij i j i
j=1
where F, P, and a are defined as in (4.22).
ij
Corollary 4.24.Suppose that A is constant. With (4.26), ξ (t)→ξ (t) and
n i j
ζ (t)→0, as t→∞, if undirected graph G is connected.
i n
Proof: Control law (4.26) can be written as

4.4 Notes 103
xˆ˙ =(I ⊗F)xˆ+ξ, (4.27a)
n
y =(I ⊗P)xˆ˙, (4.27b)
n
u=−(L ⊗I )ξ−y. (4.27c)
n m
Note that with (4.26), (4.1) can be written as
(cid:2)n
ξ˙ =ζ −ζ , ζ˙ =− a ξ −Pxˆ˙ , x¨ˆ =Fxˆ˙ +ζ . (4.28)
ij i j i ij ij i i i i
j=1
Consider the Lyapunov function candidate for (4.28) as
1 1 1
V = ξT(L ⊗I )ξ+ ζTζ+ xˆ˙T(I ⊗P)xˆ˙,
n m n
2 2 2
which is positive definite and radially unbounded with respect to ξ , ∀i(cid:6)=j,
ij
ζ , and xˆ˙ . Following the proof of Theorem 4.23, the derivative of V is given
i i
as
1
V˙ =ζT[(L ⊗I )ξ+u]− xˆ˙T(I ×Q)xˆ˙ +ζT(I ⊗P)xˆ˙
n m n n
2
1
=− xˆ˙T(I ×Q)xˆ˙ ≤0.
n
2
Let S = {(ξ ,ζ ,xˆ˙ )|V˙ = 0}. Note that V˙ ≡ 0 implies that xˆ˙ ≡ 0, which
ij i i
in turn implies that x¨ˆ ≡ 0, ζ ≡ 0 by differentiating (4.27a), and y ≡ 0
from(4.27b).Becauseζ ≡0,itfollowsthatζ˙ ≡0,whichimplies that−(L ⊗
n
I )ξ ≡0 from (4.1) and (4.27c)by noting that y ≡0. If undirected graphG
m n
is connected, (L ⊗I )ξ ≡ 0 implies that ξ ≡ ξ , i.e., ξ ≡ 0, ∀i (cid:6)= j. By
n m i j ij
Theorem F.4, it follows that ξ (t) → ξ (t) and ζ (t) → 0, ∀i (cid:6)= j, as t → ∞.
i j i
4.4 Notes
The results in this chapter are based mainly on [181–183,185,186].For other
theoretical results related to consensus algorithms for double-integrator dy-
namics, see [69,89,115,203].
Acknowledgment is given to
(cid:10)c2006JohnWiley&Sons.Reprinted,withpermission,fromWeiRenand
EllaM.Atkins,“Distributedmulti-vehiclecoordinatedcontrolvialocalinfor-
mation exchange,” International Journal of Robust and Nonlinear Control,
vol. 17, no. 10–11,pp. 1002–1033,July 2007.
(cid:10)c2007 IEEE. Reprinted, with permission, from Wei Ren, “Second-order
consensus algorithm with extensions to switching topologies and reference
models,” Proceedings of the American Control Conference, pp. 1431–1436,
New York City, 2007.

| 104 4 Consensus | Algorithms | for Double-integrator | Dynamics |
| --------------- | ---------- | --------------------- | -------- |
(cid:10)c2007
IEEE. Reprinted, with permission, from Wei Ren, “On consensus
algorithmsfordouble-integratordynamics,”Proceedings of the IEEE Confer-
ence on Decision and Control, New Orleans, LA, 2007 (to appear).
(cid:10)c2007 IEEE. Reprinted, with permission, from Wei Ren, “On consensus
algorithmsfordouble-integratordynamics,”IEEETransactionsonAutomatic
| Control, 2007 (under | review). |     |     |
| -------------------- | -------- | --- | --- |

5
Extensions to a Reference Model
Thischapterextendstheconsensusalgorithmsfordouble-integratordynamics
in Chapter 4 to a reference model. We first consider consensus algorithms
that ensure that the derivatives of the information states follow a reference.
Both strategies with and without coupling between neighbors’ information
state derivatives are addressed. We then consider consensus algorithms that
ensure that the informationstates and their derivatives evolveaccordingto a
reference model. Three strategies, full access to the reference model, leader-
following strategy, and partial access to the reference model, are addressed.
5.1 Problem Statement
SupposethattheteamconsistsofthesamenvehiclesasinChapter4,together
with an additional (virtual) vehicle labeled n+1, which acts as the unique
(virtual) leader of the team. As in Chapter 3, we call vehicle n+1 the team
leader and vehicles 1,...,n the followers. Vehicle n+1 has the information
(cid:2) (cid:2)
state ξ = ξr ∈ Rm and its derivative ζ = ζr ∈ Rm, where ξr and ζr
n+1 n+1
represent the reference states for ξ and ζ , i = 1,...,n, respectively. Note
i i
that ξ and ζ satisfy double-integrator dynamics (4.1). The reference states
i i
ξr and ζr satisfy the reference model
ξ˙r =ζr, ζ˙r =f(t,ξr,ζr), (5.1)
where f(·,·,·) is piecewise continuous in t and locally Lipschitz in ξr and ζr.
(cid:2)
WeusedirectedgraphsGA =(V ,EA ),whereV ={1,...,n+1}
n+1 n+1 n+1 n+1
(cid:2)
is the node set and EA ⊆ V × V is the edge set, and GB =
n+1 n+1 n+1 n+1
(V ,EB ), where V is the same node set as above and EB ⊆ V ×
n+1 n+1 n+1 n+1 n+1
V is the edge set, to model the interaction topologies for ξ and ζ , re-
n+1 i i
spectively, among the n + 1 vehicles. Let A = [a ] ∈ R(n+1)×(n+1)
n+1 ij
and B = [b ] ∈ R(n+1)×(n+1) be the adjacency matrix associated with
n+1 ij

106 5 Extensions to a Reference Model
GA and GB , respectively. In particular, a > 0 (respectively, b > 0) if
n+1 n+1 ij ij
(j,i) ∈ EA [respectively, (j,i) ∈ EB ] and a = 0 (respectively, b = 0)
n+1 n+1 ij ij
otherwise for all i = 1,...,n and j = 1,...,n+1, and a = 0 [respec-
(n+1)j
tively,b =0]forallj =1,...,n+1.AlsoletLA =[(cid:2) ]∈R(n+1)×(n+1)
(n+1)j (cid:7) n+1 ij
(i.e., (cid:2) = −a , i (cid:6)= j, (cid:2) = n+1 a ) and LB = [(cid:2) ] ∈ R(n+1)×(n+1)
ij ij ii (cid:7)j=1,j(cid:5)=i ij n+1 ij
(i.e., (cid:2) = −b , i (cid:6)= j, (cid:2) = n+1 b ) be the nonsymmetrical Lapla-
ij ij ii j=1,j(cid:5)=i ij
cian matrix associated with GA and GB , respectively. When there is only
n+1 n+1
one interaction topology associated with the n+1 vehicles, we simply use
(cid:2)
G =(V ,E )tomodelthe interactiontopologyamongthen+1vehi-
n+1 n+1 n+1
cles,asinChapter3.Similarly,A andL are,respectively,theadjacency
n+1 n+1
matrix and the nonsymmetrical Laplacian matrix associated with G .
n+1
Remark 5.1. When we need to focus only on vehicles 1 to n (i.e., the follow-
(cid:2) (cid:2)
ers), we still use GA = (V ,EA) and GB = (V ,EB) to model the interaction
n n n n n n
topologiesforξ andζ ,respectively,amongthenfollowers,asinChapter4.In
i i
addition,A ∈Rn×n (respectively,B ∈Rn×n)andLA ∈Rn×n (respectively,
n n n
LB ∈Rn×n)are still,respectively,the adjacencymatrix andthe nonsymmet-
n
ricalLaplacianmatrixassociatedwithGA (respectively,GB),asinChapter4.
n n
When there is only one interaction topology associated with the n followers,
(cid:2)
we simply use G = (V ,E ) to model the interaction topology among the n
n n n
followers, as in Chapter 2. Similarly, A and L are, respectively, the adja-
n n
cency matrix and the nonsymmetrical Laplacian matrix associated with G .
n
(cid:13)(cid:14)
In this chapter, there is only one interactiontopology associatedwith the
n+1 vehicles. In addition, we assume that the interaction topology is time
invariant and all weights in the consensus algorithms are constant.
5.2 Consensus with a Reference for Information State
Derivatives
In this section, the objective is to guarantee that ξ (t) → ξ (t) and ζ (t) →
i j i
ζr(t), as t → ∞. We consider two strategies with and without coupling be-
tween neighbors’ information state derivatives.
5.2.1 Consensus with Coupling Between Neighbors’ Information
State Derivatives
When there is coupling between neighbors’ information state derivatives, we
propose an algorithm as
(cid:2)n
u =ζ˙r −α(ζ −ζr)− a [(ξ −ξ )+γ(ζ −ζ )], (5.2)
i i ij i j i j
j=1

5.2 Consensus with a Reference for Information StateDerivatives 107
where α and γ are positive scalars and a is the (i,j) entry of the adjacency
ij
matrix A ∈ Rn×n associated with G . Note that with (5.2), ζr and ζ˙r are
n n
availabletoallfollowers,whichcorrespondstothecasewhere(n+1,i)∈E ,
n+1
i=1,...,n.
Lemma 5.2.Let p = [p ,...,p ]T ≥ 0 satisfy 1Tp = 1 and LTp = 0, where
1 n n n
L ∈Rn×n is the nonsymmetrical Laplacian matrix associated with G . Also
n n
let (cid:22) (cid:23)
Σ = 0 n×n I n , (5.3)
−L −αI −γL
n n n
where α and γ are positive scalars. Then
(cid:22) (cid:23)
1 pT 11 pT
lim eΣt → n α n .
t→∞ 0 n×n 0 n×n
if and only if Σ has a simple zero eigenvalue and all other eigenvalues have
negative real parts.
Proof:(Sufficiency.)TheeigenvaluesofΣcanbefoundbysolvingtheequation
det(λI −Σ)=0. Note that
2n
det(λI −Σ)=det(λ2I +γλL +αλI +L )
2n (cid:8) n n n n(cid:9)
=det (λ2+αλ)I +(1+γλ)L . (5.4)
n n
Also note that
(cid:24)n
det(λI +L )= (λ−μ ), (5.5)
n n i
i=1
where μ is the ith eigenvalue of −L .
i n
Bycomparing(5.4)and(5.5),weseethattherootsof(5.4)canbeobtained
by solving λ2+αλ = μ (1+γλ). Therefore, it is straightforward to see that
i
the eigenvalues of Σ are given by
(cid:25)
γμ −α± (γμ −α)2+4μ
i i i
ρ i± = , (5.6)
2
where ρ i± are called eigenvalues of Σ that are associated with μ i .
Note from (5.6) that Σ has k zero eigenvalues if and only if −L has
n
k zero eigenvalues. Without loss of generality, we let μ = 0, which implies
1
that ρ 1+ = 0 and ρ 1− = −α. The proof then follows a line similar to that of
Lemma 4.1 by noting that ν =[pT, 1pT]T, w =[1T,0T]T, and
1 α 1 n n
(cid:22) (cid:23)
J =
0 0 1×(2n−1)
,
0 (2n−1)×1 J(cid:8)
where J(cid:8) is the Jordan upper diagonal block matrix corresponding to the
2n−1 eigenvalues that have negative real parts.

108 5 Extensions to a Reference Model
(cid:22) (cid:23)
1 pT 11 pT
(Necessity.) If lim t→∞eΣt →
0 n
n
×n
α
0 n
n
×n
, we know that
lim t→∞PeJtP−1 has rank one, which in turn implies that lim t→∞eJt has
rank one. However, if the sufficient condition does not hold, we know that
lim t→∞eJt has a rank larger than one by following an argument similar to
the necessity proof of Lemma 4.1. This results in a contradiction.
Corollary 5.3.Let (cid:7)p be defined a(cid:10)s in Lemma 5(cid:7).2. With consensus algo-
rithm (5.2), ξ (t)→ n p ξ (0)+ t ζr(τ)dτ + 1 n p ζ (0)− 1ζr(0) and
i i=1 i i 0 α i=1 i i α
ζ (t)→ζr(t), i=1,...,n, asymptotically, as t→∞, if and only if Σ defined
i
in (5.3) has a simple zero eigenvalue and all other eigenvalues have negative
real parts.
(cid:10)
Proof: (Sufficiency.) Let ξ˜ = (cid:2) ξ −ξr, where ξr = (cid:2) t ζr(τ)dτ, and ζ˜ =ζ −ζr.
i i 0 i i
With (5.2), (4.1) can be written as
ξ˙ −ξ˙r =ζ −ζr
i i
(cid:2)n
ζ˙ =−α(ζ −ζr)− a {(ξ −ξr)−(ξ −ξr)+γ[(ζ −ζr)−(ζ −ζr)]},
i i ij i j i j
j=1
which implies that
ξ˜˙ =ζ˜
i i
(cid:2)n
ζ˜˙ =−αζ˜ − a [(ξ˜ −ξ˜)+γ(ζ˜ −ζ˜)]. (5.7)
i i ij i j i j
j=1
Equation (5.7) can be written in matrix form as
!
(cid:22) (cid:23)
ξ˜˙ ξ˜
=(Σ⊗I ) ,
ζ˜˙ m ζ˜
where ξ˜= (cid:2) [ξ˜T,...,ξ˜T]T and ζ˜= (cid:2) [ζ˜T,...,ζ˜T]T.
1 n 1 n
If Σ has a simple zero eigenvalue and all other eigenvalues have negative
real parts, we know from Lemma 5.2 that
(cid:22) (cid:23) (cid:22) (cid:23) (cid:11)(cid:22) (cid:23) (cid:12)(cid:22) (cid:23)
ξ˜(t) ξ˜(0) 1 pT 11 pT ξ˜(0)
lim = lim(eΣt⊗I ) = n α n ⊗I ,
t→∞ ζ˜(t) t→∞ m ζ˜(0) 0 n×n 0 n×n m ζ˜(0)
whichimplies thatξ˜(t)→(1 pT⊗I )ξ˜(0)+ 1(1 pT⊗I )ζ˜(0)andζ˜(t)→0.
n m α n m
This in turn gives the suffi(cid:7)cient part. (cid:10) (cid:7)
(Necessity.)Ifξ (t)→ n p ξ (0)+ t ζr(τ)dτ+ 1 n p ζ (0)−1ζr(0)
i i=1 i i 0 α i=1 i i α
and ζ (t) → ζr(t), i = 1,...,n, as t → ∞, we know that ξ˜(t) → (1 pT ⊗
i n
I )ξ˜(0)+ 1(1 pT ⊗I )ζ˜(0) and ζ˜(t)→0, which implies that
m α n m

5.2 Consensus with a Reference for Information StateDerivatives 109
(cid:22) (cid:23)
1 pT 11 pT
lim eΣt → n α n .
t→∞ 0 n×n 0 n×n
The necessary part then comes from Lemma 5.2.
We have the following theorem for consensus algorithm (5.2).
Theorem 5.4.Let p be defined as in Lemma 5.2. Also let μ be the ith eigen-
i
value of −L . Consensus algorithm (5.2) guarantees that ξ (t) →
(cid:7) n(cid:10) (cid:7) i
n p ξ (0) + t ζr(τ)dτ + 1 n p ζ (0) − 1ζr(0) and ζ (t) → ζr(t),
i=1 i i 0 α i=1 i i α i
i = 1,...,n, as t → ∞, if directed graph G has a directed spanning tree
n
and Inequality (4.10) is satisfied.
Proof: Let ρ i± be given by (5.6). If G n has a directed spanning tree, Corol-
lary 2.5 implies that −L has a simple zero eigenvalue and all other eigen-
n
values have negative real parts. Without loss of generality, we let μ =0 and
1
Re(μ i ) < 0, i = 2,··· ,n. Then we can find that ρ 1+ = 0 and ρ 1− = −α.
Note that if μ
i
< 0, then (5.6) implies that Re(ρ i±) < 0. It is left to show
that Inequality (4.10) guarantees that all ρ i± associated with μ i that satisfy
Re(μ )<0andIm(μ )(cid:6)=0havenegativerealparts.Weneedonlytoconsider
i i
μ that satisfies Re(μ ) < 0 and Im(μ ) > 0 because any μ that satisfies
i i i i
Re(μ ) < 0 and Im(μ ) < 0 is a complex conjugate of some μ that satisfies
i i i
Re(μ ) < 0 and Im(μ ) > 0. This argument then follows from Lemma 4.10.
i i
Therefore, Corollary 5.3 implies that consensus can be achieved asymptoti-
cally under the assumption of the theorem.
Remark 5.5. Under some circumstances, it might be desirable that ξ (t) →
i
ξ (t) and ζ (t)→0, as t→∞. For example, in formation stabilization appli-
j i
cations,wewanteachvehicletoagreeonitsapriori unknownfixedformation
center,whichhasaconstantpositionandzerovelocity.Inthiscase,wesimply
let ζr ≡0. (cid:13)(cid:14)
5.2.2 Consensus Without Coupling Between Neighbors’
Information State Derivatives
When there is coupling between neighbors’ information state derivatives, we
propose a consensus algorithm as
(cid:2)n
u =ζ˙r−α(ζ −ζr)− a (ξ −ξ ), i=1,...,n, (5.8)
i i ij i j
j=1
where α is a positive scalarand a is the (i,j) entry of the adjacency matrix
ij
A ∈Rn×n associated with G . Note that with (5.8), ζr and ζ˙r are available
n n
to all followers, which corresponds to the case where (n+1,i) ∈ E , i =
n+1
1,...,n.
We have the following theorem for algorithm (5.8):

110 5 Extensions to a Reference Model
Theorem 5.6.Let μ be the ith eigenvalue of −L . With (5.8), ξ (t)→ξ (t)
i n i j
and ζ (t)→ζr(t), i=1,...,n, as t→∞, if directed graph G has a directed
i n
spanning tree and
α>α¯, (5.9)
(cid:2)
where α¯ =0 if all n−1 nonzero eigenvalues of −L are negative and
n
,
(cid:2) 2
α¯ = max |μ |
∀Re(μi)<0 and Im(μi)>0 i −Re(μ i )
otherwise.
(cid:10)
Proof: Let ξ˜ = (cid:2) ξ − t ζr(τ)dτ, ζ˜ = (cid:2) ζ −ζr, ξ˜ = (cid:2) [ξ˜T,...,ξ˜T]T, and ζ˜ = (cid:2)
i i 0 i i 1 n !
ξ˜˙
[ζ˜T,...,ζ˜T]T. With (5.8), (4.1) can be written in matrix form as =(Φ⊗
1 n ζ˜˙
(cid:22) (cid:23) (cid:22) (cid:23)
I ) ξ˜ , where Φ= (cid:2) 0 n×n I n .
m ζ˜ −L
n
−αI
n
Noting that L 1 = 0 from Corollary 2.5, it follows that [1T,0T]T is
n n n n
an eig(cid:11)e(cid:22)nve(cid:23)ct(cid:12)or for Φ associated with the zero eigenvalue, which implies that
1
span n is contained in the kernel of Φ. If Φ has a simple zero eigen-
0
n (cid:22) (cid:23)
ξ˜(t)
value and all other eigenvalues have negative real parts, then →
(cid:11)(cid:22) (cid:23) (cid:12)
ζ˜(t)
1
span n ⊗η ,ast→∞,whereηissomem×1vector,whichisequivalent
0
n
to ξ (t)→ξ (t) and ζ →ζr(t), as t→∞.
i j i
Next,weshowthatifG hasadirectedspanningtreeandInequality (5.9)
n
issatisfied,then Φhasasimple zeroeigenvalueandallothereigenvalueshave
negative real parts.
LetλbeaneigenvalueofΦands=[pT,qT]T beitsassociatedeigenvector,
where p and q are n×1 column vectors. Note that
(cid:22) (cid:23)(cid:22) (cid:23) (cid:22) (cid:23)
Φs=λs⇐⇒ 0 n×n I n p =λ p
−L −αI q q
n n
⇐⇒q =λp and −L p−αq =λq ⇐⇒−L p=(λ2+αλ)p,
n n
which implies that λ2+αλ is aneigenvalue of −L with an associatedeigen-
n
(cid:2)
vectorp.Letting μ=λ2+αλgivesλ2+αλ−μ=0,whic√himplies thatgiven
−α± α2+4μ
each μ, there are two roots for λ, denoted by λ± = . As a result,
2
eacheigenvalue of −L , μ , i=1,...,n, correspondsto two eigenvalues of Φ,
n i
denoted by λ i±.
If G has a directed spanning tree, then Corollary 2.5 implies that −L
n n
has a simple zero eigenvalue and all other eigenvalues have negative real
parts. Without loss of generality, let μ = 0 and Re(μ ) < 0, i = 2,...,n.
1 i

5.3 ConsensuswithReferencesforInformationStatesandTheirDerivatives 111
Then it follows that λ 1+√ = 0 and λ 1− = −α. Note that if μ i < 0,
then Re(λ i±) = Re(
−α±
2
α2+4μi)
< 0 for any α > 0. It is left to show
that Inequality (5.9) guarantees that all eigenvalues of Φ associated with
μ that satisfy Re(μ ) < 0 and Im(μ ) (cid:6)= 0 have negative real parts. As in
i i i
Lemma 4.10, we use Fig. 5.1 to show the notations used in the proof. We
need only to consider μ that satisfies Re(μ ) < 0 and Im(μ ) > 0 because
i i i
any μ that satisfies Re(μ ) < 0 and Im(μ ) < 0 is a complex conjugate of
i i i
some μ that satisfies Re(μ ) < 0 and Im(μ ) > 0. Consider the triangle
i i i
(cid:21)formed by(cid:21) vectors α2, 4μ
i
, and α2 +4μ
i
. According to the law of cosines,
(cid:21) α2+4μ (cid:21)2 = (α2)2 + (4|μ |)2 − 8α2|μ |cos(φ ), where cos(φ ) = −Re(μi).
i (cid:31) i (cid:21) i i (cid:21) i |μi|
Note that if α > |μ | 2 , then (cid:21) α2+4μ (cid:21)2 < α4, which implies that
(cid:21)(cid:25) (cid:21) i −Reμi (cid:21) i (cid:25) (cid:21)
(cid:21) (cid:21) (cid:21) (cid:21)
(cid:21) α2+4μ (cid:21) < α. Therefore, it follows that (cid:21)Re( α2+4μ )(cid:21) < α, which in
i √ i
turn implies that Re(λ i±)=Re(
−α±
2
α2+4μi)<0.
Im
Re
Fig. 5.1. Graphical view of notations used in theproof of Theorem 5.6
Combiningthe abovearguments,it follows thatif G has a directedspan-
n
ning tree and Inequality (5.9) is valid, then ξ (t) → ξ (t) and ζ (t) → ζr(t),
i j i
as t→∞.
Corollary 5.7.Suppose that G is undirected. With (5.8), ξ (t) →ξ (t) and
n i j
ζ (t)→ζr(t), as t→∞, if G is connected.
i n
5.3 Consensus with References for Information States
and Their Derivatives
In this section, the objective is to guarantee that ξ (t) → ξr(t) and ζ (t) →
i i
ζr(t), as t→∞, where ξr(t) and ζr(t) satisfy reference model (5.1). We first
consider two special cases where either the reference model is available to
all followers on the team or the interaction topology for the n followers is

112 5 Extensions to a Reference Model
itself a directed spanning tree. We then consider the general case where the
interaction topology for the n+1 vehicles has a directed spanning tree.
5.3.1 Full Access to the Reference Model
In this strategy, we incorporate in reference model (5.1), to each vehicle’s
consensus algorithm. The consensus algorithm for each vehicle is designed as
u =ζ˙r −α[(ξ −ξr)+γ(ζ −ζr)]
i i i
(cid:2)n
− a [(ξ −ξ )+γ(ζ −ζ )], (5.10)
ij i j i j
j=1
where α and γ are positive scalars and a is the (i,j) entry of the adjacency
ij
matrixA ∈Rn×nassociatedwithG .Notethatwith(5.10),ξr,ζr,andζ˙r are
n n
availabletoallfollowers,whichcorrespondstothecasewhere(n+1,i)∈E ,
n+1
i=1,...,n.
We have the following theorem for algorithm (5.10):
(cid:2)
Theorem 5.8.Let μ be the ith eigenvalue of −L . Also let ν = −α+μ .
i n i i
Consensus algorithm (5.10) guarantees that ξ (t) → ξr(t) and ζ (t) → ζr(t),
i i
i=1,...,n, if
γ >γ¯, (5.11)
(cid:2)
where γ¯ =0, if all n−1 nonzero eigenvalues of −L are negative and
n
,
2
γ¯ = max
∀Re(νi)<0 and Im(νi)>0 |ν
i
|cos(tan−1
−
Im
Re
(
(
ν
ν
i
i
)
)
)
otherwise.
Proof: With algorithm (5.10), (4.1) can be written in matrix form as
! (cid:22) (cid:23)
ξ˜˙ ξ˜
=(Υ ⊗I ) ,
ζ˜˙ m ζ˜
wher(cid:22)e ξ˜
i
= (cid:2) ξ
i
−ξr, ζ˜
i
= (cid:2) ζ
i
−ζr, ξ˜ (cid:23)= (cid:2) [ξ˜
1
T,··· ,ξ˜
n
T]T, ζ˜ = (cid:2) [ζ˜
1
T,··· ,ζ˜
n
T]T, and
Υ = (cid:2) 0 n×n I n .Notethattheeigenvaluesof−(αI +L )
−αI −L −γ(αI +L ) n n
n n n n
are given by ν and Re(ν ) < 0, i = 1,...,n, for any G . Following (4.4)
i i n
and (4.7) with αI
n
+L
n
and ν
i
playing the√roles of L
n
and μ
i
, respectively,
the eigenvalues of Υ are givenby ρ i± =
γνi± γ
2
2νi 2+4νi.
If Inequality (5.11) is
true, we know that all eigenvalues of Υ have negative real parts by following
the proof of Theorem 4.11. Therefore, we see that ξ˜(t)→0 and ζ˜(t) →0, as
t→∞, which in turn proves the theorem.

5.3 ConsensuswithReferencesforInformationStatesandTheirDerivatives 113
G
Remark 5.9. Note that unlike Theorems 5.4 and 5.6, does not affect the
n
convergenceresultinTheorem5.8,aslongasthescalingfactorγissufficiently
large.Asaresult,evenintheworstcasethatthereisnoinformationexchange
among the followers (i.e., A = 0 ), we can still guarantee that ξ (t) →
|     | n   | n×n |     |     | i   |
| --- | --- | --- | --- | --- | --- |
ξr(t) and ζ (t) → ζr(t), i = 1,...,n, as t → ∞, as long as Inequality (5.11)
i
(t)→ξ
is valid. However,better transient performance is achieved[i.e., ξ (t)
i j
andζ (t)→ζ (t) during the transition]when G hasa directedspanning tree
| i j |     |     | n   |     |     |
| --- | --- | --- | --- | --- | --- |
(cid:13)(cid:14)
| due to coupling among | the vehicles. |     |     |     |     |
| --------------------- | ------------- | --- | --- | --- | --- |
Example 5.10. Theorem5.8canbeillustratedgraphically.Considertheinter-
action topology shown in Fig. 5.2 where reference model (5.1) is available to
ξr
all followers.Here we use node to denote the team leader. Note that there
exists an edge from node ξr to all followers on the team. (cid:13)(cid:14)
|     |                                                                                                                |                                                                                                              | (cid:5)(cid:5)(cid:17)(cid:17)                                  | (cid:22)(cid:22)                                                                 |     |
| --- | -------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------- | -------------------------------------------------------------------------------- | --- |
|     | (cid:18)(cid:22)(cid:19)(cid:23) ξ (cid:20)(cid:24) r(cid:10) (cid:21)(cid:25) (cid:5)(cid:12) (cid:5)(cid:12) | (cid:15)(cid:15)(cid:15)(cid:15)(cid:6)(cid:2) (cid:7)(cid:3) (cid:8)(cid:4) (cid:9)(cid:5) (cid:19)(cid:19) | (cid:2) (cid:6) (cid:3) (cid:7) (cid:4) (cid:8) (cid:5) (cid:9) | (cid:15)(cid:15) (cid:6) (cid:2) (cid:7) (cid:3) (cid:8) (cid:4) (cid:9) (cid:5) |     |
|     | (cid:10)                                                                                                       | (cid:5) (cid:12) (cid:5)(cid:12) (cid:12) 1                                                                  | 2                                                               | 3                                                                                |     |
(cid:10) (cid:5) (cid:5) (cid:12) (cid:12) (cid:12)
|     |     | (cid:10) (cid:10) (cid:5) (cid:5) (cid:12) (cid:12)         | (cid:12)                                                                 |                                                                                                |     |
| --- | --- | ----------------------------------------------------------- | ------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------- | --- |
|     |     | (cid:10) (cid:5) (cid:5)                                    | (cid:12) (cid:12) (cid:12)                                               |                                                                                                |     |
|     |     | (cid:10) (cid:10) (cid:5)(cid:5)                            | (cid:12) (cid:12)(cid:12)(cid:12)(cid:12)(cid:12)                        |                                                                                                |     |
|     |     | (cid:24)(cid:24) (cid:14)(cid:14)                           | (cid:5) (cid:5) (cid:6)(cid:17)(cid:17) (cid:14)(cid:14)                 |                                                                                                |     |
|     |     | (cid:6)(cid:2) (cid:7)(cid:3) (cid:8)(cid:4) (cid:9)(cid:5) | (cid:15)(cid:15) (cid:2) (cid:3) (cid:7) (cid:4) (cid:8) (cid:5) (cid:9) | (cid:15)(cid:15)(cid:6)(cid:6) (cid:6) (cid:2) (cid:7) (cid:3) (cid:8) (cid:4) (cid:9) (cid:5) |     |
|     |     | 4                                                           | 5                                                                        | 6                                                                                              |     |
Fig.5.2.Interactiontopologywherereferencemodel(5.1)isavailabletoallfollowers
| 5.3.2 Leader-following | Strategy |     |     |     |     |
| ---------------------- | -------- | --- | --- | --- | --- |
In the leader-following strategy, G is itself a directed spanning tree with
n
vehicle k the root, and reference model (5.1) is only available to vehicle k,
that is, vehicle k is the child of vehicle n + 1. Accordingly, in the leader-
G
following strategy, n+1 is also a directed spanning tree with vehicle n+1
(i.e., the unique team leader) the root, that is, each vehicle except vehicle
n+1 has exactly one parent.
The consensus algorithmfor all followers(i.e., vehicles 1 to n) is designed
as
| =ζ˙r       | −K    | −ξr)−K     | −ζr),   |                |         |
| ---------- | ----- | ---------- | ------- | -------------- | ------- |
| u i        | ri (ξ | i          | vi (ζ i | i=k            | (5.12a) |
| u =ζ˙ −K   | (ξ    | −ξ )−K     | (ζ −ζ   | ), i(cid:6)=k, | (5.12b) |
| i i(cid:3) | ri    | i i(cid:3) | vi i    | i(cid:3)       |         |
×
where K and K are m m symmetrical positive-definite matrices and
ri vi
vehicle i is the parent of vehicle i, i (cid:6)= k.1 With algorithm (5.12), (4.1) can
(cid:7)
be written as
|     | ζ˜˙ | =−K | ξ˜ −K ζ˜, |     |     |
| --- | --- | --- | --------- | --- | --- |
(5.13)
|     | i   | ri  | i vi i |     |     |
| --- | --- | --- | ------ | --- | --- |
1 That is, an edge (i ,i) exists in G . However, vehicle i is not the unique team
| (cid:2) |     | n   |     | (cid:2) |     |
| ------- | --- | --- | --- | ------- | --- |
leader.

114 5 Extensions to a Reference Model
where ξ˜ =ξ −ξr, ξ˜ =ξ −ξ , i(cid:6)=k, ζ˜ =ζ −ζr, and ζ˜ =ζ −ζ , i(cid:6)=k.
k k i i i(cid:3) k k i i i(cid:3)
Note that (5.13) implies that ξ˜(t) → 0 and ζ˜(t) → 0, as t → ∞, because
i i
K andK aresymmetricalpositive-definite matrices,whichinturnimplies
ri vi
that ξ (t) → ξr(t), ζ (t) → ζr(t), ξ (t) → ξ (t), and ζ (t) → ζ (t), i (cid:6)= k, as
k k i i(cid:3) i i(cid:3)
t→∞.Therefore,itfollowsthatξ (t)→ξr(t)andζ (t)→ζr(t),i=1,...,n,
i i
ast→∞,byrenumberingthe vehiclesconsecutivelybydepthinthe directed
spanning tree.
Remark 5.11. Notethatintheleader-followingstrategy,wheretheinteraction
topologyisitselfadirectedspanningtree,informationflowsonlyfromparents
tochildren.Whenachildisperturbedbyadisturbance,theparentisunaware
of this disturbance, and its motion remains unaffected. It might be intuitive
to introduce information flow from children to parents to introduce feedback
to improve group robustness. However, it is not clear how information from
children can be incorporatedinto the algorithm for parents without affecting
stability. (cid:13)(cid:14)
Example 5.12. Algorithm (5.12) can be illustrated by the following example.
Consider the directed spanning tree shown by Fig. 5.3, where vehicle j is the
parentofvehiclej+1,j =2,4,5,andvehicle1is theparentofvehicles2and
4. Note that there exists an edge from node ξr to vehicle 1. (cid:13)(cid:14)
(cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25) (cid:15)(cid:15)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) (cid:15)(cid:15)(cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) (cid:15)(cid:15)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5)
ξr 1 2 3
(cid:14)(cid:14)
(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) (cid:15)(cid:15)(cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) (cid:15)(cid:15)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5)
4 5 6
Fig. 5.3. A directed spanning tree where reference model (5.1) is available only to
one vehicle
5.3.3 General Case
In the general case where G is arbitrary and reference model (5.1) may be
n
available to one or multiple followers, we propose the consensus algorithm
(cid:2)n
1
u = a [ζ˙ −K (ξ −ξ )−K (ζ −ζ )]
i ij j ri i j vi i j
κ
i
j=1
1
+ a [ζ˙r −K (ξ −ξr)−K (ζ −ζr)], (5.14)
κ i(n+1) ri i vi i
i
where a is the (i,j) entry of the adjacency matrix A ∈Rn×n associated
ij (cid:7) n+1
with G , κ = (cid:2) n+1a and K and K are m×m symmetrical positive-
n+1 i j=1 ij ri vi

5.3 ConsensuswithReferencesforInformationStatesandTheirDerivatives 115
definite matrices. Note that in (5.14), each vehicle needs its neighbors’ in-
formation states and their first-, and second-order derivatives.2 In practical
implementation, the second-order derivatives of the neighbors’ information
states can be calculated by numerical differentiation.
We have the following theorem for consensus with a reference model:
Theorem 5.13.With consensus algorithm (5.14), there exists a unique so-
lution for u and ξ (t) → ξr(t) and ζ (t) → ζr(t), as t → ∞, if and only if
i i i
directed graph G has a directed spanning tree (with vehicle n+1 as the
n+1
root).3
(cid:7)
Proof: Note that κ = n+1a (cid:6)=0, i =1,...,n, under the condition of the
i j=1 ij
theorembyfollowingtheproofofTheorem3.8.Asintheproofof(cid:7)Theorem3.8,
define M = [m ] ∈ Rn×n as m = −a , i (cid:6)= j, and m = n+1 a .
ij ij ij ii j=1,j(cid:5)=i ij
(cid:2) (cid:2)
Also define b ∈ Rn as b = [−a ,...,−a ]T. Let ξ = [ξT,··· ,ξT]T,
1(n+1) n(n+1) 1 n
(cid:2) (cid:2) (cid:2)
e = (M ⊗I )ξ +(b⊗I )ξr, u = [uT,...,uT]T, K = diag(K ,...,K ),
m m 1 n r r1 rn
and K = (cid:2) diag(K ,...,K ). Noting that ζ˙ =u , we rewrite (5.14) as
v v1 vn j j
(M ⊗I )u+(b⊗I )ζ˙r =−K e−K e˙. (5.15)
m m r v
IfM hasfullrank,thenitisstraightforwardtoshowthatthereisauniqueso-
lutionforu.Undertheconditionofthetheorem,M hasfullrankbyfollowing
the proof of Theorem 3.8. This proves the first statement of the theorem.
Notethat(5.15)canbewrittenase¨=−K e−K e˙.Itfollowsthate(t)→0
r v
and e˙(t) → 0, as t → ∞, because K and K are symmetrical positive-
r v
definite matrices.Thenbyfollowingthe proofofTheorem3.15,weknowthat
ξ (t)→ξr(t) and ζ (t) →ζr(t), as t →∞, if and only if G has a directed
i i n+1
spanning tree.
Remark 5.14. Note that no constraints are imposed on f(t,ξr,ζr) in (5.1) in
the proofofTheorem5.13,as longasf(·,·,·) is piecewise continuous int and
locally Lipschitz in ξr and ζr. (cid:13)(cid:14)
Example 5.15. Theorem5.13isillustratedbythefollowingexample.Consider
the interaction topology given by Fig. 5.4, where reference model (5.1) is
available only to vehicles 1 and 5. Note that although neither vehicle 1 nor
vehicle 5 has a directed path to allother followerson the team, there exists a
directedpathfromnode ξr to allfollowersonthe team.Also note thatunlike
the leader-following strategy where the interaction topology is constrained
to be a directed spanning tree, algorithm (5.14) allows information to flow
arbitrarily among the followers.
2 The second-order derivatives of the information states are equivalent to the in-
formation control inputsby noting from (4.1) that ξ¨ ≡ζ˙ ≡u .
j j j
3 Equivalently,fromLemma2.11,vehiclen+1istheonlyvehiclethathasadirected
pathtoallothervehiclesontheteambynotingthatallentriesofthelastrowof
A n+1 are zero.

| 116 5 Extensions | to a Reference | Model |     |     |     |
| ---------------- | -------------- | ----- | --- | --- | --- |
(cid:17)(cid:17)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5)
|     | (cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25) | (cid:15)(cid:15)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) | (cid:15)(cid:15)(cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) |     |     |
| --- | ---------------------------------------------------------------- | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | --- | --- |
|     | ξr(cid:5)(cid:5)(cid:5)(cid:5)(cid:5)(cid:5)                     | 1                                                                        | 2 (cid:19)(cid:19) 3                                                     |     |     |
(cid:5)
(cid:5) (cid:5)
(cid:5)(cid:5)(cid:5)(cid:5)(cid:5)
(cid:14)(cid:14)
|     |     | (cid:6)(cid:2) (cid:7)(cid:3) (cid:8)(cid:4) (cid:9)(cid:5) (cid:2)(cid:2) | (cid:2)(cid:6)(cid:17)(cid:17)(cid:3)(cid:7) (cid:4)(cid:8)(cid:5)(cid:9) (cid:15)(cid:15)(cid:6)(cid:2)(cid:7)(cid:3) (cid:8)(cid:4)(cid:9)(cid:5) |     |     |
| --- | --- | -------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | --- | --- |
|     |     | 4                                                                          | 5 6                                                                                                                                                 |     |     |
Fig. 5.4. A general interaction topology where reference model (5.1) is available
only toa subgroup of followers and theoriginal topology without node ξr does not
| havea directed | spanningtree |     |     |     |     |
| -------------- | ------------ | --- | --- | --- | --- |
To further illustrate, let f(t,ξr,ζr) = −sin(ξr) in (5.1), where ξr(0) =
1+e−t
π and ζr(0) = 0. Figure 5.5 demonstrates that using (5.14) all followers’
2
information states and their derivatives reach consensus on the solution of
(cid:13)(cid:14)
| reference model | (5.1). |     |     |     |     |
| --------------- | ------ | --- | --- | --- | --- |
(a)
8
Reference
6
4
ξ i
2
0
−2
| 0 2 | 4 6 | 8 10 | 12 14 | 16 18 | 20  |
| --- | --- | ---- | ----- | ----- | --- |
Time (s)
(b)
2
1
0
ζ i −1
−2
−3
Reference
−4
| 0 2 | 4 6 | 8 10 | 12 14 | 16 18 | 20  |
| --- | --- | ---- | ----- | ----- | --- |
Time (s)
Fig. 5.5. Information states and their derivatives using algorithm (5.14) when ref-
erence model (5.1) is available only to a subgroup of followers

5.3 ConsensuswithReferencesforInformationStatesandTheirDerivatives 117
Note that (5.14) does not explicitly take into account a bounded control
effort. Next, we propose a consensus algorithm with bounded control inputs
as
(cid:2)n
|     | 1   |     | ζ˙  |        | ζ˙r) |     |     |     |     |
| --- | --- | --- | --- | ------ | ---- | --- | --- | --- | --- |
| u   | =   | ( a | +a  |        |      |     |     |     |     |
|     | i κ | ij  | j   | i(n+1) |      |     |     |     |     |
i
j=1
(cid:2)n
1
|     | −   | K tanh[ |     | a (ξ | −ξ )+a |        | (ξ  | −ξr)] |     |
| --- | --- | ------- | --- | ---- | ------ | ------ | --- | ----- | --- |
|     |     | κ ri    |     | ij   | i j    | i(n+1) | i   |       |     |
i
j=1
(cid:2)n
|     | −   | 1       |     |      | −ζ  |        |     | −ζr)],     |        |
| --- | --- | ------- | --- | ---- | --- | ------ | --- | ---------- | ------ |
|     |     | K tanh[ |     | a (ζ | )+a |        | (ζ  | i=1,...,n, | (5.16) |
|     |     | κ vi    |     | ij   | i j | i(n+1) | i   |            |        |
i
j=1
where a and κ are defined as in (5.14), K and K are m×m positive-
|     | ij  |     | i   |     |     |     | ri  | vi  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
definitediagonalmatrices,andtanh(·)isdefinedcomponentwise.Notethatas
in(5.14),eachvehicleneedstheinformationstatesandtheirfirst-,andsecond-
order derivatives (i.e., the information control inputs u ) from its neighbors.
j
Theorem 5.16.Suppose that f(t,ξr,ζr) in (5.1) is bounded. With (5.16),
|     |     |     |     |     |     |     |     | →   | →   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
there exists a unique bounded solution for u and ξ (t) ξr(t) and ζ (t)
|     |     |     |     |     |     |     | i   | i   | i   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
ζr(t), as t → ∞, if and only if directed graph G has a directed spanning
n+1
tree.
(cid:2)
Proof: Let M and b be defined as in the proof of Theorem 5.13. Define d =
| [dT,...,dT]T |     | ∈Rmn, | where |     |     |     |     |     |     |
| ------------ | --- | ----- | ----- | --- | --- | --- | --- | --- | --- |
|              | 1   | n     |       |     |     |     |     |     |     |
(cid:2)n
|     |     | d =−K |     | tanh[ | a   | (ξ −ξ | )+a | (ξ −ξr)] |     |
| --- | --- | ----- | --- | ----- | --- | ----- | --- | -------- | --- |
|     |     | i     | ri  |       | ij  | i     | j   | i(n+1) i |     |
j=1
(cid:2)n
|     |     |     | −K  | tanh[ | a   | (ζ −ζ | )+a | (ζ −ζr)]. |     |
| --- | --- | --- | --- | ----- | --- | ----- | --- | --------- | --- |
|     |     |     | vi  |       | ij  | i     | j   | i(n+1) i  |     |
j=1
ζ˙
| Noting | that | j =u | j , we | rewrite | (5.16)  | as  |      |     |        |
| ------ | ---- | ---- | ------ | ------- | ------- | --- | ---- | --- | ------ |
|        |      |      |        | (M ⊗I   | )u+(b⊗I |     | )ζ˙r | =d, | (5.17) |
|        |      |      |        |         | m       |     | m    |     |        |
(cid:2)
where u = [uT,...,uT]T. Note that b, ζ˙r, M, and d are all bounded. The
|     |     | 1   | n   |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
uniqueness and boundedness of u i follows from the proof of Theorem 3.8.
|     | Note | that (5.17) | can | be written |        | as  |         |     |        |
| --- | ---- | ----------- | --- | ---------- | ------ | --- | ------- | --- | ------ |
|     |      |             | e¨  | =−K        | tanh(e | )−K | tanh(e˙ | ),  | (5.18) |
|     |      |             |     | i          | ri     | i   | vi      | i   |        |
(cid:7)
(cid:2)
| wheree |     | = n | a (ξ | −ξ )+a |        | (ξ −ξr).ConsidertheLyapunovfunction |     |     |     |
| ------ | --- | --- | ---- | ------ | ------ | ----------------------------------- | --- | --- | --- |
|        | i   | j=1 | ij i | j      | i(n+1) | i                                   |     |     |     |
candidate
(cid:2)n
1
|     |     |     | V = | {1TK |      | log[cosh(e | )]+ | e˙Te˙ }, |     |
| --- | --- | --- | --- | ---- | ---- | ---------- | --- | -------- | --- |
|     |     |     |     |      | m ri |            | i   | 2 i i    |     |
i=1

| 118 | 5 Extensions |     | to a Reference | Model |     |     |     |
| --- | ------------ | --- | -------------- | ----- | --- | --- | --- |
which is positive definite and radially unbounded with respect to e and e˙ .
i i
| Differentiating |     | V gives |     |     |     |     |     |
| --------------- | --- | ------- | --- | --- | --- | --- | --- |
(cid:2)n
|     | V˙  | (e˙TK |           | )+e˙T[−K |           | )−K          |       |
| --- | --- | ----- | --------- | -------- | --------- | ------------ | ----- |
|     | =   |       | ri tanh(e | i        | ri tanh(e | i vi tanh(e˙ | i )]) |
|     |     | i     |           | i        |           |              |       |
i=1
(cid:2)n
|     | =−  | e˙TK | tanh(e˙ | )≤0. |     |     |     |
| --- | --- | ---- | ------- | ---- | --- | --- | --- |
|     |     |      | i vi    | i    |     |     |     |
i=1
Let S = {(e ,e˙ )|V˙ = 0}. Note that V˙ ≡ 0 implies that e˙ ≡ 0, which
|     |     | i i |     |     |     | i   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     | ≡   |     | ≡   | ≡   |     |
in turn implies that e¨ i 0. Because e˙ i 0 and e¨ i 0, it follows that
e ≡ 0 from (5.18). By Theorem F.4, it follows that e (t) → 0 and e˙ (t) → 0
| i   |     |     |     |     |         | i       | i   |
| --- | --- | --- | --- | --- | ------- | ------- | --- |
|     |     |     |     |     | (cid:2) | (cid:2) |     |
asymptotically, as t → ∞. Letting e = [eT,...,eT]T and ξ = [ξT,...,ξT]T
|     |     |     |     |     | 1   | n   | 1 n |
| --- | --- | --- | --- | --- | --- | --- | --- |
givese=(M⊗I )r+(b⊗I )ξr.ThenbyfollowingtheproofofTheorem3.15,
|     |     | m   | m   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
we know that ξ (t) → ξr(t) and ζ (t) → ζr(t), as t → ∞, if and only if G
|     |            | i        |       | i   |     |     | n+1 |
| --- | ---------- | -------- | ----- | --- | --- | --- | --- |
| has | a directed | spanning | tree. |     |     |     |     |
Remark 5.17. Note that with the full access strategy (5.10), the reference
modelmustbeavailabletoallfollowers.Incontrast,consensusalgorithms(5.14)
and (5.16) do not impose this constraint and allow the reference model to be
available to one or more followers. Also note that with the leader-following
strategy (5.12), each vehicle except the unique team leader has exactly one
parent (i.e., no information loops are allowed). In contrast, consensus algo-
rithms (5.14) and (5.16) allow information to flow from any follower to any
otherfollowerwhileguaranteeingthatthestabilityremainsunchangedaslong
astheminimumconnectivityrequirementsinTheorems5.13and5.16aresat-
isfied. As a result, information feedback can be introduced through the gen-
eral information exchange and coupling between neighboring vehicles, which
increases redundancy and robustness to failures of interaction links. The full
accessstrategy(5.10)canbeconsideredaspecialcaseof (5.14),wheretheref-
erence model is available to all followers.The leader-followingstrategy (5.12)
can also be considered a special case of (5.14), where the reference model is
(cid:13)(cid:14)
available only to one follower and each follower has exactly one parent.
5.4 Notes
The results in this chapter are based mainly on [179,181–183]. Section 5.2.1
follows[170,174].Avariantofalgorithm(5.8)isstudiedin[261]overanundi-
rected interaction topology. A variant of algorithm (5.12) is studied in [244].
See [155,232,238]for flocking algorithms for double-integrator dynamics.
| Acknowledgment |     |     | is given | to  |     |     |     |
| -------------- | --- | --- | -------- | --- | --- | --- | --- |
(cid:10)c2007 IEEE. Reprinted, with permission, from Wei Ren, “Second-order
consensus algorithm with extensions to switching topologies and reference
models,” Proceedings of the American Control Conference, pp. 1431–1436,
| New | York City, | 2007. |     |     |     |     |     |
| --- | ---------- | ----- | --- | --- | --- | --- | --- |

5.4 Notes 119
(cid:10)c2007 IEEE. Reprinted, with permission, from Wei Ren, “On consensus
algorithmsfordouble-integratordynamics,”Proceedings of the IEEE Confer-
ence on Decision and Control, New Orleans, LA, 2007 (to appear).
(cid:10)c2007 IEEE. Reprinted, with permission, from Wei Ren, “On consensus
algorithmsfordouble-integratordynamics,”IEEETransactionsonAutomatic
Control, 2007 (under review).

Part IV
| Consensus | Algorithms | for Rigid | Body Attitude |
| --------- | ---------- | --------- | ------------- |
Dynamics

6
Consensus Algorithms for Rigid Body Attitude
Dynamics
Thischapterconsidersconsensusalgorithmsforrigidbodyattitudedynamics.
We propose algorithms for attitude consensus among multiple rigid bodies
for three different cases. In the first case, multiple rigid bodies align their
attitudes with zero final angular velocities. In the second case, multiple rigid
bodiesconvergeto aconstantreferenceattitude while aligningtheirattitudes
duringthetransitionwithzerofinalangularvelocitieswithouttherequirement
for absolute and relative angular velocity measurements. In the third case,
multiple rigid bodies converge to the same angular velocity while aligning
theirattitudesduringthetransition.Simulationresultsforattitudeconsensus
among six rigid bodies demonstrate the effectiveness of the algorithms.
6.1 Problem Statement
Attitude controlofarigidbody has beenstudied extensivelyinthe literature
(see [129,235,249,251,254]and referencestherein). Motivated by the benefits
gained by having multiple inexpensive, simple rigid bodies working together,
cooperative attitude control of multiple rigid bodies has received recent at-
tention.For example,in space-basedinterferometryapplications,a formation
ofnetworkedspacecraftcouldbe usedtosynthesizeaspace-basedinterferom-
eter with baselines reaching tens to hundreds of kilometers as an alternative
to traditional monolithic spacecraft, where it is essential that the spacecraft
maintain relative or the same attitude during formation maneuvers.
Themainpurposeofthischapteristoextendtheconsensusalgorithmsfor
single- or double-integrator dynamics in Chapters 2–5 to rigid body attitude
dynamics. We use the term attitude consensus or attitude alignment to refer
to the case where multiple rigid bodies maintain the same attitude.
It is worthwhile to mention that although we use PD-like control laws
for attitude alignment, the algorithms developed for the double-integrator
dynamics are not directly applicable to rigid body attitude dynamics due to

124 6 Consensus Algorithms for Rigid Body AttitudeDynamics
the inherent nonlinearity in attitude kinematics. The extension from double-
integrator dynamics to rigid body attitude dynamics is nontrivial. It is also
worthwhile to mention that in contrastto workin attitude controlof a single
rigidbody,thenoveltyofthischapterliesintheanalysisofthewayinterrigid
body information exchange plays a key role in attitude alignment from a
consensus point of view.
We use Euler parameters (i.e., unit quaternions) to represent rigid body
attitudes in this chapter. Let q = [q-T,q ]T ∈ R4 be the unit quaternion,
i i i
where q- ∈ R3 and q ∈ R are, respectively, the vector and scalar parts of q ,
i i i
ω ∈ R3 be the angular velocity, and J ∈ R3×3 and τ ∈ R3 be, respectively,
i i i
theinertialtensorandcontroltorqueoftheithrigidbody.Rigidbodyattitude
dynamics using Euler parameters are given by (D.2). Attitude consensus or
alignmentisachievedorreachedamongnnetworkedrigidbodiesifforallq (0)
i
and ω (0) and all i,j =1,...,n, (cid:9)q (t)−q (t)(cid:9)→0 and (cid:9)ω (t)−ω (t)(cid:9)→0,
i i j i j
as t→∞.
In this chapter, we consider an undirected, time-invariant interaction
topology and assume that all weights in the control laws are constant. We
assume that the vectors in each control law have been appropriately trans-
formed and represented in the same coordinate frame.
As in Chapter 4, the interaction topologies for q and ω among the n
i i
rigid bodies are allowed to be different under some circumstances. We use
(cid:2) (cid:2)
undirected graphs GA = (V ,EA) and GB = (V ,EB) to model the inter-
n n n n n n
action topologies for q and ω , respectively, among the n rigid bodies. Let
i i
A =[a ]∈Rn×n andB =[b ]∈Rn×n bethe adjacencymatrixassociated
n ij n ij
with G
n
A and(cid:7) G
n
B, respectively. Also let LA
n
= [(cid:2)
ij
] ∈ Rn×n (i.e., (cid:2)
ij
= −a
ij
,
i (cid:6)= j, (cid:2) = n a ) and LB = [(cid:2) ] ∈ Rn×n (i.e., (cid:2) = −b , i (cid:6)= j,
(cid:7)ii j=1,j(cid:5)=i ij n ij ij ij
(cid:2) = n b ) be the Laplacian matrix associated with GA and GB, re-
ii j=1,j(cid:5)=i ij n n
spectively. When there is only one interaction topology associated with the
(cid:2)
n rigid bodies, we simply use G = (V ,E ) to model the interaction topol-
n n n
ogy among the n rigid bodies, as in Chapter 2. Similarly, A and L are,
n n
respectively, the adjacency matrix and Laplacian matrix associated with G .
n
6.2 Attitude Consensus with Zero Final Angular
Velocities
In this section, we consider the case where multiple rigid bodies align their
attitudesduringthetransitionandtheirangularvelocitiesapproachzero.The
proposed control torque for the ith rigid body is
(cid:2)n
τ =−k q (cid:2) r∗q −D ω − [a q .∗q +b (ω −ω )], i=1,...,n, (6.1)
i G i Gi i ij j i ij i j
j=1
wherek isanonnegativescalar,D ∈R3×3 issymmetricalpositivedefinite,
G Gi
qr ∈ R4 denotes the constant reference attitude for each rigid body, and a
ij

6.2 AttitudeConsensus with Zero Final Angular Velocities 125
and b are, respectively, the (i,j) entry of the adjacency matrix A ∈Rn×n
ij n
and B ∈Rn×n associated with, respectively, GA and GB
n n n
Remark 6.1. Note that control law (6.1) is model independent (i.e., no J ).
i
Also note that although certain torque feedback can be chosen to linearize
(D.2b), the quaternion kinematics (D.2a) are inherently nonlinear. This fea-
turemakestherigidbodyattitudealignmentproblemmorecomplicatedthan
consensus algorithms for systems modeled by single or double-integrator dy-
namics. (cid:13)(cid:14)
We have the following theorem for attitude alignment among multiple
networked rigid bodies with control torque (6.1):
Theorem 6.2.Suppose that the(cid:7)control torque is given by (6.1) and G
n
A and
GB are undirected.1 If k > 2 n a , then q (t) → qr and ω (t) → 0,
n G j=1 ij i i
i = 1,...,n, as t → ∞. If k = 0 and GA is a tree,2 then q (t) → q (t) and
G n i j
ω (t)→0, i=1,...,n, as t→∞.
i
Proof: (cid:7)
Subcase A: k >2 n a .
G j=1 ij
Consider the Lyapunov function candidate
(cid:2)n (cid:2)n (cid:2)n (cid:2)n
1 1
V =k (cid:9)qr∗ q −q (cid:9)2+ a (cid:9)qr∗ q −qr∗ q (cid:9)2+ (ωTJ ω ),
G i I 2 ij i j 2 i i i
i=1 i=1j=1 i=1
whereq = (cid:2) [0,0,0,1]T.NotethatV ispositivedefinitewithrespecttoqr∗q −
I i
q andω ,i=1,...,n.Theset{qr∗q −q ,ω |V ≤c},wherec>0,iscompact
I i i I i
with respect to qr∗q −q and ω , i=1,...,n.
i I i
Applying Lemma D.1, the derivative of V is
(cid:2)n (cid:2)n (cid:2)n
V˙ =k ωTq (cid:2) r∗q + 1 a (ω −ω )Tq .∗q
G i i 2 ij i j j i
i=1 i=1j=1
(cid:2)n
+ ωT(τ −ω ×J ω ). (6.2)
i i i i i
i=1
Note that ωT(ω ×J ω )=0 and that
i i i i
1 That is, A and B are symmetrical.
n n
2 Thecondition that GA isa tree implies that |EA|=n−1, where |·|denotes the
n n
cardinality of a set.

| 126 6 | Consensus | Algorithms        | for Rigid | Body  | AttitudeDynamics |     |     |
| ----- | --------- | ----------------- | --------- | ----- | ---------------- | --- | --- |
|       |           | (cid:2)n (cid:2)n |           |       |                  |     |     |
|       |           | 1                 |           | .∗q   |                  |     |     |
|       |           |                   | a (ω −ω   | )Tq   |                  |     |     |
|       |           |                   | ij i      | j j i |                  |     |     |
2
i=1j=1
|     |     | (cid:2)n   | (cid:2)n | (cid:2)n   | (cid:2)n |        |       |
| --- | --- | ---------- | -------- | ---------- | -------- | ------ | ----- |
|     |     | 1          | .∗q      | 1          |          | .∗q    |       |
|     | =   | ωT(        | a q      | )−         | a        | ωTq    |       |
|     |     | 2          | i ij j i | 2          | ij       | j j i  |       |
|     |     | i=1        | j=1      | i=1j=1     |          |        |       |
|     |     | (cid:2)n   | (cid:2)n | (cid:2)n   | (cid:2)n |        |       |
|     |     | 1          | .∗q      | 1          |          | .∗q    |       |
|     | =   | ωT(        | a q      | )−         | a        | ωTq    |       |
|     |     | 2          | i ij j i | 2          | ji       | j j i  |       |
|     |     | i=1        | j=1      | i=1j=1     |          |        |       |
|     |     | (cid:2)n   | (cid:2)n | (cid:2)n   | (cid:2)n |        |       |
|     |     | 1          | .∗q      | 1          |          | .∗q    |       |
|     | =   | ωT(        | a q      | )+         | a        | ωTq    |       |
|     |     | 2          | i ij j i | 2          | ji       | j i j  |       |
|     |     | i=1        | j=1      | j=1i=1     |          |        |       |
|     |     | 1 (cid:2)n | (cid:2)n | 1 (cid:2)n | (cid:2)n |        |       |
|     |     | ωT(        | .∗q      |            | ωT(      | .∗q    |       |
|     | =   |            | a q      | )+         |          | a q )  |       |
|     |     | 2          | i ij j i | 2          | j        | ji i j |       |
|     |     | i=1        | j=1      | j=1        | i=1      |        |       |
|     |     | (cid:2)n   | (cid:2)n |            |          |        |       |
|     |     | ωT(        | .∗q      |            |          |        |       |
|     | =   |            | a q ),   |            |          |        | (6.3) |
|     |     | i          | ij j i   |            |          |        |       |
|     |     | i=1        | j=1      |            |          |        |       |
where we have used the fact that a =a to obtain the second equality and
|     |     |     | ij  | ji  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
we have switched the order of the summation signs and have used the fact
| .∗q          | =−q .∗q |               |                |                   |         |       |     |
| ------------ | ------- | ------------- | -------------- | ----------------- | ------- | ----- | --- |
| that q       |         | to obtain     | the third      | equality.         |         |       |     |
| j            | i i     | j             |                |                   |         |       |     |
| As a         | result, | (6.2) becomes |                |                   |         |       |     |
|              |         |               | (cid:2)n       | (cid:2)n          |         |       |     |
|              |         |               | (cid:2)        |                   | .∗q     |       |     |
|              |         | V˙ =          | ωT(k q r∗q     | +                 | a q     | +τ ). |     |
|              |         |               | i G            | i                 | ij j i  | i     |     |
|              |         |               | i=1            | j=1               |         |       |     |
| With control | law     | (6.1),        | the derivative | of V              | becomes |       |     |
|              |         | (cid:2)n      |                | (cid:2)n (cid:2)n |         |       |     |
1
|          | V˙ =−    | (ωTD     | )−        |          | (cid:9)ω | −ω (cid:9)2 ≤0, |       |
| -------- | -------- | -------- | --------- | -------- | -------- | --------------- | ----- |
|          |          |          | Gi ω i    |          | b ij i   | j               | (6.4) |
|          |          |          | i         | 2        |          |                 |       |
|          |          | i=1      |           | i=1j=1   |          |                 |       |
| where we | have     | used the | fact that |          |          |                 |       |
|          | (cid:2)n | (cid:2)n |           | (cid:2)n | (cid:2)n |                 |       |
1
|     |     | ωT  | b (ω −ω )= |     | b (cid:9)ω | −ω (cid:9)2, |     |
| --- | --- | --- | ---------- | --- | ---------- | ------------ | --- |
|     |     | i   | ij i j     |     | ij         | i j          |     |
2
|           | i=1    | j=1      |                | i=1j=1 |      |     |     |
| --------- | ------ | -------- | -------------- | ------ | ---- | --- | --- |
| following | (4.15) | in Lemma | 4.18 by noting | that   | b =b | .   |     |
|           |        |          |                |        | ij   | ji  |     |
Let Ω = {qr∗q −q ,ω |V˙ = 0}. Note that V˙ ≡ 0 implies that ω ≡ 0,
|     |     | i   | I i |     |     |     | i   |
| --- | --- | --- | --- | --- | --- | --- | --- |
≡0,
| i=1,...,n. | Because | ω   | we know | that |     |     |     |
| ---------- | ------- | --- | ------- | ---- | --- | --- | --- |
i
(cid:2)n
|     |     | (cid:2) r∗q | .∗q        |       |           |     |       |
| --- | --- | ----------- | ---------- | ----- | --------- | --- | ----- |
|     |     | k G q       | i + a ij q | i =0, | i=1,...,n |     | (6.5) |
j
j=1
| from (D.2b) | and | (6.1). |     |     |     |     |     |
| ----------- | --- | ------ | --- | --- | --- | --- | --- |
Noting that q∗q =q∗(qrqr∗)q =(q∗qr)(qr∗q ), we rewrite (6.5) as
|     |     | j i | j i | j   | i   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |

6.2 AttitudeConsensus with Zero Final Angular Velocities 127
p
(cid:3)∗qr∗q
=0, (6.6)
i i
where
(cid:2)n
p =k q + a
qr∗
q . (6.7)
i G I ij j
j=1
Also note that (6.6) is equivalent to
−qr∗q p- +p q (cid:2) r∗q +q (cid:2) r∗q ×p- =0. (6.8)
i i i i i i
Multiplying (6.8) by (q (cid:2) r∗q ×p-)T, gives
i i
(cid:18) (cid:18)
(cid:18) (cid:18)2
(cid:18)q (cid:2) r∗q ×p-(cid:18) =0. (6.9)
i i
Combining (6.8) and (6.9) gives
−qr∗q p- +p q (cid:2) r∗q =0. (6.10)
i i i i
Using (6.7), we rewrite (6.10) as
(cid:2)n (cid:2)n
−qr∗q a q (cid:2) r∗q +(k + a qr∗q )q (cid:2) r∗q =0, i=1,...,n. (6.11)
i ij j G ij j i
j=1 j=1
Note that (6.11) can be written in matrix form as
[P(t)⊗I ]q- =0,
3 s
where q- s ∈ R3n is a column vector stack composed of q (cid:2) (cid:7) r∗q (cid:7) , (cid:2) = 1,...,n,
and P(t) = [p (t)] ∈ Rn×n is given by p (t) = k + n a qr∗q and
ij ii G j=1 ij j
p ij (t)=−a ij qr∗q i . (cid:7)
Noting that |qr∗q | ≤ 1, j = 1,...,n, and k > 2 n a , we see that
j G j=1 ij
P(t)isstrictlydiagonallydominantandthereforehasfullrank,whichinturn
implies that q- ≡ 0. Thus, we see that q (cid:2) r∗q ≡ 0, i = 1,...,n, which implies
s i
that qr∗q −q ≡0 if V˙ ≡0.
i I
Therefore,byTheoremF.3,itfollowsthatqr∗q (t)−q →0andω (t)→0,
i I i
as t→∞. Equivalently, we know that q (t)→qr and ω (t)→0, i=1,...,n,
i i
as t→∞.
Subcase B: k =0 and GA is a tree.
G n
Consider the Lyapunov function candidate
(cid:2)n (cid:2)n (cid:18) (cid:18) (cid:2)n
V = 1 a (cid:18) q ∗ q −q (cid:18)2 + 1 (ωTJ ω ),
2 ij j i I 2 i i i
i=1j=1 i=1
which is positive definite with respect to q∗q −q and ω , i = 1,...,n. The
j i I i
set {(q∗q −q ,ω )|V ≤c},where c>0, is compact with respect to q∗q −q
j i I i j i I

128 6 Consensus Algorithms for Rigid Body AttitudeDynamics
andω ,i=1,...,n.ThenbyfollowingaproceduresimilartothatinSubcase
i
A, we get (6.4).
Let Ω ={(q∗q −q ,ω )|V˙ =0} and note that V˙ ≡0 implies that ω ≡0,
j i I i i
i=1,...,n. Because ω ≡0, we know that
i
(cid:2)n
a q
.∗q
=0, i=1,...,n, (6.12)
ij j i
j=1
from (D.2b) and (6.1).
Let q .∗q be a variable associatedwith an edge (i,j)∈EA. Note that (i,j)
j i n
and (j,i) denote the same element in the edge set EA when GA is undirected.
n n
Also note that q .∗q = −q .∗q . In the following, we assume that i <j without
i j j i
loss of generality.Noting that GA is a tree, we know that |EA|=n−1, which
n n
implies that there are n−1 variables associated with EA. Let q- ∈ R3(n−1)
n u
be a column vector stack composed of all q .∗q , where (i,j) ∈ EA. By noting
j i n
that q .∗q =−q .∗q , (6.12) can be rewritten as
i j j i
(Q⊗I )q- =0, (6.13)
3 u
where Q∈Rn×n−1.
Consider a system given by Qx˜ = 0, where x˜ is a column vector stack
composed of x =x −x , where (i,j)∈EA, and x ∈R, k =1,...,n. Note
ij i j n k
thatQx˜=0canbewrittenasLAx=0,wherex=[x ,...,x ]T andLA isthe
n 1 n n
n×n (symmetrical) Laplacian matrix associated with undirected graph GA.
n
Noting that GA is a tree, we know that x =···=x , which in turn implies
n 1 n
that x˜=0. As a result, we know that Q can be transformedto a rowechelon
form to show that Qx˜ = 0 implies that x = 0, where (i,j)∈EA. The same
ij n
transformation procedure can be used on (6.13) to show that (Q⊗I )q- =0
3 u
implies that q .∗q = 0, where (i,j) ∈ EA. Thus, we see that q∗q −q ≡ 0,
j i n j i I
∀i(cid:6)=j, if V˙ ≡0.
Therefore,byTheoremF.3,itfollowsthatq∗(t)q (t)−q →0andω (t)→
j i I i
0,as t→∞.Equivalently,we knowthat q (t)→q (t), ∀i(cid:6)=j,andω (t)→0,
i j i
i=1,...,n, as t→∞.
6.3 Attitude Consensus Without Absolute and Relative
Angular Velocity Measurements
Note that (6.1) requires both absolute and relative angular velocity measure-
ments. We propose a control torque without absolute and relative angular
velocity measurements based on a passivity approach as
(cid:2)n
xˆ˙ =Fxˆ + a (q −q )+κq , (6.14a)
i i ij i j i
j=1

6.3 AttitudeConsensusWithoutAbsoluteandRelativeAngularVelocityMeasurements 129
(cid:2)n
y =PFxˆ +P a (q −q )+κPq , (6.14b)
i i ij i j i
j=1
(cid:2)n
τ =−k q (cid:2) r∗q − a q .∗q −q .∗y , i=1,...,n, (6.14c)
i G i ij j i i i
j=1
where F ∈ R4×4 is Hurwitz, κ is a positive scalar, a is the (i,j) entry
ij
of the adjacency matrix A ∈ Rn×n associated with G , k is a positive
n n G
scalar, qr ∈ R4 denotes the constant reference attitude for each rigid body,
and P ∈ R4×4 is the symmetrical positive-definite solution of the Lyapunov
equation FTP +PF = −Q with Q ∈ R4×4 symmetrical positive definite.
Note that(cid:7)only q
i
need to be exchanged among rigid bodies. Also note that
the term n a (q −q ) in (6.14a) introduces relative damping between
j=1 ij i j (cid:7)
neighboringrigidbodies,whereastheterm n a q .∗q in(6.14c)introduces
j=1 ij j i
mutual consensus between neighbors.
Remark 6.3. A passivityapproachis usedin[129,130,160,235]forcontrolling
a single vehicle. Algorithm (4.22) extends the passivity approach in these
references to achieve attitude consensus among multiple rigid bodies. (cid:13)(cid:14)
Theorem 6.4.Suppose that G n(cid:7)is undirected. With (6.14), q
i
(t) → qr and
ω (t)→0, as t→∞, if k >2 n a .
i G j=1 ij
Proof: Consider the Lyapunov function candidate
(cid:2)n (cid:2)n (cid:2)n (cid:2)n
1 1
V =k (cid:9)qr∗ q −q (cid:9)2+ a (cid:9)qr∗ q −qr∗ q (cid:9)2+ (ωTJ ω )
G i I 2 ij i j 2 i i i
i=1 i=1j=1 i=1
+xˆ˙T(M ⊗I ) −1(I ⊗P)xˆ˙,
4 n
where xˆ = (cid:2) [xˆT,...,xˆT]T and M = (cid:2) L +κI with L ∈ Rn×n the Lapla-
1 n n n n
cian matrix associated with undirected graph G . Note that L is symmet-
n n
rical positive semidefinite because G is undirected from which it follows
n
that both M and M−1 are symmetrical positive definite. From Lemma C.8,
(M⊗I )−1(I ⊗P)=(M−1⊗I )(I ⊗P)=M−1I ⊗I P =I M−1⊗PI =
4 n 4 n n 4 n 4
(I ⊗P)(M−1⊗I )=(I ⊗P)(M⊗I )−1,thatis,(M⊗I )−1 andI ⊗P com-
n 4 n 4 4 n
mute. Similarly, it is straightforward to show that (M ⊗I )−1 and I ⊗FT
4 n
also commute. Note that both M−1I ⊗I P and (M ⊗I )−1(I ⊗P) are
n 4 4 n
symmetricalpositivedefinite.Therefore,V is positivedefinite withrespectto
qr∗q −q , ω , and xˆ˙ . The set {(qr∗q −q ,ω ,xˆ˙ )|V ≤ c}, where c > 0, is
i I i i i I i i
compact with respect to qr∗q −q , ω , and xˆ˙ .
i I i i
By applying Lemma D.1, we obtain the derivative of V as

130 6 Consensus Algorithms for Rigid Body AttitudeDynamics
(cid:2)n (cid:2)n (cid:2)n (cid:2)n
V˙ =k ωTq (cid:2) r∗q + 1 a (ω −ω )Tq .∗q + ωT[τ −ω ×(J ω )]
G i i 2 ij i j j i i i i i i
i=1 i=1j=1 i=1
+xˆ˙T(I ⊗FT)(M ⊗I ) −1(I ⊗P)xˆ˙
n 4 n
+q˙T(M ⊗I )T(M ⊗I ) −1(I ⊗P)xˆ˙
4 4 n
+xˆ˙T(M ⊗I ) −1(I ⊗P)(I ⊗F)xˆ˙
4 n n
+xˆ˙T(M ⊗I ) −1(I ⊗P)(M ⊗I )q˙,
4 n 4
where we have used the relation
x¨ˆ=(I ⊗F)xˆ˙ +(M ⊗I )q˙ (6.15)
n 4
with q˙=[q˙T,...,q˙T]T. From (6.3), note that when G is undirected, then
1 n n
(cid:2)n (cid:2)n (cid:2)n (cid:2)n
1 a (ω −ω )Tq .∗q = ωT( a q .∗q ).
2 ij i j j i i ij j i
i=1j=1 i=1 j=1
Further note that (M⊗I )−1 andI ⊗FT commute,(M⊗I )−1 andI ⊗P
4 n 4 n
commute, M ⊗I = (M ⊗I )T, y = (I ⊗P)xˆ˙ with y = [yT,...,yT]T, and
4 4 n 1 n
FTP +PF =−Q. The derivative of V, therefore, becomes
(cid:2)n
V˙ =− ωTq .∗y −xˆ˙T(M ⊗I ) −1(I ⊗Q)xˆ˙ +2q˙Ty.
i i i 4 n
i=1
(cid:7) (cid:7) (cid:7) (cid:7)
Notethat2q˙Ty =2 n q˙Ty =2 n q˙∗y = n ωˇ∗q∗y = n ωTq .∗y ,
i=1 i i i=1 i i i=1 i i i i=1 i i i
where we have used (D.1), (D.3), and the fact that q∗ = [−q-T,q ]T and
i i i
ωˇ∗ =[−ωT,0]T. Therefore, the derivative of V is given by
i i
V˙ =−xˆ˙T(M ⊗I ) −1(I ⊗Q)xˆ˙,
4 n
which is negative semidefinite because (M ⊗I )−1(I ⊗Q) = M−1I ⊗QI
4 n n 4
is symmetrical positive definite.
Let S ={(qr∗q −q ,ω ,xˆ˙ )|V˙ =0}. Note that V˙ ≡0 implies that xˆ˙ ≡0,
i I i i
which in turn implies that (M ⊗I )q˙ ≡ 0 according to (6.15) and y ≡ 0 by
4 i
noting that y = Pxˆ˙ according to (6.14b). Because M ⊗I is symmetrical
i i 4
positive definite, it follows that q˙ ≡ 0. Because ωˇ = 2q∗q˙ from (D.3), it
i i i i
follows that ω ≡0. From (D.2b) and (6.14c), it then follows that
i
(cid:2)n
k q (cid:2) r∗q + a q .∗q ≡0, i=1,...,n.
G i ij j i
j=1
Then by following t(cid:7)he proof for Subcase A in Theorem 6.2, we know that
qr∗q ≡q ifk >2 n a .ByTheoremF.3,itfollowsthatq (t)→qr and
i I G j=1 ij i
ω (t)→0, as t→∞.
i

6.4 AttitudeConsensus with Nonzero Final Angular Velocities 131
6.4 Attitude Consensus with Nonzero Final Angular
Velocities
In this section, we consider the case where multiple rigid bodies align their
attitudes but with possibly nonzero final angular velocities. The proposed
control torque on the ith rigid body is
(cid:2)n
τ =ω ×J ω −J [a q .∗q +b (ω −ω )], i=1,...,n, (6.16)
i i i i i ij j i ij i j
j=1
where a and b aredefined asin (6.1).Note that (6.16)is modeldependent
ij ij
in the sense that J must be known.
i
Theorem 6.5.Suppose that GA and GB are undirected. With the control
n n
torquegiven by (6.16), if GA is a treeand GB is connected, then q (t)→q (t),
n n i j
and ω (t)→ω (t), ∀i(cid:6)=j, as t→∞.
i j
Proof: Consider the Lyapunov function candidate
(cid:2)n (cid:2)n (cid:18) (cid:18) (cid:2)n
V = 1 a (cid:18) q ∗ q −q (cid:18)2 + 1 ωTω ,
2 ij j i I 2 i i
i=1j=1 i=1
which is positive definite with respect to q∗q −q and ω . The set {(q∗q −
j i I i j i
q ,ω )|V ≤ c}, where c > 0, is compact with respect to q∗q −q and ω ,
I i j i I i
i=1,...,n.
Following a procedure similar to that of Theorem 6.2, we obtain
(cid:2)n (cid:2)n
1
V˙ =− b (cid:9)ω −ω (cid:9)2 ≤0.
ij i j
2
i=1j=1
Let Ω = {(q∗q −q ,ω )|V˙ = 0}. Note and observe that V˙ ≡ 0 implies
j i I i
that ω ≡ ω , ∀i (cid:6)= j, because undirected graph GB is connected. Therefore,
i j n
we see that ω˙ ≡ ω˙ . As a result, we know that ω˙ ∈ span{1 ⊗η}, where
i j n
ω˙ =[ω˙T,··· ,ω˙T]T and η is some 3×1 vector.
1 n
Because ω ≡ω , ∀i(cid:6)=j, we know that
i j
(cid:2)n
ω˙ =− a q .∗q , i=1,...,n, (6.17)
i ij j i
j=1
from (D.2b) and (6.16). We also know that
(cid:2)n (cid:2)n (cid:2)n
ηTω˙ =− ηT( a q .∗q )=0,
i ij j i
i=1 i=1 j=1

| 132 6 Consensus | Algorithms | for Rigid Body | AttitudeDynamics |     |
| --------------- | ---------- | -------------- | ---------------- | --- |
|                 |            |                | .∗q =−q .∗q      |     |
where we have used the fact that a =a and q . As a result, we
|     |     | ij ji | j i i j |     |
| --- | --- | ----- | ------- | --- |
see that ω˙ is orthogonalto span{1 ⊗η}. Therefore,we conclude that ω˙ ≡0.
n
| From (6.17), we | get |     |     |     |
| --------------- | --- | --- | --- | --- |
(cid:2)n
.∗q ≡0,
|     | a ij | q i | i=1,...,n. |     |
| --- | ---- | --- | ---------- | --- |
j
j=1
UndertheassumptionthatundirectedgraphGA isatree,byfollowingthe
n
|                                        |              |         | q∗q −q       | ≡ ∀i (cid:6)= |
| -------------------------------------- | ------------ | ------- | ------------ | ------------- |
| proof for Subcase                      | B in Theorem | 6.2, we | see that     | 0, j, if      |
|                                        |              |         | j i I        |               |
| V˙ ≡0.ByTheoremF.3,itfollowsthatq∗(t)q |              |         | (t)−q →0andω | (t)→ω         |
|                                        |              |         | i I          | i j (t),      |
j
∀i (cid:6)= j, as t → ∞. Equivalently, q (t) → q (t) and ω (t) → ω (t), ∀i (cid:6)= j, as
|     |     | i   | j i | j   |
| --- | --- | --- | --- | --- |
t→∞.
Remark 6.6. Theorems 6.2, 6.4, and 6.5 do not rely on the assumption that
the scalar parts of the unit quaternions must be nonnegative for all time. (cid:13)(cid:14)
| 6.5 Simulation | Results |     |     |     |
| -------------- | ------- | --- | --- | --- |
In this section, we simulate a scenario where six rigid bodies align their atti-
tudesthroughlocalinformationexchange.Weapply,respectively,(6.1),(6.14),
and (6.16) for attitude alignment. For simplicity, we assume that undirected
graphsGA andGB areidentical(i.e., EA =EB).The undirectedgraphforsix
| n   | n   | n   | n   |     |
| --- | --- | --- | --- | --- |
rigid bodies with (6.1), where k > 0, and (6.14) is shown by Fig. 6.1. The
G
undirectedgraphforthe six rigidbodies with(6.1),wherek =0,and(6.16)
G
| is shown by Fig. | 6.2.                                                     |                                                          |                                                          |     |
| ---------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | --- |
|                  | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) |     |
|                  |                                                          | 1 2                                                      | 3                                                        |     |
|                  | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) |     |
|                  |                                                          | 4 5                                                      | 6                                                        |     |
Fig.6.1.Undirectedgraphforsixrigidbodieswith(6.1),wherek >0,and(6.14).
G
| The graph is a | tree. |     |     |     |
| -------------- | ----- | --- | --- | --- |
Therigidbody specificationsareshowninTable6.1.The controlparame-
ters used for each control law are shown in Table 6.2. In the following, we let
qr = [0,0,0,1]T and choose q (0) ∈ R4 and ω (0) ∈ R3 randomly. In the fol-
|     |     | i   | i   |     |
| --- | --- | --- | --- | --- |
lowing,we use a superscript (j) to denote the jth componentof a quaternion
or a vector.
Figures 6.3, 6.4, and 6.5 show, respectively, the attitudes, angular veloci-
ties, and control torques of rigid bodies 1, 3, and 5 with (6.1) in Subcase A.

|     |                                                          |                                                          |     | 6.5                                                      | Simulation | Results 133 |
| --- | -------------------------------------------------------- | -------------------------------------------------------- | --- | -------------------------------------------------------- | ---------- | ----------- |
|     | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) |     | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) |            |             |
|     |                                                          | 1 2                                                      |     | 3                                                        |            |             |
|     | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) |     | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) |            |             |
|     |                                                          | 4 5                                                      |     | 6                                                        |            |             |
Fig. 6.2. Undirected graph for the six rigid bodies with (6.1), where k = 0,
G
and (6.16)
| Table | 6.1. | Rigid body | specifications |     |     |     |
| ----- | ---- | ---------- | -------------- | --- | --- | --- |
m2
| J 1 [1 0.1 | 0.1; 0.1 | 0.1 0.1;     | 0.1 0.1 | 0.9] kg  |       |     |
| ---------- | -------- | ------------ | ------- | -------- | ----- | --- |
| J [1.5 0.2 | 0.3;     | 0.2 0.9 0.4; | 0.3     | 0.4 2.0] | kg m2 |     |
2
| J [0.8 0.1 | 0.2; | 0.1 0.7 0.3; | 0.2 | 0.3 1.1] | kg m2 |     |
| ---------- | ---- | ------------ | --- | -------- | ----- | --- |
3
| J [1.2 0.3  | 0.7; | 0.3 0.9 0.2; | 0.7      | 0.2 1.4] | m2  |     |
| ----------- | ---- | ------------ | -------- | -------- | --- | --- |
| 4           |      |              |          |          | kg  |     |
| J [0.9 0.15 | 0.3; | 0.15 1.2     | 0.4; 0.3 | 0.4 1.2] | m2  |     |
| 5           |      |              |          |          | kg  |     |
m2
| J 6 [1.1 0.35 | 0.45;   | 0.35 1.0   | 0.5; 0.45 | 0.5      | 1.3] kg     |     |
| ------------- | ------- | ---------- | --------- | -------- | ----------- | --- |
| Table 6.2.    | Control | parameters |           | for each | control law |     |
(6.1) SubcaseA Fig. 6.1
| k =1, | D   | =2I 3, a | =5, | and b | =10 if (j,i)∈E | A=E B |
| ----- | --- | -------- | --- | ----- | -------------- | ----- |
| G     | Gi  | ij       |     | ij    |                | n n   |
(6.1) SubcaseB Fig. 6.2
| k     | D   | =2I a |     | b      | (j,i)∈E | A=E B |
| ----- | --- | ----- | --- | ------ | ------- | ----- |
| G =0, | Gi  | 3, ij | =5, | and ij | =10 if  | n n   |
(6.14) Fig. 6.1
| F =−I | 4, κ=1, | P =2I | 4, k | =1, a | =2 if (j,i)∈E | A   |
| ----- | ------- | ----- | ---- | ----- | ------------- | --- |
|       |         |       | G    |       | ij            | n   |
(6.16) Fig. 6.2
| a =5, | and | b =10 | if (j,i)∈EA=EB |     |     |     |
| ----- | --- | ----- | -------------- | --- | --- | --- |
| ij    |     | ij    |                | n   | n   |     |
Note that all rigid bodies converge to the constant reference attitude while
aligning their attitudes during the transition. Also note that their angular
velocities converge to zero.
Figures 6.6, 6.7, and 6.8 show, respectively, the attitudes, angular veloc-
ities, and control toques of rigid bodies 1, 3, and 5 with (6.1) in Subcase B.
Note that all rigid bodies converge to the same attitude, and their angular
velocities converge to zero.
Figures 6.9, 6.10, and 6.11 show, respectively, the attitudes, angular ve-
locities, and control torques of rigid bodies 1, 3, and 5 with (6.14). Note
thatallrigidbodiesconvergetotheconstantreferenceattitudewhilealigning
their attitudes during the transition even without relative angular velocity
measurements. Note that using the passivity approach there exist wiggles in
| Figs. 6.9, 6.10, and 6.11 | .   |     |     |     |     |     |
| ------------------------- | --- | --- | --- | --- | --- | --- |
Figures 6.12, 6.13, and 6.14 show, respectively, the attitudes, angular ve-
locities, and controltorques of rigid bodies 1, 3, and 5 with (6.16). Note that

| 134 | 6 Consensus | Algorithms | for Rigid | Body AttitudeDynamics |     |     |
| --- | ----------- | ---------- | --------- | --------------------- | --- | --- |
1
j=1
j=3
|     | 0.5 |     |     |     |     | j=5 |
| --- | --- | --- | --- | --- | --- | --- |
)1(q
j
0
−0.5
|     | 0 2 | 4   | 6 8 10 | 12 14 | 16  | 18 20 |
| --- | --- | --- | ------ | ----- | --- | ----- |
Time (s)
1
j=1
j=3
j=5
)2(q 0.5
j
0
|     | 0 2 | 4   | 6 8 10 | 12 14 | 16  | 18 20 |
| --- | --- | --- | ------ | ----- | --- | ----- |
Time (s)
0.6
j=1
|     | 0.4 |     |     |     |     | j=3 |
| --- | --- | --- | --- | --- | --- | --- |
j=5
)3(q 0.2
j
0
−0.2
|     | 0 2 | 4   | 6 8 10 | 12 14 | 16  | 18 20 |
| --- | --- | --- | ------ | ----- | --- | ----- |
Time (s)
|     | Fig. | 6.3. Rigid | body attitudes | with (6.1) | in SubcaseA |     |
| --- | ---- | ---------- | -------------- | ---------- | ----------- | --- |
all rigid bodies converge to the same attitude and the same nonzero angular
velocity.
6.6 Notes
The results in this chapter are based mainly on [172,176,178]. See [60] for
consensus algorithms for rigid body attitude dynamics where attitudes are
| represented    | by  | modified | Rodriguez parameters | (MRPs). |     |     |
| -------------- | --- | -------- | -------------------- | ------- | --- | --- |
| Acknowledgment |     | is       | given to             |         |     |     |
(cid:10)c2006
|     | John | Wiley | & Sons. Reprinted, | with permission, |     | from Wei Ren, |
| --- | ---- | ----- | ------------------ | ---------------- | --- | ------------- |
“Distributedattitudealignmentinspacecraftformationflying,”International
Journal of Adaptive Control and Signal Processing, vol. 21, no. 2–3, pp. 95–
| 113, March–April |     | 2007. |     |     |     |     |
| ---------------- | --- | ----- | --- | --- | --- | --- |
(cid:10)c2006 IEEE. Reprinted, with permission, from Wei Ren, “Distributed
attitude consensus among multiple networked spacecraft,” Proceedings of the
American Control Conference, pp. 1760–1765,Minneapolis, MN, 2006.
(cid:10)c2007 IEEE. Reprinted, with permission, from Wei Ren, “Distributed
cooperative attitude synchronization and tracking for multiple rigid bodies,”
IEEE Transactions on Control Systems Technology, 2007 (under review).

6.6 Notes 135
0.4
0.2
0
−0.2
−0.4
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)s/dar(
)1(ω
j
j=1
j=3
j=5
0.4
0.2
0
−0.2
−0.4
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)s/dar(
)2(ω
j
j=1
j=3
j=5
0.2
0.1
0
−0.1
−0.2
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)s/dar(
)3(ω
j
j=1
j=3
j=5
Fig. 6.4. Rigid body angular velocities with (6.1) in SubcaseA
0.5
0
−0.5
−1
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)mN(
)1(τ
j
j=1
j=3
j=5
1
0.5
0
−0.5
−1
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)mN(
)2(τ
j
j=1
j=3
j=5
1
0.5
0
−0.5
−1
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)mN(
)3(τ
j
j=1
j=3
j=5
Fig. 6.5. Rigid body control torqueswith (6.1) in Subcase A

136 6 Consensus Algorithms for Rigid Body AttitudeDynamics
0.8
0.6
0.4
0.2
0
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)1(q j
j=1
j=3
j=5
0.8
0.6
0.4
0.2
0
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)2(q j
j=1
j=3
j=5
1
0.8
0.6
0.4
0.2
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)3(q j
j=1
j=3
j=5
Fig. 6.6. Rigid body attitudeswith (6.1) in Subcase B
0.3
0.2
0.1
0
−0.1
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)s/dar(
)1(ω
j
j=1
j=3
j=5
0.2
0.1
0
−0.1
−0.2
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)s/dar(
)2(ω
j
j=1
j=3
j=5
0.3
0.2
0.1
0
−0.1
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)s/dar(
)3(ω
j
j=1
j=3
j=5
Fig. 6.7. Rigid body angular velocities with (6.1) in Subcase B

6.6 Notes 137
1
0.5
0
−0.5
−1
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)mN(
)1(τ
j
j=1
j=3
j=5
0.5
0
−0.5
−1
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)mN(
)2(τ
j
j=1
j=3
j=5
1
0.5
0
−0.5
−1
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)mN(
)3(τ
j
j=1
j=3
j=5
Fig. 6.8. Rigid body control torques with (6.1) in Subcase B
1
0.5
0
−0.5
−1
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)1(q j
j=1
j=3
j=5
1
0.5
0
−0.5
−1
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)2(q j
j=1
j=3
j=5
1
0.5
0
−0.5
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)3(q
j
j=1
j=3
j=5
Fig. 6.9. Rigid body attitudeswith (6.14)

138 6 Consensus Algorithms for Rigid Body AttitudeDynamics
4
2
0
−2
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)s/dar(
)1(ω j
j=1
j=3
j=5
10
0
−10
−20
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)s/dar(
)2(ω j
j=1
j=3
j=5
4
2
0
−2
−4
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)s/dar(
)3(ω
j
j=1
j=3
j=5
Fig. 6.10. Rigid body angular velocities with (6.14)
2
1
0
−1
−2
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)mN(
)1(τ
j
j=1
j=3
j=5
2
1
0
−1
−2
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)mN(
)2(τ
j
j=1
j=3
j=5
2
1
0
−1
−2
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)mN(
)3(τ
j
j=1
j=3
j=5
Fig. 6.11. Rigid body control torques with (6.14)

6.6 Notes 139
1
0.5
0
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)1(q j
j=1
j=3
j=5
1
0.5
0
−0.5
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)2(q
j
j=1
j=3
j=5
0.8
0.6
0.4
0.2
0
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)3(q j
j=1
j=3
j=5
Fig. 6.12. Rigid body attitudeswith (6.16)
0.3
0.2
0.1
0
−0.1
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)s/dar(
)1(ω
j
j=1
j=3
j=5
0.4
0.3
0.2
0.1
0
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)s/dar(
)2(ω
j
j=1
j=3
j=5
0.4
0.3
0.2
0.1
0
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)s/dar(
)3(ω
j
j=1
j=3
j=5
Fig. 6.13. Rigid body angular velocities with (6.16)

140 6 Consensus Algorithms for Rigid Body AttitudeDynamics
1
0.5
0
−0.5
−1
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)mN(
)1(τ
j
j=1
j=3
j=5
1
0.5
0
−0.5
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)mN(
)2(τ
j
j=1
j=3
j=5
1
0.5
0
−0.5
−1
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)mN(
)3(τ
j
j=1
j=3
j=5
Fig. 6.14. Rigid body control torques with (6.16)

7
| Relative | Attitude |     | Maintenance |     | and | Reference |
| -------- | -------- | --- | ----------- | --- | --- | --------- |
| Attitude | Tracking |     |             |     |     |           |
This chapter extends the consensus algorithms for rigid body attitude dy-
namics in Chapter 6 in two ways. First, we propose algorithms to guarantee
that multiple rigid bodies can maintain given relative attitudes and angular
velocities during the transition.Both fixed andtime-varying relative attitude
maintenanceareconsidered.Second,weproposealgorithmstoguaranteethat
multiple rigidbodies cantrackagiven,time-varying,referenceattitude when
the reference attitude is available only to a subgroupof team members. Both
cases where the attitudes are represented by Euler parameters and modified
Rodriguezparametersareconsidered.Simulationresultsonreferenceattitude
| tracking     | are presented | to       | validate    | our algorithms. |     |     |
| ------------ | ------------- | -------- | ----------- | --------------- | --- | --- |
| 7.1 Relative |               | Attitude | Maintenance |                 |     |     |
In this section, a team of rigid bodies is required to maintain given relative
attitudes andangularvelocities duringthe transition.We considerboth fixed
and time-varying relative attitude maintenance. We assume an undirected,
time-invariant interaction topology and constant weights in the control laws.
|     |     | useundirectedgraphsGA |     |     | =(V (cid:2) ,EA)andGB | =(V (cid:2) ,EB) |
| --- | --- | --------------------- | --- | --- | --------------------- | ---------------- |
As inChapter6,we
|     |     |     |     |     | n n n | n n n |
| --- | --- | --- | --- | --- | ----- | ----- |
to model the interaction topologies for q and ω , respectively, among the n
|                   |     |         |         | i             | i        |                  |
| ----------------- | --- | ------- | ------- | ------------- | -------- | ---------------- |
|                   |     | A       | ]∈Rn×n  | B             | ]∈Rn×n   |                  |
| rigid bodies.     | Let | n =[a   | ij      | and           | n =[b ij | be the adjacency |
| matrix associated |     | with GA | and GB, | respectively. |          |                  |
|                   |     | n       | n       |               |          |                  |
7.1.1 Fixed Relative Attitudes with Zero Final Angular Velocities
When multiple rigid bodies are required to maintain fixed relative attitudes
with zero final angular velocities, we propose the control torque on the ith
| rigid body | as  |     |     |     |     |     |
| ---------- | --- | --- | --- | --- | --- | --- |

142 7 Relative AttitudeMaintenance and Reference AttitudeTracking
τ =−k q (cid:3) r∗q q −D ω
i G i δi Gi i
(cid:2)n
− [a q∗(cid:3) q∗q q +b (ω −ω )], i=1,...,n, (7.1)
ij δj j i δi ij i j
j=1
wherek isanonnegativescalar,D ∈R3×3 issymmetricalpositivedefinite,
G Gi
qr ∈R4 denotes the constantreference attitude for eachrigidbody, a is the
ij
(i,j) entry of the adjacency matrix A ∈ Rn×n associated with GA, b is
n n ij
the (i,j) entry of the adjacency matrix B ∈ Rn×n associated with GB, and
n n
q ∈ R4, i = 1,...,n, are constant quaternions defining the desired relative
δi
attitudes between q and qr.
i
Remark 7.1. Notethattheproductq q∗ definesthedesiredrelativeattitudes
δj δi
between the ith rigid body and the jth rigid body. As a result, relative atti-
tudes among the rigid bodies can be achieved by appropriately choosing q ,
δi
i=1,...,n. (cid:13)(cid:14)
Theorem 7.2.Suppose that th(cid:7)e control torque is given by (7.1), and G
n
A and
GB are undirected. If k > 2 n a , then q (t) → qrq∗ and ω (t) → 0,
n G j=1 ij i δi i
i = 1,...,n, as t → ∞. If k = 0 and GA is a tree, then q∗(t)q (t) → q q∗
G n j i δj δi
and ω (t)→0, as t→∞.
i
Proof: Replacing each q
i
by q
i
q
δi
in the proof of Theorem 6.2, we k(cid:7)now that
q (t)q →qr,thatis,q (t)→qrq∗,i=1,...,n,ast→∞,ifk >2 n a ,
a
i
nd q
δi
(t)q → q (t)q
i
, that is, q
δi∗(t)q
(t) → q q∗, as t → ∞
G
, if k =
j=
0
1
an
ij
d
i δi j δj j i δj δi G
GA is a tree.
n
7.1.2 Time-varying Relative Attitudes and Angular Velocities
When multiple rigid bodies are required to maintain time-varying relative
attitudes and angular velocities, we propose the control torque on the ith
rigid body as
(cid:2)n
τ =−J ω˙ +ω ×(J ω )−J {a (q∗(cid:3) q∗q q )
i i δi i i i i ij δj j i δi
j=1
+b [(ω −ω )+(ω −ω )]}, i=1,...,n, (7.2)
ij i j δi δj
where a and b are defined as in (7.1) and the unit quaternionand angular
ij ij
velocity pair (q ,ω ) satisfies the quaternion kinematics (D.2a) and defines
δi δi
the desired time-varying relative attitudes and angular velocities among the
rigid bodies. Note that (6.16) corresponds to the case where q = q and
δi I
ω =0.
δi
Theorem 7.3.Suppose that the control torque is given by (7.2) and GA and
n
GB are undirected. If GA is a tree and GB is connected, then q∗(t)q (t) →
n n n j i
q (t)q∗ (t), and ω (t)→ω (t)+ω (t)−ω (t), ∀i(cid:6)=j, as t→∞.
δj δi i j δj δi

7.2 Reference AttitudeTracking 143
Proof: Consider the Lyapunov function candidate
(cid:2)n (cid:2)n (cid:18) (cid:18) (cid:2)n
V = 1 a (cid:18) q˜ ∗ q˜ −q (cid:18)2 + 1 ω˜Tω˜ ,
2 ij j i I 2 i i
i=1j=1 i=1
where q˜ = q q and ω˜ = ω +ω . Note that V is positive definite with
i i δi i i δi
respect to q˜∗q˜ −q and ω˜ , i = 1,...,n. The set {(q˜∗q˜ −q ,ω˜ )|V ≤ c},
j i I i j i I i
where c > 0, is compact with respect to q˜∗q˜ − q and ω˜ , i = 1,...,n.
j i I i
Following a procedure similar to that of Theorem 6.2, we obtain
(cid:2)n (cid:2)n
1
V˙ =− b (cid:9)ω˜ −ω˜ (cid:9)2 ≤0.
ij i j
2
i=1j=1
Let S = {(q˜∗q˜ −q ,ω˜ )|V˙ = 0}. Note that V˙ ≡ 0 implies that ω˜ ≡ ω˜ ,
j i I i i j
∀i (cid:6)= j, because undirected graph GB is connected. Following the proof of
n
Theorem6.5withq andω replacedbyq˜ andω˜ ,itfollowsthatq˜(t)→q˜(t)
i i i i i j
and ω˜ (t)→ω˜ (t), ∀i(cid:6)=j, as t→∞. Therefore, q∗(t)q (t)→q (t)q∗(t) and
i j j i δj δi
ω (t)→ω (t)+ω (t)−ω (t), ∀i(cid:6)=j, as t→∞.
i j δj δi
7.2 Reference Attitude Tracking
In this section, a team of rigid bodies is required to track a time-varying
referenceattitude.Weconsiderreferenceattitudetrackingwithattitudesrep-
resented by, respectively, Euler parameters and modified Rodriguez parame-
ters. We assume a directed, time-invariant interaction topology and constant
weights in the control laws.
7.2.1 Reference Attitude Tracking with Attitudes Represented by
Euler Parameters
Suppose that the team consists of the same n rigid bodies as in Chapter 6,
together with an additional (virtual) rigid body labeled n+1, which acts as
the unique (virtual) leader of the team. As in Chapter 3, we call rigid body
n+1the team leader andrigidbodies1,...,nthe followers. Rigidbodyn+1
(cid:2) (cid:2)
has attitude q = qr ∈ R4 and angular velocity ω = ωr ∈ R3, where
n+1 n+1
qr and ωr representthe time-varying reference attitude and angular velocity.
The time-varyingreferenceattitude andangularvelocitysatisfythe reference
attitude dynamics given by
q-˙r =− 1 ωr×q-r+ 1 qrωr, q˙r =− 1 ωr·q-r,
2 2 2
Jrω˙r =−ωr×(Jrωr)+τr, (7.3)

144 7 Relative AttitudeMaintenance and Reference AttitudeTracking
where q-r and qr are, respectively, the vector and scalar parts of qr and Jr
and τr denote, respectively, the reference inertial tensor and control torque
for the team. The objective of this section is to guarantee that q (t) → qr(t)
i
and ω (t)→ωr(t), i=1,...,n, as t→∞.
i
(cid:2) (cid:2)
As in Chapter 5,we use directedgraphs GA =(V ,EA ) andGB =
n+1 n+1 n+1 n+1
(V ,EB ) to model the interaction topologies for q and ω , respectively,
n+1 n+1 i i
among the n+1 rigid bodies. Let A = [a ] ∈ R(n+1)×(n+1) and B =
n+1 ij n+1
[b ]∈R(n+1)×(n+1) be the adjacency matrix associatedwith GA and GB ,
ij n+1 n+1
respectively. When there is only one interaction topology associatedwith the
(cid:2)
n+1rigidbodies,wesimplyuseG =(V ,E )tomodeltheinteraction
n+1 n+1 n+1
topologyamongthen+1rigidbodies,asinChapter3.Similarly,A isthe
n+1
adjacency matrix associated with G .
n+1
Remark 7.4. When we need to focus only on rigid bodies 1 to n (i.e., the
(cid:2) (cid:2)
followers), we still use GA = (V ,EA) and GB = (V ,EB) to model the in-
n n n n n n
teraction topologies for q and ω , respectively, among the n followers, as in
i i
Chapter 6. In addition, A ∈ Rn×n and B ∈ Rn×n are still the adjacency
n n
matrixassociatedwith GA andGB,respectively,asinChapter6.Whenthere
n n
isonlyoneinteractiontopologyassociatedwiththenfollowers,wesimplyuse
(cid:2)
G =(V ,E ) to model the interaction topology among the n followers, as in
n n n
Chapter 2. Similarly, A is the adjacency matrix associated with G . (cid:13)(cid:14)
n n
Time-varying Reference Attitude: Full Access
Whenreferenceattitudedynamics(7.3)isavailabletoallfollowers,wepropose
the control torque on the ith rigid body as
τ =ω ×(J ω )+J ω˙r−k q (cid:2) r∗q −D (ω −ωr)
i i i i i G i Gi i
(cid:2)n
− [a q .∗q +b (ω −ω )], i=1,...,n, (7.4)
ij j i ij i j
j=1
wherek isanonnegativescalar,D ∈R3×3 issymmetricalpositivedefinite,
G Gi
a is the (i,j) entry ofthe adjacency matrixA ∈Rn×n associatedwith GA,
ij n n
and b is the (i,j) entry of the adjacency matrix B ∈Rn×n associatedwith
ij n
GB. Note that (7.4) corresponds to the case where (n + 1,i) ∈ EA and
n n+1
(n+1,i)∈EB , i=1,...,n.
n+1
Theorem 7.5.Suppose that the control torque is given by (7.4) and that GA
n
and G
n
B (cid:7)are undirected. Also suppose that qr(t) and ωr(t) satisfy (7.3). If
k >2 n a , then q (t)→qr(t) and ω (t)→ωr(t), as t →∞. If k =0
G j=1 ij i i G
and GA is a tree, then q (t)→q (t) and ω (t)→ωr(t), as t→∞.
n i j i
(cid:7)
Proof: If k > 2 n a , we let q˜ = qr∗q and ω˜ = ω −ωr. Note that ac-
G j=1 ij i i i i
cordingtoLemmaD.1,q˜ andω˜ alsosatisfythequaternionkinematics(D.2a).
i i

7.2 Reference AttitudeTracking 145
Following the proof of Theorem 7.2 with q , ω , qr, and q replaced, respec-
i i δi
tively, by q˜, ω˜ , q , and q , we see that q˜(t) → q and ω˜ (t) → 0, that is,
i i I I i I i
q (t)→qr(t) andω (t)→ωr(t), as t→∞. If k =0 and GA is a tree, we see
i i G n
that q˜(t)→q˜(t) and ω˜ (t)→0, that is, q (t) →q (t) and ω (t)→ωr(t), as
i j i i j i
t→∞.
Time-varying Reference Attitude: Partial Access
Note that control law (7.4) assumes that reference attitude dynamics (7.3) is
available to each rigid body on the team, which might be restrictive in some
applications. In the general case where (7.3) is available only to some team
members, we propose the control torque on the ith rigid body as
(cid:2)
1
τ =ω ×(J ω )+ J (ω˙r+ ω˙ )
i i i i |N |+1 i j
i j∈Ni
(cid:2)
1
− {k p/ +K [(ω −ωr)+ (ω −ω )]}, i∈V , (7.5a)
|N |+1 qi πi ωi i i j L
i j∈Ni
(cid:2)
1
τ =ω ×(J ω )+ J ω˙
i i i i |N | i j
i j∈Ni
(cid:2)
1
− [k q/ +K (ω −ω )], i∈/ V , (7.5b)
|N | qi πi ωi i j L
i j∈Ni
where N ⊂ V denotes the set of neighbors of rigid body i, |N | denotes
i n i
the cardinality of N , V ⊆ V denotes the set of rigid bodies to which
i L n
the reference attitude dynamics (7.3) is available, k(cid:20)qi is a positive scalar,
K q ωi = ∈ (cid:20) R3×3 ( i q s ∗q sy ) m .N m o e t t e ri t c h a a l t p j os ∈ it N ive d d o e e fi s n n it o e t , im p π p i ly = th [ at j∈ i N ∈ i ( N q j ∗q i i n )] t q h r e ∗q c i a , s a e n o d f
πi j∈Ni j i i j
directedinformationexchange.Alsonotethateachrigidbody’scontroltorque
depends on its neighbors’ attitudes, angular velocities, and angular velocity
derivatives.In practicalimplementation, the derivatives of the neighbors’an-
gular velocities can be calculated by numerical differentiation.
Remark 7.6. Note that (7.5) corresponds to directed graph G whose adja-
n+1
cencymatrixA =[a ]∈R(n+1)×(n+1)isdefinedasa =1,i,j =1,...,n,
n+1 ij ij
if j ∈ N and a = 0 otherwise, a = 1, i = 1,...,n, if i ∈ V and
i ij i(n+1) L
a =0 otherwise, and a =0, j =1,...,n+1. (cid:13)(cid:14)
i(n+1) (n+1)j
Theorem 7.7.Let the adjacency matrix A associated with directed graph
n+1
G be defined as in Remark 7.6. With control torque (7.5), if G has a
n+1 n+1
directed spanning tree,1 then p/(t) → 0, i ∈ V , q/(t) → 0, i ∈/ V , and
πi L πi L
ω (t)→ωr(t), i=1,...,n, as t→∞
i
1 With A n+1 = [a ij ] ∈ R(n+1)×(n+1) defined in Remark 7.6, where a (n+1)j = 0,
j = 1,...,n+1, the condition that G n+1 has a directed spanning tree implies
that rigid body n+1 is the root of the directed spanning tree. This condition

146 7 Relative AttitudeMaintenance and Reference AttitudeTracking
Proof: Notethatcontroltorque(7.5b)hasadenominator|N |.Asintheproof
i
of Theorem 3.8, we know that |N | (cid:6)= 0, i = 1,...,n, if G has a directed
i n+1
spanning tree. Also note that with (7.5), ω˙ exists on both sides of (D.2b).
i
We next show that under the assumption of the theorem, there is a unique
solution for ω˙ .
i
Note that q ≡ qr and ω ≡ ωr. Also let J = N if i ∈/ V and
n+1 n+1 i i L
J =N ∪{n+1} if i∈V . Then (7.5) can be rewritten as
i i L
(cid:2) (cid:2)
1 1
τ =ω ×(J ω )+ J ω˙ − [k s/+K (ω −ω )], i=1,...,n,
i i i i |J | i j |J | qi πi ωi i j
i j∈Ji i j∈Ji
(7.6)
(cid:20)
where s = (cid:2) (q∗q ). Combining (D.2b) and (7.6), gives
πi j∈Ji j i
J ω˙ =−k s/ −K ω , i=1,...,n, (7.7)
i σi qi πi ωi σi
(cid:7)
(cid:2)
where ω = (ω −ω ). Note that (7.7) can be written in matrix form
σi j∈Ji i j
as
J[(M ⊗I )ω˙ +(b⊗I )ω˙r]=d,
3 3
where J = (cid:2) diag(J ,...,J ), ω˙ = (cid:2) [ω˙T,...,ω˙T]T, M = [m ] ∈ Rn×n with
1 (cid:7) n 1 n ij
m =−a andm = n+1 a ,b=[−a ,...,−a ]T ∈Rn,and
ij ij ii j=1,j(cid:5)=i ij 1(n+1) n(n+1)
d=[dT,...,dT]T with d =−k s/ −K ω . Note that J is invertible.Also
1 n i qi πi ωi σi
note that M is invertible under the assumption of the theorem according to
the proofofTheorem3.8.Itfollowsthatthere existsa unique solutionforω˙ ,
i
i=1,...,n.
Lemma D.1 shows that if the unit quaternion and angular velocity pairs
(q ,ω ) and (q ,ω ) both satisfy quaternion kinematics (D.2a), then the unit
k k (cid:7) (cid:7)
quaternion and angular velocity pair (q∗q ,ω −ω ) also satisfy (D.2a). It
(cid:7) k k (cid:7)
is straightforward to extend this argument by induction to show that the
unitquaternionandangularvelocitypair(s ,ω )alsosatisfies(D.2a).Thus
πi σi
given (7.7), Lemma D.2 implies that s/(t)→0 and ω (t)→0, i=1,...,n,
πi σi
as t → ∞. Note that s/(t) → 0 implies that p/(t) → 0, i ∈ V , and
πi πi L
q/(t) → 0, i ∈/ V , as t → ∞. Note that ω (t) → 0, i = 1,...,n, as
πi L σi
t → ∞, implies that (M ⊗I )ω(t)+(b⊗I )ωr(t) → 0, as t → ∞, where
3 3
(cid:2)
ω = [ωT,...,ωT]T. Then, by following the proof of Theorem 3.15, we know
1 n
that ω (t) → ωr(t), i = 1,...,n, as t → ∞, if G has a directed spanning
i n+1
tree.
Remark 7.8. NotethatTheorem7.7showsthatallfollowers’angularvelocities
approachthereferenceangularvelocity,butitisunclearwhetherallfollowers’
is also equivalent to the condition that rigid body n+1 is the only rigid body
that has adirected path toall of theotherrigid bodies on theteam, that is, the
reference states qr, ωr, and ω˙r can flow directly or indirectly to any follower on
theteam.

7.2 Reference AttitudeTracking 147
attitudes approach the reference attitude under the assumption of the theo-
rem.However,whendirectedgraphG hasaspecialstructure,convergence
n+1
to the reference attitude can be concluded. In G , if nodek has exactly
n+1
one parent, node (cid:2), then s/(t) = q .∗q (t) → 0 implies that q (t) → q (t), as
πk (cid:7) k k (cid:7)
t→∞,thatis,rigidbody k approachesthe referenceattitude qr if(cid:2)=n+1,
or rigid bodies k and (cid:2) approach the same attitude if (cid:2) (cid:6)= n+1. As a result,
edge ((cid:2),k) can be deleted fromG , and nodes k and (cid:2) can be combined
n+1
as one single node whose incoming and outgoing edges are the union of the
incoming and outgoing edges of nodes k and (cid:2). By repeating this procedure,
we can simplify G . If G can be simplified to a directed graphwith only
n+1 n+1
one node, then p/(t) → 0, i ∈ V , and q/(t) → 0, i ∈/ V , as t → ∞, di-
πi L πi L
rectly imply that q (t) → qr(t), i = 1,...,n, as t → ∞. The leader-following
i
approach for attitude alignment (e.g., [244,245]) can be considered a special
case of control law (7.5), where G is itself a directed spanning tree. (cid:13)(cid:14)
n+1
Example 7.9. Theorem 7.7 can be illustrated by the following example. Fig-
ure 7.1 shows four different interaction topologies among five rigid bodies,
where node qr denotes the team leader and node i, i = 1,...,4, denote the
ithfollower.InFig.7.1,anedgefromnodeqr tonodej denotesthatreference
attitude dynamics (7.3) is available to rigid body j. In particular,the leader-
following approach (e.g., [244,245]) requires graphs like Figs. 7.1a and 7.1b,
where the interaction topologies are themselves directed spanning trees, im-
plying thateachrigidbody exceptthe teamleaderhasexactly oneparent.In
contrast,controllaw(7.5)isusedforthegraphsshowninFigs.7.1cand7.1d,
whicharemoregeneralthanFigs.7.1aand7.1binthe sensethatinformation
canflowamongallfollowerstointroducefeedbackbetweenneighborsandref-
erence attitude dynamics (7.3) may be available to one or more followers on
theteam.Notethatnodeqr hasadirectedpathtoallfollowersinFigs.7.1a–d.
Also note that using the approach described in Remark 7.8, Figs. 7.1a–d can
be simplified to a directed graph with only one node, which directly implies
that using control law (7.5), q (t)→qr(t), as t→∞. (cid:13)(cid:14)
i
7.2.2 Reference Attitude Tracking with Attitudes Represented by
Modified Rodriguez Parameters
As described in Remark 7.8, Theorem 7.7 shows that with (7.5), all followers
cantracktheirreferenceangularvelocityifG hasadirectedspanningtree.
n+1
However,to conclude that they can track their reference attitude, G must
n+1
satisfytheconditionthatitcanbesimplifiedtoagraphwithonlyonenode.In
this section,weusemodifiedRodriguezparameters(MRPs)(seeAppendix D
fordefinitions)torepresentrigidbodyattitudes andderiveacontrollawthat
guarantees reference attitude tracking under a general directed interaction
topology.
Let σ ∈ R3 be the attitude represented using MRPs and ω ∈ R3 be the
i i
angular velocity of the ith rigid body. Attitude dynamics using MRPs are
given by (D.4). Note that (D.4) can be written as (D.5).

148 7 Relative AttitudeMaintenance and Reference AttitudeTracking
|     |     |     | (cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25) | (cid:15)(cid:15)(cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) | (cid:15)(cid:15)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) | (cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25) | (cid:15)(cid:15)(cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) |     |
| --- | --- | --- | ---------------------------------------------------------------- | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ---------------------------------------------------------------- | ------------------------------------------------------------------------ | -------------------------------------------------------- | --- |
|     |     |     | qr                                                               | 1(cid:4)                                                                 | (cid:4) 4                                                                | qr                                                               | 1                                                                        | 4(cid:20)(cid:20)                                        |     |
(cid:4)
(cid:4) (cid:4)
(cid:4)
(cid:4) (cid:4)
|     |     |     |     | (cid:14)(cid:14) | (cid:4) |     | (cid:14)(cid:14) |     |     |
| --- | --- | --- | --- | ---------------- | ------- | --- | ---------------- | --- | --- |
(cid:26)(cid:26)
|     |     |     | (a):                                                             | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9)    | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5)                                | (b):                                                             | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9)   | (cid:15)(cid:15)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5)                |     |
| --- | --- | --- | ---------------------------------------------------------------- | ----------------------------------------------------------- | --------------------------------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------- | --------------------------------------------------------------------------------------- | --- |
|     |     |     |                                                                  | 2                                                           | 3                                                                                       |                                                                  | 2                                                          | 3                                                                                       |     |
|     |     |     | (cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25) | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9)    | (cid:15)(cid:15) (cid:5)(cid:5)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) | (cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25) | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9)   | (cid:5)(cid:5) (cid:15)(cid:15)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) |     |
|     |     |     | qr(cid:3)(cid:3)(cid:3)(cid:3)(cid:3)(cid:3)(cid:3)              | 1 (cid:18)(cid:18)(cid:4)                                   | 4                                                                                       | qr                                                               | 1 (cid:18)(cid:18)(cid:4)                                  | 4                                                                                       |     |
|     |     |     |                                                                  |                                                             | (cid:4) (cid:4)                                                                         |                                                                  | (cid:4) (cid:4)                                            |                                                                                         |     |
|     |     |     |                                                                  |                                                             | (cid:4)                                                                                 |                                                                  |                                                            | (cid:4)                                                                                 |     |
|     |     |     |                                                                  | (cid:3) (cid:3)                                             | (cid:4) (cid:4)                                                                         |                                                                  |                                                            | (cid:4) (cid:4)                                                                         |     |
|     |     |     |                                                                  | (cid:3)                                                     | (cid:3) (cid:4)                                                                         |                                                                  |                                                            | (cid:4)                                                                                 |     |
|     |     |     |                                                                  |                                                             | (cid:3) (cid:3) (cid:4) (cid:4)                                                         |                                                                  |                                                            | (cid:4) (cid:4)                                                                         |     |
|     |     |     |                                                                  | (cid:14)(cid:14)                                            | (cid:3) (cid:3) (cid:17)(cid:17)(cid:6)(cid:2)(cid:17)(cid:17)(cid:7)(cid:3)            |                                                                  | (cid:14)(cid:14)                                           | (cid:17)(cid:17)(cid:6)(cid:2)(cid:7)(cid:3) (cid:14)(cid:14)                           |     |
|     |     |     |                                                                  | (cid:2)(cid:6) (cid:3)(cid:7) (cid:4)(cid:8) (cid:5)(cid:9) |                                                                                         | (cid:8)(cid:4)(cid:9)(cid:5)                                     | (cid:2)(cid:6)(cid:3)(cid:7) (cid:4)(cid:8) (cid:5)(cid:9) | (cid:8)(cid:4) (cid:9)(cid:5)                                                           |     |
|     |     |     | (c):                                                             | 2(cid:19)(cid:19)                                           | 3                                                                                       | (d):                                                             | 2(cid:19)(cid:19)                                          | 3                                                                                       |     |
Fig. 7.1. Interaction topologies among five rigid bodies where Figs. 7.1a and 7.1b
correspond to the leader-following approach and Figs. 7.1c and 7.1d correspond to
| control | law | (7.5) |     |     |     |     |     |     |     |
| ------- | --- | ----- | --- | --- | --- | --- | --- | --- | --- |
(cid:2)
Suppose that rigid body n+1 is the (virtual) team leader with σ =
n+1
(cid:2)
σr ∈R3 andω =ωr ∈R3,whereσr andωr are,respectively,thereference
n+1
attitude and angular velocity of the team. Suppose that σr, σ˙r, and σ¨r are
bounded. We assume that there is only one interaction topology associated
|      |         |       |         |     |        | G   | =(V (cid:2) | ,E         |     |
| ---- | ------- | ----- | ------- | --- | ------ | --- | ----------- | ---------- | --- |
| with | the n+1 | rigid | bodies. | We  | simply | use |             | ) to model | the |
|      |         |       |         |     |        | n+1 | n+1         | n+1        |     |
interaction topology among the n+1 rigid bodies as in Chapter 3. Similarly,
| A     |            |           |           |          |            |            | G                |       |       |
| ----- | ---------- | --------- | --------- | -------- | ---------- | ---------- | ---------------- | ----- | ----- |
| n+1   | is the     | adjacency |           | matrix   | associated | with       | n+1 .            |       |       |
|       | We propose |           | a control | torque   | for        | (D.5) as   |                  |       |       |
|       |            | τ =FT(σ   |           | )[H ∗ (σ | )(σ¨d−Λ    | σ˜˙ )+C    | ∗ (σ ,σ˙ )(σ˙d−Λ | σ˜ )  |       |
|       |            | i         |           | i i      | i i        | i i        | i i i            | i i i |       |
|       |            |           | −K (σ˜˙   |          |            |            |                  |       |       |
|       |            |           | i         | i +Λ i   | σ˜ i )],   | i=1,...,n, |                  |       | (7.8) |
| where |            |           |           |          | (cid:7)    |            |                  |       |       |
n
|     |     |     |     |            |             | a σ +a      | σr  |     |       |
| --- | --- | --- | --- | ---------- | ----------- | ----------- | --- | --- | ----- |
|     |     |     |     | σd (cid:2) | (cid:7) j=1 | ij j i(n+1) |     |     |       |
|     |     |     |     | =          | n           |             | ,   |     | (7.9) |
|     |     |     |     | i          |             | a +a        |     |     |       |
|     |     |     |     |            | j=1         | ij i(n+1)   |     |     |       |
∈R(n+1)×(n+1)
| a   | isthe | (i,j)entryoftheadjacencymatrixA |     |     |     |     |     | associated |     |
| --- | ----- | ------------------------------- | --- | --- | --- | --- | --- | ---------- | --- |
| ij  |       |                                 |     |     |     |     | n+1 |            |     |
(cid:2)
with G , σ˜ = σ −σd, and Λ and K are symmetrical positive-definite
|     | n+1 | i   | i   | i   | i   | i   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
matrices.
Remark 7.10. Note that in contrast to traditional trajectory tracking control
laws for a single robotic manipulator (e.g., [218]), σd defined by (7.9) is not
i
an external desired state but depends on the attitudes of each rigid body’s
neighbors. Also note that each rigid body’s control torque depends on its
neighbors’attitudes and their first- andsecond-orderderivatives.In practical
implementation, the second-order derivatives of the neighbors’ attitudes can
| be  | calculated | by  | numerical | differentiation. |     | (cid:13)(cid:14) |     |     |     |
| --- | ---------- | --- | --------- | ---------------- | --- | ---------------- | --- | --- | --- |

7.2 Reference AttitudeTracking 149
Theorem 7.11.With (7.8), if directed graph G has a directed spanning
n+1
tree, then σ (t)→σr(t) and σ˙ (t)→σ˙r(t), i=1,...,n, as t→∞.
i i
(cid:7)
Proof: Notethatσd definedby(7.9)hasadenominator n a +a .As
i (cid:7) j=1 ij i(n+1)
intheproofofTheorem3.8,weknowthat n a +a (cid:6)=0,i=1,...,n,
j=1 ij i(n+1)
if G has a directed spanning tree.
n+1
Also note that with (7.8), σ¨ exists on both sides of (D.5). Next, we show
i
that under the assumption of the theorem, there is a unique solution for σ¨ .
i
With (7.8), (D.5) can be written as
H ∗ (σ )(σ¨˜ +Λ σ˜˙ )+C ∗ (σ ,σ˙ )(σ˜˙ +Λ σ˜ )+K (σ˜˙ +Λ σ˜ )=0, i=1,...,n.
i i i i i i i i i i i i i i i
(cid:7) (7.10)
Multiplying n a +a on both sides of (7.10) gives
i=1 ij i(n+1)
H ∗ (σ )(σ¨ˆ +Λ σˆ˙ )+C ∗ (σ ,σ˙ )(σˆ˙ +Λ σˆ )+K (σˆ˙ +Λ σˆ )=0, i=1,...,n,
i i i i i i i i i i i i i i i
(7.11)
(cid:7) (cid:7)
where σˆ = (cid:2) [ n a + a ]σ˜ = n a (σ − σ )+ a (σ −σr).
i i=1 ij i(n+1) i i=1 ij i j i(n+1) i
(cid:2)
Letting σˆ =[σˆT,...,σˆT]T, then
1 n
σˆ =(M ⊗I )σ+(b⊗I )σr, (7.12)
3 3
where σ = [σT,...,σT]T, M = [m ] ∈ Rn×n with m = −a and m =
(cid:7) 1 n ij ij ij ii
n+1 a , and b = [−a ,...,−a ]T ∈ Rn. Equation (7.11) can
j=1,j(cid:5)=i ij 1(n+1) n(n+1)
be written in matrix form as
H ∗ (σ)(σ¨ˆ +Λσˆ˙)+C ∗ (σ,σ˙)(σˆ˙ +Λσˆ)+K(σˆ˙ +Λσˆ)=0, (7.13)
where H∗(σ)=diag[H∗(σ ),...,H∗(σ )],
1 1 n n
∗ ∗ ∗
C (σ,σ˙)=diag[C (σ ,σ˙ ),...,C (σ ,σ˙ )],
1 1 1 n n n
Λ = diag(Λ ,...,Λ ), and K = diag(K ,...,K ). Thus according to (7.12)
1 n 1 n
and(7.13),thereisauniquesolutionforσ¨ ifH∗(σ)andM⊗I areinvertible.
3
Note that H∗(σ) is invertible because all H∗(σ ) are symmetrical positive
i i
definite. Also note that M is invertible under the assumptionof the theorem,
according to the proof of Theorem 3.8.
Consider the Lyapunov function candidate
(cid:2)n
1
V = sTH ∗ (σ )s ,
2 i i i i
i=1
where s = (cid:2) σˆ˙ +Λ σˆ . Differentiating V gives
i i i i
(cid:2)n
V˙ =− sTK s <0,
i i i
i=1

150 7 Relative AttitudeMaintenance and Reference AttitudeTracking
| where we have | used | the  | fact that  | (7.11) can    | be written | as  |     |        |
| ------------- | ---- | ---- | ---------- | ------------- | ---------- | --- | --- | ------ |
|               |      | ∗    |            | ∗             |            |     |     |        |
|               |      | H (σ | i )s˙ i +C | (σ i ,σ˙ i )s | i +K i s i | =0  |     | (7.14) |
|               |      | i    |            | i             |            |     |     |        |
and H∗(σ ) − 2C∗(σ ,σ˙ ) is skew symmetrical. It thus follows that V is
| i i |     | i i | i   |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
bounded, which in turn implies that all s , i = 1,...,n, are bounded. As
i
a result, it follows that all σ and σ˙ , i = 1,...,n, are bounded because σr
|     |     |     | i   | i   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
σ˙r
| and are | bounded. |     |     |     |     |     |     |     |
| ------- | -------- | --- | --- | --- | --- | --- | --- | --- |
Note that (7.14) implies that all s˙ , i = 1,...,n, are bounded by noting
|             |                                     |     |     | i   |     |     | (cid:7) |           |
| ----------- | ----------------------------------- | --- | --- | --- | --- | --- | ------- | --------- |
| thatallH∗−1 | ),i=1,...,n,arebounded.NotingthatV¨ |     |     |     |     |     | =−2     | n sTK     |
|             | (σ                                  |     |     |     |     |     |         | s˙ ,      |
| i           | i                                   |     |     |     |     |     |         | i=1 i i i |
itfollowsthatV¨ isbounded,whichinturnimpliesthatV˙ isuniformlycontin-
|                |     |         |         | V˙(t)→0, |       |         |      | (t)→0, |
| -------------- | --- | ------- | ------- | -------- | ----- | ------- | ---- | ------ |
| uous. By Lemma |     | F.6, it | follows | that     | which | implies | that | s˙     |
i
i = 1,...,n, as t → ∞. Then it follows that σˆ (t) → 0 and σˆ˙ (t) → 0, as
|                                          |     |     |     |     | i   |            | i   |          |
| ---------------------------------------- | --- | --- | --- | --- | --- | ---------- | --- | -------- |
| t→∞,whichinturnimpliesfrom(7.12)that(M⊗I |     |     |     |     |     | )σ(t)+(b⊗I |     | )σr(t)→0 |
|                                          |     |     |     |     |     | 3          | 3   |          |
and (M⊗I )σ˙(t)+(b⊗I )σ˙r(t)→0, as t→∞. Then by following the proof
|     | 3   |     | 3   |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
of Theorem 3.15, we know that σ (t) → σr(t) and σ˙ (t) → σ˙r(t), as t → ∞,
|                      |     |         |              | i   |     | i   |     |     |
| -------------------- | --- | ------- | ------------ | --- | --- | --- | --- | --- |
| under the assumption |     | of      | the theorem. |     |     |     |     |     |
| 7.3 Simulation       |     | Results |              |     |     |     |     |     |
In this section, we first apply control law (7.5) to guarantee that six rigid
qr(t)
bodies follow their team leader with a time-varying reference attitude
andangularvelocityωr(t).We thenapplycontrollaw (7.8)toguaranteethat
sixrigidbodiesfollowtheirteamleaderwithatime-varyingreferenceattitude
| σr(t)       |     |          | ωr(t). |     |     |     |     |     |
| ----------- | --- | -------- | ------ | --- | --- | --- | --- | --- |
| and angular |     | velocity |        |     |     |     |     |     |
The rigid body specifications are chosento be same as in Table 6.1. With
control law (7.5), we let k = 1 and K = 2I . Also let τr = [0,0,0]T,
|     |     |     | qi  | ωi  | 3   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Jr = diag(1,2,1), qr(0) = [0,0,0,1]T, and ωr(0) = [0.1,0.3,0.5]T in (7.3).
We choose q (0) and ω (0) randomly. With control law (7.8), we let Λ = I ,
|     | i   | i   |     |     |     |     |     | i 3 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
∈ E
K i = 2I 3 , and a ij = 1 if (j,i) n+1 in (7.9). Suppose that the reference
attitude σr, reference angular velocity ωr = F−1(σr)σ˙r, reference torque τr,
andreferenceinertiaJr satisfy (D.4),whereτr =[0,0,0]T,Jr =diag(1,2,1),
σr(0) = [0,0,0]T, and ωr(0) = [0.1,0.3,0.5]T. We choose σ (0) and ω (0)
|     |     |     |     |     |     |     | i   | i   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
randomly. In the following, a superscript (j) denotes the jth component of a
| quaternion | or vector. |     |     |     |     |     |     |     |
| ---------- | ---------- | --- | --- | --- | --- | --- | --- | --- |
The directed graph G used in (7.5) is shown in Fig. 7.2, where node qr
7
denotes the team leader. Note that the directed graph can be simplified to a
graph with only one node using the approach described in Remark 7.8.
Figures7.3and7.4show,respectively,theattitudesandangularvelocities
of rigid bodies 1, 3, and 5 with (7.5) as well as their references. Note that
the attitudes and angular velocities of each rigid body converge to their ref-
erence values.Figure 7.5 shows the controltorques of rigid bodies 1, 3, and 5
with (7.5).
DirectedgraphG usedin(7.8)isshowninFig.7.6,wherenodeσr denotes
7
the team leader. In contrast to the directed graph shown in Fig. 7.2, the

|     |     |                                                                  |                                                                          |                                                                          | 7.3 Simulation Results 151                                               |
| --- | --- | ---------------------------------------------------------------- | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
|     |     | (cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25) | (cid:15)(cid:15)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) | (cid:15)(cid:15)(cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) | (cid:15)(cid:15)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) |
|     |     | qr                                                               | 1(cid:20)(cid:20)                                                        | 2                                                                        | 3                                                                        |
|     |     |                                                                  |                                                                          | (cid:14)(cid:14)                                                         | (cid:14)(cid:14)                                                         |
|     |     |                                                                  | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5)(cid:2)(cid:2)   | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9)(cid:2)(cid:2)   | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5)                 |
|     |     |                                                                  | 4                                                                        | 5                                                                        | 6                                                                        |
|     |     | Fig. 7.2.                                                        | Directed                                                                 | graph G 7 used                                                           | in (7.5)                                                                 |
1
j=1
j=3
0.5 j=5
)1(q Reference
j 0
−0.5
−1
|     | 0   | 2 4 6 | 8 10 | 12 14 | 16 18 20 |
| --- | --- | ----- | ---- | ----- | -------- |
Time (s)
1
j=1
j=3
0.5 j=5
)2(q Reference
j 0
−0.5
−1
|     | 0   | 2 4 6 | 8 10 | 12 14 | 16 18 20 |
| --- | --- | ----- | ---- | ----- | -------- |
Time (s)
1
j=1
j=3
0.5
j=5
)3(q Reference
j 0
−0.5
−1
|     | 0   | 2 4 6 | 8 10 | 12 14 | 16 18 20 |
| --- | --- | ----- | ---- | ----- | -------- |
Time (s)
|     |     | Fig. 7.3. | Rigid body | attitudeswith | (7.5) |
| --- | --- | --------- | ---------- | ------------- | ----- |
directed graph shown in Fig. 7.6 cannot be simplified to a graph with only
one node using the approachdescribed in Remark 7.8. However,node σr has
| a directed | path | to all followers | in Fig. | 7.6. |     |
| ---------- | ---- | ---------------- | ------- | ---- | --- |
Figures7.7and7.8show,respectively,theattitudesandangularvelocities
of rigid bodies 1, 3, and 5 with (7.8) as well as their references. Note that
the attitudes and angular velocities track their reference values even if the
directed graph shown in Fig. 7.6 cannot be simplified to a graph with only
one node. Figure 7.9 shows the control torques of rigid bodies 1, 3, and 5
with (7.8).

152 7 Relative AttitudeMaintenance and Reference AttitudeTracking
1
0.5
0
−0.5
−1
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)s/dar(
)1(ω
j
j=1
j=3
j=5
Reference
0.6
0.4
0.2
0
−0.2
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)s/dar(
)2(ω
j
j=1
j=3
j=5
Reference
1
0.5
0
−0.5
−1
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)s/dar(
)3(ω
j
j=1
j=3
j=5
Reference
Fig. 7.4. Rigid body angular velocities with (7.5)
7.4 Notes
The results in this chapter are based mainly on [176–179,184]. Control
law (7.8) can be applied to robotic manipulators for position synchroniza-
tion. See [201] for mutual synchronization of robotic manipulators.
Acknowledgment is given to
(cid:10)c2006 John Wiley & Sons. Reprinted, with permission, from Wei Ren,
“Distributedattitudealignmentinspacecraftformationflying,”International
Journal of Adaptive Control and Signal Processing, vol. 21, no. 2–3, pp. 95–
113, March–April 2007.
(cid:10)c2007 IEEE. Reprinted, with permission, from Wei Ren, “Synchronized
multiple spacecraftrotations: A revisit in the context of consensus building,”
Proceedings of the American Control Conference, pp. 3174–3179, New York
City, 2007.
(cid:10)c2007IEEE.Reprinted,withpermission,fromWeiRen,“Distributedat-
titudesynchronizationformultiplerigidbodieswithEuler-Lagrangeequations
ofmotion,”ProceedingsoftheIEEEConferenceonDecisionandControl,New
Orleans, LA, 2007 (to appear).
(cid:10)c2007 IEEE. Reprinted, with permission, from Wei Ren, “Distributed
cooperative attitude synchronization and tracking for multiple rigid bodies,”
IEEE Transactions on Control Systems Technology, 2007 (under review).

7.4 Notes 153
0.5
j=1
j=3
)mN( )1(τ 0 j=5
j −0.5
−1
| 0   | 2 4 | 6 8 | 10  | 12  | 14 16 | 18 20 |
| --- | --- | --- | --- | --- | ----- | ----- |
Time (s)
1
j=1
j=3
0.5
)mN( )2(τ j=5
0
j
−0.5
−1
| 0   | 2 4 | 6 8 | 10  | 12  | 14 16 | 18 20 |
| --- | --- | --- | --- | --- | ----- | ----- |
Time (s)
1
j=1
0.5 j=3
)mN( )3(τ j=5
0
j
−0.5
−1
| 0   | 2 4 | 6 8 | 10  | 12  | 14 16 | 18 20 |
| --- | --- | --- | --- | --- | ----- | ----- |
Time (s)
|     | Fig. 7.5. | Rigid body | control | torques | with | (7.5) |
| --- | --------- | ---------- | ------- | ------- | ---- | ----- |
(cid:17)(cid:17)(cid:2)(cid:6)(cid:3)(cid:7)
|     |      | (cid:18)(cid:22)(cid:19)(cid:23) σ (cid:20)(cid:24) r (cid:21)(cid:25) | (cid:15)(cid:15)(cid:2)(cid:6)(cid:3)(cid:7) (cid:4)(cid:8) (cid:5)(cid:9) | (cid:15)(cid:15)(cid:6)(cid:2)(cid:7)(cid:3) (cid:8)(cid:4)(cid:9)(cid:5) (cid:19)(cid:19) | (cid:4)(cid:8)(cid:5)(cid:9)                              |     |
| --- | ---- | ---------------------------------------------------------------------- | -------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ | --------------------------------------------------------- | --- |
|     |      |                                                                        | 1 (cid:20)(cid:20)                                                         | (cid:28)(cid:28)2                                                                          | 3                                                         |     |
|     |      |                                                                        |                                                                            | (cid:17)(cid:17)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4) (cid:27)(cid:27)                | (cid:14)(cid:14)                                          |     |
|     |      |                                                                        | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) (cid:19)(cid:19)  | (cid:9)(cid:5)(cid:2)(cid:2)                                                               | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8) (cid:5)(cid:9) |     |
|     |      |                                                                        | 4                                                                          | 5                                                                                          | 6                                                         |     |
|     | Fig. | 7.6. Directed                                                          | graph                                                                      | G used                                                                                     | in (7.8)                                                  |     |
7

154 7 Relative AttitudeMaintenance and Reference AttitudeTracking
1
0
−1
−2
−3
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)1(σ j
j=1
j=3
j=5
Reference
2
0
−2
−4
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)2(σ
j
j=1
j=3
j=5
Reference
2
1
0
−1
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)3(σ
j
j=1
j=3
j=5
Reference
Fig. 7.7. Rigid body attitudeswith (7.8)
2
1
0
−1
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)s/dar(
)1(ω j
j=1
j=3
j=5
Reference
4
2
0
−2
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)s/dar(
)2(ω j
j=1
j=3
j=5
Reference
2
1
0
−1
−2
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)s/dar(
)3(ω
j
j=1
j=3
j=5
Reference
Fig. 7.8. Rigid body angular velocities with (7.8)

7.4 Notes 155
2
1
0
−1
−2
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)mN(
)1(τ
j
j=1
j=3
j=5
2
1
0
−1
−2
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)mN(
)2(τ
j
j=1
j=3
j=5
2
1
0
−1
−2
0 2 4 6 8 10 12 14 16 18 20
Time (s)
)mN(
)3(τ
j
j=1
j=3
j=5
Fig. 7.9. Rigid body control torques with (7.8)

Part V
| Consensus-based |              | Design | Methodologies | for     |
| --------------- | ------------ | ------ | ------------- | ------- |
| Distributed     | Multivehicle |        | Cooperative   | Control |

8
Consensus-based Design Methodologies for
Distributed Multivehicle Cooperative Control
Contributed partly by Tim McLain
This chapter introduces a few design methodologies for distributed multi-
vehicle cooperative control based on consensus algorithms. Our approach to
distributed multivehicle cooperative control problems can be summarized in
four steps: (1) the definition of a cooperation constraint and cooperation ob-
jective; (2) the definition of a coordination variable as the minimal amount
of information needed to effect cooperation; (3) the design of a centralized
cooperation strategy; and (4) the use of consensus algorithms to transform
the centralized strategy into a distributed strategy. In addition, we overview
research in formation control and UAV cooperation.
8.1 Introduction
Groupcooperativebehaviorimpliesthatindividualsinthegroupshareacom-
monobjectiveandactaccordingtothemutualinterestofthegroup.Effective
cooperation often requires that individuals coordinate their actions. Coordi-
nation can take many forms ranging from staying out of each other’s way to
directly assisting another individual. In general, group cooperation is facil-
itated by coordinating the actions of individuals. However, each individual
may not necessarily need to coordinate directly with every other individual
in the group to effect group cooperative behavior. For example, fish engaged
in schooling behavior react only to other fish that are close physically. We
will term this type of coordination local coordination. At the other extreme
is global coordination, where an individual coordinates its action with every
other individualin the group.Due to communicationconstraintsandcompu-
tationalfeasibility,weareinterestedprimarilyingroupcooperationproblems
where the coordinationoccurslocally.One ofthe interestingchallengesinco-
operativecontrolistodesigncoordinationstrategiessothatlocalcoordination
will result in group cooperation.
Althoughthere have been numerous publications detailing specializedap-
proaches to cooperation problems, general design methodologies are only be-

160 8 Consensus-based Design Methodologies for Cooperative Control
ginning to emerge.For the most part,these methodologiesassume a groupof
homogeneous robots with local coordination. The objective of this chapter is
todescribeadesignapproachthatwehavesuccessfullyappliedtoavarietyof
cooperationproblems.Ourapproachallowsarangeofcoordinationstrategies
from local to global coordination. We do not claim that our approach will
be appropriate for all cooperation problems. We expect that it will be many
more years before the general principles underlying cooperative systems will
be fully understood.However,we hope that our approachcontributes toward
that goal.
The essence of our approach is explained in the following steps:
Step 1. Cooperation Objective and Constraints. The first step is to
define the cooperation objective analytically. Cooperation can often be
identified when certain relationshipsbetween state variablesare satisfied.
These relationships are called cooperation constraints.
Step 2. CoordinationVariable and CoordinationFunction.Thenext
step is to identify the essential information that each vehicle must know
to coordinate with the team. This information is called the coordination
variable as mentioned in Chapter 1. Often, cooperation can be achieved
through a variety of individual actions. To facilitate the selection of the
individual actions that best contribute to the cooperation objective, we
quantifytherelationshipbetweenthe coordinationvariableandthe coop-
eration objective and call this function the coordination function.
Step 3. Centralized Cooperation Scheme. The next step is to derive a
cooperationstrategyforminimizingtheteamobjectivefunctionassuming
that each member of the team has global knowledge of the coordination
variable and the coordination functions of each member of the team.
Step 4. Consensus Building. In a distributed situation where communi-
cation links are noisy and not persistent and where the communication
topology is dynamically changing and is unknown to each team member,
thecentralizedsolutionwillfail.Thefinalstepofourapproachistoimple-
ment a consensus algorithm that ensures that each member of the team
has consistent coordination information despite the inadequacies of the
communication network.
In this chapter, we describe our approach to cooperative control which is
basedontwomainideas.The firstis the notionofcoordinationvariablesand
coordinationfunctions, whichwereintroduced in[138,139].The coordination
variable is the minimum amount of information that needs to be exchanged
between two vehicles to effect coordination. Although it is known by dif-
ferent names, the notion of a coordination variable is found in many other
works on cooperative control. For example, [101,102] introduce an “action
reference” which, if known by each vehicle, facilitates formation keeping. In
leader-followingapplications [214,244],the states of the leader constitute the
coordinationvariablebecausetheactionsoftheothervehiclesintheformation
arecompletelyspecifiedoncetheleaderstatesareknown.In[22,116,121,123],

8.2 Coupling in Cooperative Control Problems 161
the notion of a virtual structure is used to derive formation control strate-
gies. The motion of each vehicle is causally dependent on the dynamic states
of the virtual structure; therefore, the states of the virtual structure are the
coordination variable. In [225], a team of autonomous underwater vehicles
(AUVs) is controlledto “swarm”arounda desiredmean locationof the team
with a specified standard deviation. The action of each vehicle is dependent
on the location of its nearest neighbor and on the desired mean and stan-
dard deviation. This information is the coordination variable. Coordination
variables may also be discrete. For example, in [27,199], cooperative task al-
location is addressed. Individual vehicle behavior is dependent on the task
allocation vector which becomes the coordination variable. Similarly, in [63],
the coordination variable is the dynamic role assignment in a robot soccer
scenario.
The second main idea in our approach to cooperative control is the no-
tionofconsensus-seeking.Becausecoordinationmayberequiredbetweentwo
vehicles that do not communicate directly, distributed consensus algorithms
introduced in Chapters 2–7 are required to ensure that the vehicles share
similar coordination variables.
8.2 Coupling in Cooperative Control Problems
Oneoftheprimarychallengesindevelopinggeneralizedstrategiesforcoopera-
tivecontrolistheidentificationofbroadclassesofproblemsthatareamenable
to well-defined, straightforward approaches. One way to classify cooperative
control problems is by the level and type of coupling involved. For example,
flying a UAV in the wake of another UAV to minimize the induced drag re-
quirestightphysicalcouplingamongtheUAVs.Ontheotherhand,ateamof
UAVs tasked to search a particular region cooperatively is coupled primarily
throughthecooperationalgorithmsemployedbytheindividualUAVs.Webe-
lieve that our approachis well suited to algorithmicallycoupled problems.In
this section, we describe different types of coupling that occur in cooperative
control problems.
With respect to the cooperative control of multivehicle systems, the de-
gree and form of the coupling among the vehicles composing the system is of
paramountimportance tothe nature andlevelofthe cooperationthatcanbe
achieved. Cooperation implies some degree of coupling, if only through the
cooperationobjectiveorconstraintsinvolved.Generallyspeaking,thegreater
the degree of the coupling, the more challenging it is to formulate effective
cooperative solutions.
Cooperative control problems can typically be formulated with a cooper-
ation objective or cooperation constraints or both. A cooperation objective
is typically optimized to increase the level of cooperation. Cooperation con-
straints, when satisfied, can be used to define the occurrence of cooperation.

162 8 Consensus-based Design Methodologies for Cooperative Control
8.2.1 Objective Coupling
Objective coupling describes the least restrictive form of coupling. It occurs
when a vehicle’s decisions affect only its costs and outcomes and do not in-
fluence another vehicle’scostsandoutcomes directly.Eachvehicle’sdecisions
affectsthecooperationobjectiveandthefeasibilityofcooperationconstraints.
Objective coupling requires vehicles to coordinate to ensure that constraints
aresatisfiedandthattheobjectiveisoptimized.Anexampleofobjectivecou-
plingisthe UAVcooperativetimingproblemdescribedin[139].Supposethat
two vehicles are to navigate independently through a threat field with the
objective of simultaneously flying over a prescribed destination. The cooper-
ation constraint requires the vehicles to arrive at the same instant, although
the cooperation objective might be to minimize the collective power required
for the mission. The trajectory taken by one vehicle (its decisions) does not
affect the trajectorytaken by the other vehicle directly, but it does affect the
othervehiclethroughthecooperationconstraintandobjective.Asthisexam-
ple illustrates, some degree of coupling is necessary for cooperation to occur,
but the coupling is strictly through the mission objective.
8.2.2 Local Coupling
Local coupling describes a more restrictive type of coupling in cooperative
systems. As with objective coupling, each vehicle’s decisions influence the
cooperation objective and the feasibility of cooperation constraints. Under
localcoupling,however,a vehicle’s decisionsaffect notonly its owncosts and
outcomes, but also the decisions (and hence the costs and outcomes) of its
local neighbors. A simple example of local or nearest neighbor coupling is
shownin the cooperativesearchproblemdescribedin [18],wheren UAVs are
assigned the task of cooperatively searching an area of interest. To provide
some structure to the search task, the vehicles are required to maintain a
loose row formation.To avoidcollisions,the UAVs arenot allowedto overlap
laterally.Tomaintaincommunication,thelateralspacingofthevehiclesmust
bekeptlessthanthecommunicationrange.Thelateralspacingconstraintscan
be viewed as cooperationconstraints.The cooperationobjective is to visit as
manytargetsaspossible.Thedecisionbyonevehicletoalteritstrajectoryto
visitasequenceoftargetswilldirectlyaffectthedecisionsofitsneighborsand
the costsandbenefits oftheir decisions.The keydifference betweenobjective
coupling andlocalcoupling is that for objective coupling the costaccruedfor
any vehicle is a function only of that vehicle’s decisions. For local coupling,
the cost accrued for any vehicle is a function of its own decisions as well as
the decisions of its local neighbors.
8.2.3 Full Coupling
Fully coupled systems involve vehicles whose decisions affect the costs and
outcomes of all other members of the team, and thus their decisions, i.e.,

8.3 Approach with an Optimization Objective 163
what a single vehicle chooses to do is influenced by whatall other vehicles on
the team are doing. Coupling exists through the cooperation objective and
cooperationconstraintasbefore,butinthismostrestrictiveformofcoupling,
the decisions of the individual vehicles are coupled directly. An example of
full coupling is the wide area search munition problem described in [209]. In
this problem, a team of autonomous flying munitions is tasked to search a
region and identify potential targets. Once a target is identified, it must be
classified by multiple passes over the target using one or more munitions.
Upon identification and verification, the target is attacked removing one of
the munitions from the team. The target must then be revisited for battle
damageassessment.Iftheminimumturningradiusofthemunitionislargein
relation to the search area, then each of these tasks will likely be performed
by a different vehicle. The coupling in this scenario is complex and requires
that each member of the team knows the intentions and flight paths of all
other members of the team.
8.2.4 Dynamic Coupling
When vehicles are coupled through physical interactions, we call it dynamic
coupling. The coupling in these systems can be either local or full coupling.
For example, in close-formation flight of aircraft, the aerodynamic coupling
that exists is local in that it affects those aircraft in the immediate wake of
a leading aircraft. Those aircraft on the outer edges of the formation are not
affected by those in the center of the formation.
Although the physics of dynamic coupling can be quite complex, there is
onesignificantadvantagewhentheactionsofonevehiclearecaptureddirectly
in the equations of motion describing other vehicles. These systems can be
treated as one large system by combining their equations of motion. In this
way,theselargesystemsareamenabletocontroltheoreticalapproaches.With
one model to characterize the behavior and interaction of multiple vehicles,
conventionalsingle-vehicleapproachescan be applied to achieve cooperation.
8.3 Approach to Distributed Cooperative Control
Problems with an Optimization Objective
In this section, we give an overview of our approach to cooperative con-
trol problems with an optimization objective and illustrate it with a simple
example. The approach has been applied to problems with objective cou-
pling[110,139],loosecoupling[18],anddynamiccoupling[188].Wewillillus-
trate the main ideas through the use of a simple academic example.
Example 8.1. Supposethatfiveairvehiclesareassignedvirtuallanes,asshown
in Fig. 8.1. Assume that the lateral positions of the vehicles are maintained
inside the lanesbyanonboardautopilotandthatthe longitudinalpositiony
i

164 8 Consensus-based Design Methodologies for Cooperative Control
ofeachvehicleis governedby the dynamicsy˙ =u .Assume thatthe vehicles
i i
are initially at different longitudinal positions in the lane. The cooperation
goal is to maneuver the vehicles so that they proceed along a uniform front
at a constant known ground speed v, as shown in Fig. 8.1. (cid:13)(cid:14)
Fig. 8.1. A team of air vehicles is tasked to proceed along a uniform front at a
| constant | ground speed |             |                |     |
| -------- | ------------ | ----------- | -------------- | --- |
| 8.3.1    | Cooperation  | Constraints | and Objectives |     |
Thefirststepinourapproachistoidentifyandquantifythecooperationcon-
straint and the cooperationobjective. The cooperation constraintis a formal
definitionoftheteamgoalandindicatesexactconditionswhencooperationis
achieved.Moreprecisely,ifx is the situationalstate ofthe ithvehicle andu
|     |     | i   |     | i   |
| --- | --- | --- | --- | --- |
is the decision variable, then the cooperation constraint is a positive definite
mapping J (x ,u ,x ,u ,...,x ,u ) that is identically zero when co-
|     | constraint | 1 1 2 | 2 n n |     |
| --- | ---------- | ----- | ----- | --- |
operation is achieved. In Example 8.1, if n is the number of vehicles, then a
| possible | cooperation | constraint | is the mapping |     |
| -------- | ----------- | ---------- | -------------- | --- |
(cid:2)n (cid:2)n
1
|     |     | J   | = (y −y )2, | (8.1) |
| --- | --- | --- | ----------- | ----- |
constraint i j
2
i=1j=1

|     |     |     | 8.3 Approach | with an | Optimization | Objective | 165 |
| --- | --- | --- | ------------ | ------- | ------------ | --------- | --- |
which is identically zero when y =y . In Example 8.1, note that if the team
i j
is closely but not precisely aligned, then the team may still be considered
in cooperation. When J constraint < !, we say that the team has achieved !-
cooperation.
For a given world situational state X ={x ,...,x }, there may be many
|     |     |     |      | 1   | n   |     |     |
| --- | --- | --- | ---- | --- | --- | --- | --- |
|     |     |     | U {u | }   |     |     |     |
different decision variables = ,...,u that achieve !-cooperation. In
|     |     |     |     | 1 n |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
addition, there may be auxiliary objectives that we would like to minimize.
For instance, in Example 8.1, we may also want to minimize overall fuel ex-
penditure. To capturethese auxiliaryobjectives,weintroduce a positive defi-
nite function J (X,U) that quantifies these objectives.This function is
objective
called the cooperation objective [139]. In Example 8.1, a possible cooperation
objective is given by the linear quadratic regulator equation [122]
(cid:15)
(cid:2)n ∞
|     | J         | =   | q[y | (τ)−θ ∗ (τ)]2+r[u | (τ)−v]2dτ, |     |     |
| --- | --------- | --- | --- | ----------------- | ---------- | --- | --- |
|     | objective |     | i   |                   | i          |     |     |
t
i=1
where q and r are positive constants and where θ∗ is the position of the
uniform front.
| 8.3.2 | Coordination | Variables | and | Coordination | Functions |     |     |
| ----- | ------------ | --------- | --- | ------------ | --------- | --- | --- |
Thesecondstepinourapproachistodeterminetheinformationthatmustbe
shared to achieve cooperation and to organizethat into a single vector called
θ∗
the coordination variable. We will let denote the coordination variable.
The approach is to distill the essentials of the cooperation problem to a set
of parameters that, if known by every vehicle in the group, can be used to
select the decision variable so that the cooperation constraint is achieved. In
Example 8.1, if every vehicle knows the desired position of the front, then
θ∗
it can regulate its position to align with the front. Therefore, let be the
θ∗
desired position of the uniform front. In Example 8.1, we will assume that
| evolves | according | to the equation |     |     |     |     |     |
| ------- | --------- | --------------- | --- | --- | --- | --- | --- |
θ˙∗
=v.
Our method assumes that the cooperation constraint can be written as a
functionofthecoordinationvariable.NotethatforExample8.1,thecoopera-
tion constraintgivenin (8.1)canbe written as a function ofthe coordination
| variable | θ∗, as |     |                   |     |     |     |     |
| -------- | ------ | --- | ----------------- | --- | --- | --- | --- |
|          |        |     | (cid:2)n (cid:2)n |     |     |     |     |
1
|     | J          | =   |     | [(y −θ ∗ )−(y | −θ ∗ )]2 | <!. |     |
| --- | ---------- | --- | --- | ------------- | -------- | --- | --- |
|     | constraint |     |     | i             | j        |     |     |
2
i=1j=1
To facilitate minimization of the auxiliary cooperation objective subject
to the cooperation constraint, we desire to write the cooperation objective
in terms of θ∗. To this end, we assume that the cooperation objective can

166 8 Consensus-based Design Methodologies for Cooperative Control
be expressed as a convex function of myopic objective functions for each ve-
hicle. The myopic objective functions depend on the coordination variable
as well as the situational state and decision variable of the individual vehi-
cle.This myopicobjectivefunctionis the coordinationfunction[139]denoted
| J (x ,u | ,θ∗). In | Example | 8.1, |     |     |     |     |
| ------- | -------- | ------- | ---- | --- | --- | --- | --- |
| cf,i i  | i        |         |      |     |     |     |     |
(cid:2)n
|     |     |     | J objective | =   | J   | cf,i , |     |
| --- | --- | --- | ----------- | --- | --- | ------ | --- |
i=1
| where |     | (cid:15) |     |     |     |     |     |
| ----- | --- | -------- | --- | --- | --- | --- | --- |
∞
|     |     |        | (τ)−θ | ∗   | (τ)]2+r[u | (τ)−v]2dτ. |       |
| --- | --- | ------ | ----- | --- | --------- | ---------- | ----- |
|     | J   | cf,i = | q[y i |     |           | i          | (8.2) |
t
Thecoordinationfunctionparameterizestheeffectofthecoordinationvariable
ontheobjectivesofeachvehicle,i.e., thecoordinationfunctiondescribeshow
themyopicobjectiveofeachvehiclechangeswithchangesinthecoordination
variable.
Posing the cooperation problem in terms of coordination variables and
coordinationfunctions will usually reduce the dimensionality of the problem.
Example 8.1 is already a scalar problem and so the dimensionality has not
been reduced.
| 8.3.3 Centralized |     | Cooperation |     | Scheme |     |     |     |
| ----------------- | --- | ----------- | --- | ------ | --- | --- | --- |
Given the terminology introduced in the previous two sections, we can pose
the cooperation scenario as the following optimization problem:
|     |     |     | 0   |     |     | 1   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
(cid:2)n
∗
|     | θ   | =argmin | lim |     | J cf,i (θ;x | i ,u i ) | (8.3) |
| --- | --- | ------- | --- | --- | ----------- | -------- | ----- |
t→∞
i=1
(θ;X,U)<!.
|     |     |     | subject to: | lim | J constraint |     |     |
| --- | --- | --- | ----------- | --- | ------------ | --- | --- |
t→∞
Thenextstepinourapproachtocooperativecontrolisthedesignofacentral-
ized strategythatsolvesthis optimizationproblem.Centralizedstrategiesare
usually easier to design than distributed strategies.Note that the centralized
algorithmwillbe problemdependent. Inthe processofsolvingproblem(8.3),
the centralized algorithm produces a decision variable for the ith vehicle de-
noted as [139]
†
|     |     |     | u   | =f  | (θ ∗ ,x | ),  | (8.4) |
| --- | --- | --- | --- | --- | ------- | --- | ----- |
|     |     |     |     | i i | i       |     |       |
†
where we assume that f is continuous in θ∗. Equations (8.3) and (8.4) rep-
i
| resent what | we term | the | cooperation | algorithm. |     |     |     |
| ----------- | ------- | --- | ----------- | ---------- | --- | --- | --- |
ForExample8.1,the centralizedsolutionrequiresthateachvehicleknows
thepositionofthefrontθ∗(t).Accordingly,thevehiclesimplementthecontrol
law
∗−y
|     |     |     | u   | =v+k(θ |     | ),  |     |
| --- | --- | --- | --- | ------ | --- | --- | --- |
|     |     |     | i   |        |     | i   |     |

8.3 Approach with an Optimization Objective 167
(cid:25)
where k = q/r is chosen to minimize the coordination function given
in (8.2). Given that θ˙∗ = v, it is straightforward to show that this strategy
yields y (t)→θ∗(t) for each i=1,...,n, which implies that
i
lim J →0,
constraint
t→∞
i.e., the cooperation constraint is satisfied for every !. Figure 8.2 shows a
simulation plot of the centralized solution where v =0.1 and k =1.
2.5
2
1.5
1
0.5
0
0 5 10 15 20 25
Time (s)
)t(y
i
Fig. 8.2. Centralized solutionoftheexampleproblem.Theposition oftheuniform
front is transmitted to all vehicles from a centralized location.
8.3.4 Consensus Building
The final step in our approach is to use consensus algorithms to decentralize
the cooperation algorithm. Multivehicle cooperation requires communication
among vehicles. In real-world environments, the communication links will be
noisyandnonpersistent,andthecommunicationtopologywillbedynamically
changingandunknowntoeachteammember.Therefore,centralizedsolutions
are rarely feasible. The key insight is that if each vehicle instantiates the
cooperation algorithm locally, and the inputs to each local instantiation are

168 8 Consensus-based Design Methodologies for Cooperative Control
identical, then assuming that the algorithm is deterministic, it will produce
identical outputs on each vehicle. However, if the local inputs are different,
then each vehicle will compute a different instantiation of the coordination
variable which we label θ . Therefore, from (8.4), we see that the decision
i
| variable | for | the ith | vehicle | is given | by  |     |     |
| -------- | --- | ------- | ------- | -------- | --- | --- | --- |
†
|     |     |     |     | u   | =f (θ ,x | ).    |     |
| --- | --- | --- | --- | --- | -------- | ----- | --- |
|     |     |     |     |     | i i i i  |       |     |
|     | †   |     |     | †   | → † (θ∗) | → θ∗. |     |
Because f is continuous, f (θ i ) f as θ i Therefore, the ob-
|     | i   |     |     | i   | i   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
jective of the consensus algorithm is to ensure that θ → θ for every i,j.
i j
Our approach to consensus building is built on the algorithms introduced in
| Chapters | 2–7. |     |     |     |     |     |     |
| -------- | ---- | --- | --- | --- | --- | --- | --- |
Ifcommunicationnoiseispresentinthesystem,thenweneedtoguarantee
| that !-consensus |     | is  | achieved, | i.e., |     |     |     |
| ---------------- | --- | --- | --------- | ----- | --- | --- | --- |
(cid:2)
|     |     |     |     | lim | (cid:9)θ (t)−θ (t)(cid:9)<!. |     |     |
| --- | --- | --- | --- | --- | ---------------------------- | --- | --- |
|     |     |     |     |     | i j                          |     |     |
t→∞
ij
−θ
Theorems 2.14 and 2.35 show that the consensus error θ i j is ISS, which
implies that the consensus error is uniformly bounded by a gain times the
| power | in the | communication |     | noise. |     |     |     |
| ----- | ------ | ------------- | --- | ------ | --- | --- | --- |
A fundamental result in nonlinear control theory is that the cascade of
twoISSsystemsisalsoISS(seeTheoremF.10).Considerthecontroldiagram
shown in Fig. 8.3. The consensus algorithm on each vehicle is ISS from the
communication noise to the consensus error. Therefore, if the cooperation
algorithmis ISS from the consensus errorto the cooperationconstraint,then
the cascade system is ISS from the communication noise to the cooperation
constraint, implying that !-cooperation is achieved for low enough levels of
| communication |     | noise. |     |     |     |     |     |
| ------------- | --- | ------ | --- | --- | --- | --- | --- |
Theapplicationofconsensusalgorithm(2.10)toExample8.1impliesthat
each vehicle updates its coordination variable instantiation according to
(cid:2)n
|     |     |     | θ˙  | =−  | a (t)(θ −θ | )+v, |     |
| --- | --- | --- | --- | --- | ---------- | ---- | --- |
|     |     |     |     | i   | ij i       | j    |     |
j=1
|                 |         |                |          |         |             | matrixA ∈Rn×n. |     |
| --------------- | ------- | -------------- | -------- | ------- | ----------- | -------------- | --- |
| where           | a ij is | the (i,j)entry |          | of the  | adjacency   | n Eachvehicle  |     |
| then implements |         | the            | modified | control | law         |                |     |
|                 |         |                |          | †       | (cid:2)     |                |     |
|                 |         |                | u        | =f (θ   | ,y )= v+k(θ | −y ),          |     |
|                 |         |                |          | i i     | i i         | i i            |     |
where k can be chosen to minimize the modified coordination function
(cid:15)
∞
|     |     | J    | =   | q[y (τ)−θ | (τ)]2+r[u | (τ)−v]2dτ. | (8.5) |
| --- | --- | ---- | --- | --------- | --------- | ---------- | ----- |
|     |     | cf,i |     | i         | i         | i          |       |
t
| Because | the | system |     |     |     |     |     |
| ------- | --- | ------ | --- | --- | --- | --- | --- |

8.4 Approach without an Optimization Objective 169
Fig. 8.3. Cascade system where the output of the consensus building mechanism
drives the coordination algorithm which uses feedback from the vehicle to achieve
coordination. Here N denotes the set of vehicles whose coordination variable in-
i
stantiations are available to vehiclei.
d
(y −y )=−k(y −y )+k(θ −θ )
i j i j i j
dt
is ISS, we are guaranteed to achieve !-cooperation. Note that because each
vehicle tracks its own notion of the front in an optimal manner [with respect
to (8.5)], this does not imply that the overallteam has optimal performance.
In fact, centralized solutions that minimize the coordination function will
always have better performance than distributed solutions. Figure 8.4 shows
a simulationplot of the distributed solutionwhere v =0.1 and k =1 andthe
standard deviation of the noise on the communication channels is σ = 0.1.
Thefirstsubplotshowstheevolutionofthecoordinationvariables.Thesecond
subplot shows the evolution of the longitudinal position of the vehicles, and
the third subplot shows the number of unidirectional communication links
that are active in the network as a function of time. Note that updates of
θ occur only when the ith vehicle is communicating with another vehicle.
i
Despite the low levels of communication, the coordination constraint is still
satisfied.
8.4 Approach to Distributed Cooperative Control
Problems Without an Optimization Objective
Often,theprimarygoalistoeffectcooperationinateamwithoutanauxiliary
cooperation objective. In that case, there is not a cooperation objective and
the algorithms focus on satisfying the cooperation constraint. When there is

170 8 Consensus-based Design Methodologies for Cooperative Control
20
15
10
5
0
0 10 20 30 40 50 60 70 80 90 100
Time (s)
)t(θ
i
20
15
10
5
0
0 10 20 30 40 50 60 70 80 90 100
Time (s)
)t(y
i
3
2
1
0
0 10 20 30 40 50 60 70 80 90 100
Time (s)
sknil
mmoc
fo
#
Fig. 8.4. DistributedsolutionofExample8.1.Aconsensusalgorithmisusedtone-
gotiateacommonposition oftheuniformfrontdespitelowlevelsofcommunication
among vehicles.
no need to minimize the cooperationobjective, we can simplify the approach
described in Section 8.3. The approach that we adopt in this case is first to
identify thecoordinationvariableandthentoapplytheconsensusalgorithms
to ensurethat teammembers haveaconsistentview ofthe coordinationvari-
able or to incorporate group behavior or dynamics even in the presence of
limited/unreliable intervehicle information exchange. Two cases will be con-
sidered.
8.4.1 Coordination Variable Constituted by a Group-level
Reference State
In this subsection, we consider the case where there exists an identifiable
group-level reference state for each individual vehicle on the team. Here the
group-level reference state constitutes the coordination variable. The group-
level reference state serves as a basis for each vehicle to derive local control
strategies.Asaresult,havingtheknowledgeofthegroup-levelreferencestate
facilitatescooperationforthewholeteam.Forexample,incooperativetiming
missions,the estimated teamarrivaltime atspecified destinations servesas a

8.4 Approach without an Optimization Objective 171
group-levelreferenceforeachvehiclebecausethemotionofeachvehiclecanbe
adjustedaccordingtotheestimatedteamarrivaltime.Inleader-followingfor-
mationflyingapplications,thestateofanactualorvirtualteamleaderserves
asagroup-levelreferenceforeachvehiclebecausetheactionsofothervehicles
in the formation are completely specified once the leader state is known. In
cooperative monitoring applications, it is often desirable that multiple UAVs
are evenly distributed around the perimeter of a boundary (e.g., a growing
forest fire) to monitor and track the perimeter as it evolves, where the equal
length of coverage serves as a group-level reference for each UAV.
Weletξ denotethe group-levelreferencestate(i.e., thecoordinationvari-
able). Let x , y , and u represent, respectively, the local state, output, and
i i i
controlinput of the ith vehicle. Suppose that the dynamics of the ith vehicle
are
x˙ =g (t,x ,u ), y =h (t,x ), i=1,...,n. (8.6)
i i i i i i i
A centralized cooperative control strategy can be designed as
ξ˙=f(t,ξ,y ,...,y ), u =κ (t,y ,...,y ,ξ), i=1,...,n,
1 n i i 1 n
where the ith control input depends on the coordination variable ξ and the
outputs of all vehicles. In this centralized scheme, the coordination variable
is implemented at a central location and broadcast to every vehicle on the
team. However,this implementation results in a single point of failure and is
not scalable to a large number of vehicles.
A remedy to these drawbacks is to instantiate a local copy of the coor-
dination variable on each vehicle. If each vehicle implements the same local
controlalgorithm,wemightexpectthatadistributedschemewillachievethe
same level of cooperationas the associated centralized scheme. However,due
to different local situational awareness uncertainties for each vehicle, there
exist discrepancies between each instantiation of the coordination variable.
For example, in multivehicle simultaneous arrival missions, each vehicle’s es-
timatedteamarrivaltime(i.e.,itscoordinationvariable)maybedynamically
changingand inconsistentwith other vehicles’estimated teamarrivaltime as
the vehicle encounters obstacles or threats. As a result, consensus algorithms
need to be applied to guarantee that each instantiation of the coordination
variable converges to a common value.
Figure8.5showsaconsensus-baseddistributedcooperativecontrolscheme
with a group-level reference state. The hierarchical architecture consists of
three layers: consensus module, cooperation module, and physical vehicle.
Eachvehicleinstantiatesalocalcopyoftheconsensusmoduleandcooperation
module. Let ξ denote the ith vehicle’s instantiation of the coordination vari-
i
able.LetN (t)andJ (t)denote,respectively,thepossiblytime-varyingsetof
i i
vehicles whose coordination variable instantiations and outputs are available
to vehicle i at time t. Depending on mission requirementand communication
bandwidth,ξ ,y ,ortheir combinationis exchangedbetweenneighbors.Note
i i
that the neighboringvehicles’outputs maybe exchangedless frequently than

172 8 Consensus-based Design Methodologies for Cooperative Control
the coordinationvariable instantiations.The objectiveof the consensus mod-
ules is to drive ξ to a consistent value that also achieves the desired mission
i
goal.The local controllawu i for eachvehicle is based on the instantiation of
the coordination variable for that vehicle. Note that each layer has feedback
information describing the performance of that layer to the layer above it, as
| denoted | by z | and | z . |     |     |     |     |     |     |
| ------- | ---- | --- | --- | --- | --- | --- | --- | --- | --- |
|         | ci   |     | vi  |     |     |     |     |     |     |
Fig.8.5.Consensus-baseddistributedcooperativecontrolschemewithagroup-level
reference state
We update the ith instantiation of the coordination variable according to
| a consensus | algorithm |     | of the   | form |            |     |           |     |       |
| ----------- | --------- | --- | -------- | ---- | ---------- | --- | --------- | --- | ----- |
|             |           | ξ˙  | =f (t,{ξ | |j   | ∈N (t)},{y | |k  | ∈J (t)}), |     | (8.7) |
|             |           | i   | i        | j    | i          | k   | i         |     |       |
∈J
wherey ,k (t),introducegroupfeedbackfromvehicleianditsneighbors
|     | k   | i   |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
totheithinstantiationofthecoordinationvariable.1 Thegoalistoguarantee
|        | →       | ∀i     | (cid:6)= |       | → ξ(p), |     |          | →    | ∞,    |
| ------ | ------- | ------ | -------- | ----- | ------- | --- | -------- | ---- | ----- |
| that ξ | i (t) ξ | j (t), | j,       | and ξ | i (t)   | i = | 1,...,n, | as t | where |
ξ(p),p=1,...,P,denoteasequenceofdesiredmissiongoals.We proposethe
| local control | for | the | ith vehicle | as       |       |        |     |     |     |
| ------------- | --- | --- | ----------- | -------- | ----- | ------ | --- | --- | --- |
|               |     |     | u           | =κ (t,{y | |k ∈J | (t)},ξ | ),  |     |     |
|               |     |     | i           | i        | k     | i      | i   |     |     |
where the ith control input depends on its own and local neighbors’ outputs
| and on | the ith      | instantiation |          | of the | coordination |     | variable. |        |     |
| ------ | ------------ | ------------- | -------- | ------ | ------------ | --- | --------- | ------ | --- |
| 8.4.2  | Coordination |               | Variable |        | Constituted  | by  | Vehicle   | States |     |
Inthissubsection,weconsiderthecasewhereeachvehicleadjustsitsownstate
according to the states of its neighbors to achieve different group objectives.
1 Note that (8.7) represents a generic form of the consensus algorithms described
| in Chapters |     | 2–7. |     |     |     |     |     |     |     |
| ----------- | --- | ---- | --- | --- | --- | --- | --- | --- | --- |

|     |     | 8.4 Approach without | an Optimization | Objective | 173 |
| --- | --- | -------------------- | --------------- | --------- | --- |
Here, the states of the vehicles or their relative state deviations constitute
the coordination variable. For example, to achieve a cooperative observation,
attitude alignment may be required for a team of vehicles with only local
information exchange of the neighboring vehicles’ attitudes. In multi-vehicle
flocking applications [198], each vehicle maneuvers according to its nearby
neighbors’positions andvelocities to achievegroupbehaviorssuchas separa-
| tion, alignment, | and | cohesion. |     |     |     |
| ---------------- | --- | --------- | --- | --- | --- |
Whenthestatesofthevehiclesortheirrelativestatedeviationsconstitute
thecoordinationvariable,wecanadapttheschemeshowninFig.8.5toadis-
tributed cooperative controlscheme, as shown in Fig. 8.6,where each vehicle
instantiatesdifferentmodulessuchasgoalseeking,consensusbuilding,forma-
tionkeeping,andcollisionavoidancetocharacterizedifferentgroupbehaviors.
Through local communication or sensing, each vehicle specifies its local con-
trollawbasedonthesecombinedmodules.Thefunctionalityoftheconsensus
module is to guarantee the alignment of velocities, attitude, altitude, and so
| on among | multiple vehicles. |     |     |     |     |
| -------- | ------------------ | --- | --- | --- | --- |
Fig. 8.6. Consensus-based distributed cooperative control scheme with different
group behaviors
Suppose that the dynamics of the ith vehicle are given by (8.6). We
| propose | the local control | for the ith vehicle | as  |     |     |
| ------- | ----------------- | ------------------- | --- | --- | --- |
|         |                   | u =κ (t,z           | ),  |     |     |
|         |                   | i i                 | i   |     |     |

174 8 Consensus-based Design Methodologies for Cooperative Control
(cid:2)
wherez =η (t,{y |(cid:2)∈J (t)})denotestheinformationsensedbyand/orcom-
i i (cid:7) i
municatedtovehicleiandJ (t)denotesthesetofvehicleswhoseinformation
i
isavailabletovehicleithrougheithercommunicationorsensing.Oneexample
isthatz iscomposedofasetofvehiclepositionsy ,wherej ∈J (t).Another
i j i
isthatz iscomposedofasetofrelativepositionmeasurementsy −y ,where
i i j
j ∈J (t)\{i}.
i
8.5 Literature Review
Inthenextseveralchapters,wewillapplythedesignmethodologiesdescribed
inSections8.3and8.4toformationcontrolofmultiplewheeledmobilerobots
and spacecraft as well as to cooperative control of multiple UAVs. Before
moving on, we will overview the existing literature on formation control and
multi-UAV cooperation.
8.5.1 Formation Control
Accurate maintenance of a geometric configuration among multiple vehicles
moving in formation promises less expensive, more capable systems that can
accomplishobjectivesimpossibleforasinglevehicle.Theconceptofformation
controlhas been studied extensively in the literature with applications to the
coordinationofmultiplegroundrobots[15,64,69,72,123,151,152,227,233,243],
UAVs[82,226],AUVs[225],satellites[37,102],aircraft[11],andspacecraft[85,
142,200,244].
There are several advantages to using formations of multiple vehicles.
Theseincludeincreasedfeasibility,accuracy,robustness,flexibility,lowercost,
energy efficiency, and probability of success. For example, a group of robots
canbeusedtomovelargeawkwardobjects[57,111]ortomovealargenumber
of objects [240]. In addition, groups of robots can be used for terrain model
acquisition [240], planetary exploration [113], or measuring radiation levels
over a large area [10]. In [263], a group of robots is used for path obstruc-
tion.This couldbe usedto impede the motionofanintruder ona battlefield.
The probability of success will also be improved if multiple vehicles moving
informationareusedtocarryoutamission,e.g.,multiple UAVsareassigned
to a certain target [24] or multiple AUVs are used to search an underwater
object [225]. In spacecraft formation flying applications, using multiple mi-
crospacecraft instead of a monolithic spacecraft can reduce the mission cost
and improve system robustness and accuracy [85].
Various strategies and approaches have been proposed for formation con-
trol.These approachescanbe roughlycategorizedas leader-following,behav-
ioral, and virtual leader/virtualstructure approaches.
In the leader-following approach, one of the vehicles is designated as the
leader, with the rest of the vehicles designated as followers. The basic idea is
that the followers track the position and orientation of the leader with some

8.5 Literature Review 175
prescribed (possibly time-varying) offset. There are numerous variations on
this theme including designating multiple leaders, forming a chain (vehicle
tracks vehicle), and other tree topologies.
One of the first studies on leader-following strategies is reported in [243],
which discusses formation control laws for mobile robots. The application of
these ideas to spacecraft formations is reported in [244], where explicit con-
trollawsforformationkeepingandrelativeattitudealignmentbasedonnear-
est neighbor tracking are derived.Severalleader-followingtechniques are dis-
cussed,includingleadertracking,nearestneighbortracking,barycentertrack-
ing, and other tree topologies. In [245], the ideas of [244] are extended to ac-
countforactuatorsaturationandareappliedtotheproblemofcontrollingthe
formation to execute a continuous rotational slew. In [85], adaptive control
laws are added to the control derived in [244] to reject common space dis-
turbances. Leader-follower approaches to satellite formation keeping in earth
orbit are described in [53], [103],and [265].
There have been a number of studies of leader-following techniques in
the mobile robotics community. In [227], a leader-following technique is used
to control a group of mobile robots to move a box cooperatively. In [56],
feedback linearization techniques are used to derive tracking control laws for
nonholonomic robots that are used for leader-following. In addition, the au-
thors describe the formation configuration as a directed graph. The shape of
the formation is changed as graph structures are changed. Another leader-
following approach for multiple nonholonomic robots is described in [264]. A
leader-following approach to the platoon problem in intelligent highways is
contained in [214].
The basic idea behind the behavioral approach is to prescribe several de-
siredbehaviorsforeachvehicleandtomakethe controlactionofeachvehicle
aweightedaverageofthecontrolforeachbehavior.Possiblebehaviorsinclude
collision avoidance, obstacle avoidance, goal seeking, and formation keeping.
Therearealsonumerousvariationsonthebehavioralapproachtomultivehicle
coordination. Most are derived by novel weights of the behaviors.
In[136],the behavioralapproachisappliedtothe problemofmaintaining
a constellation of satellites in an equally distributed ring formation in earth
orbit. Simple Lyapunov control functions are used to maintain distance and
avoid collisions. The application of the behavioral approach to aircraft flying
informationisdescribedin[11],wherecontrolstrategiesarederivedtomimic
the instinctive behavior of birds and fish. A paper that describes the behav-
ioral approach to formation keeping for mobile robots is [15], where control
strategiesarederivedbyaveragingseveralcompetingbehaviors,includinggoal
seeking, collision avoidance, and formation maintenance. Because competing
behaviors are averaged, occasionally strange and unpredicted behaviors may
occur. Unit-center tracking, leader tracking, and nearest neighbor tracking
controls are also studied. In [269], the behavioral approachis used to cause a
groupof robotsto create line andcircle formations.These ideas areextended

176 8 Consensus-based Design Methodologies for Cooperative Control
in[44]totheproblemofcontrollingaformationofmobilerobotstotransport
objects.
In the virtual leader/virtual structure approach, the entire formation is
treated as a single structure or rigid body. In the virtual structure approach,
the control is derived in three steps: first, the desired dynamics of the vir-
tual leader/virtual structure are defined; second, the motion of the virtual
leader/virtualstructureis translatedinto the desiredmotionforeachvehicle;
and finally, tracking controls for each vehicle are derived.
The virtual structure approach is applied in [28,123] to acquire high pre-
cision formation control for mobile robots. The application to formations of
spacecraftin free space is described in [19,22].The virtualleader approachis
appliedin[62,121]forformationcontrolofmobile robots.Asimilarapproach
is the action reference scheme in [101,102]. In [151], a Lyapunov formation
functionisusedtodefineaformationerror,andformationfeedbackisincorpo-
rated in the virtual leaders through parameterized trajectories. In [189,267],
the virtual structure approach is used to perform elementary formation ma-
neuvers for,respectively,mobile robots and spacecraft,where groupfeedback
is incorporated from the followers in the virtual structure to improve group
stability and robustness.
Besidesthe three approachesdescribed above,approachesbasedongraph
rigidity and artificial potential functions have been studied, respectively,
in [64,153,157,268]and [61,257] for formation control. There have also been
otherstudiesofmultiplesatellitesorbitingtheearthinformation.Twospace-
craft flying in a polar orbit formation are considered in [73,211], and a soft-
ware package that implements their approach is described in [74]. In [241],
the design of a two satellite formation flying mission for an interferometric
SAR topography mission is described. Formation keeping for low earth-orbit
satellites is consideredin [83].Relative formationkeeping forlow earthorbits
using LQ regulators is discussed in [237]. There have been several studies on
optimal fuel formation control, including [20,25,242].
8.5.2 Cooperation of Multiple UAVs
Cooperation among UAVs has it own set of unique challenges. For example,
unlike groundrobots,there is generallyverylittle physicalcouplingexceptin
theobviouscasesofcloseformationflight.Themostsignificantchallengethat
is unique to UAVs is three-dimensionalflight with immediate implications on
path planning algorithms. Another characteristic unique to fixed-wing UAVs
isthatforwardmotionisrequired.Therefore,stop-and-waitpathdeconfliction
algorithms(e.g.,[5])arenotapplicable.Inaddition,smallfixed-wingUAVsare
highlysusceptibletowind.Therefore,cooperationstrategiesmustincorporate
feedback at the highest levels to account for objective failure modes.
However,cooperationproblemsforgroundrobotsandUAVsshareanum-
ber of similarities. For example, both ground and aerial robots have strict

8.5 Literature Review 177
communication constraints:team members must be in close physical proxim-
ity to communicate, bandwidth is limited, and the communication topology
maychangeunpredictablywithtime.Bothgroundandaerialrobotsmustdeal
with collisionavoidanceconstraints.Groundrobotsarenecessarilyconcerned
withmaneuveringaroundeachotherinconfinedspatialenvironments.Onthe
other hand, aerialrobots usually havemore room to maneuver,but collisions
are typically catastrophic. Another similarity is that decentralized coopera-
tion strategies are generally required for both ground and aerial robots. In
addition, cooperation strategies must be robust to the failure of individual
team members.
Studies specific to cooperative control of UAVs have recently appeared
in the literature. Extensive efforts have been directed toward close formation
flight. Early studies reported in [29] and [45] reported significant potential
fuel savingsthatcould be gainedby close formationflight. In[167],the phys-
ical equations that describe a fixed-wing aircraft flying in the vortex of the
leaderaredescribed,andacontrolsystembasedonthelinearizedmodelisde-
veloped. The approach is extended to nonlinear aerodynamic coupling terms
in [161]. Standard inner/outer loop designs are extended to close-formation
flight in [210]. A behavioral approach to aircraft formation flight is given
in [11]. In [163], differential flatness is used to generate group formation ma-
neuvers. The effects of communication constraints on close formation flight
are studied in [82]. Rigorous conditions for stable formation flight with lim-
ited communication are developed in [69].
Multiple UAV cooperative timing problems have also received significant
attention. One version of this problem occurs where multiple UAVs are re-
quiredtoconvergeontheboundaryofaradardetectionareatomaximizethe
elementofsurprise[24,27,40,137,138].Cooperativetimingproblemsalsoarise
in re-fueling scenarios, fire and hazardous material monitoring [38], moving
area of regardproblems, and continuous surveillance problems [109].
Cooperativetiming problemsaresensitiveto the assignmentandordering
oftasks.Oneapproachforhandlingcooperativetimingistoapplytimingcon-
straints to the task assignment problem. In [7,27,199], mixed-integer linear
programming (MILP) is used to solve tightly coupled task assignment prob-
lems with timing constraints.The advantageofthis approachis thatit yields
the optimal solution for a given problem. The primary disadvantages are the
complexity of problem formulation and the computational burden. Pruning
strategies for simplifying the MILP problem have been proposed to enable
near-real-time solutions.
Although path planning for single UAVs has been an active area of re-
search for some time (e.g., see [9,66,75,262,266]),cooperative path planning
approaches for UAVs have only recently begun to appear. In [95], a decen-
tralized optimization method based on a bargaining algorithm is developed
andappliedtoamultipleaircraftcoordinationproblem.Ahybridhierarchical
control architecture is used for air traffic control in [92,207].

178 8 Consensus-based Design Methodologies for Cooperative Control
Experimental work with teams of UAVs has been limited, primarily due
tothepracticalchallengesoffieldingmultiplevehiclessimultaneously.Several
researchershavedemonstratedleaderfollowingwith twoUAVs (e.g., [34,107,
212]).CooperativetimingusingateamofthreeUAVshasbeendemonstrated
experimentally(e.g., [150]).
8.6 The Remainder of the Book
The remainder of the book is organized as follows: Chapter 9 will apply the
design scheme described in Section 8.4.1 to rendezvous and axial alignment
ofmultiple wheeledmobile robots,whererendezvousandaxialalignmentcan
be viewed as special cases of a formation stabilization problem. Chapter 10
applies the design scheme described in Section 8.4.1 to distributed forma-
tion controlof multiple wheeled mobile robots.Chapter 11 applies the design
scheme described in Section 8.4.2 to decentralized formation stabilization of
multiple wheeled mobile robots. Chapter 12 applies the design scheme de-
scribedinSection 8.4.1to deepspacespacecraftformationflying.Chapter 13
applies the design scheme described in Section 8.4.1 to cooperative fire mon-
itoring with multiple UAVs. Chapter 14 applies the design scheme described
in Section 8.3 to cooperative surveillance with multiple UAVs.
8.7 Notes
The results in this chapter are based mainly on [26,171]. Section 8.5.1 is
mainly from [22].
Acknowledgment is given to
(cid:10)c2006 IEEE. Reprinted, with permission, from Randal W. Beard, Tim-
othy W. McLain, Derek Nelson, Derek Kingston, and David Johanson, “De-
centralizedcooperativeaerialsurveillanceusing fixed-wingminiature UAVs,”
Proceedings of the IEEE, vol. 94, no. 7, pp. 1306–1324,July 2006.
(cid:10)c2006 IEEE. Reprinted, with permission, from Wei Ren, “Cooperative
control design strategies with local interactions,” Proceedings of the IEEE
Conference on Networking, Sensing, and Control, Ft. Lauderdale, FL, 2006.

Part VI
| Applications | to Multivehicle | Cooperative |
| ------------ | --------------- | ----------- |
Control

9
Rendezvous and Axial Alignment with
Multiple Wheeled Mobile Robots
In this chapter, we apply the consensus-based design scheme in Section 8.4.1
to two applications, rendezvous and axial alignment. In the rendezvous ap-
plication, multiple mobile robots simultaneously arrive at a common a priori
unknown location determined through team negotiation. In the axial align-
mentapplication,multiplemobilerobotscollectivelyaligntheirfinalpositions
alongaline.Thetwoapplicationsrelyontheconsensusalgorithmsintroduced
in Chapter 2, andare experimentally implemented andvalidated ona mobile
actuator and sensor network platform subject to directed, possibly switching
interaction topologies to explore issues and challenges in cooperative control
with communication constraints. The experimental results show the effec-
tiveness and robustness of the consensus algorithms, even in the presence of
physical platform limitations, packet loss, and information delay.
9.1 Experimental Platform
The Mobile Actuator and Sensor Network (MASnet) platform in the Center
forSelf-OrganizingandIntelligentSystems(CSOIS)atUtahStateUniversity
(USU) combines wireless sensornetworks with mobility, that is, a large num-
ber of robots can serve both as actuators and sensors. Although each robot
has limited sensing, computation, and communication ability, they can coor-
dinate with each other as a team to achieve challenging cooperative control
tasks such as formation keeping and environment monitoring.
The MASnet platform is comprised of MASmotes, an overhead camera,
andabasestationPC,asshowninFig.9.1.MASmotesareactuallytwo-wheel
differentiallysteeredrobotsthatcancarrysensorsandactuatorsandarewire-
less networked via Micaz from Crossbow [1]. The functionality of MASmotes
includes intermote and mote-to-base-station communication, data collecting,
pulse-width modulation (PWM) signalgeneration,and encoder counting.An
overheadCCDcameraisusedtoidentifyeachrobotanddetermineitsposition
and orientation (i.e., pseudo-GPS information). Images from the camera are

182 9 Rendezvousand Axial Alignment with Multiple Wheeled Mobile Robots
processed by the base station. The functionality of the base station includes
image processing, serial-to-programming-boardcommunication, pseudo-GPS
information broadcasting, and decision making. The base station communi-
cateswithagatewaymotemountedonaprogrammingboardthroughaserial
port. The gateway mote then communicates with all other MASmotes over
a 2.4 GHz wireless mesh network. Note that the gateway mote serves as a
gatewaybetweenwirelesscommunicationandserialportcommunication,and
its only purpose is to forward all messages between the serial port and the
RF port. Through communication, the base station can thereby send com-
mands and pseudo-GPS information to each MASmote. All MASmotes can
also communicate with each other over the 2.4 GHz wireless mesh network.
(a) MASnet testbed (b) MASmote robot hardware
Fig. 9.1. MASnetexperimentalplatform.Subfigure(a)showstheMASnettestbed
comprisedofMASmotes,anoverheadcamera,andabasestationPC.Subfigure(b)
shows therobot hardware.
9.2 Experimental Implementation
Because both intermote and mote-to-base-station communication are avail-
able,theMASnetplatformcanbeusedexperimentallytotestbothcentralized
anddecentralizedcooperativecontrolschemes.Foracentralizedscheme,each
MASmote isresponsibleonlyforitslow-levelmotorcontrol,whereasthebase
station, serving as a centralized commander, broadcasts pseudo-GPS infor-
mation to each MASmote robot, implements cooperative control algorithms,
and sends control commands based on the information gathered from the
whole team. For a decentralized cooperative control scheme, each MASmote
implements its own cooperative control algorithm based on the pseudo-GPS
information provided by the base station.

9.2 Experimental Implementation 183
In the experiments, all control algorithms are implemented onboard the
MASmotes, and each MASmote uses only the pseudo-GPS information of its
own and its neighbors even if the pseudo-GPS information of all MASmotes
is provided by the base station. By doing so, distributed cooperative con-
trolalgorithms involvingonly neighbor-to-neighborinformationexchangevia
communicationorsensingcanbe testedformultivehicle systems.Thefeature
oflocalinformationexchangeisimportantinapplicationsforthefollowingsit-
uations: (i) communication or sensing topologies are not fully connected, (ii)
vehicles have limited communication range and bandwidth, (iii) power con-
sumptionoftheteamisconstrained,and(iv)thestealthoftheteamneedsto
beincreased.Twoapplicationsarestudiedintheexperiments,rendezvousand
axial alignment. In both applications, only neighbor-to-neighbor information
exchange is allowed.
One challenge of applying consensus algorithms to the MASnet platform
comesfromthe factthatthe MASmote robotsarenonholonomic.Controlling
the positions of the robots overcomes this issue with the compromise that
the robot orientation information is lost when the robots reach their desired
positions.
We apply the design scheme in Section 8.4.1 to the rendezvous and axial
alignment problems. A consensus controller is applied to update the desired
position of each MASmote robot at each instant when the robot receives the
position and orientation information of its own and its neighbors from the
pseudo-GPS. For the rendezvous application, the coordinationvariable is the
team rendezvous position. For the axial alignment application, the coordina-
tion variable is the center of the line segment of alignment. For both appli-
cations, local instantiation of the coordination variable becomes the desired
positionofthecorrespondingrobot.Theupdateperiodfortheconsensuscon-
trollerdependsonthepseudo-GPSinformationupdaterate,whichisbetween
0.1 and 0.2 seconds, on average. A low-level PID position controller is also
appliedtoguaranteethateachrobotmovestoits(time-varying)desiredposi-
tion (see [43] and references therein for the position controller). The position
controller for each robot requires its current position and orientation as well
as its desired position provided by its consensus controller. Each robot uses
its encoders for position and orientation measurements between pseudo-GPS
updates. However, a pseudo-GPS update will overwrite the encoder-based
position and orientation measurements due to the inaccuracy of the low-cost
encoders.
Let r = [x ,y ]T and rd = [xd,yd]T denote, respectively, the actual and
i i i i i i
desired position of robot i. Motivated by (2.2), a possible strategy for the
rendezvous problem is to update rd as
i
(cid:2)n
r˙d =− a (rd−rd), (9.1)
i ij i j
j=1

184 9 Rendezvousand Axial Alignment with Multiple Wheeled Mobile Robots
|     |     |     |     |     | A   | ∈ Rn×n |     |
| --- | --- | --- | --- | --- | --- | ------ | --- |
where a is the (i,j) entry of the adjacency matrix associated
| ij  |     |     |     |     |     | n   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
with directed graph G =(V ,E ). Another possible strategy is to update rd
|     |     | n   | n n |     |     |     | i   |
| --- | --- | --- | --- | --- | --- | --- | --- |
as
(cid:2)n
|     |     |     | r˙d =− | a (r | −r ). |     | (9.2) |
| --- | --- | --- | ------ | ---- | ----- | --- | ----- |
|     |     |     | i      | ij i | j     |     |       |
j=1
Note that the desired team rendezvous position using (9.1) is unaffected by
robot tracking performance whereas the desired team rendezvous position
using (9.2) is dependent on the positions of the robots. The two strategies
may be appropriate for different applications, depending on the application
context.
| Note that | (9.2) | can also | be written | as       |      |     |     |
| --------- | ----- | -------- | ---------- | -------- | ---- | --- | --- |
|           |       | (cid:2)n |            | (cid:2)n |      |     |     |
|           | r˙d   | =−       | (rd−rd)+   |          | −e   |     |     |
|           |       |          | a          |          | a (e | ),  |     |
|           |       | i        | ij         | i j      | ij i | j   |     |
|           |       | j=1      |            | j=1      |      |     |     |
(cid:2)
where e = rd −r denotes the ith robot’s tracking error. Assuming a well-
| i   | i i |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
designed low-level position controller, e i (t) is bounded for a(cid:7)ll t and e i (t) ap-
n
proaches zero, as t → ∞, i = 1,...,n, which implies that a (e −e )
|     |     |     |     |     |     | j=1 ij | i j |
| --- | --- | --- | --- | --- | --- | ------ | --- |
is bounded for all t and approach(cid:18)es zero, as t(cid:18) → ∞. Therefore, it follows
|                             |     |     |     | (cid:18) rd(t)−rd(t) | (cid:18)               |     |     |
| --------------------------- | --- | --- | --- | -------------------- | ---------------------- | --- | --- |
| fromTheorems2.14and2.35that |     |     |     |                      | isboundedforalltandap- |     |     |
|                             |     |     |     | i                    | j                      |     |     |
proacheszero,ast→∞.Inotherwords,the cascadesystemcomposedofthe
|     |     |     |     |     |     | rd(t) | → rd(t) |
| --- | --- | --- | --- | --- | --- | ----- | ------- |
consensus controller and the position controller is stable, i.e.,
|             |                   |           |      |           |               | i   | j   |
| ----------- | ----------------- | --------- | ---- | --------- | ------------- | --- | --- |
| and r (t)→r | (t), ∀i(cid:6)=j, | as        | t→∞. |           |               |     |     |
| i           | j                 |           |      |           |               |     |     |
| For axial   | alignment,        | motivated |      | by (2.8), | rd is updated | as  |     |
i
(cid:2)n
|     |     | r˙d =− |     | a [(r −r | )−Δ ], |     | (9.3) |
| --- | --- | ------ | --- | -------- | ------ | --- | ----- |
|     |     | i      |     | ij i     | j ij   |     |       |
j=1
where Δ denotes the desired constant separation vector between r and r .
| ij  |     |     |     |     |     |     | i j |
| --- | --- | --- | --- | --- | --- | --- | --- |
The stability of (9.3) can be analyzed in a way similar to (9.2) by following
| Corollary | 2.12. |     |     |     |     |     |     |
| --------- | ----- | --- | --- | --- | --- | --- | --- |
In our experiments, we let a = 1 if (j,i) ∈ E and use discrete-time
|     |     |     |     | ij  | n   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
versions of (9.2) and (9.3). In this case, algorithm (9.2) updates rd as the
i
average of its current position and the current positions of its neighbors at
| each sample      | time. |         |     |     |     |     |     |
| ---------------- | ----- | ------- | --- | --- | --- | --- | --- |
| 9.3 Experimental |       | Results |     |     |     |     |     |
In this section, we show experimental results for rendezvous and axial align-
| ment on our | MASnet | platform. |     |     |     |     |     |
| ----------- | ------ | --------- | --- | --- | --- | --- | --- |

9.3 Experimental Results 185
9.3.1 Rendezvous
Fortherendezvousapplication,rendezvousoffourMASmoterobotsisstudied
under directed, time-invariant, and dynamic interaction topologies, respec-
tively.
Figure 9.2 shows six different time-invariant interaction topologies for
Cases I–VI. In particular, Case I corresponds to an undirected connected
graph, Case II corresponds to a line graph, Case III corresponds to an undi-
rected graph with two distinct subgroups, Case IV corresponds to a directed
graph with multiple nodes that have only outgoing edges (vehicles 1 and 3),
Case V corresponds to a cyclic pursuit graph, and Case VI corresponds to a
| general directed | graph that                                               | has a directed spanning                                  | tree.                                                                                                             |
| ---------------- | -------------------------------------------------------- | -------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
|                  | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) |
|                  | I 1                                                      | 2 II                                                     | 1 2(cid:20)(cid:20)                                                                                               |
(cid:14)(cid:14)
|     | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) (cid:15)(cid:15)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) |
| --- | -------------------------------------------------------- | -------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
|     | 4                                                        | 3                                                        | 4 3                                                                                                                               |
|     | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) (cid:15)(cid:15)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) |
|     | 1                                                        | 2                                                        | 1 2(cid:20)(cid:20)                                                                                                               |
III IV
(cid:14)(cid:14)
|     | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5)                 | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5)(cid:2)(cid:2) (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5)           |
| --- | -------------------------------------------------------- | ------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------- |
|     | 4                                                        | 3                                                                        | 4 3                                                                                                                                       |
|     | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) | (cid:15)(cid:15)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5)(cid:2)(cid:2) 1(cid:11) (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) |
|     | V 1(cid:20)(cid:20)                                      | 2 VI                                                                     | (cid:11) 2(cid:20)(cid:20)                                                                                                                |
(cid:11)
(cid:11) (cid:11)
(cid:11)
(cid:11) (cid:11)
|     |                                                                        | (cid:14)(cid:14)                                         | (cid:29)(cid:29)                                                                                                                |
| --- | ---------------------------------------------------------------------- | -------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
|     | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9)(cid:2)(cid:2) | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5)(cid:2)(cid:2) (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) |
|     | 4                                                                      | 3                                                        | 4 3                                                                                                                             |
Fig. 9.2. Interaction topologies among four robots for the rendezvousapplication
Figure 9.3 shows the experimental results of the rendezvous captured by
the overheadcamerafor Cases I–VI, where the circles denote the initial posi-
tions of the robots and the colored dots denote the actual trajectories of the
robotsidentifiedby the overheadcamera.Ifthe visionsystemfailsto identify
a robot during a certain period, no pseudo-GPS update is available to the
robot (equivalent to a pseudo-GPS packet loss), and hence no colored dot
is placed on the screen during that time. The trajectories of the robots are
| captured between | t=0 and | t=t seconds. |     |
| ---------------- | ------- | ------------ | --- |
f
Figure 9.3 shows that the four robots rendezvous in all cases except in
CasesIIIandIVwhereonlyasubgrouprendezvous.Thisexperimentalresult
is consistent with Theorem 2.8 because only the graphs of Cases III and IV

186 9 Rendezvousand Axial Alignment with Multiple Wheeled Mobile Robots
do not have directed spanning trees. In our experiments, the computation-
ally complex task of processing the image, finding MASmote markers, and
extracting position and orientation information introduces a delay of 0.1 to
0.2 seconds between image capture and position and orientation information
broadcast. In addition, the hardware and software limitations of the vision
system cause frequent pseudo-GPS packet loss (roughly 2–5%) and an aver-
age position measurement error of 1.32 cm. When a robot is lost from the
view of the overheadcamera due to glareor other issues,the robot’s position
andorientationinformationarenolongeravailabletoitselfanditsneighbors,
implying a pseudo-GPS packet loss. Specifically, in Case VI, the upper left
robotdoes notreceivepseudo-GPSupdates duringseveralsample periods,as
showninFig.9.3f.Despitetheexistenceoftimedelayandpseudo-GPSpacket
loss,therendezvousexperimentsachieveresultspredictedbythetheory.With
consensuscontroller(9.2),thedesiredpositionforarobotsimplyremainscon-
stant during the period when the pseudo-GPS is not available, that is, (9.2)
remains stable with time delay or pseudo-GPS loss although the algorithm
will converge more slowly, which in turn results in slower rendezvous for the
team. With the low-level position controller, when there is no pseudo-GPS
update, a robot relies on encoder data to move toward the desired position
calculated at the previous sample period. This providesa way to compensate
for time delay and pseudo-GPS loss.
In theory, if each robot has the same tracking performance, the final ren-
dezvous position using (9.2) should be the average of the initial positions of
those robots thathave directedpaths to allother robots.Inour experiments,
dueto thediscrepancyamongthe robotsandinaccuracycausedbythevision
system,thefinalrendezvouspositionisthe weightedaverageofthe initialpo-
sitionsofthoserobotsthathavedirectedpathstoallotherrobots,asshownin
Fig.9.3.ThefinalrendezvouspositioninCasesIandVareweightedaverages
of all four robots’ initial positions. In contrast, the final rendezvous position
in Cases II and VI are, respectively, robot 1’s initial position and a weighted
averageof the initial positions of robots 1, 2, and 3. This experimental result
can be explained by noting that in Cases I and V, each robot has a directed
path to every other robot; in Case II, only robot 1 has a directed path to all
other robots; and in Case VI, every robot except robot 4 has a directed path
to all other robots. In particular, in Case III, the final rendezvous position
for the upper two robots is not the center of the two robots’ initial positions
but closer to the starting position of the upper left robot. We observe in the
experimentthattheupperleftrobotreceivesspuriousorientationinformation
duringthebeginningperiodoftheexperiment,whichcausestherobottospin
at its initial position without moving toward its desired position during the
first several seconds. However, the upper right robot is able to move toward
the upper left robot to achieve rendezvous.In addition, in Case IV, the over-
headcameraproducesincorrectpositionandorientationmeasurementsforthe
upper right robot a few seconds before the upper right and lower left robots
rendezvous, which causes the upper right robot to wander around and spin.

9.3 Experimental Results 187
However,thelowerleftrobotisable tocatchthe upperrightrobottoachieve
rendezvous.These two examples demonstrate the robustnessof (9.2),evenin
the presence of incorrect output of the vision system for a certain period of
time. The robustness of (9.2) is due to the fact that the desired position for
each robot is dynamically determined according to its current position and
the current positions of its neighbors.
Furthermore, by comparing Cases I, II, V, and VI, we can see that in
CaseI,thefourrobotsrendezvousthefastestwhileinCaseV,thefourrobots
rendezvoustheslowest.Thisexperimentalresultisalsopredictedbytheory.In
particular,thefactthatconsensusunderalinegraph(CaseII)convergesmore
slowlythananundirectedconnectedgraph(CaseI)canbeseenbycomparing
the eigenvalues of the nonsymmetrical Laplacian matrix L associated with
4
theinteractiontopologyforthefourrobotsintwocases.Theeigenvalueλ (L )
2 4
of L whose real part is the second smallest characterizes the convergence
4
speedoftheconsensusalgorithm.Itisstraightforwardtoshowthatλ (L )=2
2 4
in Case I and λ (L ) = 1 in Case II by noting that a = 1 if (j,i) ∈ E . By
2 4 ij n
comparing Fig. 9.3a and 9.3b, we can see that in Case II, the upper right
robot moves toward the lower right robot instead of moving directly toward
the upper left robot due to the fact that the upper right robot can receive
information only from the lower right robot, resulting in slower convergence
for the team.
Totestrendezvousinthecaseofswitchinginteractiontopologies,weforce
the interaction topologies for the four robots to switch randomly from the
set G¯s ={G ,G ,G ,G ,G } which is shown in Fig. 9.4. Note that
4 4(1) 4(2) 4(3) 4(4) 4(5)
each directed graph in G¯s does not have a directed spanning tree but that
4
the union of these graphs denoted by Gu does have a directed spanning tree.
4
Because switching among the directed graphs in G¯s is random, the condition
4
for consensus in Theorem 2.31 is generically satisfied.
Figure 9.5a shows the experimental result of rendezvous when the inter-
action topologies switch randomly from G¯s with switching periods randomly
4
chosen between 2.75 and 8 seconds and Fig. 9.5b shows the experimental
result under the time-invariant interaction topology Gu. Note that the four
4
robots rendezvous even when the directed topologies switch randomly with
time, which validates the theory in Theorem 2.31 and demonstrates the ro-
bustness of the consensus algorithm to switching topologies, as long as the
minimum connectivity condition in Theorem 2.31 is satisfied. By comparing
Figs. 9.5a and 9.5b, it can be seen that convergence in the case of switching
topologiesis slowerthaninthe time-invariantcase because the robots simply
stop when they do not receive information from their neighbors. Also, the
switching topologies result in sudden drastic changes in robot directions, as
shown in Fig. 9.5a. In addition, in Fig. 9.5a, when the lower left robot makes
the second turn due to spurious pseudo-GPSdata for severalsample periods,
the robot starts to wander around, as shown by the concentrated dots. How-
ever, the inherent stability of the cascade system composed of the consensus

188 9 Rendezvousand Axial Alignment with Multiple Wheeled Mobile Robots
controller and the position controller causes the robot to recover, once the
vision system sends out correct position and orientation data.
9.3.2 Axial Alignment
For the axial alignment application, the case where four robots are evenly
distributed along a straight line is studied using a time-invariant interaction
topology. We choose Δ in (9.3) to guarantee that the robots align on a
ij
horizontal line with a separation distance of 24 cm along the x axis between
two adjacent neighbors.
Figure 9.6 shows the undirected interaction topology among the four ro-
bots. Figure 9.7 shows the experimental result of the axial alignment. In the-
ory, although each robot starts at an arbitrary initial position, their final
positions should be evenly distributed along a horizontal line with a separa-
tion distance of 24 centimeters. Due to hardware and software limitations of
the vision system, some robots move in the wrong direction for a period of
timeuntilthevisionsystemcorrectlyidentifiestheirorientations.Inaddition,
thereexistsapositiontrackingerrorwiththelow-levelpositioncontrollerdue
to inaccurate position and orientation measurements. Even with these limi-
tations, the overall experiment still achieves the goal of axial alignment with
an averageerroraround3 cm andfurther demonstrates the robustness ofthe
consensusalgorithm.Theexperimentalresultisconsistentwiththeargument
of Corollary 2.12.
9.3.3 Lessons Learned
Consensus algorithms have been experimentally applied to rendezvous and
axialalignment.TheresultsofbothapplicationsontheMASnetplatformhave
demonstratedthe effectiveness and robustnessof the consensus algorithms to
distributed cooperative control. Consensus algorithms provide a promising
method for distributed multivehicle cooperative control even in the presence
of physical robot limitations, packet loss, information delay, etc.
Despite the success of the experiments, there are limitations. One lim-
itation is that the robots are dependent on the vision system for position
and orientation measurements over long distances due to inaccuracy of the
encoders in the low-cost platform. When the vision system produces an in-
correct measurement or fails to identify a robot during a certain period of
time, a robot may move in the wrong direction. As the time or frequency of
vision failure increases, the overall team performance degrades dramatically.
Anotherlimitationis the pseudo-GPSupdate delay.Whenrobotsaremoving
slowly, the pseudo-GPS update delay has little effect, but at full speed, the
difference between the actual and the broadcast position and orientation can
be quite large. This is most noticeable when a robot is rotating. As a result,
thereisaneedtoimprovethevisionsystemandencoderaccuracyanddevelop

9.4 Notes 189
a prediction model for position and orientation. The combination of pseudo-
GPS data, encoder data, and mathematical model estimates is expected to
improve the accuracy of position and orientation measurements.
9.4 Notes
Theresultsinthischapterarebasedmainlyon[194,195].TheMobileActuator
andSensorNetwork(MASnet)platformisdescribedin[43]anditsreferences.
Acknowledgment is given to
(cid:10)c2007 IEEE. Reprinted, with permission, from Wei Ren, Haiyang Chao,
William Bourgeous, Nathan Sorensen, and YangQuan Chen, “Experimen-
tal validation of consensus algorithms for multi-vehicle cooperative control,”
IEEE Transactions on Control Systems Technology, 2007 (to appear).
(cid:10)c2007 IEEE. Reprinted, with permission, from Wei Ren, Haiyang Chao,
William Bourgeous, Nathan Sorensen, and YangQuan Chen, “Experimental
implementation and validation of consensus algorithms on a mobile actuator
andsensornetworkplatform,”Proceedings of the IEEE International Confer-
ence on Systems, Man, and Cybernetics,Montreal,Canada,2007(toappear).

190 9 Rendezvousand Axial Alignment with Multiple Wheeled Mobile Robots
|           | (t =11.58    |         |                  | (t =17.95     |     |
| --------- | ------------ | ------- | ---------------- | ------------- | --- |
| (a) Case  | I f          | s)      | (b) Case         | II f          | s)  |
| (c) Case  | III (t =6.93 | s)      | (d) Case         | IV (t =11.583 | s)  |
|           | f            |         |                  | f             |     |
| (e) Case  | V (t =19.80  | s)      | (f) Case         | VI (t =18.89  | s)  |
|           | f            |         |                  | f             |     |
| Fig. 9.3. | Experimental | results | of rendezvousfor | Cases I–VI    |     |

9.4 Notes 191
|     | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) | (cid:15)(cid:15)(cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9)(cid:2)(cid:2) | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5)                 | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) |
| --- | -------------------------------------------------------- | ------------------------------------------------------------------------ | ---------------------------------------------------------------------- | ------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------- |
|     | 1                                                        | 2                                                                        | 1                                                                      | 2                                                                        | 1 2(cid:20)(cid:20)                                                                                               |
|     | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9)                 | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9)               | (cid:15)(cid:15)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) |
|     | 4                                                        | 3                                                                        | 4                                                                      | 3                                                                        | 4 3                                                                                                               |
|     | G                                                        |                                                                          | G                                                                      |                                                                          | G                                                                                                                 |
|     | 4(1)                                                     |                                                                          | 4(2)                                                                   |                                                                          | 4(3)                                                                                                              |
(cid:3)(cid:3)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5)
|     | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9)                 | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5)                 | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9)(cid:4)(cid:4)                                                            |
| --- | -------------------------------------------------------- | ------------------------------------------------------------------------ | -------------------------------------------------------- | ------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------- |
|     | 1                                                        | 2(cid:20)(cid:20)                                                        | 1                                                        | 2                                                                        | 1 2(cid:20)(cid:20)                                                                                                               |
|     |                                                          |                                                                          | (cid:14)(cid:14)                                         |                                                                          | (cid:14)(cid:14)                                                                                                                  |
|     | (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) | (cid:15)(cid:15)(cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) | (cid:15)(cid:15)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) | (cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) (cid:15)(cid:15)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) |
|     | 4                                                        | 3                                                                        | 4                                                        | 3                                                                        | 4 3                                                                                                                               |
|     | G                                                        |                                                                          | G                                                        |                                                                          | Gu                                                                                                                                |
|     | 4(4)                                                     |                                                                          | 4(5)                                                     |                                                                          | 4                                                                                                                                 |
Fig. 9.4. Switching interaction topologies G 4(1)–G and their union G u for ren-
4(5) 4
dezvous
| (a) | Rendezvous | with topologies |     | (b) Rendezvous | with a time- |
| --- | ---------- | --------------- | --- | -------------- | ------------ |
randomly switching from G¯ s = invarianttopology G u (t =24 s)
|      |        |          | 4   |     | 4 f |
| ---- | ------ | -------- | --- | --- | --- |
| {G   | ,...,G | } (t =45 | s)  |     |     |
| 4(1) | 4(5)   | f        |     |     |     |
Fig. 9.5. Experimental results of rendezvous with topologies randomly switching
| from G¯ s | vs a time-invariant | topology | G u |     |     |
| --------- | ------------------- | -------- | --- | --- | --- |
| 4         |                     |          | 4   |     |     |

192 9 Rendezvousand Axial Alignment with Multiple Wheeled Mobile Robots
(cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5)
1 2
(cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) (cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5)
4 3
| Fig. 9.6. Interaction  | topology | for axial alignment |
| ---------------------- | -------- | ------------------- |
| Fig. 9.7. Experimental | result   | of axial alignment  |

10
| Distributed |     | Formation |        | Control | of Multiple |        |
| ----------- | --- | --------- | ------ | ------- | ----------- | ------ |
| Wheeled     |     | Mobile    | Robots | with    | a Virtual   | Leader |
In this chapter, we apply the consensus-based design scheme in Section 8.4.1
to formation control of multiple wheeled mobile robots with a virtual leader.
We propose a unified, distributed formation control architecture that accom-
modates an arbitrary number of subgroup leaders and arbitrary information
flow among the robots. The architecture requires only neighbor-to-neighbor
information exchange. In particular, the consensus tracking algorithm intro-
ducedinChapter3isappliedonthegroupleveltoguaranteeconsensusonthe
time-varyinggroupreferencetrajectoryinadistributedmanner.Basedonthe
group-levelconsensustrackingalgorithm,aconsensus-basedformationcontrol
strategy is then applied for vehicle level control. The proposed architecture
is experimentally implemented and validated on a multirobot platform un-
der neighbor-to-neighborinformationexchangewithboth single andmultiple
| subgroup | leaders     | involved. |           |         |              |     |
| -------- | ----------- | --------- | --------- | ------- | ------------ | --- |
| 10.1     | Distributed |           | Formation | Control | Architecture |     |
In this section, we propose a distributed formation control architecture that
accommodatesanarbitrarynumberofsubgroupleadersandensuresaccurate
formationmaintenancethroughinformationcouplingbetweenneighbors.The
architecture is adapted from the design scheme in Section 8.4.1.
As described in Section 8.5.1, one solution to formation control is the
virtual leader/virtual structure approach. Figure 10.1 shows an illustrative
example of the virtual leader/virtual structure approach with a formation
composed of four vehicles with planar motions, where C o represents the iner-
tial frame and C represents a virtual coordinate frame located at a virtual
F
center(x ,y )withanorientationθ relativetoC .InFig.10.1,r =[x ,y ]T
|     | c c |     |     | c   | o   | j j j |
| --- | --- | --- | --- | --- | --- | ----- |
andrd =[xd,yd]T
|     |       | represent,respectively,the |     |     | jth vehicle’sactualanddesired |     |
| --- | ----- | -------------------------- | --- | --- | ----------------------------- | --- |
|     | j j j |                            |     |     |                               |     |
position, and rd = [xd ,yd ]T represents the desired deviation of the jth
|         | jF       |              | jF jF |     |     |     |
| ------- | -------- | ------------ | ----- | --- | --- | --- |
| vehicle | relative | to C , where |       |     |     |     |
F

| 194 | 10 Distributed | Formation         | Control           | with       | a Virtual | Leader           |          |
| --- | -------------- | ----------------- | ----------------- | ---------- | --------- | ---------------- | -------- |
|     | (cid:22)       | (cid:23) (cid:22) | (cid:23) (cid:22) |            |           | (cid:23)(cid:22) | (cid:23) |
|     | xd(t)          |                   |                   | (t)]−sin[θ |           |                  | xd       |
|     |                | x                 | c (t)             | cos[θ c    |           | c (t)]           | (t)      |
|     | j              | =                 | +                 |            |           |                  | jF .     |
|     | yd(t)          | y                 | (t)               | sin[θ (t)] | cos[θ     | (t)]             | yd (t)   |
|     | j              |                   | c                 | c          | c         |                  | jF       |
If each vehicle can track its desired position accurately, then the desired for-
mation shape can be preserved accurately. Note that Fig. 10.1 relies on the
assumption that each vehicle knows the state of the virtual coordinate frame
(i.e.,virtualcenterpositionandorientation),denotedasξ =[x ,y ,θ ]T.Note
|     |     |     |     |     |     |     | c c c |
| --- | --- | --- | --- | --- | --- | --- | ----- |
that here ξ is the coordination variable for the team. However, as described
| in Section | 8.4.1, a | centralized | scheme | is restrictive. |     |     |     |
| ---------- | -------- | ----------- | ------ | --------------- | --- | --- | --- |
r d
jF
r
|     |     | j   | rd  |     |     |        |     |
| --- | --- | --- | --- | --- | --- | ------ | --- |
|     |     |     | j   |     | (x  | ,y ,θ) |     |
c c c
C
F
C
o
Fig. 10.1. A formation composed of four vehicles with a known virtual center
Wheneachvehiclehasinconsistentunderstandingorknowledgeofξdueto
dynamicallychangingsituationalawarenessorunreliable/limitedinformation
exchange, the desired formation geometry cannot be maintained, as shown
in Fig. 10.2, where C Fj represents the jth vehicle’s understanding of the
virtual coordinate frame with state ξ = [x ,y ,θ ]T. Here ξ denotes the
|               |               |     |        | j            | cj cj     | cj  | j   |
| ------------- | ------------- | --- | ------ | ------------ | --------- | --- | --- |
| jth vehicle’s | instantiation |     | of the | coordination | variable. |     |     |
Next, we propose the unified, distributed architecture for formation con-
trolthatisinFig.10.3.The proposedarchitectureconsistsofthreehierarchi-
cal layers: a consensus tracking module, a consensus-based formation control
module,andthephysicalvehicle.InFig.10.3,N (t)andJ (t)denote,respec-
|     |     |     |     |     | i   |     | i   |
| --- | --- | --- | --- | --- | --- | --- | --- |
tively,thesetofvehicleswhoseinstantiationsofthecoordinationvariableand
positiontrackingerrorsareavailabletovehicleiattimet.Theobjectiveofthe
consensustrackingmoduleistodriveξ toξr =[xr,yr,θr]T,whichrepresents
|     |     |     |     | i   |     | c c c |     |
| --- | --- | --- | --- | --- | --- | ----- | --- |
thereferenceforthecoordinationvariable(i.e.,thedesiredstateofthevirtual
coordinate frame). As in Chapter 3, suppose that virtual vehicle n+1 acts
(cid:2)
as the virtualleader of the team with stateξ =ξr.We use directed graph
n+1
| Gc =(Vc | ,Ec     | )tomodeltheinteractiontopologyforξ |     |     |     |     | amongthen+1 |
| ------- | ------- | ---------------------------------- | --- | --- | --- | --- | ----------- |
| n+1     | n+1 n+1 |                                    |     |     |     |     | i           |

|     |     |     | 10.1 Distributed | Formation Control | Architecture |     | 195 |
| --- | --- | --- | ---------------- | ----------------- | ------------ | --- | --- |
Fig. 10.2. A formation composed of four vehicles with inconsistent understanding
| of the virtual   | coordinate | frame  |        |             |       |      |     |
| ---------------- | ---------- | ------ | ------ | ----------- | ----- | ---- | --- |
| vehicles,whereVc |            |        | set,Ec |             | andAc | =[ac |     |
|                  |            | is the | node   | is the edge | set,  |      | ]is |
|                  |            | n+1    |        | n+1         |       | n+1  | ij  |
the (n+1)×(n+1) adjacency matrix. The localcontrollaw u , i=1,...,n,
i
for each vehicle is based on its instantiation of the coordination variable and
| the position | tracking | errors | of its | neighbors. |     |     |     |
| ------------ | -------- | ------ | ------ | ---------- | --- | --- | --- |
Fig. 10.3. A unified, distributed architecture for formation control

196 10 Distributed Formation Control with a Virtual Leader
On the consensus tracking level, each vehicle applies a consensus tracking
algorithm as
(cid:2)n
1
u = ac (t)[ξ˙ −γ(ξ −ξ )]
i η (t) ij j i j
i
j=1
1
+ ac (t)[ξ˙r −γ(ξ −ξr)], i=1,...,n, (10.1)
η (t) i(n+1) i
i
where ac (t), i = 1,...,n, j = 1,...,n + 1, is the (i,j) entry of Ac ∈
ij (cid:7) n+1
R(n+1)×(n+1) at time t, γ is a positive scalar, and η (t)= (cid:2) n+1ac (t).
i j=1 ij
Remark 10.1. Note that ξr and ξ˙r are available only to the subgroup leaders
andthenumberofthesubgroupleaderscanbeanynumberfrom1ton.Note
alsothat(10.1)isadirectapplicationofconsensusalgorithm(3.4).According
to Theorems 3.8 and 3.11, algorithm (10.1) guarantees that ξ (t) → ξr(t),
i
i=1,...,n, as t→∞, if and only if Gc has a directed spanning tree.
n+1
Suppose that the vehicles have single-integrator dynamics given by
r˙ =u , i=1,...,n, (10.2)
i i
wherer ∈Rm isthe stateandu ∈Rm isthecontrolinputoftheithvehicle.
i i
On the vehicle control level, we apply a consensus algorithm as
(cid:2)n
u =r˙d−α (r −rd)− av[(r −rd)−(r −rd)], (10.3)
i i i i i ij i i j j
j=1
whereα isapositivescalar,av isthe(i,j)entryofthen×nadjacencymatrix
i ij
Av associated with the interaction topology Gv = (Vv,Ev) for r −rd,1 and
n n n n i i
rd =[xd,yd]T with
i i i
(cid:22) (cid:23) (cid:22) (cid:23) (cid:22) (cid:23)(cid:22) (cid:23)
xd x cos(θ ) −sin(θ ) xd
i = ci + ci ci iF .
yd y sin(θ ) cos(θ ) yd
i ci ci ci iF
Note that (10.3) is an application of algorithm (3.3).
Using(10.3),(10.2)canbewritteninmatrixformasr˜˙ =−[(Lv+Q)⊗I ]r˜,
n 2
where Lv is the n×n nonsymmetrical Laplacian matrix associated with Gv,
n n
(cid:2) (cid:2) (cid:2)
Q = diag(α ,...,α ), and r˜ = [r˜T,...,r˜T]T with r˜ = r − rd. Following
1 n 1 n i i i
the proof of Theorem 3.6, we know that under an arbitrary time-invariant
interaction topology, r˜(t) →0, that is, r (t) →rd(t), i= 1,...,n, as t →∞.
i i
Inotherwords,evenacontrollawu =r˙d−α (r −rd)issufficienttoguarantee
i i i i i
that r (t) → rd(t), i = 1,...,n, as t → ∞. However, the coupling between
i i
1 Notethattheinteraction topology ontheconsensustrackinglevelgivenbyG n c +1
isdifferentfromtheinteractiontopologyonthevehiclecontrollevelgivenbyGv.
n

|     |     | 10.2 | Experimental | Results | on a Multirobot | Platform | 197 |
| --- | --- | ---- | ------------ | ------- | --------------- | -------- | --- |
neighborsinduced by the third term in (10.3)improvesgrouprobustness and
| reduces formation |             | maintenance | error.  |            |       |          |     |
| ----------------- | ----------- | ----------- | ------- | ---------- | ----- | -------- | --- |
|                   |             |             |         | →          | ξr(t) | → rd(t), |     |
| With              | both (10.1) | and         | (10.3), | if ξ i (t) | and   | r i (t)  | i = |
i
1,...,n, as t → ∞, then the desired formation shape is maintained and the
state of the virtual coordinate frame follows the desired reference.
Remark 10.2. Note that both (10.1) and (10.3) are distributed in the sense
thatonlyinformationexchangeamongneighborsisrequired.Thearchitecture
shown in Fig. 10.3 accommodates an arbitrary number of subgroup leaders
and arbitrary coupling among vehicles on both the consensus tracking level
and the vehicle control level. The distributed nature of (10.1) and (10.3)
ensures robustness of the team to failure of follower vehicles. The introduc-
tionofmultiple subgroupleadersdoesnotmakethecontrolalgorithms(10.1)
and(10.3)ortheirconvergenceanalysismorecomplicated.Alsotheintroduc-
tionofmultiplesubgroupleadersreducestheriskofasinglepointfailurethat
is inherent in a team with a single subgroup leader. In addition, with (10.1)
and(10.3),eachvehiclesimplyexchangesinformationwithitsneighborswith-
| out the need      | to  | identify | the subgroup | leaders. | (cid:13)(cid:14) |          |     |
| ----------------- | --- | -------- | ------------ | -------- | ---------------- | -------- | --- |
| 10.2 Experimental |     |          | Results      | on a     | Multirobot       | Platform |     |
In this section, we validate the proposed distributed formation control archi-
tectureonamultirobotexperimentalplatform.Weconductexperimentswith,
respectively,asinglesubgroupleader,multiplesubgroupleaders,anddirected
| switching           | interaction | topologies. |          |                    |     |     |     |
| ------------------- | ----------- | ----------- | -------- | ------------------ | --- | --- | --- |
| 10.2.1 Experimental |             |             | Platform | and Implementation |     |     |     |
Experimental tests are conducted in the Mobile Robots Laboratory at USU.
The mobile robot test bed consists of five AmigoBots and two Pioneer 3-DX
shown in Fig. 10.4. The robots can communicate with each other through
ethernet with TCP/IP protocols. The robots rely on encoder data for their
| position | and orientation |     | information. |     |     |     |     |
| -------- | --------------- | --- | ------------ | --- | --- | --- | --- |
In our experiments, we emulate limited interrobot information exchange
by simply disallowing the use of information obtained from certain members
of the group, although every robot can share information with every other
robot. By doing so, we can test distributed cooperative control algorithms
that involve only neighbor-to-neighbor information exchange due to limited
| communication |     | or sensing. |     |     |     |     |     |
| ------------- | --- | ----------- | --- | --- | --- | --- | --- |
The fact that we use differentially driven mobile robots complicates the
coordination problem due to nonholonomic constraints. In the well-known
paper by Brockett [33], it was shown that nonholonomic systems cannot be
stabilized with continuous static state feedback. The implication for differen-
tially driven mobile robots is that the position and orientation of the center

| 198 10 | Distributed | Formation        |     | Control      | with a | Virtual Leader  |     |
| ------ | ----------- | ---------------- | --- | ------------ | ------ | --------------- | --- |
|        | Fig.        | 10.4. Multirobot |     | experimental |        | platform at USU |     |
of the robot cannot be simultaneously stabilized with a time-invariant, sta-
bilizing control strategy. Both discontinuous control laws [14,54] and time
varying[164,206]controllaws havebeen foundto stabilize the center ofrota-
tionandtheorientationofasinglerobot.Themultiplerobotcaseisnaturally
more complex.
(cid:2)
Definethe“hand”positionoftherobotasthepointh=[h ,h ]T thatlies
x y
adistance Lalongthe line thatis normalto the wheelaxisandintersectsthe
(cid:2)
wheel axis at the center point r = [r ,r ]T, as shown in Fig. 10.5. The kine-
|     |     |     |     | x   | y   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
L(cid:6)=0.
matics of the hand position are holonomic for In our experiments, we
considerthe problemofcoordinatingthe handpositions ofthe robotsinstead
ofcoordinatingtheircenterpositions.Althoughthisassumptionsimplifiesthe
control problem, it is of practical interest because the hand position may be
the point of interest. For example, if the robots are equipped with a gripper
located at the hand position and the coordination task is to move an ob-
ject from one location to another, then the objective is to move the gripper
locations in a coordinated fashion. Another example occurs when the group
objectiveisthe coordinatedplacementofsensorsthatarelocatedatthehand
position.
Let (r xi ,r yi ), θ i , and (v i ,ω i ) denote the inertial position, orientation, and
linear and angular speeds of the ith robot, respectively. The kinematic equa-
| tions for | the ith robot | are |     |     |     |     |     |
| --------- | ------------- | --- | --- | --- | --- | --- | --- |
θ˙
|          | r˙       | =v cos(θ | ),       | r˙ =v             | sin(θ    | ), =ω .  | (10.4) |
| -------- | -------- | -------- | -------- | ----------------- | -------- | -------- | ------ |
|          |          | xi i     | i        | yi                | i        | i i i    |        |
| The hand | position | is given | by       |                   |          |          |        |
|          |          | (cid:22) | (cid:23) | (cid:22) (cid:23) | (cid:22) | (cid:23) |        |
|          |          | h        |          | r                 | cos(θ    | )        |        |
|          |          |          | xi       | xi                |          | i        |        |
|          |          |          | =        | +L                | i        | .        | (10.5) |
|          |          | h        |          | r                 | sin(θ    | )        |        |
|          |          |          | yi       | yi                |          | i        |        |

10.2 Experimental Results on a Multirobot Platform 199
θ
(h , h )
x y
L
(r , r )
x y
Fig. 10.5. A nonholonomic differentially drivenwheeled mobile robot
Differentiating (10.5) with respect to time gives
(cid:22) (cid:23) (cid:22) (cid:23)(cid:22) (cid:23)
h˙ cos(θ )−L sin(θ ) v
xi = i i i i . (10.6)
h˙
yi
sin(θ
i
) L
i
cos(θ
i
) ω
i
Letting (cid:22) (cid:23) (cid:22) (cid:23)(cid:22) (cid:23)
v cos(θ ) sin(θ ) u
i = i i xi ,
ω − 1 sin(θ ) 1 cos(θ ) u
i Li i Li i yi
gives (cid:22) (cid:23) (cid:22) (cid:23)
h˙ u
xi = xi , (10.7)
h˙
yi
u
yi
whichisasimplifiedkinematicequationbutissufficientforthepurposeofour
application. Note that (10.7) takes in the form of single-integratordynamics,
implying that consensus algorithm (10.3) can be directly applied.
In our experiments, a team of four AmigoBots is required to maintain a
square formation, and the virtual coordinate frame located at the center of
the square follows a circle moving in a clockwise direction. In particular, the
reference state of the virtual coordinate frame ξr =[xr,yr,θr]T satisfies
c c c
x˙r =vrcos(θr), y˙r =vrsin(θr), θ˙r =ωr,
c c c c c c c c
where vr = 9π m/s, ωr = π rad/s, [xr(0),yr(0)] = (0,0) m, and θr(0) = 0
c 500 c 50 c c c
rad. In addition, we let L = 0.15 m, xd = (cid:2) cos(φ ), and yd = (cid:2) sin(φ ),
i jF j j jF j j
where(cid:2) =0.6mandφ =π−πj rad,j =1,...,4.Eachrobotapplies(10.1)
j j 4
toachievesconsensustrackingofthe referencestateξr and(10.3)tocompute
u and u .
xi yi
10.2.2 Formation Control with a Single Subgroup Leader
In this subsection, we consider a single subgroup leader with three followers.
Figure 10.6a shows the interaction topology on the consensus tracking level,
where node ξr denotes the virtual leader of the team, subscript L denotes

| 200 | 10 Distributed | Formation |     | Control with | a Virtual | Leader |     |
| --- | -------------- | --------- | --- | ------------ | --------- | ------ | --- |
a subgroup leader, subscript F denotes a follower, and an edge from node j
to node i implies that ac = 1 in (10.1). Figure 10.6b shows the interaction
ij
topology on the vehicle control level, where an edge from node j to node i
| implies | that av | =1 in (10.3). |     |     |     |     |     |
| ------- | ------- | ------------- | --- | --- | --- | --- | --- |
ij
(cid:30)(cid:30)
(cid:26)(cid:30)(cid:31)(cid:27)  (cid:28) !(cid:29) (cid:26)(cid:30)(cid:31)(cid:27)   (cid:28)!(cid:29) (cid:15)(cid:15) (cid:26)(cid:30) (cid:31)(cid:27)   (cid:28)!(cid:29) (cid:26)(cid:30)(cid:31)(cid:27)   (cid:28)!(cid:29) (cid:2)(cid:2) (cid:15)(cid:15) (cid:26)(cid:30) (cid:31)(cid:27)   (cid:28)!(cid:29)
|     | ξ r | 1   | 2                         |     |     |                                            |                      |
| --- | --- | --- | ------------------------- | --- | --- | ------------------------------------------ | -------------------- |
|     |     | L   | (cid:13) (cid:31)(cid:31) | F   |     | 1 L (cid:15)   (cid:15)                    | (cid:31)(cid:31) 2 F |
|     |     |     | (cid:13)                  |     |     | (cid:15)                                   | (cid:14) (cid:14)    |
|     |     |     | (cid:13) (cid:13)         |     |     | (cid:15) (cid:15) (cid:14)(cid:15)(cid:14) | (cid:14)             |
(cid:13)
|     |                |                                                                  | (cid:13) (cid:13)                                  |                  |       | (cid:14) (cid:14)                                                | (cid:15) (cid:15)                                  |
| --- | -------------- | ---------------------------------------------------------------- | -------------------------------------------------- | ---------------- | ----- | ---------------------------------------------------------------- | -------------------------------------------------- |
|     |                | (cid:14)(cid:14)                                                 | (cid:13)                                           | (cid:14)(cid:14) |       | (cid:14)(cid:14) (cid:14)                                        | (cid:15) (cid:14)(cid:14)                          |
|     |                |                                                                  | (cid:13)                                           |                  |       | (cid:14)                                                         |                                                    |
|     |                | (cid:26)(cid:30)(cid:31)(cid:27) (cid:28)!(cid:29)(cid:2)(cid:2) | (cid:26)(cid:30)(cid:31)(cid:27) (cid:28)!(cid:29) |                  |       | (cid:26)(cid:30)(cid:31)(cid:27) (cid:28)!(cid:29)(cid:2)(cid:2) | (cid:26)(cid:30)(cid:31)(cid:27) (cid:28)!(cid:29) |
|     |                | 4                                                                | 3                                                  |                  |       | 4                                                                | 3                                                  |
|     |                | F                                                                |                                                    | F                |       | F                                                                | F                                                  |
|     | (a) Consensus  |                                                                  | tracking                                           |                  | (b)   | Vehicle control                                                  |                                                    |
|     | level topology |                                                                  |                                                    |                  | level | topology                                                         |                                                    |
Fig. 10.6. Interaction topologies with a single subgroup leader and threefollowers
Figure 10.7 shows the experimental result with a single subgroup leader
andthreefollowers.Inparticular,Fig.10.7ashowsthetrajectoriesofthefour
robots at t ∈ [0,t ] s and snapshots at t = 0,tf,2tf s, where t is the end
|     |     | f   |     |     |     |     | f   |
| --- | --- | --- | --- | --- | --- | --- | --- |
3 3
of the experiment. Figure 10.7b shows the relative position errors,defined as
thedifferencebetweenthedesiredandactualseparationdistancebetweenthe
robots.Figure10.7c(cid:25)showstheconsensustrackingerrorsforthevirtualcenter
position,definedas (xr −x )2+(yr −y )2,where(xr,yr)isthe reference
|     |     |     | c ci | c   | ci  | c c |     |
| --- | --- | --- | ---- | --- | --- | --- | --- |
virtualcenter positionknownby the subgroupleader.Figure10.7dshowsthe
consensustrackingerrorsforthevirtualcenterorientation,definedasθr−θ
ci ,
c
where θr is the reference virtual center orientation known by the subgroup
c
leader. Note that the team is able to travel in tight formation around the
−3
circle as shownin Fig. 10.7awith relative position errorsbetween cm and
5 cm as shown in Fig. 10.7b. Also note that the consensus tracking errorsfor
the virtual center position are below 1.6 cm, as shown in Fig. 10.7c, and the
consensus tracking errors for the virtual center orientationare between 0.06◦
| and 0.08◦, | as shown  | in Fig. | 10.7d. |          |          |         |     |
| ---------- | --------- | ------- | ------ | -------- | -------- | ------- | --- |
| 10.2.3     | Formation | Control | with   | Multiple | Subgroup | Leaders |     |
In this subsection, we consider two subgroup leaders with two followers. Fig-
ures 10.8a and 10.8b show the interaction topologies on the consensus track-
ing level and the vehicle control level, respectively. The experimental result
is shown in Fig. 10.9.Note that good formationmaintenance is also achieved
with multiple subgroup leaders involved. The introduction of multiple sub-
groupleadersincreasesthe robustnessofthe wholeteaminthe caseoffailure
of a certain subgroup leader. In addition, compared to the single subgroup

10.2 Experimental Results on a Multirobot Platform 201
500
0 t = 0 (s)
−500
−1000
t = 2tf/3 (s)
−1500
t = tf/3 (s)
−2000
−2500
−1500 −1000 −500 0 500 1000 1500
X position (mm)
)mm(
noitisop
Y
5
Robot1
R R o o b b o o t t 2 3 4 Robot4
3
2
1
0
−1
−2
−3
0 50 100 150 200 250
Time (s)
(a) Robot trajectories
)mc(
rorrE
Robot1−Robot2
Robot2−Robot3 Robot3−Robot4 Robot4−Robot1
(b) Relative position errors
1.6
1.4
1.2
1
0.8
0.6
0.4
0.2
0
0 50 100 150 200
Time (s)
)mc(
rorrE
VC−Robot2 0.08
VC−Robot3 VC−Robot4
0.06
0.04
0.02
0
−0.02
−0.04
−0.06
0 50 100 150 200
Time (s)
(c) Consensus tracking errors for the
virtualcenter position
)seerged(
rorrE
VC−Robot2
VC−Robot3 VC−Robot4
(d) Consensus trackingerrors for the
virtual centerorientation
Fig. 10.7. Experimentalresultofasquareformation withasinglesubgroupleader
and three followers
leader case, the existence of multiple subgroup leaders reduces the consensus
trackingerrorsbecausemorevehicleshavedirectaccesstothereferencestate.
10.2.4 Formation Control with Dynamically Changing Subgroup
Leaders and Interrobot Interaction Topologies
In this subsection, we consider the case where the subgroup leaders are dy-
namicallychangingandthedirectedinterrobotinteractiontopologiesarealso
dynamically changing. We assume that directed graph Gc(t) switches ran-
5
domlyfromtheset{Gc ,...,Gc },asshowninFig.10.10,withaswitching
5(1) 5(6)
time of approximately 10 seconds. Note that each Gc , i = 1,...,6, has a
5(i)
directedspanning tree with node ξr as the root.We assume thatthe directed
graph Gv(t) is the same as Gc(t) with node ξr removed.
4 5

202 10 Distributed Formation Control with a Virtual Leader
(cid:30)(cid:30)
(cid:26)(cid:30)(cid:31)(cid:27) ξ (cid:28) r !(cid:29) (cid:26)(cid:30)(cid:31)(cid:27)
!!
1 L (cid:28)!(cid:29)
(cid:13) (cid:13) (cid:13) (cid:13) (cid:13)
(cid:13) (cid:13) (cid:13) (cid:15)(cid:15) (cid:13) (cid:26)(cid:30) (cid:31)(cid:31) (cid:31)(cid:27) 2 F
(cid:14)(cid:14)
(cid:28)!(cid:29) (cid:26)(cid:30)(cid:31)(cid:27) 1 L
(cid:14)(cid:14)
(cid:28)!(cid:29)
(cid:14)
(cid:15)
(cid:14)
(cid:15) (cid:2)(cid:2)
(cid:14)
(cid:15)
(cid:14)
(cid:15)
(cid:14)
(cid:15)(cid:14)(cid:15) (cid:14)
(cid:15)
(cid:14)
(cid:15)
(cid:15)(cid:15) (cid:14)
(cid:15)
(cid:26)(cid:30) (cid:31)(cid:31) (cid:31)(cid:27) 2 F
(cid:14)(cid:14)
(cid:28)!(cid:29)
(cid:26)(cid:30)(cid:31)(cid:27) (cid:28)!(cid:29) (cid:26)(cid:30)(cid:31)(cid:27) (cid:28)!(cid:29) (cid:26)(cid:30)(cid:31)(cid:27) (cid:28)!(cid:29)(cid:2)(cid:2) (cid:26)(cid:30)(cid:31)(cid:27) (cid:28)!(cid:29)
4 3 4 3
L F L F
(a) Consensus tracking (b) Vehicle control
level topology level topology
Fig. 10.8. Interaction topologies with two subgroup leaders and two followers
Figure 10.11 shows the experimental result with dynamically changing
subgroup leaders under directed switching interrobot interaction topologies.
AsshowninFig.10.11b,therelativepositionerrorsarebetween−6cmand5
cm in our experiment. As shown in Fig. 10.11c,the consensus tracking errors
forthe virtualcenterpositionarebelow1.6cm.Figure 10.11dshowsthatthe
consensustrackingerrorsforthe virtualcenterorientationarebetween−0.1◦
and 0.15◦. Compared to the previous two cases, the errors in this case are
a bit larger. However, the four robots can still maintain a tight formation,
even when both the subgroup leaders and the directed interrobot interaction
topologies are dynamically changing.
10.3 Notes
The results in this chapter are based mainly on [197,222].
Acknowledgment is given to
(cid:10)c2007IEEE.Reprinted,withpermission,fromNathanSorensenandWei
Ren, “A unified formation control scheme with a single or multiple leaders,”
Proceedings of the American Control Conference, pp. 5412–5418, New York
City, 2007.
(cid:10)c2007 Elsevier. Reprinted, with permission, from Wei Ren and Nathan
Sorensen, “Distributed coordination architecture for multi-robot formation
control,” Robotics and Autonomous Systems, 2007 (to appear).

|     |     |           |        |     |     | 10.3 | Notes         | 203 |
| --- | --- | --------- | ------ | --- | --- | ---- | ------------- | --- |
| 500 |     |           |        | 3   |     |      |               |     |
|     |     |           | Robot1 |     |     |      | Robot1−Robot2 |     |
|     |     |           | Robot2 |     |     |      | Robot2−Robot3 |     |
|     | 0   | t = 0 (s) | Robot3 | 2   |     |      | Robot3−Robot4 |     |
|     |     |           | Robot4 |     |     |      | Robot4−Robot1 |     |
1
−500
)mm( noitisop Y
)mc( rorrE 0
−1000
t = 2tf/3 (s)
−1
| −1500 |     |     | t = tf/3 (s) |     |     |     |     |     |
| ----- | --- | --- | ------------ | --- | --- | --- | --- | --- |
−2
| −2000 |       |                    |           | −3   |              |          |        |           |
| ----- | ----- | ------------------ | --------- | ---- | ------------ | -------- | ------ | --------- |
| −2500 |       |                    |           | −4   |              |          |        |           |
| −1500 | −1000 | −500 0 500         | 1000 1500 | 0    | 50           | 100 150  | 200    | 250       |
|       |       | X position (mm)    |           |      |              | Time (s) |        |           |
|       | (a)   | Robot trajectories |           |      | (b) Relative | position | errors |           |
| 0.9   |       |                    |           | 0.06 |              |          |        |           |
|       |       |                    | VC−Robot2 |      |              |          |        | VC−Robot2 |
| 0.8   |       |                    | VC−Robot3 | 0.05 |              |          |        | VC−Robot3 |
| 0.7   |       |                    |           | 0.04 |              |          |        |           |
| 0.6   |       |                    |           | 0.03 |              |          |        |           |
)seerged( rorrE
| )mc( rorrE |     |     |     | 0.02 |     |     |     |     |
| ---------- | --- | --- | --- | ---- | --- | --- | --- | --- |
0.5
0.01
0.4
0
0.3
−0.01
0.2
−0.02
| 0.1 |     |          |         | −0.03   |     |          |     |     |
| --- | --- | -------- | ------- | ------- | --- | -------- | --- | --- |
|     | 0   |          |         | −0.04   |     |          |     |     |
|     | 0   | 50 100   | 150 200 | 0       | 50  | 100      | 150 | 200 |
|     |     | Time (s) |         |         |     | Time (s) |     |     |
(c) Consensus tracking errors for the (d) Consensus trackingerrors for the
| virtualcenter |     | position |     | virtual | centerorientation |     |     |     |
| ------------- | --- | -------- | --- | ------- | ----------------- | --- | --- | --- |
Fig. 10.9. Experimental result of a square formation with two subgroup leaders
and two followers

204 10 Distributed Formation Control with a Virtual Leader
(cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25) (cid:15)(cid:15)(cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25) (cid:15)(cid:15)(cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25) (cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25) (cid:15)(cid:15)(cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25) (cid:15)(cid:15)(cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25)
ξr 1 L(cid:20)(cid:20) (cid:16) (cid:16)2 F ξr 1 L (cid:7) (cid:7) (cid:7) 2 F(cid:20)(cid:20)
(cid:16) (cid:7)
(cid:16)(cid:16)
(cid:16) (cid:7)(cid:7)
(cid:7)
(cid:16) (cid:7)
(cid:16) (cid:7)
(cid:10)(cid:10)(cid:16) (cid:22)(cid:22)
(cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25)(cid:2)(cid:2) (cid:15)(cid:15)(cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25) (cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25)(cid:2)(cid:2) (cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25)
4 3 4 3
F F F F
Gc Gc
5(1) 5(2)
(cid:3)(cid:3)
(cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25) (cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25)(cid:2)(cid:2) (cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25) (cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25) (cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25) (cid:15)(cid:15)(cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25)
ξr 1 F(cid:20)(cid:20) (cid:7)(cid:7) (cid:7) (cid:7) (cid:7) (cid:7) (cid:7) (cid:7) (cid:7)(cid:22)(cid:22) 2 L ξr(cid:7) (cid:7) (cid:7) (cid:7) (cid:7)(cid:7) (cid:7) (cid:7) (cid:7) "" 1 F(cid:20)(cid:20) (cid:16) (cid:16) (cid:16) (cid:16) (cid:16) (cid:16) (cid:16) (cid:16) (cid:16) ##2 F (cid:14)(cid:14)
(cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25)(cid:2)(cid:2) (cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25) (cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25)(cid:2)(cid:2) (cid:18)(cid:22)(cid:19)(cid:23)(cid:20)(cid:24)(cid:21)(cid:25)
4 3 4 3
F F L F
Gc Gc
5(3) 5(4)
(cid:3)(cid:3)
(cid:18)(cid:22)(cid:19)(cid:23) ξ (cid:20)(cid:24) r (cid:21)(cid:25) (cid:7)(cid:17) (cid:7) (cid:17) (cid:7) (cid:17) (cid:7) (cid:17) (cid:7) (cid:7) (cid:17) (cid:7) (cid:17) (cid:7) (cid:17) (cid:7) (cid:18) (cid:18) (cid:22) (cid:22) (cid:17) "" 1 (cid:19) (cid:19) (cid:23) (cid:23) (cid:17) F (cid:20) (cid:20) (cid:24) (cid:24) (cid:14)(cid:14) (cid:17) (cid:21) (cid:21) (cid:25) (cid:25) (cid:10)(cid:10)(cid:16) (cid:17) (cid:2)(cid:2) (cid:16) (cid:17) (cid:16)(cid:17)(cid:16) (cid:17) (cid:16) (cid:16) (cid:17) (cid:16) (cid:17) (cid:16) (cid:17) (cid:16) (cid:15)(cid:15) (cid:15)(cid:15)(cid:3)(cid:3) (cid:18) (cid:18) (cid:22) (cid:22) 2 (cid:19) (cid:19) (cid:23) (cid:23) F (cid:20) (cid:20) (cid:24) (cid:24) (cid:20)(cid:20) (cid:21) (cid:21) (cid:25) (cid:25) (cid:18)(cid:22)(cid:19)(cid:23) ξ (cid:20)(cid:24) r (cid:21)(cid:25) (cid:7)(cid:7) (cid:7) (cid:7) (cid:7) (cid:7) (cid:7)(cid:7) (cid:7) (cid:15)(cid:15)(cid:18) (cid:18) (cid:22) (cid:22) "" 1 (cid:19) (cid:19) (cid:23) (cid:23) L (cid:20) (cid:20) (cid:24) (cid:24) (cid:14)(cid:14) (cid:20)(cid:20) (cid:21) (cid:21) (cid:25) (cid:25) (cid:2)(cid:2) (cid:15)(cid:15) (cid:15)(cid:15)(cid:18) (cid:18) (cid:22) (cid:22) 2 (cid:19) (cid:19) (cid:23) (cid:23) L (cid:20) (cid:20) (cid:24) (cid:24) (cid:14)(cid:14) (cid:21) (cid:21) (cid:25) (cid:25)
4 3 4 3
L L L F
Gc Gc
5(5) 5(6)
Fig. 10.10. Directed switching graphs of G 5 c(t)

|      |           |             |     | 10.3 | Notes 205     |
| ---- | --------- | ----------- | --- | ---- | ------------- |
| 500  |           |             | 6   |      |               |
|      |           | Robot1      |     |      | Robot1−Robot2 |
|      |           | Robot2      |     |      | Robot2−Robot3 |
| 0    | t = 0 (s) | R o b o t 3 | 4   |      | Robot3−Robot4 |
|      |           | R o b o t 4 |     |      | Robot4−Robot1 |
| −500 |           |             | 2   |      |               |
)mm( noitisop Y
)mc( rorrE
| −1000 |     |     | 0   |     |     |
| ----- | --- | --- | --- | --- | --- |
t = tf/3 (s)
| −1500 t = 2tf/3 (s) |                 |           | −2   |          |         |
| ------------------- | --------------- | --------- | ---- | -------- | ------- |
| −2000               |                 |           | −4   |          |         |
| −2500               |                 |           | −6   |          |         |
| −1500 −1000         | −500 0 500      | 1000 1500 | 0    | 50 100   | 150 200 |
|                     | X position (mm) |           |      | Time (s) |         |
(a) Trajectories of thefour robots (b) Relativeposition errors
| 1.6 |     |           | 0.15 |     |           |
| --- | --- | --------- | ---- | --- | --------- |
|     |     | VC−Robot1 |      |     | VC−Robot1 |
| 1.4 |     | VC−Robot2 |      |     | VC−Robot2 |
|     |     | VC−Robot3 |      |     | VC−Robot3 |
|     |     | VC−Robot4 | 0.1  |     | VC−Robot4 |
1.2
| 1          |     |     | )seerged( rorrE |     |     |
| ---------- | --- | --- | --------------- | --- | --- |
| )mc( rorrE |     |     | 0.05            |     |     |
0.8
| 0.6 |     |     | 0   |     |     |
| --- | --- | --- | --- | --- | --- |
0.4
−0.05
0.2
| 0   |     |     | −0.1   |     |     |
| --- | --- | --- | ------ | --- | --- |
0 20 40 60 80 100 120 140 160 180 0 20 40 60 80 100 120 140 160 180
|     | Time (s) |     |     | Time (s) |     |
| --- | -------- | --- | --- | -------- | --- |
(c)Consensustrackingerrorsforthe (d)Consensustrackingerrorsforthe
| virtualcenter | position |     | virtual | center orientation |     |
| ------------- | -------- | --- | ------- | ------------------ | --- |
Fig. 10.11. Experimental result of a square formation with dynamically changing
subgroup leaders underdirected switching interrobot interaction topologies

11
| Decentralized |        |     | Behavioral |     | Approach  |     | to        |     |
| ------------- | ------ | --- | ---------- | --- | --------- | --- | --------- | --- |
| Wheeled       | Mobile |     | Robot      |     | Formation |     | Maneuvers |     |
Inthis chapter,we apply the designscheme inSection8.4.2to formationma-
neuvers for a groupof wheeled mobile robots.Complex formation maneuvers
are decomposed into a sequence of maneuvers between formation patterns.
We present three decentralized behavior-based formation control strategies.
The first strategy uses relative position information configured in a bidirec-
tional ring topology to maintain the formation. The second strategy injects
interrobot damping via passivity techniques. The third strategy accounts for
actuator saturation.Hardwareresults on differentially drivenwheeled mobile
robots demonstrate the effectiveness of the proposed control strategies.
| 11.1 Problem |     | Statement |     |     |     |     |     |     |
| ------------ | --- | --------- | --- | --- | --- | --- | --- | --- |
The objective of this chapter is to introduce the coupled dynamics approach
toformationcontrolforagroupofwheeledmobilerobots,whichisabehavior-
based strategy. The approach is a direct application of the design scheme in
Section 8.4.2. The chapter provides a rigorous analysis of formation keeping
and convergence which is a contribution to behavior-based literature. Fur-
thermore, our approach has the advantage that it can be implemented when
only neighbor position information is available (i.e., velocity information is
| not required) | thereby | reducing |     | the communication |     | overhead. |     |     |
| ------------- | ------- | -------- | --- | ----------------- | --- | --------- | --- | --- |
InChapter10,weconsiderkinematicmodelsofmobilerobots.Incontrast,
wewillconsiderdynamicmodelsinthischapter.Eachrobothasthefollowing
| dynamic equations |     | of motion: |     |     |     |     |     |     |
| ----------------- | --- | ---------- | --- | --- | --- | --- | --- | --- |
|                   |     | ⎡          | ⎤ ⎡ |     | ⎤ ⎡ | ⎤   |     |     |
0 0
|     |     | r˙ xi   |     | v i cos(θ i | )    |           |          |        |
| --- | --- | ------- | --- | ----------- | ---- | --------- | -------- | ------ |
|     |     | ⎢       | ⎥ ⎢ |             | ⎥ ⎢  | ⎥(cid:22) | (cid:23) |        |
|     |     | ⎢ r˙ i⎥ | ⎢   | v si n (θ   | )⎥ ⎢ | 0 0 ⎥     |          |        |
|     |     | ⎢ y     | ⎥ ⎢ | i i         | ⎥ ⎢  | ⎥         | F        |        |
|     |     | θ ˙     | =   | ω           | +    | 0 0       | i ,      | (11.1) |
|     |     | ⎢ i     | ⎥ ⎢ | i           | ⎥ ⎢  | ⎥         |          |        |
|     |     | ⎣       | ⎦ ⎣ |             | ⎦ ⎣  | 1 ⎦       | τ i      |        |
|     |     | v˙      |     | 0           |      | 0         |          |        |
|     |     | i       |     |             |      | mi        |          |        |
|     |     | ω˙      |     | 0           |      | 0 1       |          |        |
|     |     | i       |     |             |      | Ji        |          |        |

208 11 Decentralized Behavioral Approach to Formation Maneuvers
wherer =[r ,r ]T isthe inertialpositionoftheithrobot,θ isthe orienta-
i xi yi i
tion,v isthelinearspeed,ω istheangularspeed,τ istheappliedtorque,F
i i i i
is the applied force, m is the mass, and J is the moment of inertia. Letting
i i
(cid:2) (cid:2)
x = [r ,r ,θ ,v ,ω ]T and u = [F ,τ ]T, the equations of motion can be
i xi yi i i i i i i
written as
x˙ =f(x )+g u , (11.2)
i i i i
where the definitions of f and g can be inferred from (11.1).
i
As in Chapter 10, we will focus on formation control of the robot hand
(cid:2)
positions h = [h ,h ]T defined by (10.5). The derivative of h is given
i xi yi i
by (10.6). The second-order derivative of h is given by
i
(cid:22) (cid:23) !(cid:22) (cid:23)
h¨ = −v i ω i sin(θ i )−L i ω i 2cos(θ i ) + m 1 i cos(θ i )−L Ji i sin(θ i ) F i .
i v ω cos(θ )−L ω2sin(θ ) 1 sin(θ ) Li cos(θ ) τ
i i i i i i mi i Ji i i
Because !
1 cos(θ )−Li sin(θ ) L
det mi i Ji i = i (cid:6)=0,
1 sin(θ ) Li cos(θ ) m J
mi i Ji i i i
system (11.2) with output (10.5) has a constant relative degree equal to two
andcanthereforebe output feedback linearized[96]aboutthe handposition.
Toward that end, define the map ψ :R5 →R5 as
⎡ ⎤
r +L cos(θ )
xi i i
⎢ ⎥
⎢ r yi +L i sin(θ i ) ⎥
ζ
i
=ψ(x
i
)= (cid:2) ⎢ ⎢v
i
cos(θ
i
)−L
i
ω
i
sin(θ
i
) ⎥ ⎥. (11.3)
⎣ ⎦
v sin(θ )+L ω cos(θ )
i i i i i
θ
i
The map ψ is a diffeomorphism whose inverse is given by
⎡ ⎤
ζ −L cos(ζ )
1i i 5i
⎢ ⎢ ζ 2i −L i sin(ζ 5i ) ⎥ ⎥
x i =ψ −1(ζ i )= ⎢ ⎢ ζ 5i ⎥ ⎥.
⎣ 1ζ cos(ζ )+ 1ζ sin(ζ ) ⎦
2 3i 5i 2 4i 5i
− 1 ζ sin(ζ )+ 1 ζ cos(ζ )
2Li 3i 5i 2Li 4i 5i
In transformed coordinates, (11.2) and (10.5) are given by
(cid:22) (cid:23) (cid:22) (cid:23)
ζ˙ ζ
1i = 3i ,
(cid:22)
ζ˙
2i (cid:23) (cid:22)
ζ
4i (cid:23) !
ζ˙ 3i = −v i ω i sin(θ i )−L i ω i 2cos(θ i ) + m 1 i cos(θ i )−L Ji i sin(θ i ) u ,
ζ˙
4i
v
i
ω
i
cos(θ
i
)−L
i
ω
i
2sin(θ
i
)
m
1
i
sin(θ
i
) L
Ji
i cos(θ
i
) i
1 1
ζ˙ =− ζ sin(ζ )+ ζ cos(ζ ).
5i 3i 5i 4i 5i
2L 2L
i i

|     |                 |             |         |     | 11.2          | Formation | Maneuvers | 209       |
| --- | --------------- | ----------- | ------- | --- | ------------- | --------- | --------- | --------- |
| The | output feedback | linearizing | control |     | [96] is given | by        |           |           |
|     |                 |             | !       | 2   | (cid:22)      |           |           | (cid:23)3 |
−1
|     | 1 cos(θ | )−L i     | sin(θ ) |     | −v ω sin(θ    | )−L | ω 2cos(θ | )   |
| --- | ------- | --------- | ------- | --- | ------------- | --- | -------- | --- |
| u   | = m i   | i Ji      | i       | ν − | i i           | i   | i i      | i , |
|     | i 1     | Li        |         | i   |               | )−L | ω2sin(θ  |     |
|     | sin(θ   | i ) cos(θ | i )     |     | v i ω i cos(θ | i   | i        | i ) |
|     | mi      | Ji        |         |     |               |     | i        |     |
(11.4)
which gives
|     |     | (cid:22) (cid:23) | (cid:22) (cid:23) |     |     |     |     |     |
| --- | --- | ----------------- | ----------------- | --- | --- | --- | --- | --- |
ζ˙ ζ
|     |     | 1i = | 3i , |     |     |     |     |     |
| --- | --- | ---- | ---- | --- | --- | --- | --- | --- |
ζ˙
|     |     |     | ζ 4i |     |     |     |     |     |
| --- | --- | --- | ---- | --- | --- | --- | --- | --- |
(cid:22) 2i (cid:23)
ζ˙
|     |     | 3i =ν | ,   |     |     |     |     |     |
| --- | --- | ----- | --- | --- | --- | --- | --- | --- |
ζ˙ i
4i
|     |     | ζ˙ =− | 1                  |       | 1    |       |     |     |
| --- | --- | ----- | ------------------ | ----- | ---- | ----- | --- | --- |
|     |     |       | ζ                  | sin(ζ | )+ ζ | cos(ζ | ),  |     |
|     |     | 5i    | 2L 3i              | 5i    | 2L   | 4i    | 5i  |     |
|     |     |       | (cid:22) (cid:23)i |       | i    |       |     |     |
ζ
|     |     | h = | 1i . |     |     |     |     |     |
| --- | --- | --- | ---- | --- | --- | --- | --- | --- |
i ζ
2i
The last equation represents the internaldynamics which are rendered unob-
servable and uncontrollable by transformation (11.3). Zero dynamics [96] are
| foundbysettingζ |     | =···=ζ | =0togetζ˙ |     | =0.Thereforethe |     | zerodynam- |     |
| --------------- | --- | ------ | --------- | --- | --------------- | --- | ---------- | --- |
|                 |     | 1i     | 4i        |     | 5i              |     |            |     |
]T
ics are stable, but not asymptotically stable. Because ζ 5i = θ i and [ζ 3i ,ζ 4i
represent the velocity of the hand position, this implies that the angle θ will
i
| stop | moving | when the hand | position | stops | moving. |     |     |     |
| ---- | ------ | ------------- | -------- | ----- | ------- | --- | --- | --- |
In the remainder of the chapter, the input-output dynamics of eachrobot
| will | be represented | by the | double-integrator |     | system, |     |     |     |
| ---- | -------------- | ------ | ----------------- | --- | ------- | --- | --- | --- |
h¨
|     |     |     |     | i =ν | i . |     |     | (11.5) |
| --- | --- | --- | --- | ---- | --- | --- | --- | ------ |
Remark 11.1. Feedbacklinearizationaboutthehandpositionwasusedin[164]
for kinematic models. This section has extended the approach to dynamic
models and has explicitly defined the internal dynamics. Note that (11.5)
takes in the form of double-integratordynamics, implying that the consensus
algorithms in Chapters 4 and 5 can be applied directly. (cid:13)(cid:14)
| 11.2 | Formation | Maneuvers |     |     |     |     |     |     |
| ---- | --------- | --------- | --- | --- | --- | --- | --- | --- |
Inthissection,wedescribethetypesofformationmaneuversthatwillbecon-
sideredinthischapter.Letnbethenumberofmobilerobotsintheformation.
| A formation |     | pattern is defined | as  | a set |     |     |     |     |
| ----------- | --- | ------------------ | --- | ----- | --- | --- | --- | --- |
P ={hd,...,hd},
|     |     |     |     | 1   | n   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
wherehd
isthedesiredconstantlocationofthehandpositionoftheithrobot.
i
We will consider the class of formation control problems where the group of
robots is required to transition through a sequence of formation patterns P ,
j

210 11 Decentralized Behavioral Approach to Formation Maneuvers
j = 1,...,J, where we assume that the sequence of formation patterns is
designedto avoidrobotcollisions.We assumethatduring the transitionfrom
oneformationpatterntoanother,itisdesirableto maintaintherobotsinthe
| same shape | as  | the destination |     | pattern. |     |     |     |
| ---------- | --- | --------------- | --- | -------- | --- | --- | --- |
There are two competing objectives. The first objective is to move the
robots to their final destination, as specified in the formation pattern. The
second objective is to maintain formation during the transition. Consider a
simple translation,as shown in Fig. 11.1.The left triangle represents the for-
mationpatternatthestartofthe maneuver,andthe righttrianglerepresents
the desired formation pattern. Suppose that initially the bottom right robot
leads the formation, as shown in Fig. 11.1. The robot has two conflicting
objectives: move right to arrive at the final goal, and move left to regain for-
mation.Ifitmovesleft,itwilllikelyovershoottheformation,whichismoving
to the right, and if it moves right, it will take longer to regain formation as
| the others | are | required | to catch | up. |     |     |     |
| ---------- | --- | -------- | -------- | --- | --- | --- | --- |
h
1
|     |     |     | P   |     |     |     | P   |
| --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     | j   |     |     |     | j+1 |
Fig. 11.1. Bottom right member of theformation is initially too far to theright
To incorporate these two competing objectives, we will define error func-
tions for both. Let E be the total error between the current positions of the
g
| robots | and the | desired | formation | pattern: |     |     |     |
| ------ | ------- | ------- | --------- | -------- | --- | --- | --- |
(cid:2)n
|     |     |     |     | E = | h˜TK | h˜ , |     |
| --- | --- | --- | --- | --- | ---- | ---- | --- |
|     |     |     |     | g   | i g  | i    |     |
i=1
h˜ (cid:2) − hd
where K g is a symmetrical positive-definite matrix and i = h i (see
i
| Fig. 11.1). | Similarly, | define | E   | as the | formation | error |     |
| ----------- | ---------- | ------ | --- | ------ | --------- | ----- | --- |
f
(cid:2)
|     |     |     |     | (h˜ −h˜ |     | (h˜ −˜h |     |
| --- | --- | --- | --- | ------- | --- | ------- | --- |
|     |     | E   | =   |         | )TK |         | ),  |
|     |     | f   |     | i       | i+1 | f i     | i+1 |
i=<n>
where K is a symmetrical positive-semidefinite matrix and where the ro-
f
|     |     |     |     |     | h˜  | ˜h  | h˜ h˜ |
| --- | --- | --- | --- | --- | --- | --- | ----- |
bot index is defined modulo n, i.e., n+1 = 1 and 0 = n . The notation
i =< n > is used to indicate summation around the ring defined by the for-
mation pattern. By maintaining E small during the maneuver, the robots
f

|     |     |     |     |     | 11.3 | Formation Control | 211 |
| --- | --- | --- | --- | --- | ---- | ----------------- | --- |
will equalize the distance that they need to go to reach the final formation
pattern. Note that E =0 if andonly if h˜ =h˜ for all i.This is equivalent
|     |     | f      |     | i   | i+1 |     |     |
| --- | --- | ------ | --- | --- | --- | --- | --- |
|     | −h  | =hd−hd |     |     |     |     |     |
to sayingthat h i i+1 ,whichwill be true only if the robots are
|     |     |     | i   | i+1 |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
inthesamerelativeformationthattheywillhaveattheendofthemaneuver.
Therefore, when E = 0, the robots will be keeping formation, but they will
f
| not necessarily | be in | the final | formation | pattern. |     |     |     |
| --------------- | ----- | --------- | --------- | -------- | --- | --- | --- |
The total error for the formation coordination problem is the sum of E
g
and E f :
| E(t)=E | (t)+E     |          | (t)     |         |     |          |        |
| ------ | --------- | -------- | ------- | ------- | --- | -------- | ------ |
|        | (cid:2) f | (cid:29) | g       |         |     | (cid:30) |        |
|        |           | h˜TK     | h˜ +(h˜ | −h˜ )TK | (h˜ | −h˜      |        |
|        | =         |          | g i     | i i+1   | f i | i+1 ) ,  | (11.6) |
i
i=<n>
where K and K weigh the relative importance of formation keeping versus
| f   | g   |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
goal convergence. The formation control objective is to drive E(t) → 0, as
t→∞.
| 11.3 Formation |     | Control |     |     |     |     |     |
| -------------- | --- | ------- | --- | --- | --- | --- | --- |
In this section, we propose three control strategies for driving E(t) defined
in (11.6) to zero, given dynamics (11.5). The first approach is coupled dy-
namics formation control derived in Section 11.3.1. The coupled dynamics
approach couples the dynamics of the robots by incorporating relative posi-
tion and velocity information between neighbors in the controlstrategy.This
approachrequires that each robot knows the relative position and velocity of
two other robots (its neighbors in the communication ring), as well as their
desired positions in the target formation pattern. The second approach, de-
rived in Section 11.3.2, is coupled dynamics formation control with passivity
based interrobot damping. This formation control strategy is identical to the
coupled dynamics approach except that the requirement for relative velocity
is removed. The third approach, derived in Section 11.3.3, is the coupled dy-
namics approach with saturated control. This strategy modifies the coupled
dynamics approach so that convergence of E is guaranteed under actuator
| saturation     | constraints. |     |           |         |     |     |     |
| -------------- | ------------ | --- | --------- | ------- | --- | --- | --- |
| 11.3.1 Coupled | Dynamics     |     | Formation | Control |     |     |     |
In this section, we derive the coupled dynamics formation control strategy.
| The proposed | control | law   | is given | by  |         |     |        |
| ------------ | ------- | ----- | -------- | --- | ------- | --- | ------ |
|              |         | ν =−K | h˜ −D    | h˙  |         |     |        |
|              |         | i     | g i      | g i |         |     |        |
|              |         | −K    | (h˜ −h˜  | )−D | (h˙ −h˙ | )   |        |
|              |         |       | f i      | i−1 | f i     | i−1 |        |
|              |         | −K    | (h˜ −h˜  | )−D | (h˙ −h˙ |     |        |
|              |         |       |          |     |         | ),  | (11.7) |
|              |         |       | f i      | i+1 | f i     | i+1 |        |

212 11 Decentralized Behavioral Approach to Formation Maneuvers
where K and D are symmetrical positive-definite matrices, and K and
| g   | g   |     |     | f   |
| --- | --- | --- | --- | --- |
D are symmetricalpositive-semidefinite matrices. Note that (11.7) is an ap-
f
plication of consensus algorithm (5.10), where the interaction topology is a
| bidirectional | ring. |     |     |     |
| ------------- | ----- | --- | --- | --- |
Remark 11.2. The first two terms in (11.7) drive the robot to its final posi-
tion in the formation pattern (goal seeking behavior). The second two terms
maintain formation with the i− 1 robot, and the last two terms maintain
formation with the i+1 robot (formation keeping behavior). (cid:13)(cid:14)
Theorem 11.3.If robot formation (11.1) is subject to the control strategy
defined in (11.4) and (11.7), then error function (11.6) converges to zero
asymptotically.
h˙(0)
Furthermore, if the formation is initially at rest, i.e., = 0, where
h˙ (cid:2) [h˙T,...,h˙T]T,
| =   | then the | formation error is bounded | by  |     |
| --- | -------- | -------------------------- | --- | --- |
| 1   | n        |                            |     |     |
(cid:2)n
E(t)≤E(0)− h˙Th˙
|     |     | .   |     | (11.8) |
| --- | --- | --- | --- | ------ |
i i
i=1
The proof of this theorem and Theorem 11.7 are simplified by the use
of Kronecker product notation. The following lemma serves to establish our
notation and makes the derivations in the proofs of Theorems 11.3 and 11.7
more transparent.
Lemma 11.4.Let C be the circulant matrix with the first row given by
[2,−1,0,...,0,−1]∈Rn.
Then C ∈ Rn×n is symmetrical positive semidefinite. If ξ = [ξT,...,ξT]T,
1 n
| where ξ ∈Rp, | then |     |     |     |
| ------------ | ---- | --- | --- | --- |
i
(cid:2)
|     | (ξ −ξ | )TJ(ξ −ξ )=ξT(C⊗J)ξ. |     |     |
| --- | ----- | -------------------- | --- | --- |
|     | i     | i+1 i i+1            |     |     |
i=<n>
|     | −ξ  | −ξ  |     |     |
| --- | --- | --- | --- | --- |
If the terms J(ξ i i−1 )+J(ξ i i+1 ) are stacked in a column vector, the
(C⊗J)ξ.
| resulting vector | can be written | as  |     |     |
| ---------------- | -------------- | --- | --- | --- |
Proof: ThefirstpartisverifiedbynotingthatC isa (symmetrical)Laplacian
matrix associated with a bidirectional ring topology whose adjacency matrix
| A ]∈Rn×n |              | =i−1andj |          |     |
| -------- | ------------ | -------- | -------- | --- |
| =[a      | isdefinedasa | =1forj   | =i+1anda | =0  |
| n ij     |              | ij       |          | ij  |
otherwise.
| The second | fact is verified | as follows: |     |     |
| ---------- | ---------------- | ----------- | --- | --- |

11.3 Formation Control 213
⎡ ⎤
⎡ ⎤ T 2J −J ... −J ⎡ ⎤
ξT(C⊗J)ξ = ⎢ ⎣ ξ . . . 1 ⎥ ⎦ ⎢ ⎢ ⎢ ⎣ − . . J 2J ... 0 . . ⎥ ⎥ ⎥ ⎦ ⎢ ⎣ ξ . . . 1 ⎥ ⎦
. .
ξ ξ
n −J ... −J 2J n
=2ξTJξ −ξTJξ −ξTJξ
1 1 1 2 1 n
−ξTJξ +2ξTJξ −ξTJξ
1 2 2 2 2 3
.
.
.
−ξ n TJξ 1 −ξ n TJξ n−1 +2ξ n TJξ n
=ξTJξ −ξTJξ −ξTJξ +ξTJξ
1 1 1 2 2 1 2 2
+ξTJξ −ξTJξ −ξTJξ +ξTJξ
2 2 2 3 3 2 3 3
.
.
.
+ξTJξ −ξTJξ −ξTJξ +ξTJξ
n n n 1 1 n 1 1
=(ξ −ξ )TJ(ξ −ξ )
1 2 1 2
.
.
.
+(ξ −ξ )TJ(ξ −ξ )
(cid:2)n 1 n 1
= (ξ −ξ )TJ(ξ −ξ ).
i i+1 i i+1
i=<n>
The third claim is again shown by direct manipulation:
⎡ ⎤ ⎡ ⎤⎡ ⎤
J(ξ −ξ )+J(ξ −ξ ) 2J −J ... −J ξ
1 n 1 2 1
⎢ ⎢ J(ξ 2 −ξ 1 )+J(ξ 2 −ξ 3 ) ⎥ ⎥ ⎢ ⎢ −J 2J −J ... ⎥ ⎥ ⎢ ⎢ξ 2 ⎥ ⎥
⎢ . ⎥=⎢ . . ⎥⎢ . ⎥=(C⊗J)ξ.
⎣ . ⎦ ⎣ . . ⎦⎣ . ⎦
. . . .
J(ξ n −ξ n−1 )+J(ξ n −ξ 1 ) −J ... −J 2J ξ n
Proof of Theorem 11.3: Letting
h˜ = (cid:2) [h˜T,...,˜hT]T,
1 n
Lemma 11.4 can be used to write E as
E =h˜T(I ⊗K +C⊗K )h˜.
n g f
Consider the Lyapunov function candidate
(cid:2)n
1 1
V = E+ h˙Th˙ , (11.9)
2 2 i i
i=1
which is positive definite and radially unbounded with respect to h˜ and h˙ by
part (v) of Lemma C.8. Note that V can be written as

214 11 Decentralized Behavioral Approach to Formation Maneuvers
1 1
V = h˜T(I ⊗K +C⊗K )h˜+ h˙Th˙.
n g f
2 2
The time derivative of V is
(cid:8) (cid:9)
V˙ =h˙T (I ⊗K +C⊗K )h˜+ν ,
n g f
(cid:2)
where ν = [νT,...,νT]T. Noting that control law (11.7) can be written in
1 n
stacked form as
ν =−(I ⊗K +C⊗K )h˜−(I ⊗D +C⊗D )h˙, (11.10)
n g f n g f
V˙ =−h˙T(I ⊗D +C⊗D )h˙,
n g f
which is negative semidefinite by part (v) of Lemma C.8.
Let Ω = {(h˜,h˙)|V˙ = 0}. Note that V˙ ≡ 0 implies that h˙ ≡ 0, which in
turn implies that h¨ ≡0. It thus follows from (11.5) and (11.10) that
(I ⊗K +C⊗K )h˜ ≡0,
n g f
which implies h˜ ≡ 0 by part (v) of Lemma C.8. The proof then follows from
Theorem F.4.
The second statement follows by noting that V˙ ≤ 0 implies that V(t) ≤
V(0) and
(cid:2)n
E(t)+ h˙Th˙ =2V(t)≤2V(0)=E(0)
i i
i=1
(cid:2)n
⇒E(t)≤E(0)− h˙Th˙ ,
i i
i=1
where the third equality follows from the fact that the formation is initially
at rest.
Remark 11.5. Equation (11.8) provides a bound on the error function E(t).
Although the bound is conservative, it implies that during a maneuver, the
error will never be worse than the initial error. It is interesting to note that
the bound becomes tighter as the velocity of the robots increases. Hardware
resultsdemonstratingtheeffectivenessof (11.7)arecontainedinSection11.4.
(cid:13)(cid:14)
11.3.2 Coupled Dynamics Formation Control with Passivity-based
Interrobot Damping
Thecontrolstrategygivenin(11.7)requiresthattherelativevelocitybetween
neighbors is known. If relative velocity information is not known, then one
possiblestrategyistosetD =0.Unfortunately,thischoiceresultsinrelative
f

11.3 Formation Control 215
motionthatisoscillatory,despiteasmoothtransitionofeachoftheindividual
robots to its desired formation pattern. To eliminate this oscillation, we use
the passivity techniques in Section 4.3 to inject relative damping into the
system. The proposed control strategy is given by
xˆ˙ =Axˆ +˜h ,
i i i
ν i =−(K g +P)h˜ i −Dh˙ i −K f (h˜ i −h˜ i−1 )−K f (h˜ i −h˜ i+1 )−PAxˆ i ,
(11.11)
where K and D are positive-definite matrices, K is a positive-semidefinite
g f
matrix, A is Hurwitz, and P is the symmetrical positive-definite solution of
theLyapunovequationATP+PAT =−Q,whereQisasymmetricalpositive-
definite matrix. Note that (11.11) is a variant of (4.26).
Remark 11.6. The state of the dynamic controller is xˆ and represents, in a
sense,theestimateoftherelativevelocitiesbetweenneighbors.Notethepres-
ence of robot velocity h˙. Because this information is required for feedback
linearization, we assume that it is also available to the controller. (cid:13)(cid:14)
Theorem 11.7.If robot formation (11.1) is subject to the control strategy
defined in (11.4) and (11.11), then error function (11.6) converges to zero
asymptotically.
Furthermore, if the formation is initially at rest, i.e., h˙(0) = 0, and the
passivity filter is initialized as
xˆ (0)=−A −1h˜ (0),
i i
then the formation error is bounded by
(cid:2)n (cid:2)n
E(t)≤E(0)− h˙Th˙ − xˆTPxˆ . (11.12)
i i i i
i=1 i=1
Proof: Defining xˆ = [xˆT,...,xˆT]T, and using Lemma 11.4, control strat-
1 n
egy (11.11) can be written as
xˆ˙ =(I ⊗A)xˆ+h˜, (11.13a)
n
(cid:8) (cid:9)
ν =− (I ⊗K )+(C⊗K )+(I ⊗P) h˜
n g f n
−(I ⊗D)h˙ −(I ⊗P)(I ⊗A)xˆ. (11.13b)
n n n
Consider the Lyapunov function candidate
1 1 1
V = h˜T(I ⊗K +C⊗K )h˜+ h˙Th˙ + xˆ˙(I ⊗P)xˆ˙,
n g f n
2 2 2
which is positive definite and radially unbounded with respect to h˜, h˙, and xˆ˙
by part (v) of Lemma (C.8). The time derivative of V is given by

216 11 Decentralized Behavioral Approach to Formation Maneuvers
(cid:8) (cid:9)
1 1
V˙ =h˙ (I ⊗K +C⊗K )h˜+ν + x¨ˆ(I ⊗P)xˆ˙ + xˆ˙(I ⊗P)x¨ˆ,
n g f n n
2 2
wherex¨=(I ⊗A)x˙+h˙.Usingthefactthat(I ⊗P)(I ⊗A)+(I ⊗A)T(I ⊗
n n n n n
P)=−(I ⊗Q),
n
(cid:8) (cid:9)
V˙ =h˙ (I ⊗K +C⊗K +I ⊗P)h˜+(I ⊗P)(I ⊗A)xˆ˙ +ν
n g f n n n
−xˆ˙(I ⊗Q)xˆ˙.
n
Application of control law (11.11) gives
V˙ =−h˙T(I ⊗D)h˙ −xˆ˙(I ⊗Q)xˆ˙,
n n
which is negative semidefinite.
Let Ω = {(h˜,h˙,xˆ˙)|V˙ = 0}. Note that V˙ ≡ 0 implies h˙ ≡ 0 and xˆ˙ ≡ 0,
which in turn implies that h¨ ≡0. It thus follows from (11.5)and (11.13)that
the following two equalities hold:
(I ⊗A)xˆ+h˜ ≡0,
(cid:8) n (cid:9)
(I ⊗K )+(C⊗K )+(I ⊗P) h˜+(I ⊗P)(I ⊗A)xˆ≡0.
n g f n n n
Combining these two equations gives
(cid:8) (cid:9)
(I ⊗K )+(C⊗K ) h˜ ≡0,
n g f
which implies h˜ ≡0. Therefore, the proof then follows from Theorem F.4.
The second statement follows from the same argument used in Theo-
rem 11.3.
11.3.3 Saturated Control
Ourexperienceisthat(11.7)and(11.11)workwellinthepresenceofactuator
saturation, but convergence is not necessarily guaranteed. In this section,
we derive a coupled dynamics strategy that explicitly accounts for actuator
saturation.
The saturationcontrolproblemappends the additional constraints,|F|≤
F and |τ| ≤ τ , to dynamics (11.1). For the robots used in our test-
max max
bed, these bounds are F = 30 N and τ = 230 Nm. Unfortunately,
max max
force and torque bounds cannot be applied directly to feedback linearized
dynamics (11.4) because the feedback linearization explicitly depends on the
tangential and angular velocity of each robot. However, because each for-
mation maneuver prescribes a finite motion, we can assume that, given the
bounded acceleration of the system, the robot velocity will also be bounded,
and thereby derive bounds
(cid:9)ν(cid:9)≤ν
max

|     |     |     |     |     |     | 11.3 Formation | Control | 217 |
| --- | --- | --- | --- | --- | --- | -------------- | ------- | --- |
on the feedback linearized forces. The saturation problem is solved by mod-
ifying error function (11.6) to have linear, rather than quadratic, growth.
| Accordingly, | let |     |     |     |     |     |     |     |
| ------------ | --- | --- | --- | --- | --- | --- | --- | --- |
(cid:2)n
|     |       |     | 1            |     | 1   |              |     |     |
| --- | ----- | --- | ------------ | --- | --- | ------------ | --- | --- |
|     |       | {   | log[cosh(k˜h |     |     | log[cosh(k˜h | )]} |     |
|     | E g = |     |              | xi  | )]+ |              | yi  |     |
|     |       |     | k            |     | k   |              |     |     |
i= 1
|     |     | (cid:2) | 4   |     |     |     |     |     |
| --- | --- | ------- | --- | --- | --- | --- | --- | --- |
1
|     |       |     | log{cosh[k(h˜ |     | −h˜ | )]}   |     |     |
| --- | ----- | --- | ------------- | --- | --- | ----- | --- | --- |
|     | E f = |     |               |     | xi  | x,i+1 |     |     |
k
i=<n>
5
1
|     |     |     | log{cosh[k(h˜ |     | −h˜ |       | )]} |     |
| --- | --- | --- | ------------- | --- | --- | ----- | --- | --- |
|     |     |     | +             |     | yi  | y,i+1 | .   |     |
k
| Similar to   | (11.6), the | total    | error        | function | is defined  | as  |     |         |
| ------------ | ----------- | -------- | ------------ | -------- | ----------- | --- | --- | ------- |
|              |             |          | E =k         | E        | +k E        | .   |     | (11.14) |
|              |             |          |              | f f      | g g         |     |     |         |
| The proposed | control     | strategy | is           |          |             |     |     |         |
|              |             | =−k      | tanh(k˜h     |          | )−dtanh(kh˙ |     |     |         |
|              |             | ν        |              |          |             |     | ),  |         |
|              |             | i        | g            | i        |             | i   |     |         |
|              |             |          | −k tanh[k(h˜ |          | −h˜         | )]  |     |         |
|              |             |          | f            |          | i i−1       |     |     |         |
|              |             |          | −k tanh[k(h˜ |          | −h˜         |     |     |         |
|              |             |          | f            |          | i i+1       | )], |     | (11.15) |
wherek ,k,anddarepositivescalars,k isanonnegativescalar,andtanh(·)
| g   |     |     |     |     | f   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
is defined componentwise. Note that (11.15) is a variant of (4.13).
Remark 11.8. Thefirsttwotermsin(11.15)movetherobottowardthedesired
formation pattern; the last two terms cause the robots to move into, and
| maintain, | formation. | (cid:13)(cid:14) |     |     |     |     |     |     |
| --------- | ---------- | ---------------- | --- | --- | --- | --- | --- | --- |
Theorem 11.9.Ifrobotformation (11.1)is subjecttothecontrolstrategyde-
fined in (11.4) and (11.15), then the control satisfies the saturation constraint
|           |          |         | (cid:9)ν(cid:9) | ≤k +d+2k |                      | ,   |     |     |
| --------- | -------- | ------- | --------------- | -------- | -------------------- | --- | --- | --- |
|           |          |         | ∞               | g        |                      | f   |     |     |
| and error | function | (11.14) | converges       | to       | zero asymptotically. |     |     |     |
Furthermore, if the formation is initially at rest, then formation er-
| ror (11.14) | satisfies |     |     |     |     |     |     |     |
| ----------- | --------- | --- | --- | --- | --- | --- | --- | --- |
(cid:2)n
1
|     |     |     | E(t)≤E(0)− |     | h˙Th˙ | .   |     |     |
| --- | --- | --- | ---------- | --- | ----- | --- | --- | --- |
i i
2
i=1
Proof: Because each component of tanh is bounded by one, each component
| of the control | law          | will be | bounded  | by k      | g +d+2k | f . |     |     |
| -------------- | ------------ | ------- | -------- | --------- | ------- | --- | --- | --- |
| Consider       | the Lyapunov |         | function | candidate |         |     |     |     |
(cid:2)n
|     |     |     |       | 1   | h˙Th˙ |     |     |     |
| --- | --- | --- | ----- | --- | ----- | --- | --- | --- |
|     |     |     | V =E+ |     |       | ,   |     |     |
|     |     |     |       | 2   | i     | i   |     |     |
i=1

218 11 Decentralized Behavioral Approach to Formation Maneuvers
where E is given by (11.14). Note that V is positive definite and radially
unbounded with respect to h˜ and h˙. Using the fact that d log[cosh(x)] =
dt
x˙tanh(x), where x∈R, the time derivative of V is given by
(cid:2)n (cid:2) (cid:2)n
V˙ =k h˙T tanh(k˜h )+k (h˙ −h˙ )T tanh[k(h˜ −h˜ )]+ h˙Tν ,
g i i f i i+1 i i+1 i i
i=1 i=<n> i=1
which, using the fact that tanh is an odd function, can be rearrangedas
(cid:2)
V˙ = h˙T i {k g tanh(k˜h i )+k f tanh[k(h˜ i −h˜ i+1 )]+k f tanh[k(h˜ i −h˜ i−1 )]+ν i }.
i=<n>
Substituting from (11.15),
(cid:2)n
V˙ =−d h˙T tanh(kh˙ ),
i i
i=1
which implies that V is a valid Lyapunov function candidate. Let Ω =
{(h˜ ,h˙ )|V˙ =0}. Note that V˙ ≡ 0 implies that h˙ ≡ 0, i=1,...,n, which in
i i i
turn implies that h¨ ≡0, i=1,...,n. It thus follows from (11.5) and (11.15)
i
that
k g tanh(k˜h i )+k f tanh[k(h˜ i −h˜ i+1 )]+k f tanh[k(h˜ i −h˜ i−1 )]≡0. (11.16)
Note that (11.16) implies that
(cid:2)n
k h˜T tanh(k˜h )
g i i
i=1
(cid:2)n
+k f h˜T i {tanh[k(h˜ i −h˜ i+1 )]+tanh[k(h˜ i −h˜ i−1 )]}≡0, (11.17)
i=1
which can be written as
(cid:2)n (cid:2)n (cid:2)n
k h˜T tanh(k˜h )−k c ˜hT tanh[k(h˜ −h˜ )]≡0, (11.18)
g i i f ij i i j
i=1 i=1j=1
where c is the (i,j) entry of the circulant matrix C in Lemma 11.4.
ij
From (4.14) in Lemma 4.18, (11.18) can be written as
(cid:2)n (cid:2)n (cid:2)n
1
k h˜T tanh(k˜h )− k c (h˜ −h˜ )T tanh[k(h˜ −h˜ )]≡0, (11.19)
g i i 2 f ij i j i j
i=1 i=1j=1
where the second term is nonpositive by noting that c ≤ 0, ∀i (cid:6)= j. It
ij
thus follows that h˜ ≡ 0, i= 1,...,n. Therefore, the proof then follows from
i
Theorem F.4.
The second statement follows from the same argument used in Theo-
rem 11.3.

11.4 Hardware Results 219
| 11.4 Hardware |     | Results |     |     |
| ------------- | --- | ------- | --- | --- |
This section describes experimental results using the control strategies de-
scribed in Section 11.3. Experimental results were obtained on three robots
in the Multiple AGent Intelligent Coordination and Control (MAGICC) lab-
oratory at Brigham Young University (BYU). The experimental platform is
showninFig.11.2.Thepositionofeachrobotismeasuredusingacombination
of dead reckoning and an overhead camera system. The physical parameters
| of the robots | shown | in Fig. 11.2 | are listed in Table | 11.1. |
| ------------- | ----- | ------------ | ------------------- | ----- |
Fig.11.2. RobotsfromtheBYUMAGICClaboratoryusedtoobtainexperimental
results
The robots are commanded to transition through the series of formation
| patterns | given by |           |                                     |           |
| -------- | -------- | --------- | ----------------------------------- | --------- |
|          |          | 2(cid:22) | (cid:23) (cid:22) (cid:23) (cid:22) | (cid:23)3 |
−1
|     |     |           | 0 1                                           |     |
| --- | --- | --------- | --------------------------------------------- | --- |
|     |     | P =       | , ,                                           | ,   |
|     |     | 1         | −3 −4 −4                                      |     |
|     |     | 2(cid:22) | (cid:23) (cid:22) (cid:23) (cid:22) (cid:23)3 |     |
|     |     |           | 0 2 −2                                        |     |
P
|     |     | 2 =       | , ,                                           | ,   |
| --- | --- | --------- | --------------------------------------------- | --- |
|     |     |           | 4 2 2                                         |     |
|     |     | 2(cid:22) | (cid:23) (cid:22) (cid:23) (cid:22) (cid:23)3 |     |
|     |     |           | 5 5 5                                         |     |
|     |     | P =       | , ,                                           | ,   |
|     |     | 3         | 6 4.5 3                                       |     |
where the units are given in feet. The test facility at the BYU MAGICC lab
is a 15 foot square.The robots are initially in the formationpattern givenby
|     |     | 2(cid:22) | (cid:23) (cid:22) (cid:23) (cid:22) | (cid:23)3 |
| --- | --- | --------- | ----------------------------------- | --------- |
|     |     |           | 0 1.5 −1.5                          |           |
P
|     |     | 0 = | −6 , −6 , −6 | .   |
| --- | --- | --- | ------------ | --- |

220 11 Decentralized Behavioral Approach to Formation Maneuvers
Table 11.1. Parameters used to obtain simulation and experimental results
|     |     | Parameter | Value   |
| --- | --- | --------- | ------- |
|     |     | m         | 10.1 kg |
i
|     |     | J 0.13 | kg m2 |
| --- | --- | ------ | ----- |
i
|     |     | L           | 0.12 |
| --- | --- | ----------- | ---- |
|     |     | i           | m    |
|     |     | K           | 0.5I |
|     |     | g in (11.7) | 2    |
|     |     | D in (11.7) | I 2  |
g
|     |     | K in (11.7)  | 5I    |
| --- | --- | ------------ | ----- |
|     |     | f            | 2     |
|     |     | D            | I     |
|     |     | f in (11.7)  | 2     |
|     |     | A in (11.11) | −5I 2 |
|     |     | Q in (11.11) | I     |
2
|     |     | K in (11.11) | 10I  |
| --- | --- | ------------ | ---- |
|     |     | g            | 2    |
|     |     | D            | I    |
|     |     | g in (11.11) | 2    |
|     |     | K in (11.11) | 5I 2 |
f
|     |     | k in (11.15) | 1   |
| --- | --- | ------------ | --- |
g
d
|     |     | g in (11.15) | 5   |
| --- | --- | ------------ | --- |
k
|     |     | f in (11.15) | 5   |
| --- | --- | ------------ | --- |
|     |     | k in (11.15) | 1   |
Figure 11.3 shows the robots transitioning between the formation pattern
using control strategy (11.7) and the gains given in Table 11.1. The desired
formation patterns are shown by “x” marks. Notice that the robots move
into the formationspecified by the targetformation pattern at the beginning
of each maneuver. The formation maneuver is defined to be complete when
E(t) < !, where ! = 0.5 m for all results shown in this chapter. When the
formation maneuver is complete, the robots begin to maneuver to the next
formation pattern. This accounts for the fact that the robots do not exactly
| reach the | formation patterns | shown in Fig. | 11.3. |
| --------- | ------------------ | ------------- | ----- |
Figure11.4showstherobotstransitioningbetweentheformationpatterns
using control strategy (11.11) and the gains given in Table 11.1.
Figure11.5showstherobotstransitioningbetweentheformationpatterns
using control strategy (11.15) and the gains given in Table 11.1. For this
experiment,the formationgainshavebeentunedto causethe robotsto move
into formation quickly before transitioning to the desired formation pattern.
11.5 Notes
| The results    | in this chapter | are based mainly | on [118]. |
| -------------- | --------------- | ---------------- | --------- |
| Acknowledgment | is              | given to         |           |
(cid:10)c2003IEEE.Reprinted,withpermission,fromJonathanR.Lawton,Ran-
dalW. Beard,andBrett Young,“Adecentralizedapproachto formationma-
neuvers,”IEEE Transactions on Robotics and Automation,vol.19,no.6,pp.
| 933–941,December | 2003. |     |     |
| ---------------- | ----- | --- | --- |

|     |     |     | 11.5 | Notes 221 |
| --- | --- | --- | ---- | --------- |
4.5
4
3.5
3
)tf( sixa Y 2.5
2
1.5
1
0.5
0
| 0 0.5 | 1 1.5 | 2 2.5 | 3 3.5 | 4 4.5 |
| ----- | ----- | ----- | ----- | ----- |
X axis (ft)
| Fig. 11.3. | Robot hand | positions with control | strategy (11.7) |     |
| ---------- | ---------- | ---------------------- | --------------- | --- |

222 11 Decentralized Behavioral Approach to Formation Maneuvers
4.5
4
3.5
3
2.5
2
1.5
1
0.5
0
0 0.5 1 1.5 2 2.5 3 3.5 4 4.5
X axis (ft)
)tf(
sixa
Y
Fig. 11.4. Robot hand positions with passivity control strategy (11.11)

11.5 Notes 223
4.5
4
3.5
3
2.5
2
1.5
1
0.5
0
0 0.5 1 1.5 2 2.5 3 3.5 4 4.5
X axis (ft)
)tf(
sixa
Y
Fig. 11.5. Robot hand positions with inputsaturation control strategy (11.15)

12
Deep Space Spacecraft Formation Flying
This chapter applies the design scheme in Section 8.4.1 to deep space space-
craft formation flying. We propose a decentralized formation control scheme
that is built on the combined strength of consensus algorithms and the vir-
tual structure approach. By following a decentralized coordination architec-
ture via the virtual structure approach,we introduce decentralized formation
control strategies, which are appropriate when a large number of spacecraft
are involved and/or stringent interspacecraft communication limitations are
applied.Inourdecentralizedscheme,eachspacecraftintheformationinstan-
tiates a local copy of the state of the virtual structure, which is the coordi-
nationvariableusing the virtualstructureframework.The localinstantiation
of the coordination variable in each spacecraft is then driven into consensus
by communication with its neighbors following a bidirectional ring topology.
The effectiveness of the proposed control strategies is demonstrated through
simulation results.
12.1 Problem Statement
The concept of multiple spacecraft flying in formation is emerging as an at-
tractivealternativetotraditionalmonolithicspacecraftforbothscientificand
military applications. The multiple spacecraft approach has several advan-
tages, including increased instrument resolution, reduced cost, reconfigura-
bility, and overall system robustness. Some of the potential applications for
formationflyingincludespace-basedinterferometersandmilitarysurveillance
instruments. Both NASA and the Air Force have identified spacecraft forma-
tion flying as a key technology for the twenty first century. In this section,
we introduce some preliminary notation and properties for spacecraft forma-
tion flying, including reference frames, desired states for each spacecraft, and
spacecraft dynamics.

| 226    | 12 Deep   | Space  | Spacecraft | Formation |     | Flying |     |
| ------ | --------- | ------ | ---------- | --------- | --- | ------ | --- |
| 12.1.1 | Reference | Frames |            |           |     |        |     |
As shown in Fig. 12.1, four coordinate frames are used in this chapter. Ref-
F
erence frame O is used as an inertial frame. The formation frame, or the
virtual structure frame F is fixed at the virtual center of the formation.
F
Reference frame F is embedded at the center of mass of each spacecraftas a
i
body frame, which rotates with the spacecraft and represents its orientation.
Reference frame Fd represents the desired configuration for each spacecraft.
i
inF
Givenany vectorp,the representationofp in terms ofits components O ,
F , and F are represented by [p] , [p] , and [p] , respectively.
| F   | i   |      |       | O          | F   | i              |     |
| --- | --- | ---- | ----- | ---------- | --- | -------------- | --- |
|     |     | Fig. | 12.1. | Coordinate |     | frame geometry |     |
F
Let the direction cosine matrix C denote the orientation of frame
ab a
with respectto F ; then [p] =C [p] ,where [p] and[p] arethe coordinate
|                             |         | b          | a         | ab   | b                                    | a b |     |
| --------------------------- | ------- | ---------- | --------- | ---- | ------------------------------------ | --- | --- |
| representationsofvectorpinF |         |            |           | andF |                                      |     |     |
|                             |         |            |           | a    | b ,respectively.Weuseunitquaternions |     |     |
| to represent                |         | spacecraft | attitudes | (see | Appendix                             | D). |     |
| 12.1.2                      | Desired | States     | for       | Each | Spacecraft                           |     |     |
As described in Section 8.5.1, in the virtual structure approach, the entire
F
desired formation is treated as a single structure with a formation frame F
locatedatitsvirtualcenterofmasstorepresentitsconfiguration.Thevirtual
structure then has position r ∈R3, velocity v ∈R3, attitude q ∈R4, and
|         |          |     |          | F   |     | F   | F   |
| ------- | -------- | --- | -------- | --- | --- | --- | --- |
|         |          | ∈R3 |          |     | F   |     |     |
| angular | velocity | ω F | relative | to  | O . |     |     |
Letr ∈R3,v ∈R3,q ∈R4,andω ∈R3 representthe position,velocity,
|     | i   | i   | i   |     | i   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
attitude, and angular velocity of the ith spacecraft relative to the inertial
frameF
|     | .Similarly,letr |     | ,v  | ,q    | ,andω | representtheposition,velocity, |     |
| --- | --------------- | --- | --- | ----- | ----- | ------------------------------ | --- |
|     | O               |     | iF  | iF iF |       | iF                             |     |
attitude,andangularvelocityoftheithspacecraftrelativetoformationframe
F
F .Asuperscript“d”isalsousedtorepresentthecorrespondingdesiredstate
| of each | spacecraft | relative | to  | either | F or | F . |     |
| ------- | ---------- | -------- | --- | ------ | ---- | --- | --- |
|         |            |          |     |        | O    | F   |     |

|     |     |     |     |     |     | 12.1 | Problem | Statement | 227 |
| --- | --- | --- | --- | --- | --- | ---- | ------- | --------- | --- |
Conceptually,wecanthinkthatplaceholderscorrespondingtoeachspace-
craft are embedded in the virtual structure to represent the desired position
and attitude of each spacecraft. As the virtual structure as a whole evolves
in time, the place holderstrace out trajectoriesfor eachcorrespondingspace-
craft to track. As a result, the actual states of the ith place holder represent
F
the desired states of the ith spacecraft. With as a reference frame, these
F
| states       | can be | denoted | by rd      | ∈R3, | vd ∈R3, | qd ∈R4, | and | ωd ∈R3. |     |
| ------------ | ------ | ------- | ---------- | ---- | ------- | ------- | --- | ------- | --- |
|              |        |         | iF         |      | iF      | iF      |     | iF      |     |
| Generally,rd |        | ,qd     | ,vd ,andωd |      |         |         |     |         |     |
canvarywithtime,whichmeansthatthe
|     |     | iF iF | iF  | iF  |     |     |     |     |     |
| --- | --- | ----- | --- | --- | --- | --- | --- | --- | --- |
desired formation shape is time-varying. However, if we are concerned with
formation maneuvers that preserve the overall formation shape, that is, each
place holder needs to preserve a fixed relative position and orientation in the
virtual structure, rd and qd should be constant, and vd and ωd should be
|     |     | iF  | iF  |     |     |     | iF  | iF  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
zero. This requirement can be loosened to make the formation shape more
flexiblebyallowingtheplaceholderstoexpandorcontractwhilestillkeeping
afixedrelativeorientation.Wewillfocusonthisscenariointhislattersection.
Of course, the approach here can be readily extended to the general case.
| Let | λ   | =   | [λ ,λ ,λ | ], where |     | the components |     | represent | the |
| --- | --- | --- | -------- | -------- | --- | -------------- | --- | --------- | --- |
|     | F   |     | 1 2      | 3        |     |                |     |           |     |
F
expansion/contractionrates of the virtual structure along each F axis. The
| state | of the | virtual structure |                           | can be | defined | as  |     |     |        |
| ----- | ------ | ----------------- | ------------------------- | ------ | ------- | --- | --- | --- | ------ |
|       |        |                   | ξ =[rT,vT,qT,ωT,λT,λ˙T]T. |        |         |     |     |     | (12.1) |
|       |        |                   |                           | F F    | F F     | F F |     |     |        |
We note that if each spacecraft has knowledge of ξ and of its own desired
position and orientation with respect to the virtual structure, then forma-
tion keeping is transformed into an individual tracking problem. Therefore,
the vector ξ represents the minimum amount of information needed by each
spacecraft to coordinate its motion with the group. Therefore, ξ is the coor-
| dination | variable | for | the team. |     |     |     |     |     |     |
| -------- | -------- | --- | --------- | --- | --- | --- | --- | --- | --- |
Given ξ, the desired states for the ith spacecraft are given by
|     |     | [rd] =[r | ] +C   | Λ[rd  | ] ,   |     |      |      |        |
| --- | --- | -------- | ------ | ----- | ----- | --- | ---- | ---- | ------ |
|     |     | i O      | F O    | OF    | iF F  |     |      |      |        |
|     |     | [vd]     |        | Λ˙[rd |       | ×(C | Λ[rd |      |        |
|     |     | =[v      | ] +C   |       | ] +[ω | ]   |      | ] ), |        |
|     |     | i O      | F O    | OF    | iF F  | F O | OF   | iF F |        |
|     |     | [qd] =[q | ] [qd  | ] ,   |       |     |      |      | (12.2) |
|     |     | i O      | F O iF | F     |       |     |      |      |        |
|     |     | [ωd] =[ω | ] ,    |       |       |     |      |      |        |
|     |     | i O      | F O    |       |       |     |      |      |        |
|     |     |          |        |       |       | F   |      |      | F      |
where C (q ) is the rotationalmatrix of frame with respect to and
|     | OF  | F   |     |     |     |     | O   |     | F   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Λ=diag(λ ). Note that unlike the constant desired states rd , vd , qd , and
|     |          | F      |             |        |     |         |     | iF iF    | iF       |
| --- | -------- | ------ | ----------- | ------ | --- | ------- | --- | -------- | -------- |
| ωd  |          | F      |             |        | rd, | vd, qd, | ωd  |          | F        |
|     | relative | to F , | the desired | states |     | and     |     | relative | to O are |
| iF  |          |        |             |        | i   | i i     | i   |          |          |
time-varyingbecauseξ istime-varying.Theevolutionequationsofthedesired
| states | are given | by  |     |     |     |     |     |     |     |
| ------ | --------- | --- | --- | --- | --- | --- | --- | --- | --- |

| 228 12            | Deep Space | Spacecraft |        | Formation | Flying     |         |        |        |
| ----------------- | ---------- | ---------- | ------ | --------- | ---------- | ------- | ------ | ------ |
|                   | [r˙d]      | =[vd]      | ,      |           |            |         |        |        |
|                   | i          | O i        | O      |           |            |         |        |        |
|                   | [v˙d]      | =[v˙       | ] +2[ω | ]         | ×(C        | Λ˙[rd ] | )      | (12.3) |
|                   | i          | O F        | O      | F O       | OF         | iF      | F      |        |
|                   |            |            | Λ¨[rd  |           |            | ×(C     | Λ[rd   |        |
|                   |            | +C         | OF     | ] F       | +[ω˙ F ] O | OF      | ] F ), |        |
|                   |            |            |        | iF        |            |         | iF     |        |
|                   | [q˙d]      | =[q˙       | ] [qd  | ] ,       |            |         |        |        |
|                   | i          | O F        | O iF   | F         |            |         |        |        |
|                   | [ω˙d]      | =[ω˙       | ] .    |           |            |         |        |        |
|                   | i          | O          | F O    |           |            |         |        |        |
| 12.1.3 Spacecraft |            | Dynamics   |        |           |            |         |        |        |
The translational dynamics of each spacecraft relative to F are
O
|     |     |     | dr  |      | dv  |      |     |        |
| --- | --- | --- | --- | ---- | --- | ---- | --- | ------ |
|     |     |     | i   | =v , | m i | =f , |     | (12.4) |
|     |     |     |     | i    | i   | i    |     |        |
|     |     |     | dt  |      | dt  |      |     |        |
|     |     |     | o   |      | o   |      |     |        |
∈R3
where m and f are,respectively,the mass and controlforce associated
|          | i i             |     |     |     |     |     |     |     |
| -------- | --------------- | --- | --- | --- | --- | --- | --- | --- |
| with the | ith spacecraft. |     |     |     |     |     |     |     |
F
The rotational dynamics of each spacecraft relative to O (see [244]) are
|     | dqˆ | i =− | 1 ×qˆ |     | 1     | dq¯ i =− | 1 ·qˆ, |     |
| --- | --- | ---- | ----- | --- | ----- | -------- | ------ | --- |
|     |     |      | ω     | +   | q¯ω , |          | ω      |     |
|     | dt  |      | 2 i   | i   | 2 i i | dt       | 2 i i  |     |
|     |     | o    |       |     |       | o        |        |     |
dω
|     | J    | i =−ω | ×(J | ω )+τ | ,   |     |     | (12.5) |
| --- | ---- | ----- | --- | ----- | --- | --- | --- | ------ |
|     | i dt |       | i   | i i   | i   |     |     |        |
o
where qˆ and q¯ are, respectively, the vector and scalar parts of q ; and J ∈
| i    | i    |     |     |     |     |     | i   | i   |
| ---- | ---- | --- | --- | --- | --- | --- | --- | --- |
| R3×3 | ∈ R3 |     |     |     |     |     |     |     |
and τ i are, respectively, the inertial tensor and control torque of
the ith spacecraft.
| 12.2 Decentralized |          |     | Architecture |     |     | via the | Virtual |     |
| ------------------ | -------- | --- | ------------ | --- | --- | ------- | ------- | --- |
| Structure          | Approach |     |              |     |     |         |         |     |
In this section, we propose a decentralized architecture for deep space space-
craft formation flying via the virtual structure approach.To demonstrate the
salient features of our decentralized scheme, we first introduce a centralized
| architecture       | via the | virtual      | structure |     | approach. |     |     |     |
| ------------------ | ------- | ------------ | --------- | --- | --------- | --- | --- | --- |
| 12.2.1 Centralized |         | Architecture |           |     |           |     |     |     |
Figure12.2showsacentralizedcoordinationarchitectureviathevirtualstruc-
ture approach.
SystemGisadiscreteeventsupervisor,whichevolvesaseriesofformation
patterns by outputting its currentformationpattern y . SystemF is the for-
G
mation controlmodule, which produces and broadcastscoordinationvariable
ξ. System K is the local spacecraft controller for the ith spacecraft, which
i
receives coordination variable ξ from the formation control module, converts

12.2 Decentralized Architecturevia theVirtual StructureApproach 229
Fig. 12.2. A centralized architecture viathe virtualstructure approach
ξ to the desired states for the ith spacecraft, and then controls the actual
state for the ith spacecraft to track its desired state. System S is the ith
i
spacecraft, with control input u representing the control force and torque,
i
and output y representing the measurable outputs from the ith spacecraft.
i
In this centralized architecture, G and F are implemented at a centralized
location (e.g., spacecraft #1), and then coordination variable ξ is broadcast
to the local controllers of the other spacecraft. Note that there is formation
feedback from each local spacecraft controller to formation control module F
through the performance measure z . Also, there is formation feedback from
i
F to G through performance measure z .
F
Remark 12.1. The strength of this centralized architecture is that formation
algorithms are fairly easy to realize. The weakness is that a heavy communi-
cation and computationalburden is concentratedon the centralizedlocation,
which may degradeoverallsystemperformance. Also the centralizedlocation
results in a single point of failure for the whole system. (cid:13)(cid:14)
12.2.2 Decentralized Architecture
In this section, instead of using a set of desired locations for each agent
as a formation pattern as in Chapter 11, we take advantage of the vir-
tual structure approach to define the formation pattern by P = ξd, where
ξd =[rdT ,vdT ,qdT ,ωdT ,λdT ,λ˙dT ]T isthedesiredconstantreferencefortheco-
F F F F F F
ordinationvariablerepresentingthedesiredstatesofthevirtualstructure.We
willassumepiecewiserigidformationswhichimplies thatvd =ωd =λ˙d ≡0.
F F F
By specifying the formation pattern for the group, the movements of each
spacecraft can be completely defined. Through a sequence of formation pat-
terns P(k) = ξd(k),k = 1,··· ,K, the group can achieve a class of formation
maneuver goals.In Chapter 11, the formation pattern is defined so that each

230 12 Deep Space Spacecraft Formation Flying
vehicle knows only its final location in the formation, whereas its trajectory
throughout the maneuver is not specified. Here the formation pattern is de-
fined such that each spacecraft will track a trajectory specified by the state
of the virtual structure, while preserving a certain formation shape.
A decentralized architecture is shown in Fig. 12.3. In the decentralized
architecture, each spacecraft in the formation instantiates a local copy of the
coordination variable. We use
ξ =[rT ,vT ,qT ,ωT ,λT ,λ˙T ]T
i Fi Fi Fi Fi Fi Fi
torepresentthecoordinationvariableinstantiatedintheithspacecraftcorre-
sponding to the coordinationvariableξ definedin(12.1).Abidirectionalring
topology is used to communicate the coordinationvariable instantiations, in-
stead of the position or attitude information among the spacecraft, to bring
each local instantiation into consensus.
Fig. 12.3. Decentralized architecture viathevirtual structure approach
In Fig. 12.3, instead of implementing the discrete event supervisor and
formationcontrolmoduleatacentralizedlocation,eachspacecrafthasalocal
copy of the discrete event supervisor G and formation control module F,
denoted by G and F for the ith spacecraft, respectively. As in Fig. 12.2,
i i
K andS representthe ithlocalspacecraftcontrollerandthe ithspacecraft,
i i
respectively.
Before the group maneuver starts, a sequence of formation patterns has
beenpresetineachdiscreteeventsupervisorG .ThegoalofG istotransition
i i
throughthe sequenceofformationpatternssothataclassofgroupmaneuver
goals can be achieved sequentially. Certain mechanisms need to be applied

12.2 Decentralized Architecturevia theVirtual StructureApproach 231
to coordinate and drive the group starting time into consensus, e.g., simple
semaphores.When the groupmaneuver starts,each discrete eventsupervisor
G outputs the current formation pattern, y =ξd(1), to the formation con-
i Gi
trolmoduleF .EachformationcontrolmoduleF implementsacoordination
i i
variable instantiation ξ . The goal of F is to evolve ξ to its current desired
i i i
formationpatternξd(k) anddriveξ intoconsensuswithcoordinationvariable
i
instantiations implemented on other spacecraft. Here we use a bidirectional
ring topology, which means that coordination variable ξ instantiated in the
i
ithspacecraftisdrivenintoconsensuswithitstwoneighbors,thatis,instanti-
ationsξ i−1 andξ i+1 implementedinthe(i−1)thandthe(i+1)thspacecraft,
respectively. Communications between the ith spacecraft and the (i−1)th
and (i+1)th spacecraft need to be established to transmit and receive the
coordinationvariableinstantiations.Formationcontrolmodule F then sends
i
its coordinationvariableinstantiationξ to the localspacecraftcontrollerK .
i i
Basedonξ , the localcontrollerK canderive the desiredstates and the cor-
i i
responding derivatives for the ith spacecraft from (12.2) and (12.3). A local
controller K is designed to guarantee that the ith spacecraft tracks its de-
i
sired states asymptotically. Formation feedback is also included from the ith
spacecraft controller K to the ith formation control module F through the
i i
performance measure z indicating the ith spacecraft’s tracking performance.
i
Accordingly, as we will see in Section 12.3, control law for ξ implemented in
i
F dependsontheperformancemeasurez ,thecurrentdesiredformationpat-
i i
tern y = ξd(k), and the corresponding coordination variable instantiations
Gi
ξ i−1 and ξ i+1 from the ith spacecraft’s neighbors. Of course, formation feed-
back can also be included from other spacecraft to the ith formation control
module F atthe costofadditionalcommunication.Formationfeedbackfrom
i
ith formation control module F to ith discrete event supervisor G is also
i i
included through the performance measure z , which indicates how far the
Fi
ithinstantiationξ isfromitscurrentmaneuvergoalξd(k) andconsensusper-
i
formance between ξ and its neighbors. Like the coordination and consensus
i
of the first groupmaneuver starting time, similar mechanisms can be applied
to indicate accomplishment of the current formation pattern and coordinate
and drive the starting time into consensus for the next formation pattern
among spacecraft. Then the same procedure described above repeats so that
a sequence of formation patterns can be achieved.
The communication requirement for each spacecraft during the maneuver
canbeestimatedasfollows.Weknowthatr ,v ,ω ,λ ,andλ˙ allhave
Fi Fi Fi Fi Fi
three components and q has four components. Thus the coordination vari-
Fi
ableξ has19components.AssumethateachcomponentisencodedasB bits
i
and the sample rate of the system is given by L Hz. By communicating with
itstwoadjacentneighbors,the requiredbandwidthforeachspacecraftcanbe
estimated as 38BL bits/s. Note that this is the case when group translation,
grouprotation, and groupexpansion/contractionare all involved.If only one
group maneuver is involved,the bandwidth can be further reduced to almost
one-third of the above estimate.

232 12 Deep Space Spacecraft Formation Flying
Remark 12.2. In[37],adecentralizedarchitectureisproposedforautonomous
establishment and maintenance of satellite formations, where each satellite
processes only local measurement information and transmission vectors from
other nodes so that a local Kalman filter can be implemented to obtain a
local control. It is also shown that the decentralized framework generates a
neighboring optimal control if the planned maneuvers and trajectories are
themselves optimal. Compared with the architecture in [37], which is based
on a fully interconnected network, the architecture proposed here imposes
fewer communication requirements. Even if the compression of data trans-
mission is realized in [37], each vehicle still needs extensive data transmitted
from all other vehicles, which causes additional intervehicle communications
especiallywhenalargenumberofvehiclesareinvolved.Thearchitecturepro-
posed here requires only communication between adjacent neighbors during
the maneuver. (cid:13)(cid:14)
Remark 12.3. Compared to its centralized alternative, there is no master in
the loop, and each spacecraft evolves in a parallel manner so that a single
point of failure existing in any centralized implementation can be eliminated
and the total system performance will not degrade catastrophically under
failure. As a result, decentralized implementation offers more flexibility, re-
liability, and robustness than the corresponding centralized alternative. The
weaknessisthateachlocalinstantiationmustbedrivenintoconsensus,which
accounts for additional complexity and intervehicle communications. Due to
the ring topology and the implementation of the coordinationvariable,infor-
mationexchangeamongspacecraftcanbe reducedinthe abovedecentralized
architecture. Therefore, this weakness can be somewhat mitigated although
the disadvantage of increased intervehicle communication requirements is a
typical concernfor decentralized systems. Of course,there may exist discrep-
ancies between the starting time of each instantiation of the coordination
variable dynamics. This starting time discrepancy can be mitigated through
the control law for each coordination variable, which will drive neighboring
coordination variable instantiations into consensus. Also, there may exist a
time delay when neighboring spacecraft exchange information. This issue is
not modeled in the above decentralized architecture. (cid:13)(cid:14)
12.3 Decentralized Formation Control Strategies
Twomajortasksneedtobecarriedoutinthedecentralizedformationcontrol
scheme via the virtual structure approach.One is to propose suitable control
lawsforeachspacecrafttotrackitsdesiredstatesdefinedbythevirtualstruc-
ture.Theotheristocontrolanddriveeachvirtualstructureinstantiationinto
consensustoachievethedesiredformationpatternsinadecentralizedmanner.
InSections12.3.1and12.3.2,wepresentcontrolstrategiesforeachspacecraft
and each virtual structure instantiation, respectively. In Section 12.3.3, we

|     |     |     |     | 12.3 Decentralized |     | Formation | Control | Strategies | 233 |
| --- | --- | --- | --- | ------------------ | --- | --------- | ------- | ---------- | --- |
provideconvergenceanalysisfor the systemcomposedof the coupleddynam-
ics of n spacecraft and n coordination variable instantiations.
| 12.3.1 | Formation |             | Control |        | Strategies      | for | Each Spacecraft |     |     |
| ------ | --------- | ----------- | ------- | ------ | --------------- | --- | --------------- | --- | --- |
| For    | the ith   | spacecraft, |         | define |                 |     |                 |     |     |
|        |           |             |         | X      | =[rT,vT,qT,ωT]T |     |                 |     |     |
|        |           |             |         | i      | i               | i i | i               |     |     |
and
|     |            |       |     | =[rdT   | ,vdT                    | ,qdT ,ωdT |        |     |     |
| --- | ---------- | ----- | --- | ------- | ----------------------- | --------- | ------ | --- | --- |
|     |            |       |     | Xd      |                         |           | ]T     |     |     |
|     |            |       |     | i       | i i                     | i         | i      |     |     |
| as  | the actual | state | and | desired | state, respectively.    |           | Define |     |     |
|     |            |       | X˜  |         | −Xd =[r˜T,v˜T,q˜T,ω˜T]T |           |        |     |     |
i =X i
|     |           |       |         |                 | i   | i i | i i |     |     |
| --- | --------- | ----- | ------- | --------------- | --- | --- | --- | --- | --- |
| as  | the error | state | for the | ith spacecraft. |     |     |     |     |     |
We know that the desired states for each spacecraft also satisfy transla-
tional and rotational dynamics (12.4) and (12.5), respectively, that is,
drd
|     |     |     |     | i   | =vd, |     |     |     |     |
| --- | --- | --- | --- | --- | ---- | --- | --- | --- | --- |
|     |     |     |     | dt  | i    |     |     |     |     |
o
dvd
|     |     |     | m   | i   | =fd, |     |     |     |     |
| --- | --- | --- | --- | --- | ---- | --- | --- | --- | --- |
|     |     |     |     | i   | i    |     |     |     |     |
dt o
|     |     |     |     | dqˆd | 1          |     | 1      |     |     |
| --- | --- | --- | --- | ---- | ---------- | --- | ------ | --- | --- |
|     |     |     |     | i    | =− ωd×qˆd+ |     | q¯dωd, |     |     |
(12.6)
|     |     |     |     | dt  | 2 i | i   | 2 i i |     |     |
| --- | --- | --- | --- | --- | --- | --- | ----- | --- | --- |
o
|     |     |     |     | dq¯d | 1          |     |     |     |     |
| --- | --- | --- | --- | ---- | ---------- | --- | --- | --- | --- |
|     |     |     |     | i    | =− ωd·qˆd, |     |     |     |     |
i i
|     |     |     |     | dt o | 2   |     |     |     |     |
| --- | --- | --- | --- | ---- | --- | --- | --- | --- | --- |
dωd
|     |     |     |     | i   | =−ωd×(J | ωd)+τd. |     |     |     |
| --- | --- | --- | --- | --- | ------- | ------- | --- | --- | --- |
J
|     |     |     |     | i dt | i   | i i | i   |     |     |
| --- | --- | --- | --- | ---- | --- | --- | --- | --- | --- |
o
Thisisvalidbecausethedesiredstatesforeachspacecraftarethesameasthe
actualstatesforeachcorrespondingplaceholder,whichsatisfiestranslational
| and | rotational | dynamics. |     |     |     |     |     |     |     |
| --- | ---------- | --------- | --- | --- | --- | --- | --- | --- | --- |
The proposed control force for the ith spacecraft is given by
|       |     |       |      | [v˙d−K      | −rd)−K            |     | −vd)],    |     |        |
| ----- | --- | ----- | ---- | ----------- | ----------------- | --- | --------- | --- | ------ |
|       |     |       | f =m |             | (r                |     | (v        |     | (12.7) |
|       |     |       | i    | i i         | ri i              | i   | vi i      | i   |        |
| where | K   | and K | are  | symmetrical | positive-definite |     | matrices. |     |        |
|       | ri  |       | vi   |             |                   |     |           |     |        |
The proposed control torque for the ith spacecraft is given by
|     |     |         | 1   |       |        | (cid:2) |       |       |        |
| --- | --- | ------- | --- | ----- | ------ | ------- | ----- | ----- | ------ |
|     | τ   | =J ω˙d+ | ω   | ×J (ω | +ωd)−k | qd∗q    | −K (ω | −ωd), | (12.8) |
|     | i   | i i     | 2 i | i     | i i    | qi i    | i ωi  | i i   |        |
where k qi is a positive scalar, K ωi is a symmetrical positive-definite matrix,
|     | (cid:2) d∗q |     |     |     |     |     |     | qd∗q |     |
| --- | ----------- | --- | --- | --- | --- | --- | --- | ---- | --- |
and q i represents the vector part of the unit quaternion i .
|     | i   |     |     |     |     |     |     | i   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Note that (12.7) and (12.8) require both Xd and X˙d which are obtained
|      |       |          |        |     |         |     | i i |     |     |
| ---- | ----- | -------- | ------ | --- | ------- | --- | --- | --- | --- |
| from | ξ and | ξ˙ using | (12.2) | and | (12.3). |     |     |     |     |
|      | i     | i        |        |     |         |     |     |     |     |

| 234 12 Deep | Space Spacecraft | Formation | Flying |     |     |
| ----------- | ---------------- | --------- | ------ | --- | --- |
12.3.2 Formation Control Strategies for Each Virtual Structure
Instantiation
As in Section 12.2.2, ξ i is the ith coordination variable instantiation and
ξd(k) is the current kth desired constant goal for the coordination variable
instantiations, i.e., the current formation pattern. For notation simplicity,
hereafter, we use ξd instead of ξd(k) to represent a certain formation pattern
| to be achieved. | Define |       |                     |           |     |
| --------------- | ------ | ----- | ------------------- | --------- | --- |
|                 | ξ˜ −ξd | =[r˜T | ,v˜T ,q˜T ,ω˜T ,λ˜T | ,λ˜˙ T ]T |     |
i =ξ i
|     |     | Fi  | Fi Fi Fi Fi | Fi  |     |
| --- | --- | --- | ----------- | --- | --- |
as the error state for the ith coordination variable instantiation. There are
two objectives for the instantiation of the coordination variable implemented
in each spacecraft. The first objective is to reach its desired constant goal ξd
defined by the formation pattern set. The second objective is to drive each
···
instantiation into consensus, i.e., ξ 1 = ξ 2 = = ξ n . We apply the ideas in-
troducedinChapters5and6todrivethecoordinationvariableinstantiations
into consensus during the maneuver,as well as evolve it to its desired goalat
| the end of the | maneuver. |     |     |     |     |
| -------------- | --------- | --- | --- | --- | --- |
DefineE asthegoalseekingerrorbetweenthecurrentcoordinationvari-
G
ξd:
| able instantiation | ξ i and | the desired | goal                       |     |     |
| ------------------ | ------- | ----------- | -------------------------- | --- | --- |
|                    |         |             | (cid:2)n (cid:18) (cid:18) |     |     |
(cid:18) −ξd(cid:18)2
|     |     | E (t)= | ξ . |     |     |
| --- | --- | ------ | --- | --- | --- |
|     |     | G      | i   |     |     |
i=1
AlsodefineE S asthe totalconsensuserrorbetweenneighboringcoordination
variable instantiations:
(cid:2)n
|     |     | E (t)= | (cid:9)ξ −ξ (cid:9)2, |     |     |
| --- | --- | ------ | --------------------- | --- | --- |
|     |     | S      | i i+1                 |     |     |
i=1
wherethesummationindexiisdefinedmodulon,i.e.,ξ n+1 =ξ 1 andξ 0 =ξ n .
Defining E(t)=E (t)+E (t), then the control objective is to drive E(t) to
|     | G   | S   |     |     |     |
| --- | --- | --- | --- | --- | --- |
zero asymptotically.
Becausethecoordinationvariablerepresentsthestatesofthevirtualstruc-
ture, the ith coordination variable instantiation satisfies the following rigid
body dynamics:
|     | ⎡     | ⎤ ⎡ |     | ⎤   |     |
| --- | ----- | --- | --- | --- | --- |
|     | r˙ Fi |     | v   |     |     |
Fi
|     | ⎢ m v˙      | ⎥ ⎢   | f                   | ⎥      |        |
| --- | ----------- | ----- | ------------------- | ------ | ------ |
|     | ⎢ F Fi      | ⎥ ⎢   | Fi                  | ⎥      |        |
|     | ⎢ q/ ˙      | ⎥ ⎢ − | 1ω × / 1            | ⎥      |        |
|     | ⎢           | ⎥ ⎢   | q + q               | ω ⎥    |        |
|     | ⎢ F i       | ⎥ ⎢   | 2 F i F i 2 F       | i Fi ⎥ |        |
|     | q ˙         | =     | − 1ω · q/           | ,      | (12.9) |
|     | ⎢ F i       | ⎥ ⎢   | 2 F i F i           | ⎥      |        |
|     | ⎢           | ⎥ ⎢   | − ×                 | ⎥      |        |
|     | ⎢J F ω ˙ Fi | ⎥ ⎢   | ω F i J F ω F i + τ | F i ⎥  |        |
|     | ⎣           | ⎦ ⎣   |                     | ⎦      |        |
|     | λ˙          |       | λ˙                  |        |        |
|     | Fi          |       | Fi                  |        |        |
λ¨
ν Fi
Fi

|     |     |     |     | 12.3 | Decentralized |     | Formation Control | Strategies | 235 |
| --- | --- | --- | --- | ---- | ------------- | --- | ----------------- | ---------- | --- |
where m and J are the virtual mass and virtual inertia of the virtual
|     | F   |     | F   |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
structure, f and τ are the virtual force and virtual torque exerted on the
|     |     | Fi  | Fi  |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
ith implementation of the virtual structure, and ν Fi is the virtual control
| effort | used | to expand |     | or contract | the | formation. |     |     |     |
| ------ | ---- | --------- | --- | ----------- | --- | ---------- | --- | --- | --- |
(cid:18) (cid:18)
(cid:2) (cid:18) (cid:18) 2
Thetrackingperformancefortheithspacecraftisdefinedase = (cid:18)X˜ (cid:18) .
|     |     |     |     |     |     |     |     | Ti  | i   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Also define
|     |     |     |     |     | Γ Gi =D | G +K | F e Ti |     | (12.10) |
| --- | --- | --- | --- | --- | ------- | ---- | ------ | --- | ------- |
to incorporate formation feedback from the ith spacecraft to the ith coordi-
nationvariable implementation, whereD G and K F are symmetricalpositive-
definite matrices. Obviously, Γ is also a positive-definite matrix. If we let
Gi
| K   | =0, there | is  | no formation |     | feedback. |     |     |     |     |
| --- | --------- | --- | ------------ | --- | --------- | --- | --- | --- | --- |
F
| The | proposed |     | control | force | f Fi      | is given | by    |        |         |
| --- | -------- | --- | ------- | ----- | --------- | -------- | ----- | ------ | ------- |
|     |          | f   | =m      | {−K   | (r −rd)−Γ |          | v     |        |         |
|     |          | Fi  |         | F     | G Fi      | F        | Gi Fi |        |         |
|     |          |     | −K      | [r    | −r        | ]−D      | [v −v | ]      | (12.11) |
|     |          |     |         | S Fi  | F(i+1)    |          | S Fi  | F(i+1) |         |
|     |          |     | −K      |       | −r        | ]−D      | −v    | ]},    |         |
|     |          |     |         | [r    | F(i−1)    |          | [v    | F(i−1) |         |
|     |          |     |         | S Fi  |           |          | S Fi  |        |         |
where K is a symmetricalpositive-definite matrix, Γ is defined in (12.10),
|     | G   |     |     |     |     |     | Gi  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
and K S and D S are symmetrical positive semidefinite matrices. Note that
| (12.11) | is       | a direct | application |        | of (5.10). |          |     |     |     |
| ------- | -------- | -------- | ----------- | ------ | ---------- | -------- | --- | --- | --- |
| The     | proposed |          | control     | torque | τ          | is given | by  |     |     |
Fi
(cid:3)
|     |     |     | τ =−k |              | qd∗q −Γ  | ω   |                |     |         |
| --- | --- | --- | ----- | ------------ | -------- | --- | -------------- | --- | ------- |
|     |     |     | Fi    | G            | F Fi     | Gi  | Fi             |     |         |
|     |     |     |       | −k q∗(cid:3) |          | −D  | −ω             |     |         |
|     |     |     |       | S            | q        | Fi  | S [ω Fi        | ]   | (12.12) |
|     |     |     |       |              | F(i+1)   |     | F(i+1)         |     |         |
|     |     |     |       | −k           | ∗(cid:3) | −D  | −ω             |     |         |
|     |     |     |       | S q          | (i−1) q  | Fi  | S [ω Fi F(i−1) | ],  |         |
F
where k > 0 and k ≥ 0 are scalars, Γ is defined in (12.10), D is a
|     | G   |     |     | S   |     |     | Gi  |     | S   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
symmetrical positive-semidefinite matrix, and qˆrepresents the vector part of
the unit quaternion. Note that (12.12) is a direct application of (6.1).
Similar to (12.11), the proposed control effort ν is given by
Fi
|     |     |      | =−K |      | −λd)−Γ |     | λ˙      |        |         |
| --- | --- | ---- | --- | ---- | ------ | --- | ------- | ------ | ------- |
|     |     | ν Fi |     | G (λ | Fi F   | Gi  | Fi      |        |         |
|     |     |      | −K  |      | −λ     | ]−D | [λ˙ −λ˙ |        |         |
|     |     |      |     | [λ   |        |     |         | ]      | (12.13) |
|     |     |      |     | S Fi | F(i+1) |     | S Fi    | F(i+1) |         |
|     |     |      | −K  | [λ   | −λ     | ]−D | [λ˙ −λ˙ | ],     |         |
|     |     |      |     | S Fi | F(i−1) |     | S Fi    | F(i−1) |         |
where K G is a symmetricalpositive-definite matrix, Γ Gi is defined in (12.10),
and K and D are symmetrical positive-semidefinite matrices. Note that
|         | S   | S        |             |     |            |     |     |     |     |
| ------- | --- | -------- | ----------- | --- | ---------- | --- | --- | --- | --- |
| (12.13) | is  | a direct | application |     | of (5.10). |     |     |     |     |
Remark 12.4. Note that the matrices in (12.11), (12.12), and (12.13) can
be chosen differently based on specific requirements to change the effective
weightsoftranslation,rotation,andexpansion/contraction.In(12.11),(12.12),
and (12.13), the first two terms are used to drive E to zero, the third and
G

| 236 12 | Deep Space | Spacecraft | Formation | Flying |     |     |
| ------ | ---------- | ---------- | --------- | ------ | --- | --- |
fourth terms are used to drive the ith and (i + 1)th coordination variable
instantiations into consensus, and the fifth and sixth terms are used to drive
(i−1)th
the ith and coordinationvariable instantiations into consensus. The
second term, that is, the formation feedback term is also used to slow down
the ith virtual structure when the ith spacecraft has a large tracking error.
This strategy requires that each spacecraft know the coordination variable
instantiations of its neighbors, which can be accomplished by nearest neigh-
bor communication. From (12.11), (12.12), and (12.13), we can also see that
besides ξ i−1 , ξ , and ξ , the control laws for the ith coordination variable
|     | i   | i+1 |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
instantiation also require the current constant formation pattern ξd and X˜
i
(cid:13)(cid:14)
| through | the formation | feedback | gain | matrix | Γ . |     |
| ------- | ------------- | -------- | ---- | ------ | --- | --- |
Gi
| 12.3.3 Convergence |     | Analysis |     |     |     |     |
| ------------------ | --- | -------- | --- | --- | --- | --- |
From (12.4), (12.5), (12.7), and (12.8), the dynamics for the ith space-
|     |     |     | X˜˙ | f(X˜ |     |     |
| --- | --- | --- | --- | ---- | --- | --- |
craft can be represented by = ,ξ ), where f(·,·) can be determined
|     |     |     | i   | i i |     |     |
| --- | --- | --- | --- | --- | --- | --- |
from those equations. From (12.9), (12.11), (12.12), and (12.13), the dy-
namics for the ith coordination variable instantiation can be represented by
ξ˙ = g(ξ ,ξ ,ξ ,X˜ ), where g(·,·,·,·) can also be determined from those
| i   | i−1 i i+1 | i   |     |     |     |     |
| --- | --------- | --- | --- | --- | --- | --- |
equations. Therefore, the coupled dynamics of the whole system composed
of n spacecraft and n coordination variable instantiations are time-invariant
with states X˜ and ξ , i = 1,··· ,n. Theorem F.3 will be used to prove the
i i
| main theorem | for convergence |     | of the | whole | system. |     |
| ------------ | --------------- | --- | ------ | ----- | ------- | --- |
Theorem 12.5.If the control strategy for each spacecraft is given by (12.7)
and (12.8)andthecontrolstrategyforeachcoordination variable(cid:7)instantiation
n
is given by (12.11), (12.12), where k G >4k S , and (12.13), then e Ti (t)+
i=1
| E(t)→0, | as t→∞. |     |     |     |     |     |
| ------- | ------- | --- | --- | --- | --- | --- |
Proof: For the system consisting of n spacecraft and n coordination variable
| instantiations, | consider | the  | Lyapunov | function | candidate: |         |
| --------------- | -------- | ---- | -------- | -------- | ---------- | ------- |
|                 |          | V =V | +V       | +V       | +V ,       | (12.14) |
|                 |          |      | sp       | Ft       | Fr Fe      |         |
where

12.3 Decentralized Formation Control Strategies 237
(cid:11) (cid:12)
(cid:2)n
1 1 1
V = r˜TK r˜ + v˜Tv˜ +k q˜Tq˜ + ω˜TJ ω˜ ,
sp 2 i ri i 2 i i qi i i 2 i i i
i=1
(cid:2)n
1
V = [r −r ]TK [r −r ]
Ft 2 Fi F(i+1) S Fi F(i+1)
i=1
(cid:2)n (cid:13) (cid:14)
1
+ r˜T K r˜ +vT v ,
2 Fi G Fi Fi Fi
i=1
(cid:2)n
V = k [q −q ]T[q −q ]
Fr S Fi F(i+1) Fi F(i+1)
i=1
(cid:11) (cid:12)
(cid:2)n
1
+ k q˜T q˜ + ωT J ω ,
G Fi Fi 2 Fi F Fi
i=1
(cid:2)n
1
V = [λ −λ ]TK [λ −λ ]
Fe 2 Fi F(i+1) S Fi F(i+1)
i=1
(cid:2)n 4 5
1
+ λ˜T K λ˜ +λ˙T λ˙ .
2 Fi G Fi Fi Fi
i=1
Withproposedcontrolforce(12.7)foreachspacecraft,thesecondequation
in translational dynamics (12.4) for the ith spacecraft can be rewritten as
v˜˙ =−K r˜ −K v˜. Applying Lemma D.1, the derivative of V is
i ri i vi i sp
(cid:2)n
V˙ = (−v˜TK v˜)
sp i vi i
i=1
(cid:22) (cid:23)
(cid:2)n
(cid:2) 1
+ ω˜T k qd∗q +τ −τd− (ω ×J ω˜ ) .
i qi i i i i 2 i i i
i=1
From(12.6),τd =J ω˙d+ωd×(J ωd).Withproposedcontroltorque(12.8)
i i i i i i
for each spacecraft, after some manipulation, we obtain
(cid:2)n (cid:13) (cid:14)
V˙ = −v˜TK v˜ −ω˜TK ω˜ ≤0. (12.15)
sp i vi i i ωi i
i=1
Differentiating V gives
Ft
(cid:2)n
V˙ = vT {K [r −r ]
Ft Fi S Fi F(i+1)
i=1
f
+K S [r Fi −r F(i−1) ]+K G r˜ Fi +
m
Fi}.
F
With control force (12.11) for each coordination variable instantiation,

238 12 Deep Space Spacecraft Formation Flying
(cid:2)n
V˙ =− {vT Γ v
Ft Fi Gi Fi
i=1
+[v −v ]TD [v −v ]}≤0. (12.16)
Fi F(i+1) S Fi F(i+1)
Applying Lemma D.1, the derivative of V is
Fr
(cid:2)n
V˙ = [ω −ω ]Tk q∗(cid:3) q
Fr Fi F(i+1) S F(i+1) Fi
i=1
(cid:2)n
(cid:3) 1
+ ωT (k qd∗q +τ − ω ×J ω ),
Fi G F Fi Fi 2 Fi F Fi
i=1
and after some manipulation,
(cid:2)n
V˙ Fr = ω F T i (k S q F ∗(cid:3) (i+1) q Fi −k S q F ∗(cid:3) i q F(i−1) +k G q (cid:3) F d∗q Fi +τ Fi ).
i=1
With proposed control torque (12.12), for each coordination variable instan-
tiation,
(cid:2)n
V˙ =− [ωT Γ ω
Fr Fi Gi Fi
i=1
+(ω −ω )TD (ω −ω )]≤0. (12.17)
Fi F(i+1) S Fi F(i+1)
Similar to V˙ , with proposed control effort (12.13) for each coordination
Ft
variable instantiation, the derivative of V is
Fe
(cid:2)n
V˙ =− {λ˙T Γ λ˙
Fe Fi Gi Fi
i=1
+[λ˙ −λ˙ ]TD [λ˙ −λ˙ ]}≤0. (12.18)
Fi F(i+1) S Fi F(i+1)
From (12.15), (12.16), (12.17), and (12.18), it is obvious that V˙ = V˙ +
sp
V˙ +V˙ +V˙ ≤ 0. Let Ω = {(X˜ ,··· ,X˜ ,ξ˜,··· ,ξ˜ )|V˙ = 0}. Note that
Ft Fr Fe 1 n 1 n
V˙ ≡0, i.e., V˙ =V˙ =V˙ =V˙ ≡0, implies that v˜ ≡0, ω˜ ≡0, v ≡0,
sp Ft Fr Fe i i Fi
ω ≡0, λ˙ ≡0, i=1,··· ,n.
Fi Fi
Because v˜ ≡ 0, we know that r˜ ≡ 0 from (12.4) and (12.7). Because
i i
(cid:2)
ω˜ ≡ 0, we also know that qd∗q ≡ 0 from (12.5) and (12.8), which then
i i i
implies that q ≡qd, i.e., q˜ ≡0.
i i i
Then, following v ≡ 0, from (12.11) and the second equation in (12.9),
Fi
it can be seen that
K r˜ +K [r −r ]
G Fi S Fi F(i+1)
+K S [r Fi −r F(i−1) ]≡0, i=1,··· ,n,

|       |     |            |     | 12.3 | Decentralized | Formation | Control | Strategies | 239 |
| ----- | --- | ---------- | --- | ---- | ------------- | --------- | ------- | ---------- | --- |
| which | is  | equivalent | to  |      |               |           |         |            |     |
−r˜
|     |     |     |     |     | K r˜   | +K [r˜       |        | ]   |         |
| --- | --- | --- | --- | --- | ------ | ------------ | ------ | --- | ------- |
|     |     |     |     |     | G      | Fi S Fi      | F(i+1) |     |         |
|     |     |     |     | −r˜ |        | ]≡0, i=1,··· |        |     |         |
|     |     |     | +K  | [r˜ | F(i−1) |              |        | ,n. | (12.19) |
S Fi
|      |       |     |               |     |      |            |       | ⊗K  | ⊗K ≡ |
| ---- | ----- | --- | ------------- | --- | ---- | ---------- | ----- | --- | ---- |
| From | Lemma |     | 11.4, (12.19) | can | also | be written | as (I | +C  | )r˜  |
|      |       |     |               |     |      |            | n     | G   | S F  |
(cid:2)
0, where r˜ = [r˜T ,··· ,r˜T ]T and C is the circulant matrix defined in
|     |     | F   | F1  | Fn  |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Lemma 11.4. Based on Lemmas C.8 and 11.4, I ⊗K is positive definite
n G
|     | C⊗K                                                      |      |          |               |     |              |      | ≡0.  |     |
| --- | -------------------------------------------------------- | ---- | -------- | ------------- | --- | ------------ | ---- | ---- | --- |
| and |                                                          | S is | positive | semidefinite. |     | Thus we know | that | r˜ F |     |
|     | Followingaproceduresimilartotheabove,wecanalsoshowthatλ˜ |      |          |               |     |              |      |      | ≡0  |
Fi
|         | λ˙  | ≡0. |     |     |     |     |     |     |     |
| ------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| because |     | Fi  |     |     |     |     |     |     |     |
≡0,from(12.12)andthe
|     | Alsofollowingω |     |     |     |     |     | fourthequationin(12.9),we |     |     |
| --- | -------------- | --- | --- | --- | --- | --- | ------------------------- | --- | --- |
Fi
know that
|     | (cid:3) |      | q∗(cid:3) |     | q∗(cid:3) |           |         |     |         |
| --- | ------- | ---- | --------- | --- | --------- | --------- | ------- | --- | ------- |
|     | k q     | d∗q  | +k        | q   | +k        | q ≡0,     | i=1,··· | ,n. | (12.20) |
|     | G       | F Fi | S F(i+1)  | Fi  | S         | F(i−1) Fi |         |     |         |
Note that (12.20) is a special case of (6.5), where the interaction topology is
a bidirectional ring. Then following the proof of Theorem 6.2, we can show
(cid:3) d∗q
that q ≡0, which implies that q(cid:18) ≡q(cid:18) d, i.e., q˜ ≡ (cid:18) 0, if(cid:18) k >4k .
|     | F   | Fi  |     |     |     | Fi (cid:18)F | Fi  | G                 | S   |
| --- | --- | --- | --- | --- | --- | ------------ | --- | ----------------- | --- |
|     |     |     |     |     |     | (cid:18)     |     | (cid:18) (cid:18) |     |
Therefore, by Theorem F.3, (cid:18)X˜ (t)(cid:18) → 0, (cid:18)ξ˜(t)(cid:18) → 0, and
|     |     |     |     |     |     | i   |     | i(cid:7) |     |
| --- | --- | --- | --- | --- | --- | --- | --- | -------- | --- |
(cid:9)ξ (t)−ξ (t)(cid:9)→0,i=1,··· ,n,ast→∞.Accordingly, n e +E(t)→
|     | i   | i+1 |     |     |     |     |     | i=1 | Ti  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
t→∞.
0, as
From Theorem 12.5, we can see that each virtual structure instantiation
will achieve its final goal asymptotically and each spacecraft will also track
its desired state specified by the virtual structure asymptotically during the
maneuver.Therefore,theformationmaneuvercanbeachievedasymptotically.
12.3.4 Discussion
Notethatdifferentperformancemeasurefunctionse Ti maybechosentomea-
sure formation maintenance. For example, e = X˜TPX˜ , where P is sym-
|     |     |     |     |     |     | Ti  | i   | i   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
metricalpositivedefinite.ThematrixP canbedesignedtoadjusttherelative
weights of translational and rotational formation error based on certain re-
quirements. The motivation for the design of the nonlinear gain matrices Γ
Gi
is to meet the following requirements. When a spacecraft is out of its desired
configuration, that is, e is large, its coordination variable instantiation will
Ti
slow down or even stop, allowing the spacecraft to regain formation. When
a spacecraft is maintaining its desired configuration, that is, e is small, its
Ti
coordination variable instantiation will keep moving toward its final goal at
a reasonable speed. By this design, each coordination variable instantiation
will be aimed at performing reasonably fast formation maneuvers as well as
preserving tight formation shape during the maneuver, despite control satu-
ration,disturbances,andmalfunctions.Inthischapter,wechooseacandidate
for such gain matrices as Γ = D +K e , where D is the symmetri-
|     |     |     |     | Gi  |     | G F Ti |     | G   |     |
| --- | --- | --- | --- | --- | --- | ------ | --- | --- | --- |
calpositive-definitegainmatrix,whichcorrespondsto the nominalformation

240 12 Deep Space Spacecraft Formation Flying
speed when the formation is preserved tightly, and K is the symmetrical
F
positive-definite formation gain matrix which weights the performance mea-
sure e . Of course, other choices are also feasible. If K = 0, no formation
Ti F
feedback is introduced. We will see that a formation gain matrix with larger
entriesresultsinbetterformationmaintenancebutslowerconvergencespeed.
Note that
e →0⇒Γ →D ,
Ti Gi G
e →∞⇒Γ →∞.
Ti Gi
As a result, nonlinear gains slow down or speed up the coordination variable
instantiationbasedonhowfareachspacecraftis outofthe desiredconfigura-
tion.
Because PD-like control laws are used for each spacecraft and each co-
ordination variable instantiation, the transient specifications for each space-
craft and each coordination variable instantiation can be satisfied by design-
ing corresponding gain matrices in control laws following the design pro-
cedure for coefficients of a second-order system. For a second-order system
s2+k s+k =0, if we define rise time t and damping ratio ζ, then natural
1 2 r
frequencyω isapproximately1.8/t .Therefore,ifweletk =ω2 =(1.8/t )2
n r 2 n r
and k = 2ζω = 2ζ(1.8/t ), the transient specifications for the system are
1 n r
satisfied. We can design K , k , K , and k according to k , and design
ri qi G G 2
K , K , and D according to k . For example, K and K can be defined
vi ωi G 1 ri vi
as k I and k I , respectively, where I is a 3×3 identity matrix.
2 3 1 3 3
Example 12.6. LetK =I andK =D =0in(12.11).Notethatthetrans-
G 3 S S
lationaldynamicsoftheithcoordinationvariableinstantiationcanberewrit-
ten as r¨˜ +Γ r˜˙ +K r˜ =0,where r˜ =r −rd =[r˜ ,r˜ ,r˜ ]T.
Fi Gi Fi G Fi Fi Fi Fi Fxi Fyi Fzi
Figure 12.4 shows a plot of r˜ for different choices of Γ . We can see that
Fxi Gi
thedynamicsoftheithcoordinationvariableinstantiationevolvemoreslowly
as the elements of Γ are increased to be sufficiently large, that is, it takes
Gi
a longertime for the ith coordinationvariable instantiationto achieve its de-
sired state. When Γ →∞, the coordination variable instantiation will stop
Gi
evolving. (cid:13)(cid:14)
Moreover, for each spacecraft, if we define a translational tracking error
for the ith spacecraft as E = 1r˜TK r˜ + 1(cid:9)v˜(cid:9)2, E decreases during the
ti 2 i ri i 2 i ti
maneuver and r˜TK r˜ is bounded by 2E (0) −(cid:9)v˜(cid:9)2. Similarly, if we de-
i ri i ti i
fine a rotational tracking error as E = k (cid:9)q˜(cid:9)2 + 1ω˜ J ω˜ , E decreases
ri qi i 2 i i i ri
during the maneuver, and (cid:9)q˜(cid:9)2 is bounded by 1 (E (0)− 1ω˜ J ω˜ ). For
i kqi ri 2 i i i
each coordination variable instantiation, following the proof for V˙ , V˙ ,
Ft Fr
and V˙
Fe
, we know that V
Ft
, V
Fr
, a(cid:7)nd V
Fe
are bounded by V
Ft
(0), V
Fr
(0),
and V (0), respectively.Therefore, n [r −r ]TK [r −r ]≤
Fe (cid:7) i=(cid:7)1 Fi(cid:18) F(i+1) S(cid:18) Fi F(i+1)
2V (0), n r˜T K r˜ ≤ 2V (0), n (cid:18) q −q (cid:18)2 ≤ 1 V (0),
Ft i=1 Fi G Fi Ft i=1 Fi F(i+1) kS Fr

|     |     |     |     |     | 12.4 Simulation | Results | 241 |
| --- | --- | --- | --- | --- | --------------- | ------- | --- |
Γ Gi =2I 3
|     | 1   |     |     |     |     |     | Γ =10 I |
| --- | --- | --- | --- | --- | --- | --- | ------- |
Gi =20I 3
Γ Gi 3
0.9
0.8
0.7
0.6
dr− ixF
0.5
ixF
r
0.4
0.3
0.2
0.1
0
|     | 0   |     | 20  | 40 60 | 80  | 100 | 120 |
| --- | --- | --- | --- | ----- | --- | --- | --- |
Time (s)
Fig. 12.4. Plot of r˜ with initial conditions r˜ (0) = 1 and r˜˙ (0) = 0 for
|           |         |     | Fxi  |     | Fxi | Fxi |     |
| --------- | ------- | --- | ---- | --- | --- | --- | --- |
| different | choices |     | of Γ |     |     |     |     |
Gi
| (cid:7) |               |          |          | (cid:7)       |           |        |      |
| ------- | ------------- | -------- | -------- | ------------- | --------- | ------ | ---- |
|         | n             | (cid:9)2 |          | n             |           |        |      |
|         | (cid:9)q˜     | ≤        | 1 V (0), | [λ −λ         | ]TK [λ −λ | ]≤2V   | (0), |
|         | i=(cid:7)1 Fi |          | kG Fr    | i=1 Fi F(i+1) | S Fi      | F(i+1) | Fe   |
|         | n             | λ˜T      | λ˜ ≤2V   |               |           |        |      |
| and     |               | K        |          | (0).          |           |        |      |
|         | i=1           | Fi       | G Fi     | Fe            |           |        |      |
| 12.4    | Simulation    |          | Results  |               |           |        |      |
In this section, we consider a scenariowith nine spacecraft.In the scenario,a
mothership with mass equal to 1500 kg is located one kilometer away from a
plane where eight daughter spacecraft each with mass 150 kg are distributed
equally along a circle with a diameter of 1 kilometer in the plane. The con-
figuration of the nine spacecraft is shown in Fig. 12.5. We assume that the
nine spacecraftformationevolveslike a rigidstructure, that is,the formation
shape is preserved, and each spacecraft preserves a fixed relative orientation
| within | the | formation | throughout | the maneuvers. |     |     |     |
| ------ | --- | --------- | ---------- | -------------- | --- | --- | --- |
We simulate a scenario where the nine spacecraft start from rest with
some initial position and attitude errors and then perform a group rotation
of45◦
aboutthe inertialz axis.Here we assume thateachplace holder inthe
formationhasthesameorientation,thatis,qd isthesameforeachspacecraft.
iF
Insimulation,weinstantiatealocalcopyofthecoordinationvariableξineach

242 12 Deep Space Spacecraft Formation Flying
600
500
400
300
200
100
0
−600
−400
−200
0 −600 −400
200 −200
0
400 200
400
X 600 600
Y
Z
#1
#8 #9
#2
#7
#3
#6 #4
#5
Fig. 12.5. The geometric configuration of ninespacecraft
spacecraftanddrivethemintoconsensususingthecontrolstrategyintroduced
in Section 12.3.2. To show the robustness of the control strategy, we start
the coordination variable implementation in each spacecraft at a different
time and introduce a different sample time, varying from 0.4 seconds to 0.6
seconds for each coordination variable instantiation. Various communication
delays are also added among spacecraft. Three cases will be compared in
this section. These include cases without actuator saturation and formation
feedback (Case I), with actuator saturation but without formation feedback
(Case II), with both actuator saturation and formation feedback (Case III).
Here,weassumethatthecontrolforceandcontroltorqueforspacecraft#1are
saturated at |f |,|f |,|f |=2 N and |τ |,|τ |,|τ |=0.0006 Nm, respectively,
x y z x y z
andthe controlforce andcontroltorquefor allother spacecraftare saturated
at |f |,|f |,|f |=1 N and |τ |,|τ |,|τ |=0.0003 Nm, respectively.
x y z x y z
(cid:7)For (cid:18)these (cid:18)simulations, the(cid:7)average coordination error is defined as
1 n (cid:18) ξ −ξ¯(cid:18) , where ξ¯ = 1 n ξ . The average coordination error in
n i=1 i n i=1 i
these three cases is plotted in Fig. 12.6. We can see that in all three cases,
eachinstantiationofthecoordinationvariableisdrivenintoconsensusasymp-
totically. Also, the average coordination error is large during the initial time
intervalbecauseeachlocalinstantiationstartsatadifferenttime.CasesIand
IIareidenticalbecausetheactuatorsaturationforeachspacecraftdoesnotaf-
fectthedynamicsofthevirtualstructurewhenthereisnoformationfeedback

12.4 Simulation Results 243
fromeachspacecrafttoitscoordinationvariableinstantiation.Themaximum
average coordination error in Case III is larger than that in the other two
casesbecauseformationfeedbackis introducedforeachcoordinationvariable
instantiation, which may add some dissimilarities between different instanti-
ations.
Average coodination vector error
0.014
No saturation, no formation feedback
With saturation, no formation feedback
With saturation and formation feedback
0.012
0.01
0.008
0.006
0.004
0.002
0
0 50 100 150
Time (min)
Fig.12.6.Theaveragecoordinationerrorofthecoordinationvariableinstantiations
In Fig. 12.7, we plot the absolute position and attitude tracking errors
for spacecraft #1, #(cid:18)4, and(cid:18)#7 in these three cases. The position tracking
e(cid:18)rror is(cid:18)defined as (cid:18) r
i
−r
i
d (cid:18) , and the attitude tracking error is defined as
(cid:18) q −qd (cid:18) . We can see that the tracking errors in each case will decrease to
i i
zero asymptotically by using the control law given in Section 12.3.1. The
absolutepositionandattitude trackingerrorsinCaseIIaremuchlargerthan
those in the other two cases due to the actuator saturation. In Case III,
with formation feedback, the absolute position and attitude tracking errors
are similar to those in Case I, even if there is actuator saturation. When we
increasetheentriesinthegainmatrixK toincreaseformationfeedback,the
F
absolutetrackingerrorscanbedecreasedfurther,butthesystemconvergence
time will increase accordingly.

| 244 | 12            | Deep Space  | Spacecraft    | Formation | Flying     |                    |               |
| --- | ------------- | ----------- | ------------- | --------- | ---------- | ------------------ | ------------- |
|     |               | Case I: (a) |               |           |            | x 10−4 Case I: (b) |               |
|     | 1.5           |             |               |           | 6          |                    |               |
|     |               |             | Spacecraft #1 |           |            |                    | spacecraft #1 |
|     | )m(  ||dr−r|| |             | Spacecraft #4 |           |            |                    | spacecraft #4 |
|     | 1             |             | Spacecraft #7 |           | ||dq−q|| 4 |                    | spacecraft #7 |
i
|     | i     |              |     |     | i   |                     |         |
| --- | ----- | ------------ | --- | --- | --- | ------------------- | ------- |
|     | i 0.5 |              |     |     | 2   |                     |         |
|     | 0     |              |     |     | 0   |                     |         |
|     | 0     | 50           | 100 | 150 |     | 0 50                | 100 150 |
|     |       | Case II: (a) |     |     |     | x 10−3 Case II: (b) |         |
|     | 30    |              |     |     | 6   |                     |         |
)m(  ||dr−r||
|     | 20  |     |     |     | ||dq−q|| 4 |     |     |
| --- | --- | --- | --- | --- | ---------- | --- | --- |
i
|     | i    |               |     |     | i   |                      |         |
| --- | ---- | ------------- | --- | --- | --- | -------------------- | ------- |
|     | i 10 |               |     |     | 2   |                      |         |
|     | 0    |               |     |     | 0   |                      |         |
|     | 0    | 50            | 100 | 150 |     | 0 50                 | 100 150 |
|     |      | Case III: (a) |     |     |     | x 10−4 Case III: (b) |         |
|     | 1.5  |               |     |     | 6   |                      |         |
)m(  ||dr−r||
|     | 1   |     |     |     | 4   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
||dq−q||
i
|     | i   |     |     |     | i   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
|     | 0.5 |     |     |     | 2   |     |     |
i
|     | 0   |            |     |     | 0   |            |         |
| --- | --- | ---------- | --- | --- | --- | ---------- | ------- |
|     | 0   | 50         | 100 | 150 |     | 0 50       | 100 150 |
|     |     | Time (min) |     |     |     | Time (min) |         |
Fig. 12.7. The absolute position and attitude tracking errors. In Case I, there
is neither actuator saturation nor formation feedback. In Case II, there is actuator
saturationbutnoformationfeedback.InCaseIII,therearebothactuatorsaturation
| and | formation | feedback. |     |     |     |     |     |
| --- | --------- | --------- | --- | --- | --- | --- | --- |
InFig.12.8,weplottherelativepositionandattitudeerrorsbetweensome
of the spacecraftin these three cases.Based on the configuration,the desired
relative distance between spacecraft #1 and #2 and the desired relative dis-
tancebetweenspacecraft#1and#6shouldbeequal.Thedesiredrelativedis-
tancebetweenspacecraft#3and#7andthedesiredrelativedistancebetween
spacecraft #5 and #9 should also be equal. We plot |(cid:9)r −r (cid:9)−(cid:9)r −r (cid:9)|
|     |           |                     |             |             |             | 1      | 2 1 6             |
| --- | --------- | ------------------- | ----------- | ----------- | ----------- | ------ | ----------------- |
|     | |(cid:9)r | −r (cid:9)−(cid:9)r | −r (cid:9)| |             |             |        |                   |
| and | 3         | 7 5                 | 9           | in part (a) | as examples | to see | how well the for- |
mation shape is preserved. The desired relative attitude between each space-
craft should be equal based on our previous assumption. We plot (cid:9)q −q (cid:9),
1 4
| (cid:9)q | −q  | (cid:9), (cid:9)q −q | (cid:9) |             |          |            |                   |
| -------- | --- | -------------------- | ------- | ----------- | -------- | ---------- | ----------------- |
|          |     | and                  | in      | part (b) as | examples | to see how | well the relative |
|          | 4 7 | 7                    | 1       |             |          |            |                   |
orientation relationships between these spacecraft are preserved. Similarly,
the relative position tracking errors in Case II are larger than those in the
other two cases due to control force saturation. In Case III, with formation
feedback, the relative position errors are smaller than those in Case II. The
relative attitude errors in Case III are even smaller than those in the other
| two | cases | due to formation | feedback. |     |     |     |     |
| --- | ----- | ---------------- | --------- | --- | --- | --- | --- |

|     |             |     | 12.5        | Notes 245 |
| --- | ----------- | --- | ----------- | --------- |
|     | Case I: (a) |     | Case I: (b) |           |
)m( rorre noitisop evitaleR
| 0.4 |                      | rorre edutitta evitaleR 0.04 |     |         |
| --- | -------------------- | ---------------------------- | --- | ------- |
|     | abs(||r−r||−||r−r||) |                              |     | ||q−q|| |
|     | 1 2 1 6              |                              |     | 1 4     |
| 0.3 | abs(||r−r||−||r−r||) | 0.03                         |     | ||q−q|| |
|     | 3 7 5 9              |                              |     | 4 7     |
||q−q||
| 0.2 |              | 0.02 |              | 7 1     |
| --- | ------------ | ---- | ------------ | ------- |
| 0.1 |              | 0.01 |              |         |
| 0   |              | 0    |              |         |
| 0   | 50 100 150   | 0    | 50           | 100 150 |
|     | Case II: (a) |      | Case II: (b) |         |
)m( rorre noitisop evitaleR
| 1.5 |     | rorre edutitta evitaleR 0.04 |     |     |
| --- | --- | ---------------------------- | --- | --- |
0.03
1
0.02
0.5
0.01
| 0                           |               | 0    |               |         |
| --------------------------- | ------------- | ---- | ------------- | ------- |
| 0                           | 50 100 150    | 0    | 50            | 100 150 |
| )m( rorre noitisop evitaleR | Case III: (a) |      | Case III: (b) |         |
| 0.4                         |               | 0.04 |               |         |
rorre edutitta evitaleR
| 0.3 |            | 0.03 |            |         |
| --- | ---------- | ---- | ---------- | ------- |
| 0.2 |            | 0.02 |            |         |
| 0.1 |            | 0.01 |            |         |
| 0   |            | 0    |            |         |
| 0   | 50 100 150 | 0    | 50         | 100 150 |
|     | Time (min) |      | Time (min) |         |
Fig. 12.8. The relative position and attitude errors. In Case I, there is neither
actuatorsaturation norformation feedback.InCaseII,thereisactuatorsaturation
but no formation feedback. In Case III, there are both actuator saturation and
formation feedback.
In Fig. 12.9, we plot the control effort for spacecraft #1 in these three
cases.Wecanseethatboththecontrolforceandcontroltorqueapproachzero
asymptotically.We can alsosee that τ z saturates in Case II during the initial
time period, whereas this saturation is mitigated with formation feedback
| introduced in | Case III. |     |     |     |
| ------------- | --------- | --- | --- | --- |
12.5 Notes
The results in this chapter are based mainly on [188]. Section 12.2.1 is
from [22], and Section 12.3.4 is from [189]. For further results in spacecraft
| formation flying, | see [39,94,103,117,142,200,244,245]. |     |     |     |
| ----------------- | ------------------------------------ | --- | --- | --- |
| Acknowledgment    | is given to                          |     |     |     |
(cid:10)c2004 AIAA. Reprinted, with permission, from Wei Ren and Randal W.
Beard, “Decentralized scheme for spacecraft formation flying via the virtual
structure approach,” Journal of Guidance, Control, and Dynamics, vol. 27,
no. 1, pp. 73–82,January–February,2004.

| 246 12 Deep       | Space Spacecraft | Formation | Flying              |     |
| ----------------- | ---------------- | --------- | ------------------- | --- |
|                   | Case I: (a)      |           | x 10−4 Case I: (b)  |     |
| 1                 |                  |           | 10                  |     |
|                   |                  |           | )mN( euqrot lortnoC | τ   |
| )N( ecrof lortnoC |                  |           |                     | x   |
τ
| 0   |     |     | 5   | y   |
| --- | --- | --- | --- | --- |
τ
|     |     | f   |     | z   |
| --- | --- | --- | --- | --- |
x
| −1  |     | f   | 0   |     |
| --- | --- | --- | --- | --- |
y
f
z
| −2  |              |     | −5                  |         |
| --- | ------------ | --- | ------------------- | ------- |
| 0   | 50 100       | 150 | 0 50                | 100 150 |
|     | Case II: (a) |     | x 10−4 Case II: (b) |         |
| 1   |              |     | 6                   |         |
)mN( euqrot lortnoC
)N( ecrof lortnoC
4
0
2
−1
0
| −2  |               |     | −2                    |         |
| --- | ------------- | --- | --------------------- | ------- |
| 0   | 50 100        | 150 | 0 50                  | 100 150 |
|     | Case III: (a) |     | x 10−4 Case III: (b)  |         |
| 1   |               |     | )mN( euqrot lortnoC 6 |         |
)N( ecrof lortnoC
4
0
2
−1
0
| −2  |            |     | −2         |         |
| --- | ---------- | --- | ---------- | ------- |
| 0   | 50 100     | 150 | 0 50       | 100 150 |
|     | Time (min) |     | Time (min) |         |
Fig. 12.9. Thecontrol effortforspacecraft #1.InCase I,thereisneitheractuator
saturation nor formation feedback. In Case II, there is actuator saturation but no
formation feedback. In Case III, there are both actuator saturation and formation
feedback.
(cid:10)c2003 IEEE. Reprinted, with permission, from Wei Ren and Randal W.
Beard,“Adecentralizedschemeforspacecraftformationflyingviathevirtual
structure approach,” Proceedings of the American Control Conference, pp.
| 1746–1751,Denver, | CO, June | 2003. |     |     |
| ----------------- | -------- | ----- | --- | --- |

13
Cooperative Fire Monitoring with Multiple
UAVs
Theobjectiveofthischapteristoexplorethefeasibilityofusingmultiplelow-
altitude, short endurance (LASE) UAVs to monitor and track cooperatively
the propagation of large forest fires. A real-time algorithm is described for
tracking the perimeters of fires with an onboard infrared sensor. Using this
algorithm, we apply the design scheme in Section 8.4.1 to develop a distrib-
utedmulti-UAVapproachtomonitoringtheperimeterofafire.Weproposea
distributedloadbalancingalgorithmthatextendsthediscrete-timeconsensus
algorithm in Chapter 2. The UAVs are assumed to have limited communica-
tion and sensing range. The effectiveness of the approach is demonstrated in
simulation using a six degree-of-freedom dynamic model for the UAV and a
numerical propagation model for the forest fire. Salient features of the ap-
proachinclude the ability to monitor a changing fire perimeter, the ability to
addandremoveUAVssystematicallyfromtheteam,andtheabilitytosupply
time-critical information to firefighters.
13.1 Problem Statement
Forest fires cause billions of dollars in damage to property and the environ-
ment every year. To combat forest fires effectively, their early detection and
continuoustrackingisvital.Withthehelpofadvancedimageprocessingtech-
niques, many methods have been developed to detect forest fires in remote
regions using satellite images (see [77,112]). Such images are typically cap-
turedbylowearth-orbitingsatelliteswithanorbitalperiodofabout10hours
and with a resolution that is sufficient only for fire detection. However, fire-
fightersneedfrequentandhigh-qualityinformationupdatesontheprogressof
fires to fight them effectively and safely. Because current forest fire monitor-
ingtechniquesaredeficient,firefightersareoftenrequiredtoenterfireregions
with little knowledge of how and where the fire is propagating, placing their
lives at risk. For these reasons, there is a need to develop more effective fire
monitoring technologies.

248 13 Cooperative Fire Monitoring with Multiple UAVs
High-altitude, long-endurance (HALE) UAVs such as the ALTAIR have
thepotentialtoincreaseimageresolutionandupdateratesoversatellitebased
systems (see [8]). However, the limited availability of HALE systems during
peak fire seasonmaylimit their overalleffectiveness and emphasizes the need
for lower cost, locally implementable systems.
Low-altitude, short-endurance (LASE) UAVs are expected to be a key
technology for enhanced fire monitoring. Flying at low altitude, these UAVs
can capture high-resolution imagery and broadcast frequent updates to fire
crews. NASA is actively pursuing this possibility with ongoing research
projects aimed at tracking the growth of fires using LASE UAVs (see [248]).
However,anumberofchallengeshavetobe solvedbeforeLASEUAVscanbe
used for fire monitoring.First, with the fire growingand changing directions,
UAVs need to be able to plan their path using limited real-time information.
Second,LASEUAVs typicallycannotcarryenoughfuelto endurealongfire-
fighting mission, which means that the UAV must have the intelligence to
return to the home base for refueling. Furthermore, for large forest fires, the
information update rate may still be too low if only a single LASE UAV is
employed. Finally, we note that fires generate tremendous heat and turbu-
lence directly above the burning region. Therefore, crossing directly over the
fire will place low-altitude UAVs at significant risk. As a consequence, LASE
UAVs are effectively restricted to the air space over the unburned region of
the fire.
The objective of this chapter is to explore the feasibility of using multiple
LASE UAVs to monitor and trackcooperativelythe propagationoflarge for-
est fires. By using teams of inexpensive, rapidly deployable LASE UAVs, the
complexity of the system will shift from the hardware platform to the coop-
erative control strategies employed to coordinate fire monitoring operations.
Although teams of LASE UAVs will be more robust to single-point failures
than a single satellite or a HALE UAV, several technical challenges must be
addressed to enable their successful implementation. Issues addressed in this
chapterinclude overcominglimited communicationrangeandflightduration,
developing a suitable coordination strategy for fire monitoring, and forming
team consensus in the presence of noisy or uncertain information.
Figure 13.1 shows the forest fire monitoring scenario considered in this
chapter. The objective is to capture images along the perimeter of the fire
anduploadthelocationofthefireperimeter(withassociatedimagery)tothe
base station as frequently and with as little latency as possible.
We make the following assumptions:First, we assume that eachUAV can
collect or receive sufficient information onboard to plan and adjust its path
autonomously. This allows the UAV to adapt its path according to the fire
perimeter.Inparticular,eachUAVisassumedtobeequippedwithaninfrared
camerathatcapturesimagesofasmallregionbeneathit.Aninfraredcamera
isparticularlysuitableforfiremonitoringbecauseitdetectstheregionsofthe
ground with the highest temperature. Second, each UAV is assumed to have
limited communicationrange,whichmeans that itcannotuploaddata to the

13.1 Problem Statement 249
Base station Checkpoint 1
2
tniopkcehC
Checkpoint 3
Checkpoint
4
Fig. 13.1. Fire monitoring scenario. The line represents thefire perimeter. A base
station deploys multiple UAVsto monitor thepropagation of thefire.
base station unless it is within a certain range of the station, and it cannot
communicate with other UAVs unless they are within a specified proximity.
Finally,eachUAV is assumedto havelimitedfuel, whichimplies thatit must
periodically return to the base station for refueling.
The delay between the times when images are collected and when they
are transmitted to the base station, can serve as a measure of the quality of
the fire monitoring algorithm. Let δ(x,t) denote the latency associated with
informationaboutthepositionxalongtheperimeterattimet.Astimepasses,
the information at the base station grows older (more latent) until a UAV
arrives to transmit the latest information it has gathered. For a particular
position x along the perimeter, δ(x,t) will simply increase with time until it
is replaced by the data downloaded from a UAV. Figure 13.2 gives a typical
depictionoflatencyevolutionforaparticularpointx ontheperimeterofthe
0
fire. The vertical edges of the sawtooth waveform represent the transmission
of data fromthe UAV to the base station,and the linearly increasingportion
ofthewaveformrepresentstheincreaseinlatencybetweenUAVupdates.The
minimum latency δ corresponds to the time of flight between the point of
min
interest and the base station. The maximum latency depends on the total
time required to make an observation at x and to deliver that data to the
0
base station.
In this chapter we develop a cooperative surveillance strategy that mini-
mizesthelatencyoffireperimetermeasurementsdeliveredtothebasestation.
This is done by minimizing the time of flight between points on the perime-
ter and the base station and by maximizing the frequency of measurement
updates delivered to the base station.

250 13 Cooperative Fire Monitoring with Multiple UAVs
Fig. 13.2. Latency between updatesfor a point x 0 on theperimeter
13.2 Fire Perimeter Tracking for a Single UAV
Cooperativefire monitoring relies upon the ability of eachindividual UAV to
trackthe fireperimeter independently.Inthis section,wewillbrieflydescribe
a robust fire tracking algorithm that we have implemented in simulation. We
assume that each UAV is equipped with an infrared camera on a pan and
tilt gimbal and an autopilot with functionality similar to the one described
in [21,108]. Our approach to fire perimeter tracking can be summarized in
six steps that are each performed at the frame rate of the onboard infrared
camera.
1. Scan through the infrared image, labeling each pixel as (a) burned (or
currently burning) and (b) unburned.
2. Usealinearclassifiertosegmenttheimageintotwopartitionswithburned
elements in one partition and unburned in the other.
3. Project the segmentation line from the camera frame into the world co-
ordinates of the UAV.
4. Construct the set of reachable points T seconds into the future and pa-
rameterize this set as a function of the roll angle. Details about this con-
struction have been reported in [23].
5. Command the roll angle that corresponds to the point in the reachable
setthatisadistanced(inworldcoordinates)ontheunburnedsideofthe
fire perimeter.
6. Command the pan and tilt angles of the camera gimbal so that the seg-
mentation line of the linear classifier divides the image into two equal
parts.
This approach is well suited to tracking the perimeter of a fire because it
usuallyevolvesinanoncontiguousway.Fireswilljumpoverroadsandstreams
and spread around rocky terrain. In addition, fire spreads faster uphill than
downhill. In mountainous environments, this characteristic leads to fingering
phenomena where fires spread in finger patterns along ridges in the terrain.
ThelinearclassifierusedinStep2effectivelysmoothsthroughnoncontiguous
boundaries.ThedistancedinStep5ensuresthattheUAVdoesnotflydirectly

13.3 Cooperative Team Tracking 251
over the burning fire, but rather flies at a safe offset distance d. Maneuvering
the gimbalinStep6 ensuresthe continuedeffectivenessofthe linearclassifier
in Step 2.
The fire tracking scheme described in this section has been successfully
demonstrated in computer simulation. Results will be briefly described in
Section 13.4.
13.3 Cooperative Team Tracking
For firefighters on the perimeter of a fire, frequent updates about the pro-
gression of the fire are critical for safety. Motivated by the design scheme
in Section 8.4.1, this section develops a distributed monitoring scheme that
allows transmitting perimeter information as often as possible to the base
station. We will assume that all UAVs fly at identical constant velocities.We
willalsoassumethatthefireperimeterishomeomorphictoacircle.However,
the algorithmpresentedinthis sectionwillfunctioncorrectlyifthe perimeter
ishomeomorphictoaline,andthe UAVsarecommandedtoreversedirection
when the end of the perimeter is reached.
13.3.1 Latency Minimization
When a UAV transmits its information to the base station, an associated
latency profile (in terms of time-stamped images) accompanies the data. Let
the latency of a point x at the time of the base station update be denoted
ρ(x). Note that δ(x,t) = ρ(x) when a UAV updates the base station and
δ(x,t) = ρ(x)+(t−t ) between updates. The objective is to design a
update
cooperative monitoring scheme that minimizes ρ(x) for every x and updates
the base station as often as possible.
Figure 13.3a shows the latency of the perimeter of the fire when a clock-
wise flying UAV arrives back at the base station after a complete tour of the
perimeter. The thickness of the path denotes the latency of the base station
updateofthatpoint.Becausethestateofthefireistransmittedonlyafterthe
UAVhastraversedthe entirefireperimeter,thegreatestlatencyisassociated
with data gathered at the beginning of the flight near the base station. Be-
cause the UAV is traveling at constant velocity, the latency profile is a linear
function of the distance traveled: ρ(x) = (P −x)/v, where v is the velocity
of the UAV and P is the perimeter. The base station receives updates only
as fastas the UAV cantraversethe entire fire perimeter. The total latency of
(cid:10)
one traversalis given by P ρ(x)dx=0.5P2/v.
0
Letone UAV be assignedto surveythe upper halfof the perimeter, anda
secondis assignedto the lowerhalf.If the UAVs departfromthe basestation
simultaneouslyandflyatthe samespeed,the update ratewillbe the sameas
the single UAV case (because both UAVs arrive back at the base station at
the same time), but the latency of the information on both sides of the base

| 252 | 13 Cooperative | Fire Monitoring | with Multiple | UAVs |     |
| --- | -------------- | --------------- | ------------- | ---- | --- |
v
Base
|     |     | station |     |     | Base |
| --- | --- | ------- | --- | --- | ---- |
station
Rendezvous
point
x x
|     | (a) Single | UAV |     | (b) Two UAVs |     |
| --- | ---------- | --- | --- | ------------ | --- |
Fig. 13.3. (a) Latency profile for a single UAV monitoring a static circular fire.
The thickness of the path denotes the latency of information at that point when it
istransmittedtothebasestation.(b)LatencyprofilewithapairofUAVsmonitoring
| a static | circular fire in | opposite directions. |     |     |     |
| -------- | ---------------- | -------------------- | --- | --- | --- |
station will be symmetrical and reduced, as can be seen in Fig. 13.3b. Here,
| the latency | profile | is given by |     |     |     |
| ----------- | ------- | ----------- | --- | --- | --- |
⎧
|     |     | ⎨ x | , for 0≤x≤P/2, |     |     |
| --- | --- | --- | -------------- | --- | --- |
v
ρ(x)=
⎩
|     |     | P −x | P/2<x≤P, |     |     |
| --- | --- | ---- | -------- | --- | --- |
v , for
(cid:10)
P ρ(x)dx=0.25P2/v,
| and the | overalllatency | of the scheme | is  |     | which is half |
| ------- | -------------- | ------------- | --- | --- | ------------- |
0
| that of | the single UAV | case. |     |     |     |
| ------- | -------------- | ----- | --- | --- | --- |
ForUAVsthatfollowtheperimeterandflyatconstantvelocity,thelatency
profile shownin Fig. 13.3bis the minimum possible latency for every x along
the perimeter of the fire. To see that this is true, note that the minimum
latency of data gathered at x on the perimeter is the time needed to travel
from x to the base station along the shortest path. Dividing the perimeter
equally between two UAVs ensures that the distance traveled between any
point on the perimeter and the base station is minimal. The consequence is
that adding more than two UAVs will not improve the latency profile ρ(x)
foranyparticularpointontheperimeter.However,therateatwhichupdates
occur will increase linearly with the number of UAV pairs employed and the
effective latency will be reduced. This is illustrated in Fig. 13.4 where four
UAVpairsareusedtosurveytheperimeter.Tomaintaintheminimumlatency
profile of Fig. 13.3b and to maximize the frequency of updates at the base
station, UAVs should be distributed equally around the perimeter with each
UAV assigned to monitor a segment of length P/n where n is the number of
UAVs.

13.3 Cooperative Team Tracking 253
Time
)t,x(δ
,ycnetaL
0
Pass 2 Pass 4
Pass 1 Pass 3
δ
max
Effective
latency
δ
min
Fig. 13.4. Effectivelatency forapointonaperimetersurveyedbyfourUAVpairs
13.3.2 Distributed Fire Monitoring Algorithm
For a fixed perimeter length and a fixed number of UAVs, the minimum
latency configuration occurs when pairs of UAVs are uniformly spread along
the perimeter of the fire in both directions (i.e., for every pair of UAVs, one
is headed in the clockwise direction and the other in the counterclockwise
direction). Pairsof UAVs will meet, transmit gatheredinformation, and then
eachUAVwillreverseitsdirectiontomeetitsneighborintheotherdirection.
Tofacilitate refueling,UAVs canexchangerolesatarendezvoussothatteam
members with the least fuel are nearest to the base station.
The aim of our distributed algorithm is to converge to this minimum la-
tency configuration. The algorithm must convergefor any perimeter size and
must readjust when the perimeter length or the number of pairs of UAVs
changes.Bydesigningthealgorithmsothatchangesinthesystemparameters
are propagated across the team quickly, we will be able to address insertion
and deletion of UAVs, as well as expansion and contractionof the perimeter.
The fundamental idea is for each UAV to take the action that will allow
neighboring pairs to “share” the perimeter between them. When two UAVs
meet, each has knowledge of the length just traveled from its previous ren-
dezvous.Thesumoftheselengthscanthenbe dividedequallybetweenthem:
theUAVthathastraveledtheleastwillloiteratthemidpointofthissegment
to wait for its neighbor the next time the two are to meet.
To illustrate the idea, consider a simple line segment ab with two UAVs
tasked to gather information cooperatively along the segment, as shown in
Fig. 13.5. Let (cid:2) be the distance traveled by the ith UAV from the last end-
i
Fig. 13.5. Simplesegment perimeter tracking

254 13 Cooperative Fire Monitoring with Multiple UAVs
point visited. In Fig. 13.5, UAV 1 has traveled the least, so after returning
to endpoint a, it will travel (cid:7)1+(cid:7)2 and then begin to loiter.UAV 2 will return
2
to endpoint b and then reverse direction until it encounters UAV 1. Because
UAV1traveledthe shortestdistance,itwillarriveatthemidpointofabfirst,
andwhenbotharrive,eachwillhavetraveledthesamedistance(i.e.,(cid:2) =(cid:2) )
1 2
from the endpoints which implies that the UAV pair has achieved the mini-
mum latency configuration.An example of twoUAV pairs monitoring a fixed
perimeter of size 2P is shown in Fig. 13.6.
Any change in the size of the segment will be tracked because the pair
effectively measures the current perimeter length by summing the distances
traveledfromthe endpoints. In other words,because the UAVs havememory
of the state of the perimeter from only one previous iteration, a continuous
loadbalancingalgorithmwilltrack finite changesin the perimeter. To enable
informationonthe growthofthe perimeter to be accountedfor more rapidly,
the UAV assigned to wait for its neighbor will loiter at the point a distance
(cid:7)1+(cid:7)2 fromwhere the endpoint waspreviously.By measuringthe discrepancy
2
of(cid:2) andthe newdistancebacktothe endpoint,UAV1canupdatethe loiter
1
distance to negate the effect of the growth in that region.
Adding UAVs to the perimeter is equivalent to stringing perimeter seg-
ments together that have changing endpoints: the endpoints for a segment
shared by one pair of UAVs are the outside neighbors of these UAVs. We
will use Monte Carlo simulations to verify that pairwise load balancing will
lead to team convergence. We maintain that by balancing the length shared
by every pair of UAVs, the team as a whole will spread itself evenly around
the perimeter and so achieve the minimum latency configuration. If the al-
gorithm can be shown to converge for arbitrary initial conditions with an
arbitrary number of team members, then insertion/deletion can be analyzed
by considering the modified system (after the insertion/deletion) with initial
conditions given from the state of the original system at the time of the in-
sertion/deletion. Each UAV implements the following algorithm, which is an
extension of discrete-time consensus algorithm (2.4):
Load Balancing Algorithm
1. Maintainan estimate of the distance traveledfromthe lastrendezvousin
each direction (each UAV shares a segment with its clockwise neighbor
and its counterclockwise neighbor).
2. Atarendezvous,theUAVthathastraveledthesmallestdistancesinceits
lastrendezvousagreesto loiteratthemidpointofthe sharedsegmentthe
nexttimeitistrackingtheperimeterinthatdirection(clockwise/counter-
clockwise).
3. If the endpoint of a segment has changed (due to perimeter growth or
neighbor actions), then the loiter distance is augmented by the change in
distance of the endpoint. This keeps the loiter point at the same position
relative to the segment length as communicated during the rendezvous.

|     |     |     | 13.3 Cooperative | Team Tracking | 255 |
| --- | --- | --- | ---------------- | ------------- | --- |
|     |     |     |                  | 1             | 2   |
|     |     | 1   | 2                | 3             | 4   |
| 1 2 |     |     | 3 4              |               |     |
(a)UAVs1and2are (b)UAVs3and4are (c) (cid:12) = (cid:12) = P, so
|          |     |          |     | 1 2          |        |
| -------- | --- | -------- | --- | ------------ | ------ |
| launched |     | launched |     | neither will | loiter |
|          |     | 1        | 2   |              |        |
| 1        | 2   |          |     |              |        |
| 3        | 4   |          |     |              |        |
|          |     | 3        | 4   | 1            | 2      |
|          |     |          |     | 3            | 4      |
(d) (cid:12) =0.25P, (cid:12) = (e)UAVs1and2re- (f) UAVs 3 and 4
| 1                | 3   |         |              |                 |      |
| ---------------- | --- | ------- | ------------ | --------------- | ---- |
| 0.75P,soUAV1will |     | turn to | their previ- | return to their | pre- |
P/2
| loiter at |     | ousrendezvouspoint |     | vious rendezvous |       |
| --------- | --- | ------------------ | --- | ---------------- | ----- |
|           |     |                    |     | point; UAVs1     | and 2 |
begin loitering
|                                |     | 1              | 2             |                    |     |
| ------------------------------ | --- | -------------- | ------------- | ------------------ | --- |
| 1                              | 2   |                |               | 1                  | 2   |
| 3                              | 4   |                |               | 3                  | 4   |
|                                |     | 3              | 4             |                    |     |
| (g)(cid:12) 1=(cid:12) =P/2,so |     | (cid:12)       | (cid:12) P/2, |                    |     |
| 3                              |     | (h) 1 =        | 2 =           | (i) Minimumlatency |     |
| neither will loiter            |     | so neitherwill | loiter        | configuration      | has |
been achieved
Fig. 13.6. Example of fixed perimeter length 2P when four UAVs implement the
| load balancing algorithm |     |     |     |     |     |
| ------------------------ | --- | --- | --- | --- | --- |

256 13 Cooperative Fire Monitoring with Multiple UAVs
4. AtleastoneUAVinarendezvouspair(e.g.,theonewiththelargertravel
distance) must not loiter en route to the next anticipated rendezvous
of this pair. This ensures that pairs of UAVs will always meet again,
independent of the change in the perimeter.
We will show through Monte Carlo simulation that the load balancing
algorithmconvergestotheminimumlatencyconfigurationforarbitraryinitial
conditions. A simulation instance consists of launching n pairs of UAVs from
the base station at random times around a fixed length circular perimeter.
Each member of the team continuously balances the load shared with each
of its two neighbors. The simulation continues until all agents are within ! of
the minimum latency configuration, or the maximum time is reached.
For eachn∈{2,...,7},100,000simulations were performed and the time
required to reach steady state recorded. Because time to convergence is a
function of the speed of the UAVs and the size of the perimeter, convergence
time is normalized by the time required for information to travel around the
perimeter. For example, if the convergence time is listed as T,then one UAV
could traverse the entire perimeter T times in the amount of time required
for the team to converge(to within !) to the minimum latency configuration.
Figure13.7showsthemeanandstandarddeviationinnormalizedconvergence
time over the 100,000 iterations for each n with normalized !=0.0003.
11
10
9
8
7
6
5
4
3
2
1
0
1 2 3 4 5 6 7 8
Number of UAV pairs
emit
ecnegrevnoc
dezilamroN
Mean
Std
Fig. 13.7. MonteCarloresultsfor100,000iterationsforn=2,...,7pairsofUAVs
Eachsimulationinstanceconvergedtotheminimumlatencyconfiguration
for every n ∈ {2,...,7}. An insertion or deletion of a pair of UAVs can be
represented by a set of initial conditions given by the state of the system
before the change with a new value of n. Monte Carlo simulations show that

13.4 Simulation Results 257
under any initial conditions for any n, the stability of the algorithm will not
be affected.
Theloadbalancingalgorithmtrackstheexpansion/contractionofaperime-
ter by construction: the actual perimeter length is effectively sampled by the
team continuously. In addition, Monte Carlo simulations have shown that in-
sertion/deletion of UAV pairs will not affect the stability of the algorithm.
We concludethatthe loadbalancingalgorithmwillconvergetothe minimum
latency configuration in the presence of team member insertion/deletion and
finite changes in perimeter length.
13.4 Simulation Results
In this section, we present simulation results that highlight the effectiveness
of the algorithms developed in this chapter. In Section 13.4.1, we describe
the fire model that is used in all of our simulations. In Section 13.4.2, we
present simulation results for the perimeter tracking algorithm described in
Section13.2.Section13.4.3containsthemaincooperativefiretrackingresults.
13.4.1 Fire Model
Totesttheperimetertrackingandcooperativecontrolalgorithmseffectively,a
realistic,time-varyingfiresimulatorwasdevelopedusingtheEcologicalModel
for Burning in the Yellowstone Region (EMBYR) (see [79,86]). EMBYR di-
vides the region of interest into a grid of cells, each with user specifiable
propertiesthataffectthe spreadofthe fire.Thesepropertiesinclude the type
of foliage,the moisture level, and the elevation. At a given time step, the fire
will spread from a burning cell to a nonburning cell, according to an inde-
pendent stochastic event that is a function of the properties of the respective
cells.ByrunningEMBYRmultipletimesandaveragingtheresult,weachieve
realistic fire simulations like the one shown in Figs. 13.8–13.10.
13.4.2 Perimeter Tracking
Step(i)inthefiretrackingalgorithm,describedinSection13.2,scansthrough
an image from an infrared camera and labels each pixel burned or unburned.
In our simulation, we use the EMBYR fire model to generate an a priori
model of the fire at each time step. During the execution of the simulation,
the current simulation time and the state of the UAV are used to generate
a binary image where 0 represents an unburned element and 1 represents a
burnedelement.Steps (ii)–(vi)areimplemented,asdescribedinSection13.2.
Simulation results of a single UAV tracking a fire perimeter are shown in
Fig. 13.11. The commanded offset distance from the boundary of the fire is
100 m.

258 13 Cooperative Fire Monitoring with Multiple UAVs
Fig. 13.8. Fire simulation of high wind conditions with an elevation gradient at
t=2800 s. Thefire is spreading in thedirection of thewind.
Inreality,thefire’sperimeterwillnotbecontiguousduetononcombustible
regions such as lakes or boulder fields. If the field of view of the camera is
larger than gaps in the perimeter, than the algorithm in Section 13.2 will
function properly because the linear classifier will find the best linear fit to
the available data which will fit a line through the noncontiguous regions.
13.4.3 Cooperative Tracking
Inthis section,we describe the results ofusing multiple UAVs to monitorthe
perimeter of a forest fire simulated using the EMBYR model. The maximum
communicationrangefortheUAVswassetat100m(approximately9pixels).
ThevelocityoftheUAVsis18m/s.Thefireperimeterisgrowingatanaverage
of2.8m/s.Figure13.12ashowsfourUAVs monitoringthefire withtwomore
UAVs (bottom left) approaching the fire from the base station. A short time
later, as shown in Fig. 13.12b, the two new UAVs (also at the bottom left)
are loitering while waiting for their next rendezvous. After approximately
600 s have passed, the UAVs are in the steady-state configuration shown in
Figs. 13.12c and 13.12d.
Inthefiremonitoringsimulation,theUAVconfigurationdoesnotprecisely
converge to the equilibrium predicted by the algorithm due to the dynamics
of the UAVs and the fire. Specifically, the steady-state configuration error

13.4 Simulation Results 259
Fig. 13.9. Fire simulation of high wind conditions with an elevation gradient at
t=6800 s. Thefire is spreading in thedirection of thewind.
depends on the turning radius of the UAVs and the growth rate of the fire
perimeter.
Despite these factors, the lengths (cid:2) (k) converge as time progresses. In
i
Fig. 13.13,it can be seen that these lengths are increasing as time progresses
due to the growth of the fire. Figures 13.14 and 13.15 also show the conver-
genceof(cid:2) (k)forastaticfirewithperimeteroflength7.2km,whichisshown
i
in Fig. 13.1. In Fig. 13.14, there are four UAVs initially monitoring the fire,
andatt=1000s,twomore UAVs areintroduced.InFig. 13.15,there aresix
UAVs monitoring the fire.
The checkpointsinFig.13.1wereused to showthe latency ofinformation
at the base station. A UAV gathers information about a checkpoint when it
is within 50 m from that point. This information is passed to its neighbor
when the UAVs communicate. When a UAV passes the base station (half-
waybetweentheleftandbottomcheckpoints),theinformationconcerningall
the checkpoints known by that UAV is passed to the base station. The static
perimeter is 7.2 km long, which would take a little less than 7 minutes to
traverse, given that the UAVs were traveling at 18 m/s (a typical speed for
small UAVs). The maximum latency for one UAV monitoring the fire would
be 6.6 minutes. However, when more UAVs are used, this latency can be cut
inhalfaswellasreducingthelatencyforinformationnearthebasestation.In

260 13 Cooperative Fire Monitoring with Multiple UAVs
Fig. 13.10. Fire simulation of high wind conditions with an elevation gradient at
t=10800 s. The fireis spreading in the direction of the wind.
theeventthatfirefighterscancommunicatewiththeUAVs,thiswouldenable
timely updates about the perimeter of the fire.
The minimum latency for each checkpoint is equivalent to a UAV flying
directly from the checkpoint to the base station. The minimum latency of
informationfor checkpoints1 and 2 is about 45s andfor checkpoints 3 and4
is about125 s.The latencies for checkpoints 1 and 4 are plotted in Fig.13.16
which demonstrates that the minimum latencies are achieved.
13.5 Notes
The results in this chapter are based mainly on [38].
Acknowledgment is given to
(cid:10)c2006Taylor&Francis.Reprinted,withpermission,fromDavidW.Cas-
beer, Derek B. Kingston, Randal W. Beard, Timothy W. McLain, Sai-Ming
Li, and Raman Mehra, “Cooperative forest fire surveillance using a team of
smallunmannedairvehicles,”International Journal of Systems Sciences,vol.
37, no. 6, pp. 351–360,May 2006 (http://www.informaworld.com).

13.5 Notes 261
Fig. 13.11. Fire perimeter tracking error for a single UAV. The UAV was com-
| manded to track | the firewith | an offset of | 100 meters. |
| --------------- | ------------ | ------------ | ----------- |

| 262 13 Cooperative | Fire Monitoring | with Multiple | UAVs |
| ------------------ | --------------- | ------------- | ---- |
FireSim: Elevation with wind direction change FireSim: Elevation with wind direction change
| 3500                     |     | 3500                     |     |
| ------------------------ | --- | ------------------------ | --- |
| 3000                     |     | 3000                     |     |
| → htroN − htuoS ← :)m( X |     | → htroN − htuoS ← :)m( X |     |
| 2500                     |     | 2500                     |     |
| 2000                     |     | 2000                     |     |
| 1500                     |     | 1500                     |     |
| 1000                     |     | 1000                     |     |
500 500 1000 1500 2000 2500 3000 3500 500 500 1000 1500 2000 2500 3000 3500
| Y (m):←  West−East → |     |     | Y (m):←  West−East → |
| -------------------- | --- | --- | -------------------- |
| (a)                  |     |     | (b)                  |
FireSim: Elevation with wind direction change FireSim: Elevation with wind direction change
| 3500                     |     | 3500                     |     |
| ------------------------ | --- | ------------------------ | --- |
| 3000                     |     | 3000                     |     |
| → htroN − htuoS ← :)m( X |     | → htroN − htuoS ← :)m( X |     |
| 2500                     |     | 2500                     |     |
| 2000                     |     | 2000                     |     |
| 1500                     |     | 1500                     |     |
| 1000                     |     | 1000                     |     |
| 500                      |     | 500                      |     |
500 1000 1500 2000 2500 3000 3500 500 1000 1500 2000 2500 3000 3500
| Y (m):←  West−East → |             |                  | Y (m):←  West−East → |
| -------------------- | ----------- | ---------------- | -------------------- |
|                      | (c)         |                  | (d)                  |
| Fig. 13.12.          | Six UAVsare | shown monitoring | a growing fire       |

13.5 Notes 263
2500
2000
1500
1000
500
0
0 200 400 600 800 1000 1200
sreteM
Time (s)
Fig. 13.13. The time histories of (cid:12) (k) are for each UAV
i
4000
3500
3000
2500
2000
1500
1000
500
0
0 500 1000 1500 2000
sreteM
Time (s)
Fig. 13.14. Convergence of(cid:12) (k) for four UAVsmonitoring thefirewith twoaddi-
i
tional UAVsintroduced at t=1000 s

| 264 | 13 Cooperative | Fire | Monitoring | with | Multiple | UAVs |     |
| --- | -------------- | ---- | ---------- | ---- | -------- | ---- | --- |
4000
3500
3000
2500
sreteM
2000
1500
1000
500
0
|     | 0   | 200 | 400 | 600 | 800 | 1000 | 1200 |
| --- | --- | --- | --- | --- | --- | ---- | ---- |
Time (s)
|     | Fig. | 13.15. | Convergence | of  | (cid:12) (k) for | six UAVs |     |
| --- | ---- | ------ | ----------- | --- | ---------------- | -------- | --- |
i
400
300
)s( yaleD
200
100
0
|     | 0   | 200 | 400 | 600 | 800 | 1000 | 1200 |
| --- | --- | --- | --- | --- | --- | ---- | ---- |
      Time (s)
400
|     | )s( yaleD 300 |     |     |     |     |     |     |
| --- | ------------- | --- | --- | --- | --- | --- | --- |
200
100
0
|     | 0   | 200 | 400 | 600 | 800 | 1000 | 1200 |
| --- | --- | --- | --- | --- | --- | ---- | ---- |
      Time (s)
|     | Fig. 13.16. | Latencies |     | for checkpoints1 | and | 4 in | Fig. 13.1 |
| --- | ----------- | --------- | --- | ---------------- | --- | ---- | --------- |

14
Cooperative Surveillance with Multiple UAVs
Contributed partly by Tim McLain
Numerous applications require aerial surveillance. Civilian applications in-
clude monitoring forest fires, oil fields and pipelines, and tracking wildlife.
Applications to homeland security include border patrol and monitoring the
perimeter of nuclear power plants. Military applications are numerous. The
currentapproachtotheseapplicationsistouseasinglemannedvehicleforsur-
veillance. However, manned vehicles are typically large and expensive. In ad-
dition,hazardousenvironmentsandoperatorfatigue canpotentially threaten
the life of the pilot. Therefore, there is a critical need for automating aerial
surveillance using UAVs. This chapter describes a cooperative control strat-
egy for aerial surveillance that has been successfully flight tested on small
(48inchwingspan)UAVs.Thecooperativecontrolstrategyfollowsthedesign
methodology described in Section 8.3.
14.1 Experimental Test Bed
Over the past several years, BYU has developed a reliable and robust test
bed for autonomous miniature air vehicles [21,23]. Figure 14.1 shows the key
elementsofourtestbed.ThefirstframeshowsBYU’sKestrelautopilotwhich
isequippedwithaRabbit300029MHzprocessor,rategyros,accelerometers,
absolute and differential pressure sensors, and GPS. The autopilot measures
only1.5×2.0×0.75inchesandweighs18grams.ThesecondframeinFig.14.1
show the airframes used for the flight tests reported in this chapter. The
airframes are 48 inch wingspan Zagi XS EPP foam flying wings that were
selected for their durability and adaptability to different mission scenarios.
Embedded in the airframe are the autopilot, batteries, a 1000 mW, 900 MHz
radio modem, a GPS receiver, video transmitter, and a small analog camera.
The third frame in Fig. 14.1 shows the ground station components. A laptop
runsthevirtualcockpitsoftwarethatinterfacesthroughacommunicationbox
to the UAVs. An RCtransmitter is usedas a stand-byfail-safe mechanismto
facilitate safe operations.

266 14 Cooperative Surveillance with Multiple UAVs
Fig. 14.1. Hardware platform used toobtain experimentalresults. Thefirst frame
showstheKestrelautopilotdesignedatBYU.Thesecondframeshowstheairframes
usedforthischapter.Thethirdframeshowsthegroundstationcomponentsforour
test bed.
Cooperative flight tests with multiple UAVs are challenging to perform,
anddevelopmentof this capability has requiredseveralyearsof experimenta-
tion and refinement. One significant challenge in working with air vehicles is
that the design/test cycle is considerably longer than that for ground robots.
Flight experiments also entail a greater levelof risk because minor errorscan
lead to catastrophic crashes. In doing experiments with UAVs, crashes are
inevitable. Choosing an airframe that survives crashes greatly shortens the
design and testing cycle. Experiments must be conducted in locations and at
speeds where possible crashes do not pose a threat to life or property.
We have taken several steps to mitigate the logistical challenges of UAV
flight experiments. These steps include the following:
Airframe Selection
The airframes that we use are designed to withstand crashes. Our airframes
are constructed of EPP foam, Kevlar, and carbon fiber. Our workhorse air-
frame is the commercialoff-the-shelfZagiXS flying wing constructedof EPP
foam [2]. The Zagi airframe was designed for midair RC dog fights and is ex-
tremely durable. It is inexpensive, hand-launchable, belly-landable, and easy
to construct, modify, and repair. The EPP foam exterior protects the elec-
tronic components during crashes.
Preflight Protocols
Our standard preflight protocol includes a standard checklist to test for the
mostcommoncausesofcrashes.Itemsonthelistincludetestingthetelemetry
link,calibratingthesensors,andverifyingproperdeflectionofcontrolsurfaces.
In-flight Parameter Changes
We have developed a software architecture that allows any autopilot para-
meter to be modified in-flight. Parameters that can be modified in-flight in-

|     |     |     | 14.1 Experimental | Test Bed | 267 |
| --- | --- | --- | ----------------- | -------- | --- |
clude control loop gains and state estimation gains. Allowing parameters to
be changed in-flight facilitates a rapid tune and debug cycle.
| Switchable | Software Modules |     |     |     |     |
| ---------- | ---------------- | --- | --- | --- | --- |
We havethe capabilitytoswitchbetweendifferentsoftwaremodulesin-flight.
This hasrecentlybeenusedtotestadaptivecontrolalgorithmsonourUAVs.
PID control was used during auto take-offand landing, but switched with an
adaptivecontrolmoduleduringflight.Thiscapabilityallowsrapidprototyping
of algorithms without extensive validation and verification efforts.
| Data Logging | and Display |     |     |     |     |
| ------------ | ----------- | --- | --- | --- | --- |
We can monitor and log any variable on the autopilot and display that data
duringtheflight.Again,this capabilityallowsalgorithmstobedebuggedand
| tuned without        | requiring | the UAV to | be landed. |     |     |
| -------------------- | --------- | ---------- | ---------- | --- | --- |
| Hardware-in-the-Loop |           | Simulator  |            |     |     |
We use a medium fidelity hardware-in-the-loop simulator that interfaces di-
rectly to the autopilot and runs in real time, allowing the autopilot code to
| be tested | and debugged | prior to flight | experimentation. |     |     |
| --------- | ------------ | --------------- | ---------------- | --- | --- |
Inadditiontotheexperimentalcapabilitiesdescribedabove,wedeveloped
twocriticaltechnologiesbeforesuccessfullydemonstratingcooperativetiming
missions on UAVs: reliable intervehicle communication and robust trajectory
| tracking in | wind. |     |     |     |     |
| ----------- | ----- | --- | --- | --- | --- |
Multiple Vehicle Communication. One of the challenges with miniature
UAVs is that size, weight, and power constraints make high-speed, wide-
bandwidth, digital communication links impractical. As an alternative, we
use inexpensive low-power, half-duplex 9600-baud radio-frequency modems,
which require all vehicles to share the same communication channel and the
| use of a turn-taking | scheme | to avoid | packet collisions. |     |     |
| -------------------- | ------ | -------- | ------------------ | --- | --- |
Cooperative control experiments have two competing communication de-
mands:First,telemetrydatafromeachofthevehiclesmustbecommunicated
to the ground station on a regular basis for data logging and system mon-
itoring. Second, coordination information must be sent among vehicles and
between the ground station and vehicles. From an individual vehicle com-
munication perspective, there are two important requirements: low latency
of high priority data transmission and confirmation of properly receiving the
transmission. To meet these communication challenges, the ground station
acts as a server and controls which vehicles can communicate what informa-
tion at what time. The transmissions can be divided into three categories:
vehicle telemetry data, commands for the vehicle, and coordination informa-
tion among vehicles. The ground station attempts to request telemetry data

268 14 Cooperative Surveillance with Multiple UAVs
from each of the vehicles at a rate based on the number of vehicles (typically
3 to 4 Hz), and all other data are transmitted on a needs basis. The ground
station dynamically assigns a priority to each type of transmission based on
urgency, time in queue, and previous frequency of transmission. This allows
highprioritymessagesto be deliveredwith low latency andalsopreventsany
type of transmission from flooding the communication channel. Although its
bandwidth is suboptimal, this communication system meets the demanding
requirements posed by cooperative UAVs and is very robust to packet loss.
Robust Trajectory Tracking in Wind. Airspeeds for the small UAVs that
weflyaretypicallybetween10and18meterspersecond,orequivalently20to
40milesperhour.A10mphwind,whichistypicalat300feetaltitudeoncalm
days,isasubstantialdisturbanceforasmallUAV.Forthecooperativetiming
experiments presented in this chapter, the UAV is directed to be at a certain
locationat a specific time. Critical to completing the missionsuccessfully are
location and timing, which are significantly affected by wind. Experimental
demonstrationofcooperativetiming requireshigh-fidelity trajectorytracking
algorithms that mitigate the effects of wind.
For timing missions, preserving path length is critical to be able to sat-
isfy the timing constraints. Flying extra distance due to poor path following
adds unwanted time to the mission. To address these issues, a vector field
path-following method has been implemented to enable the UAVs to accu-
rately follow waypoint paths. It has been shown in [148,149] that creating
vector fields of desired heading to direct the UAV onto its desired path will
result in asymptotically decaying tracking error in the presence of wind, pro-
videdgroundtrackheadingandgroundspeedareusedinthecontrollaw.Use
of this method has significantly decreased path-following errors, and conse-
quentlyoverallpathlengtherrors,thusenablingsuccessfulcooperativetiming
experiments.
14.2 Decentralized Cooperative Surveillance
Theobjectiveofthissectionistoapplythedesignmethodologyintroducedin
Section 8.3 to a cooperative aerial surveillance example and to demonstrate
theeffectivenessoftheapproachusinghigh-fidelitysimulationandflighttests
of fixed-wing miniature air vehicles. We will consider two related variants of
this problem. The first variant is persistent imaging, depicted in Fig. 14.2,
where a team of n UAVs equipped with imaging sensors is tasked to persis-
tently image a known target. If the field of view of the sensor is small with
respecttotheturningradiusoftheUAVs,thesolutionofthisproblemwillre-
quirethe teamofUAVs tofly overthe targetatregularintervals.The second
variantofthecooperativeaerialsurveillanceproblemiscooperativeidentifica-
tionwhereateamofUAVsisrequiredtoflyoveratargetsimultaneously,but
along different approach angles. In the taxonomy introduced in Section 8.2,
decentralized aerial surveillance problems are objectively coupled.

|     |     | 14.2 Decentralized | Cooperative | Surveillance | 269 |
| --- | --- | ------------------ | ----------- | ------------ | --- |
Fig. 14.2. Persistentaerialsurveillance.TheUAVsareinitiallyperforminganaux-
iliary task. Upon command, they coordinate their action to fly over the target at
| fixed time intervals. |             |     |     |     |     |
| --------------------- | ----------- | --- | --- | --- | --- |
| 14.2.1 Solution       | Methodology |     |     |     |     |
The first step in addressing the aerial surveillance problem is to identify the
cooperation constraint. Let zˆ represent the location of the target which we
assume is known to every vehicle, and let z i (t) denote the location of the ith
| vehicle at time | t. The cooperation | constraint | is given | by  |     |
| --------------- | ------------------ | ---------- | -------- | --- | --- |
(cid:2)n
|     |              | ∗ (cid:9)z | ∗ Δ)−zˆ(cid:9)2, |     |        |
| --- | ------------ | ---------- | ---------------- | --- | ------ |
|     | J constraint | (θ )=      | i (θ +γ i        |     | (14.1) |
i=1
=(k−1)whentheithvehicleisassigned
| whereΔisthedesiredspacingandγ |     | i   |     |     |     |
| ----------------------------- | --- | --- | --- | --- | --- |
the kthpositioninthe surveillancesequence.NotethatifJ =0,then
constraint
the vehicles fly by the target location at equally spaced intervals Δ seconds
apart.
In (14.1), θ∗ is the time at which the first vehicle passes over the target.
It is clear thatby increasingthe loiter time, θ∗ canbe made arbitrarilylarge.

| 270 | 14  | Cooperative | Surveillance |     | with Multiple |     | UAVs |     |     |
| --- | --- | ----------- | ------------ | --- | ------------- | --- | ---- | --- | --- |
Therefore,weneedtointroduceanauxiliaryoptimizationcriterionthatselects
among the many possibilities for θ∗. Toward that end, we assume that a
suitable path planning algorithm is available for planning waypoint paths
from the current location of the UAV z to the target zˆ in a certain time T.
i
| The algorithm |     | will | be denoted | by  | the notation |     |     |     |     |
| ------------- | --- | ---- | ---------- | --- | ------------ | --- | --- | --- | --- |
W
|     |     |     |     | =planPath(z |     | i ,zˆ,T). |     |     |     |
| --- | --- | --- | --- | ----------- | --- | --------- | --- | --- | --- |
Inaddition,weassumeafunctionLength(W)thatreturnsthe
pathlengthof
| W. The | fuel | expended | in traversing |                     | a path | is  | approximated | by  |     |
| ------ | ---- | -------- | ------------- | ------------------- | ------ | --- | ------------ | --- | --- |
|        |      |          | fuel=c        | v Length[planPath(z |        |     | ,zˆ,T)],     |     |     |
|        |      |          |               | f i                 |        |     | i            |     |     |
where v is the airspeed along the path and c is a constant. Therefore, fuel
|         | i         |     |              |     |             |     | f         |     |     |
| ------- | --------- | --- | ------------ | --- | ----------- | --- | --------- | --- | --- |
| will be | minimized |     | by selecting | the | cooperation |     | objective | as  |     |
(cid:2)n
J (θ ∗ )= c v Length{planPath[z (t ),zˆ,t +θ ∗ +γ Δ]}, (14.2)
| objective |     |     | f i |     |     | i   | 0 0 | i   |     |
| --------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
i=1
| where | t is | the time | at which | the | path planner |     | is executed. |     |     |
| ----- | ---- | -------- | -------- | --- | ------------ | --- | ------------ | --- | --- |
0
The second step is to make a suitable choice of the coordination variable.
It is clear from the discussion above that the instant when the first vehicle
passes over the target is a suitable coordination variable. As seen in (14.1)
and (14.2), the cooperation constraint and the cooperation objective can be
written in terms of the coordination variable. The coordination function is
given by
|     |     | ∗      | Length{planPath[z |     |     |     |           | ∗ Δ]}. |     |
| --- | --- | ------ | ----------------- | --- | --- | --- | --------- | ------ | --- |
|     | J   | (θ )=c | v                 |     |     | (t  | ),zˆ,t +θ | +γ     |     |
|     |     | cf,i   | f i               |     |     | i   | 0 0       | i      |     |
The third step is to devise a centralized cooperation algorithm that
solves (8.3). The formulation of the path planning problem ensures that the
cooperationconstraintis triviallysatisfied.The objectivefunction canbe op-
timized with a Mixed Integer Linear Program (MILP) solver where γ are
i
θ∗
integers and is real. As it turns out, this particular problem has suffi-
θ∗
cient structure that it admits an analytic solution [139]. Once has been
determined (by a centralized unit) then, according to (8.4), the ith vehicle
| implements |     | the path | given | by  |     |     |     |     |     |
| ---------- | --- | -------- | ----- | --- | --- | --- | --- | --- | --- |
∗
|     |     |     | u =planPath[z |     | (t ),zˆ,t | +θ  | +γ  | Δ]. | (14.3) |
| --- | --- | --- | ------------- | --- | --------- | --- | --- | --- | ------ |
|     |     |     | i             |     | i 0       | 0   | i   |     |        |
Thefinalstepistodecentralizethealgorithmusingaconsensusalgorithm.
To do so, let θ denote the ith vehicles instantiation of the coordination vari-
i
θ∗.
| able | Instead | of  | (14.3),       | the ith | vehicle   | implements |     |     |     |
| ---- | ------- | --- | ------------- | ------- | --------- | ---------- | --- | --- | --- |
|      |         |     | u =planPath[z |         | (t ),zˆ,t | +θ         | +γ  | Δ]. |     |
|      |         |     | i             |         | i 0       | 0          | i i |     |     |
Given communication with the other vehicles, the coordination variable θ is
i
then adjusted according to the consensus dynamics given in (2.2).

14.2 Decentralized Cooperative Surveillance 271
Inthe cooperativeidentification variantofthis problem,we wantallvehi-
cles to arrive at the target location simultaneously and at different approach
angles. For this problem, we set Δ = 0 and pass the approach angle as an
additional input to the path planning algorithm. In the next two sections,
we will presentsimulationresults for the decentralizedcooperativeidentifica-
tion problemand flighttest results for the centralizedpersistentimaging and
cooperative identification problem.
14.2.2 Simulation Results
To enable rapid prototyping of cooperative control algorithms, we have de-
veloped a medium-fidelity simulation environment for autonomous miniature
air vehicles. The simulation environment consists of two components. The
first is a six degree-of-freedom flight simulator with Digital Elevation Model
(DEM) terrain data [3] and realistic wind models. The second component is
an autopilot module that executes the same code that is implemented on the
physicalautopilot.Theautopilotmoduleconnectstothesamegroundstation
software that is used to fly the miniature air vehicles. A screen shot of the
flight simulator and the virtual cockpit are shown in Fig. 14.3.
Fig. 14.3. Screenshotoftheflightsimulator(bottomleftwindowinblue),andthe
virtualcockpit(background).Thesimulationenvironmentenablesrapidprototyping
of cooperative control problems for autonomous miniature air vehicles.

272 14 Cooperative Surveillance with Multiple UAVs
The cooperative identification problem was simulated using four UAVs
that were tasked to arrive at the target simultaneously with arrival angles
differing by 90◦. The average time to reach consensus to within 0.02 units
was 6.2 seconds where one communication packet per second was allowed
to be sent by each UAV to another UAV selected randomly from the team.
Simulation results are shown in Fig. 14.4.Subplots (a) and (b) showthe four
UAVs loitering until the mission execution command is issued at the end of
Subplot(b).TheUAVsareallflyingatdistinct,preassignedaltitudestoavoid
collision as they pass over the target. Subplots (c) and (d) show the UAVs
executing the cooperative identification mission.
Fig. 14.4. Simulationresultsofacooperativeidentificationmission.InSubplot(a)
theUAVareloiteringaroundaspecifiedwaypoint.InSubplot(b)themissionexecu-
tioncommandisissuedandtheUAVsplantheirapproachtrajectories.Subplots(c)
and (d) demonstrate the execution of the mission. The UAV are flying at distinct
altitudes.
Figure14.5plotstheaveragedistancefromthetargetversustimeforeach
UAV and demonstrates the effectiveness of the decentralized coordination
algorithm.

14.2 Decentralized Cooperative Surveillance 273
900
800
700
600
500
400
300
200
100
0
−50 −40 −30 −20 −10 0 10
Time (s)
)m(
tegrat
morf
ecnatsiD
Fig. 14.5. Aplot oftheaveragedistance fromthetarget versustimeforthesimu-
lated cooperative identification problem
14.2.3 Flight Tests
Flight tests were performed using three UAVs that were commanded to per-
sistently image a target at fixed intervals of Δ=3 seconds. The three UAVs
were initially commanded to loiter at specified GPS coordinates. The UAVs
were then commanded to perform a persistent imaging mission and then re-
turntotheir loiteringcoordinates.Themissionwasrepeatedsixtimesduring
a 30-minute flight. The wind speeds during the flight were between 30 and
60% percent of the UAV airspeed and were from the southwest. The average
errorinarrivaltime for the six runs,inspite ofthe highwindconditions,was
approximately 0.6 seconds.
Plots of the telemetry data are shown in Fig. 14.6. The imaging target is
depicted by a circle, whereas the transition waypoints produced by the path
planner are depicted by diamonds.
Figure14.7showsthe casewhereone ofthe UAVs startsthe missionfrom
aninitialtargetdistancesignificantlydifferentfromthatoftheothervehicles.
Note that the vehicle that is closest to the imaging point must plan a path
thatincreasesitsdistance,thusallowingtherestoftheteamtocatchupwith
it.

| 274 14 | Cooperative | Surveillance | with Multiple | UAVs |
| ------ | ----------- | ------------ | ------------- | ---- |
Fig. 14.6. Telemetry data for the flight tests of the persistent imaging mission.
Subplot (a) shows the UAVs approaching a loiter waypoint. Subplot (b) shows the
UAVs en route to the entry waypoint after the fly-by command has been issued.
Subplots (c), (d), and (e) show the UAVs transition through the imaging target.
| Subplot | (f) shows theUAVsreturning |     | to theirloiter | points. |
| ------- | -------------------------- | --- | -------------- | ------- |
Inadditiontothepersistentimagingscenario,wehavealsoflighttestedthe
simultaneousarrivalmissionusingthreeUAVs.Stillshotsofanarrivalmission
areshowninFig.14.8.Subplots(a)and(b)showthe UAVsasthey approach
the cooperative rendezvouspoint. Subplot (c) shows the simultaneous arrival
to within 0.3 seconds, and Subplot (d) shows the UAV departing from the
rendezvous point. Telemetry plots for this mission are shown in Fig. 14.9.
14.3 Notes
| The results    | in this | chapter are | based mainly | on [26]. |
| -------------- | ------- | ----------- | ------------ | -------- |
| Acknowledgment |         | is given to |              |          |
(cid:10)c2006 IEEE. Reprinted, with permission, from Randal W. Beard, Tim-
othy W. McLain, Derek Nelson, Derek Kingston, and David Johanson, “De-
centralizedcooperativeaerialsurveillanceusing fixed-wingminiature UAVs,”
Proceedings of the IEEE, vol. 94, no. 7, pp. 1306–1324,July 2006.

14.3 Notes 275
Fig. 14.7. Telemetry data for persistent imaging when one of the UAVs is signifi-
| cantly closer | to the image | point than therest | of theteam. |
| ------------- | ------------ | ------------------ | ----------- |

276 14 Cooperative Surveillance with Multiple UAVs
(a) (b)
(c) (d)
Fig. 14.8. Still shots of a cooperative timing scenario. Subplots (a) and (b) show
threeUAVsapproachingtherendezvouspoint.Subplot(c)showstherendezvousto
within 0.3 seconds. Subplot (d) shows theUAVsimmediately after therendezvous.

14.3 Notes 277
Fig. 14.9. Telemetry data for the simultaneous arrival mission. In the top right
subplot, the UAVs are orbiting prescribed loitering points. In the top left subplot,
the UAVs have just received the cooperative rendezvous signal. The bottom left
subplot shows the UAVs en route to the rendezvous point, and the bottom right
subplot shows theUAVsat the rendezvouspoint.

A
| Selected | Notations   |       | and Abbreviations |
| -------- | ----------- | ----- | ----------------- |
| ≡        | identically | equal |                   |
(cid:2)
| =   | definedas |           |     |
| --- | --------- | --------- | --- |
| ∀   | for all   |           |     |
| ∈   | belongs   | to        |     |
| ⊂   | a strict  | subset of |     |
⊆
|     | a subset | of  |     |
| --- | -------- | --- | --- |
→
tendsto
| =⇒  | implies      |     |     |
| --- | ------------ | --- | --- |
| ⇐⇒  | equivalentto |     |     |
summation
(cid:0)
product
⊗ (cid:2)
Kroneckerproduct
| max | maximum             |      |             |
| --- | ------------------- | ---- | ----------- |
| min | minimum             |      |             |
| sup | supremum,theleast   |      | upperbound  |
| inf | infimum,thegreatest |      | lower bound |
| Rp  | p×1                 |      |             |
|     | set of              | real | vectors     |
Rm×n
|       | set of m×n          | real       | matrices    |
| ----- | ------------------- | ---------- | ----------- |
| C     | set of complex      | numbers    |             |
| A>0   | a positive          | matrix     | A           |
| A≥0   | a nonnegativematrix |            | A           |
| ρ(A)  |                     |            | A           |
|       | spectral            | radius of  | matrix      |
| σ(A)  | spectrumof          | matrix     | A           |
| λ (A) | theith              | eigenvalue | of matrix A |
i
| λ (A) | themaximumeigenvalue |     | of matrix A |
| ----- | -------------------- | --- | ----------- |
max
| λ (A) | theminimumeigenvalue |     | of matrix A |
| ----- | -------------------- | --- | ----------- |
min
| det(A) |             |           | A      |
| ------ | ----------- | --------- | ------ |
|        | determinant | of matrix |        |
| Γ(A)   |             |           | A      |
|        | directed    | graph of  | matrix |
diag(a 1 ,...,a ) a diagonal matrix with diagonal entries a 1 to a
p p
diag(A ,...,A ) a block diagonal matrix with diagonal blocks A to A
| 1   | p         |          | 1 p |
| --- | --------- | -------- | --- |
| log | logarithm | function |     |

| 280 A Selected    | Notations                 | and                | Abbreviations |     |
| ----------------- | ------------------------- | ------------------ | ------------- | --- |
| tanh              | tangent                   | hyperbolicfunction |               |     |
| cosh              | cosine hyperbolicfunction |                    |               |     |
| (cid:12)x(cid:12) | norm of                   | vector             | x             |     |
| (cid:12)x(cid:12) | p-normof                  | vector             | x             |     |
p
| (cid:12)A(cid:12) | induced | p-normof | matrix | A   |
| ----------------- | ------- | -------- | ------ | --- |
p
| Re(z) |     | numberz |     |     |
| ----- | --- | ------- | --- | --- |
real part of
| Im(z) | imaginary  | part   | of numberz |          |
| ----- | ---------- | ------ | ---------- | -------- |
| 1     | p×1 column | vector | of         | all ones |
p
p×1
| 0 p | column | vector | of  | all zeros |
| --- | ------ | ------ | --- | --------- |
[0,0,0,1]T
| q I | multiplicative |     | identity | quaternion |
| --- | -------------- | --- | -------- | ---------- |
| I   | m×m identity   |     | matrix   |            |
m
| 0   | m×n zero | matrix |     |     |
| --- | -------- | ------ | --- | --- |
m×n
G
| p   | graph |     |     |     |
| --- | ----- | --- | --- | --- |
V
| p   | node set | of a graph |     |     |
| --- | -------- | ---------- | --- | --- |
| E   | edge set | of a graph |     |     |
p
| A   | p×p adjacency |     | matrix |     |
| --- | ------------- | --- | ------ | --- |
p
| L   | p×p (nonsymmetrical) |     |     | Laplacian matrix |
| --- | -------------------- | --- | --- | ---------------- |
p
| AUV  | autonomous           | underwatervehicle |            |           |
| ---- | -------------------- | ----------------- | ---------- | --------- |
| CCD  | charge-coupled       |                   | device     |           |
| GPS  | global positioning   |                   | system     |           |
| HALE | high altitude        | long              | endurance  |           |
| ISS  | input-to-statestable |                   |            |           |
| LASE | low altitude         | short             | endurance  |           |
| LTI  | linear time          | invariant         |            |           |
| LTV  | linear time          | varying           |            |           |
| MAV  | micro air            | vehicle           |            |           |
| MRP  | modified             | Rodriguez         | parameters |           |
| PID  | proportional         | integral          | derivative |           |
| PWM  | pulse-width          | modulation        |            |           |
| RC   | radio control        |                   |            |           |
| SIA  | stochastic           | indecomposable    |            | aperiodic |
| UAV  | unmanned             | air               | vehicle    |           |

B
Graph Theory Notations
It is natural to model information exchange among vehicles by directed or
undirected graphs.1 Suppose that a team consists of p vehicles. A directed
graph is a pair (V ,E ), where V = {1,...,p} is a finite nonempty node set
p p p
and E ⊆ V ×V is an edge set of ordered pairs of nodes, called edges. The
p p p
edge(i,j)intheedgesetofadirectedgraphdenotesthatvehiclej canobtain
information from vehicle i, but not necessarily vice versa. Self-edges (i,i) are
notallowedunlessotherwiseindicated.Fortheedge(i,j),iistheparent node
andj isthechildnode.Incontrasttoadirectedgraph,thepairsofnodesinan
undirected graph are unordered, where the edge (i,j) denotes that vehicles i
andj canobtaininformationfromeachother.Note thatanundirectedgraph
canbeviewedasaspecialcaseofadirectedgraph,whereanedge(i,j)inthe
undirectedgraphcorrespondstoedges(i,j)and(j,i)inthedirectedgraph.If
anedge(i,j)∈E ,thennodeiisaneighborofnodej.Thesetofneighborsof
p
node iisdenotedasN .Aweighted graphassociatesaweightwitheveryedge
i
in the graph. In this book, all graphs are weighted. The union of a collection
ofgraphsis a graphwhose node and edgesets are the unions ofthe node and
edge sets of the graphs in the collection.
A directed path is a sequence of edges in a directed graph of the form
(i ,i ),(i ,i ),.... An undirected path in anundirected graphis defined anal-
1 2 2 3
ogously. In a directed graph, a cycle is a directed path that starts and ends
atthe samenode.Adirectedgraphisstrongly connected ifthere isa directed
path from every node to every other node. An undirected graph is connected
if there is anundirected pathbetween everypair ofdistinct nodes.A directed
tree is a directed graph in which every node has exactly one parent except
for one node, called the root, which has no parent and which has a directed
pathtoeveryothernode.Notethatadirectedtreehasnocyclebecauseevery
edge is oriented away from the root. In undirected graphs, a tree is a graph
in which every pair of nodes is connected by exactly one undirected path.
1 This appendix is based mainly on [191].

282 B Graph Theory Notations
A sub6graph (V
p
s,E
p
s) of (V
p
,E
p
) is a graph such that V
p
s ⊆ V
p
and
Es ⊆ E (Vs × Vs). A (rooted) directed spanning tree (Vs,Es) of the di-
p p p p p p
rected graph(V ,E ) is a subgraphof(V ,E ) suchthat (Vs,Es) is a directed
p p p p p p
tree and Vs = V . An undirected spanning tree of an undirected graph is de-
p p
finedanalogously.Thegraph(V ,E )has orcontainsadirectedspanningtree
p p
if a directed spanning tree is a subgraph of (V ,E ). Note that the directed
p p
graph (V ,E ) has a directed spanning tree if and only if (V ,E ) has at least
p p p p
one node with a directed path to all other nodes. In undirected graphs, the
existence of an undirected spanning tree is equivalent to being connected.
However, in directed graphs, the existence of a directed spanning tree is a
weaker condition than being strongly connected. Figure B.1 shows a directed
graphthat contains more than one directed spanning tree but is not strongly
connected. Nodes 1 and 2 are both roots of directed spanning trees because
bothhavedirectedpathstoallothernodes.However,thegraphisnotstrongly
connectedbecausenodes3,4,5,and6donothavedirectedpathstoallother
nodes.
(cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) (cid:17)(cid:17)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) (cid:15)(cid:15)(cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9)
1(cid:19)(cid:19) 2 3
(cid:14)(cid:14) (cid:14)(cid:14)
(cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9) (cid:15)(cid:15)(cid:6)(cid:2)(cid:7)(cid:3)(cid:8)(cid:4)(cid:9)(cid:5) (cid:15)(cid:15)(cid:2)(cid:6)(cid:3)(cid:7)(cid:4)(cid:8)(cid:5)(cid:9)
4 5 6
Fig. B.1. Directed graph among six vehicles. An arrow from node i to node j
indicates that vehicle j receives information from vehicle i. This directed graph
contains two directed spanning trees with root nodes 1 and 2 but is not strongly
connectedbecausenodes3,4,5,and6donothavedirectedpathstoallothernodes.
The adjacency matrix A = [a ] ∈ Rp×p of a directed graph (V ,E )
p ij p p
is defined such that a is a positive weight if (j,i) ∈ E , and a = 0 if
ij p ij
(j,i)(cid:6)∈E .Self-edgesarenotallowed(i.e.,a =0)unlessotherwiseindicated.
p ii
The adjacency matrix of an undirected graph is defined analogously except
thata =a foralli(cid:6)=j because (j,i)∈E implies (i,j)∈E .Notethata
ij ji p p ij
denotestheweightfortheedge(j,i)∈E
p
.Iftheweigh(cid:7)tisnotrelev(cid:7)ant,thena
ij
is set equal to 1 if (j,i)∈E . A graphis balanced if p a = p a , for
p j=1 ij j=1 ji
all i. For an undirected graph, A is symmetrical, and thus every undirected
p
graph is balanced.
Define the matrix L =[(cid:2) ]∈Rp×p as
p ij
(cid:2)n
(cid:2) = a , (cid:2) =−a , i(cid:6)=j. (B.1)
ii ij ij ij
j=1,j(cid:5)=i
Note that if (j,i)(cid:6)∈E then (cid:2) =−a =0. Matrix L satisfies
p ij ij p

|     |     |     | B Graph Theory | Notations | 283 |
| --- | --- | --- | -------------- | --------- | --- |
(cid:2)p
|     | (cid:2) ≤0, | i(cid:6)=j, | (cid:2) =0, i=1,...,p. |     | (B.2) |
| --- | ----------- | ----------- | ---------------------- | --- | ----- |
|     | ij          |             | ij                     |     |       |
j=1
Foranundirectedgraph,L
|     |     | p issymmetricalandiscalledtheLaplacian |     |     | matrix. |
| --- | --- | -------------------------------------- | --- | --- | ------- |
However,for adirectedgraph,L isnotnecessarilysymmetricalandis some-
p
times called the nonsymmetrical Laplacian matrix [4] or directed Laplacian
matrix [115].
|     | L   |     |     | L   | =D− (cid:2) |
| --- | --- | --- | --- | --- | ----------- |
Remark B.1. Note that in (B.1) can be equivalently defined as
|     | p   |     |     |     | p   |
| --- | --- | --- | --- | --- | --- |
A ,w(cid:7)hereD =[d ]∈Rp×pisthein-degreematrixgivenasd =0,i(cid:6)=j,and
| p   | ij  |     |     | ij  |     |
| --- | --- | --- | --- | --- | --- |
p
d ii = a ij ,i=1,...,p.Also note thatfor directedgraphs,the definition
j=1
of the nonsymmetrical Laplacian matrix given by (B.1) is different from the
common definition of a Laplacian matrix for a directed graph in the graph
theoryliterature(e.g.,[204]).However,weadoptthedefinitiongivenby(B.1)
for directed graphs due to its relevance to consensus algorithms. (cid:13)(cid:14)
In both the undirected and directed cases,because L has zero row sums,
p
|     | L   |     |     | p×1 |     |
| --- | --- | --- | --- | --- | --- |
0 is an eigenvalue of p with the associated eigenvector 1 p , the column
vector of ones. Note that L is diagonally dominant and has nonnegative
p
diagonal entries. It follows from Theorem C.1 that, for an undirected graph,
| allnonzeroeigenvaluesofL |     | arepositive(L |     |     |     |
| ------------------------ | --- | ------------- | --- | --- | --- |
ispositivesemidefinite),whereas,
|     |     | p   | p   |     |     |
| --- | --- | --- | --- | --- | --- |
for a directed graph, all nonzero eigenvalues of L have positive real parts.
p
−L
Therefore, all nonzero eigenvalues of p have negative real parts. For an
undirected graph, 0 is a simple eigenvalue of L if and only if the undirected
p
graphisconnected[141,p.147].Foradirectedgraph,0isasimpleeigenvalue
ofL
ifthe directedgraphisstronglyconnected[69,Proposition3],although
p
the converse does not hold. For an undirected graph, let λ (L ) be the ith
i p
|     | L (L | ≤ (L | ≤ ··· ≤ (L |     | (L  |
| --- | ---- | ---- | ---------- | --- | --- |
eigenvalue of p with λ 1 p ) λ 2 p ) λ p p ), so that λ 1 p ) = 0.
Foranundirectedgraph,λ (L )isthealgebraic connectivity,whichispositive
2 p
if and only if the undirected graph is connected [141, p. 147]. The algebraic
connectivity quantifies the convergence rate of consensus algorithms [106].
Given a matrix S = [s ] ∈ Rp×p, the directed graph of S, denoted by
ij
V {1,...,p}
Γ(S), is the directed graph with node set p = such that there is
an edge in Γ(S) from j to i if and only if s (cid:6)=0 [91, p. 357].In other words,
ij
the entries of the adjacency matrix satisfy a > 0 if s (cid:6)= 0 and a = 0 if
|     |     |     | ij  | ij  | ij  |
| --- | --- | --- | --- | --- | --- |
s ij =0.

C
| Matrix | Theory | Notations |
| ------ | ------ | --------- |
We needthe following definitions,lemmas,and theoremsfrommatrix theory.
Theorem C.1. [91, Theorem 6.1.1 (Gershgorin’s disc theorem), p. 344] Let
| A=[a | ]∈Rn×n, and | let |
| ---- | ----------- | --- |
ij
(cid:2)n
|     |     | R (cid:8) (A)≡ |a |, i=1,...,n, |
| --- | --- | ------------------------------- |
i ij
j=1,j(cid:5)=i
denote the deleted absolute row sums of A. Then all eigenvalues of A are
| located | in the union | of n discs |
| ------- | ------------ | ---------- |
(cid:19)n
(cid:8)
{z ∈C:|z−a |≤R (A)}≡G(A).
ii i
i=1
Furthermore, if a union of k of these n discs forms a connected region that
n−k
is disjoint from all of the remaining discs, then there are precisely k
| eigenvalues | of A in | this region. |
| ----------- | ------- | ------------ |
Lemma C.2. [91, Lemma 8.2.7 part(i), p. 498] Let A ∈ Rn×n be given, let
∈ C
λ be given, and suppose x and y are vectors such that (i) Ax = λx, (ii)
ATy = λy, and (iii) xTy = 1. If |λ| = ρ(A) > 0, where ρ(A) denotes the
spectral radius of A, andλ is the only eigenvalue of A with modulus ρ(A),
|     | m→∞(λ−1A)m | →xyT. |
| --- | ---------- | ----- |
then lim
Rn×n
The matrix A ∈ is reducible if either (i) n = 1 and A = 0, or (ii)
n ≥ 2 and there exists a permutation matrix P ∈ Rn×n such that PTAP is
in block upper triangular form. A matrix is irreducible if it is not reducible.
Rn×n
Theorem C.3. [91, Theorem 6.2.24, p. 362] The matrix A∈ is irre-
| ducible | if and only if | Γ(A) is strongly connected. |
| ------- | -------------- | --------------------------- |

| 286 | C Matrix Theory | Notations |     |     |     |     |
| --- | --------------- | --------- | --- | --- | --- | --- |
A vector x or matrix A is nonnegative (respectively, positive), denoted
as x ≥ 0 (respectively, x > 0) or A ≥ 0 (respectively, A > 0), if all of
its entries are nonnegative (respectively, positive). For nonnegative matrices,
A≥B(respectively,A>B)impliesthatA−Bisanonnegative(respectively,
positive)matrix.Twon×nnonnegativematricesP andQareofthesametype
if they havezero entriesandpositive entries in the same locations(see [253]).
We use the notation P ∼Q to denote that P and Q are of the same type.
Theorem C.4. [91,Theorem8.3.1,p.503]IfA∈Rn×n isnonnegative,then
|     |     |     |     |     | ≥   | (cid:6)= |
| --- | --- | --- | --- | --- | --- | -------- |
ρ(A) is an eigenvalue of A and there is a nonnegative vector x 0, x 0,
| such that | Ax=ρ(A)x. |     |     |     |     |     |
| --------- | --------- | --- | --- | --- | --- | --- |
Theorem C.5. [91, Perron-Frobenius theorem, p. 508] If A∈Rn×n is irre-
ducible and nonnegative, then (i) ρ(A) > 0, (ii) ρ(A) is an eigenvalue of A,
(iii) there is a positive vector x such that Ax = ρ(A)x, and (iv) ρ(A) is an
algebraically (and hence geometrically) simple eigenvalue of A.
A square nonnegative matrix is primitive if it is irreducible and has ex-
actly one eigenvalue of maximum modulus, which is necessarily positive. A
squarenonnegative matrix is row stochastic if all of its row sums are 1 [91,p.
526]. Every row-stochastic matrix has 1 as an eigenvalue with an associated
eigenvector 1 . The spectral radius of a row-stochastic matrix is 1 because 1
n
is an eigenvalue and Theorem C.1 implies that all of the eigenvalues are con-
tained in a closed unit disc. The row-stochastic matrix A is indecomposable
| and aperiodic |       | k→∞Ak  | =1 νT, | where ν is a | column vector | [253]. |
| ------------- | ----- | ------ | ------ | ------------ | ------------- | ------ |
|               | (SIA) | if lim | n      |              |               |        |
]∈Rn×n,
Given a row-stochastic matrix S =[s define the matrix function
ij
(cid:2)
χ(S)=1−min
|     |     |     | min(s | i1j ,s i2j ). |     |     |
| --- | --- | --- | ----- | ------------- | --- | --- |
i1,i2
j
Note that χ(S) ≤ 1 for every row-stochastic matrix S. If χ(S) < 1, S is a
scrambling matrix. Also note that χ(S) = 0 if and only if the rows of S are
| identical | [253]. |     |     |     |     |     |
| --------- | ------ | --- | --- | --- | --- | --- |
Theorem C.6. [91, Theorem 8.5.1, p. 516] If A ∈ Rn×n is nonnegative
|                |             | k→∞[ρ(A)−1Ak]→wνT, |     |          |          | ATν |
| -------------- | ----------- | ------------------ | --- | -------- | -------- | --- |
| and primitive, | then        | lim                |     | where Aw | = ρ(A)w, | =   |
| ρ(A)ν,         | w >0, ν >0, | andw Tν =1.        |     |          |          |     |
Theorem C.7. [91, Theorem 8.5.2, p. 516] If A ∈ Rn×n is nonnegative,
Am
then A is primitive if and only if >0 for some positive integer m.
Because the spectral radius of a row-stochastic matrix is 1, Theorem C.6
implies that if A is row stochastic and primitive; then lim k→∞Ak = 1 νT,
n
| ATν   |           | 1Tν |     |     |     |     |
| ----- | --------- | --- | --- | --- | --- | --- |
| where | =ν, ν >0, | and | =1. |     |     |     |
n
|          |               |              | ∈ Rp×p,    | ∈ Rq×q, | ∈ Rp×p, |     |
| -------- | ------------- | ------------ | ---------- | ------- | ------- | --- |
| Lemma    | C.8. [84]     | Suppose that | U          | V       | X       | and |
| Y ∈Rq×q. | The following | arguments    | are valid. |         |         |     |

|       |        |      | C Matrix Theory | Notations | 287 |
| ----- | ------ | ---- | --------------- | --------- | --- |
| ⊗V)(X | ⊗Y)=UX | ⊗VY. |                 |           |     |
(i) (U
| (ii) (U ⊗V)T  | =UT ⊗VT.               |                       |         |           |     |
| ------------- | ---------------------- | --------------------- | ------- | --------- | --- |
|               |                        |                       | ⊗V)−1   | =U−1⊗V−1. |     |
| (iii) Suppose | that U                 | and V are invertible. | Then (U |           |     |
| (iv) If U     | and V are symmetrical, | so is                 | U ⊗V.   |           |     |
(v) If U and V are symmetrical positive definite (respectively, positive semi-
⊗V.
| definite), | so is U |     |     |     |     |
| ---------- | ------- | --- | --- | --- | --- |

D
| Rigid | Body | Attitude | Dynamics |     |     |     |
| ----- | ---- | -------- | -------- | --- | --- | --- |
Givenavectorvwithcoordinaterepresentation[v ,v ,v ]T,thecross-product
|          |            |          |       | 1 2    | 3   |     |
| -------- | ---------- | -------- | ----- | ------ | --- | --- |
| operator | is denoted | by [249] |       |        |     |     |
|          |            |          | ⎡     | ⎤      |     |     |
|          |            |          | 0 −v  | v      |     |     |
|          |            |          |       | 3 2    |     |     |
|          |            | v × =    | ⎣ v 0 | −v ⎦ , |     |     |
|          |            |          | 3     | 1      |     |     |
−v
|     |     |     | v   | 0   |     |     |
| --- | --- | --- | --- | --- | --- | --- |
2 1
|                  |     |           | v×w =v×w, |             |       |     |
| ---------------- | --- | --------- | --------- | ----------- | ----- | --- |
| which represents | the | fact that |           | where w =[w | ,w ,w | ]T. |
1 2 3
A quaternion is defined as q = [qˆT,q¯]T ∈ R4, where qˆ∈ R3 denotes the
vectorpartandq¯∈Rdenotesthescalarpart.Theproductoftwoquaternions
| p and q | is defined by |     | (cid:22) | (cid:23) |     |     |
| ------- | ------------- | --- | -------- | -------- | --- | --- |
q¯pˆ+p¯qˆ+qˆ×pˆ
|     |     | qp= |     | .   |     | (D.1) |
| --- | --- | --- | --- | --- | --- | ----- |
q¯p¯−qˆTpˆ
qp(cid:6)=pq,butthey
| Quaternionsarenotcommutative,i.e., |     |     |     |     | areassociative,i.e., |     |
| ---------------------------------- | --- | --- | --- | --- | -------------------- | --- |
(pq)s = p(qs), and distributive, i.e., (p+q)s = ps+qs. The conjugate of
|            |              | q∗  | [−qˆT,q¯]T. |               |          |          |
| ---------- | ------------ | --- | ----------- | ------------- | -------- | -------- |
| quaternion | q is defined | by  | =           | The conjugate | of qp is | given by |
(qp)∗ =p∗q∗.
Rigid body attitudes can be represented by Euler parameters, i.e., unit
|             |                                      |     |     | =[qˆT,q¯]T | ∈R4,where |     |
| ----------- | ------------------------------------ | --- | --- | ---------- | --------- | --- |
| quaternions | [93,250].Aunitquaternionisdefinedasq |     |     |            |           |     |
qˆ= asin(φ) ∈ R3 denotes the vector part and q¯= cos(φ) ∈ R denotes the
|     | 2   |     |     |     | 2   |     |
| --- | --- | --- | --- | --- | --- | --- |
a∈R3
scalar part of the unit quaternion.In this notation, is a unit vector in
the direction of rotation with a coordinate representation [a ,a ,a ]T, called
1 2 3
the Euler axis, and φ is the rotational angle about a, called the Euler angle.
Notethatfortheunitquaternionq,qTq
=1bydefinition.Theproductoftwo
unitquaternionsisalsoaunitquaternion.Theconjugateofaunitquaternion
is alsoa unitquaternion.Themultiplicative identity quaternionis denotedby
(cid:2)
|     |     | q   | =[0,0,0,1]T, |     |     |     |
| --- | --- | --- | ------------ | --- | --- | --- |
I
| qq∗ | q∗q |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
where = = q I and qq I = q I q = q. A unit quaternion is not unique
because q and −q represent the same attitude. However, uniqueness can be
achieved by restricting φ to the range 0≤φ≤π so that q¯≥0 [93].

290 D Rigid Body AttitudeDynamics
Suppose that qd and q represent, respectively, the desired and actual at-
titude, then the attitude error is given by q =qd∗q =[qˆT,q¯ ]T, which repre-
e e e
sents the attitude of the actualreference frame F with respect to the desired
reference frame Fd. The relationship between the rotational matrix C and
ab
the unit quaternion q is given by
C =(2q¯2−1)I+2qˆqˆT −2q¯qˆ × ,
ab
where q represents the attitude of F with respect to F [250].
a b
Attitude dynamics for rigid bodies using Euler parameters are given by
1 1 1
q-˙ =− ω ×q- + q ω , q˙ =− ω ·q-, (D.2a)
i i i i i i i i
2 2 2
J ω˙ =−ω ×(J ω )+τ , i=1,··· ,n, (D.2b)
i i i i i i
whereq- ∈R3 andq ∈Rarevectorandscalarpartsoftheunitquaternionof
i i
the ithrigidbody,ω ∈R3 is the angularvelocity,andJ ∈R3×3 andτ ∈R3
i i i
are, respectively, the inertia and controltorque [93]. Note that (D.2a) can be
written as
1
q˙ = q ωˇ, (D.3)
i i i
2
where ωˇ = [ωT,0]T ∈ R4 is a quaternion and q ωˇ is computed by follow-
i i i i
ing (D.1) with q and p replaced by q and ωˇ, respectively.
i i
Lemma D.1.Suppose that the unit quaternion and angular velocity pairs
(q ,ω )and (q ,ω ) satisfy (D.2) with the same inertia J and with the control
k k (cid:7) (cid:7)
torques τ and τ , respectively. Then the unit quaternion and angular velocity
k (cid:7)
pair (q∗q ,ω −ω ) also satisfies (D.2a). In addition, if V = (cid:9)q∗q −q (cid:9)2,
(cid:7) k k (cid:7) q (cid:7) k I
then V˙ = (ω − ω )Tq .∗q , where q .∗q denotes the vector part of the unit
q k (cid:7) (cid:7) k (cid:7) k
quaternion q∗q . Furthermore, if V =(cid:9)q −q (cid:9)2, then V˙ =(ω −ω )Tq .∗q .
(cid:7) k q k (cid:7) q k (cid:7) (cid:7) k
Moreover, if V = 1(ω −ω )·J(ω −ω ), then V˙ = (ω −ω )·{τ −τ −
ω 2 k (cid:7) k (cid:7) ω k (cid:7) k (cid:7)
1[ω ×J(ω −ω )]}.
2 k k (cid:7)
Proof: See [244,249].
Lemma D.2.Let τ = ω ×(J ω )−k qˆ −K ω , where k is a positive
i i i i qi i ωi i qi
scalar and K is a positive-definite matrix, in (D.2b). Then qˆ(t) → 0 and
ωi i
ω (t)→0, as t→∞.
i
Proof: The proof follows from [252] by using the Lyapunov function V =
k (cid:9)q −q (cid:9)2+ 1ωTJ ω .
qi i I 2 i i i
Modified Rodriguez parameters (MRPs) [235] can also be used to rep-
resent the attitude of a rigid body with respect to an inertial frame. Let
σ = a tan(φi) ∈ R3 represent the MRPs for the ith rigid body, where a is
i i 4 i
the Euler axis and φ is the Euler angle.
i
Attitude dynamics for rigid bodies using MRPs are given by

D Rigid Body AttitudeDynamics 291
σ˙ =F(σ )ω (D.4a)
i i i
J ω˙ =−ω ×J ω +τ i=1,...,n, (D.4b)
i i i i i i
where ω ∈R3 denotes the angular velocity, J ∈R3×3 is the inertia, τ ∈R3
i i i
is the control torque, and
F(σ )= (cid:2) 1 [( 1−σ i Tσ i)I +σ × +σ σT].
i 2 2 3 i i i
Following [217,254],(D.4) can be written as
H
∗
(σ )σ¨ +C
∗
(σ ,σ˙ )σ˙ =F
−T(σ
)τ , (D.5)
i i i i i i i i i
where
H
∗
(σ )=
(cid:2)
F
−T(σ
)J F
−1(σ
),
i i i i i
and
C ∗ (σ ,σ˙ )= (cid:2) −F −T(σ )J F −1(σ )F˙(σ )F −1(σ )
i i i i i i i i
−F −T(σ )(J F −1(σ )σ˙ ) × F −1(σ ).
i i i i i
Note that H∗(σ ) is a symmetrical positive-definite matrix and H˙∗(σ ) −
i i i i
2C∗(σ ,σ˙ ) is a skew-symmetrical matrix [217].
i i i

E
| Linear   | System |                          | Theory                  |     | Background |     |     |     |        |
| -------- | ------ | ------------------------ | ----------------------- | --- | ---------- | --- | --- | --- | ------ |
| Consider | the    | linear state             | equation                |     |            |     |     |     |        |
|          |        | x˙(t)=A(t)x(t)+B(t)u(t), |                         |     |            | x(t | )=x | ,   | (E.1a) |
|          |        |                          |                         |     |            | 0   | 0   |     |        |
|          |        |                          | y(t)=C(t)x(t)+D(t)u(t), |     |            |     |     |     | (E.1b) |
where x(t) ∈ Rn is the state vector, u(t) ∈ Rm is the input signal, y(t) ∈ Rp
|        |        |         | ∈ Rn×n, |      | ∈   | Rn×m, | ∈   | Rp×n, | ∈    |
| ------ | ------ | ------- | ------- | ---- | --- | ----- | --- | ----- | ---- |
| is the | output | signal, | A(t)    | B(t) |     | C(t)  |     | and   | D(t) |
Rp×m.
The linear state equation (E.1) is linear time invariant (LTI) if all of
the matrices A, B, C, and D are constant and is linear time varying (LTV)
otherwise.
| The | solution | of the | state is | given | by  |     |     |     |     |
| --- | -------- | ------ | -------- | ----- | --- | --- | --- | --- | --- |
(cid:15)
t
t≥t
|     |     | x(t)=Φ(t,t | 0 )x 0 | + Φ(t,σ)B(σ)u(σ)dσ, |     |     |     | 0 , |     |
| --- | --- | ---------- | ------ | ------------------- | --- | --- | --- | --- | --- |
t0
| where | Φ(t,t | ) is transition | matrix | defined | as  |     |     |     |     |
| ----- | ----- | --------------- | ------ | ------- | --- | --- | --- | --- | --- |
0
|     |     |     | (cid:15) | (cid:15) |     | (cid:15) |     |     |     |
| --- | --- | --- | -------- | -------- | --- | -------- | --- | --- | --- |
|     |     |     | t        |          | t   | σ1       |     |     |     |
(cid:2)
| Φ(t,t | )=I | +   | A(σ )dσ | +   | A(σ | ) A(σ | )dσ | dσ +··· | .   |
| ----- | --- | --- | ------- | --- | --- | ----- | --- | ------- | --- |
|       | 0   | n   | 1       | 1   |     | 1     | 2   | 2 1     |     |
|       |     |     | t0      |     | t0  | t0    |     |         |     |
For an LTI system, Φ(t,t )=eA(t−t0). The solution of the output is given by
0
(cid:15)
t
| y(t)=C(t)Φ(t,t |     |     | )x + | C(t)Φ(t,σ)B(σ)u(σ)dσ+D(t)u(t), |     |     |     |     | t≥t . |
| -------------- | --- | --- | ---- | ------------------------------ | --- | --- | --- | --- | ----- |
|                |     | 0   | 0    |                                |     |     |     |     | 0     |
t0
Internal stability deals with the stability of the zero-input response of
| (E.1a), | i.e., | the linear | state equation |     |     |       |     |     |       |
| ------- | ----- | ---------- | -------------- | --- | --- | ----- | --- | --- | ----- |
|         |       |            | x˙ =A(t)x,     |     | x(t | )=x . |     |     | (E.2) |
|         |       |            |                |     | 0   | 0     |     |     |       |
The following definitions and theorem characterize internal stability.

294 E Linear System Theory Background
Definition E.1. [42, p. 138] The linear state equation (E.2) is marginally
stable or stable if every finite initial state excites a bounded response. The
linear state equation (E.2) is asymptotically stable if the response excited by
every finite initial state is bounded and approaches zero, as t→∞.
Definition E.2. [205, Definitions 6.1, 6.5, and 6.12] The linear state equa-
tion (E.2) is uniformly stable if there exists a finite positive constant γ such
that for any t and x , the corresponding solution satisfies (cid:9)x(t)(cid:9) ≤ γ(cid:9)x (cid:9),
0 0 0
∀t ≥ t . The linear state equation (E.2) is uniformly exponentially stable if
0
there exist finite positive constants γ and λ such that for any t and x , the
0 0
corresponding solution satisfies (cid:9)x(t)(cid:9) ≤ γe−λ(t−t0)(cid:9)x (cid:9), t ≥ t . The linear
0 0
stateequation (E.2)isuniformlyasymptotically stableifitis uniformlystable,
and if given anypositive constantδ, thereexists apositive T suchthat for any
t and x , the corresponding solution satisfies (cid:9)x(t)(cid:9)≤δ(cid:9)x (cid:9), t≥t +T.
0 0 0 0
Theorem E.3. [205, Theorem 6.13] The linear state equation (E.2) is uni-
formly asymptotically stable if and only if it is uniformly exponentially stable.
Input-output stability deals with the stability of (E.1) with zero initial
state (i.e., x = 0). The following definition characterizes input-output sta-
0
bility.
Definition E.4. [205, Definition 6.1] The linear state equation (E.1) is uni-
formly bounded-input, bounded-output stable (BIBO) if there exists a finite
constant η such that for any t and any input signal u(t), the corresponding
0
zero-state response satisfies sup (cid:9)y(t)(cid:9)≤ηsup (cid:9)u(t)(cid:9).
t≥t0 t≥t0
Remark E.5. The definition of uniformly bounded-input, bounded-state sta-
bility follows Definition E.4 with y(t) replaced by x(t). (cid:13)(cid:14)
Note that for an LTI system, asymptotical stability always implies uni-
formlybounded-input,bounded-state stabilityanduniformly bounded-input,
bounded-output stability. However, for an LTV system, asymptotical stabil-
ity does not necessarily imply uniformly bounded-input, bounded-state and
bounded-input, bounded-output stability [42, p. 140]. The following lemma
shows their relationship for an LTV system.
Lemma E.6. [205, Lemma12.4] Supposethatthelinearstateequation (E.2)
is uniformly exponentially stable. Then the linear state equation (E.1) is uni-
formly bounded-input, bounded-state stable. Furthermore, if there exist finite
constants β, μ, andγ such that for all t, (cid:9)B(t)(cid:9) ≤ β, (cid:9)C(t)(cid:9) ≤ μ, and
(cid:9)D(t)(cid:9)≤γ, then (E.1) is uniformly bounded-input, bounded-output stable.

F
| Nonlinear | System | Theory | Background |     |
| --------- | ------ | ------ | ---------- | --- |
We need the following definitions, lemmas, and theorems from nonlinear sys-
tem theory:
| Consider | the autonomous | system |           |       |
| -------- | -------------- | ------ | --------- | ----- |
|          |                |        | x˙ =f(x), | (F.1) |
where f :D →Rn is a locally Lipschitz mapfromadomain D ⊆Rn into Rn.
Theorem F.1. [105, Theorem 4.2] Let x = 0 be an equilibrium point
|     | Rn  | → R |     |     |
| --- | --- | --- | --- | --- |
for (F.1). Let V : be a continuously differentiable function such
that
∀x(cid:6)=0,
|     |     | V(0)=0 and | V(x)>0, |     |
| --- | --- | ---------- | ------- | --- |
(cid:9)x(cid:9)→∞⇒V(x)→∞,
|          |             |                | V˙(x)<0, ∀x(cid:6)=0. |     |
| -------- | ----------- | -------------- | --------------------- | --- |
| Then x=0 | is globally | asymptotically | stable.               |     |
Definition F.2. [105, p. 127] A set M is said to be an invariant set with
respect to (F.1) if x(0)∈M implies x(t)∈M, ∀t∈R. A set M is said to be
| a positively | invariant | set if x(0)∈M | implies x(t)∈M, | ∀t≥0. |
| ------------ | --------- | ------------- | --------------- | ----- |
Theorem F.3. [218, Theorem 3.4 (Local Invariance Set Theorem)] Con-
sider the autonomous system (F.1). Let V :Rn →R be a continuously differ-
| entiable   | function. Assume | that     |                   |             |
| ---------- | ---------------- | -------- | ----------------- | ----------- |
| • for some | c>0, the         | region Ω | defined by V(x)<c | is bounded; |
c
| • V˙(x)≤0, | ∀x∈Ω | .   |     |     |
| ---------- | ---- | --- | --- | --- |
c
V˙(x)=0,
Let E be the set of all points in Ω where and let M be the largest
c
invariant set in E. Then every solution x(t) starting in Ω approaches M, as
c
t→∞.

| 296 | F Nonlinear | System | Theory | Background |     |     |     |     |     |
| --- | ----------- | ------ | ------ | ---------- | --- | --- | --- | --- | --- |
Theorem F.4. [218, Theorem 3.5 (Global Invariance Set Theorem)] Con-
sider the autonomous system (F.1). Let V :Rn →R be a continuously differ-
| entiable   | function. | Assume                 | that |     |     |     |     |     |     |
| ---------- | --------- | ---------------------- | ---- | --- | --- | --- | --- | --- | --- |
| • V˙(x)≤0, | ∀x∈Rn;    |                        |      |     |     |     |     |     |     |
| • V(x)→∞   |           | as (cid:9)x(cid:9)→∞.1 |      |     |     |     |     |     |     |
bethesetofallpointswhereV˙(x)=0,andletM
| LetE |     |     |     |     |     | bethelargestinvariant |     |     |     |
| ---- | --- | --- | --- | --- | --- | --------------------- | --- | --- | --- |
set in E. Then all solutions globally asymptotically converge to M, as t→∞.
Lemma F.5. [218, Lemma4.2(Barbalat)] Ifthedifferentiable functionf(t)
has afinitelimit,as t→∞,andif f˙(t)is uniformlycontinuous,2 thenf˙(t)→
t→∞.
0, as
Lemma F.6. [218, Lemma4.3 (Lyapunov-like Lemma)] Ifascalar function
| V(x,t)    | satisfies   | the following |     | conditions: |     |     |     |     |     |
| --------- | ----------- | ------------- | --- | ----------- | --- | --- | --- | --- | --- |
| • V(x,t)  | is lower    | bounded;      |     |             |     |     |     |     |     |
| • V˙(x,t) | is negative | semidefinite; |     |             |     |     |     |     |     |
• V˙(x,t)
|                 | is uniformly |          | continuous | in  | t;  |     |     |     |     |
| --------------- | ------------ | -------- | ---------- | --- | --- | --- | --- | --- | --- |
| then V˙(x,t)→0, |              | as t→∞.3 |            |     |     |     |     |     |     |
Definition F.7. [105, Defnition 4.2, p. 144] A continuous function α :
[0,a) → [0,∞) is said to belong to class K if it is strictly increasing and
|        |          |         |        |          | K   | ∞      |          | →   | ∞,  |
| ------ | -------- | ------- | ------ | -------- | --- | ------ | -------- | --- | --- |
| α(0) = | 0. It is | said to | belong | to class | ∞   | if a = | and α(r) |     | as  |
r →∞.
Definition F.8. [105, Defnition 4.3, p. 144] A continuous function β :
[0,a)× [0,∞) → [0,∞) is said to belong to class KL if, for each fixed s,
the mapping β(r,s) belongs to class K with respect to r and, for each fixed r,
|             |        |               |     |              |         | β(r,s)→0, |     | s→∞. |       |
| ----------- | ------ | ------------- | --- | ------------ | ------- | --------- | --- | ---- | ----- |
| the mapping | β(r,s) | is decreasing |     | with         | respect | to s and  |     | as   |       |
| Consider    | the    | system        |     |              |         |           |     |      |       |
|             |        |               |     | x˙ =f(t,x,u) |         |           |     |      | (F.2) |
wheref :[0,∞)×Rn×Rm →Rn ispiecewisecontinuousintandlocallyLip-
schitz in x andu.The input u(t) is a piecewise continuous,bounded function
t≥0.
of t for all
Definition F.9. [105, Defnition 4.7, p. 175] The system (F.2) is said to be
|     |     |     |     |     |     | KL  |     |     | K   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
input-to-state stable (ISS) if there exist a class function β and a class
function γ such that for any initial state x(t ) and any bounded input u(t),
0
t≥t
| the solution | x(t)                            | exists | for all | 0            | and satisfies |                    |          |     |       |
| ------------ | ------------------------------- | ------ | ------- | ------------ | ------------- | ------------------ | -------- | --- | ----- |
|              |                                 |        |         |              |               | (cid:22)           | (cid:23) |     |       |
|              | (cid:9)x(t)(cid:9)≤β[(cid:9)x(t |        |         | )(cid:9),t−t |               | (cid:9)u(τ)(cid:9) |          |     |       |
|              |                                 |        |         | 0            | 0 ]+γ         | sup                | .        |     | (F.3) |
t0≤τ≤t
1 A function satisfying this condition is said to be radially unbounded
2 A sufficient condition for a differentiable function to be uniformly continuous is
| that | its derivative | is bounded. |     |     |     |     |     |     |     |
| ---- | -------------- | ----------- | --- | --- | --- | --- | --- | --- | --- |
3
| Lemma | F.6 follows | from | Lemma | F.5. |     |     |     |     |     |
| ----- | ----------- | ---- | ----- | ---- | --- | --- | --- | --- | --- |

|     |     | F   | Nonlinear System Theory | Background | 297 |
| --- | --- | --- | ----------------------- | ---------- | --- |
As stated in [105, p. 175], (F.3) implies that for any bounded u(t), the
state x(t) will be bounded. In addition, if u(t) converges to zero, as t → ∞,
so does x(t).
Theorem F.10. [132, Theorem 7.9, p. 196] Consider the cascade intercon-
| nection of     | the systems |          |              |     |        |
| -------------- | ----------- | -------- | ------------ | --- | ------ |
|                |             | x˙       | =f(x,z)      |     | (F.4a) |
|                |             | z˙       | =g(z,u).     |     | (F.4b) |
| If both (F.4a) | and (F.4b)  | are ISS, | so is (F.4). |     |        |

References
1. http://www.crossbow.com.
2. http://zagi.com.
3. USGS digital elevation models. http://data.geocomm.com/dem/.
4. R. Agaev and P. Chebotarev. On the spectra of nonsymmetric Laplacian
matrices. Linear Algebra and its Applications, 399:157–178, 2005.
5. S.AkellaandS.Hutchinson. Coordinatingthemotionsofmultiplerobotswith
specific trajectories. In Proceedings of the IEEE International Conference on
Robotics and Automation, pages 624–631, Washington DC, May 2002.
6. M. Alighanbari and J. How. Decentralized task assignment for unmanned air
vehicles. InProceedings of the IEEEConference onDecision andControl, and
the European Control Conference, pages 5668–5673, Seville, Spain, December
2005.
7. M.Alighanbari,Y.Kuwata,andJ.How. Coordinationandcontrolofmultiple
UAVs with timing constraints and loitering. In Proceedings of the American
Control Conference, pages 5311–5316, Denver,CO, June2003.
8. V.Ambrosia,S.Wegener,J.Brass,andS.Schoenung.TheUAVwesternstates
fire mission: Concepts, plans, and developmental advancements. In Proceed-
ingsoftheAIAA3rdUnmannedUnlimitedTechnicalConference,Chicago,IL,
September2004. Paper no. AIAA-2004-6415.
9. E. P. Anderson and R. W. Beard. An algorithmic implementation of con-
strained extremal control for UAVs. In Proceedings of the AIAA Guidance,
Navigation, and Control Conference, Monterey, CA, August 2002. Paper no.
AIAA-2002-4470.
10. M. Anderson, M. Mckay, and B. Richardson. Multirobot automated indoor
floor characterization team. InProceedings of the IEEE International Confer-
ence on Robotics and Automation, pages 1750–1753, Minneapolis, April 1996.
11. M. R. Anderson and A. C. Robbins. Formation flight as a cooperative game.
In Proceedings of the AIAA Guidance, Navigation, and Control Conference,
pages 244–251, Boston, MA, August 1998. Paper no. AIAA-98-4124.
12. D. Angeli and P.-A. Bliman. Extension of a result by Moreau on stability
of leaderless multi-agent systems. In Proceedings of the IEEE Conference on
Decision and Control, and the European Control Conference, pages 759–764,
Seville, Spain,December 2005.

300 References
13. M.Arcak.Passivityasadesigntoolforgroupcoordination.IEEETransactions
| on Automatic | Control, | 52(8):1380–1390, |     | August 2007. |     |
| ------------ | -------- | ---------------- | --- | ------------ | --- |
14. A. Astolfi. Exponential stabilization of a wheeled mobile robot via discon-
tinuous control. Journal of Dynamic Systems, Measurement, and Control,
| 121(1):121–126, | March | 1999. |     |     |     |
| --------------- | ----- | ----- | --- | --- | --- |
15. T. Balch and R. C. Arkin. Behavior-based formation control for multirobot
teams. IEEE Transactions on Robotics and Automation, 14(6):926–939, De-
cember 1998.
16. T. Balch andL.E. Parker,editors. Robot Teams: From Diversity to Polymor-
| phism. A. | K. Peters, | Natick, MA, | 2002. |     |     |
| --------- | ---------- | ----------- | ----- | --- | --- |
17. D. Bauso, L. Giarre, and R. Pesenti. Non-linear protocols for optimal distrib-
uted consensus in networks of dynamic agents. Systems and Control Letters,
| 55(11):918–928, | 2006. |     |     |     |     |
| --------------- | ----- | --- | --- | --- | --- |
18. R. Beard and T. McLain. Multiple UAV cooperative search under collision
avoidanceandlimited rangecommunication constraints. InProceedings of the
IEEE Conference on Decision and Control, pages 25–30, Maui, HI, December
2003.
19. R. W. Beard and F. Y. Hadaegh. Constellation templates: An approach to
autonomous formation flying. In World Automation Congress, pages 177.1–
| 177.6, Anchorage, | AK,May | 1998. | ISIAC. |     |     |
| ----------------- | ------ | ----- | ------ | --- | --- |
20. R.W.BeardandF.Y.Hadaegh. Fueloptimizationforunconstrainedrotation
ofspacecraftformations. JournaloftheAstronautical Sciences,43(3):259–273,
| July–December | 1999. |     |     |     |     |
| ------------- | ----- | --- | --- | --- | --- |
21. R.W. Beard, D.Kingston, M. Quigley, D.Snyder,R.Christiansen, W. John-
son, T.McLain, and M. Goodrich. Autonomousvehicletechnologies for small
fixed-wing UAVs. Journal of Aerospace Computing, Information, and Com-
| munication, | 2(1):92–108, | 2005. |     |     |     |
| ----------- | ------------ | ----- | --- | --- | --- |
22. R. W. Beard, J. R. Lawton, and F. Y. Hadaegh. A coordination architec-
ture for spacecraft formation control. IEEE Transactions on Control Systems
| Technology, | 9(6):777–790, | November2001. |     |     |     |
| ----------- | ------------- | ------------- | --- | --- | --- |
23. R. W. Beard, D. Lee, M. Quigley, S. Thakoor, and S. Zornetzer. A new ap-
proach to observation of descent and landing of future Mars mission using
bioinspired technology innovations. AIAA Journal of Aerospace Computing,
| Information, | and Communication, |     | 2(1):65–91, | January | 2005. |
| ------------ | ------------------ | --- | ----------- | ------- | ----- |
24. R. W.Beard, T. W. McLain, M. Goodrich, and E. P. Anderson. Coordinated
targetassignmentandinterceptforunmannedairvehicles. IEEETransactions
| on Robotics | and Automation, |     | 18(6):911–922, | 2002. |     |
| ----------- | --------------- | --- | -------------- | ----- | --- |
25. R. W. Beard, T. W. McLain, and F. Y. Hadaegh. Fuel optimization for con-
strained rotation of spacecraft formations. Journal of Guidance, Control, and
| Dynamics, | 23(2):339–346, | March–April |     | 2000. |     |
| --------- | -------------- | ----------- | --- | ----- | --- |
26. R. W. Beard, T. W. McLain, D. Nelson, D. Kingston, and D. Johanson. De-
centralized cooperative aerial surveillance using fixed-wing miniature UAVs.
| Proceedings | of the IEEE, | 94(7):1306–1324, |     | 2006. |     |
| ----------- | ------------ | ---------------- | --- | ----- | --- |
27. J.Bellingham,M.Tillerson,A.Richards,andJ.P.How. Multi-taskallocation
andpathplanningforcooperatingUAVs.InS.Butenko,R.Murphey,andP.M.
Pardalos, editors, Cooperative Control: Models, Applications and Algorithms.
| Kluwer, | Norwell, MA, | 2003. |     |     |     |
| ------- | ------------ | ----- | --- | --- | --- |
28. C. Belta and V. Kumar. Abstraction and control for groups of robots. IEEE
Transactions on Robotics and Automation, 20(5):865–875, October2004.

References 301
29. W.BlakeandD.Multhopp. Design,performanceandmodelingconsiderations
for close formation flight. In Proceedings of the AIAA Guidance, Navigation,
and Control Conference, pages476–486, Boston,MA,August1998. Paperno.
AIAA-98-4343.
30. P.-A.BlimanandG.Ferrari-Trecate. Averageconsensusproblemsinnetworks
ofagentswithdelayedcommunications.InProceedingsoftheIEEEConference
on Decision and Control, and the European Control Conference, pages 7066–
| 7071, Seville, | Spain, | December2005. |     |     |     |     |
| -------------- | ------ | ------------- | --- | --- | --- | --- |
31. V.D.Blondel,J.M.Hendrickx,A.Olshevsky,andJ.N.Tsisiklis. Convergence
inmultiagentcoordination,consensus,andflocking.InProceedingsoftheIEEE
Conference on Decision and Control, and the European Control Conference,
| pages 2996–3000, |     | Seville, | Spain,December |     | 2005. |     |
| ---------------- | --- | -------- | -------------- | --- | ----- | --- |
32. V. Borkar and P. Varaiya. Asymptotic agreement in distributed estimation.
| IEEE Transactions |     | on  | Automatic | Control, | 27(3):650–655, | 1982. |
| ----------------- | --- | --- | --------- | -------- | -------------- | ----- |
33. R. W. Brockett. Asymptotic stability and feedback stabilization. In R. W.
Brockett, R. S. Millman, and H. J. Sussmann, editors, Differential Geometric
| Control | Theory, | pages | 181–191, | Boston, | 1983. Birkhau¨ser. |     |
| ------- | ------- | ----- | -------- | ------- | ------------------ | --- |
34. M. Campbell, R. D’Andrea, J. Lee, and E. Scholte. Experimental demon-
strations ofsemi-autonomouscontrol. InProceedings of the American Control
| Conference, | pages | 5338–5343, |     | Boston, | MA, July 2004. |     |
| ----------- | ----- | ---------- | --- | ------- | -------------- | --- |
35. M.Cao,A.S.Morse,andB.D.O.Anderson.Coordinationofanasynchronous
multi-agent system via averaging. In IFAC World Congress, Prague, Czech
| Republic,2005. |     | Paper | code Mo-A09-TO/5. |     |     |     |
| -------------- | --- | ----- | ----------------- | --- | --- | --- |
36. M. Cao, D. A. Spielman, and A. S. Morse. A lower bound on convergence
of a distributed network consensus algorithm. In Proceedings of the IEEE
Conference on Decision and Control, and the European Control Conference,
| pages 2356–2361, |     | Seville, | Spain,December |     | 2005. |     |
| ---------------- | --- | -------- | -------------- | --- | ----- | --- |
37. J. R. Carpenter. Decentralized control of satellite formations. International
| Journal | of Robust | and | Nonlinear | Control, | 12:141–161, | 2002. |
| ------- | --------- | --- | --------- | -------- | ----------- | ----- |
38. D. W. Casbeer, D. B. Kingston, R. W. Beard, T. W. McLain, S.-M. Li, and
R.Mehra. Cooperativeforestfiresurveillanceusingateamofsmallunmanned
air vehicles. International Journal of Systems Sciences, 37(6):351–360, 2006.
39. S.Chakravorty. Design and OptimalControl of Multi-Spacecraft Interferomet-
ric Imaging Systems. PhD thesis, University of Michigan, Ann Arbor, MI,
2004.
40. P.Chandler,S.Rasumussen,andM.Pachter. UAVcooperativepathplanning.
In Proceedings of the AIAA Guidance, Navigation, and Control Conference,
| Denver,CO, | August | 2000. | Paper | no. AIAA-2000-4370. |     |     |
| ---------- | ------ | ----- | ----- | ------------------- | --- | --- |
41. S. Chatterjee and E. Seneta. Towards consensus: Some convergence theorems
on repeated averaging. Journal of Applied Probability, 14(1):89–97, March
1977.
42. C.-T.Chen. Linear System Theory and Design. OxfordUniversityPress,New
| York,3rd | edition, | 1999. |     |     |     |     |
| -------- | -------- | ----- | --- | --- | --- | --- |
43. P.Chen,Z.Song,Z.Wang,andY.Chen.Patternformationexperimentsinmo-
bile actuator and sensor network (Mas-net). In Proceedings of the IEEE/RSJ
International Conference on Intelligent Robots and Systems, pages3658–3663,
| Edmonton, | Alberta, | Can, | August | 2005. |     |     |
| --------- | -------- | ---- | ------ | ----- | --- | --- |
44. Q.ChenandJ.Y.S.Luh. Coordinationandcontrolofagroupofsmallmobile
robots. In Proceedings of the IEEE International Conference on Robotics and
| Automation, | pages | 2315–2320, |     | San Diego, | 1994. |     |
| ----------- | ----- | ---------- | --- | ---------- | ----- | --- |

302 References
45. D.F.ChichkaandJ. L.Speyer. Solar-powered, formation-enhanced aerial ve-
hiclesystemsforsustainedendurance. InProceedings ofthe American Control
Conference, pages 684–688, Philadelphia, PA,June 1998.
46. N.Chopra andM.W.Spong. Onsynchronization ofKuramotooscillators. In
ProceedingsoftheIEEEConferenceonDecisionandControl,andtheEuropean
Control Conference, pages 3916–3922, Seville, Spain, December 2005.
47. J. Cortes. Analysis and design of distributed algorithms for chi-consensus. In
ProceedingsoftheIEEEConferenceonDecisionandControl,pages3363–3368,
San Diego, 2006.
48. J. Cortes. Finite-time convergent gradient flows with applications to network
consensus. Automatica, 42(11):1993–2000, November2006.
49. J. Cort´es, S.Mart´ınez, T. Karatas, and F. Bullo. Coverage control for mobile
sensing networks. IEEE Transactions on Robotics and Automation, 20:243–
255, 2004.
50. F. Cucker and S. Smale. Emergent behavior in flocks. IEEE Transactions on
Automatic Control, 52(5):852–862, 2007.
51. A.K.Das,R.Fierro,V.Kumar,J.P.Ostrowski,J.Spletzer,andC.J.Taylor.
A vision-based formation control framework. IEEE Transactions on Robotics
and Automation, 18(5):813–825, October 2002.
52. G.A.deCastroandF.Paganini. Convexsynthesisofcontrollersforconsensus.
InProceedings of the American Control Conference, pages4933–4938, Boston,
MA, 2004.
53. M.S.deQueiroz,V.Kapila,andQ.Yan.Adaptivenonlinearcontrolofmultiple
spacecraft formation flying. Journal of Guidance, Control, and Dynamics,
23(3):385–390, May–June 2000.
54. C. C. de Wit and O. Sordalen. Exponential stabilization of mobile robots
with nonholonomic constraints. IEEE Transactions on Automatic Control,
37(11):1791–1797, November1992.
55. M. H.DeGroot. Reaching a consensus. Journal of American Statistical Asso-
ciation, 69(345):118–121, 1974.
56. J. P. Desai, J. Ostrowski, and V. Kumar. Controlling formations of multi-
ple mobile robots. In Proceedings of the IEEE International Conference on
Robotics and Automation, pages 2864–2869, Leuven,Belgium, May 1998.
57. W. C. Dickson, R. H. Cannon, and S. M. Rock. Symbolic dynamic modeling
and analysis of object/robot-team systems with experiments. In Proceedings
of the IEEE Conference on Robotics and Automation, pages 1413–1420, Min-
neapolis, April 1996.
58. D. V. Dimarogonas and K. J. Kyriakopoulos. On the rendezvous problem
for multiple nonholonomic agents. IEEE Transactions on Automatic Control,
52(5):916–922, 2007.
59. D.V.Dimarogonas,S.G.Loizou,K.J.Kyriakopoulos,andM.M.Zavlanos. A
feedbackstabilizationandcollision avoidanceschemeformultipleindependent
non-point agents. Automatica, 42(2):229–243, 2006.
60. D. V. Dimarogonas, P. Tsiotras, and K. J. Kyriakopoulos. Laplacian cooper-
ative attitudecontrol of multiple rigid bodies. In Proceedings of the IEEE In-
ternational Symposium on Intelligent Control, pages3064–3069, Munich,Ger-
many,October 2006.
61. K.D.Do.Boundedcontrollersforformationstabilizationofmobileagentswith
limited sensing ranges. IEEE Transactions on Automatic Control, 52(3):569–
576, March 2007.

References 303
62. M.Egerstedt,X.Hu,andA.Stotsky. Controlofmobileplatformsusingavir-
tualvehicleapproach. IEEETransactions onAutomaticControl,46(11):1777–
1782, November2001.
63. R.Emery,K.Sikorski,andT.Balch. Protocolsforcollaboration, coordination
and dynamicrole assignment in arobot team. InProceedings of the IEEE In-
ternational Conference on Robotics and Automation, pages 3008–3015, Wash-
ington DC, May 2002.
64. T.Eren,P.N.Belhumeur,andA.S.Morse. Closingranksinvehicleformations
based on rigidity. In Proceedings of the IEEE Conference on Decision and
Control, pages 2959–2964, Las Vegas, NV,December2002.
65. F. Fahimi. Sliding-mode formation control for underactuated surface vessels.
IEEE Transactions on Robotics, 23(3):617–622, 2007.
66. N.Faiz,S.K.Agrawal,andR.M.Murray.Trajectoryplanningofdifferentially
flatsystemswithdynamicsandinequalities. JournalofGuidance,Control,and
Dynamics, 24(2):219–227, March–April 2001.
67. L. Fang and P. J. Antsaklis. Information consensus of asynchronous discrete-
timemulti-agentsystems. InProceedings of theAmericanControl Conference,
pages 1883–1888, Portland, OR, June2005.
68. L. Fang and P. J. Antsaklis. On communication requirements for muli-agent
consensusseeking. InP.AntsaklisandP.Tabuada,editors,Networked Embed-
ded Sensing and Control, volume 331 of Lecture Notes in Control and Infor-
mation Sciences, pages 53–68, Berlin, 2006. Springer.
69. J. A. Fax and R. M. Murray. Information flow and cooperative control of
vehicle formations. IEEE Transactions on Automatic Control, 49(9):1465–
1476, September2004.
70. J. T. Feddema, C. Lewis, and D. A. Schoenwald. Decentralized control of
cooperative robotic vehicles: Theory and application. IEEE Transactions on
Robotics and Automation, 18(5):852–864, 2002.
71. G. Ferrari-Trecate, A. Buffa, and M. Gati. Analysis of coordination in multi-
agent systems through partial difference equations. IEEE Transactions on
Automatic Control, 51(6):1058–1063, September2006.
72. R. Fierro, A. K. Das, V. Kumar, and J. P. Ostrowski. Hybrid control of
formations of robots. InProceedings of the IEEE International Conference on
Robotics and Automation, pages 157–162, Seoul, Korea, May 2001.
73. D. Folta, F. Bordi, and C. Scolese. Considerations on formation flying sepa-
rations for earth observing satellite missions. Advances in the Astronautical
Sciences, 79(2):803–822, 1992.
74. D. Folta and D. Quinn. A universal 3-D method for controlling the relative
motion of multiple spacecraft in any orbit. In Proceedings of the AIAA Guid-
ance, Navigation, and Control Conference, Boston, MA, August 1998. Paper
no. AIAA-98-4193.
75. E. Frazzoli, M. A. Dahleh, and E. Feron. Real-time motion planning for agile
autonomousvehicles. JournalofGuidance,Control,andDynamics,25(1):116–
129, January–February 2002.
76. R. A. Freeman, P. Yang, and K. M. Lynch. Distributed estimation and con-
trol of swarm formation statistics. In Proceedings of the American Control
Conference, pages 749–755, Minneapolis, June 2006.
77. J. Fujiwara, K.; Kudoh. Forest fire detection in 2001 using three-dimensional
histogram. In Proceedings of the IEEE International Geoscience and Remote
Sensing Symposium, volume4, pages 2057 – 2059, Toronto, Can, June2002.

304 References
78. L. Gao and D. Cheng. Comments on coordination of groups of mobile
agentsusingnearestneighborrules. IEEETransactionsonAutomaticControl,
50(11):1913–1916, November2005.
79. R. Gardner, W. Hargrove, M. Turner, and W. Romme. Climate change, dis-
turbances, andlandscapedynamics,pages149–172. GlobalChangeandTerres-
trial Ecosystems. International Geosphere-Biosphere Programme Book Series
- Book #2. Cambridge UniversityPress, Cambridge, UK,1996.
80. V. Gazi and K. M. Passino. Stability analysis of swarms. IEEE Transactions
on Automatic Control, 48(4):692–697, 2003.
81. G. L. Gilardoni and M. K. Clayton. On reaching a consensus using degroot’s
iterative pooling. The Annals of Statistics, 21(1):391–401, 1993.
82. F.Giulietti,L.Pollini, andM.Innocenti. Autonomousformation flight. IEEE
Control Systems Magazine, 20(6):34–44, December 2000.
83. R. E. Glickman. TIDE: The timed-destination approach to constellation for-
mation keeping. Advances in the Astronautical Sciences, 87(2):725–743, 1994.
84. A.Graham. Kronecker Products and Matrix Calculus WithApplications. Hal-
sted, New York,1981.
85. F.Y.Hadaegh,W.-M. Lu,and P.K.C.Wang. Adaptivecontrolof formation
flyingspacecraftforinterferometry. InProceedings of the IFAC Symposium on
Large Scale Systems: Theory and Applications, pages 97–102, Patras, Greece,
1998.
86. W.Hargrove,R.Gardner,M.Turner,W.Romme,andD.Despain. Simulating
fire patterns in heterogeneous landscapes. Ecological Modelling, 135:243–263,
2000.
87. Y. Hatano, A. K. Das, and M. Mesbahi. Agreement in presence of noise:
Pseudogradients on random geometric networks. In Proceedings of the IEEE
Conference on Decision and Control, and the European Control Conference,
pages 6382–6387, Seville, Spain,December 2005.
88. Y. Hatano and M. Mesbahi. Agreement over random networks. IEEE Trans-
actions on Automatic Control, 50(11):1867–1872, November2005.
89. Y.Hong,L.Gao,D.Cheng,andJ.Hu.Lyapunov-basedapproachtomultiagent
systems with switching jointly connected interconnection. IEEE Transactions
on Automatic Control, 52(5):943–948, May 2007.
90. Y.Hong,J.Hu,andL.Gao.Trackingcontrolformulti-agentconsensuswithan
active leader and variable topology. Automatica, 42(7):1177–1182, July 2006.
91. R.A.HornandC.R.Johnson. Matrix Analysis. CambridgeUniversityPress,
Cambridge, UK,1985.
92. J. K. Howlett. Path planning for sensing multiple targets from an aircraft.
Master’s thesis, Mechanical Engineering, Brigham Young University, Provo,
UT, 2002.
93. P. C. Hughes. Spacecraft Attitude Dynamics. Wiley, New York,1986.
94. I. I. Hussein. Motion Planning for Multi-Spacecraft Interferometric Imaging
Systems. PhD thesis, Universityof Michigan, AnnArbor, MI, 2005.
95. G. Inalhan, D. M. Stipanovic, and C. J. Tomlin. Decentralized optimization,
with application tomultipleaircraft coordination. InProceedings of the IEEE
ConferenceonDecisionandControl,pages1147–1155,LasVegas,NV,Decem-
ber 2002.
96. A.Isidori. Nonlinear Control Systems. CommunicationandControlEngineer-
ing. Springer-Verlag, New York,2nd edition, 1989.

References 305
97. A. Jadbabaie, J. Lin, and A. S. Morse. Coordination of groups of mobile
autonomousagentsusingnearestneighborrules. IEEE Transactions on Auto-
| matic Control, | 48(6):988–1001, |     | June 2003. |     |
| -------------- | --------------- | --- | ---------- | --- |
98. A.Jadbabaie, N. Motee, and M. Barahona. On thestability of theKuramoto
modelofcouplednonlinearoscillators. InProceedings oftheAmericanControl
| Conference, | pages | 4296–4301, | Boston, MA, | 2004. |
| ----------- | ----- | ---------- | ----------- | ----- |
99. Z. Jin and R. M. Murray. Consensus controllability for coordinated multiple
vehicle control. In The 6th International Conference on Cooperative Control
| and Optimization, |     | Gainesville, | FL, February | 2006. |
| ----------------- | --- | ------------ | ------------ | ----- |
100. E. W. Justh and P. S. Krishnaprasad. Equilibria and steering laws for planar
| formations. | Systems | and | Control Letters, | 52:25–38, 2004. |
| ----------- | ------- | --- | ---------------- | --------------- |
101. W.Kang,N.Xi,andA.Sparks.Formationcontrolofautonomousagentsin3D
workspace. In Proceedings of the IEEE International Conference on Robotics
and Automation, pages 1755–1760, San Francisco, CA, April2000.
102. W. Kang and H.-H. Yeh. Co-ordinated attitude control of multi-satellite sys-
tems. International Journal of Robust and Nonlinear Control, 12:185–205,
2002.
103. V. Kapila, A. G. Sparks, J. M. Buffington, and Q. Yan. Spacecraft formation
flying: Dynamics and control. Journal of Guidance, Control, and Dynamics,
| 23(3):561–564, | May-June2000. |     |     |     |
| -------------- | ------------- | --- | --- | --- |
104. A. Kashyap, T. Basar, and R. Srikant. Quantized consensus. Automatica,
| 43:1192–1203, | 2007. |     |     |     |
| ------------- | ----- | --- | --- | --- |
105. H. K. Khalil. Nonlinear Systems. Prentice Hall, Upper Saddle River, NJ, 3rd
edition, 2002.
106. Y. Kim and M. Mesbahi. On maximizing the second smallest eigenvalue of a
state-dependent graph Laplacian. IEEE Transactions on Automatic Control,
| 51(1):116–120, | 2006. |     |     |     |
| -------------- | ----- | --- | --- | --- |
107. E. King, Y. Kuwata, M. Alighangari, L. Bertucelli, and J. How. Coordina-
tion and control experimentson a multi-vehicletestbed. In Proceedings of the
American Control Conference, pages 5315–5320, Boston, MA, July 2004.
108. D. Kingston, R. Beard, T. McLain, M. Larsen, and W. Ren. Autonomous
vehicle technologies for small fixed wing UAVs. In Proceedings of the AIAA
2nd Unmanned Unlimited Systems, Technologies, and Operations–Aerospace,
Land,andSeaConference,SanDiego,September2003. Paperno.AIAA-2003-
6559.
109. D.B. Kingston, R.S.Holt,R.W.Beard, T. W. McLain, and D.W.Casbeer.
Decentralized perimeter surveillance using a team of UAVs. In Proceedings
of the AIAA Guidance, Navigation, and Control Conference, San Francisco,
| August | 2005. Paper | no. AIAA-2005-5831. |     |     |
| ------ | ----------- | ------------------- | --- | --- |
110. D. B. Kingston, W. Ren, and R. W. Beard. Consensus algorithms are input-
to-state stable. In Proceedings of the American Control Conference, pages
| 1686–1690, | Portland, | OR,June | 2005. |     |
| ---------- | --------- | ------- | ----- | --- |
111. C. R. Kube and H. Zhang. The use of perceptual cues in multi-robot box-
pushing. InProceedings oftheIEEEInternational Conference onRoboticsand
| Automation, | pages | 2085–2090, | Minneapolis, | April1996. |
| ----------- | ----- | ---------- | ------------ | ---------- |
112. J.-I. Kudoh and K. Hosoi. Two dimensional forest fire detection method
by using NOAA AVHRR images. In Proceedings of the IEEE International
Geoscience and Remote Sensing Symposium, volume 4, pages 2494 – 2495,
| Toulouse, | France, | July 2003. |     |     |
| --------- | ------- | ---------- | --- | --- |

306 References
113. D. Kurabayashi, J. Ota, T. Arai, and E. Yoshida. Cooperative sweeping by
multiple mobile robots. In Proceedings of the IEEE International Conference
on Robotics and Automation, pages 1744–1749, Minneapolis, April1996.
114. Y.Kuramoto. ChemicalOscillations,WavesandTurbulence. Springer,Berlin,
1984.
115. G.Lafferriere,A.Williams,J.Caughman,andJ.J.P.Veerman. Decentralized
control of vehicle formations. Systems and Control Letters, 54(9):899–910,
2005.
116. J. R. Lawton and R. W. Beard. A projection approach to spacecraft forma-
tion attitudecontrol. In 23rd Annual AAS Guidance and Control Conference,
| Breckenridge, | CO, February2000. | Paper | no. AAS | 00-011. |
| ------------- | ----------------- | ----- | ------- | ------- |
117. J. R. Lawton and R. W. Beard. Synchronized multiple spacecraft rotations.
| Automatica, | 38(8):1359–1364, | 2002. |     |     |
| ----------- | ---------------- | ----- | --- | --- |
118. J.R.Lawton,R.W.Beard,andB.Young. Adecentralizedapproachtoforma-
tion maneuvers. IEEE Transactions on Robotics and Automation, 19(6):933–
| 941, December | 2003. |     |     |     |
| ------------- | ----- | --- | --- | --- |
119. D.LeeandM.W.Spong. Agreementwithnon-uniforminformationdelays. In
Proceedings of the American Control Conference,pages756–761, Minneapolis,
| June 2006. |     |     |     |     |
| ---------- | --- | --- | --- | --- |
120. D.LeeandM.W.Spong.Stableflockingofmultipleinertialagentsonbalanced
graphs. IEEE Transactions on Automatic Control, 52(8):1469–1475, August
2007.
121. N.E.LeonardandE.Fiorelli. Virtualleaders, artificialpotentialsandcoordi-
nated control of groups. In Proceedings of the IEEE Conference on Decision
| and Control,      | pages 2968–2973, | Orlando, | FL, December   | 2001. |
| ----------------- | ---------------- | -------- | -------------- | ----- |
| 122. F. L. Lewis. | Optimal Control. | Wiley,   | New York,1986. |       |
123. M.A.LewisandK.-H.Tan. Highprecisionformation controlofmobilerobots
using virtual structures. Autonomous Robots, 4:387–403, 1997.
124. J. Lin, A. S. Morse, and B. D. O. Anderson. The multi-agent rendezvous
problem. In Proceedings of the IEEE Conference on Decision and Control,
| pages 1508–1513, | Maui, HI,2003. |     |     |     |
| ---------------- | -------------- | --- | --- | --- |
125. J. Lin, A. S. Morse, and B. D. O. Anderson. The multi-agent rendezvous
problem - the asynchronous case. In Proceedings of the IEEE Conference on
Decision and Control, pages 1926–1931, Paradise Island, Bahamas, December
2004.
126. Z.Lin,M.Broucke,andB.Francis.Localcontrolstrategiesforgroupsofmobile
autonomousagents. IEEETransactions onAutomatic Control,49(4):622–629,
| April 2004. |     |     |     |     |
| ----------- | --- | --- | --- | --- |
127. Z. Lin, B. Francis, and M. Maggiore. Necessary and sufficient graphical con-
ditions for formation control of unicycles. IEEE Transactions on Automatic
| Control, | 50(1):121–127, 2005. |     |     |     |
| -------- | -------------------- | --- | --- | --- |
128. Z. Lin, B. Francis, and M. Maggiore. State agreement for continuous-time
coupled nonlinear systems. SIAM Journal on Control and Optimization,
| 46(1):288–307, | 2007. |     |     |     |
| -------------- | ----- | --- | --- | --- |
129. F. Lizarralde and J. Wen. Attitude control without angular velocity mea-
surement: A passivity approach. IEEE Transactions on Automatic Control,
| 41(3):468–472, | March 1996. |     |     |     |
| -------------- | ----------- | --- | --- | --- |
130. A. Loria, R. Kelly, R. Ortega, and V. Santibanez. On global output feedback
regulationofEuler-Lagrangesystemswithboundedinputs.IEEETransactions
| on Automatic | Control, 42(8):1138–1143, |     | August | 1997. |
| ------------ | ------------------------- | --- | ------ | ----- |

References 307
131. N.A.Lynch. Distributed Algorithms. MorganKaufmann,SanFrancisco,1996.
132. H.J.Marquez. NonlinearControlSystems:AnalysisandDesign. Wiley,Hobo-
ken,NJ, 2003.
133. J. A. Marshall, M. E. Broucke, and B. A. Francis. Formations of vehicles in
cyclic pursuit. IEEE Transactions on Automatic Control, 49(11):1963–1974,
2004.
134. J. A. Marshall, T. Fung, M. E. Broucke, G. M. T. D’Eleuterio, and B. A.
Francis. Experiments in multirobot coordination. Robotics and Autonomous
| Systems, | 54(3):265–275, | 2006. |     |
| -------- | -------------- | ----- | --- |
135. S. Martinez, J. Cortes, and F. Bullo. On robust rendezvous for mobile au-
tonomous agents. In IFAC World Congress, Prague, Czech Republic, 2005.
| Paper code | We-A18-TO/3. |     |     |
| ---------- | ------------ | --- | --- |
136. C.R.McInnes. Autonomousringformation foraplanarconstellation ofsatel-
lites. Journal of Guidance, Control, and Dynamics, 18(5):1215–1217, 1995.
137. T.W.McLainandR.W.Beard.Cooperativerendezvousofmultipleunmanned
air vehicles. In Proceedings of the AIAA Guidance, Navigation, and Control
Conference, Denver,CO, August 2000. Paper no. AIAA-2000-4369.
138. T. W. McLain and R. W. Beard. Coordination variables, coordination func-
tions,andcooperativetimingmissions. InProceedingsoftheAmericanControl
| Conference, | pages 296–301, | Denver,CO, | June2003. |
| ----------- | -------------- | ---------- | --------- |
139. T. W. McLain and R. W. Beard. Coordination variables, coordination func-
tions, and cooperative timing missions. Journal of Guidance, Control, and
| Dynamics, | 28(1):150–161, | January 2005. |     |
| --------- | -------------- | ------------- | --- |
140. M. Mehyar, D. Spanos, J. Pongsajapan, S. H. Low, and R. M. Murray. Dis-
tributed averaging on asynchronous communication networks. In Proceedings
of the IEEE Conference on Decision and Control, and the European Control
| Conference, | pages 7446–7451, | Seville, | Spain, December2005. |
| ----------- | ---------------- | -------- | -------------------- |
141. R. Merris. Laplacian matrices of graphs: A survey. Linear Algebra and its
| Applications, | 197-198:143–176, | 1994. |     |
| ------------- | ---------------- | ----- | --- |
142. M.MesbahiandF.Y.Hadaegh.Formationflyingcontrolofmultiplespacecraft
via graphs, matrix inequalities, and switching. Journal of Guidance, Control,
| and Dynamics, | 24(2):369–377, | March–April | 2000. |
| ------------- | -------------- | ----------- | ----- |
143. K. Moore and D. Lucarelli. Decentralized adaptive scheduling using consen-
sus variables. International Journal of Robust and Nonlinear Control, 17(10–
| 11):921–940, | July 2007. |     |     |
| ------------ | ---------- | --- | --- |
144. L. Moreau. Stability of continuous-time distributed consensus algorithms. In
ProceedingsoftheIEEEConferenceonDecisionandControl,pages3998–4003,
| Paradise | Island, Bahamas, | December2004. |     |
| -------- | ---------------- | ------------- | --- |
145. L.Moreau. Stabilityof multi-agentsystemswithtime-dependentcommunica-
tionlinks. IEEE Transactions on Automatic Control,50(2):169–182, February
2005.
146. A.S.Morse. Supervisorycontroloffamilies oflinearset-pointcontrollers-part
1: Exact matching. IEEE Transactions on Automatic Control, 41(10):1413–
1431, 1996.
147. N.Moshtagh andA.Jadbabaie. Distributed geodesic control laws forflocking
ofnonholonomicagents. IEEETransactions onAutomaticControl,52(4):681–
| 686, April | 2007. |     |     |
| ---------- | ----- | --- | --- |
148. D. R. Nelson. Cooperative control of miniature air vehicles. Master’s thesis,
| Brigham | YoungUniversity,Provo, | UT, | December2005. |
| ------- | ---------------------- | --- | ------------- |

308 References
149. D. R. Nelson, D. B. Barber, T. W. McLain, and R. W. Beard. Vector field
pathfollowingforsmallunmannedairvehicles. InProceedingsoftheAmerican
Control Conference, pages 5788–5794, Minneapolis, June2006.
150. D. R. Nelson, T. W. McLain, R. S. Christiansen, R. W. Beard, and D. Jo-
hansen. Initial experiements in cooperative control of unmanned air vehicles.
In Proceedings of the AIAA 3rd Unmanned Unlimited Systems Conference,
Chicago, IL,2004. Paper no.AIAA-2004-6533.
151. P. Ogren, M. Egerstedt, and X. Hu. A control Lyapunov function approach
to multiagent coordination. IEEE Transactions on Robotics and Automation,
18(5):847–851, October 2002.
152. P. Ogren, E. Fiorelli, and N. E. Leonard. Formations with a mission: Stable
coordination of vehicle group maneuvers. In Proceedings of the 15th Interna-
tional Symposium on Mathematical Theory of Networks and Systems, Notre
Dame, IN,2002.
153. P.Ogren,E.Fiorelli,andN.E.Leonard. Cooperativecontrolofmobilesensor
networks: Adaptive gradient climbing in a distributed environment. IEEE
Transactions on Automatic Control, 49(8):1292–1302, August 2004.
154. R.Olfati-Saber. DistributedKalmanfilterwithembeddedconsensusfilters. In
ProceedingsoftheIEEEConferenceonDecisionandControl,andtheEuropean
Control Conference, pages 8179–8184, Seville, Spain, December 2005.
155. R. Olfati-Saber. Flocking for multi-agent dynamic systems: Algorithms and
theory. IEEETransactions onAutomaticControl,51(3):401–420, March2006.
156. R. Olfati-Saber, J. A. Fax, and R. M. Murray. Consensus and cooperation
in networked multi-agent systems. Proceedings of the IEEE, 95(1):215–233,
January 2007.
157. R. Olfati-Saber and R. M. Murray. Distributed cooperative control of mul-
tiple vehicle formations using structural potential functions. In IFAC World
Congress, Barcelona, Spain,July 2002.
158. R.Olfati-Saberand R.M. Murray. Consensusproblems innetworksof agents
with switching topology and time-delays. IEEE Transactions on Automatic
Control, 49(9):1520–1533, September2004.
159. R. Olfati-Saber and J. S. Shamma. Consensus filters for sensor networks and
distributed sensor fusion. In Proceedings of the IEEE Conference on Decision
and Control, and the European Control Conference, pages 6698–6703, Seville,
Spain, December2005.
160. R.Ortega,A.Loria,R.Kelly,andL.Praly.Onpassivity-basedoutputfeedback
globalstabilizationofEuler-Lagrangesystems.InternationalJournalofRobust
and Nonlinear Control, 5:313–323, 1995.
161. M. Pachter, J. J. D’Azzo, and A. W. Proud. Tight formation flight con-
trol.JournalofGuidance,Control,andDynamics,24(2):246–254,March–April
2001.
162. A. Papachristodoulou and A. Jadbabaie. Synchronization in oscillator net-
works: Switching topologies and non-homogeneous delays. In Proceedings of
theIEEEConferenceonDecisionandControl,andtheEuropeanControlCon-
ference, pages 5692–5697, Seville, Spain,December 2005.
163. S.T.Pledgie,Y.Hao,A.M.Ferreira,S.K.Agrawal,andR.Murphey. Groups
of unmanned vehicles: Differential flatness, trajectory planning, and control.
InProceedingsoftheIEEEInternationalConferenceonRoboticsandAutoma-
tion, pages 3461–3466, Washington DC, May 2002.

References 309
164. J.P.Pomet. Explicitdesignoftime-varyingstabilizingcontrollawsforaclass
ofcontrollablesystemswithoutdrift. SystemsandControlLetters,18:147–158,
1992.
165. M.Porfiri,D.G.Roberson,andD.J.Stilwell. Trackingandformation control
of multiple autonomous agents: A two-level consensus approach. Automatica,
| 43(8):1318–1328, |     | 2007. |     |     |
| ---------------- | --- | ----- | --- | --- |
166. V. M. Preciado and G. C. Verghese. Synchronization in generalized Erdos-
Renyinetworksofnonlinearoscillators. InProceedings oftheIEEEConference
on Decision and Control, and the European Control Conference, pages 4628–
| 4633, Seville, | Spain, | December2005. |     |     |
| -------------- | ------ | ------------- | --- | --- |
167. A.W.Proud,M.Pachter,andJ.J.D’Azzo. Closeformation flightcontrol. In
ProceedingsoftheAIAAGuidance,Navigation,andControlConference,pages
| 1231–1246, | Portland, | OR,August | 1999. Paper | no. AIAA-99-4207. |
| ---------- | --------- | --------- | ----------- | ----------------- |
168. Z. Qu, J. Wang, and R. A. Hull. Products of row stochastic matrices and
their applications to cooperative control for autonomous mobile robots. In
Proceedings of the American Control Conference, pages 1066–1071, Portland,
| OR,June | 2005. |     |     |     |
| ------- | ----- | --- | --- | --- |
169. A.Regmi,R.Sandoval,R.Byrne,H.Tanner,andC. Abdallah. Experimental
implementationofflockingalgorithmsinwheeledmobilerobots.InProceedings
of the American Control Conference, pages 4917–4922, Portland, OR,2005.
170. W. Ren. Consensus based formation control strategies for multi-vehicle sys-
tems. In Proceedings of the American Control Conference, pages 4237–4242,
| Minneapolis, | June2006. |     |     |     |
| ------------ | --------- | --- | --- | --- |
171. W.Ren. Cooperative controldesignstrategies with local interactions. InPro-
ceedings of IEEE Conference on Networking, Sensing, and Control, Ft. Laud-
| erdale, FL, | April2006. |     |     |     |
| ----------- | ---------- | --- | --- | --- |
172. W.Ren. Distributedattitudeconsensusamongmultiplenetworkedspacecraft.
In Proceedings of the American Control Conference, pages 1760–1765, Min-
| neapolis, | June 2006. |     |     |     |
| --------- | ---------- | --- | --- | --- |
173. W.Ren. Consensusseekinginmulti-vehiclesystemswithatime-varyingrefer-
encestate. InProceedings oftheAmericanControlConference,pages717–722,
| New York,July | 2007. |     |     |     |
| ------------- | ----- | --- | --- | --- |
174. W. Ren. Consensus strategies for cooperative control of vehicle formations.
| IET Control | Theory | & Applications, | 1(2):505–512, | March 2007. |
| ----------- | ------ | --------------- | ------------- | ----------- |
175. W.Ren. Consensustrackingunderdirectedinteractiontopologies:Algorithms
and experiments. IEEE Transactions on Control Systems Technology, 2007.
(in review).
176. W. Ren. Distributed attitudealignment in spacecraft formation flying. Inter-
national Journal of Adaptive Control and Signal Processing, 21(2–3):95–113,
| March–April | 2007. |     |     |     |
| ----------- | ----- | --- | --- | --- |
177. W. Ren. Distributed attitude synchronization for multiple rigid bodies with
Euler-Lagrange equations of motion. In Proceedings of the IEEE Conference
on Decision and Control, New Orleans, December2007. (to appear).
178. W. Ren. Distributed cooperative attitude synchronization and tracking for
multiplerigidbodies.IEEETransactionsonControlSystemsTechnology,2007.
(in review).
179. W. Ren. Formation keeping and attitude alignment for multiple spacecraft
through local interactions. Journal of Guidance, Control, and Dynamics,
| 30(2):633–638, | March–April | 2007. |     |     |
| -------------- | ----------- | ----- | --- | --- |

310 References
180. W.Ren. Multi-vehicleconsensuswithatime-varyingreference state. Systems
| and Control | Letters, | 56(7–8):474–483, |     | July 2007. |
| ----------- | -------- | ---------------- | --- | ---------- |
181. W.Ren.Onconsensusalgorithmsfordouble-integratordynamics.IEEETrans-
| actions | on Automatic | Control, | 2007. | (in review). |
| ------- | ------------ | -------- | ----- | ------------ |
182. W.Ren. Onconsensusalgorithmsfordouble-integratordynamics. InProceed-
ingsoftheIEEEConferenceonDecisionandControl,NewOrleans,December
2007. (to appear).
183. W.Ren.Second-orderconsensusalgorithmwithextensionstoswitchingtopolo-
giesandreferencemodels. InProceedings oftheAmericanControl Conference,
| pages 1431–1436, |     | New York,July |     | 2007. |
| ---------------- | --- | ------------- | --- | ----- |
184. W.Ren. Synchronizedmultiplespacecraftrotations:Arevisitinthecontextof
consensusbuilding. InProceedings of the American Control Conference, pages
| 3174–3179, | NewYork,July |     | 2007. |     |
| ---------- | ------------ | --- | ----- | --- |
185. W. Ren and E. M. Atkins. Second-order consensus protocols in multiple ve-
hicle systems with local interactions. In Proceedings of the AIAA Guidance,
Navigation, and Control Conference, San Francisco, August 2005. Paper no.
AIAA-2005-6238.
186. W. Ren and E. M. Atkins. Distributed multi-vehicle coordinated control via
local information exchange. International Journal of Robust and Nonlinear
| Control, | 17(10–11):1002–1033, |     | July | 2007. |
| -------- | -------------------- | --- | ---- | ----- |
187. W.RenandR.W.Beard. Consensusofinformationunderdynamicallychang-
inginteractiontopologies. InProceedings oftheAmericanControl Conference,
| pages 4939–4944, |     | Boston, MA, | June2004. |     |
| ---------------- | --- | ----------- | --------- | --- |
188. W. Ren and R. W. Beard. Decentralized scheme for spacecraft formation
flying via the virtual structure approach. Journal of Guidance, Control, and
| Dynamics, | 27(1):73–82, | January–February |     | 2004. |
| --------- | ------------ | ---------------- | --- | ----- |
189. W.Ren and R.W.Beard. Formation feedback control for multiplespacecraft
via virtual structures. IEE Proceedings - Control Theory and Applications,
| 151(3):357–368, | May | 2004. |     |     |
| --------------- | --- | ----- | --- | --- |
190. W. Ren and R. W. Beard. Consensus seeking in multiagent systems under
dynamicallychanginginteractiontopologies. IEEETransactionsonAutomatic
| Control, | 50(5):655–661, | May | 2005. |     |
| -------- | -------------- | --- | ----- | --- |
191. W.Ren,R.W.Beard,andE.M.Atkins.Informationconsensusinmultivehicle
cooperativecontrol:Collectivegroupbehaviorthroughlocalinteraction. IEEE
| Control | Systems Magzine, |     | 27(2):71–82, | April 2007. |
| ------- | ---------------- | --- | ------------ | ----------- |
192. W. Ren, R. W. Beard, and D. B. Kingston. Multi-agent Kalman consensus
with relativeuncertainty. InProceedings of the American Control Conference,
| pages 1865–1870, |     | Portland, | OR, June2005. |     |
| ---------------- | --- | --------- | ------------- | --- |
193. W.Ren,R.W.Beard,andT.W.McLain. Coordinationvariablesandconsen-
susbuildinginmultiplevehiclesystems.InV.Kumar,N.E.Leonard,andA.S.
Morse, editors, Cooperative Control, volume 309 of Lecture Notes in Control
and Information Sciences, pages 171–188, Berlin, 2005. Springer-Verlag.
194. W. Ren, H. Chao, W. Bourgeous, N. Sorensen, and Y. Chen. Experimental
implementation and validation of consensus algorithms on a mobile actuator
and sensor network platform. In Proceedings of the IEEE International Con-
ference on Systems, Man, and Cybernetics, Montreal, Can, October 2007. (to
appear).
195. W. Ren, H. Chao, W. Bourgeous, N. Sorensen, and Y. Chen. Experimental
validationofconsensusalgorithmsformulti-vehiclecooperativecontrol. IEEE
Transactions on Control Systems Technology, 2007. (toappear).

References 311
196. W.Ren,K.L.Moore,andY.Chen. High-orderandmodelreferenceconsensus
algorithmsincooperativecontrolofmulti-vehiclesystems. JournalofDynamic
Systems, Measurement, and Control, 129(5):678–688, September2007.
197. W.RenandN.Sorensen.Distributedcoordinationarchitectureformulti-robot
formation control. Robotics and Autonomous Systems, 2007. (to appear).
198. C. W. Reynolds. Flocks, herds, and schools: A distributed behavioral model.
Computer Graphics, 21:25–34, 1987.
199. A.Richards, J. Bellingham, M. Tillerson, and J. How. Coordination and con-
trol of UAVs. In Proceedings of the AIAA Guidance, Navigation, and Control
Conference, Monterey,CA, August 2002. Paper no. AIAA-2002-4588.
200. A. Robertson, G. Inalhan, and J. P. How. Formation control strategies for a
separated spacecraft interferometer. In Proceedings of the American Control
Conference, pages 4142–4147, San Diego, June1999.
201. A. Rodriguez-Angeles and H. Nijmeijer. Mutual synchronization of robots
via estimated state feedback: A cooperative approach. IEEE Transactions on
Control Systems Technology, 9(4):380–386, 2004.
202. S. Roy, A. Saberi, and K. Herlugson. A control-theoretic perspective on the
designofdistributedagreementprotocols. InternationalJournalofRobustand
Nonlinear Control, 17(10–11):1002–1033, July 2007.
203. S. Roy,A. Saberi, and K. Herlugson. Formation and alignment of distributed
sensing agents with double-integrator dynamics and actuator saturation. In
S. Phoha, T. LaPorta, and C. Griffin, editors, Sensor Network Applications,
Piscataway, NJ, 2007. IEEE Press.
204. G.Royleand C.Godsil. Algebraic Graph Theory. SpringerGraduateTextsin
Mathematics #207, New York,2001.
205. W. J. Rugh. Linear System Theory. Prentice Hall, Englewood Cliffs, NJ, 2nd
edition, 1996.
206. C.Samson. Time-varyingfeedbackstabilization ofcar-likewheeled mobilero-
bots. International Journal of Robotics Research, 12(1):55–64, February1993.
207. S.Sastry,G.Meyer,C.Tomlin,J.Lygeros,D.Godbole,andG.Pappas.Hybrid
control in air traffic management systems. In Proceedings of the IEEE Con-
ference on Decision and Control, pages 1478–1483, New Orleans, December
1995.
208. A. V. Savkin. Coordinated collective motion of groups of autonomous mobile
robots:AnalysisofVicsek’smodel. IEEE Transactions on Automatic Control,
49(6):981–983, 2004.
209. C.Schumacher,P.R.Chandler,andS.J.Rasmussen. Taskallocation forwide
area search munitions via network flow optimization. In Proceedings of the
AIAA Guidance, Navigation, and Control Conference, Montreal, Can, 2001.
210. C. Schumacherand S. N. Singh. Nonlinear control of multiple UAVs in close-
coupled formation flight. In Proceedings of the AIAA Guidance, Navigation,
and Control Conference, Denver, CO, August 2000. Paper no. AIAA-2000-
4373.
211. C.Scolese,D.Folta,andF.Bordi. Field ofviewlocation andformation flying
forpolarorbitingmissions. Advances inthe Astronautical Sciences,75(2):949–
966, 1991.
212. B. Seanor, G. Campa, Y. Gu, M. Napolitano, L. Rowe, and M. Perhinschi.
Formation flight test results for UAV research aircraft models. In Proceed-
ings of the AIAA 1st Intelligent Systems Technical Conference, Chicago, IL,
September2004. Paper no. AIAA-2004-6251.

312 References
213. R. Sepulchre, D. Paley, and N. Leonard. Stabilization of planar collective
motion: All-to-all communication. IEEE Transactions on Automatic Control,
| 52(5):811–824, | 2007. |     |     |     |
| -------------- | ----- | --- | --- | --- |
214. S.SheikholeslamandC.A.Desoer.Controlofinterconnectednonlineardynam-
icalsystems:Theplatoonproblem. IEEE Transactions onAutomatic Control,
| 37(6):806–810, | June 1992. |     |     |     |
| -------------- | ---------- | --- | --- | --- |
215. D. D. Siljak. Decentralized control of complex systems. Academic, Boston,
1991.
216. A. Sinha and D. Ghose. Generalization of linear cyclic pursuit with appli-
cation to rendezvous of multiple autonomous agents. IEEE Transactions on
| Automatic | Control, 51(11):1819–1824, |     | November2006. |     |
| --------- | -------------------------- | --- | ------------- | --- |
217. J.-J.E.SlotineandM.D.D.Benedetto.Hamiltonianadaptivecontrolofspace-
craft. IEEE Transactions on Automatic Control, 35(7):848–852, July 1990.
218. J.-J. E. Slotine and W. Li. Applied Nonlinear Control. Prentice Hall, Engle-
| wood Cliffs, | NJ, 1991. |     |     |     |
| ------------ | --------- | --- | --- | --- |
219. J.-J.E.SlotineandW.Wang. Astudyofsynchronizationandgroupcoopera-
tion using partial contraction theory. In V. Kumar, N. E. Leonard, and A. S.
Morse, editors, Cooperative Control, volume 309 of Lecture Notes in Control
and Information Sciences, pages 207–228, Berlin, 2005. Springer-Verlag.
220. S. L. Smith, M. E. Broucke, and B. A. Francis. A hierarchical cyclic pursuit
| scheme for | vehicle networks. | Automatica, | 41:1045–1053, | 2005. |
| ---------- | ----------------- | ----------- | ------------- | ----- |
221. S. L. Smith, M. E. Broucke, and B. A. Francis. Curve shortening and the
rendezvous problem for mobile autonomous robots. IEEE Transactions on
| Automatic | Control, 52(6):1154–1159, |     | 2007. |     |
| --------- | ------------------------- | --- | ----- | --- |
222. N. Sorensen and W. Ren. A unified formation control scheme with a single
ormultipleleaders. InProceedings of the American Control Conference, pages
| 5412–5418, | NewYork,July | 2007. |     |     |
| ---------- | ------------ | ----- | --- | --- |
223. D. P. Spanos and R. M. Murray. Distributed sensor fusion using dynamic
consensus. In IFAC World Congress, Prague, Czech Republic, 2005. Paper
code We-E04-TP/3.
224. D. P. Spanos, R. Olfati-Saber, and R. M. Murray. Dynamic consensus on
mobile networks. In IFAC World Congress, Prague, Czech Republic, 2005.
| Paper code | We-A18-TO/1. |     |     |     |
| ---------- | ------------ | --- | --- | --- |
225. D.J.StilwellandB.E.Bishop. Platoonsofunderwatervehicles. IEEEControl
| Systems | Magazine, 20(6):45–52, | December | 2000. |     |
| ------- | ---------------------- | -------- | ----- | --- |
226. D. M. Stipanovic, G. Inalhan, R. Teo, and C. J. Tomlin. Decentralized over-
lapping control of a formation of unmanned aerial vehicles. Automatica,
| 40(8):1285–1296, | 2004. |     |     |     |
| ---------------- | ----- | --- | --- | --- |
227. T. Sugar and V. Kumar. Decentralized control of cooperating mobile manip-
ulators. InProceedings of the IEEE International Conference on Robotics and
| Automation, | pages 2916–2921, | Leuven,Belgium, |     | May 1998. |
| ----------- | ---------------- | --------------- | --- | --------- |
228. J.Tan,N.Xi,W.Sheng,andJ.Xiao.Modelingmultiplerobotsystemsforarea
coverageandcooperation.InProceedingsoftheIEEEInternationalConference
on Robotics and Automation, pages 2568–2573, New Orleans, 2004.
229. H. G. Tanner. On the controllability of nearest neighbor interconnections. In
ProceedingsoftheIEEEConferenceonDecisionandControl,pages2467–2472,
| Paradise | Island, Bahamas, | December2004. |     |     |
| -------- | ---------------- | ------------- | --- | --- |
230. H. G. Tanner and D. K. Christodoulakis. State synchronization in local-
interaction networks is robust with respect to time delays. In Proceedings

References 313
of the IEEE Conference on Decision and Control, and the European Control
| Conference, | pages 4945–4950, | Seville, | Spain, December2005. |     |
| ----------- | ---------------- | -------- | -------------------- | --- |
231. H.G.Tanner,A.Jadbabaie,andG.J.Pappas.Stableflockingofmobileagents,
partii:Dynamictopology. InProceedings ofthe IEEEConference onDecision
| and Control, | pages 2016–2021, | Maui, | HI,December2003. |     |
| ------------ | ---------------- | ----- | ---------------- | --- |
232. H.G.Tanner,A.Jadbabaie,andG.J.Pappas. Flockinginfixedandswitching
networks.IEEETransactionsonAutomaticControl,52(5):863–868,May2007.
233. H.G.Tanner,G.J.Pappas,andV.Kumar. Input-to-statestabilityonforma-
tion graphs. In Proceedings of the IEEE Conference on Decision and Control,
| pages 2439–2444, | Las Vegas, | NV,December2002. |     |     |
| ---------------- | ---------- | ---------------- | --- | --- |
234. H. G. Tanner, G. J. Pappas, and V. Kumar. Leader-to-formation stability.
IEEE Transactions on Robotics and Automation, 20(3):433–455, June2004.
235. P. Tsiotras. Further passivity results for the attitude control problem. IEEE
| Transactions | on Automatic | Control, | 43(11):1597–1600, | 1998. |
| ------------ | ------------ | -------- | ----------------- | ----- |
236. J. N. Tsitsiklis, D. P. Bertsekas, and M. Athans. Distributed asynchronous
deterministicandstochasticgradientoptimization algorithms. IEEETransac-
| tions on | Automatic Control, | 31(9):803–812, | 1986. |     |
| -------- | ------------------ | -------------- | ----- | --- |
237. Y. Ulybyshev. Long-term formation keeping of satellite constellation using
linear-quadratic controller. Journal of Guidance, Control, and Dynamics,
| 21(1):109–115, | January–February |     | 1998. |     |
| -------------- | ---------------- | --- | ----- | --- |
238. J.J.P.Veerman,G.Lafferriere,J.S.Caughman,andA.Williams. Flocksand
formations. Journal of Statistical Physics, 121:901–936, December2005.
239. T. Vicsek, A. Czirok, E. B. Jacob, I. Cohen, and O. Schochet. Novel type of
phase transitions in a system of self-driven particles. Physical Review Letters,
| 75(6):1226–1229, | 1995. |     |     |     |
| ---------------- | ----- | --- | --- | --- |
240. T. Vidal, M. Ghallab, and R. Alami. Incremental mission allocation to a
large team of robots. InProceedings of the IEEE International Conference on
Robotics and Automation, pages 1620–1625, Minneapolis, April1996.
241. M.A.Vincent. DesignoftheTOPSATmission. Advances intheAstronautical
| Sciences, | 85(2):1137–1146, | 1993. |     |     |
| --------- | ---------------- | ----- | --- | --- |
242. P.WangandF.Hadaegh. Minimum-fuelformationreconfigurationofmultiple
free-flying spacecraft. ENG97–187, UCLA,Los Angeles, December 1997.
243. P. K. C. Wang. Navigation strategies for multiple autonomous mobile robots
moving in formation. Journal of Robotic Systems, 8(2):177–195, 1991.
244. P. K. C. Wang and F. Y. Hadaegh. Coordination and control of multiple
microspacecraft moving in formation. Journal of the Astronautical Sciences,
| 44(3):315–355, | 1996. |     |     |     |
| -------------- | ----- | --- | --- | --- |
245. P. K.C. Wang,F. Y. Hadaegh, and K. Lau. Synchronized formation rotation
and attitude control of multiple free-flying spacecraft. Journal of Guidance,
| Control, | and Dynamics, | 22(1):28–35, | January 1999. |     |
| -------- | ------------- | ------------ | ------------- | --- |
246. W. Wang and J.-J. E. Slotine. Contraction analysis of time-delayed commu-
nications and group cooperation. IEEE Transactions on Automatic Control,
| 51(4):712–717, | 2006. |     |     |     |
| -------------- | ----- | --- | --- | --- |
247. W. Wang and J.-J. E. Slotine. A theoretical study of different leader roles in
networks. IEEE Transactions on Automatic Control, 51(7):1156–1161, 2006.
248. S. Wegener. White paper on UAV over-the-horizon disaster management
demonstration projects, Feb 2000. http://geo.arc.nasa.gov/sge/UAVFiRE/
whitepaper.html.
249. J. T.-Y. Wen and K. Kreutz-Delgado. The attitude control problem. IEEE
Transactions on Automatic Control, 36(10):1148–1162, October 1991.

314 References
250. J. R. Wertz, editor. Spacecraft Attitude Determination and Control. Kluwer,
| Norwell, | MA, 1978. |     |     |     |     |     |
| -------- | --------- | --- | --- | --- | --- | --- |
251. B.Wie. SpaceVehicleDynamicsandControl. AIAAEducationSeries,Reston,
VA, 1998.
252. B. Wie, H. Weiss, and A. Apapostathis. Quaternion feedback regulator for
spacecraft eigenaxis rotations. Journal of Guidance, Control, and Dynamics,
| 12(3):375–380, |     | May 1989. |     |     |     |     |
| -------------- | --- | --------- | --- | --- | --- | --- |
253. J.Wolfowitz. Productsofindecomposable,aperiodic,stochasticmatrices. Pro-
ceedings of the American Mathematical Society, 15:733–736, 1963.
254. H. Wong, M. S. de Queiroz, and V. Kapila. Adaptive tracking control using
synthesized velocity from attitude measurements. Automatica, 37(6):947–953,
2001.
255. C.W.Wu.Agreementandconsensusproblemsingroupsofautonomousagents
withlineardynamics. InProceedings oftheIEEEInternational Symposiumon
| Circuits | and Systems, | pages | 292–295, | Kobe, | Japan, | 2005. |
| -------- | ------------ | ----- | -------- | ----- | ------ | ----- |
256. C. W. Wu. Synchronization and convergence of linear dynamics in random
directednetworks.IEEETransactionsonAutomaticControl,51(7):1207–1210,
July 2006.
257. W. Xi, X. Tan, and J. S. Baras. Gibbs sampler-based coordination of au-
| tonomous | swarms. | Automatica, |     | 42(7):1107–1119, | 2006. |     |
| -------- | ------- | ----------- | --- | ---------------- | ----- | --- |
258. F. Xiao and L. Wang. State consensus for multi-agent systems with switch-
ing topologies and time-varying delays. International Journal of Control,
| 79(10):1277–1284, |     | October | 2006. |     |     |     |
| ----------------- | --- | ------- | ----- | --- | --- | --- |
259. L.Xiao and S.Boyd. Fast linear iterations for distributedaveraging. Systems
| and Control | Letters, | 53(1):65–78, |     | 2004. |     |     |
| ----------- | -------- | ------------ | --- | ----- | --- | --- |
260. L. Xiao, S. Boyd, and S. Lall. A scheme for robust distributed sensor fusion
basedonaverageconsensus. InProceedings ofthe International Conference on
Information Processing in Sensor Networks, pages 63–70, Los Angeles, April
2005.
261. G. Xie and L. Wang. Consensus control for a class of networks of dynamic
agents.InternationalJournalofRobustandNonlinearControl,17(10–11):941–
959, July 2007.
262. O. A. Yakimenko. Direct method for rapid prototyping of near-optimal air-
crafttrajectories. JournalofGuidance,Control,andDynamics,23(5):865–875,
| September–October |     | 2000. |     |     |     |     |
| ----------------- | --- | ----- | --- | --- | --- | --- |
263. H.Yamaguchi. Adaptiveformation controlfordistributedautonomousmobile
robotgroups.InProceedingsoftheIEEEInternationalConferenceonRobotics
| and Automation, |     | pages | 2300–2305, | Albuquerque,NM, |     | April 1997. |
| --------------- | --- | ----- | ---------- | --------------- | --- | ----------- |
264. H. Yamaguchi and J. W. Burdick. Asymptotic stabilization of multiple non-
holonomicmobilerobotsforminggroupformations. InProceedingsoftheIEEE
International Conference on Robotics and Automation, pages 3573–3580, Leu-
| ven,Belgium, | May | 1998. |     |     |     |     |
| ------------ | --- | ----- | --- | --- | --- | --- |
265. Q. Yan,G. Yang, V. Kapila, and M. S. de Queiroz. Nonlinear dyanamics and
adaptive control of multiple spacecraft in periodic relative orbits. In Proceed-
ings of the 23rd Annual AAS Guidance and Control Conference, pages AAS
| 00–013, | Breckenridge, | CO, | February | 2000. |     |     |
| ------- | ------------- | --- | -------- | ----- | --- | --- |
266. G.YangandV.Kapila. Optimalpathplanningforunmannedairvehicleswith
kinematic and tactical constraints. In Proceedings of the IEEE Conference on
| Decision | and Control, | pages | 1301–1306, |     | Las Vegas, | NV,2002. |
| -------- | ------------ | ----- | ---------- | --- | ---------- | -------- |

References 315
267. B.Young,R.W.Beard,andJ.Kelsey. Acontrolschemeforimprovingmulti-
vehicleformation maneuvers. InProceedings of the American Control Confer-
| ence, Arlington, | VA, June2001. |     |     |     |
| ---------------- | ------------- | --- | --- | --- |
268. C. Yu, J. M. Hendrickx, B. Fidan, B. D. O. Anderson, and V. D. Blondel.
Three and higher dimensional autonomous formations: Rigidity, persistence
| and structural | persistence. | Automatica, | 43(3):387–402, | 2007. |
| -------------- | ------------ | ----------- | -------------- | ----- |
269. X.Yun,G.Alptekin,andO.Albayrak.Lineandcircleformationofdistributed
physical mobile robots. Journal of Robotic Systems, 14(2):63–76, 1997.

Index
| (cid:15)-cooperation, | 165         |             |          | consensus    | algorithm,      |               | 6, 26, 78 |     |
| --------------------- | ----------- | ----------- | -------- | ------------ | --------------- | ------------- | --------- | --- |
|                       |             |             |          | consensus    | controller,     | 183           |           |     |
| actuator              | saturation, | 216         |          | consensus    | equilibrium,    |               | 10, 33,   | 90  |
| adjacency             | matrix,     | 7, 25, 56,  | 78, 105, |              |                 |               |           |     |
|                       |             |             |          | consensus    | error,          | 234           |           |     |
| 124,                  | 141, 282    |             |          | consensus    | reference       | state,        | 56        |     |
| asymptotically        | stable,     | 294         |          | consensus    | tracking,       | 56            |           |     |
| asynchronous          | consensus,  | 15          |          | consensus    | tracking        | algorithm,    |           | 61  |
| attitudealignment,    |             | 123         |          |              |                 |               |           |     |
|                       |             |             |          | consensus    | tracking        | performance   |           |     |
| attitudeconsensus,    |             | 123         |          |              |                 |               |           |     |
|                       |             |             |          | function,    |                 | 69            |           |     |
| attitudedynamics,     |             | 290         |          |              |                 |               |           |     |
|                       |             |             |          | contain a    | directed        | spanningtree, |           | 282 |
| attitudeerror,        | 290         |             |          | contraction  | theory,         | 14            |           |     |
| average consensus,    |             | 11, 34      |          | cooperation, | 161             |               |           |     |
| average coordination  |             | error,      | 242      |              |                 |               |           |     |
|                       |             |             |          | cooperation  | algorithm,      |               | 166       |     |
| axial alignment,      |             | 184         |          |              |                 |               |           |     |
|                       |             |             |          | cooperation  | constraints,    |               | 160       |     |
|                       |             |             |          | cooperation  | objective,      |               | 165       |     |
| balanced              | graph,      | 11, 34, 282 |          |              |                 |               |           |     |
|                       |             |             |          | cooperative  | control,        | 3,            | 161       |     |
| Barbalat’s            | lemma,      | 296         |          |              |                 |               |           |     |
|                       |             |             |          | cooperative  | identification, |               | 268       |     |
| behavioral            | approach,   | 175         |          |              |                 |               |           |     |
|                       |             |             |          | cooperative  | path            | planning,     | 177       |     |
BIBO, 294
|         |         |           |         | cooperative | surveillance, |     | 268 |     |
| ------- | ------- | --------- | ------- | ----------- | ------------- | --- | --- | --- |
| bounded | control | input,66, | 96, 117 |             |               |     |     |     |
|         |         |           |         | cooperative | timing,       | 177 |     |     |
bounded-input,bounded-outputstable,
|     |     |     |     | cooperative | tracking, |     | 258 |     |
| --- | --- | --- | --- | ----------- | --------- | --- | --- | --- |
294
|                |     |               |         | coordination | function,    |     | 160, 166 |     |
| -------------- | --- | ------------- | ------- | ------------ | ------------ | --- | -------- | --- |
| bounded-input, |     | bounded-state | stable, |              |              |     |          |     |
|                |     |               |         | coordination | information, |     | 4        |     |
294
|               |              |               |     | coordination  | variable,    |     | 4, 160,        | 165 |
| ------------- | ------------ | ------------- | --- | ------------- | ------------ | --- | -------------- | --- |
|               |              |               |     | coordination  | variable     |     | instantiation, | 168 |
| centralized   | coordination | architecture, |     |               |              |     |                |     |
| 228           |              |               |     | cross-product | operator,    |     | 289            |     |
| centralized   | strategy,    | 166           |     | cycle, 281    |              |     |                |     |
| child node,   | 281          |               |     |               |              |     |                |     |
| class KL,     | 296          |               |     | decentralized | coordination |     | architecture,  |     |
| class K, 296  |              |               |     | 230           |              |     |                |     |
| class K ∞,296 |              |               |     | decision      | variable,    | 164 |                |     |
connected, 9, 34, 131, 281 directed graph, 7, 25, 56, 78, 105, 281
| consensus, | 6, 26, | 78  |     | directed | graph | of a matrix, | 283 |     |
| ---------- | ------ | --- | --- | -------- | ----- | ------------ | --- | --- |

318 Index
directed Laplacian matrix, 283 information control input,26, 78
| directed    | path,281      |     |     |     | information            | feedback, | 68          |     |
| ----------- | ------------- | --- | --- | --- | ---------------------- | --------- | ----------- | --- |
| directed    | spanningtree, |     | 282 |     | information            | state,    | 6, 26, 78   |     |
| directed    | tree, 281     |     |     |     | information            | state     | derivative, | 78  |
| distributed | coordination, |     | 21  |     | input-outputstability, |           | 294         |     |
distributed fire monitoring algorithm, input-to-statestable, 36, 296
| 253                 |        |           |            |     | interaction      | topology,     | 25, 56,       | 78, 105, |
| ------------------- | ------ | --------- | ---------- | --- | ---------------- | ------------- | ------------- | -------- |
| double-integrator   |        | dynamics, | 78         |     | 124,             | 141           |               |          |
| dwell time,         | 12,    | 45        |            |     | internal         | dynamics,     | 209           |          |
| dynamicconsensus,   |        | 35        |            |     | internal         | stability,    | 293           |          |
| dynamiccoupling,    |        | 163       |            |     | invariant        | set, 295      |               |          |
|                     |        |           |            |     | irreducible      | matrix,       | 285           |          |
| edge, 281           |        |           |            |     | ISS,36,          | 49, 168,      | 296           |          |
| edge set,           | 7, 25, | 56, 78,   | 105, 281   |     |                  |               |               |          |
|                     |        |           |            |     | Kestrel          | autopilot,    | 265           |          |
| Euler angle,        | 289    |           |            |     |                  |               |               |          |
|                     |        |           |            |     | Kuramoto         | model,        | 16            |          |
| Euler axis,         | 289    |           |            |     |                  |               |               |          |
| Euler parameters,   |        | 289       |            |     |                  |               |               |          |
|                     |        |           |            |     | Laplacian        | matrix,       | 124, 283      |          |
|                     |        |           |            |     | latency          | minimization, | 251           |          |
| fastest distributed |        | linear    | averaging, | 15  |                  |               |               |          |
|                     |        |           |            |     | leader-following |               | approach, 174 |          |
FDLA,15
|                 |                |     |     |     | leader-following |               | strategy, 113 |     |
| --------------- | -------------- | --- | --- | --- | ---------------- | ------------- | ------------- | --- |
| feedback        | linearization, |     | 208 |     |                  |               |               |     |
|                 |                |     |     |     | linear state     | equation,     | 293           |     |
| firemodel,      | 257            |     |     |     |                  |               |               |     |
|                 |                |     |     |     | linear time      | invariant,293 |               |     |
| firemonitoring, |                | 248 |     |     |                  |               |               |     |
|                 |                |     |     |     | linear time      | varying,293   |               |     |
flocking, 20
|           |                |               |          |     | load balancing      |         | algorithm, 254 |     |
| --------- | -------------- | ------------- | -------- | --- | ------------------- | ------- | -------------- | --- |
| follower, | 56, 105,       | 143           |          |     |                     |         |                |     |
|           |                |               |          |     | local coordination, |         | 159            |     |
| formation | control,       | 174           |          |     |                     |         |                |     |
|           |                |               |          |     | local coupling,     |         | 162            |     |
| formation | control        | architecture, |          | 194 |                     |         |                |     |
|           |                |               |          |     | Local InvarianceSet |         | Theorem,       | 295 |
| formation | feedback,      | 229,          | 231, 235 |     |                     |         |                |     |
|           |                |               |          |     | LTI, 293            |         |                |     |
| formation | frame,         | 226           |          |     |                     |         |                |     |
|           |                |               |          |     | LTV, 293            |         |                |     |
| formation | keeping        | behavior,     | 212      |     |                     |         |                |     |
|           |                |               |          |     | Lyapunov-likelemma, |         | 296            |     |
| formation | maneuver,      |               | 19, 209  |     |                     |         |                |     |
| formation | pattern,       | 209           |          |     |                     |         |                |     |
|           |                |               |          |     | marginally          | stable, | 294            |     |
| formation | stabilization, |               | 18       |     |                     |         |                |     |
MASnet,181
| full access,   | 112, | 144 |     |     | meet-for-dinner |           | problem, 4  |      |
| -------------- | ---- | --- | --- | --- | --------------- | --------- | ----------- | ---- |
| full coupling, | 162  |     |     |     | modified        | Rodriguez | parameters, | 147, |
290
| Gershgorin’s         | disc       | theorem,  | 285      |     |                |             |                      |     |
| -------------------- | ---------- | --------- | -------- | --- | -------------- | ----------- | -------------------- | --- |
|                      |            |           |          |     | MRP, 147,      | 290         |                      |     |
| global coordination, |            | 159       |          |     |                |             |                      |     |
|                      |            |           |          |     | multiplicative |             | identity quaternion, | 289 |
| Global InvarianceSet |            |           | Theorem, | 296 | multivehicle   | systems,    | 3                    |     |
| goal seeking         | behavior,  |           | 212      |     |                |             |                      |     |
| goal seeking         | error,     | 234       |          |     | neighbor,      | 281         |                      |     |
| graph rigidity       |            | approach, | 176      |     | node, 281      |             |                      |     |
| group-level          | reference, |           | 170      |     | node set,      | 7, 25,      | 56, 78, 105,         | 281 |
|                      |            |           |          |     | nonlinear      | oscillator, | 16                   |     |
| hand position,       |            | 198       |          |     | nonnegative    | matrix,     | 286                  |     |
has a directed spanningtree, 9, 28, 282 nonnegative vector, 286
| higher-order | dynamics, |     | 16  |     | nonsmooth      | gradient | flow, 16          |     |
| ------------ | --------- | --- | --- | --- | -------------- | -------- | ----------------- | --- |
|              |           |     |     |     | nonsymmetrical |          | Laplacian matrix, | 8,  |
| in-degree    | matrix,   | 283 |     |     | 25,            | 56, 78,  | 106, 283          |     |

Index 319
| objective        | coupling,   | 162      |          | situational      | state,         | 164      |             |
| ---------------- | ----------- | -------- | -------- | ---------------- | -------------- | -------- | ----------- |
|                  |             |          |          | spacecraft       | formation      |          | flying, 225 |
| parent node,     | 281         |          |          | static           | consensus,     | 28       |             |
| partial access,  |             | 145      |          |                  |                |          |             |
|                  |             |          |          | stochastic       | indecomposable |          | and         |
| passivity        | approach,   | 100,     | 128, 215 |                  | aperiodic,     | 286      |             |
| path planning,   |             | 177      |          | stochastic       | stability,     | 14       |             |
| perimeter        | tracking,   | 250,     | 257      | strongly         | connected,     | 9,       | 33, 281     |
| Perron-Frobenius |             | theorem, | 286      |                  |                |          |             |
|                  |             |          |          | subgraph,        | 282            |          |             |
| persistent       | imaging,    | 268      |          |                  |                |          |             |
|                  |             |          |          | subgroup         | leader,        | 56       |             |
| perturbation     | term,       | 35       |          |                  |                |          |             |
|                  |             |          |          | synchronization, |                | 16       |             |
| place holder,    | 227         |          |          |                  |                |          |             |
| position         | controller, | 183      |          | team             | leader,        | 56, 105, | 143         |
| positive         | matrix,     | 286      |          |                  |                |          |             |
|                  |             |          |          | time             | delay, 14      |          |             |
| positive         | vector,     | 286      |          |                  |                |          |             |
|                  |             |          |          | tracking         | performance,   |          | 235         |
| positively       | invariant   | set,     | 295      |                  |                |          |             |
|                  |             |          |          | transition       | matrix,        | 293      |             |
| primitive,       | 286         |          |          | tree,            | 125, 281       |          |             |
| pseudo-GPS,      | 181         |          |          | type,286         |                |          |             |
| quaternion,      | 289         |          |          |                  |                |          |             |
|                  |             |          |          | undirected       | graph,         | 124,     | 141, 281    |
| quaternion       | conjugate,  | 289      |          |                  |                |          |             |
|                  |             |          |          | undirected       | path,          | 281      |             |
|                  |             |          |          | undirected       | spanning       |          | tree, 282   |
radially unbounded,296
| reducible   | matrix,           | 285          |        | uniformly | asymptotically |        | stable, 294 |
| ----------- | ----------------- | ------------ | ------ | --------- | -------------- | ------ | ----------- |
|             |                   |              |        | uniformly | exponentially  |        | stable, 294 |
| reference   | attitudedynamics, |              | 143    |           |                |        |             |
|             |                   |              |        | uniformly | stable,        | 294    |             |
| reference   | attitudetracking, |              | 143    |           |                |        |             |
|             |                   |              |        | union,    | 43, 281        |        |             |
| reference   | model,            | 105          |        |           |                |        |             |
|             |                   |              |        | unit      | quaternion,    | 289    |             |
| relative    | attitude,         | 142          |        |           |                |        |             |
| relative    | attitude          | maintenance, | 141    |           |                |        |             |
|             |                   |              |        | Vicsek    | model,         | 27     |             |
| relative    | degree,           | 208          |        |           |                |        |             |
|             |                   |              |        | virtual   | center,        | 193    |             |
| relative    | state deviations, |              | 35, 71 |           |                |        |             |
|             |                   |              |        | virtual   | cockpit,       | 265    |             |
| rendezvous, | 18,               | 183          |        |           |                |        |             |
| root, 281   |                   |              |        | virtual   | coordinate     | frame, | 193         |
Routh stability criterion, 30 virtual leader approach, 176, 193
row-stochastic matrix, 8, 26, 286 virtual structure approach, 176, 193,
226
|                   |                   |           |     | virtual  | structureframe, |     | 226 |
| ----------------- | ----------------- | --------- | --- | -------- | --------------- | --- | --- |
| scrambling        | matrix,           | 286       |     |          |                 |     |     |
| semidefinite      | program,          | 15        |     |          |                 |     |     |
| set-valued        | Lyapunovfunction, |           | 13  | weighted | graph,          | 281 |     |
| set-valued        | Lyapunovtheory,13 |           |     |          |                 |     |     |
| SIA,12,           | 41, 286           |           |     | Zagi     | airframe,       | 265 |     |
| single-integrator |                   | dynamics, | 25  | zero     | dynamics,       | 209 |     |